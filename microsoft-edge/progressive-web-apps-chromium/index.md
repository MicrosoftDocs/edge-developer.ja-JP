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
# Windows のプログレッシブ Web アプリ  

[プログレッシブ Web アプリ][MDNApps] \ (pwas \) は、クロスプラットフォームの相互運用性を実現するために、オープン web テクノロジへのアクセスを提供し、ユーザーにデバイスに合わせてカスタマイズされたネイティブのアプリのようなエクスペリエンスを提供します。  PWAs は、サポートしているプラットフォームでのネイティブアプリのように機能するために [段階的に拡張][AListApartUnderstandingProgressiveEnhancement] された web サイトです。  PWA では、Web アプリとネイティブ アプリの良いところが組み合わされています。  

:::row:::
    :::column:::
        :::image type="icon" source="./media/i_search.png":::
        ### [見つけ][MDNPwaAdvantagesDiscoverable]
        Web 検索結果とサポートされているアプリストアから
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_package.png":::
        ### [Installable][MDNPwaAdvantagesInstallable]
        ホーム画面、[スタート] メニュー、タスクバーなどのピン留めと起動
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_push-notification.png":::
        ### [再 engageable][MDNPwaAdvantagesReEngageable]
        アプリがアクティブでない場合でも、プッシュ通知を送信する
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        :::image type="icon" source="./media/i_offline.png":::
        ### [ネットワークに依存しない][MDNPwaAdvantagesNetworkIndependent]
        オフラインおよび低ネットワークの状態で動作する
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_progressive.png":::
        ### [的][MDNPwaAdvantagesProgressive]
        デバイス機能を使用したエクスペリエンスのスケールアップ (またはダウン)
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_security.png":::
        ### [問題][MDNPwaAdvantagesSafe]
        セキュリティで保護された HTTPS エンドポイントとその他のユーザーの保護機能を提供する
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        :::image type="icon" source="./media/i_responsive.png":::
        ### [応答中][MDNPwaAdvantagesResponsive]
        ユーザーの画面サイズまたは印刷の向きと入力方式に合わせて調整する
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_link.png":::
        ### [Linkable][MDNPwaAdvantagesLinkable]
        標準ハイパーリンクを共有して起動する
    :::column-end:::
    :::column:::
        &nbsp;  
    :::column-end:::
:::row-end:::  


ユーザーによる契約を強化するために、既存の web サイトを PWA に構築 (または) します。  強化された機能には、プッシュ通知、アプリのような統合、オフラインサポートなどがあります。  ユーザーが検索とリンク共有を通じて PWA を見つけられるように、開いている web 上の参加者の作成を続けます。  いずれの場合も、web サーバーコードを使用してアプリが更新されます。  

## Microsoft Edge で PWAs (Chromium)  

Web 標準 Api をターゲットとするプログレッシブ Web アプリを構築すると、アプリはプラットフォームとデバイスの間で展開される可能性があり、デバイス固有の機能を利用できるようになります。  Microsoft Edge では、次の利点を web サイトに追加します (Chromium)。  

*   アプリは標準ベースの web プラットフォーム上に構築されています。  
*   ユーザーがブラウザーから直接アプリをインストールできるようにします。  
*   ストアベースの展開または登録なしで、ユーザーがアプリをインストールできるようにします。  
    
Desktop PWAs は、Microsoft Edge \ (Chromium \) のいずれかのプラットフォームでサポートされています。 Microsoft Edge \ (Chromium \) は、Windows 7、Windows 10、macOS で利用できます。  次の利点が含まれています。  

*   アプリケーションは、ナビゲーションバーの **インストール** アイコンを使ってブラウザー内から直接インストールできます。  
    
    :::image type="complex" source="./media/install_pwa_icon.png" alt-text="アプリケーションのインストールのポップアップとアイコン" lightbox="./media/install_pwa_icon.png":::
       アプリケーションのインストールのポップアップとアイコン  
    :::image-end:::  
    
*   アプリケーションは、[**設定**  >  ]**アプリ**メニューからインストール、実行、管理することもできます。  
    
    :::image type="complex" source="./media/app_menus.png" alt-text="アプリケーションのインストールのポップアップとアイコン" lightbox="./media/app_menus.png":::
       [設定] の [アプリケーション] メニュー項目  
    :::image-end:::  
    
*   Web 通知は Windows notification システムに統合されます。  
*   アプリをインストールしたブラウザープロファイルの共有 cookie ストア  
*   **設定およびその**他の \ (\) メニューを使用して、 `...` 証明書の検証、サイトのアクセス許可、追跡保護、ブラウザーの拡張機能など、他のブラウザー機能にアクセスする  
*   アプリをデバッグするための [Microsoft Edge DevTools][DevtoolsProgressiveWebApps] へのフルアクセス  
    
