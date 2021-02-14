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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2021
ms.locfileid: "11327527"
---
# <span data-ttu-id="7c074-104">Microsoft Edge (Chromium) 拡張機能の概要</span><span class="sxs-lookup"><span data-stu-id="7c074-104">Overview of Microsoft Edge (Chromium) Extensions</span></span>  

<span data-ttu-id="7c074-105">拡張機能は、Microsoft Edge \(Chromium\) の機能を追加または変更するために\(開発者\) 使用する小規模なプログラムです。</span><span class="sxs-lookup"><span data-stu-id="7c074-105">An extension is a small program that you \(a developer\) use to add or modify features for Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="7c074-106">拡張機能は、ユーザーの毎日の閲覧エクスペリエンスを向上することを目的とします。</span><span class="sxs-lookup"><span data-stu-id="7c074-106">An extension is intended to improve a user's day-to-day browsing experience.</span></span>  <span data-ttu-id="7c074-107">対象ユーザーにとって重要な、優れた機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="7c074-107">It provides niche functionality that is important to a target audience.</span></span>  

<span data-ttu-id="7c074-108">次のいずれかの条件に基づくアイデアまたは製品がある場合は、拡張機能を作成できます。</span><span class="sxs-lookup"><span data-stu-id="7c074-108">You may create an extension if you have an idea or product that is based upon either of the following conditions.</span></span>  

*   <span data-ttu-id="7c074-109">特定の Web ブラウザー。</span><span class="sxs-lookup"><span data-stu-id="7c074-109">A specific web browser.</span></span>  
*   <span data-ttu-id="7c074-110">特定の Web ページの機能が向上しました。</span><span class="sxs-lookup"><span data-stu-id="7c074-110">Improvements to features of specific webpages.</span></span>  
    
<span data-ttu-id="7c074-111">コンパニオン エクスペリエンスの例としては、広告のブロックやパスワード マネージャーがあります。</span><span class="sxs-lookup"><span data-stu-id="7c074-111">Examples of companion experiences include ad blockers and password managers.</span></span>  

<span data-ttu-id="7c074-112">拡張機能は、通常の web アプリと同じように構成されています。</span><span class="sxs-lookup"><span data-stu-id="7c074-112">An extension is structured similar to a regular web app.</span></span>  <span data-ttu-id="7c074-113">少なくとも、次の機能が含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c074-113">At a minimum, it should include the following features.</span></span>

*   <span data-ttu-id="7c074-114">基本的なプラットフォーム情報を含むアプリ マニフェスト JSON ファイル。</span><span class="sxs-lookup"><span data-stu-id="7c074-114">An app manifest JSON file that contains basic platform information.</span></span>  
*   <span data-ttu-id="7c074-115">機能を定義する JavaScript ファイル。</span><span class="sxs-lookup"><span data-stu-id="7c074-115">A JavaScript file that define functionality.</span></span>  
*   <span data-ttu-id="7c074-116">ユーザー インターフェイスを定義する HTML ファイルと CSS ファイル。</span><span class="sxs-lookup"><span data-stu-id="7c074-116">HTML and CSS files that define the user interface.</span></span>  

<span data-ttu-id="7c074-117">ウィンドウやタブなど、ブラウザーの一部を直接操作するには、API リクエストを送信し、多くの場合、名前でブラウザーを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c074-117">To work directly with part of the browser, such as a window or tab, you must send API requests and often reference the browser by name.</span></span>  

:::image type="complex" source="./media/example-extension-screenshot.png" alt-text="Microsoft Edge (Chromium) 拡張機能" lightbox="./media/example-extension-screenshot.png":::
  <span data-ttu-id="7c074-119">Microsoft Edge \ (Chromium \) 拡張機能</span><span class="sxs-lookup"><span data-stu-id="7c074-119">A Microsoft Edge \(Chromium\) extension</span></span>  
:::image-end:::  

## <span data-ttu-id="7c074-120">基本的なガイダンス</span><span class="sxs-lookup"><span data-stu-id="7c074-120">Basic guidance</span></span>  

