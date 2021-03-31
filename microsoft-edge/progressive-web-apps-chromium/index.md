---
description: 段階的な Web アプリ (Chromium) は、Windows 10 でネイティブに実行されます。  ここでは、Web 開発者として知る必要があるすべての情報を示します。
title: Windows 上の段階的な Web アプリ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: pwa
keywords: 段階的な Web アプリ, PWA, Edge, JavaScript, Windows, UWP, Microsoft Store
ms.openlocfilehash: a13f39dc3b3e0d47ad07b0e447556dc14093e71b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231217"
---
# <span data-ttu-id="c6b1e-105">Windows 上の段階的な Web アプリの概要</span><span class="sxs-lookup"><span data-stu-id="c6b1e-105">Progressive Web Apps on Windows overview</span></span>  

<span data-ttu-id="c6b1e-106">[段階的な Web アプリ][MDNApps] \(PWA\) を使用すると、オープン Web テクノロジにアクセスしてクロスプラットフォーム相互運用性を実現し、ユーザーのデバイス用にカスタマイズされたネイティブなアプリのようなエクスペリエンスをユーザーに提供できます。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-106">[Progressive Web Apps][MDNApps] \(PWAs\) provide access to open web technologies for cross-platform interoperability and provide your users with a native, app-like experience customized for their devices.</span></span>  <span data-ttu-id="c6b1e-107">PAS は、サポート[][AListApartUnderstandingProgressiveEnhancement]プラットフォーム上のネイティブ アプリのように機能するために徐々に拡張された Web サイトです。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-107">PWAs are websites that are [progressively enhanced][AListApartUnderstandingProgressiveEnhancement] to function like native apps on supporting platforms.</span></span>  <span data-ttu-id="c6b1e-108">PWA では、Web アプリとネイティブ アプリの良いところが組み合わされています。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-108">The qualities of a PWA combine the best of the web and native apps.</span></span>  

:::row:::
    :::column:::
        :::image type="icon" source="./media/i_search.png":::
        ### [<span data-ttu-id="c6b1e-109">検出可能</span><span class="sxs-lookup"><span data-stu-id="c6b1e-109">Discoverable</span></span>][MDNPwaAdvantagesDiscoverable]
        <span data-ttu-id="c6b1e-110">Web 検索結果とサポート アプリ ストアから</span><span class="sxs-lookup"><span data-stu-id="c6b1e-110">From web search results and supporting app stores</span></span>
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_package.png":::
        ### [<span data-ttu-id="c6b1e-111">Installable</span><span class="sxs-lookup"><span data-stu-id="c6b1e-111">Installable</span></span>][MDNPwaAdvantagesInstallable]
        <span data-ttu-id="c6b1e-112">ホーム画面、スタート メニュー、タスク バーなどからピン留めして起動する</span><span class="sxs-lookup"><span data-stu-id="c6b1e-112">Pin and launch from the home screen, Start Menu, Taskbar, and so on</span></span>
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_push-notification.png":::
        ### [<span data-ttu-id="c6b1e-113">再エンゲージ可能</span><span class="sxs-lookup"><span data-stu-id="c6b1e-113">Re-engageable</span></span>][MDNPwaAdvantagesReEngageable]
        <span data-ttu-id="c6b1e-114">アプリがアクティブではない場合でもプッシュ通知を送信する</span><span class="sxs-lookup"><span data-stu-id="c6b1e-114">Send push notifications, even when the app is not active</span></span>
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        :::image type="icon" source="./media/i_offline.png":::
        ### [<span data-ttu-id="c6b1e-115">ネットワークに依存しない</span><span class="sxs-lookup"><span data-stu-id="c6b1e-115">Network Independent</span></span>][MDNPwaAdvantagesNetworkIndependent]
        <span data-ttu-id="c6b1e-116">オフラインで、ネットワークの状態が低い場合に動作します。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-116">Works offline and in low-network conditions</span></span>
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_progressive.png":::
        ### [<span data-ttu-id="c6b1e-117">段階的</span><span class="sxs-lookup"><span data-stu-id="c6b1e-117">Progressive</span></span>][MDNPwaAdvantagesProgressive]
        <span data-ttu-id="c6b1e-118">デバイス機能を使用してエクスペリエンスをスケール アップ (または縮小) する</span><span class="sxs-lookup"><span data-stu-id="c6b1e-118">Experience scales up (or down) with device capabilities</span></span>
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_security.png":::
        ### [<span data-ttu-id="c6b1e-119">安全</span><span class="sxs-lookup"><span data-stu-id="c6b1e-119">Safe</span></span>][MDNPwaAdvantagesSafe]
        <span data-ttu-id="c6b1e-120">セキュリティで保護された HTTPS エンドポイントと他のユーザー保護機能を提供します</span><span class="sxs-lookup"><span data-stu-id="c6b1e-120">Provides a secure HTTPS endpoint and other user safeguards</span></span>
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        :::image type="icon" source="./media/i_responsive.png":::
        ### [<span data-ttu-id="c6b1e-121">応答中</span><span class="sxs-lookup"><span data-stu-id="c6b1e-121">Responsive</span></span>][MDNPwaAdvantagesResponsive]
        <span data-ttu-id="c6b1e-122">ユーザーの画面サイズや向き、入力方法に合わせて調整します。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-122">Adapts to the user's screen size or orientation and input method</span></span>
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_link.png":::
        ### [<span data-ttu-id="c6b1e-123">リンク可能</span><span class="sxs-lookup"><span data-stu-id="c6b1e-123">Linkable</span></span>][MDNPwaAdvantagesLinkable]
        <span data-ttu-id="c6b1e-124">標準ハイパーリンクを共有して起動する</span><span class="sxs-lookup"><span data-stu-id="c6b1e-124">Share and launch from a standard hyperlink</span></span>
    :::column-end:::
    :::column:::
        &nbsp;  
    :::column-end:::
