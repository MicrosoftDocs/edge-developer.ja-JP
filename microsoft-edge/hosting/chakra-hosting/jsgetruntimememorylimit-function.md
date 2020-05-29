---
description: ランタイムの現在のメモリ制限を取得します。
title: JsGetRuntimeMemoryLimit 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetRuntimeMemoryLimit
helpviewer_keywords:
- JsGetRuntimeMemoryLimit function
ms.assetid: ed81ca60-99fd-46b0-89ae-f6ac07926904
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: e6b44bb1dc8ad5fb8c07248a225c10682f96c86a
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569310"
---
# <span data-ttu-id="64587-103">JsGetRuntimeMemoryLimit 関数</span><span class="sxs-lookup"><span data-stu-id="64587-103">JsGetRuntimeMemoryLimit Function</span></span>
<span data-ttu-id="64587-104">ランタイムの現在のメモリ制限を取得します。</span><span class="sxs-lookup"><span data-stu-id="64587-104">Gets the current memory limit for a runtime.</span></span>  
  
## <span data-ttu-id="64587-105">構文</span><span class="sxs-lookup"><span data-stu-id="64587-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetRuntimeMemoryLimit(  
   _In_ JsRuntimeHandle runtime,  
   _Out_ size_t *memoryLimit  
);  
```  
  
#### <span data-ttu-id="64587-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="64587-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="64587-107">メモリ制限を取得するランタイム。</span><span class="sxs-lookup"><span data-stu-id="64587-107">The runtime whose memory limit is to be retrieved.</span></span>  
  
 `memoryLimit`  
 <span data-ttu-id="64587-108">ランタイムの現在のメモリ制限 (バイト単位)。または、制限が設定されていない場合は-1。</span><span class="sxs-lookup"><span data-stu-id="64587-108">The runtime's current memory limit, in bytes, or -1 if no limit has been set.</span></span>  
  
## <span data-ttu-id="64587-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="64587-109">Return Value</span></span>  
 <span data-ttu-id="64587-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="64587-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="64587-111">注釈</span><span class="sxs-lookup"><span data-stu-id="64587-111">Remarks</span></span>  
 <span data-ttu-id="64587-112">ランタイムのメモリ制限は、他のスレッドでランタイムがアクティブになっているかどうかに関係なく、いつでも取得できます。</span><span class="sxs-lookup"><span data-stu-id="64587-112">The memory limit of a runtime can be always be retrieved, regardless of whether or not the runtime is active on another thread.</span></span>  
  
## <span data-ttu-id="64587-113">要件</span><span class="sxs-lookup"><span data-stu-id="64587-113">Requirements</span></span>  
 <span data-ttu-id="64587-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="64587-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="64587-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="64587-115">See Also</span></span>  
 [<span data-ttu-id="64587-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="64587-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)