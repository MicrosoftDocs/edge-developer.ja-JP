---
title: 実行時のパフォーマンスを分析する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 7705428dba2ca368eb8f61b13bb96901756b081f
ms.sourcegitcommit: 0342d99bf8d3212068890bab0e1e960afa507c02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611865"
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





# <span data-ttu-id="b97dd-103">実行時のパフォーマンスを分析する</span><span class="sxs-lookup"><span data-stu-id="b97dd-103">Analyze Runtime Performance</span></span>   




<span data-ttu-id="b97dd-104">ユーザーは対話的なページとスムーズなページを期待します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-104">Users expects interactive and smooth pages.</span></span>  <span data-ttu-id="b97dd-105">ピクセルパイプラインの各ステージは、jank を導入する機会を表します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-105">Each stage in the pixel pipeline represents an opportunity to introduce jank.</span></span>  <span data-ttu-id="b97dd-106">実行時のパフォーマンスを低下させる一般的な問題を特定して修正するためのツールと戦略について説明します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-106">Learn about tools and strategies to identify and fix common problems that slow down runtime performance.</span></span>  

### <span data-ttu-id="b97dd-107">まとめ</span><span class="sxs-lookup"><span data-stu-id="b97dd-107">Summary</span></span>  

*   <span data-ttu-id="b97dd-108">ブラウザーでレイアウトを再計算するように強制する JavaScript を記述しないでください。</span><span class="sxs-lookup"><span data-stu-id="b97dd-108">Do not write JavaScript that forces the browser to recalculate layout.</span></span>  <span data-ttu-id="b97dd-109">読み取りと書き込みの関数を区切り、まず読み取りを実行します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-109">Separate read and write functions, and perform reads first.</span></span>  
*   <span data-ttu-id="b97dd-110">CSS の複雑さを超えないようにします。</span><span class="sxs-lookup"><span data-stu-id="b97dd-110">Do not over-complicate your CSS.</span></span>  <span data-ttu-id="b97dd-111">Css セレクターをシンプルにしてください。</span><span class="sxs-lookup"><span data-stu-id="b97dd-111">Use less CSS and keep your CSS selectors simple.</span></span>  
*   <span data-ttu-id="b97dd-112">可能な限りレイアウトを避けます。</span><span class="sxs-lookup"><span data-stu-id="b97dd-112">Avoid layout as much as possible.</span></span>  <span data-ttu-id="b97dd-113">レイアウトをトリガーしない CSS を選択します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-113">Choose CSS that does not trigger layout at all.</span></span>  
*   <span data-ttu-id="b97dd-114">塗装は、他のレンダリングアクティビティよりも時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="b97dd-114">Painting may take up more time than any other rendering activity.</span></span>  <span data-ttu-id="b97dd-115">ペイントのボトルネックに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b97dd-115">Watch out for paint bottlenecks.</span></span>  

## <span data-ttu-id="b97dd-116">JavaScript</span><span class="sxs-lookup"><span data-stu-id="b97dd-116">JavaScript</span></span>  

<span data-ttu-id="b97dd-117">JavaScript の計算、特に広範な視覚的な変更をトリガーする場合は、アプリケーションのパフォーマンスが低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="b97dd-117">JavaScript calculations, especially ones that trigger extensive visual changes, may stall application performance.</span></span>  <span data-ttu-id="b97dd-118">不適切なタイミングを設定したり、長時間の JavaScript を使用してユーザーの操作に干渉しないようにします。</span><span class="sxs-lookup"><span data-stu-id="b97dd-118">Do not let badly-timed or long-running JavaScript interfere with user interactions.</span></span>  

### <span data-ttu-id="b97dd-119">JavaScript: ツール</span><span class="sxs-lookup"><span data-stu-id="b97dd-119">JavaScript: Tools</span></span>  

<span data-ttu-id="b97dd-120">[**パフォーマンス**] パネルでレコーディングを実行して、suspiciously の長いイベントを探し `Evaluate Script` ます。</span><span class="sxs-lookup"><span data-stu-id="b97dd-120">Take a recording in the **Performance** panel and look for suspiciously long `Evaluate Script` events.</span></span>  <!--If you find any, you are able to enable the **JS Profiler** and re-do your recording to get more detailed information about exactly which JavaScript functions were used and how long each took.  -->  

