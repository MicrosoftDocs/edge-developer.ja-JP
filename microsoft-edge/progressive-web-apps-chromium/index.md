---
description: プログレッシブ Web アプリは Windows 10 でネイティブに実行されます。  ここでは、web 開発者として知っておく必要があるものをすべて紹介します。
title: Windows のプログレッシブ Web アプリ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/17/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: pwa
keywords: プログレッシブ web アプリ、PWA、エッジ、JavaScript、Windows、UWP、Microsoft ストア
ms.openlocfilehash: 90740bac07ebfd74f89e2524e6955621e1b09b05
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882808"
---
# <span data-ttu-id="4d09b-105">Windows のプログレッシブ Web アプリ</span><span class="sxs-lookup"><span data-stu-id="4d09b-105">Progressive Web Apps on Windows</span></span>  

<span data-ttu-id="4d09b-106">[プログレッシブ Web アプリ][MDNApps](または単に pwas) を使用する場合、クロスプラットフォームの相互運用性を実現するために開かれた web テクノロジを使用する方法と、デバイスに合わせてカスタマイズされたネイティブアプリなどのエクスペリエンスをユーザーに提供する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4d09b-106">With [Progressive Web Apps][MDNApps] \(or simply PWAs\), you do not have to decide between using open web technologies for cross-platform interoperability and providing your users with a native app-like experience customized for their devices.</span></span>  <span data-ttu-id="4d09b-107">PWAs は、サポートしているプラットフォーム上のネイティブアプリのように機能するように[段階的に拡張][AListApartUnderstandingProgressiveEnhancement]された web サイトだけです。</span><span class="sxs-lookup"><span data-stu-id="4d09b-107">PWAs are just websites that are [progressively enhanced][AListApartUnderstandingProgressiveEnhancement] to function like native apps on supporting platforms.</span></span>  <span data-ttu-id="4d09b-108">PWA では、Web アプリとネイティブ アプリの良いところが組み合わされています。</span><span class="sxs-lookup"><span data-stu-id="4d09b-108">The qualities of a PWA combine the best of the web and native apps.</span></span>  

:::row:::
    :::column:::
        ![検出可能なアイコン][ImageISearch]
        ### [<span data-ttu-id="4d09b-110">見つけ</span><span class="sxs-lookup"><span data-stu-id="4d09b-110">Discoverable</span></span>][MDNPwaAdvantagesDiscoverable]
        <span data-ttu-id="4d09b-111">Web 検索結果とサポートされているアプリストアから</span><span class="sxs-lookup"><span data-stu-id="4d09b-111">From web search results and supporting app stores</span></span>
    :::column-end:::
    :::column:::
        ![インストール可能なアイコン][ImageIPackage]
        ### [<span data-ttu-id="4d09b-113">Installable</span><span class="sxs-lookup"><span data-stu-id="4d09b-113">Installable</span></span>][MDNPwaAdvantagesInstallable]
        <span data-ttu-id="4d09b-114">ホーム画面、[スタート] メニュー、タスクバーなどのピン留めと起動</span><span class="sxs-lookup"><span data-stu-id="4d09b-114">Pin and launch from the home screen, Start Menu, Taskbar, and so on</span></span>
    :::column-end:::
    :::column:::
        ![再 engageable アイコン][ImageIPushNotification]
        ### [<span data-ttu-id="4d09b-116">再 engageable</span><span class="sxs-lookup"><span data-stu-id="4d09b-116">Re-engageable</span></span>][MDNPwaAdvantagesReEngageable]
        <span data-ttu-id="4d09b-117">アプリがアクティブでない場合でも、プッシュ通知を送信する</span><span class="sxs-lookup"><span data-stu-id="4d09b-117">Send push notifications, even when the app is not active</span></span>
    :::column-end:::
    :::column:::
        ![ネットワークに依存しないアイコン][ImageIOffline]
        ### [<span data-ttu-id="4d09b-119">ネットワークに依存しない</span><span class="sxs-lookup"><span data-stu-id="4d09b-119">Network Independent</span></span>][MDNPwaAdvantagesNetworkIndependent]
        <span data-ttu-id="4d09b-120">オフラインおよび低ネットワークの状態で動作する</span><span class="sxs-lookup"><span data-stu-id="4d09b-120">Works offline and in low-network conditions</span></span>
    :::column-end:::
