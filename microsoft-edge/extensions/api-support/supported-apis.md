---
description: 現在の Api および将来の Api に関する情報を検索して、既知の問題や Chrome の互換性を確認します。
title: 拡張機能-サポートされている Api
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge、web 開発、html、css、javascript、開発者
ms.openlocfilehash: fceba67f5fab1a223cfc94abf7f19a0a9d1bcdf0
ms.sourcegitcommit: 0879b205aa88c6b73d84f106b4b435d5a0e8cadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "10937183"
---
# サポートされる API  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

サポートされている API メンバーの詳細な一覧を次に示します。 拡張プラットフォームの開発が進行中であるため、頻繁に更新を確認してください。

> [!NOTE]
>  - Microsoft Edge では、すべての拡張 Api は名前空間の下にあり `browser` ます。例: `browser.browserAction.disable()`
>  - Microsoft Edge extension Api では、約束ではなくコールバックが使われます。


## 包括的な問題

以下の既知の問題は拡張プラットフォームで利用できます。近い将来に修正される予定です。

- CSS プロパティを使う場合 `url()` 、使用する絶対 url `ms-browser-extension://` は、Chrome の場合と同じように動作しません。 この問題を回避するには、リソースへの相対パス (ルート拡張ディレクトリから開始) を使用します。
- `window.open()` 拡張機能のバックグラウンドスクリプトでは動作しません。 代わりにを使用してください `browser.windows.create()` 。
- 共有 cookie はサポートされていますが、拡張機能のバックグラウンドスクリプトには、拡張機能が有効になる前にタブで設定されたセッション cookie へのアクセス権がありません。 この問題は永続的な cookie には影響しません。
- 拡張機能に対してサポートされていない権限しか指定されていない場合 `activeTab`拡張機能をサイドローディングすると、次のようなメッセージが表示され、拡張機能がアンインストールされます。 "拡張機能に問題が発生したため、再インストールしてください。 もう一度有効にする必要があります。」
- 非表示のアンカータグを使ったダウンロードのトリガーは、バックグラウンドスクリプトから失敗します。 これは、代わりに拡張ページから行う必要があります。


## ブックマーク

次の `bookmarks` api がサポートされています。

| API                                   | 既知の問題                                             | Chrome の非互換性
|---------------------------------------|----------------------------------------------------------|--------------------------|
| [ブックマーク](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks) | | |
| [ブックマークを作成する](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/create) | | |
| [ブックマーク。削除](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/remove) | | |
| [ブックマーク。 getTree](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/getTree) |  | |
| [ブックマーク。移動](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/move) | | |
| [ブックマーク removeTree](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/removeTree) | | |
| [ブックマーク。更新](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/update)            | | |


## browserAction

次の `browserAction` api がサポートされています。

| API                                   | 既知の問題                                             | Chrome の非互換性
|---------------------------------------|----------------------------------------------------------|--------------------------|
| [browserAction](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction) | | |
| [ブラウザアクションを無効にする](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/disable) | | |
| [ブラウザアクションを有効にする](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/enable) | | |
| [browserAction。 getBadgeBackgroundColor](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/getBadgeBackgroundColor) |  | |
| [browserAction. setBadgeBackgroundColor](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/setBadgeBackgroundColor) | | |
| [browserAction. onClicked](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/onClicked) | | |
| [browserAction. setBadgeText](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/setBadgeText)            | | |
| [browserAction ポップアップ](https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/setPopup)  | | |
| [browserAction. getBadgeText](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/getBadgeText)   | | |
| [browserAction](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/setIcon) | `browserAction.setIcon` は保持されません。 <br/><br/> この `imageData` パラメーターはサポートされていません。 <br/><br/> `path` は必須のパラメーターです。| |
| [browserAction](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/getTitle) | | |
| [browserAction のタイトル](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/setTitle) | | |

## contextMenus

次の `contextMenus` api がサポートされています。

