---
description: Edge (Chromium) 拡張機能のコンテンツセキュリティポリシー。
title: コンテンツセキュリティポリシー (CSP)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者
ms.openlocfilehash: 52d6d0afb38401250183788726013d521a269f06
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569540"
---
# <span data-ttu-id="13393-104">コンテンツセキュリティポリシー \ (CSP \)</span><span class="sxs-lookup"><span data-stu-id="13393-104">Content Security Policy \(CSP\)</span></span>  

<span data-ttu-id="13393-105">大量の潜在的なクロスサイトスクリプティングの問題を軽減するために、Microsoft Edge 拡張システムには、[コンテンツセキュリティポリシー \ (CSP \)][W3CContentSecurityPolicy]の一般的な概念が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="13393-105">In order to mitigate a large class of potential cross-site scripting issues, the Microsoft Edge Extension system has incorporated the general concept of [Content Security Policy \(CSP\)][W3CContentSecurityPolicy].</span></span>  <span data-ttu-id="13393-106">これにより、既定で拡張機能の安全性を高めるための厳格なポリシーがいくつか導入され、拡張機能やアプリケーションで読み込みと実行が可能なコンテンツの種類を管理するためのルールを作成して適用することができます。</span><span class="sxs-lookup"><span data-stu-id="13393-106">This introduces some fairly strict policies that make Extensions more secure by default, and provides you with the ability to create and enforce rules governing the types of content that may be loaded and run by your Extensions and applications.</span></span>  

<span data-ttu-id="13393-107">一般的に、CSP は、拡張機能によって読み込みまたは実行されるリソースのブロック/allowlisting 機構として機能します。</span><span class="sxs-lookup"><span data-stu-id="13393-107">In general, CSP works as a block/allowlisting mechanism for resources loaded or run by your Extensions.</span></span>  <span data-ttu-id="13393-108">拡張機能に適したポリシーを定義することで、拡張機能に必要なリソースを慎重に検討し、拡張機能によってアクセスできる唯一のリソースかどうかをブラウザーに確認することができます。</span><span class="sxs-lookup"><span data-stu-id="13393-108">Defining a reasonable policy for your Extension enables you to carefully consider the resources that your Extension requires, and to ask the browser to ensure that those are the only resources your Extension has access to.</span></span>  <span data-ttu-id="13393-109">これらのポリシーは、拡張要求に対するホストのアクセス許可よりも、セキュリティを提供します。これは、保護の追加レイヤーであり、置き換えるものではありません。</span><span class="sxs-lookup"><span data-stu-id="13393-109">These policies provide security over and above the host permissions your Extension requests; they are an additional layer of protection, not a replacement.</span></span>  

<span data-ttu-id="13393-110">Web 上のポリシーは、HTTP ヘッダーまたは要素によって定義され `meta` ます。</span><span class="sxs-lookup"><span data-stu-id="13393-110">On the web, such a policy is defined via an HTTP header or `meta` element.</span></span>  <span data-ttu-id="13393-111">Microsoft Edge Extension システムでは、どちらも適切なメカニズムではありません。</span><span class="sxs-lookup"><span data-stu-id="13393-111">Inside the Microsoft Edge Extension system, neither is an appropriate mechanism.</span></span>  <span data-ttu-id="13393-112">代わりに、拡張ポリシーは、次のように拡張子のファイルを通じて定義され `manifest.json` ます。</span><span class="sxs-lookup"><span data-stu-id="13393-112">Instead, an Extension policy is defined via the `manifest.json` file for the Extension as follows:</span></span>  

```javascript
{
    ...,
    "content_security_policy": "[POLICY STRING GOES HERE]"
    ...
}
```  

