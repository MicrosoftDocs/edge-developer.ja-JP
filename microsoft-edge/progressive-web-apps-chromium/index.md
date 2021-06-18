---
description: プログレッシブ Web アプリ (クロム) は、Windows 10 でネイティブに実行されます。  ここでは、Web 開発者として知る必要があるすべてについて説明します。
title: Windows 上のプログレッシブ Web アプリ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: pwa
keywords: プログレッシブ Web アプリ、PWA、Edge、JavaScript、Windows、UWP、Microsoft Store
ms.openlocfilehash: 47c6f98329a1da67e0f2c1a8e6243250992fb599
ms.sourcegitcommit: f4488cf2dfef0aeec04712b2ed933d68b8e93a94
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2021
ms.locfileid: "11608838"
---
# <a name="progressive-web-apps-on-windows-overview"></a><span data-ttu-id="d3ff7-105">Windows 上のプログレッシブ Web アプリの概要</span><span class="sxs-lookup"><span data-stu-id="d3ff7-105">Progressive Web Apps on Windows overview</span></span>  

<span data-ttu-id="d3ff7-106">[プログレッシブ Web Apps][MDNApps] \(PWAs\) は、プラットフォーム間の相互運用性を実現するオープン Web テクノロジへのアクセスを提供し、デバイス用にカスタマイズされたネイティブのアプリのようなエクスペリエンスをユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-106">[Progressive Web Apps][MDNApps] \(PWAs\) provide access to open web technologies for cross-platform interoperability and provide your users with a native, app-like experience customized for their devices.</span></span> <span data-ttu-id="d3ff7-107">PWA は、サポート[][AListApartUnderstandingProgressiveEnhancement]プラットフォーム上のネイティブ アプリのように機能するために段階的に拡張される Web サイトです。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-107">PWAs are websites that are [progressively enhanced][AListApartUnderstandingProgressiveEnhancement] to function like native apps on supporting platforms.</span></span> <span data-ttu-id="d3ff7-108">PWA では、Web アプリとネイティブ アプリの良いところが組み合わされています。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-108">The qualities of a PWA combine the best of the web and native apps.</span></span>  

