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

# <a name="analyze-runtime-performance"></a>実行時のパフォーマンスを分析する  

ユーザーは、対話的でスムーズなページを期待しています。  ピクセル パイプラインの各ステージは、jank を導入する機会を表します。  ランタイムのパフォーマンスを低下させる一般的な問題を特定して修正するためのツールと戦略について説明します。  

### <a name="summary"></a>要約  

*   ブラウザーにレイアウトの再計算を強制的に適用する JavaScript を記述しない。  読み取り関数と書き込み関数を分離し、最初に読み取りを実行します。  
*   CSS を複雑にし過ぎない。  CSS を少なくし、CSS セレクターをシンプルに保つ。  
*   レイアウトは可能な限り避ける。  レイアウトを全くトリガーしない CSS を選択します。  
*   ペイントには、他のレンダリング アクティビティよりも時間がかかる場合があります。  ペイントのボトルネックに注意してください。  
    
## <a name="javascript"></a>JavaScript  

JavaScript の計算、特に大規模な視覚的な変更をトリガーする計算では、アプリケーションのパフォーマンスが低下する可能性があります。  時間が悪い、または長時間実行されている JavaScript がユーザーの操作に干渉しないようにします。  

### <a name="javascript-tools"></a>JavaScript: ツール  

パフォーマンス ツールで記録を **取り** 、疑わしい長いイベントを探 `Evaluate Script` します。  <!--If you find any, you are able to enable the **JS Profiler** and re-do your recording to get more detailed information about exactly which JavaScript functions were used and how long each took.  -->  

<!--todo: add Recording section when available  -->  
<!--todo: add Profile JavaScript (JS Profiler) section when available  -->  

JavaScript でかなりのジャンクに気が付く場合は、分析を次のレベルに進めて JavaScript CPU プロファイルを収集する必要がある場合があります。  CPU プロファイルは、ページの機能内でランタイムが使用される場所を示します。  JavaScript ランタイムの高速化で CPU プロファイルを作成 [する方法について説明します][DevtoolsRenderingToolsJavascriptRuntime]。

### <a name="javascript-problems"></a>JavaScript: 問題  

次の表では、一般的な JavaScript の問題と潜在的な解決策について説明します。  

| 問題 | 例 | ソリューション |  
|:--- |:--- |:--- |  
| 応答またはアニメーションに影響を与える高価な入力ハンドラー。  | タッチ、視差スクロール。  | ブラウザーでタッチとスクロールを処理するか、リスナーを可能な限り遅くバインドします。  Paul [Lewis のランタイム パフォーマンス チェックリストの [高価な入力ハンドラー] に移動します][WebPerformanceCalendarRuntimeChecklist]。  |  
| 応答、アニメーション、読み込みに影響を与える JavaScript の時間が悪い。  | ユーザーはページ読み込み直後にスクロールします。setTimeout /setInterval。  | JavaScript ランタイムの最適化: Use `requestAnimationFrame` 、フレームに DOM 操作を広げる [、Web ワーカーを使用する][MDNUsingWebWorkers]。  |  
| 応答に影響を与える JavaScript の実行時間が長い。  | [DOMContentLoaded イベントは][MDNUsingWebWorkers]、JS の動作に合ってストールします。  | 純粋な計算作業を [Web ワーカーに移動します][MDNUsingWebWorkers]。  DOM アクセスが必要な場合は、 を使用します `requestAnimationFrame` 。  <!--Navigate to [Optimize JavaScript Execution][WebFundamentalsPerformanceRenderingOptimizeJavascriptRuntime].  -->  |  
| 応答またはアニメーションに影響を与えるガベージ y スクリプト。  | ガベージ コレクションは、任意の場所で発生する可能性があります。  | ガベージ y スクリプトを少なくします。  Paul [Lewis のランタイム パフォーマンス チェックリストの [アニメーション] の [ガベージ コレクション] に移動します][WebPerformanceCalendarRuntimeChecklist]。  |  

<!--todo: add Optimize JavaScript runtime section when available  -->  

## <a name="style"></a>形式  