:::row-end:::  


<span data-ttu-id="c6b1e-125">既存の Web サイトを PWA に \(または変換\) して、ユーザーとのエンゲージメントを強化します。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-125">Build \(or convert\) your existing website to a PWA to enhance your engagement with your users.</span></span>  <span data-ttu-id="c6b1e-126">機能拡張には、プッシュ通知、アプリのような統合、オフライン サポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-126">Enhancements include push notifications, app-like integration, and offline support.</span></span>  <span data-ttu-id="c6b1e-127">引き続きオープン Web で対象ユーザーを作成し、ユーザーが検索とリンク共有を通じて PWA を検出します。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-127">Continue to build your audience on the open web for users to discover your PWA through search and link-sharing.</span></span>  <span data-ttu-id="c6b1e-128">何より、アプリは Web サーバー コードを使用して更新されます。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-128">Best of all, your app is updated in using your web server code.</span></span>  

## <span data-ttu-id="c6b1e-129">Microsoft Edge 上の PAS (Chromium)</span><span class="sxs-lookup"><span data-stu-id="c6b1e-129">PWAs on Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="c6b1e-130">Web 標準 API をターゲットとする段階的な Web アプリを構築する場合、アプリケーションを複数のプラットフォームやデバイスに展開し、利用可能なデバイス固有の機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-130">When you build a Progressive Web App targeting web standard APIs, your application may be deployed across platforms and devices and take advantage of the device-specific capabilities as available.</span></span>  <span data-ttu-id="c6b1e-131">Microsoft Edge \(Chromium\) の PAS は、Web サイトに次の利点を追加します。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-131">PWAs in Microsoft Edge \(Chromium\) add the following advantages to your website.</span></span>  

*   <span data-ttu-id="c6b1e-132">アプリは、標準ベースの Web プラットフォーム上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-132">Your app is built on a standards-based web platform.</span></span>  
*   <span data-ttu-id="c6b1e-133">ユーザーがブラウザーから直接アプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-133">Enables your users to install your app directly from the browser.</span></span>  
*   <span data-ttu-id="c6b1e-134">ユーザーがストア ベースの展開や登録を行わずにアプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-134">Enables your users to install your app without a Store-based deployment or registration.</span></span>  
    
<span data-ttu-id="c6b1e-135">デスクトップ PAS は、Microsoft Edge \(Chromium\) が利用可能な任意のプラットフォームでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-135">Desktop PWAs are supported on any of the platforms Microsoft Edge \(Chromium\) is available.</span></span> <span data-ttu-id="c6b1e-136">Microsoft Edge \(Chromium\) は、Windows 7、Windows 10、および macOS で利用できます。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-136">Microsoft Edge \(Chromium\) is available on Windows 7, Windows 10, and macOS.</span></span>  <span data-ttu-id="c6b1e-137">次の利点が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-137">The following benefits are included.</span></span>  

