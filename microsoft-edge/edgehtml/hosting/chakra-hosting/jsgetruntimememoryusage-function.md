---
description: ランタイムの現在のメモリ使用量を取得します。
title: JsGetRuntimeMemoryUsage 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetRuntimeMemoryUsage
helpviewer_keywords:
- JsGetRuntimeMemoryUsage function
ms.assetid: b9bd4146-bfbc-4cb1-a0e9-a0ded7fb09bd
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a9c8d59e8cf73ad178f539f2f9f0ed191ceb47fd
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235099"
---
# <span data-ttu-id="54b35-103">JsGetRuntimeMemoryUsage 関数</span><span class="sxs-lookup"><span data-stu-id="54b35-103">JsGetRuntimeMemoryUsage Function</span></span>

<span data-ttu-id="54b35-104">ランタイムの現在のメモリ使用量を取得します。</span><span class="sxs-lookup"><span data-stu-id="54b35-104">Gets the current memory usage for a runtime.</span></span>  
  
## <span data-ttu-id="54b35-105">構文</span><span class="sxs-lookup"><span data-stu-id="54b35-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetRuntimeMemoryUsage(  
   _In_ JsRuntimeHandle runtime,  
   _Out_ size_t *memoryUsage  
);  
```  
  
#### <span data-ttu-id="54b35-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="54b35-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="54b35-107">メモリ使用量を取得するランタイム。</span><span class="sxs-lookup"><span data-stu-id="54b35-107">The runtime whose memory usage is to be retrieved.</span></span>  
  
 `memoryUsage`  
 <span data-ttu-id="54b35-108">ランタイムの現在のメモリ使用量 (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="54b35-108">The runtime's current memory usage, in bytes.</span></span>  
  
## <span data-ttu-id="54b35-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="54b35-109">Return Value</span></span>  
 <span data-ttu-id="54b35-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="54b35-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="54b35-111">注釈</span><span class="sxs-lookup"><span data-stu-id="54b35-111">Remarks</span></span>  
 <span data-ttu-id="54b35-112">ランタイムが別のスレッドでアクティブかどうかに関係なく、メモリ使用量は常に取得できます。</span><span class="sxs-lookup"><span data-stu-id="54b35-112">Memory usage can be always be retrieved, regardless of whether or not the runtime is active on another thread.</span></span>  
  
## <span data-ttu-id="54b35-113">要件</span><span class="sxs-lookup"><span data-stu-id="54b35-113">Requirements</span></span>  
 <span data-ttu-id="54b35-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="54b35-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="54b35-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="54b35-115">See Also</span></span>  
 [<span data-ttu-id="54b35-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="54b35-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
