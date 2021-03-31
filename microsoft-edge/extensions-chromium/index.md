---
description: Microsoft Edge (Chromium) 拡張機能の構築と公開の概要。
title: Microsoft Edge (Chromium) 拡張機能の概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge、拡張機能の開発、ブラウザーの拡張機能、アドオン、パートナー センター、開発者、Chromium の拡張機能
ms.openlocfilehash: 3ed0871883acfb7c3cf08c2da9f47d18ae3465f0
ms.sourcegitcommit: fe7301d0f62493e42e6a1a81cdbda3457f0343b8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2021
ms.locfileid: "11327527"
---
# <span data-ttu-id="d2d61-104">Microsoft Edge (Chromium) 拡張機能の概要</span><span class="sxs-lookup"><span data-stu-id="d2d61-104">Overview of Microsoft Edge (Chromium) Extensions</span></span>  

<span data-ttu-id="d2d61-105">拡張機能は、\(a developer\) が Microsoft Edge \(Chromium\) の機能を追加または変更するために使用する小さなプログラムです。</span><span class="sxs-lookup"><span data-stu-id="d2d61-105">An extension is a small program that you \(a developer\) use to add or modify features for Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="d2d61-106">拡張機能は、ユーザーの毎日の閲覧エクスペリエンスを向上することを目的とします。</span><span class="sxs-lookup"><span data-stu-id="d2d61-106">An extension is intended to improve a user's day-to-day browsing experience.</span></span>  <span data-ttu-id="d2d61-107">ターゲットのユーザーが重要視するニッチな機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="d2d61-107">It provides niche functionality that is important to a target audience.</span></span>  

<span data-ttu-id="d2d61-108">次のいずれかの条件に基づくアイデアや製品がある場合は、拡張機能を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d2d61-108">You may create an extension if you have an idea or product that is based upon either of the following conditions.</span></span>  

*   <span data-ttu-id="d2d61-109">特定の Web ブラウザー。</span><span class="sxs-lookup"><span data-stu-id="d2d61-109">A specific web browser.</span></span>  
*   <span data-ttu-id="d2d61-110">特定の Web ページの機能の改善。</span><span class="sxs-lookup"><span data-stu-id="d2d61-110">Improvements to features of specific webpages.</span></span>  
    
<span data-ttu-id="d2d61-111">コンパニオン エクスペリエンスの例としては、アド ブロッカーやパスワード マネージャーなどがあります。</span><span class="sxs-lookup"><span data-stu-id="d2d61-111">Examples of companion experiences include ad blockers and password managers.</span></span>  

<span data-ttu-id="d2d61-112">拡張機能は、通常の web アプリと同じように構成されています。</span><span class="sxs-lookup"><span data-stu-id="d2d61-112">An extension is structured similar to a regular web app.</span></span>  <span data-ttu-id="d2d61-113">少なくとも、次の機能を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2d61-113">At a minimum, it should include the following features.</span></span>

*   <span data-ttu-id="d2d61-114">基本的なプラットフォーム情報を含むアプリ マニフェスト JSON ファイル。</span><span class="sxs-lookup"><span data-stu-id="d2d61-114">An app manifest JSON file that contains basic platform information.</span></span>  
*   <span data-ttu-id="d2d61-115">機能を定義する JavaScript ファイル。</span><span class="sxs-lookup"><span data-stu-id="d2d61-115">A JavaScript file that define functionality.</span></span>  
*   <span data-ttu-id="d2d61-116">ユーザー インターフェイスを定義する HTML ファイルと CSS ファイル。</span><span class="sxs-lookup"><span data-stu-id="d2d61-116">HTML and CSS files that define the user interface.</span></span>  

<span data-ttu-id="d2d61-117">ウィンドウやタブなど、ブラウザーの一部を直接操作するには、API リクエストを送信し、多くの場合、名前でブラウザーを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2d61-117">To work directly with part of the browser, such as a window or tab, you must send API requests and often reference the browser by name.</span></span>  

