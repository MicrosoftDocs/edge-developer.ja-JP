---
description: タイムライン イベント モードでは、録音中にトリガーされたイベントすべてが表示されます。  タイムライン イベントの各種類の詳細については、タイムライン イベント参照を使用します。
title: Timeline イベントリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 2a166c9eebc980682fa872e5ee8d213f2058b384
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398666"
---
<!-- Copyright Meggin Kearney and Flavio Copes

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# <a name="timeline-event-reference"></a><span data-ttu-id="51b5e-105">Timeline イベントリファレンス</span><span class="sxs-lookup"><span data-stu-id="51b5e-105">Timeline Event reference</span></span>  

<span data-ttu-id="51b5e-106">タイムライン イベント モードでは、録音中にトリガーされたイベントすべてが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51b5e-106">The timeline events mode displays all events triggered while making a recording.</span></span>  <span data-ttu-id="51b5e-107">タイムライン イベントの各種類の詳細については、タイムライン イベント参照を使用します。</span><span class="sxs-lookup"><span data-stu-id="51b5e-107">Use the timeline event reference to learn more about each timeline event type.</span></span>  

## <a name="common-timeline-event-properties"></a><span data-ttu-id="51b5e-108">一般的なタイムライン イベントのプロパティ</span><span class="sxs-lookup"><span data-stu-id="51b5e-108">Common timeline event properties</span></span>  

<span data-ttu-id="51b5e-109">特定の詳細は、すべての種類のイベントに存在しますが、一部のイベントは特定のイベントの種類にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="51b5e-109">Certain details are present in events of all types, while some only apply to certain event types.</span></span>  <span data-ttu-id="51b5e-110">このセクションでは、さまざまなイベントの種類に共通するプロパティの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="51b5e-110">This section lists properties common to different event types.</span></span>  <span data-ttu-id="51b5e-111">特定のイベントの種類に固有のプロパティは、その後に続くイベントの種類の参照に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="51b5e-111">Properties specific to certain event types are listed in the references for those event types that follow.</span></span>  

| <span data-ttu-id="51b5e-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="51b5e-112">Property</span></span> | <span data-ttu-id="51b5e-113">いつ表示されるか</span><span class="sxs-lookup"><span data-stu-id="51b5e-113">When is it shown</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="51b5e-114">集計時間</span><span class="sxs-lookup"><span data-stu-id="51b5e-114">Aggregated time</span></span> | <span data-ttu-id="51b5e-115">入れ子になった **イベントの場合**、イベントの各カテゴリによって取られる時間。</span><span class="sxs-lookup"><span data-stu-id="51b5e-115">For events with **nested events**, the time taken by each category of events.</span></span> |  
| <span data-ttu-id="51b5e-116">呼び出し履歴</span><span class="sxs-lookup"><span data-stu-id="51b5e-116">Call Stack</span></span> | <span data-ttu-id="51b5e-117">子イベントを **持つイベントの**場合、イベントの各カテゴリによって取られた時間。</span><span class="sxs-lookup"><span data-stu-id="51b5e-117">For events with **child events**, the time taken by each category of events.</span></span> |  
| <span data-ttu-id="51b5e-118">CPU 時間</span><span class="sxs-lookup"><span data-stu-id="51b5e-118">CPU time</span></span> | <span data-ttu-id="51b5e-119">記録されたイベントにかかった CPU 時間。</span><span class="sxs-lookup"><span data-stu-id="51b5e-119">How much CPU time the recorded event took.</span></span> |  
| <span data-ttu-id="51b5e-120">詳細</span><span class="sxs-lookup"><span data-stu-id="51b5e-120">Details</span></span> | <span data-ttu-id="51b5e-121">イベントに関するその他の詳細。</span><span class="sxs-lookup"><span data-stu-id="51b5e-121">Other details about the event.</span></span> |  
| <span data-ttu-id="51b5e-122">Duration \(at time-stamp\)</span><span class="sxs-lookup"><span data-stu-id="51b5e-122">Duration \(at time-stamp\)</span></span> | <span data-ttu-id="51b5e-123">すべての子が完了するためにイベントにかかった時間。タイムスタンプは、イベントが発生した時刻で、記録が開始された時刻を基準として指定します。</span><span class="sxs-lookup"><span data-stu-id="51b5e-123">How long it took the event with all of its children to complete; timestamp is the time at which the event occurred, relative to when the recording started.</span></span> |  
| <span data-ttu-id="51b5e-124">自己時間</span><span class="sxs-lookup"><span data-stu-id="51b5e-124">Self time</span></span> | <span data-ttu-id="51b5e-125">子がいなくてもイベントにかかった時間。</span><span class="sxs-lookup"><span data-stu-id="51b5e-125">How long the event took without any of its children.</span></span> |  
| <span data-ttu-id="51b5e-126">使用ヒープ サイズ</span><span class="sxs-lookup"><span data-stu-id="51b5e-126">Used Heap Size</span></span> | <span data-ttu-id="51b5e-127">イベントの記録時にアプリケーションで使用されるメモリの量と、前回のサンプリング以降の使用ヒープ サイズのデルタ \(+/-\) の変化。</span><span class="sxs-lookup"><span data-stu-id="51b5e-127">Amount of memory being used by the application when the event was recorded, and the delta \(+/-\) change in used heap size since the last sampling.</span></span> |  

