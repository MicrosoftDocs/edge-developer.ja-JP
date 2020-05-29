---
description: オブジェクトのプロパティを配置します。
title: JsSetProperty 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetProperty
helpviewer_keywords:
- JsSetProperty function
ms.assetid: 2c36bebf-ec86-425c-8131-2dd75fd30f40
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 2aba03a73f35284f79355a7d93161d9a9518012c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570368"
---
# <span data-ttu-id="46d65-103">JsSetProperty 関数</span><span class="sxs-lookup"><span data-stu-id="46d65-103">JsSetProperty Function</span></span>
<span data-ttu-id="46d65-104">オブジェクトのプロパティを配置します。</span><span class="sxs-lookup"><span data-stu-id="46d65-104">Puts an object's property.</span></span>  
  
## <span data-ttu-id="46d65-105">構文</span><span class="sxs-lookup"><span data-stu-id="46d65-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _In_ JsValueRef value,  
   _In_ bool useStrictRules  
);  
```  
  
#### <span data-ttu-id="46d65-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="46d65-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="46d65-107">プロパティを含むオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="46d65-107">The object that contains the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="46d65-108">プロパティの ID です。</span><span class="sxs-lookup"><span data-stu-id="46d65-108">The ID of the property.</span></span>  
  
 `value`  
 <span data-ttu-id="46d65-109">プロパティの新しい値。</span><span class="sxs-lookup"><span data-stu-id="46d65-109">The new value of the property.</span></span>  
  
 `useStrictRules`  
 <span data-ttu-id="46d65-110">プロパティセットは、strict モードの規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d65-110">The property set should follow strict mode rules.</span></span>  
  
## <span data-ttu-id="46d65-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="46d65-111">Return Value</span></span>  
 <span data-ttu-id="46d65-112">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="46d65-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="46d65-113">注釈</span><span class="sxs-lookup"><span data-stu-id="46d65-113">Remarks</span></span>  
 <span data-ttu-id="46d65-114">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="46d65-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="46d65-115">要件</span><span class="sxs-lookup"><span data-stu-id="46d65-115">Requirements</span></span>  
 <span data-ttu-id="46d65-116">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="46d65-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="46d65-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="46d65-117">See Also</span></span>  
 [<span data-ttu-id="46d65-118">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="46d65-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)