*   <span data-ttu-id="c6b1e-138">アプリケーションは、ナビゲーション バーの [インストール] アイコンを使用して、ブラウザー内から直接インストールできます。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-138">Applications may be installed directly from within the browser using the **Install** icon in the navigation bar.</span></span>  
    
    :::image type="complex" source="./media/install_pwa_icon.png" alt-text="アプリケーション のフライアウトとアイコンのインストール" lightbox="./media/install_pwa_icon.png":::
       <span data-ttu-id="c6b1e-140">アプリケーション のフライアウトとアイコンのインストール</span><span class="sxs-lookup"><span data-stu-id="c6b1e-140">Install application flyout and icon</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="c6b1e-141">アプリケーションは、[設定アプリ] メニューからインストール、実行、**および**  >  **管理することもできます**。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-141">Applications may also be installed, run, and managed from the **Settings** > **Apps** menu</span></span>  
    
    :::image type="complex" source="./media/app_menus.png" alt-text="[設定] の [アプリケーション] メニュー項目" lightbox="./media/app_menus.png":::
       <span data-ttu-id="c6b1e-143">[設定] の [アプリケーション] メニュー項目</span><span class="sxs-lookup"><span data-stu-id="c6b1e-143">Application menu items under settings</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="c6b1e-144">Web 通知は Windows 通知システムに統合されます。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-144">Web Notifications are integrated into the Windows notification system</span></span>  
*   <span data-ttu-id="c6b1e-145">アプリをインストールしたブラウザー プロファイルを含む共有 Cookie ストア</span><span class="sxs-lookup"><span data-stu-id="c6b1e-145">Shared cookie store with the browser profile that installed the app</span></span>  
*   <span data-ttu-id="c6b1e-146">証明書の検証、サイトのアクセス 許可、追跡保護、ブラウザー拡張機能を含む [設定] メニューなどの \( \) メニューを使用した他のブラウザー機能 `...` へのアクセス</span><span class="sxs-lookup"><span data-stu-id="c6b1e-146">Access to other browser features using the **Setting and more** \(`...`\) menu including certificate validation, site permissions, tracking protection, and browser extensions</span></span>  
*   <span data-ttu-id="c6b1e-147">アプリをデバッグ [するために Microsoft Edge DevTools][DevtoolsProgressiveWebApps] へのフル アクセス</span><span class="sxs-lookup"><span data-stu-id="c6b1e-147">Full access to [Microsoft Edge DevTools][DevtoolsProgressiveWebApps] for debugging your app</span></span>  
    
> [!IMPORTANT]
> <span data-ttu-id="c6b1e-148">JavaScript を使用して WinRT API 要求を行う Windows 10 専用の PWA を調整するには、[EdgeHTML PWA 機能に固有のドキュメント][PwaEdgehtmlIndex] に移動します。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-148">To tailor PWAs specifically for Windows 10 that make WinRT API requests using JavaScript, navigate to [documentation specific to the EdgeHTML PWA features][PwaEdgehtmlIndex].</span></span>  <span data-ttu-id="c6b1e-149">Windows 10 で PWA をテストし、Microsoft Store で配布する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-149">Learn more about testing your PWA on Windows 10 and distributing it in the Microsoft Store.</span></span>  

> [!NOTE]
> <span data-ttu-id="c6b1e-150">PWA の利点、今後の機能、および短いデモの詳細については、ビルド [2020 PWA セッションに移動します][BuildVideo]。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-150">For more information about PWA benefits, upcoming features, and short demos, navigate to [Build 2020 PWA session][BuildVideo].</span></span> 

## <span data-ttu-id="c6b1e-151">要件</span><span class="sxs-lookup"><span data-stu-id="c6b1e-151">Requirements</span></span>  

