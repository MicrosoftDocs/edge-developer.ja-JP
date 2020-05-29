---
title: タイムラインイベントのリファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: e5f0807204877ce034fd52ea4535795ea80ba394
ms.sourcegitcommit: 50991a04c18283a8890ae33fcc3491c0476c7684
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611721"
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





# <span data-ttu-id="264ce-103">タイムラインイベントのリファレンス</span><span class="sxs-lookup"><span data-stu-id="264ce-103">Timeline Event Reference</span></span>   




<span data-ttu-id="264ce-104">タイムラインイベントモードでは、記録を作成するときにトリガーされるすべてのイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="264ce-104">The timeline events mode displays all events triggered while making a recording.</span></span>  <span data-ttu-id="264ce-105">タイムラインイベントのリファレンスを使って、各タイムラインイベントの種類について詳しく知ることができます。</span><span class="sxs-lookup"><span data-stu-id="264ce-105">Use the timeline event reference to learn more about each timeline event type.</span></span>  

## <span data-ttu-id="264ce-106">一般的なタイムラインイベントプロパティ</span><span class="sxs-lookup"><span data-stu-id="264ce-106">Common timeline event properties</span></span>  

<span data-ttu-id="264ce-107">一部の詳細は、すべての種類のイベントに存在しますが、一部のイベントの種類にしか適用されません。</span><span class="sxs-lookup"><span data-stu-id="264ce-107">Certain details are present in events of all types, while some only apply to certain event types.</span></span>  <span data-ttu-id="264ce-108">このセクションでは、さまざまなイベントの種類に共通するプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="264ce-108">This section lists properties common to different event types.</span></span>  <span data-ttu-id="264ce-109">特定のイベントの種類に固有のプロパティについては、次に示すイベントの種類に関する参照で示されています。</span><span class="sxs-lookup"><span data-stu-id="264ce-109">Properties specific to certain event types are listed in the references for those event types that follow.</span></span>  

| <span data-ttu-id="264ce-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="264ce-110">Property</span></span> | <span data-ttu-id="264ce-111">表示されるタイミング</span><span class="sxs-lookup"><span data-stu-id="264ce-111">When is it shown</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="264ce-112">集計時間</span><span class="sxs-lookup"><span data-stu-id="264ce-112">Aggregated time</span></span> | <span data-ttu-id="264ce-113">**入れ子になっ**たイベントのイベントについては、各カテゴリのイベントによって実行される時間。</span><span class="sxs-lookup"><span data-stu-id="264ce-113">For events with **nested events**, the time taken by each category of events.</span></span> |  
| <span data-ttu-id="264ce-114">通話スタック</span><span class="sxs-lookup"><span data-stu-id="264ce-114">Call Stack</span></span> | <span data-ttu-id="264ce-115">**子イベント**を持つイベントについては、各カテゴリのイベントによって行われる時間。</span><span class="sxs-lookup"><span data-stu-id="264ce-115">For events with **child events**, the time taken by each category of events.</span></span> |  
| <span data-ttu-id="264ce-116">CPU 時間</span><span class="sxs-lookup"><span data-stu-id="264ce-116">CPU time</span></span> | <span data-ttu-id="264ce-117">記録されたイベントに要した CPU 時間。</span><span class="sxs-lookup"><span data-stu-id="264ce-117">How much CPU time the recorded event took.</span></span> |  
| <span data-ttu-id="264ce-118">詳細</span><span class="sxs-lookup"><span data-stu-id="264ce-118">Details</span></span> | <span data-ttu-id="264ce-119">イベントに関するその他の詳細。</span><span class="sxs-lookup"><span data-stu-id="264ce-119">Other details about the event.</span></span> |  
| <span data-ttu-id="264ce-120">Duration (タイムスタンプ \)</span><span class="sxs-lookup"><span data-stu-id="264ce-120">Duration \(at time-stamp\)</span></span> | <span data-ttu-id="264ce-121">すべての子のイベントが完了するまでの時間。[タイムスタンプ] は、記録を開始したタイミングを基準とした、イベントが発生した時刻です。</span><span class="sxs-lookup"><span data-stu-id="264ce-121">How long it took the event with all of its children to complete; timestamp is the time at which the event occurred, relative to when the recording started.</span></span> |  
| <span data-ttu-id="264ce-122">セルフタイム</span><span class="sxs-lookup"><span data-stu-id="264ce-122">Self time</span></span> | <span data-ttu-id="264ce-123">その子のいずれかがなくてもイベントはどのくらいの時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="264ce-123">How long the event took without any of its children.</span></span> |  
| <span data-ttu-id="264ce-124">使用されたヒープサイズ</span><span class="sxs-lookup"><span data-stu-id="264ce-124">Used Heap Size</span></span> | <span data-ttu-id="264ce-125">イベントが記録されたときにアプリケーションによって使用されたメモリの量と、前回のサンプリング以降、使用されたヒープサイズのデルタ \ (+/-\) が変化します。</span><span class="sxs-lookup"><span data-stu-id="264ce-125">Amount of memory being used by the application when the event was recorded, and the delta \(+/-\) change in used heap size since the last sampling.</span></span> |  

