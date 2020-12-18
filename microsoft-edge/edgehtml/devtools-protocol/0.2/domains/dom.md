---
description: DOM ドメインの参照。 このドメインは、DOM の読み取り/書き込み操作を公開します。 各 DOM ノードは、ミラー オブジェクトで表されます `id` 。 これは `id` 、Node に関する追加情報の取得、JavaScript オブジェクト ラッパーへの解決などに使用できます。クライアントが DOM イベントを受け取るのは、クライアントに既知のノードについてのみ重要です。 バックエンドは、クライアントに送信されたノードを追跡し、同じノードを 2 回送信する必要はありません。 クライアントに送信されたノードに関する情報を収集する必要があります。<p>所有者要素 `iframe` は、対応するドキュメント要素を子ノードとして返します。</p>
title: DOM ドメイン - DevTools プロトコル バージョン 0.2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7d9861a2395f7b24142a41efea9ac599907dec27
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234790"
---
# <span data-ttu-id="84f7c-109">DOM</span><span class="sxs-lookup"><span data-stu-id="84f7c-109">DOM</span></span>

<span data-ttu-id="84f7c-110">このドメインは、DOM の読み取り/書き込み操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="84f7c-110">This domain exposes DOM read/write operations.</span></span> <span data-ttu-id="84f7c-111">各 DOM ノードは、ミラー オブジェクトで表されます `id` 。</span><span class="sxs-lookup"><span data-stu-id="84f7c-111">Each DOM Node is represented with its mirror object that has an `id`.</span></span> <span data-ttu-id="84f7c-112">これは `id` 、Node に関する追加情報の取得、JavaScript オブジェクト ラッパーへの解決などに使用できます。クライアントが DOM イベントを受け取るのは、クライアントに既知のノードについてのみ重要です。</span><span class="sxs-lookup"><span data-stu-id="84f7c-112">This `id` can be used to get additional information on the Node, resolve it into the JavaScript object wrapper, etc. It is important that client receives DOM events only for the nodes that are known to the client.</span></span> <span data-ttu-id="84f7c-113">バックエンドは、クライアントに送信されたノードを追跡し、同じノードを 2 回送信する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="84f7c-113">Backend keeps track of the nodes that were sent to the client and never sends the same node twice.</span></span> <span data-ttu-id="84f7c-114">クライアントに送信されたノードに関する情報を収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84f7c-114">It is client's responsibility to collect information about the nodes that were sent to the client.</span></span><p><span data-ttu-id="84f7c-115">所有者要素 `iframe` は、対応するドキュメント要素を子ノードとして返します。</span><span class="sxs-lookup"><span data-stu-id="84f7c-115">Note that `iframe` owner elements will return corresponding document elements as their child nodes.</span></span></p>

