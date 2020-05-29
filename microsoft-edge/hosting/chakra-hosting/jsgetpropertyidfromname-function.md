---
description: 名前に関連付けられているプロパティ ID を取得します。
title: JsGetPropertyIdFromName 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetPropertyIdFromName
helpviewer_keywords:
- JsGetPropertyIdFromName function
ms.assetid: 1674906f-746a-4c62-99cd-023276683a86
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: e1954b86937056523a30c15dbf350ac02fd63dde
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570446"
---
# <span data-ttu-id="f47be-103">JsGetPropertyIdFromName 関数</span><span class="sxs-lookup"><span data-stu-id="f47be-103">JsGetPropertyIdFromName Function</span></span>
<span data-ttu-id="f47be-104">名前に関連付けられているプロパティ ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="f47be-104">Gets the property ID associated with the name.</span></span>  
  
## <span data-ttu-id="f47be-105">構文</span><span class="sxs-lookup"><span data-stu-id="f47be-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPropertyIdFromName(  
   _In_z_ const wchar_t *name,  
   _Out_ JsPropertyIdRef *propertyId  
);  
```  
  
#### <span data-ttu-id="f47be-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f47be-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="f47be-107">取得または作成するプロパティ ID の名前。</span><span class="sxs-lookup"><span data-stu-id="f47be-107">The name of the property ID to get or create.</span></span> <span data-ttu-id="f47be-108">この名前は、数字のみで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f47be-108">The name may consist of only digits.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="f47be-109">指定した名前のこのランタイムのプロパティ ID。</span><span class="sxs-lookup"><span data-stu-id="f47be-109">The property ID in this runtime for the given name.</span></span>  
  
## <span data-ttu-id="f47be-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="f47be-110">Return Value</span></span>  
 <span data-ttu-id="f47be-111">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="f47be-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="f47be-112">注釈</span><span class="sxs-lookup"><span data-stu-id="f47be-112">Remarks</span></span>  
 <span data-ttu-id="f47be-113">プロパティ Id はコンテキストに固有であり、コンテキスト間では使用できません。</span><span class="sxs-lookup"><span data-stu-id="f47be-113">Property IDs are specific to a context and cannot be used across contexts.</span></span>  
  
 <span data-ttu-id="f47be-114">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="f47be-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="f47be-115">要件</span><span class="sxs-lookup"><span data-stu-id="f47be-115">Requirements</span></span>  
 <span data-ttu-id="f47be-116">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="f47be-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="f47be-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f47be-117">See Also</span></span>  
 [<span data-ttu-id="f47be-118">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="f47be-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)