<!--todo: add nested and child events (timelinetool) section when available -->  

## <span data-ttu-id="264ce-126">イベントの読み込み</span><span class="sxs-lookup"><span data-stu-id="264ce-126">Loading events</span></span>  

<span data-ttu-id="264ce-127">このセクションには、カテゴリとそのプロパティの読み込みに属するイベントが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="264ce-127">This section lists events that belong to Loading category and their properties.</span></span>  

| <span data-ttu-id="264ce-128">イベント</span><span class="sxs-lookup"><span data-stu-id="264ce-128">Event</span></span> | <span data-ttu-id="264ce-129">説明</span><span class="sxs-lookup"><span data-stu-id="264ce-129">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="264ce-130">HTML の解析</span><span class="sxs-lookup"><span data-stu-id="264ce-130">Parse HTML</span></span> |  <span data-ttu-id="264ce-131">Microsoft Edge は、HTML 解析アルゴリズムを実行しました。</span><span class="sxs-lookup"><span data-stu-id="264ce-131">Microsoft Edge ran the HTML parsing algorithm.</span></span> |  
| <span data-ttu-id="264ce-132">読み込みを完了する</span><span class="sxs-lookup"><span data-stu-id="264ce-132">Finish Loading</span></span> |  <span data-ttu-id="264ce-133">ネットワーク要求が完了しました。</span><span class="sxs-lookup"><span data-stu-id="264ce-133">A network request completed.</span></span> |  
| <span data-ttu-id="264ce-134">データの受信</span><span class="sxs-lookup"><span data-stu-id="264ce-134">Receive Data</span></span> |  <span data-ttu-id="264ce-135">要求のデータが受信されました。</span><span class="sxs-lookup"><span data-stu-id="264ce-135">Data for a request was received.</span></span>  <span data-ttu-id="264ce-136">1つ以上の受信データイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="264ce-136">There are one or more Receive Data events.</span></span> |  
| <span data-ttu-id="264ce-137">応答を受信する</span><span class="sxs-lookup"><span data-stu-id="264ce-137">Receive Response</span></span> |  <span data-ttu-id="264ce-138">要求からの最初の HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="264ce-138">The initial HTTP response from a request.</span></span> |  
| <span data-ttu-id="264ce-139">リクエストを送信</span><span class="sxs-lookup"><span data-stu-id="264ce-139">Send Request</span></span> |  <span data-ttu-id="264ce-140">ネットワーク要求が送信されました。</span><span class="sxs-lookup"><span data-stu-id="264ce-140">A network request has been sent.</span></span> |  

### <span data-ttu-id="264ce-141">イベントプロパティの読み込み</span><span class="sxs-lookup"><span data-stu-id="264ce-141">Loading event properties</span></span>  

