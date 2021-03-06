---
description: LongRunningScriptDetectedEvent オブジェクト
title: LongRunningScriptDetectedEvent オブジェクト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: Webview、Windows 10 アプリ、uwp、エッジ
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5f5eb3230e46ee2cd7926b21f6526e512a7a0322
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397943"
---
# <a name="longrunningscriptdetectedevent-object"></a>LongRunningScriptDetectedEvent オブジェクト  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

[MSWebViewLongRunningScriptDetected の情報を提供します](../webview/index.md#mswebviewlongrunningscriptdetected)。  

## <a name="properties"></a>プロパティ  

### <a name="executiontime"></a>executionTime  

Webview 要素が長時間実行されている[](../webview/index.md)スクリプトを実行しているミリ秒数を取得します。  

```javascript
var executionTime = LongRunningScriptDetectedEvent.executionTime;
```  

#### <a name="property-value"></a>プロパティ値  

種類: **long**  

### <a name="stoppagescriptexecution"></a>stopPageScriptExecution  

Webview 要素で実行されている長時間実行されるスクリプト [を停止](../webview/index.md) します。  

```javascript
var stopPageScriptExecution = LongRunningScriptDetectedEvent.stopPageScriptExecution;
```  

#### <a name="property-value"></a>プロパティ値  

型: **ブール型 (Boolean)**  