<!--todo: add nested and child events (timelinetool) section when available -->  

## <a name="loading-events"></a><span data-ttu-id="51b5e-128">イベントの読み込み</span><span class="sxs-lookup"><span data-stu-id="51b5e-128">Loading events</span></span>  

<span data-ttu-id="51b5e-129">このセクションでは、読み込みカテゴリとそのプロパティに属するイベントの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="51b5e-129">This section lists events that belong to Loading category and their properties.</span></span>  

| <span data-ttu-id="51b5e-130">イベント</span><span class="sxs-lookup"><span data-stu-id="51b5e-130">Event</span></span> | <span data-ttu-id="51b5e-131">説明</span><span class="sxs-lookup"><span data-stu-id="51b5e-131">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="51b5e-132">HTML の解析</span><span class="sxs-lookup"><span data-stu-id="51b5e-132">Parse HTML</span></span> |  <span data-ttu-id="51b5e-133">Microsoft Edge は HTML 解析アルゴリズムを実行しました。</span><span class="sxs-lookup"><span data-stu-id="51b5e-133">Microsoft Edge ran the HTML parsing algorithm.</span></span> |  
| <span data-ttu-id="51b5e-134">読み込みを完了する</span><span class="sxs-lookup"><span data-stu-id="51b5e-134">Finish Loading</span></span> |  <span data-ttu-id="51b5e-135">ネットワーク要求が完了しました。</span><span class="sxs-lookup"><span data-stu-id="51b5e-135">A network request completed.</span></span> |  
| <span data-ttu-id="51b5e-136">データの受信</span><span class="sxs-lookup"><span data-stu-id="51b5e-136">Receive Data</span></span> |  <span data-ttu-id="51b5e-137">要求のデータが受信された。</span><span class="sxs-lookup"><span data-stu-id="51b5e-137">Data for a request was received.</span></span>  <span data-ttu-id="51b5e-138">1 つ以上の受信データ イベントがあります。</span><span class="sxs-lookup"><span data-stu-id="51b5e-138">There are one or more Receive Data events.</span></span> |  
| <span data-ttu-id="51b5e-139">応答の受信</span><span class="sxs-lookup"><span data-stu-id="51b5e-139">Receive Response</span></span> |  <span data-ttu-id="51b5e-140">要求からの最初の HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="51b5e-140">The initial HTTP response from a request.</span></span> |  
| <span data-ttu-id="51b5e-141">要求の送信</span><span class="sxs-lookup"><span data-stu-id="51b5e-141">Send Request</span></span> |  <span data-ttu-id="51b5e-142">ネットワーク要求が送信されました。</span><span class="sxs-lookup"><span data-stu-id="51b5e-142">A network request has been sent.</span></span> |  