:::row:::
    :::column:::
        :::image type="icon" source="./media/i_search-small.png":::  
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_package-small.png":::  
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_push-notification-small.png":::  
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        ### <a name="discoverablemdnpwaadvantagesdiscoverable"></a><span data-ttu-id="d3ff7-109">[検出可能][MDNPwaAdvantagesDiscoverable]</span><span class="sxs-lookup"><span data-stu-id="d3ff7-109">[Discoverable][MDNPwaAdvantagesDiscoverable]</span></span>  
    :::column-end:::
    :::column:::
        ### <a name="installablemdnpwaadvantagesinstallable"></a><span data-ttu-id="d3ff7-110">[Installable][MDNPwaAdvantagesInstallable]</span><span class="sxs-lookup"><span data-stu-id="d3ff7-110">[Installable][MDNPwaAdvantagesInstallable]</span></span>  
    :::column-end:::
    :::column:::
        ### <a name="re-engageablemdnpwaadvantagesreengageable"></a><span data-ttu-id="d3ff7-111">[再エンゲージ可能][MDNPwaAdvantagesReEngageable]</span><span class="sxs-lookup"><span data-stu-id="d3ff7-111">[Re-engageable][MDNPwaAdvantagesReEngageable]</span></span>  
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        <span data-ttu-id="d3ff7-112">Web 検索結果とサポート アプリ ストアから</span><span class="sxs-lookup"><span data-stu-id="d3ff7-112">From web search results and supporting app stores</span></span>  
    :::column-end:::
    :::column:::
        <span data-ttu-id="d3ff7-113">ホーム画面、スタート メニュー、タスク バーなどからピン留めして起動する</span><span class="sxs-lookup"><span data-stu-id="d3ff7-113">Pin and launch from the home screen, Start Menu, Taskbar, and so on</span></span>  
    :::column-end:::
    :::column:::
        <span data-ttu-id="d3ff7-114">アプリがアクティブではない場合でも、プッシュ通知を送信する</span><span class="sxs-lookup"><span data-stu-id="d3ff7-114">Send push notifications, even when the app is not active</span></span>  
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        :::image type="icon" source="./media/i_offline-small.png":::  
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_progressive-small.png":::  
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_security-small.png":::  
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        ### <a name="network-independentmdnpwaadvantagesnetworkindependent"></a><span data-ttu-id="d3ff7-115">[ネットワークに依存しない][MDNPwaAdvantagesNetworkIndependent]</span><span class="sxs-lookup"><span data-stu-id="d3ff7-115">[Network Independent][MDNPwaAdvantagesNetworkIndependent]</span></span>  
    :::column-end:::
    :::column:::
        ### <a name="progressivemdnpwaadvantagesprogressive"></a><span data-ttu-id="d3ff7-116">[プログレッシブ][MDNPwaAdvantagesProgressive]</span><span class="sxs-lookup"><span data-stu-id="d3ff7-116">[Progressive][MDNPwaAdvantagesProgressive]</span></span>  
    :::column-end:::
    :::column:::
        ### <a name="safemdnpwaadvantagessafe"></a><span data-ttu-id="d3ff7-117">[セーフ][MDNPwaAdvantagesSafe]</span><span class="sxs-lookup"><span data-stu-id="d3ff7-117">[Safe][MDNPwaAdvantagesSafe]</span></span>  
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        <span data-ttu-id="d3ff7-118">オフラインおよびネットワークの低い状態で動作する</span><span class="sxs-lookup"><span data-stu-id="d3ff7-118">Works offline and in low-network conditions</span></span>  
    :::column-end:::
    :::column:::
        <span data-ttu-id="d3ff7-119">デバイス機能を使用してエクスペリエンスをスケールアップ (または縮小) する</span><span class="sxs-lookup"><span data-stu-id="d3ff7-119">Experience scales up (or down) with device capabilities</span></span>  
    :::column-end:::
    :::column:::
        <span data-ttu-id="d3ff7-120">セキュリティで保護された HTTPS エンドポイントと他のユーザーセーフガードを提供する</span><span class="sxs-lookup"><span data-stu-id="d3ff7-120">Provides a secure HTTPS endpoint and other user safeguards</span></span>  
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        :::image type="icon" source="./media/i_responsive-small.png":::  
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_link-small.png":::  
    :::column-end:::
    :::column:::
        &nbsp;  
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        ### <a name="responsivemdnpwaadvantagesresponsive"></a><span data-ttu-id="d3ff7-121">[応答中][MDNPwaAdvantagesResponsive]</span><span class="sxs-lookup"><span data-stu-id="d3ff7-121">[Responsive][MDNPwaAdvantagesResponsive]</span></span>  
    :::column-end:::
    :::column:::
        ### <a name="linkablemdnpwaadvantageslinkable"></a><span data-ttu-id="d3ff7-122">[Linkable][MDNPwaAdvantagesLinkable]</span><span class="sxs-lookup"><span data-stu-id="d3ff7-122">[Linkable][MDNPwaAdvantagesLinkable]</span></span>  
    :::column-end:::
    :::column:::
        &nbsp;  
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        <span data-ttu-id="d3ff7-123">ユーザーの画面サイズまたは向きと入力方法に合わせて調整します。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-123">Adapts to the user's screen size or orientation and input method</span></span>  
    :::column-end:::
    :::column:::
        <span data-ttu-id="d3ff7-124">標準ハイパーリンクからの共有と起動</span><span class="sxs-lookup"><span data-stu-id="d3ff7-124">Share and launch from a standard hyperlink</span></span>  
    :::column-end:::
    :::column:::
        &nbsp;  
    :::column-end:::
:::row-end:::  

