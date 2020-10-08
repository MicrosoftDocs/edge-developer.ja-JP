---
description: プログレッシブ Web アプリ (Chromium) は、Windows 10 でネイティブに実行されます。  ここでは、web 開発者として知っておく必要があるものをすべて紹介します。
title: Windows のプログレッシブ Web アプリ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/01/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: pwa
keywords: プログレッシブ web アプリ、PWA、エッジ、JavaScript、Windows、UWP、Microsoft ストア
ms.openlocfilehash: a9fa08a9c84ee5da8eab3c9c3edeea34439b6557
ms.sourcegitcommit: be76feed0d616a96c77ea2748a9f0d6c0c06284b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "11103941"
---
# <span data-ttu-id="2b9a4-105">Windows のプログレッシブ Web アプリ</span><span class="sxs-lookup"><span data-stu-id="2b9a4-105">Progressive Web Apps on Windows</span></span>  

<span data-ttu-id="2b9a4-106">[プログレッシブ Web アプリ][MDNApps] \ (pwas \) は、クロスプラットフォームの相互運用性を実現するために、オープン web テクノロジへのアクセスを提供し、ユーザーにデバイスに合わせてカスタマイズされたネイティブのアプリのようなエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-106">[Progressive Web Apps][MDNApps] \(PWAs\) provide access to open web technologies for cross-platform interoperability and provide your users with a native, app-like experience customized for their devices.</span></span>  <span data-ttu-id="2b9a4-107">PWAs は、サポートしているプラットフォームでのネイティブアプリのように機能するために [段階的に拡張][AListApartUnderstandingProgressiveEnhancement] された web サイトです。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-107">PWAs are websites that are [progressively enhanced][AListApartUnderstandingProgressiveEnhancement] to function like native apps on supporting platforms.</span></span>  <span data-ttu-id="2b9a4-108">PWA では、Web アプリとネイティブ アプリの良いところが組み合わされています。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-108">The qualities of a PWA combine the best of the web and native apps.</span></span>  

