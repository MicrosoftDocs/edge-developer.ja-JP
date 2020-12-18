---
description: オブジェクトのインデックス付きプロパティの外部データ情報を取得します。
title: JsGetIndexedPropertiesExternalData 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 2c313163-3462-42fd-8dee-3dfb3ac7f43f
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 627aaef48def2e042927467e1cbb6d6b7c06a525
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234358"
---
# <span data-ttu-id="97f12-103">JsGetIndexedPropertiesExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="97f12-103">JsGetIndexedPropertiesExternalData Function</span></span>

<span data-ttu-id="97f12-104">オブジェクトのインデックス付きプロパティの外部データ情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="97f12-104">Retrieves an object's indexed properties external data information.</span></span>  
  
## <span data-ttu-id="97f12-105">構文</span><span class="sxs-lookup"><span data-stu-id="97f12-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetIndexedPropertiesExternalData(  
   _In_ JsValueRef object,  
   _Out_ void** data,  
   _Out_ JsTypedArrayType* arrayType,  
   _Out_ unsigned int* elementLength  
);  
```  
  
#### <span data-ttu-id="97f12-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="97f12-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="97f12-107">オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="97f12-107">The object.</span></span>  
  
 `data`  
 <span data-ttu-id="97f12-108">オブジェクトのインデックス付きプロパティの外部データ バック ストア。</span><span class="sxs-lookup"><span data-stu-id="97f12-108">The external data back store for the object's indexed properties.</span></span>  
  
 `arrayType`  
 <span data-ttu-id="97f12-109">外部データの配列要素型。</span><span class="sxs-lookup"><span data-stu-id="97f12-109">The array element type in external data.</span></span>  
  
 `elementLength`  
 <span data-ttu-id="97f12-110">外部データ内の配列要素の数。</span><span class="sxs-lookup"><span data-stu-id="97f12-110">The number of array elements in external data.</span></span>  
  
## <span data-ttu-id="97f12-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="97f12-111">Return Value</span></span>  
 <span data-ttu-id="97f12-112">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="97f12-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="97f12-113">注釈</span><span class="sxs-lookup"><span data-stu-id="97f12-113">Remarks</span></span>  
 <span data-ttu-id="97f12-114">この API は、Microsoft Edge モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="97f12-114">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="97f12-115">要件</span><span class="sxs-lookup"><span data-stu-id="97f12-115">Requirements</span></span>  
 <span data-ttu-id="97f12-116">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="97f12-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="97f12-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="97f12-117">See Also</span></span>  
 [<span data-ttu-id="97f12-118">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="97f12-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