<span data-ttu-id="d3ff7-125">既存の Web サイトを PWA に \(または convert\) ビルドして、ユーザーとのエンゲージメントを強化します。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-125">Build \(or convert\) your existing website to a PWA to enhance engagement with your users.</span></span> <span data-ttu-id="d3ff7-126">機能拡張には、プッシュ通知、アプリのような統合、オフラインサポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-126">Enhancements include push notifications, app-like integration, and offline support.</span></span> <span data-ttu-id="d3ff7-127">引き続き、ユーザーが検索とリンク共有を通じて PWA を検出するためのオープン Web 上で対象ユーザーを構築します。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-127">Continue to build your audience on the open web for users to discover your PWA through search and link-sharing.</span></span> <span data-ttu-id="d3ff7-128">何より、アプリは Web サーバー コードを使用して更新されます。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-128">Best of all, your app is updated using your web server code.</span></span>  

## <a name="pwas-on-microsoft-edge-chromium"></a><span data-ttu-id="d3ff7-129">Microsoft Edge の PWA (クロム)</span><span class="sxs-lookup"><span data-stu-id="d3ff7-129">PWAs on Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="d3ff7-130">Web 標準 API を対象とするプログレッシブ Web アプリを構築する場合、アプリはプラットフォームやデバイス間で展開され、利用可能なデバイス固有の機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-130">When you build a Progressive Web App targeting web standard APIs, your app may be deployed across platforms and devices and take advantage of the device-specific capabilities as available.</span></span> <span data-ttu-id="d3ff7-131">Microsoft Edge \(Chromium\) の PWA は、Web サイトに次の利点を追加します。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-131">PWAs in Microsoft Edge \(Chromium\) add the following advantages to your website.</span></span>  

*   <span data-ttu-id="d3ff7-132">アプリは標準ベースの Web プラットフォーム上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-132">Your app is built on a standards-based web platform.</span></span>  
*   <span data-ttu-id="d3ff7-133">ユーザーがブラウザーから直接アプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-133">Allows your users to install your app directly from the browser.</span></span>  
*   <span data-ttu-id="d3ff7-134">ユーザーがストア ベースの展開または登録なしでアプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-134">Allows your users to install your app without a Store-based deployment or registration.</span></span>  
    
