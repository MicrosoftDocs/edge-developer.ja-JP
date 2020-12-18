---
description: ユーザーは、対話型でスムーズなページを期待します。  ピクセル パイプラインの各ステージは、jank を導入する機会を表します。  ランタイムのパフォーマンスを低下させる一般的な問題を特定して修正するためのツールと戦略について説明します。
title: ランタイム パフォーマンスの分析
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: d42ac5e7a7456971d48198a1f362eebe7156bbce
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230608"
---
<!-- Copyright Kayce Basques and Meggin Kearney

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# <span data-ttu-id="33618-106">実行時のパフォーマンスを分析する</span><span class="sxs-lookup"><span data-stu-id="33618-106">Analyze runtime performance</span></span> 

<span data-ttu-id="33618-107">ユーザーは、対話型でスムーズなページを期待します。</span><span class="sxs-lookup"><span data-stu-id="33618-107">Users expects interactive and smooth pages.</span></span>  <span data-ttu-id="33618-108">ピクセル パイプラインの各ステージは、jank を導入する機会を表します。</span><span class="sxs-lookup"><span data-stu-id="33618-108">Each stage in the pixel pipeline represents an opportunity to introduce jank.</span></span>  <span data-ttu-id="33618-109">ランタイムのパフォーマンスを低下させる一般的な問題を特定して修正するためのツールと戦略について説明します。</span><span class="sxs-lookup"><span data-stu-id="33618-109">Learn about tools and strategies to identify and fix common problems that slow down runtime performance.</span></span>  

### <span data-ttu-id="33618-110">まとめ</span><span class="sxs-lookup"><span data-stu-id="33618-110">Summary</span></span>  

*   <span data-ttu-id="33618-111">ブラウザーで強制的にレイアウトを再計算する JavaScript を記述しない。</span><span class="sxs-lookup"><span data-stu-id="33618-111">Do not write JavaScript that forces the browser to recalculate layout.</span></span>  <span data-ttu-id="33618-112">読み取り関数と書き込み関数を分離し、最初に読み取りを実行します。</span><span class="sxs-lookup"><span data-stu-id="33618-112">Separate read and write functions, and perform reads first.</span></span>  
*   <span data-ttu-id="33618-113">CSS を過剰に複雑にし過ぎない。</span><span class="sxs-lookup"><span data-stu-id="33618-113">Do not over-complicate your CSS.</span></span>  <span data-ttu-id="33618-114">CSS を少なくし、CSS セレクターをシンプルにしてください。</span><span class="sxs-lookup"><span data-stu-id="33618-114">Use less CSS and keep your CSS selectors simple.</span></span>  
*   <span data-ttu-id="33618-115">レイアウトは可能な限り避ける。</span><span class="sxs-lookup"><span data-stu-id="33618-115">Avoid layout as much as possible.</span></span>  <span data-ttu-id="33618-116">レイアウトをトリガーしない CSS を選択します。</span><span class="sxs-lookup"><span data-stu-id="33618-116">Choose CSS that does not trigger layout at all.</span></span>  
*   <span data-ttu-id="33618-117">描画には、他のレンダリング アクティビティよりも時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="33618-117">Painting may take up more time than any other rendering activity.</span></span>  <span data-ttu-id="33618-118">ペイントのボトルネックに注意してください。</span><span class="sxs-lookup"><span data-stu-id="33618-118">Watch out for paint bottlenecks.</span></span>  
    
## <span data-ttu-id="33618-119">JavaScript</span><span class="sxs-lookup"><span data-stu-id="33618-119">JavaScript</span></span>  

<span data-ttu-id="33618-120">JavaScript の計算 (特に、広範囲な表示変更をトリガーする計算) では、アプリケーションのパフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="33618-120">JavaScript calculations, especially ones that trigger extensive visual changes, may stall application performance.</span></span>  <span data-ttu-id="33618-121">時間が悪い、または長時間実行される JavaScript がユーザー操作に干渉しないようにします。</span><span class="sxs-lookup"><span data-stu-id="33618-121">Do not let badly-timed or long-running JavaScript interfere with user interactions.</span></span>  

