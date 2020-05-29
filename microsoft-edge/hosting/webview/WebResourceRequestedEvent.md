---
description: HTTP 要求が行われたときに発生するイベント。
title: WebResourceRequestedEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 79cff0d8fd68e3b5747008f343b5b46fb8093013
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10568756"
---
# WebResourceRequestedEvent オブジェクト

HTTP 要求が行われたときに発生するイベント。

## プロパティ

### 引数

リソース要求に関する情報。 これは[WebViewControlWebResourceRequestedEventArgs](/uwp/api/windows.web.ui.webviewcontrolwebresourcerequestedeventargs)のようなものです。

このプロパティは読み取り専用です。

```js
var args = webResourceRequestedEventArgs.args;
var request = args.request;
```

#### プロパティ値
種類: **any**

