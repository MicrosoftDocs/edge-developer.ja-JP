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
# Windows のプログレッシブ Web アプリ  

[プログレッシブ Web アプリ][MDNApps](または単に pwas) を使用する場合、クロスプラットフォームの相互運用性を実現するために開かれた web テクノロジを使用する方法と、デバイスに合わせてカスタマイズされたネイティブアプリなどのエクスペリエンスをユーザーに提供する必要はありません。  PWAs は、サポートしているプラットフォーム上のネイティブアプリのように機能するように[段階的に拡張][AListApartUnderstandingProgressiveEnhancement]された web サイトだけです。  PWA では、Web アプリとネイティブ アプリの良いところが組み合わされています。  

:::row:::
    :::column:::
        ![検出可能なアイコン][ImageISearch]
        ### [見つけ][MDNPwaAdvantagesDiscoverable]
        Web 検索結果とサポートされているアプリストアから
    :::column-end:::
    :::column:::
        ![インストール可能なアイコン][ImageIPackage]
        ### [Installable][MDNPwaAdvantagesInstallable]
        ホーム画面、[スタート] メニュー、タスクバーなどのピン留めと起動
    :::column-end:::
    :::column:::
        ![再 engageable アイコン][ImageIPushNotification]
        ### [再 engageable][MDNPwaAdvantagesReEngageable]
        アプリがアクティブでない場合でも、プッシュ通知を送信する
    :::column-end:::
    :::column:::
        ![ネットワークに依存しないアイコン][ImageIOffline]
        ### [ネットワークに依存しない][MDNPwaAdvantagesNetworkIndependent]
        オフラインおよび低ネットワークの状態で動作する
    :::column-end:::
:::row-end:::
:::row:::
    :::column:::
        ![プログレッシブアイコン][ImageIProgressive]
        ### [的][MDNPwaAdvantagesProgressive]
        デバイス機能を使用したエクスペリエンスのスケールアップ (またはダウン)
    :::column-end:::
    :::column:::
        ![安全なアイコン][ImageISecurity]
        ### [問題][MDNPwaAdvantagesSafe]
        セキュリティで保護された HTTPS エンドポイントとその他のユーザーの保護機能を提供する
    :::column-end:::
    :::column:::
        ![応答性アイコン][ImageIResponsive]
        ### [応答中][MDNPwaAdvantagesResponsive]
        ユーザーの画面サイズまたは印刷の向きと入力方式に合わせて調整する
    :::column-end:::
    :::column:::
        ![Linkable アイコン][ImageILink]
        ### [Linkable][MDNPwaAdvantagesLinkable]
        標準ハイパーリンクを共有して起動する
    :::column-end:::
:::row-end:::

既存のサイトを PWA に構築または変換することによって、プッシュ通知、アプリのような統合、オフラインサポートなどを使用して、既存のユーザーとより適切に連携できるようになります。  同時に、ユーザーが検索とリンク共有を通じて PWA を見つけている場合は、引き続きオープン web 上で参加者を構築する必要があります。  いずれにしても、web サーバーのコードを更新するだけでアプリを更新することができます。  

## Microsoft Edge で PWAs (Chromium)  

Web 標準 Api をターゲットとするプログレッシブ Web アプリを構築すると、アプリはプラットフォームとデバイスの間で展開され、利用可能なデバイス固有の機能を利用できるようになります。  PWAs は Microsoft Edge (Chromium \) では、web プラットフォームの観点からの標準に準拠しており、ストアベースの展開や登録を必要とせずに、ブラウザー内から直接アプリをインストールできます。  Desktop PWAs は、Windows 7、Windows 10、macOS など、Microsoft Edge \ (Chromium \) のいずれかのプラットフォームでサポートされています。  他にも次のような利点があります。  

*   アプリケーションは、ナビゲーションバーの**インストール**アイコンを使用して、ブラウザー内から直接インストールできます。  
    
    ![アプリケーションのインストールのポップアップとアイコン][ImageInstallPwa]  
    
*   [アプリの**設定**  >  **Apps** ] メニューからアプリケーションをインストール、実行、管理することもできます。  
    
    ![[設定] の [アプリケーション] メニュー項目][ImageAppMenus]  

