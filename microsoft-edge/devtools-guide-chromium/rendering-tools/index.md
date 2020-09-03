---
description: ユーザーは対話的なページとスムーズなページを期待します。  ピクセルパイプラインの各ステージは、jank を導入する機会を表します。  実行時のパフォーマンスを低下させる一般的な問題を特定して修正するためのツールと戦略について説明します。
title: 実行時のパフォーマンスを分析する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: f7ca848712268110700fac2c5fb75fe1751812bf
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992707"
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

ユーザーは対話的なページとスムーズなページを期待します。  ピクセルパイプラインの各ステージは、jank を導入する機会を表します。  実行時のパフォーマンスを低下させる一般的な問題を特定して修正するためのツールと戦略について説明します。  

### まとめ  

*   ブラウザーでレイアウトを再計算するように強制する JavaScript を記述しないでください。  読み取りと書き込みの関数を区切り、まず読み取りを実行します。  
*   CSS の複雑さを超えないようにします。  Css セレクターをシンプルにしてください。  
*   可能な限りレイアウトを避けます。  レイアウトをトリガーしない CSS を選択します。  
*   塗装は、他のレンダリングアクティビティよりも時間がかかることがあります。  ペイントのボトルネックに注意してください。  
    
## JavaScript  

JavaScript の計算、特に広範な視覚的な変更をトリガーする場合は、アプリケーションのパフォーマンスが低下することがあります。  不適切なタイミングを設定したり、長時間の JavaScript を使用してユーザーの操作に干渉しないようにします。  

### JavaScript: ツール  

[ **パフォーマンス** ] パネルでレコーディングを実行して、suspiciously の長いイベントを探し `Evaluate Script` ます。  <!--If you find any, you are able to enable the **JS Profiler** and re-do your recording to get more detailed information about exactly which JavaScript functions were used and how long each took.  -->  

<!--todo: add Recording section when available  -->  
<!--todo: add Profile JavaScript (JS Profiler) section when available  -->  

JavaScript で非常に多くの jank が見られた場合は、分析を次のレベルにして JavaScript CPU プロファイルを収集する必要があります。  CPU プロファイルは、ページの関数内でランタイムが消費される場所を示します。  CPU プロファイルを作成する方法については、「 [JavaScript ランタイムの速度を向上][DevtoolsRenderingToolsJavascriptRuntime]させる」を参照してください。

### JavaScript: 問題  

次の表では、JavaScript の一般的な問題と解決策について説明します。  

| 問題 | 例 | 解決策 |  
|:--- |:--- |:--- |  
| 応答またはアニメーションに影響する負荷の高い入力ハンドラー。  | タッチ、視差効果のスクロール。  | ブラウザーでタッチを処理してスクロールするか、またはリスナーをできるだけ遅くバインドします。  [Paul ルイスの実行時パフォーマンスチェックリストで負荷の高い入力ハンドラーを][WebPerformanceCalendarRuntimeChecklist]参照してください。  |  
| 応答、アニメーション、読み込みに影響を与える、時間がかかる JavaScript。  | ユーザーは、ページの読み込み、setTimeout、setInterval の後で右にスクロールします。  | JavaScript の実行時の最適化: 使用 `requestAnimationFrame` 、フレーム上の DOM の操作、 [Web ワーカー][MDNUsingWebWorkers]の使用などを行います。  |  
| 応答に影響を与える長時間の JavaScript。  | [Domcontentloaded イベント][MDNUsingWebWorkers]は、JS の作業をさばきするため、ストールします。  | 純粋な計算作業を [Web ワーカー][MDNUsingWebWorkers]に移動します。  DOM へのアクセスが必要な場合は、を使用 `requestAnimationFrame` します。  <!--See also [Optimize JavaScript Execution][WebFundamentalsPerformanceRenderingOptimizeJavascriptRuntime].  -->  |  
| 応答またはアニメーションに影響を与えるガーベジスクリプト。  | ガベージコレクションがどこでも発生する可能性があります。  | 書き込みが少ないガベージ y スクリプト。  「 [Paul ルイスのランタイムパフォーマンスチェックリスト」の「アニメーションのガベージコレクション][WebPerformanceCalendarRuntimeChecklist]」を参照してください。  |  

<!--todo: add Optimize JavaScript runtime section when available  -->  

## 形式  

