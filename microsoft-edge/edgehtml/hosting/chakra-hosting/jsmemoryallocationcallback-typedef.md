---
description: メモリ割り当てイベント用のユーザー実装コールバック ルーチン。
title: JsMemoryAllocationCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 511babc7-3caa-4ee5-82a2-943bbd34db8d
caps.latest.revision: 7
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 22b5cc0fe5a2c8b49f71c91d28f95ba29af37849
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234526"
---
# <span data-ttu-id="a9521-103">JsMemoryAllocationCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="a9521-103">JsMemoryAllocationCallback Typedef</span></span>

<span data-ttu-id="a9521-104">メモリ割り当てイベント用のユーザー実装コールバック ルーチン。</span><span class="sxs-lookup"><span data-stu-id="a9521-104">User implemented callback routine for memory allocation events.</span></span>  
  
## <span data-ttu-id="a9521-105">構文</span><span class="sxs-lookup"><span data-stu-id="a9521-105">Syntax</span></span>  
  
```cpp  
typedef bool (CALLBACK * JsMemoryAllocationCallback)(  
   _In_opt_ void *callbackState,  
   _In_ JsMemoryEventType allocationEvent,  
   _In_ size_t allocationSize  
);  
```  
  
#### <span data-ttu-id="a9521-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a9521-106">Parameters</span></span>  
 <span data-ttu-id="a9521-107">callbackState</span><span class="sxs-lookup"><span data-stu-id="a9521-107">callbackState</span></span>  
 <span data-ttu-id="a9521-108">JsSetRuntimeMemoryAllocationCallback に渡された状態。</span><span class="sxs-lookup"><span data-stu-id="a9521-108">The state passed to JsSetRuntimeMemoryAllocationCallback.</span></span>  
  
 <span data-ttu-id="a9521-109">allocationEvent</span><span class="sxs-lookup"><span data-stu-id="a9521-109">allocationEvent</span></span>  
 <span data-ttu-id="a9521-110">型割り当てイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="a9521-110">The type of type allocation event.</span></span>  
  
 <span data-ttu-id="a9521-111">allocationSize</span><span class="sxs-lookup"><span data-stu-id="a9521-111">allocationSize</span></span>  
 <span data-ttu-id="a9521-112">割り当てのサイズ。</span><span class="sxs-lookup"><span data-stu-id="a9521-112">The size of the allocation.</span></span>  
  
## <span data-ttu-id="a9521-113">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="a9521-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="a9521-114">JsMemoryAllocate イベントの場合、true を返す場合、ランタイムは割り当てを続行できます。</span><span class="sxs-lookup"><span data-stu-id="a9521-114">For the JsMemoryAllocate event, returning true allows the runtime to continue with allocation.</span></span> <span data-ttu-id="a9521-115">false を返す場合は、割り当て要求が拒否されます。</span><span class="sxs-lookup"><span data-stu-id="a9521-115">Returning false indicates the allocation request is rejected.</span></span> <span data-ttu-id="a9521-116">他の割り当てイベントの戻り値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="a9521-116">The return value is ignored for other allocation events.</span></span>  
  
## <span data-ttu-id="a9521-117">注釈</span><span class="sxs-lookup"><span data-stu-id="a9521-117">Remarks</span></span>  
 <span data-ttu-id="a9521-118">JsSetRuntimeMemoryAllocationCallback を使用して、このコールバックを登録します。</span><span class="sxs-lookup"><span data-stu-id="a9521-118">Use JsSetRuntimeMemoryAllocationCallback to register this callback.</span></span>  
  
## <span data-ttu-id="a9521-119">要件</span><span class="sxs-lookup"><span data-stu-id="a9521-119">Requirements</span></span>  
 <span data-ttu-id="a9521-120">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="a9521-120">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="a9521-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9521-121">See Also</span></span>  
 [<span data-ttu-id="a9521-122">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="a9521-122">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
