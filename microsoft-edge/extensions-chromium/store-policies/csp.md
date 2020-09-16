---
description: Edge (Chromium) 拡張機能のコンテンツセキュリティポリシー。
title: コンテンツセキュリティポリシー (CSP)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者
ms.openlocfilehash: f3769639465d048c42ad0705f74598fbd1db8a20
ms.sourcegitcommit: d360e419b5f96f4f691cf7330b0d8dff9126f82e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015717"
---
# コンテンツセキュリティポリシー \ (CSP \)  

大量の潜在的なクロスサイトスクリプティングの問題を軽減するために、Microsoft Edge 拡張システムには、 [コンテンツセキュリティポリシー \ (CSP \)][W3CContentSecurityPolicy]の一般的な概念が組み込まれています。  これにより、既定で拡張機能の安全性を高めるための厳格なポリシーがいくつか導入され、拡張機能やアプリケーションで読み込みと実行が可能なコンテンツの種類を管理するためのルールを作成して適用することができます。  

一般的に、CSP は、拡張機能によって読み込みまたは実行されるリソースのブロック/allowlisting 機構として機能します。  拡張機能に適したポリシーを定義することで、拡張機能に必要なリソースを慎重に検討し、拡張機能によってアクセスできる唯一のリソースかどうかをブラウザーに確認することができます。  これらのポリシーは、拡張要求に対するホストのアクセス許可よりも、セキュリティを提供します。これは、保護の追加レイヤーであり、置き換えるものではありません。  

Web 上のポリシーは、HTTP ヘッダーまたは要素によって定義され `meta` ます。  Microsoft Edge Extension システムでは、どちらも適切なメカニズムではありません。  代わりに、拡張ポリシーは、次のように拡張子のファイルを通じて定義され `manifest.json` ます。  

```javascript
{
    ...,
    "content_security_policy": "[POLICY STRING GOES HERE]"
    ...
}
```  

> CSP の構文について詳しくは、「 [コンテンツセキュリティポリシーの仕様][W3CContentSecurityPolicy] 」と「HTML5Rocks の [「コンテンツセキュリティポリシーの概要」][HTML5RocksIntroductionContentSecurityPolicy] をご覧ください。  

## 既定のポリシーの制限  

が定義されていないパッケージには、 `manifest_version` 既定のコンテンツセキュリティポリシーがありません。  2を選択した `manifest_version` 場合は、次のような既定のコンテンツセキュリティポリシーが設定されます。  

```javascript
script-src 'self'; object-src 'self'
```  

このポリシーでは、次の3つの方法で拡張機能とアプリケーションを制限して、セキュリティを強化します。  

**Eval 関数と関連関数が無効になっている**  

次のようなコードは動作しません。  

```javascript
alert(eval("foo.bar.baz"));
window.setTimeout("alert('hi')", 10);
window.setInterval("alert('hi')", 10);
new Function("return foo.bar.baz");
```  

このような JavaScript の文字列の評価は、一般的な XSS 攻撃ベクトルです。  代わりに、次のようなコードを記述する必要があります。

```javascript
alert(foo && foo.bar && foo.bar.baz);
window.setTimeout(function() { alert('hi'); }, 10);
window.setInterval(function() { alert('hi'); }, 10);
function() { return foo && foo.bar && foo.bar.baz };
```  

**インライン JavaScript が実行されない**  

インライン JavaScript は実行されません。  この制限 `<script>` は、インラインブロックとインラインイベントハンドラー (など) の両方を禁止し `<button onclick="...">` ます。

1つ目の制限では、悪意のあるサードパーティによって提供されたスクリプトを誤って実行することは不可能であるため、大量のクロスサイトスクリプト攻撃を消去しています。  ただし、コンテンツと動作の間の明確な分離を使用してコードを記述する必要があります (もちろん、実際にはこの方法で実行する必要があります)。  例としては、この方法がわかりやすくなっています。  次の内容を含む単一のブラウザーアクションポップアップとして作成することができ `pop-up.html` ます。  

