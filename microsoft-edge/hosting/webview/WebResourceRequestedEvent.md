---
description: HTTP 要求が行われたときに発生するイベント。
title: WebResourceRequestedEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 3d2bb54cc5d60aec5391f0e3fdd427c8ba8a3dab
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10751983"
---
# WebResourceRequestedEvent オブジェクト  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

HTTP 要求が行われたときに発生するイベント。  

## プロパティ  

### 引数  

リソース要求に関する情報。  これは[WebViewControlWebResourceRequestedEventArgs](/uwp/api/windows.web.ui.webviewcontrolwebresourcerequestedeventargs)のようなものです。  

このプロパティは読み取り専用です。  

```javascript
var args = webResourceRequestedEventArgs.args;
var request = args.request;
```  

#### プロパティ値  

種類: **any**  
