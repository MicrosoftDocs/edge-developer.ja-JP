---
description: 現在のコンテキストでプロファイリングを停止します。
title: JsStopProfiling 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsStopProfiling
helpviewer_keywords:
- JsStopProfiling function
ms.assetid: 3639c04f-a0f9-418b-be39-92f64b4e7ef8
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 02c42afda7e61d71b90a9a1a71aa71cc53584ff8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234719"
---
# <span data-ttu-id="deb43-103">JsStopProfiling 関数</span><span class="sxs-lookup"><span data-stu-id="deb43-103">JsStopProfiling Function</span></span>

<span data-ttu-id="deb43-104">現在のコンテキストでプロファイリングを停止します。</span><span class="sxs-lookup"><span data-stu-id="deb43-104">Stops profiling in the current context.</span></span>  
  
## <span data-ttu-id="deb43-105">構文</span><span class="sxs-lookup"><span data-stu-id="deb43-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsStopProfiling(  
   _In_ HRESULT reason  
);  
```  
  
#### <span data-ttu-id="deb43-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="deb43-106">Parameters</span></span>  
 `reason`  
 <span data-ttu-id="deb43-107">プロファイラー コールバックに渡すプロファイリングを停止する理由。</span><span class="sxs-lookup"><span data-stu-id="deb43-107">The reason for stopping profiling to pass to the profiler callback.</span></span>  
  
## <span data-ttu-id="deb43-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="deb43-108">Return Value</span></span>  
 <span data-ttu-id="deb43-109">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="deb43-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="deb43-110">注釈</span><span class="sxs-lookup"><span data-stu-id="deb43-110">Remarks</span></span>  
 <span data-ttu-id="deb43-111">プロファイリングが開始されていない場合、エラーは返されない。</span><span class="sxs-lookup"><span data-stu-id="deb43-111">Will not return an error if profiling has not started.</span></span>  
  
 <span data-ttu-id="deb43-112">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="deb43-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="deb43-113">この API はデスクトップ アプリでサポートされますが、ストア アプリではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="deb43-113">This API is supported in desktop apps, but is not supported in Store apps.</span></span>  
  
## <span data-ttu-id="deb43-114">要件</span><span class="sxs-lookup"><span data-stu-id="deb43-114">Requirements</span></span>  
 <span data-ttu-id="deb43-115">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="deb43-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="deb43-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="deb43-116">See Also</span></span>  
 [<span data-ttu-id="deb43-117">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="deb43-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