<span data-ttu-id="c6b1e-152">PWA として実行するには、サーバーホスト型 Web アプリに次の最小要件を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-152">To run as a PWA, your server-hosted web app should include following minimum requirements.</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="c6b1e-153">HTTPS</span><span class="sxs-lookup"><span data-stu-id="c6b1e-153">HTTPS</span></span>][WikiHttps]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c6b1e-154">サーバーまたはアプリの通信にセキュリティで保護された接続を提供することで、ユーザーを保護します。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-154">Protects your users by providing a secure connection for server or app communication.</span></span>  <span data-ttu-id="c6b1e-155">サービス ワーカーおよび他の PWA テクノロジは、セキュリティで保護された接続 \(またはデバッグ目的\ から) 提供される Web リソースでのみ `localhost` 動作します。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-155">Service Workers and other PWA technologies only work with web resources served over a secure connection \(or from `localhost` for debugging purposes\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="c6b1e-156">サービス ワーカー</span><span class="sxs-lookup"><span data-stu-id="c6b1e-156">Service Workers</span></span>][MDNServiceWorkerApi]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c6b1e-157">サービス ワーカー スレッドを使用して、サーバーとクライアント アプリの間のネットワーク プロキシとして機能します。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-157">Uses Service Worker threads to act as network proxies between your server and client app.</span></span>  <span data-ttu-id="c6b1e-158">サービス ワーカー スレッドは、オフライン サポート、リソース キャッシュ、プッシュ通知、バックグラウンド データ同期、およびページ読み込みパフォーマンスの最適化を提供します。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-158">Service Worker threads provide offline support, resource caching, push notifications, background data sync, and  page-load performance optimizations.</span></span>    
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="c6b1e-159">Web アプリ マニフェスト</span><span class="sxs-lookup"><span data-stu-id="c6b1e-159">Web App Manifest</span></span>][MDNWebAppManifest]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c6b1e-160">Web アプリに関する重要な情報を説明する JSON ベースのメタデータ ファイルを提供し、Windows 10 および他のホスト プラットフォームが PWA ユーザーにインストール可能でネイティブなアプリのようなエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-160">Provides a JSON-based metadata file that describes key information about your web app, so that Windows 10 and other host platforms provide your PWA users with an installable, native app-like experience.</span></span>  <span data-ttu-id="c6b1e-161">主要な情報には、アイコン、言語、および URL エントリ ポイントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-161">Key information includes icons, language, and URL entry point.</span></span> 
   :::column-end:::
:::row-end:::  