> <span data-ttu-id="13393-113">CSP の構文について詳しくは、「[コンテンツセキュリティポリシーの仕様][W3CContentSecurityPolicy]」と「HTML5Rocks の[「コンテンツセキュリティポリシーの概要」][HTML5RocksIntroductionContentSecurityPolicy]をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="13393-113">For full details regarding the CSP syntax, please take a look at the [Content Security Policy specification][W3CContentSecurityPolicy] , and the ["An Introduction to Content Security Policy"][HTML5RocksIntroductionContentSecurityPolicy] article on HTML5Rocks.</span></span>  

## <span data-ttu-id="13393-114">既定のポリシーの制限</span><span class="sxs-lookup"><span data-stu-id="13393-114">Default Policy Restrictions</span></span>  

<span data-ttu-id="13393-115">が定義されていないパッケージには、 `manifest_version` 既定のコンテンツセキュリティポリシーがありません。</span><span class="sxs-lookup"><span data-stu-id="13393-115">Packages that do not define a `manifest_version` do not have a default content security policy.</span></span>  <span data-ttu-id="13393-116">2を選択した `manifest_version` 場合は、次のような既定のコンテンツセキュリティポリシーが設定されます。</span><span class="sxs-lookup"><span data-stu-id="13393-116">Those that select `manifest_version` 2, have a default content security policy of:</span></span>  

```javascript
script-src 'self'; object-src 'self'
```  

<span data-ttu-id="13393-117">このポリシーでは、次の3つの方法で拡張機能とアプリケーションを制限して、セキュリティを強化します。</span><span class="sxs-lookup"><span data-stu-id="13393-117">This policy adds security by limiting Extensions and applications in three ways:</span></span>  

**<span data-ttu-id="13393-118">Eval 関数と関連関数が無効になっている</span><span class="sxs-lookup"><span data-stu-id="13393-118">Eval and related functions are disabled</span></span>**  

<span data-ttu-id="13393-119">次のようなコードは動作しません。</span><span class="sxs-lookup"><span data-stu-id="13393-119">Code like the following does not work:</span></span>  

```javascript
alert(eval("foo.bar.baz"));
window.setTimeout("alert('hi')", 10);
window.setInterval("alert('hi')", 10);
new Function("return foo.bar.baz");
```  

<span data-ttu-id="13393-120">このような JavaScript の文字列の評価は、一般的な XSS 攻撃ベクトルです。</span><span class="sxs-lookup"><span data-stu-id="13393-120">Evaluating strings of JavaScript like this is a common XSS attack vector.</span></span>  <span data-ttu-id="13393-121">代わりに、次のようなコードを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13393-121">Instead, you should write code like:</span></span>

```javascript
alert(foo && foo.bar && foo.bar.baz);
window.setTimeout(function() { alert('hi'); }, 10);
window.setInterval(function() { alert('hi'); }, 10);
function() { return foo && foo.bar && foo.bar.baz };
```  

**<span data-ttu-id="13393-122">インライン JavaScript が実行されない</span><span class="sxs-lookup"><span data-stu-id="13393-122">Inline JavaScript are not run</span></span>**  

<span data-ttu-id="13393-123">インライン JavaScript は実行されません。</span><span class="sxs-lookup"><span data-stu-id="13393-123">Inline JavaScript are not run.</span></span>  <span data-ttu-id="13393-124">この制限 `<script>` は、インラインブロックとインラインイベントハンドラー (など) の両方を禁止し `<button onclick="...">` ます。</span><span class="sxs-lookup"><span data-stu-id="13393-124">This restriction bans both inline `<script>` blocks and inline event handlers, such as `<button onclick="...">`.</span></span>

