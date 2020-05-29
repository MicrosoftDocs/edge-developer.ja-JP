---
title: 実行時のパフォーマンスの分析を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: bff2d2fb0ff8424303289183ca8c5935ef477381
ms.sourcegitcommit: 50991a04c18283a8890ae33fcc3491c0476c7684
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611742"
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
> ページを読みやすくする方法については、「 [Web サイトの速度を最適化][DevtoolsSpeedGetStarted]する」を参照してください。  

実行時のパフォーマンスは、読み込みとは異なり、ページが実行されている場合の実行方法です。  このチュートリアルでは、Microsoft Edge DevTools のパフォーマンスパネルを使って実行時のパフォーマンスを分析する方法について説明します。  このチュートリアルで学習するスキル**は、ページ**の応答、アニメーション、およびアイドルフェーズを分析するのに役立ちます。  

<!--todo: add rail link when section is ready -->  

## 使ってみる   

このチュートリアルでは、ライブページで DevTools を開き、[パフォーマンス] パネルを使用して、ページ上のパフォーマンスのボトルネックを見つけます。  

1.  **InPrivate モード**で Microsoft Edge を開きます。  InPrivate モードでは、Microsoft Edge がクリーンな状態で実行されます。  たとえば、多くの拡張機能がインストールされている場合は、これらの拡張機能によってパフォーマンスの測定値にノイズが発生する可能性があります。  
    
    <!--TODO: replace section when updated for new Edge  -->
    
1.  InPrivate ウィンドウに次のページを読み込みます。  このデモでは、プロファイルを作成しています。  ページには、上下に移動する小さなアイコンが表示されます。  
    
    ```https
    https://microsoft-edge-chromium-devtools.glitch.me/jank/
    ```  
    
1.  [ `Control` + `Shift` + `I` \ (Windows \)] または [ `Command` + `Option` + `I` \ (macOS \)] を押して、devtools を開きます。  
    
    > ###### 図 1  
    > 左側のデモと、右側の DevTools  
    > ![左側のデモと、右側の DevTools][ImageGetStarted]  
    
    > [!NOTE]
    > このスクリーンショットの残りの部分については、「DevTools [」が別のウィンドウにドッキング][DevtoolsCustomizePlacement]されていないため、内容をより詳しく確認できます。  
    
### モバイル CPU のシミュレーション  

モバイルデバイスは、デスクトップとノート pc よりも CPU の消費電力が非常に少なくなっています。  ページをプロファイルするたびに、CPU 調整を使って、ページがモバイルデバイスでどのように動作するかをシミュレートします。  

1.  DevTools で、[**パフォーマンス**] タブをクリックします。  
1.  [**スクリーンショット**] チェックボックスがオンになっていることを確認します。  
1.  「**キャプチャ設定**」「 ![ キャプチャ設定」をクリックし ][ImageCaptureSettingsIcon] ます。  DevTools は、パフォーマンス指標のキャプチャに関連する設定を明らかにします。  
1.  **CPU**の場合は、[ **4 倍速減速**] を選びます。  DevTools では、CPU が通常より4倍遅くなるように CPU を調整します。  
    
    > ###### 図 2  
    > CPU 調整  
    > ![CPU 調整][ImageCPUThrottling]  
    
    > [!NOTE]
    > 他のページをテストする場合、ローエンドのモバイルデバイスで正常に動作することを確認するには、CPU の調整を**6x の遅延**に設定します。  このデモは、6x の速度ではうまく機能しません。そのため、説明のために4倍速の速度を使います。  
    
### デモを設定する  

この web サイトのすべてのリーダーで一貫して動作するランタイムパフォーマンスデモを作成するのは困難です。  このセクションでは、特定のセットアップに関係なく、デモをカスタマイズして、このチュートリアルで説明しているスクリーンショットと説明との一貫性を保つことができます。

1.  青色のアイコンが以前よりも著しく遅くなるまで、[ **10 を追加**] をクリックしたままにします。  ハイエンドのコンピューターでは、20回のクリックがかかることがあります。  
1.  [**最適化**] をクリックします。  青いアイコンが速く、スムーズに移動します。  

    > [!NOTE]
    > 最適化されたバージョンと最適化されていないバージョンの違いがはっきりしない場合は、[ **10 回減算**] をクリックして、もう一度試してみてください。  
    > 追加した青色のアイコンが多すぎる場合は、CPU を最大にするだけで、2つのバージョンの結果に大きな違いが表示されることはありません。  

1.  [**最適化の取り消し**] をクリックします。  青いアイコンは遅くなり、さらに jank が増えます。  

### 実行時のパフォーマンスを記録する   