<span data-ttu-id="c6b1e-162">PWA を高くするには、アプリが次の要件も満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-162">To be a great PWA, your app must also meet the following requirements.</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="c6b1e-163">ブラウザー間の互換性</span><span class="sxs-lookup"><span data-stu-id="c6b1e-163">Cross-browser compatibility</span></span>][MDNCrossBrowserTesting]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c6b1e-164">さまざまなブラウザーと環境でテスト [することで、PWA][MicrosoftDeveloperEdgeToolsRemote] が動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-164">Ensure your PWA works by [testing][MicrosoftDeveloperEdgeToolsRemote] in different browsers and environments.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="c6b1e-165">レスポンシブ デザイン</span><span class="sxs-lookup"><span data-stu-id="c6b1e-165">Responsive design</span></span>][WikiResponsiveWebDesign]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c6b1e-166">柔軟なレイアウトと柔軟な画像を使用します。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-166">Employs fluid layouts and flexible images.</span></span>  <span data-ttu-id="c6b1e-167">レスポンシブ デザインには、ユーザーのデバイスに UX を適合する次の要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-167">Responsive design includes the following elements that adapt your UX to your user's device.</span></span>  
      
      *   <span data-ttu-id="c6b1e-168">CSS [グリッド][MDNCssGridLayout]</span><span class="sxs-lookup"><span data-stu-id="c6b1e-168">CSS [grid][MDNCssGridLayout]</span></span>  
      *   [<span data-ttu-id="c6b1e-169">flexbox</span><span class="sxs-lookup"><span data-stu-id="c6b1e-169">flexbox</span></span>][MDNCssFlexibleBoxLayout]  
      *   <span data-ttu-id="c6b1e-170">CSS [グリッド][MDNCssGridLayout] と [flexbox][MDNCssFlexibleBoxLayout]</span><span class="sxs-lookup"><span data-stu-id="c6b1e-170">CSS [grid][MDNCssGridLayout] and [flexbox][MDNCssFlexibleBoxLayout]</span></span>  
      *   [<span data-ttu-id="c6b1e-171">メディア クエリ</span><span class="sxs-lookup"><span data-stu-id="c6b1e-171">media queries</span></span>][MDNMediaQueries]  
      *   [<span data-ttu-id="c6b1e-172">レスポンシブ イメージ</span><span class="sxs-lookup"><span data-stu-id="c6b1e-172">responsive images</span></span>][MDNResponsiveImages]  
      
      <span data-ttu-id="c6b1e-173">ブラウザー [のデバイス エミュレーション][DevToolsGuideDeviceModeTestingOtherBrowsers] ツールを使用してローカルでテストするか [、Windows][DevtoolsRemoteDebuggingWindows] または [Android][DevtoolsRemoteDebuggingIndex] でリモート デバッグ セッションを作成し、ターゲット デバイスで直接テストします。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-173">Uses [device emulation tools][DevToolsGuideDeviceModeTestingOtherBrowsers] from your browser to locally test, or create a remote debugging session on [Windows][DevtoolsRemoteDebuggingWindows] or [Android][DevtoolsRemoteDebuggingIndex] to test directly on a target device.</span></span>
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="c6b1e-174">ディープ リンク</span><span class="sxs-lookup"><span data-stu-id="c6b1e-174">Deep linking</span></span>][WikiDeepLinking]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c6b1e-175">サイトの各ページを一意の URL にルーティングし、既存のユーザーがソーシャル メディア共有を通じてより広い対象ユーザーを引き付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-175">Routes each page of your site to a unique URL so existing users may help you engage an even broader audience through social media sharing.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="c6b1e-176">検証とテストのプラクティス</span><span class="sxs-lookup"><span data-stu-id="c6b1e-176">Validation and testing practices</span></span>][Webhint]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c6b1e-177">[Webhint][Webhint] linter のようなコード品質ツールを使用して、アプリの効率、堅牢性、安全性、アクセシビリティを最適化します。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-177">Uses code quality tools like the [Webhint][Webhint] linter to optimize the efficiency, robustness, safety, and accessibility of your app.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="c6b1e-178">Chromium PWA チェックリスト</span><span class="sxs-lookup"><span data-stu-id="c6b1e-178">Chromium PWA Checklist</span></span>][WebDevGoodPwaChecklist]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c6b1e-179">Google ベースライン PWA チェックリストに対して PWA を検証します。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-179">Verifies your PWA against the Google baseline PWA checklist.</span></span>  
   :::column-end:::
:::row-end:::  

> [!NOTE]
> <span data-ttu-id="c6b1e-180">PWA を Microsoft [Store][MicrosoftDeveloperStore] アプリケーションに変換するには、Microsoft Store の [段階的な Web アプリ (EdgeHTML)][PwaEdgehtmlMicrosoftStore] に移動します。</span><span class="sxs-lookup"><span data-stu-id="c6b1e-180">To turn your PWA into a [Microsoft Store][MicrosoftDeveloperStore] application, navigate to [Progressive Web Apps (EdgeHTML) in the Microsoft Store][PwaEdgehtmlMicrosoftStore].</span></span>  
  
## <span data-ttu-id="c6b1e-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6b1e-181">See also</span></span>  

