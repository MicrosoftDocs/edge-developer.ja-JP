---
description: タイムラインイベントモードでは、記録を作成するときにトリガーされるすべてのイベントが表示されます。  タイムラインイベントのリファレンスを使って、各タイムラインイベントの種類について詳しく知ることができます。
title: タイムライン イベント リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 624035636e2231cf1f3cd1e2ba0fdda7e2e4fa00
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992849"
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





# <span data-ttu-id="298a5-105">タイムライン イベント リファレンス</span><span class="sxs-lookup"><span data-stu-id="298a5-105">Timeline Event Reference</span></span>   




<span data-ttu-id="298a5-106">タイムラインイベントモードでは、記録を作成するときにトリガーされるすべてのイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="298a5-106">The timeline events mode displays all events triggered while making a recording.</span></span>  <span data-ttu-id="298a5-107">タイムラインイベントのリファレンスを使って、各タイムラインイベントの種類について詳しく知ることができます。</span><span class="sxs-lookup"><span data-stu-id="298a5-107">Use the timeline event reference to learn more about each timeline event type.</span></span>  

## <span data-ttu-id="298a5-108">一般的なタイムラインイベントプロパティ</span><span class="sxs-lookup"><span data-stu-id="298a5-108">Common timeline event properties</span></span>  

<span data-ttu-id="298a5-109">一部の詳細は、すべての種類のイベントに存在しますが、一部のイベントの種類にしか適用されません。</span><span class="sxs-lookup"><span data-stu-id="298a5-109">Certain details are present in events of all types, while some only apply to certain event types.</span></span>  <span data-ttu-id="298a5-110">このセクションでは、さまざまなイベントの種類に共通するプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="298a5-110">This section lists properties common to different event types.</span></span>  <span data-ttu-id="298a5-111">特定のイベントの種類に固有のプロパティについては、次に示すイベントの種類に関する参照で示されています。</span><span class="sxs-lookup"><span data-stu-id="298a5-111">Properties specific to certain event types are listed in the references for those event types that follow.</span></span>  

| <span data-ttu-id="298a5-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="298a5-112">Property</span></span> | <span data-ttu-id="298a5-113">表示されるタイミング</span><span class="sxs-lookup"><span data-stu-id="298a5-113">When is it shown</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="298a5-114">集計時間</span><span class="sxs-lookup"><span data-stu-id="298a5-114">Aggregated time</span></span> | <span data-ttu-id="298a5-115">**入れ子になっ**たイベントのイベントについては、各カテゴリのイベントによって実行される時間。</span><span class="sxs-lookup"><span data-stu-id="298a5-115">For events with **nested events**, the time taken by each category of events.</span></span> |  
| <span data-ttu-id="298a5-116">通話スタック</span><span class="sxs-lookup"><span data-stu-id="298a5-116">Call Stack</span></span> | <span data-ttu-id="298a5-117">**子イベント**を持つイベントについては、各カテゴリのイベントによって行われる時間。</span><span class="sxs-lookup"><span data-stu-id="298a5-117">For events with **child events**, the time taken by each category of events.</span></span> |  
| <span data-ttu-id="298a5-118">CPU 時間</span><span class="sxs-lookup"><span data-stu-id="298a5-118">CPU time</span></span> | <span data-ttu-id="298a5-119">記録されたイベントに要した CPU 時間。</span><span class="sxs-lookup"><span data-stu-id="298a5-119">How much CPU time the recorded event took.</span></span> |  
| <span data-ttu-id="298a5-120">詳細</span><span class="sxs-lookup"><span data-stu-id="298a5-120">Details</span></span> | <span data-ttu-id="298a5-121">イベントに関するその他の詳細。</span><span class="sxs-lookup"><span data-stu-id="298a5-121">Other details about the event.</span></span> |  
| <span data-ttu-id="298a5-122">Duration (タイムスタンプ \)</span><span class="sxs-lookup"><span data-stu-id="298a5-122">Duration \(at time-stamp\)</span></span> | <span data-ttu-id="298a5-123">すべての子のイベントが完了するまでの時間。[タイムスタンプ] は、記録を開始したタイミングを基準とした、イベントが発生した時刻です。</span><span class="sxs-lookup"><span data-stu-id="298a5-123">How long it took the event with all of its children to complete; timestamp is the time at which the event occurred, relative to when the recording started.</span></span> |  
| <span data-ttu-id="298a5-124">セルフタイム</span><span class="sxs-lookup"><span data-stu-id="298a5-124">Self time</span></span> | <span data-ttu-id="298a5-125">その子のいずれかがなくてもイベントはどのくらいの時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="298a5-125">How long the event took without any of its children.</span></span> |  
| <span data-ttu-id="298a5-126">使用されたヒープサイズ</span><span class="sxs-lookup"><span data-stu-id="298a5-126">Used Heap Size</span></span> | <span data-ttu-id="298a5-127">イベントが記録されたときにアプリケーションによって使用されたメモリの量と、前回のサンプリング以降、使用されたヒープサイズのデルタ \ (+/-\) が変化します。</span><span class="sxs-lookup"><span data-stu-id="298a5-127">Amount of memory being used by the application when the event was recorded, and the delta \(+/-\) change in used heap size since the last sampling.</span></span> |  