> [!IMPORTANT]
> 特に、JavaScript を使って WinRT API 要求を行う Windows 10 用に PWAs をカスタマイズするには、 [EDGEHTML PWA 機能に固有のドキュメント][PwaEdgehtmlIndex]に移動します。  Windows 10 での PWA のテストと Microsoft Store での配布について説明します。  

> [!NOTE]
> PWA の利点、今後の機能、および簡単なデモの詳細については、「 [ビルド 2020 PWA セッション][BuildVideo]」を参照してください。 

## 要件  

PWA として実行するには、サーバーでホストされる web アプリに次の最小要件が含まれている必要があります。  

:::row:::
   :::column span="1":::
      [HTTPS][WikiHttps]  
   :::column-end:::
   :::column span="2":::
      サーバーまたはアプリの通信にセキュリティで保護された接続を提供して、ユーザーを保護します。  サービス作業者やその他の PWA テクノロジは、セキュリティで保護された接続を経由して提供される web リソース (または `localhost` デバッグ目的でのみ) と動作します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [サービス ワーカー][MDNServiceWorkerApi]  
   :::column-end:::
   :::column span="2":::
      サービスワーカースレッドを使って、サーバーとクライアントアプリの間でネットワークプロキシとして機能します。  サービスワーカースレッドは、オフラインサポート、リソースキャッシュ、プッシュ通知、バックグラウンドデータ同期、ページ読み込みパフォーマンス最適化を提供します。    
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [Web アプリマニフェスト][MDNWebAppManifest]  
   :::column-end:::
   :::column span="2":::
      Web アプリに関する主要な情報を示す JSON ベースのメタデータファイルを提供します。これにより、Windows 10 やその他のホストプラットフォームで、インストール可能なネイティブアプリのようなエクスペリエンスを備えた PWA ユーザーが提供されます。  重要な情報には、アイコン、言語、URL エントリポイントが含まれます。 
   :::column-end:::
:::row-end:::  

また、アプリは次の要件を満たしている必要があります。  

:::row:::
   :::column span="1":::
      [ブラウザー間の互換性][MDNCrossBrowserTesting]  
   :::column-end:::
   :::column span="2":::
      さまざまなブラウザーと環境で [テスト][MicrosoftDeveloperEdgeToolsRemote] して、PWA が動作することを確認します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [レスポンシブ デザイン][WikiResponsiveWebDesign]  
   :::column-end:::
   :::column span="2":::
      流動的なレイアウトと柔軟な画像を採用しています。  応答性の高いデザインには、ユーザーのデバイスに UX を適応させる次の要素が含まれています。  
      
      *   CSS [グリッド][MDNCssGridLayout]  
      *   [flexbox][MDNCssFlexibleBoxLayout]  
      *   CSS [grid][MDNCssGridLayout] と [flexbox][MDNCssFlexibleBoxLayout]  
      *   [メディアクエリ][MDNMediaQueries]  
      *   [応答性の高い画像][MDNResponsiveImages]  
      
      ブラウザーの [デバイスエミュレーションツール][DevToolsGuide|::ref1::|] を使ってローカルテストを行うか、 [リモートデバッグセッション][DevToolsProtocolClientsEdgeDevToolsPreview] を作成してターゲットデバイスで直接テストします。
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [ディープリンク][WikiDeepLinking]  
   :::column-end:::
   :::column span="2":::
      サイトの各ページを一意の URL にルーティングして、既存のユーザーがソーシャルメディア共有を通じてさらに多くのユーザーとの共同作業を行うことができるようにします。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [検証とテストのプラクティス][Webhint]  
   :::column-end:::
   :::column span="2":::
      アプリの効率、堅牢性、安全性、アクセシビリティを最適化するために、 [Webhint][Webhint] などのコード品質ツールを使用します。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [Chromium PWA チェックリスト][WebDevGoodPwaChecklist]  
   :::column-end:::
   :::column span="2":::
      Google baseline の PWA チェックリストに対して PWA を確認します。  
   :::column-end:::
:::row-end:::  

> [!NOTE]
> [Microsoft][MicrosoftDeveloperStore] store アプリケーションとして PWA を有効にするには、 [Microsoft Store のプログレッシブ Web Apps (EdgeHTML)][PwaEdgehtmlMicrosoftStore]に移動します。  
  
## 関連項目  

*   [神話の場合][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [プログレッシブ Web アプリのためのプログレッシブロードマップ][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [プログレッシブ Web アプリでのオフライン投稿][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [PWA&][AaronGustafsonNotebookPwaQa]  
*   [Web でのお賭け][JoretegBlogBettingWeb]  
*   [プログレッシブ Web アプリに名前を付ける][Fberriman20170626NamingProgressiveWebApps]  
*   [フレームワークなしでプログレッシブ Web アプリケーションを設計して構築する (パート 1)][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]  
*   [フレームワークを使わないプログレッシブ Web アプリケーションの設計と構築 (パート 2)][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]  
*   [フレームワークを使わないプログレッシブ Web アプリケーションの設計と構築 (パート 3)][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]  
    
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
