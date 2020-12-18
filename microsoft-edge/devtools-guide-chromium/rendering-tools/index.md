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

# 実行時のパフォーマンスを分析する 

ユーザーは、対話型でスムーズなページを期待します。  ピクセル パイプラインの各ステージは、jank を導入する機会を表します。  ランタイムのパフォーマンスを低下させる一般的な問題を特定して修正するためのツールと戦略について説明します。  

### まとめ  

*   ブラウザーで強制的にレイアウトを再計算する JavaScript を記述しない。  読み取り関数と書き込み関数を分離し、最初に読み取りを実行します。  
*   CSS を過剰に複雑にし過ぎない。  CSS を少なくし、CSS セレクターをシンプルにしてください。  
*   レイアウトは可能な限り避ける。  レイアウトをトリガーしない CSS を選択します。  
*   描画には、他のレンダリング アクティビティよりも時間がかかる場合があります。  ペイントのボトルネックに注意してください。  
    
## JavaScript  

JavaScript の計算 (特に、広範囲な表示変更をトリガーする計算) では、アプリケーションのパフォーマンスが低下する可能性があります。  時間が悪い、または長時間実行される JavaScript がユーザー操作に干渉しないようにします。  

### JavaScript: ツール  

パフォーマンス パネルでレコーディングを **行** い、疑わしい長いイベントを探 `Evaluate Script` します。  <!--If you find any, you are able to enable the **JS Profiler** and re-do your recording to get more detailed information about exactly which JavaScript functions were used and how long each took.  -->  

<!--todo: add Recording section when available  -->  
<!--todo: add Profile JavaScript (JS Profiler) section when available  -->  

JavaScript でかなりの数の jank に気が付く場合は、分析を次のレベルに進めて JavaScript CPU プロファイルを収集する必要があります。  CPU プロファイルは、ページの機能内でランタイムが使用される場所を示します。  JavaScript ランタイムの高速化で CPU プロファイル [を作成する方法について説明します][DevtoolsRenderingToolsJavascriptRuntime]。

### JavaScript: 問題  

次の表では、いくつかの一般的な JavaScript の問題と潜在的な解決策について説明します。  

| 問題 | 例 | 解決策 |  
|:--- |:--- |:--- |  
| 応答またはアニメーションに影響を与える高コストの入力ハンドラー。  | タッチ、視差スクロール。  | ブラウザーでタッチとスクロールを処理するか、リスナーを可能な限り遅くバインドします。  [Paul Paul Paul のランタイム パフォーマンス チェックリストの「高価な入力ハンドラー」を参照してください][WebPerformanceCalendarRuntimeChecklist]。  |  
| 応答、アニメーション、読み込みに影響を与える時間が悪い JavaScript。  | ユーザーはページの読み込み直後にスクロールします。setTimeout / setInterval。  | JavaScript ランタイムの最適化: 使用 `requestAnimationFrame` 、DOM 操作をフレームに広げる [、Web ワーカーを使用する][MDNUsingWebWorkers]。  |  
| 応答に影響を与える長時間実行される JavaScript。  | [DOMContentLoaded][MDNUsingWebWorkers]イベントは、JS の処理が行き詰まっている間にストールします。  | 純粋な計算作業を [Web ワーカーに移動します][MDNUsingWebWorkers]。  DOM アクセスが必要な場合は、次の値を使用します `requestAnimationFrame` 。  <!--See also [Optimize JavaScript Execution][WebFundamentalsPerformanceRenderingOptimizeJavascriptRuntime].  -->  |  
| 応答またはアニメーションに影響を与えるガベージ y スクリプト。  | ガベージ コレクションは、任意の場所で発生する可能性があります。  | ガベージ y スクリプトを少なくする。  [Paul Paul のランタイム パフォーマンス チェックリストのアニメーションのガベージ コレクションを参照してください][WebPerformanceCalendarRuntimeChecklist]。  |  

<!--todo: add Optimize JavaScript runtime section when available  -->  

## 形式  

