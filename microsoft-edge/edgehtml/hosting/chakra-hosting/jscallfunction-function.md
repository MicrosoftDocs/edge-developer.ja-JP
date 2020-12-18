---
description: 関数を呼び出します。
title: JsCallFunction 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCallFunction
helpviewer_keywords:
- JsCallFunction function
ms.assetid: 8a1dca72-d720-4a28-a86e-6809465006fe
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: dc26f66cb7deae0857ce34cbd4d83ee26046b3c8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234543"
---
# <span data-ttu-id="207f4-103">JsCallFunction 関数</span><span class="sxs-lookup"><span data-stu-id="207f4-103">JsCallFunction Function</span></span>

<span data-ttu-id="207f4-104">関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="207f4-104">Invokes a function.</span></span>  
  
## <span data-ttu-id="207f4-105">構文</span><span class="sxs-lookup"><span data-stu-id="207f4-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCallFunction(  
   _In_ JsValueRef function,  
   _In_reads_(argumentCount) JsValueRef *arguments,  
   _In_ unsigned short argumentCount,  
   _Out_opt_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="207f4-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="207f4-106">Parameters</span></span>  
 `function`  
 <span data-ttu-id="207f4-107">呼び出す関数。</span><span class="sxs-lookup"><span data-stu-id="207f4-107">The function to invoke.</span></span>  
  
 `arguments`  
 <span data-ttu-id="207f4-108">呼び出しの引数。</span><span class="sxs-lookup"><span data-stu-id="207f4-108">The arguments to the call.</span></span>  
  
 `argumentCount`  
 <span data-ttu-id="207f4-109">関数に渡される引数の数。</span><span class="sxs-lookup"><span data-stu-id="207f4-109">The number of arguments being passed in to the function.</span></span>  
  
 `result`  
 <span data-ttu-id="207f4-110">関数呼び出しから返される値 (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="207f4-110">The value returned from the function invocation, if any.</span></span>  
  
## <span data-ttu-id="207f4-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="207f4-111">Return Value</span></span>  
 <span data-ttu-id="207f4-112">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="207f4-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="207f4-113">注釈</span><span class="sxs-lookup"><span data-stu-id="207f4-113">Remarks</span></span>  
 <span data-ttu-id="207f4-114">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="207f4-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="207f4-115">要件</span><span class="sxs-lookup"><span data-stu-id="207f4-115">Requirements</span></span>  
 <span data-ttu-id="207f4-116">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="207f4-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="207f4-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="207f4-117">See Also</span></span>  
 [<span data-ttu-id="207f4-118">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="207f4-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
