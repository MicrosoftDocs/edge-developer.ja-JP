---
description: Webview 機能を有効または無効にするプロパティを定義します。
title: MSWebViewSettings オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 147f852f8fbcb2a748c00b472814e9cc45b9c9da
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752179"
---
# MSWebViewSettings オブジェクト  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

[Webview](../webview.md)機能を有効または無効にするプロパティを定義します。  

## プロパティ  

### isIndexedDBEnabled  

[Webview](../webview.md)での IndexedDB の使用が許可されているかどうかを示す値を取得または設定します。  

```javascript
var isIndexedDBEnabled = MSWebViewSettings.isIndexedDBEnabled;
MSWebViewSettings.isIndexedDBEnabled = isIndexedDBEnabled;
```  

#### プロパティ値  

種類:**ブール**型  

**Webview**で IndexedDB が許可されている場合は**True** 。それ以外の場合は**false**です。  

### isJavaScriptEnabled  

[Webview](../webview.md)で JavaScript の使用が許可されているかどうかを示す値を取得または設定します。  

```javascript
var isJavaScriptEnabled = MSWebViewSettings.isJavaScriptEnabled;
MSWebViewSettings.isJavaScriptEnabled = isJavaScriptEnabled;
```  

#### プロパティ値  

種類:**ブール**型  

**True**[Webview](../webview.md)では JavaScript が許可されています。それ以外の場合は**false**です。  

### isScriptNotifyAllowed  

[Webview](../webview.md)で[scriptnotifyevent](ScriptNotifyEvent.md)の使用が許可されているかどうかを示す値を取得または設定します。  

```javascript
var isScriptNotifyAllowed = MSWebViewSettings.isScriptNotifyAllowed;
MSWebViewSettings.isScriptNotifyAllowed = isScriptNotifyAllowed;
```  

#### プロパティ値  

種類:**ブール**型  

[Webview](../webview.md)では、 **True** [scriptnotifyevent](ScriptNotifyEvent.md)が許可されています。それ以外の場合は**false**です。  