| <span data-ttu-id="264ce-142">プロパティ</span><span class="sxs-lookup"><span data-stu-id="264ce-142">Property</span></span> | <span data-ttu-id="264ce-143">説明</span><span class="sxs-lookup"><span data-stu-id="264ce-143">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="264ce-144">リソース</span><span class="sxs-lookup"><span data-stu-id="264ce-144">Resource</span></span> | <span data-ttu-id="264ce-145">要求されたリソースの URL です。</span><span class="sxs-lookup"><span data-stu-id="264ce-145">The URL of the requested resource.</span></span> |  
| <span data-ttu-id="264ce-146">Preview</span><span class="sxs-lookup"><span data-stu-id="264ce-146">Preview</span></span> | <span data-ttu-id="264ce-147">要求されたリソースのプレビュー \ (images のみ)。</span><span class="sxs-lookup"><span data-stu-id="264ce-147">Preview of the requested resource \(images only\).</span></span> |  
| <span data-ttu-id="264ce-148">Request メソッド</span><span class="sxs-lookup"><span data-stu-id="264ce-148">Request Method</span></span> | <span data-ttu-id="264ce-149">要求 (\ など) に使用される HTTP メソッド `GET` `POST` 。</span><span class="sxs-lookup"><span data-stu-id="264ce-149">HTTP method used for the request \(`GET` or `POST`, for example\).</span></span> |  
| <span data-ttu-id="264ce-150">ステータス コード</span><span class="sxs-lookup"><span data-stu-id="264ce-150">Status Code</span></span> | <span data-ttu-id="264ce-151">HTTP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="264ce-151">HTTP response code.</span></span> |  
| <span data-ttu-id="264ce-152">MIME の種類</span><span class="sxs-lookup"><span data-stu-id="264ce-152">MIME Type</span></span> | <span data-ttu-id="264ce-153">要求されたリソースの MIME の種類。</span><span class="sxs-lookup"><span data-stu-id="264ce-153">MIME type of the requested resource.</span></span> |  
| <span data-ttu-id="264ce-154">エンコードされたデータの長さ</span><span class="sxs-lookup"><span data-stu-id="264ce-154">Encoded Data Length</span></span> | <span data-ttu-id="264ce-155">要求されたリソースの長さ (バイト単位) です。</span><span class="sxs-lookup"><span data-stu-id="264ce-155">Length of requested resource in bytes.</span></span> |  

## <span data-ttu-id="264ce-156">スクリプトイベント</span><span class="sxs-lookup"><span data-stu-id="264ce-156">Scripting events</span></span>  

<span data-ttu-id="264ce-157">このセクションには、スクリプトカテゴリとそのプロパティに属するイベントが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="264ce-157">This section lists events that belong to the Scripting category and their properties.</span></span>  

