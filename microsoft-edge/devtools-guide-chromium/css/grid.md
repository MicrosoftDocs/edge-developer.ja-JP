---
description: Microsoft Edge DevTools を使用して、ページ CSS の CSS を表示し、変更する方法について説明します。
title: Microsoft Edge DevTools で CSS グリッドを検査する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/22/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 150aea57aa676580b554cc74292671ed567a0a2c
ms.sourcegitcommit: 6e2b26d41a0aa56ac34e6edc7dddd852ddb415b1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2020
ms.locfileid: "11134105"
---
# CSS グリッドの検査  

この記事では、カスタマイズ可能な grid オーバーレイを使用して、web サイト上の CSS グリッドを特定し、グリッドレイアウトの問題をデバッグする方法について説明します。  

この記事の図で使用されている例は、次の web ページから抜粋したものです。  

*   [フルーツ箱][JecFyiDemoCssGridFruit]  
*   [軽食ボックス][JecFyiDemoCssGridSnack]  

## 始める前に  

CSS Grid は、web のための強力なレイアウトパラダイムです。  CSS Grid について学習するのに最適な場所です。また、多くの機能は、MDN の [Css グリッドレイアウトガイド][MdnCssGridLayout] です。  

## CSS グリッドについて知る  

ページ上の HTML 要素がある場合 `display: grid` 、またはその要素が適用されている場合 `display: inline-grid` 、 `grid` [ [要素][DevtoolsGuideChromiumOpen] ] パネルでは、その横にバッジが表示されます。  

:::image type="complex" source="../media/grid-discover-grid.msft.png" alt-text="検出グリッド" lightbox="../media/grid-discover-grid.msft.png":::
   検出グリッド  
:::image-end:::  

ページのグリッドオーバーレイの表示を切り替えるには、バッジを選択します。  オーバーレイは要素の上に表示され、grid のようにレイアウトされ、グリッド線とトラックの位置を表示します。  

:::image type="complex" source="../media/grid-highlight-grid.msft.png" alt-text="検出グリッド" lightbox="../media/grid-highlight-grid.msft.png":::
   グリッドのバッジを切り替える  
:::image-end:::  

[ **レイアウト** ] ウィンドウを開く。  ページにグリッドが含まれている場合、[ **レイアウト** ] ウィンドウには、グリッドを表示するための多くのオプションを含む **Grid** セクションが含まれます。  

:::image type="complex" source="../media/grid-layout-pane.msft.png" alt-text="検出グリッド" lightbox="../media/grid-layout-pane.msft.png":::
   **レイアウト** ウィンドウ  
:::image-end:::  

[**レイアウト**] ウィンドウの [**グリッド**] セクションには、次の2つのサブセクションが含まれています。  

*   オーバーレイ表示の設定  
*   グリッドのオーバーレイ  

<!--todo: @zoher verify the details for each of the sub-sections.  -->  

## オーバーレイ表示の設定  

**オーバーレイの表示設定**は、次の2つの部分で構成されています。  

*   ドロップダウンメニューから次のいずれかのオプションを選択します。  
    
    | [線] オプション | 詳細 |  
    |:--- |:--- |  
    | **行ラベルを非表示にする** | 各グリッドオーバーレイの線のラベルを非表示にします。 |  
    | **行番号を表示する** | 各グリッドオーバーレイの線数を表示します (既定で選択されています)。 |  
    | **行の名前を表示する** | 名前が指定されているときに、グリッドオーバーレイごとに行の名前を表示します。 |  
    
*  次のオプションの横にあるチェックボックスをオンにします。  
    
    | オプション | 詳細 |  
    |:--- |:--- |  
    | **トラックサイズの表示**  | トラックのサイズを表示 (または非表示) します。 |  
    | **エリア名を表示する** | 名前が指定されているときに、領域の名前が表示されます (または非表示にします)。 |  
    | **グリッド線を拡張する** | 各軸に沿ってグリッド寸法の拡張機能を表示します (または非表示にします)。  既定では、グリッド線は、要素の内側にのみ表示され `display: grid` `display: inline-grid` ます。 |  
    
以下のセクションでは、 **オーバーレイ表示**の各設定について詳しく説明します。  

### 行番号を表示する  

既定では、グリッドオーバーレイに正と負の行番号が表示されます。  

グリッドオーバーレイの負の数値の詳細については、「 [CSS グリッドを使用して行ベースの配置][MdnLineBasedPlacementCssGrid]に移動する」を参照してください。  

:::image type="complex" source="../media/grid-show-line-numbers.msft.png" alt-text="検出グリッド" lightbox="../media/grid-show-line-numbers.msft.png":::
   行番号を表示する  
:::image-end:::  

### 行ラベルを非表示にする  

行番号を非表示にするには、[ **行ラベルを表示** しない] を選択します。  

:::image type="complex" source="../media/grid-hide-line-labels.msft.png" alt-text="検出グリッド" lightbox="../media/grid-hide-line-labels.msft.png":::
   行ラベルを非表示にする  
:::image-end:::  

### 行の名前を表示する  

<!--todo: @rachel verify the link and text for line name -->  
グリッドオーバーレイの行名の詳細については、「 [名前付きグリッド線を使用してレイアウト][MdnLayoutUsingNamedGridLines]に移動する」を参照してください。  

[ **行名の表示** ] を選択して、番号ではなく行の名前を表示します。  この例では、4つの行に、、、、 `left` `middle1` `middle2` という名前が付いてい `right` ます。  

