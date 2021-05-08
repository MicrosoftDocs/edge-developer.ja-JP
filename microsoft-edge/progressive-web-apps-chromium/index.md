---
description: プログレッシブ Web アプリ (Chromium) は、アプリでネイティブWindows 10。  ここでは、Web 開発者として知る必要があるすべてについて説明します。
title: プログレッシブ Web Apps on Windows
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: pwa
keywords: プログレッシブ Web アプリ、PWA、Edge、JavaScript、Windows、UWP、Microsoft Store
ms.openlocfilehash: f1f5370af0710927f66c8231274fe307cb3ee2a4
ms.sourcegitcommit: 7f7922dbb6af87ecac1378d18359125770c5b8e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "11536810"
---
# <a name="progressive-web-apps-on-windows-overview"></a>プログレッシブ Web Apps on Windows概要  

[プログレッシブ Web Apps][MDNApps] \(PWAs\) は、プラットフォーム間の相互運用性を実現するオープン Web テクノロジへのアクセスを提供し、デバイス用にカスタマイズされたネイティブのアプリのようなエクスペリエンスをユーザーに提供します。  PWA は、サポート[][AListApartUnderstandingProgressiveEnhancement]プラットフォーム上のネイティブ アプリのように機能するために段階的に拡張される Web サイトです。  PWA では、Web アプリとネイティブ アプリの良いところが組み合わされています。  

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
        ### <a name="discoverablemdnpwaadvantagesdiscoverable"></a>[検出可能][MDNPwaAdvantagesDiscoverable]  
    :::column-end:::
    :::column:::
        ### <a name="installablemdnpwaadvantagesinstallable"></a>[Installable][MDNPwaAdvantagesInstallable]  
    :::column-end:::
    :::column:::
        ### <a name="re-engageablemdnpwaadvantagesreengageable"></a>[再エンゲージ可能][MDNPwaAdvantagesReEngageable]  
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        Web 検索結果とサポート アプリ ストアから  
    :::column-end:::
    :::column:::
        ホーム画面、スタート メニュー、タスク バーなどからピン留めして起動する  
    :::column-end:::
    :::column:::
        アプリがアクティブではない場合でも、プッシュ通知を送信する  
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
        ### <a name="network-independentmdnpwaadvantagesnetworkindependent"></a>[ネットワークに依存しない][MDNPwaAdvantagesNetworkIndependent]  
    :::column-end:::
    :::column:::
        ### <a name="progressivemdnpwaadvantagesprogressive"></a>[プログレッシブ][MDNPwaAdvantagesProgressive]  
    :::column-end:::
    :::column:::
        ### <a name="safemdnpwaadvantagessafe"></a>[セーフ][MDNPwaAdvantagesSafe]  
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        オフラインおよびネットワークの低い状態で動作する  
    :::column-end:::
    :::column:::
        デバイス機能を使用してエクスペリエンスをスケールアップ (または縮小) する  
    :::column-end:::
    :::column:::
        セキュリティで保護された HTTPS エンドポイントと他のユーザーセーフガードを提供する  
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
        ### <a name="responsivemdnpwaadvantagesresponsive"></a>[応答中][MDNPwaAdvantagesResponsive]  
    :::column-end:::
    :::column:::
        ### <a name="linkablemdnpwaadvantageslinkable"></a>[Linkable][MDNPwaAdvantagesLinkable]  
    :::column-end:::
    :::column:::
        &nbsp;  
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        ユーザーの画面サイズまたは向きと入力方法に合わせて調整します。  
    :::column-end:::
    :::column:::
        標準ハイパーリンクからの共有と起動  
    :::column-end:::
    :::column:::
        &nbsp;  
    :::column-end:::
:::row-end:::  

既存の Web サイトを既存の web サイトに構築し、PWAを強化します。  機能拡張には、プッシュ通知、アプリのような統合、オフラインサポートが含まれます。  引き続き、ユーザーが検索とリンク共有を通じてPWAを検出するために、オープン Web 上で対象ユーザーを構築します。  何より、アプリは Web サーバー コードを使用して更新されます。  

## <a name="pwas-on-microsoft-edge-chromium"></a>PWA on Microsoft Edge (Chromium)  