<span data-ttu-id="d3ff7-135">デスクトップ PWA は、Microsoft Edge \(Chromium\) が利用可能なプラットフォームでサポート [されています](https://www.microsoft.com/edge)。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-135">Desktop PWAs are supported on any of the platforms Microsoft Edge \(Chromium\) is [available](https://www.microsoft.com/edge).</span></span> <span data-ttu-id="d3ff7-136">以下の利点が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-136">The following benefits are included.</span></span>

*   <span data-ttu-id="d3ff7-137">ナビゲーション バーの [インストール] アイコンを使用して、ブラウザー **内からアプリ** を直接インストールできます。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-137">Apps may be installed directly from within the browser using the **Install** icon in the navigation bar.</span></span>  
    
    :::image type="complex" source="./media/install-progressive-web-app-icon.png" alt-text="アプリのフライアウトとアイコンのインストール" lightbox="./media/install-progressive-web-app-icon.png":::
       <span data-ttu-id="d3ff7-139">アプリのフライアウトとアイコンのインストール</span><span class="sxs-lookup"><span data-stu-id="d3ff7-139">Install app flyout and icon</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="d3ff7-140">[設定アプリ] メニューからアプリをインストール、実行、\*\*\*\* および  >  **管理**することもできます。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-140">Apps may also be installed, run, and managed from the **Settings** > **Apps** menu</span></span>  
    
    :::image type="complex" source="./media/app-menus.png" alt-text="[設定] の下のアプリ メニュー項目" lightbox="./media/app-menus.png":::
       <span data-ttu-id="d3ff7-142">[設定] の下のアプリ メニュー項目</span><span class="sxs-lookup"><span data-stu-id="d3ff7-142">App menu items under settings</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="d3ff7-143">Web 通知は Windows 通知システムに統合されています</span><span class="sxs-lookup"><span data-stu-id="d3ff7-143">Web Notifications are integrated into the Windows notification system</span></span>  
*   <span data-ttu-id="d3ff7-144">アプリをインストールしたブラウザー プロファイルを持つ共有 Cookie ストア</span><span class="sxs-lookup"><span data-stu-id="d3ff7-144">Shared cookie store with the browser profile that installed the app</span></span>  
*   <span data-ttu-id="d3ff7-145">証明書の検証、サイトのアクセス許可、追跡保護、ブラウザー拡張機能を含む **[設定** ] および [\] メニューを使用して他のブラウザー機能 `...` にアクセスする</span><span class="sxs-lookup"><span data-stu-id="d3ff7-145">Access to other browser features using the **Setting and more** \(`...`\) menu including certificate validation, site permissions, tracking protection, and browser extensions</span></span>  
*   <span data-ttu-id="d3ff7-146">アプリをデバッグ [する Microsoft Edge DevTools][DevtoolsProgressiveWebApps] へのフル アクセス</span><span class="sxs-lookup"><span data-stu-id="d3ff7-146">Full access to [Microsoft Edge DevTools][DevtoolsProgressiveWebApps] for debugging your app</span></span>  
    
> [!NOTE]
> <span data-ttu-id="d3ff7-147">PWA の利点、今後の機能、および短いデモの詳細については、「ビルド [2020 PWA セッション」に移動します][BuildVideo]。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-147">For more information about PWA benefits, upcoming features, and short demos, navigate to [Build 2020 PWA session][BuildVideo].</span></span> 

## <a name="requirements"></a><span data-ttu-id="d3ff7-148">要件</span><span class="sxs-lookup"><span data-stu-id="d3ff7-148">Requirements</span></span>  

<span data-ttu-id="d3ff7-149">PWA として実行するには、サーバーホスト型 Web アプリに以下の最小要件を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-149">To run as a PWA, your server-hosted web app should include following minimum requirements.</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="d3ff7-150">HTTPS</span><span class="sxs-lookup"><span data-stu-id="d3ff7-150">HTTPS</span></span>][WikiHttps]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="d3ff7-151">サーバーまたはアプリの通信にセキュリティで保護された接続を提供することで、ユーザーを保護します。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-151">Protects your users by providing a secure connection for server or app communication.</span></span>  <span data-ttu-id="d3ff7-152">Service Workers および他の PWA テクノロジは、セキュリティで保護された接続 \(またはデバッグ目的\) を使用して提供される Web リソースでのみ `localhost` 動作します。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-152">Service Workers and other PWA technologies only work with web resources served over a secure connection \(or from `localhost` for debugging purposes\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="d3ff7-153">サービス ワーカー</span><span class="sxs-lookup"><span data-stu-id="d3ff7-153">Service Workers</span></span>][MDNServiceWorkerApi]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="d3ff7-154">サービス ワーカー スレッドを使用して、サーバーとクライアント アプリの間のネットワーク プロキシとして機能します。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-154">Uses Service Worker threads to act as network proxies between your server and client app.</span></span>  <span data-ttu-id="d3ff7-155">Service Worker スレッドは、オフライン サポート、リソース キャッシュ、プッシュ通知、バックグラウンド データ同期、およびページ読み込みパフォーマンスの最適化を提供します。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-155">Service Worker threads provide offline support, resource caching, push notifications, background data sync, and  page-load performance optimizations.</span></span>    
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="d3ff7-156">Web アプリ マニフェスト</span><span class="sxs-lookup"><span data-stu-id="d3ff7-156">Web App Manifest</span></span>][MDNWebAppManifest]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="d3ff7-157">Web アプリに関する重要な情報を説明する JSON ベースのメタデータ ファイルを提供し、Windows 10 や他のホスト プラットフォームが PWA ユーザーにインストール可能なネイティブ アプリのようなエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-157">Provides a JSON-based metadata file that describes key information about your web app, so that Windows 10 and other host platforms provide your PWA users with an installable, native app-like experience.</span></span>  <span data-ttu-id="d3ff7-158">主要な情報には、アイコン、言語、URL エントリ ポイントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-158">Key information includes icons, language, and URL entry point.</span></span> 
   :::column-end:::
:::row-end:::  