| API                    | 既知の問題 | Chrome の非互換性
|------------------------|--------------|----------------------|
| [contextMenus](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus)  |  | |
| [Contextmenus](https://developer.mozilla.org/Add-ons/WebExtensions/API/contextMenus/ContextType) | `"page_action"` `ContextType` ページアクションのコンテキストメニューには表示されません。| Microsoft Edge では、をサポートしていません `"launcher"` `ContextType` 。|
| [コンテキストメニューを作成する](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/create)    | 拡張子にが指定されていない場合は、生成された `contextmenuid` 固有のもので `id` はありません。 | |
| [コンテキストメニュー。 onClicked](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/onClicked) | | |
| [コンテキストメニューを削除します。](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/remove) | | |
| [removeAll](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/removeAll) | | |
| [contextMenus。更新](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/update) | | |

## cookie

次の `cookies` api がサポートされています。

| API                    | 既知の問題 | Chrome の非互換性
|------------------------|--------------|----------------------|
| [cookie](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/cookies)  |  | |
| [クッキー。 get](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/get)    |  | |
| [getAll](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/getAll) |   | URL が指定されていない場合、cookie は現在開かれているタブ内の Url に対してのみ取得されます。 Chrome では、これにより、ユーザーのコンピューター上のすべての cookie が取得されます。 |
| [getAllCookieStores](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/getAllCookieStores)  | | ID が "0" の既定の cookie ストアを常に返します。 すべての cookie はこのストアに属しています。 |
| [onChanged](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/onChanged)    | | サポートされません。 |
| [cookies。削除](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/remove) |  | |
| [クッキー。設定](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/set)    |  | |



## 補助

次の `extension` api がサポートされています。

| API                                   | 既知の問題 | Chrome の非互換性
|---------------------------------------|----------------------------------------------------------|-------------|
[補助](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/extension) | | |
[拡張子. getBackgroundPage](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/extension/getBackgroundPage) | | |
[拡張子 getURL](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/extension/getURL) | | |
[拡張機能の getViews](https://developer.mozilla.org/Add-ons/WebExtensions/API/extension/getViews) | | |
[拡張子 isAllowedIncognitoAccess](https://developer.mozilla.org/Add-ons/WebExtensions/API/extension/isAllowedIncognitoAccess) | | | 
[extension.inIncognitoContext](https://developer.mozilla.org/Add-ons/WebExtensions/API/extension/inIncognitoContext) | | | 



## プロパティー

次の `i18n` api がサポートされています。

API | 既知の問題 | Chrome の非互換性
:------| :-------- | :---------------------
[プロパティー](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/i18n) | | |
[i18n の言語](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/i18n/getAcceptLanguages) | | |
[getMessage](https://developer.mozilla.org/Add-ons/WebExtensions/API/i18n/getMessage) | `i18n.getMessage` 無効なキーを使うと、エラーが発生することなく、例外がスローされます。 <br/><br/> `i18n.getMessage` 引数には文字列が必要ですが、int または例外をスローすることもできます。 | |
[getUILanguage](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/i18n/getUILanguage) | | |

## アイドル

次の `idle` api がサポートされています。

API | 既知の問題 | Chrome の非互換性
:------| :-------- | :---------------------
[アイドル](https://developer.mozilla.org/Add-ons/WebExtensions/API/idle) | | |
[setDetectionInterval](https://developer.mozilla.org/Add-ons/WebExtensions/API/idle/setDetectionInterval) | | |
[idle 状態](https://developer.mozilla.org/Add-ons/WebExtensions/API/idle/queryState) | | |

## 通知

次の `notifications` api がサポートされています。

API | 既知の問題 | Chrome の非互換性
:------| :-------- | :---------------------
[通知](https://developer.mozilla.org/Add-ons/WebExtensions/API/notifications) | | |
[通知.NotificationOptions](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/NotificationOptions) | | |
[通知.TemplateType](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/TemplateType) | | |
[通知。クリア](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/clear) | | |
[通知。作成](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/create) | | |
[getAll](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/getAll) | | |
[通知。更新](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/update) | | |
[onButtonClicked](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/onButtonClicked) | | |
[通知。 onClicked](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/onClicked) | | |
[通知。 onClosed](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/onClosed) | | |
通知。 onPermissionLevelChanged | | |
通知。 getPermissionLevel | | |

## Page アクション

次の `pageAction` api がサポートされています。

API | 既知の問題 | Chrome の非互換性
:------------ | :------------- | :--------------------
[Page アクション](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction) | | |
[pageAction。 getPopup](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/getPopup) | | |
[getTitle](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/getTitle) | | |
[Page アクション。非表示](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/hide) | | |
[pageAction. onClicked](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/onClicked) | | |
[setIcon](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/setIcon) | | この `imageData` パラメーターはサポートされていません。 <br/><br/> `path` は必須のパラメーターです。 |
[pageAction. setPopup](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/setPopup) | | |
[pageAction. setTitle](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/setTitle) | | |
[[ページ] アクション](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/show) | | |



## 言語

次の `runtime` api がサポートされています。

API | 既知の問題 | Chrome の非互換性
:------------ | :------------- | :-------------------
[言語](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime) | | |
[runtime. 切断](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/Port) | | |
[onDisconnect](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/Port) | | |
[postMessage](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/Port) | | |
[runtime。接続](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connect) | | |
[runtime Native](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative) | | |
[runtime.id](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/id) | | |
[runtime. getBackgroundPage](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/getBackgroundPage) | | |
[実行時の getManifest](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/getManifest) | | |
[getURL](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/getURL) | | |
[lastError](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/lastError) | | |
[runtime。再読み込み](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/reload) | | |
[runtime](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendMessage) | Microsoft Edge 拡張機能のページを使用して、 `runtime.sendMessage` / `onMessage` メッセージを自分自身に送信することができます。 <br/><br/> `runtime.sendmessage` は、サイトページからはサポートされません。 | Microsoft Edge では、このパラメーターはサポートされていません `options` 。|
[sendNativeMessage](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) | | |
[setUninstallUrl](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/setUninstallUrl) | | |
[実行時。 onConnect](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/onConnect) | | |
[インストールされた onInstalled](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/onInstalled) | | |
[onMessage](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/onMessage) | `tab` イベントのオブジェクト `runtime.onMessage` は、完全には実装されていません。 | `MessageSender.tlsChannelId` Microsoft Edge ではサポートされていません。|

## ストレージ

次の `storage` api がサポートされています。

API | 既知の問題 | Chrome の非互換性
:------------ | :------------- | :------------------------
[ストレージ](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/storage) |  | |
[.local. get](https://developer.mozilla.org/Add-ons/WebExtensions/API/Storage/StorageArea/get)  | | |
[保存します。削除](https://developer.mozilla.org/Add-ons/WebExtensions/API/Storage/StorageArea/remove)  | | |
[設定](https://developer.mozilla.org/Add-ons/WebExtensions/API/Storage/StorageArea/set)  | | |
[.local。クリア](https://developer.mozilla.org/Add-ons/WebExtensions/API/Storage/StorageArea/clear) | | |
[ローカルの getBytesInUse](https://developer.mozilla.org/Add-ons/WebExtensions/API/Storage/StorageArea/getBytesInUse) | | `storage.local` データは Chrome とは異なる形式で保持されるため、呼び出し時に別の値が返され `storage.local.getBytesInUse` ます。  <br/><br/>例: `storage.local.set({ "k": { "s": "âas" } }` Chrome と50で Microsoft Edge で13という値を返します。|
[保存します。取得](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/storage/StorageArea/get) | "マニフェスト" フィールドと "マニフェスト" フィールドの合計文字数が `name` `author` 31 文字を超える場合、 `storage.sync` 名前空間は機能しないことがあります。 | |
[ストレージ. 同期の削除](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/storage/StorageArea/remove) | | |
[設定します。](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/storage/StorageArea/set) | | |
[onChanged](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/storage/onChanged) | | |

## タブ

次の `tabs` api がサポートされています。

API | 既知の問題 | Chrome の非互換性
:------------ | :------------- | :----------------
[タブ](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs) | | |
[captureVisibleTab](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/captureVisibleTab) | | |
[タブ。作成](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/create) | | `selected`、 `pinned` 、および `openerTabId` はサポートされていません。 |
[タブの言語](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/detectLanguage) | | |
[tabs.executeScript](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/executeScript) | `runAt` は無視されますが、オンになっています。 特定のフレームでのスクリプトの実行は、まだサポートされていません。 | |
[タブ。 get](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/get) | [オプション] ページでは、タブが表示されない場合、この呼び出しは失敗します。 | |
[tabs Current](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/getCurrent) | | |
[tabs Css](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/insertCSS) | `runAt` は無視されますが、オンになっています。 | `cssOrigin` はサポートされていません。 |
[タブを有効にします。](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onActivated) | | |
[tabs 添付](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onAttached) | | |
[作成されたタブ](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onCreated) | | |
[タブ。切断](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs) | | |
[タブが削除されました](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onRemoved) | | |
[タブ。上書き](https://developer.mozilla.org/Add-ons/WebExtensions/API/tabs/onReplaced) | | |
[onUpdated](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onUpdated) | アンインストール/再インストール後、Microsoft Edge が再起動されるまで、URL は受信されません。 | |
[タブ。クエリ](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/query) | `pinned`、 `audible` 、および `muted` はまだサポートされていません。 <br/><br/> `"popup"` `windowType` はまだサポートされていません。 | `highlighted` はサポートされていません。 <br/><br/> `"panel"`、 `"app"` 、および `"devtools"` `windowType` はサポートされていません。 |
[タブ。再読み込み](https://developer.mozilla.org/Add-ons/WebExtensions/API/tabs/reload) | | Microsoft Edge では、約束はサポートされていません。 |
[タブ。削除](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/remove) | | |
[tabs](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/sendMessage) | メッセージ特定のフレームはまだサポートされていません。 `tabs.sendMessage` [ `runtime.onMessage` 受信] タブにリスナーが表示されていない場合は、タブ更新後に応答を送信しません。 | |
[タブ.見出し](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/Tab) | `audible`、、、、 `mutedInfo` `inPrivate` `width` および `height` プロパティはまだサポートされていません。 | `openerTabId`、 `selected` 、および `highlighted` プロパティはサポートされていません。 |
[タブ。更新](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/update) | `pinned` また、 `muted` まだサポートされていません。 | `highlighted` サポートされ `selected` ていません。 |


## Web ナビゲーション

次の `webNavigation` api がサポートされています。


| API                                                                                                                                                           | 既知の問題                                | Chrome の非互換性                                                                                                    |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------|
| [Web ナビゲーション](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation)                                                     | タブ id が正しくありません。                      | フィルター処理、遷移の型、および遷移 Tion修飾子はサポートされていません。 <br/><br/> タブについては、すべて `processIds` 同じです。 |
| [getAllFrames](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/getAllFrames)                           | オブジェクト間の要素は含まれません。 |                                                                                                                             |
| [webNavigation。 getFrame](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/getFrame)                                   |                                             |                                                                                                                             |
| [onBeforeNavigate](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onBeforeNavigate)                   |                                             |                                                                                                                             |
| [webNavigation。 onCommitted](https://developer.mozilla.org/Add-ons/WebExtensions/API/webNavigation/onCommitted)                                           |                                             |                                                                                                                             |
| [webNavigation. onCompleted](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onCompleted)                             |                                             |                                                                                                                             |
| [webNavigation のターゲット](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onCreatedNavigationTarget) |                                             |                                                                                                                             |
| [webNavigation。 onDOMContentLoaded](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onDOMContentLoaded)               |                                             |                                                                                                                             |
| [webNavigation。 onErrorOccurred 発生しました](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onErrorOccurred)                     |                                             |                                                                                                                             |
| [webNavigation Statestateupdated](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onHistoryStateUpdated)         |                                             |                                                                                                                             |
| [webNavigation: onReferenceFragmentUpdated](https://developer.mozilla.org/Add-ons/WebExtensions/API/webNavigation/onReferenceFragmentUpdated)            |                                             |                                                                                                                             |
| [webNavigation は置き換えられました](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onTabReplaced)                         |                                             | サポートされません。                                                                                                              |
| [Web ナビゲーションの種類](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/TransitionType)                       |                                             |                                                                                                                             |
| [Web ナビゲーションの修飾子](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/TransitionQualifier)             |                                             |                                                                                                                             |

## webRequest

次の `webRequest` api がサポートされています。

API | 既知の問題 | Chrome の非互換性
:------ | :----- | :-------
[webRequest](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest) | `webRequest` 同期の場合はサポートされません `XmlHttpRequests` 。 | オプション、背景、ポップアップページなどの拡張機能からのネットワーク要求はサポートされていません。<br/><br/> および要素からのネットワーク要求 `<object>` `<embed>` はサポートされていません。<br/><br/> キャッシュされた要求に対してヘッダーを変更することはできません。  |
[ハンドラーの変更](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/handlerBehaviorChanged) | | ハンドラーの変更は、Microsoft Edge で自動的に処理されます。<br/><br/>この呼び出しを行っても効果はありません。  |
[onAuthRequired](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onAuthRequired) | | |
[onBeforeRedirect](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onBeforeRedirect) | | |
[onBeforeRequest](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onBeforeRequest) | | `requestBody` はサポートされていません。 |
[onBeforeSendHeaders](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onBeforeSendHeaders) | | |
[onCompleted](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onCompleted) | | |
[onErrorOccurred](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onErrorOccurred) | | |
[onHeadersReceived](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onHeadersReceived) | |  |
[onResponseStarted 開始されました](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onResponseStarted) | |  |
[onSendHeaders](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onSendHeaders) | | |

## windows

次の `windows` api がサポートされています。


| API                                                                                                                               | 既知の問題                                                   | Chrome の非互換性                                                                                        |
|:----------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------|
| [windows](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows)                                     |                                                                | `Window` Microsoft Edge では、オブジェクトはプロパティをサポートしていません `alwaysOnTop` 。 <br/><br/>InPrivate はサポートされていません。 |
| [窓.CreateType](https://developer.mozilla.org/Add-ons/WebExtensions/API/windows/CreateType)                            |                                                                | `"panel"` `"detached_panel"`Microsoft Edge ではサポートされていません。                                           |
| [windows. 作成](https://developer.mozilla.org/Add-ons/WebExtensions/API/windows/create)                                    |                                                                | `tabId` タブの切断のパラメーターはサポートされていません。                                                       |
| [windows. get](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/get)                             |                                                                |                                                                                                                 |
| [getAll](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/getAll)                       | `windows.getAll({populate: true})` プロパティが見つかりません `tabs` 。 |                                                                                                                 |
| [windows getCurrent](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/getCurrent)               |                                                                |                                                                                                                 |
| [windows getLastFocused](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/getLastFocused)       |                                                                |                                                                                                                 |
| [windows. 更新](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/update)                       | Position の指定はサポートされていません。                          | `"minimized"`/`"maximized"`/`"fullscreen"``drawAttention`Microsoft Edge ではサポートされていません。             |
| [windows onCreated](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/onCreated)                 |                                                                | `WindowType` フィルターはサポートされていません。                                                                           |
| [onFocusChanged](https://developer.mozilla.org/Add-ons/WebExtensions/API/windows/onFocusChanged)                    |                                                                | `WindowType` フィルターはサポートされていません。                                                                           |
| [窓.WindowState](https://developer.mozilla.org/Add-ons/WebExtensions/API/windows/WindowState)                          | `"minimized"`、 `"maximized"` `"fullscreen"` はサポートされていません。 | `"docked"` Microsoft Edge ではサポートされていません。                                                                  |
| [窓.WindowType](https://developer.mozilla.org/Add-ons/WebExtensions/API/windows/WindowType)                            |                                                                | `"panel"`、 `"app"` 、および `"devtools"` は Microsoft Edge でサポートされていません。                                       |
| [窓.WINDOW_ID_CURRENT](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/WINDOW_ID_CURRENT) |                                                                |                                                                                                                 |
| [窓.WINDOW_ID_NONE](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/WINDOW_ID_NONE)       |                                                                |                                                                                                                 |