:::row:::
    :::column:::
        :::image type="icon" source="./media/i_search.png":::
        ### [<span data-ttu-id="2b9a4-109">見つけ</span><span class="sxs-lookup"><span data-stu-id="2b9a4-109">Discoverable</span></span>][MDNPwaAdvantagesDiscoverable]
        <span data-ttu-id="2b9a4-110">Web 検索結果とサポートされているアプリストアから</span><span class="sxs-lookup"><span data-stu-id="2b9a4-110">From web search results and supporting app stores</span></span>
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_package.png":::
        ### [<span data-ttu-id="2b9a4-111">Installable</span><span class="sxs-lookup"><span data-stu-id="2b9a4-111">Installable</span></span>][MDNPwaAdvantagesInstallable]
        <span data-ttu-id="2b9a4-112">ホーム画面、[スタート] メニュー、タスクバーなどのピン留めと起動</span><span class="sxs-lookup"><span data-stu-id="2b9a4-112">Pin and launch from the home screen, Start Menu, Taskbar, and so on</span></span>
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_push-notification.png":::
        ### [<span data-ttu-id="2b9a4-113">再 engageable</span><span class="sxs-lookup"><span data-stu-id="2b9a4-113">Re-engageable</span></span>][MDNPwaAdvantagesReEngageable]
        <span data-ttu-id="2b9a4-114">アプリがアクティブでない場合でも、プッシュ通知を送信する</span><span class="sxs-lookup"><span data-stu-id="2b9a4-114">Send push notifications, even when the app is not active</span></span>
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        :::image type="icon" source="./media/i_offline.png":::
        ### [<span data-ttu-id="2b9a4-115">ネットワークに依存しない</span><span class="sxs-lookup"><span data-stu-id="2b9a4-115">Network Independent</span></span>][MDNPwaAdvantagesNetworkIndependent]
        <span data-ttu-id="2b9a4-116">オフラインおよび低ネットワークの状態で動作する</span><span class="sxs-lookup"><span data-stu-id="2b9a4-116">Works offline and in low-network conditions</span></span>
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_progressive.png":::
        ### [<span data-ttu-id="2b9a4-117">的</span><span class="sxs-lookup"><span data-stu-id="2b9a4-117">Progressive</span></span>][MDNPwaAdvantagesProgressive]
        <span data-ttu-id="2b9a4-118">デバイス機能を使用したエクスペリエンスのスケールアップ (またはダウン)</span><span class="sxs-lookup"><span data-stu-id="2b9a4-118">Experience scales up (or down) with device capabilities</span></span>
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_security.png":::
        ### [<span data-ttu-id="2b9a4-119">問題</span><span class="sxs-lookup"><span data-stu-id="2b9a4-119">Safe</span></span>][MDNPwaAdvantagesSafe]
        <span data-ttu-id="2b9a4-120">セキュリティで保護された HTTPS エンドポイントとその他のユーザーの保護機能を提供する</span><span class="sxs-lookup"><span data-stu-id="2b9a4-120">Provides a secure HTTPS endpoint and other user safeguards</span></span>
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        :::image type="icon" source="./media/i_responsive.png":::
        ### [<span data-ttu-id="2b9a4-121">応答中</span><span class="sxs-lookup"><span data-stu-id="2b9a4-121">Responsive</span></span>][MDNPwaAdvantagesResponsive]
        <span data-ttu-id="2b9a4-122">ユーザーの画面サイズまたは印刷の向きと入力方式に合わせて調整する</span><span class="sxs-lookup"><span data-stu-id="2b9a4-122">Adapts to the user's screen size or orientation and input method</span></span>
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_link.png":::
        ### [<span data-ttu-id="2b9a4-123">Linkable</span><span class="sxs-lookup"><span data-stu-id="2b9a4-123">Linkable</span></span>][MDNPwaAdvantagesLinkable]
        <span data-ttu-id="2b9a4-124">標準ハイパーリンクを共有して起動する</span><span class="sxs-lookup"><span data-stu-id="2b9a4-124">Share and launch from a standard hyperlink</span></span>
    :::column-end:::
    :::column:::
        &nbsp;  
    :::column-end:::
:::row-end:::  


<span data-ttu-id="2b9a4-125">ユーザーによる契約を強化するために、既存の web サイトを PWA に構築 (または) します。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-125">Build \(or convert\) your existing website to a PWA to enhance your engagement with your users.</span></span>  <span data-ttu-id="2b9a4-126">強化された機能には、プッシュ通知、アプリのような統合、オフラインサポートなどがあります。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-126">Enhancements include push notifications, app-like integration, and offline support.</span></span>  <span data-ttu-id="2b9a4-127">ユーザーが検索とリンク共有を通じて PWA を見つけられるように、開いている web 上の参加者の作成を続けます。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-127">Continue to build your audience on the open web for users to discover your PWA through search and link-sharing.</span></span>  <span data-ttu-id="2b9a4-128">いずれの場合も、web サーバーコードを使用してアプリが更新されます。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-128">Best of all, your app is updated in using your web server code.</span></span>  

## <span data-ttu-id="2b9a4-129">Microsoft Edge で PWAs (Chromium)</span><span class="sxs-lookup"><span data-stu-id="2b9a4-129">PWAs on Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="2b9a4-130">Web 標準 Api をターゲットとするプログレッシブ Web アプリを構築すると、アプリはプラットフォームとデバイスの間で展開される可能性があり、デバイス固有の機能を利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-130">When you build a Progressive Web App targeting web standard APIs, your application may be deployed across platforms and devices and take advantage of the device-specific capabilities as available.</span></span>  <span data-ttu-id="2b9a4-131">Microsoft Edge では、次の利点を web サイトに追加します (Chromium)。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-131">PWAs in Microsoft Edge \(Chromium\) add the following advantages to your website.</span></span>  