<!--todo: add Recording section when available  -->  
<!--todo: add Profile JavaScript (JS Profiler) section when available  -->  

<span data-ttu-id="b97dd-121">JavaScript で非常に多くの jank が見られた場合は、分析を次のレベルにして JavaScript CPU プロファイルを収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b97dd-121">f you noticing quite a bit of jank in your JavaScript, you may need to take your analysis to the next level and collect a JavaScript CPU profile.</span></span>  <span data-ttu-id="b97dd-122">CPU プロファイルは、ページの関数内でランタイムが消費される場所を示します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-122">CPU profiles show where runtime is spent within the functions of your page.</span></span>  <span data-ttu-id="b97dd-123">CPU プロファイルを作成する方法については、「 [JavaScript ランタイムの速度を向上][DevtoolsRenderingToolsJavascriptRuntime]させる」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b97dd-123">Learn how to create CPU profiles in [Speed Up JavaScript Runtime][DevtoolsRenderingToolsJavascriptRuntime].</span></span>

### <span data-ttu-id="b97dd-124">JavaScript: 問題</span><span class="sxs-lookup"><span data-stu-id="b97dd-124">JavaScript: Problems</span></span>  

<span data-ttu-id="b97dd-125">次の表では、JavaScript の一般的な問題と解決策について説明します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-125">The following table describes some common JavaScript problems and potential solutions:</span></span>  

