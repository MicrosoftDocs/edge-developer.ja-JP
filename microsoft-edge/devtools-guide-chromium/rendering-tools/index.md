---
description: ユーザーは、対話的でスムーズなページを期待しています。  ピクセル パイプラインの各ステージは、jank を導入する機会を表します。  ランタイムのパフォーマンスを低下させる一般的な問題を特定して修正するためのツールと戦略について説明します。
title: 実行時のパフォーマンスを分析する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 646db5b2e88e33b109e5eb3ae01a296bf3a4fb46
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398001"
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

# <a name="analyze-runtime-performance"></a><span data-ttu-id="a2f5c-106">実行時のパフォーマンスを分析する</span><span class="sxs-lookup"><span data-stu-id="a2f5c-106">Analyze runtime performance</span></span>  

<span data-ttu-id="a2f5c-107">ユーザーは、対話的でスムーズなページを期待しています。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-107">Users expects interactive and smooth pages.</span></span>  <span data-ttu-id="a2f5c-108">ピクセル パイプラインの各ステージは、jank を導入する機会を表します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-108">Each stage in the pixel pipeline represents an opportunity to introduce jank.</span></span>  <span data-ttu-id="a2f5c-109">ランタイムのパフォーマンスを低下させる一般的な問題を特定して修正するためのツールと戦略について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-109">Learn about tools and strategies to identify and fix common problems that slow down runtime performance.</span></span>  

### <a name="summary"></a><span data-ttu-id="a2f5c-110">要約</span><span class="sxs-lookup"><span data-stu-id="a2f5c-110">Summary</span></span>  

*   <span data-ttu-id="a2f5c-111">ブラウザーにレイアウトの再計算を強制的に適用する JavaScript を記述しない。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-111">Do not write JavaScript that forces the browser to recalculate layout.</span></span>  <span data-ttu-id="a2f5c-112">読み取り関数と書き込み関数を分離し、最初に読み取りを実行します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-112">Separate read and write functions, and perform reads first.</span></span>  
*   <span data-ttu-id="a2f5c-113">CSS を複雑にし過ぎない。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-113">Do not over-complicate your CSS.</span></span>  <span data-ttu-id="a2f5c-114">CSS を少なくし、CSS セレクターをシンプルに保つ。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-114">Use less CSS and keep your CSS selectors simple.</span></span>  
*   <span data-ttu-id="a2f5c-115">レイアウトは可能な限り避ける。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-115">Avoid layout as much as possible.</span></span>  <span data-ttu-id="a2f5c-116">レイアウトを全くトリガーしない CSS を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-116">Choose CSS that does not trigger layout at all.</span></span>  
*   <span data-ttu-id="a2f5c-117">ペイントには、他のレンダリング アクティビティよりも時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-117">Painting may take up more time than any other rendering activity.</span></span>  <span data-ttu-id="a2f5c-118">ペイントのボトルネックに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-118">Watch out for paint bottlenecks.</span></span>  
    
## <a name="javascript"></a><span data-ttu-id="a2f5c-119">JavaScript</span><span class="sxs-lookup"><span data-stu-id="a2f5c-119">JavaScript</span></span>  

<span data-ttu-id="a2f5c-120">JavaScript の計算、特に大規模な視覚的な変更をトリガーする計算では、アプリケーションのパフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-120">JavaScript calculations, especially ones that trigger extensive visual changes, may stall application performance.</span></span>  <span data-ttu-id="a2f5c-121">時間が悪い、または長時間実行されている JavaScript がユーザーの操作に干渉しないようにします。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-121">Do not let badly-timed or long-running JavaScript interfere with user interactions.</span></span>  

### <a name="javascript-tools"></a><span data-ttu-id="a2f5c-122">JavaScript: ツール</span><span class="sxs-lookup"><span data-stu-id="a2f5c-122">JavaScript: Tools</span></span>  