*   <span data-ttu-id="2b9a4-132">アプリは標準ベースの web プラットフォーム上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-132">Your app is built on a standards-based web platform.</span></span>  
*   <span data-ttu-id="2b9a4-133">ユーザーがブラウザーから直接アプリをインストールできるようにします。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-133">Enables your users to install your app directly from the browser.</span></span>  
*   <span data-ttu-id="2b9a4-134">ストアベースの展開または登録なしで、ユーザーがアプリをインストールできるようにします。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-134">Enables your users to install your app without a Store-based deployment or registration.</span></span>  
    
<span data-ttu-id="2b9a4-135">Desktop PWAs は、Microsoft Edge \ (Chromium \) のいずれかのプラットフォームでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-135">Desktop PWAs are supported on any of the platforms Microsoft Edge \(Chromium\) is available.</span></span> <span data-ttu-id="2b9a4-136">Microsoft Edge \ (Chromium \) は、Windows 7、Windows 10、macOS で利用できます。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-136">Microsoft Edge \(Chromium\) is available on Windows 7, Windows 10, and macOS.</span></span>  <span data-ttu-id="2b9a4-137">次の利点が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-137">The following benefits are included.</span></span>  

*   <span data-ttu-id="2b9a4-138">アプリケーションは、ナビゲーションバーの **インストール** アイコンを使ってブラウザー内から直接インストールできます。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-138">Applications may be installed directly from within the browser using the **Install** icon in the navigation bar.</span></span>  
    
    :::image type="complex" source="./media/install_pwa_icon.png" alt-text="アプリケーションのインストールのポップアップとアイコン" lightbox="./media/install_pwa_icon.png":::
       <span data-ttu-id="2b9a4-140">アプリケーションのインストールのポップアップとアイコン</span><span class="sxs-lookup"><span data-stu-id="2b9a4-140">Install application flyout and icon</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="2b9a4-141">アプリケーションは、[**設定**  >  ]**アプリ**メニューからインストール、実行、管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-141">Applications may also be installed, run, and managed from the **Settings** > **Apps** menu</span></span>  
    
    :::image type="complex" source="./media/app_menus.png" alt-text="アプリケーションのインストールのポップアップとアイコン" lightbox="./media/app_menus.png":::
       <span data-ttu-id="2b9a4-143">[設定] の [アプリケーション] メニュー項目</span><span class="sxs-lookup"><span data-stu-id="2b9a4-143">Application menu items under settings</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="2b9a4-144">Web 通知は Windows notification システムに統合されます。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-144">Web Notifications are integrated into the Windows notification system</span></span>  
*   <span data-ttu-id="2b9a4-145">アプリをインストールしたブラウザープロファイルの共有 cookie ストア</span><span class="sxs-lookup"><span data-stu-id="2b9a4-145">Shared cookie store with the browser profile that installed the app</span></span>  
*   <span data-ttu-id="2b9a4-146">**設定およびその**他の \ (\) メニューを使用して、 `...` 証明書の検証、サイトのアクセス許可、追跡保護、ブラウザーの拡張機能など、他のブラウザー機能にアクセスする</span><span class="sxs-lookup"><span data-stu-id="2b9a4-146">Access to other browser features using the **Setting and more** \(`...`\) menu including certificate validation, site permissions, tracking protection, and browser extensions</span></span>  
*   <span data-ttu-id="2b9a4-147">アプリをデバッグするための [Microsoft Edge DevTools][DevtoolsProgressiveWebApps] へのフルアクセス</span><span class="sxs-lookup"><span data-stu-id="2b9a4-147">Full access to [Microsoft Edge DevTools][DevtoolsProgressiveWebApps] for debugging your app</span></span>  
    