<!--todo: add nested and child events (timelinetool) section when available -->  

## <span data-ttu-id="298a5-128">イベントの読み込み</span><span class="sxs-lookup"><span data-stu-id="298a5-128">Loading events</span></span>  

<span data-ttu-id="298a5-129">このセクションには、カテゴリとそのプロパティの読み込みに属するイベントが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="298a5-129">This section lists events that belong to Loading category and their properties.</span></span>  

| <span data-ttu-id="298a5-130">イベント</span><span class="sxs-lookup"><span data-stu-id="298a5-130">Event</span></span> | <span data-ttu-id="298a5-131">説明</span><span class="sxs-lookup"><span data-stu-id="298a5-131">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="298a5-132">HTML の解析</span><span class="sxs-lookup"><span data-stu-id="298a5-132">Parse HTML</span></span> |  <span data-ttu-id="298a5-133">Microsoft Edge は、HTML 解析アルゴリズムを実行しました。</span><span class="sxs-lookup"><span data-stu-id="298a5-133">Microsoft Edge ran the HTML parsing algorithm.</span></span> |  
| <span data-ttu-id="298a5-134">読み込みを完了する</span><span class="sxs-lookup"><span data-stu-id="298a5-134">Finish Loading</span></span> |  <span data-ttu-id="298a5-135">ネットワーク要求が完了しました。</span><span class="sxs-lookup"><span data-stu-id="298a5-135">A network request completed.</span></span> |  
| <span data-ttu-id="298a5-136">データの受信</span><span class="sxs-lookup"><span data-stu-id="298a5-136">Receive Data</span></span> |  <span data-ttu-id="298a5-137">要求のデータが受信されました。</span><span class="sxs-lookup"><span data-stu-id="298a5-137">Data for a request was received.</span></span>  <span data-ttu-id="298a5-138">1つ以上の受信データイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="298a5-138">There are one or more Receive Data events.</span></span> |  
| <span data-ttu-id="298a5-139">応答を受信する</span><span class="sxs-lookup"><span data-stu-id="298a5-139">Receive Response</span></span> |  <span data-ttu-id="298a5-140">要求からの最初の HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="298a5-140">The initial HTTP response from a request.</span></span> |  
| <span data-ttu-id="298a5-141">リクエストを送信</span><span class="sxs-lookup"><span data-stu-id="298a5-141">Send Request</span></span> |  <span data-ttu-id="298a5-142">ネットワーク要求が送信されました。</span><span class="sxs-lookup"><span data-stu-id="298a5-142">A network request has been sent.</span></span> |  

### <span data-ttu-id="298a5-143">イベントプロパティの読み込み</span><span class="sxs-lookup"><span data-stu-id="298a5-143">Loading event properties</span></span>  

