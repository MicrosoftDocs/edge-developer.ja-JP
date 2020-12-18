---
description: コンストラクターとして関数を呼び出します。
title: JsConstructObject 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsConstructObject
helpviewer_keywords:
- JsConstructObject function
ms.assetid: b07d2440-db55-4a6a-8376-56b40a8039a1
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 8dbb757456412e50efaf3a026d169e6b3612b6b1
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234541"
---
# <span data-ttu-id="22b28-103">JsConstructObject 関数</span><span class="sxs-lookup"><span data-stu-id="22b28-103">JsConstructObject Function</span></span>

<span data-ttu-id="22b28-104">コンストラクターとして関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="22b28-104">Invokes a function as a constructor.</span></span>  
  
## <span data-ttu-id="22b28-105">構文</span><span class="sxs-lookup"><span data-stu-id="22b28-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsConstructObject(  
   _In_ JsValueRef function,  
   _In_reads_(argumentCount) JsValueRef *arguments,  
   _In_ unsigned short argumentCount,  
   _Out_opt_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="22b28-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="22b28-106">Parameters</span></span>  
 `function`  
 <span data-ttu-id="22b28-107">コンストラクターとして呼び出す関数。</span><span class="sxs-lookup"><span data-stu-id="22b28-107">The function to invoke as a constructor.</span></span>  
  
 `arguments`  
 <span data-ttu-id="22b28-108">呼び出しの引数。</span><span class="sxs-lookup"><span data-stu-id="22b28-108">The arguments to the call.</span></span>  
  
 `argumentCount`  
 <span data-ttu-id="22b28-109">関数に渡される引数の数。</span><span class="sxs-lookup"><span data-stu-id="22b28-109">The number of arguments being passed in to the function.</span></span>  
  
 `result`  
 <span data-ttu-id="22b28-110">関数呼び出しから返される値。</span><span class="sxs-lookup"><span data-stu-id="22b28-110">The value returned from the function invocation.</span></span>  
  
## <span data-ttu-id="22b28-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="22b28-111">Return Value</span></span>  
 <span data-ttu-id="22b28-112">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="22b28-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="22b28-113">注釈</span><span class="sxs-lookup"><span data-stu-id="22b28-113">Remarks</span></span>  
 <span data-ttu-id="22b28-114">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="22b28-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="22b28-115">要件</span><span class="sxs-lookup"><span data-stu-id="22b28-115">Requirements</span></span>  
 <span data-ttu-id="22b28-116">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="22b28-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="22b28-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="22b28-117">See Also</span></span>  
 [<span data-ttu-id="22b28-118">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="22b28-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