Web 標準 API を対象とするプログレッシブ Web アプリを構築する場合、アプリはプラットフォームやデバイス間で展開され、利用可能なデバイス固有の機能を利用できます。  \(Microsoft Edge Chromium\) の PWA は、Web サイトに次の利点を追加します。  

*   アプリは標準ベースの Web プラットフォーム上に構築されています。  
*   ユーザーがブラウザーから直接アプリをインストールできます。  
*   ユーザーがストア ベースの展開または登録なしでアプリをインストールできます。  
    
デスクトップ PWA は、\(Chromium\) を使用Microsoft Edgeプラットフォームでサポートされます。 Microsoft Edge \(Chromium\) は、Windows 7、Windows 10、および macOS で使用できます。  以下の利点が含まれています。  

*   ナビゲーション バーの [インストール] アイコンを使用して、ブラウザー **内からアプリ** を直接インストールできます。  
    
    :::image type="complex" source="./media/install-progressive-web-app-icon.png" alt-text="アプリのフライアウトとアイコンのインストール" lightbox="./media/install-progressive-web-app-icon.png":::
       アプリのフライアウトとアイコンのインストール  
    :::image-end:::  
    
*   [アプリ] メニューからアプリをインストール、実行 **、設定**  >  **することもできます**。  
    
    :::image type="complex" source="./media/app-menus.png" alt-text="[設定] の下のアプリ メニュー項目" lightbox="./media/app-menus.png":::
       [設定] の下のアプリ メニュー項目  
    :::image-end:::  
    
*   Web 通知は、ユーザー通知システムWindows統合されます。  
*   アプリをインストールしたブラウザー プロファイルを持つ共有 Cookie ストア  
*   証明書の検証、サイトのアクセス許可、追跡保護、ブラウザー拡張機能を含む **[設定** ] および [\] メニューを使用して他のブラウザー機能 `...` にアクセスする  
*   アプリのデバッグ[Microsoft Edge DevTools][DevtoolsProgressiveWebApps]へのフル アクセス  
    
> [!NOTE]
> 利点、今後の機能PWA短いデモの詳細については、「[ビルド 2020 PWA セッション」を参照してください][BuildVideo]。 

## <a name="requirements"></a>要件  

サーバーホスト型 web アプリPWA実行するには、次の最小要件を含める必要があります。  

:::row:::
   :::column span="1":::
      [HTTPS][WikiHttps]  
   :::column-end:::
   :::column span="2":::
      サーバーまたはアプリの通信にセキュリティで保護された接続を提供することで、ユーザーを保護します。  Service Workers および他PWAテクノロジは、セキュリティで保護された接続 \(またはデバッグ目的\から) で提供される Web リソース `localhost` でのみ動作します。  
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
      web アプリに関する重要な情報を説明する JSON ベースのメタデータ ファイルを提供し、Windows 10 や他のホスト プラットフォームが PWA ユーザーにインストール可能なネイティブ アプリのようなエクスペリエンスを提供します。  主要な情報には、アイコン、言語、URL エントリ ポイントが含まれます。 
   :::column-end:::
:::row-end:::  

最適な機能をPWA、アプリは次の要件も満たしている必要があります。  

:::row:::
   :::column span="1":::
      [ブラウザー間の互換性][MDNCrossBrowserTesting]  
   :::column-end:::
   :::column span="2":::
      さまざまなブラウザー PWA環境で[テストを行って、][MicrosoftDeveloperEdgeToolsRemote]アプリケーションが動作します。  
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
          
      ブラウザー[のデバイス エミュレーション][DevToolsGuideDeviceModeTestingOtherBrowsers]ツールを使用してローカルでテストするか、Windows または[Android][DevtoolsRemoteDebuggingIndex]でリモート デバッグ セッション[を][DevtoolsRemoteDebuggingWindows]作成して、ターゲット デバイスで直接テストします。
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
      [Chromium PWAチェックリスト][WebDevGoodPwaChecklist]  
   :::column-end:::
   :::column span="2":::
      Google 基準計画PWAチェックリストと比較して、PWA確認します。  
   :::column-end:::
:::row-end:::  

