---
description: JavaScript 型指定された配列オブジェクトを作成します。
title: JsCreateTypedArray 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 937a2a91-6f5f-4aaa-a018-d3089702bf36
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 62f62296d81dafe6515f69a990e33ff5c00730e1
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234880"
---
# <span data-ttu-id="896aa-103">JsCreateTypedArray 関数</span><span class="sxs-lookup"><span data-stu-id="896aa-103">JsCreateTypedArray Function</span></span>

<span data-ttu-id="896aa-104">JavaScript 型指定された配列オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="896aa-104">Creates a JavaScript typed array object.</span></span>  
  
## <span data-ttu-id="896aa-105">構文</span><span class="sxs-lookup"><span data-stu-id="896aa-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateTypedArray(  
   _In_ JsTypedArrayType arrayType,  
   _In_ JsValueRef baseArray,  
   _In_ unsigned int byteOffset,  
   _In_ unsigned int elementLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="896aa-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="896aa-106">Parameters</span></span>  
 `arrayType`  
 <span data-ttu-id="896aa-107">作成する配列の型を指定します。</span><span class="sxs-lookup"><span data-stu-id="896aa-107">The type of the array to create.</span></span>  
  
 `baseArray`  
 <span data-ttu-id="896aa-108">新しい配列の基本配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="896aa-108">The base array of the new array.</span></span> <span data-ttu-id="896aa-109">ベース `JS_INVALID_REFERENCE` 配列がない場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="896aa-109">Use `JS_INVALID_REFERENCE` if no base array.</span></span>  
  
 `byteOffset`  
 <span data-ttu-id="896aa-110">結果の型指定された配列を参照する ( ) の開始からのオフセットをバイト `baseArray` `ArrayBuffer` 単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="896aa-110">The offset in bytes from the start of `baseArray` (`ArrayBuffer`) for result typed array to reference.</span></span> <span data-ttu-id="896aa-111">オブジェクトの場合 `baseArray` にのみ適用 `ArrayBuffer` されます。</span><span class="sxs-lookup"><span data-stu-id="896aa-111">Only applicable when `baseArray` is an `ArrayBuffer` object.</span></span> <span data-ttu-id="896aa-112">それ以外の場合は 0 を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="896aa-112">Must be 0 otherwise.</span></span>  
  
 `elementLength`  
 <span data-ttu-id="896aa-113">配列内の要素の数。</span><span class="sxs-lookup"><span data-stu-id="896aa-113">The number of elements in the array.</span></span> <span data-ttu-id="896aa-114">新しい型指定された配列を作成するときにのみ適用できます。(is) を指定しない場合、または `baseArray` `baseArray` `JS_INVALID_REFERENCE` オブジェクト `baseArray` の場合 `ArrayBuffer` に適用されます。</span><span class="sxs-lookup"><span data-stu-id="896aa-114">Only applicable when creating a new typed array without `baseArray` (`baseArray` is `JS_INVALID_REFERENCE`) or when `baseArray` is an `ArrayBuffer` object.</span></span> <span data-ttu-id="896aa-115">それ以外の場合は 0 を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="896aa-115">Must be 0 otherwise.</span></span>  
  
 `result`  
 <span data-ttu-id="896aa-116">新しい型指定された配列オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="896aa-116">The new typed array object.</span></span>  
  
## <span data-ttu-id="896aa-117">戻り値</span><span class="sxs-lookup"><span data-stu-id="896aa-117">Return Value</span></span>  
 <span data-ttu-id="896aa-118">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="896aa-118">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="896aa-119">注釈</span><span class="sxs-lookup"><span data-stu-id="896aa-119">Remarks</span></span>  
 <span data-ttu-id="896aa-120">使用 `baseArray` できる値は、別 `ArrayBuffer` の型指定された配列、または JavaScript です `Array` 。</span><span class="sxs-lookup"><span data-stu-id="896aa-120">The `baseArray` can be an `ArrayBuffer`, another typed array, or a JavaScript `Array`.</span></span> <span data-ttu-id="896aa-121">返される型指定された配列は、その配列が if である場合に使用します。それ以外の場合は、基になるソース配列のコピー `baseArray` `ArrayBuffer` を作成して使用します。</span><span class="sxs-lookup"><span data-stu-id="896aa-121">The returned typed array will use the `baseArray` if it is an `ArrayBuffer`, or otherwise create and use a copy of the underlying source array.</span></span>  
  
 <span data-ttu-id="896aa-122">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="896aa-122">Requires an active script context.</span></span>  
  
 <span data-ttu-id="896aa-123">この API は、Microsoft Edge モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="896aa-123">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="896aa-124">要件</span><span class="sxs-lookup"><span data-stu-id="896aa-124">Requirements</span></span>  
 <span data-ttu-id="896aa-125">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="896aa-125">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="896aa-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="896aa-126">See Also</span></span>  
 [<span data-ttu-id="896aa-127">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="896aa-127">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