```html
<!doctype html>
<html>
    <head>
        <title>My Awesome Pop-up!</title>
        <script>
            function awesome() {
                // do something awesome!
            }
            
            function totallyAwesome() {
                // do something TOTALLY awesome!
            }
            
            function clickHandler(element) {
                setTimeout("awesome(); totallyAwesome()", 1000);
            }
            
            function main() {
                // Initialization work goes here.
            }
        </script>
    </head>
    <body onload="main();">
        <button onclick="clickHandler(this)">
            Click for awesomeness!
        </button>
    </body>
</html>
```  

期待どおりに動作させるためには、次の3つの項目を変更する必要があります。  

*   `clickHandler`定義は外部 JavaScript ファイルに移動する必要があり `popup.js` ます。 \ (適切なターゲットの場合があります)。  
*   インラインイベントハンドラーの定義は、のように書き換える必要があり `addEventListener` `popup.js` ます。  
    次のようなコードを使ってプログラムを起動している場合は `<body onload="main();">` 、 `DOMContentLoaded` 必要に応じて、ドキュメントのイベントまたはウィンドウのイベントにフックすることで、プログラムを置き換えることを検討してください `load` 。  通常は、前者を使用します。  

*   呼び出しは、 `setTimeout` 実行するために JavaScript に文字列を変換しないように書き換える必要があり `"awesome(); totallyAwesome()"` ます。  
    これらの変更は、次のようになります。  

```javascript
function awesome() {
    // Do something awesome!
}

function totallyAwesome() {
    // do something TOTALLY awesome!
}

function awesomeTask() {
    awesome();
    totallyAwesome();
}

function clickHandler(e) {
    setTimeout(awesomeTask, 1000);
}

function main() {
    // Initialization work goes here.
}

// Add event listeners once the DOM has fully loaded by listening for the
// `DOMContentLoaded` event on the document, and adding your listeners to
// specific elements when it triggers.
document.addEventListener('DOMContentLoaded', function () {
    document.querySelector('button').addEventListener('click', clickHandler);
    main();
});
```  

```html
<!doctype html>
<html>
    <head>
        <title>My Awesome Pop-up!</title>
        <script src="popup.js"></script>
    </head>
    <body>
        <button>Click for awesomeness!</button>
    </body>
</html>
```  

**ローカルスクリプトとオブジェクトリソースのみが読み込まれます。**  

スクリプトとオブジェクトのリソースは、拡張パッケージからのみ読み込むことができます。これは、web からは大きくできません。  これにより、お客様が明示的に承認したコードのみが実行され、アクティブなネットワーク攻撃者によるリソースの要求の不正なリダイレクトを防ぐことができます。  

JQuery \ (または他のライブラリ \) で外部 CDN から読み込みを行うコードを記述する代わりに、拡張機能パッケージに jQuery の特定のバージョンを含めることを検討してください。  これは、次のようになります。  

```html
<!doctype html>
<html>
    <head>
        <title>My Awesome Pop-up!</title>
        <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.7.1/jquery.min.js"></script>
    </head>
    <body>
        <button>Click for awesomeness!</button>
    </body>
</html>
```  

ファイルをダウンロードして、パッケージに含め、次のように書き込みます。  

```html
<!doctype html>
<html>
    <head>
        <title>My Awesome Pop-up!</title>
        <script src="jquery.min.js"></script>
    </head>
    <body>
        <button>Click for awesomeness!</button>
    </body>
</html>
```  

## 既定のポリシーの緩和  

**インラインスクリプト**  

<!-- Up until Chrome 45, there was no mechanism for relaxing the restriction against running inline JavaScript.  In particular, setting a script policy that includes `'unsafe-inline'` has no effect.  

As of Chrome 46, -->  

インラインスクリプトを許可するには、ポリシーのソースコードの base64 でエンコードされたハッシュを指定します。  このハッシュのプレフィックスは、使用されているハッシュアルゴリズム \ (sha256、sha384、または sha512 \) である必要があります。  例については、「 [ \<script\> 要素のハッシュの使用状況][W3CContentSecurityPolicyLevel2ScriptSrcHashUsage] 」を参照してください。  

