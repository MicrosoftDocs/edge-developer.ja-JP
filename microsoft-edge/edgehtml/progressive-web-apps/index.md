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
# Windows でのプログレッシブ Web アプリ (EdgeHTML)  

[段階的な Web アプリ][MDNApps]\(または単に PAS\) を使用すると、オープン Web テクノロジを使用してクロスプラットフォーム相互運用性を実現し、ユーザーのデバイス用にカスタマイズされたネイティブのアプリのようなエクスペリエンスをユーザーに提供する必要が生じます。  PAS は、サポート プラットフォーム上のネイティブ[][AListApartUnderstandingProgressiveEnhancement]アプリのように機能するために徐々に拡張された Web サイトにすすむためです。  PWA では、Web アプリとネイティブ アプリの良いところが組み合わされています。  

:::row:::
    :::column:::
        ![検出可能なアイコン][ImageISearch]
        ### [検出可能][MDNPwaAdvantagesDiscoverable]
        Web 検索結果とサポート アプリ ストアから
    :::column-end:::
    :::column:::
        ![インストール可能なアイコン][ImageIPackage]
        ### [Installable][MDNPwaAdvantagesInstallable]
        ホーム画面からピン留めして起動する  
    :::column-end:::
    :::column:::
        ![再エンゲージ可能なアイコン][ImageIPushNotification]
        ### [再エンゲージ可能][MDNPwaAdvantagesReEngageable]
        アプリがアクティブではない場合でもプッシュ通知を送信する  
    :::column-end:::
    :::column:::
        ![ネットワークに依存しないアイコン][ImageIOffline]
        ### [ネットワークに依存しない][MDNPwaAdvantagesNetworkIndependent]
        オフラインで、ネットワークの状態が低い場合に動作します。  
    :::column-end:::
:::row-end:::
:::row:::
    :::column:::
        ![段階的なアイコン][ImageIProgressive]
        ### [段階的][MDNPwaAdvantagesProgressive]
        デバイスの機能を使用してエクスペリエンスを拡大縮小 \(アップまたはダウン\) する  
    :::column-end:::
    :::column:::
        ![安全なアイコン][ImageISecurity]
        ### [安全][MDNPwaAdvantagesSafe]
        セキュリティで保護された HTTPS エンドポイントと他のユーザー保護機能を提供します  
    :::column-end:::
    :::column:::
        ![レスポンシブ アイコン][ImageIResponsive]
        ### [応答中][MDNPwaAdvantagesResponsive]
        ユーザーの画面サイズ/向き、入力方法に合わせて調整します。  
    :::column-end:::
    :::column:::
        ![リンク可能なアイコン][ImageILink]
        ### [リンク可能][MDNPwaAdvantagesLinkable]
        標準ハイパーリンクを共有して起動する  
    :::column-end:::
:::row-end:::

既存のサイトを構築または PWA に変換することで、プッシュ通知とオフライン サポートにより、既存の対象ユーザーのエンゲージメントを向上できます。  同時に、ユーザーが検索とリンク共有を通じて PWA を検出すると、開いている Web で引き続き対象ユーザーを構築できます。  

## Windows 10 の PAS (EdgeHTML)  

> [!NOTE]
> EdgeHTML から Microsoft Edge (Chromium) に移行した場合、PAS で使用される基礎となる Web プラットフォームは同じではありません。  Edge (Chromium) PAS は、ブラウザーからインストールされ、ブラウザー内で実行されます。  Edge (EdgeHTML) PAS はユニバーサル Windows プラットフォーム (UWP) アプリケーションとして実行され、以前の EdgeHTML Web プラットフォームを使用します。  PWA に Windows 10 API アクセスが必要な場合は、この EdgeHTML ドキュメントが役立っています。  Windows 固有の API にアクセスせずにクロス プラットフォーム サポートを目標にしている場合は [、Microsoft Edge (Chromium) PWA ドキュメントにアクセスしてください][PwaChromiumIndex]。  

