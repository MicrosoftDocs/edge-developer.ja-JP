---
description: フル ガベージ コレクションを実行します。
title: JsCollectGarbage 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCollectGarbage
helpviewer_keywords:
- JsCollectGarbage function
ms.assetid: 995c79a5-6e18-45be-81ff-2a5d3348edb8
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: c551ddf119ec0aa349fcd756f6001d92dbbb0faa
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234544"
---
# <span data-ttu-id="eaa4f-103">JsCollectGarbage 関数</span><span class="sxs-lookup"><span data-stu-id="eaa4f-103">JsCollectGarbage Function</span></span>

<span data-ttu-id="eaa4f-104">フル ガベージ コレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="eaa4f-104">Performs a full garbage collection.</span></span>  
  
## <span data-ttu-id="eaa4f-105">構文</span><span class="sxs-lookup"><span data-stu-id="eaa4f-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCollectGarbage(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### <span data-ttu-id="eaa4f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eaa4f-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="eaa4f-107">ガベージ コレクションが実行されるランタイム。</span><span class="sxs-lookup"><span data-stu-id="eaa4f-107">The runtime in which the garbage collection will be performed.</span></span>  
  
## <span data-ttu-id="eaa4f-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="eaa4f-108">Return Value</span></span>  
 <span data-ttu-id="eaa4f-109">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="eaa4f-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="eaa4f-110">要件</span><span class="sxs-lookup"><span data-stu-id="eaa4f-110">Requirements</span></span>  
 <span data-ttu-id="eaa4f-111">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="eaa4f-111">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="eaa4f-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="eaa4f-112">See Also</span></span>  
 [<span data-ttu-id="eaa4f-113">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="eaa4f-113">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
