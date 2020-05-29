---
description: 現在のコンテキストのランタイムが例外状態であるかどうかを判断します。
title: JsHasException 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsHasException
helpviewer_keywords:
- JsHasException function
ms.assetid: ac7da3ce-c746-4154-bbb8-bcb0859a8d5b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 25ddb8f9cc407dd414a6cd2210c315eb4dd7b141
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570431"
---
# <span data-ttu-id="37878-103">JsHasException 関数</span><span class="sxs-lookup"><span data-stu-id="37878-103">JsHasException Function</span></span>
<span data-ttu-id="37878-104">現在のコンテキストのランタイムが例外状態であるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="37878-104">Determines whether the runtime of the current context is in an exception state.</span></span>  
  
## <span data-ttu-id="37878-105">構文</span><span class="sxs-lookup"><span data-stu-id="37878-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsHasException(  
   _Out_ bool *hasException  
);  
```  
  
#### <span data-ttu-id="37878-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="37878-106">Parameters</span></span>  
 `hasException`  
 <span data-ttu-id="37878-107">現在のコンテキストのランタイムが例外状態にあるかどうか。</span><span class="sxs-lookup"><span data-stu-id="37878-107">Whether the runtime of the current context is in the exception state.</span></span>  
  
## <span data-ttu-id="37878-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="37878-108">Return Value</span></span>  
 <span data-ttu-id="37878-109">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="37878-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="37878-110">注釈</span><span class="sxs-lookup"><span data-stu-id="37878-110">Remarks</span></span>  
 <span data-ttu-id="37878-111">ランタイムへの呼び出しによって例外が発生した場合 (スクリプトを実行した場合、または変換エラーなどが原因である場合)、ランタイムは "例外の状態" に配置されます。</span><span class="sxs-lookup"><span data-stu-id="37878-111">If a call into the runtime results in an exception (either as the result of running a script or due to something like a conversion failure), the runtime is placed into an "exception state."</span></span> <span data-ttu-id="37878-112">ランタイムによって作成されたコンテキスト (例外 Api を除く) へのすべての呼び出しは、 `JsErrorInExceptionState` 例外が消去されるまで失敗します。</span><span class="sxs-lookup"><span data-stu-id="37878-112">All calls into any context created by the runtime (except for the exception APIs) will fail with `JsErrorInExceptionState` until the exception is cleared.</span></span>  
  
 <span data-ttu-id="37878-113">コールバックがエンジンに返されたときに、現在のコンテキストのランタイムが例外状態にある場合、エンジンは例外を自動的に再スローします。</span><span class="sxs-lookup"><span data-stu-id="37878-113">If the runtime of the current context is in the exception state when a callback returns into the engine, the engine will automatically rethrow the exception.</span></span>  
  
 <span data-ttu-id="37878-114">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="37878-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="37878-115">要件</span><span class="sxs-lookup"><span data-stu-id="37878-115">Requirements</span></span>  
 <span data-ttu-id="37878-116">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="37878-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="37878-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="37878-117">See Also</span></span>  
 [<span data-ttu-id="37878-118">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="37878-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)