| <span data-ttu-id="264ce-158">イベント</span><span class="sxs-lookup"><span data-stu-id="264ce-158">Event</span></span> | <span data-ttu-id="264ce-159">説明</span><span class="sxs-lookup"><span data-stu-id="264ce-159">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="264ce-160">アニメーションフレームが発生した</span><span class="sxs-lookup"><span data-stu-id="264ce-160">Animation Frame Fired</span></span> | <span data-ttu-id="264ce-161">スケジュールされたアニメーションフレームが起動され、そのコールバックハンドラーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="264ce-161">A scheduled animation frame fired, and its callback handler invoked.</span></span> |  
| <span data-ttu-id="264ce-162">アニメーションフレームのキャンセル</span><span class="sxs-lookup"><span data-stu-id="264ce-162">Cancel Animation Frame</span></span> |  <span data-ttu-id="264ce-163">スケジュールされたアニメーションのフレームが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="264ce-163">A scheduled animation frame was canceled.</span></span> |  
| <span data-ttu-id="264ce-164">GC イベント</span><span class="sxs-lookup"><span data-stu-id="264ce-164">GC Event</span></span> |  <span data-ttu-id="264ce-165">ガーベジコレクションが行われました。</span><span class="sxs-lookup"><span data-stu-id="264ce-165">Garbage collection occurred.</span></span> |  
| <span data-ttu-id="264ce-166">DOMContentLoaded</span><span class="sxs-lookup"><span data-stu-id="264ce-166">DOMContentLoaded</span></span> |  <span data-ttu-id="264ce-167">[Domcontentloaded イベント][MDNWindowDOMContentLoadedEvent]がブラウザーによって起動されました。</span><span class="sxs-lookup"><span data-stu-id="264ce-167">The [DOMContentLoaded event][MDNWindowDOMContentLoadedEvent] was fired by the browser.</span></span>  <span data-ttu-id="264ce-168">このイベントは、すべてのページの DOM コンテンツが読み込まれて解析されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="264ce-168">This event is fired when all of the page's DOM content has been loaded and parsed.</span></span> |  
| <span data-ttu-id="264ce-169">スクリプトの評価</span><span class="sxs-lookup"><span data-stu-id="264ce-169">Evaluate Script</span></span> | <span data-ttu-id="264ce-170">スクリプトが評価されました。</span><span class="sxs-lookup"><span data-stu-id="264ce-170">A script was evaluated.</span></span> |  
| <span data-ttu-id="264ce-171">イベント</span><span class="sxs-lookup"><span data-stu-id="264ce-171">Event</span></span> | <span data-ttu-id="264ce-172">JavaScript イベント ( `mousedown` 、、など `key` )。</span><span class="sxs-lookup"><span data-stu-id="264ce-172">A JavaScript event \(for example, `mousedown`, or `key`\).</span></span> |  
| <span data-ttu-id="264ce-173">関数呼び出し</span><span class="sxs-lookup"><span data-stu-id="264ce-173">Function Call</span></span> | <span data-ttu-id="264ce-174">最上位レベルの JavaScript 関数の呼び出しが行われました (ブラウザーが JavaScript エンジン \ に入力した場合にのみ表示されます)。</span><span class="sxs-lookup"><span data-stu-id="264ce-174">A top-level JavaScript function call was made \(only appears when browser enters JavaScript engine\).</span></span> |  
| <span data-ttu-id="264ce-175">インストールタイマー</span><span class="sxs-lookup"><span data-stu-id="264ce-175">Install Timer</span></span> | <span data-ttu-id="264ce-176">タイマーは[Setinterval ()][MDNWindowOrWorkerGlobalScopeSetInterval]または[setTimeout ()][MDNWindowOrWorkerGlobalScopeSetTimeout]を使って作成されました。</span><span class="sxs-lookup"><span data-stu-id="264ce-176">A timer was created with [setInterval()][MDNWindowOrWorkerGlobalScopeSetInterval] or [setTimeout()][MDNWindowOrWorkerGlobalScopeSetTimeout].</span></span> |  
| <span data-ttu-id="264ce-177">アニメーションフレームを要求する</span><span class="sxs-lookup"><span data-stu-id="264ce-177">Request Animation Frame</span></span> | <span data-ttu-id="264ce-178">通話によって `requestAnimationFrame()` 新しいフレームがスケジュールされました。</span><span class="sxs-lookup"><span data-stu-id="264ce-178">A `requestAnimationFrame()` call scheduled a new frame.</span></span> |  
| <span data-ttu-id="264ce-179">タイマーを削除する</span><span class="sxs-lookup"><span data-stu-id="264ce-179">Remove Timer</span></span> | <span data-ttu-id="264ce-180">以前に作成したタイマーが消去されました。</span><span class="sxs-lookup"><span data-stu-id="264ce-180">A previously created timer was cleared.</span></span> |  
| <span data-ttu-id="264ce-181">Time</span><span class="sxs-lookup"><span data-stu-id="264ce-181">Time</span></span> |  <span data-ttu-id="264ce-182">" [Console. time ()][ConsoleApiTime]" というスクリプト。</span><span class="sxs-lookup"><span data-stu-id="264ce-182">A script called [console.time()][ConsoleApiTime].</span></span> |  
| <span data-ttu-id="264ce-183">終了時刻</span><span class="sxs-lookup"><span data-stu-id="264ce-183">Time End</span></span> | <span data-ttu-id="264ce-184">" [Console. timeEnd ()][ConsoleApiTimeEnd]" というスクリプト。</span><span class="sxs-lookup"><span data-stu-id="264ce-184">A script called [console.timeEnd()][ConsoleApiTimeEnd].</span></span> |  
| <span data-ttu-id="264ce-185">タイマーが発生した</span><span class="sxs-lookup"><span data-stu-id="264ce-185">Timer Fired</span></span> | <span data-ttu-id="264ce-186">またはでスケジュールされていたタイマーが起動しました `setInterval()` `setTimeout()` 。</span><span class="sxs-lookup"><span data-stu-id="264ce-186">A timer fired that was scheduled with `setInterval()` or `setTimeout()`.</span></span> |  
| <span data-ttu-id="264ce-187">XHR のレディ状態の変更</span><span class="sxs-lookup"><span data-stu-id="264ce-187">XHR Ready State Change</span></span> | <span data-ttu-id="264ce-188">XMLHTTPRequest のレディ状態が変更されました。</span><span class="sxs-lookup"><span data-stu-id="264ce-188">The ready state of an XMLHTTPRequest changed.</span></span> |  
| <span data-ttu-id="264ce-189">XHR 読み込み</span><span class="sxs-lookup"><span data-stu-id="264ce-189">XHR Load</span></span> | <span data-ttu-id="264ce-190">`XMLHTTPRequest`読み込みが完了しました。</span><span class="sxs-lookup"><span data-stu-id="264ce-190">An `XMLHTTPRequest` finished loading.</span></span> |  

