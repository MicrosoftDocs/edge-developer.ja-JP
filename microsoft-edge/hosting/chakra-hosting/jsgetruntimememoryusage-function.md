---
description: ランタイムの現在のメモリ使用量を取得します。
title: JsGetRuntimeMemoryUsage 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetRuntimeMemoryUsage
helpviewer_keywords:
- JsGetRuntimeMemoryUsage function
ms.assetid: b9bd4146-bfbc-4cb1-a0e9-a0ded7fb09bd
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9ec8472132b4c50b279ee95f36995bf46c0e29e5
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569306"
---
# <span data-ttu-id="a69e2-103">JsGetRuntimeMemoryUsage 関数</span><span class="sxs-lookup"><span data-stu-id="a69e2-103">JsGetRuntimeMemoryUsage Function</span></span>
<span data-ttu-id="a69e2-104">ランタイムの現在のメモリ使用量を取得します。</span><span class="sxs-lookup"><span data-stu-id="a69e2-104">Gets the current memory usage for a runtime.</span></span>  
  
## <span data-ttu-id="a69e2-105">構文</span><span class="sxs-lookup"><span data-stu-id="a69e2-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetRuntimeMemoryUsage(  
   _In_ JsRuntimeHandle runtime,  
   _Out_ size_t *memoryUsage  
);  
```  
  
#### <span data-ttu-id="a69e2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a69e2-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="a69e2-107">メモリ使用量を取得するランタイム。</span><span class="sxs-lookup"><span data-stu-id="a69e2-107">The runtime whose memory usage is to be retrieved.</span></span>  
  
 `memoryUsage`  
 <span data-ttu-id="a69e2-108">ランタイムの現在のメモリ使用量 (バイト単位) です。</span><span class="sxs-lookup"><span data-stu-id="a69e2-108">The runtime's current memory usage, in bytes.</span></span>  
  
## <span data-ttu-id="a69e2-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="a69e2-109">Return Value</span></span>  
 <span data-ttu-id="a69e2-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="a69e2-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="a69e2-111">注釈</span><span class="sxs-lookup"><span data-stu-id="a69e2-111">Remarks</span></span>  
 <span data-ttu-id="a69e2-112">メモリ使用量は、他のスレッドでランタイムがアクティブになっているかどうかに関係なく、いつでも取得できます。</span><span class="sxs-lookup"><span data-stu-id="a69e2-112">Memory usage can be always be retrieved, regardless of whether or not the runtime is active on another thread.</span></span>  
  
## <span data-ttu-id="a69e2-113">要件</span><span class="sxs-lookup"><span data-stu-id="a69e2-113">Requirements</span></span>  
 <span data-ttu-id="a69e2-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="a69e2-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="a69e2-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a69e2-115">See Also</span></span>  
 [<span data-ttu-id="a69e2-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="a69e2-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)