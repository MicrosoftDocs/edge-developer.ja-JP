---
description: Microsoft Edge (Chromium) の拡張機能の概要と、一般的なブラウザーの拡張機能の構築および公開。
title: Microsoft Edge (Chromium) の拡張機能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/28/2020
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge、拡張機能の開発、ブラウザーの拡張、アドオン、パートナーセンター、開発者、chromium の拡張機能
ms.openlocfilehash: 2c4c34805e93bf6fbae57f1d0230cc821d1f3f65
ms.sourcegitcommit: a5392ab44133d742c0e1fa500ad9a872989b7c3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2020
ms.locfileid: "10684700"
---
# <span data-ttu-id="0f0b8-104">Microsoft Edge (Chromium) の拡張機能</span><span class="sxs-lookup"><span data-stu-id="0f0b8-104">Microsoft Edge (Chromium) Extensions</span></span>  

<span data-ttu-id="0f0b8-105">拡張機能とは、Microsoft Edge \ (Chromium \) に新しい機能を追加したり、既存の機能を変更したりするために使用できる小さなプログラムです。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-105">An extension is a small program that you \(the developer\) may use to add new features to Microsoft Edge \(Chromium\) or modify the existing functionality.</span></span>  <span data-ttu-id="0f0b8-106">拡張は、対象ユーザーにとって重要なニッチ機能を提供することによって、ユーザーの日常的なブラウジングエクスペリエンスを向上させることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-106">An extension is intended to improve a user's day-to-day browsing experience by providing niche functionality that is important to targeted audiences.</span></span>  

<span data-ttu-id="0f0b8-107">アイデアまたは製品が特定の web ブラウザーの利用可能性に依存している場合、または提供する機能によって既存の web サイトが拡張されている場合は、拡張機能を作成できます。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-107">You may create extensions if your idea or product depends on the availability of a specific web browser or augments the browsing experience where the functionality that you want to provide extends existing websites.</span></span>  <span data-ttu-id="0f0b8-108">コンパニオンエクスペリエンスの例としては、adblockers やパスワードマネージャーなどがあります。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-108">Examples of companion experiences include adblockers and password managers.</span></span>  

<span data-ttu-id="0f0b8-109">拡張機能は、通常の web アプリと同じように構成されています。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-109">An extension is structured similar to a regular web app.</span></span>  <span data-ttu-id="0f0b8-110">少なくとも、基本的なプラットフォーム情報を含むアプリマニフェストの JSON ファイル、機能を定義する JavaScript ファイル、およびユーザーインターフェイス \ (必要に応じて) の外観を決定するための HTML ファイルと CSS ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-110">At a minimum, it includes an app manifest JSON file that contains basic platform information, a JavaScript file to define functionality, and a HTML and CSS file to determine the look of the user interface \(as required\).</span></span>  <span data-ttu-id="0f0b8-111">ウィンドウやタブなど、ブラウザーの一部を直接操作するには、API 要求を送信し、多くの場合、名前でブラウザーを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-111">To work directly with part of the browser, such as a window or tab, you must send API requests and often reference the browser by name.</span></span>  

:::image type="complex" source="./media/example-extension-screenshot.png" alt-text="Microsoft Edge (Chromium) 拡張機能":::
  <span data-ttu-id="0f0b8-113">Microsoft Edge \ (Chromium \) 拡張機能</span><span class="sxs-lookup"><span data-stu-id="0f0b8-113">A Microsoft Edge \(Chromium\) extension</span></span>  
:::image-end:::  

## <span data-ttu-id="0f0b8-114">基本的なガイダンス</span><span class="sxs-lookup"><span data-stu-id="0f0b8-114">Basic guidance</span></span>  

<span data-ttu-id="0f0b8-115">Safari、Firefox、Chrome、Opera、Brave、Microsoft Edge など、一般的なブラウザーの一部を対象として構築します。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-115">Some of the most popular browsers to build for include Safari, Firefox, Chrome, Opera, Brave, and Microsoft Edge.</span></span>  <span data-ttu-id="0f0b8-116">拡張機能の開発に関するチュートリアルとドキュメントの調査を始めるのに最適な場所は、ブラウザー組織によってホストされているサイトです。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-116">Great places to begin your extension development tutorials and documentation research are sites hosted by the browser organizations.</span></span>  <span data-ttu-id="0f0b8-117">次の表は確定的なものではありません。これは、便利な出発点として使用してください。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-117">The following table is not definitive, please use it as a helpful starting point.</span></span>  

