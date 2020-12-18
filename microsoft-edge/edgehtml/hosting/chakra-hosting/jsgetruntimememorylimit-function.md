---
description: ランタイムの現在のメモリ制限を取得します。
title: JsGetRuntimeMemoryLimit 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetRuntimeMemoryLimit
helpviewer_keywords:
- JsGetRuntimeMemoryLimit function
ms.assetid: ed81ca60-99fd-46b0-89ae-f6ac07926904
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: ed04a0fb921d22eea17eaf86ef7a0152fbf2a1d0
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235038"
---
# <span data-ttu-id="20ed0-103">JsGetRuntimeMemoryLimit 関数</span><span class="sxs-lookup"><span data-stu-id="20ed0-103">JsGetRuntimeMemoryLimit Function</span></span>

<span data-ttu-id="20ed0-104">ランタイムの現在のメモリ制限を取得します。</span><span class="sxs-lookup"><span data-stu-id="20ed0-104">Gets the current memory limit for a runtime.</span></span>  
  
## <span data-ttu-id="20ed0-105">構文</span><span class="sxs-lookup"><span data-stu-id="20ed0-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetRuntimeMemoryLimit(  
   _In_ JsRuntimeHandle runtime,  
   _Out_ size_t *memoryLimit  
);  
```  
  
#### <span data-ttu-id="20ed0-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="20ed0-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="20ed0-107">メモリ制限を取得するランタイム。</span><span class="sxs-lookup"><span data-stu-id="20ed0-107">The runtime whose memory limit is to be retrieved.</span></span>  
  
 `memoryLimit`  
 <span data-ttu-id="20ed0-108">ランタイムの現在のメモリ制限 (バイト単位)、または制限が設定されていない場合は -1。</span><span class="sxs-lookup"><span data-stu-id="20ed0-108">The runtime's current memory limit, in bytes, or -1 if no limit has been set.</span></span>  
  
## <span data-ttu-id="20ed0-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="20ed0-109">Return Value</span></span>  
 <span data-ttu-id="20ed0-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="20ed0-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="20ed0-111">注釈</span><span class="sxs-lookup"><span data-stu-id="20ed0-111">Remarks</span></span>  
 <span data-ttu-id="20ed0-112">ランタイムが別のスレッドでアクティブかどうかに関係なく、ランタイムのメモリ制限を常に取得できます。</span><span class="sxs-lookup"><span data-stu-id="20ed0-112">The memory limit of a runtime can be always be retrieved, regardless of whether or not the runtime is active on another thread.</span></span>  
  
## <span data-ttu-id="20ed0-113">要件</span><span class="sxs-lookup"><span data-stu-id="20ed0-113">Requirements</span></span>  
 <span data-ttu-id="20ed0-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="20ed0-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="20ed0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="20ed0-115">See Also</span></span>  
 [<span data-ttu-id="20ed0-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="20ed0-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