<span data-ttu-id="7c074-121">Safari、Firefox、Chrome、Opera、Safari、Microsoft Edge などの拡張機能を構築する最も一般的なブラウザーの一部です。</span><span class="sxs-lookup"><span data-stu-id="7c074-121">Some of the most popular browsers to build extensions for include Safari, Firefox, Chrome, Opera, Brave, and Microsoft Edge.</span></span>  <span data-ttu-id="7c074-122">拡張機能の開発に関するチュートリアルとドキュメントの調査を始めるのに最適な場所は、ブラウザー組織によってホストされているサイトです。</span><span class="sxs-lookup"><span data-stu-id="7c074-122">Great places to begin your extension development tutorials and documentation research are sites hosted by the browser organizations.</span></span>  <span data-ttu-id="7c074-123">次の表は確定的ではありません。開始点として使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c074-123">The following table isn't definitive, and may be used as a starting point.</span></span>  

| <span data-ttu-id="7c074-124">Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="7c074-124">Web browser</span></span> | <span data-ttu-id="7c074-125">Chromium ベースの場合</span><span class="sxs-lookup"><span data-stu-id="7c074-125">Chromium-based?</span></span> | <span data-ttu-id="7c074-126">拡張機能開発 Web ページ</span><span class="sxs-lookup"><span data-stu-id="7c074-126">Extension development webpage</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7c074-127">Safari</span><span class="sxs-lookup"><span data-stu-id="7c074-127">Safari</span></span> | <span data-ttu-id="7c074-128">いいえ</span><span class="sxs-lookup"><span data-stu-id="7c074-128">No</span></span> | [<span data-ttu-id="7c074-129">developer.apple.com/documentation/safariservices/safari_app_extensions</span><span class="sxs-lookup"><span data-stu-id="7c074-129">developer.apple.com/documentation/safariservices/safari_app_extensions</span></span>][AppleDeveloperSafariservicesAppExtensions] |  
| <span data-ttu-id="7c074-130">Firefox</span><span class="sxs-lookup"><span data-stu-id="7c074-130">Firefox</span></span> | <span data-ttu-id="7c074-131">いいえ</span><span class="sxs-lookup"><span data-stu-id="7c074-131">No</span></span> | [<span data-ttu-id="7c074-132">developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions</span><span class="sxs-lookup"><span data-stu-id="7c074-132">developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions</span></span>][MDNWebextensions] |  
| <span data-ttu-id="7c074-133">クロム</span><span class="sxs-lookup"><span data-stu-id="7c074-133">Chrome</span></span> | <span data-ttu-id="7c074-134">はい</span><span class="sxs-lookup"><span data-stu-id="7c074-134">Yes</span></span> | [<span data-ttu-id="7c074-135">developer.chrome.com/extensions</span><span class="sxs-lookup"><span data-stu-id="7c074-135">developer.chrome.com/extensions</span></span>][ChromeDeveloperExtensions] |  
| <span data-ttu-id="7c074-136">Opera</span><span class="sxs-lookup"><span data-stu-id="7c074-136">Opera</span></span> | <span data-ttu-id="7c074-137">はい</span><span class="sxs-lookup"><span data-stu-id="7c074-137">Yes</span></span> | [<span data-ttu-id="7c074-138">dev.opera.com/extensions</span><span class="sxs-lookup"><span data-stu-id="7c074-138">dev.opera.com/extensions</span></span>][OperaDevExtensions] |  
| <span data-ttu-id="7c074-139">Brave</span><span class="sxs-lookup"><span data-stu-id="7c074-139">Brave</span></span> | <span data-ttu-id="7c074-140">はい</span><span class="sxs-lookup"><span data-stu-id="7c074-140">Yes</span></span> | <span data-ttu-id="7c074-141">[Chrome Web ストア][GoogleChromeWebstoreCategoryExtensions]を使用します</span><span class="sxs-lookup"><span data-stu-id="7c074-141">Uses [Chrome Web Store][GoogleChromeWebstoreCategoryExtensions]</span></span> |  
| <span data-ttu-id="7c074-142">新しい Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7c074-142">new Microsoft Edge</span></span> | <span data-ttu-id="7c074-143">はい</span><span class="sxs-lookup"><span data-stu-id="7c074-143">Yes</span></span> | [<span data-ttu-id="7c074-144">developer.microsoft.com/microsoft-edge/extensions</span><span class="sxs-lookup"><span data-stu-id="7c074-144">developer.microsoft.com/microsoft-edge/extensions</span></span>][MicrosoftDeveloperEdgeExtensions] |  