**リモートスクリプト**  

一部の外部 JavaScript またはオブジェクトリソースを必要とする場合は、スクリプトを受け入れることができる安全な元の元によって、ポリシーを制限された範囲に緩和することができます。  拡張機能の昇格されたアクセス許可で読み込まれたランタイムリソースが、意図したリソースとまったく同じであり、アクティブなネットワーク攻撃者によって置き換えられていないことを確認します。  [Man-in-the-middle 攻撃][WikiManMiddleAttacks]は、HTTP 経由での簡単で検出できないため、これらの元は受け入れられません。  

現時点では、開発者は、、、、 `blob` `filesystem` `https` およびというスキームでオリジンを allowlist `extension` できます。  オリジンのホスト部分は、およびスキームに対して明示的に指定する必要があり `https` `extension` ます。  Https: などの一般的なワイルド `https://*` カード `https://*.com` は使用できません。たとえば、などのサブドメインワイルドカードを `https://*.example.com` 使用できます。  [パブリックサフィックスリスト][PublicSuffixList]のドメインは、一般的なトップレベルドメインとしても表示されます。  これらのドメインからリソースを読み込むには、サブドメインが明示的に表示されている必要があります。  たとえば、 `https://*.cloudfront.net` は有効ではありませんが、 `https://XXXX.cloudfront.net` `https://*.XXXX.cloudfront.net` allowlisted で指定できます。  

開発が簡単になるように、ローカルコンピューター上のサーバーから HTTP 経由で読み込まれたリソースは、allowlisted 表示されることがあります。  スクリプトとオブジェクトソースは、またはのいずれかのポートで allowlist ことができ `http://127.0.0.1` `http://localhost` ます。  

> [!NOTE]
> HTTP 経由で読み込まれたリソースに対する制限は、直接実行されるリソースに対してのみ適用されます。  たとえば、任意の起点への XMLHTTPRequest 接続を作成することもできます。既定のポリシーでは、 `connect-src` どのような方法でも他の CSP ディレクティブは制限されません。  

HTTPS 経由で example.com からスクリプトリソースを読み込むことができる緩やかなポリシー定義は、次のようになります。  

```javascript
"content_security_policy": "script-src 'self' https://example.com; object-src 'self'"
```  

> [!NOTE]
> どちらも、 `script-src` `object-src` ポリシーによって定義されます。  Microsoft Edge は、これらの各値が \ (少なくと \ \) ' ' に制限されていないポリシーを受け入れません `self` 。  

<!-- Making use of Google Analytics is the canonical example for this sort of policy definition.  It is common enough that an Analytics boilerplate of sorts is provided in the Event Tracking with Google Analytics sample Extension, and a brief tutorial that goes into more detail.  -->  

**JavaScript の評価**  

ポリシーに対して、 `eval()` およびというような関連する機能を、 `setTimeout(String)` `setInterval(String)` `new Function(String)` ポリシーに追加することによって緩和することができ `unsafe-eval` ます。  

```javascript
"content_security_policy": "script-src 'self' 'unsafe-eval'; object-src 'self'"
```  

ただし、これを行うことは強くお勧めします。  これらの関数は、XSS 攻撃ベクトルになります。  

## 既定のポリシーを強化する  

もちろん、お客様の便宜を通じてセキュリティを強化するために、延長によって許可されたあらゆるエクステントにこのポリシーを締めることができます。  拡張機能で、関連付けられている拡張パッケージ (たとえば、ポリシーが該当する場合など) の任意の種類 \ (画像など) のリソースを読み込むことができるように指定するには、次のようにし `default-src 'self'` ます。  

<!-- The Mappy sample Extension is a good example of an Extension that is been locked down above and beyond the defaults.  -->  

## コンテンツスクリプト  

ディスカッション中のポリシーは、拡張機能の背景ページとイベントページに適用されます。  コンテンツスクリプトが拡張機能のコンテンツスクリプトにどのように適用されるかは、さらに複雑になります。  