:::image type="complex" source="./media/example-extension-screenshot.png" alt-text="Microsoft Edge (Chromium) 拡張機能" lightbox="./media/example-extension-screenshot.png":::
  <span data-ttu-id="d2d61-119">Microsoft Edge \(Chromium \) 拡張機能</span><span class="sxs-lookup"><span data-stu-id="d2d61-119">A Microsoft Edge \(Chromium\) extension</span></span>  
:::image-end:::  

## <span data-ttu-id="d2d61-120">基本的なガイダンス</span><span class="sxs-lookup"><span data-stu-id="d2d61-120">Basic guidance</span></span>  

<span data-ttu-id="d2d61-121">拡張機能の構築のための最も一般的なブラウザーの一部には、Safari、Firefox、Chrome、Opera、Brave、Microsoft Edge などがあります。</span><span class="sxs-lookup"><span data-stu-id="d2d61-121">Some of the most popular browsers to build extensions for include Safari, Firefox, Chrome, Opera, Brave, and Microsoft Edge.</span></span>  <span data-ttu-id="d2d61-122">拡張機能の開発に関するチュートリアルとドキュメントの調査を始めるのに最適な場所は、ブラウザー組織によってホストされているサイトです。</span><span class="sxs-lookup"><span data-stu-id="d2d61-122">Great places to begin your extension development tutorials and documentation research are sites hosted by the browser organizations.</span></span>  <span data-ttu-id="d2d61-123">次の表は最終的なものではなく、開始点として使用できます。</span><span class="sxs-lookup"><span data-stu-id="d2d61-123">The following table isn't definitive, and may be used as a starting point.</span></span>  

| <span data-ttu-id="d2d61-124">Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="d2d61-124">Web browser</span></span> | <span data-ttu-id="d2d61-125">Chromium ベースの場合</span><span class="sxs-lookup"><span data-stu-id="d2d61-125">Chromium-based?</span></span> | <span data-ttu-id="d2d61-126">拡張機能の開発 Web ページ</span><span class="sxs-lookup"><span data-stu-id="d2d61-126">Extension development webpage</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="d2d61-127">Safari</span><span class="sxs-lookup"><span data-stu-id="d2d61-127">Safari</span></span> | <span data-ttu-id="d2d61-128">いいえ</span><span class="sxs-lookup"><span data-stu-id="d2d61-128">No</span></span> | [<span data-ttu-id="d2d61-129">developer.apple.com/documentation/safariservices/safari_app_extensions</span><span class="sxs-lookup"><span data-stu-id="d2d61-129">developer.apple.com/documentation/safariservices/safari_app_extensions</span></span>][AppleDeveloperSafariservicesAppExtensions] |  
| <span data-ttu-id="d2d61-130">Firefox</span><span class="sxs-lookup"><span data-stu-id="d2d61-130">Firefox</span></span> | <span data-ttu-id="d2d61-131">いいえ</span><span class="sxs-lookup"><span data-stu-id="d2d61-131">No</span></span> | [<span data-ttu-id="d2d61-132">developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions</span><span class="sxs-lookup"><span data-stu-id="d2d61-132">developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions</span></span>][MDNWebextensions] |  
| <span data-ttu-id="d2d61-133">クロム</span><span class="sxs-lookup"><span data-stu-id="d2d61-133">Chrome</span></span> | <span data-ttu-id="d2d61-134">はい</span><span class="sxs-lookup"><span data-stu-id="d2d61-134">Yes</span></span> | [<span data-ttu-id="d2d61-135">developer.chrome.com/extensions</span><span class="sxs-lookup"><span data-stu-id="d2d61-135">developer.chrome.com/extensions</span></span>][ChromeDeveloperExtensions] |  
| <span data-ttu-id="d2d61-136">Opera</span><span class="sxs-lookup"><span data-stu-id="d2d61-136">Opera</span></span> | <span data-ttu-id="d2d61-137">はい</span><span class="sxs-lookup"><span data-stu-id="d2d61-137">Yes</span></span> | [<span data-ttu-id="d2d61-138">dev.opera.com/extensions</span><span class="sxs-lookup"><span data-stu-id="d2d61-138">dev.opera.com/extensions</span></span>][OperaDevExtensions] |  
| <span data-ttu-id="d2d61-139">Brave</span><span class="sxs-lookup"><span data-stu-id="d2d61-139">Brave</span></span> | <span data-ttu-id="d2d61-140">はい</span><span class="sxs-lookup"><span data-stu-id="d2d61-140">Yes</span></span> | <span data-ttu-id="d2d61-141">[Chrome Web ストア][GoogleChromeWebstoreCategoryExtensions]を使用します</span><span class="sxs-lookup"><span data-stu-id="d2d61-141">Uses [Chrome Web Store][GoogleChromeWebstoreCategoryExtensions]</span></span> |  
| <span data-ttu-id="d2d61-142">新しい Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d2d61-142">new Microsoft Edge</span></span> | <span data-ttu-id="d2d61-143">はい</span><span class="sxs-lookup"><span data-stu-id="d2d61-143">Yes</span></span> | [<span data-ttu-id="d2d61-144">developer.microsoft.com/microsoft-edge/extensions</span><span class="sxs-lookup"><span data-stu-id="d2d61-144">developer.microsoft.com/microsoft-edge/extensions</span></span>][MicrosoftDeveloperEdgeExtensions] |  