| <span data-ttu-id="0f0b8-118">Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="0f0b8-118">Web browser</span></span> | <span data-ttu-id="0f0b8-119">Chromium ベースの場合</span><span class="sxs-lookup"><span data-stu-id="0f0b8-119">Chromium-based?</span></span> | <span data-ttu-id="0f0b8-120">拡張機能開発のホームページ</span><span class="sxs-lookup"><span data-stu-id="0f0b8-120">Extension development homepage</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="0f0b8-121">Safari</span><span class="sxs-lookup"><span data-stu-id="0f0b8-121">Safari</span></span> | <span data-ttu-id="0f0b8-122">なし</span><span class="sxs-lookup"><span data-stu-id="0f0b8-122">No</span></span> | [<span data-ttu-id="0f0b8-123">developer.apple.com/documentation/safariservices/safari_app_extensions</span><span class="sxs-lookup"><span data-stu-id="0f0b8-123">developer.apple.com/documentation/safariservices/safari_app_extensions</span></span>][AppleDeveloperSafariservicesAppExtensions] |  
| <span data-ttu-id="0f0b8-124">Firefox</span><span class="sxs-lookup"><span data-stu-id="0f0b8-124">Firefox</span></span> | <span data-ttu-id="0f0b8-125">なし</span><span class="sxs-lookup"><span data-stu-id="0f0b8-125">No</span></span> | [<span data-ttu-id="0f0b8-126">developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions</span><span class="sxs-lookup"><span data-stu-id="0f0b8-126">developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions</span></span>][MDNWebextensions] |  
| <span data-ttu-id="0f0b8-127">クロム</span><span class="sxs-lookup"><span data-stu-id="0f0b8-127">Chrome</span></span> | <span data-ttu-id="0f0b8-128">あり</span><span class="sxs-lookup"><span data-stu-id="0f0b8-128">Yes</span></span> | [<span data-ttu-id="0f0b8-129">developer.chrome.com/extensions</span><span class="sxs-lookup"><span data-stu-id="0f0b8-129">developer.chrome.com/extensions</span></span>][ChromeDeveloperExtensions] |  
| <span data-ttu-id="0f0b8-130">Opera</span><span class="sxs-lookup"><span data-stu-id="0f0b8-130">Opera</span></span> | <span data-ttu-id="0f0b8-131">あり</span><span class="sxs-lookup"><span data-stu-id="0f0b8-131">Yes</span></span> | [<span data-ttu-id="0f0b8-132">dev.opera.com/extensions</span><span class="sxs-lookup"><span data-stu-id="0f0b8-132">dev.opera.com/extensions</span></span>][OperaDevExtensions] |  
| <span data-ttu-id="0f0b8-133">Brave</span><span class="sxs-lookup"><span data-stu-id="0f0b8-133">Brave</span></span> | <span data-ttu-id="0f0b8-134">あり</span><span class="sxs-lookup"><span data-stu-id="0f0b8-134">Yes</span></span> | <span data-ttu-id="0f0b8-135">[Chrome Web ストア][GoogleChromeWebstoreCategoryExtensions]を使用します</span><span class="sxs-lookup"><span data-stu-id="0f0b8-135">Uses [Chrome Web Store][GoogleChromeWebstoreCategoryExtensions]</span></span> |  
| <span data-ttu-id="0f0b8-136">新しい Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0f0b8-136">new Microsoft Edge</span></span> | <span data-ttu-id="0f0b8-137">あり</span><span class="sxs-lookup"><span data-stu-id="0f0b8-137">Yes</span></span> | [<span data-ttu-id="0f0b8-138">developer.microsoft.com/microsoft-edge/extensions</span><span class="sxs-lookup"><span data-stu-id="0f0b8-138">developer.microsoft.com/microsoft-edge/extensions</span></span>][MicrosoftDeveloperEdgeExtensions] |  