最適化されたバージョンのページを実行すると、青色のアイコンが速く移動します。  
それはどうしてですか。  どちらのバージョンでも、同じ時間の間隔でアイコンを移動することが想定されています。  最適化されていないバージョンのパフォーマンスのボトルネックを検出する方法については、パフォーマンスパネルで記録しておきます。  

1.  DevTools で、[**レコードの記録**] をクリックし ![ ][ImageRecordIcon] ます。  
    DevTools は、ページが実行されたときにパフォーマンスのメトリックをキャプチャします。  
    
    > ###### 図 3 
    > ページのプロファイリング  
    > ![ページのプロファイリング][ImagePageProfiling]  
    
1.  数秒待ってください。  
1.  [**停止**] をクリックします。  DevTools は記録を停止し、データを処理して、パフォーマンスパネルに結果を表示します。  
    
    > ###### 図 4  
    > プロファイルの結果  
    > ![プロファイルの結果][ImageProfileResults]  

これは、データ量が圧倒的であるということです。  ご安心ください。すぐに、すべての意味がわかりやすくなります。  

## 結果を分析する   

ページのパフォーマンスの記録が完了したら、ページのパフォーマンスの低下を測定して、何かの原因を見つけることができます。  

### 1秒あたりのフレーム数の分析  

アニメーションのパフォーマンスを測定するための主な指標は、1秒あたりのフレーム数 (FPS) です。  アニメーションが 60 FPS で実行されている場合は、ユーザーが満足しています。  

1.  **FPS**グラフを確認します。  **FPS**の上に赤色のバーが表示されている場合は、ユーザーエクスペリエンスが損なわれる可能性が低いため、フレームレートが低下していることを意味します。  一般に、緑色のバーが大きくなるほど、FPS は高くなります。  
    
    > ###### 図 5  
    > FPS グラフ  
    > ![FPS グラフ][ImageFPSChart]  

1.  **FPS**グラフの下には、 **CPU**グラフが表示されます。  **CPU**グラフの色は、[パフォーマンス] パネルの下部にある [**概要**] タブの色に対応しています。  **Cpu**グラフが色がいっぱいになっているということは、記録中に cpu が最大化されていたことを意味します。  長期間にわたって CPU が不足している場合は、作業を軽減する方法を見つけるための手掛かりとなります。  
    
    > ###### 図 6  
    > [CPU グラフ] と [概要] タブ  
    > ![[CPU グラフ] と [概要] タブ][ImageCPUSummary]  

1.  **FPS**、 **CPU**、または**ネット**チャートの上にマウスポインターを置きます。  [DevTools] は、現時点でのページのスクリーンショットを示します。  マウスを左または右に移動して、記録を再生します。  これはスクラブと呼ばれ、アニメーションの進行状況を手動で分析するのに役立ちます。  
    
    > ###### 図 7  
    > 記録の2500ms マークの周りのページのスクリーンショットを表示する  
    > ![記録の2500ms マークの周りのページのスクリーンショットを表示する][ImageViewingScreenshot]  

1.  [**フレーム**] セクションで、緑色の四角形のいずれかにマウスポインターを置きます。  DevTools には、特定のフレームの FPS が表示されます。  各フレームは、60 FPS のターゲットよりも適切な場合があります。  
    
    > ###### 図 8  
    > フレーム上のマウスポインター  
    > ![フレーム上のマウスポインター][ImageFrameHover]  

もちろん、このデモでは、ページが適切に動作していないことがわかります。  実際のシナリオでは、このことが明確ではない場合もあります。そのため、これらのすべてのツールを使って測定を行うと便利です。  

#### ボーナス: FPS メーターを開く  

もう1つの便利なツールは FPS メーターで、ページの実行時に FPS に対してリアルタイムの推定値が提供されます。  

1.  `Control` + `Shift` + `P` コマンドメニューを開くには、\ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押します。  
1.  `Rendering`コマンドメニューで入力を開始し、[**レンダリングの表示**] を選択します。  
1.  [**レンダリング**] タブで、[ **FPS メーター**] を有効にします。  新しいオーバーレイがビューポートの右上に表示されます。  
    
    > ###### 図 9  
    > FPS メーター  
    > ![FPS メーター][ImageFPSMeter]  

1.  **FPS メーター**を無効にし、を押して [ `Escape` **レンダリング**] タブを閉じます。 このチュートリアルでは使用しません。  

### ボトルネックを見つける  

これで、アニメーションが正常に動作していないことを測定し、確認しました。次に、その理由について説明します。  

1.  [概要] タブに注目してください。 イベントが選択されていない場合、このタブにはアクティビティの内訳が表示されます。  このページでは、ほとんどの時間のレンダリングに費やされています。  パフォーマンスは、作業を軽減することを目的としているため、目標は、作業のレンダリングに費やされる時間を減らすことです。  
    
    > ###### 図 10  
    > [概要] タブ  
    > ![[概要] タブ][ImageSummaryTab]  

