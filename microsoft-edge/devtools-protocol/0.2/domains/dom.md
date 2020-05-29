---
description: DOM ドメインの参照。 このドメインは DOM の読み取り/書き込み操作を公開します。 各 DOM ノードは、が含まれているミラーオブジェクトで表され `id` ます。 これを使って、 `id` ノードの追加情報を取得したり、JavaScript オブジェクトラッパーなどに解決したりすることができます。クライアントが認識しているノードでのみ DOM イベントを受信することが重要です。 バックエンドは、クライアントに送信されたノードを追跡し、同じノードを2回送信することはありません。 クライアントに送信されたノードに関する情報は、クライアント側で収集する必要があります。<p>`iframe`Owner 要素は、子ノードとして対応するドキュメント要素を返します。</p>
title: DOM ドメイン-DevTools プロトコルバージョン0.2
author: pelavall
ms.author: pelavall
ms.date: 8/17/2018
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 9ebe5ff709ac2981cb2359b7279c5d4e5d375426
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569606"
---
# <span data-ttu-id="81fbb-109">DOM</span><span class="sxs-lookup"><span data-stu-id="81fbb-109">DOM</span></span>
<span data-ttu-id="81fbb-110">このドメインは DOM の読み取り/書き込み操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="81fbb-110">This domain exposes DOM read/write operations.</span></span> <span data-ttu-id="81fbb-111">各 DOM ノードは、が含まれているミラーオブジェクトで表され `id` ます。</span><span class="sxs-lookup"><span data-stu-id="81fbb-111">Each DOM Node is represented with its mirror object that has an `id`.</span></span> <span data-ttu-id="81fbb-112">これを使って、 `id` ノードの追加情報を取得したり、JavaScript オブジェクトラッパーなどに解決したりすることができます。クライアントが認識しているノードでのみ DOM イベントを受信することが重要です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-112">This `id` can be used to get additional information on the Node, resolve it into the JavaScript object wrapper, etc. It is important that client receives DOM events only for the nodes that are known to the client.</span></span> <span data-ttu-id="81fbb-113">バックエンドは、クライアントに送信されたノードを追跡し、同じノードを2回送信することはありません。</span><span class="sxs-lookup"><span data-stu-id="81fbb-113">Backend keeps track of the nodes that were sent to the client and never sends the same node twice.</span></span> <span data-ttu-id="81fbb-114">クライアントに送信されたノードに関する情報は、クライアント側で収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81fbb-114">It is client's responsibility to collect information about the nodes that were sent to the client.</span></span><p><span data-ttu-id="81fbb-115">`iframe`Owner 要素は、子ノードとして対応するドキュメント要素を返します。</span><span class="sxs-lookup"><span data-stu-id="81fbb-115">Note that `iframe` owner elements will return corresponding document elements as their child nodes.</span></span></p>

