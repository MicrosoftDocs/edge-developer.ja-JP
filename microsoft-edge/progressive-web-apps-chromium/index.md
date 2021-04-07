---
description: プログレッシブ Web アプリ (クロム) は、Windows 10 でネイティブに実行されます。  ここでは、Web 開発者として知る必要があるすべてについて説明します。
title: Windows 上のプログレッシブ Web アプリ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/06/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: pwa
keywords: プログレッシブ Web アプリ、PWA、Edge、JavaScript、Windows、UWP、Microsoft Store
ms.openlocfilehash: be832ee5c0ad395dae7b4946c41da157ab5cd9ba
ms.sourcegitcommit: 146072bf606b84e5145a48333abf9c6b892a12d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2021
ms.locfileid: "11480189"
---
# <a name="progressive-web-apps-on-windows-overview"></a>Windows 上のプログレッシブ Web アプリの概要  

[プログレッシブ Web Apps][MDNApps] \(PWAs\) は、プラットフォーム間の相互運用性を実現するオープン Web テクノロジへのアクセスを提供し、デバイス用にカスタマイズされたネイティブのアプリのようなエクスペリエンスをユーザーに提供します。  PWA は、サポート[][AListApartUnderstandingProgressiveEnhancement]プラットフォーム上のネイティブ アプリのように機能するために段階的に拡張される Web サイトです。  PWA では、Web アプリとネイティブ アプリの良いところが組み合わされています。  

:::row:::
    :::column:::
        :::image type="icon" source="./media/i_search-small.png":::
        ### <a name="discoverablemdnpwaadvantagesdiscoverable"></a>[検出可能][MDNPwaAdvantagesDiscoverable]
        Web 検索結果とサポート アプリ ストアから
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_package-small.png":::
        ### <a name="installablemdnpwaadvantagesinstallable"></a>[Installable][MDNPwaAdvantagesInstallable]
        ホーム画面、スタート メニュー、タスク バーなどからピン留めして起動する
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_push-notification-small.png":::
        ### <a name="re-engageablemdnpwaadvantagesreengageable"></a>[再エンゲージ可能][MDNPwaAdvantagesReEngageable]
        アプリがアクティブではない場合でも、プッシュ通知を送信する
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        :::image type="icon" source="./media/i_offline-small.png":::
        ### <a name="network-independentmdnpwaadvantagesnetworkindependent"></a>[ネットワークに依存しない][MDNPwaAdvantagesNetworkIndependent]
        オフラインおよびネットワークの低い状態で動作する
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_progressive-small.png":::
        ### <a name="progressivemdnpwaadvantagesprogressive"></a>[プログレッシブ][MDNPwaAdvantagesProgressive]
        デバイス機能を使用してエクスペリエンスをスケールアップ (または縮小) する
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_security-small.png":::
        ### <a name="safemdnpwaadvantagessafe"></a>[セーフ][MDNPwaAdvantagesSafe]
        セキュリティで保護された HTTPS エンドポイントと他のユーザーセーフガードを提供する
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        :::image type="icon" source="./media/i_responsive-small.png":::
        ### <a name="responsivemdnpwaadvantagesresponsive"></a>[応答中][MDNPwaAdvantagesResponsive]
        ユーザーの画面サイズまたは向きと入力方法に合わせて調整します。
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_link-small.png":::
        ### <a name="linkablemdnpwaadvantageslinkable"></a>[Linkable][MDNPwaAdvantagesLinkable]
        標準ハイパーリンクからの共有と起動
    :::column-end:::
    :::column:::
        &nbsp;  
    :::column-end:::
:::row-end:::  


既存の Web サイトを PWA に \(または convert\) ビルドして、ユーザーとのエンゲージメントを強化します。  機能拡張には、プッシュ通知、アプリのような統合、オフラインサポートが含まれます。  引き続き、ユーザーが検索とリンク共有を通じて PWA を検出するためのオープン Web 上で対象ユーザーを構築します。  何より、アプリは Web サーバー コードを使用して更新されます。  

## <a name="pwas-on-microsoft-edge-chromium"></a>Microsoft Edge の PWA (クロム)  

Web 標準 API を対象とするプログレッシブ Web アプリを構築する場合、アプリはプラットフォームやデバイス間で展開され、利用可能なデバイス固有の機能を利用できます。  Microsoft Edge \(Chromium\) の PWA は、Web サイトに次の利点を追加します。  

*   アプリは標準ベースの Web プラットフォーム上に構築されています。  
*   ユーザーがブラウザーから直接アプリをインストールできます。  
*   ユーザーがストア ベースの展開または登録なしでアプリをインストールできます。  
    
デスクトップ PWA は、Microsoft Edge \(Chromium\) が利用可能なプラットフォームでサポートされています。 Microsoft Edge \(Chromium\) は、Windows 7、Windows 10、および macOS で利用できます。  以下の利点が含まれています。  

*   ナビゲーション バーの [インストール] アイコンを使用して、ブラウザー **内からアプリ** を直接インストールできます。  
    
    :::image type="complex" source="./media/install-progressive-web-app-icon.png" alt-text="アプリのフライアウトとアイコンのインストール" lightbox="./media/install-progressive-web-app-icon.png":::
       アプリのフライアウトとアイコンのインストール  
    :::image-end:::  
    
*   [設定アプリ] メニューからアプリをインストール、実行、**** および  >  **管理**することもできます。  
    
    :::image type="complex" source="./media/app-menus.png" alt-text="[設定] の下のアプリ メニュー項目" lightbox="./media/app-menus.png":::
       [設定] の下のアプリ メニュー項目  
    :::image-end:::  
    
