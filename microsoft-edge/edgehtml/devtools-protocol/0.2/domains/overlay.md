---
description: オーバーレイ ドメインのリファレンス。 オーバーレイ ドメインは視覚的な視覚効果とノード選択操作を公開します。
title: オーバーレイ ドメイン - DevTools プロトコル バージョン 0.2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: dcf5feff9983aa2e9e61ac0569938988812165f8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234410"
---
# <span data-ttu-id="f8012-104">オーバーレイ</span><span class="sxs-lookup"><span data-stu-id="f8012-104">Overlay</span></span>

<span data-ttu-id="f8012-105">オーバーレイ ドメインは視覚的な視覚効果とノード選択操作を公開します</span><span class="sxs-lookup"><span data-stu-id="f8012-105">Overlay domain exposes visual adornments and node selection interaction</span></span>

| | |
|-|-|
| [**<span data-ttu-id="f8012-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="f8012-106">Methods</span></span>**](#methods) | <span data-ttu-id="f8012-107">[有効](#enable)、[無効](#disable)[、setInspectMode](#setinspectmode)</span><span class="sxs-lookup"><span data-stu-id="f8012-107">[enable](#enable), [disable](#disable), [setInspectMode](#setinspectmode)</span></span> |
| [**<span data-ttu-id="f8012-108">イベント</span><span class="sxs-lookup"><span data-stu-id="f8012-108">Events</span></span>**](#events) | <span data-ttu-id="f8012-109">[inspectNodeRequested](#inspectnoderequested)、 [nodeHighlightRequested](#nodehighlightrequested)</span><span class="sxs-lookup"><span data-stu-id="f8012-109">[inspectNodeRequested](#inspectnoderequested), [nodeHighlightRequested](#nodehighlightrequested)</span></span> |
| [**<span data-ttu-id="f8012-110">依存関係</span><span class="sxs-lookup"><span data-stu-id="f8012-110">Dependencies</span></span>**](#dependencies) | [<span data-ttu-id="f8012-111">DOM</span><span class="sxs-lookup"><span data-stu-id="f8012-111">DOM</span></span>](dom.md) |
## <span data-ttu-id="f8012-112">メソッド</span><span class="sxs-lookup"><span data-stu-id="f8012-112">Methods</span></span>

### <span data-ttu-id="f8012-113">[有効]</span><span class="sxs-lookup"><span data-stu-id="f8012-113">enable</span></span>
<span data-ttu-id="f8012-114">レポートとイベント <code>nodeHighlightRequested</code> を有効 <code>inspectElementRequested</code> にする</span><span class="sxs-lookup"><span data-stu-id="f8012-114">Enables reporting of <code>nodeHighlightRequested</code> and <code>inspectElementRequested</code> events</span></span>

</p>

---

### <span data-ttu-id="f8012-115">[無効]</span><span class="sxs-lookup"><span data-stu-id="f8012-115">disable</span></span>
<span data-ttu-id="f8012-116">オーバーレイ ドメイン イベントのレポートを無効にします</span><span class="sxs-lookup"><span data-stu-id="f8012-116">Disables reporting of Overlay domain events</span></span>

</p>

---

### <span data-ttu-id="f8012-117">setInspectMode</span><span class="sxs-lookup"><span data-stu-id="f8012-117">setInspectMode</span></span>
<span data-ttu-id="f8012-118">クライアントの要素選択モードを設定します。</span><span class="sxs-lookup"><span data-stu-id="f8012-118">Sets the element selection mode for the client</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f8012-119">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f8012-119">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f8012-120">モード</span><span class="sxs-lookup"><span data-stu-id="f8012-120">mode</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="f8012-121">検査モード。</span><span class="sxs-lookup"><span data-stu-id="f8012-121">The inspection mode.</span></span>  <span data-ttu-id="f8012-122">有効な値は、'searchForNode' および 'none' です。</span><span class="sxs-lookup"><span data-stu-id="f8012-122">Valid values are 'searchForNode' and 'none'.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="f8012-123">highlightConfig</span><span class="sxs-lookup"><span data-stu-id="f8012-123">highlightConfig</span></span> <br/> <i><span data-ttu-id="f8012-124">オプション</span><span class="sxs-lookup"><span data-stu-id="f8012-124">optional</span></span></i></td>
            <td><a href="dom.md#highlightconfig"><code class="flyout">DOM.HighlightConfig</code></a></td>
            <td><span data-ttu-id="f8012-125">検査中に使用する強調表示の構成</span><span class="sxs-lookup"><span data-stu-id="f8012-125">The highlight configuration to use while inspecting</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="f8012-126">イベント</span><span class="sxs-lookup"><span data-stu-id="f8012-126">Events</span></span>

### <span data-ttu-id="f8012-127">inspectNodeRequested</span><span class="sxs-lookup"><span data-stu-id="f8012-127">inspectNodeRequested</span></span>
<span data-ttu-id="f8012-128">ユーザーが特定のノードを検査するメッセージをクライアントに通知します。</span><span class="sxs-lookup"><span data-stu-id="f8012-128">Notifies the client that the user has asked to inspect a particular node</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f8012-129">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f8012-129">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f8012-130">backendNodeId</span><span class="sxs-lookup"><span data-stu-id="f8012-130">backendNodeId</span></span></td>
            <td><a href="dom.md#backendnodeid"><code class="flyout">DOM.BackendNodeId</code></a></td>
            <td><span data-ttu-id="f8012-131">要求されたノードのバックエンド ノード ID</span><span class="sxs-lookup"><span data-stu-id="f8012-131">The backend node ID of node requested</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="f8012-132">nodeHighlightRequested</span><span class="sxs-lookup"><span data-stu-id="f8012-132">nodeHighlightRequested</span></span>
<span data-ttu-id="f8012-133">ユーザーがノードの上にマウス ポインターを移動し、ノードを検査する可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="f8012-133">Indicates that the user has hovered over the node and may inspect the node</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f8012-134">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f8012-134">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f8012-135">nodeId</span><span class="sxs-lookup"><span data-stu-id="f8012-135">nodeId</span></span></td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td><span data-ttu-id="f8012-136">考慮するノードのノード ID</span><span class="sxs-lookup"><span data-stu-id="f8012-136">The node ID of the node being considered</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="f8012-137">依存関係</span><span class="sxs-lookup"><span data-stu-id="f8012-137">Dependencies</span></span>

[<span data-ttu-id="f8012-138">DOM</span><span class="sxs-lookup"><span data-stu-id="f8012-138">DOM</span></span>](dom.md)
