---
description: オブジェクトの指定したインデックスにある値を取得します。
title: JsGetIndexedProperty 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetIndexedProperty
helpviewer_keywords:
- JsGetIndexedProperty function
ms.assetid: f61ea388-0ae6-4a19-b3b5-75ed49a3f32d
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: bd0246464d00884ca71fd8d3564ce775415f6267
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234356"
---
# <span data-ttu-id="89e19-103">JsGetIndexedProperty 関数</span><span class="sxs-lookup"><span data-stu-id="89e19-103">JsGetIndexedProperty Function</span></span>

<span data-ttu-id="89e19-104">オブジェクトの指定したインデックスにある値を取得します。</span><span class="sxs-lookup"><span data-stu-id="89e19-104">Retrieve the value at the specified index of an object.</span></span>  
  
## <span data-ttu-id="89e19-105">構文</span><span class="sxs-lookup"><span data-stu-id="89e19-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetIndexedProperty(  
   _In_ JsValueRef object,  
   _In_ JsValueRef index,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="89e19-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="89e19-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="89e19-107">操作対象のオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="89e19-107">The object to operate on.</span></span>  
  
 `index`  
 <span data-ttu-id="89e19-108">取得するインデックス。</span><span class="sxs-lookup"><span data-stu-id="89e19-108">The index to retrieve.</span></span>  
  
 `result`  
 <span data-ttu-id="89e19-109">取得した値。</span><span class="sxs-lookup"><span data-stu-id="89e19-109">The retrieved value.</span></span>  
  
## <span data-ttu-id="89e19-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="89e19-110">Return Value</span></span>  
 <span data-ttu-id="89e19-111">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="89e19-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="89e19-112">注釈</span><span class="sxs-lookup"><span data-stu-id="89e19-112">Remarks</span></span>  
 <span data-ttu-id="89e19-113">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="89e19-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="89e19-114">要件</span><span class="sxs-lookup"><span data-stu-id="89e19-114">Requirements</span></span>  
 <span data-ttu-id="89e19-115">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="89e19-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="89e19-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="89e19-116">See Also</span></span>  
 [<span data-ttu-id="89e19-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="89e19-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
