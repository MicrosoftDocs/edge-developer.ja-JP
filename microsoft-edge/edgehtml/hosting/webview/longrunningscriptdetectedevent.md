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
# <a name="longrunningscriptdetectedevent-object"></a><span data-ttu-id="5b3a3-104">LongRunningScriptDetectedEvent オブジェクト</span><span class="sxs-lookup"><span data-stu-id="5b3a3-104">LongRunningScriptDetectedEvent object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="5b3a3-105">[MSWebViewLongRunningScriptDetected の情報を提供します](../webview/index.md#mswebviewlongrunningscriptdetected)。</span><span class="sxs-lookup"><span data-stu-id="5b3a3-105">Provides information for [MSWebViewLongRunningScriptDetected](../webview/index.md#mswebviewlongrunningscriptdetected).</span></span>  

## <a name="properties"></a><span data-ttu-id="5b3a3-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5b3a3-106">Properties</span></span>  

### <a name="executiontime"></a><span data-ttu-id="5b3a3-107">executionTime</span><span class="sxs-lookup"><span data-stu-id="5b3a3-107">executionTime</span></span>  

<span data-ttu-id="5b3a3-108">Webview 要素が長時間実行されている[](../webview/index.md)スクリプトを実行しているミリ秒数を取得します。</span><span class="sxs-lookup"><span data-stu-id="5b3a3-108">Gets the number of milliseconds that the [webview](../webview/index.md) element has been executing a long-running script.</span></span>  

```javascript
var executionTime = LongRunningScriptDetectedEvent.executionTime;
```  

#### <a name="property-value"></a><span data-ttu-id="5b3a3-109">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="5b3a3-109">Property value</span></span>  

<span data-ttu-id="5b3a3-110">種類: **long**</span><span class="sxs-lookup"><span data-stu-id="5b3a3-110">Type: **long**</span></span>  

### <a name="stoppagescriptexecution"></a><span data-ttu-id="5b3a3-111">stopPageScriptExecution</span><span class="sxs-lookup"><span data-stu-id="5b3a3-111">stopPageScriptExecution</span></span>  

<span data-ttu-id="5b3a3-112">Webview 要素で実行されている長時間実行されるスクリプト [を停止](../webview/index.md) します。</span><span class="sxs-lookup"><span data-stu-id="5b3a3-112">Stops a long-running script executing in the [webview](../webview/index.md) element.</span></span>  

```javascript
var stopPageScriptExecution = LongRunningScriptDetectedEvent.stopPageScriptExecution;
```  

#### <a name="property-value"></a><span data-ttu-id="5b3a3-113">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="5b3a3-113">Property value</span></span>  

<span data-ttu-id="5b3a3-114">型: **ブール型 (Boolean)**</span><span class="sxs-lookup"><span data-stu-id="5b3a3-114">Type: **Boolean**</span></span>  
