---
description: 二重値から数値を作成します。
title: JsDoubleToNumber 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsDoubleToNumber
helpviewer_keywords:
- JsDoubleToNumber function
ms.assetid: 43eb2ee1-2789-4302-954e-c4087e1ee786
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d3385633f41c2e20c43ca865eaeec763b6ff7f43
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234728"
---
# <span data-ttu-id="bfa96-103">JsDoubleToNumber 関数</span><span class="sxs-lookup"><span data-stu-id="bfa96-103">JsDoubleToNumber Function</span></span>

<span data-ttu-id="bfa96-104">値から数値を作成 `double` します。</span><span class="sxs-lookup"><span data-stu-id="bfa96-104">Creates a number value from a `double` value.</span></span>  
  
## <span data-ttu-id="bfa96-105">構文</span><span class="sxs-lookup"><span data-stu-id="bfa96-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDoubleToNumber(  
   _In_ double doubleValue,  
   _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="bfa96-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bfa96-106">Parameters</span></span>  
 `doubleValue`  
 <span data-ttu-id="bfa96-107">数値 `double` に変換する値を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfa96-107">The `double` to convert to a number value.</span></span>  
  
 `value`  
 <span data-ttu-id="bfa96-108">新しい数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfa96-108">The new number value.</span></span>  
  
## <span data-ttu-id="bfa96-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="bfa96-109">Return Value</span></span>  
 <span data-ttu-id="bfa96-110">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="bfa96-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="bfa96-111">注釈</span><span class="sxs-lookup"><span data-stu-id="bfa96-111">Remarks</span></span>  
 <span data-ttu-id="bfa96-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="bfa96-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="bfa96-113">要件</span><span class="sxs-lookup"><span data-stu-id="bfa96-113">Requirements</span></span>  
 <span data-ttu-id="bfa96-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="bfa96-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="bfa96-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="bfa96-115">See Also</span></span>  
 [<span data-ttu-id="bfa96-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="bfa96-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
