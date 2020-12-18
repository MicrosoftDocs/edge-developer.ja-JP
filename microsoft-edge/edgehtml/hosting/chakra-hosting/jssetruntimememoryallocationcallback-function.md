---
description: 指定されたランタイムのメモリ割り当てコールバックを設定します。
title: JsSetRuntimeMemoryAllocationCallback 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryAllocationCallback
helpviewer_keywords:
- JsSetRuntimeMemoryAllocationCallback function
ms.assetid: 6aa7d58d-6456-4df1-815f-1ba36fb4ae14
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: ee2abf36e14c26ac58b90d48a6115fd6502307c9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234684"
---
# <span data-ttu-id="b120f-103">JsSetRuntimeMemoryAllocationCallback 関数</span><span class="sxs-lookup"><span data-stu-id="b120f-103">JsSetRuntimeMemoryAllocationCallback Function</span></span>

<span data-ttu-id="b120f-104">指定されたランタイムのメモリ割り当てコールバックを設定します。</span><span class="sxs-lookup"><span data-stu-id="b120f-104">Sets a memory allocation callback for specified runtime.</span></span>  
  
## <span data-ttu-id="b120f-105">構文</span><span class="sxs-lookup"><span data-stu-id="b120f-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetRuntimeMemoryAllocationCallback(  
   _In_ JsRuntimeHandle runtime,  
   _In_opt_ void *callbackState,  
   _In_ JsMemoryAllocationCallback allocationCallback  
);  
```  
  
#### <span data-ttu-id="b120f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b120f-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="b120f-107">割り当てコールバックを登録するランタイム。</span><span class="sxs-lookup"><span data-stu-id="b120f-107">The runtime for which to register the allocation callback.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="b120f-108">コールバックに戻されるユーザー指定の状態。</span><span class="sxs-lookup"><span data-stu-id="b120f-108">User provided state that will be passed back to the callback.</span></span>  
  
 `allocationCallback`  
 <span data-ttu-id="b120f-109">メモリ割り当てイベントに対して呼び出されるメモリ割り当てコールバック。</span><span class="sxs-lookup"><span data-stu-id="b120f-109">Memory allocation callback to be called for memory allocation events.</span></span>  
  
## <span data-ttu-id="b120f-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="b120f-110">Return Value</span></span>  
 <span data-ttu-id="b120f-111">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="b120f-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="b120f-112">注釈</span><span class="sxs-lookup"><span data-stu-id="b120f-112">Remarks</span></span>  
 <span data-ttu-id="b120f-113">メモリ割り当てコールバックを登録すると、ランタイムは、OS からメモリを取得または解放するたびにホストにコールバックします。</span><span class="sxs-lookup"><span data-stu-id="b120f-113">Registering a memory allocation callback will cause the runtime to call back to the host whenever it acquires memory from, or releases memory to, the OS.</span></span> <span data-ttu-id="b120f-114">コールバック ルーチンは、ランタイム メモリ マネージャーがメモリ ブロックを割り当てる前に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b120f-114">The callback routine is called before the runtime memory manager allocates a block of memory.</span></span> <span data-ttu-id="b120f-115">コールバックが false を返した場合、割り当ては拒否されます。</span><span class="sxs-lookup"><span data-stu-id="b120f-115">The allocation will be rejected if the callback returns false.</span></span> <span data-ttu-id="b120f-116">ランタイム メモリ マネージャーは、メモリブロックを解放した後、および割り当てエラーが発生した後もコールバック ルーチンを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b120f-116">The runtime memory manager will also invoke the callback routine after freeing a block of memory, as well as after allocation failures.</span></span>  
  
 <span data-ttu-id="b120f-117">コールバックは現在のランタイム実行スレッドで呼び出されるため、コールバックが完了するまで実行はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="b120f-117">The callback is invoked on the current runtime execution thread, therefore execution is blocked until the callback completes.</span></span>  
  
 <span data-ttu-id="b120f-118">コールバックの戻り値は保存されません。以前に拒否された割り当てでは、ランタイムが後で新しいメモリ割り当てのためにコールバックを再び呼び出すのを妨げることはありません。</span><span class="sxs-lookup"><span data-stu-id="b120f-118">The return value of the callback is not stored; previously rejected allocations will not prevent the runtime from invoking the callback again later for new memory allocations.</span></span>  
  
## <span data-ttu-id="b120f-119">要件</span><span class="sxs-lookup"><span data-stu-id="b120f-119">Requirements</span></span>  
 <span data-ttu-id="b120f-120">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="b120f-120">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="b120f-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="b120f-121">See Also</span></span>  
 [<span data-ttu-id="b120f-122">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="b120f-122">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