| <span data-ttu-id="298a5-144">プロパティ</span><span class="sxs-lookup"><span data-stu-id="298a5-144">Property</span></span> | <span data-ttu-id="298a5-145">説明</span><span class="sxs-lookup"><span data-stu-id="298a5-145">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="298a5-146">リソース</span><span class="sxs-lookup"><span data-stu-id="298a5-146">Resource</span></span> | <span data-ttu-id="298a5-147">要求されたリソースの URL です。</span><span class="sxs-lookup"><span data-stu-id="298a5-147">The URL of the requested resource.</span></span> |  
| <span data-ttu-id="298a5-148">Preview</span><span class="sxs-lookup"><span data-stu-id="298a5-148">Preview</span></span> | <span data-ttu-id="298a5-149">要求されたリソースのプレビュー \ (images のみ)。</span><span class="sxs-lookup"><span data-stu-id="298a5-149">Preview of the requested resource \(images only\).</span></span> |  
| <span data-ttu-id="298a5-150">Request メソッド</span><span class="sxs-lookup"><span data-stu-id="298a5-150">Request Method</span></span> | <span data-ttu-id="298a5-151">要求 (\ など) に使用される HTTP メソッド `GET` `POST` 。</span><span class="sxs-lookup"><span data-stu-id="298a5-151">HTTP method used for the request \(`GET` or `POST`, for example\).</span></span> |  
| <span data-ttu-id="298a5-152">ステータス コード</span><span class="sxs-lookup"><span data-stu-id="298a5-152">Status Code</span></span> | <span data-ttu-id="298a5-153">HTTP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="298a5-153">HTTP response code.</span></span> |  
| <span data-ttu-id="298a5-154">MIME の種類</span><span class="sxs-lookup"><span data-stu-id="298a5-154">MIME Type</span></span> | <span data-ttu-id="298a5-155">要求されたリソースの MIME の種類。</span><span class="sxs-lookup"><span data-stu-id="298a5-155">MIME type of the requested resource.</span></span> |  
| <span data-ttu-id="298a5-156">エンコードされたデータの長さ</span><span class="sxs-lookup"><span data-stu-id="298a5-156">Encoded Data Length</span></span> | <span data-ttu-id="298a5-157">要求されたリソースの長さ (バイト単位) です。</span><span class="sxs-lookup"><span data-stu-id="298a5-157">Length of requested resource in bytes.</span></span> |  

## <span data-ttu-id="298a5-158">スクリプトイベント</span><span class="sxs-lookup"><span data-stu-id="298a5-158">Scripting events</span></span>  

<span data-ttu-id="298a5-159">このセクションには、スクリプトカテゴリとそのプロパティに属するイベントが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="298a5-159">This section lists events that belong to the Scripting category and their properties.</span></span>  

