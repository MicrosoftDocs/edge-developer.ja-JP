---
description: Double 値から数値を作成します。
title: JsDoubleToNumber 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsDoubleToNumber
helpviewer_keywords:
- JsDoubleToNumber function
ms.assetid: 43eb2ee1-2789-4302-954e-c4087e1ee786
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c33adbe217f27f77e348fc56e87c4587c6a6ec4c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570472"
---
# <span data-ttu-id="206d8-103">JsDoubleToNumber 関数</span><span class="sxs-lookup"><span data-stu-id="206d8-103">JsDoubleToNumber Function</span></span>
<span data-ttu-id="206d8-104">値から数値を作成し `double` ます。</span><span class="sxs-lookup"><span data-stu-id="206d8-104">Creates a number value from a `double` value.</span></span>  
  
## <span data-ttu-id="206d8-105">構文</span><span class="sxs-lookup"><span data-stu-id="206d8-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDoubleToNumber(  
   _In_ double doubleValue,  
   _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="206d8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="206d8-106">Parameters</span></span>  
 `doubleValue`  
 <span data-ttu-id="206d8-107">`double`数値に変換するには、を指定します。</span><span class="sxs-lookup"><span data-stu-id="206d8-107">The `double` to convert to a number value.</span></span>  
  
 `value`  
 <span data-ttu-id="206d8-108">新しい数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="206d8-108">The new number value.</span></span>  
  
## <span data-ttu-id="206d8-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="206d8-109">Return Value</span></span>  
 <span data-ttu-id="206d8-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="206d8-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="206d8-111">注釈</span><span class="sxs-lookup"><span data-stu-id="206d8-111">Remarks</span></span>  
 <span data-ttu-id="206d8-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="206d8-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="206d8-113">要件</span><span class="sxs-lookup"><span data-stu-id="206d8-113">Requirements</span></span>  
 <span data-ttu-id="206d8-114">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="206d8-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="206d8-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="206d8-115">See Also</span></span>  
 [<span data-ttu-id="206d8-116">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="206d8-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)