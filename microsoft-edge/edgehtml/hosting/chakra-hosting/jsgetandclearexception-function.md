---
description: 現在のコンテキストのランタイムを例外状態にした例外を返し、そのランタイムの例外状態をリセットします。
title: JsGetAndClearException 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetAndClearException
helpviewer_keywords:
- JsGetAndClearException function
ms.assetid: 6aec8a88-41ee-47f6-b5f4-32f3cae6bb7b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cb296ea351d0466a856d5ac020550ebacc254ac9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234652"
---
# <span data-ttu-id="7142f-103">JsGetAndClearException 関数</span><span class="sxs-lookup"><span data-stu-id="7142f-103">JsGetAndClearException Function</span></span>

<span data-ttu-id="7142f-104">現在のコンテキストのランタイムを例外状態にした例外を返し、そのランタイムの例外状態をリセットします。</span><span class="sxs-lookup"><span data-stu-id="7142f-104">Returns the exception that caused the runtime of the current context to be in the exception state and resets the exception state for that runtime.</span></span>  
  
## <span data-ttu-id="7142f-105">構文</span><span class="sxs-lookup"><span data-stu-id="7142f-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetAndClearException(  
   _Out_ JsValueRef *exception  
);  
```  
  
#### <span data-ttu-id="7142f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7142f-106">Parameters</span></span>  
 `exception`  
 <span data-ttu-id="7142f-107">現在のコンテキストのランタイムの例外。</span><span class="sxs-lookup"><span data-stu-id="7142f-107">The exception for the runtime of the current context.</span></span>  
  
## <span data-ttu-id="7142f-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="7142f-108">Return Value</span></span>  
 <span data-ttu-id="7142f-109">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="7142f-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="7142f-110">注釈</span><span class="sxs-lookup"><span data-stu-id="7142f-110">Remarks</span></span>  
 <span data-ttu-id="7142f-111">現在のコンテキストのランタイムが例外状態ではない場合、この API は返します `JsErrorInvalidArgument` 。</span><span class="sxs-lookup"><span data-stu-id="7142f-111">If the runtime of the current context is not in an exception state, this API will return `JsErrorInvalidArgument`.</span></span> <span data-ttu-id="7142f-112">ランタイムが無効になっている場合、スクリプトが終了したことを示す例外が返されますが、例外はクリアされません (ランタイムが使用して再び有効になっている場合、例外はクリアされます `JsEnableRuntimeExecution` )。</span><span class="sxs-lookup"><span data-stu-id="7142f-112">If the runtime is disabled, this will return an exception indicating that the script was terminated, but it will not clear the exception (the exception will be cleared if the runtime is re-enabled using `JsEnableRuntimeExecution`).</span></span>  
  
 <span data-ttu-id="7142f-113">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="7142f-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="7142f-114">要件</span><span class="sxs-lookup"><span data-stu-id="7142f-114">Requirements</span></span>  
 <span data-ttu-id="7142f-115">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="7142f-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="7142f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="7142f-116">See Also</span></span>  
 [<span data-ttu-id="7142f-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="7142f-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
