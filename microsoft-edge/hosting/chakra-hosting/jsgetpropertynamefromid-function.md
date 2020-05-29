---
description: プロパティ ID に関連付けられている名前を取得します。
title: JsGetPropertyNameFromId 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetPropertyNameFromId
helpviewer_keywords:
- JsGetPropertyNameFromId function
ms.assetid: b4ca442c-573d-4bc3-adf7-1b8d48480b3a
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1e76c69c1d746302bb95cd7229872845c4fbcc88
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569317"
---
# <span data-ttu-id="794a9-103">JsGetPropertyNameFromId 関数</span><span class="sxs-lookup"><span data-stu-id="794a9-103">JsGetPropertyNameFromId Function</span></span>
<span data-ttu-id="794a9-104">プロパティ ID に関連付けられている名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="794a9-104">Gets the name associated with the property ID.</span></span>  
  
## <span data-ttu-id="794a9-105">構文</span><span class="sxs-lookup"><span data-stu-id="794a9-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPropertyNameFromId(  
   _In_ JsPropertyIdRef propertyId,  
   _Outptr_result_z_ const wchar_t **name  
);  
```  
  
#### <span data-ttu-id="794a9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="794a9-106">Parameters</span></span>  
 `propertyId`  
 <span data-ttu-id="794a9-107">名前を取得するプロパティ ID。</span><span class="sxs-lookup"><span data-stu-id="794a9-107">The property ID to get the name of.</span></span>  
  
 `name`  
 <span data-ttu-id="794a9-108">プロパティ ID に関連付けられている名前。</span><span class="sxs-lookup"><span data-stu-id="794a9-108">The name associated with the property ID.</span></span>  
  
## <span data-ttu-id="794a9-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="794a9-109">Return Value</span></span>  
 <span data-ttu-id="794a9-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="794a9-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="794a9-111">注釈</span><span class="sxs-lookup"><span data-stu-id="794a9-111">Remarks</span></span>  
 <span data-ttu-id="794a9-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="794a9-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="794a9-113">返されるバッファーは、ランタイムが有効であり、ランタイムが破棄されると使うことができない限り、有効です。</span><span class="sxs-lookup"><span data-stu-id="794a9-113">The returned buffer is valid as long as the runtime is alive and cannot be used once the runtime has been disposed.</span></span>  
  
## <span data-ttu-id="794a9-114">要件</span><span class="sxs-lookup"><span data-stu-id="794a9-114">Requirements</span></span>  
 <span data-ttu-id="794a9-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="794a9-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="794a9-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="794a9-116">See Also</span></span>  
 [<span data-ttu-id="794a9-117">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="794a9-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)