---
description: 現在のコンテキストでプロファイリングを開始します。
title: JsStartProfiling 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsStartProfiling
helpviewer_keywords:
- JsStartProfiling function
ms.assetid: 638da395-42dd-4fc5-b581-819e647e887d
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 891c39305e08d214a8f06b680c7022683a9d6fe4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10570270"
---
# <span data-ttu-id="65321-103">JsStartProfiling 関数</span><span class="sxs-lookup"><span data-stu-id="65321-103">JsStartProfiling Function</span></span>
<span data-ttu-id="65321-104">現在のコンテキストでプロファイリングを開始します。</span><span class="sxs-lookup"><span data-stu-id="65321-104">Starts profiling in the current context.</span></span>  
  
## <span data-ttu-id="65321-105">構文</span><span class="sxs-lookup"><span data-stu-id="65321-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsStartProfiling(  
   _In_ IActiveScriptProfilerCallback *callback,  
   _In_ PROFILER_EVENT_MASK eventMask,  
   _In_ unsigned long context  
);  
```  
  
#### <span data-ttu-id="65321-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="65321-106">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="65321-107">使用するプロファイリングのコールバック。</span><span class="sxs-lookup"><span data-stu-id="65321-107">The profiling callback to use.</span></span>  
  
 `eventMask`  
 <span data-ttu-id="65321-108">コールバックするプロファイリングイベント。</span><span class="sxs-lookup"><span data-stu-id="65321-108">The profiling events to callback with.</span></span>  
  
 `context`  
 <span data-ttu-id="65321-109">プロファイリングのコールバックに渡すコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="65321-109">A context to pass to the profiling callback.</span></span>  
  
## <span data-ttu-id="65321-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="65321-110">Return Value</span></span>  
 <span data-ttu-id="65321-111">`JsNoError`操作が正常に完了した場合は、エラーコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="65321-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="65321-112">注釈</span><span class="sxs-lookup"><span data-stu-id="65321-112">Remarks</span></span>  
 <span data-ttu-id="65321-113">アクティブなスクリプトコンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="65321-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="65321-114">この API はデスクトップアプリでサポートされますが、ストアアプリではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="65321-114">This API is supported in desktop apps, but is not supported in Store apps.</span></span>  
  
## <span data-ttu-id="65321-115">要件</span><span class="sxs-lookup"><span data-stu-id="65321-115">Requirements</span></span>  
 <span data-ttu-id="65321-116">**ヘッダー:** jsrt</span><span class="sxs-lookup"><span data-stu-id="65321-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="65321-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="65321-117">See Also</span></span>  
 [<span data-ttu-id="65321-118">リファレンス (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="65321-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)