### <a name="loading-event-properties"></a><span data-ttu-id="51b5e-143">イベント プロパティの読み込み</span><span class="sxs-lookup"><span data-stu-id="51b5e-143">Loading event properties</span></span>  

| <span data-ttu-id="51b5e-144">プロパティ</span><span class="sxs-lookup"><span data-stu-id="51b5e-144">Property</span></span> | <span data-ttu-id="51b5e-145">説明</span><span class="sxs-lookup"><span data-stu-id="51b5e-145">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="51b5e-146">リソース</span><span class="sxs-lookup"><span data-stu-id="51b5e-146">Resource</span></span> | <span data-ttu-id="51b5e-147">要求されたリソースの URL。</span><span class="sxs-lookup"><span data-stu-id="51b5e-147">The URL of the requested resource.</span></span> |  
| <span data-ttu-id="51b5e-148">Preview</span><span class="sxs-lookup"><span data-stu-id="51b5e-148">Preview</span></span> | <span data-ttu-id="51b5e-149">要求されたリソース \(images only\) のプレビュー。</span><span class="sxs-lookup"><span data-stu-id="51b5e-149">Preview of the requested resource \(images only\).</span></span> |  
| <span data-ttu-id="51b5e-150">Request メソッド</span><span class="sxs-lookup"><span data-stu-id="51b5e-150">Request Method</span></span> | <span data-ttu-id="51b5e-151">要求 \( または 、 `GET` たとえば `POST` \) に使用される HTTP メソッド。</span><span class="sxs-lookup"><span data-stu-id="51b5e-151">HTTP method used for the request \(`GET` or `POST`, for example\).</span></span> |  
| <span data-ttu-id="51b5e-152">ステータス コード</span><span class="sxs-lookup"><span data-stu-id="51b5e-152">Status Code</span></span> | <span data-ttu-id="51b5e-153">HTTP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="51b5e-153">HTTP response code.</span></span> |  
| <span data-ttu-id="51b5e-154">MIME の種類</span><span class="sxs-lookup"><span data-stu-id="51b5e-154">MIME Type</span></span> | <span data-ttu-id="51b5e-155">要求されたリソースの MIME の種類。</span><span class="sxs-lookup"><span data-stu-id="51b5e-155">MIME type of the requested resource.</span></span> |  
| <span data-ttu-id="51b5e-156">エンコードされたデータの長さ</span><span class="sxs-lookup"><span data-stu-id="51b5e-156">Encoded Data Length</span></span> | <span data-ttu-id="51b5e-157">要求されたリソースの長さ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="51b5e-157">Length of requested resource in bytes.</span></span> |  

## <a name="scripting-events"></a><span data-ttu-id="51b5e-158">スクリプト イベント</span><span class="sxs-lookup"><span data-stu-id="51b5e-158">Scripting events</span></span>  

<span data-ttu-id="51b5e-159">このセクションでは、Scripting カテゴリとそのプロパティに属するイベントの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="51b5e-159">This section lists events that belong to the Scripting category and their properties.</span></span>  

