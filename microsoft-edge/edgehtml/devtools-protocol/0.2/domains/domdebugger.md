---
description: DOMDebugger ドメインのリファレンス。 DOM デバッグでは、特定の DOM 操作とイベントにブレークポイントを設定できます。 JavaScript の実行は、通常のブレークポイント セットがある場合と同様に、これらの操作で停止します。
title: DOMDebugger ドメイン - DevTools プロトコル バージョン 0.2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d97a9a8f2d0e49166f5f081e8bb0c0d5d3cdd93f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234412"
---
# <span data-ttu-id="ce821-105">DOMDebugger</span><span class="sxs-lookup"><span data-stu-id="ce821-105">DOMDebugger</span></span>

<span data-ttu-id="ce821-106">DOM デバッグでは、特定の DOM 操作とイベントにブレークポイントを設定できます。</span><span class="sxs-lookup"><span data-stu-id="ce821-106">DOM debugging allows setting breakpoints on particular DOM operations and events.</span></span> <span data-ttu-id="ce821-107">JavaScript の実行は、通常のブレークポイント セットがある場合と同様に、これらの操作で停止します。</span><span class="sxs-lookup"><span data-stu-id="ce821-107">JavaScript execution will stop on these operations as if there was a regular breakpoint set.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="ce821-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="ce821-108">Methods</span></span>**](#methods) | <span data-ttu-id="ce821-109">[setInstrumentationBreakpoint](#setinstrumentationbreakpoint), [removeInstrumentationBreakpoint](#removeinstrumentationbreakpoint)</span><span class="sxs-lookup"><span data-stu-id="ce821-109">[setInstrumentationBreakpoint](#setinstrumentationbreakpoint), [removeInstrumentationBreakpoint](#removeinstrumentationbreakpoint)</span></span> |
## <span data-ttu-id="ce821-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="ce821-110">Methods</span></span>

### <span data-ttu-id="ce821-111">setInstrumentationBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ce821-111">setInstrumentationBreakpoint</span></span>
<span><b><span data-ttu-id="ce821-112">試験的。</span><span class="sxs-lookup"><span data-stu-id="ce821-112">Experimental.</span></span> </b></span><span data-ttu-id="ce821-113">特定のネイティブ イベントにブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="ce821-113">Sets a breakpoint on a particular native event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ce821-114">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ce821-114">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ce821-115">eventName</span><span class="sxs-lookup"><span data-stu-id="ce821-115">eventName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="ce821-116">停止するインストルメンテーション名。</span><span class="sxs-lookup"><span data-stu-id="ce821-116">Instrumentation name to stop on.</span></span> <span data-ttu-id="ce821-117">有効な値: 'scriptFirstStatement'。</span><span class="sxs-lookup"><span data-stu-id="ce821-117">Valid values: 'scriptFirstStatement'.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="ce821-118">removeInstrumentationBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ce821-118">removeInstrumentationBreakpoint</span></span>
<span><b><span data-ttu-id="ce821-119">試験的。</span><span class="sxs-lookup"><span data-stu-id="ce821-119">Experimental.</span></span> </b></span><span data-ttu-id="ce821-120">特定のネイティブ イベントのブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="ce821-120">Removes a breakpoint on a particular native event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ce821-121">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ce821-121">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ce821-122">eventName</span><span class="sxs-lookup"><span data-stu-id="ce821-122">eventName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="ce821-123">停止するインストルメンテーション名。</span><span class="sxs-lookup"><span data-stu-id="ce821-123">Instrumentation name to stop on.</span></span> <span data-ttu-id="ce821-124">有効な値: 'scriptFirstStatement'。</span><span class="sxs-lookup"><span data-stu-id="ce821-124">Valid values: 'scriptFirstStatement'.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---