通常、コンテンツスクリプトは、拡張機能の CSP の対象にはなりません。  コンテンツスクリプトは HTML ではないため、このような影響を与えるのは、 `eval` 拡張機能の CSP で指定されていない場合でも使用できるという点です `unsafe-eval` 。ただし、これはお勧めできません。  さらに、ページの CSP はコンテンツスクリプトには適用されません。  さらに複雑なタグとして、 `<script>` コンテンツスクリプトが作成され、実行されているページの DOM に挿入されます。  これらは、DOM 注入されたスクリプトとして転送されます。  

ページへの挿入直後に実行される DOM の挿入されたスクリプトは、期待どおりに実行されます。  単純な例として、次のコードを含むコンテンツスクリプトを想像してみてください。  

```javascript
document.write("<script>alert(1);</script>");
 ```  

このコンテンツスクリプトは、のすぐにを発生させ `alert` `document.write()` ます。  これは、ページで指定されているポリシーに関係なく実行されることに注意してください。
ただし、この動作は、DOM に挿入されたスクリプトと、挿入時にすぐに実行されないスクリプトの両方で複雑になります。  拡張機能が、関連付けられている CSP を提供するページで実行されているとし `script-src 'self'` ます。  ここでは、コンテンツスクリプトで次のコードを実行します。  

```javascript
document.write("<button onclick='alert(1);'>click me</button>'");
```  

ユーザーがそのボタンをクリックした場合、 `onclick` スクリプトは実行されません。  これは、スクリプトがすぐに実行されることはなく、click イベントが発生するまではコードが解釈されないため、(拡張子 \) のページの CSP は動作を制限します。  また、CSP で指定されていないため `unsafe-inline` 、インラインイベントハンドラーはブロックされます。  
この場合、適切な動作を実装する正しい方法は、 `onclick` 次のようにコンテンツスクリプトからハンドラーを関数として追加することです。  

```javascript
document.write("<button id='mybutton'>click me</button>'");
var button = document.getElementById('mybutton');
button.onclick = function() {
      alert(1);
};
```  

コンテンツスクリプトで次の操作を実行した場合も、同様の問題が発生します。  

```javascript
var script = document.createElement('script');
script.innerHTML = 'alert(1);'
document.getElementById('body').appendChild(script);
```  

この場合、スクリプトが実行され、アラートが表示されます。  ただし、次のような場合に該当します。  

```javascript
var script = document.createElement('script');
script.innerHTML = 'eval("alert(1);")';
=document.getElementById('body').appendChild(script);
```  

初期スクリプトを実行している間、の呼び出し `eval` はブロックされます。  つまり、初期スクリプトランタイムが許可されている間、スクリプト内の動作はページの CSP によって規制されます。  
したがって、DOM に挿入されたスクリプトを拡張機能に記述する方法によっては、ページの CSP を変更すると、拡張機能の動作に影響する場合があります。  コンテンツスクリプトはページの CSP によって影響を受けることはないため、この方法では、拡張機能で可能な限り多くの動作を、DOM に挿入されたスクリプトではなくコンテンツスクリプトに含めることができます。  

<!-- image links -->  

<!-- links -->  

[HTML5RocksIntroductionContentSecurityPolicy]: https://www.html5rocks.com/en/tutorials/security/content-security-policy "コンテンツセキュリティポリシーの概要-HTML5 の岩"  
[PublicSuffixList]: https://publicsuffix.org/list "パブリックサフィックスの一覧を表示する"  
[W3CContentSecurityPolicyLevel2ScriptSrcHashUsage]: https://www.w3.org/TR/CSP2#script-src-hash-usage "\ <スクリプト \ > 要素のハッシュの使用-コンテンツセキュリティポリシーレベル2"  
[W3CContentSecurityPolicy]: https://w3c.github.io/webappsec-csp "コンテンツセキュリティポリシーレベル3"  
[WikiManMiddleAttacks]: https://en.wikipedia.org/wiki/Man-in-the-middle_attack "Man-in-the-middle 攻撃-Wikipedia (Wikipedia)"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developer.chrome.com/extensions/contentSecurityPolicy)にあります。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
