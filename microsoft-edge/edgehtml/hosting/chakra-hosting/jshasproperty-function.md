---
description: オブジェクトにプロパティが含めるかどうかを指定します。
title: JsHasProperty 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsHasProperty
helpviewer_keywords:
- JsHasProperty function
ms.assetid: 26c94c3d-aae6-4257-8644-df63c7e714fb
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e45ecfaafb06c49a6a3773eb798ee93a19fd6d6e
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234737"
---
# <span data-ttu-id="98512-103">JsHasProperty 関数</span><span class="sxs-lookup"><span data-stu-id="98512-103">JsHasProperty Function</span></span>

<span data-ttu-id="98512-104">オブジェクトにプロパティが含めるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="98512-104">Determines whether an object has a property.</span></span>  
  
## <span data-ttu-id="98512-105">構文</span><span class="sxs-lookup"><span data-stu-id="98512-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsHasProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ bool *hasProperty  
);  
```  
  
#### <span data-ttu-id="98512-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="98512-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="98512-107">プロパティを含む可能性があるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="98512-107">The object that may contain the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="98512-108">プロパティの ID。</span><span class="sxs-lookup"><span data-stu-id="98512-108">The ID of the property.</span></span>  
  
 `hasProperty`  
 <span data-ttu-id="98512-109">オブジェクト (またはプロトタイプ) がプロパティを持つかどうか。</span><span class="sxs-lookup"><span data-stu-id="98512-109">Whether the object (or a prototype) has the property.</span></span>  
  
## <span data-ttu-id="98512-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="98512-110">Return Value</span></span>  
 <span data-ttu-id="98512-111">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="98512-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="98512-112">注釈</span><span class="sxs-lookup"><span data-stu-id="98512-112">Remarks</span></span>  
 <span data-ttu-id="98512-113">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="98512-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="98512-114">要件</span><span class="sxs-lookup"><span data-stu-id="98512-114">Requirements</span></span>  
 <span data-ttu-id="98512-115">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="98512-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="98512-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="98512-116">See Also</span></span>  
 [<span data-ttu-id="98512-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="98512-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