*   Web 通知は Windows 通知システムに統合されています  
*   アプリをインストールしたブラウザー プロファイルを持つ共有 Cookie ストア  
*   証明書の検証、サイトのアクセス許可、追跡保護、ブラウザー拡張機能を含む **[設定** ] および [\] メニューを使用して他のブラウザー機能 `...` にアクセスする  
*   アプリをデバッグ [する Microsoft Edge DevTools][DevtoolsProgressiveWebApps] へのフル アクセス  
    
> [!NOTE]
> PWA の利点、今後の機能、および短いデモの詳細については、「ビルド [2020 PWA セッション」に移動します][BuildVideo]。 

## <a name="requirements"></a>要件  

PWA として実行するには、サーバーホスト型 Web アプリに以下の最小要件を含める必要があります。  

:::row:::
   :::column span="1":::
      [HTTPS][WikiHttps]  
   :::column-end:::
   :::column span="2":::
      サーバーまたはアプリの通信にセキュリティで保護された接続を提供することで、ユーザーを保護します。  Service Workers および他の PWA テクノロジは、セキュリティで保護された接続 \(またはデバッグ目的\) を使用して提供される Web リソースでのみ `localhost` 動作します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [サービス ワーカー][MDNServiceWorkerApi]  
   :::column-end:::
   :::column span="2":::
      サービス ワーカー スレッドを使用して、サーバーとクライアント アプリの間のネットワーク プロキシとして機能します。  Service Worker スレッドは、オフライン サポート、リソース キャッシュ、プッシュ通知、バックグラウンド データ同期、およびページ読み込みパフォーマンスの最適化を提供します。    
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [Web アプリ マニフェスト][MDNWebAppManifest]  
   :::column-end:::
   :::column span="2":::
      Web アプリに関する重要な情報を説明する JSON ベースのメタデータ ファイルを提供し、Windows 10 や他のホスト プラットフォームが PWA ユーザーにインストール可能なネイティブ アプリのようなエクスペリエンスを提供します。  主要な情報には、アイコン、言語、URL エントリ ポイントが含まれます。 
   :::column-end:::
:::row-end:::  

PWA を高くするには、アプリが次の要件も満たしている必要があります。  

:::row:::
   :::column span="1":::
      [ブラウザー間の互換性][MDNCrossBrowserTesting]  
   :::column-end:::
   :::column span="2":::
      異なるブラウザーと環境でテスト [を行って][MicrosoftDeveloperEdgeToolsRemote] 、PWA が動作を確認します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [レスポンシブ デザイン][WikiResponsiveWebDesign]  
   :::column-end:::
   :::column span="2":::
      流動的なレイアウトと柔軟な画像を使用します。  レスポンシブ デザインには、ユーザーのデバイスに UX を適合する次の要素が含まれています。  
      
      *   CSS [グリッド][MDNCssGridLayout]  
      *   [flexbox][MDNCssFlexibleBoxLayout]  
      *   CSS [グリッドと][MDNCssGridLayout] [flexbox][MDNCssFlexibleBoxLayout]  
      *   [メディア クエリ][MDNMediaQueries]  
      *   [レスポンシブ イメージ][MDNResponsiveImages]  
      
      ブラウザー [のデバイス エミュレーション][DevToolsGuideDeviceModeTestingOtherBrowsers] ツールを使用してローカルでテストするか [、Windows][DevtoolsRemoteDebuggingWindows] または [Android][DevtoolsRemoteDebuggingIndex] でリモート デバッグ セッションを作成して、ターゲット デバイスで直接テストします。
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [ディープ リンク][WikiDeepLinking]  
   :::column-end:::
   :::column span="2":::
      サイトの各ページを一意の URL にルーティングし、既存のユーザーがソーシャル メディア共有を通じてより広範なユーザーを引き付けるのに役立ちます。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [検証とテストのプラクティス][Webhint]  
   :::column-end:::
   :::column span="2":::
      [Webhint linter][Webhint]のようなコード品質ツールを使用して、アプリの効率、堅牢性、安全性、アクセシビリティを最適化します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [クロム PWA チェックリスト][WebDevGoodPwaChecklist]  
   :::column-end:::
   :::column span="2":::
      Google ベースライン PWA チェックリストに対して PWA を確認します。  
   :::column-end:::
:::row-end:::  

> [!NOTE]
> PWA を Microsoft Store アプリに変更するには [、Microsoft][MicrosoftDeveloperStore] [ストアのプログレッシブ Web アプリに移動します][PwaChromiumMicrosoftStore]。  
  
## <a name="see-also"></a>関連項目  

*   [ミス バトリング PWA][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [プログレッシブ Web アプリのプログレッシブ ロードマップ][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [プログレッシブ Web アプリを使用したオフライン POST][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [PWA Q&A][AaronGustafsonNotebookPwaQa]  
*   [Web でのベット][JoretegBlogBettingWeb]  
*   [プログレッシブ Web アプリの名前付け][Fberriman20170626NamingProgressiveWebApps]  
*   [フレームワークを使用しないプログレッシブ Web アプリの設計と構築 (パート 1)][Smashingmagazine201907ProgressiveWebAppFrameworkPart1]  
*   [フレームワークを使用しないプログレッシブ Web アプリの設計と構築 (パート 2)][Smashingmagazine201907ProgressiveWebAppFrameworkPart2]  
*   [フレームワークを使用しないプログレッシブ Web アプリの設計と構築 (パート 3)][Smashingmagazine201907ProgressiveWebAppFrameworkPart3]  
    
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
