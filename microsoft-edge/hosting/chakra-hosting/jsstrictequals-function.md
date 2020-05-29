---
description: 厳密等価の2つの JavaScript 値を比較します。
title: JsStrictEquals 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsStrictEquals
helpviewer_keywords:
- JsStrictEquals function
ms.assetid: b35bc655-7ff8-496a-b678-8950bb976047
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: b7f2b7a66c32428100f0c0d0f9db6150559ed7a2
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570367"
---
# <span data-ttu-id="4e6ef-103">JsStrictEquals 関数</span><span class="sxs-lookup"><span data-stu-id="4e6ef-103">JsStrictEquals Function</span></span>
<span data-ttu-id="4e6ef-104">厳密等価の2つの JavaScript 値を比較します。</span><span class="sxs-lookup"><span data-stu-id="4e6ef-104">Compare two JavaScript values for strict equality.</span></span>  
  
## <span data-ttu-id="4e6ef-105">構文</span><span class="sxs-lookup"><span data-stu-id="4e6ef-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsStrictEquals(  
   _In_ JsValueRef object1,  
   _In_ JsValueRef object2,  
   _Out_ bool *result  
);  
```  
  
#### <span data-ttu-id="4e6ef-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4e6ef-106">Parameters</span></span>  
 `object1`  
 <span data-ttu-id="4e6ef-107">比較する最初のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4e6ef-107">The first object to compare.</span></span>  
  
 `object2`  
 <span data-ttu-id="4e6ef-108">比較する2番目のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4e6ef-108">The second object to compare.</span></span>  
  
 `result`  
 <span data-ttu-id="4e6ef-109">値が厳密に等しいかどうか。</span><span class="sxs-lookup"><span data-stu-id="4e6ef-109">Whether the values are strictly equal.</span></span>  
  
## <span data-ttu-id="4e6ef-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="4e6ef-110">Return Value</span></span>  
 <span data-ttu-id="4e6ef-111">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="4e6ef-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="4e6ef-112">注釈</span><span class="sxs-lookup"><span data-stu-id="4e6ef-112">Remarks</span></span>  
 <span data-ttu-id="4e6ef-113">この関数は、 `===` Javascript の演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="4e6ef-113">This function is equivalent to the `===` operator in Javascript.</span></span>  
  
 <span data-ttu-id="4e6ef-114">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="4e6ef-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="4e6ef-115">要件</span><span class="sxs-lookup"><span data-stu-id="4e6ef-115">Requirements</span></span>  
 <span data-ttu-id="4e6ef-116">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="4e6ef-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="4e6ef-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e6ef-117">See Also</span></span>  
 [<span data-ttu-id="4e6ef-118">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="4e6ef-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)