| <span data-ttu-id="298a5-160">イベント</span><span class="sxs-lookup"><span data-stu-id="298a5-160">Event</span></span> | <span data-ttu-id="298a5-161">説明</span><span class="sxs-lookup"><span data-stu-id="298a5-161">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="298a5-162">アニメーションフレームが発生した</span><span class="sxs-lookup"><span data-stu-id="298a5-162">Animation Frame Fired</span></span> | <span data-ttu-id="298a5-163">スケジュールされたアニメーションフレームが起動され、そのコールバックハンドラーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="298a5-163">A scheduled animation frame fired, and its callback handler invoked.</span></span> |  
| <span data-ttu-id="298a5-164">アニメーションフレームのキャンセル</span><span class="sxs-lookup"><span data-stu-id="298a5-164">Cancel Animation Frame</span></span> |  <span data-ttu-id="298a5-165">スケジュールされたアニメーションのフレームが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="298a5-165">A scheduled animation frame was canceled.</span></span> |  
| <span data-ttu-id="298a5-166">GC イベント</span><span class="sxs-lookup"><span data-stu-id="298a5-166">GC Event</span></span> |  <span data-ttu-id="298a5-167">ガーベジコレクションが行われました。</span><span class="sxs-lookup"><span data-stu-id="298a5-167">Garbage collection occurred.</span></span> |  
| <span data-ttu-id="298a5-168">DOMContentLoaded</span><span class="sxs-lookup"><span data-stu-id="298a5-168">DOMContentLoaded</span></span> |  <span data-ttu-id="298a5-169">[Domcontentloaded イベント][MDNWindowDOMContentLoadedEvent]がブラウザーによって起動されました。</span><span class="sxs-lookup"><span data-stu-id="298a5-169">The [DOMContentLoaded event][MDNWindowDOMContentLoadedEvent] was fired by the browser.</span></span>  <span data-ttu-id="298a5-170">このイベントは、すべてのページの DOM コンテンツが読み込まれて解析されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="298a5-170">This event is fired when all of the page's DOM content has been loaded and parsed.</span></span> |  
| <span data-ttu-id="298a5-171">スクリプトの評価</span><span class="sxs-lookup"><span data-stu-id="298a5-171">Evaluate Script</span></span> | <span data-ttu-id="298a5-172">スクリプトが評価されました。</span><span class="sxs-lookup"><span data-stu-id="298a5-172">A script was evaluated.</span></span> |  
| <span data-ttu-id="298a5-173">イベント</span><span class="sxs-lookup"><span data-stu-id="298a5-173">Event</span></span> | <span data-ttu-id="298a5-174">JavaScript イベント ( `mousedown` 、、など `key` )。</span><span class="sxs-lookup"><span data-stu-id="298a5-174">A JavaScript event \(for example, `mousedown`, or `key`\).</span></span> |  
| <span data-ttu-id="298a5-175">関数呼び出し</span><span class="sxs-lookup"><span data-stu-id="298a5-175">Function Call</span></span> | <span data-ttu-id="298a5-176">最上位レベルの JavaScript 関数の呼び出しが行われました (ブラウザーが JavaScript エンジン \ に入力した場合にのみ表示されます)。</span><span class="sxs-lookup"><span data-stu-id="298a5-176">A top-level JavaScript function call was made \(only appears when browser enters JavaScript engine\).</span></span> |  
| <span data-ttu-id="298a5-177">インストールタイマー</span><span class="sxs-lookup"><span data-stu-id="298a5-177">Install Timer</span></span> | <span data-ttu-id="298a5-178">タイマーは [Setinterval ()][MDNWindowOrWorkerGlobalScopeSetInterval] または [setTimeout ()][MDNWindowOrWorkerGlobalScopeSetTimeout]を使って作成されました。</span><span class="sxs-lookup"><span data-stu-id="298a5-178">A timer was created with [setInterval()][MDNWindowOrWorkerGlobalScopeSetInterval] or [setTimeout()][MDNWindowOrWorkerGlobalScopeSetTimeout].</span></span> |  
| <span data-ttu-id="298a5-179">アニメーションフレームを要求する</span><span class="sxs-lookup"><span data-stu-id="298a5-179">Request Animation Frame</span></span> | <span data-ttu-id="298a5-180">通話によって `requestAnimationFrame()` 新しいフレームがスケジュールされました。</span><span class="sxs-lookup"><span data-stu-id="298a5-180">A `requestAnimationFrame()` call scheduled a new frame.</span></span> |  
| <span data-ttu-id="298a5-181">タイマーを削除する</span><span class="sxs-lookup"><span data-stu-id="298a5-181">Remove Timer</span></span> | <span data-ttu-id="298a5-182">以前に作成したタイマーが消去されました。</span><span class="sxs-lookup"><span data-stu-id="298a5-182">A previously created timer was cleared.</span></span> |  
| <span data-ttu-id="298a5-183">時間</span><span class="sxs-lookup"><span data-stu-id="298a5-183">Time</span></span> |  <span data-ttu-id="298a5-184">" [Console. time ()][ConsoleApiTime]" というスクリプト。</span><span class="sxs-lookup"><span data-stu-id="298a5-184">A script called [console.time()][ConsoleApiTime].</span></span> |  
| <span data-ttu-id="298a5-185">終了時刻</span><span class="sxs-lookup"><span data-stu-id="298a5-185">Time End</span></span> | <span data-ttu-id="298a5-186">" [Console. timeEnd ()][ConsoleApiTimeEnd]" というスクリプト。</span><span class="sxs-lookup"><span data-stu-id="298a5-186">A script called [console.timeEnd()][ConsoleApiTimeEnd].</span></span> |  
| <span data-ttu-id="298a5-187">タイマーが発生した</span><span class="sxs-lookup"><span data-stu-id="298a5-187">Timer Fired</span></span> | <span data-ttu-id="298a5-188">またはでスケジュールされていたタイマーが起動しました `setInterval()` `setTimeout()` 。</span><span class="sxs-lookup"><span data-stu-id="298a5-188">A timer fired that was scheduled with `setInterval()` or `setTimeout()`.</span></span> |  
| <span data-ttu-id="298a5-189">XHR のレディ状態の変更</span><span class="sxs-lookup"><span data-stu-id="298a5-189">XHR Ready State Change</span></span> | <span data-ttu-id="298a5-190">XMLHTTPRequest のレディ状態が変更されました。</span><span class="sxs-lookup"><span data-stu-id="298a5-190">The ready state of an XMLHTTPRequest changed.</span></span> |  
| <span data-ttu-id="298a5-191">XHR 読み込み</span><span class="sxs-lookup"><span data-stu-id="298a5-191">XHR Load</span></span> | <span data-ttu-id="298a5-192">`XMLHTTPRequest`読み込みが完了しました。</span><span class="sxs-lookup"><span data-stu-id="298a5-192">An `XMLHTTPRequest` finished loading.</span></span> |  