Windows 10 を活用する段階的な Web アプリを構築すると [、Microsoft Store][MicrosoftDeveloperStore]を通じて PWA を配布できます。Windows 10 インストール ベースの 6 億人以上のアクティブな月次ユーザーが、アプリの対象ユーザーの可能性を高めています。  この方法で開発されたアプリケーションは、 [ユニバーサル Windows プラットフォーム][WindowsUWPGetStartedGuide] アプリとして実行され、WinRT API へのアクセスのようなネイティブな機能を持ちます。  WinRT API を使用する場合、コードをレンダリングする Web プラットフォームは EdgeHTML なので、Windows 固有の API を呼び出す前に機能検出を使用して、PWA が Microsoft Edge \(Chromium\) PWA が使用可能なプラットフォーム間で PWA を確実に実行できます。  

[ここでは、Web][PwaEdgehtmlGetStarted] アプリを PWA \(EdgeHTML\) に変換し、Windows 10 でテストし、Microsoft Store で配布する方法について説明します。  

## 要件  

PWA として実行するには、サーバーホスト型 Web アプリが少なくとも次の要件を満たしている必要があります。  

*   [HTTPS][WikiHttps]。  サーバー/アプリ通信用のセキュリティで保護された接続を提供することで、ユーザーを保護します。  サービス ワーカーおよび他の PWA テクノロジは、セキュリティで保護された接続 \(またはデバッグ目的\ から) 提供される Web リソースでのみ `localhost` 動作します。  
  
*   [サービス ワーカー][MDNServiceWorkerApi]。  オフライン サポート、リソース キャッシュ、プッシュ通知、バックグラウンド データ同期、ページ読み込みパフォーマンスの最適化を提供するために、サービス ワーカー スレッドを使用して、サーバーとクライアント アプリ間のネットワーク プロキシとして機能します。  

*   [Web アプリ マニフェスト][MDNWebAppManifest]。  Windows 10 や他のホスト プラットフォームが PWA ユーザーにインストール可能でネイティブなアプリのようなエクスペリエンスを提供するために、Web アプリ \(アイコン、言語、URL エントリ ポイント\) に関する重要な情報を説明する JSON ベースのメタデータ ファイルを提供します。  Web アプリ マニフェストにサイトを関連付け、Bing インデックス サービスを通じて [Microsoft Store][PwaEdgehtmlMicrosoftStoreImportingBing] に自動的に含める資格を得る。  

PWA を高くするには、アプリには以下も必要です。  

*   [ブラウザー間の互換性][MDNCrossBrowserTesting]。  さまざまなブラウザーと環境でテスト [することで、PWA][MicrosoftDeveloperEdgeToolsRemote] が動作する必要があります。  Windows 10 では、Microsoft Edge ブラウザーと完全な PWA エクスペリエンスの両方で、必ずアプリをテストしてください。  
  
*   [レスポンシブ デザイン][WikiResponsiveWebDesign]。  [CSS][MDNCssGridLayout]グリッドや[flexbox、][MDNCssFlexibleBoxLayout]メディア クエリ、および [レスポンシブ[][MDNMediaQueries]イメージ[MDNResponsiveImages]]で柔軟なレイアウトと柔軟な画像を使用して、ユーザーのデバイスに UX を適合します。  ブラウザーから[デバイス エミュレーション ツール][DevToolsGuideEmulation]を使用してローカルでテストするか、リモート[][DevToolsProtocolClientsEdgeDevToolsPreview]デバッグ セッションをセットアップしてターゲット デバイスで直接テストします。  Windows 10 では、PCA \(EdgeHTML\) は[][WindowsUWPDesignDevicesIndex]、デスクトップ、電話、タブレット以外のフォーム ファクター [(Xbox、テレビ][WindowsUWPDesignDevicesDesigningTv][、Surface Hub、Windows][MicrosoftDeveloperWindowsSurfaceHub] [Mixed Reality][MicrosoftDeveloperWindowsMixedReality]デバイスなど) に合わせて調整することもできます。  
  
