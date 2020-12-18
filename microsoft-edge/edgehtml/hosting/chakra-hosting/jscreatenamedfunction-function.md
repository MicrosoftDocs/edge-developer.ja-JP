---
description: 名前を持つ新しい JavaScript 関数を作成します。
title: JsCreateNamedFunction 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 72f40d06-ab82-4fed-a632-68af6b4126c2
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: b54add359422a9312a0ded641051fd04585f3d7e
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234666"
---
# <span data-ttu-id="5c964-103">JsCreateNamedFunction 関数</span><span class="sxs-lookup"><span data-stu-id="5c964-103">JsCreateNamedFunction Function</span></span>

<span data-ttu-id="5c964-104">名前を持つ新しい JavaScript 関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="5c964-104">Creates a new JavaScript function with name.</span></span>
  
## <span data-ttu-id="5c964-105">構文</span><span class="sxs-lookup"><span data-stu-id="5c964-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateNamedFunction(  
   _In_ JsValueRef name,  
   _In_ JsNativeFunction nativeFunction,  
   _In_opt_ void *callbackState,  
   _Out_ JsValueRef *function  
);  
```  
  
#### <span data-ttu-id="5c964-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5c964-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="5c964-107">診断および文字列化の目的で使用されるこの関数の名前。</span><span class="sxs-lookup"><span data-stu-id="5c964-107">The name of this function that will be used for diagnostics and stringification purposes.</span></span>  
  
 `nativeFunction`  
 <span data-ttu-id="5c964-108">関数が呼び出されると呼び出すメソッド。</span><span class="sxs-lookup"><span data-stu-id="5c964-108">The method to call when the function is invoked.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="5c964-109">コールバックに戻されるユーザー指定の状態。</span><span class="sxs-lookup"><span data-stu-id="5c964-109">User provided state that will be passed back to the callback.</span></span>  
  
 `function`  
 <span data-ttu-id="5c964-110">新しい関数オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5c964-110">The new function object.</span></span>  
  
## <span data-ttu-id="5c964-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="5c964-111">Return Value</span></span>  
  
## <span data-ttu-id="5c964-112">注釈</span><span class="sxs-lookup"><span data-stu-id="5c964-112">Remarks</span></span>  
 <span data-ttu-id="5c964-113">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="5c964-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="5c964-114">この API は、Microsoft Edge モードでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5c964-114">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="5c964-115">要件</span><span class="sxs-lookup"><span data-stu-id="5c964-115">Requirements</span></span>  
 <span data-ttu-id="5c964-116">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="5c964-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="5c964-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c964-117">See Also</span></span>  
 [<span data-ttu-id="5c964-118">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="5c964-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
