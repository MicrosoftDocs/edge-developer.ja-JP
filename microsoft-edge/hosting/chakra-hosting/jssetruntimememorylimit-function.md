---
description: ランタイムの現在のメモリの制限を設定します。
title: JsSetRuntimeMemoryLimit 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryLimit
helpviewer_keywords:
- JsSetRuntimeMemoryLimit function
ms.assetid: 74feb31f-19f6-43e3-b117-0694c59ac593
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: ec8d098c528ac813926797280541aa2c9c4fee79
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570274"
---
# <span data-ttu-id="deefd-103">JsSetRuntimeMemoryLimit 関数</span><span class="sxs-lookup"><span data-stu-id="deefd-103">JsSetRuntimeMemoryLimit Function</span></span>
<span data-ttu-id="deefd-104">ランタイムの現在のメモリの制限を設定します。</span><span class="sxs-lookup"><span data-stu-id="deefd-104">Sets the current memory limit for a runtime.</span></span>  
  
## <span data-ttu-id="deefd-105">構文</span><span class="sxs-lookup"><span data-stu-id="deefd-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetRuntimeMemoryLimit(  
   _In_ JsRuntimeHandle runtime,  
   _In_ size_t memoryLimit  
);  
```  
  
#### <span data-ttu-id="deefd-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="deefd-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="deefd-107">メモリの制限を設定するランタイム。</span><span class="sxs-lookup"><span data-stu-id="deefd-107">The runtime whose memory limit is to be set.</span></span>  
  
 `memoryLimit`  
 <span data-ttu-id="deefd-108">メモリ制限なしの新しいランタイムメモリ制限 (バイト単位) または-1。</span><span class="sxs-lookup"><span data-stu-id="deefd-108">The new runtime memory limit, in bytes, or -1 for no memory limit.</span></span>  
  
## <span data-ttu-id="deefd-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="deefd-109">Return Value</span></span>  
 <span data-ttu-id="deefd-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="deefd-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="deefd-111">注釈</span><span class="sxs-lookup"><span data-stu-id="deefd-111">Remarks</span></span>  
 <span data-ttu-id="deefd-112">メモリの制限により、"メモリ不足" というエラーが発生して、制限を超過する操作はすべて失敗します。</span><span class="sxs-lookup"><span data-stu-id="deefd-112">A memory limit will cause any operation which exceeds the limit to fail with an "out of memory" error.</span></span> <span data-ttu-id="deefd-113">ランタイムのメモリ制限を-1 に設定することは、ランタイムにメモリの制限がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="deefd-113">Setting a runtime's memory limit to -1 means that the runtime has no memory limit.</span></span> <span data-ttu-id="deefd-114">新しいランタイムには、メモリ制限がない既定値が設定されています。</span><span class="sxs-lookup"><span data-stu-id="deefd-114">New runtimes default to having no memory limit.</span></span> <span data-ttu-id="deefd-115">新しいメモリ制限が現在の使用量を超えている場合、その呼び出しは成功し、ランタイムのメモリ使用量が制限を下回るまで、このランタイムの以降の割り当ては失敗します。</span><span class="sxs-lookup"><span data-stu-id="deefd-115">If the new memory limit exceeds current usage, the call will succeed and any future allocations in this runtime will fail until the runtime's memory usage drops below the limit.</span></span>  
  
 <span data-ttu-id="deefd-116">ランタイムのメモリ制限は、他のスレッドでランタイムがアクティブになっているかどうかに関係なく、いつでも設定できます。</span><span class="sxs-lookup"><span data-stu-id="deefd-116">A runtime's memory limit can be always be set, regardless of whether or not the runtime is active on another thread.</span></span>  
  
## <span data-ttu-id="deefd-117">要件</span><span class="sxs-lookup"><span data-stu-id="deefd-117">Requirements</span></span>  
 <span data-ttu-id="deefd-118">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="deefd-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="deefd-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="deefd-119">See Also</span></span>  
 [<span data-ttu-id="deefd-120">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="deefd-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)