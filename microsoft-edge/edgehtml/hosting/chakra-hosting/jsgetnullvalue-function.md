---
description: 現在のスクリプト コンテキスト `null` の値を取得します。
title: JsGetNullValue 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetNullValue
helpviewer_keywords:
- JsGetNullValue function
ms.assetid: 132a1496-8dfe-4d3c-a8f8-389f5b0b50d2
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 31e1ba19f9f27e75f0166238d98390e2c4a26c24
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234355"
---
# <span data-ttu-id="15c98-103">JsGetNullValue 関数</span><span class="sxs-lookup"><span data-stu-id="15c98-103">JsGetNullValue Function</span></span>

<span data-ttu-id="15c98-104">現在のスクリプト コンテキスト `null` の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="15c98-104">Gets the value of `null` in the current script context.</span></span>  
  
## <span data-ttu-id="15c98-105">構文</span><span class="sxs-lookup"><span data-stu-id="15c98-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetNullValue(  
   _Out_ JsValueRef *nullValue  
);  
```  
  
#### <span data-ttu-id="15c98-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="15c98-106">Parameters</span></span>  
 `nullValue`  
 <span data-ttu-id="15c98-107">値 `null` を指定します。</span><span class="sxs-lookup"><span data-stu-id="15c98-107">The `null` value.</span></span>  
  
## <span data-ttu-id="15c98-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="15c98-108">Return Value</span></span>  
 <span data-ttu-id="15c98-109">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="15c98-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="15c98-110">注釈</span><span class="sxs-lookup"><span data-stu-id="15c98-110">Remarks</span></span>  
 <span data-ttu-id="15c98-111">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="15c98-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="15c98-112">要件</span><span class="sxs-lookup"><span data-stu-id="15c98-112">Requirements</span></span>  
 <span data-ttu-id="15c98-113">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="15c98-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="15c98-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="15c98-114">See Also</span></span>  
 [<span data-ttu-id="15c98-115">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="15c98-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
