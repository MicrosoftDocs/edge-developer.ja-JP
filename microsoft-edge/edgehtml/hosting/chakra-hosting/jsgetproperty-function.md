---
description: オブジェクトのプロパティを取得します。
title: JsGetProperty 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetProperty
helpviewer_keywords:
- JsGetProperty function
ms.assetid: 606bc14f-e849-4f88-a148-6660e923c07b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e5731fa3f889fc1b182f88e37ae90c96d3825402
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234332"
---
# <span data-ttu-id="8fd77-103">JsGetProperty 関数</span><span class="sxs-lookup"><span data-stu-id="8fd77-103">JsGetProperty Function</span></span>

<span data-ttu-id="8fd77-104">オブジェクトのプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="8fd77-104">Gets an object's property.</span></span>  
  
## <span data-ttu-id="8fd77-105">構文</span><span class="sxs-lookup"><span data-stu-id="8fd77-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="8fd77-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8fd77-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="8fd77-107">プロパティを含むオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="8fd77-107">The object that contains the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="8fd77-108">プロパティの ID。</span><span class="sxs-lookup"><span data-stu-id="8fd77-108">The ID of the property.</span></span>  
  
 `value`  
 <span data-ttu-id="8fd77-109">プロパティの値。</span><span class="sxs-lookup"><span data-stu-id="8fd77-109">The value of the property.</span></span>  
  
## <span data-ttu-id="8fd77-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="8fd77-110">Return Value</span></span>  
 <span data-ttu-id="8fd77-111">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="8fd77-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="8fd77-112">注釈</span><span class="sxs-lookup"><span data-stu-id="8fd77-112">Remarks</span></span>  
 <span data-ttu-id="8fd77-113">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="8fd77-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="8fd77-114">要件</span><span class="sxs-lookup"><span data-stu-id="8fd77-114">Requirements</span></span>  
 <span data-ttu-id="8fd77-115">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="8fd77-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="8fd77-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="8fd77-116">See Also</span></span>  
 [<span data-ttu-id="8fd77-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="8fd77-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
