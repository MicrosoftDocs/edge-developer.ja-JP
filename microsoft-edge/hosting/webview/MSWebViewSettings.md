---
description: Webview 機能を有効または無効にするプロパティを定義します。
title: MSWebViewSettings オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/10/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 0e164e7eb44edc636201f283ec4bbe866a122b8e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569234"
---
# MSWebViewSettings オブジェクト

[Webview](../webview.md)機能を有効または無効にするプロパティを定義します。

## プロパティ

### isIndexedDBEnabled

[Webview](../webview.md)での IndexedDB の使用が許可されているかどうかを示す値を取得または設定します。

```js
var isIndexedDBEnabled = MSWebViewSettings.isIndexedDBEnabled;
MSWebViewSettings.isIndexedDBEnabled = isIndexedDBEnabled;
```

#### プロパティ値
種類:**ブール**型

**Webview**で IndexedDB が許可されている場合は**True** 。それ以外の場合は**false**です。 

### isJavaScriptEnabled

[Webview](../webview.md)で JavaScript の使用が許可されているかどうかを示す値を取得または設定します。

```js
var isJavaScriptEnabled = MSWebViewSettings.isJavaScriptEnabled;
MSWebViewSettings.isJavaScriptEnabled = isJavaScriptEnabled;
```

#### プロパティ値
種類:**ブール**型

**True**[Webview](../webview.md)では JavaScript が許可されています。それ以外の場合は**false**です。 

### isScriptNotifyAllowed

[Webview](../webview.md)で[scriptnotifyevent](ScriptNotifyEvent.md)の使用が許可されているかどうかを示す値を取得または設定します。

```js
var isScriptNotifyAllowed = MSWebViewSettings.isScriptNotifyAllowed;
MSWebViewSettings.isScriptNotifyAllowed = isScriptNotifyAllowed;
```

#### プロパティ値
種類:**ブール**型

[Webview](../webview.md)では、 **True** [scriptnotifyevent](ScriptNotifyEvent.md)が許可されています。それ以外の場合は**false**です。 
