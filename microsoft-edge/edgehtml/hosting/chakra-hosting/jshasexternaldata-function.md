---
description: オブジェクトが外部オブジェクトであるかどうかを判別します。
title: JsHasExternalData 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsHasExternalData
helpviewer_keywords:
- JsHasExternalData function
ms.assetid: a077e3ac-4f6f-4d94-8398-f1b5cc4c18e0
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d73333215a33fc409190a0e33fa616b6350fb2a3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234388"
---
# <span data-ttu-id="9a628-103">JsHasExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="9a628-103">JsHasExternalData Function</span></span>

<span data-ttu-id="9a628-104">オブジェクトが外部オブジェクトであるかどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="9a628-104">Determines whether an object is an external object.</span></span>  
  
## <span data-ttu-id="9a628-105">構文</span><span class="sxs-lookup"><span data-stu-id="9a628-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsHasExternalData(  
   _In_ JsValueRef object,  
   _Out_ bool *value  
);  
```  
  
#### <span data-ttu-id="9a628-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9a628-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="9a628-107">オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9a628-107">The object.</span></span>  
  
 `value`  
 <span data-ttu-id="9a628-108">オブジェクトが外部オブジェクトかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9a628-108">Whether the object is an external object.</span></span>  
  
## <span data-ttu-id="9a628-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="9a628-109">Return Value</span></span>  
 <span data-ttu-id="9a628-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="9a628-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="9a628-111">注釈</span><span class="sxs-lookup"><span data-stu-id="9a628-111">Remarks</span></span>  
 <span data-ttu-id="9a628-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="9a628-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="9a628-113">要件</span><span class="sxs-lookup"><span data-stu-id="9a628-113">Requirements</span></span>  
 <span data-ttu-id="9a628-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="9a628-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="9a628-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a628-115">See Also</span></span>  
 [<span data-ttu-id="9a628-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="9a628-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
