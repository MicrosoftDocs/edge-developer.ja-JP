---
description: オブジェクトのプロパティを取得します。
title: JsGetProperty 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetProperty
helpviewer_keywords:
- JsGetProperty function
ms.assetid: 606bc14f-e849-4f88-a148-6660e923c07b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: ea0e5a3bad9363800d2b4a3a18ab932ecc384486
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570448"
---
# <span data-ttu-id="068e5-103">JsGetProperty 関数</span><span class="sxs-lookup"><span data-stu-id="068e5-103">JsGetProperty Function</span></span>
<span data-ttu-id="068e5-104">オブジェクトのプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="068e5-104">Gets an object's property.</span></span>  
  
## <span data-ttu-id="068e5-105">構文</span><span class="sxs-lookup"><span data-stu-id="068e5-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="068e5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="068e5-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="068e5-107">プロパティを含むオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="068e5-107">The object that contains the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="068e5-108">プロパティの ID です。</span><span class="sxs-lookup"><span data-stu-id="068e5-108">The ID of the property.</span></span>  
  
 `value`  
 <span data-ttu-id="068e5-109">プロパティの値。</span><span class="sxs-lookup"><span data-stu-id="068e5-109">The value of the property.</span></span>  
  
## <span data-ttu-id="068e5-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="068e5-110">Return Value</span></span>  
 <span data-ttu-id="068e5-111">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="068e5-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="068e5-112">注釈</span><span class="sxs-lookup"><span data-stu-id="068e5-112">Remarks</span></span>  
 <span data-ttu-id="068e5-113">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="068e5-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="068e5-114">要件</span><span class="sxs-lookup"><span data-stu-id="068e5-114">Requirements</span></span>  
 <span data-ttu-id="068e5-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="068e5-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="068e5-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="068e5-116">See Also</span></span>  
 [<span data-ttu-id="068e5-117">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="068e5-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)