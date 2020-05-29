---
description: オブジェクトが外部オブジェクトかどうかを判別します。
title: JsHasExternalData 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsHasExternalData
helpviewer_keywords:
- JsHasExternalData function
ms.assetid: a077e3ac-4f6f-4d94-8398-f1b5cc4c18e0
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 0ca86df09264eb82dac2e928874ca15edd2c8c8e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570434"
---
# <span data-ttu-id="2e777-103">JsHasExternalData 関数</span><span class="sxs-lookup"><span data-stu-id="2e777-103">JsHasExternalData Function</span></span>
<span data-ttu-id="2e777-104">オブジェクトが外部オブジェクトかどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="2e777-104">Determines whether an object is an external object.</span></span>  
  
## <span data-ttu-id="2e777-105">構文</span><span class="sxs-lookup"><span data-stu-id="2e777-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsHasExternalData(  
   _In_ JsValueRef object,  
   _Out_ bool *value  
);  
```  
  
#### <span data-ttu-id="2e777-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2e777-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="2e777-107">オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2e777-107">The object.</span></span>  
  
 `value`  
 <span data-ttu-id="2e777-108">オブジェクトが外部オブジェクトであるかどうか</span><span class="sxs-lookup"><span data-stu-id="2e777-108">Whether the object is an external object.</span></span>  
  
## <span data-ttu-id="2e777-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="2e777-109">Return Value</span></span>  
 <span data-ttu-id="2e777-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="2e777-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="2e777-111">注釈</span><span class="sxs-lookup"><span data-stu-id="2e777-111">Remarks</span></span>  
 <span data-ttu-id="2e777-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="2e777-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="2e777-113">要件</span><span class="sxs-lookup"><span data-stu-id="2e777-113">Requirements</span></span>  
 <span data-ttu-id="2e777-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="2e777-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="2e777-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e777-115">See Also</span></span>  
 [<span data-ttu-id="2e777-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="2e777-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)