> [!IMPORTANT]
> <span data-ttu-id="7c074-145">サイトのチュートリアルの多くは、開発するブラウザーと一致しない可能性があるブラウザー固有の API を使用します。</span><span class="sxs-lookup"><span data-stu-id="7c074-145">Many of the tutorials of the sites use browser-specific APIs that may not match the browser for which you develop.</span></span>  <span data-ttu-id="7c074-146">ほとんどの場合、Chromium 拡張機能は、異なる Chromium ブラウザーで動作しており、API は期待どおりに動作します。</span><span class="sxs-lookup"><span data-stu-id="7c074-146">In most cases, a Chromium extension works as-is in different Chromium browsers and the APIs work as expected.</span></span>  <span data-ttu-id="7c074-147">一般的ではない一部の API は、厳密にはブラウザー固有のものである場合があります。</span><span class="sxs-lookup"><span data-stu-id="7c074-147">Only some less common APIs may be strictly browser-specific.</span></span>  <span data-ttu-id="7c074-148">チュートリアルへのリンクについては、[関連情報] [に移動します](#see-also)。</span><span class="sxs-lookup"><span data-stu-id="7c074-148">For links to the tutorials, navigate to [See also](#see-also).</span></span>  

## <span data-ttu-id="7c074-149">Chromium を使用する理由</span><span class="sxs-lookup"><span data-stu-id="7c074-149">Why Chromium?</span></span>  

<span data-ttu-id="7c074-150">各ブラウザーの拡張機能ストアで拡張機能を公開する場合は、各バージョンで個別のブラウザー環境を対象として実行するように、拡張機能を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c074-150">If your goal is to publish your extension in the extensions store for each browser, it must be modified for each version to target and run in each distinct browser environment.</span></span>  <span data-ttu-id="7c074-151">たとえば [、Safari 拡張機能では、Web][AppleDeveloperSafariservicesAppExtensions] とネイティブ の両方のコードを使用して、対応するネイティブ アプリケーションと通信できます。</span><span class="sxs-lookup"><span data-stu-id="7c074-151">For example, [Safari extensions][AppleDeveloperSafariservicesAppExtensions] may use both web and native code to communicate with counterpart native applications.</span></span>  <span data-ttu-id="7c074-152">前の表の最後の 4 つのブラウザーは同じコード パッケージを使用し、並列バージョンを維持するための要件を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="7c074-152">The last four browsers in the previous table use the same code package, and minimizes the requirement to maintain parallel versions.</span></span>  <span data-ttu-id="7c074-153">これらのブラウザーは Chromium オープン ソース [プロジェクトに基づいて作成されています][|::ref1::|Home]。</span><span class="sxs-lookup"><span data-stu-id="7c074-153">These browsers are based on the [Chromium open-source project][|::ref1::|Home].</span></span>  

<span data-ttu-id="7c074-154">Chromium 拡張機能を作成して、最小量のコードを書き込む。</span><span class="sxs-lookup"><span data-stu-id="7c074-154">Create a Chromium extension to write the least amount of code.</span></span>  <span data-ttu-id="7c074-155">また、拡張機能ストアの最大数と、拡張機能を見つけて取得するユーザーの最終的な最大数も対象とします。</span><span class="sxs-lookup"><span data-stu-id="7c074-155">It also targets the maximum number of extension stores and ultimately the maximum number of users who find and acquire your extension.</span></span>  

<span data-ttu-id="7c074-156">次のコンテンツでは、Chromium の拡張機能に焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="7c074-156">The following content focuses mostly on Chromium extensions.</span></span>  

## <span data-ttu-id="7c074-157">ブラウザーの互換性と拡張テスト</span><span class="sxs-lookup"><span data-stu-id="7c074-157">Browser compatibility and extension testing</span></span>  

<span data-ttu-id="7c074-158">Chromium ブラウザー間に API パリティが存在しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="7c074-158">Occasionally, API parity doesn't exist between Chromium browsers.</span></span>  <span data-ttu-id="7c074-159">たとえば、ID と API 支払いには違いがあります。</span><span class="sxs-lookup"><span data-stu-id="7c074-159">For example, there are differences in the identity and payment APIs.</span></span>  <span data-ttu-id="7c074-160">拡張機能が顧客の期待を満たするように、次の公式ブラウザー ドキュメントを通じて API の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="7c074-160">To ensure your extension meets customer expectations, review API status through the following official browser docs.</span></span>  

*   [<span data-ttu-id="7c074-161">Chrome API</span><span class="sxs-lookup"><span data-stu-id="7c074-161">Chrome APIs</span></span>][ChromeDeveloperExtensionsApiIndex]  
*   [<span data-ttu-id="7c074-162">Opera でサポートされている拡張 API</span><span class="sxs-lookup"><span data-stu-id="7c074-162">Extension APIs supported in Opera</span></span>][OperaDevExtensionsApis]  
*   [<span data-ttu-id="7c074-163">Chrome 拡張機能を Microsoft Edge に移植する (Chromium)</span><span class="sxs-lookup"><span data-stu-id="7c074-163">Port Chrome extension to Microsoft Edge (Chromium)</span></span>][ExtensionsChromiumDeveloperGuidePortChrome]  
    
<span data-ttu-id="7c074-164">必要な API は、各ブラウザー間の違いに対処するために行う必要がある変更を定義します。</span><span class="sxs-lookup"><span data-stu-id="7c074-164">The APIs you require define the changes you must make to address the differences between each browser.</span></span>  <span data-ttu-id="7c074-165">これは、ストアごとに少し異なるコード パッケージを作成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="7c074-165">It may mean that you must create slightly different code packages with small differences for each store.</span></span>  

<span data-ttu-id="7c074-166">拡張機能をブラウザー ストアに提出する前に、さまざまな環境で拡張機能をテストするには、開発中にブラウザーにサイドロードします。</span><span class="sxs-lookup"><span data-stu-id="7c074-166">To test your extension in different environments before you submit it to a browser store, sideload it into your browser while you develop it.</span></span>  

## <span data-ttu-id="7c074-167">拡張機能をブラウザー ストアに公開する</span><span class="sxs-lookup"><span data-stu-id="7c074-167">Publish your extension to browser stores</span></span>  

<span data-ttu-id="7c074-168">次のブラウザー ストアで、ブラウザーの拡張機能の提出、検索を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7c074-168">You may submit and seek browser extensions in the following browser stores.</span></span>  

*   [<span data-ttu-id="7c074-169">Firefox ブラウザーのアドオン</span><span class="sxs-lookup"><span data-stu-id="7c074-169">Firefox Browser Add-ons</span></span>][MozillaAddonsFirefoxExtensions]  
*   [<span data-ttu-id="7c074-170">Chrome Web ストア</span><span class="sxs-lookup"><span data-stu-id="7c074-170">Chrome Web Store</span></span>][GoogleChromeWebstoreCategoryExtensions]  
*   [<span data-ttu-id="7c074-171">Opera のアドオン</span><span class="sxs-lookup"><span data-stu-id="7c074-171">Opera addons</span></span>][OperaAddonsExtensions]  
*   [<span data-ttu-id="7c074-172">Microsoft Edge アドオン</span><span class="sxs-lookup"><span data-stu-id="7c074-172">Microsoft Edge Add-ons</span></span>][MicrosoftEdgeAddonsCategoryExtensions]  

<span data-ttu-id="7c074-173">一部のストアでは、他のブラウザーからリストされた拡張機能をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="7c074-173">Some stores allow you to download listed extensions from other browsers.</span></span>  <span data-ttu-id="7c074-174">ただし、ブラウザー ストアでは、ブラウザー間のアクセスは保証されません。</span><span class="sxs-lookup"><span data-stu-id="7c074-174">However, cross-browser access is not guaranteed by browser stores.</span></span>  <span data-ttu-id="7c074-175">ユーザーが異なるブラウザーで拡張機能を見つけるには、各ブラウザー拡張機能ストアに登録情報を保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c074-175">To ensure your users find your extension in different browsers, you should maintain a listing on each browser extension store.</span></span>  

<span data-ttu-id="7c074-176">ユーザーが拡張機能を別のブラウザーにインストールする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="7c074-176">Users may need to install your extension in different browsers.</span></span> <span data-ttu-id="7c074-177">このシナリオでは、既存の Chromium 拡張機能をあるブラウザーから別のブラウザーに移行できます。</span><span class="sxs-lookup"><span data-stu-id="7c074-177">In this scenario, you may migrate existing Chromium extensions from one browser to another.</span></span>  

### <span data-ttu-id="7c074-178">既存の拡張機能を Microsoft Edge に移行する</span><span class="sxs-lookup"><span data-stu-id="7c074-178">Migrate an existing extension to Microsoft Edge</span></span>  

<span data-ttu-id="7c074-179">既に別の Chromium ブラウザー用の拡張機能を開発している場合は、Microsoft Edge アドオン ストアに提出できます。</span><span class="sxs-lookup"><span data-stu-id="7c074-179">If you've already developed an extension for another Chromium browser, you may submit it to the Microsoft Edge Add-ons store.</span></span> <span data-ttu-id="7c074-180">拡張機能を書き換える必要はなく、Microsoft Edge で動作を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c074-180">You don't need to rewrite your extension, and must verify it works in Microsoft Edge.</span></span>  <span data-ttu-id="7c074-181">既存の Chromium 拡張機能を他の Chromium ブラウザーに移行する場合は、ターゲット ブラウザーで同じ API または代替機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c074-181">When you migrate an existing Chromium extension to other Chromium browsers, ensure the same APIs or alternatives are available for your target browser.</span></span>  

<span data-ttu-id="7c074-182">Chrome 拡張機能を Microsoft Edge に移植する方法について詳しくは、「Chrome 拡張機能を [Microsoft Edge (Chromium)][ExtensionsChromiumDeveloperGuidePortChrome]に移植する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7c074-182">For more information on porting your Chrome extension to Microsoft Edge, navigate to [Port Chrome extensions to Microsoft Edge (Chromium)][ExtensionsChromiumDeveloperGuidePortChrome].</span></span> <span data-ttu-id="7c074-183">拡張機能をターゲット ブラウザーに移植した後、次の手順で公開します。</span><span class="sxs-lookup"><span data-stu-id="7c074-183">After you port your extension to the target browser, the next step is to publish it.</span></span>  

### <span data-ttu-id="7c074-184">Microsoft Edge アドオン Web サイトへの公開</span><span class="sxs-lookup"><span data-stu-id="7c074-184">Publish to the Microsoft Edge add-ons website</span></span>  

<span data-ttu-id="7c074-185">Microsoft Edge への拡張機能の公開を開始するには、MSA メール アカウントを使用して開発者アカウントに登録し、拡張機能の登録情報をストアに提出する必要があります。 [][MicrosoftDeveloperRegistration]</span><span class="sxs-lookup"><span data-stu-id="7c074-185">To start publishing your extension to Microsoft Edge, you must [register for a developer account][MicrosoftDeveloperRegistration] with an MSA email account to submit your extension listing to the store.</span></span>  <span data-ttu-id="7c074-186">MSA メール アカウントには `@outlook.com` 、次 `@live.com` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7c074-186">An MSA email account includes `@outlook.com`, `@live.com`, and so on.</span></span>  <span data-ttu-id="7c074-187">登録するメール アドレスを選択する場合は、拡張機能の所有権を組織内の他のユーザーに転送または共有する必要がある場合を検討します。</span><span class="sxs-lookup"><span data-stu-id="7c074-187">When you choose an email address to register, consider if you must transfer or share ownership of the extension with others in your organization.</span></span>  <span data-ttu-id="7c074-188">登録が完了したら、ストアに新しい拡張機能の申請を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="7c074-188">After registration is complete, you may create a new extension submission to the store.</span></span>  

<span data-ttu-id="7c074-189">拡張機能をストアに提出するには、次の項目を指定してください。</span><span class="sxs-lookup"><span data-stu-id="7c074-189">To submit your extension to the store, ensure you provide the following items.</span></span>  

*   <span data-ttu-id="7c074-190">コード ファイルを含 `.zip` むアーカイブ \( \) ファイル。</span><span class="sxs-lookup"><span data-stu-id="7c074-190">An archive \(`.zip`\) file that contains your code files.</span></span>  
*   <span data-ttu-id="7c074-191">ロゴと小さなプロモーション 用タイルを含む、必要なすべてのビジュアル アセット。</span><span class="sxs-lookup"><span data-stu-id="7c074-191">All required visual assets, which include a logo and small promotional tile.</span></span>  
*   <span data-ttu-id="7c074-192">オプションのプロモーション 用メディア (スクリーンショット、プロモーション 用タイル、ビデオ URL など)。</span><span class="sxs-lookup"><span data-stu-id="7c074-192">Optional promotional media, such as screenshots, promotional tiles, and a video URL.</span></span>  
*   <span data-ttu-id="7c074-193">名前、簡単な説明、プライバシー ポリシーのリンクなど、拡張機能について説明する情報。</span><span class="sxs-lookup"><span data-stu-id="7c074-193">Information that describes your extension such as the name, short description, and a privacy policy link.</span></span>  

> [!NOTE]
> <span data-ttu-id="7c074-194">ストアによって、送信要件が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7c074-194">Different stores may have different submission requirements.</span></span>  <span data-ttu-id="7c074-195">上記の一覧は、Microsoft Edge [の拡張機能を][ExtensionsChromiumPublish] 公開する場合の要件をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="7c074-195">The above list summarizes the [requirements][ExtensionsChromiumPublish] to publish an extension for Microsoft Edge.</span></span>  

<span data-ttu-id="7c074-196">拡張機能を正常に提出すると、拡張機能はレビュー プロセスを受け、認定プロセスに合格または不合格になります。</span><span class="sxs-lookup"><span data-stu-id="7c074-196">After you've successfully submitted your extension, your extension undergoes a review process and either passes or fails the certification process.</span></span>  <span data-ttu-id="7c074-197">所有者には、結果が通知され、必要に応じて次の手順が示されます。</span><span class="sxs-lookup"><span data-stu-id="7c074-197">Owners are notified of the outcome and given next steps as required.</span></span>  <span data-ttu-id="7c074-198">拡張機能の更新プログラムをストアに提出すると、新しいレビュー プロセスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="7c074-198">If you submit an extension update to the store, a new review process is started.</span></span>  

## <span data-ttu-id="7c074-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c074-199">See also</span></span>  

*   [<span data-ttu-id="7c074-200">Google Chrome 拡張機能の移植</span><span class="sxs-lookup"><span data-stu-id="7c074-200">Port a Google Chrome extension</span></span>][ExtensionworkshopPorting]  
*   [<span data-ttu-id="7c074-201">Safari アプリ拡張機能を構築する</span><span class="sxs-lookup"><span data-stu-id="7c074-201">Build a Safari App extension</span></span>][AppleDeveloperSafariservicesAppExtensionsBuilding]  
*   [<span data-ttu-id="7c074-202">初めての拡張機能 (Firefox)</span><span class="sxs-lookup"><span data-stu-id="7c074-202">Your first extension (Firefox)</span></span>][MDNWebextensionsYourFirst]  
*   [<span data-ttu-id="7c074-203">チュートリアルの開始 (Chrome)</span><span class="sxs-lookup"><span data-stu-id="7c074-203">Get started tutorial (Chrome)</span></span>][ChromeDeveloperExtensionsGetstarted]  
*   [<span data-ttu-id="7c074-204">開始する (Opera)</span><span class="sxs-lookup"><span data-stu-id="7c074-204">Get started (Opera)</span></span>][OperaDevExtensionsGettingStarted]  
*   [<span data-ttu-id="7c074-205">Microsoft Edge (Chromium) 拡張機能の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="7c074-205">Get started with Microsoft Edge (Chromium) extensions</span></span>][ExtensionsChromiumGettingStartedIndex]  

<!-- links -->  

[ExtensionsChromiumDeveloperGuidePortChrome]: ./developer-guide/port-chrome-extension.md "Chrome 拡張機能を Microsoft Edge (Chromium) |Microsoft Docs"  
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

[OperaAddonsExtensions]: https://addons.opera.com/extensions "拡張機能 | Opera のアドオン"  

[OperaDevExtensions]: https://dev.opera.com/extensions "Extensions ドキュメント |Dev. Opera"  
[OperaDevExtensionsApis]: https://dev.opera.com/extensions/apis "Opera | でサポートされている拡張 APIDev. Opera"  
[OperaDevExtensionsGettingStarted]: https://dev.opera.com/extensions/getting-started "使い始|Dev. Opera"  