| <span data-ttu-id="51b5e-160">イベント</span><span class="sxs-lookup"><span data-stu-id="51b5e-160">Event</span></span> | <span data-ttu-id="51b5e-161">説明</span><span class="sxs-lookup"><span data-stu-id="51b5e-161">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="51b5e-162">アニメーション フレームの作成</span><span class="sxs-lookup"><span data-stu-id="51b5e-162">Animation Frame Fired</span></span> | <span data-ttu-id="51b5e-163">スケジュールされたアニメーション フレームが起動され、コールバック ハンドラーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="51b5e-163">A scheduled animation frame fired, and its callback handler invoked.</span></span> |  
| <span data-ttu-id="51b5e-164">アニメーション フレームの取り消し</span><span class="sxs-lookup"><span data-stu-id="51b5e-164">Cancel Animation Frame</span></span> |  <span data-ttu-id="51b5e-165">スケジュールされたアニメーション フレームが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="51b5e-165">A scheduled animation frame was canceled.</span></span> |  
| <span data-ttu-id="51b5e-166">GC イベント</span><span class="sxs-lookup"><span data-stu-id="51b5e-166">GC Event</span></span> |  <span data-ttu-id="51b5e-167">ガベージ コレクションが発生しました。</span><span class="sxs-lookup"><span data-stu-id="51b5e-167">Garbage collection occurred.</span></span> |  
| <span data-ttu-id="51b5e-168">DOMContentLoaded</span><span class="sxs-lookup"><span data-stu-id="51b5e-168">DOMContentLoaded</span></span> |  <span data-ttu-id="51b5e-169">[DOMContentLoaded イベントは][MDNWindowDOMContentLoadedEvent]ブラウザーによって発生しました。</span><span class="sxs-lookup"><span data-stu-id="51b5e-169">The [DOMContentLoaded event][MDNWindowDOMContentLoadedEvent] was fired by the browser.</span></span>  <span data-ttu-id="51b5e-170">このイベントは、ページのすべての DOM コンテンツが読み込まれ、解析されると発生します。</span><span class="sxs-lookup"><span data-stu-id="51b5e-170">This event is fired when all of the DOM content of the page is loaded and parsed.</span></span> |  
| <span data-ttu-id="51b5e-171">スクリプトの評価</span><span class="sxs-lookup"><span data-stu-id="51b5e-171">Evaluate Script</span></span> | <span data-ttu-id="51b5e-172">スクリプトが評価されました。</span><span class="sxs-lookup"><span data-stu-id="51b5e-172">A script was evaluated.</span></span> |  
| <span data-ttu-id="51b5e-173">イベント</span><span class="sxs-lookup"><span data-stu-id="51b5e-173">Event</span></span> | <span data-ttu-id="51b5e-174">JavaScript イベント \(たとえば `mousedown` `key` 、、\)。</span><span class="sxs-lookup"><span data-stu-id="51b5e-174">A JavaScript event \(for example, `mousedown`, or `key`\).</span></span> |  
| <span data-ttu-id="51b5e-175">関数呼び出し</span><span class="sxs-lookup"><span data-stu-id="51b5e-175">Function Call</span></span> | <span data-ttu-id="51b5e-176">トップ レベルの JavaScript 関数呼び出しが行われた \(ブラウザーが JavaScript エンジン\に入った場合にのみ表示されます)。</span><span class="sxs-lookup"><span data-stu-id="51b5e-176">A top-level JavaScript function call was made \(only appears when browser enters JavaScript engine\).</span></span> |  
| <span data-ttu-id="51b5e-177">インストール タイマー</span><span class="sxs-lookup"><span data-stu-id="51b5e-177">Install Timer</span></span> | <span data-ttu-id="51b5e-178">[setInterval() または setTimeout() を][MDNWindowOrWorkerGlobalScopeSetInterval]使用[してタイマーが作成されました][MDNWindowOrWorkerGlobalScopeSetTimeout]。</span><span class="sxs-lookup"><span data-stu-id="51b5e-178">A timer was created with [setInterval()][MDNWindowOrWorkerGlobalScopeSetInterval] or [setTimeout()][MDNWindowOrWorkerGlobalScopeSetTimeout].</span></span> |  
| <span data-ttu-id="51b5e-179">アニメーション フレームの要求</span><span class="sxs-lookup"><span data-stu-id="51b5e-179">Request Animation Frame</span></span> | <span data-ttu-id="51b5e-180">新 `requestAnimationFrame()` しいフレームをスケジュールした呼び出し。</span><span class="sxs-lookup"><span data-stu-id="51b5e-180">A `requestAnimationFrame()` call scheduled a new frame.</span></span> |  
| <span data-ttu-id="51b5e-181">タイマーの削除</span><span class="sxs-lookup"><span data-stu-id="51b5e-181">Remove Timer</span></span> | <span data-ttu-id="51b5e-182">以前に作成したタイマーがクリアされました。</span><span class="sxs-lookup"><span data-stu-id="51b5e-182">A previously created timer was cleared.</span></span> |  
| <span data-ttu-id="51b5e-183">時間</span><span class="sxs-lookup"><span data-stu-id="51b5e-183">Time</span></span> |  <span data-ttu-id="51b5e-184">[console.time() というスクリプト][ConsoleApiTime]。</span><span class="sxs-lookup"><span data-stu-id="51b5e-184">A script called [console.time()][ConsoleApiTime].</span></span> |  
| <span data-ttu-id="51b5e-185">タイム エンド</span><span class="sxs-lookup"><span data-stu-id="51b5e-185">Time End</span></span> | <span data-ttu-id="51b5e-186">[console.timeEnd()][ConsoleApiTimeEnd]というスクリプト。</span><span class="sxs-lookup"><span data-stu-id="51b5e-186">A script called [console.timeEnd()][ConsoleApiTimeEnd].</span></span> |  
| <span data-ttu-id="51b5e-187">タイマーの発生</span><span class="sxs-lookup"><span data-stu-id="51b5e-187">Timer Fired</span></span> | <span data-ttu-id="51b5e-188">またはでスケジュールされたタイマーが `setInterval()` 発生 `setTimeout()` しました。</span><span class="sxs-lookup"><span data-stu-id="51b5e-188">A timer fired that was scheduled with `setInterval()` or `setTimeout()`.</span></span> |  
| <span data-ttu-id="51b5e-189">XHR Ready State Change</span><span class="sxs-lookup"><span data-stu-id="51b5e-189">XHR Ready State Change</span></span> | <span data-ttu-id="51b5e-190">XMLHTTPRequest の準備状態が変更されました。</span><span class="sxs-lookup"><span data-stu-id="51b5e-190">The ready state of an XMLHTTPRequest changed.</span></span> |  
| <span data-ttu-id="51b5e-191">XHR の読み込み</span><span class="sxs-lookup"><span data-stu-id="51b5e-191">XHR Load</span></span> | <span data-ttu-id="51b5e-192">読 `XMLHTTPRequest` み込みが完了しました。</span><span class="sxs-lookup"><span data-stu-id="51b5e-192">An `XMLHTTPRequest` finished loading.</span></span> |  