スタイルの変更が DOM 内の複数の要素に影響を与える場合は特に、スタイルの変更にはコストがかかります。  要素にスタイルを適用すると、ブラウザーは関連する要素への影響を把握し、レイアウトを再計算し、再描画します。  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  
-->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

### スタイル: ツール  

パフォーマンス パネルでレコーディング **を行** います。  大きなイベント `Recalculate Style` \(purple\ で表示) の記録を確認します。  

<!--todo: add Recording section when available  -->  

イベントをクリック `Recalculate Style` すると、[詳細] ウィンドウにイベントに関する詳細情報 **が表示** されます。  スタイルの変更に時間がかかっている場合は、パフォーマンスが低下します。  スタイルの計算が多数の要素に影響を与える場合、これは改善の必要があるもう 1 つの領域です。  

:::image type="complex" source="../media/rendering-tools-performance-recalculate-style-summary.msft.png" alt-text="長い再計算スタイル" lightbox="../media/rendering-tools-performance-recalculate-style-summary.msft.png":::
   長い再計算スタイル  
:::image-end:::  

イベントの影響を軽減 `Recalculate Style` するには、次の方法を使用します。  

*   CSS トリガー [を使用して、][CssTriggers] レイアウト、ペイント、およびコンポジットをトリガーする CSS プロパティを確認します。  これらのプロパティは、レンダリングのパフォーマンスに最も大きな影響を与えます。  
*   影響の少ないプロパティに切り替えます。  <!--See [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties] for more guidance.  -->  
    
<!--todo: add Stick to compositor-only properties and manage layer count section when available -->  

### スタイル: 問題  

次の表に、一般的なスタイルの問題と考える解決策を示します。  

| 問題 | 例 | 解決策 |  
|:--- |:--- |:--- |  
| 応答またはアニメーションに影響を与えるコストの高いスタイルの計算。  | 幅、高さ、位置など、要素の形状を変更する CSS プロパティ。ブラウザーは他のすべての要素をチェックし、レイアウトを再計算します。  | レイアウトをトリガーする CSS を回避する |  
| 応答またはアニメーションに影響を与える複雑なセレクター。  | 入れ子になったセレクターは、親と子を含む他のすべての要素に関する情報をブラウザーに強制的に知らします。  | クラスだけで CSS の要素を参照します。  |  

<!--todo: add Avoid CSS that triggers layouts section when available -->  
<!--todo: add Reduce the Scope and Complexity of Styles Calculations (Reference an element in your CSS with just a class) section when available -->  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  -->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

## レイアウト  

レイアウト (または Firefox でのリフロー) は、ブラウザーがページ上のすべての要素の位置とサイズを計算するプロセスです。  Web のレイアウト モデルは、1 つの要素が他の要素に影響を与える可能性を意味します。たとえば、要素の幅は、通常、すべての子要素の幅に影響を与え、ツリーを上下に移動 `<body>` します。  このプロセスは、ブラウザーに非常に関係する場合があります。  

一般的な経験として、フレームが完成する前に DOM から幾何学的な価値を求める場合は、"強制同期レイアウト" を使用します。これは、頻繁に繰り返したり、大規模な DOM ツリーに対して実行したりすると、パフォーマンスが大きなボトルネックになる可能性があります。  

<!--Related Guides:  

*   [Avoid Layout Thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts]  
*   [Diagnose Forced Synchronous Layouts][DevtoolsRenderingToolsForcedSynchronousLayouts]  -->  

<!--todo: add Avoid CSS that triggers layouts (Avoid Layout Thrashing) section when available -->  
<!--todo: add Diagnose Forced Synchronous Layouts section when available  -->  

### レイアウト: ツール  

[ **パフォーマンス]** ウィンドウは、ページが強制同期レイアウトの原因となる場合を識別します。  これらの `Layout` イベントは赤いバーでマークされます。  

:::image type="complex" source="../media/rendering-tools-jank-performance-recalculate-style-summary.msft.png" alt-text="強制同期レイアウト" lightbox="../media/rendering-tools-jank-performance-recalculate-style-summary.msft.png":::
   強制同期レイアウト  
:::image-end:::  

