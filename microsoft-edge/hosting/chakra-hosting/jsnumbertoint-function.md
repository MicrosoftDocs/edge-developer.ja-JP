---
description: '`int`数値の値を取得します。'
title: JsNumberToInt 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 8b9256d6-76ac-4c74-a97c-fbb16c13f5f5
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: cf4c8cb42c737cfb9efee5422fe6bb3c1389cbfd
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570423"
---
# <span data-ttu-id="2f18f-103">JsNumberToInt 関数</span><span class="sxs-lookup"><span data-stu-id="2f18f-103">JsNumberToInt Function</span></span>
<span data-ttu-id="2f18f-104">`int`数値の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="2f18f-104">Retrieves the `int` value of a number value.</span></span>  
  
## <span data-ttu-id="2f18f-105">構文</span><span class="sxs-lookup"><span data-stu-id="2f18f-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsNumberToInt(  
      _In_ JsValueRef value,  
      _Out_ int *intValue  
);  
```  
  
#### <span data-ttu-id="2f18f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2f18f-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="2f18f-107">値に変換する数値 `int` 。</span><span class="sxs-lookup"><span data-stu-id="2f18f-107">The number value to convert to an `int` value.</span></span>  
  
 `intValue`  
 <span data-ttu-id="2f18f-108">`int`値。</span><span class="sxs-lookup"><span data-stu-id="2f18f-108">The `int` value.</span></span>  
  
## <span data-ttu-id="2f18f-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="2f18f-109">Return Value</span></span>  
  
## <span data-ttu-id="2f18f-110">注釈</span><span class="sxs-lookup"><span data-stu-id="2f18f-110">Remarks</span></span>  
 <span data-ttu-id="2f18f-111">この関数は、数値の値を取得し、値に変換し `int` ます。</span><span class="sxs-lookup"><span data-stu-id="2f18f-111">This function retrieves the value of a number value and converts to an `int` value.</span></span> <span data-ttu-id="2f18f-112">`JsErrorInvalidArgument`値の型が数値以外の場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="2f18f-112">It will fail with `JsErrorInvalidArgument` if the type of the value is not number.</span></span>  
  
 <span data-ttu-id="2f18f-113">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="2f18f-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="2f18f-114">この API は、EdgeHTML モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2f18f-114">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="2f18f-115">要件</span><span class="sxs-lookup"><span data-stu-id="2f18f-115">Requirements</span></span>  
 <span data-ttu-id="2f18f-116">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="2f18f-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="2f18f-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f18f-117">See Also</span></span>  
 [<span data-ttu-id="2f18f-118">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="2f18f-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)