### <a name="scripting-event-properties"></a><span data-ttu-id="51b5e-193">スクリプト イベントのプロパティ</span><span class="sxs-lookup"><span data-stu-id="51b5e-193">Scripting event properties</span></span>  

| <span data-ttu-id="51b5e-194">プロパティ</span><span class="sxs-lookup"><span data-stu-id="51b5e-194">Property</span></span> | <span data-ttu-id="51b5e-195">説明</span><span class="sxs-lookup"><span data-stu-id="51b5e-195">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="51b5e-196">タイマー ID</span><span class="sxs-lookup"><span data-stu-id="51b5e-196">Timer ID</span></span> | <span data-ttu-id="51b5e-197">タイマー ID。</span><span class="sxs-lookup"><span data-stu-id="51b5e-197">The timer ID.</span></span> |  
| <span data-ttu-id="51b5e-198">タイムアウト</span><span class="sxs-lookup"><span data-stu-id="51b5e-198">Timeout</span></span> | <span data-ttu-id="51b5e-199">タイマーで指定されたタイムアウト。</span><span class="sxs-lookup"><span data-stu-id="51b5e-199">The timeout specified by the timer.</span></span> |  
| <span data-ttu-id="51b5e-200">繰り返し</span><span class="sxs-lookup"><span data-stu-id="51b5e-200">Repeats</span></span> | <span data-ttu-id="51b5e-201">タイマーが繰り返される場合を指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="51b5e-201">Boolean that specifies if the timer repeats.</span></span> |  
| <span data-ttu-id="51b5e-202">関数呼び出し</span><span class="sxs-lookup"><span data-stu-id="51b5e-202">Function Call</span></span> | <span data-ttu-id="51b5e-203">呼び出された関数。</span><span class="sxs-lookup"><span data-stu-id="51b5e-203">A function that was invoked.</span></span> |  