| | |
|-|-|
| [**<span data-ttu-id="84f7c-116">メソッド</span><span class="sxs-lookup"><span data-stu-id="84f7c-116">Methods</span></span>**](#methods) | <span data-ttu-id="84f7c-117">[enable](#enable)、 [disable](#disable)、 [getDocument](#getdocument)、 [highlightNode](#highlightnode)、 [hideHighlight](#hidehighlight)、 [requestChildNodes](#requestchildnodes)、 [getAttributes](#getattributes)、 [getOuterHTML](#getouterhtml)、 [pushNodesByBackendIdsToFrontend](#pushnodesbybackendidstofrontend), querySelector , [querySelectorAll](#queryselectorall), requestNode , [](#queryselector) [resolveNode](#requestnode), [setInspectedNode](#setinspectednode) [](#resolvenode)</span><span class="sxs-lookup"><span data-stu-id="84f7c-117">[enable](#enable), [disable](#disable), [getDocument](#getdocument), [highlightNode](#highlightnode), [hideHighlight](#hidehighlight), [requestChildNodes](#requestchildnodes), [getAttributes](#getattributes), [getOuterHTML](#getouterhtml), [pushNodesByBackendIdsToFrontend](#pushnodesbybackendidstofrontend), [querySelector](#queryselector), [querySelectorAll](#queryselectorall), [requestNode](#requestnode), [resolveNode](#resolvenode), [setInspectedNode](#setinspectednode)</span></span> |
| [**<span data-ttu-id="84f7c-118">イベント</span><span class="sxs-lookup"><span data-stu-id="84f7c-118">Events</span></span>**](#events) | <span data-ttu-id="84f7c-119">[setChildNodes](#setchildnodes), [attributeModified](#attributemodified), [attributeRemoved](#attributeremoved), [characterDataModified](#characterdatamodified), [childNodeInserted](#childnodeinserted), [childNodeRemoved](#childnoderemoved), [documentUpdated](#documentupdated)</span><span class="sxs-lookup"><span data-stu-id="84f7c-119">[setChildNodes](#setchildnodes), [attributeModified](#attributemodified), [attributeRemoved](#attributeremoved), [characterDataModified](#characterdatamodified), [childNodeInserted](#childnodeinserted), [childNodeRemoved](#childnoderemoved), [documentUpdated](#documentupdated)</span></span> |
| [**<span data-ttu-id="84f7c-120">型</span><span class="sxs-lookup"><span data-stu-id="84f7c-120">Types</span></span>**](#types) | <span data-ttu-id="84f7c-121">[](#rgba)RGBA、HighlightConfig、NodeId、Node、BackendNodeId [、PseudoType](#pseudotype) [](#highlightconfig) [](#nodeid) [](#node) [](#backendnodeid)</span><span class="sxs-lookup"><span data-stu-id="84f7c-121">[RGBA](#rgba), [HighlightConfig](#highlightconfig), [NodeId](#nodeid), [Node](#node), [BackendNodeId](#backendnodeid), [PseudoType](#pseudotype)</span></span> |
| [**<span data-ttu-id="84f7c-122">依存関係</span><span class="sxs-lookup"><span data-stu-id="84f7c-122">Dependencies</span></span>**](#dependencies) | [<span data-ttu-id="84f7c-123">ランタイム</span><span class="sxs-lookup"><span data-stu-id="84f7c-123">Runtime</span></span>](runtime.md) |
## <span data-ttu-id="84f7c-124">メソッド</span><span class="sxs-lookup"><span data-stu-id="84f7c-124">Methods</span></span>

### <span data-ttu-id="84f7c-125">[有効]</span><span class="sxs-lookup"><span data-stu-id="84f7c-125">enable</span></span>
<span data-ttu-id="84f7c-126">指定されたページの DOM エージェントを有効にする。</span><span class="sxs-lookup"><span data-stu-id="84f7c-126">Enables DOM agent for the given page.</span></span>

</p>

---

### <span data-ttu-id="84f7c-127">[無効]</span><span class="sxs-lookup"><span data-stu-id="84f7c-127">disable</span></span>
<span data-ttu-id="84f7c-128">指定されたページの DOM エージェントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="84f7c-128">Disables DOM agent for the given page.</span></span> <span data-ttu-id="84f7c-129">DOM を無効にすると、以前に有効だった nodeId が無効になります。</span><span class="sxs-lookup"><span data-stu-id="84f7c-129">Disabling the DOM will invalidate any previously valid nodeIds.</span></span>

</p>

---

### <span data-ttu-id="84f7c-130">getDocument</span><span class="sxs-lookup"><span data-stu-id="84f7c-130">getDocument</span></span>
<span data-ttu-id="84f7c-131">ルート DOM ノード (および必要に応じてサブツリー) を呼び出し元に返します。</span><span class="sxs-lookup"><span data-stu-id="84f7c-131">Returns the root DOM node (and optionally the subtree) to the caller.</span></span> <span data-ttu-id="84f7c-132">呼 `getDocument` び出しにより、以前に有効だった nodeId が無効になります</span><span class="sxs-lookup"><span data-stu-id="84f7c-132">Calling `getDocument` will invalidate any previously valid nodeIds</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-133">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84f7c-133">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-134">depth</span><span class="sxs-lookup"><span data-stu-id="84f7c-134">depth</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="84f7c-135">子を取得する最大深度 (既定値は 2)。</span><span class="sxs-lookup"><span data-stu-id="84f7c-135">The maximum depth at which children should be retrieved, defaults to 2.</span></span> <span data-ttu-id="84f7c-136">サブツリー全体に -1 を使用します。</span><span class="sxs-lookup"><span data-stu-id="84f7c-136">Use -1 for entire subtree.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-137">(1)</span><span class="sxs-lookup"><span data-stu-id="84f7c-137">pierce</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="84f7c-138">サブツリーを返す際に iframe をスキャンするかどうかを指定します (既定値は false)。</span><span class="sxs-lookup"><span data-stu-id="84f7c-138">Whether or not iframes should be traversed when returning the subtree (default is false).</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-139">戻り値</span><span class="sxs-lookup"><span data-stu-id="84f7c-139">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-140">root</span><span class="sxs-lookup"><span data-stu-id="84f7c-140">root</span></span></td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td><span data-ttu-id="84f7c-141">結果ノード。</span><span class="sxs-lookup"><span data-stu-id="84f7c-141">Resulting Node.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="84f7c-142">highlightNode</span><span class="sxs-lookup"><span data-stu-id="84f7c-142">highlightNode</span></span>
<span data-ttu-id="84f7c-143">特定の ID またはオブジェクト ラッパーを持つ DOM ノードを休止します。</span><span class="sxs-lookup"><span data-stu-id="84f7c-143">Higlights DOM node with given id or object wrapper.</span></span> <span data-ttu-id="84f7c-144">nodeId、backendNodeId、または objectId を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84f7c-144">nodeId, backendNodeId, or objectId must be specified.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-145">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84f7c-145">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-146">nodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-146">nodeId</span></span> <br/> <i><span data-ttu-id="84f7c-147">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-147">optional</span></span></i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="84f7c-148">強調表示するノードの識別子。</span><span class="sxs-lookup"><span data-stu-id="84f7c-148">Identifier of the node to highlight.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-149">backendNodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-149">backendNodeId</span></span> <br/> <i><span data-ttu-id="84f7c-150">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-150">optional</span></span></i></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId</code></a></td>
            <td><span data-ttu-id="84f7c-151">強調表示するバックエンド ノードの識別子。</span><span class="sxs-lookup"><span data-stu-id="84f7c-151">Identifier of the backend node to highlight.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-152">objectId</span><span class="sxs-lookup"><span data-stu-id="84f7c-152">objectId</span></span> <br/> <i><span data-ttu-id="84f7c-153">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-153">optional</span></span></i></td>
            <td><a href="runtime.md#remoteobjectid"><code class="flyout">Runtime.RemoteObjectId</code></a></td>
            <td><span data-ttu-id="84f7c-154">強調表示するノードの JavaScript オブジェクト ID。</span><span class="sxs-lookup"><span data-stu-id="84f7c-154">JavaScript object id of the node to be highlighted.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-155">higlightConfig</span><span class="sxs-lookup"><span data-stu-id="84f7c-155">higlightConfig</span></span></td>
            <td><a href="#highlightconfig"><code class="flyout">HighlightConfig</code></a></td>
            <td><span data-ttu-id="84f7c-156">強調表示の外観の記述子。</span><span class="sxs-lookup"><span data-stu-id="84f7c-156">Descriptor of the highlight appearance.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-157">戻り値</span><span class="sxs-lookup"><span data-stu-id="84f7c-157">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-158">root</span><span class="sxs-lookup"><span data-stu-id="84f7c-158">root</span></span></td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td><span data-ttu-id="84f7c-159">結果ノード。</span><span class="sxs-lookup"><span data-stu-id="84f7c-159">Resulting Node.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="84f7c-160">hideHighlight</span><span class="sxs-lookup"><span data-stu-id="84f7c-160">hideHighlight</span></span>
<span data-ttu-id="84f7c-161">現在の DOM ノードの強調表示を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="84f7c-161">Hides any current DOM node highlight.</span></span>

</p>

---

### <span data-ttu-id="84f7c-162">requestChildNodes</span><span class="sxs-lookup"><span data-stu-id="84f7c-162">requestChildNodes</span></span>
<span data-ttu-id="84f7c-163">特定の ID を持つノードの子がイベントの形式で呼び出し元に返される要求 `setChildNodes` 。</span><span class="sxs-lookup"><span data-stu-id="84f7c-163">Requests that children of the node with given id are returned to ghe caller in the form of `setChildNodes` events.</span></span> `setChildNodes` <span data-ttu-id="84f7c-164">は、要求されたノードから指定された深さまで、以前に子を返していないノードごとに発生します。</span><span class="sxs-lookup"><span data-stu-id="84f7c-164">will be fired for each node that has not previously returned it's children, starting from the requested node down to the specified depth.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-165">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84f7c-165">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-166">nodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-166">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="84f7c-167">子を取得するノードの ID。</span><span class="sxs-lookup"><span data-stu-id="84f7c-167">Id of the node to get children from.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-168">depth</span><span class="sxs-lookup"><span data-stu-id="84f7c-168">depth</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="84f7c-169">子を取得する最大深度 (既定値は 1)。</span><span class="sxs-lookup"><span data-stu-id="84f7c-169">The maximum depth at which children should be retrieved, defaults to 1.</span></span> <span data-ttu-id="84f7c-170">サブツリー全体に -1 を使用します。</span><span class="sxs-lookup"><span data-stu-id="84f7c-170">Use -1 for entire subtree.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-171">(1)</span><span class="sxs-lookup"><span data-stu-id="84f7c-171">pierce</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="84f7c-172">サブツリーを返す際に iframe をスキャンするかどうかを指定します (既定値は false)。</span><span class="sxs-lookup"><span data-stu-id="84f7c-172">Whether or not iframes should be traversed when returning the subtree (default is false).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="84f7c-173">getAttributes</span><span class="sxs-lookup"><span data-stu-id="84f7c-173">getAttributes</span></span>
<span data-ttu-id="84f7c-174">指定されたノードの属性を返します。</span><span class="sxs-lookup"><span data-stu-id="84f7c-174">Returns attributes for the specified node.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-175">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84f7c-175">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-176">nodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-176">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="84f7c-177">属性を取得するノードの ID。</span><span class="sxs-lookup"><span data-stu-id="84f7c-177">Id of the node to retrieve attibutes for.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-178">戻り値</span><span class="sxs-lookup"><span data-stu-id="84f7c-178">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-179">attributes</span><span class="sxs-lookup"><span data-stu-id="84f7c-179">attributes</span></span></td>
            <td><code class="flyout">string[]</code></td>
            <td><span data-ttu-id="84f7c-180">ノード属性の名前と値のインターリーブ配列。</span><span class="sxs-lookup"><span data-stu-id="84f7c-180">An interleaved array of node attribute names and values.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="84f7c-181">getOuterHTML</span><span class="sxs-lookup"><span data-stu-id="84f7c-181">getOuterHTML</span></span>
<span data-ttu-id="84f7c-182">ノードの HTML マークアップを返します。</span><span class="sxs-lookup"><span data-stu-id="84f7c-182">Returns node's HTML markup.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-183">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84f7c-183">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-184">nodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-184">nodeId</span></span> <br/> <i><span data-ttu-id="84f7c-185">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-185">optional</span></span></i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="84f7c-186">ノードの識別子。</span><span class="sxs-lookup"><span data-stu-id="84f7c-186">Identifier of the node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-187">backendNodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-187">backendNodeId</span></span> <br/> <i><span data-ttu-id="84f7c-188">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-188">optional</span></span></i></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId</code></a></td>
            <td><span data-ttu-id="84f7c-189">バックエンド ノードの識別子。</span><span class="sxs-lookup"><span data-stu-id="84f7c-189">Identifier of the backend node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-190">objectId</span><span class="sxs-lookup"><span data-stu-id="84f7c-190">objectId</span></span> <br/> <i><span data-ttu-id="84f7c-191">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-191">optional</span></span></i></td>
            <td><a href="runtime.md#remoteobjectid"><code class="flyout">Runtime.RemoteObjectId</code></a></td>
            <td><span data-ttu-id="84f7c-192">ノード ラッパーの JavaScript オブジェクト ID。</span><span class="sxs-lookup"><span data-stu-id="84f7c-192">JavaScript object id of the node wrapper.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-193">戻り値</span><span class="sxs-lookup"><span data-stu-id="84f7c-193">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-194">outerHTML</span><span class="sxs-lookup"><span data-stu-id="84f7c-194">outerHTML</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="84f7c-195">外部 HTML マークアップ。</span><span class="sxs-lookup"><span data-stu-id="84f7c-195">Outer HTML markup.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="84f7c-196">pushNodesByBackendIdsToFrontend</span><span class="sxs-lookup"><span data-stu-id="84f7c-196">pushNodesByBackendIdsToFrontend</span></span>
<span data-ttu-id="84f7c-197">ノード ID を検索し、指定されたバックエンド ノード ID のすべての親を解決します。</span><span class="sxs-lookup"><span data-stu-id="84f7c-197">Looks up Node Ids and resolves all parents for the specified Backend Node Ids</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-198">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84f7c-198">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-199">backendNodeIds</span><span class="sxs-lookup"><span data-stu-id="84f7c-199">backendNodeIds</span></span></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId[]</code></a></td>
            <td><span data-ttu-id="84f7c-200">解決するノードのバックエンド ノードの ID</span><span class="sxs-lookup"><span data-stu-id="84f7c-200">Backend Node IDs of the nodes to resolve</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-201">戻り値</span><span class="sxs-lookup"><span data-stu-id="84f7c-201">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-202">nodeIds</span><span class="sxs-lookup"><span data-stu-id="84f7c-202">nodeIds</span></span></td>
            <td><a href="#node"><code class="flyout">Node[]</code></a></td>
            <td><span data-ttu-id="84f7c-203">解決されたノードのノード ID</span><span class="sxs-lookup"><span data-stu-id="84f7c-203">Node Ids of the resolved nodes</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="84f7c-204">querySelector</span><span class="sxs-lookup"><span data-stu-id="84f7c-204">querySelector</span></span>
<span data-ttu-id="84f7c-205">指定された `querySelector` ノードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="84f7c-205">Executes `querySelector` on a given node.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-206">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84f7c-206">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-207">nodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-207">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="84f7c-208">クエリを実行するノードの ID。</span><span class="sxs-lookup"><span data-stu-id="84f7c-208">Id of the node to query upon.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-209">selector</span><span class="sxs-lookup"><span data-stu-id="84f7c-209">selector</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="84f7c-210">セレクター文字列。</span><span class="sxs-lookup"><span data-stu-id="84f7c-210">The selector string.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-211">戻り値</span><span class="sxs-lookup"><span data-stu-id="84f7c-211">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-212">nodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-212">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="84f7c-213">クエリ セレクターの結果。</span><span class="sxs-lookup"><span data-stu-id="84f7c-213">Query selector result.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="84f7c-214">querySelectorAll</span><span class="sxs-lookup"><span data-stu-id="84f7c-214">querySelectorAll</span></span>
<span data-ttu-id="84f7c-215">指定された `querySelectorAll` ノードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="84f7c-215">Executes `querySelectorAll` on a given node.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-216">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84f7c-216">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-217">nodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-217">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="84f7c-218">クエリを実行するノードの ID。</span><span class="sxs-lookup"><span data-stu-id="84f7c-218">Id of the node to query upon.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-219">selector</span><span class="sxs-lookup"><span data-stu-id="84f7c-219">selector</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="84f7c-220">セレクター文字列。</span><span class="sxs-lookup"><span data-stu-id="84f7c-220">The selector string.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-221">戻り値</span><span class="sxs-lookup"><span data-stu-id="84f7c-221">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-222">nodeIds</span><span class="sxs-lookup"><span data-stu-id="84f7c-222">nodeIds</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId[]</code></a></td>
            <td><span data-ttu-id="84f7c-223">クエリ セレクターの結果。</span><span class="sxs-lookup"><span data-stu-id="84f7c-223">Query selector results.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="84f7c-224">requestNode</span><span class="sxs-lookup"><span data-stu-id="84f7c-224">requestNode</span></span>
<span data-ttu-id="84f7c-225">指定されたリモート オブジェクト ID を持つノードが呼び出し元に送信される要求。</span><span class="sxs-lookup"><span data-stu-id="84f7c-225">Requests that the node with given remote object Id is sent to caller.</span></span> <span data-ttu-id="84f7c-226">ノードからルートへのパスを形成するノードも、一連の通知としてクライアントに送信 `setChildNodes` されます。</span><span class="sxs-lookup"><span data-stu-id="84f7c-226">All nodes that form the path from the node to the root are also sent to the client as a series of `setChildNodes` notifications.</span></span> <span data-ttu-id="84f7c-227">要求されたノードを含むドキュメントがクライアントによって要求されていない場合は、0 を返します。</span><span class="sxs-lookup"><span data-stu-id="84f7c-227">returns 0 if the document containing the requested node has not previously been requested by the client.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-228">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84f7c-228">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-229">objectId</span><span class="sxs-lookup"><span data-stu-id="84f7c-229">objectId</span></span></td>
            <td><a href="runtime.md#remoteobjectid"><code class="flyout">Runtime.RemoteObjectId</code></a></td>
            <td><span data-ttu-id="84f7c-230">ノードに変換する JavaScript オブジェクト ID。</span><span class="sxs-lookup"><span data-stu-id="84f7c-230">JavaScript object Id to convert into node.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-231">戻り値</span><span class="sxs-lookup"><span data-stu-id="84f7c-231">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-232">nodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-232">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="84f7c-233">特定のオブジェクトのノード ID。</span><span class="sxs-lookup"><span data-stu-id="84f7c-233">Node Id for given object.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="84f7c-234">resolveNode</span><span class="sxs-lookup"><span data-stu-id="84f7c-234">resolveNode</span></span>
<span data-ttu-id="84f7c-235">指定された NodeId または BackendNodeId の JavaScript ノード オブジェクトを解決します。</span><span class="sxs-lookup"><span data-stu-id="84f7c-235">Resolves the JavaScript node object for a given NodeId or BackendNodeId.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-236">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84f7c-236">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-237">nodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-237">nodeId</span></span> <br/> <i><span data-ttu-id="84f7c-238">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-238">optional</span></span></i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="84f7c-239">解決するノードの ID。</span><span class="sxs-lookup"><span data-stu-id="84f7c-239">Id of the node to resolve.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-240">backendNodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-240">backendNodeId</span></span> <br/> <i><span data-ttu-id="84f7c-241">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-241">optional</span></span></i></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId</code></a></td>
            <td><span data-ttu-id="84f7c-242">解決するノードのバックエンド ノード ID。</span><span class="sxs-lookup"><span data-stu-id="84f7c-242">Backend Node Id of the node to resolve.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-243">objectGroup</span><span class="sxs-lookup"><span data-stu-id="84f7c-243">objectGroup</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="84f7c-244">複数のオブジェクトを解放するために使用できるシンボリック グループ名。</span><span class="sxs-lookup"><span data-stu-id="84f7c-244">Symbolic group name that can be used to release multiple objects.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-245">戻り値</span><span class="sxs-lookup"><span data-stu-id="84f7c-245">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-246">object</span><span class="sxs-lookup"><span data-stu-id="84f7c-246">object</span></span></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><span data-ttu-id="84f7c-247">特定のノードの JavaScript オブジェクト ラッパー。</span><span class="sxs-lookup"><span data-stu-id="84f7c-247">JavaScript object wrapper for given node.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="84f7c-248">setInspectedNode</span><span class="sxs-lookup"><span data-stu-id="84f7c-248">setInspectedNode</span></span>
<span><b><span data-ttu-id="84f7c-249">試験的。</span><span class="sxs-lookup"><span data-stu-id="84f7c-249">Experimental.</span></span> </b></span><span data-ttu-id="84f7c-250">コンソールで、ID が $0 ~ $4 の前の検査済みノードを参照できます。</span><span class="sxs-lookup"><span data-stu-id="84f7c-250">Enables console to refer to the previous inspected node with given id via $0-$4.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-251">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84f7c-251">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-252">nodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-252">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="84f7c-253">コマンド ライン API で $0 ~$4 を使用してアクセスできる DOM ノード ID。</span><span class="sxs-lookup"><span data-stu-id="84f7c-253">DOM node id to be accessible by means of $0-$4 in command line API.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="84f7c-254">イベント</span><span class="sxs-lookup"><span data-stu-id="84f7c-254">Events</span></span>

### <span data-ttu-id="84f7c-255">setChildNodes</span><span class="sxs-lookup"><span data-stu-id="84f7c-255">setChildNodes</span></span>
<span data-ttu-id="84f7c-256">バックエンドがクライアントに DOM 構造の欠落を提供する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="84f7c-256">Fired when the backend wishes to provide client with missing DOM structure.</span></span> <span data-ttu-id="84f7c-257">これは、nodeIds を要求しているほとんどの呼び出しで発生します。</span><span class="sxs-lookup"><span data-stu-id="84f7c-257">This happens upon most calls requesting nodeIds</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-258">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84f7c-258">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-259">parentId</span><span class="sxs-lookup"><span data-stu-id="84f7c-259">parentId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="84f7c-260">子を含む親ノード。</span><span class="sxs-lookup"><span data-stu-id="84f7c-260">Parent node to poplate with children.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-261">nodes</span><span class="sxs-lookup"><span data-stu-id="84f7c-261">nodes</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId[]</code></a></td>
            <td><span data-ttu-id="84f7c-262">子ノードの配列。</span><span class="sxs-lookup"><span data-stu-id="84f7c-262">Child nodes array.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="84f7c-263">attributeModified</span><span class="sxs-lookup"><span data-stu-id="84f7c-263">attributeModified</span></span>
<span data-ttu-id="84f7c-264">`Element`'s 属性が変更された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="84f7c-264">Fired when `Element`'s attribute is modified.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-265">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84f7c-265">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-266">nodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-266">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="84f7c-267">変更されたノードの ID。</span><span class="sxs-lookup"><span data-stu-id="84f7c-267">Id of the node that has changed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-268">name</span><span class="sxs-lookup"><span data-stu-id="84f7c-268">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="84f7c-269">属性名。</span><span class="sxs-lookup"><span data-stu-id="84f7c-269">Attribute name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-270">value</span><span class="sxs-lookup"><span data-stu-id="84f7c-270">value</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="84f7c-271">属性値。</span><span class="sxs-lookup"><span data-stu-id="84f7c-271">Attribute value.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="84f7c-272">attributeRemoved</span><span class="sxs-lookup"><span data-stu-id="84f7c-272">attributeRemoved</span></span>
<span data-ttu-id="84f7c-273">`Element`'s 属性が削除された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="84f7c-273">Fired when `Element`'s attribute is removed.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-274">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84f7c-274">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-275">nodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-275">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="84f7c-276">変更されたノードの ID。</span><span class="sxs-lookup"><span data-stu-id="84f7c-276">Id of the node that has changed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-277">name</span><span class="sxs-lookup"><span data-stu-id="84f7c-277">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="84f7c-278">属性名。</span><span class="sxs-lookup"><span data-stu-id="84f7c-278">Attribute name.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="84f7c-279">characterDataModified</span><span class="sxs-lookup"><span data-stu-id="84f7c-279">characterDataModified</span></span>
<span data-ttu-id="84f7c-280">Mirrors `DOMCharacterDataModified` イベント。</span><span class="sxs-lookup"><span data-stu-id="84f7c-280">Mirrors `DOMCharacterDataModified` event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-281">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84f7c-281">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-282">nodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-282">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="84f7c-283">変更されたノードの ID。</span><span class="sxs-lookup"><span data-stu-id="84f7c-283">Id of the node that has changed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-284">charcterData</span><span class="sxs-lookup"><span data-stu-id="84f7c-284">charcterData</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="84f7c-285">新しいテキスト値。</span><span class="sxs-lookup"><span data-stu-id="84f7c-285">New text value.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="84f7c-286">childNodeInserted</span><span class="sxs-lookup"><span data-stu-id="84f7c-286">childNodeInserted</span></span>
<span data-ttu-id="84f7c-287">Mirrors `DOMNodeInserted` イベント。</span><span class="sxs-lookup"><span data-stu-id="84f7c-287">Mirrors `DOMNodeInserted` event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-288">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84f7c-288">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-289">parentNodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-289">parentNodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="84f7c-290">変更されたノードの ID。</span><span class="sxs-lookup"><span data-stu-id="84f7c-290">Id of the node that has changed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-291">previousNodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-291">previousNodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="84f7c-292">挿入されたノードの前の兄弟の ID。</span><span class="sxs-lookup"><span data-stu-id="84f7c-292">Id of the inserted node's previous sibling.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-293">node</span><span class="sxs-lookup"><span data-stu-id="84f7c-293">node</span></span></td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td><span data-ttu-id="84f7c-294">挿入されたノード データ。</span><span class="sxs-lookup"><span data-stu-id="84f7c-294">Inserted node data.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="84f7c-295">childNodeRemoved</span><span class="sxs-lookup"><span data-stu-id="84f7c-295">childNodeRemoved</span></span>
<span data-ttu-id="84f7c-296">Mirrors `DOMNodeRemoved` イベント。</span><span class="sxs-lookup"><span data-stu-id="84f7c-296">Mirrors `DOMNodeRemoved` event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-297">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84f7c-297">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-298">parentNodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-298">parentNodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="84f7c-299">変更されたノードの ID。</span><span class="sxs-lookup"><span data-stu-id="84f7c-299">Id of the node that has changed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-300">nodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-300">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="84f7c-301">削除されたノードの ID。</span><span class="sxs-lookup"><span data-stu-id="84f7c-301">Id of the node that has been removed.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="84f7c-302">documentUpdated</span><span class="sxs-lookup"><span data-stu-id="84f7c-302">documentUpdated</span></span>
<span data-ttu-id="84f7c-303">完全に `Document` 更新された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="84f7c-303">Fired when `Document` has been totally updated.</span></span> <span data-ttu-id="84f7c-304">ノード ID が無効です。</span><span class="sxs-lookup"><span data-stu-id="84f7c-304">Node ids are no longer valid.</span></span>

</p>

---

## <span data-ttu-id="84f7c-305">型</span><span class="sxs-lookup"><span data-stu-id="84f7c-305">Types</span></span>

### <a name="rgba"></a> <span data-ttu-id="84f7c-306">RGBA</span><span class="sxs-lookup"><span data-stu-id="84f7c-306">RGBA</span></span> `object`

<span data-ttu-id="84f7c-307">RGBA カラーを保持する構造体。</span><span class="sxs-lookup"><span data-stu-id="84f7c-307">A Structure holding an RGBA color.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-308">プロパティ</span><span class="sxs-lookup"><span data-stu-id="84f7c-308">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-309">r</span><span class="sxs-lookup"><span data-stu-id="84f7c-309">r</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="84f7c-310">[0- 255] の範囲の赤いコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="84f7c-310">The red component, in the [0-255] range.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-311">g</span><span class="sxs-lookup"><span data-stu-id="84f7c-311">g</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="84f7c-312">[0- 255] の範囲の緑のコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="84f7c-312">The green component, in the [0-255] range.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-313">b</span><span class="sxs-lookup"><span data-stu-id="84f7c-313">b</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="84f7c-314">[0~ 255] の範囲の青色のコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="84f7c-314">The blue component, in the [0-255] range.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-315">a</span><span class="sxs-lookup"><span data-stu-id="84f7c-315">a</span></span> <br/> <i><span data-ttu-id="84f7c-316">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-316">optional</span></span></i></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="84f7c-317">[0- 1] の範囲のアルファ成分。</span><span class="sxs-lookup"><span data-stu-id="84f7c-317">The alpha component, in the [0-1] range.</span></span> <span data-ttu-id="84f7c-318">既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="84f7c-318">Default is 1.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="highlightconfig"></a> <span data-ttu-id="84f7c-319">HighlightConfig</span><span class="sxs-lookup"><span data-stu-id="84f7c-319">HighlightConfig</span></span> `object`

<span data-ttu-id="84f7c-320">ページ要素を強調表示する構成データ。</span><span class="sxs-lookup"><span data-stu-id="84f7c-320">Configuration data for highlighting of page elements.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-321">プロパティ</span><span class="sxs-lookup"><span data-stu-id="84f7c-321">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-322">contentColor</span><span class="sxs-lookup"><span data-stu-id="84f7c-322">contentColor</span></span> <br/> <i><span data-ttu-id="84f7c-323">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-323">optional</span></span></i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td><span data-ttu-id="84f7c-324">コンテンツ ボックスの強調表示の塗りつぶしの色。</span><span class="sxs-lookup"><span data-stu-id="84f7c-324">The content box highlight fill color.</span></span> <span data-ttu-id="84f7c-325">既定値は透明です。</span><span class="sxs-lookup"><span data-stu-id="84f7c-325">Default is transparent.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-326">paddingColor</span><span class="sxs-lookup"><span data-stu-id="84f7c-326">paddingColor</span></span> <br/> <i><span data-ttu-id="84f7c-327">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-327">optional</span></span></i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td><span data-ttu-id="84f7c-328">パディングの強調表示の塗りつぶしの色。</span><span class="sxs-lookup"><span data-stu-id="84f7c-328">The padding highlight fill color.</span></span> <span data-ttu-id="84f7c-329">既定値は透明です。</span><span class="sxs-lookup"><span data-stu-id="84f7c-329">Default is transparent.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-330">borderColor</span><span class="sxs-lookup"><span data-stu-id="84f7c-330">borderColor</span></span> <br/> <i><span data-ttu-id="84f7c-331">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-331">optional</span></span></i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td><span data-ttu-id="84f7c-332">枠線の強調表示の塗りつぶしの色を指定します。</span><span class="sxs-lookup"><span data-stu-id="84f7c-332">The border highlight fill color.</span></span> <span data-ttu-id="84f7c-333">既定値は透明です。</span><span class="sxs-lookup"><span data-stu-id="84f7c-333">Default is transparent.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-334">marginColor</span><span class="sxs-lookup"><span data-stu-id="84f7c-334">marginColor</span></span> <br/> <i><span data-ttu-id="84f7c-335">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-335">optional</span></span></i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td><span data-ttu-id="84f7c-336">余白の強調表示の塗りつぶしの色。</span><span class="sxs-lookup"><span data-stu-id="84f7c-336">The margin highlight fill color.</span></span> <span data-ttu-id="84f7c-337">既定値は透明です。</span><span class="sxs-lookup"><span data-stu-id="84f7c-337">Default is transparent.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="nodeid"></a> <span data-ttu-id="84f7c-338">NodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-338">NodeId</span></span> `integer`

<span data-ttu-id="84f7c-339">一意の DOM ノード識別子</span><span class="sxs-lookup"><span data-stu-id="84f7c-339">Unique DOM node identifier</span></span>

</p>

---

### <a name="node"></a> <span data-ttu-id="84f7c-340">ノード</span><span class="sxs-lookup"><span data-stu-id="84f7c-340">Node</span></span> `object`

<span data-ttu-id="84f7c-341">実際の DOM ノードを表す Mirror オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="84f7c-341">Mirror object that represents the actual DOM nodes.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="84f7c-342">プロパティ</span><span class="sxs-lookup"><span data-stu-id="84f7c-342">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="84f7c-343">nodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-343">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="84f7c-344">このノードを参照するために使用されるノード識別子。</span><span class="sxs-lookup"><span data-stu-id="84f7c-344">Node Identifier used to reference this node.</span></span> <span data-ttu-id="84f7c-345">バックエンドは、クライアントに既知の nodeId を持つノードに対して DOM イベントを発生します。</span><span class="sxs-lookup"><span data-stu-id="84f7c-345">Backend will fire DOM events for nodes that have a nodeId that is known to the client</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-346">parentId</span><span class="sxs-lookup"><span data-stu-id="84f7c-346">parentId</span></span> <br/> <i><span data-ttu-id="84f7c-347">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-347">optional</span></span></i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="84f7c-348">親 Node のノード識別子 (ノードがある場合)。</span><span class="sxs-lookup"><span data-stu-id="84f7c-348">Node Identifier of the parent Node, if any.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-349">backendNodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-349">backendNodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="84f7c-350">ノードのバックエンド ノード識別子。</span><span class="sxs-lookup"><span data-stu-id="84f7c-350">Backend Node identifier of the node.</span></span> <span data-ttu-id="84f7c-351">BackendNodeIds は、クライアントに既知のノードを参照しますが、このノードに関する DOM イベントはプッシュされません。</span><span class="sxs-lookup"><span data-stu-id="84f7c-351">BackendNodeIds reference Nodes that can be known to the client, but do not push DOM events about this node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-352">nodeType</span><span class="sxs-lookup"><span data-stu-id="84f7c-352">nodeType</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td>`Node`<span data-ttu-id="84f7c-353">'s nodeType.</span><span class="sxs-lookup"><span data-stu-id="84f7c-353">'s nodeType.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-354">nodeName</span><span class="sxs-lookup"><span data-stu-id="84f7c-354">nodeName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td>`Node`<span data-ttu-id="84f7c-355">'s nodeName.</span><span class="sxs-lookup"><span data-stu-id="84f7c-355">'s nodeName.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-356">localName</span><span class="sxs-lookup"><span data-stu-id="84f7c-356">localName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td>`Node`<span data-ttu-id="84f7c-357">'s localName</span><span class="sxs-lookup"><span data-stu-id="84f7c-357">'s localName</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-358">nodeValue</span><span class="sxs-lookup"><span data-stu-id="84f7c-358">nodeValue</span></span></td>
            <td><code class="flyout">string</code></td>
            <td>`Node`<span data-ttu-id="84f7c-359">'s nodeValue</span><span class="sxs-lookup"><span data-stu-id="84f7c-359">'s nodeValue</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-360">childNodeCount</span><span class="sxs-lookup"><span data-stu-id="84f7c-360">childNodeCount</span></span> <br/> <i><span data-ttu-id="84f7c-361">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-361">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="84f7c-362">ノードの子 `Container` 数。</span><span class="sxs-lookup"><span data-stu-id="84f7c-362">Child count for `Container` nodes.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-363">子供</span><span class="sxs-lookup"><span data-stu-id="84f7c-363">children</span></span> <br/> <i><span data-ttu-id="84f7c-364">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-364">optional</span></span></i></td>
            <td><a href="#node"><code class="flyout">Node[]</code></a></td>
            <td><span data-ttu-id="84f7c-365">子を指定して要求された場合の、このノードの子ノード。</span><span class="sxs-lookup"><span data-stu-id="84f7c-365">Child nodes of this node when requested with children.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-366">attributes</span><span class="sxs-lookup"><span data-stu-id="84f7c-366">attributes</span></span> <br/> <i><span data-ttu-id="84f7c-367">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-367">optional</span></span></i></td>
            <td><code class="flyout">string[]</code></td>
            <td><span data-ttu-id="84f7c-368">フラット配列 `Element` '[name1, value1, name2, value2] の形式のノードの属性</span><span class="sxs-lookup"><span data-stu-id="84f7c-368">Attributes of `Element` nodes in the form of a flat array \`[name1, value1, name2, value2]</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-369">documentURL</span><span class="sxs-lookup"><span data-stu-id="84f7c-369">documentURL</span></span> <br/> <i><span data-ttu-id="84f7c-370">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-370">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="84f7c-371">ノードが指 `Document` すドキュメント URL。</span><span class="sxs-lookup"><span data-stu-id="84f7c-371">Document URL that `Document` nodes point to.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-372">baseURL</span><span class="sxs-lookup"><span data-stu-id="84f7c-372">baseURL</span></span> <br/> <i><span data-ttu-id="84f7c-373">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-373">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="84f7c-374">ノードが URL の `Document` 完了に使用するドキュメント URL。</span><span class="sxs-lookup"><span data-stu-id="84f7c-374">Document URL that `Document` nodes use for URL completion.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-375">publicId</span><span class="sxs-lookup"><span data-stu-id="84f7c-375">publicId</span></span> <br/> <i><span data-ttu-id="84f7c-376">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-376">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`DocumentType` <span data-ttu-id="84f7c-377">ノードの publicId。</span><span class="sxs-lookup"><span data-stu-id="84f7c-377">Node's publicId.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-378">systemId</span><span class="sxs-lookup"><span data-stu-id="84f7c-378">systemId</span></span> <br/> <i><span data-ttu-id="84f7c-379">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-379">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`DocumentType` <span data-ttu-id="84f7c-380">ノードの systemId。</span><span class="sxs-lookup"><span data-stu-id="84f7c-380">Node's systemId.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-381">internalSubset</span><span class="sxs-lookup"><span data-stu-id="84f7c-381">internalSubset</span></span> <br/> <i><span data-ttu-id="84f7c-382">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-382">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`DocumentType` <span data-ttu-id="84f7c-383">ノードの internalSubset。</span><span class="sxs-lookup"><span data-stu-id="84f7c-383">Node's internalSubset.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-384">xmlVersion</span><span class="sxs-lookup"><span data-stu-id="84f7c-384">xmlVersion</span></span> <br/> <i><span data-ttu-id="84f7c-385">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-385">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`Document` <span data-ttu-id="84f7c-386">XML ドキュメントの場合のノードの xml バージョン。</span><span class="sxs-lookup"><span data-stu-id="84f7c-386">Node's xml version in the case of XML documents.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-387">name</span><span class="sxs-lookup"><span data-stu-id="84f7c-387">name</span></span> <br/> <i><span data-ttu-id="84f7c-388">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-388">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`Attr` <span data-ttu-id="84f7c-389">ノードの名前。</span><span class="sxs-lookup"><span data-stu-id="84f7c-389">Node's name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-390">value</span><span class="sxs-lookup"><span data-stu-id="84f7c-390">value</span></span> <br/> <i><span data-ttu-id="84f7c-391">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-391">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`Attr` <span data-ttu-id="84f7c-392">ノードの値。</span><span class="sxs-lookup"><span data-stu-id="84f7c-392">Node's value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-393">frameId</span><span class="sxs-lookup"><span data-stu-id="84f7c-393">frameId</span></span> <br/> <i><span data-ttu-id="84f7c-394">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-394">optional</span></span></i></td>
            <td><a href="page.md#frameid"><code class="flyout">Page.FrameId</code></a></td>
            <td><span data-ttu-id="84f7c-395">フレーム所有者要素のフレーム ID。</span><span class="sxs-lookup"><span data-stu-id="84f7c-395">Frame ID for frame owner elements.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-396">contentDocument</span><span class="sxs-lookup"><span data-stu-id="84f7c-396">contentDocument</span></span> <br/> <i><span data-ttu-id="84f7c-397">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-397">optional</span></span></i></td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td><span data-ttu-id="84f7c-398">フレーム所有者要素のコンテンツ ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="84f7c-398">Content document for frame owner elements.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="84f7c-399">isSVG</span><span class="sxs-lookup"><span data-stu-id="84f7c-399">isSVG</span></span> <br/> <i><span data-ttu-id="84f7c-400">オプション</span><span class="sxs-lookup"><span data-stu-id="84f7c-400">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="84f7c-401">ノードが SVG の場合は True。</span><span class="sxs-lookup"><span data-stu-id="84f7c-401">True if the node is SVG.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="backendnodeid"></a> <span data-ttu-id="84f7c-402">BackendNodeId</span><span class="sxs-lookup"><span data-stu-id="84f7c-402">BackendNodeId</span></span> `integer`

<span data-ttu-id="84f7c-403">フロントエンドにプッシュされていない可能性があるノードを参照するために使用される一意の DOM ノード識別子。</span><span class="sxs-lookup"><span data-stu-id="84f7c-403">Unique DOM node identifier used to reference a node that may not have been pushed to the front-end.</span></span>

</p>

---

### <a name="pseudotype"></a> <span data-ttu-id="84f7c-404">PseudoType</span><span class="sxs-lookup"><span data-stu-id="84f7c-404">PseudoType</span></span> `string`

<span data-ttu-id="84f7c-405">擬似要素型。</span><span class="sxs-lookup"><span data-stu-id="84f7c-405">Pseudo element type.</span></span>

##### <span data-ttu-id="84f7c-406">使用できる値</span><span class="sxs-lookup"><span data-stu-id="84f7c-406">Allowed Values</span></span>
<span data-ttu-id="84f7c-407">最初の行、最初の文字、前、後、選択範囲</span><span class="sxs-lookup"><span data-stu-id="84f7c-407">first-line, first-letter, before, after, selection</span></span>
</p>

---

## <span data-ttu-id="84f7c-408">依存関係</span><span class="sxs-lookup"><span data-stu-id="84f7c-408">Dependencies</span></span>

[<span data-ttu-id="84f7c-409">ランタイム</span><span class="sxs-lookup"><span data-stu-id="84f7c-409">Runtime</span></span>](runtime.md)