スタイルの変更にはコストがかかります。特に、それらの変更が DOM の複数の要素に影響する場合。  要素にスタイルを適用すると、ブラウザーがすべての関連要素への影響を把握し、レイアウトを再計算し、再描画します。  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  
-->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

### スタイル: ツール  

[ **パフォーマンス** ] パネルでレコーディングを実行します。  大きい `Recalculate Style` イベント (紫 \) の記録を確認します。  

<!--todo: add Recording section when available  -->  

イベントをクリック `Recalculate Style` すると、 **詳細** ウィンドウにイベントの詳細情報が表示されます。  スタイルの変更に時間がかかる場合は、パフォーマンスに影響します。  スタイルの計算が多くの要素に影響を与えている場合は、さらに改善の余地がある別の領域です。  

:::image type="complex" source="../media/rendering-tools-performance-recalculate-style-summary.msft.png" alt-text="長い再計算のスタイル" lightbox="../media/rendering-tools-performance-recalculate-style-summary.msft.png":::
   長い再計算のスタイル  
:::image-end:::  

イベントの影響を軽減するには、 `Recalculate Style` 次の操作を行います。  

*   [Css トリガー][CssTriggers]を使って、レイアウト、ペイント、コンポジットをトリガーする css プロパティについて説明します。  これらのプロパティは、レンダリングのパフォーマンスに影響を及ぼすことはほとんどありません。  
*   影響の少ないプロパティに切り替える。  <!--See [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties] for more guidance.  -->  
    
<!--todo: add Stick to compositor-only properties and manage layer count section when available -->  

### スタイル: 問題  

次の表では、一般的なスタイルの問題と考えられる解決策について説明します。  

| 問題 | 例 | 解決策 |  
|:--- |:--- |:--- |  
| 応答またはアニメーションに影響する負荷の高いスタイルの計算。  | Width、height、position などの要素のジオメトリを変更する CSS プロパティ。ブラウザーは、他のすべての要素をチェックし、レイアウトを再計算します。  | レイアウトをトリガーする CSS を使わない |  
| 応答またはアニメーションに影響を与える複雑なセレクター。  | 入れ子になったセレクターを有効にすると、親と子を含む、他のすべての要素に関するすべての情報がブラウザーで認識されます。  | CSS の要素をクラスのみで参照します。  |  

<!--todo: add Avoid CSS that triggers layouts section when available -->  
<!--todo: add Reduce the Scope and Complexity of Styles Calculations (Reference an element in your CSS with just a class) section when available -->  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  -->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

## レイアウト  

レイアウト (または Firefox によるリフロー) は、ブラウザーがページ上のすべての要素の位置とサイズを計算するプロセスです。  Web のレイアウトモデルでは、1つの要素が他の要素に影響を与える可能性があります。たとえば、要素の幅は通常、子要素の幅、つまり、 `<body>` ツリーの上下の方向に影響します。  このプロセスは、ブラウザーに非常に関連している可能性があります。  

一般的な目安として、フレームが完了する前に DOM から幾何学的な値を取得するように要求すると、"強制同期レイアウト" が適用されます。これは、頻繁に繰り返すか、大きな DOM ツリーに対して実行された場合は、パフォーマンスが大幅に低下する可能性があります。  

<!--Related Guides:  

*   [Avoid Layout Thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts]  
*   [Diagnose Forced Synchronous Layouts][DevtoolsRenderingToolsForcedSynchronousLayouts]  -->  

<!--todo: add Avoid CSS that triggers layouts (Avoid Layout Thrashing) section when available -->  
<!--todo: add Diagnose Forced Synchronous Layouts section when available  -->  

### レイアウト: ツール  

[ **パフォーマンス** ] ウィンドウは、ページで強制的な同期レイアウトが行われるタイミングを示します。  これらの `Layout` イベントは赤いバーでマークされます。  

:::image type="complex" source="../media/rendering-tools-jank-performance-recalculate-style-summary.msft.png" alt-text="強制同期レイアウト" lightbox="../media/rendering-tools-jank-performance-recalculate-style-summary.msft.png":::
   強制同期レイアウト  
:::image-end:::  

"レイアウトのスラッシング" は、強制的な同期レイアウト条件を繰り返します。  これは、JavaScript が DOM を繰り返し読み書きするときに発生します。これにより、ブラウザーでは、レイアウトの再計算が強制的に行われます。  レイアウトのスラッシングを特定するには、複数の強制同期レイアウトの警告パターンを探します。  前の図を参照してください。  

### レイアウト: 問題  

