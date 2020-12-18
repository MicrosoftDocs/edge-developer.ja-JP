---
description: 新しい JavaScript 関数を作成します。
title: JsCreateFunction 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateFunction
helpviewer_keywords:
- JsCreateFunction function
ms.assetid: b298a96a-5ef7-4203-a8c8-55f9bfc6d2bb
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f7e67e86e6d8055664bfb1b58e6d5653f6d75d1b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234885"
---
# <span data-ttu-id="ece21-103">JsCreateFunction 関数</span><span class="sxs-lookup"><span data-stu-id="ece21-103">JsCreateFunction Function</span></span>

<span data-ttu-id="ece21-104">新しい JavaScript 関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="ece21-104">Creates a new JavaScript function.</span></span>
  
## <span data-ttu-id="ece21-105">構文</span><span class="sxs-lookup"><span data-stu-id="ece21-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateFunction(  
   _In_ JsNativeFunction nativeFunction,  
   _In_opt_ void *callbackState,  
   _Out_ JsValueRef *function  
);  
```  
  
#### <span data-ttu-id="ece21-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ece21-106">Parameters</span></span>  
 `nativeFunction`  
 <span data-ttu-id="ece21-107">関数が呼び出されると呼び出すメソッド。</span><span class="sxs-lookup"><span data-stu-id="ece21-107">The method to call when the function is invoked.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="ece21-108">コールバックに戻されるユーザー指定の状態。</span><span class="sxs-lookup"><span data-stu-id="ece21-108">User-provided state that will be passed back to the callback.</span></span>  
  
 `function`  
 <span data-ttu-id="ece21-109">新しい関数オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ece21-109">The new function object.</span></span>  
  
## <span data-ttu-id="ece21-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="ece21-110">Return Value</span></span>  
 <span data-ttu-id="ece21-111">呼び出しの結果 (指定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="ece21-111">The result of the call, if any.</span></span>  
  
## <span data-ttu-id="ece21-112">注釈</span><span class="sxs-lookup"><span data-stu-id="ece21-112">Remarks</span></span>  
 <span data-ttu-id="ece21-113">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="ece21-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="ece21-114">要件</span><span class="sxs-lookup"><span data-stu-id="ece21-114">Requirements</span></span>  
 <span data-ttu-id="ece21-115">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="ece21-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ece21-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ece21-116">See Also</span></span>  
 [<span data-ttu-id="ece21-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="ece21-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
