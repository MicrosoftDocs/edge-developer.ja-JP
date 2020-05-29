---
description: JavaScript の型指定された array オブジェクトを作成します。
title: JsCreateTypedArray 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 937a2a91-6f5f-4aaa-a018-d3089702bf36
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 57c5d15d76bf8b3ff29d10f7500fe41b3e959f68
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569348"
---
# <span data-ttu-id="d8f44-103">JsCreateTypedArray 関数</span><span class="sxs-lookup"><span data-stu-id="d8f44-103">JsCreateTypedArray Function</span></span>
<span data-ttu-id="d8f44-104">JavaScript の型指定された array オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d8f44-104">Creates a JavaScript typed array object.</span></span>  
  
## <span data-ttu-id="d8f44-105">構文</span><span class="sxs-lookup"><span data-stu-id="d8f44-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateTypedArray(  
   _In_ JsTypedArrayType arrayType,  
   _In_ JsValueRef baseArray,  
   _In_ unsigned int byteOffset,  
   _In_ unsigned int elementLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="d8f44-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d8f44-106">Parameters</span></span>  
 `arrayType`  
 <span data-ttu-id="d8f44-107">作成する配列の型。</span><span class="sxs-lookup"><span data-stu-id="d8f44-107">The type of the array to create.</span></span>  
  
 `baseArray`  
 <span data-ttu-id="d8f44-108">新しい配列のベース配列。</span><span class="sxs-lookup"><span data-stu-id="d8f44-108">The base array of the new array.</span></span> <span data-ttu-id="d8f44-109">`JS_INVALID_REFERENCE`ベース配列がない場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="d8f44-109">Use `JS_INVALID_REFERENCE` if no base array.</span></span>  
  
 `byteOffset`  
 <span data-ttu-id="d8f44-110">`baseArray` `ArrayBuffer` 参照する結果型配列の先頭からのバイト単位のオフセット。</span><span class="sxs-lookup"><span data-stu-id="d8f44-110">The offset in bytes from the start of `baseArray` (`ArrayBuffer`) for result typed array to reference.</span></span> <span data-ttu-id="d8f44-111">オブジェクトの場合にのみ適用 `baseArray` さ `ArrayBuffer` れます。</span><span class="sxs-lookup"><span data-stu-id="d8f44-111">Only applicable when `baseArray` is an `ArrayBuffer` object.</span></span> <span data-ttu-id="d8f44-112">0以外の場合は、0を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8f44-112">Must be 0 otherwise.</span></span>  
  
 `elementLength`  
 <span data-ttu-id="d8f44-113">配列内の要素の数。</span><span class="sxs-lookup"><span data-stu-id="d8f44-113">The number of elements in the array.</span></span> <span data-ttu-id="d8f44-114">(Is) を使わずに、 `baseArray` `baseArray` またはオブジェクトの場合にのみ適用 `JS_INVALID_REFERENCE` `baseArray` さ `ArrayBuffer` れます。</span><span class="sxs-lookup"><span data-stu-id="d8f44-114">Only applicable when creating a new typed array without `baseArray` (`baseArray` is `JS_INVALID_REFERENCE`) or when `baseArray` is an `ArrayBuffer` object.</span></span> <span data-ttu-id="d8f44-115">0以外の場合は、0を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8f44-115">Must be 0 otherwise.</span></span>  
  
 `result`  
 <span data-ttu-id="d8f44-116">新しい型付き配列オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d8f44-116">The new typed array object.</span></span>  
  
## <span data-ttu-id="d8f44-117">戻り値</span><span class="sxs-lookup"><span data-stu-id="d8f44-117">Return Value</span></span>  
 <span data-ttu-id="d8f44-118">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="d8f44-118">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="d8f44-119">注釈</span><span class="sxs-lookup"><span data-stu-id="d8f44-119">Remarks</span></span>  
 <span data-ttu-id="d8f44-120">は、、 `baseArray` `ArrayBuffer` 別の型付き配列、または JavaScript にすることができ `Array` ます。</span><span class="sxs-lookup"><span data-stu-id="d8f44-120">The `baseArray` can be an `ArrayBuffer`, another typed array, or a JavaScript `Array`.</span></span> <span data-ttu-id="d8f44-121">返される型指定された配列は、それがの場合は、それ以外の場合は、 `baseArray` `ArrayBuffer` 基になるソース配列のコピーを作成して使用します。</span><span class="sxs-lookup"><span data-stu-id="d8f44-121">The returned typed array will use the `baseArray` if it is an `ArrayBuffer`, or otherwise create and use a copy of the underlying source array.</span></span>  
  
 <span data-ttu-id="d8f44-122">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="d8f44-122">Requires an active script context.</span></span>  
  
 <span data-ttu-id="d8f44-123">この API は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d8f44-123">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="d8f44-124">要件</span><span class="sxs-lookup"><span data-stu-id="d8f44-124">Requirements</span></span>  
 <span data-ttu-id="d8f44-125">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="d8f44-125">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="d8f44-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8f44-126">See Also</span></span>  
 [<span data-ttu-id="d8f44-127">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="d8f44-127">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)