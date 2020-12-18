---
description: 数値の `double` 値を取得します。
title: JsNumberToDouble 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsNumberToDouble
helpviewer_keywords:
- JsNumberToDouble function
ms.assetid: 5f52e8b6-2b70-49a3-879a-bd83ebf2ac33
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e4ae744f091045116a639aff619c475c7c7025f3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234869"
---
# <span data-ttu-id="fac2c-103">JsNumberToDouble 関数</span><span class="sxs-lookup"><span data-stu-id="fac2c-103">JsNumberToDouble Function</span></span>

<span data-ttu-id="fac2c-104">数値の `double` 値を取得します。</span><span class="sxs-lookup"><span data-stu-id="fac2c-104">Retrieves the `double` value of a number value.</span></span>  
  
## <span data-ttu-id="fac2c-105">構文</span><span class="sxs-lookup"><span data-stu-id="fac2c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsNumberToDouble(  
   _In_ JsValueRef value,  
   _Out_ double *doubleValue  
);  
```  
  
#### <span data-ttu-id="fac2c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fac2c-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="fac2c-107">値に変換する数値を指定 `double` します。</span><span class="sxs-lookup"><span data-stu-id="fac2c-107">The number value to convert to a `double` value.</span></span>  
  
 `doubleValue`  
 <span data-ttu-id="fac2c-108">値 `double` を指定します。</span><span class="sxs-lookup"><span data-stu-id="fac2c-108">The `double` value.</span></span>  
  
## <span data-ttu-id="fac2c-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="fac2c-109">Return Value</span></span>  
 <span data-ttu-id="fac2c-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="fac2c-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="fac2c-111">注釈</span><span class="sxs-lookup"><span data-stu-id="fac2c-111">Remarks</span></span>  
 <span data-ttu-id="fac2c-112">この関数は数値の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="fac2c-112">This function retrieves the value of a number value.</span></span> <span data-ttu-id="fac2c-113">値の型が `JsErrorInvalidArgument` 数値ではない場合は失敗します。</span><span class="sxs-lookup"><span data-stu-id="fac2c-113">It will fail with `JsErrorInvalidArgument` if the type of the value is not number.</span></span>  
  
 <span data-ttu-id="fac2c-114">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="fac2c-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="fac2c-115">要件</span><span class="sxs-lookup"><span data-stu-id="fac2c-115">Requirements</span></span>  
 <span data-ttu-id="fac2c-116">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="fac2c-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="fac2c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="fac2c-117">See Also</span></span>  
 [<span data-ttu-id="fac2c-118">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="fac2c-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