1.  **メイン**セクションを展開する。  DevTools には、時間の経過に伴うメインスレッドでのアクティビティを示す炎のグラフが表示されます。  X 軸は、時間の経過に伴う記録を表します。  各バーはイベントを表します。  広いバーは、イベントが長くなったことを意味します。  Y 軸は、呼び出しスタックを表します。  互いに重なり合っているイベントが表示される場合は、上位のイベントによって下位のイベントが発生したことを意味します。  
    
    > ##### 図 11  
    > メインセクション  
    > ![メインセクション][ImageMainSection]  

1.  レコーディングには大量のデータが含まれています。  1つのイベントを拡大表示するには、[**概要**] の上にマウスポインターを合わせてドラッグします。これは、 **FPS**、 **CPU**、および**NET**グラフを含むセクションです。  **メイン**セクションと [**概要**] タブには、レコーディングの選択した部分に関する情報のみが表示されます。  
    
    > ###### 図 12  
    > 1つのイベントを拡大する  
    > ![イベントを拡大する][ImageZoomedAnimation]  
    
    > [!NOTE]
    > ズームするもう1つの方法は**Main** 、背景をクリックするかイベントを選択して、、、 `W` `A` `S` 、およびキーを押して、メインセクションにフォーカスを移動することです `D` 。  
    
    1.  **アニメーションフレームの発生**イベントの右上にある赤い三角形に注目してください。  赤い三角形が表示された場合は、このイベントに関連する問題が発生している可能性があることを示す警告です。  
    
    > [!NOTE]
    > [ `requestAnimationFrame()` コールバック][MDNWebRequestAnimationFrame]が実行されるたびに、**アニメーションフレームの発生**イベントが発生します。  
    
1.  [ **Animation Frame** ] イベントをクリックします。  [**概要**] タブに、そのイベントに関する情報が表示されるようになりました。  [**公開**] リンクに注目してください。  このボタンをクリックすると、DevTools によって、**アニメーションフレームの発生**イベントを開始したイベントが強調表示されます。  また、 **「.js:95** 」というリンクも確認してください。  これをクリックすると、ソースコード内の関連する行にジャンプします。
    
    > ##### 図 13  
    > アニメーションフレームの発生イベントに関する詳細情報  
    > ![アニメーションフレームの発生イベントに関する詳細情報][ImageAnimationFrameFired]  
    
    > [!NOTE]
    > イベントを選択した後、方向キーを使用してイベントの隣にあるイベントを選択します。  

1.  [**更新**] イベントには、紫色のイベントがいくつかあります。  幅が広くなっている場合は、それぞれに赤い三角形が表示されているように見えます。  ここで紫色の**レイアウト**イベントを1つクリックします。  DevTools は、[**概要**] タブのイベントに関する詳細情報を提供します。 実際には、強制的な折り返しの折り返し (別の word レイアウト \) に関する警告が表示されます。  

1.  [**概要**] タブで、[**レイアウトの強制**] の下の [ **.js:71** ] リンクをクリックします。  DevTools は、レイアウトを強制したコード行に移動します。  
    
    > ##### 図 14  
    > 強制レイアウトの原因となったコード行  
    > ![強制レイアウトの原因となったコード行][ImageForcedLayoutSRC]  
    
    > [!NOTE]
    > このコードの問題は、アニメーションフレームごとに、各アイコンのスタイルが変更され、ページ上の各アイコンの位置が照会されることです。  スタイルが変更されているため、各アイコンの位置が変更されたかどうかはブラウザーでは認識されないため、アイコンの位置を計算するには、アイコンのレイアウトを再設定する必要があります。  <!--  See [Avoid forced synchronous layouts][RenderingAvoidSynchronousLayouts] to learn more.  -->

<!-- todo: add layouts section when available -->

Phew!  これは非常に多くのユーザーを対象としていますが、実行時のパフォーマンスを分析するための基本的なワークフローの基礎として確固としています。  よく出来ました。  

### ボーナス: 最適化されたバージョンを分析する  

学習したワークフローとツールを使用して、最適化されたコードを有効にして、別のパフォーマンスの記録を取ることで、結果を分析するデモの [**最適化**] をクリックします。  向上したフレームレートから、**メイン**セクションの炎グラフのイベントの減少まで、最適化されたバージョンのアプリの動作が大幅に低下することを確認できます。その結果、パフォーマンスが向上します。  

