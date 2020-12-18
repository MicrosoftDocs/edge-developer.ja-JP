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
# Windows 上の段階的な Web アプリの概要  

[段階的な Web アプリ][MDNApps] \(PWA\) を使用すると、オープン Web テクノロジにアクセスしてクロスプラットフォーム相互運用性を実現し、ユーザーのデバイス用にカスタマイズされたネイティブなアプリのようなエクスペリエンスをユーザーに提供できます。  PAS は、サポート[][AListApartUnderstandingProgressiveEnhancement]プラットフォーム上のネイティブ アプリのように機能するために徐々に拡張された Web サイトです。  PWA では、Web アプリとネイティブ アプリの良いところが組み合わされています。  

:::row:::
    :::column:::
        :::image type="icon" source="./media/i_search.png":::
        ### [検出可能][MDNPwaAdvantagesDiscoverable]
        Web 検索結果とサポート アプリ ストアから
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_package.png":::
        ### [Installable][MDNPwaAdvantagesInstallable]
        ホーム画面、スタート メニュー、タスク バーなどからピン留めして起動する
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_push-notification.png":::
        ### [再エンゲージ可能][MDNPwaAdvantagesReEngageable]
        アプリがアクティブではない場合でもプッシュ通知を送信する
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        :::image type="icon" source="./media/i_offline.png":::
        ### [ネットワークに依存しない][MDNPwaAdvantagesNetworkIndependent]
        オフラインで、ネットワークの状態が低い場合に動作します。
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_progressive.png":::
        ### [段階的][MDNPwaAdvantagesProgressive]
        デバイス機能を使用してエクスペリエンスをスケール アップ (または縮小) する
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_security.png":::
        ### [安全][MDNPwaAdvantagesSafe]
        セキュリティで保護された HTTPS エンドポイントと他のユーザー保護機能を提供します
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        :::image type="icon" source="./media/i_responsive.png":::
        ### [応答中][MDNPwaAdvantagesResponsive]
        ユーザーの画面サイズや向き、入力方法に合わせて調整します。
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_link.png":::
        ### [リンク可能][MDNPwaAdvantagesLinkable]
        標準ハイパーリンクを共有して起動する
    :::column-end:::
    :::column:::
        &nbsp;  
    :::column-end:::
:::row-end:::  


既存の Web サイトを PWA に \(または変換\) して、ユーザーとのエンゲージメントを強化します。  機能拡張には、プッシュ通知、アプリのような統合、オフライン サポートが含まれます。  引き続きオープン Web で対象ユーザーを作成し、ユーザーが検索とリンク共有を通じて PWA を検出します。  何より、アプリは Web サーバー コードを使用して更新されます。  

## Microsoft Edge 上の PAS (Chromium)  

Web 標準 API をターゲットとする段階的な Web アプリを構築する場合、アプリケーションを複数のプラットフォームやデバイスに展開し、利用可能なデバイス固有の機能を利用できます。  Microsoft Edge \(Chromium\) の PAS は、Web サイトに次の利点を追加します。  

*   アプリは、標準ベースの Web プラットフォーム上に構築されています。  
*   ユーザーがブラウザーから直接アプリをインストールできます。  
*   ユーザーがストア ベースの展開や登録を行わずにアプリをインストールできます。  
    
デスクトップ PAS は、Microsoft Edge \(Chromium\) が利用可能な任意のプラットフォームでサポートされています。 Microsoft Edge \(Chromium\) は、Windows 7、Windows 10、および macOS で利用できます。  次の利点が含まれています。  

*   アプリケーションは、ナビゲーション バーの [インストール]**** アイコンを使用して、ブラウザー内から直接インストールできます。  
    
    :::image type="complex" source="./media/install_pwa_icon.png" alt-text="アプリケーション のフライアウトとアイコンのインストール" lightbox="./media/install_pwa_icon.png":::
       アプリケーション のフライアウトとアイコンのインストール  
    :::image-end:::  
    
*   アプリケーションは、[設定アプリ] メニューからインストール、実行、**および**  >  **管理することもできます**。  
    
    :::image type="complex" source="./media/app_menus.png" alt-text="[設定] の [アプリケーション] メニュー項目" lightbox="./media/app_menus.png":::
       [設定] の [アプリケーション] メニュー項目  
    :::image-end:::  
    
*   Web 通知は Windows 通知システムに統合されます。  
*   アプリをインストールしたブラウザー プロファイルを含む共有 Cookie ストア  
*   証明書の検証、サイトのアクセス**** 許可、追跡保護、ブラウザー拡張機能を含む [設定] メニューなどの \( \) メニューを使用した他のブラウザー機能 `...` へのアクセス  
*   アプリをデバッグ [するために Microsoft Edge DevTools][DevtoolsProgressiveWebApps] へのフル アクセス  
    
> [!IMPORTANT]
> JavaScript を使用して WinRT API 要求を行う Windows 10 専用の PWA を調整するには、[EdgeHTML PWA 機能に固有のドキュメント][PwaEdgehtmlIndex] に移動します。  Windows 10 で PWA をテストし、Microsoft Store で配布する方法について説明します。  