<span data-ttu-id="a2f5c-123">パフォーマンス ツールで記録を **取り** 、疑わしい長いイベントを探 `Evaluate Script` します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-123">Take a recording in the **Performance** tool and look for suspiciously long `Evaluate Script` events.</span></span>  <!--If you find any, you are able to enable the **JS Profiler** and re-do your recording to get more detailed information about exactly which JavaScript functions were used and how long each took.  -->  

<!--todo: add Recording section when available  -->  
<!--todo: add Profile JavaScript (JS Profiler) section when available  -->  

<span data-ttu-id="a2f5c-124">JavaScript でかなりのジャンクに気が付く場合は、分析を次のレベルに進めて JavaScript CPU プロファイルを収集する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-124">f you noticing quite a bit of jank in your JavaScript, you may need to take your analysis to the next level and collect a JavaScript CPU profile.</span></span>  <span data-ttu-id="a2f5c-125">CPU プロファイルは、ページの機能内でランタイムが使用される場所を示します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-125">CPU profiles show where runtime is spent within the functions of your page.</span></span>  <span data-ttu-id="a2f5c-126">JavaScript ランタイムの高速化で CPU プロファイルを作成 [する方法について説明します][DevtoolsRenderingToolsJavascriptRuntime]。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-126">Learn how to create CPU profiles in [Speed Up JavaScript Runtime][DevtoolsRenderingToolsJavascriptRuntime].</span></span>

### <a name="javascript-problems"></a><span data-ttu-id="a2f5c-127">JavaScript: 問題</span><span class="sxs-lookup"><span data-stu-id="a2f5c-127">JavaScript: Problems</span></span>  

<span data-ttu-id="a2f5c-128">次の表では、一般的な JavaScript の問題と潜在的な解決策について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-128">The following table describes some common JavaScript problems and potential solutions.</span></span>  

