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
# <span data-ttu-id="7a9fe-104">CSS グリッドの検査</span><span class="sxs-lookup"><span data-stu-id="7a9fe-104">Inspect CSS Grid</span></span>  

<span data-ttu-id="7a9fe-105">この記事では、カスタマイズ可能な grid オーバーレイを使用して、web サイト上の CSS グリッドを特定し、グリッドレイアウトの問題をデバッグする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-105">This article walks you through identifying CSS grids on a website and debugging grid layout issues using customizable grid overlays.</span></span>  

<span data-ttu-id="7a9fe-106">この記事の図で使用されている例は、次の web ページから抜粋したものです。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-106">The examples used in the figures in this article are taken from the following webpages.</span></span>  

*   [<span data-ttu-id="7a9fe-107">フルーツ箱</span><span class="sxs-lookup"><span data-stu-id="7a9fe-107">Fruit box</span></span>][JecFyiDemoCssGridFruit]  
*   [<span data-ttu-id="7a9fe-108">軽食ボックス</span><span class="sxs-lookup"><span data-stu-id="7a9fe-108">Snack box</span></span>][JecFyiDemoCssGridSnack]  

## <span data-ttu-id="7a9fe-109">始める前に</span><span class="sxs-lookup"><span data-stu-id="7a9fe-109">Before you begin</span></span>  

<span data-ttu-id="7a9fe-110">CSS Grid は、web のための強力なレイアウトパラダイムです。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-110">CSS Grid is a powerful layout paradigm for the web.</span></span>  <span data-ttu-id="7a9fe-111">CSS Grid について学習するのに最適な場所です。また、多くの機能は、MDN の [Css グリッドレイアウトガイド][MdnCssGridLayout] です。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-111">A great place to get started learning about CSS Grid and the many features is the [CSS Grid Layout guide][MdnCssGridLayout] on MDN.</span></span>  

## <span data-ttu-id="7a9fe-112">CSS グリッドについて知る</span><span class="sxs-lookup"><span data-stu-id="7a9fe-112">Discover CSS grids</span></span>  

<span data-ttu-id="7a9fe-113">ページ上の HTML 要素がある場合 `display: grid` 、またはその要素が適用されている場合 `display: inline-grid` 、 `grid` [ [要素][DevtoolsGuideChromiumOpen] ] パネルでは、その横にバッジが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-113">When an HTML element on your page has `display: grid` or `display: inline-grid` applied to it, a `grid` badge is displayed next to it in the [Elements][DevtoolsGuideChromiumOpen] panel.</span></span>  

:::image type="complex" source="../media/grid-discover-grid.msft.png" alt-text="検出グリッド" lightbox="../media/grid-discover-grid.msft.png":::
   <span data-ttu-id="7a9fe-115">検出グリッド</span><span class="sxs-lookup"><span data-stu-id="7a9fe-115">Discover grid</span></span>  
:::image-end:::  

<span data-ttu-id="7a9fe-116">ページのグリッドオーバーレイの表示を切り替えるには、バッジを選択します。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-116">Select the badge to toggle the display of a grid overlay on the page.</span></span>  <span data-ttu-id="7a9fe-117">オーバーレイは要素の上に表示され、grid のようにレイアウトされ、グリッド線とトラックの位置を表示します。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-117">The overlay appears over the element, laid out like a grid to display the position of the grid lines and tracks:</span></span>  

:::image type="complex" source="../media/grid-highlight-grid.msft.png" alt-text="検出グリッド" lightbox="../media/grid-highlight-grid.msft.png":::
   <span data-ttu-id="7a9fe-119">グリッドのバッジを切り替える</span><span class="sxs-lookup"><span data-stu-id="7a9fe-119">Toggle grid badge</span></span>  
:::image-end:::  

<span data-ttu-id="7a9fe-120">[ **レイアウト** ] ウィンドウを開く。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-120">Open the **Layout** pane.</span></span>  <span data-ttu-id="7a9fe-121">ページにグリッドが含まれている場合、[ **レイアウト** ] ウィンドウには、グリッドを表示するための多くのオプションを含む **Grid** セクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-121">When grids are included on a page, the **Layout** pane includes a **Grid** section containing a number of options for viewing the grids.</span></span>  

