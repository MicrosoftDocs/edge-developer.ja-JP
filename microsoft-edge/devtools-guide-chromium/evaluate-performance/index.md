---
description: Microsoft Edge DevTools で実行時のパフォーマンスを評価する方法について説明します。
title: 実行時のパフォーマンスの分析を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 65351f3846ed76ef8a27dbff2cfb08c497282d15
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992947"
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

# 実行時のパフォーマンスの分析を開始する  

> [!NOTE]
> ページの読み込みを高速化する方法については、「 [Web サイトの速度を最適化][DevtoolsSpeedGetStarted]する」を参照してください。  

実行時のパフォーマンスは、読み込みとは異なり、ページが実行されている場合の実行方法です。  次のチュートリアルでは、Microsoft Edge DevTools パフォーマンスパネルを使って実行時のパフォーマンスを分析する方法について説明します。  このチュートリアルで学習するスキル **は、ページ** の応答、アニメーション、およびアイドルフェーズを分析するのに役立ちます。  

<!--todo: add rail link when section is ready -->  

## 使ってみる  

次のチュートリアルでは、ライブページで DevTools を開き、[ **パフォーマンス** ] パネルを使用して、ページ上のパフォーマンスのボトルネックを見つけます。  

1.  **InPrivate モード**で Microsoft Edge を開きます。  InPrivate モードでは、Microsoft Edge がクリーンな状態で実行されます。  たとえば、多くの拡張機能がインストールされている場合は、拡張機能によってパフォーマンスの測定値にノイズが発生する可能性があります。  
    
    <!--TODO: replace section when updated for new Edge  -->
    
1.  InPrivate ウィンドウに次のページを読み込みます。  このページは、プロファイルを作成しようとしているデモです。  ページには、上下に移動する小さなアイコンが表示されます。  
    
    ```https
    https://microsoft-edge-chromium-devtools.glitch.me/sluggish/
    ```  
    
1.  `Control` + `Shift` + `I` Devtools を開くには、\ (Windows \) または `Command` + `Option` + `I` \ (macOS \) を選択します。  
    
    :::image type="complex" source="../media/evaluate-performance-get-started-side-by-side.msft.png" alt-text="左側のデモと、右側の DevTools" lightbox="../media/evaluate-performance-get-started-side-by-side.msft.png":::
       左側のデモと、右側の DevTools  
    :::image-end:::  
    
    > [!NOTE]
    > その他の機能については、「DevTools [」は別のウィンドウにドッキング][DevtoolsCustomizePlacement] 解除され、内容に集中しやすくなっています。  
    
### モバイル CPU のシミュレーション  

モバイルデバイスは、デスクトップとノート pc よりも CPU の消費電力が非常に少なくなっています。  ページをプロファイルするたびに、CPU 調整を使って、ページがモバイルデバイスでどのように動作するかをシミュレートします。  

1.  DevTools で、[ **パフォーマンス** ] タブを選択します。  
1.  [ **スクリーンショット** ] チェックボックスがオンになっていることを確認します。  
1.  [ **キャプチャの設定** ] を選びます。Capture 設定] [ImageCaptureSettingsIcon] \)。  DevTools は、パフォーマンス指標のキャプチャに関連する設定を明らかにします。  
1.  **CPU**の場合は、[ **4 倍速減速**] を選びます。  DevTools では、CPU が通常より4倍遅くなるように CPU を調整します。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-capture-settings.msft.png" alt-text="CPU 調整" lightbox="../media/evaluate-performance-performance-capture-settings.msft.png":::
       CPU 調整  
    :::image-end:::  
    
    > [!NOTE]
    > 他のページをテストする場合各ページがローエンドのモバイルデバイスで適切に動作することを確認したい場合は、CPU の調整を **6x の速度**に設定します。  デモは、6x の速度では適切に動作しないため、説明目的のために4倍速の遅延を使います。  
    
### デモを設定する  

Web サイトのすべてのリーダーで一貫して動作するランタイムパフォーマンスのデモを作成することは困難です。  以下のセクションでは、特定の設定に関係なく、デモをカスタマイズして、エクスペリエンスがスクリーンショットと説明と比較的一貫していることを確認できます。

1.  青いアイコンが以前よりも著しく遅くなるまで、[ **10 を追加** ] ボタンを選択します。  ハイエンドのコンピュータでは、約20回選択できます。  
1.  [ **最適化**] を選びます。  青いアイコンが速く、スムーズに移動します。  
    
    > [!NOTE]
    > 最適化されたバージョンと最適化されていないバージョンの違いをより詳しく表示するには、[ **10 を減算** ] ボタンを数回選択して、もう一度やり直してください。  
    > 追加した青色のアイコンが多すぎる場合は、CPU を最大にすることができます。2つのバージョンの結果には、大きな違いが表示されないことがあります。  
    