| | |
|-|-|
| [**<span data-ttu-id="81fbb-116">メソッド</span><span class="sxs-lookup"><span data-stu-id="81fbb-116">Methods</span></span>**](#methods) | <span data-ttu-id="81fbb-117">[enable](#enable)、 [disable](#disable)、 [getdocument](#getdocument)、 [highlightNode](#highlightnode)、 [hidehighlight 表示](#hidehighlight)、 [requestchildnodes](#requestchildnodes)、 [getdocument](#getattributes) [、](#getouterhtml)getdocument、 [pushNodesByBackendIdsToFrontend](#pushnodesbybackendidstofrontend)、 [queryselector](#queryselector)、 [querySelectorAll](#queryselectorall)、 [requestnode](#requestnode)、 [resolveNode](#resolvenode)、 [setInspectedNode](#setinspectednode)</span><span class="sxs-lookup"><span data-stu-id="81fbb-117">[enable](#enable), [disable](#disable), [getDocument](#getdocument), [highlightNode](#highlightnode), [hideHighlight](#hidehighlight), [requestChildNodes](#requestchildnodes), [getAttributes](#getattributes), [getOuterHTML](#getouterhtml), [pushNodesByBackendIdsToFrontend](#pushnodesbybackendidstofrontend), [querySelector](#queryselector), [querySelectorAll](#queryselectorall), [requestNode](#requestnode), [resolveNode](#resolvenode), [setInspectedNode](#setinspectednode)</span></span> |
| [**<span data-ttu-id="81fbb-118">イベント</span><span class="sxs-lookup"><span data-stu-id="81fbb-118">Events</span></span>**](#events) | <span data-ttu-id="81fbb-119">[Setchildnodes](#setchildnodes)、 [attributeModified](#attributemodified)、 [attributeRemoved](#attributeremoved)、 [characterDataModified](#characterdatamodified)、 [childnodeinserted](#childnodeinserted)、 [childNodeRemoved](#childnoderemoved)、 [documentupdated](#documentupdated)</span><span class="sxs-lookup"><span data-stu-id="81fbb-119">[setChildNodes](#setchildnodes), [attributeModified](#attributemodified), [attributeRemoved](#attributeremoved), [characterDataModified](#characterdatamodified), [childNodeInserted](#childnodeinserted), [childNodeRemoved](#childnoderemoved), [documentUpdated](#documentupdated)</span></span> |
| [**<span data-ttu-id="81fbb-120">型</span><span class="sxs-lookup"><span data-stu-id="81fbb-120">Types</span></span>**](#types) | <span data-ttu-id="81fbb-121">[RGBA](#rgba)、 [HighlightConfig](#highlightconfig)、 [NodeId](#nodeid)、 [Node](#node)、 [backendnodeid](#backendnodeid)、[擬似型](#pseudotype)</span><span class="sxs-lookup"><span data-stu-id="81fbb-121">[RGBA](#rgba), [HighlightConfig](#highlightconfig), [NodeId](#nodeid), [Node](#node), [BackendNodeId](#backendnodeid), [PseudoType](#pseudotype)</span></span> |
| [**<span data-ttu-id="81fbb-122">依存関係</span><span class="sxs-lookup"><span data-stu-id="81fbb-122">Dependencies</span></span>**](#dependencies) | [<span data-ttu-id="81fbb-123">言語</span><span class="sxs-lookup"><span data-stu-id="81fbb-123">Runtime</span></span>](runtime.md) |
## <span data-ttu-id="81fbb-124">メソッド</span><span class="sxs-lookup"><span data-stu-id="81fbb-124">Methods</span></span>

### <span data-ttu-id="81fbb-125">[有効]</span><span class="sxs-lookup"><span data-stu-id="81fbb-125">enable</span></span>
<span data-ttu-id="81fbb-126">指定したページについて DOM agent を有効にします。</span><span class="sxs-lookup"><span data-stu-id="81fbb-126">Enables DOM agent for the given page.</span></span>

</p>

---

### <span data-ttu-id="81fbb-127">[無効]</span><span class="sxs-lookup"><span data-stu-id="81fbb-127">disable</span></span>
<span data-ttu-id="81fbb-128">指定されたページの DOM エージェントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="81fbb-128">Disables DOM agent for the given page.</span></span> <span data-ttu-id="81fbb-129">DOM を無効にすると、以前の有効な nodeIds が無効になります。</span><span class="sxs-lookup"><span data-stu-id="81fbb-129">Disabling the DOM will invalidate any previously valid nodeIds.</span></span>

</p>

---

### <span data-ttu-id="81fbb-130">getDocument</span><span class="sxs-lookup"><span data-stu-id="81fbb-130">getDocument</span></span>
<span data-ttu-id="81fbb-131">ルート DOM ノード (および必要に応じてサブツリー) を呼び出し元に返します。</span><span class="sxs-lookup"><span data-stu-id="81fbb-131">Returns the root DOM node (and optionally the subtree) to the caller.</span></span> <span data-ttu-id="81fbb-132">通話 `getDocument` によって、以前に有効になったすべての nodeIds が無効になります</span><span class="sxs-lookup"><span data-stu-id="81fbb-132">Calling `getDocument` will invalidate any previously valid nodeIds</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-133">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81fbb-133">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-134">奥行</span><span class="sxs-lookup"><span data-stu-id="81fbb-134">depth</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="81fbb-135">子が取得される最大の深度。既定値は2です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-135">The maximum depth at which children should be retrieved, defaults to 2.</span></span> <span data-ttu-id="81fbb-136">サブツリー全体に-1 を使用します。</span><span class="sxs-lookup"><span data-stu-id="81fbb-136">Use -1 for entire subtree.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-137">貫通</span><span class="sxs-lookup"><span data-stu-id="81fbb-137">pierce</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="81fbb-138">サブツリーを返すときに iframe を走査するかどうか (既定は false)。</span><span class="sxs-lookup"><span data-stu-id="81fbb-138">Whether or not iframes should be traversed when returning the subtree (default is false).</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-139">返し</span><span class="sxs-lookup"><span data-stu-id="81fbb-139">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-140">根本的</span><span class="sxs-lookup"><span data-stu-id="81fbb-140">root</span></span></td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td><span data-ttu-id="81fbb-141">結果ノード。</span><span class="sxs-lookup"><span data-stu-id="81fbb-141">Resulting Node.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="81fbb-142">highlightNode</span><span class="sxs-lookup"><span data-stu-id="81fbb-142">highlightNode</span></span>
<span data-ttu-id="81fbb-143">指定した id またはオブジェクトラッパーの Higlights DOM ノード。</span><span class="sxs-lookup"><span data-stu-id="81fbb-143">Higlights DOM node with given id or object wrapper.</span></span> <span data-ttu-id="81fbb-144">nodeId、backendNodeId、または objectId を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81fbb-144">nodeId, backendNodeId, or objectId must be specified.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-145">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81fbb-145">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-146">nodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-146">nodeId</span></span> <br/> <i><span data-ttu-id="81fbb-147">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-147">optional</span></span></i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="81fbb-148">強調表示するノードの識別子。</span><span class="sxs-lookup"><span data-stu-id="81fbb-148">Identifier of the node to highlight.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-149">backendNodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-149">backendNodeId</span></span> <br/> <i><span data-ttu-id="81fbb-150">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-150">optional</span></span></i></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId</code></a></td>
            <td><span data-ttu-id="81fbb-151">強調表示するバックエンドノードの id です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-151">Identifier of the backend node to highlight.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-152">objectId</span><span class="sxs-lookup"><span data-stu-id="81fbb-152">objectId</span></span> <br/> <i><span data-ttu-id="81fbb-153">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-153">optional</span></span></i></td>
            <td><a href="runtime.md#remoteobjectid"><code class="flyout">Runtime.RemoteObjectId</code></a></td>
            <td><span data-ttu-id="81fbb-154">強調表示されるノードの JavaScript オブジェクト id。</span><span class="sxs-lookup"><span data-stu-id="81fbb-154">JavaScript object id of the node to be highlighted.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-155">higlightConfig</span><span class="sxs-lookup"><span data-stu-id="81fbb-155">higlightConfig</span></span></td>
            <td><a href="#highlightconfig"><code class="flyout">HighlightConfig</code></a></td>
            <td><span data-ttu-id="81fbb-156">強調表示の外観の記述子。</span><span class="sxs-lookup"><span data-stu-id="81fbb-156">Descriptor of the highlight appearance.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-157">返し</span><span class="sxs-lookup"><span data-stu-id="81fbb-157">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-158">根本的</span><span class="sxs-lookup"><span data-stu-id="81fbb-158">root</span></span></td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td><span data-ttu-id="81fbb-159">結果ノード。</span><span class="sxs-lookup"><span data-stu-id="81fbb-159">Resulting Node.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="81fbb-160">hideHighlight 表示</span><span class="sxs-lookup"><span data-stu-id="81fbb-160">hideHighlight</span></span>
<span data-ttu-id="81fbb-161">現在の DOM ノードの強調表示を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="81fbb-161">Hides any current DOM node highlight.</span></span>

</p>

---

### <span data-ttu-id="81fbb-162">requestChildNodes</span><span class="sxs-lookup"><span data-stu-id="81fbb-162">requestChildNodes</span></span>
<span data-ttu-id="81fbb-163">指定した id を持つノードの子が、イベント形式で ghe 呼び出し元に返されるように要求 `setChildNodes` します。</span><span class="sxs-lookup"><span data-stu-id="81fbb-163">Requests that children of the node with given id are returned to ghe caller in the form of `setChildNodes` events.</span></span> `setChildNodes` <span data-ttu-id="81fbb-164">これは、要求されたノードから指定された深さまで、前に子が返されていないノードごとに発生します。</span><span class="sxs-lookup"><span data-stu-id="81fbb-164">will be fired for each node that has not previously returned it's children, starting from the requested node down to the specified depth.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-165">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81fbb-165">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-166">nodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-166">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="81fbb-167">子を取得するノードの Id です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-167">Id of the node to get children from.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-168">奥行</span><span class="sxs-lookup"><span data-stu-id="81fbb-168">depth</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="81fbb-169">子が取得される最大の深度。既定値は1です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-169">The maximum depth at which children should be retrieved, defaults to 1.</span></span> <span data-ttu-id="81fbb-170">サブツリー全体に-1 を使用します。</span><span class="sxs-lookup"><span data-stu-id="81fbb-170">Use -1 for entire subtree.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-171">貫通</span><span class="sxs-lookup"><span data-stu-id="81fbb-171">pierce</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="81fbb-172">サブツリーを返すときに iframe を走査するかどうか (既定は false)。</span><span class="sxs-lookup"><span data-stu-id="81fbb-172">Whether or not iframes should be traversed when returning the subtree (default is false).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="81fbb-173">getAttributes</span><span class="sxs-lookup"><span data-stu-id="81fbb-173">getAttributes</span></span>
<span data-ttu-id="81fbb-174">指定されたノードの属性を返します。</span><span class="sxs-lookup"><span data-stu-id="81fbb-174">Returns attributes for the specified node.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-175">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81fbb-175">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-176">nodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-176">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="81fbb-177">Attibutes を取得するノードの Id です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-177">Id of the node to retrieve attibutes for.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-178">返し</span><span class="sxs-lookup"><span data-stu-id="81fbb-178">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-179">属性</span><span class="sxs-lookup"><span data-stu-id="81fbb-179">attributes</span></span></td>
            <td><code class="flyout">string[]</code></td>
            <td><span data-ttu-id="81fbb-180">ノード属性名と値のインターリーブ配列。</span><span class="sxs-lookup"><span data-stu-id="81fbb-180">An interleaved array of node attribute names and values.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="81fbb-181">getOuterHTML</span><span class="sxs-lookup"><span data-stu-id="81fbb-181">getOuterHTML</span></span>
<span data-ttu-id="81fbb-182">ノードの HTML マークアップを返します。</span><span class="sxs-lookup"><span data-stu-id="81fbb-182">Returns node's HTML markup.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-183">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81fbb-183">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-184">nodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-184">nodeId</span></span> <br/> <i><span data-ttu-id="81fbb-185">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-185">optional</span></span></i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="81fbb-186">ノードの識別子です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-186">Identifier of the node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-187">backendNodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-187">backendNodeId</span></span> <br/> <i><span data-ttu-id="81fbb-188">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-188">optional</span></span></i></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId</code></a></td>
            <td><span data-ttu-id="81fbb-189">バックエンドノードの識別子。</span><span class="sxs-lookup"><span data-stu-id="81fbb-189">Identifier of the backend node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-190">objectId</span><span class="sxs-lookup"><span data-stu-id="81fbb-190">objectId</span></span> <br/> <i><span data-ttu-id="81fbb-191">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-191">optional</span></span></i></td>
            <td><a href="runtime.md#remoteobjectid"><code class="flyout">Runtime.RemoteObjectId</code></a></td>
            <td><span data-ttu-id="81fbb-192">ノードラッパーの JavaScript オブジェクト id。</span><span class="sxs-lookup"><span data-stu-id="81fbb-192">JavaScript object id of the node wrapper.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-193">返し</span><span class="sxs-lookup"><span data-stu-id="81fbb-193">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-194">outerHTML</span><span class="sxs-lookup"><span data-stu-id="81fbb-194">outerHTML</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="81fbb-195">外部の HTML マークアップ。</span><span class="sxs-lookup"><span data-stu-id="81fbb-195">Outer HTML markup.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="81fbb-196">pushNodesByBackendIdsToFrontend</span><span class="sxs-lookup"><span data-stu-id="81fbb-196">pushNodesByBackendIdsToFrontend</span></span>
<span data-ttu-id="81fbb-197">ノード Id を検索し、指定したバックエンドノード Id の親をすべて解決します</span><span class="sxs-lookup"><span data-stu-id="81fbb-197">Looks up Node Ids and resolves all parents for the specified Backend Node Ids</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-198">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81fbb-198">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-199">backendNodeIds</span><span class="sxs-lookup"><span data-stu-id="81fbb-199">backendNodeIds</span></span></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId[]</code></a></td>
            <td><span data-ttu-id="81fbb-200">解決するノードのバックエンドノード Id</span><span class="sxs-lookup"><span data-stu-id="81fbb-200">Backend Node IDs of the nodes to resolve</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-201">返し</span><span class="sxs-lookup"><span data-stu-id="81fbb-201">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-202">nodeIds</span><span class="sxs-lookup"><span data-stu-id="81fbb-202">nodeIds</span></span></td>
            <td><a href="#node"><code class="flyout">Node[]</code></a></td>
            <td><span data-ttu-id="81fbb-203">解決されたノードのノード Id</span><span class="sxs-lookup"><span data-stu-id="81fbb-203">Node Ids of the resolved nodes</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="81fbb-204">querySelector</span><span class="sxs-lookup"><span data-stu-id="81fbb-204">querySelector</span></span>
<span data-ttu-id="81fbb-205">`querySelector`指定したノードで実行します。</span><span class="sxs-lookup"><span data-stu-id="81fbb-205">Executes `querySelector` on a given node.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-206">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81fbb-206">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-207">nodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-207">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="81fbb-208">照会するノードの Id です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-208">Id of the node to query upon.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-209">スイッチ</span><span class="sxs-lookup"><span data-stu-id="81fbb-209">selector</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="81fbb-210">セレクター文字列。</span><span class="sxs-lookup"><span data-stu-id="81fbb-210">The selector string.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-211">返し</span><span class="sxs-lookup"><span data-stu-id="81fbb-211">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-212">nodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-212">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="81fbb-213">クエリセレクターの結果。</span><span class="sxs-lookup"><span data-stu-id="81fbb-213">Query selector result.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="81fbb-214">querySelectorAll</span><span class="sxs-lookup"><span data-stu-id="81fbb-214">querySelectorAll</span></span>
<span data-ttu-id="81fbb-215">`querySelectorAll`指定したノードで実行します。</span><span class="sxs-lookup"><span data-stu-id="81fbb-215">Executes `querySelectorAll` on a given node.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-216">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81fbb-216">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-217">nodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-217">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="81fbb-218">照会するノードの Id です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-218">Id of the node to query upon.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-219">スイッチ</span><span class="sxs-lookup"><span data-stu-id="81fbb-219">selector</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="81fbb-220">セレクター文字列。</span><span class="sxs-lookup"><span data-stu-id="81fbb-220">The selector string.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-221">返し</span><span class="sxs-lookup"><span data-stu-id="81fbb-221">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-222">nodeIds</span><span class="sxs-lookup"><span data-stu-id="81fbb-222">nodeIds</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId[]</code></a></td>
            <td><span data-ttu-id="81fbb-223">クエリセレクターの結果。</span><span class="sxs-lookup"><span data-stu-id="81fbb-223">Query selector results.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="81fbb-224">requestNode</span><span class="sxs-lookup"><span data-stu-id="81fbb-224">requestNode</span></span>
<span data-ttu-id="81fbb-225">指定したリモートオブジェクト Id を持つノードが発信者に送信されるように要求します。</span><span class="sxs-lookup"><span data-stu-id="81fbb-225">Requests that the node with given remote object Id is sent to caller.</span></span> <span data-ttu-id="81fbb-226">ノードからルートへのパスを形成するすべてのノードは、一連の通知としてクライアントにも送信され `setChildNodes` ます。</span><span class="sxs-lookup"><span data-stu-id="81fbb-226">All nodes that form the path from the node to the root are also sent to the client as a series of `setChildNodes` notifications.</span></span> <span data-ttu-id="81fbb-227">要求されたノードを含むドキュメントがクライアントによって要求されていない場合は、0を返します。</span><span class="sxs-lookup"><span data-stu-id="81fbb-227">returns 0 if the document containing the requested node has not previously been requested by the client.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-228">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81fbb-228">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-229">objectId</span><span class="sxs-lookup"><span data-stu-id="81fbb-229">objectId</span></span></td>
            <td><a href="runtime.md#remoteobjectid"><code class="flyout">Runtime.RemoteObjectId</code></a></td>
            <td><span data-ttu-id="81fbb-230">ノードに変換する JavaScript オブジェクト Id。</span><span class="sxs-lookup"><span data-stu-id="81fbb-230">JavaScript object Id to convert into node.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-231">返し</span><span class="sxs-lookup"><span data-stu-id="81fbb-231">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-232">nodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-232">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="81fbb-233">指定されたオブジェクトのノード Id。</span><span class="sxs-lookup"><span data-stu-id="81fbb-233">Node Id for given object.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="81fbb-234">resolveNode</span><span class="sxs-lookup"><span data-stu-id="81fbb-234">resolveNode</span></span>
<span data-ttu-id="81fbb-235">指定された NodeId または BackendNodeId の JavaScript ノードオブジェクトを解決します。</span><span class="sxs-lookup"><span data-stu-id="81fbb-235">Resolves the JavaScript node object for a given NodeId or BackendNodeId.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-236">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81fbb-236">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-237">nodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-237">nodeId</span></span> <br/> <i><span data-ttu-id="81fbb-238">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-238">optional</span></span></i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="81fbb-239">解決するノードの Id です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-239">Id of the node to resolve.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-240">backendNodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-240">backendNodeId</span></span> <br/> <i><span data-ttu-id="81fbb-241">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-241">optional</span></span></i></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId</code></a></td>
            <td><span data-ttu-id="81fbb-242">解決するノードのバックエンドノード Id。</span><span class="sxs-lookup"><span data-stu-id="81fbb-242">Backend Node Id of the node to resolve.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-243">objectGroup</span><span class="sxs-lookup"><span data-stu-id="81fbb-243">objectGroup</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="81fbb-244">複数のオブジェクトを解放するために使用できるシンボリックグループ名。</span><span class="sxs-lookup"><span data-stu-id="81fbb-244">Symbolic group name that can be used to release multiple objects.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-245">返し</span><span class="sxs-lookup"><span data-stu-id="81fbb-245">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-246">object</span><span class="sxs-lookup"><span data-stu-id="81fbb-246">object</span></span></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><span data-ttu-id="81fbb-247">指定したノードの JavaScript オブジェクトラッパー。</span><span class="sxs-lookup"><span data-stu-id="81fbb-247">JavaScript object wrapper for given node.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="81fbb-248">setInspectedNode</span><span class="sxs-lookup"><span data-stu-id="81fbb-248">setInspectedNode</span></span>
<span><b><span data-ttu-id="81fbb-249">的.</span><span class="sxs-lookup"><span data-stu-id="81fbb-249">Experimental.</span></span> </b></span><span data-ttu-id="81fbb-250">$0-$ 4 経由で、指定した id の以前の検査済みノードを本体で参照できるようにします。</span><span class="sxs-lookup"><span data-stu-id="81fbb-250">Enables console to refer to the previous inspected node with given id via $0-$4.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-251">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81fbb-251">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-252">nodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-252">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="81fbb-253">DOM ノード id にアクセスするには、コマンドライン API で $0-$ 4 を使います。</span><span class="sxs-lookup"><span data-stu-id="81fbb-253">DOM node id to be accessible by means of $0-$4 in command line API.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="81fbb-254">イベント</span><span class="sxs-lookup"><span data-stu-id="81fbb-254">Events</span></span>

### <span data-ttu-id="81fbb-255">setChildNodes</span><span class="sxs-lookup"><span data-stu-id="81fbb-255">setChildNodes</span></span>
<span data-ttu-id="81fbb-256">バックエンドが、DOM 構造が見つからないクライアントを提供するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="81fbb-256">Fired when the backend wishes to provide client with missing DOM structure.</span></span> <span data-ttu-id="81fbb-257">これは、ほとんどの呼び出しで nodeIds を要求している場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="81fbb-257">This happens upon most calls requesting nodeIds</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-258">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81fbb-258">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-259">parentId</span><span class="sxs-lookup"><span data-stu-id="81fbb-259">parentId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="81fbb-260">子がある poplate の親ノード。</span><span class="sxs-lookup"><span data-stu-id="81fbb-260">Parent node to poplate with children.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-261">ノード</span><span class="sxs-lookup"><span data-stu-id="81fbb-261">nodes</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId[]</code></a></td>
            <td><span data-ttu-id="81fbb-262">子ノードの配列。</span><span class="sxs-lookup"><span data-stu-id="81fbb-262">Child nodes array.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="81fbb-263">attributeModified</span><span class="sxs-lookup"><span data-stu-id="81fbb-263">attributeModified</span></span>
<span data-ttu-id="81fbb-264">`Element`属性が変更されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="81fbb-264">Fired when `Element`'s attribute is modified.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-265">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81fbb-265">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-266">nodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-266">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="81fbb-267">変更されたノードの Id です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-267">Id of the node that has changed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-268">name</span><span class="sxs-lookup"><span data-stu-id="81fbb-268">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="81fbb-269">属性名。</span><span class="sxs-lookup"><span data-stu-id="81fbb-269">Attribute name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-270">value</span><span class="sxs-lookup"><span data-stu-id="81fbb-270">value</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="81fbb-271">属性値。</span><span class="sxs-lookup"><span data-stu-id="81fbb-271">Attribute value.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="81fbb-272">attributeRemoved</span><span class="sxs-lookup"><span data-stu-id="81fbb-272">attributeRemoved</span></span>
<span data-ttu-id="81fbb-273">属性が削除されたときに発生 `Element` します。</span><span class="sxs-lookup"><span data-stu-id="81fbb-273">Fired when `Element`'s attribute is removed.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-274">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81fbb-274">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-275">nodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-275">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="81fbb-276">変更されたノードの Id です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-276">Id of the node that has changed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-277">name</span><span class="sxs-lookup"><span data-stu-id="81fbb-277">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="81fbb-278">属性名。</span><span class="sxs-lookup"><span data-stu-id="81fbb-278">Attribute name.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="81fbb-279">characterDataModified</span><span class="sxs-lookup"><span data-stu-id="81fbb-279">characterDataModified</span></span>
<span data-ttu-id="81fbb-280">ミラー `DOMCharacterDataModified` イベント。</span><span class="sxs-lookup"><span data-stu-id="81fbb-280">Mirrors `DOMCharacterDataModified` event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-281">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81fbb-281">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-282">nodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-282">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="81fbb-283">変更されたノードの Id です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-283">Id of the node that has changed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-284">charcterData</span><span class="sxs-lookup"><span data-stu-id="81fbb-284">charcterData</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="81fbb-285">新しいテキスト値。</span><span class="sxs-lookup"><span data-stu-id="81fbb-285">New text value.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="81fbb-286">childNodeInserted</span><span class="sxs-lookup"><span data-stu-id="81fbb-286">childNodeInserted</span></span>
<span data-ttu-id="81fbb-287">ミラー `DOMNodeInserted` イベント。</span><span class="sxs-lookup"><span data-stu-id="81fbb-287">Mirrors `DOMNodeInserted` event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-288">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81fbb-288">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-289">parentNodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-289">parentNodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="81fbb-290">変更されたノードの Id です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-290">Id of the node that has changed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-291">前の Nodeid</span><span class="sxs-lookup"><span data-stu-id="81fbb-291">previousNodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="81fbb-292">挿入されたノードの前の兄弟の Id です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-292">Id of the inserted node's previous sibling.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-293">ノード</span><span class="sxs-lookup"><span data-stu-id="81fbb-293">node</span></span></td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td><span data-ttu-id="81fbb-294">挿入されたノードデータ。</span><span class="sxs-lookup"><span data-stu-id="81fbb-294">Inserted node data.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="81fbb-295">childNodeRemoved</span><span class="sxs-lookup"><span data-stu-id="81fbb-295">childNodeRemoved</span></span>
<span data-ttu-id="81fbb-296">ミラー `DOMNodeRemoved` イベント。</span><span class="sxs-lookup"><span data-stu-id="81fbb-296">Mirrors `DOMNodeRemoved` event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-297">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81fbb-297">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-298">parentNodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-298">parentNodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="81fbb-299">変更されたノードの Id です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-299">Id of the node that has changed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-300">nodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-300">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="81fbb-301">削除されたノードの Id です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-301">Id of the node that has been removed.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="81fbb-302">ドキュメントが更新されました</span><span class="sxs-lookup"><span data-stu-id="81fbb-302">documentUpdated</span></span>
<span data-ttu-id="81fbb-303">`Document`が全体的に更新されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="81fbb-303">Fired when `Document` has been totally updated.</span></span> <span data-ttu-id="81fbb-304">ノード id が無効になりました。</span><span class="sxs-lookup"><span data-stu-id="81fbb-304">Node ids are no longer valid.</span></span>

</p>

---

## <span data-ttu-id="81fbb-305">型</span><span class="sxs-lookup"><span data-stu-id="81fbb-305">Types</span></span>

### <a name="rgba"></a> <span data-ttu-id="81fbb-306">RGBA</span><span class="sxs-lookup"><span data-stu-id="81fbb-306">RGBA</span></span> `object`

<span data-ttu-id="81fbb-307">RGBA 色を保持する構造体。</span><span class="sxs-lookup"><span data-stu-id="81fbb-307">A Structure holding an RGBA color.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-308">プロパティ</span><span class="sxs-lookup"><span data-stu-id="81fbb-308">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-309">終点</span><span class="sxs-lookup"><span data-stu-id="81fbb-309">r</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="81fbb-310">赤のコンポーネント。 [0-255] 範囲。</span><span class="sxs-lookup"><span data-stu-id="81fbb-310">The red component, in the [0-255] range.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-311">agdlp</span><span class="sxs-lookup"><span data-stu-id="81fbb-311">g</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="81fbb-312">緑のコンポーネント。 [0-255] 範囲。</span><span class="sxs-lookup"><span data-stu-id="81fbb-312">The green component, in the [0-255] range.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-313">]5d</span><span class="sxs-lookup"><span data-stu-id="81fbb-313">b</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="81fbb-314">青の要素。 [0-255] 範囲。</span><span class="sxs-lookup"><span data-stu-id="81fbb-314">The blue component, in the [0-255] range.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-315">a</span><span class="sxs-lookup"><span data-stu-id="81fbb-315">a</span></span> <br/> <i><span data-ttu-id="81fbb-316">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-316">optional</span></span></i></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="81fbb-317">アルファコンポーネント。 [0-1] 範囲。</span><span class="sxs-lookup"><span data-stu-id="81fbb-317">The alpha component, in the [0-1] range.</span></span> <span data-ttu-id="81fbb-318">既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-318">Default is 1.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="highlightconfig"></a> <span data-ttu-id="81fbb-319">HighlightConfig</span><span class="sxs-lookup"><span data-stu-id="81fbb-319">HighlightConfig</span></span> `object`

<span data-ttu-id="81fbb-320">ページ要素の強調表示用の構成データ。</span><span class="sxs-lookup"><span data-stu-id="81fbb-320">Configuration data for highlighting of page elements.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-321">プロパティ</span><span class="sxs-lookup"><span data-stu-id="81fbb-321">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-322">contentColor</span><span class="sxs-lookup"><span data-stu-id="81fbb-322">contentColor</span></span> <br/> <i><span data-ttu-id="81fbb-323">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-323">optional</span></span></i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td><span data-ttu-id="81fbb-324">[コンテンツ] ボックスが強調表示された塗りつぶしの色。</span><span class="sxs-lookup"><span data-stu-id="81fbb-324">The content box highlight fill color.</span></span> <span data-ttu-id="81fbb-325">Default は透過的です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-325">Default is transparent.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-326">paddingColor</span><span class="sxs-lookup"><span data-stu-id="81fbb-326">paddingColor</span></span> <br/> <i><span data-ttu-id="81fbb-327">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-327">optional</span></span></i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td><span data-ttu-id="81fbb-328">パディングの強調表示の色。</span><span class="sxs-lookup"><span data-stu-id="81fbb-328">The padding highlight fill color.</span></span> <span data-ttu-id="81fbb-329">Default は透過的です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-329">Default is transparent.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-330">borderColor</span><span class="sxs-lookup"><span data-stu-id="81fbb-330">borderColor</span></span> <br/> <i><span data-ttu-id="81fbb-331">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-331">optional</span></span></i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td><span data-ttu-id="81fbb-332">境界線の塗りつぶしの色が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="81fbb-332">The border highlight fill color.</span></span> <span data-ttu-id="81fbb-333">Default は透過的です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-333">Default is transparent.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-334">marginColor</span><span class="sxs-lookup"><span data-stu-id="81fbb-334">marginColor</span></span> <br/> <i><span data-ttu-id="81fbb-335">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-335">optional</span></span></i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td><span data-ttu-id="81fbb-336">余白には塗りつぶしの色が強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="81fbb-336">The margin highlight fill color.</span></span> <span data-ttu-id="81fbb-337">Default は透過的です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-337">Default is transparent.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="nodeid"></a> <span data-ttu-id="81fbb-338">NodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-338">NodeId</span></span> `integer`

<span data-ttu-id="81fbb-339">一意の DOM ノード識別子</span><span class="sxs-lookup"><span data-stu-id="81fbb-339">Unique DOM node identifier</span></span>

</p>

---

### <a name="node"></a> <span data-ttu-id="81fbb-340">ノード</span><span class="sxs-lookup"><span data-stu-id="81fbb-340">Node</span></span> `object`

<span data-ttu-id="81fbb-341">実際の DOM ノードを表す Mirror オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="81fbb-341">Mirror object that represents the actual DOM nodes.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="81fbb-342">プロパティ</span><span class="sxs-lookup"><span data-stu-id="81fbb-342">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="81fbb-343">nodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-343">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="81fbb-344">このノードを参照するために使用されるノード識別子。</span><span class="sxs-lookup"><span data-stu-id="81fbb-344">Node Identifier used to reference this node.</span></span> <span data-ttu-id="81fbb-345">バックエンドは、クライアントが認識している nodeId を持つノードについて、DOM イベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="81fbb-345">Backend will fire DOM events for nodes that have a nodeId that is known to the client</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-346">parentId</span><span class="sxs-lookup"><span data-stu-id="81fbb-346">parentId</span></span> <br/> <i><span data-ttu-id="81fbb-347">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-347">optional</span></span></i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="81fbb-348">親ノードのノード識別子 (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="81fbb-348">Node Identifier of the parent Node, if any.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-349">backendNodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-349">backendNodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="81fbb-350">ノードのバックエンドノード識別子。</span><span class="sxs-lookup"><span data-stu-id="81fbb-350">Backend Node identifier of the node.</span></span> <span data-ttu-id="81fbb-351">BackendNodeIds はクライアントに対して知っている可能性があるが、このノードについては DOM イベントをプッシュしません。</span><span class="sxs-lookup"><span data-stu-id="81fbb-351">BackendNodeIds reference Nodes that can be known to the client, but do not push DOM events about this node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-352">nodeType</span><span class="sxs-lookup"><span data-stu-id="81fbb-352">nodeType</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td>`Node`<span data-ttu-id="81fbb-353">の nodeType。</span><span class="sxs-lookup"><span data-stu-id="81fbb-353">'s nodeType.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-354">nodeName</span><span class="sxs-lookup"><span data-stu-id="81fbb-354">nodeName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td>`Node`<span data-ttu-id="81fbb-355">の nodeName。</span><span class="sxs-lookup"><span data-stu-id="81fbb-355">'s nodeName.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-356">localName</span><span class="sxs-lookup"><span data-stu-id="81fbb-356">localName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td>`Node`<span data-ttu-id="81fbb-357">の localName</span><span class="sxs-lookup"><span data-stu-id="81fbb-357">'s localName</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-358">nodeValue</span><span class="sxs-lookup"><span data-stu-id="81fbb-358">nodeValue</span></span></td>
            <td><code class="flyout">string</code></td>
            <td>`Node`<span data-ttu-id="81fbb-359">の nodeValue</span><span class="sxs-lookup"><span data-stu-id="81fbb-359">'s nodeValue</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-360">childNodeCount</span><span class="sxs-lookup"><span data-stu-id="81fbb-360">childNodeCount</span></span> <br/> <i><span data-ttu-id="81fbb-361">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-361">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="81fbb-362">ノードの子カウント `Container` 。</span><span class="sxs-lookup"><span data-stu-id="81fbb-362">Child count for `Container` nodes.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-363">子供</span><span class="sxs-lookup"><span data-stu-id="81fbb-363">children</span></span> <br/> <i><span data-ttu-id="81fbb-364">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-364">optional</span></span></i></td>
            <td><a href="#node"><code class="flyout">Node[]</code></a></td>
            <td><span data-ttu-id="81fbb-365">子が要求されたときの、このノードの子ノード。</span><span class="sxs-lookup"><span data-stu-id="81fbb-365">Child nodes of this node when requested with children.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-366">属性</span><span class="sxs-lookup"><span data-stu-id="81fbb-366">attributes</span></span> <br/> <i><span data-ttu-id="81fbb-367">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-367">optional</span></span></i></td>
            <td><code class="flyout">string[]</code></td>
            <td><span data-ttu-id="81fbb-368">`Element`フラット配列 ' [name1, value1, name2, value2] の形式のノードの属性</span><span class="sxs-lookup"><span data-stu-id="81fbb-368">Attributes of `Element` nodes in the form of a flat array \`[name1, value1, name2, value2]</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-369">documentURL</span><span class="sxs-lookup"><span data-stu-id="81fbb-369">documentURL</span></span> <br/> <i><span data-ttu-id="81fbb-370">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-370">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="81fbb-371">ノードが指しているドキュメントの URL `Document` 。</span><span class="sxs-lookup"><span data-stu-id="81fbb-371">Document URL that `Document` nodes point to.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-372">baseURL</span><span class="sxs-lookup"><span data-stu-id="81fbb-372">baseURL</span></span> <br/> <i><span data-ttu-id="81fbb-373">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-373">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="81fbb-374">`Document`ノードが url の完了に使用するドキュメント URL。</span><span class="sxs-lookup"><span data-stu-id="81fbb-374">Document URL that `Document` nodes use for URL completion.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-375">publicId</span><span class="sxs-lookup"><span data-stu-id="81fbb-375">publicId</span></span> <br/> <i><span data-ttu-id="81fbb-376">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-376">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`DocumentType` <span data-ttu-id="81fbb-377">ノードの publicId。</span><span class="sxs-lookup"><span data-stu-id="81fbb-377">Node's publicId.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-378">systemId</span><span class="sxs-lookup"><span data-stu-id="81fbb-378">systemId</span></span> <br/> <i><span data-ttu-id="81fbb-379">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-379">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`DocumentType` <span data-ttu-id="81fbb-380">ノードの systemId。</span><span class="sxs-lookup"><span data-stu-id="81fbb-380">Node's systemId.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-381">internalSubset セット</span><span class="sxs-lookup"><span data-stu-id="81fbb-381">internalSubset</span></span> <br/> <i><span data-ttu-id="81fbb-382">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-382">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`DocumentType` <span data-ttu-id="81fbb-383">ノードの internalSubset セット。</span><span class="sxs-lookup"><span data-stu-id="81fbb-383">Node's internalSubset.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-384">xmlVersion</span><span class="sxs-lookup"><span data-stu-id="81fbb-384">xmlVersion</span></span> <br/> <i><span data-ttu-id="81fbb-385">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-385">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`Document` <span data-ttu-id="81fbb-386">XML ドキュメントの場合、ノードの xml バージョン。</span><span class="sxs-lookup"><span data-stu-id="81fbb-386">Node's xml version in the case of XML documents.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-387">name</span><span class="sxs-lookup"><span data-stu-id="81fbb-387">name</span></span> <br/> <i><span data-ttu-id="81fbb-388">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-388">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`Attr` <span data-ttu-id="81fbb-389">ノードの名前。</span><span class="sxs-lookup"><span data-stu-id="81fbb-389">Node's name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-390">value</span><span class="sxs-lookup"><span data-stu-id="81fbb-390">value</span></span> <br/> <i><span data-ttu-id="81fbb-391">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-391">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`Attr` <span data-ttu-id="81fbb-392">ノードの値。</span><span class="sxs-lookup"><span data-stu-id="81fbb-392">Node's value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-393">フレーム Id</span><span class="sxs-lookup"><span data-stu-id="81fbb-393">frameId</span></span> <br/> <i><span data-ttu-id="81fbb-394">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-394">optional</span></span></i></td>
            <td><a href="page.md#frameid"><code class="flyout">Page.FrameId</code></a></td>
            <td><span data-ttu-id="81fbb-395">Frame owner 要素のフレーム ID。</span><span class="sxs-lookup"><span data-stu-id="81fbb-395">Frame ID for frame owner elements.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-396">contentDocument</span><span class="sxs-lookup"><span data-stu-id="81fbb-396">contentDocument</span></span> <br/> <i><span data-ttu-id="81fbb-397">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-397">optional</span></span></i></td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td><span data-ttu-id="81fbb-398">Frame owner 要素のコンテンツドキュメント。</span><span class="sxs-lookup"><span data-stu-id="81fbb-398">Content document for frame owner elements.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="81fbb-399">isSVG</span><span class="sxs-lookup"><span data-stu-id="81fbb-399">isSVG</span></span> <br/> <i><span data-ttu-id="81fbb-400">オプション</span><span class="sxs-lookup"><span data-stu-id="81fbb-400">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="81fbb-401">ノードが SVG の場合は True です。</span><span class="sxs-lookup"><span data-stu-id="81fbb-401">True if the node is SVG.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="backendnodeid"></a> <span data-ttu-id="81fbb-402">BackendNodeId</span><span class="sxs-lookup"><span data-stu-id="81fbb-402">BackendNodeId</span></span> `integer`

<span data-ttu-id="81fbb-403">フロントエンドにプッシュされていない可能性があるノードを参照するために使用される一意の DOM ノード識別子。</span><span class="sxs-lookup"><span data-stu-id="81fbb-403">Unique DOM node identifier used to reference a node that may not have been pushed to the front-end.</span></span>

</p>

---

### <a name="pseudotype"></a> <span data-ttu-id="81fbb-404">擬似の型</span><span class="sxs-lookup"><span data-stu-id="81fbb-404">PseudoType</span></span> `string`

<span data-ttu-id="81fbb-405">疑似要素型。</span><span class="sxs-lookup"><span data-stu-id="81fbb-405">Pseudo element type.</span></span>

##### <span data-ttu-id="81fbb-406">許可される値</span><span class="sxs-lookup"><span data-stu-id="81fbb-406">Allowed Values</span></span>
<span data-ttu-id="81fbb-407">1行目、1文字目、前、後、選択範囲</span><span class="sxs-lookup"><span data-stu-id="81fbb-407">first-line, first-letter, before, after, selection</span></span>
</p>

---

## <span data-ttu-id="81fbb-408">依存関係</span><span class="sxs-lookup"><span data-stu-id="81fbb-408">Dependencies</span></span>

[<span data-ttu-id="81fbb-409">言語</span><span class="sxs-lookup"><span data-stu-id="81fbb-409">Runtime</span></span>](runtime.md)