:::row-end:::
:::row:::
    :::column:::
        ![プログレッシブアイコン][ImageIProgressive]
        ### [<span data-ttu-id="4d09b-122">的</span><span class="sxs-lookup"><span data-stu-id="4d09b-122">Progressive</span></span>][MDNPwaAdvantagesProgressive]
        <span data-ttu-id="4d09b-123">デバイス機能を使用したエクスペリエンスのスケールアップ (またはダウン)</span><span class="sxs-lookup"><span data-stu-id="4d09b-123">Experience scales up (or down) with device capabilities</span></span>
    :::column-end:::
    :::column:::
        ![安全なアイコン][ImageISecurity]
        ### [<span data-ttu-id="4d09b-125">問題</span><span class="sxs-lookup"><span data-stu-id="4d09b-125">Safe</span></span>][MDNPwaAdvantagesSafe]
        <span data-ttu-id="4d09b-126">セキュリティで保護された HTTPS エンドポイントとその他のユーザーの保護機能を提供する</span><span class="sxs-lookup"><span data-stu-id="4d09b-126">Provides a secure HTTPS endpoint and other user safeguards</span></span>
    :::column-end:::
    :::column:::
        ![応答性アイコン][ImageIResponsive]
        ### [<span data-ttu-id="4d09b-128">応答中</span><span class="sxs-lookup"><span data-stu-id="4d09b-128">Responsive</span></span>][MDNPwaAdvantagesResponsive]
        <span data-ttu-id="4d09b-129">ユーザーの画面サイズまたは印刷の向きと入力方式に合わせて調整する</span><span class="sxs-lookup"><span data-stu-id="4d09b-129">Adapts to the user's screen size or orientation and input method</span></span>
    :::column-end:::
    :::column:::
        ![Linkable アイコン][ImageILink]
        ### [<span data-ttu-id="4d09b-131">Linkable</span><span class="sxs-lookup"><span data-stu-id="4d09b-131">Linkable</span></span>][MDNPwaAdvantagesLinkable]
        <span data-ttu-id="4d09b-132">標準ハイパーリンクを共有して起動する</span><span class="sxs-lookup"><span data-stu-id="4d09b-132">Share and launch from a standard hyperlink</span></span>
    :::column-end:::
:::row-end:::

<span data-ttu-id="4d09b-133">既存のサイトを PWA に構築または変換することによって、プッシュ通知、アプリのような統合、オフラインサポートなどを使用して、既存のユーザーとより適切に連携できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4d09b-133">By building or converting your existing site to a PWA, you engage better with your existing audience using push notifications, app-like integration, and offline support.</span></span>  <span data-ttu-id="4d09b-134">同時に、ユーザーが検索とリンク共有を通じて PWA を見つけている場合は、引き続きオープン web 上で参加者を構築する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d09b-134">At the same time, you should continue to build your audience on the open web, as users discover your PWA through search and link-sharing.</span></span>  <span data-ttu-id="4d09b-135">いずれにしても、web サーバーのコードを更新するだけでアプリを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="4d09b-135">Best of all, you may update your app by simply updating your web server code.</span></span>  

## <span data-ttu-id="4d09b-136">Microsoft Edge で PWAs (Chromium)</span><span class="sxs-lookup"><span data-stu-id="4d09b-136">PWAs on Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="4d09b-137">Web 標準 Api をターゲットとするプログレッシブ Web アプリを構築すると、アプリはプラットフォームとデバイスの間で展開され、利用可能なデバイス固有の機能を利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4d09b-137">When you build a Progressive Web App targeting web standard APIs, your application may be deployed across platforms and devices and take advantage of the device specific capabilities as available.</span></span>  <span data-ttu-id="4d09b-138">PWAs は Microsoft Edge (Chromium \) では、web プラットフォームの観点からの標準に準拠しており、ストアベースの展開や登録を必要とせずに、ブラウザー内から直接アプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="4d09b-138">PWAs in Microsoft Edge \(Chromium\) are completely standards-based from a web platform perspective and enable users to install the app directly from within the browser without the need for Store-based deployment or registration.</span></span>  <span data-ttu-id="4d09b-139">Desktop PWAs は、Windows 7、Windows 10、macOS など、Microsoft Edge \ (Chromium \) のいずれかのプラットフォームでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4d09b-139">Desktop PWAs are supported on any of the platforms Microsoft Edge \(Chromium\) is available, including Windows 7, Windows 10, and macOS.</span></span>  <span data-ttu-id="4d09b-140">他にも次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="4d09b-140">Other benefits include:</span></span>  

