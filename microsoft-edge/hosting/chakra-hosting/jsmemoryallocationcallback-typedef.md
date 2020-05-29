---
description: メモリ割り当てイベントのコールバックルーチンが実装されています。
title: JsMemoryAllocationCallback Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 511babc7-3caa-4ee5-82a2-943bbd34db8d
caps.latest.revision: 7
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: b11b3d076c01dbfcae190fd665528323d6f8b987
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569289"
---
# <span data-ttu-id="747aa-103">JsMemoryAllocationCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="747aa-103">JsMemoryAllocationCallback Typedef</span></span>
<span data-ttu-id="747aa-104">メモリ割り当てイベントのコールバックルーチンが実装されています。</span><span class="sxs-lookup"><span data-stu-id="747aa-104">User implemented callback routine for memory allocation events.</span></span>  
  
## <span data-ttu-id="747aa-105">構文</span><span class="sxs-lookup"><span data-stu-id="747aa-105">Syntax</span></span>  
  
```cpp  
typedef bool (CALLBACK * JsMemoryAllocationCallback)(  
   _In_opt_ void *callbackState,  
   _In_ JsMemoryEventType allocationEvent,  
   _In_ size_t allocationSize  
);  
```  
  
#### <span data-ttu-id="747aa-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="747aa-106">Parameters</span></span>  
 <span data-ttu-id="747aa-107">/ステータス</span><span class="sxs-lookup"><span data-stu-id="747aa-107">callbackState</span></span>  
 <span data-ttu-id="747aa-108">JsSetRuntimeMemoryAllocationCallback に渡される状態。</span><span class="sxs-lookup"><span data-stu-id="747aa-108">The state passed to JsSetRuntimeMemoryAllocationCallback.</span></span>  
  
 <span data-ttu-id="747aa-109">・イベント</span><span class="sxs-lookup"><span data-stu-id="747aa-109">allocationEvent</span></span>  
 <span data-ttu-id="747aa-110">型割り当てイベントの型。</span><span class="sxs-lookup"><span data-stu-id="747aa-110">The type of type allocation event.</span></span>  
  
 <span data-ttu-id="747aa-111">割り当てサイズ</span><span class="sxs-lookup"><span data-stu-id="747aa-111">allocationSize</span></span>  
 <span data-ttu-id="747aa-112">割り当てのサイズ。</span><span class="sxs-lookup"><span data-stu-id="747aa-112">The size of the allocation.</span></span>  
  
## <span data-ttu-id="747aa-113">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="747aa-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="747aa-114">JsMemoryAllocate イベントの場合、true を返すことで、ランタイムは割り当てを続行できます。</span><span class="sxs-lookup"><span data-stu-id="747aa-114">For the JsMemoryAllocate event, returning true allows the runtime to continue with allocation.</span></span> <span data-ttu-id="747aa-115">False を返すと、割り当て要求は拒否されます。</span><span class="sxs-lookup"><span data-stu-id="747aa-115">Returning false indicates the allocation request is rejected.</span></span> <span data-ttu-id="747aa-116">他の割り当てイベントでは、戻り値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="747aa-116">The return value is ignored for other allocation events.</span></span>  
  
## <span data-ttu-id="747aa-117">注釈</span><span class="sxs-lookup"><span data-stu-id="747aa-117">Remarks</span></span>  
 <span data-ttu-id="747aa-118">このコールバックを登録するには、JsSetRuntimeMemoryAllocationCallback を使用します。</span><span class="sxs-lookup"><span data-stu-id="747aa-118">Use JsSetRuntimeMemoryAllocationCallback to register this callback.</span></span>  
  
## <span data-ttu-id="747aa-119">要件</span><span class="sxs-lookup"><span data-stu-id="747aa-119">Requirements</span></span>  
 <span data-ttu-id="747aa-120">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="747aa-120">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="747aa-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="747aa-121">See Also</span></span>  
 [<span data-ttu-id="747aa-122">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="747aa-122">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)