*   [<span data-ttu-id="c6b1e-182">1000,000</span><span class="sxs-lookup"><span data-stu-id="c6b1e-182">Myth Busting PWAs</span></span>][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [<span data-ttu-id="c6b1e-183">段階的な Web アプリの段階的なロードマップ</span><span class="sxs-lookup"><span data-stu-id="c6b1e-183">A Progressive Roadmap for your Progressive Web App</span></span>][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [<span data-ttu-id="c6b1e-184">段階的な Web アプリを使用したオフライン POS</span><span class="sxs-lookup"><span data-stu-id="c6b1e-184">Offline POSTs with Progressive Web Apps</span></span>][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [<span data-ttu-id="c6b1e-185">PWA Q&A</span><span class="sxs-lookup"><span data-stu-id="c6b1e-185">PWA Q&A</span></span>][AaronGustafsonNotebookPwaQa]  
*   [<span data-ttu-id="c6b1e-186">Web 上で楽しむ</span><span class="sxs-lookup"><span data-stu-id="c6b1e-186">Betting on the Web</span></span>][JoretegBlogBettingWeb]  
*   [<span data-ttu-id="c6b1e-187">段階的な Web アプリの名前付け</span><span class="sxs-lookup"><span data-stu-id="c6b1e-187">Naming Progressive Web Apps</span></span>][Fberriman20170626NamingProgressiveWebApps]  
*   [<span data-ttu-id="c6b1e-188">フレームワークを使用しない段階的な Web アプリケーションの設計と構築 (パート 1)</span><span class="sxs-lookup"><span data-stu-id="c6b1e-188">Designing And Building A Progressive Web Application Without A Framework (Part 1)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]  
*   [<span data-ttu-id="c6b1e-189">フレームワークを使用しない段階的な Web アプリケーションの設計と構築 (パート 2)</span><span class="sxs-lookup"><span data-stu-id="c6b1e-189">Designing And Building A Progressive Web Application Without A Framework (Part 2)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]  
*   [<span data-ttu-id="c6b1e-190">フレームワークを使用しない段階的な Web アプリケーションの設計と構築 (パート 3)</span><span class="sxs-lookup"><span data-stu-id="c6b1e-190">Designing And Building A Progressive Web Application Without A Framework (Part 3)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]  
    
<!-- links -->  

[DevtoolsRemoteDebuggingIndex]: ../devtools-guide-chromium/remote-debugging/index.md "Android デバイスのリモート デバッグの概要 |Microsoft Docs"  
[DevtoolsRemoteDebuggingWindows]: ../devtools-guide-chromium/remote-debugging/windows.md "Windows 10 デバイスのリモート デバッグの概要 | Microsoft Docs"  
[DevToolsGuideDeviceModeTestingOtherBrowsers]: ../devtools-guide-chromium/device-mode/testing-other-browsers.md "他のブラウザーをエミュレートしてテストする |Microsoft Docs"  
[DevtoolsProgressiveWebApps]: ../devtools-guide-chromium/progressive-web-apps/index.md "段階的な Web アプリをデバッグする |Microsoft Docs"  
<!--[DevGuideWhatsNewEdgeHtml17]: ../dev-guide/whats-new/edgehtml-17.md "What's new in EdgeHTML 17 | Microsoft Docs"  -->  
<!--[DevGuideWhatsNewEdgeHtml14]: ../dev-guide/whats-new/edgehtml-14.md "What's New in EdgeHTML 14 | Microsoft Docs"  -->  
[PwaEdgehtmlIndex]: ../edgehtml/progressive-web-apps/index.md "Windows の段階的な Web アプリ (EdgeHTML) |Microsoft Docs"  
[PwaEdgehtmlMicrosoftStore]: ../edgehtml/progressive-web-apps/microsoft-store.md "Microsoft Store の段階的な Web アプリ |Microsoft Docs"
<!--PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission]: ../progressive-web-apps/microsoft-store.md#criteria-for-automatic-submission "Criteria for automatic submission - Progressive Web Apps in the Microsoft Store"  -->  

[WindowsUWPControlsPatternTilesNotificationsWns]: /windows/uwp/controls-and-patterns/tiles-and-notifications-windows-push-notification-services--wns--overview.md "Windows プッシュ Notification Services (WNS) の概要 |Microsoft Docs"  
[WindowsUWPDesignDevicesDesigningTv]: /windows/uwp/design/devices/designing-for-tv.md "Xbox およびテレビ向け設計 |Microsoft Docs"  
[WindowsUWPDesignDevicesIndex]: /windows/uwp/design/devices/index.md "UWP デバイスの UI に関する考慮事項 |Microsoft Docs"  
[WindowsUWPGetStartedGuide]: /windows/uwp/get-started/universal-application-platform-guide.md "ユニバーサル Windows プラットフォーム (UWP) アプリとは|Microsoft Docs"  
[WindowsUWPLaunchResumeBackgroundTasks]: /windows/uwp/launch-resume/support-your-app-with-background-tasks.md "バックグラウンド タスクでアプリをサポートする |Microsoft Docs"  
[WindowsUWPPublishIndex]: /windows/uwp/publish/index.md "Windows アプリとゲームの公開 |Microsoft Docs"  
[WindowsUWPPublishDeveloperAccount]: /windows/uwp/publish/opening-a-developer-account.md "開発者アカウントを開く |Microsoft Docs"  

[WindowsBlogsWelcomingPWAsEdgeWindows]: https://blogs.windows.com/msedgedev/2018/02/06/welcoming-progressive-web-apps-edge-windows-10/#56z7mJwKsykfbR4I.97 "Microsoft Edge と Windows 10 への段階的な Web アプリの歓迎 - Windows ブログ"  
[MicrosoftDeveloperEdgePlatformStatusBackgroundSync]: https://developer.microsoft.com/microsoft-edge/platform/status/backgroundsyncapi "バックグラウンド同期 API - Microsoft Edge プラットフォームの状態"  
[MicrosoftDeveloperEdgePlatformStatusWebApplicationManifest]: https://developer.microsoft.com/microsoft-edge/platform/status/webapplicationmanifest "Web アプリケーション マニフェスト - Microsoft Edge プラットフォームの状態"  
[MicrosoftDeveloperEdgeToolsRemote]: https://developer.microsoft.com/microsoft-edge/tools/remote "クイック テスト"  
[MicrosoftDeveloperWindowsMixedReality]: https://developer.microsoft.com/windows/mixed-reality "開発者向けの Mixed Reality"  
[MicrosoftDeveloperWindowsSurfaceHub]: https://developer.microsoft.com/windows/surfacehub "Microsoft Surface Hub"  
[MicrosoftDeveloperStore]: https://developer.microsoft.com/store "Microsoft Developer Store"  
[MicrosoftEdge]: https://www.microsoft.com/edge "新しい Microsoft Edge ブラウザーをダウンロードする"  
[MicrosoftSupportWindowsFocusAssist]: https://support.microsoft.com/help/4026996/windows-10-turn-focus-assist-on-or-off "Windows 10 でフォーカス アシストをオンまたはオフにする"  
[MicrosoftSupportWindowsNotificationSettings]: https://support.microsoft.com/help/4028678/windows-10-change-notification-settings "Windows 10 での通知設定の変更"  

[AaronGustafsonNotebookPwaQa]: https://www.aaron-gustafson.com/notebook/pwa-qa "PWA Q&A"  

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
[MDNResponsiveImages]: https://developer.mozilla.org/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images "レスポンシブ イメージ |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "サービス ワーカー API |MDN"  
[MDNSyncManager]: https://developer.mozilla.org/docs/Web/API/SyncManager "SyncManager |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web アプリ マニフェスト |MDN"  

[BuildVideo]: https://www.youtube.com/watch?v=y4p_QHZtMKM "PWA ビデオ"  

[CloudfourThinksProgressiveRoadmapYourWebApp]: https://cloudfour.com/thinks/a-progressive-roadmap-for-your-progressive-web-app "段階的な Web アプリの段階的なロードマップ"  

[Davrous20191018MythBustingPwasNewEdgeEdition]: https://www.davrous.com/2019/10/18/myth-busting-pwas-the-new-edge-edition "新しい Edge Edition の機能を提供する PAS"  

[Fberriman20170626NamingProgressiveWebApps]: https://fberriman.com/2017/06/26/naming-progressive-web-apps "段階的な Web アプリの名前付け"  

[JoretegBlogBettingWeb]: https://joreteg.com/blog/betting-on-the-web "Web 上で楽しむ"  

[MediumWebEdgeOfflinePostsProgressiveWebApps]: https://medium.com/web-on-the-edge/offline-posts-with-progressive-web-apps-fc2dc4ad895 "段階的な Web アプリを使用したオフライン POS"  

[PWABuilder]: https://www.pwabuilder.com "PWABuilder"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-1 "フレームワークを使用しない段階的な Web アプリケーションの設計と構築 (パート 1)"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-2 "フレームワークを使用しない段階的な Web アプリケーションの設計と構築 (パート 2)"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-3 "フレームワークを使用しない段階的な Web アプリケーションの設計と構築 (パート 3)"  

[WebDevGoodPwaChecklist]: https://web.dev/pwa-checklist "優れた段階的な Web アプリを作成する方法 |web.dev"  

[Webhint]: https://webhint.io "webhint"  

[WikiDeepLinking]: https://en.wikipedia.org/wiki/Deep_linking "ディープ リンク - Wikipedia"  
[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS - Wikipedia"  
[WikiResponsiveWebDesign]: https://en.wikipedia.org/wiki/Responsive_web_design "レスポンシブ Web デザイン - Wikipedia"  
