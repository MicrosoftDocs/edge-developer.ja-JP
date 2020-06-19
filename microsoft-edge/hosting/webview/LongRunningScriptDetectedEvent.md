---
description: ''
title: LongRunningScriptDetectedEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview、windows 10 アプリ、uwp、edge
ms.openlocfilehash: 5fe90495b83ab8f95ee594d3400c8c1a26f0547e
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752152"
---
# LongRunningScriptDetectedEvent オブジェクト  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

[MSWebViewLongRunningScriptDetected](../webview.md#mswebviewlongrunningscriptdetected)に関する情報を提供します。  

## プロパティ  

### executionTime  

[Webview](../webview.md)要素が長時間実行されているスクリプトを実行しているミリ秒数を取得します。  

```javascript
var executionTime = LongRunningScriptDetectedEvent.executionTime;
```  

#### プロパティ値  

種類: **long**  

### stopPageScriptExecution  

[Webview](../webview.md)要素で実行されている長時間実行されるスクリプトを停止します。  

```javascript
var stopPageScriptExecution = LongRunningScriptDetectedEvent.stopPageScriptExecution;
```  

#### プロパティ値  

種類:**ブール**型  
