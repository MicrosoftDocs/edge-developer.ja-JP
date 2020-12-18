---
description: シンボルに関連付けられているプロパティ ID を取得します。
title: JsGetPropertyIdFromSymbol 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 190fe4b9-352e-4b10-9d0e-6c6bbd6363e8
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d97f1fb517164d692cdd010f899dc40d2e3596ed
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234912"
---
# <span data-ttu-id="e9134-103">JsGetPropertyIdFromSymbol 関数</span><span class="sxs-lookup"><span data-stu-id="e9134-103">JsGetPropertyIdFromSymbol Function</span></span>

<span data-ttu-id="e9134-104">シンボルに関連付けられているプロパティ ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="e9134-104">Gets the property ID associated with the symbol.</span></span>  
  
## <span data-ttu-id="e9134-105">構文</span><span class="sxs-lookup"><span data-stu-id="e9134-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPropertyIdFromSymbol(  
   _In_ JsValueRef symbol,  
   _Out_ JsPropertyIdRef *propertyId  
);  
```  
  
#### <span data-ttu-id="e9134-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e9134-106">Parameters</span></span>  
 `symbol`  
 <span data-ttu-id="e9134-107">プロパティ ID が取得されるシンボル。</span><span class="sxs-lookup"><span data-stu-id="e9134-107">The symbol whose property ID is being retrieved.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="e9134-108">指定されたシンボルのプロパティ ID。</span><span class="sxs-lookup"><span data-stu-id="e9134-108">The property ID for the given symbol.</span></span>  
  
## <span data-ttu-id="e9134-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="e9134-109">Return Value</span></span>  
 <span data-ttu-id="e9134-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="e9134-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="e9134-111">注釈</span><span class="sxs-lookup"><span data-stu-id="e9134-111">Remarks</span></span>  
 <span data-ttu-id="e9134-112">プロパティの ID はコンテキストに固有の値であり、コンテキスト間では使用できません。</span><span class="sxs-lookup"><span data-stu-id="e9134-112">Property IDs are specific to a context and cannot be used across contexts.</span></span>  
  
 <span data-ttu-id="e9134-113">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="e9134-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="e9134-114">この API は、Microsoft Edge モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e9134-114">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="e9134-115">要件</span><span class="sxs-lookup"><span data-stu-id="e9134-115">Requirements</span></span>  
 <span data-ttu-id="e9134-116">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="e9134-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="e9134-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9134-117">See Also</span></span>  
 [<span data-ttu-id="e9134-118">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="e9134-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
