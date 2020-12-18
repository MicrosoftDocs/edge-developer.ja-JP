---
description: オブジェクトのインデックス付きプロパティを外部データに設定します。 外部データは、オブジェクトのインデックス付きプロパティのバック ストアとして使用され、型指定された配列のようにアクセスされます。
title: JsSetIndexedPropertiesToExternalData 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: cee2d86d-ed42-4acb-86ef-95a67e63d0d6
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: fa0eba3659c20066913cd42a0a18dd5ffe5f857f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234512"
---
# <span data-ttu-id="47ab0-104">JsSetIndexedPropertiesToExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="47ab0-104">JsSetIndexedPropertiesToExternalData Function</span></span>

<span data-ttu-id="47ab0-105">オブジェクトのインデックス付きプロパティを外部データに設定します。</span><span class="sxs-lookup"><span data-stu-id="47ab0-105">Sets an object's indexed properties to external data.</span></span> <span data-ttu-id="47ab0-106">外部データは、オブジェクトのインデックス付きプロパティのバック ストアとして使用され、型指定された配列のようにアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="47ab0-106">The external data will be used as back store for the object's indexed properties and accessed like a typed array.</span></span>  
  
## <span data-ttu-id="47ab0-107">構文</span><span class="sxs-lookup"><span data-stu-id="47ab0-107">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetIndexedPropertiesToExternalData(  
   _In_ JsValueRef object,  
   _In_ void* data,  
   _In_ JsTypedArrayType arrayType,  
   _In_ unsigned int elementLength  
);  
```  
  
#### <span data-ttu-id="47ab0-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="47ab0-108">Parameters</span></span>  
 `object`  
 <span data-ttu-id="47ab0-109">操作対象のオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="47ab0-109">The object to operate on.</span></span>  
  
 `data`  
 <span data-ttu-id="47ab0-110">オブジェクトのインデックス付きプロパティのバック ストアとして使用される外部データ。</span><span class="sxs-lookup"><span data-stu-id="47ab0-110">The external data to be used as back store for the object's indexed properties.</span></span>  
  
 `arrayType`  
 <span data-ttu-id="47ab0-111">外部データの配列要素型。</span><span class="sxs-lookup"><span data-stu-id="47ab0-111">The array element type in external data.</span></span>  
  
 `elementLength`  
 <span data-ttu-id="47ab0-112">外部データ内の配列要素の数。</span><span class="sxs-lookup"><span data-stu-id="47ab0-112">The number of array elements in external data.</span></span>  
  
## <span data-ttu-id="47ab0-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="47ab0-113">Return Value</span></span>  
 <span data-ttu-id="47ab0-114">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="47ab0-114">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="47ab0-115">注釈</span><span class="sxs-lookup"><span data-stu-id="47ab0-115">Remarks</span></span>  
 <span data-ttu-id="47ab0-116">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="47ab0-116">Requires an active script context.</span></span>  
  
 <span data-ttu-id="47ab0-117">この API は EdgeHTML モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="47ab0-117">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="47ab0-118">要件</span><span class="sxs-lookup"><span data-stu-id="47ab0-118">Requirements</span></span>  
 <span data-ttu-id="47ab0-119">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="47ab0-119">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="47ab0-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="47ab0-120">See Also</span></span>  
 [<span data-ttu-id="47ab0-121">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="47ab0-121">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