次の表では、一般的なレイアウトの問題と考えられる解決策について説明します。  

| 問題 | 例 | 解決策 |  
|:--- |:--- |:--- |  
| 応答またはアニメーションに影響する強制同期レイアウト  | ピクセルパイプラインで事前にレイアウトを実行するようにブラウザーを強制することで、レンダリングプロセスの手順が繰り返しられます。  | スタイルを最初に読み込み、次に書き込みを行います。  <!--See also [Avoid large, complex layouts and layout thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts].  -->  |  
| 応答またはアニメーションに影響するレイアウトのスラッシング。  | ブラウザーを読み取り/書き込み可能な読み取り/書き込みのサイクルにして、ブラウザーのレイアウトを再計算するように強制するループ。  | [Fastdom ライブラリ][GitHubWilsonpageFastdom]を使用して、読み取り/書き込み操作を自動的にバッチ処理します。  |  

<!--todo: add Avoid CSS that triggers layouts (Avoid large, complex layouts and layout thrashing) section when available -->  

## ペイントとコンポジット  

ペイントとは、ピクセル単位で塗りつぶしを行うプロセスです。  これは、多くの場合、レンダリング処理の中で最もコストがかかる部分です。  ページが何らかの方法で janky されている場合は、ペイントの問題が発生している可能性があります。  

[合成] では、ページの塗りつぶされた部分を、画面に表示するために一緒に配置します。  ほとんどの場合、コンポジター専用のプロパティにしてペイントをまったく行わないようにすると、パフォーマンスが大幅に向上しますが、過剰なレイヤーカウントについては注意が必要です。  <!--See also [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  

<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

### ペイントとコンポジット: ツール  

ペイントにかかる時間や、ペイントの頻度を知りたい場合  [**パフォーマンス**] パネルの [[高度な描画インストルメンテーションを有効にする][DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation]] 設定を確認して、記録を撮ります。  レンダリング時間の大半がペイントに費やされている場合は、ペイントの問題が発生します。  

<!--
:::image type="complex" source="../media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png" alt-text="Long paint times in timeline recording" lightbox="../media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png":::
   Long paint times in timeline recording  
:::image-end:::  
-->  

<!--
Check out the **Rendering** panel for further configurations that are able to help you diagnose paint problems.  -->  

<!--todo: link Rendering panel in ../evaluate-performance/timeline-tool  sub-section when live  -->  

### ペイントとコンポジット: 問題  

次の表では、一般的な塗装およびコンポジットの問題と考えられる解決策について説明します。  

| 問題 | 例 | 解決策 |  
|:--- |:--- |:--- |  
| 応答やアニメーションに影響を与える塗装。  | 大きな塗装領域または負荷の高い応答やアニメーション。  | ペイントは避け、独自のレイヤーに移動する要素のレベル上げ、変形と不透明度の使用を行います。  <!--See [Simplify paint complexity and reduce paint areas][WebFundamentalsPerformanceRenderingSimplifyPaintComplexity].  -->  |  
| アニメーションに影響するレイヤーの爆発。  | 多くの要素をオーバープロモーションすると、 `translateZ(0)` アニメーションのパフォーマンスに大きく影響します。  | レイヤーへの昇格は慎重に行うことができます。把握している場合にのみ、明確な改善が提供されます。  <!--See [Stick to composite-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  |  

<!--todo: add Simplify paint complexity and reduce paint areas section when available  -->  
<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

## Microsoft Edge DevTools チームと連絡を取り合う  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsRenderingToolsJavascriptRuntime]: ./js-runtime.md "JavaScript の実行時間を短縮する |Microsoft ドキュメント"  
[DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation]: ../evaluate-performance/reference.md#enable-advanced-paint-instrumentation "高度な描画のインストルメンテーションを有効にする-パフォーマンス分析リファレンス |Microsoft ドキュメント"

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

[MDNUsingWebWorkers]: https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers "Web ワーカーの使い方 |MDN"  

[WebPerformanceCalendarRuntimeChecklist]: https://calendar.perfplanet.com/2013/the-runtime-performance-checklist/ "ランタイムパフォーマンスチェックリスト-Web パフォーマンスカレンダー"  

[GitHubWilsonpageFastdom]: https://github.com/wilsonpage/fastdom "このページ/fastdom |GitHub"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/index) にあり、 [Kayce basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) および [Meggin Kearney][MegginKearney] \ (Tech writer \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