### <span data-ttu-id="33618-122">JavaScript: ツール</span><span class="sxs-lookup"><span data-stu-id="33618-122">JavaScript: Tools</span></span>  

<span data-ttu-id="33618-123">パフォーマンス パネルでレコーディングを **行** い、疑わしい長いイベントを探 `Evaluate Script` します。</span><span class="sxs-lookup"><span data-stu-id="33618-123">Take a recording in the **Performance** panel and look for suspiciously long `Evaluate Script` events.</span></span>  <!--If you find any, you are able to enable the **JS Profiler** and re-do your recording to get more detailed information about exactly which JavaScript functions were used and how long each took.  -->  

<!--todo: add Recording section when available  -->  
<!--todo: add Profile JavaScript (JS Profiler) section when available  -->  

<span data-ttu-id="33618-124">JavaScript でかなりの数の jank に気が付く場合は、分析を次のレベルに進めて JavaScript CPU プロファイルを収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33618-124">f you noticing quite a bit of jank in your JavaScript, you may need to take your analysis to the next level and collect a JavaScript CPU profile.</span></span>  <span data-ttu-id="33618-125">CPU プロファイルは、ページの機能内でランタイムが使用される場所を示します。</span><span class="sxs-lookup"><span data-stu-id="33618-125">CPU profiles show where runtime is spent within the functions of your page.</span></span>  <span data-ttu-id="33618-126">JavaScript ランタイムの高速化で CPU プロファイル [を作成する方法について説明します][DevtoolsRenderingToolsJavascriptRuntime]。</span><span class="sxs-lookup"><span data-stu-id="33618-126">Learn how to create CPU profiles in [Speed Up JavaScript Runtime][DevtoolsRenderingToolsJavascriptRuntime].</span></span>

### <span data-ttu-id="33618-127">JavaScript: 問題</span><span class="sxs-lookup"><span data-stu-id="33618-127">JavaScript: Problems</span></span>  

<span data-ttu-id="33618-128">次の表では、いくつかの一般的な JavaScript の問題と潜在的な解決策について説明します。</span><span class="sxs-lookup"><span data-stu-id="33618-128">The following table describes some common JavaScript problems and potential solutions:</span></span>  

