---
description: '`double`数値の値を取得します。'
title: JsNumberToDouble 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsNumberToDouble
helpviewer_keywords:
- JsNumberToDouble function
ms.assetid: 5f52e8b6-2b70-49a3-879a-bd83ebf2ac33
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: fc99e02aa0376bb100b4e1302c29532a57bd539f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569283"
---
# <span data-ttu-id="299ac-103">JsNumberToDouble 関数</span><span class="sxs-lookup"><span data-stu-id="299ac-103">JsNumberToDouble Function</span></span>
<span data-ttu-id="299ac-104">`double`数値の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="299ac-104">Retrieves the `double` value of a number value.</span></span>  
  
## <span data-ttu-id="299ac-105">構文</span><span class="sxs-lookup"><span data-stu-id="299ac-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsNumberToDouble(  
   _In_ JsValueRef value,  
   _Out_ double *doubleValue  
);  
```  
  
#### <span data-ttu-id="299ac-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="299ac-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="299ac-107">値に変換する数値 `double` 。</span><span class="sxs-lookup"><span data-stu-id="299ac-107">The number value to convert to a `double` value.</span></span>  
  
 `doubleValue`  
 <span data-ttu-id="299ac-108">`double`値。</span><span class="sxs-lookup"><span data-stu-id="299ac-108">The `double` value.</span></span>  
  
## <span data-ttu-id="299ac-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="299ac-109">Return Value</span></span>  
 <span data-ttu-id="299ac-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="299ac-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="299ac-111">注釈</span><span class="sxs-lookup"><span data-stu-id="299ac-111">Remarks</span></span>  
 <span data-ttu-id="299ac-112">この関数は、数値の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="299ac-112">This function retrieves the value of a number value.</span></span> <span data-ttu-id="299ac-113">`JsErrorInvalidArgument`値の型が数値以外の場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="299ac-113">It will fail with `JsErrorInvalidArgument` if the type of the value is not number.</span></span>  
  
 <span data-ttu-id="299ac-114">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="299ac-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="299ac-115">要件</span><span class="sxs-lookup"><span data-stu-id="299ac-115">Requirements</span></span>  
 <span data-ttu-id="299ac-116">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="299ac-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="299ac-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="299ac-117">See Also</span></span>  
 [<span data-ttu-id="299ac-118">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="299ac-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)