---
description: プログレッシブ Web アプリは Windows 10 でネイティブに実行されます。  ここでは、web 開発者として知っておく必要があるものをすべて紹介します。
title: Windows のプログレッシブ Web アプリ (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/28/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: pwa
keywords: プログレッシブ web アプリ、PWA、エッジ、JavaScript、Windows、UWP、Microsoft ストア
ms.openlocfilehash: 778502f6db9a89da810b4fb59b10e8fb889fa4b5
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568781"
---
# Windows のプログレッシブ Web アプリ (EdgeHTML)  

[プログレッシブ Web アプリ][MDNApps](または単に pwas) を使用する場合、クロスプラットフォームの相互運用性を実現するために開かれた web テクノロジを使用する方法と、デバイスに合わせてカスタマイズされたネイティブアプリなどのエクスペリエンスをユーザーに提供することを決定する必要はありません。  これは、PWAs は、サポートしているプラットフォーム上のネイティブアプリのように機能するように[段階的に拡張][AListApartUnderstandingProgressiveEnhancement]された web サイトだけであるためです。  PWA では、Web アプリとネイティブ アプリの良いところが組み合わされています。  

:::row:::
    :::column:::
        ![検出可能なアイコン][ImageISearch]
        ### [見つけ][MDNPwaAdvantagesDiscoverable]
        Web 検索結果とサポートされているアプリストアから
    :::column-end:::
    :::column:::
        ![インストール可能なアイコン][ImageIPackage]
        ### [Installable][MDNPwaAdvantagesInstallable]
        ホーム画面からピン留めして起動する  
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
        デバイス機能を使用して、エクスペリエンスを (上または下に) 拡張する  
    :::column-end:::
    :::column:::
        ![安全なアイコン][ImageISecurity]
        ### [問題][MDNPwaAdvantagesSafe]
        セキュリティで保護された HTTPS エンドポイントとその他のユーザーの保護機能を提供する  
    :::column-end:::
    :::column:::
        ![応答性アイコン][ImageIResponsive]
        ### [応答中][MDNPwaAdvantagesResponsive]
        ユーザーの画面サイズ/向きと入力方式に合わせて調整する  
    :::column-end:::
    :::column:::
        ![Linkable アイコン][ImageILink]
        ### [Linkable][MDNPwaAdvantagesLinkable]
        標準ハイパーリンクを共有して起動する  
    :::column-end:::
:::row-end:::

既存のサイトを作成したり、既存のサイトを PWA に変換したりすることで、既存の対象ユーザーに対してプッシュ通知とオフラインサポートを強化することができます。  同時に、ユーザーが検索とリンク共有を通じて PWA を見つけているため、開いている web で参加者の作成を続けることができます。  

## PWAs は Windows 10 (EdgeHTML) で行われました  

> [!NOTE]
> EdgeHTML から [Microsoft Edge へ移動] (Chromium) を使うと、PWAs によって使用された基になる web プラットフォームは同じではありません。  Edge (Chromium) PWAs は、ブラウザーからインストールして実行します。  Edge (EdgeHTML) PWAs ユニバーサル Windows プラットフォーム (UWP) アプリケーションとして実行され、以前の EdgeHTML web プラットフォームを使用しています。  PWA に Windows 10 API アクセスが必要な場合は、この EdgeHTML のドキュメントを参照してください。  Windows 固有の API アクセスのないクロスプラットフォームサポートの目標である場合は、 [Microsoft Edge (Chromium) PWA ドキュメント][PwaChromiumIndex]に移動してください。  

プログレッシブ Web アプリを構築して Windows 10 を利用できるようにすると、 [Microsoft ストア][MicrosoftDeveloperStore]で PWA を配布できます。 windows 10 のインストールベースの 600% 100 のインストールベースは、アプリの対象ユーザーになります。  この方法で開発されたアプリケーションは、[ユニバーサル Windows プラットフォーム][WindowsUWPGetStartedGuide]アプリとして実行され、WinRT api へのアクセスなどのネイティブ機能を備えています。  コードをレンダリングする web プラットフォームは、WinRT Api を使っているときには EdgeHTML であることに注意してください。 Windows 固有の Api を呼び出す前に、機能の検出を確実に使用して、Microsoft Edge \ (Chromium \) PWAs が利用可能なプラットフォーム間でも PWA を実行できるようにしてください。  

ここでは、web アプリを PWA \ (EdgeHTML \) に変換して、Windows 10 でテストし、Microsoft Store で配布[する方法について説明][PwaEdgehtmlGetStarted]します。  

## 要件  

PWA として実行するには、サーバーでホストされている web アプリで少なくとも次の要件を満たす必要があります。  

*   [X] [HTTPS][WikiHttps]。  サーバー/アプリの通信にセキュリティで保護された接続を提供して、ユーザーを保護します。  サービス作業者やその他の PWA テクノロジは、セキュリティで保護された接続を経由して提供される web リソース (または `localhost` デバッグ目的でのみ) と動作します。  
  
*   [X][サービスワーカー][MDNServiceWorkerApi]。  サービスワーカースレッドを使って、オフラインサポート、リソースキャッシュ、プッシュ通知、バックグラウンドデータ同期、ページ読み込みパフォーマンス最適化を提供するために、サーバーとクライアントアプリの間でネットワークプロキシとして機能します。  

*   [X] [Web app マニフェスト][MDNWebAppManifest]。  Windows 10 やその他のホストプラットフォームが、インストール可能なネイティブアプリのようなエクスペリエンスを備えた PWA ユーザーを提供できるように、Windows 10 とその他のホストプラットフォームが、自分の web アプリについての重要な情報を記述した JSON ベースのメタデータファイルを提供します。  Web アプリマニフェストにサイトを関連付けると、Bing インデックスサービスを通じて[Microsoft ストアに自動的に含める][PwaEdgehtmlMicrosoftStoreImportingBing]ことができます。  

アプリには、次のような便利な PWA もあります。  

*   [X][ブラウザ間の互換性][MDNCrossBrowserTesting]。  さまざまなブラウザーと環境で[テスト][MicrosoftDeveloperEdgeToolsRemote]して、PWA が動作することを確認します。  Windows 10 では、アプリを Microsoft Edge ブラウザーと完全な PWA 環境の両方でテストしてください。インストールされているスタンドアロン Windows 10 アプリ (EdgeHTML エンジン \) としてインストールします。  
  
*   [X][応答性][WikiResponsiveWebDesign]の高いデザイン。  柔軟なレイアウトと柔軟性の高い画像を CSS [grid][MDNCssGridLayout]や[flexbox][MDNCssFlexibleBoxLayout]、[メディアクエリ][MDNMediaQueries]、および [応答性の高い画像[MDNResponsiveImages]で使用して、ユーザーのデバイスに合わせて UX を調整します。  ブラウザーのデバイス[エミュレーションツール][DevToolsGuide|::ref1::|]を使ってローカルでテストするか、[リモートデバッグセッション][DevToolsProtocolClientsEdgeDevToolsPreview]をセットアップしてターゲットデバイスで直接テストします。  Windows 10 では、PWAs \ (EdgeHTML) を、デスクトップ、スマートフォン、タブレット以外[のフォームファクターに合わせて調整][WindowsUWPDesignDevicesIndex]することができます。これには、 [Xbox とテレビ][WindowsUWPDesignDevicesDesigningTv]、 [Surface Hub][MicrosoftDeveloperWindowsSurfaceHub]、 [Windows Mixed Reality][MicrosoftDeveloperWindowsMixedReality]デバイスが含まれます。  
  
*   [X][ディープリンク][WikiDeepLinking]。  サイトの各ページを一意の URL にルーティングして、既存のユーザーがソーシャルメディア共有を通じてさらに多くのユーザーとの共同作業を行うことができるようにします。  

*   [X][ベストプラクティス][Webhint]。  アプリの効率、堅牢性、安全性、アクセシビリティを最適化するには、 [webhint][Webhint]のようなコード品質ツールを使用します。  

プログレッシブ Web アプリを[Microsoft Store][MicrosoftDeveloperStore]に提出するには、次のものが必要です。  

*   [X] [Microsoft 開発者アカウント][WindowsUWPPublishDeveloperAccount]  
*   [X] [Windows アプリを発行するための][WindowsUWPPublishIndex]完了した手順  

今後数ヶ月で、既存の PWAs が web 会議に[固有の条件][PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission]を満たしている場合は、Bing 検索エンジンによって、Microsoft Store に自動的にインデックスが作成されます (開発者は、Windows 10 の対象ユーザーに対してそれらを直接管理できます)。  

詳細については[、Microsoft ストアで Pwas (EdgeHTML)][PwaEdgehtmlMicrosoftStore]を確認してください。  

## 現在の可用性  

ブラウザエンジンのプログレッシブ Web アプリのさまざまな機能をサポートしています。多くのアーキテクチャコンポーネントに対応していますが、最も重要なのは[FETCH API][MDNFetchApi]の基礎となるネットワークインフラストラクチャです。  EdgeHTML エンジンでの PWA のサポートは、Windows 10 1809 リリースで完了しています。  その時間が EdgeHTML エンジンに組み込まれていないため、web の標準をさらに改善するため、互換性テストを実行し、機能の検出を使用して、PWA の必要な機能が EdgeHTML プラットフォームでサポートされていないことを確認してください。  

今後の Microsoft Edge \ (Chromium \) リリースの2020では、ブラウザープラットフォームは、Chromium ブラウザーがサポートされているデバイス間で動作するこれらの機能を完全にサポートしています。  

EdgeHTML と Windows では、標準ベースの PWA テクノロジの現在の状態は、次のようになります。  

| テクノロジ | 目的 | 対象 | 使用上の注意 |  
|:--- |:--- |:--- |:--- |  
| [Web アプリケーションマニフェスト][MDNWebAppManifest] | インストールとアプリストアのプロモーションを有効にするために、ホスト OS にアプリのメタデータを提供します。  Microsoft Store で PWAs が必要。  | [開発中][MicrosoftDeveloperEdgePlatformStatusWebApplicationManifest] | 現時点では、 [PWA ビルダー][|::ref2::|]を使用して、W3C に準拠した JSON マニフェストを生成し、さまざまな OS プラットフォーム用にアプリをパッケージ化することができます。  Windows の場合、PWA ビルダーでは、JSON マニフェストが `.appxmanifest` windows 10 アプリで必要な \ (XML \) 形式に変換されます。  |  
| [取得 API][MDNFetchApi] | ページリソースの非同期ネットワーク \ (要求、返信) を提供します。 |[EdgeHTML 14 +][DevGuideWhatsNewEdgeHtml14] /Build 14393 + | [サービスワーカー API][MDNServiceWorkerApi]構文は、フェッチベースのネットワーク api に基づいています。  さらに、 [FETCH API][MDNFetchApi]をもっと一般的な新しい方法として使うこともでき `XMLHttpRequest` ます。  |  
| [Service Worker API][MDNServiceWorkerApi] | Web ページに依存しないイベント駆動型のスクリプトを実行する、オフライン対応の web アプリモデル/ネットワークプロキシを提供します。  | [EdgeHTML17][DevGuideWhatsNewEdgeHtml17] /Build 17133 + | `Enable Service Workers`EdgeHTML 16 には、実験的サポート \ (裏に旗) が同梱されています。  EdgeHTML 17 + ビルドでは既定でオンになっています。  |  
| [キャッシュ API][MDNCache] | ネットワーク要求と応答のペアのストレージメカニズムを提供します | [EdgeHTML17][DevGuideWhatsNewEdgeHtml17] /Build 17133 + | 上の「 [Service WORKER API][MDNServiceWorkerApi]のメモ」を参照してください。  |  
| [プッシュ API][MDNPushApi] | サービスワーカーがプッシュ通知をサブスクライブできるようにします。 |[EdgeHTML17][DevGuideWhatsNewEdgeHtml17] /Build 17133 +| 上の「 [Service WORKER API][MDNServiceWorkerApi]のメモ」を参照してください。  Windows 10 アプリ \ (PWAs を含む) では、W3C[プッシュ API][MDNPushApi]をサポートするプッシュ通知を実行するために、 [Windows プッシュ通知サービス \ (WNS)][WindowsUWPControlsPatternTilesNotificationsWns]が必要です。  |  
| [通知 API][MDNNotificationsApi] | サービスワーカーが、プッシュメッセージ時にシステム通知をユーザーに表示できるようにします。 | [EdgeHTML 14 +][DevGuideWhatsNewEdgeHtml14] /Build 14393 + | EdgeHTML の Web 通知は、ユーザーがアプリの通知を管理し、[非表示時間][MicrosoftSupportWindowsFocusAssist]を設定できる Windows 10[アクションセンター][MicrosoftSupportWindowsNotificationSettings]と完全に統合されています。  |  
| [バックグラウンド同期 API][MDNSyncManager] | ユーザーがオンラインに戻ったことをサービスワーカーに通知するための API を提供します。また、定期的なイベントのスケジュールを設定して、ローカルデータをサーバーと同期します。 | [開発中][MicrosoftDeveloperEdgePlatformStatusBackgroundSync] | 現時点では、ネイティブの[WinRT BackgroundTask API][WindowsUWPLaunchResumeBackgroundTasks]を使って、Windows 10 アプリとして実行されたときに PWA のバックグラウンドタスクを実装することができます。  |  

Windows 10 での Microsoft ストアサポートの現在の状態は、次のとおりです。  

| ストアへの申請の方法 | ステータス | 詳細 |  
|:--- |:--- |:--- |  
| 手動 \ (開発者によって開始されました) | 利用可能 | 開始するには[、Microsoft Store で Pwas (EdgeHTML)][PwaEdgehtmlMicrosoftStore]を確認してください。  |  
| 自動 \ (Bing \) での自動インデックス作成 | 近日提供予定 | 現時点では、アプリパートナーの限定されたサブセットで PWA のオンボードプロセスを[試験][WindowsBlogsWelcomingPWAsEdgeWindows]的に行っています。  今後数ヶ月で、Microsoft はメインストリーム web 上で Microsoft ストアに配信されました。  自動生成された PWA リストの Microsoft ストアの要件の詳細については、「 [Bing を使用した自動][PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission]生成される pwa のインポートの要件」を参照してください。  |  

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

[DevToolsProtocolClientsEdgeDevToolsPreview]: ../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge DevTools のプレビュー-DevTools プロトコルクライアント"  
[DevToolsGuideEmulation]: ../devtools-guide/emulation.md "エミュレーション"  
[DevGuideWhatsNewEdgeHtml17]: ../dev-guide/whats-new/edgehtml-17.md "EdgeHTML 17 の新機能"  
[DevGuideWhatsNewEdgeHtml14]: ../dev-guide/whats-new/edgehtml-14.md "EdgeHTML 14 の新機能"  
[PwaChromiumIndex]: ../progressive-web-apps-chromium/index.md "Windows のプログレッシブ Web アプリ (Chromium)"  
[PwaEdgehtmlGetStarted]: ../progressive-web-apps-edgehtml/get-started.md "プログレッシブ Web アプリ (EdgeHTML) の使用を開始する"  
[PwaEdgehtmlMicrosoftStore]: ../progressive-web-apps-edgehtml/microsoft-store.md "Microsoft Store のプログレッシブ Web アプリ"
[PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission]: ../progressive-web-apps-edgehtml/microsoft-store.md#criteria-for-automatic-submission "Microsoft Store での自動送信 Web アプリの条件"  
[PwaEdgehtmlMicrosoftStoreImportingBing]: microsoft-store.md#automatic-pwa-importing-with-bing "Microsoft Store の Bing プログレッシブ Web アプリ (EdgeHTML) を使用した自動 PWA インポート"  


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

[PWABuilder]: https://www.pwabuilder.com "PWABuilder"  

[Webhint]: https://webhint.io "web ヒント"  

[WikiDeepLinking]: https://en.wikipedia.org/wiki/Deep_linking "ディープリンク-Wikipedia"  
[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS-Wikipedia"  
[WikiResponsiveWebDesign]: https://en.wikipedia.org/wiki/Responsive_web_design "応答性の高い web デザイン-Wikipedia"  