> [!NOTE]
> PWA の利点、今後の機能、および短いデモの詳細については、ビルド [2020 PWA セッションに移動します][BuildVideo]。 

## 要件  

PWA として実行するには、サーバーホスト型 Web アプリに次の最小要件を含める必要があります。  

:::row:::
   :::column span="1":::
      [HTTPS][WikiHttps]  
   :::column-end:::
   :::column span="2":::
      サーバーまたはアプリの通信にセキュリティで保護された接続を提供することで、ユーザーを保護します。  サービス ワーカーおよび他の PWA テクノロジは、セキュリティで保護された接続 \(またはデバッグ目的\ から) 提供される Web リソースでのみ `localhost` 動作します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [サービス ワーカー][MDNServiceWorkerApi]  
   :::column-end:::
   :::column span="2":::
      サービス ワーカー スレッドを使用して、サーバーとクライアント アプリの間のネットワーク プロキシとして機能します。  サービス ワーカー スレッドは、オフライン サポート、リソース キャッシュ、プッシュ通知、バックグラウンド データ同期、およびページ読み込みパフォーマンスの最適化を提供します。    
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [Web アプリ マニフェスト][MDNWebAppManifest]  
   :::column-end:::
   :::column span="2":::
      Web アプリに関する重要な情報を説明する JSON ベースのメタデータ ファイルを提供し、Windows 10 および他のホスト プラットフォームが PWA ユーザーにインストール可能でネイティブなアプリのようなエクスペリエンスを提供します。  主要な情報には、アイコン、言語、および URL エントリ ポイントが含まれます。 
   :::column-end:::
:::row-end:::  

PWA を高くするには、アプリが次の要件も満たしている必要があります。  

:::row:::
   :::column span="1":::
      [ブラウザー間の互換性][MDNCrossBrowserTesting]  
   :::column-end:::
   :::column span="2":::
      さまざまなブラウザーと環境でテスト [することで、PWA][MicrosoftDeveloperEdgeToolsRemote] が動作する必要があります。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [レスポンシブ デザイン][WikiResponsiveWebDesign]  
   :::column-end:::
   :::column span="2":::
      柔軟なレイアウトと柔軟な画像を使用します。  レスポンシブ デザインには、ユーザーのデバイスに UX を適合する次の要素が含まれています。  
      
      *   CSS [グリッド][MDNCssGridLayout]  
      *   [flexbox][MDNCssFlexibleBoxLayout]  
      *   CSS [グリッド][MDNCssGridLayout] と [flexbox][MDNCssFlexibleBoxLayout]  
      *   [メディア クエリ][MDNMediaQueries]  
      *   [レスポンシブ イメージ][MDNResponsiveImages]  
      
      ブラウザー [のデバイス エミュレーション][DevToolsGuideDeviceModeTestingOtherBrowsers] ツールを使用してローカルでテストするか [、Windows][DevtoolsRemoteDebuggingWindows] または [Android][DevtoolsRemoteDebuggingIndex] でリモート デバッグ セッションを作成し、ターゲット デバイスで直接テストします。
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [ディープ リンク][WikiDeepLinking]  
   :::column-end:::
   :::column span="2":::
      サイトの各ページを一意の URL にルーティングし、既存のユーザーがソーシャル メディア共有を通じてより広い対象ユーザーを引き付けるのに役立ちます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [検証とテストのプラクティス][Webhint]  
   :::column-end:::
   :::column span="2":::
      [Webhint][Webhint] linter のようなコード品質ツールを使用して、アプリの効率、堅牢性、安全性、アクセシビリティを最適化します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [Chromium PWA チェックリスト][WebDevGoodPwaChecklist]  
   :::column-end:::
   :::column span="2":::
      Google ベースライン PWA チェックリストに対して PWA を検証します。  
   :::column-end:::
:::row-end:::  

> [!NOTE]
> PWA を Microsoft [Store][MicrosoftDeveloperStore] アプリケーションに変換するには、Microsoft Store の [段階的な Web アプリ (EdgeHTML)][PwaEdgehtmlMicrosoftStore] に移動します。  
  
## 関連項目  

*   [1000,000][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [段階的な Web アプリの段階的なロードマップ][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [段階的な Web アプリを使用したオフライン POS][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [PWA Q&A][AaronGustafsonNotebookPwaQa]  
*   [Web 上で楽しむ][JoretegBlogBettingWeb]  
*   [段階的な Web アプリの名前付け][Fberriman20170626NamingProgressiveWebApps]  
*   [フレームワークを使用しない段階的な Web アプリケーションの設計と構築 (パート 1)][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]  
*   [フレームワークを使用しない段階的な Web アプリケーションの設計と構築 (パート 2)][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]  
*   [フレームワークを使用しない段階的な Web アプリケーションの設計と構築 (パート 3)][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]  
    
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