<!--In the demo, **orange** element spans from left to right, with `grid-column: left` and `grid-column: right` CSS.  Showing line names makes it easier to visualize the start and end position of the element.  -->  

:::image type="complex" source="../media/grid-show-line-names.msft.png" alt-text="検出グリッド" lightbox="../media/grid-show-line-names.msft.png":::
   **行の名前を表示する**  
:::image-end:::  

### トラックサイズの表示  

[ **トラックサイズの表示** ] チェックボックスをオンにして、グリッドのトラックサイズを表示します。  

`[authored size]`各行ラベルに [DevTools] と表示され `[computed size]` ます。  

| Size | 詳細 |  
|:--- |:--- |  
| **作成サイズ** | スタイルシートで定義されているサイズ (定義されていない場合は省略します)。 |  
| **計算されたサイズ** | 画面上の実際のサイズ。 |  

デモでは、 `snack-box` 列のサイズは CSS で定義されてい `grid-template-columns:1fr 2fr;` ます。  そのため、列の行ラベルには、作成と計算の両方のサイズが表示されます。  

| トラックサイズ | 作成サイズ | 計算されたサイズ |  
|:--- |:--- |:--- |  
| **1 fr** &#x2022; **96.66 px** | 1fr | 96.66 px |  
| **2fr** &#x2022; **193.32 px** | 2fr | 193.32 px |  

[行のラベル] には、計算済みのサイズだけが表示されます。これは、スタイルシートで定義されている行のサイズがないためです。  

| トラックサイズ | 作成サイズ | 計算されたサイズ |  
|:--- |:--- |:--- |  
| **80px** | &nbsp;| 80px |  
| **80px** | &nbsp;| 80px |  

:::image type="complex" source="../media/grid-show-track-sizes.msft.png" alt-text="検出グリッド" lightbox="../media/grid-show-track-sizes.msft.png":::
   **トラックサイズの表示**  
:::image-end:::  

### エリア名を表示する  

エリア名を表示するには、[ **エリア名の表示** ] チェックボックスをオンにします。  この例では、grid には、 **top**、 **bottom1** 、 **bottom2**の3つの領域があります。  

:::image type="complex" source="../media/grid-show-area-names.msft.png" alt-text="検出グリッド" lightbox="../media/grid-show-area-names.msft.png":::
   **エリア名を表示する**  
:::image-end:::  

### グリッド線を拡張する  

[ **グリッド線の延長** ] チェックボックスをオンにして、各軸に沿ってビューポートの端までグリッド線を延長します。  

:::image type="complex" source="../media/grid-extend-grid-lines.msft.png" alt-text="検出グリッド" lightbox="../media/grid-extend-grid-lines.msft.png":::
   **グリッド線を拡張する**  
:::image-end:::  

## グリッドのオーバーレイ  

[ **グリッドオーバーレイ** ] セクションには、ページに表示されているグリッドの一覧があります。各ボックスには、さまざまなオプションがあります。  

### 複数のグリッドのオーバーレイビューを有効にする  

<!--todo: @zoher verify and provide updates -->  

複数のグリッドのオーバーレイグリッドを表示するには、グリッドの各名前の横にあるチェックボックスをオンにします。  この例では、2つの grid オーバーレイが有効であり、それぞれ異なる色で表されています。  

*   `main`  
*   `div.snack-box`  
    
:::image type="complex" source="../media/grid-grid-overlays.msft.png" alt-text="検出グリッド" lightbox="../media/grid-grid-overlays.msft.png":::
   複数のグリッドのオーバーレイビューを有効にする  
:::image-end:::  

### グリッドオーバーレイの色をカスタマイズする  

カラーピッカーを開いてグリッドオーバーレイの色をカスタマイズするには、グリッドオーバーレイの名前の横にあるボックスを選択します。  

:::image type="complex" source="../media/grid-grid-overlays-color.msft.png" alt-text="検出グリッド" lightbox="../media/grid-grid-overlays-color.msft.png":::
   グリッドオーバーレイの色をカスタマイズする  
:::image-end:::  

### グリッドを強調表示する  

[ **要素** ] パネルで HTML 要素を強調表示し、web ページ上でその要素にスクロールするには、[ **要素] パネルで [要素を表示** ] を選び ![ ます ([要素パネル] アイコンの要素を表示し ][ImageShowElementInElementsPanelIcon] ます)。  

:::image type="complex" source="../media/grid-grid-overlays-highlight.msft.png" alt-text="検出グリッド" lightbox="../media/grid-grid-overlays-highlight.msft.png":::
   グリッドを強調表示する  
:::image-end:::  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageShowElementInElementsPanelIcon]: ../media/show-element-in-element-panel-icon.msft.png  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open.md "Microsoft Edge DevTools を開く |Microsoft ドキュメント"  

[JecFyiDemoCssGridFruit]: https://jec.fyi/demo/css-grid-fruit "CSS グリッド |jec"  
[JecFyiDemoCssGridSnack]: https://jec.fyi/demo/css-grid-snack "CSS グリッド |jec"  

[MdnCssGridLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout "CSS グリッドレイアウト |MDN"  
[MdnLayoutUsingNamedGridLines]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout/Layout_using_Named_Grid_Lines "名前付きグリッド線を使用したレイアウト |MDN"  
[MdnLineBasedPlacementCssGrid]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout/Line-based_Placement_with_CSS_Grid "CSS グリッドを使用した線ベースの配置 |MDN"  

> [!NOTE]
> このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。  
> 元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/css/grid) にあり、 [Jecelyn][JecelynYeen] で作成されています (開発者の代表者、Chrome devtools \)。  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