:::image type="complex" source="../media/grid-layout-pane.msft.png" alt-text="検出グリッド" lightbox="../media/grid-layout-pane.msft.png":::
   <span data-ttu-id="7a9fe-123">**レイアウト** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="7a9fe-123">**Layout** pane</span></span>  
:::image-end:::  

<span data-ttu-id="7a9fe-124">[**レイアウト**] ウィンドウの [**グリッド**] セクションには、次の2つのサブセクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-124">The **Grid** section in the **Layout** pane contains the following 2 sub-sections.</span></span>  

*   <span data-ttu-id="7a9fe-125">オーバーレイ表示の設定</span><span class="sxs-lookup"><span data-stu-id="7a9fe-125">Overlay display settings</span></span>  
*   <span data-ttu-id="7a9fe-126">グリッドのオーバーレイ</span><span class="sxs-lookup"><span data-stu-id="7a9fe-126">Grid overlays</span></span>  

<!--todo: @zoher verify the details for each of the sub-sections.  -->  

## <span data-ttu-id="7a9fe-127">オーバーレイ表示の設定</span><span class="sxs-lookup"><span data-stu-id="7a9fe-127">Overlay display settings</span></span>  

<span data-ttu-id="7a9fe-128">**オーバーレイの表示設定**は、次の2つの部分で構成されています。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-128">The **Overlay display settings** consists of following 2 parts.</span></span>  

*   <span data-ttu-id="7a9fe-129">ドロップダウンメニューから次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-129">Choose one of the following options from the dropdown menu.</span></span>  
    
    | <span data-ttu-id="7a9fe-130">[線] オプション</span><span class="sxs-lookup"><span data-stu-id="7a9fe-130">Line option</span></span> | <span data-ttu-id="7a9fe-131">詳細</span><span class="sxs-lookup"><span data-stu-id="7a9fe-131">Details</span></span> |  
    |:--- |:--- |  
    | **<span data-ttu-id="7a9fe-132">行ラベルを非表示にする</span><span class="sxs-lookup"><span data-stu-id="7a9fe-132">Hide line labels</span></span>** | <span data-ttu-id="7a9fe-133">各グリッドオーバーレイの線のラベルを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-133">Hide the labels of the lines for each grid overlay.</span></span> |  
    | **<span data-ttu-id="7a9fe-134">行番号を表示する</span><span class="sxs-lookup"><span data-stu-id="7a9fe-134">Show line numbers</span></span>** | <span data-ttu-id="7a9fe-135">各グリッドオーバーレイの線数を表示します (既定で選択されています)。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-135">Display the numbers of the lines for each grid overlay \(selected by default\).</span></span> |  
    | **<span data-ttu-id="7a9fe-136">行の名前を表示する</span><span class="sxs-lookup"><span data-stu-id="7a9fe-136">Show line names</span></span>** | <span data-ttu-id="7a9fe-137">名前が指定されているときに、グリッドオーバーレイごとに行の名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-137">Display the names of the lines for each grid overlay when names are provided.</span></span> |  
    
