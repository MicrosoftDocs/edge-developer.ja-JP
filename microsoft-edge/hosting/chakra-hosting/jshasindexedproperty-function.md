---
description: 指定されたインデックスでオブジェクトに値が含まれているかどうかをテストします。
title: JsHasIndexedProperty 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsHasIndexedProperty
helpviewer_keywords:
- JsHasIndexedProperty function
ms.assetid: 30436a3d-fda0-407e-aba2-142be2310372
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 85d9fa12c44bd1d961ec2a7ba494484873635586
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570428"
---
# <span data-ttu-id="1ebbe-103">JsHasIndexedProperty 関数</span><span class="sxs-lookup"><span data-stu-id="1ebbe-103">JsHasIndexedProperty Function</span></span>
<span data-ttu-id="1ebbe-104">指定されたインデックスでオブジェクトに値が含まれているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="1ebbe-104">Tests whether an object has a value at the specified index.</span></span>  
  
## <span data-ttu-id="1ebbe-105">構文</span><span class="sxs-lookup"><span data-stu-id="1ebbe-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsHasIndexedProperty(  
   _In_ JsValueRef object,  
   _In_ JsValueRef index,  
   _Out_ bool *result  
);  
```  
  
#### <span data-ttu-id="1ebbe-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1ebbe-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="1ebbe-107">操作対象のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1ebbe-107">The object to operate on.</span></span>  
  
 `index`  
 <span data-ttu-id="1ebbe-108">テストするインデックス。</span><span class="sxs-lookup"><span data-stu-id="1ebbe-108">The index to test.</span></span>  
  
 `result`  
 <span data-ttu-id="1ebbe-109">指定したインデックスの値がオブジェクトに含まれるかどうか</span><span class="sxs-lookup"><span data-stu-id="1ebbe-109">Whether the object has an value at the specified index.</span></span>  
  
## <span data-ttu-id="1ebbe-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="1ebbe-110">Return Value</span></span>  
 <span data-ttu-id="1ebbe-111">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="1ebbe-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="1ebbe-112">注釈</span><span class="sxs-lookup"><span data-stu-id="1ebbe-112">Remarks</span></span>  
 <span data-ttu-id="1ebbe-113">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="1ebbe-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="1ebbe-114">要件</span><span class="sxs-lookup"><span data-stu-id="1ebbe-114">Requirements</span></span>  
 <span data-ttu-id="1ebbe-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="1ebbe-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="1ebbe-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ebbe-116">See Also</span></span>  
 [<span data-ttu-id="1ebbe-117">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="1ebbe-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)