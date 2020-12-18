---
description: Microsoft Edge DevTools を使用してページ CSS の CSS を表示および変更する方法について説明します。
title: Microsoft Edge DevTools で CSS グリッドを検査する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 1fe6bd1c8efd244315fb9a38777df6ea3e9b1a4d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231098"
---
# CSS グリッドを検査する  

この記事では、Web サイト上の CSS グリッドを識別し、カスタマイズ可能なグリッド オーバーレイを使用してグリッド レイアウトの問題をデバッグする方法について説明します。  

この記事の図で使用されている例は、次の Web ページから取り上されています。  

*   [果ボックス][JecFyiDemoCssGridFruit]  
*   [ボックス (1 つ)][JecFyiDemoCssGridSnack]  

## 始める前に  

CSS グリッドは、Web の強力なレイアウト パラダイムです。  CSS グリッドと多くの機能について学び始めるのに最適な場所は、MDN の [CSS グリッド レイアウト][MdnCssGridLayout] ガイドです。  

## CSS グリッドの検出  

ページ上の HTML 要素が追加または適用されると、[要素] パネルの横 `display: grid` `display: inline-grid` にバッジ `grid` が [表示][DevtoolsGuideChromiumOpen] されます。  

:::image type="complex" source="../media/grid-discover-grid.msft.png" alt-text="検出グリッド" lightbox="../media/grid-discover-grid.msft.png":::
   検出グリッド  
:::image-end:::  

バッジを選択して、ページ上のグリッド オーバーレイの表示を切り替える。  オーバーレイは要素の上に表示され、グリッドのようにレイアウトされ、グリッド線とトラックの位置が表示されます。  

:::image type="complex" source="../media/grid-highlight-grid.msft.png" alt-text="トグル グリッド バッジ" lightbox="../media/grid-highlight-grid.msft.png":::
   トグル グリッド バッジ  
:::image-end:::  

[レイアウト] **ウィンドウを開** きます。  グリッドがページに含まれる場合、[レイアウト]**** ウィンドウにはグリッド**** を表示するための多数のオプションを含む Grid セクションが含まれます。  

:::image type="complex" source="../media/grid-layout-pane.msft.png" alt-text="レイアウト ウィンドウ" lightbox="../media/grid-layout-pane.msft.png":::
   **レイアウト** ウィンドウ  
:::image-end:::  

[ **レイアウト]** ウィンドウの **[グリッド] セクション** には、次の 2 つのサブセクションが含まれます。  

*   オーバーレイの表示設定  
*   グリッド オーバーレイ  

<!--todo: @zoher verify the details for each of the sub-sections.  -->  

## オーバーレイの表示設定  

オーバーレイ **の表示設定は、** 次の 2 つのパーツで構成されます。  

*   ドロップダウン メニューから次のいずれかのオプションを選択します。  
    
    | 行オプション | 詳細 |  
    |:--- |:--- |  
    | **線ラベルを非表示にする** | 各グリッド オーバーレイの線のラベルを非表示にします。 |  
    | **行番号を表示する** | 各グリッド オーバーレイ \(既定で選択\) の線の番号を表示します。 |  
    | **行名を表示する** | 名前が指定されている場合は、各グリッド オーバーレイの線の名前を表示します。 |  
    
*  次のオプションの横にあるチェックボックスを選択します。  
    
    | オプション | 詳細 |  
    |:--- |:--- |  
    | **トラックのサイズを表示する**  | トラックのサイズを \(または hide\) 表示します。 |  
    | **エリア名を表示する** | 名前が指定されている場合は、エリアの名前を \(または hide\) で表示します。 |  
    | **グリッド線を拡張する** | 各軸に沿ったグリッドの寸法の拡張情報を \(または hides\) で表示します。  既定では、グリッド線は要素内に表示されるか、CSS が設定されている要素 `display: grid` `display: inline-grid` 内にのみ表示されます。 |  
    
次のセクションでは、オーバーレイの各表示設定の **詳細について説明します**。  

### 行番号を表示する  

既定では、正と負の行番号がグリッド オーバーレイに表示されます。  

グリッド オーバーレイ内の負の数の詳細については、CSS グリッドを使用して [線ベースの配置に移動します][MdnLineBasedPlacementCssGrid]。  

:::image type="complex" source="../media/grid-show-line-numbers.msft.png" alt-text="行番号を表示する" lightbox="../media/grid-show-line-numbers.msft.png":::
   行番号を表示する  
:::image-end:::  

### 線ラベルを非表示にする  

行番号 **を非表示にする場合は、[** 行ラベルを非表示にする] を選択します。  

:::image type="complex" source="../media/grid-hide-line-labels.msft.png" alt-text="線ラベルを非表示にする" lightbox="../media/grid-hide-line-labels.msft.png":::
   線ラベルを非表示にする  
:::image-end:::  

### 行名を表示する  

グリッド オーバーレイの線名の詳細については、名前付きグリッド線を使用 [してレイアウトに移動します][MdnLayoutUsingNamedGridLines]。  