### <span data-ttu-id="264ce-191">スクリプトイベントプロパティ</span><span class="sxs-lookup"><span data-stu-id="264ce-191">Scripting event properties</span></span>  

| <span data-ttu-id="264ce-192">プロパティ</span><span class="sxs-lookup"><span data-stu-id="264ce-192">Property</span></span> | <span data-ttu-id="264ce-193">説明</span><span class="sxs-lookup"><span data-stu-id="264ce-193">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="264ce-194">タイマー ID</span><span class="sxs-lookup"><span data-stu-id="264ce-194">Timer ID</span></span> | <span data-ttu-id="264ce-195">タイマー ID。</span><span class="sxs-lookup"><span data-stu-id="264ce-195">The timer ID.</span></span> |  
| <span data-ttu-id="264ce-196">タイムアウト</span><span class="sxs-lookup"><span data-stu-id="264ce-196">Timeout</span></span> | <span data-ttu-id="264ce-197">タイマーによって指定されたタイムアウト。</span><span class="sxs-lookup"><span data-stu-id="264ce-197">The timeout specified by the timer.</span></span> |  
| <span data-ttu-id="264ce-198">繰り返し</span><span class="sxs-lookup"><span data-stu-id="264ce-198">Repeats</span></span> | <span data-ttu-id="264ce-199">タイマーを繰り返すかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="264ce-199">Boolean that specifies if the timer repeats.</span></span> |  
| <span data-ttu-id="264ce-200">関数呼び出し</span><span class="sxs-lookup"><span data-stu-id="264ce-200">Function Call</span></span> | <span data-ttu-id="264ce-201">呼び出された関数。</span><span class="sxs-lookup"><span data-stu-id="264ce-201">A function that was invoked.</span></span> |  

## <span data-ttu-id="264ce-202">レンダリングイベント</span><span class="sxs-lookup"><span data-stu-id="264ce-202">Rendering events</span></span>  

<span data-ttu-id="264ce-203">このセクションには、レンダリングカテゴリとそのプロパティに属するイベントが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="264ce-203">This section lists events that belong to Rendering category and their properties.</span></span>  

| <span data-ttu-id="264ce-204">イベント</span><span class="sxs-lookup"><span data-stu-id="264ce-204">Event</span></span> | <span data-ttu-id="264ce-205">説明</span><span class="sxs-lookup"><span data-stu-id="264ce-205">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="264ce-206">レイアウトの無効化</span><span class="sxs-lookup"><span data-stu-id="264ce-206">Invalidate layout</span></span> | <span data-ttu-id="264ce-207">ページレイアウトは DOM の変更によって無効にされました。</span><span class="sxs-lookup"><span data-stu-id="264ce-207">The page layout was invalidated by a DOM change.</span></span> |  
| <span data-ttu-id="264ce-208">レイアウト</span><span class="sxs-lookup"><span data-stu-id="264ce-208">Layout</span></span> | <span data-ttu-id="264ce-209">ページレイアウトが完了しました。</span><span class="sxs-lookup"><span data-stu-id="264ce-209">A page layout was completed.</span></span> |  
| <span data-ttu-id="264ce-210">スタイルの再計算</span><span class="sxs-lookup"><span data-stu-id="264ce-210">Recalculate style</span></span> | <span data-ttu-id="264ce-211">Microsoft Edge で再計算された要素のスタイル。</span><span class="sxs-lookup"><span data-stu-id="264ce-211">Microsoft Edge recalculated element styles.</span></span> |  
| <span data-ttu-id="264ce-212">Scroll</span><span class="sxs-lookup"><span data-stu-id="264ce-212">Scroll</span></span> | <span data-ttu-id="264ce-213">入れ子になったビューのコンテンツがスクロールされました。</span><span class="sxs-lookup"><span data-stu-id="264ce-213">The content of nested view was scrolled.</span></span> |  

