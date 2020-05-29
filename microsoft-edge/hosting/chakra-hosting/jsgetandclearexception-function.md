---
description: 現在のコンテキストのランタイムが例外の状態であり、そのランタイムの例外の状態をリセットした場合に発生する例外を返します。
title: JsGetAndClearException 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetAndClearException
helpviewer_keywords:
- JsGetAndClearException function
ms.assetid: 6aec8a88-41ee-47f6-b5f4-32f3cae6bb7b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: eb70b4b66b4bb270d9f26487708720efddc2effa
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570465"
---
# <span data-ttu-id="42dc5-103">JsGetAndClearException 関数</span><span class="sxs-lookup"><span data-stu-id="42dc5-103">JsGetAndClearException Function</span></span>
<span data-ttu-id="42dc5-104">現在のコンテキストのランタイムが例外の状態であり、そのランタイムの例外の状態をリセットした場合に発生する例外を返します。</span><span class="sxs-lookup"><span data-stu-id="42dc5-104">Returns the exception that caused the runtime of the current context to be in the exception state and resets the exception state for that runtime.</span></span>  
  
## <span data-ttu-id="42dc5-105">構文</span><span class="sxs-lookup"><span data-stu-id="42dc5-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetAndClearException(  
   _Out_ JsValueRef *exception  
);  
```  
  
#### <span data-ttu-id="42dc5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="42dc5-106">Parameters</span></span>  
 `exception`  
 <span data-ttu-id="42dc5-107">現在のコンテキストのランタイムの例外。</span><span class="sxs-lookup"><span data-stu-id="42dc5-107">The exception for the runtime of the current context.</span></span>  
  
## <span data-ttu-id="42dc5-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="42dc5-108">Return Value</span></span>  
 <span data-ttu-id="42dc5-109">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="42dc5-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="42dc5-110">注釈</span><span class="sxs-lookup"><span data-stu-id="42dc5-110">Remarks</span></span>  
 <span data-ttu-id="42dc5-111">現在のコンテキストのランタイムが例外状態ではない場合は、この API から戻り `JsErrorInvalidArgument` ます。</span><span class="sxs-lookup"><span data-stu-id="42dc5-111">If the runtime of the current context is not in an exception state, this API will return `JsErrorInvalidArgument`.</span></span> <span data-ttu-id="42dc5-112">ランタイムが無効になっている場合、スクリプトが終了されたことを示す例外が返されますが、例外は消去されません (ランタイムが再有効化されている場合、例外は消去され `JsEnableRuntimeExecution` ます)。</span><span class="sxs-lookup"><span data-stu-id="42dc5-112">If the runtime is disabled, this will return an exception indicating that the script was terminated, but it will not clear the exception (the exception will be cleared if the runtime is re-enabled using `JsEnableRuntimeExecution`).</span></span>  
  
 <span data-ttu-id="42dc5-113">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="42dc5-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="42dc5-114">要件</span><span class="sxs-lookup"><span data-stu-id="42dc5-114">Requirements</span></span>  
 <span data-ttu-id="42dc5-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="42dc5-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="42dc5-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="42dc5-116">See Also</span></span>  
 [<span data-ttu-id="42dc5-117">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="42dc5-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)