[ **行名の表示] を** 選択すると、番号ではなく行名が表示されます。  この例では、4 行の名前 ( `left` , `middle1` . `middle2` `right` .  

<!--In the demo, **orange** element spans from left to right, with `grid-column: left` and `grid-column: right` CSS.  Showing line names makes it easier to visualize the start and end position of the element.  -->  

:::image type="complex" source="../media/grid-show-line-names.msft.png" alt-text="行名を表示する" lightbox="../media/grid-show-line-names.msft.png":::
   **行名を表示する**  
:::image-end:::  

### トラックのサイズを表示する  

グリッドの **トラック サイズを表示するには** 、[トラックサイズを表示する] チェック ボックスをオンにします。  

DevTools は、 `[authored size]` 各 `[computed size]` 行ラベルに表示されます。  

| Size | 詳細 |  
|:--- |:--- |  
| **作成されたサイズ** | スタイルシート \(定義されていない場合は省略\) で定義されているサイズです。 |  
| **計算されたサイズ** | 画面の実際のサイズ。 |  

デモでは、列 `snack-box` のサイズが CSS で定義 `grid-template-columns:1fr 2fr;` されています。  したがって、列の行ラベルには、作成されたサイズと計算されたサイズの両方が表示されます。  

| サイズを追跡する | 作成サイズ | 計算されたサイズ |  
|:--- |:--- |:--- |  
| **1fr &#x2022;** **96.66px** | 1fr | 96.66px |  
| **2fr &#x2022;** **193.32px** | 2fr | 193.32px |  

行行ラベルは、スタイルシートに定義された行サイズが定義されていないので、計算されたサイズのみを表示します。  

| サイズを追跡する | 作成サイズ | 計算されたサイズ |  
|:--- |:--- |:--- |  
| **80px** | &nbsp;| 80px |  
| **80px** | &nbsp;| 80px |  

:::image type="complex" source="../media/grid-show-track-sizes.msft.png" alt-text="トラックのサイズを表示する" lightbox="../media/grid-show-track-sizes.msft.png":::
   **トラックのサイズを表示する**  
:::image-end:::  

### エリア名を表示する  

エリア名を表示するには、[エリア名を表示 **する] チェック ボックスをオン** にします。  この例では、グリッドには**top、bottom1、bottom2**の 3 つの領域**があります**。 ****  

:::image type="complex" source="../media/grid-show-area-names.msft.png" alt-text="エリア名を表示する" lightbox="../media/grid-show-area-names.msft.png":::
   **エリア名を表示する**  
:::image-end:::  

### グリッド線を拡張する  

グリッド線 **を各軸に** 沿ってビューポートの端まで拡張するには、[グリッド線の拡張] チェック ボックスをオンにします。  

:::image type="complex" source="../media/grid-extend-grid-lines.msft.png" alt-text="グリッド線を拡張する" lightbox="../media/grid-extend-grid-lines.msft.png":::
   **グリッド線を拡張する**  
:::image-end:::  

## グリッド オーバーレイ  

[Grid **overlays]** セクションには、ページ上に存在するグリッドの一覧が表示されます。各グリッドには、さまざまなオプションと共にチェック ボックスが表示されます。  

### 複数のグリッドのオーバーレイ ビューを有効にする  

複数のグリッドのオーバーレイ グリッドを表示するには、グリッドの各名前の横にあるチェック ボックスをオンにします。  この例では、それぞれ異なる色で表される 2 つのグリッド オーバーレイが有効になっています。  

*   `main`  
*   `div.snack-box`  
    
:::image type="complex" source="../media/grid-grid-overlays.msft.png" alt-text="複数のグリッドのオーバーレイ ビューを有効にする" lightbox="../media/grid-grid-overlays.msft.png":::
   複数のグリッドのオーバーレイ ビューを有効にする  
:::image-end:::  

### グリッド オーバーレイの色をカスタマイズする  

カラー ピッカーを開き、グリッド オーバーレイの色をカスタマイズするには、グリッド オーバーレイの名前の横にあるボックスを選択します。  

:::image type="complex" source="../media/grid-grid-overlays-color.msft.png" alt-text="グリッド オーバーレイの色をカスタマイズする" lightbox="../media/grid-grid-overlays-color.msft.png":::
   グリッド オーバーレイの色をカスタマイズする  
:::image-end:::  

### グリッドを強調表示する  

[要素] パネルで**** HTML 要素を強調表示し、Web ページ上でスクロールするには、[要素] パネル**\(** [要素] パネル アイコン \) アイコンの [要素の表示] 要素を選択 ![ ][ImageShowElementInElementsPanelIcon] します。  

:::image type="complex" source="../media/grid-grid-overlays-highlight.msft.png" alt-text="グリッドを強調表示する" lightbox="../media/grid-grid-overlays-highlight.msft.png":::
   グリッドを強調表示する  
:::image-end:::  

## Microsoft Edge DevTools チームと連絡を取る  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageShowElementInElementsPanelIcon]: ../media/show-element-in-element-panel-icon.msft.png  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  

[JecFyiDemoCssGridFruit]: https://jec.fyi/demo/css-grid-fruit "CSS グリッド |jec.fyi"  
[JecFyiDemoCssGridSnack]: https://jec.fyi/demo/css-grid-snack "CSS グリッド |jec.fyi"  

[MdnCssGridLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout "CSS グリッド レイアウト |MDN"  
[MdnLayoutUsingNamedGridLines]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout/Layout_using_Named_Grid_Lines "名前付き枠線を使用したレイアウト |MDN"  
[MdnLineBasedPlacementCssGrid]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout/Line-based_Placement_with_CSS_Grid "CSS グリッドを使用した線ベースの配置 |MDN"  

> [!NOTE]
> このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。  
> [Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developers.google.com/web/tools/chrome-devtools/css/grid)にあります。  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
