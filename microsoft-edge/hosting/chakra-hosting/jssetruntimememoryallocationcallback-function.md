---
description: 指定されたランタイムのメモリ割り当てのコールバックを設定します。
title: JsSetRuntimeMemoryAllocationCallback 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryAllocationCallback
helpviewer_keywords:
- JsSetRuntimeMemoryAllocationCallback function
ms.assetid: 6aa7d58d-6456-4df1-815f-1ba36fb4ae14
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 5c648761473023f00e894fbf75c794cfcc9422c5
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570275"
---
# <span data-ttu-id="666dc-103">JsSetRuntimeMemoryAllocationCallback 関数</span><span class="sxs-lookup"><span data-stu-id="666dc-103">JsSetRuntimeMemoryAllocationCallback Function</span></span>
<span data-ttu-id="666dc-104">指定されたランタイムのメモリ割り当てのコールバックを設定します。</span><span class="sxs-lookup"><span data-stu-id="666dc-104">Sets a memory allocation callback for specified runtime.</span></span>  
  
## <span data-ttu-id="666dc-105">構文</span><span class="sxs-lookup"><span data-stu-id="666dc-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetRuntimeMemoryAllocationCallback(  
   _In_ JsRuntimeHandle runtime,  
   _In_opt_ void *callbackState,  
   _In_ JsMemoryAllocationCallback allocationCallback  
);  
```  
  
#### <span data-ttu-id="666dc-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="666dc-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="666dc-107">割り当てのコールバックを登録するランタイム。</span><span class="sxs-lookup"><span data-stu-id="666dc-107">The runtime for which to register the allocation callback.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="666dc-108">コールバックに戻される、ユーザーによって指定された状態。</span><span class="sxs-lookup"><span data-stu-id="666dc-108">User provided state that will be passed back to the callback.</span></span>  
  
 `allocationCallback`  
 <span data-ttu-id="666dc-109">メモリ割り当てイベントに対して呼び出すメモリ割り当てのコールバック。</span><span class="sxs-lookup"><span data-stu-id="666dc-109">Memory allocation callback to be called for memory allocation events.</span></span>  
  
## <span data-ttu-id="666dc-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="666dc-110">Return Value</span></span>  
 <span data-ttu-id="666dc-111">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="666dc-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="666dc-112">注釈</span><span class="sxs-lookup"><span data-stu-id="666dc-112">Remarks</span></span>  
 <span data-ttu-id="666dc-113">メモリ割り当てコールバックを登録すると、ランタイムは、メモリを取得したとき、または OS にメモリを解放するたびに、ホストにコールバックします。</span><span class="sxs-lookup"><span data-stu-id="666dc-113">Registering a memory allocation callback will cause the runtime to call back to the host whenever it acquires memory from, or releases memory to, the OS.</span></span> <span data-ttu-id="666dc-114">ランタイムメモリマネージャーがメモリブロックを割り当てる前に、コールバックルーチンが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="666dc-114">The callback routine is called before the runtime memory manager allocates a block of memory.</span></span> <span data-ttu-id="666dc-115">コールバックが false を返すと、割り当ては拒否されます。</span><span class="sxs-lookup"><span data-stu-id="666dc-115">The allocation will be rejected if the callback returns false.</span></span> <span data-ttu-id="666dc-116">また、ランタイムメモリマネージャーは、メモリブロックを解放した後、割り当てエラーが発生した後に、コールバックルーチンも呼び出します。</span><span class="sxs-lookup"><span data-stu-id="666dc-116">The runtime memory manager will also invoke the callback routine after freeing a block of memory, as well as after allocation failures.</span></span>  
  
 <span data-ttu-id="666dc-117">コールバックは現在のランタイム実行スレッドで呼び出されるため、コールバックが完了するまで実行はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="666dc-117">The callback is invoked on the current runtime execution thread, therefore execution is blocked until the callback completes.</span></span>  
  
 <span data-ttu-id="666dc-118">コールバックの戻り値は保存されません。以前に拒否された割り当てによって、新しいメモリの割り当てに対して、ランタイムは後で再びコールバックを呼び出すことができなくなります。</span><span class="sxs-lookup"><span data-stu-id="666dc-118">The return value of the callback is not stored; previously rejected allocations will not prevent the runtime from invoking the callback again later for new memory allocations.</span></span>  
  
## <span data-ttu-id="666dc-119">要件</span><span class="sxs-lookup"><span data-stu-id="666dc-119">Requirements</span></span>  
 <span data-ttu-id="666dc-120">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="666dc-120">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="666dc-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="666dc-121">See Also</span></span>  
 [<span data-ttu-id="666dc-122">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="666dc-122">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)