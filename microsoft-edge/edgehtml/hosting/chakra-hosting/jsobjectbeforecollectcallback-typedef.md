---
description: オブジェクトを収集する前に呼び出されるコールバック。
title: JsObjectBeforeCollectCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: f21a064a-579f-44cb-9d21-76b62e8c18f5
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 4c24385ec5e15919719ffb0ae71c8adf39c1724c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234865"
---
# <span data-ttu-id="b98b2-103">JsObjectBeforeCollectCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="b98b2-103">JsObjectBeforeCollectCallback Typedef</span></span>

<span data-ttu-id="b98b2-104">オブジェクトを収集する前に呼び出されるコールバック。</span><span class="sxs-lookup"><span data-stu-id="b98b2-104">A callback called before collecting an object.</span></span>  
  
## <span data-ttu-id="b98b2-105">構文</span><span class="sxs-lookup"><span data-stu-id="b98b2-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsObjectBeforeCollectCallback)(  
  _In_ JsRef ref,  
  _In_opt_ void *callbackState  
);  
```  
  
#### <span data-ttu-id="b98b2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b98b2-106">Parameters</span></span>  
 `ref`  
 <span data-ttu-id="b98b2-107">収集するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="b98b2-107">The object to be collected.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="b98b2-108">に渡された状態 `JsSetObjectBeforeCollectCallback` 。</span><span class="sxs-lookup"><span data-stu-id="b98b2-108">The state passed to `JsSetObjectBeforeCollectCallback`.</span></span>  
  
## <span data-ttu-id="b98b2-109">注釈</span><span class="sxs-lookup"><span data-stu-id="b98b2-109">Remarks</span></span>  
 <span data-ttu-id="b98b2-110">この API は EdgeHTML モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b98b2-110">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="b98b2-111">要件</span><span class="sxs-lookup"><span data-stu-id="b98b2-111">Requirements</span></span>  
 <span data-ttu-id="b98b2-112">jsrt.h</span><span class="sxs-lookup"><span data-stu-id="b98b2-112">jsrt.h</span></span>  
  
## <span data-ttu-id="b98b2-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="b98b2-113">See Also</span></span>  
 [<span data-ttu-id="b98b2-114">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="b98b2-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
