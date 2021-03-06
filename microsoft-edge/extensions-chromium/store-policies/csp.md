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
# <a name="content-security-policy-csp"></a><span data-ttu-id="796c3-104">コンテンツ セキュリティ ポリシー \(CSP\)</span><span class="sxs-lookup"><span data-stu-id="796c3-104">Content Security Policy \(CSP\)</span></span>  

<span data-ttu-id="796c3-105">潜在的なクロスサイト スクリプティングの問題の大規模なクラスを軽減するために、Microsoft Edge Extension システムはコンテンツ セキュリティ ポリシー [\(CSP\)][W3CContentSecurityPolicy]の一般的な概念を組み込んだ。</span><span class="sxs-lookup"><span data-stu-id="796c3-105">In order to mitigate a large class of potential cross-site scripting issues, the Microsoft Edge Extension system has incorporated the general concept of [Content Security Policy \(CSP\)][W3CContentSecurityPolicy].</span></span>  <span data-ttu-id="796c3-106">これにより、拡張機能のセキュリティを既定で高めるかなり厳格なポリシーが導入され、拡張機能とアプリケーションによって読み込まれ、実行される可能性のあるコンテンツの種類を管理するルールを作成および適用できます。</span><span class="sxs-lookup"><span data-stu-id="796c3-106">This introduces some fairly strict policies that make Extensions more secure by default, and provides you with the ability to create and enforce rules governing the types of content that may be loaded and run by your Extensions and applications.</span></span>  

<span data-ttu-id="796c3-107">一般に、CSP は拡張機能によって読み込まれた、または実行されるリソースのブロック/許可リストメカニズムとして機能します。</span><span class="sxs-lookup"><span data-stu-id="796c3-107">In general, CSP works as a block/allowlisting mechanism for resources loaded or run by your Extensions.</span></span>  <span data-ttu-id="796c3-108">拡張機能の適切なポリシーを定義すると、拡張機能で必要なリソースを慎重に検討し、拡張機能がアクセスできる唯一のリソースをブラウザーに確認することができます。</span><span class="sxs-lookup"><span data-stu-id="796c3-108">Defining a reasonable policy for your Extension enables you to carefully consider the resources that your Extension requires, and to ask the browser to ensure that those are the only resources your Extension has access to.</span></span>  <span data-ttu-id="796c3-109">ポリシーは、拡張機能が要求するホストのアクセス許可以上のセキュリティを提供します。これらは、代替ではなく、保護の追加の層です。</span><span class="sxs-lookup"><span data-stu-id="796c3-109">The policies provide security over and above the host permissions your Extension requests; they are an additional layer of protection, not a replacement.</span></span>  

<span data-ttu-id="796c3-110">Web では、このようなポリシーは HTTP ヘッダーまたは要素を介して定義 `meta` されます。</span><span class="sxs-lookup"><span data-stu-id="796c3-110">On the web, such a policy is defined via an HTTP header or `meta` element.</span></span>  <span data-ttu-id="796c3-111">Microsoft Edge Extension システム内では、どちらも適切なメカニズムとは言えな</span><span class="sxs-lookup"><span data-stu-id="796c3-111">Inside the Microsoft Edge Extension system, neither is an appropriate mechanism.</span></span>  <span data-ttu-id="796c3-112">代わりに、拡張機能ポリシーは、拡張機能のファイルを使用 `manifest.json` して次のように定義されます。</span><span class="sxs-lookup"><span data-stu-id="796c3-112">Instead, an Extension policy is defined using the `manifest.json` file for the Extension as follows:</span></span>  

```javascript
{
    ...,
    "content_security_policy": "[POLICY STRING GOES HERE]"
    ...
}
```  

> <span data-ttu-id="796c3-113">CSP 構文の詳細については、HTML5Rocks の「コンテンツ[][W3CContentSecurityPolicy]セキュリティ ポリシーの仕様」[][HTML5RocksIntroductionContentSecurityPolicy]と「コンテンツ セキュリティ ポリシーの概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="796c3-113">For full details regarding the CSP syntax, please take a look at the [Content Security Policy specification][W3CContentSecurityPolicy] , and the ["An Introduction to Content Security Policy"][HTML5RocksIntroductionContentSecurityPolicy] article on HTML5Rocks.</span></span>  