> [!NOTE]
> アプリにPWAするにはMicrosoft Storeのプログレッシブ Web [][MicrosoftDeveloperStore] [アプリに移動][PwaChromiumMicrosoftStore]Microsoft Store。  
  
## <a name="see-also"></a>関連項目  

*   [ミス バトリング PWA][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [プログレッシブ Web アプリのプログレッシブ ロードマップ][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [プログレッシブ Web アプリを使用したオフライン POST][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [PWAQ&A][AaronGustafsonNotebookPwaQa]  
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
[PwaChromiumMicrosoftStore]: ./microsoft-store.md "プログレッシブ Web アプリをアプリに発行Microsoft Store |Microsoft Docs"

[WindowsUWPControlsPatternTilesNotificationsWns]: /windows/uwp/controls-and-patterns/tiles-and-notifications-windows-push-notification-services--wns--overview.md "Windowsプッシュ Notification Services (WNS) の概要|Microsoft Docs"  
[WindowsUWPDesignDevicesDesigningTv]: /windows/uwp/design/devices/designing-for-tv.md "Xbox とテレビのデザイン|Microsoft Docs"  
[WindowsUWPDesignDevicesIndex]: /windows/uwp/design/devices/index.md "UWP デバイスの UI に関する考慮事項|Microsoft Docs"  
[WindowsUWPGetStartedGuide]: /windows/uwp/get-started/universal-application-platform-guide.md "ユニバーサル Windows プラットフォーム (UWP) アプリ|Microsoft Docs"  
[WindowsUWPLaunchResumeBackgroundTasks]: /windows/uwp/launch-resume/support-your-app-with-background-tasks.md "バックグラウンド タスクを使用してアプリをサポート|Microsoft Docs"  
[WindowsUWPPublishIndex]: /windows/uwp/publish/index.md "アプリWindowsゲームを公開|Microsoft Docs"  
[WindowsUWPPublishDeveloperAccount]: /windows/uwp/publish/opening-a-developer-account.md "開発者アカウントを開|Microsoft Docs"  

[WindowsBlogsWelcomingPWAsEdgeWindows]: https://blogs.windows.com/msedgedev/2018/02/06/welcoming-progressive-web-apps-edge-windows-10/#56z7mJwKsykfbR4I.97 "プログレッシブ Web アプリを使ったMicrosoft EdgeとWindows 10 - Windows ブログ"  
[MicrosoftDeveloperEdgePlatformStatusBackgroundSync]: https://developer.microsoft.com/microsoft-edge/platform/status/backgroundsyncapi "バックグラウンド同期 API - Microsoft Edgeの状態"  
[MicrosoftDeveloperEdgePlatformStatusWebAppManifest]: https://developer.microsoft.com/microsoft-edge/platform/status/webapplicationmanifest "Web アプリ マニフェスト - Microsoft Edgeの状態"  
[MicrosoftDeveloperEdgeToolsRemote]: https://developer.microsoft.com/microsoft-edge/tools/remote "インスタント テスト"  
[MicrosoftDeveloperWindowsMixedReality]: https://developer.microsoft.com/windows/mixed-reality "開発者向け Mixed Reality"  
[MicrosoftDeveloperWindowsSurfaceHub]: https://developer.microsoft.com/windows/surfacehub "Microsoft Surface Hub"  
[MicrosoftDeveloperStore]: https://developer.microsoft.com/store "Microsoft Developer Store"  
[MicrosoftEdge]: https://www.microsoft.com/edge "新しいブラウザー Microsoft Edgeダウンロード"  
[MicrosoftSupportWindowsFocusAssist]: https://support.microsoft.com/help/4026996/windows-10-turn-focus-assist-on-or-off "[フォーカス アシスト] をオンまたはオフにするWindows 10"  
[MicrosoftSupportWindowsNotificationSettings]: https://support.microsoft.com/help/4028678/windows-10-change-notification-settings "[通知の設定を変更する] Windows 10"  

[AaronGustafsonNotebookPwaQa]: https://www.aaron-gustafson.com/notebook/pwa-qa "PWAQ&A"  

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

[BuildVideo]: https://www.youtube.com/watch?v=y4p_QHZtMKM "PWAビデオ"  

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