*  <span data-ttu-id="7a9fe-138">次のオプションの横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-138">Choose the checkbox next the following options.</span></span>  
    
    | <span data-ttu-id="7a9fe-139">オプション</span><span class="sxs-lookup"><span data-stu-id="7a9fe-139">Option</span></span> | <span data-ttu-id="7a9fe-140">詳細</span><span class="sxs-lookup"><span data-stu-id="7a9fe-140">Details</span></span> |  
    |:--- |:--- |  
    | **<span data-ttu-id="7a9fe-141">トラックサイズの表示</span><span class="sxs-lookup"><span data-stu-id="7a9fe-141">Show track sizes</span></span>**  | <span data-ttu-id="7a9fe-142">トラックのサイズを表示 (または非表示) します。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-142">Display \(or hide\) the sizes of the tracks.</span></span> |  
    | **<span data-ttu-id="7a9fe-143">エリア名を表示する</span><span class="sxs-lookup"><span data-stu-id="7a9fe-143">Show area names</span></span>** | <span data-ttu-id="7a9fe-144">名前が指定されているときに、領域の名前が表示されます (または非表示にします)。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-144">Display \(or hide\) the names of the area, when names are provided.</span></span> |  
    | **<span data-ttu-id="7a9fe-145">グリッド線を拡張する</span><span class="sxs-lookup"><span data-stu-id="7a9fe-145">Extend grid lines</span></span>** | <span data-ttu-id="7a9fe-146">各軸に沿ってグリッド寸法の拡張機能を表示します (または非表示にします)。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-146">Displays \(or hides\) the extensions of the grid dimensions along each axis.</span></span>  <span data-ttu-id="7a9fe-147">既定では、グリッド線は、要素の内側にのみ表示され `display: grid` `display: inline-grid` ます。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-147">By default, grid lines are only shown inside the element with `display: grid` or `display: inline-grid` CSS set on it.</span></span> |  
    
<span data-ttu-id="7a9fe-148">以下のセクションでは、 **オーバーレイ表示**の各設定について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-148">The following sections provide details for each of the **Overlay display settings**.</span></span>  

### <span data-ttu-id="7a9fe-149">行番号を表示する</span><span class="sxs-lookup"><span data-stu-id="7a9fe-149">Show line numbers</span></span>  

<span data-ttu-id="7a9fe-150">既定では、グリッドオーバーレイに正と負の行番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-150">By default, the positive and negative line numbers are displayed on the grid overlay.</span></span>  

<span data-ttu-id="7a9fe-151">グリッドオーバーレイの負の数値の詳細については、「 [CSS グリッドを使用して行ベースの配置][MdnLineBasedPlacementCssGrid]に移動する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-151">For more information about negative numbers in the grid overlay, navigate to [Line-based placement with CSS Grid][MdnLineBasedPlacementCssGrid].</span></span>  

:::image type="complex" source="../media/grid-show-line-numbers.msft.png" alt-text="検出グリッド" lightbox="../media/grid-show-line-numbers.msft.png":::
   <span data-ttu-id="7a9fe-153">行番号を表示する</span><span class="sxs-lookup"><span data-stu-id="7a9fe-153">Display line numbers</span></span>  
:::image-end:::  

### <span data-ttu-id="7a9fe-154">行ラベルを非表示にする</span><span class="sxs-lookup"><span data-stu-id="7a9fe-154">Hide line labels</span></span>  

<span data-ttu-id="7a9fe-155">行番号を非表示にするには、[ **行ラベルを表示** しない] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-155">Select **Hide line labels** to hide the line numbers.</span></span>  

:::image type="complex" source="../media/grid-hide-line-labels.msft.png" alt-text="検出グリッド" lightbox="../media/grid-hide-line-labels.msft.png":::
   <span data-ttu-id="7a9fe-157">行ラベルを非表示にする</span><span class="sxs-lookup"><span data-stu-id="7a9fe-157">Hide line labels</span></span>  
:::image-end:::  

### <span data-ttu-id="7a9fe-158">行の名前を表示する</span><span class="sxs-lookup"><span data-stu-id="7a9fe-158">Show line names</span></span>  

<!--todo: @rachel verify the link and text for line name -->  
<span data-ttu-id="7a9fe-159">グリッドオーバーレイの行名の詳細については、「 [名前付きグリッド線を使用してレイアウト][MdnLayoutUsingNamedGridLines]に移動する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-159">For more information about line names in the grid overlay, navigate to [Layout using named grid lines][MdnLayoutUsingNamedGridLines].</span></span>  

<span data-ttu-id="7a9fe-160">[ **行名の表示** ] を選択して、番号ではなく行の名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-160">Select **Show line names** to view the line names instead of numbers.</span></span>  <span data-ttu-id="7a9fe-161">この例では、4つの行に、、、、 `left` `middle1` `middle2` という名前が付いてい `right` ます。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-161">In the example, 4 lines have names: `left`, `middle1`, `middle2`, and `right`.</span></span>  