## <a name="default-policy-restrictions"></a><span data-ttu-id="796c3-114">既定のポリシー制限</span><span class="sxs-lookup"><span data-stu-id="796c3-114">Default Policy Restrictions</span></span>  

<span data-ttu-id="796c3-115">a を定義しないパッケージ `manifest_version` には、既定のコンテンツ セキュリティ ポリシーが適用されません。</span><span class="sxs-lookup"><span data-stu-id="796c3-115">Packages that do not define a `manifest_version` do not have a default content security policy.</span></span>  <span data-ttu-id="796c3-116">`manifest_version`2 を選択するパッケージには、次の既定のコンテンツ セキュリティ ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="796c3-116">Packages that choose `manifest_version` 2, have a the follwoing default content security policy.</span></span>  

```javascript
script-src 'self'; object-src 'self'
```  

<span data-ttu-id="796c3-117">このポリシーは、拡張機能とアプリケーションを次の 3 つの方法で制限することでセキュリティを強化します。</span><span class="sxs-lookup"><span data-stu-id="796c3-117">The policy adds security by limiting Extensions and applications in three ways:</span></span>  

**<span data-ttu-id="796c3-118">Eval および関連する関数が無効になっている</span><span class="sxs-lookup"><span data-stu-id="796c3-118">Eval and related functions are disabled</span></span>**  

<span data-ttu-id="796c3-119">次のようなコードは機能しません。</span><span class="sxs-lookup"><span data-stu-id="796c3-119">Code like the following does not work:</span></span>  

```javascript
alert(eval("foo.bar.baz"));
window.setTimeout("alert('hi')", 10);
window.setInterval("alert('hi')", 10);
new Function("return foo.bar.baz");
```  

<span data-ttu-id="796c3-120">このような JavaScript の文字列の評価は、一般的な XSS 攻撃ベクトルです。</span><span class="sxs-lookup"><span data-stu-id="796c3-120">Evaluating strings of JavaScript like this is a common XSS attack vector.</span></span>  <span data-ttu-id="796c3-121">代わりに、次のようなコードを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="796c3-121">Instead, you should write code like:</span></span>

```javascript
alert(foo && foo.bar && foo.bar.baz);
window.setTimeout(function() { alert('hi'); }, 10);
window.setInterval(function() { alert('hi'); }, 10);
function() { return foo && foo.bar && foo.bar.baz };
```  

**<span data-ttu-id="796c3-122">インライン JavaScript が実行されない</span><span class="sxs-lookup"><span data-stu-id="796c3-122">Inline JavaScript are not run</span></span>**  

<span data-ttu-id="796c3-123">インライン JavaScript は実行されません。</span><span class="sxs-lookup"><span data-stu-id="796c3-123">Inline JavaScript are not run.</span></span>  <span data-ttu-id="796c3-124">この制限は、インライン ブロックとインライン `<script>` イベント ハンドラーの両方 (など) を禁止します `<button onclick="...">` 。</span><span class="sxs-lookup"><span data-stu-id="796c3-124">This restriction bans both inline `<script>` blocks and inline event handlers, such as `<button onclick="...">`.</span></span>

<span data-ttu-id="796c3-125">最初の制限では、悪意のあるサード パーティによって提供されるスクリプトを誤って実行することは不可能にすることで、クロスサイト スクリプティング攻撃の巨大なクラスを一掃します。</span><span class="sxs-lookup"><span data-stu-id="796c3-125">The first restriction wipes out a huge class of cross-site scripting attacks by making it impossible for you to accidentally run the script provided by a malicious third-party.</span></span>  <span data-ttu-id="796c3-126">ただし、コンテンツと動作の間でクリーンな分離を使用してコードを記述する必要があります 。もちろん、これはもちろん行う必要があります。正しいですか?\)。</span><span class="sxs-lookup"><span data-stu-id="796c3-126">It does, however, require you to write your code with a clean separation between content and behavior \(which you should of course do anyway, right?\).</span></span>  <span data-ttu-id="796c3-127">たとえば、これを明確にする場合があります。</span><span class="sxs-lookup"><span data-stu-id="796c3-127">An example may make this clearer.</span></span>  <span data-ttu-id="796c3-128">ブラウザー アクション のポップアップは、次を含む 1 つのポップアップとして `pop-up.html` 記述できます。</span><span class="sxs-lookup"><span data-stu-id="796c3-128">You may try to write a Browser Action pop-up as a single `pop-up.html` containing:</span></span>  

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

