---
description: ランタイムの現在のメモリ制限を設定します。
title: JsSetRuntimeMemoryLimit 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryLimit
helpviewer_keywords:
- JsSetRuntimeMemoryLimit function
ms.assetid: 74feb31f-19f6-43e3-b117-0694c59ac593
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 1c31d8bbbec4be22fc1af09e546ad4c95f8ec2bd
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234336"
---
# <span data-ttu-id="ceb4d-103">JsSetRuntimeMemoryLimit 関数</span><span class="sxs-lookup"><span data-stu-id="ceb4d-103">JsSetRuntimeMemoryLimit Function</span></span>

<span data-ttu-id="ceb4d-104">ランタイムの現在のメモリ制限を設定します。</span><span class="sxs-lookup"><span data-stu-id="ceb4d-104">Sets the current memory limit for a runtime.</span></span>  
  
## <span data-ttu-id="ceb4d-105">構文</span><span class="sxs-lookup"><span data-stu-id="ceb4d-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetRuntimeMemoryLimit(  
   _In_ JsRuntimeHandle runtime,  
   _In_ size_t memoryLimit  
);  
```  
  
#### <span data-ttu-id="ceb4d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ceb4d-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="ceb4d-107">メモリ制限を設定するランタイム。</span><span class="sxs-lookup"><span data-stu-id="ceb4d-107">The runtime whose memory limit is to be set.</span></span>  
  
 `memoryLimit`  
 <span data-ttu-id="ceb4d-108">新しいランタイム メモリ制限 (バイト単位)、または -1 (メモリ制限なし)。</span><span class="sxs-lookup"><span data-stu-id="ceb4d-108">The new runtime memory limit, in bytes, or -1 for no memory limit.</span></span>  
  
## <span data-ttu-id="ceb4d-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="ceb4d-109">Return Value</span></span>  
 <span data-ttu-id="ceb4d-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="ceb4d-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="ceb4d-111">注釈</span><span class="sxs-lookup"><span data-stu-id="ceb4d-111">Remarks</span></span>  
 <span data-ttu-id="ceb4d-112">メモリ制限により、制限を超える操作は "メモリ切れ" エラーで失敗します。</span><span class="sxs-lookup"><span data-stu-id="ceb4d-112">A memory limit will cause any operation which exceeds the limit to fail with an "out of memory" error.</span></span> <span data-ttu-id="ceb4d-113">ランタイムのメモリ制限を -1 に設定すると、ランタイムにはメモリ制限はありません。</span><span class="sxs-lookup"><span data-stu-id="ceb4d-113">Setting a runtime's memory limit to -1 means that the runtime has no memory limit.</span></span> <span data-ttu-id="ceb4d-114">新しいランタイムでは、既定でメモリ制限はありません。</span><span class="sxs-lookup"><span data-stu-id="ceb4d-114">New runtimes default to having no memory limit.</span></span> <span data-ttu-id="ceb4d-115">新しいメモリ制限が現在の使用量を超えると、呼び出しは成功し、ランタイムのメモリ使用量が制限を下回るまで、このランタイムでの今後の割り当ては失敗します。</span><span class="sxs-lookup"><span data-stu-id="ceb4d-115">If the new memory limit exceeds current usage, the call will succeed and any future allocations in this runtime will fail until the runtime's memory usage drops below the limit.</span></span>  
  
 <span data-ttu-id="ceb4d-116">ランタイムのメモリ制限は、ランタイムが別のスレッドでアクティブかどうかに関係なく、常に設定できます。</span><span class="sxs-lookup"><span data-stu-id="ceb4d-116">A runtime's memory limit can be always be set, regardless of whether or not the runtime is active on another thread.</span></span>  
  
## <span data-ttu-id="ceb4d-117">要件</span><span class="sxs-lookup"><span data-stu-id="ceb4d-117">Requirements</span></span>  
 <span data-ttu-id="ceb4d-118">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="ceb4d-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ceb4d-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="ceb4d-119">See Also</span></span>  
 [<span data-ttu-id="ceb4d-120">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="ceb4d-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