### <span data-ttu-id="298a5-193">スクリプトイベントプロパティ</span><span class="sxs-lookup"><span data-stu-id="298a5-193">Scripting event properties</span></span>  

| <span data-ttu-id="298a5-194">プロパティ</span><span class="sxs-lookup"><span data-stu-id="298a5-194">Property</span></span> | <span data-ttu-id="298a5-195">説明</span><span class="sxs-lookup"><span data-stu-id="298a5-195">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="298a5-196">タイマー ID</span><span class="sxs-lookup"><span data-stu-id="298a5-196">Timer ID</span></span> | <span data-ttu-id="298a5-197">タイマー ID。</span><span class="sxs-lookup"><span data-stu-id="298a5-197">The timer ID.</span></span> |  
| <span data-ttu-id="298a5-198">タイムアウト</span><span class="sxs-lookup"><span data-stu-id="298a5-198">Timeout</span></span> | <span data-ttu-id="298a5-199">タイマーによって指定されたタイムアウト。</span><span class="sxs-lookup"><span data-stu-id="298a5-199">The timeout specified by the timer.</span></span> |  
| <span data-ttu-id="298a5-200">繰り返し</span><span class="sxs-lookup"><span data-stu-id="298a5-200">Repeats</span></span> | <span data-ttu-id="298a5-201">タイマーを繰り返すかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="298a5-201">Boolean that specifies if the timer repeats.</span></span> |  
| <span data-ttu-id="298a5-202">関数呼び出し</span><span class="sxs-lookup"><span data-stu-id="298a5-202">Function Call</span></span> | <span data-ttu-id="298a5-203">呼び出された関数。</span><span class="sxs-lookup"><span data-stu-id="298a5-203">A function that was invoked.</span></span> |  

## <span data-ttu-id="298a5-204">レンダリングイベント</span><span class="sxs-lookup"><span data-stu-id="298a5-204">Rendering events</span></span>  

<span data-ttu-id="298a5-205">このセクションには、レンダリングカテゴリとそのプロパティに属するイベントが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="298a5-205">This section lists events that belong to Rendering category and their properties.</span></span>  

| <span data-ttu-id="298a5-206">イベント</span><span class="sxs-lookup"><span data-stu-id="298a5-206">Event</span></span> | <span data-ttu-id="298a5-207">説明</span><span class="sxs-lookup"><span data-stu-id="298a5-207">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="298a5-208">レイアウトの無効化</span><span class="sxs-lookup"><span data-stu-id="298a5-208">Invalidate layout</span></span> | <span data-ttu-id="298a5-209">ページレイアウトは DOM の変更によって無効にされました。</span><span class="sxs-lookup"><span data-stu-id="298a5-209">The page layout was invalidated by a DOM change.</span></span> |  
| <span data-ttu-id="298a5-210">レイアウト</span><span class="sxs-lookup"><span data-stu-id="298a5-210">Layout</span></span> | <span data-ttu-id="298a5-211">ページレイアウトが完了しました。</span><span class="sxs-lookup"><span data-stu-id="298a5-211">A page layout was completed.</span></span> |  
| <span data-ttu-id="298a5-212">スタイルの再計算</span><span class="sxs-lookup"><span data-stu-id="298a5-212">Recalculate style</span></span> | <span data-ttu-id="298a5-213">Microsoft Edge で再計算された要素のスタイル。</span><span class="sxs-lookup"><span data-stu-id="298a5-213">Microsoft Edge recalculated element styles.</span></span> |  
| <span data-ttu-id="298a5-214">Scroll</span><span class="sxs-lookup"><span data-stu-id="298a5-214">Scroll</span></span> | <span data-ttu-id="298a5-215">入れ子になったビューのコンテンツがスクロールされました。</span><span class="sxs-lookup"><span data-stu-id="298a5-215">The content of nested view was scrolled.</span></span> |  