<!--In the demo, **orange** element spans from left to right, with `grid-column: left` and `grid-column: right` CSS.  Showing line names makes it easier to visualize the start and end position of the element.  -->  

:::image type="complex" source="../media/grid-show-line-names.msft.png" alt-text="検出グリッド" lightbox="../media/grid-show-line-names.msft.png":::
   **<span data-ttu-id="7a9fe-163">行の名前を表示する</span><span class="sxs-lookup"><span data-stu-id="7a9fe-163">Show line names</span></span>**  
:::image-end:::  

### <span data-ttu-id="7a9fe-164">トラックサイズの表示</span><span class="sxs-lookup"><span data-stu-id="7a9fe-164">Show track sizes</span></span>  

<span data-ttu-id="7a9fe-165">[ **トラックサイズの表示** ] チェックボックスをオンにして、グリッドのトラックサイズを表示します。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-165">Enable the **Show track sizes** checkbox to view the track sizes of the grid.</span></span>  

<span data-ttu-id="7a9fe-166">`[authored size]`各行ラベルに [DevTools] と表示され `[computed size]` ます。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-166">DevTools displays `[authored size]` and `[computed size]` in each line label.</span></span>  

| <span data-ttu-id="7a9fe-167">Size</span><span class="sxs-lookup"><span data-stu-id="7a9fe-167">Size</span></span> | <span data-ttu-id="7a9fe-168">詳細</span><span class="sxs-lookup"><span data-stu-id="7a9fe-168">Details</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="7a9fe-169">作成サイズ</span><span class="sxs-lookup"><span data-stu-id="7a9fe-169">authored size</span></span>** | <span data-ttu-id="7a9fe-170">スタイルシートで定義されているサイズ (定義されていない場合は省略します)。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-170">The size defined in stylesheet \(omitted if not defined\).</span></span> |  
| **<span data-ttu-id="7a9fe-171">計算されたサイズ</span><span class="sxs-lookup"><span data-stu-id="7a9fe-171">computed size</span></span>** | <span data-ttu-id="7a9fe-172">画面上の実際のサイズ。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-172">The actual size on screen.</span></span> |  

<span data-ttu-id="7a9fe-173">デモでは、 `snack-box` 列のサイズは CSS で定義されてい `grid-template-columns:1fr 2fr;` ます。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-173">In the demo, the `snack-box` column sizes are defined in the `grid-template-columns:1fr 2fr;` CSS.</span></span>  <span data-ttu-id="7a9fe-174">そのため、列の行ラベルには、作成と計算の両方のサイズが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-174">Therefore, the column line labels display both authored and computed sizes.</span></span>  

| <span data-ttu-id="7a9fe-175">トラックサイズ</span><span class="sxs-lookup"><span data-stu-id="7a9fe-175">Track size</span></span> | <span data-ttu-id="7a9fe-176">作成サイズ</span><span class="sxs-lookup"><span data-stu-id="7a9fe-176">Authored size</span></span> | <span data-ttu-id="7a9fe-177">計算されたサイズ</span><span class="sxs-lookup"><span data-stu-id="7a9fe-177">Computed size</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7a9fe-178">**1 fr** &#x2022; **96.66 px**</span><span class="sxs-lookup"><span data-stu-id="7a9fe-178">**1fr** &#x2022; **96.66px**</span></span> | <span data-ttu-id="7a9fe-179">1fr</span><span class="sxs-lookup"><span data-stu-id="7a9fe-179">1fr</span></span> | <span data-ttu-id="7a9fe-180">96.66 px</span><span class="sxs-lookup"><span data-stu-id="7a9fe-180">96.66px</span></span> |  
| <span data-ttu-id="7a9fe-181">**2fr** &#x2022; **193.32 px**</span><span class="sxs-lookup"><span data-stu-id="7a9fe-181">**2fr** &#x2022; **193.32px**</span></span> | <span data-ttu-id="7a9fe-182">2fr</span><span class="sxs-lookup"><span data-stu-id="7a9fe-182">2fr</span></span> | <span data-ttu-id="7a9fe-183">193.32 px</span><span class="sxs-lookup"><span data-stu-id="7a9fe-183">193.32px</span></span> |  