> [!IMPORTANT]
> <span data-ttu-id="d2d61-145">サイトの多くのチュートリアルでは、開発しているブラウザーと一致しない可能性のあるブラウザー固有の API を使用しています。</span><span class="sxs-lookup"><span data-stu-id="d2d61-145">Many of the tutorials of the sites use browser-specific APIs that may not match the browser for which you develop.</span></span>  <span data-ttu-id="d2d61-146">ほとんどの場合、Chromium 拡張機能は、異なる Chromium ブラウザーで動作しており、API は期待どおりに動作します。</span><span class="sxs-lookup"><span data-stu-id="d2d61-146">In most cases, a Chromium extension works as-is in different Chromium browsers and the APIs work as expected.</span></span>  <span data-ttu-id="d2d61-147">一般的ではない一部の API は、厳密にはブラウザー固有のものである場合があります。</span><span class="sxs-lookup"><span data-stu-id="d2d61-147">Only some less common APIs may be strictly browser-specific.</span></span>  <span data-ttu-id="d2d61-148">チュートリアルへのリンクについては、[関連項目](#see-also) に移動します。</span><span class="sxs-lookup"><span data-stu-id="d2d61-148">For links to the tutorials, navigate to [See also](#see-also).</span></span>  

## <span data-ttu-id="d2d61-149">Chromium を使用する理由</span><span class="sxs-lookup"><span data-stu-id="d2d61-149">Why Chromium?</span></span>  

<span data-ttu-id="d2d61-150">拡張機能を拡張ストアで公開することを目標としている場合は、それぞれ別のブラウザー環境でターゲットを指定して実行できるようにするために、複数のバージョンを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2d61-150">If your goal is to publish your extension in the extensions store for each browser, it must be modified for each version to target and run in each distinct browser environment.</span></span>  <span data-ttu-id="d2d61-151">たとえば、[Safari extensions][AppleDeveloperSafariservicesAppExtensions] は、Web とネイティブ コードの両方を活用して、もう一方のネイティブ アプリケーションとの通信に使用できます。</span><span class="sxs-lookup"><span data-stu-id="d2d61-151">For example, [Safari extensions][AppleDeveloperSafariservicesAppExtensions] may use both web and native code to communicate with counterpart native applications.</span></span>  <span data-ttu-id="d2d61-152">前の表の最後の 4 つのブラウザーは同じコード パッケージを使用し、並列バージョンを維持するための要件を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="d2d61-152">The last four browsers in the previous table use the same code package, and minimizes the requirement to maintain parallel versions.</span></span>  <span data-ttu-id="d2d61-153">これは、ブラウザーが [Chromium のオープンソース プロジェクト][|::ref1::|Home]に基づいています。</span><span class="sxs-lookup"><span data-stu-id="d2d61-153">These browsers are based on the [Chromium open-source project][|::ref1::|Home].</span></span>  

<span data-ttu-id="d2d61-154">Chromium の拡張機能を作成して、最小量のコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="d2d61-154">Create a Chromium extension to write the least amount of code.</span></span>  <span data-ttu-id="d2d61-155">また、拡張ストアの最大数と、最終的に拡張機能を検出して取得するユーザーの最大数もターゲットに指定します。</span><span class="sxs-lookup"><span data-stu-id="d2d61-155">It also targets the maximum number of extension stores and ultimately the maximum number of users who find and acquire your extension.</span></span>  

<span data-ttu-id="d2d61-156">次のコンテンツでは、Chromium の拡張機能に焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="d2d61-156">The following content focuses mostly on Chromium extensions.</span></span>  

## <span data-ttu-id="d2d61-157">ブラウザーの互換性と拡張テスト</span><span class="sxs-lookup"><span data-stu-id="d2d61-157">Browser compatibility and extension testing</span></span>  

<span data-ttu-id="d2d61-158">場合によっては、Chromium ブラウザーの間に API パリティが存在しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="d2d61-158">Occasionally, API parity doesn't exist between Chromium browsers.</span></span>  <span data-ttu-id="d2d61-159">たとえば、ID と API 支払いには違いがあります。</span><span class="sxs-lookup"><span data-stu-id="d2d61-159">For example, there are differences in the identity and payment APIs.</span></span>  <span data-ttu-id="d2d61-160">拡張機能が顧客の期待を満たするようにするには、次の公式ブラウザー ドキュメントを通して API の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="d2d61-160">To ensure your extension meets customer expectations, review API status through the following official browser docs.</span></span>  

*   [<span data-ttu-id="d2d61-161">Chrome API</span><span class="sxs-lookup"><span data-stu-id="d2d61-161">Chrome APIs</span></span>][ChromeDeveloperExtensionsApiIndex]  
*   [<span data-ttu-id="d2d61-162">Opera でサポートされる拡張 API</span><span class="sxs-lookup"><span data-stu-id="d2d61-162">Extension APIs supported in Opera</span></span>][OperaDevExtensionsApis]  
*   [<span data-ttu-id="d2d61-163">Chrome 拡張機能を Microsoft Edge (Chromium) に移植する</span><span class="sxs-lookup"><span data-stu-id="d2d61-163">Port Chrome extension to Microsoft Edge (Chromium)</span></span>][ExtensionsChromiumDeveloperGuidePortChrome]  
    
<span data-ttu-id="d2d61-164">必要な API は、各ブラウザー間の違いに対処するために行う必要がある変更を定義します。</span><span class="sxs-lookup"><span data-stu-id="d2d61-164">The APIs you require define the changes you must make to address the differences between each browser.</span></span>  <span data-ttu-id="d2d61-165">つまり、ストアごとに少しずつ異なるコード パッケージを作成することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d2d61-165">It may mean that you must create slightly different code packages with small differences for each store.</span></span>  

<span data-ttu-id="d2d61-166">ブラウザー ストアに提出する前に、さまざまな環境で拡張機能をテストするには、開発中にブラウザーにサイドロードします。</span><span class="sxs-lookup"><span data-stu-id="d2d61-166">To test your extension in different environments before you submit it to a browser store, sideload it into your browser while you develop it.</span></span>  

## <span data-ttu-id="d2d61-167">拡張機能をブラウザー ストアに公開する</span><span class="sxs-lookup"><span data-stu-id="d2d61-167">Publish your extension to browser stores</span></span>  

<span data-ttu-id="d2d61-168">次のブラウザー ストアで、ブラウザーの拡張機能の提出、検索を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d2d61-168">You may submit and seek browser extensions in the following browser stores.</span></span>  

*   [<span data-ttu-id="d2d61-169">Firefox ブラウザーのアドオン</span><span class="sxs-lookup"><span data-stu-id="d2d61-169">Firefox Browser Add-ons</span></span>][MozillaAddonsFirefoxExtensions]  
*   [<span data-ttu-id="d2d61-170">Chrome Web ストア</span><span class="sxs-lookup"><span data-stu-id="d2d61-170">Chrome Web Store</span></span>][GoogleChromeWebstoreCategoryExtensions]  
*   [<span data-ttu-id="d2d61-171">Opera のアドオン</span><span class="sxs-lookup"><span data-stu-id="d2d61-171">Opera addons</span></span>][OperaAddonsExtensions]  
*   [<span data-ttu-id="d2d61-172">Microsoft Edge アドオン</span><span class="sxs-lookup"><span data-stu-id="d2d61-172">Microsoft Edge Add-ons</span></span>][MicrosoftEdgeAddonsCategoryExtensions]  

<span data-ttu-id="d2d61-173">一部のストアでは、他のブラウザーからリストされた拡張機能をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="d2d61-173">Some stores allow you to download listed extensions from other browsers.</span></span>  <span data-ttu-id="d2d61-174">ただし、ブラウザー ストアでは、ブラウザー間のアクセスは保証されません。</span><span class="sxs-lookup"><span data-stu-id="d2d61-174">However, cross-browser access is not guaranteed by browser stores.</span></span>  <span data-ttu-id="d2d61-175">ユーザーが異なるブラウザーで拡張機能を見つけるには、各ブラウザー拡張機能ストアでリストを維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2d61-175">To ensure your users find your extension in different browsers, you should maintain a listing on each browser extension store.</span></span>  

<span data-ttu-id="d2d61-176">ユーザーが異なるブラウザーに拡張機能をインストールすることが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d2d61-176">Users may need to install your extension in different browsers.</span></span> <span data-ttu-id="d2d61-177">このシナリオでは、あるブラウザーから別のブラウザーに既存の Chromium 拡張機能を移行できます。</span><span class="sxs-lookup"><span data-stu-id="d2d61-177">In this scenario, you may migrate existing Chromium extensions from one browser to another.</span></span>  

### <span data-ttu-id="d2d61-178">既存の拡張機能を Microsoft Edge に移行する</span><span class="sxs-lookup"><span data-stu-id="d2d61-178">Migrate an existing extension to Microsoft Edge</span></span>  

<span data-ttu-id="d2d61-179">既に別の Chromium ブラウザー用の拡張機能を開発している場合は、Microsoft Edge アドオン ストアに提出できます。</span><span class="sxs-lookup"><span data-stu-id="d2d61-179">If you've already developed an extension for another Chromium browser, you may submit it to the Microsoft Edge Add-ons store.</span></span> <span data-ttu-id="d2d61-180">拡張機能を書き換える必要はなく、Microsoft Edge で動作することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2d61-180">You don't need to rewrite your extension, and must verify it works in Microsoft Edge.</span></span>  <span data-ttu-id="d2d61-181">既存の Chromium 拡張機能を他の Chromium ブラウザーに移行する場合は、ターゲット ブラウザーで同じ API または代替手段を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d2d61-181">When you migrate an existing Chromium extension to other Chromium browsers, ensure the same APIs or alternatives are available for your target browser.</span></span>  

<span data-ttu-id="d2d61-182">Chrome 拡張機能を Microsoft Edge に移植する方法の詳細については、[Microsoft Edge (Chromium) の Chrome 拡張機能移植][ExtensionsChromiumDeveloperGuidePortChrome]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2d61-182">For more information on porting your Chrome extension to Microsoft Edge, navigate to [Port Chrome extensions to Microsoft Edge (Chromium)][ExtensionsChromiumDeveloperGuidePortChrome].</span></span> <span data-ttu-id="d2d61-183">ターゲット ブラウザーに拡張機能を移植したら、次の手順で公開することができます。</span><span class="sxs-lookup"><span data-stu-id="d2d61-183">After you port your extension to the target browser, the next step is to publish it.</span></span>  

### <span data-ttu-id="d2d61-184">Microsoft Edge のアドオン web サイトに公開</span><span class="sxs-lookup"><span data-stu-id="d2d61-184">Publish to the Microsoft Edge add-ons website</span></span>  

<span data-ttu-id="d2d61-185">Microsoft Edge への拡張機能の公開を開始するには、MSA メールアカウントを持つ [開発者アカウントに登録][MicrosoftDeveloperRegistration] して、拡張機能のリストをストアに提出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2d61-185">To start publishing your extension to Microsoft Edge, you must [register for a developer account][MicrosoftDeveloperRegistration] with an MSA email account to submit your extension listing to the store.</span></span>  <span data-ttu-id="d2d61-186">MSAのメールアカウントには、`@outlook.com`、`@live.com` などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d2d61-186">An MSA email account includes `@outlook.com`, `@live.com`, and so on.</span></span>  <span data-ttu-id="d2d61-187">登録するメールアドレスを選択する場合は、組織内の他のユーザーと拡張機能の所有権を移転または共有する必要があるかどうかを検討してください。</span><span class="sxs-lookup"><span data-stu-id="d2d61-187">When you choose an email address to register, consider if you must transfer or share ownership of the extension with others in your organization.</span></span>  <span data-ttu-id="d2d61-188">登録が完了したら、ストアに新しい拡張機能の申請を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="d2d61-188">After registration is complete, you may create a new extension submission to the store.</span></span>  

<span data-ttu-id="d2d61-189">拡張機能をストアに提出するには、次の項目を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2d61-189">To submit your extension to the store, ensure you provide the following items.</span></span>  

*   <span data-ttu-id="d2d61-190">コード ファイルを含むアーカイブ \(`.zip`\) ファイル。</span><span class="sxs-lookup"><span data-stu-id="d2d61-190">An archive \(`.zip`\) file that contains your code files.</span></span>  
*   <span data-ttu-id="d2d61-191">ロゴと小規模プロモーション タイルなどの必要なすべてのビジュアル資産。</span><span class="sxs-lookup"><span data-stu-id="d2d61-191">All required visual assets, which include a logo and small promotional tile.</span></span>  
*   <span data-ttu-id="d2d61-192">スクリーンショット、プロモーション タイル、ビデオ URL などのオプションのプロモーション メディア。</span><span class="sxs-lookup"><span data-stu-id="d2d61-192">Optional promotional media, such as screenshots, promotional tiles, and a video URL.</span></span>  
*   <span data-ttu-id="d2d61-193">名前、短い説明、プライバシー ポリシーへのリンクなど、拡張機能について説明する情報。</span><span class="sxs-lookup"><span data-stu-id="d2d61-193">Information that describes your extension such as the name, short description, and a privacy policy link.</span></span>  

> [!NOTE]
> <span data-ttu-id="d2d61-194">ストアによって、送信要件が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d2d61-194">Different stores may have different submission requirements.</span></span>  <span data-ttu-id="d2d61-195">上記のリストは、Microsoft Edge に拡張機能を公開するための [要件][ExtensionsChromiumPublish] をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="d2d61-195">The above list summarizes the [requirements][ExtensionsChromiumPublish] to publish an extension for Microsoft Edge.</span></span>  

<span data-ttu-id="d2d61-196">拡張機能を正常に提出した後、拡張機能にはレビュー プロセスが適用され、認定プロセスに合格または不合格になります。</span><span class="sxs-lookup"><span data-stu-id="d2d61-196">After you've successfully submitted your extension, your extension undergoes a review process and either passes or fails the certification process.</span></span>  <span data-ttu-id="d2d61-197">所有者には、結果が通知され、必要に応じて次の手順が示されます。</span><span class="sxs-lookup"><span data-stu-id="d2d61-197">Owners are notified of the outcome and given next steps as required.</span></span>  <span data-ttu-id="d2d61-198">拡張機能の更新プログラムをストアに提出すると、新しいレビュー プロセスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="d2d61-198">If you submit an extension update to the store, a new review process is started.</span></span>  

## <span data-ttu-id="d2d61-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="d2d61-199">See also</span></span>  

*   [<span data-ttu-id="d2d61-200">Google Chrome 拡張機能を移植する</span><span class="sxs-lookup"><span data-stu-id="d2d61-200">Port a Google Chrome extension</span></span>][ExtensionworkshopPorting]  
*   [<span data-ttu-id="d2d61-201">Safari アプリの拡張機能を構築する</span><span class="sxs-lookup"><span data-stu-id="d2d61-201">Build a Safari App extension</span></span>][AppleDeveloperSafariservicesAppExtensionsBuilding]  
*   [<span data-ttu-id="d2d61-202">初めての拡張機能 (Firefox)</span><span class="sxs-lookup"><span data-stu-id="d2d61-202">Your first extension (Firefox)</span></span>][MDNWebextensionsYourFirst]  
*   [<span data-ttu-id="d2d61-203">チュートリアルの開始 (Chrome)</span><span class="sxs-lookup"><span data-stu-id="d2d61-203">Get started tutorial (Chrome)</span></span>][ChromeDeveloperExtensionsGetstarted]  
*   [<span data-ttu-id="d2d61-204">作業の開始 (Opera)</span><span class="sxs-lookup"><span data-stu-id="d2d61-204">Get started (Opera)</span></span>][OperaDevExtensionsGettingStarted]  
*   [<span data-ttu-id="d2d61-205">Microsoft Edge (Chromium) 拡張機能の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="d2d61-205">Get started with Microsoft Edge (Chromium) extensions</span></span>][ExtensionsChromiumGettingStartedIndex]  

<!-- links -->  

[ExtensionsChromiumDeveloperGuidePortChrome]: ./developer-guide/port-chrome-extension.md "Microsoft Edge (Chromium) へのChrome 拡張機能移植 | Microsoft Docs"  
[ExtensionsChromiumGettingStartedIndex]: ./getting-started/index.md "Microsoft Edge (Chromium) の拡張機能をお使いになる前に | Microsoft Docs"  
[ExtensionsChromiumPublish]: ./publish/publish-extension.md "拡張機能公開 | Microsoft Docs"  

[MicrosoftDeveloperEdgeExtensions]: https://developer.microsoft.com/microsoft-edge/extensions "Microsoft Edge 用拡張機能開発 | Microsoft デベロッパー"  
[MicrosoftDeveloperRegistration]: https://developer.microsoft.com/registration "パートナーセンター | Microsoft デベロッパー"  

[MicrosoftEdgeAddonsCategoryExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge 用拡張機能 | Microsoft Edge"  

[AppleDeveloperSafariservicesAppExtensions]: https://developer.apple.com/documentation/safariservices/safari_app_extensions "Safari アプリ用拡張機能 | Apple デベロッパー"  
[AppleDeveloperSafariservicesAppExtensionsBuilding]: https://developer.apple.com/documentation/safariservices/safari_app_extensions/building_a_safari_app_extension "Safari アプリ拡張機能構築 | Apple デベロッパー"  

[ChromeDeveloperExtensions]: https://developer.chrome.com/extensions "拡張機能とは | Chrome デベロッパー"  
[ChromeDeveloperExtensionsApiIndex]: https://developer.chrome.com/extensions/api_index "Chrome API | Chrome デベロッパー"  
[ChromeDeveloperExtensionsGetstarted]: https://developer.chrome.com/extensions/getstarted "はじめのチュートリアル | Chrome デベロッパー"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium"  

[ExtensionworkshopPorting]: https://extensionworkshop.com/documentation/develop/porting-a-google-chrome-extension "Google Chrome 拡張機能移植 | 拡張機能ワークショップ"  

[GoogleChromeWebstoreCategoryExtensions]: https://chrome.google.com/webstore/category/extensions "拡張機能 | Chrome Web ストア"  

[MDNWebextensions]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions "ブラウザーの拡張機能 | MDN"  
[MDNWebextensionsYourFirst]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/Your_first_WebExtension "初めての拡張機能 | MDN"  

[MozillaAddonsFirefoxExtensions]: https://addons.mozilla.org/firefox/extensions "拡張機能 | Firefox 用のアドオン"  

[OperaAddonsExtensions]: https://addons.opera.com/extensions "拡張機能 | Opera 用のアドオン"  

[OperaDevExtensions]: https://dev.opera.com/extensions "拡張機能のドキュメント |Dev. Opera"  
[OperaDevExtensionsApis]: https://dev.opera.com/extensions/apis "Opera | でサポートされる拡張 API | Dev. Opera"  
[OperaDevExtensionsGettingStarted]: https://dev.opera.com/extensions/getting-started "はじめに | Dev. Opera"  
