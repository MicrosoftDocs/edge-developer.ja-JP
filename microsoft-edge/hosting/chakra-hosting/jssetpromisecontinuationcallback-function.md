---
description: 後で実行するためにタスクをキューに入れる必要があるときに、コンテキストによって呼び出される promise 継続コールバック関数を設定します。
title: JsSetPromiseContinuationCallback 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 6ef0faf4-1500-4bd9-aeca-c208492af8ea
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9438bf05d879b0c2014c0a4d49d374d26eff3fb4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570370"
---
# <span data-ttu-id="bfef6-103">JsSetPromiseContinuationCallback 関数</span><span class="sxs-lookup"><span data-stu-id="bfef6-103">JsSetPromiseContinuationCallback Function</span></span>
<span data-ttu-id="bfef6-104">後で実行するためにタスクをキューに入れる必要があるときに、コンテキストによって呼び出される promise 継続コールバック関数を設定します。</span><span class="sxs-lookup"><span data-stu-id="bfef6-104">Sets a promise continuation callback function that is called by the context when a task needs to be queued for future execution.</span></span>  
  
## <span data-ttu-id="bfef6-105">構文</span><span class="sxs-lookup"><span data-stu-id="bfef6-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetPromiseContinuationCallback(  
   _In_ JsPromiseContinuationCallback promiseContinuationCallback,  
   _In_opt_ void *callbackState  
);  
```  
  
#### <span data-ttu-id="bfef6-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bfef6-106">Parameters</span></span>  
 `promiseContinuationCallback`  
 <span data-ttu-id="bfef6-107">設定されているコールバック関数。</span><span class="sxs-lookup"><span data-stu-id="bfef6-107">The callback function being set.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="bfef6-108">コールバックに戻される、ユーザーによって指定された状態。</span><span class="sxs-lookup"><span data-stu-id="bfef6-108">User provided state that will be passed back to the callback.</span></span>  
  
## <span data-ttu-id="bfef6-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="bfef6-109">Return Value</span></span>  
 <span data-ttu-id="bfef6-110">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="bfef6-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="bfef6-111">注釈</span><span class="sxs-lookup"><span data-stu-id="bfef6-111">Remarks</span></span>  
 <span data-ttu-id="bfef6-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="bfef6-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="bfef6-113">この API は、EdgeHTML モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="bfef6-113">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="bfef6-114">要件</span><span class="sxs-lookup"><span data-stu-id="bfef6-114">Requirements</span></span>  
 <span data-ttu-id="bfef6-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="bfef6-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="bfef6-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="bfef6-116">See Also</span></span>  
 [<span data-ttu-id="bfef6-117">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="bfef6-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)