---
description: オブジェクトのインデックス付きプロパティを外部データに設定します。 外部データは、オブジェクトのインデックス付きプロパティのバックストアとして使用され、型付き配列と同じようにアクセスされます。
title: JsSetIndexedPropertiesToExternalData 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: cee2d86d-ed42-4acb-86ef-95a67e63d0d6
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c1aed6e194b1dc1c35f403626a7b6c02a7752ffb
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570376"
---
# <span data-ttu-id="ecf16-104">JsSetIndexedPropertiesToExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="ecf16-104">JsSetIndexedPropertiesToExternalData Function</span></span>
<span data-ttu-id="ecf16-105">オブジェクトのインデックス付きプロパティを外部データに設定します。</span><span class="sxs-lookup"><span data-stu-id="ecf16-105">Sets an object's indexed properties to external data.</span></span> <span data-ttu-id="ecf16-106">外部データは、オブジェクトのインデックス付きプロパティのバックストアとして使用され、型付き配列と同じようにアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="ecf16-106">The external data will be used as back store for the object's indexed properties and accessed like a typed array.</span></span>  
  
## <span data-ttu-id="ecf16-107">構文</span><span class="sxs-lookup"><span data-stu-id="ecf16-107">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetIndexedPropertiesToExternalData(  
   _In_ JsValueRef object,  
   _In_ void* data,  
   _In_ JsTypedArrayType arrayType,  
   _In_ unsigned int elementLength  
);  
```  
  
#### <span data-ttu-id="ecf16-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ecf16-108">Parameters</span></span>  
 `object`  
 <span data-ttu-id="ecf16-109">操作対象のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ecf16-109">The object to operate on.</span></span>  
  
 `data`  
 <span data-ttu-id="ecf16-110">オブジェクトのインデックス付きプロパティのバックストアとして使用する外部データ。</span><span class="sxs-lookup"><span data-stu-id="ecf16-110">The external data to be used as back store for the object's indexed properties.</span></span>  
  
 `arrayType`  
 <span data-ttu-id="ecf16-111">外部データの配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="ecf16-111">The array element type in external data.</span></span>  
  
 `elementLength`  
 <span data-ttu-id="ecf16-112">外部データの配列要素の数です。</span><span class="sxs-lookup"><span data-stu-id="ecf16-112">The number of array elements in external data.</span></span>  
  
## <span data-ttu-id="ecf16-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="ecf16-113">Return Value</span></span>  
 <span data-ttu-id="ecf16-114">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="ecf16-114">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="ecf16-115">注釈</span><span class="sxs-lookup"><span data-stu-id="ecf16-115">Remarks</span></span>  
 <span data-ttu-id="ecf16-116">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="ecf16-116">Requires an active script context.</span></span>  
  
 <span data-ttu-id="ecf16-117">この API は、EdgeHTML モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ecf16-117">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="ecf16-118">要件</span><span class="sxs-lookup"><span data-stu-id="ecf16-118">Requirements</span></span>  
 <span data-ttu-id="ecf16-119">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="ecf16-119">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ecf16-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="ecf16-120">See Also</span></span>  
 [<span data-ttu-id="ecf16-121">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="ecf16-121">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)