---
description: エッジ (クロム) 拡張機能のコンテンツ セキュリティ ポリシー。
title: コンテンツ セキュリティ ポリシー (CSP)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, パートナー センター, 開発者
ms.openlocfilehash: 8307482e780b4d631edffd976cca7ba724e2ad40
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397518"
---
# <a name="content-security-policy-csp"></a>コンテンツ セキュリティ ポリシー \(CSP\)  

潜在的なクロスサイト スクリプティングの問題の大規模なクラスを軽減するために、Microsoft Edge Extension システムはコンテンツ セキュリティ ポリシー [\(CSP\)][W3CContentSecurityPolicy]の一般的な概念を組み込んだ。  これにより、拡張機能のセキュリティを既定で高めるかなり厳格なポリシーが導入され、拡張機能とアプリケーションによって読み込まれ、実行される可能性のあるコンテンツの種類を管理するルールを作成および適用できます。  

一般に、CSP は拡張機能によって読み込まれた、または実行されるリソースのブロック/許可リストメカニズムとして機能します。  拡張機能の適切なポリシーを定義すると、拡張機能で必要なリソースを慎重に検討し、拡張機能がアクセスできる唯一のリソースをブラウザーに確認することができます。  ポリシーは、拡張機能が要求するホストのアクセス許可以上のセキュリティを提供します。これらは、代替ではなく、保護の追加の層です。  

Web では、このようなポリシーは HTTP ヘッダーまたは要素を介して定義 `meta` されます。  Microsoft Edge Extension システム内では、どちらも適切なメカニズムとは言えな  代わりに、拡張機能ポリシーは、拡張機能のファイルを使用 `manifest.json` して次のように定義されます。  

```javascript
{
    ...,
    "content_security_policy": "[POLICY STRING GOES HERE]"
    ...
}
```  

> CSP 構文の詳細については、HTML5Rocks の「コンテンツ[][W3CContentSecurityPolicy]セキュリティ ポリシーの仕様」[][HTML5RocksIntroductionContentSecurityPolicy]と「コンテンツ セキュリティ ポリシーの概要」を参照してください。  

## <a name="default-policy-restrictions"></a>既定のポリシー制限  

a を定義しないパッケージ `manifest_version` には、既定のコンテンツ セキュリティ ポリシーが適用されません。  `manifest_version`2 を選択するパッケージには、次の既定のコンテンツ セキュリティ ポリシーがあります。  

```javascript
script-src 'self'; object-src 'self'
```  

このポリシーは、拡張機能とアプリケーションを次の 3 つの方法で制限することでセキュリティを強化します。  

**Eval および関連する関数が無効になっている**  

次のようなコードは機能しません。  

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

インライン JavaScript は実行されません。  この制限は、インライン ブロックとインライン `<script>` イベント ハンドラーの両方 (など) を禁止します `<button onclick="...">` 。

最初の制限では、悪意のあるサード パーティによって提供されるスクリプトを誤って実行することは不可能にすることで、クロスサイト スクリプティング攻撃の巨大なクラスを一掃します。  ただし、コンテンツと動作の間でクリーンな分離を使用してコードを記述する必要があります 。もちろん、これはもちろん行う必要があります。正しいですか?\)。  たとえば、これを明確にする場合があります。  ブラウザー アクション のポップアップは、次を含む 1 つのポップアップとして `pop-up.html` 記述できます。  

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

この動作を期待通りに行うには、次の 3 つの点が変更される必要があります。  