> [!IMPORTANT]
> <span data-ttu-id="2b9a4-148">特に、JavaScript を使って WinRT API 要求を行う Windows 10 用に PWAs をカスタマイズするには、 [EDGEHTML PWA 機能に固有のドキュメント][PwaEdgehtmlIndex]に移動します。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-148">To tailor PWAs specifically for Windows 10 that make WinRT API requests using JavaScript, navigate to [documentation specific to the EdgeHTML PWA features][PwaEdgehtmlIndex].</span></span>  <span data-ttu-id="2b9a4-149">Windows 10 での PWA のテストと Microsoft Store での配布について説明します。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-149">Learn more about testing your PWA on Windows 10 and distributing it in the Microsoft Store.</span></span>  

> [!NOTE]
> <span data-ttu-id="2b9a4-150">PWA の利点、今後の機能、および簡単なデモの詳細については、「 [ビルド 2020 PWA セッション][BuildVideo]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-150">For more information about PWA benefits, upcoming features, and short demos, navigate to [Build 2020 PWA session][BuildVideo].</span></span> 

## <span data-ttu-id="2b9a4-151">要件</span><span class="sxs-lookup"><span data-stu-id="2b9a4-151">Requirements</span></span>  

<span data-ttu-id="2b9a4-152">PWA として実行するには、サーバーでホストされる web アプリに次の最小要件が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-152">To run as a PWA, your server-hosted web app should include following minimum requirements.</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="2b9a4-153">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2b9a4-153">HTTPS</span></span>][WikiHttps]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="2b9a4-154">サーバーまたはアプリの通信にセキュリティで保護された接続を提供して、ユーザーを保護します。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-154">Protects your users by providing a secure connection for server or app communication.</span></span>  <span data-ttu-id="2b9a4-155">サービス作業者やその他の PWA テクノロジは、セキュリティで保護された接続を経由して提供される web リソース (または `localhost` デバッグ目的でのみ) と動作します。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-155">Service Workers and other PWA technologies only work with web resources served over a secure connection \(or from `localhost` for debugging purposes\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="2b9a4-156">サービス ワーカー</span><span class="sxs-lookup"><span data-stu-id="2b9a4-156">Service Workers</span></span>][MDNServiceWorkerApi]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="2b9a4-157">サービスワーカースレッドを使って、サーバーとクライアントアプリの間でネットワークプロキシとして機能します。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-157">Uses Service Worker threads to act as network proxies between your server and client app.</span></span>  <span data-ttu-id="2b9a4-158">サービスワーカースレッドは、オフラインサポート、リソースキャッシュ、プッシュ通知、バックグラウンドデータ同期、ページ読み込みパフォーマンス最適化を提供します。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-158">Service Worker threads provide offline support, resource caching, push notifications, background data sync, and  page-load performance optimizations.</span></span>    
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="2b9a4-159">Web アプリマニフェスト</span><span class="sxs-lookup"><span data-stu-id="2b9a4-159">Web App Manifest</span></span>][MDNWebAppManifest]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="2b9a4-160">Web アプリに関する主要な情報を示す JSON ベースのメタデータファイルを提供します。これにより、Windows 10 やその他のホストプラットフォームで、インストール可能なネイティブアプリのようなエクスペリエンスを備えた PWA ユーザーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-160">Provides a JSON-based metadata file that describes key information about your web app, so that Windows 10 and other host platforms provide your PWA users with an installable, native app-like experience.</span></span>  <span data-ttu-id="2b9a4-161">重要な情報には、アイコン、言語、URL エントリポイントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-161">Key information includes icons, language, and URL entry point.</span></span> 
   :::column-end:::
:::row-end:::  