| <span data-ttu-id="b97dd-126">問題</span><span class="sxs-lookup"><span data-stu-id="b97dd-126">Problem</span></span> | <span data-ttu-id="b97dd-127">例</span><span class="sxs-lookup"><span data-stu-id="b97dd-127">Example</span></span> | <span data-ttu-id="b97dd-128">解決策</span><span class="sxs-lookup"><span data-stu-id="b97dd-128">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="b97dd-129">応答またはアニメーションに影響する負荷の高い入力ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="b97dd-129">Expensive input handlers affecting response or animation.</span></span>  | <span data-ttu-id="b97dd-130">タッチ、視差効果のスクロール。</span><span class="sxs-lookup"><span data-stu-id="b97dd-130">Touch, parallax scrolling.</span></span>  | <span data-ttu-id="b97dd-131">ブラウザーでタッチを処理してスクロールするか、またはリスナーをできるだけ遅くバインドします。</span><span class="sxs-lookup"><span data-stu-id="b97dd-131">Let the browser handle touch and scrolls, or bind the listener as late as possible.</span></span>  <span data-ttu-id="b97dd-132">[Paul ルイスの実行時パフォーマンスチェックリストで負荷の高い入力ハンドラーを][WebPerformanceCalendarRuntimeChecklist]参照してください。</span><span class="sxs-lookup"><span data-stu-id="b97dd-132">See [Expensive Input Handlers in Paul Lewis' runtime performance checklist][WebPerformanceCalendarRuntimeChecklist].</span></span>  |  
| <span data-ttu-id="b97dd-133">応答、アニメーション、読み込みに影響を与える、時間がかかる JavaScript。</span><span class="sxs-lookup"><span data-stu-id="b97dd-133">Badly-timed JavaScript affecting response, animation, load.</span></span>  | <span data-ttu-id="b97dd-134">ユーザーは、ページの読み込み、setTimeout、setInterval の後で右にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="b97dd-134">User scrolls right after page load, setTimeout / setInterval.</span></span>  | <span data-ttu-id="b97dd-135">JavaScript の実行時の最適化: 使用 `requestAnimationFrame` 、フレーム上の DOM の操作、 [Web ワーカー][MDNUsingWebWorkers]の使用などを行います。</span><span class="sxs-lookup"><span data-stu-id="b97dd-135">Optimize JavaScript runtime: use `requestAnimationFrame`, spread DOM manipulation over frames, use [Web Workers][MDNUsingWebWorkers].</span></span>  |  
| <span data-ttu-id="b97dd-136">応答に影響を与える長時間の JavaScript。</span><span class="sxs-lookup"><span data-stu-id="b97dd-136">Long-running JavaScript affecting response.</span></span>  | <span data-ttu-id="b97dd-137">[Domcontentloaded イベント][MDNUsingWebWorkers]は、JS の作業をさばきするため、ストールします。</span><span class="sxs-lookup"><span data-stu-id="b97dd-137">The [DOMContentLoaded event][MDNUsingWebWorkers] stalls as it is swamped with JS work.</span></span>  | <span data-ttu-id="b97dd-138">純粋な計算作業を[Web ワーカー][MDNUsingWebWorkers]に移動します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-138">Move pure computational work to [Web Workers][MDNUsingWebWorkers].</span></span>  <span data-ttu-id="b97dd-139">DOM へのアクセスが必要な場合は、を使用 `requestAnimationFrame` します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-139">If you need DOM access, use `requestAnimationFrame`.</span></span>  <!--See also [Optimize JavaScript Execution][WebFundamentalsPerformanceRenderingOptimizeJavascriptRuntime].  -->  |  
| <span data-ttu-id="b97dd-140">応答またはアニメーションに影響を与えるガーベジスクリプト。</span><span class="sxs-lookup"><span data-stu-id="b97dd-140">Garbage-y scripts affecting response or animation.</span></span>  | <span data-ttu-id="b97dd-141">ガベージコレクションがどこでも発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b97dd-141">Garbage collection may happen anywhere.</span></span>  | <span data-ttu-id="b97dd-142">書き込みが少ないガベージ y スクリプト。</span><span class="sxs-lookup"><span data-stu-id="b97dd-142">Write less garbage-y scripts.</span></span>  <span data-ttu-id="b97dd-143">「 [Paul ルイスのランタイムパフォーマンスチェックリスト」の「アニメーションのガベージコレクション][WebPerformanceCalendarRuntimeChecklist]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b97dd-143">See [Garbage Collection in Animation in Paul Lewis' runtime performance checklist][WebPerformanceCalendarRuntimeChecklist].</span></span>  |  

<!--todo: add Optimize JavaScript runtime section when available  -->  

## <span data-ttu-id="b97dd-144">形式</span><span class="sxs-lookup"><span data-stu-id="b97dd-144">Style</span></span>  

<span data-ttu-id="b97dd-145">スタイルの変更にはコストがかかります。特に、それらの変更が DOM の複数の要素に影響する場合。</span><span class="sxs-lookup"><span data-stu-id="b97dd-145">Style changes are costly, especially if those changes affect more than one element in the DOM.</span></span>  <span data-ttu-id="b97dd-146">要素にスタイルを適用すると、ブラウザーがすべての関連要素への影響を把握し、レイアウトを再計算し、再描画します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-146">Any time you apply styles to an element, the browser figures out the impact on all related elements, recalculates the layout, and repaints.</span></span>  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  
-->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

### <span data-ttu-id="b97dd-147">スタイル: ツール</span><span class="sxs-lookup"><span data-stu-id="b97dd-147">Style: Tools</span></span>  

<span data-ttu-id="b97dd-148">[**パフォーマンス**] パネルでレコーディングを実行します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-148">Take a recording in the **Performance** panel.</span></span>  <span data-ttu-id="b97dd-149">大きい `Recalculate Style` イベント (紫 \) の記録を確認します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-149">Check the recording for large `Recalculate Style` events \(displayed in purple\).</span></span>  

<!--todo: add Recording section when available  -->  

<span data-ttu-id="b97dd-150">イベントをクリック `Recalculate Style` すると、**詳細**ウィンドウにイベントの詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b97dd-150">Click on a `Recalculate Style` event to view more information about it in the **Details** pane.</span></span>  <span data-ttu-id="b97dd-151">スタイルの変更に時間がかかる場合は、パフォーマンスに影響します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-151">If the style changes are taking a long time, that is a performance hit.</span></span>  <span data-ttu-id="b97dd-152">スタイルの計算が多くの要素に影響を与えている場合は、さらに改善の余地がある別の領域です。</span><span class="sxs-lookup"><span data-stu-id="b97dd-152">If the style calculations are affecting a large number of elements, that is another area with room for improvement.</span></span>  

> ##### <span data-ttu-id="b97dd-153">図 1</span><span class="sxs-lookup"><span data-stu-id="b97dd-153">Figure 1</span></span>  
> <span data-ttu-id="b97dd-154">長い再計算のスタイル</span><span class="sxs-lookup"><span data-stu-id="b97dd-154">Long recalculate style</span></span>  
> ![長い再計算のスタイル][ImageLongRecalculateStyle]

<span data-ttu-id="b97dd-156">イベントの影響を軽減するには、 `Recalculate Style` 次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b97dd-156">To reduce the impact of `Recalculate Style` events:</span></span>  

*   <span data-ttu-id="b97dd-157">[Css トリガー][CssTriggers]を使って、レイアウト、ペイント、コンポジットをトリガーする css プロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-157">Use the [CSS Triggers][CssTriggers] to learn which CSS properties trigger layout, paint, and composite.</span></span>  <span data-ttu-id="b97dd-158">これらのプロパティは、レンダリングのパフォーマンスに影響を及ぼすことはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="b97dd-158">These properties have the worst impact on rendering performance.</span></span>  
*   <span data-ttu-id="b97dd-159">影響の少ないプロパティに切り替える。</span><span class="sxs-lookup"><span data-stu-id="b97dd-159">Switch to properties that have less impact.</span></span>  <!--See [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties] for more guidance.  -->  

<!--todo: add Stick to compositor-only properties and manage layer count section when available -->  

### <span data-ttu-id="b97dd-160">スタイル: 問題</span><span class="sxs-lookup"><span data-stu-id="b97dd-160">Style: Problems</span></span>  

<span data-ttu-id="b97dd-161">次の表では、一般的なスタイルの問題と考えられる解決策について説明します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-161">The following table describes some common style problems and potential solutions:</span></span>  

| <span data-ttu-id="b97dd-162">問題</span><span class="sxs-lookup"><span data-stu-id="b97dd-162">Problem</span></span> | <span data-ttu-id="b97dd-163">例</span><span class="sxs-lookup"><span data-stu-id="b97dd-163">Example</span></span> | <span data-ttu-id="b97dd-164">解決策</span><span class="sxs-lookup"><span data-stu-id="b97dd-164">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="b97dd-165">応答またはアニメーションに影響する負荷の高いスタイルの計算。</span><span class="sxs-lookup"><span data-stu-id="b97dd-165">Expensive style calculations affecting response or animation.</span></span>  | <span data-ttu-id="b97dd-166">Width、height、position などの要素のジオメトリを変更する CSS プロパティ。ブラウザーは、他のすべての要素をチェックし、レイアウトを再計算します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-166">Any CSS property that changes the geometry of an element, like the width, height, or position; the browser checks all other elements and recalculates the layout.</span></span>  | <span data-ttu-id="b97dd-167">レイアウトをトリガーする CSS を使わない</span><span class="sxs-lookup"><span data-stu-id="b97dd-167">Avoid CSS that triggers layouts</span></span> |  
| <span data-ttu-id="b97dd-168">応答またはアニメーションに影響を与える複雑なセレクター。</span><span class="sxs-lookup"><span data-stu-id="b97dd-168">Complex selectors affecting response or animation.</span></span>  | <span data-ttu-id="b97dd-169">入れ子になったセレクターを有効にすると、親と子を含む、他のすべての要素に関するすべての情報がブラウザーで認識されます。</span><span class="sxs-lookup"><span data-stu-id="b97dd-169">Nested selectors force the browser to know everything about all the other elements, including parents and children.</span></span>  | <span data-ttu-id="b97dd-170">CSS の要素をクラスのみで参照します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-170">Reference an element in your CSS with just a class.</span></span>  |  

<!--todo: add Avoid CSS that triggers layouts section when available -->  
<!--todo: add Reduce the Scope and Complexity of Styles Calculations (Reference an element in your CSS with just a class) section when available -->  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  -->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

## <span data-ttu-id="b97dd-171">レイアウト</span><span class="sxs-lookup"><span data-stu-id="b97dd-171">Layout</span></span>  

<span data-ttu-id="b97dd-172">レイアウト (または Firefox によるリフロー) は、ブラウザーがページ上のすべての要素の位置とサイズを計算するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="b97dd-172">Layout (or reflow in Firefox) is the process by which the browser calculates the positions and sizes of all the elements on a page.</span></span>  <span data-ttu-id="b97dd-173">Web のレイアウトモデルでは、1つの要素が他の要素に影響を与える可能性があります。たとえば、要素の幅は通常、子要素の幅、つまり、 `<body>` ツリーの上下の方向に影響します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-173">The layout model of the web means that one element may affect others; for example, the width of the `<body>` element typically affects the widths of any child elements, and so on, all the way up and down the tree.</span></span>  <span data-ttu-id="b97dd-174">このプロセスは、ブラウザーに非常に関連している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b97dd-174">The process may be quite involved for the browser.</span></span>  

<span data-ttu-id="b97dd-175">一般的な目安として、フレームが完了する前に DOM から幾何学的な値を取得するように要求すると、"強制同期レイアウト" が適用されます。これは、頻繁に繰り返すか、大きな DOM ツリーに対して実行された場合は、パフォーマンスが大幅に低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b97dd-175">As a general rule of thumb, if you ask for a geometric value back from the DOM before a frame is complete, you are going to find yourself with "forced synchronous layouts", which may be a big performance bottleneck if repeated frequently or performed for a large DOM tree.</span></span>  

<!--Related Guides:  

*   [Avoid Layout Thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts]  
*   [Diagnose Forced Synchronous Layouts][DevtoolsRenderingToolsForcedSynchronousLayouts]  -->  

<!--todo: add Avoid CSS that triggers layouts (Avoid Layout Thrashing) section when available -->  
<!--todo: add Diagnose Forced Synchronous Layouts section when available  -->  

### <span data-ttu-id="b97dd-176">レイアウト: ツール</span><span class="sxs-lookup"><span data-stu-id="b97dd-176">Layout: Tools</span></span>  

<span data-ttu-id="b97dd-177">[**パフォーマンス**] ウィンドウは、ページで強制的な同期レイアウトが行われるタイミングを示します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-177">The **Performance** pane identifies when a page causes forced synchronous layouts.</span></span>  <span data-ttu-id="b97dd-178">これらの `Layout` イベントは赤いバーでマークされます。</span><span class="sxs-lookup"><span data-stu-id="b97dd-178">These `Layout` events are marked with red bars.</span></span>  

> ##### <span data-ttu-id="b97dd-179">図 2</span><span class="sxs-lookup"><span data-stu-id="b97dd-179">Figure 2</span></span>  
> <span data-ttu-id="b97dd-180">強制同期レイアウト</span><span class="sxs-lookup"><span data-stu-id="b97dd-180">Forced synchronous layout</span></span>  
> ![強制同期レイアウト][ImageForcedSynchronousLayout]  

<span data-ttu-id="b97dd-182">"レイアウトのスラッシング" は、強制的な同期レイアウト条件を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-182">"Layout thrashing" is a repetition of forced synchronous layout conditions.</span></span>  <span data-ttu-id="b97dd-183">これは、JavaScript が DOM を繰り返し読み書きするときに発生します。これにより、ブラウザーでは、レイアウトの再計算が強制的に行われます。</span><span class="sxs-lookup"><span data-stu-id="b97dd-183">This occurs when JavaScript writes and reads from the DOM repeatedly, which forces the browser to recalculate the layout over and over.</span></span>  <span data-ttu-id="b97dd-184">レイアウトのスラッシングを特定するには、複数の強制同期レイアウトの警告パターンを探します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-184">To identify layout thrashing, look for a pattern of multiple forced synchronous layout warnings.</span></span>  <span data-ttu-id="b97dd-185">[図 2](#figure-2)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b97dd-185">See [Figure 2](#figure-2).</span></span>  

### <span data-ttu-id="b97dd-186">レイアウト: 問題</span><span class="sxs-lookup"><span data-stu-id="b97dd-186">Layout: Problems</span></span>  

<span data-ttu-id="b97dd-187">次の表では、一般的なレイアウトの問題と考えられる解決策について説明します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-187">The following table describes some common layout problems and potential solutions:</span></span>  

| <span data-ttu-id="b97dd-188">問題</span><span class="sxs-lookup"><span data-stu-id="b97dd-188">Problem</span></span> | <span data-ttu-id="b97dd-189">例</span><span class="sxs-lookup"><span data-stu-id="b97dd-189">Example</span></span> | <span data-ttu-id="b97dd-190">解決策</span><span class="sxs-lookup"><span data-stu-id="b97dd-190">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="b97dd-191">応答またはアニメーションに影響する強制同期レイアウト</span><span class="sxs-lookup"><span data-stu-id="b97dd-191">Forced synchronous layout affecting response or animation.</span></span>  | <span data-ttu-id="b97dd-192">ピクセルパイプラインで事前にレイアウトを実行するようにブラウザーを強制することで、レンダリングプロセスの手順が繰り返しられます。</span><span class="sxs-lookup"><span data-stu-id="b97dd-192">Forcing the browser to perform layout earlier in the pixel pipeline, resulting in repeating steps in the rendering process.</span></span>  | <span data-ttu-id="b97dd-193">スタイルを最初に読み込み、次に書き込みを行います。</span><span class="sxs-lookup"><span data-stu-id="b97dd-193">Batch your style reads first, then do any writes.</span></span>  <!--See also [Avoid large, complex layouts and layout thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts].  -->  |  
| <span data-ttu-id="b97dd-194">応答またはアニメーションに影響するレイアウトのスラッシング。</span><span class="sxs-lookup"><span data-stu-id="b97dd-194">Layout thrashing affecting response or animation.</span></span>  | <span data-ttu-id="b97dd-195">ブラウザーを読み取り/書き込み可能な読み取り/書き込みのサイクルにして、ブラウザーのレイアウトを再計算するように強制するループ。</span><span class="sxs-lookup"><span data-stu-id="b97dd-195">A loop that puts the browser into a read-write-read-write cycle, forcing the browser to recalculate layout over and over again.</span></span>  | <span data-ttu-id="b97dd-196">[Fastdom ライブラリ][GitHubWilsonpageFastdom]を使用して、読み取り/書き込み操作を自動的にバッチ処理します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-196">Automatically batch read-write operations using [FastDom library][GitHubWilsonpageFastdom].</span></span>  |  

<!--todo: add Avoid CSS that triggers layouts (Avoid large, complex layouts and layout thrashing) section when available -->  

## <span data-ttu-id="b97dd-197">ペイントとコンポジット</span><span class="sxs-lookup"><span data-stu-id="b97dd-197">Paint and composite</span></span>  

<span data-ttu-id="b97dd-198">ペイントとは、ピクセル単位で塗りつぶしを行うプロセスです。</span><span class="sxs-lookup"><span data-stu-id="b97dd-198">Paint is the process of filling in pixels.</span></span>  <span data-ttu-id="b97dd-199">これは、多くの場合、レンダリング処理の中で最もコストがかかる部分です。</span><span class="sxs-lookup"><span data-stu-id="b97dd-199">It is often the most costly part of the rendering process.</span></span>  <span data-ttu-id="b97dd-200">ページが何らかの方法で janky されている場合は、ペイントの問題が発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b97dd-200">If you noticed that your page is janky in any way, it is likely that you have paint problems.</span></span>  

<span data-ttu-id="b97dd-201">[合成] では、ページの塗りつぶされた部分を、画面に表示するために一緒に配置します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-201">Compositing is where the painted parts of the page are put together for displaying on screen.</span></span>  <span data-ttu-id="b97dd-202">ほとんどの場合、コンポジター専用のプロパティにしてペイントをまったく行わないようにすると、パフォーマンスが大幅に向上しますが、過剰なレイヤーカウントについては注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="b97dd-202">For the most part, if you stick to compositor-only properties and avoid paint altogether, you should see a major improvement in performance, but you need to watch out for excessive layer counts.</span></span>  <!--See also [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  

<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

### <span data-ttu-id="b97dd-203">ペイントとコンポジット: ツール</span><span class="sxs-lookup"><span data-stu-id="b97dd-203">Paint and composite: Tools</span></span>  

<span data-ttu-id="b97dd-204">ペイントにかかる時間や、ペイントの頻度を知りたい場合</span><span class="sxs-lookup"><span data-stu-id="b97dd-204">Want to know how long painting takes or how often painting occurs?</span></span>  <span data-ttu-id="b97dd-205">[**パフォーマンス**] パネルの [[高度な描画インストルメンテーションを有効にする][DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation]] 設定を確認して、記録を撮ります。</span><span class="sxs-lookup"><span data-stu-id="b97dd-205">Check the [Enable advanced paint instrumentation][DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation] setting in the **Performance** panel and then take a recording.</span></span>  <span data-ttu-id="b97dd-206">レンダリング時間の大半がペイントに費やされている場合は、ペイントの問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-206">If most of your rendering time is spent painting, you have paint problems.</span></span>  

<!--
> ##### Old Figure 3  
> Long paint times in timeline recording  
> ![Long paint times in timeline recording][ImageLongPaintTimes]  
-->  

<!--
Check out the **Rendering** panel for further configurations that are able to help you diagnose paint problems.  -->  

<!--todo: link Rendering panel in ../evaluate-performance/timeline-tool  sub-section when live  -->  

### <span data-ttu-id="b97dd-207">ペイントとコンポジット: 問題</span><span class="sxs-lookup"><span data-stu-id="b97dd-207">Paint and composite: Problems</span></span>  

<span data-ttu-id="b97dd-208">次の表では、一般的な塗装およびコンポジットの問題と考えられる解決策について説明します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-208">The following table describes some common paint and composite problems and potential solutions:</span></span>  

| <span data-ttu-id="b97dd-209">問題</span><span class="sxs-lookup"><span data-stu-id="b97dd-209">Problem</span></span> | <span data-ttu-id="b97dd-210">例</span><span class="sxs-lookup"><span data-stu-id="b97dd-210">Example</span></span> | <span data-ttu-id="b97dd-211">解決策</span><span class="sxs-lookup"><span data-stu-id="b97dd-211">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="b97dd-212">応答やアニメーションに影響を与える塗装。</span><span class="sxs-lookup"><span data-stu-id="b97dd-212">Paint storms affecting response or animation.</span></span>  | <span data-ttu-id="b97dd-213">大きな塗装領域または負荷の高い応答やアニメーション。</span><span class="sxs-lookup"><span data-stu-id="b97dd-213">Big paint areas or expensive paints affecting response or animation.</span></span>  | <span data-ttu-id="b97dd-214">ペイントは避け、独自のレイヤーに移動する要素のレベル上げ、変形と不透明度の使用を行います。</span><span class="sxs-lookup"><span data-stu-id="b97dd-214">Avoid paint, promote elements that are moving to their own layer, use transforms and opacity.</span></span>  <!--See [Simplify paint complexity and reduce paint areas][WebFundamentalsPerformanceRenderingSimplifyPaintComplexity].  -->  |  
| <span data-ttu-id="b97dd-215">アニメーションに影響するレイヤーの爆発。</span><span class="sxs-lookup"><span data-stu-id="b97dd-215">Layer explosions affecting animations.</span></span>  | <span data-ttu-id="b97dd-216">多くの要素をオーバープロモーションすると、 `translateZ(0)` アニメーションのパフォーマンスに大きく影響します。</span><span class="sxs-lookup"><span data-stu-id="b97dd-216">Overpromotion of too many elements with `translateZ(0)` greatly affects animation performance.</span></span>  | <span data-ttu-id="b97dd-217">レイヤーへの昇格は慎重に行うことができます。把握している場合にのみ、明確な改善が提供されます。</span><span class="sxs-lookup"><span data-stu-id="b97dd-217">Promote to layers sparingly, and only when you know it offers tangible improvements.</span></span>  <!--See [Stick to composite-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  |  

<!--todo: add Simplify paint complexity and reduce paint areas section when available  -->  
<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

<!--## Feedback   -->  



<!-- image links -->  

[ImageLongRecalculateStyle]: /microsoft-edge/devtools-guide-chromium/media/rendering-tools-performance-recalculate-style-summary.msft.png "図 1: 長い再計算のスタイル"  
[ImageForcedSynchronousLayout]: /microsoft-edge/devtools-guide-chromium/media/rendering-tools-jank-performance-recalculate-style-summary.msft.png "図 2: 強制同期レイアウト"  
<!--[ImageLongPaintTimes]: /microsoft-edge/devtools-guide-chromium/media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png "Old Figure 3: Long paint times in timeline recording"  -->  

<!-- links -->  

[DevtoolsRenderingToolsJavascriptRuntime]: /microsoft-edge/devtools-guide-chromium/rendering-tools/js-runtime "JavaScript の実行時間を短縮する"  

[DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#enable-advanced-paint-instrumentation "高度な描画インストルメンテーションを有効にする-パフォーマンス分析リファレンス"

<!--[DevtoolsRenderingToolsForcedSynchronousLayouts]: /microsoft-edge/devtools-guide-chromium/rendering-tools/forced-synchronous-layouts "Diagnose Forced Synchronous Layouts"  -->  

<!-- The Timeline Tool page is deprecated  -->  
<!--[DevtoolsEvaluatePerformanceTimelineToolProfileJavascript]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/timeline-tool#profile-javascript "Profile JavaScript - How to Use the Timeline Tool"  -->  
<!--[DevtoolsEvaluatePerformanceTimelineToolProfilePainting]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/timeline-tool#profile-painting "Profile painting - How to Use the Timeline Tool"  -->  
<!--[DevtoolsEvaluatePerformanceTimelineToolRecording]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/timeline-tool#make-a-recording "Make a recording - How to Use the Timeline Tool"  -->  
<!--[DevtoolsEvaluatePerformanceTimelineToolRenderingSettings]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/timeline-tool#rendering-settings "Rendering settings - How to Use the Timeline Tool"  -->  

<!--[WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts]: /web/fundamentals/performance/rendering/avoid-large-complex-layouts-and-layout-thrashing "Avoid Large, Complex Layouts, and Layout Thrashing"  -->  
<!--[WebFundamentalsPerformanceRenderingOptimizeJavascriptRuntime]: /web/fundamentals/performance/rendering/optimize-javascript-execution "Optimize JavaScript Runtime"  -->  
<!--[WebFundamentalsPerformanceRenderingReduceScope]: /web/fundamentals/performance/rendering/reduce-the-scope-and-complexity-of-style-calculations "Reduce the Scope and Complexity of Style Calculations"  -->  
<!--[WebFundamentalsPerformanceRenderingSimplifyPaintComplexity]: /web/fundamentals/performance/rendering/simplify-paint-complexity-and-reduce-paint-areas "Simplify Paint Complexity and Reduce Paint Areas"  -->  
<!--[WebFundamentalsPerformanceRenderingCompositorOnlyProperties]: /web/fundamentals/performance/rendering/stick-to-compositor-only-properties-and-manage-layer-count "Stick to Compositor-Only Properties and Manage Layer Count"  -->  

[CssTriggers]: https://csstriggers.com "CSS トリガー"  

[MDNUsingWebWorkers]: https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers "Web ワーカーの使い方 |MDN"  

[WebPerformanceCalendarRuntimeChecklist]: https://calendar.perfplanet.com/2013/the-runtime-performance-checklist/ "ランタイムパフォーマンスチェックリスト-Web パフォーマンスカレンダー"  

[GitHubWilsonpageFastdom]: https://github.com/wilsonpage/fastdom "このページ/fastdom |GitHub"  

> [!NOTE]
> <span data-ttu-id="b97dd-226">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="b97dd-226">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b97dd-227">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/index)にあり、 [Kayce basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) および[Meggin Kearney][MegginKearney] \ (Tech writer \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="b97dd-227">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="b97dd-229">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="b97dd-229">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