*   <span data-ttu-id="4d09b-141">アプリケーションは、ナビゲーションバーの**インストール**アイコンを使用して、ブラウザー内から直接インストールできます。</span><span class="sxs-lookup"><span data-stu-id="4d09b-141">Applications may be installed directly from within the browser via the **Install** icon in the navigation bar.</span></span>  
    
    ![アプリケーションのインストールのポップアップとアイコン][ImageInstallPwa]  
    
*   <span data-ttu-id="4d09b-143">[アプリの**設定**  >  **Apps** ] メニューからアプリケーションをインストール、実行、管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="4d09b-143">Applications may also be installed, run and managed from the **Settings** > **Apps** menu</span></span>  
    
    ![[設定] の [アプリケーション] メニュー項目][ImageAppMenus]  

*   <span data-ttu-id="4d09b-145">Web 通知は Windows notification システムに統合されます。</span><span class="sxs-lookup"><span data-stu-id="4d09b-145">Web Notifications are integrated into the Windows notification system</span></span>
*   <span data-ttu-id="4d09b-146">アプリをインストールしたブラウザープロファイルの共有 cookie ストア</span><span class="sxs-lookup"><span data-stu-id="4d09b-146">Shared cookie store with the browser profile that installed the app</span></span>
*   <span data-ttu-id="4d09b-147">メニューから、 `...` 証明書の検証、サイトのアクセス許可、追跡保護、ブラウザーの拡張機能など、他のブラウザー機能にアクセスする</span><span class="sxs-lookup"><span data-stu-id="4d09b-147">Access to other browser features via the `...` menu including certificate validation, site permissions, tracking protection, and browser extensions</span></span>
*   <span data-ttu-id="4d09b-148">アプリをデバッグするための[Microsoft Edge DevTools][DevtoolsProgressiveWebApps]へのフルアクセス</span><span class="sxs-lookup"><span data-stu-id="4d09b-148">Full access to [Microsoft Edge DevTools][DevtoolsProgressiveWebApps] for debugging your app</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="4d09b-149">特に、JavaScript を使って WinRT API 要求を行う Windows 10 用に PWAs をカスタマイズする方法については、「 [EDGEHTML PWA 機能に固有のドキュメント][PwaEdgehtmlIndex]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d09b-149">To tailor PWAs specifically for Windows 10 that make WinRT API requests using JavaScript, see the [documentation specific to the EdgeHTML PWA features][PwaEdgehtmlIndex].</span></span>  <span data-ttu-id="4d09b-150">Windows 10 での PWA のテストと Microsoft Store での配布について説明します。</span><span class="sxs-lookup"><span data-stu-id="4d09b-150">Learn more about testing your PWA on Windows 10 and distributing it in the Microsoft Store.</span></span>  

> [!NOTE]
> <span data-ttu-id="4d09b-151">PWA 特典、今後の機能、簡単なデモの概要については、[ビルド 2020 pwa セッション][BuildVideo]を確認してください。</span><span class="sxs-lookup"><span data-stu-id="4d09b-151">Check out the [Build 2020 PWA session][BuildVideo] for an overview of PWA benefits, upcoming features and short demos.</span></span> 

## <span data-ttu-id="4d09b-152">要件</span><span class="sxs-lookup"><span data-stu-id="4d09b-152">Requirements</span></span>  

<span data-ttu-id="4d09b-153">PWA として実行するには、サーバーでホストされる web アプリに次の最小要件が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d09b-153">To run as a PWA, your server-hosted web app should include following minimum requirements.</span></span>  

