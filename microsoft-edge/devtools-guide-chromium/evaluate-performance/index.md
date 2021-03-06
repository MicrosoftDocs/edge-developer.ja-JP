---
description: Microsoft Edge DevTools で実行時のパフォーマンスを評価する方法について説明します。
title: ランタイム のパフォーマンスの分析の開始
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 074c112b99abb4689cac2274338f2276bc46b4ae
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398722"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# <a name="get-started-with-analyzing-runtime-performance"></a>ランタイム のパフォーマンスの分析の開始  

> [!NOTE]
> ページの読み込み速度を速くする方法については、「オプティマイズ Web サイトの [速度」に移動します][DevtoolsSpeedGetStarted]。  

実行時のパフォーマンスは、読み込みとは対照的に、ページの実行時のパフォーマンスです。  次のチュートリアル記事では、Microsoft Edge DevTools Performance パネルを使用して実行時のパフォーマンスを分析する方法について説明します。  **RAIL**モデルに関して、このチュートリアルで学習するスキルは、ページの応答、アニメーション、アイドル状態のフェーズを分析する場合に役立ちます。  

<!--todo: add rail link when section is ready -->  

## <a name="get-started"></a>概要  

次のチュートリアルでは、ライブ ページで DevTools を開き****、[パフォーマンス] パネルを使用してページのパフォーマンスのボトルネックを見つける。  

1.  **InPrivate モードで Microsoft Edge を開きます**。  InPrivate モードでは、Microsoft Edge がクリーンな状態で実行されます。  たとえば、多くの拡張機能がインストールされている場合、拡張機能によってパフォーマンス測定値にノイズが発生する可能性があります。  
    
    <!--TODO: replace section when updated for new Edge  -->
    
1.  InPrivate ウィンドウに次のページを読み込む。  このページは、プロファイルを作成するデモです。  ページには、上下に移動する小さなアイコンの束が表示されます。  
    
    ```https
    https://microsoft-edge-chromium-devtools.glitch.me/sluggish/
    ```  
    
1.  `Control` + `Shift` + `I` \(Windows, Linux\) または `Command` + `Option` + `I` \(macOS\) を選択して DevTools を開きます。  
    
    :::image type="complex" source="../media/evaluate-performance-get-started-side-by-side.msft.png" alt-text="左側のデモと右側の DevTools" lightbox="../media/evaluate-performance-get-started-side-by-side.msft.png":::
       左側のデモと右側の DevTools  
    :::image-end:::  
    
    > [!NOTE]
    > 残りの図では、DevTools はコンテンツに[][DevtoolsCustomizePlacement]焦点を当てるには別のウィンドウにドッキングされません。  
    
### <a name="simulate-a-mobile-cpu"></a>モバイル CPU のシミュレーション  

モバイル デバイスの CPU 電力は、デスクトップやラップトップに比してはるかに少ない。  ページをプロファイルするたびに、CPU 調整を使用して、モバイル デバイスでのページのパフォーマンスをシミュレートします。  

1.  DevTools で、[パフォーマンス] ツール **を選択** します。  
1.  [スクリーンショット] チェック **ボックスが有効** になっていることを確認します。  
1.  [ **キャプチャ設定]** \(!] を選択します。Capture Settings][ImageCaptureSettingsIcon]\)。  DevTools は、パフォーマンス 指標のキャプチャ方法に関連する設定を表示します。  
1.  **[CPU]** の場合は **、[4 倍の速度低下] を選択します**。  DevTools は CPU を調整して、通常の 4 倍遅くします。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-capture-settings.msft.png" alt-text="CPU スロットル" lightbox="../media/evaluate-performance-performance-capture-settings.msft.png":::
       CPU スロットル  
    :::image-end:::  
    
    > [!NOTE]
    > 他のページをテストする場合。各ページがローエンド モバイル デバイスで適切に動作する場合は、CPU 調整を **6 倍の速度低下に設定します**。  デモは 6 倍のスローダウンではうまく動作しないので、4 倍のスローダウンを命令目的で使用します。  
    
### <a name="set-up-the-demo"></a>デモのセットアップ  