### <span data-ttu-id="264ce-214">イベントプロパティのレンダリング</span><span class="sxs-lookup"><span data-stu-id="264ce-214">Rendering event properties</span></span>  

| <span data-ttu-id="264ce-215">プロパティ</span><span class="sxs-lookup"><span data-stu-id="264ce-215">Property</span></span> | <span data-ttu-id="264ce-216">説明</span><span class="sxs-lookup"><span data-stu-id="264ce-216">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="264ce-217">レイアウトの無効化</span><span class="sxs-lookup"><span data-stu-id="264ce-217">Layout invalidated</span></span> | <span data-ttu-id="264ce-218">レイアウトレコードの場合、レイアウトが無効になる原因となったコードのスタックトレース。</span><span class="sxs-lookup"><span data-stu-id="264ce-218">For Layout records, the stack trace of the code that caused the layout to be invalidated.</span></span> |  
| <span data-ttu-id="264ce-219">レイアウトが必要なノード</span><span class="sxs-lookup"><span data-stu-id="264ce-219">Nodes that need layout</span></span> | <span data-ttu-id="264ce-220">レイアウトレコードの場合は、relayout が開始される前に、必要なレイアウトとしてマークされたノードの数。</span><span class="sxs-lookup"><span data-stu-id="264ce-220">For Layout records, the number of nodes that were marked as needing layout before the relayout started.</span></span>  <span data-ttu-id="264ce-221">これらは通常、開発者コードによって無効にされたノードに加えて、relayout ルートまでのパスを示しています。</span><span class="sxs-lookup"><span data-stu-id="264ce-221">These are normally those nodes that were invalidated by developer code, plus a path upward to relayout root.</span></span> |  
| <span data-ttu-id="264ce-222">レイアウトツリーのサイズ</span><span class="sxs-lookup"><span data-stu-id="264ce-222">Layout tree size</span></span> | <span data-ttu-id="264ce-223">レイアウトレコードの場合、relayout ルート \ (Microsoft Edge が relayout を開始するノード) の下にあるノードの合計数です。</span><span class="sxs-lookup"><span data-stu-id="264ce-223">For Layout records, the total number of nodes under the relayout root \(the node that Microsoft Edge starts the relayout\).</span></span> |  
| <span data-ttu-id="264ce-224">レイアウトの範囲</span><span class="sxs-lookup"><span data-stu-id="264ce-224">Layout scope</span></span> | <span data-ttu-id="264ce-225">可能な値は `Partial` \ (再レイアウトの境界は DOM の一部) または `Whole document` です。</span><span class="sxs-lookup"><span data-stu-id="264ce-225">Possible values are `Partial` \(the re-layout boundary is a portion of the DOM\) or `Whole document`.</span></span> |  
| <span data-ttu-id="264ce-226">影響を受ける要素</span><span class="sxs-lookup"><span data-stu-id="264ce-226">Elements affected</span></span> | <span data-ttu-id="264ce-227">スタイルの再計算には、スタイル再計算によって影響を受ける要素の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="264ce-227">For Recalculate style records, the number of elements affected by a style recalculation.</span></span> |  
| <span data-ttu-id="264ce-228">無効になったスタイル</span><span class="sxs-lookup"><span data-stu-id="264ce-228">Styles invalidated</span></span> | <span data-ttu-id="264ce-229">スタイルレコードの再計算には、スタイルの無効化を引き起こしたコードのスタックトレースを提供します。</span><span class="sxs-lookup"><span data-stu-id="264ce-229">For Recalculate style records, provides the stack trace of the code that caused the style invalidation.</span></span> |  

## <span data-ttu-id="264ce-230">描画イベント</span><span class="sxs-lookup"><span data-stu-id="264ce-230">Painting events</span></span>  

<span data-ttu-id="264ce-231">このセクションには、Painting カテゴリとそのプロパティに属するイベントが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="264ce-231">This section lists events that belong to Painting category and their properties.</span></span>  