<span data-ttu-id="13393-125">1つ目の制限では、悪意のあるサードパーティによって提供されたスクリプトを誤って実行することは不可能であるため、大量のクロスサイトスクリプト攻撃を消去しています。</span><span class="sxs-lookup"><span data-stu-id="13393-125">The first restriction wipes out a huge class of cross-site scripting attacks by making it impossible for you to accidentally run the script provided by a malicious third-party.</span></span>  <span data-ttu-id="13393-126">ただし、コンテンツと動作の間の明確な分離を使用してコードを記述する必要があります (もちろん、実際にはこの方法で実行する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="13393-126">It does, however, require you to write your code with a clean separation between content and behavior \(which you should of course do anyway, right?\).</span></span>  <span data-ttu-id="13393-127">例としては、この方法がわかりやすくなっています。</span><span class="sxs-lookup"><span data-stu-id="13393-127">An example may make this clearer.</span></span>  <span data-ttu-id="13393-128">次の内容を含む単一のブラウザーアクションポップアップとして作成することができ `pop-up.html` ます。</span><span class="sxs-lookup"><span data-stu-id="13393-128">You may try to write a Browser Action pop-up as a single `pop-up.html` containing:</span></span>  

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

<span data-ttu-id="13393-129">期待どおりに動作させるためには、次の3つの項目を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13393-129">Three things must change in order to make this work the way you expect it to:</span></span>  

*   <span data-ttu-id="13393-130">`clickHandler`定義は外部 JavaScript ファイルに移動する必要があり `popup.js` ます。 \ (適切なターゲットの場合があります)。</span><span class="sxs-lookup"><span data-stu-id="13393-130">The `clickHandler` definition must be moved into an external JavaScript file \(`popup.js` may be a good target).</span></span>  
*   <span data-ttu-id="13393-131">インラインイベントハンドラーの定義は、のように書き換える必要があり `addEventListener` `popup.js` ます。</span><span class="sxs-lookup"><span data-stu-id="13393-131">The inline event handler definitions must be rewritten in terms of `addEventListener` and extracted into `popup.js`.</span></span>  
    <span data-ttu-id="13393-132">次のようなコードを使ってプログラムを起動している場合は `<body onload="main();">` 、 `DOMContentLoaded` 必要に応じて、ドキュメントのイベントまたはウィンドウのイベントにフックすることで、プログラムを置き換えることを検討してください `load` 。</span><span class="sxs-lookup"><span data-stu-id="13393-132">If you are currently starting your program using code like `<body onload="main();">`, consider replacing it by hooking into the `DOMContentLoaded` event of the document, or the `load` event of the window, depending on your requirements.</span></span>  <span data-ttu-id="13393-133">通常は、前者を使用します。</span><span class="sxs-lookup"><span data-stu-id="13393-133">Use the former, since it generally triggers more quickly.</span></span>  

*   <span data-ttu-id="13393-134">呼び出しは、 `setTimeout` 実行するために JavaScript に文字列を変換しないように書き換える必要があり `"awesome(); totallyAwesome()"` ます。</span><span class="sxs-lookup"><span data-stu-id="13393-134">The `setTimeout` call must be rewritten to avoid converting the string `"awesome(); totallyAwesome()"` into JavaScript for running.</span></span>  
    <span data-ttu-id="13393-135">これらの変更は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="13393-135">Those changes may look something like the following:</span></span>  

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

**<span data-ttu-id="13393-136">ローカルスクリプトとオブジェクトリソースのみが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="13393-136">Only local script and object resources are loaded</span></span>**  

<span data-ttu-id="13393-137">スクリプトとオブジェクトのリソースは、拡張パッケージからのみ読み込むことができます。これは、web からは大きくできません。</span><span class="sxs-lookup"><span data-stu-id="13393-137">Script and object resources are only able to be loaded from the Extension package, not from the web at large.</span></span>  <span data-ttu-id="13393-138">これにより、お客様が明示的に承認したコードのみが実行され、アクティブなネットワーク攻撃者によるリソースの要求の不正なリダイレクトを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="13393-138">This ensures that your Extension only runs the code you specifically approved, preventing an active network attacker from maliciously redirecting your request for a resource.</span></span>  

<span data-ttu-id="13393-139">JQuery \ (または他のライブラリ \) で外部 CDN から読み込みを行うコードを記述する代わりに、拡張機能パッケージに jQuery の特定のバージョンを含めることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="13393-139">Instead of writing code that depends on jQuery \(or any other library\) loading from an external CDN, consider including the specific version of jQuery in your Extension package.</span></span>  <span data-ttu-id="13393-140">これは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="13393-140">That is, instead of:</span></span>  

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

<span data-ttu-id="13393-141">ファイルをダウンロードして、パッケージに含め、次のように書き込みます。</span><span class="sxs-lookup"><span data-stu-id="13393-141">Download the file, include it in your package, and write:</span></span>  

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

## <span data-ttu-id="13393-142">既定のポリシーの緩和</span><span class="sxs-lookup"><span data-stu-id="13393-142">Relaxing the default policy</span></span>  

**<span data-ttu-id="13393-143">インラインスクリプト</span><span class="sxs-lookup"><span data-stu-id="13393-143">Inline Script</span></span>**  

<!-- Up until Chrome 45, there was no mechanism for relaxing the restriction against running inline JavaScript.  In particular, setting a script policy that includes `'unsafe-inline'` has no effect.  

As of Chrome 46, -->  

<span data-ttu-id="13393-144">インラインスクリプトを許可するには、ポリシーのソースコードの base64 でエンコードされたハッシュを指定します。</span><span class="sxs-lookup"><span data-stu-id="13393-144">Inline scripts are able to be allowed by specifying the base64-encoded hash of the source code in the policy.</span></span>  <span data-ttu-id="13393-145">このハッシュのプレフィックスは、使用されているハッシュアルゴリズム \ (sha256、sha384、または sha512 \) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="13393-145">This hash must be prefixed by the used hash algorithm \(sha256, sha384 or sha512\).</span></span>  <span data-ttu-id="13393-146">例については、「 [\ <スクリプト \ > 要素のハッシュの使用状況][W3CContentSecurityPolicyLevel2ScriptSrcHashUsage]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13393-146">See [Hash usage for \<script\> elements][W3CContentSecurityPolicyLevel2ScriptSrcHashUsage] for an example.</span></span>  

**<span data-ttu-id="13393-147">リモートスクリプト</span><span class="sxs-lookup"><span data-stu-id="13393-147">Remote Script</span></span>**  

<span data-ttu-id="13393-148">一部の外部 JavaScript またはオブジェクトリソースを必要とする場合は、スクリプトを受け入れることができる安全な元の元によって、ポリシーを制限された範囲に緩和することができます。</span><span class="sxs-lookup"><span data-stu-id="13393-148">If you require some external JavaScript or object resources, you may relax the policy to a limited extent by allowlisting secure origins from which scripts should be accepted.</span></span>  <span data-ttu-id="13393-149">拡張機能の昇格されたアクセス許可で読み込まれたランタイムリソースが、意図したリソースとまったく同じであり、アクティブなネットワーク攻撃者によって置き換えられていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="13393-149">Verify that runtime resources loaded with with elevated permissions of an Extension are exactly the resources you expect, and are not replaced by an active network attacker.</span></span>  <span data-ttu-id="13393-150">[Man-in-the-middle 攻撃][WikiManMiddleAttacks]は、HTTP 経由での簡単で検出できないため、これらの元は受け入れられません。</span><span class="sxs-lookup"><span data-stu-id="13393-150">As [man-in-the-middle attacks][WikiManMiddleAttacks] are both trivial and undetectable over HTTP, those origins are not accepted.</span></span>  

<span data-ttu-id="13393-151">現時点では、開発者は、、、、 `blob` `filesystem` `https` およびというスキームでオリジンを allowlist `extension` できます。</span><span class="sxs-lookup"><span data-stu-id="13393-151">Currently, developers are able to allowlist origins with the following schemes: `blob`, `filesystem`, `https`, and `extension`.</span></span>  <span data-ttu-id="13393-152">オリジンのホスト部分は、およびスキームに対して明示的に指定する必要があり `https` `extension` ます。</span><span class="sxs-lookup"><span data-stu-id="13393-152">The host part of the origin must explicitly be specified for the `https` and `extension` schemes.</span></span>  <span data-ttu-id="13393-153">Https: などの一般的なワイルド `https://*` カード `https://*.com` は使用できません。たとえば、などのサブドメインワイルドカードを `https://*.example.com` 使用できます。</span><span class="sxs-lookup"><span data-stu-id="13393-153">Generic wildcards such as https:, `https://*` and `https://*.com` are not allowed; subdomain wildcards such as `https://*.example.com` are allowed.</span></span>  <span data-ttu-id="13393-154">[パブリックサフィックスリスト][PublicSuffixList]のドメインは、一般的なトップレベルドメインとしても表示されます。</span><span class="sxs-lookup"><span data-stu-id="13393-154">Domains in the [Public Suffix list][PublicSuffixList] are also viewed as generic top-level domains.</span></span>  <span data-ttu-id="13393-155">これらのドメインからリソースを読み込むには、サブドメインが明示的に表示されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="13393-155">To load a resource from these domains, the subdomain must explicitly be listed.</span></span>  <span data-ttu-id="13393-156">たとえば、 `https://*.cloudfront.net` は有効ではありませんが、 `https://XXXX.cloudfront.net` `https://*.XXXX.cloudfront.net` allowlisted で指定できます。</span><span class="sxs-lookup"><span data-stu-id="13393-156">For example, `https://*.cloudfront.net` is not valid, but `https://XXXX.cloudfront.net` and `https://*.XXXX.cloudfront.net` are able to be allowlisted.</span></span>  

<span data-ttu-id="13393-157">開発が簡単になるように、ローカルコンピューター上のサーバーから HTTP 経由で読み込まれたリソースは、allowlisted 表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="13393-157">For development ease, resources loaded over HTTP from servers on your local machine are able to be allowlisted.</span></span>  <span data-ttu-id="13393-158">スクリプトとオブジェクトソースは、またはのいずれかのポートで allowlist ことができ `http://127.0.0.1` `http://localhost` ます。</span><span class="sxs-lookup"><span data-stu-id="13393-158">You may allowlist script and object sources on any port of either `http://127.0.0.1` or `http://localhost`.</span></span>  

> [!NOTE]
> <span data-ttu-id="13393-159">HTTP 経由で読み込まれたリソースに対する制限は、直接実行されるリソースに対してのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="13393-159">The restriction against resources loaded over HTTP applies only to those resources which are directly run.</span></span>  <span data-ttu-id="13393-160">たとえば、任意の起点への XMLHTTPRequest 接続を作成することもできます。既定のポリシーでは、 `connect-src` どのような方法でも他の CSP ディレクティブは制限されません。</span><span class="sxs-lookup"><span data-stu-id="13393-160">You are still free, for example, to make XMLHTTPRequest connections to any origin you like; the default policy does not restrict `connect-src` or any of the other CSP directives in any way.</span></span>  

<span data-ttu-id="13393-161">HTTPS 経由で example.com からスクリプトリソースを読み込むことができる緩やかなポリシー定義は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="13393-161">A relaxed policy definition which allows script resources to be loaded from example.com over HTTPS may look like:</span></span>  

```javascript
"content_security_policy": "script-src 'self' https://example.com; object-src 'self'"
```  

> [!NOTE]
> <span data-ttu-id="13393-162">どちらも、 `script-src` `object-src` ポリシーによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="13393-162">Both `script-src` and `object-src` are defined by the policy.</span></span>  <span data-ttu-id="13393-163">Microsoft Edge は、これらの各値が \ (少なくと \ \) ' ' に制限されていないポリシーを受け入れません `self` 。</span><span class="sxs-lookup"><span data-stu-id="13393-163">Microsoft Edge does not accept a policy that does not limit each of these values to \(at least\) '`self`'.</span></span>  

<!-- Making use of Google Analytics is the canonical example for this sort of policy definition.  It is common enough that an Analytics boilerplate of sorts is provided in the Event Tracking with Google Analytics sample Extension, and a brief tutorial that goes into more detail.  -->  

**<span data-ttu-id="13393-164">JavaScript の評価</span><span class="sxs-lookup"><span data-stu-id="13393-164">Evaluated JavaScript</span></span>**  

<span data-ttu-id="13393-165">ポリシーに対して、 `eval()` およびというような関連する機能を、 `setTimeout(String)` `setInterval(String)` `new Function(String)` ポリシーに追加することによって緩和することができ `unsafe-eval` ます。</span><span class="sxs-lookup"><span data-stu-id="13393-165">The policy against `eval()` and related functions like `setTimeout(String)`, `setInterval(String)`, and `new Function(String)` are able to be relaxed by adding `unsafe-eval` to your policy:</span></span>  

```javascript
"content_security_policy": "script-src 'self' 'unsafe-eval'; object-src 'self'"
```  

<span data-ttu-id="13393-166">ただし、これを行うことは強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="13393-166">However, we strongly recommend against doing this.</span></span>  <span data-ttu-id="13393-167">これらの関数は、XSS 攻撃ベクトルになります。</span><span class="sxs-lookup"><span data-stu-id="13393-167">These functions are notorious XSS attack vectors.</span></span>  

## <span data-ttu-id="13393-168">既定のポリシーを強化する</span><span class="sxs-lookup"><span data-stu-id="13393-168">Tightening the default policy</span></span>  

<span data-ttu-id="13393-169">もちろん、お客様の便宜を通じてセキュリティを強化するために、延長によって許可されたあらゆるエクステントにこのポリシーを締めることができます。</span><span class="sxs-lookup"><span data-stu-id="13393-169">You may, of course, tighten this policy to whatever extent your Extension allows in order to increase security at the expense of convenience.</span></span>  <span data-ttu-id="13393-170">拡張機能で、関連付けられている拡張パッケージ (たとえば、ポリシーが該当する場合など) の任意の種類 \ (画像など) のリソースを読み込むことができるように指定するには、次のようにし `default-src 'self'` ます。</span><span class="sxs-lookup"><span data-stu-id="13393-170">To specify that your Extension are able to only load resources of any type \(images, and so on\) from the associated Extension package, for example, a policy of `default-src 'self'` may be appropriate.</span></span>  

<!-- The Mappy sample Extension is a good example of an Extension that is been locked down above and beyond the defaults.  -->  

## <span data-ttu-id="13393-171">コンテンツスクリプト</span><span class="sxs-lookup"><span data-stu-id="13393-171">Content Scripts</span></span>  

<span data-ttu-id="13393-172">ディスカッション中のポリシーは、拡張機能の背景ページとイベントページに適用されます。</span><span class="sxs-lookup"><span data-stu-id="13393-172">The policy being discussing applies to the background pages and event pages of the Extension.</span></span>  <span data-ttu-id="13393-173">コンテンツスクリプトが拡張機能のコンテンツスクリプトにどのように適用されるかは、さらに複雑になります。</span><span class="sxs-lookup"><span data-stu-id="13393-173">How the content scripts apply to the content scripts of the Extension is more complicated.</span></span>  

<span data-ttu-id="13393-174">通常、コンテンツスクリプトは、拡張機能の CSP の対象にはなりません。</span><span class="sxs-lookup"><span data-stu-id="13393-174">Content scripts are generally not subject to the CSP of the Extension.</span></span>  <span data-ttu-id="13393-175">コンテンツスクリプトは HTML ではないため、このような影響を与えるのは、 `eval` 拡張機能の CSP で指定されていない場合でも使用できるという点です `unsafe-eval` 。ただし、これはお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="13393-175">Since content scripts are not HTML, the main impact of this is that they may use `eval` even if the CSP of the Extension does not specify `unsafe-eval`, although this is not recommended.</span></span>  <span data-ttu-id="13393-176">さらに、ページの CSP はコンテンツスクリプトには適用されません。</span><span class="sxs-lookup"><span data-stu-id="13393-176">Additionally, the CSP of the page does not apply to content scripts.</span></span>  <span data-ttu-id="13393-177">さらに複雑なタグとして、 `<script>` コンテンツスクリプトが作成され、実行されているページの DOM に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="13393-177">More complicated are `<script>` tags that content scripts create and put into the DOM of the page they are running on.</span></span>  <span data-ttu-id="13393-178">これらは、DOM 注入されたスクリプトとして転送されます。</span><span class="sxs-lookup"><span data-stu-id="13393-178">These are referenced as DOM injected scripts going forward.</span></span>  

<span data-ttu-id="13393-179">ページへの挿入直後に実行される DOM の挿入されたスクリプトは、期待どおりに実行されます。</span><span class="sxs-lookup"><span data-stu-id="13393-179">DOM injected scripts that run immediately upon injection into the page runs as you may expect.</span></span>  <span data-ttu-id="13393-180">単純な例として、次のコードを含むコンテンツスクリプトを想像してみてください。</span><span class="sxs-lookup"><span data-stu-id="13393-180">Imagine a content script with the following code as a simple example:</span></span>  

```javascript
document.write("<script>alert(1);</script>");
 ```  

<span data-ttu-id="13393-181">このコンテンツスクリプトは、のすぐにを発生させ `alert` `document.write()` ます。</span><span class="sxs-lookup"><span data-stu-id="13393-181">This content script causes an `alert` immediately upon the `document.write()`.</span></span>  <span data-ttu-id="13393-182">これは、ページで指定されているポリシーに関係なく実行されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="13393-182">Note that this runs regardless of the policy a page may specify.</span></span>
<span data-ttu-id="13393-183">ただし、この動作は、DOM に挿入されたスクリプトと、挿入時にすぐに実行されないスクリプトの両方で複雑になります。</span><span class="sxs-lookup"><span data-stu-id="13393-183">However, the behavior becomes more complicated both inside that DOM injected script and for any script that does not immediately run upon injection.</span></span>  <span data-ttu-id="13393-184">拡張機能が、関連付けられている CSP を提供するページで実行されているとし `script-src 'self'` ます。</span><span class="sxs-lookup"><span data-stu-id="13393-184">Imagine that your Extension is running on a page that provides an associated CSP that specifies `script-src 'self'`.</span></span>  <span data-ttu-id="13393-185">ここでは、コンテンツスクリプトで次のコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="13393-185">Now imagine the content script runs the following code:</span></span>  

```javascript
document.write("<button onclick='alert(1);'>click me</button>'");
```  

<span data-ttu-id="13393-186">ユーザーがそのボタンをクリックした場合、 `onclick` スクリプトは実行されません。</span><span class="sxs-lookup"><span data-stu-id="13393-186">If a user clicks on that button, the `onclick` script does not run.</span></span>  <span data-ttu-id="13393-187">これは、スクリプトがすぐに実行されることはなく、click イベントが発生するまではコードが解釈されないため、(拡張子 \) のページの CSP は動作を制限します。</span><span class="sxs-lookup"><span data-stu-id="13393-187">This is because the script did not immediately run and code is not interpreted until the click event occurs is not considered part of the content script, so the CSP of the page \(not of the Extension\) restricts the behavior.</span></span>  <span data-ttu-id="13393-188">また、CSP で指定されていないため `unsafe-inline` 、インラインイベントハンドラーはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="13393-188">And since that CSP does not specify `unsafe-inline`, the inline event handler is blocked.</span></span>  
<span data-ttu-id="13393-189">この場合、適切な動作を実装する正しい方法は、 `onclick` 次のようにコンテンツスクリプトからハンドラーを関数として追加することです。</span><span class="sxs-lookup"><span data-stu-id="13393-189">The correct way to implement the desired behavior in this case may be to add the `onclick` handler as a function from the content script as follows:</span></span>  

```javascript
document.write("<button id='mybutton'>click me</button>'");
var button = document.getElementById('mybutton');
button.onclick = function() {
      alert(1);
};
```  

<span data-ttu-id="13393-190">コンテンツスクリプトで次の操作を実行した場合も、同様の問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="13393-190">Another similar issue arises if the content script runs the following:</span></span>  

```javascript
var script = document.createElement('script');
script.innerHTML = 'alert(1);'
document.getElementById('body').appendChild(script);
```  

<span data-ttu-id="13393-191">この場合、スクリプトが実行され、アラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="13393-191">In this case, the script runs and the alert displays.</span></span>  <span data-ttu-id="13393-192">ただし、次のような場合に該当します。</span><span class="sxs-lookup"><span data-stu-id="13393-192">However, take this case:</span></span>  

```javascript
var script = document.createElement('script');
script.innerHTML = 'eval("alert(1);")';
=document.getElementById('body').appendChild(script);
```  

<span data-ttu-id="13393-193">初期スクリプトを実行している間、の呼び出し `eval` はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="13393-193">While the initial script runs, the call to `eval` is blocked.</span></span>  <span data-ttu-id="13393-194">つまり、初期スクリプトランタイムが許可されている間、スクリプト内の動作はページの CSP によって規制されます。</span><span class="sxs-lookup"><span data-stu-id="13393-194">That is, while the initial script runtime is allowed, the behavior within the script is regulated by the CSP of the page.</span></span>  
<span data-ttu-id="13393-195">したがって、DOM に挿入されたスクリプトを拡張機能に記述する方法によっては、ページの CSP を変更すると、拡張機能の動作に影響する場合があります。</span><span class="sxs-lookup"><span data-stu-id="13393-195">Thus, depending on how you write DOM injected scripts in your Extension, changes to the CSP of the page may affect the behavior of your Extension.</span></span>  <span data-ttu-id="13393-196">コンテンツスクリプトはページの CSP によって影響を受けることはないため、この方法では、拡張機能で可能な限り多くの動作を、DOM に挿入されたスクリプトではなくコンテンツスクリプトに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="13393-196">Since content scripts are not affected by the CSP of the page, this a great reason to put as much behavior as possible of your Extension into the content script rather than DOM injected scripts.</span></span>  

<!-- image links -->  

<!-- links -->  

[HTML5RocksIntroductionContentSecurityPolicy]: https://www.html5rocks.com/en/tutorials/security/content-security-policy "コンテンツセキュリティポリシーの概要-HTML5 の岩"  
[PublicSuffixList]: https://publicsuffix.org/list "パブリックサフィックスの一覧を表示する"  
[W3CContentSecurityPolicyLevel2ScriptSrcHashUsage]: https://www.w3.org/TR/CSP2#script-src-hash-usage "\ <スクリプト \ > 要素のハッシュの使用-コンテンツセキュリティポリシーレベル2"  
[W3CContentSecurityPolicy]: https://w3c.github.io/webappsec-csp "コンテンツセキュリティポリシーレベル3"  
[WikiManMiddleAttacks]: https://en.wikipedia.org/wiki/Man-in-the-middle_attack "Man-in-the-middle 攻撃-Wikipedia (Wikipedia)"  

> [!NOTE]
> <span data-ttu-id="13393-202">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="13393-202">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="13393-203">元のページは[ここ](https://developer.chrome.com/extensions/contentSecurityPolicy)にあります。</span><span class="sxs-lookup"><span data-stu-id="13393-203">The original page is found [here](https://developer.chrome.com/extensions/contentSecurityPolicy).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="13393-205">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="13393-205">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