<span data-ttu-id="d3ff7-159">PWA を高くするには、アプリが次の要件も満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-159">To be a great PWA, your app must also meet the following requirements.</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="d3ff7-160">ブラウザー間の互換性</span><span class="sxs-lookup"><span data-stu-id="d3ff7-160">Cross-browser compatibility</span></span>][MDNCrossBrowserTesting]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="d3ff7-161">異なるブラウザーと環境でテスト [を行って][MicrosoftDeveloperEdgeToolsRemote] 、PWA が動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-161">Ensure your PWA works by [testing][MicrosoftDeveloperEdgeToolsRemote] in different browsers and environments.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="d3ff7-162">レスポンシブ デザイン</span><span class="sxs-lookup"><span data-stu-id="d3ff7-162">Responsive design</span></span>][WikiResponsiveWebDesign]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="d3ff7-163">流動的なレイアウトと柔軟な画像を使用します。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-163">Employs fluid layouts and flexible images.</span></span>  <span data-ttu-id="d3ff7-164">レスポンシブ デザインには、ユーザーのデバイスに UX を適合する次の要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-164">Responsive design includes the following elements that adapt your UX to your user's device.</span></span>  
      
      *   <span data-ttu-id="d3ff7-165">CSS [グリッド][MDNCssGridLayout]</span><span class="sxs-lookup"><span data-stu-id="d3ff7-165">CSS [grid][MDNCssGridLayout]</span></span>  
      *   [<span data-ttu-id="d3ff7-166">flexbox</span><span class="sxs-lookup"><span data-stu-id="d3ff7-166">flexbox</span></span>][MDNCssFlexibleBoxLayout]  
      *   <span data-ttu-id="d3ff7-167">CSS [グリッドと][MDNCssGridLayout] [flexbox][MDNCssFlexibleBoxLayout]</span><span class="sxs-lookup"><span data-stu-id="d3ff7-167">CSS [grid][MDNCssGridLayout] and [flexbox][MDNCssFlexibleBoxLayout]</span></span>  
      *   [<span data-ttu-id="d3ff7-168">メディア クエリ</span><span class="sxs-lookup"><span data-stu-id="d3ff7-168">media queries</span></span>][MDNMediaQueries]  
      *   [<span data-ttu-id="d3ff7-169">レスポンシブ イメージ</span><span class="sxs-lookup"><span data-stu-id="d3ff7-169">responsive images</span></span>][MDNResponsiveImages]  
          
      <span data-ttu-id="d3ff7-170">ブラウザー [のデバイス エミュレーション][DevToolsGuideDeviceModeTestingOtherBrowsers] ツールを使用してローカルでテストするか [、Windows][DevtoolsRemoteDebuggingWindows] または [Android][DevtoolsRemoteDebuggingIndex] でリモート デバッグ セッションを作成して、ターゲット デバイスで直接テストします。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-170">Uses [device emulation tools][DevToolsGuideDeviceModeTestingOtherBrowsers] from your browser to locally test, or create a remote debugging session on [Windows][DevtoolsRemoteDebuggingWindows] or [Android][DevtoolsRemoteDebuggingIndex] to test directly on a target device.</span></span>
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="d3ff7-171">ディープ リンク</span><span class="sxs-lookup"><span data-stu-id="d3ff7-171">Deep linking</span></span>][WikiDeepLinking]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="d3ff7-172">サイトの各ページを一意の URL にルーティングし、既存のユーザーがソーシャル メディア共有を通じてより広範なユーザーを引き付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-172">Routes each page of your site to a unique URL so existing users may help you engage an even broader audience through social media sharing.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="d3ff7-173">検証とテストのプラクティス</span><span class="sxs-lookup"><span data-stu-id="d3ff7-173">Validation and testing practices</span></span>][Webhint]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="d3ff7-174">[Webhint linter][Webhint]のようなコード品質ツールを使用して、アプリの効率、堅牢性、安全性、アクセシビリティを最適化します。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-174">Uses code quality tools like the [Webhint][Webhint] linter to optimize the efficiency, robustness, safety, and accessibility of your app.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="d3ff7-175">クロム PWA チェックリスト</span><span class="sxs-lookup"><span data-stu-id="d3ff7-175">Chromium PWA Checklist</span></span>][WebDevGoodPwaChecklist]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="d3ff7-176">Google ベースライン PWA チェックリストに対して PWA を確認します。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-176">Verifies your PWA against the Google baseline PWA checklist.</span></span>  
   :::column-end:::