スタイルの変更は、特にこれらの変更が DOM 内の複数の要素に影響を与える場合、コストがかかります。  要素にスタイルを適用すると、ブラウザーは関連する要素への影響を把握し、レイアウトを再計算し、再描画します。  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  
-->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

### <a name="style-tools"></a>スタイル: ツール  

パフォーマンス ツールで記録 **を取** る。  大きなイベント `Recalculate Style` \(紫で表示される\) の記録を確認します。  

<!--todo: add Recording section when available  -->  

詳細ウィンドウ `Recalculate Style` でイベントの詳細を表示するには、イベントを **選択** します。  スタイルの変更に時間がかかっている場合は、パフォーマンスが低下します。  スタイルの計算が多数の要素に影響を与える場合は、改善の必要があるもう 1 つの領域です。  

:::image type="complex" source="../media/rendering-tools-performance-recalculate-style-summary.msft.png" alt-text="長い再計算スタイル" lightbox="../media/rendering-tools-performance-recalculate-style-summary.msft.png":::
   長い再計算スタイル  
:::image-end:::  

イベントの影響を軽減 `Recalculate Style` するには、次の方法を実行します。  

*   CSS トリガー [を使用して、][CssTriggers] レイアウト、ペイント、コンポジットをトリガーする CSS プロパティを確認します。  これらのプロパティは、レンダリングパフォーマンスに最悪の影響を与えます。  
*   影響の少ないプロパティに切り替えます。  <!--For more guidance, navigate to [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  
    
<!--todo: add Stick to compositor-only properties and manage layer count section when available -->  

### <a name="style-problems"></a>スタイル: 問題  

次の表では、一般的なスタイルの問題と潜在的な解決策について説明します。  

| 問題 | 例 | ソリューション |  
|:--- |:--- |:--- |  
| 応答またはアニメーションに影響を与える高価なスタイルの計算。  | 幅、高さ、位置など、要素のジオメトリを変更する CSS プロパティ。ブラウザーは他のすべての要素をチェックし、レイアウトを再計算します。  | レイアウトをトリガーする CSS を回避する |  
| 応答またはアニメーションに影響を与える複雑なセレクター。  | 入れ子になったセレクターは、親と子を含む他のすべての要素についてブラウザーに知らされます。  | クラスだけで CSS の要素を参照します。  |  

<!--todo: add Avoid CSS that triggers layouts section when available -->  
<!--todo: add Reduce the Scope and Complexity of Styles Calculations (Reference an element in your CSS with just a class) section when available -->  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  -->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

## <a name="layout"></a>レイアウト  

レイアウト (または Firefox でのリフロー) は、ブラウザーがページ上のすべての要素の位置とサイズを計算するプロセスです。  Web のレイアウト モデルは、1 つの要素が他の要素に影響を与える可能性を意味します。たとえば、要素の幅は、通常、ツリーの上下のすべての方法で、任意の子要素の幅に `<body>` 影響します。  このプロセスは、ブラウザーに非常に関係している可能性があります。  

一般的な経験則として、フレームが完成する前に DOM から幾何学的な値を返す必要がある場合は、"強制同期レイアウト" を使用します。これは、頻繁に繰り返したり、大規模な DOM ツリーに対して実行したりすると、パフォーマンスのボトルネックが大きい可能性があります。  

<!--Related Guides:  

*   [Avoid Layout Thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts]  
*   [Diagnose Forced Synchronous Layouts][DevtoolsRenderingToolsForcedSynchronousLayouts]  -->  

<!--todo: add Avoid CSS that triggers layouts (Avoid Layout Thrashing) section when available -->  
<!--todo: add Diagnose Forced Synchronous Layouts section when available  -->  

### <a name="layout-tools"></a>レイアウト: ツール  

[ **パフォーマンス]** ウィンドウは、ページが強制的に同期レイアウトを発生させる原因を識別します。  これらの `Layout` イベントは赤いバーでマークされます。  

:::image type="complex" source="../media/rendering-tools-jank-performance-recalculate-style-summary.msft.png" alt-text="強制同期レイアウト" lightbox="../media/rendering-tools-jank-performance-recalculate-style-summary.msft.png":::
   強制同期レイアウト  
:::image-end:::  

"レイアウトスラッシング" は、強制的な同期レイアウト条件の繰り返しです。  これは、JavaScript が DOM から繰り返し書き込みおよび読み取りを行い、ブラウザーがレイアウトを何度も再計算する場合に発生します。  レイアウトのスラッシングを特定するには、複数の強制同期レイアウト警告のパターンを探します。  前の図を確認します。  

### <a name="layout-problems"></a>レイアウト: 問題  

次の表では、一般的なレイアウトの問題と潜在的な解決策について説明します。  

| 問題 | 例 | ソリューション |  
|:--- |:--- |:--- |  
| 応答またはアニメーションに影響を与える強制的な同期レイアウト。  | ブラウザーにピクセル パイプラインのレイアウトを実行する前に、レンダリング プロセスの手順を繰り返す必要があります。  | スタイルの読み取りを最初にバッチ処理してから、書き込みを行います。  <!--Navigate to [Avoid large, complex layouts and layout thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts].  -->  |  
| 応答またはアニメーションに影響を与えるレイアウトのスラッシング。  | ブラウザーを読み取り/書き込み/読み取り/書き込みサイクルに入れ、ブラウザーがレイアウトを何度も再計算するループ。  | FastDom ライブラリを使用して読み取り/書き込み [操作を自動的にバッチ処理します][GitHubWilsonpageFastdom]。  |  

<!--todo: add Avoid CSS that triggers layouts (Avoid large, complex layouts and layout thrashing) section when available -->  

## <a name="paint-and-composite"></a>ペイントとコンポジット  

ペイントは、ピクセル単位で塗り分けするプロセスです。  多くの場合、レンダリング プロセスの最もコストの高い部分です。  ページがデザイン通り動作していない場合は、ペイントの問題が発生している可能性があります。  

合成とは、ページの塗られた部分を画面に表示するための組み合わせて作成する場所です。  ほとんどの場合、コンポジター専用のプロパティに固執し、ペイントを完全に避ける場合は、パフォーマンスが大幅に向上しますが、過剰なレイヤー数に注意する必要があります。  <!--Navigate to [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  

<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

### <a name="paint-and-composite-tools"></a>ペイントとコンポジット: ツール  

ペイントにかかる時間や、ペイントが発生する頻度を知りたがっていますか?  [パフォーマンス] [パネルの [高度なペイントインス][DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation] トルメンテーションを有効にする] **設定を確認** し、録音を行います。  ほとんどのレンダリング時間がペイントに費やされている場合は、ペイントに問題があります。  

<!--
:::image type="complex" source="../media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png" alt-text="Long paint times in timeline recording" lightbox="../media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png":::
   Long paint times in timeline recording  
:::image-end:::  
-->  

<!--
Check out the **Rendering** panel for further configurations that are able to help you diagnose paint problems.  -->  

<!--todo: link Rendering panel in ../evaluate-performance/timeline-tool  sub-section when live  -->  

### <a name="paint-and-composite-problems"></a>ペイントとコンポジット: 問題  

次の表では、一般的なペイントとコンポジットの問題と潜在的な解決策について説明します。  

| 問題 | 例 | ソリューション |  
|:--- |:--- |:--- |  
| 応答またはアニメーションに影響を与えるストームをペイントします。  | 応答やアニメーションに影響を与える大きなペイント領域または高価なペイント。  | ペイントを避け、独自のレイヤーに移動する要素を昇格し、変換と不透明度を使用します。  <!--Navigate to [Simplify paint complexity and reduce paint areas][WebFundamentalsPerformanceRenderingSimplifyPaintComplexity].  -->  |  
| アニメーションに影響を与えるレイヤーの爆発。  | アニメーションのパフォーマンスに大きな影響を与える要素が多すぎます `translateZ(0)` 。  | レイヤーへの昇格は、重要な改善点を提供する場合にのみ行います。  <!--Navigate to [Stick to composite-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  |  

<!--todo: add Simplify paint complexity and reduce paint areas section when available  -->  
<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

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
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> 元のページはここで[](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/index)見つかり[、Kayce バス][KayceBasques]ク人 \(Technical Writer, Chrome DevTools \& ライトハウス\) と[Meggin Kearney][MegginKearney] \(Tech Writer\) によって作成されています。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