### <span data-ttu-id="298a5-216">イベントプロパティのレンダリング</span><span class="sxs-lookup"><span data-stu-id="298a5-216">Rendering event properties</span></span>  

| <span data-ttu-id="298a5-217">プロパティ</span><span class="sxs-lookup"><span data-stu-id="298a5-217">Property</span></span> | <span data-ttu-id="298a5-218">説明</span><span class="sxs-lookup"><span data-stu-id="298a5-218">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="298a5-219">レイアウトの無効化</span><span class="sxs-lookup"><span data-stu-id="298a5-219">Layout invalidated</span></span> | <span data-ttu-id="298a5-220">レイアウトレコードの場合、レイアウトが無効になる原因となったコードのスタックトレース。</span><span class="sxs-lookup"><span data-stu-id="298a5-220">For Layout records, the stack trace of the code that caused the layout to be invalidated.</span></span> |  
| <span data-ttu-id="298a5-221">レイアウトが必要なノード</span><span class="sxs-lookup"><span data-stu-id="298a5-221">Nodes that need layout</span></span> | <span data-ttu-id="298a5-222">レイアウトレコードの場合は、relayout が開始される前に、必要なレイアウトとしてマークされたノードの数。</span><span class="sxs-lookup"><span data-stu-id="298a5-222">For Layout records, the number of nodes that were marked as needing layout before the relayout started.</span></span>  <span data-ttu-id="298a5-223">これらは通常、開発者コードによって無効にされたノードに加えて、relayout ルートまでのパスを示しています。</span><span class="sxs-lookup"><span data-stu-id="298a5-223">These are normally those nodes that were invalidated by developer code, plus a path upward to relayout root.</span></span> |  
| <span data-ttu-id="298a5-224">レイアウトツリーのサイズ</span><span class="sxs-lookup"><span data-stu-id="298a5-224">Layout tree size</span></span> | <span data-ttu-id="298a5-225">レイアウトレコードの場合、relayout ルート \ (Microsoft Edge が relayout を開始するノード) の下にあるノードの合計数です。</span><span class="sxs-lookup"><span data-stu-id="298a5-225">For Layout records, the total number of nodes under the relayout root \(the node that Microsoft Edge starts the relayout\).</span></span> |  
| <span data-ttu-id="298a5-226">レイアウトの範囲</span><span class="sxs-lookup"><span data-stu-id="298a5-226">Layout scope</span></span> | <span data-ttu-id="298a5-227">可能な値は `Partial` \ (再レイアウトの境界は DOM の一部) または `Whole document` です。</span><span class="sxs-lookup"><span data-stu-id="298a5-227">Possible values are `Partial` \(the re-layout boundary is a portion of the DOM\) or `Whole document`.</span></span> |  
| <span data-ttu-id="298a5-228">影響を受ける要素</span><span class="sxs-lookup"><span data-stu-id="298a5-228">Elements affected</span></span> | <span data-ttu-id="298a5-229">スタイルの再計算には、スタイル再計算によって影響を受ける要素の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="298a5-229">For Recalculate style records, the number of elements affected by a style recalculation.</span></span> |  
| <span data-ttu-id="298a5-230">無効になったスタイル</span><span class="sxs-lookup"><span data-stu-id="298a5-230">Styles invalidated</span></span> | <span data-ttu-id="298a5-231">スタイルレコードの再計算には、スタイルの無効化を引き起こしたコードのスタックトレースを提供します。</span><span class="sxs-lookup"><span data-stu-id="298a5-231">For Recalculate style records, provides the stack trace of the code that caused the style invalidation.</span></span> |  

## <span data-ttu-id="298a5-232">描画イベント</span><span class="sxs-lookup"><span data-stu-id="298a5-232">Painting events</span></span>  

<span data-ttu-id="298a5-233">このセクションには、Painting カテゴリとそのプロパティに属するイベントが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="298a5-233">This section lists events that belong to Painting category and their properties.</span></span>  

