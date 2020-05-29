---
description: ''
title: LongRunningScriptDetectedEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/10/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 6cf7af656531eea5046f7af44d4d43ff224d0f08
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569243"
---
# LongRunningScriptDetectedEvent オブジェクト

[MSWebViewLongRunningScriptDetected](../webview.md#mswebviewlongrunningscriptdetected)に関する情報を提供します。

## プロパティ

### executionTime

[Webview](../webview.md)要素が長時間実行されているスクリプトを実行しているミリ秒数を取得します。

```js
var executionTime = LongRunningScriptDetectedEvent.executionTime;
```

#### プロパティ値
種類: **long**

### stopPageScriptExecution
[Webview](../webview.md)要素で実行されている長時間実行されるスクリプトを停止します。

```js
var stopPageScriptExecution = LongRunningScriptDetectedEvent.stopPageScriptExecution;
```

#### プロパティ値
種類:**ブール**型