## <a name="rendering-events"></a><span data-ttu-id="51b5e-204">レンダリング イベント</span><span class="sxs-lookup"><span data-stu-id="51b5e-204">Rendering events</span></span>  

<span data-ttu-id="51b5e-205">このセクションでは、レンダリング カテゴリとそのプロパティに属するイベントの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="51b5e-205">This section lists events that belong to Rendering category and their properties.</span></span>  

| <span data-ttu-id="51b5e-206">イベント</span><span class="sxs-lookup"><span data-stu-id="51b5e-206">Event</span></span> | <span data-ttu-id="51b5e-207">説明</span><span class="sxs-lookup"><span data-stu-id="51b5e-207">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="51b5e-208">レイアウトを無効にする</span><span class="sxs-lookup"><span data-stu-id="51b5e-208">Invalidate layout</span></span> | <span data-ttu-id="51b5e-209">DOM の変更によってページ レイアウトが無効にされました。</span><span class="sxs-lookup"><span data-stu-id="51b5e-209">The page layout was invalidated by a DOM change.</span></span> |  
| <span data-ttu-id="51b5e-210">レイアウト</span><span class="sxs-lookup"><span data-stu-id="51b5e-210">Layout</span></span> | <span data-ttu-id="51b5e-211">ページ レイアウトが完了しました。</span><span class="sxs-lookup"><span data-stu-id="51b5e-211">A page layout was completed.</span></span> |  
| <span data-ttu-id="51b5e-212">スタイルの再計算</span><span class="sxs-lookup"><span data-stu-id="51b5e-212">Recalculate style</span></span> | <span data-ttu-id="51b5e-213">Microsoft Edge で再計算された要素のスタイル。</span><span class="sxs-lookup"><span data-stu-id="51b5e-213">Microsoft Edge recalculated element styles.</span></span> |  
| <span data-ttu-id="51b5e-214">Scroll</span><span class="sxs-lookup"><span data-stu-id="51b5e-214">Scroll</span></span> | <span data-ttu-id="51b5e-215">入れ子になったビューの内容がスクロールされました。</span><span class="sxs-lookup"><span data-stu-id="51b5e-215">The content of nested view was scrolled.</span></span> |  

### <a name="rendering-event-properties"></a><span data-ttu-id="51b5e-216">レンダリング イベントのプロパティ</span><span class="sxs-lookup"><span data-stu-id="51b5e-216">Rendering event properties</span></span>  

