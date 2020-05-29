---
description: 記号に関連付けられているプロパティ ID を取得します。
title: JsGetPropertyIdFromSymbol 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 190fe4b9-352e-4b10-9d0e-6c6bbd6363e8
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 0d11dbaf25b85e2bcd85a0cf2bac1b499fd4fa3e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570447"
---
# <span data-ttu-id="823f8-103">JsGetPropertyIdFromSymbol 関数</span><span class="sxs-lookup"><span data-stu-id="823f8-103">JsGetPropertyIdFromSymbol Function</span></span>
<span data-ttu-id="823f8-104">記号に関連付けられているプロパティ ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="823f8-104">Gets the property ID associated with the symbol.</span></span>  
  
## <span data-ttu-id="823f8-105">構文</span><span class="sxs-lookup"><span data-stu-id="823f8-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPropertyIdFromSymbol(  
   _In_ JsValueRef symbol,  
   _Out_ JsPropertyIdRef *propertyId  
);  
```  
  
#### <span data-ttu-id="823f8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="823f8-106">Parameters</span></span>  
 `symbol`  
 <span data-ttu-id="823f8-107">プロパティ ID を取得する対象のシンボル。</span><span class="sxs-lookup"><span data-stu-id="823f8-107">The symbol whose property ID is being retrieved.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="823f8-108">指定されたシンボルのプロパティ ID。</span><span class="sxs-lookup"><span data-stu-id="823f8-108">The property ID for the given symbol.</span></span>  
  
## <span data-ttu-id="823f8-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="823f8-109">Return Value</span></span>  
 <span data-ttu-id="823f8-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="823f8-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="823f8-111">注釈</span><span class="sxs-lookup"><span data-stu-id="823f8-111">Remarks</span></span>  
 <span data-ttu-id="823f8-112">プロパティ Id はコンテキストに固有であり、コンテキスト間では使用できません。</span><span class="sxs-lookup"><span data-stu-id="823f8-112">Property IDs are specific to a context and cannot be used across contexts.</span></span>  
  
 <span data-ttu-id="823f8-113">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="823f8-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="823f8-114">この API は、Microsoft Edge モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="823f8-114">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="823f8-115">要件</span><span class="sxs-lookup"><span data-stu-id="823f8-115">Requirements</span></span>  
 <span data-ttu-id="823f8-116">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="823f8-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="823f8-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="823f8-117">See Also</span></span>  
 [<span data-ttu-id="823f8-118">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="823f8-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)