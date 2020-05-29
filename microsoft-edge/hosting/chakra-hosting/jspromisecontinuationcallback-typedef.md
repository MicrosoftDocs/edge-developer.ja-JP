---
description: Promise 継続コールバック。
title: JsPromiseContinuationCallback Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 51a3fd02-9668-4cf7-bb0b-e1fd03b2528f
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 023d88af5ff82056d8f57453e0a53b91b34565a6
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569271"
---
# <span data-ttu-id="54fe7-103">JsPromiseContinuationCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="54fe7-103">JsPromiseContinuationCallback Typedef</span></span>
<span data-ttu-id="54fe7-104">Promise 継続コールバック。</span><span class="sxs-lookup"><span data-stu-id="54fe7-104">A promise continuation callback.</span></span>  
  
## <span data-ttu-id="54fe7-105">構文</span><span class="sxs-lookup"><span data-stu-id="54fe7-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsPromiseContinuationCallback)(  
  _In_ JsValueRef task,  
  _In_opt_ void *callbackState  
);  
```  
  
#### <span data-ttu-id="54fe7-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="54fe7-106">Parameters</span></span>  
 `task`  
  `callbackState`  
  
## <span data-ttu-id="54fe7-107">注釈</span><span class="sxs-lookup"><span data-stu-id="54fe7-107">Remarks</span></span>  
 <span data-ttu-id="54fe7-108">ホストでは、で promise 継続コールバックを指定でき `JsSetPromiseContinuationCallback` ます。</span><span class="sxs-lookup"><span data-stu-id="54fe7-108">The host can specify a promise continuation callback in `JsSetPromiseContinuationCallback`.</span></span> <span data-ttu-id="54fe7-109">スクリプトによって後で実行されるタスクが作成された場合、promise 継続コールバックはタスクと共に呼び出され、タスクは FIFO キューに入れて、現在のスクリプトの実行が完了したときに実行されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="54fe7-109">If a script creates a task to be run later, then the promise continuation callback will be called with the task and the task should be put in a FIFO queue, to be run when the current script is done executing.</span></span>  
  
 <span data-ttu-id="54fe7-110">この API は、EdgeHTML モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="54fe7-110">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="54fe7-111">要件</span><span class="sxs-lookup"><span data-stu-id="54fe7-111">Requirements</span></span>  
 <span data-ttu-id="54fe7-112">jsrt</span><span class="sxs-lookup"><span data-stu-id="54fe7-112">jsrt.h</span></span>  
  
## <span data-ttu-id="54fe7-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="54fe7-113">See Also</span></span>  
 [<span data-ttu-id="54fe7-114">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="54fe7-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)