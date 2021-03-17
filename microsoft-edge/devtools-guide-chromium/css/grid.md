---
description: Microsoft Edge DevTools を使用してページ CSS の CSS を表示および変更する方法について説明します。
title: Microsoft Edge DevTools で CSS グリッドを検査する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 034fbdf82ddba39fc0818bc6f3add8824c6bb3ac
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439262"
---
# <a name="inspect-css-grid"></a>CSS グリッドの検査  

この記事では、Web サイトで CSS グリッドを識別し、カスタマイズ可能なグリッド オーバーレイを使用してグリッド レイアウトの問題をデバッグする方法について説明します。  

この記事の図で使用される例は、次の Web ページから取り上されています。  

*   [フルーツ ボックス][JecFyiDemoCssGridFruit]  
*   [スナック ボックス][JecFyiDemoCssGridSnack]  

## <a name="before-you-begin"></a>始める前に  

CSS Grid は、Web の強力なレイアウト のパラダイムです。  CSS Grid の学習を始めるのに最適な場所であり、多くの機能は [MDN][MdnCssGridLayout] の CSS グリッド レイアウト ガイドです。  

## <a name="discover-css-grids"></a>CSS グリッドの検出  

ページの HTML 要素がページに適用されている場合、その横に [要素] パネルにバッジ `display: grid` `display: inline-grid` `grid` が [表示][DevtoolsGuideChromiumOpen] されます。  

:::image type="complex" source="../media/grid-discover-grid.msft.png" alt-text="グリッドの検出" lightbox="../media/grid-discover-grid.msft.png":::
   グリッドの検出  
:::image-end:::  

バッジを選択して、ページ上のグリッド オーバーレイの表示を切り替える。  オーバーレイは要素の上に表示され、グリッドのようにレイアウトされ、グリッド線とトラックの位置が表示されます。  

:::image type="complex" source="../media/grid-highlight-grid.msft.png" alt-text="トグル グリッド バッジ" lightbox="../media/grid-highlight-grid.msft.png":::
   トグル グリッド バッジ  
:::image-end:::  

[レイアウト] **ウィンドウを開** きます。  グリッドがページに含まれている場合、[レイアウト]**** ウィンドウには、**** グリッドを表示するための多数のオプションを含むグリッド セクションが含まれます。  

:::image type="complex" source="../media/grid-layout-pane.msft.png" alt-text="レイアウト ウィンドウ" lightbox="../media/grid-layout-pane.msft.png":::
   **レイアウト** ウィンドウ  
:::image-end:::  

[ **レイアウト]** ウィンドウの **[グリッド] セクション** には、次の 2 つのサブセクションが含まれます。  

*   オーバーレイ表示設定  
*   グリッド オーバーレイ  

<!--todo: @zoher verify the details for each of the sub-sections.  -->  

## <a name="overlay-display-settings"></a>オーバーレイ表示設定  

オーバーレイ **の表示設定は** 、次の 2 つの部分で構成されます。  

*   ドロップダウン メニューから次のいずれかのオプションを選択します。  
    
    | Line オプション | 詳細 |  
    |:--- |:--- |  
    | **線ラベルを非表示にする** | 各グリッド オーバーレイの線のラベルを非表示にします。 |  
    | **行番号の表示** | 各グリッド オーバーレイ \(default\で選択) の線の番号を表示します。 |  
    | **行名の表示** | 名前が指定されている場合は、各グリッド オーバーレイの線の名前を表示します。 |  
    
*  次のオプションの横にあるチェック ボックスをオンにします。  
    
    | オプション | 詳細 |  
    |:--- |:--- |  
    | **トラックのサイズを表示する**  | トラックのサイズを \(または hide\) で表示します。 |  
    | **エリア名の表示** | 名前が指定されている場合は、エリアの名前を \(または hide\) で表示します。 |  
    | **グリッド線を拡張する** | 各軸に沿ってグリッド寸法の拡張子 \(または hides\) を表示します。  既定では、グリッド線は要素に設定されている要素または `display: grid` CSS セット内 `display: inline-grid` にのみ表示されます。 |  
    
次のセクションでは、オーバーレイ表示の各設定の詳細 **について説明します**。  

### <a name="show-line-numbers"></a>行番号の表示  

既定では、正と負の行番号がグリッド オーバーレイに表示されます。  

グリッド オーバーレイ内の負の数値の詳細については、「CSS Grid を使用した線ベースの [配置」に移動します][MdnLineBasedPlacementCssGrid]。  

:::image type="complex" source="../media/grid-show-line-numbers.msft.png" alt-text="行番号の表示" lightbox="../media/grid-show-line-numbers.msft.png":::
   行番号の表示  
:::image-end:::  

### <a name="hide-line-labels"></a>線ラベルを非表示にする  

[線 **のラベルを非表示にする** ] を選択して、行番号を非表示にします。  

:::image type="complex" source="../media/grid-hide-line-labels.msft.png" alt-text="線ラベルを非表示にする" lightbox="../media/grid-hide-line-labels.msft.png":::
   線ラベルを非表示にする  
:::image-end:::  

### <a name="show-line-names"></a>行名の表示  

グリッド オーバーレイの行名の詳細については、「名前付きグリッド線を使用 [したレイアウト」に移動します][MdnLayoutUsingNamedGridLines]。  

[ **行名の表示]** を選択して、数字の代わりに行名を表示します。  この例では、4 行に名前 `left` `middle1` 、、、 `middle2` および を指定します `right` 。  

<!--In the demo, **orange** element spans from left to right, with `grid-column: left` and `grid-column: right` CSS.  Showing line names makes it easier to visualize the start and end position of the element.  -->  