| <span data-ttu-id="51b5e-217">プロパティ</span><span class="sxs-lookup"><span data-stu-id="51b5e-217">Property</span></span> | <span data-ttu-id="51b5e-218">説明</span><span class="sxs-lookup"><span data-stu-id="51b5e-218">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="51b5e-219">レイアウトが無効</span><span class="sxs-lookup"><span data-stu-id="51b5e-219">Layout invalidated</span></span> | <span data-ttu-id="51b5e-220">Layout レコードの場合、レイアウトを無効にしたコードのスタック トレース。</span><span class="sxs-lookup"><span data-stu-id="51b5e-220">For Layout records, the stack trace of the code that caused the layout to be invalidated.</span></span> |  
| <span data-ttu-id="51b5e-221">レイアウトが必要なノード</span><span class="sxs-lookup"><span data-stu-id="51b5e-221">Nodes that need layout</span></span> | <span data-ttu-id="51b5e-222">Layout レコードの場合、リレーアウトが開始される前に必要なレイアウトとしてマークされたノードの数。</span><span class="sxs-lookup"><span data-stu-id="51b5e-222">For Layout records, the number of nodes that were marked as needing layout before the relayout started.</span></span>  <span data-ttu-id="51b5e-223">これらは通常、開発者コードによって無効にされたノードと、ルートを中継する上方向のパスです。</span><span class="sxs-lookup"><span data-stu-id="51b5e-223">These are normally those nodes that were invalidated by developer code, plus a path upward to relayout root.</span></span> |  
| <span data-ttu-id="51b5e-224">レイアウト ツリーのサイズ</span><span class="sxs-lookup"><span data-stu-id="51b5e-224">Layout tree size</span></span> | <span data-ttu-id="51b5e-225">Layout レコードの場合、リレーアウト ルート \(Microsoft Edge が relayout\を開始するノード) の下のノードの総数。</span><span class="sxs-lookup"><span data-stu-id="51b5e-225">For Layout records, the total number of nodes under the relayout root \(the node that Microsoft Edge starts the relayout\).</span></span> |  
| <span data-ttu-id="51b5e-226">レイアウト スコープ</span><span class="sxs-lookup"><span data-stu-id="51b5e-226">Layout scope</span></span> | <span data-ttu-id="51b5e-227">可能な値 `Partial` は \(再レイアウト境界は DOM\の一部) または `Whole document` です。</span><span class="sxs-lookup"><span data-stu-id="51b5e-227">Possible values are `Partial` \(the re-layout boundary is a portion of the DOM\) or `Whole document`.</span></span> |  
| <span data-ttu-id="51b5e-228">影響を受ける要素</span><span class="sxs-lookup"><span data-stu-id="51b5e-228">Elements affected</span></span> | <span data-ttu-id="51b5e-229">[スタイル レコードの再計算] では、スタイル再計算の影響を受ける要素の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="51b5e-229">For Recalculate style records, the number of elements affected by a style recalculation.</span></span> |  
| <span data-ttu-id="51b5e-230">スタイルが無効</span><span class="sxs-lookup"><span data-stu-id="51b5e-230">Styles invalidated</span></span> | <span data-ttu-id="51b5e-231">[スタイル レコードの再計算] では、スタイルが無効になる原因となるコードのスタック トレースを提供します。</span><span class="sxs-lookup"><span data-stu-id="51b5e-231">For Recalculate style records, provides the stack trace of the code that caused the style invalidation.</span></span> |  

## <a name="painting-events"></a><span data-ttu-id="51b5e-232">ペイント イベント</span><span class="sxs-lookup"><span data-stu-id="51b5e-232">Painting events</span></span>  

<span data-ttu-id="51b5e-233">このセクションでは、Painting カテゴリとそのプロパティに属するイベントの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="51b5e-233">This section lists events that belong to Painting category and their properties.</span></span>  

