---
description: オーバーレイドメインの参照。 オーバーレイドメインは、視覚表示修飾要素とノード選択の相互作用を公開します。
title: オーバーレイドメイン-DevTools プロトコルバージョン0.2
author: pelavall
ms.author: pelavall
ms.date: 8/17/2018
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: a7657e2abc99e45894f19f6557f12f78f8ee9c75
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569599"
---
# <span data-ttu-id="f108c-104">オーバーレイ</span><span class="sxs-lookup"><span data-stu-id="f108c-104">Overlay</span></span>
<span data-ttu-id="f108c-105">オーバーレイドメインは、視覚表示修飾要素とノード選択の相互作用を公開します。</span><span class="sxs-lookup"><span data-stu-id="f108c-105">Overlay domain exposes visual adornments and node selection interaction</span></span>

| | |
|-|-|
| [**<span data-ttu-id="f108c-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="f108c-106">Methods</span></span>**](#methods) | <span data-ttu-id="f108c-107">[有効化](#enable)、[無効化](#disable)、 [setInspectMode](#setinspectmode)</span><span class="sxs-lookup"><span data-stu-id="f108c-107">[enable](#enable), [disable](#disable), [setInspectMode](#setinspectmode)</span></span> |
| [**<span data-ttu-id="f108c-108">イベント</span><span class="sxs-lookup"><span data-stu-id="f108c-108">Events</span></span>**](#events) | <span data-ttu-id="f108c-109">[inspectNodeRequested](#inspectnoderequested)、 [nodeHighlightRequested](#nodehighlightrequested)</span><span class="sxs-lookup"><span data-stu-id="f108c-109">[inspectNodeRequested](#inspectnoderequested), [nodeHighlightRequested](#nodehighlightrequested)</span></span> |
| [**<span data-ttu-id="f108c-110">依存関係</span><span class="sxs-lookup"><span data-stu-id="f108c-110">Dependencies</span></span>**](#dependencies) | [<span data-ttu-id="f108c-111">DOM</span><span class="sxs-lookup"><span data-stu-id="f108c-111">DOM</span></span>](dom.md) |
## <span data-ttu-id="f108c-112">メソッド</span><span class="sxs-lookup"><span data-stu-id="f108c-112">Methods</span></span>

### <span data-ttu-id="f108c-113">[有効]</span><span class="sxs-lookup"><span data-stu-id="f108c-113">enable</span></span>
<span data-ttu-id="f108c-114">およびイベントの報告を有効に <code>nodeHighlightRequested</code> します <code>inspectElementRequested</code></span><span class="sxs-lookup"><span data-stu-id="f108c-114">Enables reporting of <code>nodeHighlightRequested</code> and <code>inspectElementRequested</code> events</span></span>

</p>

---

### <span data-ttu-id="f108c-115">[無効]</span><span class="sxs-lookup"><span data-stu-id="f108c-115">disable</span></span>
<span data-ttu-id="f108c-116">オーバーレイドメインイベントのレポートを無効にします</span><span class="sxs-lookup"><span data-stu-id="f108c-116">Disables reporting of Overlay domain events</span></span>

</p>

---

### <span data-ttu-id="f108c-117">setInspectMode</span><span class="sxs-lookup"><span data-stu-id="f108c-117">setInspectMode</span></span>
<span data-ttu-id="f108c-118">クライアントの要素選択モードを設定します</span><span class="sxs-lookup"><span data-stu-id="f108c-118">Sets the element selection mode for the client</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f108c-119">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f108c-119">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f108c-120">モード</span><span class="sxs-lookup"><span data-stu-id="f108c-120">mode</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="f108c-121">検査モード。</span><span class="sxs-lookup"><span data-stu-id="f108c-121">The inspection mode.</span></span>  <span data-ttu-id="f108c-122">有効な値は、"searchForNode" と "none" です。</span><span class="sxs-lookup"><span data-stu-id="f108c-122">Valid values are 'searchForNode' and 'none'.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f108c-123">highlightConfig</span><span class="sxs-lookup"><span data-stu-id="f108c-123">highlightConfig</span></span> <br/> <i><span data-ttu-id="f108c-124">オプション</span><span class="sxs-lookup"><span data-stu-id="f108c-124">optional</span></span></i></td>
            <td><a href="dom.md#highlightconfig"><code class="flyout">DOM.HighlightConfig</code></a></td>
            <td><span data-ttu-id="f108c-125">調査中に使用する強調表示構成</span><span class="sxs-lookup"><span data-stu-id="f108c-125">The highlight configuration to use while inspecting</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="f108c-126">イベント</span><span class="sxs-lookup"><span data-stu-id="f108c-126">Events</span></span>

### <span data-ttu-id="f108c-127">inspectNodeRequested</span><span class="sxs-lookup"><span data-stu-id="f108c-127">inspectNodeRequested</span></span>
<span data-ttu-id="f108c-128">ユーザーが特定のノードを検査するよう求めたことをクライアントに通知します。</span><span class="sxs-lookup"><span data-stu-id="f108c-128">Notifies the client that the user has asked to inspect a particular node</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f108c-129">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f108c-129">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f108c-130">backendNodeId</span><span class="sxs-lookup"><span data-stu-id="f108c-130">backendNodeId</span></span></td>
            <td><a href="dom.md#backendnodeid"><code class="flyout">DOM.BackendNodeId</code></a></td>
            <td><span data-ttu-id="f108c-131">要求されたノードのバックエンドノード ID</span><span class="sxs-lookup"><span data-stu-id="f108c-131">The backend node ID of node requested</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="f108c-132">nodeHighlightRequested</span><span class="sxs-lookup"><span data-stu-id="f108c-132">nodeHighlightRequested</span></span>
<span data-ttu-id="f108c-133">ユーザーがノードの上にマウスポインターを置いて、ノードを検査することを示します。</span><span class="sxs-lookup"><span data-stu-id="f108c-133">Indicates that the user has hovered over the node and may inspect the node</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f108c-134">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f108c-134">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f108c-135">nodeId</span><span class="sxs-lookup"><span data-stu-id="f108c-135">nodeId</span></span></td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td><span data-ttu-id="f108c-136">考慮対象のノードのノード ID</span><span class="sxs-lookup"><span data-stu-id="f108c-136">The node ID of the node being considered</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="f108c-137">依存関係</span><span class="sxs-lookup"><span data-stu-id="f108c-137">Dependencies</span></span>

[<span data-ttu-id="f108c-138">DOM</span><span class="sxs-lookup"><span data-stu-id="f108c-138">DOM</span></span>](dom.md)