*   [ディープ リンク][WikiDeepLinking]。  サイトの各ページを一意の URL にルーティングして、既存のユーザーがソーシャル メディア共有を通じてより広い対象ユーザーを引き付けるのに役立ちます。  

*   [ベスト プラクティス][Webhint]。  [webhint][Webhint] linter のようなコード品質ツールを使用して、アプリの効率、堅牢性、安全性、アクセシビリティを最適化します。  

Microsoft Store に段階的な Web アプリを [提出するには、次][MicrosoftDeveloperStore]の情報が必要です。  

*   [Microsoft 開発者アカウント][WindowsUWPPublishDeveloperAccount]  
*   Windows アプリ [を公開するための完了した手順][WindowsUWPPublishIndex]  

数か月以内に、Web 上の既存の PAS が特定の条件を満たす場合、Bing 検索エンジンによって Microsoft Store \(開発者は Windows 10 の対象ユーザー用に直接管理できる\) に自動的にインデックスが作成されます。 [][PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission]  

詳細については [、Microsoft Store で PAS (EdgeHTML)][PwaEdgehtmlMicrosoftStore] を確認してください。  

## 現在の可用性  

段階的な Web アプリに対するブラウザー エンジンのサポートは、多くのアーキテクチャ コンポーネントを呼び出します。最も重要なのは [、Fetch API][MDNFetchApi]の基礎となるネットワーク インフラストラクチャです。  EdgeHTML エンジンでの PWA サポートは、Windows 10 1809 リリースで完了しました。  その時間が EdgeHTML エンジンに組み込まれるのではないので、Web 標準をさらに改善しました。そのため、EdgeHTML プラットフォームで PWA が必要とする機能がサポートされていない場合は、互換性テストを実行し、機能検出を使用して適切にフォールバックしてください。  

2020 年に予定されている Microsoft Edge \(Chromium\) リリースでは、Chromium ブラウザーがサポートされているデバイス間で動作するこれらの機能がブラウザー プラットフォームで完全にサポートされています。  

EdgeHTML と Windows の場合、標準ベースの PWA テクノロジの現在の状態を次に示します。  