:::image type="complex" source="../media/grid-show-line-names.msft.png" alt-text="行名の表示" lightbox="../media/grid-show-line-names.msft.png":::
   **行名の表示**  
:::image-end:::  

### <a name="show-track-sizes"></a>トラックのサイズを表示する  

グリッドの **トラック サイズを表示** するには、[トラックサイズを表示する] チェック ボックスをオンにします。  

DevTools は、 `[authored size]` 各 `[computed size]` 行ラベルに表示されます。  

| Size | 詳細 |  
|:--- |:--- |  
| **オーサリングされたサイズ** | stylesheet \(defined\ではない場合は省略) で定義されているサイズ。 |  
| **計算されたサイズ** | 画面の実際のサイズ。 |  

デモでは、列 `snack-box` のサイズは CSS で定義 `grid-template-columns:1fr 2fr;` されます。  したがって、列の行ラベルには、作成サイズと計算サイズの両方が表示されます。  

| トラックのサイズ | オーサリングされたサイズ | 計算されたサイズ |  
|:--- |:--- |:--- |  
| **1fr &#x2022;** **96.66px** | 1fr | 96.66px |  
| **2fr &#x2022;** **193.32px** | 2fr | 193.32px |  

行行ラベルは、スタイルシートで定義されている行サイズが無く、計算されたサイズのみを表示します。  

| トラックのサイズ | オーサリングされたサイズ | 計算されたサイズ |  
|:--- |:--- |:--- |  
| **80px** | &nbsp;| 80px |  
| **80px** | &nbsp;| 80px |  

:::image type="complex" source="../media/grid-show-track-sizes.msft.png" alt-text="トラックのサイズを表示する" lightbox="../media/grid-show-track-sizes.msft.png":::
   **トラックのサイズを表示する**  
:::image-end:::  

### <a name="show-area-names"></a>エリア名の表示  

エリア名を表示するには、[エリア名を表示 **] チェック ボックスをオン** にします。  この例では、グリッドには、上、下**1、** 下 2 の 3 つの******領域があります**。  

:::image type="complex" source="../media/grid-show-area-names.msft.png" alt-text="エリア名の表示" lightbox="../media/grid-show-area-names.msft.png":::
   **エリア名の表示**  
:::image-end:::  

### <a name="extend-grid-lines"></a>グリッド線を拡張する  

[グリッド線 **の拡張]** チェック ボックスをオンにすると、グリッド線を各軸に沿ってビューポートの端まで拡張できます。  

:::image type="complex" source="../media/grid-extend-grid-lines.msft.png" alt-text="グリッド線を拡張する" lightbox="../media/grid-extend-grid-lines.msft.png":::
   **グリッド線を拡張する**  
:::image-end:::  

## <a name="grid-overlays"></a>グリッド オーバーレイ  

[ **グリッド オーバーレイ] セクション** には、ページ上に存在するグリッドの一覧が含まれる。各グリッドには、さまざまなオプションと共に、チェック ボックスが付きます。  

### <a name="enable-overlay-views-of-multiple-grids"></a>複数のグリッドのオーバーレイ ビューを有効にする  

複数のグリッドのオーバーレイ グリッドを表示するには、グリッドの各名前の横にあるチェック ボックスをオンにします。  この例では、それぞれ異なる色で表される 2 つのグリッド オーバーレイが有効になっています。  

*   `main`  
*   `div.snack-box`  
    
:::image type="complex" source="../media/grid-grid-overlays.msft.png" alt-text="複数のグリッドのオーバーレイ ビューを有効にする" lightbox="../media/grid-grid-overlays.msft.png":::
   複数のグリッドのオーバーレイ ビューを有効にする  
:::image-end:::  

### <a name="customize-the-grid-overlay-color"></a>グリッド オーバーレイの色をカスタマイズする  

カラー ピッカーを開き、グリッド オーバーレイの色をカスタマイズするには、グリッド オーバーレイの名前の横にあるボックスを選択します。  

:::image type="complex" source="../media/grid-grid-overlays-color.msft.png" alt-text="グリッド オーバーレイの色をカスタマイズする" lightbox="../media/grid-grid-overlays-color.msft.png":::
   グリッド オーバーレイの色をカスタマイズする  
:::image-end:::  

### <a name="highlight-the-grid"></a>グリッドを強調表示する  

[要素] ツールで**** HTML 要素を強調表示し、Web ページ上でスクロールするには、[要素] パネル**\(** [要素] パネル アイコン \) の [要素の表示] アイコンで [要素の表示] 要素 ![ ](../media/show-element-in-element-panel-icon.msft.png) を選択します。  

:::image type="complex" source="../media/grid-grid-overlays-highlight.msft.png" alt-text="グリッドを強調表示する" lightbox="../media/grid-grid-overlays-highlight.msft.png":::
   グリッドを強調表示する  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  

[JecFyiDemoCssGridFruit]: https://jec.fyi/demo/css-grid-fruit "CSS グリッド |jec.fyi"  
[JecFyiDemoCssGridSnack]: https://jec.fyi/demo/css-grid-snack "CSS グリッド |jec.fyi"  

[MdnCssGridLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout "CSS グリッド レイアウト |MDN"  
[MdnLayoutUsingNamedGridLines]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout/Layout_using_Named_Grid_Lines "名前付きグリッド線を使用した|MDN"  
[MdnLineBasedPlacementCssGrid]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout/Line-based_Placement_with_CSS_Grid "CSS Grid を使用した行ベースの配置|MDN"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> [Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developers.google.com/web/tools/chrome-devtools/css/grid)にあります。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