<span data-ttu-id="796c3-129">この動作を期待通りに行うには、次の 3 つの点が変更される必要があります。</span><span class="sxs-lookup"><span data-stu-id="796c3-129">Three things must change in order to make this work the way you expect it to:</span></span>  

*   <span data-ttu-id="796c3-130">定義 `clickHandler` は、外部 JavaScript ファイル \( に移動する必要 `popup.js` があります。</span><span class="sxs-lookup"><span data-stu-id="796c3-130">The `clickHandler` definition must be moved into an external JavaScript file \(`popup.js` may be a good target).</span></span>  
*   <span data-ttu-id="796c3-131">インライン イベント ハンドラーの定義は、 という点で書き換え、 `addEventListener` に抽出する必要があります `popup.js` 。</span><span class="sxs-lookup"><span data-stu-id="796c3-131">The inline event handler definitions must be rewritten in terms of `addEventListener` and extracted into `popup.js`.</span></span>  
    <span data-ttu-id="796c3-132">現在、コードを使用してプログラムを開始している場合は、要件に応じて、ドキュメントのイベントまたはウィンドウのイベントにフックして置き換え検討 `<body onload="main();">` `DOMContentLoaded` `load` してください。</span><span class="sxs-lookup"><span data-stu-id="796c3-132">If you are currently starting your program using code like `<body onload="main();">`, consider replacing it by hooking into the `DOMContentLoaded` event of the document, or the `load` event of the window, depending on your requirements.</span></span>  <span data-ttu-id="796c3-133">一般にトリガーが速く行うので、前者を使用します。</span><span class="sxs-lookup"><span data-stu-id="796c3-133">Use the former, since it generally triggers more quickly.</span></span>  

*   <span data-ttu-id="796c3-134">文字列を JavaScript に変換して実行しないように、呼び出し `setTimeout` `"awesome(); totallyAwesome()"` を書き換えする必要があります。</span><span class="sxs-lookup"><span data-stu-id="796c3-134">The `setTimeout` call must be rewritten to avoid converting the string `"awesome(); totallyAwesome()"` into JavaScript for running.</span></span>  
    <span data-ttu-id="796c3-135">これらの変更は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="796c3-135">Those changes may look something like the following:</span></span>  

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

**<span data-ttu-id="796c3-136">ローカル スクリプトとオブジェクト リソースだけが読み込まれる</span><span class="sxs-lookup"><span data-stu-id="796c3-136">Only local script and object resources are loaded</span></span>**  

<span data-ttu-id="796c3-137">スクリプトリソースとオブジェクト リソースは、拡張機能パッケージからしか読み込めることはできません。Web からのみ読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="796c3-137">Script and object resources are only able to be loaded from the Extension package, not from the web at large.</span></span>  <span data-ttu-id="796c3-138">これにより、拡張機能は、特に承認したコードのみを実行し、アクティブなネットワーク攻撃者がリソースの要求を悪意を持ってリダイレクトするのを防ぐことを保証します。</span><span class="sxs-lookup"><span data-stu-id="796c3-138">This ensures that your Extension only runs the code you specifically approved, preventing an active network attacker from maliciously redirecting your request for a resource.</span></span>  

<span data-ttu-id="796c3-139">外部 CDN からの jQuery \(または他のライブラリ\) の読み込みに依存するコードを記述する代わりに、拡張機能パッケージに特定のバージョンの jQuery を含めて検討してください。</span><span class="sxs-lookup"><span data-stu-id="796c3-139">Instead of writing code that depends on jQuery \(or any other library\) loading from an external CDN, consider including the specific version of jQuery in your Extension package.</span></span>  <span data-ttu-id="796c3-140">つまり、次の代わりに次の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="796c3-140">That is, instead of:</span></span>  

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

<span data-ttu-id="796c3-141">ファイルをダウンロードし、パッケージに含め、次の値を記述します。</span><span class="sxs-lookup"><span data-stu-id="796c3-141">Download the file, include it in your package, and write:</span></span>  

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

## <a name="relaxing-the-default-policy"></a><span data-ttu-id="796c3-142">既定のポリシーをリラックスする</span><span class="sxs-lookup"><span data-stu-id="796c3-142">Relaxing the default policy</span></span>  

**<span data-ttu-id="796c3-143">インライン スクリプト</span><span class="sxs-lookup"><span data-stu-id="796c3-143">Inline Script</span></span>**  

<!-- Up until Chrome 45, there was no mechanism for relaxing the restriction against running inline JavaScript.  In particular, setting a script policy that includes `'unsafe-inline'` has no effect.  

As of Chrome 46, -->  

<span data-ttu-id="796c3-144">インライン スクリプトは、ポリシーでソース コードの base64 エンコードハッシュを指定することで許可できます。</span><span class="sxs-lookup"><span data-stu-id="796c3-144">Inline scripts are able to be allowed by specifying the base64-encoded hash of the source code in the policy.</span></span>  <span data-ttu-id="796c3-145">このハッシュの先頭には、使用するハッシュ アルゴリズム \(sha256、sha384、sha512\) を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="796c3-145">This hash must be prefixed by the used hash algorithm \(sha256, sha384 or sha512\).</span></span>  <span data-ttu-id="796c3-146">たとえば、要素のハッシュ使用法 [に \<script\> 移動します][W3CContentSecurityPolicyLevel2ScriptSrcHashUsage]。</span><span class="sxs-lookup"><span data-stu-id="796c3-146">For an example, navigate to [Hash usage for \<script\> elements][W3CContentSecurityPolicyLevel2ScriptSrcHashUsage].</span></span>  

**<span data-ttu-id="796c3-147">リモート スクリプト</span><span class="sxs-lookup"><span data-stu-id="796c3-147">Remote Script</span></span>**  

<span data-ttu-id="796c3-148">外部 JavaScript またはオブジェクト リソースが必要な場合は、スクリプトを受け入れるセキュリティで保護された起点を許可することで、ポリシーを制限された範囲でリラックスできます。</span><span class="sxs-lookup"><span data-stu-id="796c3-148">If you require some external JavaScript or object resources, you may relax the policy to a limited extent by allowlisting secure origins from which scripts should be accepted.</span></span>  <span data-ttu-id="796c3-149">拡張機能の昇格されたアクセス許可で読み込まれたランタイム リソースが、期待するリソースであり、アクティブなネットワーク攻撃者に置き換えることはできません。</span><span class="sxs-lookup"><span data-stu-id="796c3-149">Verify that runtime resources loaded with with elevated permissions of an Extension are exactly the resources you expect, and are not replaced by an active network attacker.</span></span>  <span data-ttu-id="796c3-150">中間 [者による攻撃][WikiManMiddleAttacks] は、HTTP 上では簡単で検出できないので、それらの発生元は受け入れなされません。</span><span class="sxs-lookup"><span data-stu-id="796c3-150">As [man-in-the-middle attacks][WikiManMiddleAttacks] are both trivial and undetectable over HTTP, those origins are not accepted.</span></span>  

<span data-ttu-id="796c3-151">現在、開発者は、次のスキームを使用して、オリジンを許可 `blob` できます。 `filesystem` `https` `extension`</span><span class="sxs-lookup"><span data-stu-id="796c3-151">Currently, developers are able to allowlist origins with the following schemes: `blob`, `filesystem`, `https`, and `extension`.</span></span>  <span data-ttu-id="796c3-152">オリジンのホスト 部分は、and スキームに対して明示的に `https` 指定する `extension` 必要があります。</span><span class="sxs-lookup"><span data-stu-id="796c3-152">The host part of the origin must explicitly be specified for the `https` and `extension` schemes.</span></span>  <span data-ttu-id="796c3-153">https:など、一般的なワイルドカードは許可されません。サブドメインのワイルドカード `https://*` `https://*.com` (許可 `https://*.example.com` されている場合など)。</span><span class="sxs-lookup"><span data-stu-id="796c3-153">Generic wildcards such as https:, `https://*` and `https://*.com` are not allowed; subdomain wildcards such as `https://*.example.com` are allowed.</span></span>  <span data-ttu-id="796c3-154">[パブリック サフィックス] [リストのドメインは][PublicSuffixList] 、汎用のトップ レベル ドメインとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="796c3-154">Domains in the [Public Suffix list][PublicSuffixList] are also viewed as generic top-level domains.</span></span>  <span data-ttu-id="796c3-155">これらのドメインからリソースを読み込むには、サブドメインを明示的に一覧表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="796c3-155">To load a resource from these domains, the subdomain must explicitly be listed.</span></span>  <span data-ttu-id="796c3-156">たとえば、 `https://*.cloudfront.net` 無効ですが、 `https://XXXX.cloudfront.net` `https://*.XXXX.cloudfront.net` 可能です `allowlisted` 。</span><span class="sxs-lookup"><span data-stu-id="796c3-156">For example, `https://*.cloudfront.net` is not valid, but `https://XXXX.cloudfront.net` and `https://*.XXXX.cloudfront.net` are able to be `allowlisted`.</span></span>  

<span data-ttu-id="796c3-157">開発を容易にするために、ローカル コンピューター上のサーバーから HTTP を使用して読み込まれるリソースを使用できます `allowlisted` 。</span><span class="sxs-lookup"><span data-stu-id="796c3-157">For development ease, resources loaded over HTTP from servers on your local machine are able to be `allowlisted`.</span></span>  <span data-ttu-id="796c3-158">スクリプトとオブジェクト ソースは、いずれかのポートで許可 `http://127.0.0.1` できます `http://localhost` 。</span><span class="sxs-lookup"><span data-stu-id="796c3-158">You may allowlist script and object sources on any port of either `http://127.0.0.1` or `http://localhost`.</span></span>  

> [!NOTE]
> <span data-ttu-id="796c3-159">HTTP を使用して読み込まれるリソースに対する制限は、直接実行されるリソースにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="796c3-159">The restriction against resources loaded over HTTP applies only to those resources which are directly run.</span></span>  <span data-ttu-id="796c3-160">たとえば、任意のオリジンへの接続を行う場合、既定のポリシーでは制限も他の CSP ディレクティブも制限 `XMLHTTPRequest` `connect-src` されません。</span><span class="sxs-lookup"><span data-stu-id="796c3-160">You are still free, for example, to make `XMLHTTPRequest` connections to any origin you like; the default policy does not restrict `connect-src` or any of the other CSP directives in any way.</span></span>  

<span data-ttu-id="796c3-161">HTTPS 経由でスクリプト リソースを読み込むリラックスしたポリシー定義は `example.com` 、次のような場合があります。</span><span class="sxs-lookup"><span data-stu-id="796c3-161">A relaxed policy definition which allows script resources to be loaded from `example.com` over HTTPS may look like:</span></span>  

```javascript
"content_security_policy": "script-src 'self' https://example.com; object-src 'self'"
```  

> [!NOTE]
> <span data-ttu-id="796c3-162">両方 `script-src` とも `object-src` 、ポリシーによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="796c3-162">Both `script-src` and `object-src` are defined by the policy.</span></span>  <span data-ttu-id="796c3-163">Microsoft Edge では、これらの各値を \(少なくとも\) ' 'に制限しないポリシーは受け入 `self` れかねない。</span><span class="sxs-lookup"><span data-stu-id="796c3-163">Microsoft Edge does not accept a policy that does not limit each of these values to \(at least\) '`self`'.</span></span>  

<!-- Making use of Google Analytics is the canonical example for this sort of policy definition.  It is common enough that an Analytics boilerplate of sorts is provided in the Event Tracking with Google Analytics sample Extension, and a brief tutorial that goes into more detail.  -->  

**<span data-ttu-id="796c3-164">評価された JavaScript</span><span class="sxs-lookup"><span data-stu-id="796c3-164">Evaluated JavaScript</span></span>**  

<span data-ttu-id="796c3-165">ポリシーに対 `eval()` するポリシーと関連する関数 (、、など) は、ポリシーに追加することで `setTimeout(String)` `setInterval(String)` `new Function(String)` `unsafe-eval` 緩和できます。</span><span class="sxs-lookup"><span data-stu-id="796c3-165">The policy against `eval()` and related functions like `setTimeout(String)`, `setInterval(String)`, and `new Function(String)` are able to be relaxed by adding `unsafe-eval` to your policy:</span></span>  

```javascript
"content_security_policy": "script-src 'self' 'unsafe-eval'; object-src 'self'"
```  

<span data-ttu-id="796c3-166">ただし、ポリシーのリラックスは避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="796c3-166">However, you should avoid relaxing policies.</span></span>  <span data-ttu-id="796c3-167">関数は悪名高い XSS 攻撃ベクトルです。</span><span class="sxs-lookup"><span data-stu-id="796c3-167">The functions are notorious XSS attack vectors.</span></span>  

## <a name="tightening-the-default-policy"></a><span data-ttu-id="796c3-168">既定のポリシーの強化</span><span class="sxs-lookup"><span data-stu-id="796c3-168">Tightening the default policy</span></span>  

<span data-ttu-id="796c3-169">もちろん、利便性を犠牲にしてセキュリティを強化するために、拡張機能が許可する範囲でこのポリシーを強化することができます。</span><span class="sxs-lookup"><span data-stu-id="796c3-169">You may, of course, tighten this policy to whatever extent your Extension allows in order to increase security at the expense of convenience.</span></span>  <span data-ttu-id="796c3-170">関連付けられた拡張パッケージから任意の種類の \(images など)のリソースのみを読み込み可能にするように指定するには、ポリシーが適切な `default-src 'self'` 場合があります。</span><span class="sxs-lookup"><span data-stu-id="796c3-170">To specify that your Extension are able to only load resources of any type \(images, and so on\) from the associated Extension package, for example, a policy of `default-src 'self'` may be appropriate.</span></span>  

<!-- The Mappy sample Extension is a good example of an Extension that is been locked down above and beyond the defaults.  -->  

## <a name="content-scripts"></a><span data-ttu-id="796c3-171">コンテンツ スクリプト</span><span class="sxs-lookup"><span data-stu-id="796c3-171">Content Scripts</span></span>  

<span data-ttu-id="796c3-172">説明するポリシーは、拡張機能のバックグラウンド ページとイベント ページに適用されます。</span><span class="sxs-lookup"><span data-stu-id="796c3-172">The policy being discussing applies to the background pages and event pages of the Extension.</span></span>  <span data-ttu-id="796c3-173">拡張機能のコンテンツ スクリプトにコンテンツ スクリプトを適用する方法は、より複雑です。</span><span class="sxs-lookup"><span data-stu-id="796c3-173">How the content scripts apply to the content scripts of the Extension is more complicated.</span></span>  

<span data-ttu-id="796c3-174">コンテンツ スクリプトは、通常、拡張機能の CSP の対象ではありません。</span><span class="sxs-lookup"><span data-stu-id="796c3-174">Content scripts are generally not subject to the CSP of the Extension.</span></span>  <span data-ttu-id="796c3-175">コンテンツ スクリプトは HTML ではなからないので、拡張機能の CSP が指定されていない場合でも使用できる場合が主な影響ですが、これは `eval` `unsafe-eval` お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="796c3-175">Since content scripts are not HTML, the main impact of this is that they may use `eval` even if the CSP of the Extension does not specify `unsafe-eval`, although this is not recommended.</span></span>  <span data-ttu-id="796c3-176">さらに、ページの CSP はコンテンツ スクリプトには適用されません。</span><span class="sxs-lookup"><span data-stu-id="796c3-176">Additionally, the CSP of the page does not apply to content scripts.</span></span>  <span data-ttu-id="796c3-177">さらに複雑になる `<script>` のは、コンテンツ スクリプトが作成し、実行しているページの DOM に入れるタグです。</span><span class="sxs-lookup"><span data-stu-id="796c3-177">More complicated are `<script>` tags that content scripts create and put into the DOM of the page they are running on.</span></span>  <span data-ttu-id="796c3-178">これらは、今後 DOM によって挿入されるスクリプトとして参照されます。</span><span class="sxs-lookup"><span data-stu-id="796c3-178">These are referenced as DOM injected scripts going forward.</span></span>  

<span data-ttu-id="796c3-179">ページに挿入するとすぐに実行される DOM によって挿入されたスクリプトは、予想通り実行されます。</span><span class="sxs-lookup"><span data-stu-id="796c3-179">DOM injected scripts that run immediately upon injection into the page runs as you may expect.</span></span>  <span data-ttu-id="796c3-180">簡単な例として、次のコードを含むコンテンツ スクリプトを想像してください。</span><span class="sxs-lookup"><span data-stu-id="796c3-180">Imagine a content script with the following code as a simple example:</span></span>  

```javascript
document.write("<script>alert(1);</script>");
 ```  

<span data-ttu-id="796c3-181">このコンテンツ スクリプトは、 の `alert` 直後に発生します `document.write()` 。</span><span class="sxs-lookup"><span data-stu-id="796c3-181">This content script causes an `alert` immediately upon the `document.write()`.</span></span>  <span data-ttu-id="796c3-182">これは、ページで指定できるポリシーに関係なく実行されます。</span><span class="sxs-lookup"><span data-stu-id="796c3-182">Note that this runs regardless of the policy a page may specify.</span></span>
<span data-ttu-id="796c3-183">ただし、DOM によって挿入されたスクリプトの内部と、挿入時にすぐに実行されないスクリプトの両方で、動作が複雑になります。</span><span class="sxs-lookup"><span data-stu-id="796c3-183">However, the behavior becomes more complicated both inside that DOM injected script and for any script that does not immediately run upon injection.</span></span>  <span data-ttu-id="796c3-184">指定する関連付けられた CSP を提供するページで拡張機能が実行されているとします `script-src 'self'` 。</span><span class="sxs-lookup"><span data-stu-id="796c3-184">Imagine that your Extension is running on a page that provides an associated CSP that specifies `script-src 'self'`.</span></span>  <span data-ttu-id="796c3-185">次に、コンテンツ スクリプトが次のコードを実行するとします。</span><span class="sxs-lookup"><span data-stu-id="796c3-185">Now imagine the content script runs the following code:</span></span>  

```javascript
document.write("<button onclick='alert(1);'>click me</button>'");
```  

<span data-ttu-id="796c3-186">ユーザーがボタンを選択した場合、 `onclick` スクリプトは実行されません。</span><span class="sxs-lookup"><span data-stu-id="796c3-186">If a user chooses that button, the `onclick` script does not run.</span></span>  <span data-ttu-id="796c3-187">これは、スクリプトがすぐに実行され、イベントが発生するまでコードが解釈されないので、コンテンツ スクリプトの一部と見なされないので、ページ \(Extension\ではない) の CSP は動作を `click` 制限します。</span><span class="sxs-lookup"><span data-stu-id="796c3-187">This is because the script did not immediately run and code is not interpreted until the `click` event occurs is not considered part of the content script, so the CSP of the page \(not of the Extension\) restricts the behavior.</span></span>  <span data-ttu-id="796c3-188">また、CSP が指定していないの `unsafe-inline` で、インライン イベント ハンドラーはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="796c3-188">And since that CSP does not specify `unsafe-inline`, the inline event handler is blocked.</span></span>  
<span data-ttu-id="796c3-189">この場合、目的の動作を実装する正しい方法は、次のようにコンテンツ スクリプトからハンドラーを関数として `onclick` 追加する方法です。</span><span class="sxs-lookup"><span data-stu-id="796c3-189">The correct way to implement the desired behavior in this case may be to add the `onclick` handler as a function from the content script as follows:</span></span>  

```javascript
document.write("<button id='mybutton'>click me</button>'");
var button = document.getElementById('mybutton');
button.onclick = function() {
      alert(1);
};
```  

<span data-ttu-id="796c3-190">コンテンツ スクリプトで次のような問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="796c3-190">Another similar issue arises if the content script runs the following:</span></span>  

```javascript
var script = document.createElement('script');
script.innerHTML = 'alert(1);'
document.getElementById('body').appendChild(script);
```  

<span data-ttu-id="796c3-191">この場合、スクリプトが実行され、アラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="796c3-191">In this case, the script runs and the alert displays.</span></span>  <span data-ttu-id="796c3-192">ただし、次の場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="796c3-192">However, take this case:</span></span>  

```javascript
var script = document.createElement('script');
script.innerHTML = 'eval("alert(1);")';
=document.getElementById('body').appendChild(script);
```  

<span data-ttu-id="796c3-193">最初のスクリプトの実行中、呼び出し `eval` はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="796c3-193">While the initial script runs, the call to `eval` is blocked.</span></span>  <span data-ttu-id="796c3-194">つまり、最初のスクリプト ランタイムが許可されている間、スクリプト内の動作はページの CSP によって規制されます。</span><span class="sxs-lookup"><span data-stu-id="796c3-194">That is, while the initial script runtime is allowed, the behavior within the script is regulated by the CSP of the page.</span></span>  
<span data-ttu-id="796c3-195">したがって、拡張機能に DOM 挿入スクリプトを記述する方法によっては、ページの CSP に対する変更が拡張機能の動作に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="796c3-195">Thus, depending on how you write DOM injected scripts in your Extension, changes to the CSP of the page may affect the behavior of your Extension.</span></span>  <span data-ttu-id="796c3-196">コンテンツ スクリプトはページの CSP の影響を受けかねないので、DOM によって挿入されたスクリプトではなく、拡張機能の可能な限り多くの動作をコンテンツ スクリプトに入れる大きな理由です。</span><span class="sxs-lookup"><span data-stu-id="796c3-196">Since content scripts are not affected by the CSP of the page, this a great reason to put as much behavior as possible of your Extension into the content script rather than DOM injected scripts.</span></span>  

<!-- image links -->  

<!-- links -->  

[HTML5RocksIntroductionContentSecurityPolicy]: https://www.html5rocks.com/en/tutorials/security/content-security-policy "コンテンツ セキュリティ ポリシーの概要|HTML5 ロック"  
[PublicSuffixList]: https://publicsuffix.org/list "パブリック サフィックス の一覧を表示する"  
[W3CContentSecurityPolicyLevel2ScriptSrcHashUsage]: https://www.w3.org/TR/CSP2#script-src-hash-usage "\<script\>要素のハッシュ使用法 - コンテンツ セキュリティ ポリシー レベル 2 |W3C"  
[W3CContentSecurityPolicy]: https://w3c.github.io/webappsec-csp "コンテンツ セキュリティ ポリシー レベル 3 |W3C"  
[WikiManMiddleAttacks]: https://en.wikipedia.org/wiki/Man-in-the-middle_attack "中間者攻撃|Wikipedia"  

> [!NOTE]
> <span data-ttu-id="796c3-202">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="796c3-202">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="796c3-203">元のページは次 [のページに表示されます](https://developer.chrome.com/extensions/contentSecurityPolicy)。</span><span class="sxs-lookup"><span data-stu-id="796c3-203">The original page is found [here](https://developer.chrome.com/extensions/contentSecurityPolicy).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="796c3-205">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="796c3-205">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