<span data-ttu-id="7a9fe-184">[行のラベル] には、計算済みのサイズだけが表示されます。これは、スタイルシートで定義されている行のサイズがないためです。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-184">The row line labels display only computed sizes, since there are no row sizes defined in the stylesheet.</span></span>  

| <span data-ttu-id="7a9fe-185">トラックサイズ</span><span class="sxs-lookup"><span data-stu-id="7a9fe-185">Track size</span></span> | <span data-ttu-id="7a9fe-186">作成サイズ</span><span class="sxs-lookup"><span data-stu-id="7a9fe-186">Authored size</span></span> | <span data-ttu-id="7a9fe-187">計算されたサイズ</span><span class="sxs-lookup"><span data-stu-id="7a9fe-187">Computed size</span></span> |  
|:--- |:--- |:--- |  
| **<span data-ttu-id="7a9fe-188">80px</span><span class="sxs-lookup"><span data-stu-id="7a9fe-188">80px</span></span>** | &nbsp;| <span data-ttu-id="7a9fe-189">80px</span><span class="sxs-lookup"><span data-stu-id="7a9fe-189">80px</span></span> |  
| **<span data-ttu-id="7a9fe-190">80px</span><span class="sxs-lookup"><span data-stu-id="7a9fe-190">80px</span></span>** | &nbsp;| <span data-ttu-id="7a9fe-191">80px</span><span class="sxs-lookup"><span data-stu-id="7a9fe-191">80px</span></span> |  

:::image type="complex" source="../media/grid-show-track-sizes.msft.png" alt-text="検出グリッド" lightbox="../media/grid-show-track-sizes.msft.png":::
   **<span data-ttu-id="7a9fe-193">トラックサイズの表示</span><span class="sxs-lookup"><span data-stu-id="7a9fe-193">Show track sizes</span></span>**  
:::image-end:::  

### <span data-ttu-id="7a9fe-194">エリア名を表示する</span><span class="sxs-lookup"><span data-stu-id="7a9fe-194">Show area names</span></span>  

