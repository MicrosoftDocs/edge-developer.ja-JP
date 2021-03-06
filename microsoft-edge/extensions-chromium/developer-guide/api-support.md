---
description: Microsoft Edge 拡張機能を構築するときに使用するサポートされている API の一覧。
title: Microsoft Edge 拡張機能でサポートされる API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, 拡張機能の開発, ブラウザー拡張機能, アドオン, 拡張 API , 開発者, Web 開発
ms.openlocfilehash: 20e924b5c973b9ecd433feeb3a772c6d17746369
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398106"
---
# <a name="supported-apis-for-microsoft-edge-extensions"></a>Microsoft Edge 拡張機能でサポートされる API

次の表に、Microsoft Edge \(Chromium\) ブラウザーの拡張機能を構築するときに使用できる API の一覧を示します。

| API                                   | 説明                                            
|---------------------------------------|----------------------------------------------------------|
| [アラーム](https://developer.chrome.com/extensions/alarms) | コードを定期的に実行するか、将来指定した時刻に実行するスケジュールを設定します。 |
| [ブックマーク](https://developer.chrome.com/extensions/bookmarks) | ブックマークを作成、整理、および操作します。 |
| [browserAction](https://developer.chrome.com/extensions/browserAction) | ブラウザーアクションを使用して、Microsoft Edge のツールバーにアイコンを配置します。 ブラウザーアクションを使用して、ヒント、バッジ、ポップアップを追加することもできます。 |
| [browsingData](https://developer.chrome.com/extensions/browsingData) | ユーザーのローカル プロファイルから参照データを削除します。 |
| [コマンド](https://developer.chrome.com/extensions/commands) | 拡張機能のアクションをトリガーするキーボード ショートカットを追加します。 たとえば、ブラウザーを開くか、拡張機能にコマンドを送信するアクションです。 |
| [contentSettings](https://developer.chrome.com/extensions/contentSettings) | 一般に、コンテンツ設定を使用すると、グローバルではなく、各サイトでの Microsoft Edge の動作をカスタマイズできます。 Web サイトで Cookie、JavaScript、プラグインなどの機能を使用できるかどうかを制御する設定を変更します。 |
| [contextMenus](https://developer.chrome.com/extensions/contextMenus) | Microsoft Edge のコンテキスト メニューにアイテムを追加します。 メニュー項目は、画像、ハイパーリンク、ページなど、さまざまなオブジェクトに適用できます。 |
| [Cookie](https://developer.chrome.com/extensions/cookies) | Cookie のクエリと変更、および変更時の通知の受信。 |
| [デバッガー](https://developer.chrome.com/extensions/debugger) | 1 つ以上のタブに接続して、ネットワーク操作をインストルメントに追加し、JavaScript をデバッグし、DOM を変更し、CSS を変更します。 デバッガー tabId を使用して、sendCommand を使用してタブをターゲットにし、イベントを onEvent コールバックから tabId でルーティングします。 |
| [declarativeContent](https://developer.chrome.com/extensions/declarativeContent) | ページのコンテンツを読み取る権限を必要とせずに、ページのコンテンツに応じてアクションを実行します。 |
| [declarativeNetRequest](https://developer.chrome.com/extensions/declarativeNetRequest) | 宣言型ルールを指定してネットワーク要求をブロックまたは変更することで、より多くのプライバシーを提供します。 拡張機能は、要求を傍受してコンテンツを表示せずにネットワーク要求を変更できます。 |
| [desktopCapture](https://developer.chrome.com/extensions/desktopCapture) | 画面、個々のウィンドウ、またはタブのコンテンツをキャプチャします。 |
| [devtools.inspectedWindow](https://developer.chrome.com/extensions/devtools_inspectedWindow) | 検査されたウィンドウを操作します。  たとえば、ページのタブ ID を取得したり、コードを評価したり、ページを更新したり、ページのリソースを取得したりします。 |
| [devtools.network](https://developer.chrome.com/extensions/devtools_network) | [ネットワーク] パネルの [開発者ツール] によって表示されるネットワーク要求に関する情報を取得します。 |
| [devtools.panels](https://developer.chrome.com/extensions/devtools.panels) | 独自のパネルを作成したり、既存のパネルにアクセスしたり、サイドバーを追加したりして、拡張機能を Developer Tools ウィンドウ UI に統合します。 |
| [downloads](https://developer.chrome.com/extensions/downloads) | プログラムを使用してダウンロードを開始、監視、操作、および検索します。 |
| [enterprise.hardwarePlatform](https://developer.chrome.com/extensions/enterprise.hardwarePlatform) | ブラウザーが実行されるハードウェア プラットフォームの製造元とモデルを取得します。 この API は、エンタープライズ ポリシーによってインストールされた拡張機能でのみ使用できます。 |
| [イベント](https://developer.chrome.com/extensions/events) | 興味深いイベントが発生した場合に通知するイベントを発生する API で使用される一般的な型。 |
| [拡張機能](https://developer.chrome.com/extensions/extension) | 任意の拡張ページでは、この API のユーティリティを使用できます。 拡張機能とコンテンツ スクリプトの間でメッセージを交換するためのサポートが含まれています。これは「メッセージの渡し」で説明されています。 |
| [extensionTypes](https://developer.chrome.com/extensions/extensionTypes) | Microsoft Edge 拡張機能の型宣言が含まれる。 |
| [fontSettings](https://developer.chrome.com/extensions/fontSettings) | Microsoft Edge でフォント設定を管理します。 |
| [履歴](https://developer.chrome.com/extensions/history) | ブラウザーのアクセスしたページのレコードを操作します。 ブラウザーの履歴で URL を追加、削除、またはクエリできます。 履歴ページを独自のバージョンで上書きするには、[ページの上書き] に移動します。 |
| [i18n](https://developer.chrome.com/extensions/i18n) | アプリまたは拡張機能全体で国際化を実装します。 |
| [アイドル状態](https://developer.chrome.com/extensions/idle) | コンピューターのアイドル状態が変更された場合を検出します。 |
| [管理](https://developer.chrome.com/extensions/management) | インストール済みまたは実行中の拡張機能の一覧を管理します。 これは、組み込みの [新しいタブ] ページを上書きする拡張機能に役立ちます。 |
| [通知](https://developer.chrome.com/extensions/notifications) | テンプレートを使用してリッチ通知を作成し、システム トレイに表示します。 |
| [omnibox](https://developer.chrome.com/extensions/omnibox) | Microsoft Edge アドレス バー (オムニボックスとも呼ばれる) にキーワードを登録します。 |
| [pageAction](https://developer.chrome.com/extensions/pageAction) | アドレス バーの右側にある Microsoft Edge ツールバーにアイコンを追加します。 ページ アクションは、現在のページで実行できるアクションであり、すべてのページには適用できません。 非アクティブな場合、ページアクションは灰色で表示されます。 |
| [pageCapture](https://developer.chrome.com/extensions/pageCapture) | タブを MHTML ファイルとして保存します。|
| [アクセス許可](https://developer.chrome.com/extensions/permissions) | インストール時ではなく、実行時に宣言されたオプションのアクセス許可を取得します。 この API を使用すると、ユーザーに必要なアクセス許可と承認済みアクセス許可を表示できます。 |
| [電源](https://developer.chrome.com/extensions/power) | システムの電源管理機能を上書きします。 |
| [printerProvider](https://developer.chrome.com/extensions/printerProvider) | イベントを使用して、プリンター、その機能を照会し、印刷ジョブを送信します。 |
| [プライバシー](https://developer.chrome.com/extensions/privacy) | ユーザーのプライバシーに影響を与える Microsoft Edge の機能を制御します。 この API は、Microsoft `EdgeSetting` Edge の構成 `types` を取得および設定するプロトタイプに依存します。 |
| [プロキシ](https://developer.chrome.com/extensions/proxy) | Microsoft Edge のプロキシ設定を管理します。 この API は、Microsoft Edge のプロキシ構成を取得および設定する `EdgeSetting` `types` API のプロトタイプに依存します。 |
| [ランタイム](https://developer.chrome.com/extensions/runtime) | バックグラウンド ページを取得し、マニフェストに関する詳細を返し、アプリまたは拡張機能ライフサイクルのイベントをリッスンして応答します。 URL の相対パスを完全修飾 URL に変換できます。 |
| [セッション](https://developer.chrome.com/extensions/sessions) | ブラウズ セッションからタブとウィンドウのクエリと復元を行います。 |
| [ストレージ](https://developer.chrome.com/extensions/storage) | ユーザー データの変更を保存、取得、および追跡します。 |
| [system.memory](https://developer.chrome.com/extensions/system_memory) | `system.memory`API。 |
| [system.storage](https://developer.chrome.com/extensions/system_storage) | ストレージ デバイスに関するクエリ情報。 ストレージ デバイスが接続または切り離されている場合にも通知を受信できます。 |
| [tabCapture](https://developer.chrome.com/extensions/tabCapture) | タブ メディア ストリームを操作します。 |
| [タブ](https://developer.chrome.com/extensions/tabs) | ブラウザーのタブ システムを操作して、タブの作成、変更、並べ替えを行います。 |
| [topSites](https://developer.chrome.com/extensions/topSites) | 新しいタブ ページに表示される、最もアクセス数の多いサイトとも呼ばれる上位サイトにアクセスします。 これらのサイトには、ユーザーがカスタマイズしたショートカットは含めいません。 |
| [tts](https://developer.chrome.com/extensions/tts) | 合成された音声合成 (TTS) を再生します。 |
| [ttsEngine](https://developer.chrome.com/extensions/ttsEngine) | 拡張機能を使用して音声合成 (TTS) エンジンを実装します。 この API を使用するように登録された拡張機能は、話す発話や他のパラメーターを含むイベントを受け取ります。 拡張機能は、使用可能な任意の Web テクノロジを使用して音声を合成および出力し、イベントを呼び出し元の関数に送り返して状態を報告できます。 |
| [型](https://developer.chrome.com/extensions/types) | Microsoft Edge の型宣言。 |
| [webNavigation](https://developer.chrome.com/extensions/webNavigation) | ナビゲーション要求の状態に関する通知を受信します。 |
| [webRequest](https://developer.chrome.com/extensions/webRequest) | トラフィックを監視および分析します。 要求を傍受、ブロック、または変更します。 |
| [windows](https://developer.chrome.com/extensions/windows) | ブラウザー ウィンドウを操作して、ブラウザーでウィンドウを作成、変更、再配置します。 |



## <a name="unsupported-extension-apis"></a>サポートされていない拡張 API

Microsoft Edge では、次の拡張 API はサポートされていません。

* `chrome.gcm`.
* `chrome.identity.getAccounts`.
* `chrome.identity.getAuthToken` - 代わりとして、OAuth2 トークンを `launchWebAuthFlow` フェッチしてユーザーを認証することができます。
* `chrome.instanceID`.


## <a name="additional-considerations-for-supported-apis"></a>サポートされる API に関するその他の考慮事項

* ユーザーが使用するには、MSA または Azure Active Directory アカウントを使用して Microsoft Edge にサインインする必要があります `chrome.identity.getProfileUserInfo` 。 ユーザーがオンプレミスの Active Directory アカウントを使用して Microsoft Edge にサインインしている場合、API は電子メールと ID の値 `null` を返します。

* Microsoft Edge は、サインインしているユーザーのトークンを要求するために使用する Chrome Web ストア支払いを使用する拡張機能 `identity.getAuthtoken` をサポートしていない。 これらのトークンは、REST ベースのライセンス API に送信されます。 


<!-- links -->  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページは次 [のページに表示されます](https://developer.chrome.com/apps/external_extensions)。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