| <span data-ttu-id="4d09b-154">要件</span><span class="sxs-lookup"><span data-stu-id="4d09b-154">Requirement</span></span> | <span data-ttu-id="4d09b-155">詳細</span><span class="sxs-lookup"><span data-stu-id="4d09b-155">Details</span></span> | 
|:--- |:--- |  
| [<span data-ttu-id="4d09b-156">HTTPS</span><span class="sxs-lookup"><span data-stu-id="4d09b-156">HTTPS</span></span>][WikiHttps] | <span data-ttu-id="4d09b-157">サーバーまたはアプリの通信にセキュリティで保護された接続を提供して、ユーザーを保護します。</span><span class="sxs-lookup"><span data-stu-id="4d09b-157">Protect your users by providing a secure connection for server or app communication.</span></span>  <span data-ttu-id="4d09b-158">サービス作業者やその他の PWA テクノロジは、セキュリティで保護された接続を経由して提供される web リソース (または `localhost` デバッグ目的でのみ) と動作します。</span><span class="sxs-lookup"><span data-stu-id="4d09b-158">Service Workers and other PWA technologies only work with web resources served over a secure connection \(or from `localhost` for debugging purposes\).</span></span>  |  
| [<span data-ttu-id="4d09b-159">サービス ワーカー</span><span class="sxs-lookup"><span data-stu-id="4d09b-159">Service Workers</span></span>][MDNServiceWorkerApi] | <span data-ttu-id="4d09b-160">サービスワーカースレッドを使って、オフラインサポート、リソースキャッシュ、プッシュ通知、バックグラウンドデータ同期、ページ読み込みパフォーマンス最適化を提供するために、サーバーとクライアントアプリの間でネットワークプロキシとして機能します。</span><span class="sxs-lookup"><span data-stu-id="4d09b-160">Use Service Worker threads to act as network proxies between your server and client app in order to provide offline support, resource caching, push notifications, background data sync, and  page load perf optimizations.</span></span>  |  
| [<span data-ttu-id="4d09b-161">Web アプリマニフェスト</span><span class="sxs-lookup"><span data-stu-id="4d09b-161">Web App Manifest</span></span>][MDNWebAppManifest] | <span data-ttu-id="4d09b-162">Windows 10 やその他のホストプラットフォームが、インストール可能なネイティブアプリのようなエクスペリエンスを備えた PWA ユーザーを提供できるように、Windows 10 とその他のホストプラットフォームが、自分の web アプリについての重要な情報を記述した JSON ベースのメタデータファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="4d09b-162">Provide a JSON-based metadata file describing key information about your web app \(such as icons, language, and URL entry point\), so that Windows 10 and other host platforms are able to provide your PWA users with an installable, native app-like experience.</span></span>  |  

<span data-ttu-id="4d09b-163">また、アプリは次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d09b-163">To be a great PWA, your app must also meet the following requirements.</span></span>  