| <span data-ttu-id="298a5-234">イベント</span><span class="sxs-lookup"><span data-stu-id="298a5-234">Event</span></span> | <span data-ttu-id="298a5-235">説明</span><span class="sxs-lookup"><span data-stu-id="298a5-235">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="298a5-236">複合レイヤー</span><span class="sxs-lookup"><span data-stu-id="298a5-236">Composite Layers</span></span> | <span data-ttu-id="298a5-237">Microsoft Edge レンダリングエンジン用の合成画像レイヤー。</span><span class="sxs-lookup"><span data-stu-id="298a5-237">The composited image layers for the Microsoft Edge rendering engine.</span></span> |  
| <span data-ttu-id="298a5-238">画像のデコード</span><span class="sxs-lookup"><span data-stu-id="298a5-238">Image Decode</span></span> | <span data-ttu-id="298a5-239">画像リソースがデコードされました。</span><span class="sxs-lookup"><span data-stu-id="298a5-239">An image resource was decoded.</span></span> |  
| <span data-ttu-id="298a5-240">画像のサイズ変更</span><span class="sxs-lookup"><span data-stu-id="298a5-240">Image Resize</span></span> | <span data-ttu-id="298a5-241">画像がネイティブの寸法からサイズ変更されました。</span><span class="sxs-lookup"><span data-stu-id="298a5-241">An image was resized from its native dimensions.</span></span> |  
| <span data-ttu-id="298a5-242">ペイント</span><span class="sxs-lookup"><span data-stu-id="298a5-242">Paint</span></span> | <span data-ttu-id="298a5-243">合成レイヤーは、ディスプレイの領域に対して描画されました。</span><span class="sxs-lookup"><span data-stu-id="298a5-243">Composited layers were painted to a region of the display.</span></span>  <span data-ttu-id="298a5-244">ペイントレコードの上にマウスポインターを置くと、更新されたディスプレイの領域が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="298a5-244">Hovering over a Paint record highlights the region of the display that was updated.</span></span> |  

### <span data-ttu-id="298a5-245">Painting イベントプロパティ</span><span class="sxs-lookup"><span data-stu-id="298a5-245">Painting event properties</span></span>  

| <span data-ttu-id="298a5-246">プロパティ</span><span class="sxs-lookup"><span data-stu-id="298a5-246">Property</span></span> | <span data-ttu-id="298a5-247">説明</span><span class="sxs-lookup"><span data-stu-id="298a5-247">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="298a5-248">場所</span><span class="sxs-lookup"><span data-stu-id="298a5-248">Location</span></span> | <span data-ttu-id="298a5-249">Paint イベントの場合は、ペイントの四角形の x 座標と y 座標を使用します。</span><span class="sxs-lookup"><span data-stu-id="298a5-249">For Paint events, the x and y coordinates of the paint rectangle.</span></span> |  
| <span data-ttu-id="298a5-250">各</span><span class="sxs-lookup"><span data-stu-id="298a5-250">Dimensions</span></span> | <span data-ttu-id="298a5-251">Paint イベントの場合は、塗装領域の高さと幅。</span><span class="sxs-lookup"><span data-stu-id="298a5-251">For Paint events, the height and width of the painted region.</span></span> |  

 



<!-- image links -->  

<!-- links -->

[ConsoleApiTime]: /microsoft-edge/devtools-guide-chromium/console/api#time "タイムコンソール API リファレンス"  
[ConsoleApiTimeEnd]: /microsoft-edge/devtools-guide-chromium/console/api#timeend "timeEnd-本体の API リファレンス"  
<!--[EvaluatePerformanceTimelineTool]: timeline-tool "How to Use the Timeline Tool"  -->

[MDNWindowDOMContentLoadedEvent]: https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded "Window: DOMContentLoaded イベント |MDN"  
[MDNWindowOrWorkerGlobalScopeSetInterval]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setInterval "WindowOrWorkerGlobalScope Interval () |MDN"  
[MDNWindowOrWorkerGlobalScopeSetTimeout]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setTimeout "WindowOrWorkerGlobalScope () |MDN"  

> [!NOTE]
> <span data-ttu-id="298a5-257">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="298a5-257">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="298a5-258">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/performance-reference) にあり、 [Meggin Kearney][MegginKearney] \ (Tech Writer \) と [Flavio Copes][FlavioCopes] \ (完全なスタック開発者) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="298a5-258">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/performance-reference) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Flavio Copes][FlavioCopes] \(Full Stack Developer\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="298a5-260">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="298a5-260">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[FlavioCopes]: https://developers.google.com/web/resources/contributors/flaviocopes  