Web サイトのすべての閲覧者に一貫して動作するランタイム パフォーマンス デモを作成するのは難しいです。  次のセクションでは、デモをカスタマイズして、特定のセットアップに関係なく、エクスペリエンスがスクリーンショットや説明と比較的一貫性を保ちます。

1.  青い **アイコンが以前よりも明らかに遅くなるまで、[10** の追加] ボタンを選択します。  高級機械では、20 回くらい選択できます。  
1.  [最適化 **] を選択します**。  青いアイコンは、より速く、よりスムーズに移動する必要があります。  
    
    > [!NOTE]
    > 最適化されたバージョンと最適化されていないバージョンの違いをより適切に表示するには **、[10** の減算] ボタンを数回選択し、もう一度やり直してください。  
    > 青いアイコンを追加しすぎると、CPU を最大にし、2 つのバージョンの結果に大きな違いが生じない場合があります。  
    
1.  [ **最適化解除] を選択します**。  青いアイコンの移動速度が遅く、再び低調になります。  
    
### <a name="record-runtime-performance"></a>実行時のパフォーマンスを記録する  

最適化されたバージョンのページを実行すると、青いアイコンの移動速度が速くなります。  それはどうしてですか。  どちらのバージョンも、アイコンを同じ時間内に同じ容量の領域に移動する必要があります。  [パフォーマンス] パネルでレコーディングを行い、最適化されていないバージョンでパフォーマンスのボトルネックを検出する方法について説明します。  

1.  DevTools で **、[Record** \(!] を選択します。Record][ImageRecordIcon]\)。  DevTools は、ページの実行時にパフォーマンス 指標をキャプチャします。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-profiling.msft.png" alt-text="ページのプロファイル" lightbox="../media/evaluate-performance-performance-profiling.msft.png":::
       ページのプロファイル  
    :::image-end:::  
    
1.  数秒待ちます。  
1.  [ **停止] を選択します**。  DevTools は記録を停止し、データを処理し、結果を [パフォーマンス] パネルに表示します。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-capture-results.msft.png" alt-text="プロファイルの結果" lightbox="../media/evaluate-performance-performance-capture-results.msft.png":::
       プロファイルの結果  
    :::image-end:::  
    
うわー、それは圧倒的な量のデータです。  心配しないで、すぐにプロセスはもっと理にかなっています。  

## <a name="analyze-the-results"></a>結果を分析する  

ページのパフォーマンスを記録した後、ページのパフォーマンスの品質を測定し、原因を見つける。  

### <a name="analyze-frames-per-second"></a>1 秒あたりのフレーム数の分析  

アニメーションのパフォーマンスを測定する主な指標は、1 秒あたりのフレーム数 \(FPS\) です。  アニメーションが 60 FPS で実行される場合、ユーザーは満足しています。  

1.  FPS グラフ **を確認** します。  赤いバーが **FPS**の上に表示されるたびに、フレームレートが低くドロップされ、ユーザー エクスペリエンスに害を与える可能性があります。  一般に、緑のバーが大きいほど、FPS は高くなります。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-fps-chart.msft.png" alt-text="FPS グラフ" lightbox="../media/evaluate-performance-performance-fps-chart.msft.png":::
       **FPS グラフ**  
    :::image-end:::  
    
1.  FPS グラフ **の下** に **CPU グラフ** が表示されます。  CPU グラフの**色**は、[パフォーマンス] パネルの**** 下部にある [概要] パネルの色に対応します。  CPU グラフが **色に** 満ちていという事実は、記録中に CPU が最大にされたという意味です。  CPU が長時間使い切った場合は常に、より少ない作業を行う方法を見つける必要があります。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-cpu-chart.msft.png" alt-text="[CPU グラフ] と [概要] パネル" lightbox="../media/evaluate-performance-performance-cpu-chart.msft.png":::
       **[CPU グラフ**] と **[概要]** パネル  
    :::image-end:::  
    