> [!IMPORTANT]
> <span data-ttu-id="0f0b8-139">サイトの多くのチュートリアルでは、開発しているブラウザーと一致しない可能性のあるブラウザー固有の Api を使用しています。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-139">Many of the tutorials of the sites use browser-specific APIs that may not match the browser for which you are developing.</span></span>  <span data-ttu-id="0f0b8-140">ほとんどの場合、Chromium 拡張機能は、異なる Chromium ブラウザーで動作しており、Api は期待どおりに動作します。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-140">In most cases, a Chromium extension works as-is in different Chromium browsers and the APIs work as expected.</span></span>  <span data-ttu-id="0f0b8-141">一部の一般的ではない Api は、厳密にはブラウザー固有のものである場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-141">Only some less common APIs may be strictly browser-specific.</span></span>  <span data-ttu-id="0f0b8-142">チュートリアルへのリンクについては、「[関連項目](#see-also)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-142">For links to the tutorials, see [See also](#see-also).</span></span>  

## <span data-ttu-id="0f0b8-143">Chromium</span><span class="sxs-lookup"><span data-stu-id="0f0b8-143">Why Chromium</span></span>  

<span data-ttu-id="0f0b8-144">拡張機能を可能な限り多くのブラウザー拡張ストアに公開することを目標としている場合は、それぞれのブラウザー環境でターゲットを指定して実行するために、複数のバージョンに対して変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-144">If your goal is to publish your extension to as many browser extensions stores as possible, it must be modified for multiple versions in order to target and run in each distinct browser environment.</span></span>  <span data-ttu-id="0f0b8-145">[Safari extensions][AppleDeveloperSafariservicesAppExtensions]は、他の拡張型とは異なり、web とネイティブコードの両方を活用して、ネイティブアプリケーションとの通信に使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-145">[Safari extensions][AppleDeveloperSafariservicesAppExtensions], unlike other extension types, may leverage both web and native code to communicate with counterpart native applications.</span></span>  <span data-ttu-id="0f0b8-146">[Firefox extensions][MDNWebextensions]は、他の種類の拡張機能と共通していますが、考慮すべき[点][ExtensionworkshopPorting]もいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-146">[Firefox extensions][MDNWebextensions] share more in common with the other extension types but there are also some [differences][ExtensionworkshopPorting] to consider.</span></span>  <span data-ttu-id="0f0b8-147">ただし、良いお知らせがあります。上記の表の最後の4つのブラウザーでは、同じコードパッケージを活用して、並列バージョンを変更および管理するための要件を最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-147">However, there is some good news; the last four browsers in the chart above are able to leverage the same code package and minimize the requirement to alter and maintain parallel versions.</span></span>  <span data-ttu-id="0f0b8-148">これは、ブラウザーが[Chromium のオープンソースプロジェクト][|::ref1::|Home]に基づいているためです。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-148">That is because the browsers are based on the [Chromium open-source project][|::ref1::|Home].</span></span>  

<span data-ttu-id="0f0b8-149">Chromium 拡張機能を作成すると、ターゲットとする拡張ストアの数を最大化するコードの量を最小限に抑えることができます。最終的には、拡張機能を検索して取得できるユーザーの数です。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-149">Creating a Chromium extension enables you to write the least amount of code to maximize both the number of extension stores you are targeting and ultimately the number of users that are able to find and acquire your extension.</span></span>  

<span data-ttu-id="0f0b8-150">次のコンテンツは、ほとんどが Chromium の拡張機能に焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-150">The following content focuses mostly on Chromium extensions.</span></span>  

## <span data-ttu-id="0f0b8-151">ブラウザーの互換性と拡張テスト</span><span class="sxs-lookup"><span data-stu-id="0f0b8-151">Browser compatibility and extension testing</span></span>  

<span data-ttu-id="0f0b8-152">場合によっては、Chromium ブラウザーの間に API パリティが存在しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-152">Occasionally, API parity does not exist between Chromium browsers.</span></span>  <span data-ttu-id="0f0b8-153">たとえば、id と支払いの Api には違いがあります。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-153">For example, there are differences in the identity and payment APIs.</span></span>  <span data-ttu-id="0f0b8-154">拡張機能が顧客の期待を満たしていることを確認するには、 [Chrome api][ChromeDeveloperExtensionsApiIndex]、 [Opera でサポートされている拡張 api][OperaDevExtensionsApis]、 [Microsoft (Chromium) Edge へのポート chrome 拡張][ExtensionsChromiumDeveloperGuidePortChrome]機能などの公式ブラウザードキュメントを使って、API の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-154">To ensure your extension meets customer expectations, review API statuses through official browser documentation such as [Chrome APIs][ChromeDeveloperExtensionsApiIndex], [Extension APIs Supported in Opera][OperaDevExtensionsApis], and [Port Chrome Extension To Microsoft (Chromium) Edge][ExtensionsChromiumDeveloperGuidePortChrome].</span></span>  

<span data-ttu-id="0f0b8-155">必要な Api によっては、これらの違いにより、各ストアのコードにわずかな違いがあるため、わずかに異なるコードパッケージを作成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-155">Depending on the APIs that you require, these differences may mean that you must create slightly different code packages with small differences in the code for each store.</span></span>  

<span data-ttu-id="0f0b8-156">拡張機能を開発する際には、ブラウザーでサイドローディングを使用して、拡張機能をブラウザーストアに提出する前に、他の環境でテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-156">When developing your extension, you may sideload it in your browser to test it in different environments before submitting your extension to browser stores.</span></span>  

## <span data-ttu-id="0f0b8-157">拡張機能をブラウザーストアに公開する</span><span class="sxs-lookup"><span data-stu-id="0f0b8-157">Publish your extension to browser stores</span></span>  

<span data-ttu-id="0f0b8-158">次のブラウザーストアで、ブラウザーの拡張機能を送信およびシークすることができます。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-158">You may submit and seek browser extensions in the following browser stores.</span></span>  

*   [<span data-ttu-id="0f0b8-159">Firefox Browser のアドオン</span><span class="sxs-lookup"><span data-stu-id="0f0b8-159">Firefox Browser Add-ons</span></span>][MozillaAddonsFirefoxExtensions]  
*   [<span data-ttu-id="0f0b8-160">Chrome Web ストア</span><span class="sxs-lookup"><span data-stu-id="0f0b8-160">Chrome Web Store</span></span>][GoogleChromeWebstoreCategoryExtensions]  
*   [<span data-ttu-id="0f0b8-161">Opera のアドオン</span><span class="sxs-lookup"><span data-stu-id="0f0b8-161">Opera addons</span></span>][OperaAddonsExtensions]  
*   [<span data-ttu-id="0f0b8-162">Microsoft Edge アドオン</span><span class="sxs-lookup"><span data-stu-id="0f0b8-162">Microsoft Edge Add-ons</span></span>][MicrosoftEdgeAddonsCategoryExtensions]  

<span data-ttu-id="0f0b8-163">一部のストアでは、他のブラウザーから一覧表示された拡張機能をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-163">Some stores allow you to download listed extensions from other browsers.</span></span>  <span data-ttu-id="0f0b8-164">別のブラウザーからダウンロードした場合、ユーザーがさまざまなブラウザーで既存のストア登録情報に移動できるようになると、(開発者用の) 作業を事前に保存して、追加のストアに提出する必要がない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-164">Downloading from from another browser may save you \(the developer\) effort upfront and remove the requirement to submit to additional stores if users are able to navigate to the existing store listings across different browsers.</span></span>  <span data-ttu-id="0f0b8-165">ただし、ブラウザーストアでは、ブラウザー間のアクセスは保証されません。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-165">However, cross-browser access is not guaranteed by browser stores.</span></span>  <span data-ttu-id="0f0b8-166">ユーザーがさまざまなブラウザーで拡張機能を見つけることができるようにするには、各ブラウザー拡張ストアで一覧を保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-166">To ensure your users are able to find your extension in different browsers, you should maintain a listing on each browser extension store.</span></span>  

<span data-ttu-id="0f0b8-167">内線番号には、複数のブラウザーを使用することが多い対象ユーザーが重複していることがあります。または、それ以外のユーザーを対象としている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-167">An extension may have overlapping audiences that often use multiple browsers, or you may discover that it should be targeting an audience that it has not before.</span></span>  <span data-ttu-id="0f0b8-168">これを実現するために、既存の Chromium の拡張機能をあるブラウザーから別のブラウザーに移行することができます。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-168">To make this happen, existing Chromium extensions may be migrated from one browser to another.</span></span>  

### <span data-ttu-id="0f0b8-169">既存の拡張機能を Microsoft Edge に移行する</span><span class="sxs-lookup"><span data-stu-id="0f0b8-169">Migrate an existing extension to Microsoft Edge</span></span>  

<span data-ttu-id="0f0b8-170">既に別の Chromium browser の拡張機能を開発していて、それを提供して Microsoft Edge で動作することを確認したい場合は、拡張機能を書き換える必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-170">If you already developed an extension for another Chromium browser and want to offer it and ensure it works through Microsoft Edge, you do not have to rewrite your extension.</span></span>  <span data-ttu-id="0f0b8-171">使用している Api がさまざまなブラウザーで使用できる場合や、必要な機能を提供する他の Api がある場合は、既存の Chromium 拡張機能を他の Chromium ブラウザーに移行するのは簡単です。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-171">Migrating existing Chromium extensions to other Chromium browsers is straightforward as long as the APIs you use are available on different browsers or there are other APIs that provide the required functionality.</span></span>  

<span data-ttu-id="0f0b8-172">Chrome 拡張機能の移植の詳細については、「 [Microsoft (Chromium) Edge のポート Chrome 拡張機能][ExtensionsChromiumDeveloperGuidePortChrome]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-172">For more information on porting your Chrome extension, see [Port Chrome extensions to Microsoft (Chromium) Edge][ExtensionsChromiumDeveloperGuidePortChrome].</span></span>  <span data-ttu-id="0f0b8-173">ターゲットブラウザに拡張機能を移植したら、次の手順として公開します。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-173">Once you have ported your extension to the target browser, the next step is to publish it.</span></span>  

### <span data-ttu-id="0f0b8-174">Microsoft Edge のアドオン web サイトに発行する</span><span class="sxs-lookup"><span data-stu-id="0f0b8-174">Publishing to the Microsoft Edge add-ons website</span></span>  

<span data-ttu-id="0f0b8-175">Microsoft Edge への拡張機能の公開を開始するには、MSA メールアカウント (@outlook .com、@live など) を持つ[開発者アカウントに登録][MicrosoftDeveloperRegistration]して、ストアで拡張機能の一覧を提出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-175">To get started publishing your extension to Microsoft Edge, you must [register for a developer account][MicrosoftDeveloperRegistration] with a MSA email account \(@outlook.com, @live.com, and so on\) to submit your extension listing in the store.</span></span>  <span data-ttu-id="0f0b8-176">登録するメールアドレスを選択する場合は、組織内の他のユーザーと内線番号の所有権を移転または共有する必要があるかどうかを検討してください。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-176">When choosing an email address to register, consider if you must transfer or share ownership of the extension with others in your organization.</span></span>  <span data-ttu-id="0f0b8-177">登録が完了したら、ストアに新しい拡張機能の申請を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-177">After registration is complete, you may create a new extension submission to the store.</span></span>  

<span data-ttu-id="0f0b8-178">内線番号をストアに提出するには、次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-178">To submit your extension to the store, you must meet the following requirements.</span></span>  

*   <span data-ttu-id="0f0b8-179">コードファイルを含むアーカイブ \ (.zip) ファイル。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-179">An archive \(.zip\) file that contains your code files.</span></span>  
*   <span data-ttu-id="0f0b8-180">必要なすべてのビジュアルアセット。ロゴと小規模プロモーションタイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-180">All required visual assets, which includes a logo and small promotional tile.</span></span>  
*   <span data-ttu-id="0f0b8-181">スクリーンショット、大きなプロモーションタイル、URL、または拡張機能のビデオへの任意の組み合わせなど、オプションのプロモーションメディア。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-181">Optional promotional media, such as screenshots, larger promotional tiles, a URL, or any combination to videos of your extension.</span></span>  
*   <span data-ttu-id="0f0b8-182">名前、短い説明、長い説明、プライバシーポリシーへのリンクなど、拡張機能について説明する情報。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-182">Information that describes your extension such as the name, short description, long description, and a link to your privacy policy.</span></span>  

> [!NOTE]
> <span data-ttu-id="0f0b8-183">ストアによって、送信要件が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-183">Different stores may have different submission requirements.</span></span>  <span data-ttu-id="0f0b8-184">上記の一覧は、Microsoft Edge に拡張機能を公開するための[要件][ExtensionsChromiumPublish]をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-184">The above list summarizes the [requirements][ExtensionsChromiumPublish] for publishing an extension to Microsoft Edge.</span></span>  

<span data-ttu-id="0f0b8-185">申請プロセスが完了すると、拡張機能が確認され、認定プロセスに合格するか、または不合格になります。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-185">After you complete the submission process, your extension is reviewed and either passes or fails the certification process.</span></span>  <span data-ttu-id="0f0b8-186">所有者には、結果が通知され、必要に応じて次の手順が示されます。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-186">Owners are notified of the outcome and given next steps as required.</span></span>  <span data-ttu-id="0f0b8-187">拡張機能一覧の詳細の更新など、更新された拡張機能をストアに提出すると、新しいレビュープロセスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="0f0b8-187">If you submit an updated extension to the store, including updates to the extension listing details, a new review process is started.</span></span>  

## <span data-ttu-id="0f0b8-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f0b8-188">See also</span></span>  

*   [<span data-ttu-id="0f0b8-189">Google Chrome 拡張機能の移植</span><span class="sxs-lookup"><span data-stu-id="0f0b8-189">Porting a Google Chrome extension</span></span>][ExtensionworkshopPorting]  
*   [<span data-ttu-id="0f0b8-190">Safari アプリの拡張機能の構築</span><span class="sxs-lookup"><span data-stu-id="0f0b8-190">Building a Safari App Extension</span></span>][AppleDeveloperSafariservicesAppExtensionsBuilding]  
*   [<span data-ttu-id="0f0b8-191">最初の内線番号 (Firefox)</span><span class="sxs-lookup"><span data-stu-id="0f0b8-191">Your first extension (Firefox)</span></span>][MDNWebextensionsYourFirst]  
*   [<span data-ttu-id="0f0b8-192">はじめにのチュートリアル (Chrome)</span><span class="sxs-lookup"><span data-stu-id="0f0b8-192">Getting Started Tutorial (Chrome)</span></span>][ChromeDeveloperExtensionsGetstarted]  
*   [<span data-ttu-id="0f0b8-193">はじめに (Opera)</span><span class="sxs-lookup"><span data-stu-id="0f0b8-193">Getting Started (Opera)</span></span>][OperaDevExtensionsGettingStarted]  
*   [<span data-ttu-id="0f0b8-194">Microsoft Edge (Chromium) の拡張機能の概要</span><span class="sxs-lookup"><span data-stu-id="0f0b8-194">Getting Started With Microsoft Edge (Chromium) Extensions</span></span>][ExtensionsChromiumGettingStartedIndex]  

<!-- image links -->  

<!-- links -->  

[ExtensionsChromiumDeveloperGuidePortChrome]: ./developer-guide/port-chrome-extension.md "Microsoft (Chromium) Edge のポート Chrome 拡張機能 |Microsoft ドキュメント"  
[ExtensionsChromiumGettingStartedIndex]: ./getting-started/index.md "Microsoft Edge (Chromium) Extensions の概要 |Microsoft ドキュメント"  
[ExtensionsChromiumPublish]: ./publish/publish-extension.md "拡張子を公開する |Microsoft ドキュメント"  

[MicrosoftDeveloperEdgeExtensions]: https://developer.microsoft.com/microsoft-edge/extensions "Microsoft Edge 用の拡張機能を開発する |Microsoft 開発者"  
[MicrosoftDeveloperRegistration]: https://developer.microsoft.com/registration "パートナーセンター |Microsoft 開発者"  

[MicrosoftEdgeAddonsCategoryExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge 用の拡張機能 |Microsoft Edge"  

[AppleDeveloperSafariservicesAppExtensions]: https://developer.apple.com/documentation/safariservices/safari_app_extensions "Safari アプリの拡張機能 |Apple 開発者"  
[AppleDeveloperSafariservicesAppExtensionsBuilding]: https://developer.apple.com/documentation/safariservices/safari_app_extensions/building_a_safari_app_extension "Safari アプリの拡張機能の構築 |Apple 開発者"  

[ChromeDeveloperExtensions]: https://developer.chrome.com/extensions "拡張子とはChrome 開発者"  
[ChromeDeveloperExtensionsApiIndex]: https://developer.chrome.com/extensions/api_index "Chrome Api |Chrome 開発者"  
[ChromeDeveloperExtensionsGetstarted]: https://developer.chrome.com/extensions/getstarted "はじめにのチュートリアル |Chrome 開発者"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium"  

[ExtensionworkshopPorting]: https://extensionworkshop.com/documentation/develop/porting-a-google-chrome-extension "Google Chrome 拡張機能の移植 |拡張ワークショップ"  

[GoogleChromeWebstoreCategoryExtensions]: https://chrome.google.com/webstore/category/extensions "拡張子 |Chrome Web ストア"  

[MDNWebextensions]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions "ブラウザーの拡張機能 |MDN"  
[MDNWebextensionsYourFirst]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/Your_first_WebExtension "最初の内線番号 |MDN"  

[MozillaAddonsFirefoxExtensions]: https://addons.mozilla.org/firefox/extensions "拡張子 |Firefox 用のアドオン"  

[OperaAddonsExtensions]: https://addons.opera.com/extensions "拡張子 |Opera のアドオン"  

[OperaDevExtensions]: https://dev.opera.com/extensions "拡張機能ドキュメント |Opera"  
[OperaDevExtensionsApis]: https://dev.opera.com/extensions/apis "Opera でサポートされている拡張 ApiOpera"  
[OperaDevExtensionsGettingStarted]: https://dev.opera.com/extensions/getting-started "はじめにOpera"  
