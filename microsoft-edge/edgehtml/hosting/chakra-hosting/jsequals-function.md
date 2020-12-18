---
description: 2 つの JavaScript 値を比較して等しい。
title: JsEquals 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsEquals
helpviewer_keywords:
- JsEquals function
ms.assetid: 8377a7b6-12ff-43e4-8cc8-5a5a198a168b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 88f906419e73ed0de6ddde0a872becbd18908997
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11235102"
---
# <span data-ttu-id="c30a8-103">JsEquals 関数</span><span class="sxs-lookup"><span data-stu-id="c30a8-103">JsEquals Function</span></span>

<span data-ttu-id="c30a8-104">2 つの JavaScript 値を比較して等しい。</span><span class="sxs-lookup"><span data-stu-id="c30a8-104">Compare two JavaScript values for equality.</span></span>  
  
## <span data-ttu-id="c30a8-105">構文</span><span class="sxs-lookup"><span data-stu-id="c30a8-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsEquals(  
   _In_ JsValueRef object1,  
   _In_ JsValueRef object2,  
   _Out_ bool *result  
);  
```  
  
#### <span data-ttu-id="c30a8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c30a8-106">Parameters</span></span>  
 `object1`  
 <span data-ttu-id="c30a8-107">比較する最初のオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c30a8-107">The first object to compare.</span></span>  
  
 `object2`  
 <span data-ttu-id="c30a8-108">比較する 2 番目のオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c30a8-108">The second object to compare.</span></span>  
  
 `result`  
 <span data-ttu-id="c30a8-109">値が等しいかどうか。</span><span class="sxs-lookup"><span data-stu-id="c30a8-109">Whether the values are equal.</span></span>  
  
## <span data-ttu-id="c30a8-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="c30a8-110">Return Value</span></span>  
 <span data-ttu-id="c30a8-111">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="c30a8-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="c30a8-112">注釈</span><span class="sxs-lookup"><span data-stu-id="c30a8-112">Remarks</span></span>  
 <span data-ttu-id="c30a8-113">この関数は `==` 、Javascript の演算子と同等です。</span><span class="sxs-lookup"><span data-stu-id="c30a8-113">This function is equivalent to the `==` operator in Javascript.</span></span>  
  
 <span data-ttu-id="c30a8-114">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="c30a8-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="c30a8-115">要件</span><span class="sxs-lookup"><span data-stu-id="c30a8-115">Requirements</span></span>  
 <span data-ttu-id="c30a8-116">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="c30a8-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="c30a8-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c30a8-117">See Also</span></span>  
 [<span data-ttu-id="c30a8-118">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="c30a8-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
