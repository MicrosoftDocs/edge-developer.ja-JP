---
description: ページ ドメインの DevTools プロトコル バージョン 0.2 (EdgeHTML) リファレンス。 検査されたページに関連するアクションとイベントは、ページ ドメインに属します。
title: ページ ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d969dd100164ace61445a4618174cfa943dcfd2b
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398848"
---
# <a name="page-domain---devtools-protocol-version-02-edgehtml"></a><span data-ttu-id="2d289-104">ページ ドメイン - DevTools プロトコル バージョン 0.2 (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="2d289-104">Page Domain - DevTools Protocol Version 0.2 (EdgeHTML)</span></span>  

<span data-ttu-id="2d289-105">検査されたページに関連するアクションとイベントは、ページ ドメインに属します。</span><span class="sxs-lookup"><span data-stu-id="2d289-105">Actions and events related to the inspected page belong to the page domain.</span></span>  

| <span data-ttu-id="2d289-106">分類</span><span class="sxs-lookup"><span data-stu-id="2d289-106">Classification</span></span> | <span data-ttu-id="2d289-107">Members</span><span class="sxs-lookup"><span data-stu-id="2d289-107">Members</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="2d289-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="2d289-108">Methods</span></span>](#methods) | <span data-ttu-id="2d289-109">[enable](#enable), [disable](#disable), [navigate](#navigate), [getFrameTree](#getframetree)</span><span class="sxs-lookup"><span data-stu-id="2d289-109">[enable](#enable), [disable](#disable), [navigate](#navigate), [getFrameTree](#getframetree)</span></span> |  
| [<span data-ttu-id="2d289-110">イベント</span><span class="sxs-lookup"><span data-stu-id="2d289-110">Events</span></span>](#events) | <span data-ttu-id="2d289-111">[frameAttached](#frameattached), [frameDetached](#framedetached), [frameNavigated](#framenavigated), [loadEventFired](#loadeventfired), [domContentEventFired](#domcontenteventfired)</span><span class="sxs-lookup"><span data-stu-id="2d289-111">[frameAttached](#frameattached), [frameDetached](#framedetached), [frameNavigated](#framenavigated), [loadEventFired](#loadeventfired), [domContentEventFired](#domcontenteventfired)</span></span> |  
| [<span data-ttu-id="2d289-112">型</span><span class="sxs-lookup"><span data-stu-id="2d289-112">Types</span></span>](#types) | <span data-ttu-id="2d289-113">[FrameId](#frameid)、 [Frame](#frame)、 [FrameTree](#frametree)</span><span class="sxs-lookup"><span data-stu-id="2d289-113">[FrameId](#frameid), [Frame](#frame), [FrameTree](#frametree)</span></span> |  

## <a name="methods"></a><span data-ttu-id="2d289-114">メソッド</span><span class="sxs-lookup"><span data-stu-id="2d289-114">Methods</span></span>  

### <a name="enable"></a><span data-ttu-id="2d289-115">[有効]</span><span class="sxs-lookup"><span data-stu-id="2d289-115">enable</span></span>  

<span data-ttu-id="2d289-116">ページ ドメイン通知を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2d289-116">Enables page domain notifications.</span></span>  

&nbsp;  

---  

### <a name="disable"></a><span data-ttu-id="2d289-117">[無効]</span><span class="sxs-lookup"><span data-stu-id="2d289-117">disable</span></span>  

<span data-ttu-id="2d289-118">ページ ドメイン通知を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2d289-118">Disables page domain notifications.</span></span>  

&nbsp;  

---  

### <a name="navigate"></a><span data-ttu-id="2d289-119">ナビゲート</span><span class="sxs-lookup"><span data-stu-id="2d289-119">navigate</span></span>  

<span data-ttu-id="2d289-120">現在のページを特定の URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="2d289-120">Navigates current page to the given URL.</span></span>  

| <span data-ttu-id="2d289-121">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d289-121">Parameters</span></span> | <span data-ttu-id="2d289-122">型</span><span class="sxs-lookup"><span data-stu-id="2d289-122">Type</span></span> | <span data-ttu-id="2d289-123">詳細</span><span class="sxs-lookup"><span data-stu-id="2d289-123">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="2d289-124">url</span><span class="sxs-lookup"><span data-stu-id="2d289-124">url</span></span> | `string` | <span data-ttu-id="2d289-125">ページを移動する URL。</span><span class="sxs-lookup"><span data-stu-id="2d289-125">URL to navigate the page to.</span></span> |  
| <span data-ttu-id="2d289-126">frameId \(optional\)</span><span class="sxs-lookup"><span data-stu-id="2d289-126">frameId \(optional\)</span></span> | [<span data-ttu-id="2d289-127">FrameId</span><span class="sxs-lookup"><span data-stu-id="2d289-127">FrameId</span></span>](#frameid) | <span data-ttu-id="2d289-128">移動するフレーム ID。</span><span class="sxs-lookup"><span data-stu-id="2d289-128">Frame id to navigate.</span></span>  <span data-ttu-id="2d289-129">指定しない場合は、トップ ページを移動します。</span><span class="sxs-lookup"><span data-stu-id="2d289-129">If not specified, will navigate the top page.</span></span> |  

| <span data-ttu-id="2d289-130">戻り値</span><span class="sxs-lookup"><span data-stu-id="2d289-130">Returns</span></span> | <span data-ttu-id="2d289-131">型</span><span class="sxs-lookup"><span data-stu-id="2d289-131">Type</span></span> | <span data-ttu-id="2d289-132">詳細</span><span class="sxs-lookup"><span data-stu-id="2d289-132">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="2d289-133">frameId</span><span class="sxs-lookup"><span data-stu-id="2d289-133">frameId</span></span> | [<span data-ttu-id="2d289-134">FrameId</span><span class="sxs-lookup"><span data-stu-id="2d289-134">FrameId</span></span>](#frameid) | <span data-ttu-id="2d289-135">移動するフレーム ID。</span><span class="sxs-lookup"><span data-stu-id="2d289-135">Frame id that will be navigated.</span></span> |  

---  

### <a name="getframetree"></a><span data-ttu-id="2d289-136">getFrameTree</span><span class="sxs-lookup"><span data-stu-id="2d289-136">getFrameTree</span></span>  

<span data-ttu-id="2d289-137">現在のフレーム ツリー構造を返します。</span><span class="sxs-lookup"><span data-stu-id="2d289-137">Returns present frame tree structure.</span></span>  

| <span data-ttu-id="2d289-138">戻り値</span><span class="sxs-lookup"><span data-stu-id="2d289-138">Returns</span></span> | <span data-ttu-id="2d289-139">型</span><span class="sxs-lookup"><span data-stu-id="2d289-139">Type</span></span> | <span data-ttu-id="2d289-140">詳細</span><span class="sxs-lookup"><span data-stu-id="2d289-140">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="2d289-141">frameTree</span><span class="sxs-lookup"><span data-stu-id="2d289-141">frameTree</span></span> | [<span data-ttu-id="2d289-142">FrameTree</span><span class="sxs-lookup"><span data-stu-id="2d289-142">FrameTree</span></span>](#frametree) | <span data-ttu-id="2d289-143">現在のフレーム ツリー構造。</span><span class="sxs-lookup"><span data-stu-id="2d289-143">Present frame tree structure.</span></span> |  

---  

## <a name="events"></a><span data-ttu-id="2d289-144">イベント</span><span class="sxs-lookup"><span data-stu-id="2d289-144">Events</span></span>  

### <a name="frameattached"></a><span data-ttu-id="2d289-145">frameAttached</span><span class="sxs-lookup"><span data-stu-id="2d289-145">frameAttached</span></span>  

<span data-ttu-id="2d289-146">フレームが親に接続されている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="2d289-146">Fired when frame has been attached to its parent.</span></span>  

| <span data-ttu-id="2d289-147">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d289-147">Parameters</span></span> | <span data-ttu-id="2d289-148">型</span><span class="sxs-lookup"><span data-stu-id="2d289-148">Type</span></span> | <span data-ttu-id="2d289-149">詳細</span><span class="sxs-lookup"><span data-stu-id="2d289-149">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="2d289-150">frameId</span><span class="sxs-lookup"><span data-stu-id="2d289-150">frameId</span></span> | [<span data-ttu-id="2d289-151">FrameId</span><span class="sxs-lookup"><span data-stu-id="2d289-151">FrameId</span></span>](#frameid) | <span data-ttu-id="2d289-152">接続されているフレームの ID。</span><span class="sxs-lookup"><span data-stu-id="2d289-152">Id of the frame that has been attached.</span></span> |  
| <span data-ttu-id="2d289-153">parentFrameId</span><span class="sxs-lookup"><span data-stu-id="2d289-153">parentFrameId</span></span> | [<span data-ttu-id="2d289-154">FrameId</span><span class="sxs-lookup"><span data-stu-id="2d289-154">FrameId</span></span>](#frameid) | <span data-ttu-id="2d289-155">親フレーム識別子。</span><span class="sxs-lookup"><span data-stu-id="2d289-155">Parent frame identifier.</span></span> |  
| <span data-ttu-id="2d289-156">stack \(optional\)</span><span class="sxs-lookup"><span data-stu-id="2d289-156">stack \(optional\)</span></span> | [<span data-ttu-id="2d289-157">Runtime.StackTrace</span><span class="sxs-lookup"><span data-stu-id="2d289-157">Runtime.StackTrace</span></span>](./runtime.md#stacktrace) | <span data-ttu-id="2d289-158">フレームが接続された場合の JavaScript スタック トレースは、スクリプトからフレームが開始された場合にのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="2d289-158">JavaScript stack trace of when frame was attached, only set if frame initiated from script.</span></span> |  

---  

### <a name="framedetached"></a><span data-ttu-id="2d289-159">frameDetached</span><span class="sxs-lookup"><span data-stu-id="2d289-159">frameDetached</span></span>  

<span data-ttu-id="2d289-160">フレームが親から切り離された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="2d289-160">Fired when frame has been detached from its parent.</span></span>  

| <span data-ttu-id="2d289-161">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d289-161">Parameters</span></span> | <span data-ttu-id="2d289-162">型</span><span class="sxs-lookup"><span data-stu-id="2d289-162">Type</span></span> | <span data-ttu-id="2d289-163">詳細</span><span class="sxs-lookup"><span data-stu-id="2d289-163">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="2d289-164">frameId</span><span class="sxs-lookup"><span data-stu-id="2d289-164">frameId</span></span> | [<span data-ttu-id="2d289-165">FrameId</span><span class="sxs-lookup"><span data-stu-id="2d289-165">FrameId</span></span>](#frameid) | <span data-ttu-id="2d289-166">デタッチされたフレームの ID。</span><span class="sxs-lookup"><span data-stu-id="2d289-166">ID of the frame that has been detached.</span></span> |  

---  

### <a name="framenavigated"></a><span data-ttu-id="2d289-167">frameNavigated</span><span class="sxs-lookup"><span data-stu-id="2d289-167">frameNavigated</span></span>  

<span data-ttu-id="2d289-168">フレームのナビゲーションが完了すると発生します。</span><span class="sxs-lookup"><span data-stu-id="2d289-168">Fired once navigation of the frame has completed.</span></span>  

| <span data-ttu-id="2d289-169">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d289-169">Parameters</span></span> | <span data-ttu-id="2d289-170">型</span><span class="sxs-lookup"><span data-stu-id="2d289-170">Type</span></span> | <span data-ttu-id="2d289-171">詳細</span><span class="sxs-lookup"><span data-stu-id="2d289-171">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="2d289-172">フレーム</span><span class="sxs-lookup"><span data-stu-id="2d289-172">frame</span></span> | [<span data-ttu-id="2d289-173">フレーム</span><span class="sxs-lookup"><span data-stu-id="2d289-173">Frame</span></span>](#frame) | <span data-ttu-id="2d289-174">Frame オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2d289-174">Frame object.</span></span> |  

---  

### <a name="loadeventfired"></a><span data-ttu-id="2d289-175">loadEventFired</span><span class="sxs-lookup"><span data-stu-id="2d289-175">loadEventFired</span></span>  

<span data-ttu-id="2d289-176">イベントに対応 `window.onload` します。</span><span class="sxs-lookup"><span data-stu-id="2d289-176">Corresponds to the `window.onload` event.</span></span>  

| <span data-ttu-id="2d289-177">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d289-177">Parameters</span></span> | <span data-ttu-id="2d289-178">型</span><span class="sxs-lookup"><span data-stu-id="2d289-178">Type</span></span> | <span data-ttu-id="2d289-179">詳細</span><span class="sxs-lookup"><span data-stu-id="2d289-179">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="2d289-180">タイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="2d289-180">timestamp</span></span> | `number` | <span data-ttu-id="2d289-181">エポックからのミリ秒単位。</span><span class="sxs-lookup"><span data-stu-id="2d289-181">Number of milliseconds since epoch.</span></span> |  

---  

### <a name="domcontenteventfired"></a><span data-ttu-id="2d289-182">domContentEventFired</span><span class="sxs-lookup"><span data-stu-id="2d289-182">domContentEventFired</span></span>  

<span data-ttu-id="2d289-183">イベントに対応 `document.onDOMContentLoaded` します。</span><span class="sxs-lookup"><span data-stu-id="2d289-183">Corresponds to the `document.onDOMContentLoaded` event.</span></span>  

| <span data-ttu-id="2d289-184">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d289-184">Parameters</span></span> | <span data-ttu-id="2d289-185">型</span><span class="sxs-lookup"><span data-stu-id="2d289-185">Type</span></span> | <span data-ttu-id="2d289-186">詳細</span><span class="sxs-lookup"><span data-stu-id="2d289-186">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="2d289-187">タイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="2d289-187">timestamp</span></span> | `number` | <span data-ttu-id="2d289-188">エポックからのミリ秒単位。</span><span class="sxs-lookup"><span data-stu-id="2d289-188">Number of milliseconds since epoch.</span></span> |  

---  

## <a name="types"></a><span data-ttu-id="2d289-189">型</span><span class="sxs-lookup"><span data-stu-id="2d289-189">Types</span></span>  

### <a name="frameid-string"></a><span data-ttu-id="2d289-190">FrameId 文字列</span><span class="sxs-lookup"><span data-stu-id="2d289-190">FrameId string</span></span>  

<a name="frameid"></a>  

<span data-ttu-id="2d289-191">一意のフレーム識別子。</span><span class="sxs-lookup"><span data-stu-id="2d289-191">Unique frame identifier.</span></span>  

&nbsp;  

---  

### <a name="frame-object"></a><span data-ttu-id="2d289-192">Frame オブジェクト</span><span class="sxs-lookup"><span data-stu-id="2d289-192">Frame object</span></span>  

<a name="frame"></a>  

<span data-ttu-id="2d289-193">ページのフレームに関する情報。</span><span class="sxs-lookup"><span data-stu-id="2d289-193">Information about the Frame on the Page.</span></span>  

| <span data-ttu-id="2d289-194">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2d289-194">Properties</span></span> | <span data-ttu-id="2d289-195">型</span><span class="sxs-lookup"><span data-stu-id="2d289-195">Type</span></span> | <span data-ttu-id="2d289-196">詳細</span><span class="sxs-lookup"><span data-stu-id="2d289-196">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="2d289-197">id</span><span class="sxs-lookup"><span data-stu-id="2d289-197">id</span></span> | [<span data-ttu-id="2d289-198">FrameId</span><span class="sxs-lookup"><span data-stu-id="2d289-198">FrameId</span></span>](#frameid) | <span data-ttu-id="2d289-199">フレームの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="2d289-199">Frame unique identifier.</span></span> |  
| <span data-ttu-id="2d289-200">parentId \(optional\)</span><span class="sxs-lookup"><span data-stu-id="2d289-200">parentId \(optional\)</span></span> | [<span data-ttu-id="2d289-201">FrameId</span><span class="sxs-lookup"><span data-stu-id="2d289-201">FrameId</span></span>](#frameid) | <span data-ttu-id="2d289-202">親フレームの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="2d289-202">Parent frame unique identifier.</span></span> |  
| <span data-ttu-id="2d289-203">name \(optional\)</span><span class="sxs-lookup"><span data-stu-id="2d289-203">name \(optional\)</span></span> | `string` | <span data-ttu-id="2d289-204">タグで指定されているフレームの名前。</span><span class="sxs-lookup"><span data-stu-id="2d289-204">Frame's name as specified in the tag.</span></span> |  
| <span data-ttu-id="2d289-205">url</span><span class="sxs-lookup"><span data-stu-id="2d289-205">url</span></span> | `string` | <span data-ttu-id="2d289-206">フレーム ドキュメントの URL。</span><span class="sxs-lookup"><span data-stu-id="2d289-206">Frame document's URL.</span></span> |  
| <span data-ttu-id="2d289-207">securityOrigin</span><span class="sxs-lookup"><span data-stu-id="2d289-207">securityOrigin</span></span> | `string` | <span data-ttu-id="2d289-208">フレーム ドキュメントのセキュリティの発生元。</span><span class="sxs-lookup"><span data-stu-id="2d289-208">Frame document's security origin.</span></span> |  
| <span data-ttu-id="2d289-209">mimeType</span><span class="sxs-lookup"><span data-stu-id="2d289-209">mimeType</span></span> | `string` | <span data-ttu-id="2d289-210">ブラウザーによって決定されるドキュメントの mimeType をフレームします。</span><span class="sxs-lookup"><span data-stu-id="2d289-210">Frame document's mimeType as determined by the browser.</span></span> |  

---  

### <a name="frametree-object"></a><span data-ttu-id="2d289-211">FrameTree オブジェクト</span><span class="sxs-lookup"><span data-stu-id="2d289-211">FrameTree object</span></span>  

<a name="frametree"></a>  

<span data-ttu-id="2d289-212">フレーム階層に関する情報。</span><span class="sxs-lookup"><span data-stu-id="2d289-212">Information about the Frame hierarchy.</span></span>  

| <span data-ttu-id="2d289-213">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2d289-213">Properties</span></span> | <span data-ttu-id="2d289-214">型</span><span class="sxs-lookup"><span data-stu-id="2d289-214">Type</span></span> | <span data-ttu-id="2d289-215">詳細</span><span class="sxs-lookup"><span data-stu-id="2d289-215">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="2d289-216">フレーム</span><span class="sxs-lookup"><span data-stu-id="2d289-216">frame</span></span> | [<span data-ttu-id="2d289-217">フレーム</span><span class="sxs-lookup"><span data-stu-id="2d289-217">Frame</span></span>](#frame) | <span data-ttu-id="2d289-218">このツリー アイテムのフレーム情報。</span><span class="sxs-lookup"><span data-stu-id="2d289-218">Frame information for this tree item.</span></span> |  
| <span data-ttu-id="2d289-219">childFrames \(optional\)</span><span class="sxs-lookup"><span data-stu-id="2d289-219">childFrames \(optional\)</span></span> | [<span data-ttu-id="2d289-220">FrameTree[]</span><span class="sxs-lookup"><span data-stu-id="2d289-220">FrameTree[]</span></span>](#frametree) | <span data-ttu-id="2d289-221">子フレーム。</span><span class="sxs-lookup"><span data-stu-id="2d289-221">Child frames.</span></span> |  

---  