| <span data-ttu-id="51b5e-234">イベント</span><span class="sxs-lookup"><span data-stu-id="51b5e-234">Event</span></span> | <span data-ttu-id="51b5e-235">説明</span><span class="sxs-lookup"><span data-stu-id="51b5e-235">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="51b5e-236">コンポジット レイヤー</span><span class="sxs-lookup"><span data-stu-id="51b5e-236">Composite Layers</span></span> | <span data-ttu-id="51b5e-237">Microsoft Edge レンダリング エンジンの合成イメージ レイヤー。</span><span class="sxs-lookup"><span data-stu-id="51b5e-237">The composited image layers for the Microsoft Edge rendering engine.</span></span> |  
| <span data-ttu-id="51b5e-238">画像デコード</span><span class="sxs-lookup"><span data-stu-id="51b5e-238">Image Decode</span></span> | <span data-ttu-id="51b5e-239">イメージ リソースがデコードされました。</span><span class="sxs-lookup"><span data-stu-id="51b5e-239">An image resource was decoded.</span></span> |  
| <span data-ttu-id="51b5e-240">イメージのサイズ変更</span><span class="sxs-lookup"><span data-stu-id="51b5e-240">Image Resize</span></span> | <span data-ttu-id="51b5e-241">イメージのサイズは、ネイティブディメンションから変更されました。</span><span class="sxs-lookup"><span data-stu-id="51b5e-241">An image was resized from its native dimensions.</span></span> |  
| <span data-ttu-id="51b5e-242">ペイント</span><span class="sxs-lookup"><span data-stu-id="51b5e-242">Paint</span></span> | <span data-ttu-id="51b5e-243">合成されたレイヤーは、ディスプレイの領域にペイントされました。</span><span class="sxs-lookup"><span data-stu-id="51b5e-243">Composited layers were painted to a region of the display.</span></span>  <span data-ttu-id="51b5e-244">Paint レコードの上にカーソルを置くと、更新された表示領域が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="51b5e-244">Hovering over a Paint record highlights the region of the display that was updated.</span></span> |  

### <a name="painting-event-properties"></a><span data-ttu-id="51b5e-245">イベントプロパティのペイント</span><span class="sxs-lookup"><span data-stu-id="51b5e-245">Painting event properties</span></span>  

| <span data-ttu-id="51b5e-246">プロパティ</span><span class="sxs-lookup"><span data-stu-id="51b5e-246">Property</span></span> | <span data-ttu-id="51b5e-247">説明</span><span class="sxs-lookup"><span data-stu-id="51b5e-247">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="51b5e-248">場所</span><span class="sxs-lookup"><span data-stu-id="51b5e-248">Location</span></span> | <span data-ttu-id="51b5e-249">Paint イベントの場合、ペイント四角形の x 座標と y 座標。</span><span class="sxs-lookup"><span data-stu-id="51b5e-249">For Paint events, the x and y coordinates of the paint rectangle.</span></span> |  
| <span data-ttu-id="51b5e-250">ディメンション</span><span class="sxs-lookup"><span data-stu-id="51b5e-250">Dimensions</span></span> | <span data-ttu-id="51b5e-251">Paint イベントの場合、ペイントされた領域の高さと幅。</span><span class="sxs-lookup"><span data-stu-id="51b5e-251">For Paint events, the height and width of the painted region.</span></span> |  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="51b5e-252">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="51b5e-252">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->

[ConsoleApiTime]: /microsoft-edge/devtools-guide-chromium/console/api#time "time - コンソール API リファレンス"  
[ConsoleApiTimeEnd]: /microsoft-edge/devtools-guide-chromium/console/api#timeend "timeEnd - コンソール API リファレンス"  
<!--[EvaluatePerformanceTimelineTool]: timeline-tool "How to Use the Timeline Tool"  -->

[MDNWindowDOMContentLoadedEvent]: https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded "ウィンドウ: DOMContentLoaded イベント |MDN"  
[MDNWindowOrWorkerGlobalScopeSetInterval]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setInterval "WindowOrWorkerGlobalScope.setInterval() |MDN"  
[MDNWindowOrWorkerGlobalScopeSetTimeout]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setTimeout "WindowOrWorkerGlobalScope.setTimeout() |MDN"  

> [!NOTE]
> <span data-ttu-id="51b5e-258">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="51b5e-258">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="51b5e-259">元のページ [はここで見](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/performance-reference) つかり [、Meggin Kearney][MegginKearney] \(Tech Writer\) と [Flavio Copes \(Full Stack][FlavioCopes] Developer\) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="51b5e-259">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/performance-reference) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Flavio Copes][FlavioCopes] \(Full Stack Developer\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="51b5e-261">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="51b5e-261">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[FlavioCopes]: https://developers.google.com/web/resources/contributors/flaviocopes  
