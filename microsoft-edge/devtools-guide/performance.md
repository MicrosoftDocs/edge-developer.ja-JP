---
description: '[パフォーマンス] パネルを使用して、ユーザーの操作中にページの responsivenes を分析する'
title: DevTools-パフォーマンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools、パフォーマンス、プロファイル、フレームレート、fps、CPU 使用率、JavaScript 実行
ms.custom: seodec18
ms.openlocfilehash: aecf3cf49592dbf1f24231e76f14ddc2ca1228c3
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569676"
---
# <span data-ttu-id="b74db-104">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="b74db-104">Performance</span></span>

<span data-ttu-id="b74db-105">**パフォーマンス**パネルには、ユーザー操作の過程で UI の応答性をプロファイリングおよび分析するためのツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b74db-105">The **Performance** panel offers tools for profiling and analyzing the responsiveness of your UI during the course of user interaction.</span></span> <span data-ttu-id="b74db-106">これにより、次のことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="b74db-106">With it, you can:</span></span>

 - <span data-ttu-id="b74db-107">ページのさまざまなコンポーネントの[実行時間の測定](#recording-a-profile)</span><span class="sxs-lookup"><span data-stu-id="b74db-107">[Measure execution times](#recording-a-profile) of the various components of your page</span></span> 
 - <span data-ttu-id="b74db-108">ページを実行するための CPU サイクルを最大限に活用し、ユーザーに対して視覚的な効果を得ら[れる場所までドリルダウン](#timeline-ruler)します。</span><span class="sxs-lookup"><span data-stu-id="b74db-108">[Drill down to where you're spending the most CPU cycles](#timeline-ruler) to run your page and the resulting visual effect for your users</span></span>
 - <span data-ttu-id="b74db-109">[プロセスを使用するページ実行時間のステップバイステップの詳細を理解する](#timeline-details)</span><span class="sxs-lookup"><span data-stu-id="b74db-109">[Get a step-by-step breakdown of the processes](#timeline-details) consuming page execution time</span></span> 
 - <span data-ttu-id="b74db-110">[JavaScript の呼び出し履歴をウォーク](#javascript-call-stacks)して、レイアウトの再計算を必要とするものなど、コストの高い操作を特定します。</span><span class="sxs-lookup"><span data-stu-id="b74db-110">[Walk your JavaScript call stacks](#javascript-call-stacks) to identify costly operations, such as those requiring layout recalculations</span></span> 

![DevTools のパフォーマンスパネル](./media/performance.png)

## <span data-ttu-id="b74db-112">プロファイルの記録</span><span class="sxs-lookup"><span data-stu-id="b74db-112">Recording a profile</span></span>

<span data-ttu-id="b74db-113">ページのパフォーマンスを分析するための最初の手順は、特定のユーザーシナリオを実行するときにプロファイルをキャプチャすることです。たとえば、修正しようとしているパフォーマンスバグの再現手順や、ユーザーエクスペリエンスを向上させるために最適化する一般的なユースケースなどです。</span><span class="sxs-lookup"><span data-stu-id="b74db-113">The first step to analyzing the performance of your page is to capture a profile as you perform a particular user scenario, such as the repro steps of a performance bug you're trying to fix, or a typical use case you want to optimize for a better user experience.</span></span> 

### <span data-ttu-id="b74db-114">ツール バー</span><span class="sxs-lookup"><span data-stu-id="b74db-114">Toolbar</span></span>

<span data-ttu-id="b74db-115">**Start**  /  **Stop**ツールバーの [スタート] ボタン (または) を使って、 `Ctrl+E` パフォーマンス追跡を開始および終了します。</span><span class="sxs-lookup"><span data-stu-id="b74db-115">Use the **Start** / **Stop** buttons on the toolbar (or `Ctrl+E`) to initiate and conclude your performance trace.</span></span> <span data-ttu-id="b74db-116">[**パフォーマンス**] タブに緑色のインジケーターが表示され、レコーディングが進行中であることを示します。</span><span class="sxs-lookup"><span data-stu-id="b74db-116">A green indicator will apear on the **Performance** tab to indicate a recording is in progress.</span></span> 

![パフォーマンスパネルのツールバー](./media/performance_toolbar.png)

<span data-ttu-id="b74db-118">プロファイルを停止すると、パフォーマンスレポートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b74db-118">A performance report will generate upon stopping the profile.</span></span> <span data-ttu-id="b74db-119">`Ctrl+S`後で DevTools で disk () と reload () に保存することを選択でき `Ctrl+O` ます。</span><span class="sxs-lookup"><span data-stu-id="b74db-119">You can choose to save it to disk (`Ctrl+S`) and reload (`Ctrl+O`) in  DevTools at a later time.</span></span>  <span data-ttu-id="b74db-120">DevTools 診断セッションは、 *diagsession*拡張子を付けて保存されます。</span><span class="sxs-lookup"><span data-stu-id="b74db-120">DevTools diagnostic sessions are saved with the *.diagsession* extension.</span></span>

<span data-ttu-id="b74db-121">プロファイルを記録する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b74db-121">Here are some things to keep in mind when recording a profile:</span></span>

- <span data-ttu-id="b74db-122">分析しようとしているシナリオを捕捉するために必要な最小限のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="b74db-122">Perform the fewest actions you need to capture the scenario you're trying to analyze.</span></span> <span data-ttu-id="b74db-123">このページで余分な操作を行うと、余分なデータが生成され、結果が乱雑になります。</span><span class="sxs-lookup"><span data-stu-id="b74db-123">Extraneous actions with the page will produce extra data and clutter your results.</span></span>

- <span data-ttu-id="b74db-124">プロファイラーは、ページナビゲーション、 [Domcontentloaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded)、ページの[読み込み](https://developer.mozilla.org/docs/Web/Events/load)など、レポート内の主要なアプリのライフサイクルイベントを自動的にマークします。</span><span class="sxs-lookup"><span data-stu-id="b74db-124">The profiler will automatically mark major app lifecycle events in the report, such as page navigation, [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded), and page [load](https://developer.mozilla.org/docs/Web/Events/load).</span></span> <span data-ttu-id="b74db-125">カスタムマーカーを追加するには、コードまたは本体の中から[Performance. マーク ()](https://developer.mozilla.org/docs/Web/API/Performance/mark)メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b74db-125">You can add custom markers by calling the [Performance.mark()](https://developer.mozilla.org/docs/Web/API/Performance/mark) method from within your code or the console.</span></span> 

- <span data-ttu-id="b74db-126">分析で最初のページ読み込み時間が重要な場合は、すべてのページリソースがネットワークから読み込まれるように、([ネットワーク](./network.md)パネルから) ブラウザキャッシュをクリアしてください。</span><span class="sxs-lookup"><span data-stu-id="b74db-126">If initial page load times are important to your analysis, make sure to clear your browser cache (from the [Network](./network.md) panel) to ensure all page resources are loading from the network.</span></span>

- <span data-ttu-id="b74db-127">また、複数のセッションを記録したり、異なるマシン間で同じシナリオをサンプリングして、ワイルドカードによるパフォーマンスの問題について理解しやすくすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b74db-127">Sometimes it helps to record multiple sessions and/or sample the same scenario across different machines to better understand the performance issue in the wild.</span></span>

## <span data-ttu-id="b74db-128">タイムラインルーラー</span><span class="sxs-lookup"><span data-stu-id="b74db-128">Timeline ruler</span></span>

<span data-ttu-id="b74db-129">タイムラインは、スライディングルーラーとして動作します。</span><span class="sxs-lookup"><span data-stu-id="b74db-129">The timeline works as a sliding ruler.</span></span> <span data-ttu-id="b74db-130">レポートの範囲を、関心のある特定の時間 (または一連のイベント) に制限する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="b74db-130">Use it to limit the scope of the report to the particular timeframe (or span of events) of interest.</span></span> <span data-ttu-id="b74db-131">黒い**スライドコントロール**をドラッグして、調査する時間の範囲を制限し、低い [*詳細] ウィンドウ*の[タイムライン](#timeline-details)と[JavaScript の呼び出し履歴](#javascript-call-stacks)レポートから不要なプロファイリングデータをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="b74db-131">Drag the black **slide controls** to limit the time range you wish to investigate and filter out extraneous profiling data from the [Timeline](#timeline-details) and [JavaScript call stacks](#javascript-call-stacks) reports in the lower *Details pane*.</span></span> 

<span data-ttu-id="b74db-132">ルーラーには2種類のマーカーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b74db-132">You will see two types of markers on the ruler:</span></span>

 - <span data-ttu-id="b74db-133">タイムライン上の**アプリのライフサイクルマーク**(ページナビゲーション、 [domcontentloaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded)、ページ[読み込み](https://developer.mozilla.org/docs/Web/Events/load)など) は、プロファイルの記録時に自動的に記録されます。</span><span class="sxs-lookup"><span data-stu-id="b74db-133">**App lifecycle marks** on the timeline (such as page navigation, [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded), and page [load](https://developer.mozilla.org/docs/Web/Events/load)) are automatically logged as you record a profile.</span></span>

 - <span data-ttu-id="b74db-134">**ユーザーマーク**はカスタムマーカーであり、コードまたは Devtools[**コンソール**](./console.md)内から[Performance. mark ()](https://developer.mozilla.org/docs/Web/API/Performance/mark)メソッドへの呼び出しを追加することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b74db-134">**User marks** are custom markers you can choose to add  with calls to the [Performance.mark()](https://developer.mozilla.org/docs/Web/API/Performance/mark) method from within your code or the  DevTools [**Console**](./console.md).</span></span> <span data-ttu-id="b74db-135">[Measure ()](https://developer.mozilla.org/docs/Web/API/Performance/measure)メソッドを使って、1つの名前付きメジャーとして、*開始*と*終了*のマークをまとめてグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="b74db-135">You can group *start* and *end* marks together as a single, named measure with the [Performance.measure()](https://developer.mozilla.org/docs/Web/API/Performance/measure) method.</span></span> 

<span data-ttu-id="b74db-136">時間範囲を選択すると、ツールバーからさら**に拡大**することができます。または、[ズーム] と [**クリア**] を**リセット**すると、パフォーマンストレースの完全なビューに戻ります (時間範囲を選択していない場合)。</span><span class="sxs-lookup"><span data-stu-id="b74db-136">Once you have selected a time range, you can further **Zoom in** from the toolbar, or **Reset zoom** and **Clear selection** to return to the full view of the performance trace (with no time range selected).</span></span> <span data-ttu-id="b74db-137">これらのコントロールは、右クリックのコンテキストメニューからも利用できます。</span><span class="sxs-lookup"><span data-stu-id="b74db-137">These controls are also available from the right-click context menu.</span></span>

![パフォーマンスパネルのタイムライン](./media/performance_timeline.png)

### <span data-ttu-id="b74db-139">CPU 使用率</span><span class="sxs-lookup"><span data-stu-id="b74db-139">CPU utilization</span></span>

<span data-ttu-id="b74db-140">**CPU 使用率の%** タイムライングラフは、カテゴリ別に分類されてページを実行するために必要なさまざまなブラウザーサブシステムによって消費される処理リソースを示しています。</span><span class="sxs-lookup"><span data-stu-id="b74db-140">The **CPU utilization %** timeline graph describes the processing resources consumed by the various browser subsystems required to run the page, broken out by category:</span></span>

#### <span data-ttu-id="b74db-141">読み込み中</span><span class="sxs-lookup"><span data-stu-id="b74db-141">Loading</span></span>
<span data-ttu-id="b74db-142">アプリリソースの取得と HTML および CSS の解析に費やされた時間を示します。</span><span class="sxs-lookup"><span data-stu-id="b74db-142">Indicates time spent retrieving app resources and parsing HTML and CSS.</span></span> <span data-ttu-id="b74db-143">これには、ネットワーク要求を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b74db-143">This can include network requests.</span></span> <span data-ttu-id="b74db-144">[タイムライン](#timeline-details)には、次の関連するイベントが記録されます。</span><span class="sxs-lookup"><span data-stu-id="b74db-144">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="b74db-145">イベント</span><span class="sxs-lookup"><span data-stu-id="b74db-145">Event</span></span> | <span data-ttu-id="b74db-146">説明</span><span class="sxs-lookup"><span data-stu-id="b74db-146">Description</span></span>
:------------ | :-------------
<span data-ttu-id="b74db-147">Cssparc</span><span class="sxs-lookup"><span data-stu-id="b74db-147">CssParsing</span></span>  | <span data-ttu-id="b74db-148">解析する必要がある新しい CSS コンテンツが検出されました。</span><span class="sxs-lookup"><span data-stu-id="b74db-148">New CSS content was encountered that needed to be parsed.</span></span>
<span data-ttu-id="b74db-149">HtmlParsing 解析</span><span class="sxs-lookup"><span data-stu-id="b74db-149">HtmlParsing</span></span> | <span data-ttu-id="b74db-150">新しい HTML コンテンツが検出されました。これには、ノードへの解析と DOM への挿入が必要です。</span><span class="sxs-lookup"><span data-stu-id="b74db-150">New HTML content was encountered that needed to be parsed into nodes and inserted into the DOM.</span></span>
<span data-ttu-id="b74db-151">HttpRequest</span><span class="sxs-lookup"><span data-stu-id="b74db-151">HttpRequest</span></span> | <span data-ttu-id="b74db-152">DOM でリモートリソースが検出されたか、HTTP 要求を行う必要がある XMLHttpRequest が作成されました。</span><span class="sxs-lookup"><span data-stu-id="b74db-152">A remote resource was encountered in the DOM or an XMLHttpRequest was created that required an HTTP request to be made.</span></span>
<span data-ttu-id="b74db-153">HtmlSpeculativeDownloading</span><span class="sxs-lookup"><span data-stu-id="b74db-153">HtmlSpeculativeDownloading</span></span> | <span data-ttu-id="b74db-154">ページの HTML コンテンツは、必要なリソースを検索しています。そのためには、HTTP 要求ができるだけ早くスケジュールされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b74db-154">The page's HTML content was being searched for required resources so that the HTTP requests for them could be scheduled as quickly as possible.</span></span>


#### <span data-ttu-id="b74db-155">作成</span><span class="sxs-lookup"><span data-stu-id="b74db-155">Scripting</span></span>
<span data-ttu-id="b74db-156">JavaScript の解析と実行に費やされた時間を示します。</span><span class="sxs-lookup"><span data-stu-id="b74db-156">Indicates time spent parsing and executing JavaScript.</span></span> <span data-ttu-id="b74db-157">これには、DOM イベント、タイマー、スクリプトの評価、アニメーションフレームのコールバックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b74db-157">This includes DOM events, timers, script evaluation, and animation frame callbacks.</span></span> <span data-ttu-id="b74db-158">[タイムライン](#timeline-details)には、次の関連するイベントが記録されます。</span><span class="sxs-lookup"><span data-stu-id="b74db-158">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="b74db-159">イベント</span><span class="sxs-lookup"><span data-stu-id="b74db-159">Event</span></span> | <span data-ttu-id="b74db-160">説明</span><span class="sxs-lookup"><span data-stu-id="b74db-160">Description</span></span>
:------------ | :-------------
<span data-ttu-id="b74db-161">DomEvent</span><span class="sxs-lookup"><span data-stu-id="b74db-161">DomEvent</span></span> | <span data-ttu-id="b74db-162">DOM オブジェクトでイベントが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b74db-162">An event was fired on a DOM object.</span></span>
<span data-ttu-id="b74db-163">評価のスクリプト</span><span class="sxs-lookup"><span data-stu-id="b74db-163">EvaluatingScript</span></span> | <span data-ttu-id="b74db-164">`<script>`DOM で新しい要素が検出されたため、解析および実行が必要です。</span><span class="sxs-lookup"><span data-stu-id="b74db-164">A new `<script>` element was encountered in the DOM and needed to be parsed and executed.</span></span>
<span data-ttu-id="b74db-165">EventHandler</span><span class="sxs-lookup"><span data-stu-id="b74db-165">EventHandler</span></span> | <span data-ttu-id="b74db-166">登録済みのイベントリスナーは、発生する DOM イベントに応じてトリガーされました。</span><span class="sxs-lookup"><span data-stu-id="b74db-166">A registered event listener was triggered in response to a DOM event being fired.</span></span>
<span data-ttu-id="b74db-167">フレーム</span><span class="sxs-lookup"><span data-stu-id="b74db-167">Frame</span></span> | <span data-ttu-id="b74db-168">新しいフレームが準備されている間、登録済みのコールバックがトリガーされ、視覚的な変更が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b74db-168">While a new frame was being prepared a registered callback was triggered so that it could contribute visual changes.</span></span>
<span data-ttu-id="b74db-169">測定値</span><span class="sxs-lookup"><span data-stu-id="b74db-169">Measure</span></span> | <span data-ttu-id="b74db-170">アプリ固有のシナリオは、このメソッドを使って測定されました `performance.measure()` 。</span><span class="sxs-lookup"><span data-stu-id="b74db-170">An app-specific scenario was measured using the `performance.measure()` method.</span></span>
<span data-ttu-id="b74db-171">MediaQueryListener</span><span class="sxs-lookup"><span data-stu-id="b74db-171">MediaQueryListener</span></span> | <span data-ttu-id="b74db-172">登録済みのメディアクエリが無効になりました。これにより、関連付けられたリスナーが実行されます。</span><span class="sxs-lookup"><span data-stu-id="b74db-172">A registered media query was invalidated which resulted in the execution of its associated listener(s).</span></span>
<span data-ttu-id="b74db-173">ミューテーター</span><span class="sxs-lookup"><span data-stu-id="b74db-173">MutationObserver</span></span> | <span data-ttu-id="b74db-174">1つまたは複数の DOM 要素が変更されたため、これによって、ミューテーターの関連付けられたコールバックが実行されました。</span><span class="sxs-lookup"><span data-stu-id="b74db-174">One or more observed DOM elements were modified which resulted in the execution of a MutationObserver's associated callback.</span></span>
<span data-ttu-id="b74db-175">TimerFired</span><span class="sxs-lookup"><span data-stu-id="b74db-175">TimerFired</span></span> | <span data-ttu-id="b74db-176">スケジュールされたタイマーが経過したため、関連付けられたコールバックが実行されました。</span><span class="sxs-lookup"><span data-stu-id="b74db-176">A scheduled timer elapsed which resulted in the execution of its associated callback.</span></span>
<span data-ttu-id="b74db-177">WindowsRuntimeAsyncCallback</span><span class="sxs-lookup"><span data-stu-id="b74db-177">WindowsRuntimeAsyncCallback</span></span> | <span data-ttu-id="b74db-178">非同期操作は、コールバックをトリガーした Windows ランタイムオブジェクトによって実行されました `Promise` 。</span><span class="sxs-lookup"><span data-stu-id="b74db-178">An async operation was completed by a Windows Runtime object which triggered a `Promise` callback.</span></span>
<span data-ttu-id="b74db-179">WindowsRuntimeEvent</span><span class="sxs-lookup"><span data-stu-id="b74db-179">WindowsRuntimeEvent</span></span> | <span data-ttu-id="b74db-180">登録済みリスナーをトリガーする Windows ランタイムオブジェクトでイベントが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b74db-180">An event was fired on a Windows Runtime object which triggered a registered listener.</span></span>

#### <span data-ttu-id="b74db-181">GC.COLLECT</span><span class="sxs-lookup"><span data-stu-id="b74db-181">GC</span></span>
<span data-ttu-id="b74db-182">使用されなくなったオブジェクトのメモリ収集に費やされた時間を示します。</span><span class="sxs-lookup"><span data-stu-id="b74db-182">Indicates time spent collecting memory for objects that are no longer in use.</span></span> <span data-ttu-id="b74db-183">[タイムライン](#timeline-details)には、次の関連するイベントが記録されます。</span><span class="sxs-lookup"><span data-stu-id="b74db-183">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="b74db-184">イベント</span><span class="sxs-lookup"><span data-stu-id="b74db-184">Event</span></span> | <span data-ttu-id="b74db-185">説明</span><span class="sxs-lookup"><span data-stu-id="b74db-185">Description</span></span>
:------------ | :-------------
<span data-ttu-id="b74db-186">ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="b74db-186">GarbageCollection</span></span> | <span data-ttu-id="b74db-187">JavaScript ランタイムは、アプリの現在のメモリ使用量を監査したため、どのオブジェクトも参照されず、収集される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b74db-187">The JavaScript runtime audited the app's current memory usage in order to determine which objects aren't being referenced anymore and could therefore be collected.</span></span>

#### <span data-ttu-id="b74db-188">スタイル</span><span class="sxs-lookup"><span data-stu-id="b74db-188">Styling</span></span>
<span data-ttu-id="b74db-189">要素のプレゼンテーションとレイアウトの計算に費やされた時間を示します。</span><span class="sxs-lookup"><span data-stu-id="b74db-189">Indicates time spent calculating element presentation and layout.</span></span> <span data-ttu-id="b74db-190">[タイムライン](#timeline-details)には、次の関連するイベントが記録されます。</span><span class="sxs-lookup"><span data-stu-id="b74db-190">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="b74db-191">イベント</span><span class="sxs-lookup"><span data-stu-id="b74db-191">Event</span></span> | <span data-ttu-id="b74db-192">説明</span><span class="sxs-lookup"><span data-stu-id="b74db-192">Description</span></span>
:------------ | :-------------
<span data-ttu-id="b74db-193">AlignedBeat</span><span class="sxs-lookup"><span data-stu-id="b74db-193">AlignedBeat</span></span> | <span data-ttu-id="b74db-194">DOM に対して行われた保留中のビジュアル変更が処理され、アプリの表示が更新される可能性がありました。</span><span class="sxs-lookup"><span data-stu-id="b74db-194">Pending visual changes that were made to the DOM were processed so that the app's display could be updated.</span></span>
<span data-ttu-id="b74db-195">Csん</span><span class="sxs-lookup"><span data-stu-id="b74db-195">CssCalculation</span></span> | <span data-ttu-id="b74db-196">DOM に変更が加えられたため、新しい CSS コンテンツが追加されました。影響を受けるすべての要素の style プロパティを再計算する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b74db-196">Changes were made to the DOM or new CSS content was added, requiring the style properties of all affected elements to be recalculated.</span></span>
<span data-ttu-id="b74db-197">レイアウト</span><span class="sxs-lookup"><span data-stu-id="b74db-197">Layout</span></span> | <span data-ttu-id="b74db-198">DOM に変更が加えられました。これには、影響を受けるすべての要素のサイズや位置を計算する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b74db-198">Changes were made to the DOM that required the size and/or position of all affected elements to be computed.</span></span>

#### <span data-ttu-id="b74db-199">レンダリング</span><span class="sxs-lookup"><span data-stu-id="b74db-199">Rendering</span></span>
<span data-ttu-id="b74db-200">画面の描画に使われた時間を示します。</span><span class="sxs-lookup"><span data-stu-id="b74db-200">Indicates time spent in painting the screen.</span></span> <span data-ttu-id="b74db-201">[タイムライン](#timeline-details)には、次の関連するイベントが記録されます。</span><span class="sxs-lookup"><span data-stu-id="b74db-201">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="b74db-202">イベント</span><span class="sxs-lookup"><span data-stu-id="b74db-202">Event</span></span> | <span data-ttu-id="b74db-203">説明</span><span class="sxs-lookup"><span data-stu-id="b74db-203">Description</span></span>
:------------ | :-------------
<span data-ttu-id="b74db-204">ペイント</span><span class="sxs-lookup"><span data-stu-id="b74db-204">Paint</span></span> | <span data-ttu-id="b74db-205">DOM に視覚的な変更が加えられました。これにより、ページの影響を受けるすべての部分を再描画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b74db-205">Visual changes were made to the DOM that required all affected portions of the page to be redrawn.</span></span>
<span data-ttu-id="b74db-206">RenderLayer</span><span class="sxs-lookup"><span data-stu-id="b74db-206">RenderLayer</span></span> | <span data-ttu-id="b74db-207">視覚的な変更は、DOM の (レイヤーと呼ばれる) DOM の独立したレンダリングフラグメントに対して行われ、ページの各部分を再描画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b74db-207">Visual changes were made to an independently rendered fragment of the DOM (called a layer) which required its respective portion of the page to be redrawn.</span></span>

#### <span data-ttu-id="b74db-208">画像のデコード</span><span class="sxs-lookup"><span data-stu-id="b74db-208">Image decoding</span></span>
<span data-ttu-id="b74db-209">画像の展開とデコードに費やされた時間を示します。</span><span class="sxs-lookup"><span data-stu-id="b74db-209">Indicates time spent decompressing and decoding images.</span></span> <span data-ttu-id="b74db-210">[タイムライン](#timeline-details)には、次の関連するイベントが記録されます。</span><span class="sxs-lookup"><span data-stu-id="b74db-210">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="b74db-211">イベント</span><span class="sxs-lookup"><span data-stu-id="b74db-211">Event</span></span> | <span data-ttu-id="b74db-212">説明</span><span class="sxs-lookup"><span data-stu-id="b74db-212">Description</span></span>
:------------ | :-------------
<span data-ttu-id="b74db-213">ImageDecoded</span><span class="sxs-lookup"><span data-stu-id="b74db-213">ImageDecoded</span></span> | <span data-ttu-id="b74db-214">画像は DOM に含まれていましたが、元の形式からビットマップに圧縮解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b74db-214">An image was included into the DOM and needed be to decompressed from its original format into a bitmap.</span></span>

### <span data-ttu-id="b74db-215">視覚的なスループット</span><span class="sxs-lookup"><span data-stu-id="b74db-215">Visual throughput</span></span>

<span data-ttu-id="b74db-216">プロファイリングシナリオの過程で、[**ビジュアルスループット (fps)** ] グラフには、 *1 秒あたりの推定フレーム数*(fps) が表示されます。 60 FPS は最適な表示レートです。</span><span class="sxs-lookup"><span data-stu-id="b74db-216">The **Visual throughput (FPS)** graph shows the estimated *frames per second* (FPS) during the course of the profiling scenario, where 60 FPS is the ideal display rate.</span></span> <span data-ttu-id="b74db-217">フレームレートの dip は、パフォーマンスのボトルネックを示し、フレームレートが0であることを意味します。フレームは完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="b74db-217">Dips in the frame rate indicate performance bottlenecks and a frame rate of zero means that frames are getting dropped entirely.</span></span>

## <span data-ttu-id="b74db-218">タイムラインの詳細</span><span class="sxs-lookup"><span data-stu-id="b74db-218">Timeline details</span></span>

<span data-ttu-id="b74db-219">一番下詳細ウィンドウを使用して、ページ上で発生した問題の詳細をすべて表示します。</span><span class="sxs-lookup"><span data-stu-id="b74db-219">Use the lowermost details pane to get the full breakdown of what happened on the page.</span></span> <span data-ttu-id="b74db-220">[**タイムラインの詳細**] タブには、さまざまなブラウザーサブシステム内で発生したイベントの内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b74db-220">The **Timeline details** tab provides a breakdown of events that occurred within the various browser subsystems.</span></span>

![パフォーマンスタイムラインの詳細ウィンドウ](./media/performance_details_timeline.png)

1. **<span data-ttu-id="b74db-222">イベントリストの並べ替えコントロール</span><span class="sxs-lookup"><span data-stu-id="b74db-222">Event list sort control</span></span>**

    <span data-ttu-id="b74db-223">[**並べ替え**] ドロップダウンコントロールを使用して、[イベントの一覧](#event-list)の順序を*開始時刻*または*期間 (両端を含む*) で切り替えます。</span><span class="sxs-lookup"><span data-stu-id="b74db-223">Use the **Sort by** dropdown control to toggle the [Event list](#event-list) order between *Start time* or *Duration (inclusive*).</span></span> <span data-ttu-id="b74db-224">これにより、[選択したタイムラインの詳細](#selected-timeline-details)のビューも変更されます。</span><span class="sxs-lookup"><span data-stu-id="b74db-224">This also changes the view of the [Selected timeline details](#selected-timeline-details).</span></span>

2. **<span data-ttu-id="b74db-225">フレームごとにイベントをグループ化する</span><span class="sxs-lookup"><span data-stu-id="b74db-225">Group events by frame</span></span>**

    <span data-ttu-id="b74db-226">最上位レベルのイベントを [**フレームで**グループ化する] トグルを使って *、アニメーション*/ビジュアルの更新が行われている期間中の対応する作業単位 ("frame") にグループ化します。</span><span class="sxs-lookup"><span data-stu-id="b74db-226">Use the **Group top level events by frames** toggle to group top-level events (*HTML parsing, Layout, DOM event,* etc.) into their corresponding unit of work (or "frame") during periods of time where animations/visual updates were occurring.</span></span> <span data-ttu-id="b74db-227">フレームは、他のイベントと同じように扱われるため、[イベントリスト](#event-list)でクリックしたときに、表示される*時間*の概要を提供できます。</span><span class="sxs-lookup"><span data-stu-id="b74db-227">The frames are treated like other events, so they can be sorted/filtered and provide an *Inclusive time* summary when clicked in the [Event list](#event-list).</span></span>

3. **<span data-ttu-id="b74db-228">イベントリストフィルターコントロール</span><span class="sxs-lookup"><span data-stu-id="b74db-228">Event list filter controls</span></span>**

    <span data-ttu-id="b74db-229">[**イベントのフィルター** ] メニューを使って、[タイムラインの詳細](#timeline-details)に表示されるイベントの種類を構成します。</span><span class="sxs-lookup"><span data-stu-id="b74db-229">Use the **Filter events** menu to configure the types of events shown in the [timeline details](#timeline-details).</span></span> 

    ![パフォーマンスイベントをフィルター処理するためのコントロール](./media/performance_filter_events.png) 

    <span data-ttu-id="b74db-231">次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b74db-231">The following filters are available:</span></span>

   - <span data-ttu-id="b74db-232">**画像のデコード**: バックグラウンドスレッドで発生したイベント (画像のデコード、GC など) を表示します。</span><span class="sxs-lookup"><span data-stu-id="b74db-232">**Image decoding**: Show events which occurred on a background thread (e.g. Image decoding, GC).</span></span> 
   - <span data-ttu-id="b74db-233">**ネットワークトラフィック**: ネットワークにバインドされていた HTTP 要求を表示します。</span><span class="sxs-lookup"><span data-stu-id="b74db-233">**Network traffic**: Show HTTP requests which were network-bound.</span></span>
   - <span data-ttu-id="b74db-234">**Ui アクティビティ**: ui スレッドまたはレンダースレッド (DOM イベントハンドラー、レイアウトなど) で発生したイベントを表示します。</span><span class="sxs-lookup"><span data-stu-id="b74db-234">**UI activity**: Show events which occurred on the UI thread and/or render thread (e.g. DOM event handlers, Layout).</span></span>
   - <span data-ttu-id="b74db-235">**ユーザー測定**: measure () メソッドの呼び出しを示すカスタムイベントを表示します。</span><span class="sxs-lookup"><span data-stu-id="b74db-235">**User measures**: Show custom events which indicate calls to the performance.measure() method.</span></span>

     <span data-ttu-id="b74db-236">また、包括的な期間によって上位レベルのイベントをさらにフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="b74db-236">You can further filter top-level events by their inclusive duration.</span></span>

### <span data-ttu-id="b74db-237">イベントリスト</span><span class="sxs-lookup"><span data-stu-id="b74db-237">Event list</span></span>

<span data-ttu-id="b74db-238">*イベントリスト*には、選択した期間中に発生した[ブラウザーサブシステムイベント](#cpu-utilization)の時系列の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b74db-238">The *Event list* gives you a chronological list of [browser subsystem events](#cpu-utilization) that occurred during the selected span of time.</span></span> 

<span data-ttu-id="b74db-239">任意のエントリをクリックして、その項目の**選択したイベントの詳細**グラフにデータを入力します。</span><span class="sxs-lookup"><span data-stu-id="b74db-239">Click on any entry to populate the **Selected event details** chart for that item.</span></span> <span data-ttu-id="b74db-240">入れ子になったイベント/関数を含むエントリには、**包括**(関数の実行に費やされた関数*と*その他の関数の実行に費やされた時間) と**排他的**な値が表示されます (通話機能の本文内のみに費やされた時間)。</span><span class="sxs-lookup"><span data-stu-id="b74db-240">Entries with nested events / functions will show their **inclusive** (time spent executing the function *and* any other functions it called) and **exclusive** (time spent only within the body of the calling function itself) times displayed in the chart.</span></span>

<span data-ttu-id="b74db-241">任意のエントリを右クリックしてコンテキストメニューを開き、そのイベントのみにタイムラインをフィルター処理し、[**デバッガー**](./debugger.md) (該当する場合は [[**要素**](./elements.md)] パネル) でイベントを担当するソースコードを表示します。</span><span class="sxs-lookup"><span data-stu-id="b74db-241">Right-click on any entry to open the context menu to filter the timeline to only that event and view the source code responsible for the event in the [**Debugger**](./debugger.md) (or [**Elements**](./elements.md) panel, if applicable).</span></span>

### <span data-ttu-id="b74db-242">選択されたタイムラインの詳細</span><span class="sxs-lookup"><span data-stu-id="b74db-242">Selected timeline details</span></span>

<span data-ttu-id="b74db-243">*選択したタイムラインの詳細*には、選択した期間中の包括/排他イベントの時間の詳細な棒グラフが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b74db-243">The *Selected timeline details* provides a detailed bar graph of inclusive/exclusive event times during the selected time span.</span></span> <span data-ttu-id="b74db-244">**イベントリストの並べ替えコントロール**を使用して、*期間*で並べ替えると、最も長いイベントが視覚的に強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="b74db-244">When you sort by *Duration (inclusive)* using the **Event list sort control**, the longest running events will visually stand out in this chart.</span></span> 

### <span data-ttu-id="b74db-245">選択されたイベントの詳細</span><span class="sxs-lookup"><span data-stu-id="b74db-245">Selected event details</span></span>

<span data-ttu-id="b74db-246">このレポートは、選択したイベントに関する詳細情報を提供します。これには、*開始時刻*、実行中のスレッド型 (*ダウンロード*、 *UI*、*レンダリング*など)、および特定のイベントの種類に固有のその他のコンテキストの詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b74db-246">This report provides further information about the selected event, including *Start time*, the executing thread type (for example, *Download*, *UI*, *Render*), and other contextual details specific to the specific event type.</span></span> <span data-ttu-id="b74db-247">たとえば、*イベントリスナー*の型には、*コールバック関数*と*スケジューリングの呼び出しスタック*へのデバッガーリンクが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b74db-247">For example, *Event listener* types provide debugger links to the *Callback function* and *Scheduling call stack*.</span></span>

## <span data-ttu-id="b74db-248">JavaScript の呼び出し履歴</span><span class="sxs-lookup"><span data-stu-id="b74db-248">JavaScript call stacks</span></span>

![JavaScript の呼び出し履歴のパフォーマンスタイミング](./media/performance_details_javascript.png)

<span data-ttu-id="b74db-250">[ **JavaScript 呼び出しスタック**] タブには、選択した期間中に実行されたスクリプト関数の CPU 使用量に関する情報とタイミングが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b74db-250">The **JavaScript call stacks** tab provides CPU usage information and timings for the script functions that ran during the selected time range:</span></span>

 <span data-ttu-id="b74db-251">列</span><span class="sxs-lookup"><span data-stu-id="b74db-251">Column</span></span> | <span data-ttu-id="b74db-252">説明</span><span class="sxs-lookup"><span data-stu-id="b74db-252">Description</span></span>
:------------ | :-------------
<span data-ttu-id="b74db-253">関数名</span><span class="sxs-lookup"><span data-stu-id="b74db-253">Function name</span></span> | <span data-ttu-id="b74db-254">ブラウザーまたはユーザー定義関数の名前。</span><span class="sxs-lookup"><span data-stu-id="b74db-254">Name of browser or user-defined function.</span></span>
<span data-ttu-id="b74db-255">包括的 CPU (%)</span><span class="sxs-lookup"><span data-stu-id="b74db-255">Inclusive CPU (%)</span></span> | <span data-ttu-id="b74db-256">この関数およびこの関数によって呼び出される関数で選択された CPU アクティビティのパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="b74db-256">Percentage of selected CPU activity in this function and in functions called by this function.</span></span>
<span data-ttu-id="b74db-257">排他 CPU (%)</span><span class="sxs-lookup"><span data-stu-id="b74db-257">Exclusive CPU (%)</span></span> | <span data-ttu-id="b74db-258">この関数で選択された CPU アクティビティのうち、この関数によって呼び出された関数のアクティビティを除いた割合。</span><span class="sxs-lookup"><span data-stu-id="b74db-258">Percentage of selected CPU activity in this function, excluding activity in functions called by this function.</span></span>
<span data-ttu-id="b74db-259">包括的 CPU (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="b74db-259">Inclusive CPU (ms)</span></span> | <span data-ttu-id="b74db-260">この関数およびこの関数によって呼び出される関数でコードを実行するために消費された CPU 時間。</span><span class="sxs-lookup"><span data-stu-id="b74db-260">CPU time spent executing code in this function and in functions called by this function.</span></span>
<span data-ttu-id="b74db-261">排他的 CPU (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="b74db-261">Exclusive CPU (ms)</span></span> | <span data-ttu-id="b74db-262">この関数でのコード実行に消費された CPU 時間。この関数によって呼び出された関数の時間は除外されます。</span><span class="sxs-lookup"><span data-stu-id="b74db-262">CPU time spent executing code in this function, excluding time in functions called by this function.</span></span>
<span data-ttu-id="b74db-263">URL</span><span class="sxs-lookup"><span data-stu-id="b74db-263">URL</span></span> | <span data-ttu-id="b74db-264">スタックフレームが発生した URL。</span><span class="sxs-lookup"><span data-stu-id="b74db-264">URL(s) where stack frame occurred.</span></span> <span data-ttu-id="b74db-265">ブラウザー (標準ベースの web Api) から発信された関数呼び出しは、 *[DOM]* というラベルが付いています。</span><span class="sxs-lookup"><span data-stu-id="b74db-265">Function calls originating from the browser (standards-based web APIs) are labeled as *[DOM]*.</span></span>

## <span data-ttu-id="b74db-266">ショートカット</span><span class="sxs-lookup"><span data-stu-id="b74db-266">Shortcuts</span></span>

| <span data-ttu-id="b74db-267">操作</span><span class="sxs-lookup"><span data-stu-id="b74db-267">Action</span></span>                         | <span data-ttu-id="b74db-268">キー</span><span class="sxs-lookup"><span data-stu-id="b74db-268">Shortcut</span></span>     |
|:-------------------------------|:-------------|
| <span data-ttu-id="b74db-269">プロファイリングセッションの開始/停止</span><span class="sxs-lookup"><span data-stu-id="b74db-269">Start / Stop profiling session</span></span> | `Ctrl` + `E` |
| <span data-ttu-id="b74db-270">プロファイルセッションのインポート</span><span class="sxs-lookup"><span data-stu-id="b74db-270">Import profiling session</span></span>       | `Ctrl` + `O` |
| <span data-ttu-id="b74db-271">プロファイリングセッションのエクスポート</span><span class="sxs-lookup"><span data-stu-id="b74db-271">Export profiling session</span></span>       | `Ctrl` + `S` |

## <span data-ttu-id="b74db-272">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b74db-272">Known Issues</span></span>

### <span data-ttu-id="b74db-273">プロファイルセッションの開始中にエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="b74db-273">An error occurred while starting the profiling session</span></span>

<span data-ttu-id="b74db-274">次のエラーメッセージが表示される場合は、パフォーマンスツールで**プロファイリングセッションの開始時にエラーが発生しまし**た。回避策については、次の手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="b74db-274">If you see this error message: **An error occurred while starting the profiling session** in the Performance tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="b74db-275">キーを押し `Windows Key`  +  `R` ます。</span><span class="sxs-lookup"><span data-stu-id="b74db-275">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="b74db-276">[実行] ダイアログボックスで、「 **services.msc**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="b74db-276">In the Run dialog, enter **services.msc**.</span></span>
![既知の問題-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="b74db-278">**Microsoft (R) Diagnostics Hub Standard コレクタサービス**を探して右クリックします。</span><span class="sxs-lookup"><span data-stu-id="b74db-278">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![既知の問題-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="b74db-280">**Microsoft (R) Diagnostics Hub Standard コレクタサービス**を再起動します。</span><span class="sxs-lookup"><span data-stu-id="b74db-280">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![既知の問題-3](./media/known_issues_3.PNG)

5. <span data-ttu-id="b74db-282">Microsoft Edge 開発者ツールとタブを閉じます。新しいタブを開き、目的のページに移動して、キーを押し `F12` ます。</span><span class="sxs-lookup"><span data-stu-id="b74db-282">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="b74db-283">これで、プロファイリングを開始できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b74db-283">You should now be able to begin profiling.</span></span>
![既知の問題-4](./media/known_issues_4-performance.PNG)

<span data-ttu-id="b74db-285">まだ問題が発生していますか?</span><span class="sxs-lookup"><span data-stu-id="b74db-285">Still running into problems?</span></span> <span data-ttu-id="b74db-286">フィードバックの**送信**アイコンを使ってフィードバックをお送りください。</span><span class="sxs-lookup"><span data-stu-id="b74db-286">Please send us your feedback using the **Send feedback** icon!</span></span> 

![既知の問題-5](./media/known_issues_5.PNG)

### <span data-ttu-id="b74db-288">プロファイリングセッションの停止中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b74db-288">An error occurred while stopping the profiling session.</span></span>

<span data-ttu-id="b74db-289">このエラーメッセージが表示される場合: パフォーマンスツールで**プロファイリングセッションを停止しているときにエラーが発生**した場合は、次の手順に従って回避策を実行します。</span><span class="sxs-lookup"><span data-stu-id="b74db-289">If you see this error message: **An error occurred while stopping the profiling session** in the Performance tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="b74db-290">キーを押し `Windows Key`  +  `R` ます。</span><span class="sxs-lookup"><span data-stu-id="b74db-290">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="b74db-291">[実行] ダイアログボックスで、「 **services.msc**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="b74db-291">In the Run dialog, enter **services.msc**.</span></span>
![既知の問題-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="b74db-293">**Microsoft (R) Diagnostics Hub Standard コレクタサービス**を探して右クリックします。</span><span class="sxs-lookup"><span data-stu-id="b74db-293">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![既知の問題-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="b74db-295">**Microsoft (R) Diagnostics Hub Standard コレクタサービス**を再起動します。</span><span class="sxs-lookup"><span data-stu-id="b74db-295">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![既知の問題-3](./media/known_issues_3.PNG)

5. <span data-ttu-id="b74db-297">Microsoft Edge 開発者ツールとタブを閉じます。新しいタブを開き、目的のページに移動して、キーを押し `F12` ます。</span><span class="sxs-lookup"><span data-stu-id="b74db-297">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="b74db-298">これで、プロファイリングを開始できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b74db-298">You should now be able to begin profiling.</span></span>
![既知の問題-4](./media/known_issues_4-performance.PNG)

<span data-ttu-id="b74db-300">まだ問題が発生していますか?</span><span class="sxs-lookup"><span data-stu-id="b74db-300">Still running into problems?</span></span> <span data-ttu-id="b74db-301">フィードバックの**送信**アイコンを使ってフィードバックをお送りください。</span><span class="sxs-lookup"><span data-stu-id="b74db-301">Please send us your feedback using the **Send feedback** icon!</span></span> 

![既知の問題-5](./media/known_issues_5.PNG)
