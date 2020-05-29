---
description: ページドメインの参照。 検査されたページに関連するアクションとイベントは、ページドメインに属しています。
title: ページドメイン-DevTools プロトコルバージョン0.2
author: pelavall
ms.author: pelavall
ms.date: 8/17/2018
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: 688cc1fcfce0b81c5eed0c858a4a60b4754c49a4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569601"
---
# <span data-ttu-id="91f58-104">Page</span><span class="sxs-lookup"><span data-stu-id="91f58-104">Page</span></span>
<span data-ttu-id="91f58-105">検査されたページに関連するアクションとイベントは、ページドメインに属しています。</span><span class="sxs-lookup"><span data-stu-id="91f58-105">Actions and events related to the inspected page belong to the page domain.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="91f58-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="91f58-106">Methods</span></span>**](#methods) | <span data-ttu-id="91f58-107">[有効化](#enable)、[無効化](#disable)、[移動](#navigate)、 [getフレームツリー](#getframetree)</span><span class="sxs-lookup"><span data-stu-id="91f58-107">[enable](#enable), [disable](#disable), [navigate](#navigate), [getFrameTree](#getframetree)</span></span> |
| [**<span data-ttu-id="91f58-108">イベント</span><span class="sxs-lookup"><span data-stu-id="91f58-108">Events</span></span>**](#events) | <span data-ttu-id="91f58-109">[フレームアタッチ](#frameattached)、[フレーム分離](#framedetached)、 [framenavigated](#framenavigated)、 [loadEventFired](#loadeventfired)、 [domcontenteventfired](#domcontenteventfired)</span><span class="sxs-lookup"><span data-stu-id="91f58-109">[frameAttached](#frameattached), [frameDetached](#framedetached), [frameNavigated](#framenavigated), [loadEventFired](#loadeventfired), [domContentEventFired](#domcontenteventfired)</span></span> |
| [**<span data-ttu-id="91f58-110">型</span><span class="sxs-lookup"><span data-stu-id="91f58-110">Types</span></span>**](#types) | <span data-ttu-id="91f58-111">フレーム[id](#frameid)、[フレーム、フレーム](#frame)[ツリー](#frametree)</span><span class="sxs-lookup"><span data-stu-id="91f58-111">[FrameId](#frameid), [Frame](#frame), [FrameTree](#frametree)</span></span> |
## <span data-ttu-id="91f58-112">メソッド</span><span class="sxs-lookup"><span data-stu-id="91f58-112">Methods</span></span>

### <span data-ttu-id="91f58-113">[有効]</span><span class="sxs-lookup"><span data-stu-id="91f58-113">enable</span></span>
<span data-ttu-id="91f58-114">ページドメインの通知を有効にします。</span><span class="sxs-lookup"><span data-stu-id="91f58-114">Enables page domain notifications.</span></span>

</p>

---

### <span data-ttu-id="91f58-115">[無効]</span><span class="sxs-lookup"><span data-stu-id="91f58-115">disable</span></span>
<span data-ttu-id="91f58-116">ページドメインの通知を無効にします。</span><span class="sxs-lookup"><span data-stu-id="91f58-116">Disables page domain notifications.</span></span>

</p>

---

### <span data-ttu-id="91f58-117">ナビゲート</span><span class="sxs-lookup"><span data-stu-id="91f58-117">navigate</span></span>
<span data-ttu-id="91f58-118">指定した URL に現在のページを移動します。</span><span class="sxs-lookup"><span data-stu-id="91f58-118">Navigates current page to the given URL.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="91f58-119">パラメーター</span><span class="sxs-lookup"><span data-stu-id="91f58-119">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="91f58-120">url</span><span class="sxs-lookup"><span data-stu-id="91f58-120">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="91f58-121">ページの移動先の URL。</span><span class="sxs-lookup"><span data-stu-id="91f58-121">URL to navigate the page to.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="91f58-122">フレーム Id</span><span class="sxs-lookup"><span data-stu-id="91f58-122">frameId</span></span> <br/> <i><span data-ttu-id="91f58-123">オプション</span><span class="sxs-lookup"><span data-stu-id="91f58-123">optional</span></span></i></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="91f58-124">移動するフレーム id。</span><span class="sxs-lookup"><span data-stu-id="91f58-124">Frame id to navigate.</span></span> <span data-ttu-id="91f58-125">指定しない場合、上のページが移動します。</span><span class="sxs-lookup"><span data-stu-id="91f58-125">If not specified, will navigate the top page.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="91f58-126">返し</span><span class="sxs-lookup"><span data-stu-id="91f58-126">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="91f58-127">フレーム Id</span><span class="sxs-lookup"><span data-stu-id="91f58-127">frameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="91f58-128">移動されるフレーム id。</span><span class="sxs-lookup"><span data-stu-id="91f58-128">Frame id that will be navigated.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="91f58-129">Getフレームツリー</span><span class="sxs-lookup"><span data-stu-id="91f58-129">getFrameTree</span></span>
<span data-ttu-id="91f58-130">存在するフレームツリー構造体を返します。</span><span class="sxs-lookup"><span data-stu-id="91f58-130">Returns present frame tree structure.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="91f58-131">返し</span><span class="sxs-lookup"><span data-stu-id="91f58-131">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="91f58-132">フレームツリー</span><span class="sxs-lookup"><span data-stu-id="91f58-132">frameTree</span></span></td>
            <td><a href="#frametree"><code class="flyout">FrameTree</code></a></td>
            <td><span data-ttu-id="91f58-133">フレームツリー構造を表示します。</span><span class="sxs-lookup"><span data-stu-id="91f58-133">Present frame tree structure.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="91f58-134">イベント</span><span class="sxs-lookup"><span data-stu-id="91f58-134">Events</span></span>

### <span data-ttu-id="91f58-135">フレーム添付</span><span class="sxs-lookup"><span data-stu-id="91f58-135">frameAttached</span></span>
<span data-ttu-id="91f58-136">フレームが親にアタッチされたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="91f58-136">Fired when frame has been attached to its parent.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="91f58-137">パラメーター</span><span class="sxs-lookup"><span data-stu-id="91f58-137">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="91f58-138">フレーム Id</span><span class="sxs-lookup"><span data-stu-id="91f58-138">frameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="91f58-139">添付されたフレームの Id です。</span><span class="sxs-lookup"><span data-stu-id="91f58-139">Id of the frame that has been attached.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="91f58-140">Parentフレーム Id</span><span class="sxs-lookup"><span data-stu-id="91f58-140">parentFrameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="91f58-141">親フレーム識別子。</span><span class="sxs-lookup"><span data-stu-id="91f58-141">Parent frame identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="91f58-142">スタック</span><span class="sxs-lookup"><span data-stu-id="91f58-142">stack</span></span> <br/> <i><span data-ttu-id="91f58-143">オプション</span><span class="sxs-lookup"><span data-stu-id="91f58-143">optional</span></span></i></td>
            <td><a href="runtime.md#stacktrace"><code class="flyout">Runtime.StackTrace</code></a></td>
            <td><span data-ttu-id="91f58-144">フレームがアタッチされたときの JavaScript スタックトレース。 script からフレームが開始された場合にのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="91f58-144">JavaScript stack trace of when frame was attached, only set if frame initiated from script.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="91f58-145">フレームのデタッチ</span><span class="sxs-lookup"><span data-stu-id="91f58-145">frameDetached</span></span>
<span data-ttu-id="91f58-146">Frame が親から切り離されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="91f58-146">Fired when frame has been detached from its parent.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="91f58-147">パラメーター</span><span class="sxs-lookup"><span data-stu-id="91f58-147">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="91f58-148">フレーム Id</span><span class="sxs-lookup"><span data-stu-id="91f58-148">frameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="91f58-149">デタッチされたフレームの Id です。</span><span class="sxs-lookup"><span data-stu-id="91f58-149">Id of the frame that has been detached.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="91f58-150">Framのゲート</span><span class="sxs-lookup"><span data-stu-id="91f58-150">frameNavigated</span></span>
<span data-ttu-id="91f58-151">フレームのナビゲーションが完了した後に発生します。</span><span class="sxs-lookup"><span data-stu-id="91f58-151">Fired once navigation of the frame has completed.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="91f58-152">パラメーター</span><span class="sxs-lookup"><span data-stu-id="91f58-152">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="91f58-153">時間</span><span class="sxs-lookup"><span data-stu-id="91f58-153">frame</span></span></td>
            <td><a href="#frame"><code class="flyout">Frame</code></a></td>
            <td><span data-ttu-id="91f58-154">Frame オブジェクト</span><span class="sxs-lookup"><span data-stu-id="91f58-154">Frame object.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="91f58-155">loadEventFired</span><span class="sxs-lookup"><span data-stu-id="91f58-155">loadEventFired</span></span>
<span data-ttu-id="91f58-156">Onload イベントに対応しています。</span><span class="sxs-lookup"><span data-stu-id="91f58-156">Corresponds to the window.onload event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="91f58-157">パラメーター</span><span class="sxs-lookup"><span data-stu-id="91f58-157">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="91f58-158">示</span><span class="sxs-lookup"><span data-stu-id="91f58-158">timestamp</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="91f58-159">エポックからのミリ秒数。</span><span class="sxs-lookup"><span data-stu-id="91f58-159">Number of milliseconds since epoch.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="91f58-160">domContentEventFired</span><span class="sxs-lookup"><span data-stu-id="91f58-160">domContentEventFired</span></span>
<span data-ttu-id="91f58-161">OnDOMContentLoaded イベントに対応しています。</span><span class="sxs-lookup"><span data-stu-id="91f58-161">Corresponds to the document.onDOMContentLoaded event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="91f58-162">パラメーター</span><span class="sxs-lookup"><span data-stu-id="91f58-162">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="91f58-163">示</span><span class="sxs-lookup"><span data-stu-id="91f58-163">timestamp</span></span></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="91f58-164">エポックからのミリ秒数。</span><span class="sxs-lookup"><span data-stu-id="91f58-164">Number of milliseconds since epoch.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="91f58-165">型</span><span class="sxs-lookup"><span data-stu-id="91f58-165">Types</span></span>

### <a name="frameid"></a> <span data-ttu-id="91f58-166">フレーム Id</span><span class="sxs-lookup"><span data-stu-id="91f58-166">FrameId</span></span> `string`

<span data-ttu-id="91f58-167">一意のフレーム識別子。</span><span class="sxs-lookup"><span data-stu-id="91f58-167">Unique frame identifier.</span></span>

</p>

---

### <a name="frame"></a> <span data-ttu-id="91f58-168">フレーム</span><span class="sxs-lookup"><span data-stu-id="91f58-168">Frame</span></span> `object`

<span data-ttu-id="91f58-169">ページのフレームに関する情報。</span><span class="sxs-lookup"><span data-stu-id="91f58-169">Information about the Frame on the Page.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="91f58-170">プロパティ</span><span class="sxs-lookup"><span data-stu-id="91f58-170">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="91f58-171">id</span><span class="sxs-lookup"><span data-stu-id="91f58-171">id</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="91f58-172">Frame の一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="91f58-172">Frame unique identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="91f58-173">parentId</span><span class="sxs-lookup"><span data-stu-id="91f58-173">parentId</span></span> <br/> <i><span data-ttu-id="91f58-174">オプション</span><span class="sxs-lookup"><span data-stu-id="91f58-174">optional</span></span></i></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span data-ttu-id="91f58-175">親フレームの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="91f58-175">Parent frame unique identifier.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="91f58-176">name</span><span class="sxs-lookup"><span data-stu-id="91f58-176">name</span></span> <br/> <i><span data-ttu-id="91f58-177">オプション</span><span class="sxs-lookup"><span data-stu-id="91f58-177">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="91f58-178">タグで指定されているフレームの名前。</span><span class="sxs-lookup"><span data-stu-id="91f58-178">Frame's name as specified in the tag.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="91f58-179">url</span><span class="sxs-lookup"><span data-stu-id="91f58-179">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="91f58-180">フレームドキュメントの URL。</span><span class="sxs-lookup"><span data-stu-id="91f58-180">Frame document's URL.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="91f58-181">securityOrigin</span><span class="sxs-lookup"><span data-stu-id="91f58-181">securityOrigin</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="91f58-182">フレームドキュメントのセキュリティ基準。</span><span class="sxs-lookup"><span data-stu-id="91f58-182">Frame document's security origin.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="91f58-183">Mime</span><span class="sxs-lookup"><span data-stu-id="91f58-183">mimeType</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="91f58-184">ブラウザーで決定されるフレームドキュメントの Mime。</span><span class="sxs-lookup"><span data-stu-id="91f58-184">Frame document's mimeType as determined by the browser.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="frametree"></a> <span data-ttu-id="91f58-185">フレームツリー</span><span class="sxs-lookup"><span data-stu-id="91f58-185">FrameTree</span></span> `object`

<span data-ttu-id="91f58-186">フレーム階層に関する情報。</span><span class="sxs-lookup"><span data-stu-id="91f58-186">Information about the Frame hierarchy.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="91f58-187">プロパティ</span><span class="sxs-lookup"><span data-stu-id="91f58-187">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="91f58-188">時間</span><span class="sxs-lookup"><span data-stu-id="91f58-188">frame</span></span></td>
            <td><a href="#frame"><code class="flyout">Frame</code></a></td>
            <td><span data-ttu-id="91f58-189">このツリー項目のフレーム情報。</span><span class="sxs-lookup"><span data-stu-id="91f58-189">Frame information for this tree item.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="91f58-190">childFrames</span><span class="sxs-lookup"><span data-stu-id="91f58-190">childFrames</span></span> <br/> <i><span data-ttu-id="91f58-191">オプション</span><span class="sxs-lookup"><span data-stu-id="91f58-191">optional</span></span></i></td>
            <td><a href="#frametree"><code class="flyout">FrameTree[]</code></a></td>
            <td><span data-ttu-id="91f58-192">子フレーム。</span><span class="sxs-lookup"><span data-stu-id="91f58-192">Child frames.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---