1.  **FPS、CPU、または** **NET**グラフに**カーソルを合**わせる。  DevTools は、その時点でページのスクリーンショットを表示します。  マウスを左右に動かすと、録音が再生されます。  アクションはスクラブとして参照され、アニメーションの進行状況を手動で分析する場合に便利です。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-screenshot-hover.msft.png" alt-text="記録の 2500ms マークを中心にページのスクリーンショットを表示する" lightbox="../media/evaluate-performance-performance-screenshot-hover.msft.png":::
       記録の 2500ms マークを中心にページのスクリーンショットを表示する  
    :::image-end:::  
    
1.  [フレーム **] セクション** で、緑色の四角形の 1 つをポイントします。  DevTools には、その特定のフレームの FPS が表示されます。  各フレームは、ターゲットの 60 FPS を大いに下回っている可能性があります。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-frame-hover.msft.png" alt-text="フレームにカーソルを合わせる" lightbox="../media/evaluate-performance-performance-frame-hover.msft.png":::
       フレームにカーソルを合わせる  
    :::image-end:::  
    
もちろん、表示は Web ページがうまく機能していないと示します。  しかし、実際のシナリオでは、明らかではないので、測定を行うすべてのツールを使用すると便利です。  

#### <a name="bonus-open-the-fps-meter"></a>ボーナス: FPS メーターを開く  

もう 1 つの便利なツールは、ページの実行時に FPS のリアルタイム推定値を提供する FPS メーターです。  

1.  `Control`+`Shift`+`P` \(Windows, Linux\) または `Command`+`Shift`+`P` \(macOS\) を選択して、**コマンド メニュー** を開きます。  
1.  コマンド メニューで `Rendering` 入力を **開始し、[レンダリング** の表示] **を選択します**。  
1.  レンダリング ツール **で、FPS** メーター **を有効にします**。  新しいオーバーレイがビューポートの右側に表示されます。  
    
    :::image type="complex" source="../media/evaluate-performance-fps-meter-overlay.msft.png" alt-text="FPS メーター" lightbox="../media/evaluate-performance-fps-meter-overlay.msft.png":::
       **FPS メーター**  
        :::image-end:::  
    
1.  FPS メーターを **オフにし、[** レンダリング] `Escape` ツールを閉じる場合 **に選択** します。  このチュートリアルでは **、FPS メーター** を使用しません。  
    
### <a name="find-the-bottleneck"></a>ボトルネックを見つける  

アニメーションがうまく機能していないと測定して確認した後、次の手順は「なぜですか」という質問に答えます。  

1.  イベントが選択されている場合は、[ **概要** ] パネルにアクティビティの内訳が表示されます。  ページはレンダリングに多くの時間を費やしました。  パフォーマンスは少ない作業を行う技術ですから、レンダリング作業に費やされる時間を減らすことが目標です。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-summary-tab.msft.png" alt-text="[概要] パネル" lightbox="../media/evaluate-performance-performance-summary-tab.msft.png":::
       [ **概要]** パネル  
    :::image-end:::  
    
1.  [メイン] **セクションを展開** します。  DevTools は、メイン スレッドのアクティビティの時間の一部を示します。  x 軸は、時間の過ぎた記録を表します。  各バーはイベントを表します。  バーが広いということは、イベントに時間がかかったという意味です。  y 軸は呼び出し履歴を表します。  イベントが互いに重なって表示される場合は、上位イベントによって下位イベントが発生したという意味です。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-main.msft.png" alt-text="[メイン] セクション" lightbox="../media/evaluate-performance-performance-main.msft.png":::
       [ **メイン]** セクション  
    :::image-end:::  
    
1.  記録には多くのデータがあります。  1 つのイベントを拡大するには。**** **** **FPS、CPU、** および NET グラフを含むセクションである Overview の上でカーソルを選択、保持、**およびドラッグ**します。  [ **メイン]** セクションと **[概要]** パネルには、録音の選択した部分の情報だけが表示されます。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="イベントを拡大する" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
       イベントを拡大する  
    :::image-end:::  
    
    > [!NOTE]
    > もう 1 つの方法として、ズーム、 **メイン** セクションのフォーカス、背景またはイベントの選択、および `W` 、 `A` `S` を選択します `D` 。  
    
    1.  Animation Frame Fired イベントの右の赤い三角形 **にフォーカス** します。  赤い三角形が表示されるたびに、イベントに関連する問題が発生する可能性があるという警告です。  
    
    > [!NOTE]
    > Animation **Frame Fired イベント**は、コールバックが実行[ `requestAnimationFrame()` されるたびに][MDNWebRequestAnimationFrame]発生します。  
    
