---
description: Promise 継続コールバック。
title: JsPromiseContinuationCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 51a3fd02-9668-4cf7-bb0b-e1fd03b2528f
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: da121d186cd9d0ab1a9770be08c9a92b52cf3366
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235088"
---
# <span data-ttu-id="2f888-103">JsPromiseContinuationCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="2f888-103">JsPromiseContinuationCallback Typedef</span></span>

<span data-ttu-id="2f888-104">Promise 継続コールバック。</span><span class="sxs-lookup"><span data-stu-id="2f888-104">A promise continuation callback.</span></span>  
  
## <span data-ttu-id="2f888-105">構文</span><span class="sxs-lookup"><span data-stu-id="2f888-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsPromiseContinuationCallback)(  
  _In_ JsValueRef task,  
  _In_opt_ void *callbackState  
);  
```  
  
#### <span data-ttu-id="2f888-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2f888-106">Parameters</span></span>  
 `task`  
  `callbackState`  
  
## <span data-ttu-id="2f888-107">注釈</span><span class="sxs-lookup"><span data-stu-id="2f888-107">Remarks</span></span>  
 <span data-ttu-id="2f888-108">ホストは、promise 継続コールバックを指定できます `JsSetPromiseContinuationCallback` 。</span><span class="sxs-lookup"><span data-stu-id="2f888-108">The host can specify a promise continuation callback in `JsSetPromiseContinuationCallback`.</span></span> <span data-ttu-id="2f888-109">スクリプトが後で実行するタスクを作成する場合は、promise 継続コールバックがタスクと一緒に呼び出され、タスクは、現在のスクリプトの実行が完了した時に実行される、FIFO キューに入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f888-109">If a script creates a task to be run later, then the promise continuation callback will be called with the task and the task should be put in a FIFO queue, to be run when the current script is done executing.</span></span>  
  
 <span data-ttu-id="2f888-110">この API は EdgeHTML モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2f888-110">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="2f888-111">要件</span><span class="sxs-lookup"><span data-stu-id="2f888-111">Requirements</span></span>  
 <span data-ttu-id="2f888-112">jsrt.h</span><span class="sxs-lookup"><span data-stu-id="2f888-112">jsrt.h</span></span>  
  
## <span data-ttu-id="2f888-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f888-113">See Also</span></span>  
 [<span data-ttu-id="2f888-114">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="2f888-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
