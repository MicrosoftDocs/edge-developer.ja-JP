---
description: DOMDebugger ドメインの参照。 DOM デバッグでは、特定の DOM 操作およびイベントに対してブレークポイントを設定することができます。 通常のブレークポイントが設定されている場合と同様に、JavaScript の実行はこの操作によって停止されます。
title: DOMDebugger ドメイン-DevTools プロトコルバージョン0.2
author: pelavall
ms.author: pelavall
ms.date: 8/17/2018
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: 437a88ff93bda36d85a8f5632c1a02aa205d049b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569600"
---
# <span data-ttu-id="e948f-105">DOMDebugger</span><span class="sxs-lookup"><span data-stu-id="e948f-105">DOMDebugger</span></span>
<span data-ttu-id="e948f-106">DOM デバッグでは、特定の DOM 操作およびイベントに対してブレークポイントを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="e948f-106">DOM debugging allows setting breakpoints on particular DOM operations and events.</span></span> <span data-ttu-id="e948f-107">通常のブレークポイントが設定されている場合と同様に、JavaScript の実行はこの操作によって停止されます。</span><span class="sxs-lookup"><span data-stu-id="e948f-107">JavaScript execution will stop on these operations as if there was a regular breakpoint set.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="e948f-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="e948f-108">Methods</span></span>**](#methods) | <span data-ttu-id="e948f-109">[setInstrumentationBreakpoint](#setinstrumentationbreakpoint)、 [removeInstrumentationBreakpoint](#removeinstrumentationbreakpoint)</span><span class="sxs-lookup"><span data-stu-id="e948f-109">[setInstrumentationBreakpoint](#setinstrumentationbreakpoint), [removeInstrumentationBreakpoint](#removeinstrumentationbreakpoint)</span></span> |
## <span data-ttu-id="e948f-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="e948f-110">Methods</span></span>

### <span data-ttu-id="e948f-111">setInstrumentationBreakpoint</span><span class="sxs-lookup"><span data-stu-id="e948f-111">setInstrumentationBreakpoint</span></span>
<span><b><span data-ttu-id="e948f-112">的.</span><span class="sxs-lookup"><span data-stu-id="e948f-112">Experimental.</span></span> </b></span><span data-ttu-id="e948f-113">特定のネイティブイベントにブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="e948f-113">Sets a breakpoint on a particular native event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e948f-114">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e948f-114">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e948f-115">eventName</span><span class="sxs-lookup"><span data-stu-id="e948f-115">eventName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e948f-116">停止するインストルメンテーション名。</span><span class="sxs-lookup"><span data-stu-id="e948f-116">Instrumentation name to stop on.</span></span> <span data-ttu-id="e948f-117">有効な値: ' scriptFirstStatement '。</span><span class="sxs-lookup"><span data-stu-id="e948f-117">Valid values: 'scriptFirstStatement'.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="e948f-118">removeInstrumentationBreakpoint</span><span class="sxs-lookup"><span data-stu-id="e948f-118">removeInstrumentationBreakpoint</span></span>
<span><b><span data-ttu-id="e948f-119">的.</span><span class="sxs-lookup"><span data-stu-id="e948f-119">Experimental.</span></span> </b></span><span data-ttu-id="e948f-120">特定のネイティブイベントのブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="e948f-120">Removes a breakpoint on a particular native event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e948f-121">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e948f-121">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e948f-122">eventName</span><span class="sxs-lookup"><span data-stu-id="e948f-122">eventName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e948f-123">停止するインストルメンテーション名。</span><span class="sxs-lookup"><span data-stu-id="e948f-123">Instrumentation name to stop on.</span></span> <span data-ttu-id="e948f-124">有効な値: ' scriptFirstStatement '。</span><span class="sxs-lookup"><span data-stu-id="e948f-124">Valid values: 'scriptFirstStatement'.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---
