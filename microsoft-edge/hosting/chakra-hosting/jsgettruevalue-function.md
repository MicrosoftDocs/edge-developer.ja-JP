---
description: 現在のスクリプトコンテキスト内の値を取得し `true` ます。
title: JsGetTrueValue 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetTrueValue
helpviewer_keywords:
- JsGetTrueValue function
ms.assetid: c2a56d48-344b-492b-90b8-f570710f8310
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 620ed775947db9d7156d61df1cfdf974a46baec2
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569303"
---
# <span data-ttu-id="bfc93-103">JsGetTrueValue 関数</span><span class="sxs-lookup"><span data-stu-id="bfc93-103">JsGetTrueValue Function</span></span>
<span data-ttu-id="bfc93-104">現在のスクリプトコンテキスト内の値を取得し `true` ます。</span><span class="sxs-lookup"><span data-stu-id="bfc93-104">Gets the value of `true` in the current script context.</span></span>  
  
## <span data-ttu-id="bfc93-105">構文</span><span class="sxs-lookup"><span data-stu-id="bfc93-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetTrueValue(  
   _Out_ JsValueRef *trueValue  
);  
```  
  
#### <span data-ttu-id="bfc93-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bfc93-106">Parameters</span></span>  
 `trueValue`  
 <span data-ttu-id="bfc93-107">`true`値。</span><span class="sxs-lookup"><span data-stu-id="bfc93-107">The `true` value.</span></span>  
  
## <span data-ttu-id="bfc93-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="bfc93-108">Return Value</span></span>  
 <span data-ttu-id="bfc93-109">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="bfc93-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="bfc93-110">注釈</span><span class="sxs-lookup"><span data-stu-id="bfc93-110">Remarks</span></span>  
 <span data-ttu-id="bfc93-111">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="bfc93-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="bfc93-112">要件</span><span class="sxs-lookup"><span data-stu-id="bfc93-112">Requirements</span></span>  
 <span data-ttu-id="bfc93-113">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="bfc93-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="bfc93-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="bfc93-114">See Also</span></span>  
 [<span data-ttu-id="bfc93-115">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="bfc93-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)