"レイアウトのスラッシュ" は、強制的な同期レイアウト条件の繰り返しです。  これは、JavaScript が DOM の書き込みと読み取りを繰り返し行う場合に発生します。これにより、ブラウザーはレイアウトを何度も再計算する必要があります。  レイアウトのスラッシュを特定するには、複数の強制同期レイアウト警告のパターンを探します。  前の図を参照してください。  

### レイアウト: 問題  

次の表に、一般的なレイアウトの問題と考える解決策を示します。  

| 問題 | 例 | 解決策 |  
|:--- |:--- |:--- |  
| 応答またはアニメーションに影響を与える強制同期レイアウト。  | ブラウザーがピクセル パイプラインの前の方でレイアウトを実行し、レンダリング プロセスで繰り返しの手順を実行します。  | 最初にスタイルの読み取りをバッチ処理してから、書き込みを行います。  <!--See also [Avoid large, complex layouts and layout thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts].  -->  |  
| 応答またはアニメーションに影響を与えるレイアウトのスラッシュ。  | ブラウザーを読み取り/書き込み/読み取り/書き込みサイクルに入れ、ブラウザーでレイアウトを何度も再計算するループ。  | FastDom ライブラリを使用して読み取り/書き込み [操作を自動的にバッチ処理します][GitHubWilsonpageFastdom]。  |  

<!--todo: add Avoid CSS that triggers layouts (Avoid large, complex layouts and layout thrashing) section when available -->  

## ペイントとコンポジット  

ペイントは、ピクセル単位で塗り分けするプロセスです。  多くの場合、レンダリング プロセスの中で最もコストの高い部分です。  何かの方法でページが不気味なページである場合は、ペイントの問題が発生している可能性があります。  

合成とは、ページの塗り分けされた部分を画面に表示する場所です。  ほとんどの場合、コンポジター専用のプロパティを使用し、ペイントを完全に回避すると、パフォーマンスが大幅に向上しますが、過剰なレイヤー数に注意する必要があります。  <!--See also [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  

<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

### ペイントとコンポジット: ツール  

塗り分けにかかる時間や、塗り分けにかかる頻度を知りたい場合は、  [パフォーマンス][パネルで [高度なペイントイン][DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation]**ストル**メンテーションを有効にする] 設定をオンにし、記録を取る。  ほとんどのレンダリング時間が描画に費やされている場合は、ペイントの問題が発生します。  

<!--
:::image type="complex" source="../media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png" alt-text="Long paint times in timeline recording" lightbox="../media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png":::
   Long paint times in timeline recording  
:::image-end:::  
-->  

<!--
Check out the **Rendering** panel for further configurations that are able to help you diagnose paint problems.  -->  

<!--todo: link Rendering panel in ../evaluate-performance/timeline-tool  sub-section when live  -->  

### ペイントとコンポジット: 問題  

次の表に、一般的なペイントと複合の問題と考える解決策を示します。  

| 問題 | 例 | 解決策 |  
|:--- |:--- |:--- |  
| 応答またはアニメーションに影響を与えるペイント ストーム。  | 大きなペイント領域や、応答やアニメーションに影響を与える高価なペイント。  | ペイントを使うのを避け、独自のレイヤーに移動する要素を昇格し、変換と不透明度を使います。  <!--See [Simplify paint complexity and reduce paint areas][WebFundamentalsPerformanceRenderingSimplifyPaintComplexity].  -->  |  
| アニメーションに影響を与えるレイヤー のエクスプリング。  | 要素が多すぎると、アニメーションのパフォーマンスに大 `translateZ(0)` きな影響を与えます。  | レイヤーに積極的に昇格します。それがわかっている場合にのみ、具体的な改善が提供されます。  <!--See [Stick to composite-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  |  

<!--todo: add Simplify paint complexity and reduce paint areas section when available  -->  
<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

## Microsoft Edge DevTools チームと連絡を取る  

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
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページはここから[](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/index)見つかり[、Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Writer\) と[Meggin Kearney][MegginKearney] \(Tech Writer\) が執筆しています。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
