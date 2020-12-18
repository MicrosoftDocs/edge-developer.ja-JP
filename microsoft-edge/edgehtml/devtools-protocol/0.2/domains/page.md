---
description: ページ ドメインの DevTools プロトコル バージョン 0.2 (EdgeHTML) リファレンス。 検査されたページに関連するアクションとイベントは、ページ ドメインに属します。
title: ページ ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2f1849a2e2aa2f53cef9dff5d03ac991d368a6f3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234411"
---
# <span data-ttu-id="d83a7-104">ページ ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="d83a7-104">Page Domain - DevTools Protocol Version 0.2 (EdgeHTML)</span></span>  

<span data-ttu-id="d83a7-105">検査されたページに関連するアクションとイベントは、ページ ドメインに属します。</span><span class="sxs-lookup"><span data-stu-id="d83a7-105">Actions and events related to the inspected page belong to the page domain.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="d83a7-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="d83a7-106">Methods</span></span>**](#methods) | <span data-ttu-id="d83a7-107">[有効](#enable)、[無効、](#disable)[移動](#navigate)[、getFrameTree](#getframetree)</span><span class="sxs-lookup"><span data-stu-id="d83a7-107">[enable](#enable), [disable](#disable), [navigate](#navigate), [getFrameTree](#getframetree)</span></span> |
| [**<span data-ttu-id="d83a7-108">イベント</span><span class="sxs-lookup"><span data-stu-id="d83a7-108">Events</span></span>**](#events) | <span data-ttu-id="d83a7-109">[frameAttached](#frameattached)、 [frameDetached](#framedetached)、 [frameNavigated](#framenavigated)、 [loadEventFired](#loadeventfired)、 [domContentEventFired](#domcontenteventfired)</span><span class="sxs-lookup"><span data-stu-id="d83a7-109">[frameAttached](#frameattached), [frameDetached](#framedetached), [frameNavigated](#framenavigated), [loadEventFired](#loadeventfired), [domContentEventFired](#domcontenteventfired)</span></span> |
| [**<span data-ttu-id="d83a7-110">型</span><span class="sxs-lookup"><span data-stu-id="d83a7-110">Types</span></span>**](#types) | <span data-ttu-id="d83a7-111">[](#frameid)FrameId、Frame、FrameTree [](#frame) [](#frametree)</span><span class="sxs-lookup"><span data-stu-id="d83a7-111">[FrameId](#frameid), [Frame](#frame), [FrameTree](#frametree)</span></span> |
## <span data-ttu-id="d83a7-112">メソッド</span><span class="sxs-lookup"><span data-stu-id="d83a7-112">Methods</span></span>

### <span data-ttu-id="d83a7-113">[有効]</span><span class="sxs-lookup"><span data-stu-id="d83a7-113">enable</span></span>
<span data-ttu-id="d83a7-114">ページ ドメイン通知を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d83a7-114">Enables page domain notifications.</span></span>

</p>

---

### <span data-ttu-id="d83a7-115">[無効]</span><span class="sxs-lookup"><span data-stu-id="d83a7-115">disable</span></span>
<span data-ttu-id="d83a7-116">ページ ドメイン通知を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d83a7-116">Disables page domain notifications.</span></span>

</p>

---

### <span data-ttu-id="d83a7-117">ナビゲート</span><span class="sxs-lookup"><span data-stu-id="d83a7-117">navigate</span></span>
<span data-ttu-id="d83a7-118">現在のページを特定の URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="d83a7-118">Navigates current page to the given URL.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="d83a7-119">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d83a7-119">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="d83a7-120">url</span><span class="sxs-lookup"><span data-stu-id="d83a7-120">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="d83a7-121">ページの移動先の URL。</span><span class="sxs-lookup"><span data-stu-id="d83a7-121">URL to navigate the page to.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="d83a7-122">frameId</span><span class="sxs-lookup"><span data-stu-id="d83a7-122">frameId</span></span> <br/> <i><span data-ttu-id="d83a7-123">オプション</span><span class="sxs-lookup"><span data-stu-id="d83a7-123">optional</span></span></i></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="d83a7-124">移動するフレーム ID。</span><span class="sxs-lookup"><span data-stu-id="d83a7-124">Frame id to navigate.</span></span> <span data-ttu-id="d83a7-125">指定しない場合、トップ ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="d83a7-125">If not specified, will navigate the top page.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="d83a7-126">戻り値</span><span class="sxs-lookup"><span data-stu-id="d83a7-126">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="d83a7-127">frameId</span><span class="sxs-lookup"><span data-stu-id="d83a7-127">frameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="d83a7-128">移動するフレーム ID です。</span><span class="sxs-lookup"><span data-stu-id="d83a7-128">Frame id that will be navigated.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="d83a7-129">getFrameTree</span><span class="sxs-lookup"><span data-stu-id="d83a7-129">getFrameTree</span></span>
<span data-ttu-id="d83a7-130">現在のフレーム ツリー構造を返します。</span><span class="sxs-lookup"><span data-stu-id="d83a7-130">Returns present frame tree structure.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="d83a7-131">戻り値</span><span class="sxs-lookup"><span data-stu-id="d83a7-131">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="d83a7-132">frameTree</span><span class="sxs-lookup"><span data-stu-id="d83a7-132">frameTree</span></span></td>
            <td><a href="#frametree"><code class="flyout">FrameTree</code></a></td>
            <td><span data-ttu-id="d83a7-133">現在のフレーム ツリー構造。</span><span class="sxs-lookup"><span data-stu-id="d83a7-133">Present frame tree structure.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="d83a7-134">イベント</span><span class="sxs-lookup"><span data-stu-id="d83a7-134">Events</span></span>

### <span data-ttu-id="d83a7-135">frameAttached</span><span class="sxs-lookup"><span data-stu-id="d83a7-135">frameAttached</span></span>
<span data-ttu-id="d83a7-136">フレームが親にアタッチされている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="d83a7-136">Fired when frame has been attached to its parent.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="d83a7-137">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d83a7-137">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="d83a7-138">frameId</span><span class="sxs-lookup"><span data-stu-id="d83a7-138">frameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="d83a7-139">アタッチされているフレームの ID。</span><span class="sxs-lookup"><span data-stu-id="d83a7-139">Id of the frame that has been attached.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="d83a7-140">parentFrameId</span><span class="sxs-lookup"><span data-stu-id="d83a7-140">parentFrameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="d83a7-141">親フレーム識別子。</span><span class="sxs-lookup"><span data-stu-id="d83a7-141">Parent frame identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="d83a7-142">stack</span><span class="sxs-lookup"><span data-stu-id="d83a7-142">stack</span></span> <br/> <i><span data-ttu-id="d83a7-143">オプション</span><span class="sxs-lookup"><span data-stu-id="d83a7-143">optional</span></span></i></td>
            <td><a href="runtime.md#stacktrace"><code class="flyout">Runtime.StackTrace</code></a></td>
            <td><span data-ttu-id="d83a7-144">フレームがアタッチされた場合の JavaScript スタック トレース。スクリプトからフレームが開始された場合にのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="d83a7-144">JavaScript stack trace of when frame was attached, only set if frame initiated from script.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="d83a7-145">frameDetached</span><span class="sxs-lookup"><span data-stu-id="d83a7-145">frameDetached</span></span>
<span data-ttu-id="d83a7-146">フレームが親からデタッチされた場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="d83a7-146">Fired when frame has been detached from its parent.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="d83a7-147">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d83a7-147">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="d83a7-148">frameId</span><span class="sxs-lookup"><span data-stu-id="d83a7-148">frameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="d83a7-149">デタッチされたフレームの ID。</span><span class="sxs-lookup"><span data-stu-id="d83a7-149">Id of the frame that has been detached.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="d83a7-150">frameNavigated</span><span class="sxs-lookup"><span data-stu-id="d83a7-150">frameNavigated</span></span>
<span data-ttu-id="d83a7-151">フレームのナビゲーションが完了すると発生します。</span><span class="sxs-lookup"><span data-stu-id="d83a7-151">Fired once navigation of the frame has completed.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="d83a7-152">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d83a7-152">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="d83a7-153">frame</span><span class="sxs-lookup"><span data-stu-id="d83a7-153">frame</span></span></td>
            <td><a href="#frame"><code class="flyout">Frame</code></a></td>
            <td><span data-ttu-id="d83a7-154">Frame オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d83a7-154">Frame object.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="d83a7-155">loadEventFired</span><span class="sxs-lookup"><span data-stu-id="d83a7-155">loadEventFired</span></span>
<span data-ttu-id="d83a7-156">window.onload イベントに対応します。</span><span class="sxs-lookup"><span data-stu-id="d83a7-156">Corresponds to the window.onload event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="d83a7-157">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d83a7-157">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="d83a7-158">timestamp</span><span class="sxs-lookup"><span data-stu-id="d83a7-158">timestamp</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="d83a7-159">エポックからのミリ秒。</span><span class="sxs-lookup"><span data-stu-id="d83a7-159">Number of milliseconds since epoch.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="d83a7-160">domContentEventFired</span><span class="sxs-lookup"><span data-stu-id="d83a7-160">domContentEventFired</span></span>
<span data-ttu-id="d83a7-161">document.onDOMContentLoaded イベントに対応します。</span><span class="sxs-lookup"><span data-stu-id="d83a7-161">Corresponds to the document.onDOMContentLoaded event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="d83a7-162">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d83a7-162">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="d83a7-163">timestamp</span><span class="sxs-lookup"><span data-stu-id="d83a7-163">timestamp</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="d83a7-164">エポックからのミリ秒。</span><span class="sxs-lookup"><span data-stu-id="d83a7-164">Number of milliseconds since epoch.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="d83a7-165">型</span><span class="sxs-lookup"><span data-stu-id="d83a7-165">Types</span></span>

### <a name="frameid"></a> <span data-ttu-id="d83a7-166">FrameId</span><span class="sxs-lookup"><span data-stu-id="d83a7-166">FrameId</span></span> `string`

<span data-ttu-id="d83a7-167">一意のフレーム識別子。</span><span class="sxs-lookup"><span data-stu-id="d83a7-167">Unique frame identifier.</span></span>

</p>

---

### <a name="frame"></a> <span data-ttu-id="d83a7-168">フレーム</span><span class="sxs-lookup"><span data-stu-id="d83a7-168">Frame</span></span> `object`

<span data-ttu-id="d83a7-169">ページ上のフレームに関する情報。</span><span class="sxs-lookup"><span data-stu-id="d83a7-169">Information about the Frame on the Page.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="d83a7-170">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d83a7-170">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="d83a7-171">id</span><span class="sxs-lookup"><span data-stu-id="d83a7-171">id</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="d83a7-172">フレームの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="d83a7-172">Frame unique identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="d83a7-173">parentId</span><span class="sxs-lookup"><span data-stu-id="d83a7-173">parentId</span></span> <br/> <i><span data-ttu-id="d83a7-174">オプション</span><span class="sxs-lookup"><span data-stu-id="d83a7-174">optional</span></span></i></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="d83a7-175">親フレームの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="d83a7-175">Parent frame unique identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="d83a7-176">name</span><span class="sxs-lookup"><span data-stu-id="d83a7-176">name</span></span> <br/> <i><span data-ttu-id="d83a7-177">オプション</span><span class="sxs-lookup"><span data-stu-id="d83a7-177">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="d83a7-178">タグで指定されているフレームの名前。</span><span class="sxs-lookup"><span data-stu-id="d83a7-178">Frame's name as specified in the tag.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="d83a7-179">url</span><span class="sxs-lookup"><span data-stu-id="d83a7-179">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="d83a7-180">フレーム ドキュメントの URL。</span><span class="sxs-lookup"><span data-stu-id="d83a7-180">Frame document's URL.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="d83a7-181">securityOrigin</span><span class="sxs-lookup"><span data-stu-id="d83a7-181">securityOrigin</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="d83a7-182">フレーム ドキュメントのセキュリティの原点。</span><span class="sxs-lookup"><span data-stu-id="d83a7-182">Frame document's security origin.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="d83a7-183">mimeType</span><span class="sxs-lookup"><span data-stu-id="d83a7-183">mimeType</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="d83a7-184">ブラウザーによって決まる、ドキュメントの mimeType をフレームします。</span><span class="sxs-lookup"><span data-stu-id="d83a7-184">Frame document's mimeType as determined by the browser.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="frametree"></a> <span data-ttu-id="d83a7-185">FrameTree</span><span class="sxs-lookup"><span data-stu-id="d83a7-185">FrameTree</span></span> `object`

<span data-ttu-id="d83a7-186">フレーム階層に関する情報。</span><span class="sxs-lookup"><span data-stu-id="d83a7-186">Information about the Frame hierarchy.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="d83a7-187">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d83a7-187">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="d83a7-188">frame</span><span class="sxs-lookup"><span data-stu-id="d83a7-188">frame</span></span></td>
            <td><a href="#frame"><code class="flyout">Frame</code></a></td>
            <td><span data-ttu-id="d83a7-189">このツリー項目のフレーム情報。</span><span class="sxs-lookup"><span data-stu-id="d83a7-189">Frame information for this tree item.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="d83a7-190">childFrames</span><span class="sxs-lookup"><span data-stu-id="d83a7-190">childFrames</span></span> <br/> <i><span data-ttu-id="d83a7-191">オプション</span><span class="sxs-lookup"><span data-stu-id="d83a7-191">optional</span></span></i></td>
            <td><a href="#frametree"><code class="flyout">FrameTree[]</code></a></td>
            <td><span data-ttu-id="d83a7-192">子フレーム。</span><span class="sxs-lookup"><span data-stu-id="d83a7-192">Child frames.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---