1.  [ **最適化の取り消し**] を選びます。  青いアイコンは遅くなり、さらに sluggishness が増えます。  
    
### 実行時のパフォーマンスを記録する  

最適化されたバージョンのページを実行すると、青色のアイコンが速く移動します。  それはどうしてですか。  どちらのバージョンでも、同じ時間の間隔でアイコンを移動することが想定されています。  最適化されていないバージョンのパフォーマンスのボトルネックを検出する方法については、パフォーマンスパネルで記録しておきます。  

1.  DevTools で、[ **Record** ] (! [Record] [ImageRecordIcon] \)。  DevTools は、ページが実行されたときにパフォーマンスのメトリックをキャプチャします。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-profiling.msft.png" alt-text="ページのプロファイル" lightbox="../media/evaluate-performance-performance-profiling.msft.png":::
       ページのプロファイル  
    :::image-end:::  
    
1.  数秒待ってください。  
1.  [ **停止**] を選びます。  DevTools は記録を停止し、データを処理して、パフォーマンスパネルに結果を表示します。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-capture-results.msft.png" alt-text="プロファイルの結果" lightbox="../media/evaluate-performance-performance-capture-results.msft.png":::
       プロファイルの結果  
    :::image-end:::  
    
これは、データ量が圧倒的であるということです。  このプロセスについては、すぐに理解してください。  

## 結果を分析する  

ページのパフォーマンスを記録したら、ページのパフォーマンスの品質を測定し、任意の原因を見つけます。  

### 1秒あたりのフレーム数の分析  

アニメーションのパフォーマンスを測定するための主な指標は、1秒あたりのフレーム数 (FPS) です。  アニメーションが 60 FPS で実行されている場合は、ユーザーが満足しています。  

1.  **FPS**グラフを確認します。  **FPS**の上に赤色のバーが表示されている場合は、ユーザーエクスペリエンスが損なわれる可能性が低いため、フレームレートが低下していることを意味します。  一般に、緑色のバーが大きくなるほど、FPS は高くなります。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-fps-chart.msft.png" alt-text="FPS グラフ" lightbox="../media/evaluate-performance-performance-fps-chart.msft.png":::
       **FPS**グラフ  
    :::image-end:::  
    
1.  **FPS**グラフの下には、 **CPU**グラフが表示されます。  **CPU**グラフの色は、[パフォーマンス] パネルの下部にある [**概要**] タブの色に対応しています。  **Cpu**グラフが色がいっぱいになっているということは、記録中に cpu が最大化されていたことを意味します。  長期間にわたって CPU が不足している場合は、作業を軽減する方法を見つけるための手掛かりとなります。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-cpu-chart.msft.png" alt-text="[CPU グラフ] と [概要] タブ" lightbox="../media/evaluate-performance-performance-cpu-chart.msft.png":::
       [ **CPU** グラフ] と [ **概要** ] タブ  
    :::image-end:::  
    
1.  **FPS**、 **CPU**、または**ネット**チャートをポイントします。  [DevTools] は、現時点でのページのスクリーンショットを示します。  マウスを左または右に移動して、記録を再生します。  この操作はスクラブとして参照され、アニメーションの進行状況を手動で分析するのに役立ちます。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-screenshot-hover.msft.png" alt-text="記録の2500ms マークの周りのページのスクリーンショットを表示する" lightbox="../media/evaluate-performance-performance-screenshot-hover.msft.png":::
       記録の2500ms マークの周りのページのスクリーンショットを表示する  
    :::image-end:::  
    
1.  [ **フレーム** ] セクションで、緑色の四角形のいずれかにマウスポインターを置きます。  DevTools には、特定のフレームの FPS が表示されます。  各フレームは、60 FPS のターゲットよりも適切な場合があります。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-frame-hover.msft.png" alt-text="フレーム上にカーソルを移動する" lightbox="../media/evaluate-performance-performance-frame-hover.msft.png":::
       フレーム上にカーソルを移動する  
    :::image-end:::  
    
もちろん、ページが正常に動作していないことを確認する必要があります。  実際のシナリオでは、このことが明確ではない可能性があるため、すべてのツールを使って測定を行うと便利です。  

#### ボーナス: FPS メーターを開く  

もう1つの便利なツールは FPS メーターで、ページの実行時に FPS に対してリアルタイムの推定値が提供されます。  

