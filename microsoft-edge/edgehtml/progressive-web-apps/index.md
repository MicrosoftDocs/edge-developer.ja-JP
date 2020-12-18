---
description: 段階的な Web アプリは、Windows 10 でネイティブに実行されます。  ここでは、Web 開発者として知る必要があるすべての情報を示します。
title: Windows でのプログレッシブ Web アプリ (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
ms.technology: pwa
keywords: 段階的な Web アプリ, PWA, Edge, JavaScript, Windows, UWP, Microsoft Store
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 87996f6be7c1963c01a476b307a31e689e3880d4
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234720"
---
# <span data-ttu-id="6a1ec-105">Windows でのプログレッシブ Web アプリ (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="6a1ec-105">Progressive Web Apps (EdgeHTML) on Windows</span></span>  

<span data-ttu-id="6a1ec-106">[段階的な Web アプリ][MDNApps]\(または単に PAS\) を使用すると、オープン Web テクノロジを使用してクロスプラットフォーム相互運用性を実現し、ユーザーのデバイス用にカスタマイズされたネイティブのアプリのようなエクスペリエンスをユーザーに提供する必要が生じます。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-106">With [Progressive Web Apps][MDNApps] \(or simply PWAs\) you do not have to decide between using open web technologies for cross-platform interoperability and providing your users with a native app-like experience customized for their device.</span></span>  <span data-ttu-id="6a1ec-107">PAS は、サポート プラットフォーム上のネイティブ[][AListApartUnderstandingProgressiveEnhancement]アプリのように機能するために徐々に拡張された Web サイトにすすむためです。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-107">That is because PWAs are just websites that are [progressively enhanced][AListApartUnderstandingProgressiveEnhancement] to function like native apps on supporting platforms.</span></span>  <span data-ttu-id="6a1ec-108">PWA では、Web アプリとネイティブ アプリの良いところが組み合わされています。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-108">The qualities of a PWA combine the best of the web and native apps.</span></span>  

:::row:::
    :::column:::
        ![検出可能なアイコン][ImageISearch]
        ### [<span data-ttu-id="6a1ec-110">検出可能</span><span class="sxs-lookup"><span data-stu-id="6a1ec-110">Discoverable</span></span>][MDNPwaAdvantagesDiscoverable]
        <span data-ttu-id="6a1ec-111">Web 検索結果とサポート アプリ ストアから</span><span class="sxs-lookup"><span data-stu-id="6a1ec-111">From web search results and supporting app stores</span></span>
    :::column-end:::
    :::column:::
        ![インストール可能なアイコン][ImageIPackage]
        ### [<span data-ttu-id="6a1ec-113">Installable</span><span class="sxs-lookup"><span data-stu-id="6a1ec-113">Installable</span></span>][MDNPwaAdvantagesInstallable]
        <span data-ttu-id="6a1ec-114">ホーム画面からピン留めして起動する</span><span class="sxs-lookup"><span data-stu-id="6a1ec-114">Pin and launch from the home screen</span></span>  
    :::column-end:::
    :::column:::
        ![再エンゲージ可能なアイコン][ImageIPushNotification]
        ### [<span data-ttu-id="6a1ec-116">再エンゲージ可能</span><span class="sxs-lookup"><span data-stu-id="6a1ec-116">Re-engageable</span></span>][MDNPwaAdvantagesReEngageable]
        <span data-ttu-id="6a1ec-117">アプリがアクティブではない場合でもプッシュ通知を送信する</span><span class="sxs-lookup"><span data-stu-id="6a1ec-117">Send push notifications, even when the app is not active</span></span>  
    :::column-end:::
    :::column:::
        ![ネットワークに依存しないアイコン][ImageIOffline]
        ### [<span data-ttu-id="6a1ec-119">ネットワークに依存しない</span><span class="sxs-lookup"><span data-stu-id="6a1ec-119">Network Independent</span></span>][MDNPwaAdvantagesNetworkIndependent]
        <span data-ttu-id="6a1ec-120">オフラインで、ネットワークの状態が低い場合に動作します。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-120">Works offline and in low-network conditions</span></span>  
    :::column-end:::
:::row-end:::
:::row:::
    :::column:::
        ![段階的なアイコン][ImageIProgressive]
        ### [<span data-ttu-id="6a1ec-122">段階的</span><span class="sxs-lookup"><span data-stu-id="6a1ec-122">Progressive</span></span>][MDNPwaAdvantagesProgressive]
        <span data-ttu-id="6a1ec-123">デバイスの機能を使用してエクスペリエンスを拡大縮小 \(アップまたはダウン\) する</span><span class="sxs-lookup"><span data-stu-id="6a1ec-123">Experience scales \(up or down\) with device capabilities</span></span>  
    :::column-end:::
    :::column:::
        ![安全なアイコン][ImageISecurity]
        ### [<span data-ttu-id="6a1ec-125">安全</span><span class="sxs-lookup"><span data-stu-id="6a1ec-125">Safe</span></span>][MDNPwaAdvantagesSafe]
        <span data-ttu-id="6a1ec-126">セキュリティで保護された HTTPS エンドポイントと他のユーザー保護機能を提供します</span><span class="sxs-lookup"><span data-stu-id="6a1ec-126">Provides a secure HTTPS endpoint and other user safeguards</span></span>  
    :::column-end:::
    :::column:::
        ![レスポンシブ アイコン][ImageIResponsive]
        ### [<span data-ttu-id="6a1ec-128">応答中</span><span class="sxs-lookup"><span data-stu-id="6a1ec-128">Responsive</span></span>][MDNPwaAdvantagesResponsive]
        <span data-ttu-id="6a1ec-129">ユーザーの画面サイズ/向き、入力方法に合わせて調整します。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-129">Adapts to the user's screen size / orientation and input method</span></span>  
    :::column-end:::
    :::column:::
        ![リンク可能なアイコン][ImageILink]
        ### [<span data-ttu-id="6a1ec-131">リンク可能</span><span class="sxs-lookup"><span data-stu-id="6a1ec-131">Linkable</span></span>][MDNPwaAdvantagesLinkable]
        <span data-ttu-id="6a1ec-132">標準ハイパーリンクを共有して起動する</span><span class="sxs-lookup"><span data-stu-id="6a1ec-132">Share and launch from a standard hyperlink</span></span>  
    :::column-end:::
:::row-end:::

<span data-ttu-id="6a1ec-133">既存のサイトを構築または PWA に変換することで、プッシュ通知とオフライン サポートにより、既存の対象ユーザーのエンゲージメントを向上できます。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-133">By building or converting your existing site to a PWA, you are able to better engage your existing audience with push notifications and offline support.</span></span>  <span data-ttu-id="6a1ec-134">同時に、ユーザーが検索とリンク共有を通じて PWA を検出すると、開いている Web で引き続き対象ユーザーを構築できます。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-134">At the same time, you are able to continue building your audience on the open web, as users discover your PWA through search and link-sharing.</span></span>  

## <span data-ttu-id="6a1ec-135">Windows 10 の PAS (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="6a1ec-135">PWAs on Windows 10 (EdgeHTML)</span></span>  

> [!NOTE]
> <span data-ttu-id="6a1ec-136">EdgeHTML から Microsoft Edge (Chromium) に移行した場合、PAS で使用される基礎となる Web プラットフォームは同じではありません。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-136">With the move to Microsoft Edge (Chromium) from EdgeHTML, the underlying web platforms used by PWAs are not the same.</span></span>  <span data-ttu-id="6a1ec-137">Edge (Chromium) PAS は、ブラウザーからインストールされ、ブラウザー内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-137">Edge (Chromium) PWAs are installed from and run within the browser.</span></span>  <span data-ttu-id="6a1ec-138">Edge (EdgeHTML) PAS はユニバーサル Windows プラットフォーム (UWP) アプリケーションとして実行され、以前の EdgeHTML Web プラットフォームを使用します。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-138">Edge (EdgeHTML) PWAs run as Universal Windows Platform (UWP) applications and use the older EdgeHTML web platform.</span></span>  <span data-ttu-id="6a1ec-139">PWA に Windows 10 API アクセスが必要な場合は、この EdgeHTML ドキュメントが役立っています。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-139">If you require Windows 10 API access for your PWA, this EdgeHTML documentation is for you.</span></span>  <span data-ttu-id="6a1ec-140">Windows 固有の API にアクセスせずにクロス プラットフォーム サポートを目標にしている場合は [、Microsoft Edge (Chromium) PWA ドキュメントにアクセスしてください][PwaChromiumIndex]。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-140">If your goal is cross platform support without Windows specific API access, please head over to the [Microsoft Edge (Chromium) PWA documentation][PwaChromiumIndex].</span></span>  

<span data-ttu-id="6a1ec-141">Windows 10 を活用する段階的な Web アプリを構築すると [、Microsoft Store][MicrosoftDeveloperStore]を通じて PWA を配布できます。Windows 10 インストール ベースの 6 億人以上のアクティブな月次ユーザーが、アプリの対象ユーザーの可能性を高めています。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-141">When you build a Progressive Web App to take advantage of Windows 10, you are able to distribute your PWA through the [Microsoft Store][MicrosoftDeveloperStore], the entire Windows 10 install base of 600+ million active monthly users is your potential app audience!</span></span>  <span data-ttu-id="6a1ec-142">この方法で開発されたアプリケーションは、 [ユニバーサル Windows プラットフォーム][WindowsUWPGetStartedGuide] アプリとして実行され、WinRT API へのアクセスのようなネイティブな機能を持ちます。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-142">Applications developed this way run as [Universal Windows Platform][WindowsUWPGetStartedGuide] apps and have native like access to the WinRT APIs.</span></span>  <span data-ttu-id="6a1ec-143">WinRT API を使用する場合、コードをレンダリングする Web プラットフォームは EdgeHTML なので、Windows 固有の API を呼び出す前に機能検出を使用して、PWA が Microsoft Edge \(Chromium\) PWA が使用可能なプラットフォーム間で PWA を確実に実行できます。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-143">Note that the web platform rendering your code is EdgeHTML when using the WinRT APIs so be sure to use feature detection before calling any Windows specific APIs to ensure your PWA is able to still run across platforms where Microsoft Edge \(Chromium\) PWAs are available.</span></span>  

<span data-ttu-id="6a1ec-144">[ここでは、Web][PwaEdgehtmlGetStarted] アプリを PWA \(EdgeHTML\) に変換し、Windows 10 でテストし、Microsoft Store で配布する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-144">[Here is how to get started][PwaEdgehtmlGetStarted] converting your web app to a PWA \(EdgeHTML\), testing it on Windows 10, and distributing it in the Microsoft Store.</span></span>  

## <span data-ttu-id="6a1ec-145">要件</span><span class="sxs-lookup"><span data-stu-id="6a1ec-145">Requirements</span></span>  

<span data-ttu-id="6a1ec-146">PWA として実行するには、サーバーホスト型 Web アプリが少なくとも次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-146">To run as a PWA, your server-hosted web app at minimum requires:</span></span>  

*   <span data-ttu-id="6a1ec-147">[HTTPS][WikiHttps]。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-147">[HTTPS][WikiHttps].</span></span>  <span data-ttu-id="6a1ec-148">サーバー/アプリ通信用のセキュリティで保護された接続を提供することで、ユーザーを保護します。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-148">Protect your users by providing a secure connection for server/app communication.</span></span>  <span data-ttu-id="6a1ec-149">サービス ワーカーおよび他の PWA テクノロジは、セキュリティで保護された接続 \(またはデバッグ目的\ から) 提供される Web リソースでのみ `localhost` 動作します。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-149">Service workers and other PWA technologies only work with web resources served over a secure connection \(or from `localhost` for debugging purposes\).</span></span>  
  
*   <span data-ttu-id="6a1ec-150">[サービス ワーカー][MDNServiceWorkerApi]。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-150">[Service workers][MDNServiceWorkerApi].</span></span>  <span data-ttu-id="6a1ec-151">オフライン サポート、リソース キャッシュ、プッシュ通知、バックグラウンド データ同期、ページ読み込みパフォーマンスの最適化を提供するために、サービス ワーカー スレッドを使用して、サーバーとクライアント アプリ間のネットワーク プロキシとして機能します。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-151">Use service worker threads to act as network proxies between your server and client app in order to provide offline support, resource caching, push notifications, background data sync, and page load perf optimizations.</span></span>  

*   <span data-ttu-id="6a1ec-152">[Web アプリ マニフェスト][MDNWebAppManifest]。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-152">[Web app manifest][MDNWebAppManifest].</span></span>  <span data-ttu-id="6a1ec-153">Windows 10 や他のホスト プラットフォームが PWA ユーザーにインストール可能でネイティブなアプリのようなエクスペリエンスを提供するために、Web アプリ \(アイコン、言語、URL エントリ ポイント\) に関する重要な情報を説明する JSON ベースのメタデータ ファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-153">Provide a JSON-based metadata file describing key information about your web app \(such as icons, language, and URL entry point\) so that Windows 10 and other host platforms are able to provide your PWA users with an installable, native app-like experience.</span></span>  <span data-ttu-id="6a1ec-154">Web アプリ マニフェストにサイトを関連付け、Bing インデックス サービスを通じて [Microsoft Store][PwaEdgehtmlMicrosoftStoreImportingBing] に自動的に含める資格を得る。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-154">Associating your site with a web app manifest makes it eligible for [automatic inclusion in the Microsoft Store][PwaEdgehtmlMicrosoftStoreImportingBing] through the Bing indexing service.</span></span>  

<span data-ttu-id="6a1ec-155">PWA を高くするには、アプリには以下も必要です。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-155">To be a great PWA, your app also needs:</span></span>  

*   <span data-ttu-id="6a1ec-156">[ブラウザー間の互換性][MDNCrossBrowserTesting]。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-156">[Cross-browser compatibility][MDNCrossBrowserTesting].</span></span>  <span data-ttu-id="6a1ec-157">さまざまなブラウザーと環境でテスト [することで、PWA][MicrosoftDeveloperEdgeToolsRemote] が動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-157">Ensure your PWA works by [testing][MicrosoftDeveloperEdgeToolsRemote] in different browsers and environments.</span></span>  <span data-ttu-id="6a1ec-158">Windows 10 では、Microsoft Edge ブラウザーと完全な PWA エクスペリエンスの両方で、必ずアプリをテストしてください。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-158">On Windows 10, be sure to test your app both in the Microsoft Edge browser and also in the full PWA experience: as an installed, standalone Windows 10 app \(powered by the EdgeHTML engine\).</span></span>  
  
*   <span data-ttu-id="6a1ec-159">[レスポンシブ デザイン][WikiResponsiveWebDesign]。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-159">[Responsive design][WikiResponsiveWebDesign].</span></span>  <span data-ttu-id="6a1ec-160">[CSS][MDNCssGridLayout]グリッドや[flexbox、][MDNCssFlexibleBoxLayout]メディア クエリ、および [レスポンシブ[][MDNMediaQueries]イメージ[MDNResponsiveImages]]で柔軟なレイアウトと柔軟な画像を使用して、ユーザーのデバイスに UX を適合します。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-160">Employ fluid layouts and flexible images with CSS [grid][MDNCssGridLayout] and/or [flexbox][MDNCssFlexibleBoxLayout], [media queries][MDNMediaQueries], and [responsive images[MDNResponsiveImages] to adapt your UX to your user's device.</span></span>  <span data-ttu-id="6a1ec-161">ブラウザーから[デバイス エミュレーション ツール][DevToolsGuideEmulation]を使用してローカルでテストするか、リモート[][DevToolsProtocolClientsEdgeDevToolsPreview]デバッグ セッションをセットアップしてターゲット デバイスで直接テストします。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-161">Use device [emulation tools][DevToolsGuideEmulation] from your browser to test locally, or set up a [remote debugging session][DevToolsProtocolClientsEdgeDevToolsPreview] to test directly on a target device.</span></span>  <span data-ttu-id="6a1ec-162">Windows 10 では、PCA \(EdgeHTML\) は[][WindowsUWPDesignDevicesIndex]、デスクトップ、電話、タブレット以外のフォーム ファクター [(Xbox、テレビ][WindowsUWPDesignDevicesDesigningTv][、Surface Hub、Windows][MicrosoftDeveloperWindowsSurfaceHub] [Mixed Reality][MicrosoftDeveloperWindowsMixedReality]デバイスなど) に合わせて調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-162">On Windows 10, PWAs \(EdgeHTML\) are able to also be [tailored for form factors][WindowsUWPDesignDevicesIndex] beyond desktop, phone and tablet, including: [Xbox and TV][WindowsUWPDesignDevicesDesigningTv], [Surface Hub][MicrosoftDeveloperWindowsSurfaceHub], and [Windows Mixed Reality][MicrosoftDeveloperWindowsMixedReality] devices.</span></span>  
  
*   <span data-ttu-id="6a1ec-163">[ディープ リンク][WikiDeepLinking]。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-163">[Deep linking][WikiDeepLinking].</span></span>  <span data-ttu-id="6a1ec-164">サイトの各ページを一意の URL にルーティングして、既存のユーザーがソーシャル メディア共有を通じてより広い対象ユーザーを引き付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-164">Route each page of your site to a unique URL so existing users may help you engage an even broader audience through social media sharing.</span></span>  

*   <span data-ttu-id="6a1ec-165">[ベスト プラクティス][Webhint]。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-165">[Best practices][Webhint].</span></span>  <span data-ttu-id="6a1ec-166">[webhint][Webhint] linter のようなコード品質ツールを使用して、アプリの効率、堅牢性、安全性、アクセシビリティを最適化します。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-166">Use code quality tools like the [webhint][Webhint] linter to optimize the efficiency, robustness, safety, and accessibility of your app.</span></span>  

<span data-ttu-id="6a1ec-167">Microsoft Store に段階的な Web アプリを [提出するには、次][MicrosoftDeveloperStore]の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-167">To submit your Progressive Web App to the [Microsoft Store][MicrosoftDeveloperStore], you must have:</span></span>  

*   <span data-ttu-id="6a1ec-168">[Microsoft 開発者アカウント][WindowsUWPPublishDeveloperAccount]</span><span class="sxs-lookup"><span data-stu-id="6a1ec-168">A [Microsoft developer account][WindowsUWPPublishDeveloperAccount]</span></span>  
*   <span data-ttu-id="6a1ec-169">Windows アプリ [を公開するための完了した手順][WindowsUWPPublishIndex]</span><span class="sxs-lookup"><span data-stu-id="6a1ec-169">Completed [steps for publishing a Windows app][WindowsUWPPublishIndex]</span></span>  

<span data-ttu-id="6a1ec-170">数か月以内に、Web 上の既存の PAS が特定の条件を満たす場合、Bing 検索エンジンによって Microsoft Store \(開発者は Windows 10 の対象ユーザー用に直接管理できる\) に自動的にインデックスが作成されます。 [][PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission]</span><span class="sxs-lookup"><span data-stu-id="6a1ec-170">In the coming months, existing PWAs on the web meeting [specific criteria][PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission] are auto-indexed by the Bing search engine into the Microsoft Store \(where developers are able to directly manage them for their Windows 10 audience\).</span></span>  

<span data-ttu-id="6a1ec-171">詳細については [、Microsoft Store で PAS (EdgeHTML)][PwaEdgehtmlMicrosoftStore] を確認してください。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-171">Check out [PWAs (EdgeHTML) in the Microsoft Store][PwaEdgehtmlMicrosoftStore] for further details.</span></span>  

## <span data-ttu-id="6a1ec-172">現在の可用性</span><span class="sxs-lookup"><span data-stu-id="6a1ec-172">Current availability</span></span>  

<span data-ttu-id="6a1ec-173">段階的な Web アプリに対するブラウザー エンジンのサポートは、多くのアーキテクチャ コンポーネントを呼び出します。最も重要なのは [、Fetch API][MDNFetchApi]の基礎となるネットワーク インフラストラクチャです。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-173">Browser engine support for Progressive Web Apps calls for a number of architectural components, the most significant being the networking infrastructure underlying the [Fetch API][MDNFetchApi].</span></span>  <span data-ttu-id="6a1ec-174">EdgeHTML エンジンでの PWA サポートは、Windows 10 1809 リリースで完了しました。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-174">PWA support in the EdgeHTML engine was completed in the Windows 10 1809 release.</span></span>  <span data-ttu-id="6a1ec-175">その時間が EdgeHTML エンジンに組み込まれるのではないので、Web 標準をさらに改善しました。そのため、EdgeHTML プラットフォームで PWA が必要とする機能がサポートされていない場合は、互換性テストを実行し、機能検出を使用して適切にフォールバックしてください。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-175">Further improvements to web standards since that time will not be incorporated into the EdgeHTML engine so be sure to run compatibility tests and use feature detection to gracefully fallback should the feature your PWA needs be unsupported on the EdgeHTML platform.</span></span>  

<span data-ttu-id="6a1ec-176">2020 年に予定されている Microsoft Edge \(Chromium\) リリースでは、Chromium ブラウザーがサポートされているデバイス間で動作するこれらの機能がブラウザー プラットフォームで完全にサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-176">For the upcoming Microsoft Edge \(Chromium\) release in 2020, the browser platform has full support for these features that work across devices where the Chromium browser is supported.</span></span>  

<span data-ttu-id="6a1ec-177">EdgeHTML と Windows の場合、標準ベースの PWA テクノロジの現在の状態を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-177">For EdgeHTML and Windows, here is the current status of standards-based PWA technologies:</span></span>  

| <span data-ttu-id="6a1ec-178">テクノロジ</span><span class="sxs-lookup"><span data-stu-id="6a1ec-178">Technology</span></span> | <span data-ttu-id="6a1ec-179">目的</span><span class="sxs-lookup"><span data-stu-id="6a1ec-179">Purpose</span></span> | <span data-ttu-id="6a1ec-180">対象</span><span class="sxs-lookup"><span data-stu-id="6a1ec-180">Availability</span></span> | <span data-ttu-id="6a1ec-181">使用上の注意</span><span class="sxs-lookup"><span data-stu-id="6a1ec-181">Usage notes</span></span> |  
|:--- |:--- |:--- |:--- |  
| [<span data-ttu-id="6a1ec-182">Web アプリケーション マニフェスト</span><span class="sxs-lookup"><span data-stu-id="6a1ec-182">Web Application Manifest</span></span>][MDNWebAppManifest] | <span data-ttu-id="6a1ec-183">インストールとアプリ ストアのプロモーションを有効にするためのアプリ メタデータをホスト OS に提供します。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-183">Provides app metadata to the host OS for enabling installation and app store promotion.</span></span>  <span data-ttu-id="6a1ec-184">Microsoft Store の PAS に必要です。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-184">Required for PWAs in the Microsoft Store.</span></span>  | [<span data-ttu-id="6a1ec-185">開発中</span><span class="sxs-lookup"><span data-stu-id="6a1ec-185">In development</span></span>][MicrosoftDeveloperEdgePlatformStatusWebApplicationManifest] | <span data-ttu-id="6a1ec-186">現在のところ [、PWA Builder][|::ref1::|] を使用して W3C 準拠の JSON マニフェストを生成し、さまざまな OS プラットフォーム用にアプリをパッケージ化することができます。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-186">For now, you are able to use [PWA Builder][|::ref1::|] to generate a W3C-compliant JSON manifest and package your app for various OS platforms.</span></span>  <span data-ttu-id="6a1ec-187">Windows の場合、PWA Builder は JSON マニフェストを Windows 10 アプリに必要な `.appxmanifest` \(XML\) 形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-187">For Windows, PWA Builder translates your JSON manifest into the `.appxmanifest` \(XML\) format required by Windows 10 apps.</span></span>  |  
| [<span data-ttu-id="6a1ec-188">API のフェッチ</span><span class="sxs-lookup"><span data-stu-id="6a1ec-188">Fetch API</span></span>][MDNFetchApi] | <span data-ttu-id="6a1ec-189">ページ リソースの非同期ネットワーク \(要求、応答\) を提供します。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-189">Provides asynchronous networking \(requests, responses\) for page resources</span></span> |<span data-ttu-id="6a1ec-190">[EdgeHTML 14+][DevGuideWhatsNewEdgeHtml14] / ビルド 14393+</span><span class="sxs-lookup"><span data-stu-id="6a1ec-190">[EdgeHTML 14+][DevGuideWhatsNewEdgeHtml14] / Build 14393+</span></span> | <span data-ttu-id="6a1ec-191">サービス [ワーカー API 構文][MDNServiceWorkerApi] は、フェッチ ベースのネットワーク API に基づいて作成されます。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-191">The [Service Worker API][MDNServiceWorkerApi] syntax is based on Fetch-based networking APIs.</span></span>  <span data-ttu-id="6a1ec-192">また、Fetch API は、より一般的 [に最新][MDNFetchApi] の代替手段として使用することもできます `XMLHttpRequest` 。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-192">You are able to also use [Fetch API][MDNFetchApi] more generally as a modern alternative to `XMLHttpRequest`.</span></span>  |  
| [<span data-ttu-id="6a1ec-193">サービス ワーカー API</span><span class="sxs-lookup"><span data-stu-id="6a1ec-193">Service Worker API</span></span>][MDNServiceWorkerApi] | <span data-ttu-id="6a1ec-194">オフライン対応の Web アプリ モデル/ネットワーク プロキシを提供します。イベント駆動型スクリプトは Web ページから独立して実行されます。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-194">Provides an offline-capable web app model / network proxy, where event-driven scripts run independent of web pages</span></span>  | <span data-ttu-id="6a1ec-195">[EdgeHTML17][DevGuideWhatsNewEdgeHtml17] / ビルド 17133+</span><span class="sxs-lookup"><span data-stu-id="6a1ec-195">[EdgeHTML17][DevGuideWhatsNewEdgeHtml17] / Build 17133+</span></span> | <span data-ttu-id="6a1ec-196">EdgeHTML 16 に出荷された試験的なサポート \(behind `Enable Service Workers` flag\)</span><span class="sxs-lookup"><span data-stu-id="6a1ec-196">Experimental support \(behind `Enable Service Workers` flag\) shipped in EdgeHTML 16.</span></span>  <span data-ttu-id="6a1ec-197">EdgeHTML 17+ ビルドでは、既定でオンになります。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-197">On by default in EdgeHTML 17+ builds.</span></span>  |  
| [<span data-ttu-id="6a1ec-198">キャッシュ API</span><span class="sxs-lookup"><span data-stu-id="6a1ec-198">Cache API</span></span>][MDNCache] | <span data-ttu-id="6a1ec-199">ネットワーク要求と応答のペアの記憶域メカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-199">Provides a storage mechanism for network request/response pairs</span></span> | <span data-ttu-id="6a1ec-200">[EdgeHTML17][DevGuideWhatsNewEdgeHtml17] / ビルド 17133+</span><span class="sxs-lookup"><span data-stu-id="6a1ec-200">[EdgeHTML17][DevGuideWhatsNewEdgeHtml17] / Build 17133+</span></span> | <span data-ttu-id="6a1ec-201">上記 [のサービス ワーカー API に関するメモ][MDNServiceWorkerApi] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-201">See [Service Worker API][MDNServiceWorkerApi] note above.</span></span>  |  
| [<span data-ttu-id="6a1ec-202">プッシュ API</span><span class="sxs-lookup"><span data-stu-id="6a1ec-202">Push API</span></span>][MDNPushApi] | <span data-ttu-id="6a1ec-203">サービス ワーカーがプッシュ通知をサブスクライブできます。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-203">Enables a service worker to subscribe to push notifications</span></span> |<span data-ttu-id="6a1ec-204">[EdgeHTML17][DevGuideWhatsNewEdgeHtml17] / ビルド 17133+</span><span class="sxs-lookup"><span data-stu-id="6a1ec-204">[EdgeHTML17][DevGuideWhatsNewEdgeHtml17] / Build 17133+</span></span>| <span data-ttu-id="6a1ec-205">上記 [のサービス ワーカー API に関するメモ][MDNServiceWorkerApi] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-205">See [Service Worker API][MDNServiceWorkerApi] note above.</span></span>  <span data-ttu-id="6a1ec-206">Windows 10 アプリ \(PAS を含む\) では、W3C プッシュ API をサポートするプッシュ通知を配信するために Windows プッシュ通知サービス [\(WNS\)][WindowsUWPControlsPatternTilesNotificationsWns] が必要 [です][MDNPushApi]。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-206">Windows 10 apps \(including PWAs\) require the [Windows Push Notification Service \(WNS\)][WindowsUWPControlsPatternTilesNotificationsWns] to deliver push notifications, which supports the W3C [Push API][MDNPushApi].</span></span>  |  
| [<span data-ttu-id="6a1ec-207">通知 API</span><span class="sxs-lookup"><span data-stu-id="6a1ec-207">Notifications API</span></span>][MDNNotificationsApi] | <span data-ttu-id="6a1ec-208">サービス ワーカーがプッシュ メッセージ時にユーザーにシステム通知を表示できます。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-208">Enables a service worker to display a system notification to the user upon push message</span></span> | <span data-ttu-id="6a1ec-209">[EdgeHTML 14+][DevGuideWhatsNewEdgeHtml14] / ビルド 14393+</span><span class="sxs-lookup"><span data-stu-id="6a1ec-209">[EdgeHTML 14+][DevGuideWhatsNewEdgeHtml14] / Build 14393+</span></span> | <span data-ttu-id="6a1ec-210">EdgeHTML の Web 通知は、ユーザーがアプリの通知を[][MicrosoftSupportWindowsNotificationSettings]管理し、Quiet Hours を設定できる Windows 10 アクション センターと完全[に統合されています][MicrosoftSupportWindowsFocusAssist]。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-210">Web Notifications in EdgeHTML are fully integrated with the Windows 10 [Action Center][MicrosoftSupportWindowsNotificationSettings], where users are able to manage app notifications and set [Quiet Hours][MicrosoftSupportWindowsFocusAssist].</span></span>  |  
| [<span data-ttu-id="6a1ec-211">バックグラウンド同期 API</span><span class="sxs-lookup"><span data-stu-id="6a1ec-211">Background Sync API</span></span>][MDNSyncManager] | <span data-ttu-id="6a1ec-212">ユーザーがオンラインに戻り、定期的なイベントをスケジュールしてローカル データをサーバーと同期するサービス ワーカーに通知する API を提供します。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-212">Provides an API for notifying a service worker that the user has come back online and for scheduling periodic events to synchronize local data with the server</span></span> | [<span data-ttu-id="6a1ec-213">開発中</span><span class="sxs-lookup"><span data-stu-id="6a1ec-213">In development</span></span>][MicrosoftDeveloperEdgePlatformStatusBackgroundSync] | <span data-ttu-id="6a1ec-214">現在のところ、ネイティブ [の WinRT BackgroundTask API][WindowsUWPLaunchResumeBackgroundTasks] を使用して、Windows 10 アプリとして実行するときに PWA のバックグラウンド タスクを実装できます。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-214">For now, you are able to use the native [WinRT BackgroundTask API][WindowsUWPLaunchResumeBackgroundTasks] to implement background tasks for your PWA when it runs as a Windows 10 app.</span></span>  |  

<span data-ttu-id="6a1ec-215">Windows 10 の PAS に対する Microsoft Store サポートの現在の状態を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-215">Here is the current status of Microsoft Store support for PWAs on Windows 10:</span></span>  

| <span data-ttu-id="6a1ec-216">ストア申請メソッド</span><span class="sxs-lookup"><span data-stu-id="6a1ec-216">Store submission method</span></span> | <span data-ttu-id="6a1ec-217">ステータス</span><span class="sxs-lookup"><span data-stu-id="6a1ec-217">Status</span></span> | <span data-ttu-id="6a1ec-218">詳細</span><span class="sxs-lookup"><span data-stu-id="6a1ec-218">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="6a1ec-219">Manual \(developer initiated\)</span><span class="sxs-lookup"><span data-stu-id="6a1ec-219">Manual \(developer initiated\)</span></span> | <span data-ttu-id="6a1ec-220">利用可能</span><span class="sxs-lookup"><span data-stu-id="6a1ec-220">Available</span></span> | <span data-ttu-id="6a1ec-221">Microsoft [Store で PAS (EdgeHTML) を][PwaEdgehtmlMicrosoftStore] 確認して、始めましょう。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-221">Check out [PWAs (EdgeHTML) in the Microsoft Store][PwaEdgehtmlMicrosoftStore] to get started.</span></span>  |  
| <span data-ttu-id="6a1ec-222">Automatic \(auto-indexed with Bing\)</span><span class="sxs-lookup"><span data-stu-id="6a1ec-222">Automatic \(auto-indexed with Bing\)</span></span> | <span data-ttu-id="6a1ec-223">近日提供予定</span><span class="sxs-lookup"><span data-stu-id="6a1ec-223">Coming soon</span></span> | <span data-ttu-id="6a1ec-224">現在、 [アプリ パートナーの限定][WindowsBlogsWelcomingPWAsEdgeWindows] されたサブセットを使用して PWA オンボーディング プロセスを試験的に実施しています。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-224">We are [currently piloting][WindowsBlogsWelcomingPWAsEdgeWindows] the PWA onboarding process with a limited subset of app partners.</span></span>  <span data-ttu-id="6a1ec-225">数か月以内に、Microsoft はメインストリーム Web 全体の PAS を Microsoft Store に歓迎します。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-225">In the coming months Microsoft welcomes PWAs across the mainstream web to the Microsoft Store.</span></span>  <span data-ttu-id="6a1ec-226">自動生成 [された PWA 登録情報][PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission] に関する Microsoft Store の要件の詳細については、Bing による自動 PWA インポートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a1ec-226">Check out [Automatic PWA importing with Bing][PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission] to learn more about Microsoft Store requirements for auto-generated PWA listings.</span></span>  |  

<!-- image links -->  

[ImageISearch]: media/i_search.png  
[ImageIPackage]: media/i_package.png  
[ImageIPushNotification]: media/i_push-notification.png  
[ImageIOffline]: media/i_offline.png  
[ImageIProgressive]: media/i_progressive.png  
[ImageISecurity]: media/i_security.png  
[ImageIResponsive]: media/i_responsive.png  
[ImageILink]: media/i_link.png  

<!-- links -->  

[DevToolsProtocolClientsEdgeDevToolsPreview]: ../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge DevTools Preview - DevTools プロトコル クライアント |Microsoft Docs"  
[DevToolsGuideEmulation]: ../devtools-guide/emulation.md "エミュレーション |Microsoft Docs"  
[DevGuideWhatsNewEdgeHtml17]: ../dev-guide/whats-new/edgehtml-17.md "EdgeHTML 17 の新機能 |Microsoft Docs"  
[DevGuideWhatsNewEdgeHtml14]: ../dev-guide/whats-new/edgehtml-14.md "EdgeHTML 14 の新機能 |Microsoft Docs"  
[PwaChromiumIndex]: ../../progressive-web-apps-chromium/index.md "Windows での段階的な Web アプリ (Chromium) |Microsoft Docs"  
[PwaEdgehtmlGetStarted]: ../progressive-web-apps/get-started.md "段階的な Web アプリ (EdgeHTML) の概要 |Microsoft Docs"  
[PwaEdgehtmlMicrosoftStore]: ../progressive-web-apps/microsoft-store.md "Microsoft Store の段階的な Web アプリ |Microsoft Docs"
[PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission]: ../progressive-web-apps/microsoft-store.md#criteria-for-automatic-submission "自動申請の条件 - Microsoft Store の段階的な Web アプリ |Microsoft Docs"  
[PwaEdgehtmlMicrosoftStoreImportingBing]: ./microsoft-store.md#automatic-pwa-importing-with-bing "Bing による自動 PWA インポート - Microsoft Store の段階的な Web アプリ (EdgeHTML) |Microsoft Docs"  


[WindowsUWPControlsPatternTilesNotificationsWns]: /windows/uwp/controls-and-patterns/tiles-and-notifications-windows-push-notification-services--wns--overview.md "Windows プッシュ Notification Services \(WNS\) の概要"  
[WindowsUWPDesignDevicesDesigningTv]: /windows/uwp/design/devices/designing-for-tv.md "Xbox およびテレビ向け設計"  
[WindowsUWPDesignDevicesIndex]: /windows/uwp/design/devices/index.md "UWP デバイスの UI に関する考慮事項"  
[WindowsUWPGetStartedGuide]: /windows/uwp/get-started/universal-application-platform-guide.md "ユニバーサル Windows プラットフォーム (UWP) アプリとは"  
[WindowsUWPLaunchResumeBackgroundTasks]: /windows/uwp/launch-resume/support-your-app-with-background-tasks.md "バックグラウンド タスクでアプリをサポートする"  
[WindowsUWPPublishIndex]: /windows/uwp/publish/index.md "Windows アプリとゲームの公開"  
[WindowsUWPPublishDeveloperAccount]: /windows/uwp/publish/opening-a-developer-account.md "開発者アカウントを開く"  

[WindowsBlogsWelcomingPWAsEdgeWindows]: https://blogs.windows.com/msedgedev/2018/02/06/welcoming-progressive-web-apps-edge-windows-10/#56z7mJwKsykfbR4I.97 "Microsoft Edge と Windows 10 への段階的な Web アプリの歓迎 - Windows ブログ"  
[MicrosoftDeveloperEdgePlatformStatusBackgroundSync]: https://developer.microsoft.com/microsoft-edge/platform/status/backgroundsyncapi "バックグラウンド同期 API - Microsoft Edge プラットフォームの状態"  
[MicrosoftDeveloperEdgePlatformStatusWebApplicationManifest]: https://developer.microsoft.com/microsoft-edge/platform/status/webapplicationmanifest "Web アプリケーション マニフェスト - Microsoft Edge プラットフォームの状態"  
[MicrosoftDeveloperEdgeToolsRemote]: https://developer.microsoft.com/microsoft-edge/tools/remote "クイック テスト"  
[MicrosoftDeveloperWindowsMixedReality]: https://developer.microsoft.com/windows/mixed-reality "開発者向けの Mixed Reality"  
[MicrosoftDeveloperWindowsSurfaceHub]: https://developer.microsoft.com/windows/surfacehub "Microsoft Surface Hub"  
[MicrosoftDeveloperStore]: https://developer.microsoft.com/store "Microsoft Developer Store"  
[MicrosoftSupportWindowsFocusAssist]: https://support.microsoft.com/help/4026996/windows-10-turn-focus-assist-on-or-off "Windows 10 でフォーカス アシストをオンまたはオフにする"  
[MicrosoftSupportWindowsNotificationSettings]: https://support.microsoft.com/help/4028678/windows-10-change-notification-settings "Windows 10 での通知設定の変更"  

[AListApartUnderstandingProgressiveEnhancement]: https://alistapart.com/article/understandingprogressiveenhancement "段階的な機能拡張について - 別のリスト"  

[MDNApps]: https://developer.mozilla.org/Apps/Progressive "apps |MDN"  
[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "Cache |MDN"  
[MDNCrossBrowserTesting]: https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing "クロス ブラウザー テスト |MDN"  
[MDNCssFlexibleBoxLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Flexible_Box_Layout "CSS 柔軟なボックス レイアウト |MDN"  
[MDNCssGridLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout "CSS グリッド レイアウト |MDN"  
[MDNFetchApi]: https://developer.mozilla.org/docs/Web/API/Fetch_API "FETCH API |MDN"  
[MDNMediaQueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries "メディア クエリ |MDN"  
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "プッシュ API |MDN"  
[MDNPwaAdvantagesDiscoverable]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Discoverable "検出可能 - 段階的な Web アプリの利点"  
[MDNPwaAdvantagesInstallable]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Installable "インストール可能 - 段階的な Web アプリの利点"  
[MDNPwaAdvantagesLinkable]: https://developer.mozilla.org/Apps/Progressive/Advantages#Linkable "リンク可能 - 段階的な Web アプリの利点"  
[MDNPwaAdvantagesNetworkIndependent]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Network_independent "ネットワークに依存しない - 段階的な Web アプリの利点"  
[MDNPwaAdvantagesProgressive]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Progressive "段階的な - 段階的な Web アプリの利点"  
[MDNPwaAdvantagesReEngageable]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Re-engageable "再エンゲージ可能 - 段階的な Web アプリの利点"  
[MDNPwaAdvantagesResponsive]: https://developer.mozilla.org/Apps/Progressive/Advantages#Responsive "応答性 - 段階的な Web アプリの利点"  
[MDNPwaAdvantagesSafe]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Safe "安全 - 段階的な Web アプリの利点"  
[MDNResponsiveImages レスポンシブ]: https://developer.mozilla.org/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images "イメージ |MDN"  
[MDNResponsiveImages]: https://developer.mozilla.org/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images "Responsive images | MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "サービス ワーカー API |MDN"  
[MDNSyncManager]: https://developer.mozilla.org/docs/Web/API/SyncManager "SyncManager |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web アプリ マニフェスト |MDN"  

[PWABuilder]: https://www.pwabuilder.com "PWABuilder"  

[Webhint]: https://webhint.io "webhint"  

[WikiDeepLinking]: https://en.wikipedia.org/wiki/Deep_linking "ディープ リンク - Wikipedia"  
[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS - Wikipedia"  
[WikiResponsiveWebDesign]: https://en.wikipedia.org/wiki/Responsive_web_design "レスポンシブ Web デザイン - Wikipedia"  