| <span data-ttu-id="a2f5c-129">問題</span><span class="sxs-lookup"><span data-stu-id="a2f5c-129">Problem</span></span> | <span data-ttu-id="a2f5c-130">例</span><span class="sxs-lookup"><span data-stu-id="a2f5c-130">Example</span></span> | <span data-ttu-id="a2f5c-131">ソリューション</span><span class="sxs-lookup"><span data-stu-id="a2f5c-131">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="a2f5c-132">応答またはアニメーションに影響を与える高価な入力ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-132">Expensive input handlers affecting response or animation.</span></span>  | <span data-ttu-id="a2f5c-133">タッチ、視差スクロール。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-133">Touch, parallax scrolling.</span></span>  | <span data-ttu-id="a2f5c-134">ブラウザーでタッチとスクロールを処理するか、リスナーを可能な限り遅くバインドします。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-134">Let the browser handle touch and scrolls, or bind the listener as late as possible.</span></span>  <span data-ttu-id="a2f5c-135">Paul [Lewis のランタイム パフォーマンス チェックリストの [高価な入力ハンドラー] に移動します][WebPerformanceCalendarRuntimeChecklist]。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-135">Navigate to [Expensive Input Handlers in Paul Lewis' runtime performance checklist][WebPerformanceCalendarRuntimeChecklist].</span></span>  |  
| <span data-ttu-id="a2f5c-136">応答、アニメーション、読み込みに影響を与える JavaScript の時間が悪い。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-136">Badly-timed JavaScript affecting response, animation, load.</span></span>  | <span data-ttu-id="a2f5c-137">ユーザーはページ読み込み直後にスクロールします。setTimeout /setInterval。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-137">User scrolls right after page load, setTimeout / setInterval.</span></span>  | <span data-ttu-id="a2f5c-138">JavaScript ランタイムの最適化: Use `requestAnimationFrame` 、フレームに DOM 操作を広げる [、Web ワーカーを使用する][MDNUsingWebWorkers]。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-138">Optimize JavaScript runtime: use `requestAnimationFrame`, spread DOM manipulation over frames, use [Web Workers][MDNUsingWebWorkers].</span></span>  |  
| <span data-ttu-id="a2f5c-139">応答に影響を与える JavaScript の実行時間が長い。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-139">Long-running JavaScript affecting response.</span></span>  | <span data-ttu-id="a2f5c-140">[DOMContentLoaded イベントは][MDNUsingWebWorkers]、JS の動作に合ってストールします。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-140">The [DOMContentLoaded event][MDNUsingWebWorkers] stalls as it is swamped with JS work.</span></span>  | <span data-ttu-id="a2f5c-141">純粋な計算作業を [Web ワーカーに移動します][MDNUsingWebWorkers]。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-141">Move pure computational work to [Web Workers][MDNUsingWebWorkers].</span></span>  <span data-ttu-id="a2f5c-142">DOM アクセスが必要な場合は、 を使用します `requestAnimationFrame` 。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-142">If you need DOM access, use `requestAnimationFrame`.</span></span>  <!--Navigate to [Optimize JavaScript Execution][WebFundamentalsPerformanceRenderingOptimizeJavascriptRuntime].  -->  |  
| <span data-ttu-id="a2f5c-143">応答またはアニメーションに影響を与えるガベージ y スクリプト。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-143">Garbage-y scripts affecting response or animation.</span></span>  | <span data-ttu-id="a2f5c-144">ガベージ コレクションは、任意の場所で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-144">Garbage collection may happen anywhere.</span></span>  | <span data-ttu-id="a2f5c-145">ガベージ y スクリプトを少なくします。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-145">Write less garbage-y scripts.</span></span>  <span data-ttu-id="a2f5c-146">Paul [Lewis のランタイム パフォーマンス チェックリストの [アニメーション] の [ガベージ コレクション] に移動します][WebPerformanceCalendarRuntimeChecklist]。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-146">Navigate to [Garbage Collection in Animation in Paul Lewis' runtime performance checklist][WebPerformanceCalendarRuntimeChecklist].</span></span>  |  

<!--todo: add Optimize JavaScript runtime section when available  -->  

## <a name="style"></a><span data-ttu-id="a2f5c-147">形式</span><span class="sxs-lookup"><span data-stu-id="a2f5c-147">Style</span></span>  

<span data-ttu-id="a2f5c-148">スタイルの変更は、特にこれらの変更が DOM 内の複数の要素に影響を与える場合、コストがかかります。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-148">Style changes are costly, especially if those changes affect more than one element in the DOM.</span></span>  <span data-ttu-id="a2f5c-149">要素にスタイルを適用すると、ブラウザーは関連する要素への影響を把握し、レイアウトを再計算し、再描画します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-149">Any time you apply styles to an element, the browser figures out the impact on all related elements, recalculates the layout, and repaints.</span></span>  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  
-->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

### <a name="style-tools"></a><span data-ttu-id="a2f5c-150">スタイル: ツール</span><span class="sxs-lookup"><span data-stu-id="a2f5c-150">Style: Tools</span></span>  

<span data-ttu-id="a2f5c-151">パフォーマンス ツールで記録 **を取** る。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-151">Take a recording in the **Performance** tool.</span></span>  <span data-ttu-id="a2f5c-152">大きなイベント `Recalculate Style` \(紫で表示される\) の記録を確認します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-152">Check the recording for large `Recalculate Style` events \(displayed in purple\).</span></span>  

<!--todo: add Recording section when available  -->  

<span data-ttu-id="a2f5c-153">詳細ウィンドウ `Recalculate Style` でイベントの詳細を表示するには、イベントを **選択** します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-153">Choose a `Recalculate Style` event to view more information about it in the **Details** pane.</span></span>  <span data-ttu-id="a2f5c-154">スタイルの変更に時間がかかっている場合は、パフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-154">If the style changes are taking a long time, that is a performance hit.</span></span>  <span data-ttu-id="a2f5c-155">スタイルの計算が多数の要素に影響を与える場合は、改善の必要があるもう 1 つの領域です。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-155">If the style calculations are affecting a large number of elements, that is another area with room for improvement.</span></span>  

:::image type="complex" source="../media/rendering-tools-performance-recalculate-style-summary.msft.png" alt-text="長い再計算スタイル" lightbox="../media/rendering-tools-performance-recalculate-style-summary.msft.png":::
   <span data-ttu-id="a2f5c-157">長い再計算スタイル</span><span class="sxs-lookup"><span data-stu-id="a2f5c-157">Long recalculate style</span></span>  
:::image-end:::  

<span data-ttu-id="a2f5c-158">イベントの影響を軽減 `Recalculate Style` するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-158">To reduce the impact of `Recalculate Style` events:</span></span>  

*   <span data-ttu-id="a2f5c-159">CSS トリガー [を使用して、][CssTriggers] レイアウト、ペイント、コンポジットをトリガーする CSS プロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-159">Use the [CSS Triggers][CssTriggers] to learn which CSS properties trigger layout, paint, and composite.</span></span>  <span data-ttu-id="a2f5c-160">これらのプロパティは、レンダリングパフォーマンスに最悪の影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-160">These properties have the worst impact on rendering performance.</span></span>  
*   <span data-ttu-id="a2f5c-161">影響の少ないプロパティに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-161">Switch to properties that have less impact.</span></span>  <!--For more guidance, navigate to [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  
    
<!--todo: add Stick to compositor-only properties and manage layer count section when available -->  

### <a name="style-problems"></a><span data-ttu-id="a2f5c-162">スタイル: 問題</span><span class="sxs-lookup"><span data-stu-id="a2f5c-162">Style: Problems</span></span>  

<span data-ttu-id="a2f5c-163">次の表では、一般的なスタイルの問題と潜在的な解決策について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-163">The following table describes some common style problems and potential solutions.</span></span>  

| <span data-ttu-id="a2f5c-164">問題</span><span class="sxs-lookup"><span data-stu-id="a2f5c-164">Problem</span></span> | <span data-ttu-id="a2f5c-165">例</span><span class="sxs-lookup"><span data-stu-id="a2f5c-165">Example</span></span> | <span data-ttu-id="a2f5c-166">ソリューション</span><span class="sxs-lookup"><span data-stu-id="a2f5c-166">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="a2f5c-167">応答またはアニメーションに影響を与える高価なスタイルの計算。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-167">Expensive style calculations affecting response or animation.</span></span>  | <span data-ttu-id="a2f5c-168">幅、高さ、位置など、要素のジオメトリを変更する CSS プロパティ。ブラウザーは他のすべての要素をチェックし、レイアウトを再計算します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-168">Any CSS property that changes the geometry of an element, like the width, height, or position; the browser checks all other elements and recalculates the layout.</span></span>  | <span data-ttu-id="a2f5c-169">レイアウトをトリガーする CSS を回避する</span><span class="sxs-lookup"><span data-stu-id="a2f5c-169">Avoid CSS that triggers layouts</span></span> |  
| <span data-ttu-id="a2f5c-170">応答またはアニメーションに影響を与える複雑なセレクター。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-170">Complex selectors affecting response or animation.</span></span>  | <span data-ttu-id="a2f5c-171">入れ子になったセレクターは、親と子を含む他のすべての要素についてブラウザーに知らされます。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-171">Nested selectors force the browser to know everything about all the other elements, including parents and children.</span></span>  | <span data-ttu-id="a2f5c-172">クラスだけで CSS の要素を参照します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-172">Reference an element in your CSS with just a class.</span></span>  |  

<!--todo: add Avoid CSS that triggers layouts section when available -->  
<!--todo: add Reduce the Scope and Complexity of Styles Calculations (Reference an element in your CSS with just a class) section when available -->  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  -->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

## <a name="layout"></a><span data-ttu-id="a2f5c-173">レイアウト</span><span class="sxs-lookup"><span data-stu-id="a2f5c-173">Layout</span></span>  

<span data-ttu-id="a2f5c-174">レイアウト (または Firefox でのリフロー) は、ブラウザーがページ上のすべての要素の位置とサイズを計算するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-174">Layout (or reflow in Firefox) is the process by which the browser calculates the positions and sizes of all the elements on a page.</span></span>  <span data-ttu-id="a2f5c-175">Web のレイアウト モデルは、1 つの要素が他の要素に影響を与える可能性を意味します。たとえば、要素の幅は、通常、ツリーの上下のすべての方法で、任意の子要素の幅に `<body>` 影響します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-175">The layout model of the web means that one element may affect others; for example, the width of the `<body>` element typically affects the widths of any child elements, and so on, all the way up and down the tree.</span></span>  <span data-ttu-id="a2f5c-176">このプロセスは、ブラウザーに非常に関係している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-176">The process may be quite involved for the browser.</span></span>  

<span data-ttu-id="a2f5c-177">一般的な経験則として、フレームが完成する前に DOM から幾何学的な値を返す必要がある場合は、"強制同期レイアウト" を使用します。これは、頻繁に繰り返したり、大規模な DOM ツリーに対して実行したりすると、パフォーマンスのボトルネックが大きい可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-177">As a general rule of thumb, if you ask for a geometric value back from the DOM before a frame is complete, you are going to find yourself with "forced synchronous layouts", which may be a big performance bottleneck if repeated frequently or performed for a large DOM tree.</span></span>  

<!--Related Guides:  

*   [Avoid Layout Thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts]  
*   [Diagnose Forced Synchronous Layouts][DevtoolsRenderingToolsForcedSynchronousLayouts]  -->  

<!--todo: add Avoid CSS that triggers layouts (Avoid Layout Thrashing) section when available -->  
<!--todo: add Diagnose Forced Synchronous Layouts section when available  -->  

### <a name="layout-tools"></a><span data-ttu-id="a2f5c-178">レイアウト: ツール</span><span class="sxs-lookup"><span data-stu-id="a2f5c-178">Layout: Tools</span></span>  

<span data-ttu-id="a2f5c-179">[ **パフォーマンス]** ウィンドウは、ページが強制的に同期レイアウトを発生させる原因を識別します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-179">The **Performance** pane identifies when a page causes forced synchronous layouts.</span></span>  <span data-ttu-id="a2f5c-180">これらの `Layout` イベントは赤いバーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-180">These `Layout` events are marked with red bars.</span></span>  

:::image type="complex" source="../media/rendering-tools-jank-performance-recalculate-style-summary.msft.png" alt-text="強制同期レイアウト" lightbox="../media/rendering-tools-jank-performance-recalculate-style-summary.msft.png":::
   <span data-ttu-id="a2f5c-182">強制同期レイアウト</span><span class="sxs-lookup"><span data-stu-id="a2f5c-182">Forced synchronous layout</span></span>  
:::image-end:::  

<span data-ttu-id="a2f5c-183">"レイアウトスラッシング" は、強制的な同期レイアウト条件の繰り返しです。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-183">"Layout thrashing" is a repetition of forced synchronous layout conditions.</span></span>  <span data-ttu-id="a2f5c-184">これは、JavaScript が DOM から繰り返し書き込みおよび読み取りを行い、ブラウザーがレイアウトを何度も再計算する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-184">This occurs when JavaScript writes and reads from the DOM repeatedly, which forces the browser to recalculate the layout over and over.</span></span>  <span data-ttu-id="a2f5c-185">レイアウトのスラッシングを特定するには、複数の強制同期レイアウト警告のパターンを探します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-185">To identify layout thrashing, look for a pattern of multiple forced synchronous layout warnings.</span></span>  <span data-ttu-id="a2f5c-186">前の図を確認します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-186">Review the previous figure.</span></span>  

### <a name="layout-problems"></a><span data-ttu-id="a2f5c-187">レイアウト: 問題</span><span class="sxs-lookup"><span data-stu-id="a2f5c-187">Layout: Problems</span></span>  

<span data-ttu-id="a2f5c-188">次の表では、一般的なレイアウトの問題と潜在的な解決策について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-188">The following table describes some common layout problems and potential solutions.</span></span>  

| <span data-ttu-id="a2f5c-189">問題</span><span class="sxs-lookup"><span data-stu-id="a2f5c-189">Problem</span></span> | <span data-ttu-id="a2f5c-190">例</span><span class="sxs-lookup"><span data-stu-id="a2f5c-190">Example</span></span> | <span data-ttu-id="a2f5c-191">ソリューション</span><span class="sxs-lookup"><span data-stu-id="a2f5c-191">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="a2f5c-192">応答またはアニメーションに影響を与える強制的な同期レイアウト。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-192">Forced synchronous layout affecting response or animation.</span></span>  | <span data-ttu-id="a2f5c-193">ブラウザーにピクセル パイプラインのレイアウトを実行する前に、レンダリング プロセスの手順を繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-193">Forcing the browser to perform layout earlier in the pixel pipeline, resulting in repeating steps in the rendering process.</span></span>  | <span data-ttu-id="a2f5c-194">スタイルの読み取りを最初にバッチ処理してから、書き込みを行います。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-194">Batch your style reads first, then do any writes.</span></span>  <!--Navigate to [Avoid large, complex layouts and layout thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts].  -->  |  
| <span data-ttu-id="a2f5c-195">応答またはアニメーションに影響を与えるレイアウトのスラッシング。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-195">Layout thrashing affecting response or animation.</span></span>  | <span data-ttu-id="a2f5c-196">ブラウザーを読み取り/書き込み/読み取り/書き込みサイクルに入れ、ブラウザーがレイアウトを何度も再計算するループ。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-196">A loop that puts the browser into a read-write-read-write cycle, forcing the browser to recalculate layout over and over again.</span></span>  | <span data-ttu-id="a2f5c-197">FastDom ライブラリを使用して読み取り/書き込み [操作を自動的にバッチ処理します][GitHubWilsonpageFastdom]。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-197">Automatically batch read-write operations using [FastDom library][GitHubWilsonpageFastdom].</span></span>  |  

<!--todo: add Avoid CSS that triggers layouts (Avoid large, complex layouts and layout thrashing) section when available -->  

## <a name="paint-and-composite"></a><span data-ttu-id="a2f5c-198">ペイントとコンポジット</span><span class="sxs-lookup"><span data-stu-id="a2f5c-198">Paint and composite</span></span>  

<span data-ttu-id="a2f5c-199">ペイントは、ピクセル単位で塗り分けするプロセスです。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-199">Paint is the process of filling in pixels.</span></span>  <span data-ttu-id="a2f5c-200">多くの場合、レンダリング プロセスの最もコストの高い部分です。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-200">It is often the most costly part of the rendering process.</span></span>  <span data-ttu-id="a2f5c-201">ページがデザイン通り動作していない場合は、ペイントの問題が発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-201">If you noticed that your page is not working as designed in any way, it is likely that you have paint problems.</span></span>  

<span data-ttu-id="a2f5c-202">合成とは、ページの塗られた部分を画面に表示するための組み合わせて作成する場所です。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-202">Compositing is where the painted parts of the page are put together for displaying on screen.</span></span>  <span data-ttu-id="a2f5c-203">ほとんどの場合、コンポジター専用のプロパティに固執し、ペイントを完全に避ける場合は、パフォーマンスが大幅に向上しますが、過剰なレイヤー数に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-203">For the most part, if you stick to compositor-only properties and avoid paint altogether, you should notice a major improvement in performance, but you need to watch out for excessive layer counts.</span></span>  <!--Navigate to [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  

<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

### <a name="paint-and-composite-tools"></a><span data-ttu-id="a2f5c-204">ペイントとコンポジット: ツール</span><span class="sxs-lookup"><span data-stu-id="a2f5c-204">Paint and composite: Tools</span></span>  

<span data-ttu-id="a2f5c-205">ペイントにかかる時間や、ペイントが発生する頻度を知りたがっていますか?</span><span class="sxs-lookup"><span data-stu-id="a2f5c-205">Want to know how long painting takes or how often painting occurs?</span></span>  <span data-ttu-id="a2f5c-206">[パフォーマンス] [パネルの [高度なペイントインス][DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation] トルメンテーションを有効にする] **設定を確認** し、録音を行います。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-206">Check the [Enable advanced paint instrumentation][DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation] setting in the **Performance** panel and then take a recording.</span></span>  <span data-ttu-id="a2f5c-207">ほとんどのレンダリング時間がペイントに費やされている場合は、ペイントに問題があります。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-207">If most of your rendering time is spent painting, you have paint problems.</span></span>  

<!--
:::image type="complex" source="../media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png" alt-text="Long paint times in timeline recording" lightbox="../media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png":::
   Long paint times in timeline recording  
:::image-end:::  
-->  

<!--
Check out the **Rendering** panel for further configurations that are able to help you diagnose paint problems.  -->  

<!--todo: link Rendering panel in ../evaluate-performance/timeline-tool  sub-section when live  -->  

### <a name="paint-and-composite-problems"></a><span data-ttu-id="a2f5c-208">ペイントとコンポジット: 問題</span><span class="sxs-lookup"><span data-stu-id="a2f5c-208">Paint and composite: Problems</span></span>  

<span data-ttu-id="a2f5c-209">次の表では、一般的なペイントとコンポジットの問題と潜在的な解決策について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-209">The following table describes some common paint and composite problems and potential solutions.</span></span>  

| <span data-ttu-id="a2f5c-210">問題</span><span class="sxs-lookup"><span data-stu-id="a2f5c-210">Problem</span></span> | <span data-ttu-id="a2f5c-211">例</span><span class="sxs-lookup"><span data-stu-id="a2f5c-211">Example</span></span> | <span data-ttu-id="a2f5c-212">ソリューション</span><span class="sxs-lookup"><span data-stu-id="a2f5c-212">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="a2f5c-213">応答またはアニメーションに影響を与えるストームをペイントします。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-213">Paint storms affecting response or animation.</span></span>  | <span data-ttu-id="a2f5c-214">応答やアニメーションに影響を与える大きなペイント領域または高価なペイント。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-214">Big paint areas or expensive paints affecting response or animation.</span></span>  | <span data-ttu-id="a2f5c-215">ペイントを避け、独自のレイヤーに移動する要素を昇格し、変換と不透明度を使用します。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-215">Avoid paint, promote elements that are moving to their own layer, use transforms and opacity.</span></span>  <!--Navigate to [Simplify paint complexity and reduce paint areas][WebFundamentalsPerformanceRenderingSimplifyPaintComplexity].  -->  |  
| <span data-ttu-id="a2f5c-216">アニメーションに影響を与えるレイヤーの爆発。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-216">Layer explosions affecting animations.</span></span>  | <span data-ttu-id="a2f5c-217">アニメーションのパフォーマンスに大きな影響を与える要素が多すぎます `translateZ(0)` 。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-217">Overpromotion of too many elements with `translateZ(0)` greatly affects animation performance.</span></span>  | <span data-ttu-id="a2f5c-218">レイヤーへの昇格は、重要な改善点を提供する場合にのみ行います。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-218">Promote to layers sparingly, and only when you know it offers tangible improvements.</span></span>  <!--Navigate to [Stick to composite-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  |  

<!--todo: add Simplify paint complexity and reduce paint areas section when available  -->  
<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="a2f5c-219">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="a2f5c-219">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsRenderingToolsJavascriptRuntime]: ./js-runtime.md "JavaScript ランタイム の高速化|Microsoft Docs"  
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

[MDNUsingWebWorkers]: https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers "Web ワーカー の使用|MDN"  

[WebPerformanceCalendarRuntimeChecklist]: https://calendar.perfplanet.com/2013/the-runtime-performance-checklist/ "ランタイム パフォーマンス チェックリスト - Web パフォーマンス カレンダー"  

[GitHubWilsonpageFastdom]: https://github.com/wilsonpage/fastdom "wilsonpage/fastdom |GitHub"  

> [!NOTE]
> <span data-ttu-id="a2f5c-226">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-226">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="a2f5c-227">元のページはここで[](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/index)見つかり[、Kayce バス][KayceBasques]ク人 \(Technical Writer, Chrome DevTools \& ライトハウス\) と[Meggin Kearney][MegginKearney] \(Tech Writer\) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-227">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="a2f5c-229">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="a2f5c-229">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
