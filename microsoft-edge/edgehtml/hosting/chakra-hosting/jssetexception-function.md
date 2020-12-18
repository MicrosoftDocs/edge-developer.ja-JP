---
description: 現在のコンテキストのランタイムを例外状態に設定します。
title: JsSetException 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetException
helpviewer_keywords:
- JsSetException function
ms.assetid: c528793a-2e1b-4ee1-bd2e-e63fd547dc40
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2c2e3840d2a831db23a525c5d8854b9b2fcfb8c9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234725"
---
# <span data-ttu-id="a076f-103">JsSetException 関数</span><span class="sxs-lookup"><span data-stu-id="a076f-103">JsSetException Function</span></span>

<span data-ttu-id="a076f-104">現在のコンテキストのランタイムを例外状態に設定します。</span><span class="sxs-lookup"><span data-stu-id="a076f-104">Sets the runtime of the current context to an exception state.</span></span>  
  
## <span data-ttu-id="a076f-105">構文</span><span class="sxs-lookup"><span data-stu-id="a076f-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetException(  
   _In_ JsValueRef exception  
);  
```  
  
#### <span data-ttu-id="a076f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a076f-106">Parameters</span></span>  
 `exception`  
 <span data-ttu-id="a076f-107">現在のコンテキストのランタイムに設定する JavaScript 例外。</span><span class="sxs-lookup"><span data-stu-id="a076f-107">The JavaScript exception to set for the runtime of the current context.</span></span>  
  
## <span data-ttu-id="a076f-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="a076f-108">Return Value</span></span>  
 `JsNoError` <span data-ttu-id="a076f-109">エンジンが例外状態に設定されている場合、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="a076f-109">if the engine was set into an exception state, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="a076f-110">注釈</span><span class="sxs-lookup"><span data-stu-id="a076f-110">Remarks</span></span>  
 <span data-ttu-id="a076f-111">現在のコンテキストのランタイムが既に例外状態の場合、この API は返します `JsErrorInExceptionState` 。</span><span class="sxs-lookup"><span data-stu-id="a076f-111">If the runtime of the current context is already in an exception state, this API will return `JsErrorInExceptionState`.</span></span>  
  
 <span data-ttu-id="a076f-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="a076f-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="a076f-113">要件</span><span class="sxs-lookup"><span data-stu-id="a076f-113">Requirements</span></span>  
 <span data-ttu-id="a076f-114">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="a076f-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="a076f-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a076f-115">See Also</span></span>  
 [<span data-ttu-id="a076f-116">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="a076f-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