*   Web 通知は Windows notification システムに統合されます。
*   アプリをインストールしたブラウザープロファイルの共有 cookie ストア
*   メニューから、 `...` 証明書の検証、サイトのアクセス許可、追跡保護、ブラウザーの拡張機能など、他のブラウザー機能にアクセスする
*   アプリをデバッグするための[Microsoft Edge DevTools][DevtoolsProgressiveWebApps]へのフルアクセス  

> [!IMPORTANT]
> 特に、JavaScript を使って WinRT API 要求を行う Windows 10 用に PWAs をカスタマイズする方法については、「 [EDGEHTML PWA 機能に固有のドキュメント][PwaEdgehtmlIndex]」を参照してください。  Windows 10 での PWA のテストと Microsoft Store での配布について説明します。  

> [!NOTE]
> PWA 特典、今後の機能、簡単なデモの概要については、[ビルド 2020 pwa セッション][BuildVideo]を確認してください。 

## 要件  

PWA として実行するには、サーバーでホストされる web アプリに次の最小要件が含まれている必要があります。  

| 要件 | 詳細 | 
|:--- |:--- |  
| [HTTPS][WikiHttps] | サーバーまたはアプリの通信にセキュリティで保護された接続を提供して、ユーザーを保護します。  サービス作業者やその他の PWA テクノロジは、セキュリティで保護された接続を経由して提供される web リソース (または `localhost` デバッグ目的でのみ) と動作します。  |  
| [サービス ワーカー][MDNServiceWorkerApi] | サービスワーカースレッドを使って、オフラインサポート、リソースキャッシュ、プッシュ通知、バックグラウンドデータ同期、ページ読み込みパフォーマンス最適化を提供するために、サーバーとクライアントアプリの間でネットワークプロキシとして機能します。  |  
| [Web アプリマニフェスト][MDNWebAppManifest] | Windows 10 やその他のホストプラットフォームが、インストール可能なネイティブアプリのようなエクスペリエンスを備えた PWA ユーザーを提供できるように、Windows 10 とその他のホストプラットフォームが、自分の web アプリについての重要な情報を記述した JSON ベースのメタデータファイルを提供します。  |  

また、アプリは次の要件を満たしている必要があります。  

| 要件 | 詳細 | 
|:--- |:--- |  
| [ブラウザー間の互換性][MDNCrossBrowserTesting] | さまざまなブラウザーと環境で[テスト][MicrosoftDeveloperEdgeToolsRemote]して、PWA が動作することを確認します。  |  
| [レスポンシブ デザイン][WikiResponsiveWebDesign] | CSS [grid][MDNCssGridLayout]、 [flexbox][MDNCssFlexibleBoxLayout]、css [grid][MDNCssGridLayout]と[flexbox][MDNCssFlexibleBoxLayout] 、[メディアクエリ][MDNMediaQueries]、[応答性][MDNResponsiveImages]の高い画像を使用して、ユーザーのデバイスに合わせて UX を調整します。  ブラウザーの[デバイスエミュレーションツール][DevToolsGuide|::ref1::|]を使ってローカルでテストするか、[リモートデバッグセッション][DevToolsProtocolClientsEdgeDevToolsPreview]をセットアップしてターゲットデバイスで直接テストします。  |  
| [ディープリンク][WikiDeepLinking] | サイトの各ページを一意の URL にルーティングして、既存のユーザーがソーシャルメディア共有を通じてさらに多くのユーザーとの共同作業を行うことができるようにします。  |  
| [ベスト プラクティス][Webhint] | アプリの効率、堅牢性、安全性、アクセシビリティを最適化するには、 [Webhint][Webhint]のようなコード品質ツールを使用します。  |  
| [Chromium PWA チェックリスト][WebDevGoodPwaChecklist] | Google ベースラインの PWA チェックリストに対して PWA のチェックボックスをオンにします。  |  

[Microsoft Store][MicrosoftDeveloperStore]アプリケーションとして PWA を有効にする場合は、「[プログレッシブ Web Apps (EdgeHTML)][PwaEdgehtmlMicrosoftStore] 」のドキュメントを参照してください。  
  

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