:::row-end:::  

> [!NOTE]
> <span data-ttu-id="d3ff7-177">PWA を Microsoft Store アプリに変更するには [、Microsoft][MicrosoftDeveloperStore] [ストアのプログレッシブ Web アプリに移動します][PwaChromiumMicrosoftStore]。</span><span class="sxs-lookup"><span data-stu-id="d3ff7-177">To turn your PWA into a [Microsoft Store][MicrosoftDeveloperStore] app, navigate to [Progressive Web Apps in the Microsoft Store][PwaChromiumMicrosoftStore].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ff7-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3ff7-178">See also</span></span>  

*   [<span data-ttu-id="d3ff7-179">ミス バトリング PWA</span><span class="sxs-lookup"><span data-stu-id="d3ff7-179">Myth Busting PWAs</span></span>][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [<span data-ttu-id="d3ff7-180">プログレッシブ Web アプリのプログレッシブ ロードマップ</span><span class="sxs-lookup"><span data-stu-id="d3ff7-180">A Progressive Roadmap for your Progressive Web App</span></span>][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [<span data-ttu-id="d3ff7-181">プログレッシブ Web アプリを使用したオフライン POST</span><span class="sxs-lookup"><span data-stu-id="d3ff7-181">Offline POSTs with Progressive Web Apps</span></span>][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [<span data-ttu-id="d3ff7-182">PWA Q&A</span><span class="sxs-lookup"><span data-stu-id="d3ff7-182">PWA Q&A</span></span>][AaronGustafsonNotebookPwaQa]  
*   [<span data-ttu-id="d3ff7-183">Web でのベット</span><span class="sxs-lookup"><span data-stu-id="d3ff7-183">Betting on the Web</span></span>][JoretegBlogBettingWeb]  
*   [<span data-ttu-id="d3ff7-184">プログレッシブ Web アプリの名前付け</span><span class="sxs-lookup"><span data-stu-id="d3ff7-184">Naming Progressive Web Apps</span></span>][Fberriman20170626NamingProgressiveWebApps]  
*   [<span data-ttu-id="d3ff7-185">フレームワークを使用しないプログレッシブ Web アプリの設計と構築 (パート 1)</span><span class="sxs-lookup"><span data-stu-id="d3ff7-185">Designing And Building A Progressive Web App Without A Framework (Part 1)</span></span>][Smashingmagazine201907ProgressiveWebAppFrameworkPart1]  
*   [<span data-ttu-id="d3ff7-186">フレームワークを使用しないプログレッシブ Web アプリの設計と構築 (パート 2)</span><span class="sxs-lookup"><span data-stu-id="d3ff7-186">Designing And Building A Progressive Web App Without A Framework (Part 2)</span></span>][Smashingmagazine201907ProgressiveWebAppFrameworkPart2]  
*   [<span data-ttu-id="d3ff7-187">フレームワークを使用しないプログレッシブ Web アプリの設計と構築 (パート 3)</span><span class="sxs-lookup"><span data-stu-id="d3ff7-187">Designing And Building A Progressive Web App Without A Framework (Part 3)</span></span>][Smashingmagazine201907ProgressiveWebAppFrameworkPart3]  
    
<!-- links -->  

[DevtoolsRemoteDebuggingIndex]: ../devtools-guide-chromium/remote-debugging/index.md "Android デバイスのリモート デバッグの開始|Microsoft Docs"  
[DevtoolsRemoteDebuggingWindows]: ../devtools-guide-chromium/remote-debugging/windows.md "Windows 10 デバイスのリモート デバッグの概要 | Microsoft Docs"  
[DevToolsGuideDeviceModeTestingOtherBrowsers]: ../devtools-guide-chromium/device-mode/testing-other-browsers.md "他のブラウザーをエミュレートしてテスト|Microsoft Docs"  
[DevtoolsProgressiveWebApps]: ../devtools-guide-chromium/progressive-web-apps/index.md "プログレッシブ Web アプリのデバッグ |Microsoft Docs"  
[PwaChromiumMicrosoftStore]: ./microsoft-store.md "プログレッシブ Web アプリを Microsoft Store アプリに発行|Microsoft Docs"

[WindowsUWPControlsPatternTilesNotificationsWns]: /windows/uwp/controls-and-patterns/tiles-and-notifications-windows-push-notification-services--wns--overview.md "Windows プッシュ Notification Services (WNS) の概要|Microsoft Docs"  
[WindowsUWPDesignDevicesDesigningTv]: /windows/uwp/design/devices/designing-for-tv.md "Xbox とテレビのデザイン|Microsoft Docs"  
[WindowsUWPDesignDevicesIndex]: /windows/uwp/design/devices/index.md "UWP デバイスの UI に関する考慮事項|Microsoft Docs"  
[WindowsUWPGetStartedGuide]: /windows/uwp/get-started/universal-application-platform-guide.md "ユニバーサル Windows プラットフォーム (UWP) アプリとは何|Microsoft Docs"  
[WindowsUWPLaunchResumeBackgroundTasks]: /windows/uwp/launch-resume/support-your-app-with-background-tasks.md "バックグラウンド タスクを使用してアプリをサポート|Microsoft Docs"  
[WindowsUWPPublishIndex]: /windows/uwp/publish/index.md "Windows アプリとゲーム を公開|Microsoft Docs"  
[WindowsUWPPublishDeveloperAccount]: /windows/uwp/publish/opening-a-developer-account.md "開発者アカウントを開|Microsoft Docs"  

[WindowsBlogsWelcomingPWAsEdgeWindows]: https://blogs.windows.com/msedgedev/2018/02/06/welcoming-progressive-web-apps-edge-windows-10/#56z7mJwKsykfbR4I.97 "プログレッシブ Web アプリを Microsoft Edge と Windows 10 に歓迎する - Windows ブログ"  
[MicrosoftDeveloperEdgePlatformStatusBackgroundSync]: https://developer.microsoft.com/microsoft-edge/platform/status/backgroundsyncapi "バックグラウンド同期 API - Microsoft Edge プラットフォームの状態"  
[MicrosoftDeveloperEdgePlatformStatusWebAppManifest]: https://developer.microsoft.com/microsoft-edge/platform/status/webapplicationmanifest "Web アプリ マニフェスト - Microsoft Edge プラットフォームの状態"  
[MicrosoftDeveloperEdgeToolsRemote]: https://developer.microsoft.com/microsoft-edge/tools/remote "インスタント テスト"  
[MicrosoftDeveloperWindowsMixedReality]: https://developer.microsoft.com/windows/mixed-reality "開発者向け Mixed Reality"  
[MicrosoftDeveloperWindowsSurfaceHub]: https://developer.microsoft.com/windows/surfacehub "Microsoft Surface Hub"  
[MicrosoftDeveloperStore]: https://developer.microsoft.com/store "Microsoft Developer Store"  
[MicrosoftEdge]: https://www.microsoft.com/edge "新しい Microsoft Edge ブラウザーをダウンロードする"  
[MicrosoftSupportWindowsFocusAssist]: https://support.microsoft.com/help/4026996/windows-10-turn-focus-assist-on-or-off "Windows 10 でフォーカス アシストのオンとオフを切り替える"  
[MicrosoftSupportWindowsNotificationSettings]: https://support.microsoft.com/help/4028678/windows-10-change-notification-settings "Windows 10 で通知設定を変更する"  

[AaronGustafsonNotebookPwaQa]: https://www.aaron-gustafson.com/notebook/pwa-qa "PWA Q&A"  

[AListApartUnderstandingProgressiveEnhancement]: https://alistapart.com/article/understandingprogressiveenhancement "プログレッシブエンハンスメントについて - リストを離れて"  

[MDNApps]: https://developer.mozilla.org/Apps/Progressive "アプリ|MDN"  
[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "キャッシュ |MDN"  
[MDNCrossBrowserTesting]: https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing "クロス ブラウザー テスト |MDN"  
[MDNCssFlexibleBoxLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Flexible_Box_Layout "CSS Flexible Box Layout |MDN"  
[MDNCssGridLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout "CSS グリッド レイアウト |MDN"  
[MDNFetchApi]: https://developer.mozilla.org/docs/Web/API/Fetch_API "FETCH API |MDN"  
[MDNMediaQueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries "メディア クエリ|MDN"  
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "プッシュ API |MDN"  
[MDNPwaAdvantagesDiscoverable]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Discoverable "検出可能 - プログレッシブ Web アプリの利点"  
[MDNPwaAdvantagesInstallable]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Installable "インストール可能 - プログレッシブ Web アプリの利点"  
[MDNPwaAdvantagesLinkable]: https://developer.mozilla.org/Apps/Progressive/Advantages#Linkable "リンク可能 - プログレッシブ Web アプリの利点"  
[MDNPwaAdvantagesNetworkIndependent]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Network_independent "ネットワークに依存しない - プログレッシブ Web アプリの利点"  
[MDNPwaAdvantagesProgressive]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Progressive "プログレッシブ - プログレッシブ Web アプリの利点"  
[MDNPwaAdvantagesReEngageable]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Re-engageable "再エンゲージメント可能 - プログレッシブ Web アプリの利点"  
[MDNPwaAdvantagesResponsive]: https://developer.mozilla.org/Apps/Progressive/Advantages#Responsive "レスポンシブ - プログレッシブ Web アプリの利点"  
[MDNPwaAdvantagesSafe]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Safe "セーフ - プログレッシブ Web アプリの利点"  
[MDNResponsiveImages]: https://developer.mozilla.org/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images "応答性の高い|MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "Service Worker API |MDN"  
[MDNSyncManager]: https://developer.mozilla.org/docs/Web/API/SyncManager "SyncManager |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web アプリ マニフェスト |MDN"  

[BuildVideo]: https://www.youtube.com/watch?v=y4p_QHZtMKM "PWA ビデオ"  

[CloudfourThinksProgressiveRoadmapYourWebApp]: https://cloudfour.com/thinks/a-progressive-roadmap-for-your-progressive-web-app "プログレッシブ Web アプリのプログレッシブ ロードマップ"  

[Davrous20191018MythBustingPwasNewEdgeEdition]: https://www.davrous.com/2019/10/18/myth-busting-pwas-the-new-edge-edition "ミス バスターリング PWA – 新しいエッジ エディション"  

[Fberriman20170626NamingProgressiveWebApps]: https://fberriman.com/2017/06/26/naming-progressive-web-apps "プログレッシブ Web アプリの名前付け"  

[JoretegBlogBettingWeb]: https://joreteg.com/blog/betting-on-the-web "Web でのベット"  

[MediumWebEdgeOfflinePostsProgressiveWebApps]: https://medium.com/web-on-the-edge/offline-posts-with-progressive-web-apps-fc2dc4ad895 "プログレッシブ Web アプリを使用したオフライン POST"  

[PWABuilder]: https://www.pwabuilder.com "PWABuilder"  

[Smashingmagazine201907ProgressiveWebAppFrameworkPart1]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-1 "フレームワークを使用しないプログレッシブ Web アプリケーションの設計と構築 (パート 1)"  

[Smashingmagazine201907ProgressiveWebAppFrameworkPart2]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-2 "フレームワークを使用しないプログレッシブ Web アプリケーションの設計と構築 (パート 2)"  

[Smashingmagazine201907ProgressiveWebAppFrameworkPart3]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-3 "フレームワークを使用しないプログレッシブ Web アプリケーションの設計と構築 (パート 3)"  

[WebDevGoodPwaChecklist]: https://web.dev/pwa-checklist "優れたプログレッシブ Web アプリを作る理由は何|web.dev"  

[Webhint]: https://webhint.io "webhint"  

[WikiDeepLinking]: https://en.wikipedia.org/wiki/Deep_linking "ディープ リンク - Wikipedia"  
[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS - Wikipedia"  
[WikiResponsiveWebDesign]: https://en.wikipedia.org/wiki/Responsive_web_design "レスポンシブ Web デザイン - Wikipedia"  