<span data-ttu-id="2b9a4-162">また、アプリは次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-162">To be a great PWA, your app must also meet the following requirements.</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="2b9a4-163">ブラウザー間の互換性</span><span class="sxs-lookup"><span data-stu-id="2b9a4-163">Cross-browser compatibility</span></span>][MDNCrossBrowserTesting]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="2b9a4-164">さまざまなブラウザーと環境で [テスト][MicrosoftDeveloperEdgeToolsRemote] して、PWA が動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-164">Ensure your PWA works by [testing][MicrosoftDeveloperEdgeToolsRemote] in different browsers and environments.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="2b9a4-165">レスポンシブ デザイン</span><span class="sxs-lookup"><span data-stu-id="2b9a4-165">Responsive design</span></span>][WikiResponsiveWebDesign]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="2b9a4-166">流動的なレイアウトと柔軟な画像を採用しています。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-166">Employs fluid layouts and flexible images.</span></span>  <span data-ttu-id="2b9a4-167">応答性の高いデザインには、ユーザーのデバイスに UX を適応させる次の要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-167">Responsive design includes the following elements that adapt your UX to your user's device.</span></span>  
      
      *   <span data-ttu-id="2b9a4-168">CSS [グリッド][MDNCssGridLayout]</span><span class="sxs-lookup"><span data-stu-id="2b9a4-168">CSS [grid][MDNCssGridLayout]</span></span>  
      *   [<span data-ttu-id="2b9a4-169">flexbox</span><span class="sxs-lookup"><span data-stu-id="2b9a4-169">flexbox</span></span>][MDNCssFlexibleBoxLayout]  
      *   <span data-ttu-id="2b9a4-170">CSS [grid][MDNCssGridLayout] と [flexbox][MDNCssFlexibleBoxLayout]</span><span class="sxs-lookup"><span data-stu-id="2b9a4-170">CSS [grid][MDNCssGridLayout] and [flexbox][MDNCssFlexibleBoxLayout]</span></span>  
      *   [<span data-ttu-id="2b9a4-171">メディアクエリ</span><span class="sxs-lookup"><span data-stu-id="2b9a4-171">media queries</span></span>][MDNMediaQueries]  
      *   [<span data-ttu-id="2b9a4-172">応答性の高い画像</span><span class="sxs-lookup"><span data-stu-id="2b9a4-172">responsive images</span></span>][MDNResponsiveImages]  
      
      <span data-ttu-id="2b9a4-173">ブラウザーの [デバイスエミュレーションツール][DevToolsGuide|::ref1::|] を使ってローカルテストを行うか、 [リモートデバッグセッション][DevToolsProtocolClientsEdgeDevToolsPreview] を作成してターゲットデバイスで直接テストします。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-173">Uses [device emulation tools][DevToolsGuide|::ref1::|] from your browser to locally test, or create a [remote debugging session][DevToolsProtocolClientsEdgeDevToolsPreview] to test directly on a target device.</span></span>
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="2b9a4-174">ディープリンク</span><span class="sxs-lookup"><span data-stu-id="2b9a4-174">Deep linking</span></span>][WikiDeepLinking]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="2b9a4-175">サイトの各ページを一意の URL にルーティングして、既存のユーザーがソーシャルメディア共有を通じてさらに多くのユーザーとの共同作業を行うことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-175">Routes each page of your site to a unique URL so existing users may help you engage an even broader audience through social media sharing.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="2b9a4-176">検証とテストのプラクティス</span><span class="sxs-lookup"><span data-stu-id="2b9a4-176">Validation and testing practices</span></span>][Webhint]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="2b9a4-177">アプリの効率、堅牢性、安全性、アクセシビリティを最適化するために、 [Webhint][Webhint] などのコード品質ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-177">Uses code quality tools like the [Webhint][Webhint] linter to optimize the efficiency, robustness, safety, and accessibility of your app.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="2b9a4-178">Chromium PWA チェックリスト</span><span class="sxs-lookup"><span data-stu-id="2b9a4-178">Chromium PWA Checklist</span></span>][WebDevGoodPwaChecklist]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="2b9a4-179">Google baseline の PWA チェックリストに対して PWA を確認します。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-179">Verifies your PWA against the Google baseline PWA checklist.</span></span>  
   :::column-end:::
:::row-end:::  

