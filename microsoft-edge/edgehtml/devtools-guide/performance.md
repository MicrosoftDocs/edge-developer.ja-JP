---
description: パフォーマンス パネルを使用して、ユーザー操作中のページの応答性を分析する
title: DevTools - パフォーマンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, パフォーマンス, プロファイル, フレーム レート, fps, CPU 使用率, JavaScript の実行
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 561cfe62f7db492ce3914b4daba8ccf8c0a62a8a
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234471"
---
# <span data-ttu-id="7681f-104">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="7681f-104">Performance</span></span>

<span data-ttu-id="7681f-105">パフォーマンス **パネル** には、ユーザー操作中の UI の応答性をプロファイリングおよび分析するためのツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="7681f-105">The **Performance** panel offers tools for profiling and analyzing the responsiveness of your UI during the course of user interaction.</span></span> <span data-ttu-id="7681f-106">この方法を使用すると、次の方法を行います。</span><span class="sxs-lookup"><span data-stu-id="7681f-106">With it, you can:</span></span>

 - <span data-ttu-id="7681f-107">[ページのさまざまなコンポーネント](#recording-a-profile) の実行時間を測定する</span><span class="sxs-lookup"><span data-stu-id="7681f-107">[Measure execution times](#recording-a-profile) of the various components of your page</span></span> 
 - <span data-ttu-id="7681f-108">[ページを実行するために最も多](#timeline-ruler) くの CPU サイクルを費やしている場所にドリルダウンし、結果としてユーザーに表示効果を与える</span><span class="sxs-lookup"><span data-stu-id="7681f-108">[Drill down to where you're spending the most CPU cycles](#timeline-ruler) to run your page and the resulting visual effect for your users</span></span>
 - <span data-ttu-id="7681f-109">[ページの実行時間を消費するプロセスの詳細を](#timeline-details) ステップバイステップで取得する</span><span class="sxs-lookup"><span data-stu-id="7681f-109">[Get a step-by-step breakdown of the processes](#timeline-details) consuming page execution time</span></span> 
 - <span data-ttu-id="7681f-110">[レイアウトの再計算が必要な](#javascript-call-stacks) 操作など、コストのかかる操作を識別するために JavaScript の呼び出し履歴を確認する</span><span class="sxs-lookup"><span data-stu-id="7681f-110">[Walk your JavaScript call stacks](#javascript-call-stacks) to identify costly operations, such as those requiring layout recalculations</span></span> 

![DevTools パフォーマンス パネル](./media/performance.png)

## <span data-ttu-id="7681f-112">プロファイルの記録</span><span class="sxs-lookup"><span data-stu-id="7681f-112">Recording a profile</span></span>

<span data-ttu-id="7681f-113">ページのパフォーマンスを分析する最初の手順は、特定のユーザー シナリオを実行する際にプロファイルをキャプチャする手順です。たとえば、修正しようとしているパフォーマンス バグの再確認手順や、ユーザー エクスペリエンスを向上するために最適化する一般的な使用例です。</span><span class="sxs-lookup"><span data-stu-id="7681f-113">The first step to analyzing the performance of your page is to capture a profile as you perform a particular user scenario, such as the repro steps of a performance bug you're trying to fix, or a typical use case you want to optimize for a better user experience.</span></span> 

### <span data-ttu-id="7681f-114">ツール バー</span><span class="sxs-lookup"><span data-stu-id="7681f-114">Toolbar</span></span>

<span data-ttu-id="7681f-115">パフォーマンス トレース**を**  /  **開始**および終了するには、ツール バー (または) の [開始停止] `Ctrl+E` ボタンを使用します。</span><span class="sxs-lookup"><span data-stu-id="7681f-115">Use the **Start** / **Stop** buttons on the toolbar (or `Ctrl+E`) to initiate and conclude your performance trace.</span></span> <span data-ttu-id="7681f-116">緑色のインジケーターが [パフォーマンス] タブに表示されます。記録が進行中です。</span><span class="sxs-lookup"><span data-stu-id="7681f-116">A green indicator will apear on the **Performance** tab to indicate a recording is in progress.</span></span> 

![パフォーマンス パネルツール バー](./media/performance_toolbar.png)

<span data-ttu-id="7681f-118">プロファイルを停止すると、パフォーマンス レポートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="7681f-118">A performance report will generate upon stopping the profile.</span></span> <span data-ttu-id="7681f-119">後で DevTools でディスク ( ) に保存し、再読み込 `Ctrl+S` み ( `Ctrl+O` ) することができます。</span><span class="sxs-lookup"><span data-stu-id="7681f-119">You can choose to save it to disk (`Ctrl+S`) and reload (`Ctrl+O`) in  DevTools at a later time.</span></span>  <span data-ttu-id="7681f-120">DevTools 診断セッションは *、.diagsession 拡張機能と一緒に保存* されます。</span><span class="sxs-lookup"><span data-stu-id="7681f-120">DevTools diagnostic sessions are saved with the *.diagsession* extension.</span></span>

<span data-ttu-id="7681f-121">プロファイルを記録する際に注意する必要があるいくつかのことを次に示します。</span><span class="sxs-lookup"><span data-stu-id="7681f-121">Here are some things to keep in mind when recording a profile:</span></span>

- <span data-ttu-id="7681f-122">分析しようとしているシナリオをキャプチャするために必要な操作を最も少なくします。</span><span class="sxs-lookup"><span data-stu-id="7681f-122">Perform the fewest actions you need to capture the scenario you're trying to analyze.</span></span> <span data-ttu-id="7681f-123">ページに対する余分な操作により、余分なデータが生成され、結果が乱雑になります。</span><span class="sxs-lookup"><span data-stu-id="7681f-123">Extraneous actions with the page will produce extra data and clutter your results.</span></span>

- <span data-ttu-id="7681f-124">プロファイラーは、ページ ナビゲーション [、DOMContentLoaded、](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded)ページ読み込みなど、レポート内の主要なアプリ ライフサイクル イベントを自動的にマーク [します](https://developer.mozilla.org/docs/Web/Events/load)。</span><span class="sxs-lookup"><span data-stu-id="7681f-124">The profiler will automatically mark major app lifecycle events in the report, such as page navigation, [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded), and page [load](https://developer.mozilla.org/docs/Web/Events/load).</span></span> <span data-ttu-id="7681f-125">カスタム マーカーを追加するには、コードまたはコンソール内から [Performance.mark()](https://developer.mozilla.org/docs/Web/API/Performance/mark) メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="7681f-125">You can add custom markers by calling the [Performance.mark()](https://developer.mozilla.org/docs/Web/API/Performance/mark) method from within your code or the console.</span></span> 

- <span data-ttu-id="7681f-126">初期ページの読み込み時間が分析に重要な場合は、(ネットワーク パネルから[](./network.md)) ブラウザーのキャッシュをクリアして、すべてのページ リソースがネットワークから読み込み中である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7681f-126">If initial page load times are important to your analysis, make sure to clear your browser cache (from the [Network](./network.md) panel) to ensure all page resources are loading from the network.</span></span>

- <span data-ttu-id="7681f-127">場合によっては、複数のセッションを記録したり、異なるコンピューター間で同じシナリオをサンプルしたりして、パフォーマンスの問題を大自然に理解するのに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="7681f-127">Sometimes it helps to record multiple sessions and/or sample the same scenario across different machines to better understand the performance issue in the wild.</span></span>

## <span data-ttu-id="7681f-128">タイムライン ルーラー</span><span class="sxs-lookup"><span data-stu-id="7681f-128">Timeline ruler</span></span>

<span data-ttu-id="7681f-129">タイムラインはスライド ルーラーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="7681f-129">The timeline works as a sliding ruler.</span></span> <span data-ttu-id="7681f-130">レポートの範囲を対象の特定の期間 (またはイベントの範囲) に制限するために使用します。</span><span class="sxs-lookup"><span data-stu-id="7681f-130">Use it to limit the scope of the report to the particular timeframe (or span of events) of interest.</span></span> <span data-ttu-id="7681f-131">黒の **スライド** コントロールをドラッグして、調査する時間範囲を制限し、下部の [詳細] ウィンドウの [Timeline](#timeline-details) および [JavaScript](#javascript-call-stacks) コール スタック レポートから余分なプロファイリング データをフィルターで取り出 *します*。</span><span class="sxs-lookup"><span data-stu-id="7681f-131">Drag the black **slide controls** to limit the time range you wish to investigate and filter out extraneous profiling data from the [Timeline](#timeline-details) and [JavaScript call stacks](#javascript-call-stacks) reports in the lower *Details pane*.</span></span> 

<span data-ttu-id="7681f-132">ルーラーには次の 2 種類のマーカーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7681f-132">You will see two types of markers on the ruler:</span></span>

 - <span data-ttu-id="7681f-133">**タイムライン上のアプリ** のライフサイクル マーク (ページ ナビゲーション [、DOMContentLoaded、](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded)ページ読み込 [みなど)](https://developer.mozilla.org/docs/Web/Events/load)は、プロファイルを記録すると自動的に記録されます。</span><span class="sxs-lookup"><span data-stu-id="7681f-133">**App lifecycle marks** on the timeline (such as page navigation, [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded), and page [load](https://developer.mozilla.org/docs/Web/Events/load)) are automatically logged as you record a profile.</span></span>

 - <span data-ttu-id="7681f-134">**ユーザー マーク** は、コード内または DevTools コンソールから [Performance.mark()](https://developer.mozilla.org/docs/Web/API/Performance/mark) メソッドを呼び出して追加できるカスタム マーカー [**です**](./console.md)。</span><span class="sxs-lookup"><span data-stu-id="7681f-134">**User marks** are custom markers you can choose to add  with calls to the [Performance.mark()](https://developer.mozilla.org/docs/Web/API/Performance/mark) method from within your code or the  DevTools [**Console**](./console.md).</span></span> <span data-ttu-id="7681f-135">Performance.measure() メソッド*を使用すると*、開始マークと終了マークを 1 つの名前付[きのメジャーとしてグループ化](https://developer.mozilla.org/docs/Web/API/Performance/measure)できます。</span><span class="sxs-lookup"><span data-stu-id="7681f-135">You can group *start* and *end* marks together as a single, named measure with the [Performance.measure()](https://developer.mozilla.org/docs/Web/API/Performance/measure) method.</span></span> 

<span data-ttu-id="7681f-136">時間範囲を選択した後は、ツールバーからさらに拡大表示するか、ズームと選択解除 をリセットして パフォーマンス トレースの完全なビューに戻ります (時間範囲は選択されません)。 </span><span class="sxs-lookup"><span data-stu-id="7681f-136">Once you have selected a time range, you can further **Zoom in** from the toolbar, or **Reset zoom** and **Clear selection** to return to the full view of the performance trace (with no time range selected).</span></span> <span data-ttu-id="7681f-137">これらのコントロールは、右クリックのコンテキスト メニューから使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="7681f-137">These controls are also available from the right-click context menu.</span></span>

![パフォーマンス パネルのタイムライン](./media/performance_timeline.png)

### <span data-ttu-id="7681f-139">CPU 使用率</span><span class="sxs-lookup"><span data-stu-id="7681f-139">CPU utilization</span></span>

<span data-ttu-id="7681f-140">**CPU 使用率 % タイムライン**グラフは、ページの実行に必要なさまざまなブラウザー サブシステムによって消費される処理リソースを、カテゴリ別に示しています。</span><span class="sxs-lookup"><span data-stu-id="7681f-140">The **CPU utilization %** timeline graph describes the processing resources consumed by the various browser subsystems required to run the page, broken out by category:</span></span>

#### <span data-ttu-id="7681f-141">読み込み中</span><span class="sxs-lookup"><span data-stu-id="7681f-141">Loading</span></span>
<span data-ttu-id="7681f-142">アプリ リソースの取得と HTML と CSS の解析に費やした時間を示します。</span><span class="sxs-lookup"><span data-stu-id="7681f-142">Indicates time spent retrieving app resources and parsing HTML and CSS.</span></span> <span data-ttu-id="7681f-143">これには、ネットワーク要求が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7681f-143">This can include network requests.</span></span> <span data-ttu-id="7681f-144">タイムラインには、次の関連イベントが記録 [されます](#timeline-details)。</span><span class="sxs-lookup"><span data-stu-id="7681f-144">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="7681f-145">イベント</span><span class="sxs-lookup"><span data-stu-id="7681f-145">Event</span></span> | <span data-ttu-id="7681f-146">説明</span><span class="sxs-lookup"><span data-stu-id="7681f-146">Description</span></span>
:------------ | :-------------
<span data-ttu-id="7681f-147">CssParsing</span><span class="sxs-lookup"><span data-stu-id="7681f-147">CssParsing</span></span>  | <span data-ttu-id="7681f-148">解析が必要な新しい CSS コンテンツが検出されました。</span><span class="sxs-lookup"><span data-stu-id="7681f-148">New CSS content was encountered that needed to be parsed.</span></span>
<span data-ttu-id="7681f-149">HtmlParsing</span><span class="sxs-lookup"><span data-stu-id="7681f-149">HtmlParsing</span></span> | <span data-ttu-id="7681f-150">ノードに解析して DOM に挿入する必要がある新しい HTML コンテンツが検出されました。</span><span class="sxs-lookup"><span data-stu-id="7681f-150">New HTML content was encountered that needed to be parsed into nodes and inserted into the DOM.</span></span>
<span data-ttu-id="7681f-151">HttpRequest</span><span class="sxs-lookup"><span data-stu-id="7681f-151">HttpRequest</span></span> | <span data-ttu-id="7681f-152">DOM でリモート リソースが検出されたか、HTTP 要求を行う必要がある XMLHttpRequest が作成されました。</span><span class="sxs-lookup"><span data-stu-id="7681f-152">A remote resource was encountered in the DOM or an XMLHttpRequest was created that required an HTTP request to be made.</span></span>
<span data-ttu-id="7681f-153">HtmlSpeculativeDownloading</span><span class="sxs-lookup"><span data-stu-id="7681f-153">HtmlSpeculativeDownloading</span></span> | <span data-ttu-id="7681f-154">ページの HTML コンテンツは、HTTP 要求を可能な限り迅速にスケジュールするために必要なリソースを検索しています。</span><span class="sxs-lookup"><span data-stu-id="7681f-154">The page's HTML content was being searched for required resources so that the HTTP requests for them could be scheduled as quickly as possible.</span></span>


#### <span data-ttu-id="7681f-155">スクリプト</span><span class="sxs-lookup"><span data-stu-id="7681f-155">Scripting</span></span>
<span data-ttu-id="7681f-156">JavaScript の解析と実行に費やした時間を示します。</span><span class="sxs-lookup"><span data-stu-id="7681f-156">Indicates time spent parsing and executing JavaScript.</span></span> <span data-ttu-id="7681f-157">これには、DOM イベント、タイマー、スクリプト評価、およびアニメーション フレーム コールバックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7681f-157">This includes DOM events, timers, script evaluation, and animation frame callbacks.</span></span> <span data-ttu-id="7681f-158">タイムラインには、次の関連イベントが記録 [されます](#timeline-details)。</span><span class="sxs-lookup"><span data-stu-id="7681f-158">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="7681f-159">イベント</span><span class="sxs-lookup"><span data-stu-id="7681f-159">Event</span></span> | <span data-ttu-id="7681f-160">説明</span><span class="sxs-lookup"><span data-stu-id="7681f-160">Description</span></span>
:------------ | :-------------
<span data-ttu-id="7681f-161">DomEvent</span><span class="sxs-lookup"><span data-stu-id="7681f-161">DomEvent</span></span> | <span data-ttu-id="7681f-162">DOM オブジェクトでイベントが発生しました。</span><span class="sxs-lookup"><span data-stu-id="7681f-162">An event was fired on a DOM object.</span></span>
<span data-ttu-id="7681f-163">EvaluatingScript</span><span class="sxs-lookup"><span data-stu-id="7681f-163">EvaluatingScript</span></span> | <span data-ttu-id="7681f-164">DOM `<script>` で新しい要素が検出され、解析と実行が必要でした。</span><span class="sxs-lookup"><span data-stu-id="7681f-164">A new `<script>` element was encountered in the DOM and needed to be parsed and executed.</span></span>
<span data-ttu-id="7681f-165">EventHandler</span><span class="sxs-lookup"><span data-stu-id="7681f-165">EventHandler</span></span> | <span data-ttu-id="7681f-166">登録されたイベント リスナーは、DOM イベントが発生した場合に応答してトリガーされました。</span><span class="sxs-lookup"><span data-stu-id="7681f-166">A registered event listener was triggered in response to a DOM event being fired.</span></span>
<span data-ttu-id="7681f-167">フレーム</span><span class="sxs-lookup"><span data-stu-id="7681f-167">Frame</span></span> | <span data-ttu-id="7681f-168">新しいフレームの準備中に、登録されたコールバックがトリガーされ、視覚的な変更が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7681f-168">While a new frame was being prepared a registered callback was triggered so that it could contribute visual changes.</span></span>
<span data-ttu-id="7681f-169">測定値</span><span class="sxs-lookup"><span data-stu-id="7681f-169">Measure</span></span> | <span data-ttu-id="7681f-170">アプリ固有のシナリオは、このメソッドを使用して測定 `performance.measure()` されました。</span><span class="sxs-lookup"><span data-stu-id="7681f-170">An app-specific scenario was measured using the `performance.measure()` method.</span></span>
<span data-ttu-id="7681f-171">MediaQueryListener</span><span class="sxs-lookup"><span data-stu-id="7681f-171">MediaQueryListener</span></span> | <span data-ttu-id="7681f-172">登録されたメディア クエリが無効にされ、関連付けられたリスナーが実行されました。</span><span class="sxs-lookup"><span data-stu-id="7681f-172">A registered media query was invalidated which resulted in the execution of its associated listener(s).</span></span>
<span data-ttu-id="7681f-173">MutationObserver</span><span class="sxs-lookup"><span data-stu-id="7681f-173">MutationObserver</span></span> | <span data-ttu-id="7681f-174">1 つ以上の確認済み DOM 要素が変更され、その結果、CallbackObserver に関連付けられたコールバックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="7681f-174">One or more observed DOM elements were modified which resulted in the execution of a MutationObserver's associated callback.</span></span>
<span data-ttu-id="7681f-175">TimerFired</span><span class="sxs-lookup"><span data-stu-id="7681f-175">TimerFired</span></span> | <span data-ttu-id="7681f-176">スケジュールされたタイマーが経過し、関連付けられたコールバックが実行されました。</span><span class="sxs-lookup"><span data-stu-id="7681f-176">A scheduled timer elapsed which resulted in the execution of its associated callback.</span></span>
<span data-ttu-id="7681f-177">WindowsRuntimeAsyncCallback</span><span class="sxs-lookup"><span data-stu-id="7681f-177">WindowsRuntimeAsyncCallback</span></span> | <span data-ttu-id="7681f-178">非同期操作は、コールバックをトリガーした Windows ランタイム オブジェクトによって完了 `Promise` しました。</span><span class="sxs-lookup"><span data-stu-id="7681f-178">An async operation was completed by a Windows Runtime object which triggered a `Promise` callback.</span></span>
<span data-ttu-id="7681f-179">WindowsRuntimeEvent</span><span class="sxs-lookup"><span data-stu-id="7681f-179">WindowsRuntimeEvent</span></span> | <span data-ttu-id="7681f-180">登録されたリスナーをトリガーした Windows ランタイム オブジェクトでイベントが発生しました。</span><span class="sxs-lookup"><span data-stu-id="7681f-180">An event was fired on a Windows Runtime object which triggered a registered listener.</span></span>

#### <span data-ttu-id="7681f-181">GC</span><span class="sxs-lookup"><span data-stu-id="7681f-181">GC</span></span>
<span data-ttu-id="7681f-182">使用されなくなったオブジェクトのメモリ収集に費やした時間を示します。</span><span class="sxs-lookup"><span data-stu-id="7681f-182">Indicates time spent collecting memory for objects that are no longer in use.</span></span> <span data-ttu-id="7681f-183">タイムラインには、次の関連イベントが記録 [されます](#timeline-details)。</span><span class="sxs-lookup"><span data-stu-id="7681f-183">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="7681f-184">イベント</span><span class="sxs-lookup"><span data-stu-id="7681f-184">Event</span></span> | <span data-ttu-id="7681f-185">説明</span><span class="sxs-lookup"><span data-stu-id="7681f-185">Description</span></span>
:------------ | :-------------
<span data-ttu-id="7681f-186">ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="7681f-186">GarbageCollection</span></span> | <span data-ttu-id="7681f-187">JavaScript ランタイムは、参照されなくなったオブジェクトを特定するために、アプリの現在のメモリ使用量を監査しました。そのため、どのオブジェクトが収集される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7681f-187">The JavaScript runtime audited the app's current memory usage in order to determine which objects aren't being referenced anymore and could therefore be collected.</span></span>

#### <span data-ttu-id="7681f-188">スタイル設定</span><span class="sxs-lookup"><span data-stu-id="7681f-188">Styling</span></span>
<span data-ttu-id="7681f-189">要素のプレゼンテーションとレイアウトの計算に費やした時間を示します。</span><span class="sxs-lookup"><span data-stu-id="7681f-189">Indicates time spent calculating element presentation and layout.</span></span> <span data-ttu-id="7681f-190">タイムラインには、次の関連イベントが記録 [されます](#timeline-details)。</span><span class="sxs-lookup"><span data-stu-id="7681f-190">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="7681f-191">イベント</span><span class="sxs-lookup"><span data-stu-id="7681f-191">Event</span></span> | <span data-ttu-id="7681f-192">説明</span><span class="sxs-lookup"><span data-stu-id="7681f-192">Description</span></span>
:------------ | :-------------
<span data-ttu-id="7681f-193">AlignedBeat</span><span class="sxs-lookup"><span data-stu-id="7681f-193">AlignedBeat</span></span> | <span data-ttu-id="7681f-194">DOM に対して行われた保留中の視覚的な変更は、アプリの表示を更新するために処理されました。</span><span class="sxs-lookup"><span data-stu-id="7681f-194">Pending visual changes that were made to the DOM were processed so that the app's display could be updated.</span></span>
<span data-ttu-id="7681f-195">CssCalculation</span><span class="sxs-lookup"><span data-stu-id="7681f-195">CssCalculation</span></span> | <span data-ttu-id="7681f-196">DOM に変更が加えられたか、新しい CSS コンテンツが追加され、影響を受けるすべての要素のスタイル プロパティを再計算する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="7681f-196">Changes were made to the DOM or new CSS content was added, requiring the style properties of all affected elements to be recalculated.</span></span>
<span data-ttu-id="7681f-197">レイアウト</span><span class="sxs-lookup"><span data-stu-id="7681f-197">Layout</span></span> | <span data-ttu-id="7681f-198">DOM に変更が加え、影響を受けるすべての要素のサイズや位置を計算する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="7681f-198">Changes were made to the DOM that required the size and/or position of all affected elements to be computed.</span></span>

#### <span data-ttu-id="7681f-199">レンダリング</span><span class="sxs-lookup"><span data-stu-id="7681f-199">Rendering</span></span>
<span data-ttu-id="7681f-200">画面の塗り分けに費やした時間を示します。</span><span class="sxs-lookup"><span data-stu-id="7681f-200">Indicates time spent in painting the screen.</span></span> <span data-ttu-id="7681f-201">タイムラインには、次の関連イベントが記録 [されます](#timeline-details)。</span><span class="sxs-lookup"><span data-stu-id="7681f-201">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="7681f-202">イベント</span><span class="sxs-lookup"><span data-stu-id="7681f-202">Event</span></span> | <span data-ttu-id="7681f-203">説明</span><span class="sxs-lookup"><span data-stu-id="7681f-203">Description</span></span>
:------------ | :-------------
<span data-ttu-id="7681f-204">ペイント</span><span class="sxs-lookup"><span data-stu-id="7681f-204">Paint</span></span> | <span data-ttu-id="7681f-205">DOM に対して視覚的な変更が行われたので、ページの影響を受けるすべての部分を再描画する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="7681f-205">Visual changes were made to the DOM that required all affected portions of the page to be redrawn.</span></span>
<span data-ttu-id="7681f-206">RenderLayer</span><span class="sxs-lookup"><span data-stu-id="7681f-206">RenderLayer</span></span> | <span data-ttu-id="7681f-207">DOM の個別にレンダリングされたフラグメント (レイヤーと呼ばれる) に対して視覚的な変更が行われたので、ページのそれぞれの部分を再描画する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="7681f-207">Visual changes were made to an independently rendered fragment of the DOM (called a layer) which required its respective portion of the page to be redrawn.</span></span>

#### <span data-ttu-id="7681f-208">画像のデコード</span><span class="sxs-lookup"><span data-stu-id="7681f-208">Image decoding</span></span>
<span data-ttu-id="7681f-209">イメージの解凍とデコードに費やした時間を示します。</span><span class="sxs-lookup"><span data-stu-id="7681f-209">Indicates time spent decompressing and decoding images.</span></span> <span data-ttu-id="7681f-210">タイムラインには、次の関連イベントが記録 [されます](#timeline-details)。</span><span class="sxs-lookup"><span data-stu-id="7681f-210">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="7681f-211">イベント</span><span class="sxs-lookup"><span data-stu-id="7681f-211">Event</span></span> | <span data-ttu-id="7681f-212">説明</span><span class="sxs-lookup"><span data-stu-id="7681f-212">Description</span></span>
:------------ | :-------------
<span data-ttu-id="7681f-213">ImageDecoded</span><span class="sxs-lookup"><span data-stu-id="7681f-213">ImageDecoded</span></span> | <span data-ttu-id="7681f-214">イメージは DOM に含まれており、元の形式からビットマップに解凍する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="7681f-214">An image was included into the DOM and needed be to decompressed from its original format into a bitmap.</span></span>

### <span data-ttu-id="7681f-215">視覚的なスループット</span><span class="sxs-lookup"><span data-stu-id="7681f-215">Visual throughput</span></span>

<span data-ttu-id="7681f-216">ビジュアル **スループット (FPS)** グラフは、プロファイリング シナリオの過程で 1 秒あたりの推定 *フレーム数* (FPS) を示します。60 FPS が理想的な表示速度です。</span><span class="sxs-lookup"><span data-stu-id="7681f-216">The **Visual throughput (FPS)** graph shows the estimated *frames per second* (FPS) during the course of the profiling scenario, where 60 FPS is the ideal display rate.</span></span> <span data-ttu-id="7681f-217">フレーム レートのディップはパフォーマンスのボトルネックを示し、フレーム レートがゼロの場合はフレームが完全にドロップされます。</span><span class="sxs-lookup"><span data-stu-id="7681f-217">Dips in the frame rate indicate performance bottlenecks and a frame rate of zero means that frames are getting dropped entirely.</span></span>

## <span data-ttu-id="7681f-218">タイムラインの詳細</span><span class="sxs-lookup"><span data-stu-id="7681f-218">Timeline details</span></span>

<span data-ttu-id="7681f-219">最も下の詳細ウィンドウを使用して、ページで発生した内容の詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="7681f-219">Use the lowermost details pane to get the full breakdown of what happened on the page.</span></span> <span data-ttu-id="7681f-220">[ **タイムラインの詳細]** タブには、さまざまなブラウザー サブシステム内で発生したイベントの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7681f-220">The **Timeline details** tab provides a breakdown of events that occurred within the various browser subsystems.</span></span>

![パフォーマンス タイムラインの詳細ウィンドウ](./media/performance_details_timeline.png)

1. **<span data-ttu-id="7681f-222">イベント リストの並べ替えコントロール</span><span class="sxs-lookup"><span data-stu-id="7681f-222">Event list sort control</span></span>**

    <span data-ttu-id="7681f-223">[並べ**替え]** ドロップダウン コントロールを使用して、[イベント リスト](#event-list)の順序を開始時刻と期間 (含む) の間*で切り替えてください*。</span><span class="sxs-lookup"><span data-stu-id="7681f-223">Use the **Sort by** dropdown control to toggle the [Event list](#event-list) order between *Start time* or *Duration (inclusive*).</span></span> <span data-ttu-id="7681f-224">これにより、選択したタイムラインの詳細 [のビューも変更されます](#selected-timeline-details)。</span><span class="sxs-lookup"><span data-stu-id="7681f-224">This also changes the view of the [Selected timeline details](#selected-timeline-details).</span></span>

2. **<span data-ttu-id="7681f-225">イベントをフレーム別にグループ化する</span><span class="sxs-lookup"><span data-stu-id="7681f-225">Group events by frame</span></span>**

    <span data-ttu-id="7681f-226">フレームトグル でグループ トップ レベル イベントを使用して、アニメーションやビジュアル更新が発生していた期間中に、トップ レベル イベント (HTML 解析、*レイアウト、DOM*イベントなど) を対応する作業単位 (または "フレーム") にグループ化します。</span><span class="sxs-lookup"><span data-stu-id="7681f-226">Use the **Group top level events by frames** toggle to group top-level events (*HTML parsing, Layout, DOM event,* etc.) into their corresponding unit of work (or "frame") during periods of time where animations/visual updates were occurring.</span></span> <span data-ttu-id="7681f-227">フレームは他のイベントと同様に扱われるので、並べ替え/フィルター処理を 行い、イベント リストでクリックすると包括的な時刻の要約[を提供できます](#event-list)。</span><span class="sxs-lookup"><span data-stu-id="7681f-227">The frames are treated like other events, so they can be sorted/filtered and provide an *Inclusive time* summary when clicked in the [Event list](#event-list).</span></span>

3. **<span data-ttu-id="7681f-228">イベント リスト フィルター コントロール</span><span class="sxs-lookup"><span data-stu-id="7681f-228">Event list filter controls</span></span>**

    <span data-ttu-id="7681f-229">[Filter **events] メニューを使用** して、タイムラインの詳細に表示されるイベントの種類を [構成します](#timeline-details)。</span><span class="sxs-lookup"><span data-stu-id="7681f-229">Use the **Filter events** menu to configure the types of events shown in the [timeline details](#timeline-details).</span></span> 

    ![パフォーマンス イベントをフィルター処理する制御](./media/performance_filter_events.png) 

    <span data-ttu-id="7681f-231">次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7681f-231">The following filters are available:</span></span>

   - <span data-ttu-id="7681f-232">**画像デコード**: バックグラウンド スレッドで発生したイベントを表示します (画像のデコード、GC など)。</span><span class="sxs-lookup"><span data-stu-id="7681f-232">**Image decoding**: Show events which occurred on a background thread (e.g. Image decoding, GC).</span></span> 
   - <span data-ttu-id="7681f-233">**ネットワーク トラフィック**: ネットワークにバインドされた HTTP 要求を表示します。</span><span class="sxs-lookup"><span data-stu-id="7681f-233">**Network traffic**: Show HTTP requests which were network-bound.</span></span>
   - <span data-ttu-id="7681f-234">**UI アクティビティ**: UI スレッドやレンダリング スレッド (DOM イベント ハンドラー、レイアウトなど) で発生したイベントを表示します。</span><span class="sxs-lookup"><span data-stu-id="7681f-234">**UI activity**: Show events which occurred on the UI thread and/or render thread (e.g. DOM event handlers, Layout).</span></span>
   - <span data-ttu-id="7681f-235">**ユーザーメジャー**: performance.measure() メソッドの呼び出しを示すカスタム イベントを表示します。</span><span class="sxs-lookup"><span data-stu-id="7681f-235">**User measures**: Show custom events which indicate calls to the performance.measure() method.</span></span>

     <span data-ttu-id="7681f-236">さらに、包括的な期間でトップ レベルのイベントをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="7681f-236">You can further filter top-level events by their inclusive duration.</span></span>

### <span data-ttu-id="7681f-237">イベント リスト</span><span class="sxs-lookup"><span data-stu-id="7681f-237">Event list</span></span>

<span data-ttu-id="7681f-238">イベント*リストには*、選択した期間中に発生した[](#cpu-utilization)ブラウザー サブシステム イベントの時系列リストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7681f-238">The *Event list* gives you a chronological list of [browser subsystem events](#cpu-utilization) that occurred during the selected span of time.</span></span> 

<span data-ttu-id="7681f-239">任意のエントリをクリックして、そのアイテムの **[選択したイベントの詳細** ] グラフに値を設定します。</span><span class="sxs-lookup"><span data-stu-id="7681f-239">Click on any entry to populate the **Selected event details** chart for that item.</span></span> <span data-ttu-id="7681f-240">入れ子になったイベント/関数を含むエントリには、グラフに表示される包括的な時間(関数とその関数が呼び出した他の関数の実行に費やされた時間) と排他時間 (呼び出し元関数自体の本体内でのみ費やされた時間) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7681f-240">Entries with nested events / functions will show their **inclusive** (time spent executing the function *and* any other functions it called) and **exclusive** (time spent only within the body of the calling function itself) times displayed in the chart.</span></span>

<span data-ttu-id="7681f-241">任意のエントリを右クリックしてコンテキスト メニューを開き、タイムラインをそのイベントにのみフィルター処理し、イベントを担当するソース コードを[**デバッガー**](./debugger.md) [](./elements.md) (該当する場合は [要素] パネル) に表示します。</span><span class="sxs-lookup"><span data-stu-id="7681f-241">Right-click on any entry to open the context menu to filter the timeline to only that event and view the source code responsible for the event in the [**Debugger**](./debugger.md) (or [**Elements**](./elements.md) panel, if applicable).</span></span>

### <span data-ttu-id="7681f-242">選択したタイムラインの詳細</span><span class="sxs-lookup"><span data-stu-id="7681f-242">Selected timeline details</span></span>

<span data-ttu-id="7681f-243">選択 *したタイムラインの詳細は* 、選択した期間中の包括的/排他的なイベント時間の詳細な棒グラフを提供します。</span><span class="sxs-lookup"><span data-stu-id="7681f-243">The *Selected timeline details* provides a detailed bar graph of inclusive/exclusive event times during the selected time span.</span></span> <span data-ttu-id="7681f-244">イベント リストの並べ替えコントロールを 使用して*期間 (* 含む) で並べ替える場合、最も長い実行中のイベントは、このグラフで視覚的に目立っています。</span><span class="sxs-lookup"><span data-stu-id="7681f-244">When you sort by *Duration (inclusive)* using the **Event list sort control**, the longest running events will visually stand out in this chart.</span></span> 

### <span data-ttu-id="7681f-245">選択したイベントの詳細</span><span class="sxs-lookup"><span data-stu-id="7681f-245">Selected event details</span></span>

<span data-ttu-id="7681f-246">このレポートでは、選択したイベントに関する詳細情報を 提供します。これには、開始時刻、実行中のスレッドの 種類 (ダウンロード *、UI、レンダリング*など)、特定のイベントの種類に固有のその他のコンテキスト詳細が含まれるものがあります。</span><span class="sxs-lookup"><span data-stu-id="7681f-246">This report provides further information about the selected event, including *Start time*, the executing thread type (for example, *Download*, *UI*, *Render*), and other contextual details specific to the specific event type.</span></span> <span data-ttu-id="7681f-247">たとえば、イベント リスナー *の種類は* 、コールバック関数とスケジュールの呼び出し履歴 *への* デバッガー *リンクを提供します*。</span><span class="sxs-lookup"><span data-stu-id="7681f-247">For example, *Event listener* types provide debugger links to the *Callback function* and *Scheduling call stack*.</span></span>

## <span data-ttu-id="7681f-248">JavaScript の呼び出し履歴</span><span class="sxs-lookup"><span data-stu-id="7681f-248">JavaScript call stacks</span></span>

![JavaScript 呼び出しスタックのパフォーマンスのタイミング](./media/performance_details_javascript.png)

<span data-ttu-id="7681f-250">**[JavaScript コール スタック]** タブは、選択した時間範囲内で実行されたスクリプト関数の CPU 使用率情報とタイミングを提供します。</span><span class="sxs-lookup"><span data-stu-id="7681f-250">The **JavaScript call stacks** tab provides CPU usage information and timings for the script functions that ran during the selected time range:</span></span>

 <span data-ttu-id="7681f-251">列</span><span class="sxs-lookup"><span data-stu-id="7681f-251">Column</span></span> | <span data-ttu-id="7681f-252">説明</span><span class="sxs-lookup"><span data-stu-id="7681f-252">Description</span></span>
:------------ | :-------------
<span data-ttu-id="7681f-253">関数名</span><span class="sxs-lookup"><span data-stu-id="7681f-253">Function name</span></span> | <span data-ttu-id="7681f-254">ブラウザーまたはユーザー定義関数の名前。</span><span class="sxs-lookup"><span data-stu-id="7681f-254">Name of browser or user-defined function.</span></span>
<span data-ttu-id="7681f-255">包括 CPU (%)</span><span class="sxs-lookup"><span data-stu-id="7681f-255">Inclusive CPU (%)</span></span> | <span data-ttu-id="7681f-256">この関数およびこの関数によって呼び出される関数で選択された CPU アクティビティの割合。</span><span class="sxs-lookup"><span data-stu-id="7681f-256">Percentage of selected CPU activity in this function and in functions called by this function.</span></span>
<span data-ttu-id="7681f-257">排他 CPU (%)</span><span class="sxs-lookup"><span data-stu-id="7681f-257">Exclusive CPU (%)</span></span> | <span data-ttu-id="7681f-258">この関数で呼び出される関数のアクティビティを除く、この関数で選択された CPU アクティビティの割合。</span><span class="sxs-lookup"><span data-stu-id="7681f-258">Percentage of selected CPU activity in this function, excluding activity in functions called by this function.</span></span>
<span data-ttu-id="7681f-259">包括 CPU (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="7681f-259">Inclusive CPU (ms)</span></span> | <span data-ttu-id="7681f-260">この関数およびこの関数によって呼び出される関数でのコードの実行に費やされた CPU 時間。</span><span class="sxs-lookup"><span data-stu-id="7681f-260">CPU time spent executing code in this function and in functions called by this function.</span></span>
<span data-ttu-id="7681f-261">排他的 CPU (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="7681f-261">Exclusive CPU (ms)</span></span> | <span data-ttu-id="7681f-262">この関数で呼び出される関数の時間を除いて、この関数のコードの実行に費やされた CPU 時間。</span><span class="sxs-lookup"><span data-stu-id="7681f-262">CPU time spent executing code in this function, excluding time in functions called by this function.</span></span>
<span data-ttu-id="7681f-263">URL</span><span class="sxs-lookup"><span data-stu-id="7681f-263">URL</span></span> | <span data-ttu-id="7681f-264">スタック フレームが発生した URL。</span><span class="sxs-lookup"><span data-stu-id="7681f-264">URL(s) where stack frame occurred.</span></span> <span data-ttu-id="7681f-265">ブラウザー (標準ベースの Web API) から呼び出される関数呼び出しには *、[DOM] というラベルが付きます*。</span><span class="sxs-lookup"><span data-stu-id="7681f-265">Function calls originating from the browser (standards-based web APIs) are labeled as *[DOM]*.</span></span>

## <span data-ttu-id="7681f-266">ショートカット</span><span class="sxs-lookup"><span data-stu-id="7681f-266">Shortcuts</span></span>

| <span data-ttu-id="7681f-267">操作</span><span class="sxs-lookup"><span data-stu-id="7681f-267">Action</span></span>                         | <span data-ttu-id="7681f-268">ショートカット</span><span class="sxs-lookup"><span data-stu-id="7681f-268">Shortcut</span></span>     |
|:-------------------------------|:-------------|
| <span data-ttu-id="7681f-269">プロファイリング セッションの開始/停止</span><span class="sxs-lookup"><span data-stu-id="7681f-269">Start / Stop profiling session</span></span> | `Ctrl` + `E` |
| <span data-ttu-id="7681f-270">プロファイリング セッションのインポート</span><span class="sxs-lookup"><span data-stu-id="7681f-270">Import profiling session</span></span>       | `Ctrl` + `O` |
| <span data-ttu-id="7681f-271">プロファイリング セッションのエクスポート</span><span class="sxs-lookup"><span data-stu-id="7681f-271">Export profiling session</span></span>       | `Ctrl` + `S` |

## <span data-ttu-id="7681f-272">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7681f-272">Known Issues</span></span>

### <span data-ttu-id="7681f-273">プロファイリング セッションの開始中にエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="7681f-273">An error occurred while starting the profiling session</span></span>

<span data-ttu-id="7681f-274">このエラー メッセージが表示された **場合:** パフォーマンス ツールでプロファイリング セッションの開始中にエラーが発生した場合は、次の手順に従って回避策を確認してください。</span><span class="sxs-lookup"><span data-stu-id="7681f-274">If you see this error message: **An error occurred while starting the profiling session** in the Performance tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="7681f-275">を押 `Windows Key`  +  `R` します。</span><span class="sxs-lookup"><span data-stu-id="7681f-275">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="7681f-276">[ファイル名を指定して実行] ダイアログボックスに **、「services.msc」と入力します**。</span><span class="sxs-lookup"><span data-stu-id="7681f-276">In the Run dialog, enter **services.msc**.</span></span>
![既知の問題-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="7681f-278">Microsoft **(R) Diagnostics Hub Standard Collector Service** を見つけて右クリックします。</span><span class="sxs-lookup"><span data-stu-id="7681f-278">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![既知の問題-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="7681f-280">Microsoft **(R) Diagnostics Hub Standard Collector Service を再起動します**。</span><span class="sxs-lookup"><span data-stu-id="7681f-280">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![既知の問題- 3](./media/known_issues_3.PNG)

5. <span data-ttu-id="7681f-282">Microsoft Edge 開発者ツールとタブを閉じます。新しいタブを開き、ページに移動して、押します `F12` 。</span><span class="sxs-lookup"><span data-stu-id="7681f-282">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="7681f-283">これで、プロファイリングを開始できます。</span><span class="sxs-lookup"><span data-stu-id="7681f-283">You should now be able to begin profiling.</span></span>
![既知の問題- 4](./media/known_issues_4-performance.PNG)

<span data-ttu-id="7681f-285">それでも問題が発生しますか?</span><span class="sxs-lookup"><span data-stu-id="7681f-285">Still running into problems?</span></span> <span data-ttu-id="7681f-286">フィードバックの送信アイコンを使用して、フィードバック **をお送り** ください。</span><span class="sxs-lookup"><span data-stu-id="7681f-286">Please send us your feedback using the **Send feedback** icon!</span></span> 

![既知の問題- 5](./media/known_issues_5.PNG)

### <span data-ttu-id="7681f-288">プロファイリング セッションの停止中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="7681f-288">An error occurred while stopping the profiling session.</span></span>

<span data-ttu-id="7681f-289">このエラー メッセージが表示された **場合:** パフォーマンス ツールでプロファイリング セッションを停止中にエラーが発生した場合は、次の手順に従って回避策を確認してください。</span><span class="sxs-lookup"><span data-stu-id="7681f-289">If you see this error message: **An error occurred while stopping the profiling session** in the Performance tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="7681f-290">を押 `Windows Key`  +  `R` します。</span><span class="sxs-lookup"><span data-stu-id="7681f-290">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="7681f-291">[ファイル名を指定して実行] ダイアログボックスに **、「services.msc」と入力します**。</span><span class="sxs-lookup"><span data-stu-id="7681f-291">In the Run dialog, enter **services.msc**.</span></span>
![既知の問題-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="7681f-293">Microsoft **(R) Diagnostics Hub Standard Collector Service** を見つけて右クリックします。</span><span class="sxs-lookup"><span data-stu-id="7681f-293">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![既知の問題-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="7681f-295">Microsoft **(R) Diagnostics Hub Standard Collector Service を再起動します**。</span><span class="sxs-lookup"><span data-stu-id="7681f-295">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![既知の問題- 3](./media/known_issues_3.PNG)

5. <span data-ttu-id="7681f-297">Microsoft Edge 開発者ツールとタブを閉じます。新しいタブを開き、ページに移動して、押します `F12` 。</span><span class="sxs-lookup"><span data-stu-id="7681f-297">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="7681f-298">これで、プロファイリングを開始できます。</span><span class="sxs-lookup"><span data-stu-id="7681f-298">You should now be able to begin profiling.</span></span>
![既知の問題- 4](./media/known_issues_4-performance.PNG)

<span data-ttu-id="7681f-300">それでも問題が発生しますか?</span><span class="sxs-lookup"><span data-stu-id="7681f-300">Still running into problems?</span></span> <span data-ttu-id="7681f-301">フィードバックの送信アイコンを使用して、フィードバック **をお送り** ください。</span><span class="sxs-lookup"><span data-stu-id="7681f-301">Please send us your feedback using the **Send feedback** icon!</span></span> 

![既知の問題- 5](./media/known_issues_5.PNG)
