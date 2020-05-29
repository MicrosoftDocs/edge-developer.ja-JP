---
description: 現在のコンテキストでプロファイリングを停止します。
title: JsStopProfiling 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsStopProfiling
helpviewer_keywords:
- JsStopProfiling function
ms.assetid: 3639c04f-a0f9-418b-be39-92f64b4e7ef8
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9d021c7c9849d20283a39d6ecffc89c5b2ea0db0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570269"
---
# <span data-ttu-id="396cb-103">JsStopProfiling 関数</span><span class="sxs-lookup"><span data-stu-id="396cb-103">JsStopProfiling Function</span></span>
<span data-ttu-id="396cb-104">現在のコンテキストでプロファイリングを停止します。</span><span class="sxs-lookup"><span data-stu-id="396cb-104">Stops profiling in the current context.</span></span>  
  
## <span data-ttu-id="396cb-105">構文</span><span class="sxs-lookup"><span data-stu-id="396cb-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsStopProfiling(  
   _In_ HRESULT reason  
);  
```  
  
#### <span data-ttu-id="396cb-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="396cb-106">Parameters</span></span>  
 `reason`  
 <span data-ttu-id="396cb-107">プロファイリングを停止してプロファイラーのコールバックに渡す理由。</span><span class="sxs-lookup"><span data-stu-id="396cb-107">The reason for stopping profiling to pass to the profiler callback.</span></span>  
  
## <span data-ttu-id="396cb-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="396cb-108">Return Value</span></span>  
 <span data-ttu-id="396cb-109">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="396cb-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="396cb-110">注釈</span><span class="sxs-lookup"><span data-stu-id="396cb-110">Remarks</span></span>  
 <span data-ttu-id="396cb-111">プロファイリングが開始されていない場合、エラーは返されません。</span><span class="sxs-lookup"><span data-stu-id="396cb-111">Will not return an error if profiling has not started.</span></span>  
  
 <span data-ttu-id="396cb-112">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="396cb-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="396cb-113">この API はデスクトップアプリでサポートされますが、ストアアプリではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="396cb-113">This API is supported in desktop apps, but is not supported in Store apps.</span></span>  
  
## <span data-ttu-id="396cb-114">要件</span><span class="sxs-lookup"><span data-stu-id="396cb-114">Requirements</span></span>  
 <span data-ttu-id="396cb-115">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="396cb-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="396cb-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="396cb-116">See Also</span></span>  
 [<span data-ttu-id="396cb-117">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="396cb-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)