> [!NOTE]
> <span data-ttu-id="2b9a4-180">[Microsoft][MicrosoftDeveloperStore] store アプリケーションとして PWA を有効にするには、 [Microsoft Store のプログレッシブ Web Apps (EdgeHTML)][PwaEdgehtmlMicrosoftStore]に移動します。</span><span class="sxs-lookup"><span data-stu-id="2b9a4-180">To turn your PWA into a [Microsoft Store][MicrosoftDeveloperStore] application, navigate to [Progressive Web Apps (EdgeHTML) in the Microsoft Store][PwaEdgehtmlMicrosoftStore].</span></span>  
  
## <span data-ttu-id="2b9a4-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b9a4-181">See also</span></span>  

*   [<span data-ttu-id="2b9a4-182">神話の場合</span><span class="sxs-lookup"><span data-stu-id="2b9a4-182">Myth Busting PWAs</span></span>][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [<span data-ttu-id="2b9a4-183">プログレッシブ Web アプリのためのプログレッシブロードマップ</span><span class="sxs-lookup"><span data-stu-id="2b9a4-183">A Progressive Roadmap for your Progressive Web App</span></span>][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [<span data-ttu-id="2b9a4-184">プログレッシブ Web アプリでのオフライン投稿</span><span class="sxs-lookup"><span data-stu-id="2b9a4-184">Offline POSTs with Progressive Web Apps</span></span>][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [<span data-ttu-id="2b9a4-185">PWA&</span><span class="sxs-lookup"><span data-stu-id="2b9a4-185">PWA Q&A</span></span>][AaronGustafsonNotebookPwaQa]  
*   [<span data-ttu-id="2b9a4-186">Web でのお賭け</span><span class="sxs-lookup"><span data-stu-id="2b9a4-186">Betting on the Web</span></span>][JoretegBlogBettingWeb]  
*   [<span data-ttu-id="2b9a4-187">プログレッシブ Web アプリに名前を付ける</span><span class="sxs-lookup"><span data-stu-id="2b9a4-187">Naming Progressive Web Apps</span></span>][Fberriman20170626NamingProgressiveWebApps]  
*   [<span data-ttu-id="2b9a4-188">フレームワークなしでプログレッシブ Web アプリケーションを設計して構築する (パート 1)</span><span class="sxs-lookup"><span data-stu-id="2b9a4-188">Designing And Building A Progressive Web Application Without A Framework (Part 1)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]  
*   [<span data-ttu-id="2b9a4-189">フレームワークを使わないプログレッシブ Web アプリケーションの設計と構築 (パート 2)</span><span class="sxs-lookup"><span data-stu-id="2b9a4-189">Designing And Building A Progressive Web Application Without A Framework (Part 2)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]  
*   [<span data-ttu-id="2b9a4-190">フレームワークを使わないプログレッシブ Web アプリケーションの設計と構築 (パート 3)</span><span class="sxs-lookup"><span data-stu-id="2b9a4-190">Designing And Building A Progressive Web Application Without A Framework (Part 3)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]  
    
<!-- links -->  

[DevToolsProtocolClientsEdgeDevToolsPreview]: ../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge の DevTools プレビュー - DevTools プロトコル クライアント"  
[DevToolsGuideEmulation]: ../devtools-guide/emulation.md "エミュレーション"  
[DevtoolsProgressiveWebApps]: ../devtools-guide-chromium/progressive-web-apps.md "プログレッシブ Web アプリをデバッグする"  
[DevGuideWhatsNewEdgeHtml17]: ../dev-guide/whats-new/edgehtml-17.md "EdgeHTML 17 の新機能"  
[DevGuideWhatsNewEdgeHtml14]: ../dev-guide/whats-new/edgehtml-14.md "EdgeHTML 14 の新機能"  
[PwaEdgehtmlIndex]: ../progressive-web-apps-edgehtml/index.md "Windows のプログレッシブ Web アプリ (EdgeHTML)"  
[PwaEdgehtmlMicrosoftStore]: ../progressive-web-apps-edgehtml/microsoft-store.md "Microsoft Store のプログレッシブ Web アプリ"
<!--PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission]: ../progressive-web-apps-edgehtml/microsoft-store.md#criteria-for-automatic-submission "Criteria for automatic submission - Progressive Web Apps in the Microsoft Store"  -->  

[WindowsUWPControlsPatternTilesNotificationsWns]: /windows/uwp/controls-and-patterns/tiles-and-notifications-windows-push-notification-services--wns--overview.md "Windows プッシュ通知サービス \ (WNS \) の概要"  
[WindowsUWPDesignDevicesDesigningTv]: /windows/uwp/design/devices/designing-for-tv.md "Xbox およびテレビ向け設計"  
[WindowsUWPDesignDevicesIndex]: /windows/uwp/design/devices/index.md "UWP デバイスの UI に関する考慮事項"  
[WindowsUWPGetStartedGuide]: /windows/uwp/get-started/universal-application-platform-guide.md "ユニバーサル Windows プラットフォーム (UWP) アプリとは何ですか?"  
[WindowsUWPLaunchResumeBackgroundTasks]: /windows/uwp/launch-resume/support-your-app-with-background-tasks.md "バックグラウンドタスクによるアプリのサポート"  
[WindowsUWPPublishIndex]: /windows/uwp/publish/index.md "Windows アプリとゲームを公開する"  
[WindowsUWPPublishDeveloperAccount]: /windows/uwp/publish/opening-a-developer-account.md "開発者アカウントを開く"  

[WindowsBlogsWelcomingPWAsEdgeWindows]: https://blogs.windows.com/msedgedev/2018/02/06/welcoming-progressive-web-apps-edge-windows-10/#56z7mJwKsykfbR4I.97 "Microsoft Edge および Windows 10 へのプログレッシブ Web アプリの歓迎-Windows ブログ"  
[MicrosoftDeveloperEdgePlatformStatusBackgroundSync]: https://developer.microsoft.com/microsoft-edge/platform/status/backgroundsyncapi "バックグラウンド同期 API-Microsoft Edge プラットフォームの状態"  
[MicrosoftDeveloperEdgePlatformStatusWebApplicationManifest]: https://developer.microsoft.com/microsoft-edge/platform/status/webapplicationmanifest "Web アプリケーションマニフェスト-Microsoft Edge プラットフォームの状態"  
[MicrosoftDeveloperEdgeToolsRemote]: https://developer.microsoft.com/microsoft-edge/tools/remote "即座のテスト"  
[MicrosoftDeveloperWindowsMixedReality]: https://developer.microsoft.com/windows/mixed-reality "開発者向けの Mixed Reality"  
[MicrosoftDeveloperWindowsSurfaceHub]: https://developer.microsoft.com/windows/surfacehub "Microsoft Surface Hub"  
[MicrosoftDeveloperStore]: https://developer.microsoft.com/store "Microsoft Developer Store"  
[MicrosoftEdge]: https://www.microsoft.com/edge "新しい Microsoft Edge ブラウザーをダウンロードする"  
[MicrosoftSupportWindowsFocusAssist]: https://support.microsoft.com/help/4026996/windows-10-turn-focus-assist-on-or-off "Windows 10 でフォーカスアシストのオンとオフを切り替える"  
[MicrosoftSupportWindowsNotificationSettings]: https://support.microsoft.com/help/4028678/windows-10-change-notification-settings "Windows 10 の通知設定を変更する"  

[AaronGustafsonNotebookPwaQa]: https://www.aaron-gustafson.com/notebook/pwa-qa "PWA&"  

[AListApartUnderstandingProgressiveEnhancement]: https://alistapart.com/article/understandingprogressiveenhancement "プログレッシブエンハンスメントについて-リストとの分離"  

[MDNApps]: https://developer.mozilla.org/Apps/Progressive "アプリ |MDN"  
[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "キャッシュ |MDN"  
[MDNCrossBrowserTesting]: https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing "クロスブラウザーテスト |MDN"  
[MDNCssFlexibleBoxLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Flexible_Box_Layout "CSS の柔軟なボックスレイアウト |MDN"  
[MDNCssGridLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout "CSS グリッドレイアウト |MDN"  
[MDNFetchApi]: https://developer.mozilla.org/docs/Web/API/Fetch_API "取得 API |MDN"  
[MDNMediaQueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries "メディアクエリ |MDN"  
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "プッシュ API |MDN"  
[MDNPwaAdvantagesDiscoverable]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Discoverable "見つけやすい web アプリの利点"  
[MDNPwaAdvantagesInstallable]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Installable "インストール可能なプログレッシブ web アプリの利点"  
[MDNPwaAdvantagesLinkable]: https://developer.mozilla.org/Apps/Progressive/Advantages#Linkable "Linkable プログレッシブ web アプリの利点"  
[MDNPwaAdvantagesNetworkIndependent]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Network_independent "ネットワークに依存しないプログレッシブ web アプリの利点"  
[MDNPwaAdvantagesProgressive]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Progressive "プログレッシブプログレッシブ web アプリの利点"  
[MDNPwaAdvantagesReEngageable]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Re-engageable "Engageable-プログレッシブ web アプリの利点"  
[MDNPwaAdvantagesResponsive]: https://developer.mozilla.org/Apps/Progressive/Advantages#Responsive "応答性の高いプログレッシブ web アプリの利点"  
[MDNPwaAdvantagesSafe]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Safe "安全なプログレッシブ web アプリの利点"  
[MDNResponsiveImages]: https://developer.mozilla.org/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images "応答性の高い画像 |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "Service Worker API |MDN"  
[MDNSyncManager]: https://developer.mozilla.org/docs/Web/API/SyncManager "SyncManager |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web アプリマニフェスト |MDN"  

[BuildVideo]: https://www.youtube.com/watch?v=y4p_QHZtMKM "PWA ビデオ"  

[CloudfourThinksProgressiveRoadmapYourWebApp]: https://cloudfour.com/thinks/a-progressive-roadmap-for-your-progressive-web-app "プログレッシブ Web アプリのためのプログレッシブロードマップ"  

[Davrous20191018MythBustingPwasNewEdgeEdition]: https://www.davrous.com/2019/10/18/myth-busting-pwas-the-new-edge-edition "神話のお客は新しい Edge エディション"  

[Fberriman20170626NamingProgressiveWebApps]: https://fberriman.com/2017/06/26/naming-progressive-web-apps "プログレッシブ Web アプリに名前を付ける"  

[JoretegBlogBettingWeb]: https://joreteg.com/blog/betting-on-the-web "Web でのお賭け"  

[MediumWebEdgeOfflinePostsProgressiveWebApps]: https://medium.com/web-on-the-edge/offline-posts-with-progressive-web-apps-fc2dc4ad895 "プログレッシブ Web アプリでのオフライン投稿"  

[PWABuilder]: https://www.pwabuilder.com "PWABuilder"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-1 "フレームワークなしでプログレッシブ Web アプリケーションを設計して構築する (パート 1)"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-2 "フレームワークを使わないプログレッシブ Web アプリケーションの設計と構築 (パート 2)"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-3 "フレームワークを使わないプログレッシブ Web アプリケーションの設計と構築 (パート 3)"  

[WebDevGoodPwaChecklist]: https://web.dev/pwa-checklist "優れたプログレッシブ Web アプリはどのようになりますか? |web.xml"  

[Webhint]: https://webhint.io "web ヒント"  

[WikiDeepLinking]: https://en.wikipedia.org/wiki/Deep_linking "ディープリンク-Wikipedia"  
[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS-Wikipedia"  
[WikiResponsiveWebDesign]: https://en.wikipedia.org/wiki/Responsive_web_design "応答性の高い web デザイン-Wikipedia"  
