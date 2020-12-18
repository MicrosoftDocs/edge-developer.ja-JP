---
description: 数値の `int` 値を取得します。
title: JsNumberToInt 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 8b9256d6-76ac-4c74-a97c-fbb16c13f5f5
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 928be9a7cc5cd3e26e8b8df99af1e08a6c50209c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234867"
---
# <span data-ttu-id="9a2ff-103">JsNumberToInt 関数</span><span class="sxs-lookup"><span data-stu-id="9a2ff-103">JsNumberToInt Function</span></span>

<span data-ttu-id="9a2ff-104">数値の `int` 値を取得します。</span><span class="sxs-lookup"><span data-stu-id="9a2ff-104">Retrieves the `int` value of a number value.</span></span>  
  
## <span data-ttu-id="9a2ff-105">構文</span><span class="sxs-lookup"><span data-stu-id="9a2ff-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsNumberToInt(  
      _In_ JsValueRef value,  
      _Out_ int *intValue  
);  
```  
  
#### <span data-ttu-id="9a2ff-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9a2ff-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="9a2ff-107">値に変換する数値を指定 `int` します。</span><span class="sxs-lookup"><span data-stu-id="9a2ff-107">The number value to convert to an `int` value.</span></span>  
  
 `intValue`  
 <span data-ttu-id="9a2ff-108">値 `int` を指定します。</span><span class="sxs-lookup"><span data-stu-id="9a2ff-108">The `int` value.</span></span>  
  
## <span data-ttu-id="9a2ff-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="9a2ff-109">Return Value</span></span>  
  
## <span data-ttu-id="9a2ff-110">注釈</span><span class="sxs-lookup"><span data-stu-id="9a2ff-110">Remarks</span></span>  
 <span data-ttu-id="9a2ff-111">この関数は数値の値を取得し、値に変換 `int` します。</span><span class="sxs-lookup"><span data-stu-id="9a2ff-111">This function retrieves the value of a number value and converts to an `int` value.</span></span> <span data-ttu-id="9a2ff-112">値の型が `JsErrorInvalidArgument` 数値ではない場合は失敗します。</span><span class="sxs-lookup"><span data-stu-id="9a2ff-112">It will fail with `JsErrorInvalidArgument` if the type of the value is not number.</span></span>  
  
 <span data-ttu-id="9a2ff-113">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="9a2ff-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="9a2ff-114">この API は EdgeHTML モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9a2ff-114">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="9a2ff-115">要件</span><span class="sxs-lookup"><span data-stu-id="9a2ff-115">Requirements</span></span>  
 <span data-ttu-id="9a2ff-116">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="9a2ff-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="9a2ff-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a2ff-117">See Also</span></span>  
 [<span data-ttu-id="9a2ff-118">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="9a2ff-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