*   定義 `clickHandler` は、外部 JavaScript ファイル \( に移動する必要 `popup.js` があります。  
*   インライン イベント ハンドラーの定義は、 という点で書き換え、 `addEventListener` に抽出する必要があります `popup.js` 。  
    現在、コードを使用してプログラムを開始している場合は、要件に応じて、ドキュメントのイベントまたはウィンドウのイベントにフックして置き換え検討 `<body onload="main();">` `DOMContentLoaded` `load` してください。  一般にトリガーが速く行うので、前者を使用します。  

*   文字列を JavaScript に変換して実行しないように、呼び出し `setTimeout` `"awesome(); totallyAwesome()"` を書き換えする必要があります。  
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

**ローカル スクリプトとオブジェクト リソースだけが読み込まれる**  

スクリプトリソースとオブジェクト リソースは、拡張機能パッケージからしか読み込めることはできません。Web からのみ読み込む必要があります。  これにより、拡張機能は、特に承認したコードのみを実行し、アクティブなネットワーク攻撃者がリソースの要求を悪意を持ってリダイレクトするのを防ぐことを保証します。  

外部 CDN からの jQuery \(または他のライブラリ\) の読み込みに依存するコードを記述する代わりに、拡張機能パッケージに特定のバージョンの jQuery を含めて検討してください。  つまり、次の代わりに次の値を使用します。  

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

ファイルをダウンロードし、パッケージに含め、次の値を記述します。  

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

## <a name="relaxing-the-default-policy"></a>既定のポリシーをリラックスする  

**インライン スクリプト**  

<!-- Up until Chrome 45, there was no mechanism for relaxing the restriction against running inline JavaScript.  In particular, setting a script policy that includes `'unsafe-inline'` has no effect.  

As of Chrome 46, -->  

インライン スクリプトは、ポリシーでソース コードの base64 エンコードハッシュを指定することで許可できます。  このハッシュの先頭には、使用するハッシュ アルゴリズム \(sha256、sha384、sha512\) を付ける必要があります。  たとえば、要素のハッシュ使用法 [に \<script\> 移動します][W3CContentSecurityPolicyLevel2ScriptSrcHashUsage]。  

**リモート スクリプト**  

外部 JavaScript またはオブジェクト リソースが必要な場合は、スクリプトを受け入れるセキュリティで保護された起点を許可することで、ポリシーを制限された範囲でリラックスできます。  拡張機能の昇格されたアクセス許可で読み込まれたランタイム リソースが、期待するリソースであり、アクティブなネットワーク攻撃者に置き換えることはできません。  中間 [者による攻撃][WikiManMiddleAttacks] は、HTTP 上では簡単で検出できないので、それらの発生元は受け入れなされません。  

現在、開発者は、次のスキームを使用して、オリジンを許可 `blob` できます。 `filesystem` `https` `extension`  オリジンのホスト 部分は、and スキームに対して明示的に `https` 指定する `extension` 必要があります。  https:など、一般的なワイルドカードは許可されません。サブドメインのワイルドカード `https://*` `https://*.com` (許可 `https://*.example.com` されている場合など)。  [パブリック サフィックス] [リストのドメインは][PublicSuffixList] 、汎用のトップ レベル ドメインとして表示されます。  これらのドメインからリソースを読み込むには、サブドメインを明示的に一覧表示する必要があります。  たとえば、 `https://*.cloudfront.net` 無効ですが、 `https://XXXX.cloudfront.net` `https://*.XXXX.cloudfront.net` 可能です `allowlisted` 。  

開発を容易にするために、ローカル コンピューター上のサーバーから HTTP を使用して読み込まれるリソースを使用できます `allowlisted` 。  スクリプトとオブジェクト ソースは、いずれかのポートで許可 `http://127.0.0.1` できます `http://localhost` 。  

> [!NOTE]
> HTTP を使用して読み込まれるリソースに対する制限は、直接実行されるリソースにのみ適用されます。  たとえば、任意のオリジンへの接続を行う場合、既定のポリシーでは制限も他の CSP ディレクティブも制限 `XMLHTTPRequest` `connect-src` されません。  

HTTPS 経由でスクリプト リソースを読み込むリラックスしたポリシー定義は `example.com` 、次のような場合があります。  

```javascript
"content_security_policy": "script-src 'self' https://example.com; object-src 'self'"
```  

> [!NOTE]
> 両方 `script-src` とも `object-src` 、ポリシーによって定義されます。  Microsoft Edge では、これらの各値を \(少なくとも\) ' 'に制限しないポリシーは受け入 `self` れかねない。  

<!-- Making use of Google Analytics is the canonical example for this sort of policy definition.  It is common enough that an Analytics boilerplate of sorts is provided in the Event Tracking with Google Analytics sample Extension, and a brief tutorial that goes into more detail.  -->  

**評価された JavaScript**  

ポリシーに対 `eval()` するポリシーと関連する関数 (、、など) は、ポリシーに追加することで `setTimeout(String)` `setInterval(String)` `new Function(String)` `unsafe-eval` 緩和できます。  

```javascript
"content_security_policy": "script-src 'self' 'unsafe-eval'; object-src 'self'"
```  

ただし、ポリシーのリラックスは避ける必要があります。  関数は悪名高い XSS 攻撃ベクトルです。  

## <a name="tightening-the-default-policy"></a>既定のポリシーの強化  

もちろん、利便性を犠牲にしてセキュリティを強化するために、拡張機能が許可する範囲でこのポリシーを強化することができます。  関連付けられた拡張パッケージから任意の種類の \(images など)のリソースのみを読み込み可能にするように指定するには、ポリシーが適切な `default-src 'self'` 場合があります。  

<!-- The Mappy sample Extension is a good example of an Extension that is been locked down above and beyond the defaults.  -->  

## <a name="content-scripts"></a>コンテンツ スクリプト  

説明するポリシーは、拡張機能のバックグラウンド ページとイベント ページに適用されます。  拡張機能のコンテンツ スクリプトにコンテンツ スクリプトを適用する方法は、より複雑です。  

コンテンツ スクリプトは、通常、拡張機能の CSP の対象ではありません。  コンテンツ スクリプトは HTML ではなからないので、拡張機能の CSP が指定されていない場合でも使用できる場合が主な影響ですが、これは `eval` `unsafe-eval` お勧めしません。  さらに、ページの CSP はコンテンツ スクリプトには適用されません。  さらに複雑になる `<script>` のは、コンテンツ スクリプトが作成し、実行しているページの DOM に入れるタグです。  これらは、今後 DOM によって挿入されるスクリプトとして参照されます。  

ページに挿入するとすぐに実行される DOM によって挿入されたスクリプトは、予想通り実行されます。  簡単な例として、次のコードを含むコンテンツ スクリプトを想像してください。  

```javascript
document.write("<script>alert(1);</script>");
 ```  

このコンテンツ スクリプトは、 の `alert` 直後に発生します `document.write()` 。  これは、ページで指定できるポリシーに関係なく実行されます。
ただし、DOM によって挿入されたスクリプトの内部と、挿入時にすぐに実行されないスクリプトの両方で、動作が複雑になります。  指定する関連付けられた CSP を提供するページで拡張機能が実行されているとします `script-src 'self'` 。  次に、コンテンツ スクリプトが次のコードを実行するとします。  

```javascript
document.write("<button onclick='alert(1);'>click me</button>'");
```  

ユーザーがボタンを選択した場合、 `onclick` スクリプトは実行されません。  これは、スクリプトがすぐに実行され、イベントが発生するまでコードが解釈されないので、コンテンツ スクリプトの一部と見なされないので、ページ \(Extension\ではない) の CSP は動作を `click` 制限します。  また、CSP が指定していないの `unsafe-inline` で、インライン イベント ハンドラーはブロックされます。  
この場合、目的の動作を実装する正しい方法は、次のようにコンテンツ スクリプトからハンドラーを関数として `onclick` 追加する方法です。  

```javascript
document.write("<button id='mybutton'>click me</button>'");
var button = document.getElementById('mybutton');
button.onclick = function() {
      alert(1);
};
```  

コンテンツ スクリプトで次のような問題が発生します。  

```javascript
var script = document.createElement('script');
script.innerHTML = 'alert(1);'
document.getElementById('body').appendChild(script);
```  

この場合、スクリプトが実行され、アラートが表示されます。  ただし、次の場合に使用します。  

```javascript
var script = document.createElement('script');
script.innerHTML = 'eval("alert(1);")';
=document.getElementById('body').appendChild(script);
```  

最初のスクリプトの実行中、呼び出し `eval` はブロックされます。  つまり、最初のスクリプト ランタイムが許可されている間、スクリプト内の動作はページの CSP によって規制されます。  
したがって、拡張機能に DOM 挿入スクリプトを記述する方法によっては、ページの CSP に対する変更が拡張機能の動作に影響を与える可能性があります。  コンテンツ スクリプトはページの CSP の影響を受けかねないので、DOM によって挿入されたスクリプトではなく、拡張機能の可能な限り多くの動作をコンテンツ スクリプトに入れる大きな理由です。  

<!-- image links -->  

<!-- links -->  

[HTML5RocksIntroductionContentSecurityPolicy]: https://www.html5rocks.com/en/tutorials/security/content-security-policy "コンテンツ セキュリティ ポリシーの概要|HTML5 ロック"  
[PublicSuffixList]: https://publicsuffix.org/list "パブリック サフィックス の一覧を表示する"  
[W3CContentSecurityPolicyLevel2ScriptSrcHashUsage]: https://www.w3.org/TR/CSP2#script-src-hash-usage "\<script\>要素のハッシュ使用法 - コンテンツ セキュリティ ポリシー レベル 2 |W3C"  
[W3CContentSecurityPolicy]: https://w3c.github.io/webappsec-csp "コンテンツ セキュリティ ポリシー レベル 3 |W3C"  
[WikiManMiddleAttacks]: https://en.wikipedia.org/wiki/Man-in-the-middle_attack "中間者攻撃|Wikipedia"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページは次 [のページに表示されます](https://developer.chrome.com/extensions/contentSecurityPolicy)。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
