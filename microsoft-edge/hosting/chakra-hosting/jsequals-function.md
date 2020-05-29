---
description: 2つの JavaScript 値が等しいかどうかを比較します。
title: JsEquals 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsEquals
helpviewer_keywords:
- JsEquals function
ms.assetid: 8377a7b6-12ff-43e4-8cc8-5a5a198a168b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 84416584a048512ab20754a3b59eb8ec255901c4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570468"
---
# <span data-ttu-id="57ff5-103">JsEquals 関数</span><span class="sxs-lookup"><span data-stu-id="57ff5-103">JsEquals Function</span></span>
<span data-ttu-id="57ff5-104">2つの JavaScript 値が等しいかどうかを比較します。</span><span class="sxs-lookup"><span data-stu-id="57ff5-104">Compare two JavaScript values for equality.</span></span>  
  
## <span data-ttu-id="57ff5-105">構文</span><span class="sxs-lookup"><span data-stu-id="57ff5-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsEquals(  
   _In_ JsValueRef object1,  
   _In_ JsValueRef object2,  
   _Out_ bool *result  
);  
```  
  
#### <span data-ttu-id="57ff5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="57ff5-106">Parameters</span></span>  
 `object1`  
 <span data-ttu-id="57ff5-107">比較する最初のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="57ff5-107">The first object to compare.</span></span>  
  
 `object2`  
 <span data-ttu-id="57ff5-108">比較する2番目のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="57ff5-108">The second object to compare.</span></span>  
  
 `result`  
 <span data-ttu-id="57ff5-109">値が等しいかどうか。</span><span class="sxs-lookup"><span data-stu-id="57ff5-109">Whether the values are equal.</span></span>  
  
## <span data-ttu-id="57ff5-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="57ff5-110">Return Value</span></span>  
 <span data-ttu-id="57ff5-111">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="57ff5-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="57ff5-112">注釈</span><span class="sxs-lookup"><span data-stu-id="57ff5-112">Remarks</span></span>  
 <span data-ttu-id="57ff5-113">この関数は、 `==` Javascript の演算子と同じです。</span><span class="sxs-lookup"><span data-stu-id="57ff5-113">This function is equivalent to the `==` operator in Javascript.</span></span>  
  
 <span data-ttu-id="57ff5-114">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="57ff5-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="57ff5-115">要件</span><span class="sxs-lookup"><span data-stu-id="57ff5-115">Requirements</span></span>  
 <span data-ttu-id="57ff5-116">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="57ff5-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="57ff5-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="57ff5-117">See Also</span></span>  
 [<span data-ttu-id="57ff5-118">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="57ff5-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)