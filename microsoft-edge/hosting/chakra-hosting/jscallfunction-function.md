---
description: 関数を呼び出します。
title: JsCallFunction 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCallFunction
helpviewer_keywords:
- JsCallFunction function
ms.assetid: 8a1dca72-d720-4a28-a86e-6809465006fe
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: f242ccef71d8a2b361dbe2d1a299728f5551f5d3
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569396"
---
# <span data-ttu-id="7ee69-103">JsCallFunction 関数</span><span class="sxs-lookup"><span data-stu-id="7ee69-103">JsCallFunction Function</span></span>
<span data-ttu-id="7ee69-104">関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="7ee69-104">Invokes a function.</span></span>  
  
## <span data-ttu-id="7ee69-105">構文</span><span class="sxs-lookup"><span data-stu-id="7ee69-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCallFunction(  
   _In_ JsValueRef function,  
   _In_reads_(argumentCount) JsValueRef *arguments,  
   _In_ unsigned short argumentCount,  
   _Out_opt_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="7ee69-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7ee69-106">Parameters</span></span>  
 `function`  
 <span data-ttu-id="7ee69-107">呼び出す関数。</span><span class="sxs-lookup"><span data-stu-id="7ee69-107">The function to invoke.</span></span>  
  
 `arguments`  
 <span data-ttu-id="7ee69-108">呼び出しの引数。</span><span class="sxs-lookup"><span data-stu-id="7ee69-108">The arguments to the call.</span></span>  
  
 `argumentCount`  
 <span data-ttu-id="7ee69-109">関数に渡される引数の数。</span><span class="sxs-lookup"><span data-stu-id="7ee69-109">The number of arguments being passed in to the function.</span></span>  
  
 `result`  
 <span data-ttu-id="7ee69-110">関数呼び出しから返される値 (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="7ee69-110">The value returned from the function invocation, if any.</span></span>  
  
## <span data-ttu-id="7ee69-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="7ee69-111">Return Value</span></span>  
 <span data-ttu-id="7ee69-112">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="7ee69-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="7ee69-113">注釈</span><span class="sxs-lookup"><span data-stu-id="7ee69-113">Remarks</span></span>  
 <span data-ttu-id="7ee69-114">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="7ee69-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="7ee69-115">要件</span><span class="sxs-lookup"><span data-stu-id="7ee69-115">Requirements</span></span>  
 <span data-ttu-id="7ee69-116">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="7ee69-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="7ee69-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ee69-117">See Also</span></span>  
 [<span data-ttu-id="7ee69-118">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="7ee69-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)