1.  [アニメーション フレーム **の発生] イベントを選択** します。  [ **概要] パネル** に、そのイベントに関する情報が表示されます。  [表示] **リンクに注意** してください。  選択した後、DevTools は Animation Frame Fired イベントを開始したイベント **を強調表示** します。  また ** 、app.js:95 リンクにフォーカス** します。  選択すると、ソース コード内の関連する行が表示されます。
    
    :::image type="complex" source="../media/evaluate-performance-performance-animation-frame-fired.msft.png" alt-text="Animation Frame Fired イベントの詳細" lightbox="../media/evaluate-performance-performance-animation-frame-fired.msft.png":::
       Animation Frame **Fired イベントの詳細**  
    :::image-end:::  
    
    > [!NOTE]
    > イベントを選択した後、矢印キーを使用して、イベントの横にあるイベントを選択します。  
    
1.  **app.update イベント**では、紫色のイベントが多く発生します。  紫色の各イベントが広い場合は、それぞれのイベントに赤い三角形が付く可能性があるように見えます。  
1.  紫色のレイアウト イベントのいずれかを **選択** します。  DevTools は、[概要] パネルでイベントに関する詳細 **を提供** します。  実際、強制リフロー \(layout\の別の単語) に関する警告があります。  
    
1.  [概要 **] パネルで** 、[レイアウトの強制] ** の [app.js:71]** リンク **を選択します**。  DevTools は、レイアウトを強制したコード行にアクセスします。  
    
    :::image type="complex" source="../media/evaluate-performance-sources-app-update.msft.png" alt-text="強制レイアウトの原因となるコード行" lightbox="../media/evaluate-performance-sources-app-update.msft.png":::
       強制レイアウトの原因となるコード行  
    :::image-end:::  
    
    > [!NOTE]
    > コードの問題は、各アニメーション フレームで各アイコンのスタイルを変更し、ページ上の各アイコンの位置を照会する点です。  スタイルが変更されたため、ブラウザーは各アイコンの位置が変更されたかどうか分からないので、新しい位置を計算するためにアイコンのレイアウトを変更する必要があります。  <!--  > To learn more, navigate to [Avoid forced synchronous layouts][RenderingAvoidSynchronousLayouts].  -->
    
<!-- todo: add layouts section when available -->

それは学ぶことが多かった。  これで、実行時のパフォーマンスを分析するための基本的なワークフローの基盤が構築されました。  よく出来ました。  

### <a name="bonus-analyze-the-optimized-version"></a>ボーナス: 最適化されたバージョンを分析する  

学習したワークフローとツールを使用して、デモで [**** 最適化] を選択して、最適化されたコードを有効にし、別のパフォーマンス記録を実行し、結果を分析します。  改善されたフレームレートから、メイン セクションのフレーム グラフ内のイベントの**** 削減まで、アプリの最適化されたバージョンでは作業が大幅に少なく、パフォーマンスが向上します。  

> [!NOTE]
> 最適化されたバージョンでさえ、すべてのアイコンのプロパティを操作します `top` 。  より良い方法は、合成にのみ影響を与えるプロパティに固執する方法です。  <!--  > For more information, navigate to [Use transform and opacity changes for animations][RenderingCompositor].  -->  

<!--todo: add rendering section when available -->

## <a name="next-steps"></a>次の手順

<!--The foundation for understanding performance is the RAIL model.  The RAIL model teaches you the performance metrics that are most important to your users.  
To learn more, navigate to [Measure Performance With The RAIL Model][RAIL].  -->  

パフォーマンス ツールの使い心地を **向上するために** 、プラクティスは完璧です。  ページのプロファイリングと結果の分析を試してみてください。  結果について質問がある場合は、[フィードバックの送信]**** アイコンを使用し `Alt` + `Shift` + `I` 、[\(Windows, Linux\] を選択 `Option` + `Shift` + `I` )、\(macOS\)を選択するか[、DevTools][TwitterEdgeDevtools]チームをつぶやきます。  可能であれば、再現可能なページへのスクリーンショットまたはリンクを含める。  

