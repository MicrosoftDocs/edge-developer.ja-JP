---
description: 将来の実行のためにタスクをキューに入れる必要があるときにコンテキストによって呼び出される promise 継続コールバック関数を設定します。
title: JsSetPromiseContinuationCallback 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 6ef0faf4-1500-4bd9-aeca-c208492af8ea
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: da928431f05831c95d5bc116dbd129de9cb5f3b4
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234764"
---
# <span data-ttu-id="dc4d6-103">JsSetPromiseContinuationCallback 関数</span><span class="sxs-lookup"><span data-stu-id="dc4d6-103">JsSetPromiseContinuationCallback Function</span></span>

<span data-ttu-id="dc4d6-104">将来の実行のためにタスクをキューに入れる必要があるときにコンテキストによって呼び出される promise 継続コールバック関数を設定します。</span><span class="sxs-lookup"><span data-stu-id="dc4d6-104">Sets a promise continuation callback function that is called by the context when a task needs to be queued for future execution.</span></span>  
  
## <span data-ttu-id="dc4d6-105">構文</span><span class="sxs-lookup"><span data-stu-id="dc4d6-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetPromiseContinuationCallback(  
   _In_ JsPromiseContinuationCallback promiseContinuationCallback,  
   _In_opt_ void *callbackState  
);  
```  
  
#### <span data-ttu-id="dc4d6-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dc4d6-106">Parameters</span></span>  
 `promiseContinuationCallback`  
 <span data-ttu-id="dc4d6-107">設定するコールバック関数。</span><span class="sxs-lookup"><span data-stu-id="dc4d6-107">The callback function being set.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="dc4d6-108">コールバックに戻されるユーザー指定の状態。</span><span class="sxs-lookup"><span data-stu-id="dc4d6-108">User provided state that will be passed back to the callback.</span></span>  
  
## <span data-ttu-id="dc4d6-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="dc4d6-109">Return Value</span></span>  
 <span data-ttu-id="dc4d6-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="dc4d6-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="dc4d6-111">注釈</span><span class="sxs-lookup"><span data-stu-id="dc4d6-111">Remarks</span></span>  
 <span data-ttu-id="dc4d6-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="dc4d6-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="dc4d6-113">この API は EdgeHTML モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="dc4d6-113">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="dc4d6-114">要件</span><span class="sxs-lookup"><span data-stu-id="dc4d6-114">Requirements</span></span>  
 <span data-ttu-id="dc4d6-115">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="dc4d6-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="dc4d6-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc4d6-116">See Also</span></span>  
 [<span data-ttu-id="dc4d6-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="dc4d6-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
