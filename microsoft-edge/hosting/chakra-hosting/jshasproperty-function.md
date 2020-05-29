---
description: オブジェクトにプロパティがあるかどうかを判別します。
title: JsHasProperty 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsHasProperty
helpviewer_keywords:
- JsHasProperty function
ms.assetid: 26c94c3d-aae6-4257-8644-df63c7e714fb
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c6cc195ae02c28500f0a018256d24278ad4b47d8
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570427"
---
# <span data-ttu-id="ae211-103">JsHasProperty 関数</span><span class="sxs-lookup"><span data-stu-id="ae211-103">JsHasProperty Function</span></span>
<span data-ttu-id="ae211-104">オブジェクトにプロパティがあるかどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="ae211-104">Determines whether an object has a property.</span></span>  
  
## <span data-ttu-id="ae211-105">構文</span><span class="sxs-lookup"><span data-stu-id="ae211-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsHasProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ bool *hasProperty  
);  
```  
  
#### <span data-ttu-id="ae211-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ae211-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="ae211-107">プロパティを含む可能性のあるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ae211-107">The object that may contain the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="ae211-108">プロパティの ID です。</span><span class="sxs-lookup"><span data-stu-id="ae211-108">The ID of the property.</span></span>  
  
 `hasProperty`  
 <span data-ttu-id="ae211-109">オブジェクト (またはプロトタイプ) にプロパティが含まれているかどうか。</span><span class="sxs-lookup"><span data-stu-id="ae211-109">Whether the object (or a prototype) has the property.</span></span>  
  
## <span data-ttu-id="ae211-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="ae211-110">Return Value</span></span>  
 <span data-ttu-id="ae211-111">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="ae211-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="ae211-112">注釈</span><span class="sxs-lookup"><span data-stu-id="ae211-112">Remarks</span></span>  
 <span data-ttu-id="ae211-113">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="ae211-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="ae211-114">要件</span><span class="sxs-lookup"><span data-stu-id="ae211-114">Requirements</span></span>  
 <span data-ttu-id="ae211-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="ae211-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ae211-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae211-116">See Also</span></span>  
 [<span data-ttu-id="ae211-117">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="ae211-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)