| <span data-ttu-id="33618-129">問題</span><span class="sxs-lookup"><span data-stu-id="33618-129">Problem</span></span> | <span data-ttu-id="33618-130">例</span><span class="sxs-lookup"><span data-stu-id="33618-130">Example</span></span> | <span data-ttu-id="33618-131">解決策</span><span class="sxs-lookup"><span data-stu-id="33618-131">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="33618-132">応答またはアニメーションに影響を与える高コストの入力ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="33618-132">Expensive input handlers affecting response or animation.</span></span>  | <span data-ttu-id="33618-133">タッチ、視差スクロール。</span><span class="sxs-lookup"><span data-stu-id="33618-133">Touch, parallax scrolling.</span></span>  | <span data-ttu-id="33618-134">ブラウザーでタッチとスクロールを処理するか、リスナーを可能な限り遅くバインドします。</span><span class="sxs-lookup"><span data-stu-id="33618-134">Let the browser handle touch and scrolls, or bind the listener as late as possible.</span></span>  <span data-ttu-id="33618-135">[Paul Paul Paul のランタイム パフォーマンス チェックリストの「高価な入力ハンドラー」を参照してください][WebPerformanceCalendarRuntimeChecklist]。</span><span class="sxs-lookup"><span data-stu-id="33618-135">See [Expensive Input Handlers in Paul Lewis' runtime performance checklist][WebPerformanceCalendarRuntimeChecklist].</span></span>  |  
| <span data-ttu-id="33618-136">応答、アニメーション、読み込みに影響を与える時間が悪い JavaScript。</span><span class="sxs-lookup"><span data-stu-id="33618-136">Badly-timed JavaScript affecting response, animation, load.</span></span>  | <span data-ttu-id="33618-137">ユーザーはページの読み込み直後にスクロールします。setTimeout / setInterval。</span><span class="sxs-lookup"><span data-stu-id="33618-137">User scrolls right after page load, setTimeout / setInterval.</span></span>  | <span data-ttu-id="33618-138">JavaScript ランタイムの最適化: 使用 `requestAnimationFrame` 、DOM 操作をフレームに広げる [、Web ワーカーを使用する][MDNUsingWebWorkers]。</span><span class="sxs-lookup"><span data-stu-id="33618-138">Optimize JavaScript runtime: use `requestAnimationFrame`, spread DOM manipulation over frames, use [Web Workers][MDNUsingWebWorkers].</span></span>  |  
| <span data-ttu-id="33618-139">応答に影響を与える長時間実行される JavaScript。</span><span class="sxs-lookup"><span data-stu-id="33618-139">Long-running JavaScript affecting response.</span></span>  | <span data-ttu-id="33618-140">[DOMContentLoaded][MDNUsingWebWorkers]イベントは、JS の処理が行き詰まっている間にストールします。</span><span class="sxs-lookup"><span data-stu-id="33618-140">The [DOMContentLoaded event][MDNUsingWebWorkers] stalls as it is swamped with JS work.</span></span>  | <span data-ttu-id="33618-141">純粋な計算作業を [Web ワーカーに移動します][MDNUsingWebWorkers]。</span><span class="sxs-lookup"><span data-stu-id="33618-141">Move pure computational work to [Web Workers][MDNUsingWebWorkers].</span></span>  <span data-ttu-id="33618-142">DOM アクセスが必要な場合は、次の値を使用します `requestAnimationFrame` 。</span><span class="sxs-lookup"><span data-stu-id="33618-142">If you need DOM access, use `requestAnimationFrame`.</span></span>  <!--See also [Optimize JavaScript Execution][WebFundamentalsPerformanceRenderingOptimizeJavascriptRuntime].  -->  |  
| <span data-ttu-id="33618-143">応答またはアニメーションに影響を与えるガベージ y スクリプト。</span><span class="sxs-lookup"><span data-stu-id="33618-143">Garbage-y scripts affecting response or animation.</span></span>  | <span data-ttu-id="33618-144">ガベージ コレクションは、任意の場所で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="33618-144">Garbage collection may happen anywhere.</span></span>  | <span data-ttu-id="33618-145">ガベージ y スクリプトを少なくする。</span><span class="sxs-lookup"><span data-stu-id="33618-145">Write less garbage-y scripts.</span></span>  <span data-ttu-id="33618-146">[Paul Paul のランタイム パフォーマンス チェックリストのアニメーションのガベージ コレクションを参照してください][WebPerformanceCalendarRuntimeChecklist]。</span><span class="sxs-lookup"><span data-stu-id="33618-146">See [Garbage Collection in Animation in Paul Lewis' runtime performance checklist][WebPerformanceCalendarRuntimeChecklist].</span></span>  |  

<!--todo: add Optimize JavaScript runtime section when available  -->  

## <span data-ttu-id="33618-147">形式</span><span class="sxs-lookup"><span data-stu-id="33618-147">Style</span></span>  

<span data-ttu-id="33618-148">スタイルの変更が DOM 内の複数の要素に影響を与える場合は特に、スタイルの変更にはコストがかかります。</span><span class="sxs-lookup"><span data-stu-id="33618-148">Style changes are costly, especially if those changes affect more than one element in the DOM.</span></span>  <span data-ttu-id="33618-149">要素にスタイルを適用すると、ブラウザーは関連する要素への影響を把握し、レイアウトを再計算し、再描画します。</span><span class="sxs-lookup"><span data-stu-id="33618-149">Any time you apply styles to an element, the browser figures out the impact on all related elements, recalculates the layout, and repaints.</span></span>  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  
-->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

### <span data-ttu-id="33618-150">スタイル: ツール</span><span class="sxs-lookup"><span data-stu-id="33618-150">Style: Tools</span></span>  

<span data-ttu-id="33618-151">パフォーマンス パネルでレコーディング **を行** います。</span><span class="sxs-lookup"><span data-stu-id="33618-151">Take a recording in the **Performance** panel.</span></span>  <span data-ttu-id="33618-152">大きなイベント `Recalculate Style` \(purple\ で表示) の記録を確認します。</span><span class="sxs-lookup"><span data-stu-id="33618-152">Check the recording for large `Recalculate Style` events \(displayed in purple\).</span></span>  

<!--todo: add Recording section when available  -->  

<span data-ttu-id="33618-153">イベントをクリック `Recalculate Style` すると、[詳細] ウィンドウにイベントに関する詳細情報 **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="33618-153">Click on a `Recalculate Style` event to view more information about it in the **Details** pane.</span></span>  <span data-ttu-id="33618-154">スタイルの変更に時間がかかっている場合は、パフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="33618-154">If the style changes are taking a long time, that is a performance hit.</span></span>  <span data-ttu-id="33618-155">スタイルの計算が多数の要素に影響を与える場合、これは改善の必要があるもう 1 つの領域です。</span><span class="sxs-lookup"><span data-stu-id="33618-155">If the style calculations are affecting a large number of elements, that is another area with room for improvement.</span></span>  

:::image type="complex" source="../media/rendering-tools-performance-recalculate-style-summary.msft.png" alt-text="長い再計算スタイル" lightbox="../media/rendering-tools-performance-recalculate-style-summary.msft.png":::
   <span data-ttu-id="33618-157">長い再計算スタイル</span><span class="sxs-lookup"><span data-stu-id="33618-157">Long recalculate style</span></span>  
:::image-end:::  

<span data-ttu-id="33618-158">イベントの影響を軽減 `Recalculate Style` するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="33618-158">To reduce the impact of `Recalculate Style` events:</span></span>  

*   <span data-ttu-id="33618-159">CSS トリガー [を使用して、][CssTriggers] レイアウト、ペイント、およびコンポジットをトリガーする CSS プロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="33618-159">Use the [CSS Triggers][CssTriggers] to learn which CSS properties trigger layout, paint, and composite.</span></span>  <span data-ttu-id="33618-160">これらのプロパティは、レンダリングのパフォーマンスに最も大きな影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="33618-160">These properties have the worst impact on rendering performance.</span></span>  
*   <span data-ttu-id="33618-161">影響の少ないプロパティに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="33618-161">Switch to properties that have less impact.</span></span>  <!--See [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties] for more guidance.  -->  
    
<!--todo: add Stick to compositor-only properties and manage layer count section when available -->  

### <span data-ttu-id="33618-162">スタイル: 問題</span><span class="sxs-lookup"><span data-stu-id="33618-162">Style: Problems</span></span>  

<span data-ttu-id="33618-163">次の表に、一般的なスタイルの問題と考える解決策を示します。</span><span class="sxs-lookup"><span data-stu-id="33618-163">The following table describes some common style problems and potential solutions:</span></span>  

| <span data-ttu-id="33618-164">問題</span><span class="sxs-lookup"><span data-stu-id="33618-164">Problem</span></span> | <span data-ttu-id="33618-165">例</span><span class="sxs-lookup"><span data-stu-id="33618-165">Example</span></span> | <span data-ttu-id="33618-166">解決策</span><span class="sxs-lookup"><span data-stu-id="33618-166">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="33618-167">応答またはアニメーションに影響を与えるコストの高いスタイルの計算。</span><span class="sxs-lookup"><span data-stu-id="33618-167">Expensive style calculations affecting response or animation.</span></span>  | <span data-ttu-id="33618-168">幅、高さ、位置など、要素の形状を変更する CSS プロパティ。ブラウザーは他のすべての要素をチェックし、レイアウトを再計算します。</span><span class="sxs-lookup"><span data-stu-id="33618-168">Any CSS property that changes the geometry of an element, like the width, height, or position; the browser checks all other elements and recalculates the layout.</span></span>  | <span data-ttu-id="33618-169">レイアウトをトリガーする CSS を回避する</span><span class="sxs-lookup"><span data-stu-id="33618-169">Avoid CSS that triggers layouts</span></span> |  
| <span data-ttu-id="33618-170">応答またはアニメーションに影響を与える複雑なセレクター。</span><span class="sxs-lookup"><span data-stu-id="33618-170">Complex selectors affecting response or animation.</span></span>  | <span data-ttu-id="33618-171">入れ子になったセレクターは、親と子を含む他のすべての要素に関する情報をブラウザーに強制的に知らします。</span><span class="sxs-lookup"><span data-stu-id="33618-171">Nested selectors force the browser to know everything about all the other elements, including parents and children.</span></span>  | <span data-ttu-id="33618-172">クラスだけで CSS の要素を参照します。</span><span class="sxs-lookup"><span data-stu-id="33618-172">Reference an element in your CSS with just a class.</span></span>  |  

<!--todo: add Avoid CSS that triggers layouts section when available -->  
<!--todo: add Reduce the Scope and Complexity of Styles Calculations (Reference an element in your CSS with just a class) section when available -->  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  -->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

## <span data-ttu-id="33618-173">レイアウト</span><span class="sxs-lookup"><span data-stu-id="33618-173">Layout</span></span>  

<span data-ttu-id="33618-174">レイアウト (または Firefox でのリフロー) は、ブラウザーがページ上のすべての要素の位置とサイズを計算するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="33618-174">Layout (or reflow in Firefox) is the process by which the browser calculates the positions and sizes of all the elements on a page.</span></span>  <span data-ttu-id="33618-175">Web のレイアウト モデルは、1 つの要素が他の要素に影響を与える可能性を意味します。たとえば、要素の幅は、通常、すべての子要素の幅に影響を与え、ツリーを上下に移動 `<body>` します。</span><span class="sxs-lookup"><span data-stu-id="33618-175">The layout model of the web means that one element may affect others; for example, the width of the `<body>` element typically affects the widths of any child elements, and so on, all the way up and down the tree.</span></span>  <span data-ttu-id="33618-176">このプロセスは、ブラウザーに非常に関係する場合があります。</span><span class="sxs-lookup"><span data-stu-id="33618-176">The process may be quite involved for the browser.</span></span>  

<span data-ttu-id="33618-177">一般的な経験として、フレームが完成する前に DOM から幾何学的な価値を求める場合は、"強制同期レイアウト" を使用します。これは、頻繁に繰り返したり、大規模な DOM ツリーに対して実行したりすると、パフォーマンスが大きなボトルネックになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="33618-177">As a general rule of thumb, if you ask for a geometric value back from the DOM before a frame is complete, you are going to find yourself with "forced synchronous layouts", which may be a big performance bottleneck if repeated frequently or performed for a large DOM tree.</span></span>  

<!--Related Guides:  

*   [Avoid Layout Thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts]  
*   [Diagnose Forced Synchronous Layouts][DevtoolsRenderingToolsForcedSynchronousLayouts]  -->  

<!--todo: add Avoid CSS that triggers layouts (Avoid Layout Thrashing) section when available -->  
<!--todo: add Diagnose Forced Synchronous Layouts section when available  -->  

### <span data-ttu-id="33618-178">レイアウト: ツール</span><span class="sxs-lookup"><span data-stu-id="33618-178">Layout: Tools</span></span>  

<span data-ttu-id="33618-179">[ **パフォーマンス]** ウィンドウは、ページが強制同期レイアウトの原因となる場合を識別します。</span><span class="sxs-lookup"><span data-stu-id="33618-179">The **Performance** pane identifies when a page causes forced synchronous layouts.</span></span>  <span data-ttu-id="33618-180">これらの `Layout` イベントは赤いバーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="33618-180">These `Layout` events are marked with red bars.</span></span>  

:::image type="complex" source="../media/rendering-tools-jank-performance-recalculate-style-summary.msft.png" alt-text="強制同期レイアウト" lightbox="../media/rendering-tools-jank-performance-recalculate-style-summary.msft.png":::
   <span data-ttu-id="33618-182">強制同期レイアウト</span><span class="sxs-lookup"><span data-stu-id="33618-182">Forced synchronous layout</span></span>  
:::image-end:::  

<span data-ttu-id="33618-183">"レイアウトのスラッシュ" は、強制的な同期レイアウト条件の繰り返しです。</span><span class="sxs-lookup"><span data-stu-id="33618-183">"Layout thrashing" is a repetition of forced synchronous layout conditions.</span></span>  <span data-ttu-id="33618-184">これは、JavaScript が DOM の書き込みと読み取りを繰り返し行う場合に発生します。これにより、ブラウザーはレイアウトを何度も再計算する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33618-184">This occurs when JavaScript writes and reads from the DOM repeatedly, which forces the browser to recalculate the layout over and over.</span></span>  <span data-ttu-id="33618-185">レイアウトのスラッシュを特定するには、複数の強制同期レイアウト警告のパターンを探します。</span><span class="sxs-lookup"><span data-stu-id="33618-185">To identify layout thrashing, look for a pattern of multiple forced synchronous layout warnings.</span></span>  <span data-ttu-id="33618-186">前の図を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33618-186">See the previous figure.</span></span>  

### <span data-ttu-id="33618-187">レイアウト: 問題</span><span class="sxs-lookup"><span data-stu-id="33618-187">Layout: Problems</span></span>  

<span data-ttu-id="33618-188">次の表に、一般的なレイアウトの問題と考える解決策を示します。</span><span class="sxs-lookup"><span data-stu-id="33618-188">The following table describes some common layout problems and potential solutions:</span></span>  

| <span data-ttu-id="33618-189">問題</span><span class="sxs-lookup"><span data-stu-id="33618-189">Problem</span></span> | <span data-ttu-id="33618-190">例</span><span class="sxs-lookup"><span data-stu-id="33618-190">Example</span></span> | <span data-ttu-id="33618-191">解決策</span><span class="sxs-lookup"><span data-stu-id="33618-191">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="33618-192">応答またはアニメーションに影響を与える強制同期レイアウト。</span><span class="sxs-lookup"><span data-stu-id="33618-192">Forced synchronous layout affecting response or animation.</span></span>  | <span data-ttu-id="33618-193">ブラウザーがピクセル パイプラインの前の方でレイアウトを実行し、レンダリング プロセスで繰り返しの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="33618-193">Forcing the browser to perform layout earlier in the pixel pipeline, resulting in repeating steps in the rendering process.</span></span>  | <span data-ttu-id="33618-194">最初にスタイルの読み取りをバッチ処理してから、書き込みを行います。</span><span class="sxs-lookup"><span data-stu-id="33618-194">Batch your style reads first, then do any writes.</span></span>  <!--See also [Avoid large, complex layouts and layout thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts].  -->  |  
| <span data-ttu-id="33618-195">応答またはアニメーションに影響を与えるレイアウトのスラッシュ。</span><span class="sxs-lookup"><span data-stu-id="33618-195">Layout thrashing affecting response or animation.</span></span>  | <span data-ttu-id="33618-196">ブラウザーを読み取り/書き込み/読み取り/書き込みサイクルに入れ、ブラウザーでレイアウトを何度も再計算するループ。</span><span class="sxs-lookup"><span data-stu-id="33618-196">A loop that puts the browser into a read-write-read-write cycle, forcing the browser to recalculate layout over and over again.</span></span>  | <span data-ttu-id="33618-197">FastDom ライブラリを使用して読み取り/書き込み [操作を自動的にバッチ処理します][GitHubWilsonpageFastdom]。</span><span class="sxs-lookup"><span data-stu-id="33618-197">Automatically batch read-write operations using [FastDom library][GitHubWilsonpageFastdom].</span></span>  |  

<!--todo: add Avoid CSS that triggers layouts (Avoid large, complex layouts and layout thrashing) section when available -->  

## <span data-ttu-id="33618-198">ペイントとコンポジット</span><span class="sxs-lookup"><span data-stu-id="33618-198">Paint and composite</span></span>  

<span data-ttu-id="33618-199">ペイントは、ピクセル単位で塗り分けするプロセスです。</span><span class="sxs-lookup"><span data-stu-id="33618-199">Paint is the process of filling in pixels.</span></span>  <span data-ttu-id="33618-200">多くの場合、レンダリング プロセスの中で最もコストの高い部分です。</span><span class="sxs-lookup"><span data-stu-id="33618-200">It is often the most costly part of the rendering process.</span></span>  <span data-ttu-id="33618-201">何かの方法でページが不気味なページである場合は、ペイントの問題が発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="33618-201">If you noticed that your page is janky in any way, it is likely that you have paint problems.</span></span>  

<span data-ttu-id="33618-202">合成とは、ページの塗り分けされた部分を画面に表示する場所です。</span><span class="sxs-lookup"><span data-stu-id="33618-202">Compositing is where the painted parts of the page are put together for displaying on screen.</span></span>  <span data-ttu-id="33618-203">ほとんどの場合、コンポジター専用のプロパティを使用し、ペイントを完全に回避すると、パフォーマンスが大幅に向上しますが、過剰なレイヤー数に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33618-203">For the most part, if you stick to compositor-only properties and avoid paint altogether, you should see a major improvement in performance, but you need to watch out for excessive layer counts.</span></span>  <!--See also [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  

<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

### <span data-ttu-id="33618-204">ペイントとコンポジット: ツール</span><span class="sxs-lookup"><span data-stu-id="33618-204">Paint and composite: Tools</span></span>  

<span data-ttu-id="33618-205">塗り分けにかかる時間や、塗り分けにかかる頻度を知りたい場合は、</span><span class="sxs-lookup"><span data-stu-id="33618-205">Want to know how long painting takes or how often painting occurs?</span></span>  <span data-ttu-id="33618-206">[パフォーマンス][パネルで [高度なペイントイン][DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation]**ストル**メンテーションを有効にする] 設定をオンにし、記録を取る。</span><span class="sxs-lookup"><span data-stu-id="33618-206">Check the [Enable advanced paint instrumentation][DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation] setting in the **Performance** panel and then take a recording.</span></span>  <span data-ttu-id="33618-207">ほとんどのレンダリング時間が描画に費やされている場合は、ペイントの問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="33618-207">If most of your rendering time is spent painting, you have paint problems.</span></span>  

<!--
:::image type="complex" source="../media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png" alt-text="Long paint times in timeline recording" lightbox="../media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png":::
   Long paint times in timeline recording  
:::image-end:::  
-->  

<!--
Check out the **Rendering** panel for further configurations that are able to help you diagnose paint problems.  -->  

<!--todo: link Rendering panel in ../evaluate-performance/timeline-tool  sub-section when live  -->  

### <span data-ttu-id="33618-208">ペイントとコンポジット: 問題</span><span class="sxs-lookup"><span data-stu-id="33618-208">Paint and composite: Problems</span></span>  

<span data-ttu-id="33618-209">次の表に、一般的なペイントと複合の問題と考える解決策を示します。</span><span class="sxs-lookup"><span data-stu-id="33618-209">The following table describes some common paint and composite problems and potential solutions:</span></span>  

| <span data-ttu-id="33618-210">問題</span><span class="sxs-lookup"><span data-stu-id="33618-210">Problem</span></span> | <span data-ttu-id="33618-211">例</span><span class="sxs-lookup"><span data-stu-id="33618-211">Example</span></span> | <span data-ttu-id="33618-212">解決策</span><span class="sxs-lookup"><span data-stu-id="33618-212">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="33618-213">応答またはアニメーションに影響を与えるペイント ストーム。</span><span class="sxs-lookup"><span data-stu-id="33618-213">Paint storms affecting response or animation.</span></span>  | <span data-ttu-id="33618-214">大きなペイント領域や、応答やアニメーションに影響を与える高価なペイント。</span><span class="sxs-lookup"><span data-stu-id="33618-214">Big paint areas or expensive paints affecting response or animation.</span></span>  | <span data-ttu-id="33618-215">ペイントを使うのを避け、独自のレイヤーに移動する要素を昇格し、変換と不透明度を使います。</span><span class="sxs-lookup"><span data-stu-id="33618-215">Avoid paint, promote elements that are moving to their own layer, use transforms and opacity.</span></span>  <!--See [Simplify paint complexity and reduce paint areas][WebFundamentalsPerformanceRenderingSimplifyPaintComplexity].  -->  |  
| <span data-ttu-id="33618-216">アニメーションに影響を与えるレイヤー のエクスプリング。</span><span class="sxs-lookup"><span data-stu-id="33618-216">Layer explosions affecting animations.</span></span>  | <span data-ttu-id="33618-217">要素が多すぎると、アニメーションのパフォーマンスに大 `translateZ(0)` きな影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="33618-217">Overpromotion of too many elements with `translateZ(0)` greatly affects animation performance.</span></span>  | <span data-ttu-id="33618-218">レイヤーに積極的に昇格します。それがわかっている場合にのみ、具体的な改善が提供されます。</span><span class="sxs-lookup"><span data-stu-id="33618-218">Promote to layers sparingly, and only when you know it offers tangible improvements.</span></span>  <!--See [Stick to composite-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  |  

<!--todo: add Simplify paint complexity and reduce paint areas section when available  -->  
<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

## <span data-ttu-id="33618-219">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="33618-219">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsRenderingToolsJavascriptRuntime]: ./js-runtime.md "JavaScript ランタイムを高速化する |Microsoft Docs"  
[DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation]: ../evaluate-performance/reference.md#turn-on-advanced-paint-instrumentation "高度なペイントインストルメンテーションを有効にする - パフォーマンス分析リファレンス |Microsoft Docs"

<!--[DevtoolsRenderingToolsForcedSynchronousLayouts]: ./rendering-tools/forced-synchronous-layouts.md "Diagnose Forced Synchronous Layouts | Microsoft Docs"  -->  

<!-- The Timeline Tool page is deprecated  -->  
<!--[DevtoolsEvaluatePerformanceTimelineToolProfileJavascript]: ../evaluate-performance/timeline-tool#profile-javascript "Profile JavaScript - How to Use the Timeline Tool | Microsoft Docs"  -->  
<!--[DevtoolsEvaluatePerformanceTimelineToolProfilePainting]: ../evaluate-performance/timeline-tool#profile-painting "Profile painting - How to Use the Timeline Tool | Microsoft Docs"  -->  
<!--[DevtoolsEvaluatePerformanceTimelineToolRecording]: ../evaluate-performance/timeline-tool#make-a-recording "Make a recording - How to Use the Timeline Tool | Microsoft Docs"  -->  
<!--[DevtoolsEvaluatePerformanceTimelineToolRenderingSettings]: ../evaluate-performance/timeline-tool#rendering-settings "Rendering settings - How to Use the Timeline Tool | Microsoft Docs"  -->  

<!--[WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts]: /web/fundamentals/performance/rendering/avoid-large-complex-layouts-and-layout-thrashing "Avoid Large, Complex Layouts, and Layout Thrashing"  -->  
<!--[WebFundamentalsPerformanceRenderingOptimizeJavascriptRuntime]: /web/fundamentals/performance/rendering/optimize-javascript-execution "Optimize JavaScript Runtime"  -->  
<!--[WebFundamentalsPerformanceRenderingReduceScope]: /web/fundamentals/performance/rendering/reduce-the-scope-and-complexity-of-style-calculations "Reduce the Scope and Complexity of Style Calculations"  -->  
<!--[WebFundamentalsPerformanceRenderingSimplifyPaintComplexity]: /web/fundamentals/performance/rendering/simplify-paint-complexity-and-reduce-paint-areas "Simplify Paint Complexity and Reduce Paint Areas"  -->  
<!--[WebFundamentalsPerformanceRenderingCompositorOnlyProperties]: /web/fundamentals/performance/rendering/stick-to-compositor-only-properties-and-manage-layer-count "Stick to Compositor-Only Properties and Manage Layer Count"  -->  

[CssTriggers]: https://csstriggers.com "CSS トリガー"  

[MDNUsingWebWorkers]: https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers "Web ワーカーを使用する |MDN"  

[WebPerformanceCalendarRuntimeChecklist]: https://calendar.perfplanet.com/2013/the-runtime-performance-checklist/ "ランタイム パフォーマンス チェックリスト - Web パフォーマンス カレンダー"  

[GitHubWilsonpageFastdom]: https://github.com/wilsonpage/fastdom "wilsonpage/fastdom |GitHub"  

> [!NOTE]
> <span data-ttu-id="33618-226">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="33618-226">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="33618-227">元のページはここから[](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/index)見つかり[、Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Writer\) と[Meggin Kearney][MegginKearney] \(Tech Writer\) が執筆しています。</span><span class="sxs-lookup"><span data-stu-id="33618-227">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="33618-229">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="33618-229">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
