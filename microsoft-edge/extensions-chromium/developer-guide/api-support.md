---
description: Microsoft Edge extensions の構築時に使用されるサポートされている Api の一覧です。
title: Microsoft Edge extensions でサポートされている Api
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/14/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、extensions の開発、ブラウザーの拡張、アドオン、拡張 api、開発者、web 開発
ms.openlocfilehash: 868473393da6cefbf146fb7acd6c9816903bd253
ms.sourcegitcommit: af91bfc3e6d8afc51f0fbbc0fe392262f424225c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2020
ms.locfileid: "11120394"
---
# Microsoft Edge extensions でサポートされている Api

次の表では、Microsoft Edge \ (Chromium) ブラウザーの拡張機能を構築するときに使用できる Api の一覧を示します。

| API                                   | 説明                                            
|---------------------------------------|----------------------------------------------------------|
| [アラーム](https://developer.chrome.com/extensions/alarms) | 定期的に、または指定した時間に実行されるようにコードをスケジュールします。 |
| [ブックマーク](https://developer.chrome.com/extensions/bookmarks) | ブックマークの作成、整理、操作を行います。 |
| [browserAction](https://developer.chrome.com/extensions/browserAction) | ブラウザーのアクションを使用して、Microsoft Edge のツールバーにアイコンを配置します。 また、ブラウザーアクションを使って、ヒント、バッジ、またはポップアップを追加することもできます。 |
| [データの一部](https://developer.chrome.com/extensions/browsingData) | ユーザーのローカルプロファイルから参照データを削除します。 |
| [コマンド](https://developer.chrome.com/extensions/commands) | 拡張機能でアクションをトリガーするショートカットキーを追加します。 たとえば、ブラウザーを開くアクション、または拡張子にコマンドを送信する操作などです。 |
| [contentSettings](https://developer.chrome.com/extensions/contentSettings) | 一般に、コンテンツの設定では、グローバルにではなく、各サイトの Microsoft Edge の動作をカスタマイズすることができます。 Web サイトで cookie、JavaScript、プラグインなどの機能を使用できるかどうかを制御する設定を変更します。 |
| [contextMenus](https://developer.chrome.com/extensions/contextMenus) | Microsoft Edge でコンテキストメニューに項目を追加します。 メニュー項目は、画像、ハイパーリンク、ページなどのさまざまなオブジェクトに適用される場合があります。 |
| [cookie](https://developer.chrome.com/extensions/cookies) | Cookie を照会して変更すると、変更時に通知を受け取ることができます。 |
| [ブレーク](https://developer.chrome.com/extensions/debugger) | 1つまたは複数のタブに接続して、ネットワークの操作をインストルメント化したり、JavaScript をデバッグしたり、DOM を変更したり、CSS を変更したりします。 デバッガタブ Id を使用して、sendCommand でタブをターゲットにし、イベントごとにイベントをイベント別のコールバックからルーティングします。 |
| [declarativeContent](https://developer.chrome.com/extensions/declarativeContent) | ページコンテンツの読み取りアクセス許可を必要とせずに、ページのコンテンツに応じてアクションを実行します。 |
| [declarativeNetRequest](https://developer.chrome.com/extensions/declarativeNetRequest) | 宣言型ルールを指定してネットワーク要求をブロックまたは変更することで、より多くのプライバシーを提供します。 要求を傍受してコンテンツを表示することなく、拡張機能でネットワーク要求を変更できるようにします。 |
| [desktopCapture](https://developer.chrome.com/extensions/desktopCapture) | 画面、個々のウィンドウ、またはタブのコンテンツをキャプチャします。 |
| [devtools](https://developer.chrome.com/extensions/devtools_inspectedWindow) | 検査されたウィンドウを操作します。 たとえば、ページのタブ ID の取得、コードの評価、ページの読み込み、またはページ上のリソースの取得などを行うことができます。 |
| [devtools. ネットワーク](https://developer.chrome.com/extensions/devtools_network) | [ネットワーク] パネルの開発者ツールによって表示されるネットワーク要求に関する情報を取得します。 |
| [devtools パネル](https://developer.chrome.com/extensions/devtools.panels) | 独自のパネルの作成、既存のパネルへのアクセス、サイドバーの追加などを行って、拡張機能を [開発者ツール] ウィンドウの UI に統合します。 |
| [downloads](https://developer.chrome.com/extensions/downloads) | プログラムを使用して、ダウンロードを開始、監視、操作、検索します。 |
| [エンタープライズ向けのプラットフォーム](https://developer.chrome.com/extensions/enterprise.hardwarePlatform) | ブラウザーが実行されているハードウェアプラットフォームの製造元とモデルを入手します。 この API は、エンタープライズポリシーによってインストールされた拡張機能でのみ利用できます。 |
| [事象](https://developer.chrome.com/extensions/events) | 興味のあるイベントが発生したときに、イベントを発生させる Api で使われる一般的な型。 |
| [補助](https://developer.chrome.com/extensions/extension) | すべての拡張ページで、この API のユーティリティを使うことができます。 これには、メッセージパッシングで説明されている、拡張機能とコンテンツスクリプト間でのメッセージ交換のサポートが含まれています。 |
| [extensionTypes](https://developer.chrome.com/extensions/extensionTypes) | Microsoft Edge extensions の型宣言が含まれています。 |
| [fontSettings](https://developer.chrome.com/extensions/fontSettings) | Microsoft Edge でフォントの設定を管理します。 |
| [履歴](https://developer.chrome.com/extensions/history) | ブラウザーのアクセスページの記録を操作します。 ブラウザーの履歴では、Url の追加、削除、または照会を行うことができます。 独自のバージョンで履歴ページを上書きする方法については、「ページを上書きする」を参照してください。 |
| [プロパティー](https://developer.chrome.com/extensions/i18n) | アプリ全体または拡張機能を通じて国際化を実装します。 |
| [アイドル](https://developer.chrome.com/extensions/idle) | コンピューターのアイドル状態が変化したときに検出します。 |
| [マネージメント](https://developer.chrome.com/extensions/management) | インストール済みまたは実行中の拡張機能の一覧を管理します。 組み込みの新しいタブページを上書きする拡張機能に適しています。 |
| [通知](https://developer.chrome.com/extensions/notifications) | テンプレートを使用して豊富な通知を作成し、システムトレイに表示します。 |
| [omnibox](https://developer.chrome.com/extensions/omnibox) | Microsoft Edge のアドレスバー (omnibox とも呼ばれます) にキーワードを登録します。 |
| [Page アクション](https://developer.chrome.com/extensions/pageAction) | アドレスバーの右側にある Microsoft Edge ツールバーにアイコンを追加します。 ページアクションは、現在のページで実行できるアクションで、すべてのページに適用されるわけではありません。 非アクティブになっていると、ページアクションは淡色表示になります。 |
| [pageCapture](https://developer.chrome.com/extensions/pageCapture) | MHTML ファイルとしてタブを保存します。|
| [権限](https://developer.chrome.com/extensions/permissions) | 宣言された、省略可能なアクセス許可は、インストール時ではなく実行時に取得します。 この API を使って、必要な、または承認されたアクセス許可をユーザーに表示することができます。 |
| [電源](https://developer.chrome.com/extensions/power) | システムの電源管理機能を上書きします。 |
| [プリンタープロバイダー](https://developer.chrome.com/extensions/printerProvider) | イベントを使用して、プリンターとその機能を照会し、印刷ジョブを送信します。 |
| [プライバシー](https://developer.chrome.com/extensions/privacy) | Microsoft Edge の、ユーザーのプライバシーに影響する機能を制御します。 この API は、のプロトタイプに依存して、 `EdgeSetting` `types` Microsoft Edge の構成を取得して設定します。 |
| [プロキシ](https://developer.chrome.com/extensions/proxy) | Microsoft Edge のプロキシ設定を管理します。 この API は、api のプロトタイプによって、 `EdgeSetting` `types` Microsoft Edge のプロキシ構成を取得して設定します。 |
| [言語](https://developer.chrome.com/extensions/runtime) | 背景ページを取得し、マニフェストに関する詳細を返し、アプリまたは拡張機能のライフサイクルでイベントをリッスンして応答します。 Url の相対パスを完全修飾 Url に変換することもできます。 |
| [数](https://developer.chrome.com/extensions/sessions) | 閲覧セッションからのタブとウィンドウの照会と復元。 |
| [ストレージ](https://developer.chrome.com/extensions/storage) | ユーザーデータに対する変更を保存、取得、追跡します。 |
| [システムメモリ](https://developer.chrome.com/extensions/system_memory) | `system.memory`API。 |
| [システム. 記憶域](https://developer.chrome.com/extensions/system_storage) | ストレージデバイスに関する情報を照会します。 ストレージデバイスがアタッチまたはデタッチされたときに通知を受け取ることもできます。 |
| [tabCapture](https://developer.chrome.com/extensions/tabCapture) | タブメディアストリームを操作します。 |
| [タブ](https://developer.chrome.com/extensions/tabs) | ブラウザーのタブシステムを操作して、タブの作成、変更、再配置を行います。 |
| [topSites](https://developer.chrome.com/extensions/topSites) | 新しいタブページに表示されるトップサイト (多くのアクセス可能なサイトとも呼ばれます) にアクセスします。 これらのサイトには、ユーザーによってカスタマイズされたショートカットは含まれません。 |
| [合成](https://developer.chrome.com/extensions/tts) | 合成した音声合成 (TTS) を再生します。 |
| [ttsEngine](https://developer.chrome.com/extensions/ttsEngine) | 拡張機能を使用して、音声合成 (TTS) エンジンを実装します。 この API を使用するために登録する拡張機能は、話される発声やその他のパラメーターを含むイベントを受信します。 拡張機能を使うと、利用可能な web テクノロジを使用して音声を合成および出力し、呼び出し元の関数にイベントを送り、状態を報告することができます。 |
| [タイプ](https://developer.chrome.com/extensions/types) | Microsoft Edge の型宣言。 |
| [Web ナビゲーション](https://developer.chrome.com/extensions/webNavigation) | ナビゲーション要求の状態に関する通知を受信します。 |
| [webRequest](https://developer.chrome.com/extensions/webRequest) | トラフィックを監視および分析します。 要求のインターセプト、ブロック、または変更を行います。 |
| [windows](https://developer.chrome.com/extensions/windows) | ブラウザーウィンドウを操作して、ブラウザーでウィンドウの作成、変更、再配置を行います。 |



## サポートされていない拡張 Api

Microsoft Edge では、次の拡張 Api はサポートされていません。

* `chrome.gcm`.
* `chrome.identity.getAccounts`.
* `chrome.identity.getAuthToken` -代替として、OAuth2 トークンを取得してユーザーを認証するために使うことができ `launchWebAuthFlow` ます。
* `chrome.instanceID`.


## サポートされている Api に関するその他の考慮事項

* ユーザーは、MSA または Azure Active Directory アカウントを使用して Microsoft Edge にサインインしている必要があり `chrome.identity.getProfileUserInfo` ます。 ユーザーがオンプレミスの Active Directory アカウントを使用して Microsoft Edge にサインインしている場合、API は `null` メールと ID の値に対して戻ります。

* Microsoft Edge では、 `identity.getAuthtoken` サインインしたユーザーのトークンを要求するために使用するため、Chrome Web Store の支払いを使用する拡張機能はサポートされていません。 これらのトークンは、REST ベースのライセンス API に送信されます。 


<!-- links -->  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developer.chrome.com/apps/external_extensions)にあります。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
