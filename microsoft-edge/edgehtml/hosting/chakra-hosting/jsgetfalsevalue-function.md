---
description: 現在のスクリプト コンテキスト `false` の値を取得します。
title: JsGetFalseValue 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetFalseValue
helpviewer_keywords:
- JsGetFalseValue function
ms.assetid: 621a584c-4ca8-4ba0-b19a-6cb50cf830b6
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: c87ad969fc7547f4d650148005327fb93dce805d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234771"
---
# <span data-ttu-id="c68f5-103">JsGetFalseValue 関数</span><span class="sxs-lookup"><span data-stu-id="c68f5-103">JsGetFalseValue Function</span></span>

<span data-ttu-id="c68f5-104">現在のスクリプト コンテキスト `false` の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="c68f5-104">Gets the value of `false` in the current script context.</span></span>  
  
## <span data-ttu-id="c68f5-105">構文</span><span class="sxs-lookup"><span data-stu-id="c68f5-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetFalseValue(  
   _Out_ JsValueRef *falseValue  
);  
```  
  
#### <span data-ttu-id="c68f5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c68f5-106">Parameters</span></span>  
 `falseValue`  
 <span data-ttu-id="c68f5-107">値 `false` を指定します。</span><span class="sxs-lookup"><span data-stu-id="c68f5-107">The `false` value.</span></span>  
  
## <span data-ttu-id="c68f5-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="c68f5-108">Return Value</span></span>  
 <span data-ttu-id="c68f5-109">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="c68f5-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="c68f5-110">注釈</span><span class="sxs-lookup"><span data-stu-id="c68f5-110">Remarks</span></span>  
 <span data-ttu-id="c68f5-111">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="c68f5-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="c68f5-112">要件</span><span class="sxs-lookup"><span data-stu-id="c68f5-112">Requirements</span></span>  
 <span data-ttu-id="c68f5-113">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="c68f5-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="c68f5-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="c68f5-114">See Also</span></span>  
 [<span data-ttu-id="c68f5-115">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="c68f5-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
