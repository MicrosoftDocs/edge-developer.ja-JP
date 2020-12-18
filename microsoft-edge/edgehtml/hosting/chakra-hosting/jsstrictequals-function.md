---
description: 2 つの JavaScript 値を厳密な等号と比較します。
title: JsStrictEquals 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsStrictEquals
helpviewer_keywords:
- JsStrictEquals function
ms.assetid: b35bc655-7ff8-496a-b678-8950bb976047
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 98af1629129986cc21cafe5660d3155e031919dc
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234685"
---
# <span data-ttu-id="632a3-103">JsStrictEquals 関数</span><span class="sxs-lookup"><span data-stu-id="632a3-103">JsStrictEquals Function</span></span>

<span data-ttu-id="632a3-104">2 つの JavaScript 値を厳密な等号と比較します。</span><span class="sxs-lookup"><span data-stu-id="632a3-104">Compare two JavaScript values for strict equality.</span></span>  
  
## <span data-ttu-id="632a3-105">構文</span><span class="sxs-lookup"><span data-stu-id="632a3-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsStrictEquals(  
   _In_ JsValueRef object1,  
   _In_ JsValueRef object2,  
   _Out_ bool *result  
);  
```  
  
#### <span data-ttu-id="632a3-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="632a3-106">Parameters</span></span>  
 `object1`  
 <span data-ttu-id="632a3-107">比較する最初のオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="632a3-107">The first object to compare.</span></span>  
  
 `object2`  
 <span data-ttu-id="632a3-108">比較する 2 番目のオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="632a3-108">The second object to compare.</span></span>  
  
 `result`  
 <span data-ttu-id="632a3-109">値が厳密に等しいかどうか。</span><span class="sxs-lookup"><span data-stu-id="632a3-109">Whether the values are strictly equal.</span></span>  
  
## <span data-ttu-id="632a3-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="632a3-110">Return Value</span></span>  
 <span data-ttu-id="632a3-111">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="632a3-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="632a3-112">注釈</span><span class="sxs-lookup"><span data-stu-id="632a3-112">Remarks</span></span>  
 <span data-ttu-id="632a3-113">この関数は `===` 、Javascript の演算子と同等です。</span><span class="sxs-lookup"><span data-stu-id="632a3-113">This function is equivalent to the `===` operator in Javascript.</span></span>  
  
 <span data-ttu-id="632a3-114">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="632a3-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="632a3-115">要件</span><span class="sxs-lookup"><span data-stu-id="632a3-115">Requirements</span></span>  
 <span data-ttu-id="632a3-116">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="632a3-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="632a3-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="632a3-117">See Also</span></span>  
 [<span data-ttu-id="632a3-118">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="632a3-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