1.  [ `Control` + `Shift` + `P` \ (Windows \)] または [ `Command` + `Shift` + `P` \ (macOS \)] を選択して、**コマンドメニュー**を開きます。  
1.  `Rendering`**コマンドメニュー**で入力を開始し、[**レンダリングの表示**] を選択します。  
1.  [ **レンダリング** ] タブで、[ **FPS メーター**] を有効にします。  新しいオーバーレイがビューポートの右上に表示されます。  
    
    :::image type="complex" source="../media/evaluate-performance-fps-meter-overlay.msft.png" alt-text="FPS メーター" lightbox="../media/evaluate-performance-fps-meter-overlay.msft.png":::
       **FPS メーター**  
        :::image-end:::  
    
1.  **FPS メーター**を無効にし、を選択して [ `Escape` **レンダリング**] タブを閉じます。 このチュートリアルでは、 **FPS メーター**は使用していません。  
    
### ボトルネックを見つける  

アニメーションが適切に実行されていないことを測定して確認した後、次の手順は "理由" という質問に答えます。  

1.  イベントが選択されていない場合、[ **概要** ] タブにアクティビティの内訳が表示されます。  このページでは、ほとんどの時間のレンダリングに費やされています。  パフォーマンスは、作業を軽減することを目的としているため、目標は、作業のレンダリングに費やされる時間を減らすことです。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-summary-tab.msft.png" alt-text="[概要] タブ" lightbox="../media/evaluate-performance-performance-summary-tab.msft.png":::
       [ **概要** ] タブ  
    :::image-end:::  
    
1.  **メイン**セクションを展開する。  DevTools には、時間の経過に伴うメインスレッドでのアクティビティを示す炎のグラフが表示されます。  X 軸は、時間の経過に伴う記録を表します。  各バーはイベントを表します。  広いバーは、イベントが長くなったことを意味します。  Y 軸は、呼び出しスタックを表します。  互いに重なり合っているイベントが表示される場合は、上位のイベントによって下位のイベントが発生したことを意味します。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-main.msft.png" alt-text="メインセクション" lightbox="../media/evaluate-performance-performance-main.msft.png":::
       **メイン**セクション  
    :::image-end:::  
    
1.  レコーディングには大量のデータが含まれています。  1つのイベントにズームするには[ **概要**] の上にカーソルを置くと、 **FPS**、 **CPU**、および **ネット** チャートが含まれているセクションになります。  **メイン**セクションと [**概要**] タブには、レコーディングの選択した部分に関する情報のみが表示されます。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="イベントを拡大する" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
       イベントを拡大する  
    :::image-end:::  
    
    > [!NOTE]
    > ズームするもう1つの方法として、 **メイン** セクションにフォーカスを移動し、背景またはイベントを選択して、、、、またはを選択し `W` `A` `S` `D` ます。  
    
    1.  **アニメーションフレームの発生**イベントの右上にある赤い三角形にフォーカスを設定します。  赤い三角形が表示されると、イベントに関連する問題が発生している可能性があることを示す警告が表示されます。  
    
    > [!NOTE]
    > [ `requestAnimationFrame()` コールバック][MDNWebRequestAnimationFrame]が実行されるたびに、**アニメーションフレームの発生**イベントが発生します。  
    
1.  [ **Animation Frame** ] イベントを選びます。  [ **概要** ] タブに、そのイベントに関する情報が表示されるようになりました。  [ **公開** ] リンクに注目してください。  このツールを選ぶと、 **アニメーションフレームの発生** イベントを開始したイベントが強調表示されます。  また、 **app.js:95** のリンクに注目してください。  選択すると、ソースコードの該当する行が表示されます。
    
    :::image type="complex" source="../media/evaluate-performance-performance-animation-frame-fired.msft.png" alt-text="アニメーションフレームの発生イベントに関する詳細情報" lightbox="../media/evaluate-performance-performance-animation-frame-fired.msft.png":::
       **アニメーションフレームの発生**イベントに関する詳細情報  
    :::image-end:::  
    
    > [!NOTE]
    > イベントを選択した後、方向キーを使用してイベントの隣にあるイベントを選択します。  
    
1.  [ **更新** ] イベントには、紫色のイベントがいくつかあります。  紫色の各イベントの幅が広くなっている場合は、それぞれに赤い三角形が表示されているように見えます。  
1.  紫色の **レイアウト** イベントのいずれかを選択します。  DevTools は、[ **概要** ] タブのイベントに関する詳細情報を提供します。 実際には、強制的な折り返しの折り返し (別の word レイアウト \) に関する警告が表示されます。  
    
