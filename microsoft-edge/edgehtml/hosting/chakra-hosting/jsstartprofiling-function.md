---
description: 現在のコンテキストでプロファイリングを開始します。
title: JsStartProfiling 関数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsStartProfiling
helpviewer_keywords:
- JsStartProfiling function
ms.assetid: 638da395-42dd-4fc5-b581-819e647e887d
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 332ff04a987e6e7ae5030983af96dd48249e58e2
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234718"
---
# <span data-ttu-id="4dc38-103">JsStartProfiling 関数</span><span class="sxs-lookup"><span data-stu-id="4dc38-103">JsStartProfiling Function</span></span>

<span data-ttu-id="4dc38-104">現在のコンテキストでプロファイリングを開始します。</span><span class="sxs-lookup"><span data-stu-id="4dc38-104">Starts profiling in the current context.</span></span>  
  
## <span data-ttu-id="4dc38-105">構文</span><span class="sxs-lookup"><span data-stu-id="4dc38-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsStartProfiling(  
   _In_ IActiveScriptProfilerCallback *callback,  
   _In_ PROFILER_EVENT_MASK eventMask,  
   _In_ unsigned long context  
);  
```  
  
#### <span data-ttu-id="4dc38-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4dc38-106">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="4dc38-107">使用するプロファイリング コールバック。</span><span class="sxs-lookup"><span data-stu-id="4dc38-107">The profiling callback to use.</span></span>  
  
 `eventMask`  
 <span data-ttu-id="4dc38-108">コールバックに使用するプロファイリング イベント。</span><span class="sxs-lookup"><span data-stu-id="4dc38-108">The profiling events to callback with.</span></span>  
  
 `context`  
 <span data-ttu-id="4dc38-109">プロファイリング コールバックに渡すコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="4dc38-109">A context to pass to the profiling callback.</span></span>  
  
## <span data-ttu-id="4dc38-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="4dc38-110">Return Value</span></span>  
 <span data-ttu-id="4dc38-111">操作が `JsNoError` 成功した場合はコード、それ以外の場合はエラー コード。</span><span class="sxs-lookup"><span data-stu-id="4dc38-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="4dc38-112">注釈</span><span class="sxs-lookup"><span data-stu-id="4dc38-112">Remarks</span></span>  
 <span data-ttu-id="4dc38-113">アクティブなスクリプト コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="4dc38-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="4dc38-114">この API はデスクトップ アプリでサポートされますが、ストア アプリではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4dc38-114">This API is supported in desktop apps, but is not supported in Store apps.</span></span>  
  
## <span data-ttu-id="4dc38-115">要件</span><span class="sxs-lookup"><span data-stu-id="4dc38-115">Requirements</span></span>  
 <span data-ttu-id="4dc38-116">**ヘッダー:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="4dc38-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="4dc38-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="4dc38-117">See Also</span></span>  
 [<span data-ttu-id="4dc38-118">リファレンス (JavaScript ランタイム)</span><span class="sxs-lookup"><span data-stu-id="4dc38-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