| <span data-ttu-id="264ce-232">イベント</span><span class="sxs-lookup"><span data-stu-id="264ce-232">Event</span></span> | <span data-ttu-id="264ce-233">説明</span><span class="sxs-lookup"><span data-stu-id="264ce-233">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="264ce-234">複合レイヤー</span><span class="sxs-lookup"><span data-stu-id="264ce-234">Composite Layers</span></span> | <span data-ttu-id="264ce-235">Microsoft Edge レンダリングエンジン用の合成画像レイヤー。</span><span class="sxs-lookup"><span data-stu-id="264ce-235">The composited image layers for the Microsoft Edge rendering engine.</span></span> |  
| <span data-ttu-id="264ce-236">画像のデコード</span><span class="sxs-lookup"><span data-stu-id="264ce-236">Image Decode</span></span> | <span data-ttu-id="264ce-237">画像リソースがデコードされました。</span><span class="sxs-lookup"><span data-stu-id="264ce-237">An image resource was decoded.</span></span> |  
| <span data-ttu-id="264ce-238">画像のサイズ変更</span><span class="sxs-lookup"><span data-stu-id="264ce-238">Image Resize</span></span> | <span data-ttu-id="264ce-239">画像がネイティブの寸法からサイズ変更されました。</span><span class="sxs-lookup"><span data-stu-id="264ce-239">An image was resized from its native dimensions.</span></span> |  
| <span data-ttu-id="264ce-240">ペイント</span><span class="sxs-lookup"><span data-stu-id="264ce-240">Paint</span></span> | <span data-ttu-id="264ce-241">合成レイヤーは、ディスプレイの領域に対して描画されました。</span><span class="sxs-lookup"><span data-stu-id="264ce-241">Composited layers were painted to a region of the display.</span></span>  <span data-ttu-id="264ce-242">ペイントレコードの上にマウスポインターを置くと、更新されたディスプレイの領域が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="264ce-242">Hovering over a Paint record highlights the region of the display that was updated.</span></span> |  

### <span data-ttu-id="264ce-243">Painting イベントプロパティ</span><span class="sxs-lookup"><span data-stu-id="264ce-243">Painting event properties</span></span>  

| <span data-ttu-id="264ce-244">プロパティ</span><span class="sxs-lookup"><span data-stu-id="264ce-244">Property</span></span> | <span data-ttu-id="264ce-245">説明</span><span class="sxs-lookup"><span data-stu-id="264ce-245">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="264ce-246">場所</span><span class="sxs-lookup"><span data-stu-id="264ce-246">Location</span></span> | <span data-ttu-id="264ce-247">Paint イベントの場合は、ペイントの四角形の x 座標と y 座標を使用します。</span><span class="sxs-lookup"><span data-stu-id="264ce-247">For Paint events, the x and y coordinates of the paint rectangle.</span></span> |  
| <span data-ttu-id="264ce-248">各</span><span class="sxs-lookup"><span data-stu-id="264ce-248">Dimensions</span></span> | <span data-ttu-id="264ce-249">Paint イベントの場合は、塗装領域の高さと幅。</span><span class="sxs-lookup"><span data-stu-id="264ce-249">For Paint events, the height and width of the painted region.</span></span> |  

 



<!-- image links -->  

<!-- links -->

[ConsoleApiTime]: /microsoft-edge/devtools-guide-chromium/console/api#time "タイムコンソール API リファレンス"  
[ConsoleApiTimeEnd]: /microsoft-edge/devtools-guide-chromium/console/api#timeend "timeEnd-本体の API リファレンス"  
<!--[EvaluatePerformanceTimelineTool]: timeline-tool "How to Use the Timeline Tool"  -->

[MDNWindowDOMContentLoadedEvent]: https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded "Window: DOMContentLoaded イベント |MDN"  
[MDNWindowOrWorkerGlobalScopeSetInterval]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setInterval "WindowOrWorkerGlobalScope Interval () |MDN"  
[MDNWindowOrWorkerGlobalScopeSetTimeout]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setTimeout "WindowOrWorkerGlobalScope () |MDN"  

> [!NOTE]
> <span data-ttu-id="264ce-255">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="264ce-255">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="264ce-256">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/performance-reference)にあり、 [Meggin Kearney][MegginKearney] \ (Tech Writer \) と[Flavio Copes][FlavioCopes] \ (完全なスタック開発者) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="264ce-256">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/performance-reference) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Flavio Copes][FlavioCopes] \(Full Stack Developer\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="264ce-258">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="264ce-258">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[FlavioCopes]: https://developers.google.com/web/resources/contributors/flaviocopes  
