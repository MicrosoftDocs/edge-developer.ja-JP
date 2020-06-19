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
# <span data-ttu-id="c169d-103">LongRunningScriptDetectedEvent オブジェクト</span><span class="sxs-lookup"><span data-stu-id="c169d-103">LongRunningScriptDetectedEvent object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="c169d-104">[MSWebViewLongRunningScriptDetected](../webview.md#mswebviewlongrunningscriptdetected)に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c169d-104">Provides information for [MSWebViewLongRunningScriptDetected](../webview.md#mswebviewlongrunningscriptdetected).</span></span>  

## <span data-ttu-id="c169d-105">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c169d-105">Properties</span></span>  

### <span data-ttu-id="c169d-106">executionTime</span><span class="sxs-lookup"><span data-stu-id="c169d-106">executionTime</span></span>  

<span data-ttu-id="c169d-107">[Webview](../webview.md)要素が長時間実行されているスクリプトを実行しているミリ秒数を取得します。</span><span class="sxs-lookup"><span data-stu-id="c169d-107">Gets the number of milliseconds that the [webview](../webview.md) element has been executing a long-running script.</span></span>  

```javascript
var executionTime = LongRunningScriptDetectedEvent.executionTime;
```  

#### <span data-ttu-id="c169d-108">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="c169d-108">Property value</span></span>  

<span data-ttu-id="c169d-109">種類: **long**</span><span class="sxs-lookup"><span data-stu-id="c169d-109">Type: **long**</span></span>  

### <span data-ttu-id="c169d-110">stopPageScriptExecution</span><span class="sxs-lookup"><span data-stu-id="c169d-110">stopPageScriptExecution</span></span>  

<span data-ttu-id="c169d-111">[Webview](../webview.md)要素で実行されている長時間実行されるスクリプトを停止します。</span><span class="sxs-lookup"><span data-stu-id="c169d-111">Stops a long-running script executing in the [webview](../webview.md) element.</span></span>  

```javascript
var stopPageScriptExecution = LongRunningScriptDetectedEvent.stopPageScriptExecution;
```  

#### <span data-ttu-id="c169d-112">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="c169d-112">Property value</span></span>  

<span data-ttu-id="c169d-113">種類:**ブール**型</span><span class="sxs-lookup"><span data-stu-id="c169d-113">Type: **Boolean**</span></span>  