1.  [**概要**] タブで、[**強制的にレイアウト**] の [ **app.js:71** ] リンクを選択します。  DevTools は、レイアウトを強制したコード行に移動します。  
    
    :::image type="complex" source="../media/evaluate-performance-sources-app-update.msft.png" alt-text="強制レイアウトの原因となったコード行" lightbox="../media/evaluate-performance-sources-app-update.msft.png":::
       強制レイアウトの原因となったコード行  
    :::image-end:::  
    
    > [!NOTE]
    > コードに問題がある場合は、各アニメーションフレームで、各アイコンのスタイルを変更してから、ページ上の各アイコンの位置を照会します。  スタイルが変更されているため、各アイコンの位置が変更されたかどうかはブラウザーで認識されないため、新しい位置を計算するにはアイコンを再レイアウトする必要があります。  <!--  > See [Avoid forced synchronous layouts][RenderingAvoidSynchronousLayouts] to learn more.  -->
    
<!-- todo: add layouts section when available -->

もっと学ぶことができました。  これで、実行時のパフォーマンスを分析するための基本的なワークフローの堅固な基盤ができます。  よく出来ました。  

### ボーナス: 最適化されたバージョンを分析する  

学習したワークフローとツールを使用して、最適化されたコードを有効にし、別のパフォーマンスの記録を取ることで、結果を分析するデモで [ **最適化** ] を選択します。  向上したフレームレートから、 **メイン** セクションの炎グラフのイベントの減少まで、アプリの最適化されたバージョンの動作が大幅に低下し、パフォーマンスが向上することを確認できます。  

> [!NOTE]
> 最適化されたバージョンでも、 `top` すべてのアイコンのプロパティを操作するため、最適な方法ではありません。  さらに良い方法は、合成にのみ適用されるプロパティにすることです。  <!--  > See [Use transform and opacity changes for animations][RenderingCompositor] for more information.  -->  

<!--todo: add rendering section when available -->

## 次のステップ

<!--The foundation for understanding performance is the RAIL model.  The RAIL model teaches you the performance metrics that are most important to your users.  
See [Measure Performance With The RAIL Model][RAIL] to learn more.  -->  

[パフォーマンス] パネルを使いやすくするために、練習は完璧です。  ページのプロファイリングを行って、結果を分析してみてください。  結果についての質問がある場合は、[**フィードバックの送信**] アイコンを使用して、[ `Alt` + `Shift` + `I` \ (Windows \)]、[ `Option` + `Shift` + `I` \ (macOS \)]、または [ [devtools] チームにツイート][TwitterEdgeDevtools]します。  可能であれば、スクリーンショットまたは再現可能なページへのリンクを含めます。  

:::image type="complex" source="../media/evaluate-performance-feedback-icon.msft.png" alt-text="Microsoft Edge DevTools の * * フィードバック * * アイコン" lightbox="../media/evaluate-performance-feedback-icon.msft.png":::
   Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン  
:::image-end:::  

<!-- To really become an expert in runtime performance, you must learn how the browser translates HTML, CSS, and JS into pixels on a screen.  The best place to start is the [Rendering Performance Overview][RenderingPerformance].  [The Anatomy Of A Frame][FrameAnatomy] dives into even more detail.  -->  

最後に、実行時のパフォーマンスを向上させるためのさまざまな方法があります。  この記事では、特定のアニメーションのボトルネックに焦点を絞って、パフォーマンスパネルの焦点を絞ったツアーを提供していますが、これは、発生する可能性のある多数のボトルネックの1つにすぎません。  <!--  The rest of the Rendering Performance series has a lot of good tips for improving various aspects of runtime performance, such as:  -->

<!--
*   [Optimizing JS Execution][RenderingOptimizeJS]  
*   [Reduce The Scope And Complexity Of Style Calculations][RenderingReduceScope]  
*   [Avoid Large, Complex Layouts And Layout Thrashing][RenderingAvoidThrashing]  
*   [Simplify Paint Complexity And Reduce Paint Areas][RenderingSimplifyPaint]  
*   [Stick To Compositor-Only Properties And Manage Layer Count][RenderingManageLayers]  
*   [Debounce Your Input Handlers][RenderingDebounceInputs]  
-->

<!-- links -->

[DevtoolsCustomizePlacement]: ../customize/placement.md "Microsoft Edge DevTools の配置を変更する (ドッキング解除、下へのドッキング、左へのドッキング)"  
[DevtoolsSpeedGetStarted]: ../speed/get-started.md "Microsoft Edge DevTools を使用して Web サイトの速度を最適化する"  

[TwitterEdgeDevtools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "EdgeDevTools-ツイートの投稿 |Twitter"  

[MDNWebRequestAnimationFrame]: https://developer.mozilla.org/docs/Web/API/window/requestAnimationFrame "Window./アニメーションフレーム \ (\) |MDN"  

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
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
