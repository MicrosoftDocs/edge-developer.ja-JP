---
description: 現在のコンテキストのランタイムが例外状態であるかどうかを判別します。
title: JsHasException 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsHasException
helpviewer_keywords:
- JsHasException function
ms.assetid: ac7da3ce-c746-4154-bbb8-bcb0859a8d5b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 4f4abbd6c69a6b2b6414dae2f1de3a2acf21cc32
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234393"
---
# <span data-ttu-id="834c5-103">JsHasException 関数</span><span class="sxs-lookup"><span data-stu-id="834c5-103">JsHasException Function</span></span>

<span data-ttu-id="834c5-104">現在のコンテキストのランタイムが例外状態であるかどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="834c5-104">Determines whether the runtime of the current context is in an exception state.</span></span>  
  
## <span data-ttu-id="834c5-105">構文</span><span class="sxs-lookup"><span data-stu-id="834c5-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsHasException(  
   _Out_ bool *hasException  
);  
```  
  
#### <span data-ttu-id="834c5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="834c5-106">Parameters</span></span>  
 `hasException`  
 <span data-ttu-id="834c5-107">現在のコンテキストのランタイムが例外状態であるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="834c5-107">Whether the runtime of the current context is in the exception state.</span></span>  
  
## <span data-ttu-id="834c5-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="834c5-108">Return Value</span></span>  
 <span data-ttu-id="834c5-109">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="834c5-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="834c5-110">注釈</span><span class="sxs-lookup"><span data-stu-id="834c5-110">Remarks</span></span>  
 <span data-ttu-id="834c5-111">ランタイムの呼び出しで例外が発生した場合 (スクリプトの実行結果、または変換エラーなどの理由により)、ランタイムは "例外状態" になります。</span><span class="sxs-lookup"><span data-stu-id="834c5-111">If a call into the runtime results in an exception (either as the result of running a script or due to something like a conversion failure), the runtime is placed into an "exception state."</span></span> <span data-ttu-id="834c5-112">ランタイムによって作成されたコンテキストへのすべての呼び出し (例外 API を除く) は、例外がクリアされるまで `JsErrorInExceptionState` 失敗します。</span><span class="sxs-lookup"><span data-stu-id="834c5-112">All calls into any context created by the runtime (except for the exception APIs) will fail with `JsErrorInExceptionState` until the exception is cleared.</span></span>  
  
 <span data-ttu-id="834c5-113">コールバックがエンジンに戻る際に、現在のコンテキストのランタイムが例外状態にある場合、エンジンは自動的に例外を再スローします。</span><span class="sxs-lookup"><span data-stu-id="834c5-113">If the runtime of the current context is in the exception state when a callback returns into the engine, the engine will automatically rethrow the exception.</span></span>  
  
 <span data-ttu-id="834c5-114">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="834c5-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="834c5-115">要件</span><span class="sxs-lookup"><span data-stu-id="834c5-115">Requirements</span></span>  
 <span data-ttu-id="834c5-116">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="834c5-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="834c5-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="834c5-117">See Also</span></span>  
 [<span data-ttu-id="834c5-118">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="834c5-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
