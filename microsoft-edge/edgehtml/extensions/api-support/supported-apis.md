---
description: 現在および将来の API と既知の問題/Chrome の互換性に関する情報を検索します。
title: 拡張機能 - サポートされている API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, Web 開発, html, css, javascript, 開発者
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: b8cf13f42c99779f23eaa7b941093752fb25b207
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235047"
---
# サポートされる API  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

サポートされている API メンバーの詳細な一覧を次に示します。 拡張機能プラットフォームの開発は進行中なので、更新プログラムを頻繁に確認してください。

> [!NOTE]
>  - Microsoft Edge の場合、すべての拡張 API は名前空間の下にあります 。例: `browser` `browser.browserAction.disable()`
>  - Microsoft Edge 拡張機能 API は、promise ではなくコールバックを使用します。


## 包括的な問題

次の既知の問題は拡張機能プラットフォーム全体に及び、近い将来に修正される予定です。

- CSS プロパティを使用する場合、使用する絶対 URL は `url()` `ms-browser-extension://` Chrome の場合と同様に機能しません。 この問題を回避するには、代わりに(ルート拡張ディレクトリから始まる) リソースへの相対パスを使用します。
- `window.open()` 拡張機能のバックグラウンド スクリプトでは動作しません。 代わりに `browser.windows.create()` 使用してください。
- 共有 Cookie はサポートされています。ただし、拡張機能のバックグラウンド スクリプトは、拡張機能を有効にする前に、タブで設定されたセッション Cookie にアクセスできません。 この問題は、永続的な Cookie には影響を及ぼします。
- サポートされていないアクセス許可だけが拡張機能に対して指定されている場合(例: `activeTab`をクリックすると、拡張機能がアンインストールされ、「拡張機能に問題が発生したので、再インストールする必要がありました。 もう一度有効にする必要があります。"
- 非表示のアンカー タグを使用してダウンロードをトリガーすると、バックグラウンド スクリプトから失敗します。 これは、代わりに拡張機能ページから行う必要があります。


## ブックマーク

次の `bookmarks` API がサポートされています。

| API                                   | 既知の問題                                             | Chrome の非互換性
|---------------------------------------|----------------------------------------------------------|--------------------------|
| [ブックマーク](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks) | | |
| [bookmarks.create](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/create) | | |
| [bookmarks.remove](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/remove) | | |
| [bookmarks.getTree](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/getTree) |  | |
| [bookmarks.move](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/move) | | |
| [bookmarks.removeTree](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/removeTree) | | |
| [bookmarks.update](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/update)            | | |


## browserAction

次の `browserAction` API がサポートされています。

| API                                   | 既知の問題                                             | Chrome の非互換性
|---------------------------------------|----------------------------------------------------------|--------------------------|
| [browserAction](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction) | | |
| [browserAction.disable](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/disable) | | |
| [browserAction.enable](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/enable) | | |
| [browserAction.getBadgeBackgroundColor](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/getBadgeBackgroundColor) |  | |
| [browserAction.setBadgeBackgroundColor](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/setBadgeBackgroundColor) | | |
| [browserAction.onClicked](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/onClicked) | | |
| [browserAction.setBadgeText](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/setBadgeText)            | | |
| [browserAction.setPopup](https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/setPopup)  | | |
| [browserAction.getBadgeText](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/getBadgeText)   | | |
| [browserAction.setIcon](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/setIcon) | `browserAction.setIcon` は保持されません。 <br/><br/> この `imageData` パラメーターはサポートされていません。 <br/><br/> `path` は必須パラメーターです。| |
| [browserAction.getTitle](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/getTitle) | | |
| [browserAction.setTitle](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/setTitle) | | |

## contextMenus

次の `contextMenus` API がサポートされています。

| API                    | 既知の問題 | Chrome の非互換性
|------------------------|--------------|----------------------|
| [contextMenus](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus)  |  | |
| [contextMenus.ContextType](https://developer.mozilla.org/Add-ons/WebExtensions/API/contextMenus/ContextType) | `"page_action"` `ContextType` は、ページ アクションのコンテキスト メニューに表示されます。| Microsoft Edge では、次の機能はサポートされていません `"launcher"` `ContextType` 。|
| [contextMenus.create](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/create)    | 拡張機能が提供しない場合、 `contextmenuid` 生成された `id` 値は一意ではありません。 | |
| [contextMenus.onClicked](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/onClicked) | | |
| [contextMenus.remove](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/remove) | | |
| [contextMenus.removeAll](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/removeAll) | | |
| [contextMenus.update](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/update) | | |

## cookie

次の `cookies` API がサポートされています。

| API                    | 既知の問題 | Chrome の非互換性
|------------------------|--------------|----------------------|
| [cookie](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/cookies)  |  | |
| [cookies.get](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/get)    |  | |
| [cookies.getAll](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/getAll) |   | URL が指定されていない場合、Cookie は現在開いているタブの URL に対してだけ取得されます。 Chrome では、ユーザーのコンピューター上のすべての Cookie が取得されます。 |
| [cookies.getAllCookieStores](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/getAllCookieStores)  | | ID が "0" の同じ既定の Cookie ストアを常に返します。 すべての Cookie は、このストアに属しています。 |
| [cookies.onChanged](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/onChanged)    | | サポートされません。 |
| [cookies.remove](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/remove) |  | |
| [cookies.set](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/set)    |  | |



## extension

次の `extension` API がサポートされています。

| API                                   | 既知の問題 | Chrome の非互換性
|---------------------------------------|----------------------------------------------------------|-------------|
[extension](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/extension) | | |
[extension.getBackgroundPage](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/extension/getBackgroundPage) | | |
[extension.getURL](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/extension/getURL) | | |
[extension.getViews](https://developer.mozilla.org/Add-ons/WebExtensions/API/extension/getViews) | | |
[extension.isAllowedIncognitoAccess](https://developer.mozilla.org/Add-ons/WebExtensions/API/extension/isAllowedIncognitoAccess) | | | 
[extension.inIncognitoContext](https://developer.mozilla.org/Add-ons/WebExtensions/API/extension/inIncognitoContext) | | | 



## i18n

次の `i18n` API がサポートされています。

API | 既知の問題 | Chrome の非互換性
:------| :-------- | :---------------------
[i18n](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/i18n) | | |
[i18n.getAcceptLanguages](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/i18n/getAcceptLanguages) | | |
[i18n.getMessage](https://developer.mozilla.org/Add-ons/WebExtensions/API/i18n/getMessage) | `i18n.getMessage` キーが無効な場合、正常に失敗するのではなく、例外がスローされます。 <br/><br/> `i18n.getMessage` 引数は文字列を必要としますが、int を許可するか、例外をスローする必要があります。 | |
[i18n.getUILanguage](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/i18n/getUILanguage) | | |

## idle

次の `idle` API がサポートされています。

API | 既知の問題 | Chrome の非互換性
:------| :-------- | :---------------------
[idle](https://developer.mozilla.org/Add-ons/WebExtensions/API/idle) | | |
[idle.setDetectionInterval](https://developer.mozilla.org/Add-ons/WebExtensions/API/idle/setDetectionInterval) | | |
[idle.queryState](https://developer.mozilla.org/Add-ons/WebExtensions/API/idle/queryState) | | |

## 通知

次の `notifications` API がサポートされています。

API | 既知の問題 | Chrome の非互換性
:------| :-------- | :---------------------
[通知](https://developer.mozilla.org/Add-ons/WebExtensions/API/notifications) | | |
[通知。NotificationOptions](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/NotificationOptions) | | |
[通知。TemplateType](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/TemplateType) | | |
[notifications.clear](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/clear) | | |
[notifications.create](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/create) | | |
[notifications.getAll](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/getAll) | | |
[notifications.update](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/update) | | |
[notifications.onButtonClicked](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/onButtonClicked) | | |
[notifications.onClicked](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/onClicked) | | |
[notifications.onClosed](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/onClosed) | | |
notifications.onPermissionLevelChanged | | |
notifications.getPermissionLevel | | |

## pageAction

次の `pageAction` API がサポートされています。

API | 既知の問題 | Chrome の非互換性
:------------ | :------------- | :--------------------
[pageAction](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction) | | |
[pageAction.getPopup](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/getPopup) | | |
[pageAction.getTitle](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/getTitle) | | |
[pageAction.hide](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/hide) | | |
[pageAction.onClicked](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/onClicked) | | |
[pageAction.setIcon](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/setIcon) | | この `imageData` パラメーターはサポートされていません。 <br/><br/> `path` は必須パラメーターです。 |
[pageAction.setPopup](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/setPopup) | | |
[pageAction.setTitle](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/setTitle) | | |
[pageAction.show](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/show) | | |



## runtime

次の `runtime` API がサポートされています。

API | 既知の問題 | Chrome の非互換性
:------------ | :------------- | :-------------------
[runtime](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime) | | |
[runtime.port.disconnect](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/Port) | | |
[runtime.port.onDisconnect](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/Port) | | |
[runtime.port.postMessage](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/Port) | | |
[runtime.connect](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connect) | | |
[runtime.connectNative](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative) | | |
[runtime.id](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/id) | | |
[runtime.getBackgroundPage](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/getBackgroundPage) | | |
[runtime.getManifest](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/getManifest) | | |
[runtime.getURL](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/getURL) | | |
[runtime.lastError](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/lastError) | | |
[runtime.reload](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/reload) | | |
[runtime.sendMessage](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendMessage) | Microsoft Edge の拡張機能ページを使用 `runtime.sendMessage` / `onMessage` して、メッセージを自分自身に送信できます。 <br/><br/> `runtime.sendmessage` はサイト ページではサポートされていません。 | Microsoft Edge では、このパラメーターはサポート `options` されていません。|
[runtime.sendNativeMessage](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) | | |
[runtime.setUninstallUrl](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/setUninstallUrl) | | |
[runtime.onConnect](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/onConnect) | | |
[runtime.onInstalled](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/onInstalled) | | |
[runtime.onMessage](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/onMessage) | `tab` オブジェクトが `runtime.onMessage` 完全に実装されていません。 | `MessageSender.tlsChannelId` は Microsoft Edge ではサポートされていません。|

## ストレージ

次の `storage` API がサポートされています。

API | 既知の問題 | Chrome の非互換性
:------------ | :------------- | :------------------------
[ストレージ](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/storage) |  | |
[storage.local.get](https://developer.mozilla.org/Add-ons/WebExtensions/API/Storage/StorageArea/get)  | | |
[storage.local.remove](https://developer.mozilla.org/Add-ons/WebExtensions/API/Storage/StorageArea/remove)  | | |
[storage.local.set](https://developer.mozilla.org/Add-ons/WebExtensions/API/Storage/StorageArea/set)  | | |
[storage.local.clear](https://developer.mozilla.org/Add-ons/WebExtensions/API/Storage/StorageArea/clear) | | |
[storage.local.getBytesInUse](https://developer.mozilla.org/Add-ons/WebExtensions/API/Storage/StorageArea/getBytesInUse) | | `storage.local` data is persisted in a different format than Chrome, causing a different value to be returned when calling `storage.local.getBytesInUse` .  <br/><br/>例: `storage.local.set({ "k": { "s": "âas" } }` Chrome では 13、Microsoft Edge では 50 を返します。|
[storage.sync.get](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/storage/StorageArea/get) | マニフェスト フィールドとマニフェスト フィールドの文字の合計量が 31 文字を超えると、名前空間 `name` `author` `storage.sync` が機能しない可能性があります。 | |
[storage.sync.remove](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/storage/StorageArea/remove) | | |
[storage.sync.set](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/storage/StorageArea/set) | | |
[storage.onChanged](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/storage/onChanged) | | |

## tabs

次の `tabs` API がサポートされています。

API | 既知の問題 | Chrome の非互換性
:------------ | :------------- | :----------------
[tabs](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs) | | |
[tabs.captureVisibleTab](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/captureVisibleTab) | | |
[tabs.create](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/create) | | `selected`、 `pinned` サポート `openerTabId` されていません。 |
[tabs.detectLanguage](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/detectLanguage) | | |
[tabs.executeScript](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/executeScript) | `runAt` は無視されます。 特定のフレームでのスクリプトの実行はまだサポートされていません。 | |
[tabs.get](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/get) | [オプション] ページは、ウィンドウに表示されないタブについて尋ねると、この呼び出しに失敗します。 | |
[tabs.getCurrent](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/getCurrent) | | |
[tabs.insertCSS](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/insertCSS) | `runAt` は無視されます。 | `cssOrigin` はサポートされていません。 |
[tabs.onActivated](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onActivated) | | |
[tabs.onAttached](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onAttached) | | |
[tabs.onCreated](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onCreated) | | |
[tabs.onDetached](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs) | | |
[tabs.onRemoved](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onRemoved) | | |
[tabs.onReplaced](https://developer.mozilla.org/Add-ons/WebExtensions/API/tabs/onReplaced) | | |
[tabs.onUpdated](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onUpdated) | アンインストール/再インストール後、Microsoft Edge が再起動されるまで URL は受信されません。 | |
[tabs.query](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/query) | `pinned`、 `audible` および `muted` まだサポートされていません。 <br/><br/> `"popup"` `windowType` はサポートされていません。 | `highlighted` はサポートされていません。 <br/><br/> `"panel"`、 `"app"` サポート `"devtools"` `windowType` されていません。 |
[tabs.reload](https://developer.mozilla.org/Add-ons/WebExtensions/API/tabs/reload) | | Microsoft Edge では、Promise はサポートされていません。 |
[tabs.remove](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/remove) | | |
[tabs.sendMessage](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/sendMessage) | 特定のフレームのメッセージングはまだサポートされていません。 `tabs.sendMessage` 受信タブにリスナーが存在しない場合は、タブの更新後に応答 `runtime.onMessage` を送信しない。 | |
[タブ。Tab](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/Tab) | `audible`、 `mutedInfo` `inPrivate` `width` `height` およびプロパティはまだサポートされていません。 | `openerTabId`、 `selected` および `highlighted` プロパティはサポートされていません。 |
[tabs.update](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/update) | `pinned` まだ `muted` サポートされていません。 | `highlighted` サポート `selected` されていません。 |


## webNavigation

次の `webNavigation` API がサポートされています。


| API                                                                                                                                                           | 既知の問題                                | Chrome の非互換性                                                                                                    |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------|
| [webNavigation](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation)                                                     | タブ ID が正しくありません。                      | フィルター処理、TransitionTypes、TransitionQualifier はサポートされていません。 <br/><br/> タブの場合、すべて `processIds` 同じです。 |
| [webNavigation.getAllFrames](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/getAllFrames)                           | オブジェクト as-iframe 要素は含めではありません。 |                                                                                                                             |
| [webNavigation.getFrame](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/getFrame)                                   |                                             |                                                                                                                             |
| [webNavigation.onBeforeNavigate](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onBeforeNavigate)                   |                                             |                                                                                                                             |
| [webNavigation.onCommitted](https://developer.mozilla.org/Add-ons/WebExtensions/API/webNavigation/onCommitted)                                           |                                             |                                                                                                                             |
| [webNavigation.onCompleted](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onCompleted)                             |                                             |                                                                                                                             |
| [webNavigation.onCreatedNavigationTarget](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onCreatedNavigationTarget) |                                             |                                                                                                                             |
| [webNavigation.onDOMContentLoaded](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onDOMContentLoaded)               |                                             |                                                                                                                             |
| [webNavigation.onErrorOccurred](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onErrorOccurred)                     |                                             |                                                                                                                             |
| [webNavigation.onHistoryStateUpdated](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onHistoryStateUpdated)         |                                             |                                                                                                                             |
| [webNavigation.onReferenceFragmentUpdated](https://developer.mozilla.org/Add-ons/WebExtensions/API/webNavigation/onReferenceFragmentUpdated)            |                                             |                                                                                                                             |
| [webNavigation.onTabReplaced](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onTabReplaced)                         |                                             | サポートされません。                                                                                                              |
| [webNavigation.TransitionType](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/TransitionType)                       |                                             |                                                                                                                             |
| [webNavigation.TransitionQualifier](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/TransitionQualifier)             |                                             |                                                                                                                             |

## webRequest

次の `webRequest` API がサポートされています。

API | 既知の問題 | Chrome の非互換性
:------ | :----- | :-------
[webRequest](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest) | `webRequest` 同期ではサポートされていません `XmlHttpRequests` 。 | オプション、背景、ポップアップ ページなど、拡張機能からのネットワーク要求はサポートされていません。<br/><br/> ネットワーク要求と `<object>` 要素 `<embed>` はサポートされていません。<br/><br/> キャッシュされた要求に対してヘッダーを変更することはできません。  |
[handlerBehaviorChanged](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/handlerBehaviorChanged) | | ハンドラーの変更は、Microsoft Edge で自動的に処理されます。<br/><br/>これを呼び出す効果はありません。  |
[onAuthRequired](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onAuthRequired) | | |
[onBeforeRedirect](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onBeforeRedirect) | | |
[onBeforeRequest](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onBeforeRequest) | | `requestBody` はサポートされていません。 |
[onBeforeSendHeaders](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onBeforeSendHeaders) | | |
[onCompleted](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onCompleted) | | |
[onErrorOccurred](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onErrorOccurred) | | |
[onHeadersReceived](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onHeadersReceived) | |  |
[onResponseStarted](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onResponseStarted) | |  |
[onSendHeaders](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onSendHeaders) | | |

## windows

次の `windows` API がサポートされています。


| API                                                                                                                               | 既知の問題                                                   | Chrome の非互換性                                                                                        |
|:----------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------|
| [windows](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows)                                     |                                                                | `Window` オブジェクトは `alwaysOnTop` 、Microsoft Edge のプロパティをサポートしません。 <br/><br/>InPrivate はサポートされていません。 |
| [ウィンドウ。CreateType](https://developer.mozilla.org/Add-ons/WebExtensions/API/windows/CreateType)                            |                                                                | `"panel"` Microsoft `"detached_panel"` Edge ではサポートされていません。                                           |
| [windows.create](https://developer.mozilla.org/Add-ons/WebExtensions/API/windows/create)                                    |                                                                | `tabId` タブを削除するパラメーターはサポートされていません。                                                       |
| [windows.get](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/get)                             |                                                                |                                                                                                                 |
| [windows.getAll](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/getAll)                       | `windows.getAll({populate: true})` プロパティがありません `tabs` 。 |                                                                                                                 |
| [windows.getCurrent](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/getCurrent)               |                                                                |                                                                                                                 |
| [windows.getLastFocused](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/getLastFocused)       |                                                                |                                                                                                                 |
| [windows.update](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/update)                       | 位置の指定はサポートされていません。                          | `"minimized"`/`"maximized"`/`"fullscreen"` Microsoft `drawAttention` Edge ではサポートされていません。             |
| [windows.onCreated](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/onCreated)                 |                                                                | `WindowType` filter はサポートされていません。                                                                           |
| [windows.onFocusChanged](https://developer.mozilla.org/Add-ons/WebExtensions/API/windows/onFocusChanged)                    |                                                                | `WindowType` filter はサポートされていません。                                                                           |
| [ウィンドウ。WindowState](https://developer.mozilla.org/Add-ons/WebExtensions/API/windows/WindowState)                          | `"minimized"`、 `"maximized"` `"fullscreen"` サポートされていません。 | `"docked"` は Microsoft Edge ではサポートされていません。                                                                  |
| [ウィンドウ。WindowType](https://developer.mozilla.org/Add-ons/WebExtensions/API/windows/WindowType)                            |                                                                | `"panel"`、Microsoft Edge では `"app"` `"devtools"` サポートされていません。                                       |
| [ウィンドウ。WINDOW_ID_CURRENT](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/WINDOW_ID_CURRENT) |                                                                |                                                                                                                 |
| [ウィンドウ。WINDOW_ID_NONE](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/WINDOW_ID_NONE)       |                                                                |                                                                                                                 |