| テクノロジ | 目的 | 対象 | 使用上の注意 |  
|:--- |:--- |:--- |:--- |  
| [Web アプリケーション マニフェスト][MDNWebAppManifest] | インストールとアプリ ストアのプロモーションを有効にするためのアプリ メタデータをホスト OS に提供します。  Microsoft Store の PAS に必要です。  | [開発中][MicrosoftDeveloperEdgePlatformStatusWebApplicationManifest] | 現在のところ [、PWA Builder][|::ref1::|] を使用して W3C 準拠の JSON マニフェストを生成し、さまざまな OS プラットフォーム用にアプリをパッケージ化することができます。  Windows の場合、PWA Builder は JSON マニフェストを Windows 10 アプリに必要な `.appxmanifest` \(XML\) 形式に変換します。  |  
| [API のフェッチ][MDNFetchApi] | ページ リソースの非同期ネットワーク \(要求、応答\) を提供します。 |[EdgeHTML 14+][DevGuideWhatsNewEdgeHtml14] / ビルド 14393+ | サービス [ワーカー API 構文][MDNServiceWorkerApi] は、フェッチ ベースのネットワーク API に基づいて作成されます。  また、Fetch API は、より一般的 [に最新][MDNFetchApi] の代替手段として使用することもできます `XMLHttpRequest` 。  |  
| [サービス ワーカー API][MDNServiceWorkerApi] | オフライン対応の Web アプリ モデル/ネットワーク プロキシを提供します。イベント駆動型スクリプトは Web ページから独立して実行されます。  | [EdgeHTML17][DevGuideWhatsNewEdgeHtml17] / ビルド 17133+ | EdgeHTML 16 に出荷された試験的なサポート \(behind `Enable Service Workers` flag\)  EdgeHTML 17+ ビルドでは、既定でオンになります。  |  
| [キャッシュ API][MDNCache] | ネットワーク要求と応答のペアの記憶域メカニズムを提供します。 | [EdgeHTML17][DevGuideWhatsNewEdgeHtml17] / ビルド 17133+ | 上記 [のサービス ワーカー API に関するメモ][MDNServiceWorkerApi] を参照してください。  |  
| [プッシュ API][MDNPushApi] | サービス ワーカーがプッシュ通知をサブスクライブできます。 |[EdgeHTML17][DevGuideWhatsNewEdgeHtml17] / ビルド 17133+| 上記 [のサービス ワーカー API に関するメモ][MDNServiceWorkerApi] を参照してください。  Windows 10 アプリ \(PAS を含む\) では、W3C プッシュ API をサポートするプッシュ通知を配信するために Windows プッシュ通知サービス [\(WNS\)][WindowsUWPControlsPatternTilesNotificationsWns] が必要 [です][MDNPushApi]。  |  
| [通知 API][MDNNotificationsApi] | サービス ワーカーがプッシュ メッセージ時にユーザーにシステム通知を表示できます。 | [EdgeHTML 14+][DevGuideWhatsNewEdgeHtml14] / ビルド 14393+ | EdgeHTML の Web 通知は、ユーザーがアプリの通知を[][MicrosoftSupportWindowsNotificationSettings]管理し、Quiet Hours を設定できる Windows 10 アクション センターと完全[に統合されています][MicrosoftSupportWindowsFocusAssist]。  |  
| [バックグラウンド同期 API][MDNSyncManager] | ユーザーがオンラインに戻り、定期的なイベントをスケジュールしてローカル データをサーバーと同期するサービス ワーカーに通知する API を提供します。 | [開発中][MicrosoftDeveloperEdgePlatformStatusBackgroundSync] | 現在のところ、ネイティブ [の WinRT BackgroundTask API][WindowsUWPLaunchResumeBackgroundTasks] を使用して、Windows 10 アプリとして実行するときに PWA のバックグラウンド タスクを実装できます。  |  

Windows 10 の PAS に対する Microsoft Store サポートの現在の状態を次に示します。  

| ストア申請メソッド | ステータス | 詳細 |  
|:--- |:--- |:--- |  
| Manual \(developer initiated\) | 利用可能 | Microsoft [Store で PAS (EdgeHTML) を][PwaEdgehtmlMicrosoftStore] 確認して、始めましょう。  |  
| Automatic \(auto-indexed with Bing\) | 近日提供予定 | 現在、 [アプリ パートナーの限定][WindowsBlogsWelcomingPWAsEdgeWindows] されたサブセットを使用して PWA オンボーディング プロセスを試験的に実施しています。  数か月以内に、Microsoft はメインストリーム Web 全体の PAS を Microsoft Store に歓迎します。  自動生成 [された PWA 登録情報][PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission] に関する Microsoft Store の要件の詳細については、Bing による自動 PWA インポートを参照してください。  |  

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
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "サービス ワーカー API |MDN"  
[MDNSyncManager]: https://developer.mozilla.org/docs/Web/API/SyncManager "SyncManager |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web アプリ マニフェスト |MDN"  

[PWABuilder]: https://www.pwabuilder.com "PWABuilder"  

[Webhint]: https://webhint.io "webhint"  

[WikiDeepLinking]: https://en.wikipedia.org/wiki/Deep_linking "ディープ リンク - Wikipedia"  
[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS - Wikipedia"  
[WikiResponsiveWebDesign]: https://en.wikipedia.org/wiki/Responsive_web_design "レスポンシブ Web デザイン - Wikipedia"  