<span data-ttu-id="7a9fe-195">エリア名を表示するには、[ **エリア名の表示** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-195">To view the area names, enable the **Show area names** checkbox.</span></span>  <span data-ttu-id="7a9fe-196">この例では、grid には、 **top**、 **bottom1** 、 **bottom2**の3つの領域があります。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-196">In the example, there are 3 areas in the grid: **top**, **bottom1** and **bottom2**.</span></span>  

:::image type="complex" source="../media/grid-show-area-names.msft.png" alt-text="検出グリッド" lightbox="../media/grid-show-area-names.msft.png":::
   **<span data-ttu-id="7a9fe-198">エリア名を表示する</span><span class="sxs-lookup"><span data-stu-id="7a9fe-198">Show area names</span></span>**  
:::image-end:::  

### <span data-ttu-id="7a9fe-199">グリッド線を拡張する</span><span class="sxs-lookup"><span data-stu-id="7a9fe-199">Extend grid lines</span></span>  

<span data-ttu-id="7a9fe-200">[ **グリッド線の延長** ] チェックボックスをオンにして、各軸に沿ってビューポートの端までグリッド線を延長します。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-200">Enable the **Extend grid lines** checkbox to extend the grid lines to the edge of the viewport along each axis.</span></span>  

:::image type="complex" source="../media/grid-extend-grid-lines.msft.png" alt-text="検出グリッド" lightbox="../media/grid-extend-grid-lines.msft.png":::
   **<span data-ttu-id="7a9fe-202">グリッド線を拡張する</span><span class="sxs-lookup"><span data-stu-id="7a9fe-202">Extend grid lines</span></span>**  
:::image-end:::  

## <span data-ttu-id="7a9fe-203">グリッドのオーバーレイ</span><span class="sxs-lookup"><span data-stu-id="7a9fe-203">Grid overlays</span></span>  

<span data-ttu-id="7a9fe-204">[ **グリッドオーバーレイ** ] セクションには、ページに表示されているグリッドの一覧があります。各ボックスには、さまざまなオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-204">The **Grid overlays** section contains a list of grids that are present on the page, each with a checkbox, along with various options.</span></span>  

### <span data-ttu-id="7a9fe-205">複数のグリッドのオーバーレイビューを有効にする</span><span class="sxs-lookup"><span data-stu-id="7a9fe-205">Enable overlay views of multiple grids</span></span>  

<!--todo: @zoher verify and provide updates -->  

<span data-ttu-id="7a9fe-206">複数のグリッドのオーバーレイグリッドを表示するには、グリッドの各名前の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-206">To display the overlay grid for multiple grids, choose the checkbox next to each name of the grid.</span></span>  <span data-ttu-id="7a9fe-207">この例では、2つの grid オーバーレイが有効であり、それぞれ異なる色で表されています。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-207">In the example, there are 2 grid overlays enabled that are each represented with different colors.</span></span>  

*   `main`  
*   `div.snack-box`  
    
:::image type="complex" source="../media/grid-grid-overlays.msft.png" alt-text="検出グリッド" lightbox="../media/grid-grid-overlays.msft.png":::
   <span data-ttu-id="7a9fe-209">複数のグリッドのオーバーレイビューを有効にする</span><span class="sxs-lookup"><span data-stu-id="7a9fe-209">Enable overlay views of multiple grids</span></span>  
:::image-end:::  

### <span data-ttu-id="7a9fe-210">グリッドオーバーレイの色をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="7a9fe-210">Customize the grid overlay color</span></span>  

<span data-ttu-id="7a9fe-211">カラーピッカーを開いてグリッドオーバーレイの色をカスタマイズするには、グリッドオーバーレイの名前の横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-211">To open the color picker and customize the grid overlay color, choose the box next to the name of the grid overlay.</span></span>  

:::image type="complex" source="../media/grid-grid-overlays-color.msft.png" alt-text="検出グリッド" lightbox="../media/grid-grid-overlays-color.msft.png":::
   <span data-ttu-id="7a9fe-213">グリッドオーバーレイの色をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="7a9fe-213">Customize the grid overlay color</span></span>  
:::image-end:::  

### <span data-ttu-id="7a9fe-214">グリッドを強調表示する</span><span class="sxs-lookup"><span data-stu-id="7a9fe-214">Highlight the grid</span></span>  

<span data-ttu-id="7a9fe-215">[ **要素** ] パネルで HTML 要素を強調表示し、web ページ上でその要素にスクロールするには、[ **要素] パネルで [要素を表示** ] を選び ![ ます ([要素パネル] アイコンの要素を表示し ][ImageShowElementInElementsPanelIcon] ます)。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-215">To highlight the HTML element in the **Elements** panel and scroll to it on the webpage, choose the **Show element in the Elements panel** \(![Show element in the Elements panel icon][ImageShowElementInElementsPanelIcon]\) icon.</span></span>  

:::image type="complex" source="../media/grid-grid-overlays-highlight.msft.png" alt-text="検出グリッド" lightbox="../media/grid-grid-overlays-highlight.msft.png":::
   <span data-ttu-id="7a9fe-217">グリッドを強調表示する</span><span class="sxs-lookup"><span data-stu-id="7a9fe-217">Highlight the grid</span></span>  
:::image-end:::  

## <span data-ttu-id="7a9fe-218">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="7a9fe-218">Getting in touch with the Microsoft Edge DevTools team</span></span>  

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
> <span data-ttu-id="7a9fe-225">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-225">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="7a9fe-226">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/css/grid) にあり、 [Jecelyn][JecelynYeen] で作成されています (開発者の代表者、Chrome devtools \)。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-226">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/grid) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="7a9fe-228">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="7a9fe-228">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
