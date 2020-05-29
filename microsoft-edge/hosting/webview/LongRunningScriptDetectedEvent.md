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
# <span data-ttu-id="479ba-103">LongRunningScriptDetectedEvent オブジェクト</span><span class="sxs-lookup"><span data-stu-id="479ba-103">LongRunningScriptDetectedEvent object</span></span>

<span data-ttu-id="479ba-104">[MSWebViewLongRunningScriptDetected](../webview.md#mswebviewlongrunningscriptdetected)に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="479ba-104">Provides information for [MSWebViewLongRunningScriptDetected](../webview.md#mswebviewlongrunningscriptdetected).</span></span>

## <span data-ttu-id="479ba-105">プロパティ</span><span class="sxs-lookup"><span data-stu-id="479ba-105">Properties</span></span>

### <span data-ttu-id="479ba-106">executionTime</span><span class="sxs-lookup"><span data-stu-id="479ba-106">executionTime</span></span>

<span data-ttu-id="479ba-107">[Webview](../webview.md)要素が長時間実行されているスクリプトを実行しているミリ秒数を取得します。</span><span class="sxs-lookup"><span data-stu-id="479ba-107">Gets the number of milliseconds that the [webview](../webview.md) element has been executing a long-running script.</span></span>

```js
var executionTime = LongRunningScriptDetectedEvent.executionTime;
```

#### <span data-ttu-id="479ba-108">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="479ba-108">Property value</span></span>
<span data-ttu-id="479ba-109">種類: **long**</span><span class="sxs-lookup"><span data-stu-id="479ba-109">Type: **long**</span></span>

### <span data-ttu-id="479ba-110">stopPageScriptExecution</span><span class="sxs-lookup"><span data-stu-id="479ba-110">stopPageScriptExecution</span></span>
<span data-ttu-id="479ba-111">[Webview](../webview.md)要素で実行されている長時間実行されるスクリプトを停止します。</span><span class="sxs-lookup"><span data-stu-id="479ba-111">Stops a long-running script executing in the [webview](../webview.md) element.</span></span>

```js
var stopPageScriptExecution = LongRunningScriptDetectedEvent.stopPageScriptExecution;
```

#### <span data-ttu-id="479ba-112">プロパティ値</span><span class="sxs-lookup"><span data-stu-id="479ba-112">Property value</span></span>
<span data-ttu-id="479ba-113">種類:**ブール**型</span><span class="sxs-lookup"><span data-stu-id="479ba-113">Type: **Boolean**</span></span>