| <span data-ttu-id="4d09b-164">要件</span><span class="sxs-lookup"><span data-stu-id="4d09b-164">Requirement</span></span> | <span data-ttu-id="4d09b-165">詳細</span><span class="sxs-lookup"><span data-stu-id="4d09b-165">Details</span></span> | 
|:--- |:--- |  
| [<span data-ttu-id="4d09b-166">ブラウザー間の互換性</span><span class="sxs-lookup"><span data-stu-id="4d09b-166">Cross-browser compatibility</span></span>][MDNCrossBrowserTesting] | <span data-ttu-id="4d09b-167">さまざまなブラウザーと環境で[テスト][MicrosoftDeveloperEdgeToolsRemote]して、PWA が動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="4d09b-167">Ensure your PWA works by [testing][MicrosoftDeveloperEdgeToolsRemote] in different browsers and environments.</span></span>  |  
| [<span data-ttu-id="4d09b-168">レスポンシブ デザイン</span><span class="sxs-lookup"><span data-stu-id="4d09b-168">Responsive design</span></span>][WikiResponsiveWebDesign] | <span data-ttu-id="4d09b-169">CSS [grid][MDNCssGridLayout]、 [flexbox][MDNCssFlexibleBoxLayout]、css [grid][MDNCssGridLayout]と[flexbox][MDNCssFlexibleBoxLayout] 、[メディアクエリ][MDNMediaQueries]、[応答性][MDNResponsiveImages]の高い画像を使用して、ユーザーのデバイスに合わせて UX を調整します。</span><span class="sxs-lookup"><span data-stu-id="4d09b-169">Employ fluid layouts and flexible images with CSS [grid][MDNCssGridLayout], [flexbox][MDNCssFlexibleBoxLayout], CSS [grid][MDNCssGridLayout] and [flexbox][MDNCssFlexibleBoxLayout] , [media queries][MDNMediaQueries], and [responsive images][MDNResponsiveImages] to adapt your UX to your user's device.</span></span>  <span data-ttu-id="4d09b-170">ブラウザーの[デバイスエミュレーションツール][DevToolsGuide|::ref1::|]を使ってローカルでテストするか、[リモートデバッグセッション][DevToolsProtocolClientsEdgeDevToolsPreview]をセットアップしてターゲットデバイスで直接テストします。</span><span class="sxs-lookup"><span data-stu-id="4d09b-170">Use [device emulation tools][DevToolsGuide|::ref1::|] from your browser to test locally, or set up a [remote debugging session][DevToolsProtocolClientsEdgeDevToolsPreview] to test directly on a target device.</span></span>  |  
| [<span data-ttu-id="4d09b-171">ディープリンク</span><span class="sxs-lookup"><span data-stu-id="4d09b-171">Deep linking</span></span>][WikiDeepLinking] | <span data-ttu-id="4d09b-172">サイトの各ページを一意の URL にルーティングして、既存のユーザーがソーシャルメディア共有を通じてさらに多くのユーザーとの共同作業を行うことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="4d09b-172">Route each page of your site to a unique URL so existing users may help you engage an even broader audience through social media sharing.</span></span>  |  
| [<span data-ttu-id="4d09b-173">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="4d09b-173">Best practices</span></span>][Webhint] | <span data-ttu-id="4d09b-174">アプリの効率、堅牢性、安全性、アクセシビリティを最適化するには、 [Webhint][Webhint]のようなコード品質ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="4d09b-174">Use code quality tools like the [Webhint][Webhint] linter to optimize the efficiency, robustness, safety, and accessibility of your app.</span></span>  |  
| [<span data-ttu-id="4d09b-175">Chromium PWA チェックリスト</span><span class="sxs-lookup"><span data-stu-id="4d09b-175">Chromium PWA Checklist</span></span>][WebDevGoodPwaChecklist] | <span data-ttu-id="4d09b-176">Google ベースラインの PWA チェックリストに対して PWA のチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4d09b-176">Check your PWA against the Google baseline PWA checklist.</span></span>  |  

<span data-ttu-id="4d09b-177">[Microsoft Store][MicrosoftDeveloperStore]アプリケーションとして PWA を有効にする場合は、「[プログレッシブ Web Apps (EdgeHTML)][PwaEdgehtmlMicrosoftStore] 」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d09b-177">If you want to turn your PWA into a [Microsoft Store][MicrosoftDeveloperStore] application, head to the [Progressive Web Apps (EdgeHTML)][PwaEdgehtmlMicrosoftStore] documentation.</span></span>  
  

<!-- image links -->  

[ImageISearch]: media/i_search.png  
[ImageIPackage]: media/i_package.png  
[ImageIPushNotification]: media/i_push-notification.png  
[ImageIOffline]: media/i_offline.png  
[ImageIProgressive]: media/i_progressive.png  
[ImageISecurity]: media/i_security.png  
[ImageIResponsive]: media/i_responsive.png  
[ImageILink]: media/i_link.png  

[ImageInstallPwa]: ./media/Install_PWA.png  
[ImageAppMenus]: ./media/App_menus.png  

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

[PWABuilder]: https://www.pwabuilder.com "PWABuilder"  

[WebDevGoodPwaChecklist]: https://web.dev/pwa-checklist "優れたプログレッシブ Web アプリはどのようになりますか? |web.xml"  

[Webhint]: https://webhint.io "web ヒント"  

[WikiDeepLinking]: https://en.wikipedia.org/wiki/Deep_linking "ディープリンク-Wikipedia"  
[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS-Wikipedia"  
[WikiResponsiveWebDesign]: https://en.wikipedia.org/wiki/Responsive_web_design "応答性の高い web デザイン-Wikipedia"  