:::image type="complex" source="../media/evaluate-performance-feedback-icon.msft.png" alt-text="Microsoft Edge DevTools の **Feedback** アイコン" lightbox="../media/evaluate-performance-feedback-icon.msft.png":::
   Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン  
:::image-end:::  

<!-- To really become an expert in runtime performance, you must learn how the browser translates HTML, CSS, and JS into pixels on a screen.  The best place to start is the [Rendering Performance Overview][RenderingPerformance].  [The Anatomy Of A Frame][FrameAnatomy] dives into even more detail.  -->  

最後に、実行時のパフォーマンスを向上させる多くの方法があります。  この記事では、特定のアニメーションのボトルネックに焦点を当て、パフォーマンス パネルを中心にツアーを行いましたが、発生する可能性がある多くのボトルネックの 1 つのみです。  <!--  The rest of the Rendering Performance series has a lot of good tips for improving various aspects of runtime performance, such as:  -->

<!--
*   [Optimizing JS Execution][RenderingOptimizeJS]  
*   [Reduce The Scope And Complexity Of Style Calculations][RenderingReduceScope]  
*   [Avoid Large, Complex Layouts And Layout Thrashing][RenderingAvoidThrashing]  
*   [Simplify Paint Complexity And Reduce Paint Areas][RenderingSimplifyPaint]  
*   [Stick To Compositor-Only Properties And Manage Layer Count][RenderingManageLayers]  
*   [Debounce Your Input Handlers][RenderingDebounceInputs]  
-->

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->

[DevtoolsCustomizePlacement]: ../customize/placement.md "Microsoft Edge DevTools の配置を変更する (Undock、Dock to Bottom、Dock to Left)"  
[DevtoolsSpeedGetStarted]: ../speed/get-started.md "Microsoft Edge DevTools を使用して Web サイトの速度を最適化する"  

[TwitterEdgeDevtools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "EdgeDevTools - ツイートを投稿|Twitter"  

[MDNWebRequestAnimationFrame]: https://developer.mozilla.org/docs/Web/API/window/requestAnimationFrame "Window.requestAnimationFrame\(\) |MDN"  

<!--[InPrivate]: https://support.microsoft.com/help/4026200/microsoft-edge-browse-inprivate "Browse InPrivate in Microsoft Edge"  -->

<!--[FrameAnatomy]: https://aerotwist.com/blog/the-anatomy-of-a-frame  -->  

<!--[RAIL]: /web/fundamentals/performance/rail  -->  
<!--[RenderingAvoidSynchronousLayouts]: /web/fundamentals/performance/rendering/avoid-large-complex-layouts-and-layout-thrashing#avoid_forced_synchronous_layouts  -->  
<!--[RenderingAvoidThrashing]: /web/fundamentals/performance/rendering/avoid-large-complex-layouts-and-layout-thrashing  -->  
<!--[RenderingCompositor]: /web/fundamentals/performance/rendering/stick-to-compositor-only-properties-and-manage-layer-count#use_transform_and_opacity_changes_for_animations  -->  
<!--[RenderingDebounceInputs]: /web/fundamentals/performance/rendering/debounce-your-input-handlers  -->
<!--[RenderingManageLayers]: /web/fundamentals/performance/rendering/stick-to-compositor-only-properties-and-manage-layer-count  -->  
<!--[RenderingOptimizeJS]: /web/fundamentals/performance/rendering/optimize-javascript-execution  -->  
<!--[RenderingPerformance]: /web/fundamentals/performance/rendering  -->  
<!--[RenderingReduceScope]: /web/fundamentals/performance/rendering/reduce-the-scope-and-complexity-of-style-calculations  -->  
<!--[RenderingSimplifyPaint]: /web/fundamentals/performance/rendering/simplify-paint-complexity-and-reduce-paint-areas  -->  

<!--[StackOverflowAlphabetBrowserDevtools]: https://stackoverflow.com/questions/ask?tags=alphabet-browser-devtools "Alphabet Browser - Stack Overflow"  -->  

> [!NOTE]
> このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