> [!NOTE]
> この "最適化された" バージョンでも、 `top` 各アイコンのプロパティを操作しているので、それほど便利ではありません。  さらに良い方法は、合成にのみ適用されるプロパティにすることです。  
<!--  > See [Use transform and opacity changes for animations][RenderingCompositor] for more information.  -->  

<!--todo: add rendering section when available -->

## 次のステップ

<!--The foundation for understanding performance is the RAIL model.  This model teaches you the performance metrics that are most important to your users.  
See [Measure Performance With The RAIL Model][RAIL] to learn more.  -->  

[パフォーマンス] パネルを使いやすくするために、練習は完璧です。  独自のページをプロファイリングして、結果を分析してみてください。  結果について質問がある場合は、[**フィードバック**] アイコンを使用するか `Alt`  +  `Shift`  +  `I` ( `Option`  +  `Shift`  +  `I` macOS の場合)、または[ツイート][TwitterEdgeDevtools]をクリックしてください。  可能であれば、スクリーンショットまたは再現可能なページへのリンクを含めます。

> ##### 図 15
> Microsoft Edge DevTools の**フィードバック**アイコン  
> ![Microsoft Edge DevTools の * * フィードバック * * アイコン][ImageFeedbackIcon]

<!-- To really master runtime performance, you've got to learn how the browser translates HTML, CSS, and JS into pixels on a screen.  The best place to start is the [Rendering Performance Overview][RenderingPerformance].  [The Anatomy Of A Frame][FrameAnatomy] dives into even more detail.  -->  

最後に、実行時のパフォーマンスを向上させるためのさまざまな方法があります。  このチュートリアルでは、1つの特定のアニメーションのボトルネックに重点を置いて、[パフォーマンス] パネルのフォーカスツアーを提供していますが、発生する可能性のある多数のボトルネックの1つにすぎません。  <!--  The rest of the Rendering Performance series has a lot of good tips for improving various aspects of runtime performance, such as:  -->

<!--
*   [Optimizing JS Execution][RenderingOptimizeJS]  
*   [Reduce The Scope And Complexity Of Style Calculations][RenderingReduceScope]  
*   [Avoid Large, Complex Layouts And Layout Thrashing][RenderingAvoidThrashing]  
*   [Simplify Paint Complexity And Reduce Paint Areas][RenderingSimplifyPaint]  
*   [Stick To Compositor-Only Properties And Manage Layer Count][RenderingManageLayers]  
*   [Debounce Your Input Handlers][RenderingDebounceInputs]  
-->

<!-- image links -->  

[ImageCaptureSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/capture-settings-icon.msft.png  
[ImageRecordIcon]: /microsoft-edge/devtools-guide-chromium/media/record-icon.msft.png  

[ImageGetStarted]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-get-started-side-by-side.msft.png "図 1: 左側のデモと右側の DevTools"  
[ImageCPUThrottling]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-capture-settings.msft.png "図 2: CPU 調整"  
[ImagePageProfiling]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-profiling.msft.png "図 3: ページのプロファイリング"  
[ImageProfileResults]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-capture-results.msft.png "図 4: プロファイルの結果"  
[ImageFPSChart]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-fps-chart.msft.png "図 5: FPS グラフ"  
[ImageCPUSummary]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-cpu-chart.msft.png "図 6: 青色で囲まれた [CPU グラフ] と [概要] タブ"  
[ImageViewingScreenshot]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-screenshot-hover.msft.png "図 7: 記録の2500ms マークの周りのページのスクリーンショットの表示"  
[ImageFrameHover]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-frame-hover.msft.png "図 8: フレーム上のマウスポインター"  
[ImageFPSMeter]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-fps-meter-overlay.msft.png "図 9: FPS メーター"  
[ImageSummaryTab]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-summary-tab.msft.png "図 10: [概要] タブ"  
[ImageMainSection]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-main.msft.png "図 11: メインセクション"  
[ImageZoomedAnimation]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-main-zoomed.msft.png "図 12: 1 つのアニメーションフレームの発生イベントを拡大する"  
[ImageAnimationFrameFired]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-animation-frame-fired.msft.png "図 13: アニメーションフレームの発生イベントに関する詳細情報"  
[ImageForcedLayoutSRC]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-sources-app-update.msft.png "図 14: 強制レイアウトの原因となったコード行"  
[ImageFeedbackIcon]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-feedback-icon.msft.png "図 15: Microsoft Edge DevTools の * * フィードバック * * アイコン"

<!-- links -->

[DevtoolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "Microsoft Edge DevTools の配置を変更する (ドッキング解除、下へのドッキング、左へのドッキング)"  
[DevtoolsSpeedGetStarted]: /microsoft-edge/devtools-guide-chromium/speed/get-started "Microsoft Edge DevTools を使用して Web サイトの速度を最適化する"  

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
> このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
