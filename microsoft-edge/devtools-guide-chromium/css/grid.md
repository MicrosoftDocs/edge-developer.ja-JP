---
description: DevTools の Microsoft Edgeを使用して、ページ CSS の CSS を表示および変更する方法について説明します。
title: DevTools で CSS グリッドMicrosoft Edgeする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 68493fae5e96ef1b2c7ed1205d67fd2b4cf67df5
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564456"
---
# <a name="inspect-css-grid"></a><span data-ttu-id="a0307-104">CSS グリッドの検査</span><span class="sxs-lookup"><span data-stu-id="a0307-104">Inspect CSS Grid</span></span>  

<span data-ttu-id="a0307-105">この記事では、Web サイトで CSS グリッドを識別し、カスタマイズ可能なグリッド オーバーレイを使用してグリッド レイアウトの問題をデバッグする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0307-105">This article walks you through identifying CSS grids on a website and debugging grid layout issues using customizable grid overlays.</span></span>  

<span data-ttu-id="a0307-106">この記事の図で使用される例は、次の Web ページから取り上されています。</span><span class="sxs-lookup"><span data-stu-id="a0307-106">The examples used in the figures in this article are taken from the following webpages.</span></span>  

*   [<span data-ttu-id="a0307-107">フルーツ ボックス</span><span class="sxs-lookup"><span data-stu-id="a0307-107">Fruit box</span></span>][JecFyiDemoCssGridFruit]  
*   [<span data-ttu-id="a0307-108">スナック ボックス</span><span class="sxs-lookup"><span data-stu-id="a0307-108">Snack box</span></span>][JecFyiDemoCssGridSnack]  

## <a name="before-you-begin"></a><span data-ttu-id="a0307-109">始める前に</span><span class="sxs-lookup"><span data-stu-id="a0307-109">Before you begin</span></span>  

<span data-ttu-id="a0307-110">CSS Grid は、Web の強力なレイアウト のパラダイムです。</span><span class="sxs-lookup"><span data-stu-id="a0307-110">CSS Grid is a powerful layout paradigm for the web.</span></span>  <span data-ttu-id="a0307-111">CSS Grid の学習を始めるのに最適な場所であり、多くの機能は [MDN][MdnCssGridLayout] の CSS グリッド レイアウト ガイドです。</span><span class="sxs-lookup"><span data-stu-id="a0307-111">A great place to get started learning about CSS Grid and the many features is the [CSS Grid Layout guide][MdnCssGridLayout] on MDN.</span></span>  

## <a name="discover-css-grids"></a><span data-ttu-id="a0307-112">CSS グリッドの検出</span><span class="sxs-lookup"><span data-stu-id="a0307-112">Discover CSS grids</span></span>  

<span data-ttu-id="a0307-113">ページの HTML 要素がページに適用されている場合、その横に [要素] パネルにバッジ `display: grid` `display: inline-grid` `grid` が [表示][DevtoolsGuideChromiumOpen] されます。</span><span class="sxs-lookup"><span data-stu-id="a0307-113">When an HTML element on your page has `display: grid` or `display: inline-grid` applied to it, a `grid` badge is displayed next to it in the [Elements][DevtoolsGuideChromiumOpen] panel.</span></span>  

:::image type="complex" source="../media/grid-discover-grid.msft.png" alt-text="グリッドの検出" lightbox="../media/grid-discover-grid.msft.png":::
   <span data-ttu-id="a0307-115">グリッドの検出</span><span class="sxs-lookup"><span data-stu-id="a0307-115">Discover grid</span></span>  
:::image-end:::  

<span data-ttu-id="a0307-116">バッジを選択して、ページ上のグリッド オーバーレイの表示を切り替える。</span><span class="sxs-lookup"><span data-stu-id="a0307-116">Choose the badge to toggle the display of a grid overlay on the page.</span></span>  <span data-ttu-id="a0307-117">オーバーレイは要素の上に表示され、グリッドのようにレイアウトされ、グリッド線とトラックの位置が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0307-117">The overlay appears over the element, laid out like a grid to display the position of the grid lines and tracks:</span></span>  

:::image type="complex" source="../media/grid-highlight-grid.msft.png" alt-text="トグル グリッド バッジ" lightbox="../media/grid-highlight-grid.msft.png":::
   <span data-ttu-id="a0307-119">トグル グリッド バッジ</span><span class="sxs-lookup"><span data-stu-id="a0307-119">Toggle grid badge</span></span>  
:::image-end:::  

<span data-ttu-id="a0307-120">[レイアウト] **ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="a0307-120">Open the **Layout** pane.</span></span>  <span data-ttu-id="a0307-121">グリッドがページに含まれている場合、[レイアウト]\*\*\*\* ウィンドウには、\*\*\*\* グリッドを表示するための多数のオプションを含むグリッド セクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a0307-121">When grids are included on a page, the **Layout** pane includes a **Grid** section containing a number of options for viewing the grids.</span></span>  

:::image type="complex" source="../media/grid-layout-pane.msft.png" alt-text="レイアウト ウィンドウ" lightbox="../media/grid-layout-pane.msft.png":::
   <span data-ttu-id="a0307-123">**レイアウト** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="a0307-123">**Layout** pane</span></span>  
:::image-end:::  

<span data-ttu-id="a0307-124">[ **レイアウト]** ウィンドウの **[グリッド] セクション** には、次の 2 つのサブセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a0307-124">The **Grid** section in the **Layout** pane contains the following 2 sub-sections.</span></span>  

*   <span data-ttu-id="a0307-125">オーバーレイ表示設定</span><span class="sxs-lookup"><span data-stu-id="a0307-125">Overlay display settings</span></span>  
*   <span data-ttu-id="a0307-126">グリッド オーバーレイ</span><span class="sxs-lookup"><span data-stu-id="a0307-126">Grid overlays</span></span>  

<!--todo: @zoher verify the details for each of the sub-sections.  -->  

## <a name="overlay-display-settings"></a><span data-ttu-id="a0307-127">オーバーレイ表示設定</span><span class="sxs-lookup"><span data-stu-id="a0307-127">Overlay display settings</span></span>  

<span data-ttu-id="a0307-128">オーバーレイ **の表示設定は** 、次の 2 つの部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="a0307-128">The **Overlay display settings** consists of following 2 parts.</span></span>  

*   <span data-ttu-id="a0307-129">ドロップダウン メニューから次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a0307-129">Choose one of the following options from the dropdown menu.</span></span>  
    
    | <span data-ttu-id="a0307-130">Line オプション</span><span class="sxs-lookup"><span data-stu-id="a0307-130">Line option</span></span> | <span data-ttu-id="a0307-131">詳細</span><span class="sxs-lookup"><span data-stu-id="a0307-131">Details</span></span> |  
    |:--- |:--- |  
    | **<span data-ttu-id="a0307-132">線ラベルを非表示にする</span><span class="sxs-lookup"><span data-stu-id="a0307-132">Hide line labels</span></span>** | <span data-ttu-id="a0307-133">各グリッド オーバーレイの線のラベルを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="a0307-133">Hide the labels of the lines for each grid overlay.</span></span> |  
    | **<span data-ttu-id="a0307-134">行番号の表示</span><span class="sxs-lookup"><span data-stu-id="a0307-134">Show line numbers</span></span>** | <span data-ttu-id="a0307-135">各グリッド オーバーレイ \(default\で選択) の線の番号を表示します。</span><span class="sxs-lookup"><span data-stu-id="a0307-135">Display the numbers of the lines for each grid overlay \(selected by default\).</span></span> |  
    | **<span data-ttu-id="a0307-136">行名の表示</span><span class="sxs-lookup"><span data-stu-id="a0307-136">Show line names</span></span>** | <span data-ttu-id="a0307-137">名前が指定されている場合は、各グリッド オーバーレイの線の名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="a0307-137">Display the names of the lines for each grid overlay when names are provided.</span></span> |  
    
*  <span data-ttu-id="a0307-138">次のオプションの横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a0307-138">Choose the checkbox next the following options.</span></span>  
    
    | <span data-ttu-id="a0307-139">オプション</span><span class="sxs-lookup"><span data-stu-id="a0307-139">Option</span></span> | <span data-ttu-id="a0307-140">詳細</span><span class="sxs-lookup"><span data-stu-id="a0307-140">Details</span></span> |  
    |:--- |:--- |  
    | **<span data-ttu-id="a0307-141">トラックのサイズを表示する</span><span class="sxs-lookup"><span data-stu-id="a0307-141">Show track sizes</span></span>**  | <span data-ttu-id="a0307-142">トラックのサイズを \(または hide\) で表示します。</span><span class="sxs-lookup"><span data-stu-id="a0307-142">Display \(or hide\) the sizes of the tracks.</span></span> |  
    | **<span data-ttu-id="a0307-143">エリア名の表示</span><span class="sxs-lookup"><span data-stu-id="a0307-143">Show area names</span></span>** | <span data-ttu-id="a0307-144">名前が指定されている場合は、エリアの名前を \(または hide\) で表示します。</span><span class="sxs-lookup"><span data-stu-id="a0307-144">Display \(or hide\) the names of the area, when names are provided.</span></span> |  
    | **<span data-ttu-id="a0307-145">グリッド線を拡張する</span><span class="sxs-lookup"><span data-stu-id="a0307-145">Extend grid lines</span></span>** | <span data-ttu-id="a0307-146">各軸に沿ってグリッド寸法の拡張子 \(または hides\) を表示します。</span><span class="sxs-lookup"><span data-stu-id="a0307-146">Displays \(or hides\) the extensions of the grid dimensions along each axis.</span></span>  <span data-ttu-id="a0307-147">既定では、グリッド線は要素に設定されている要素または `display: grid` CSS セット内 `display: inline-grid` にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0307-147">By default, grid lines are only shown inside the element with `display: grid` or `display: inline-grid` CSS set on it.</span></span> |  
    
<span data-ttu-id="a0307-148">次のセクションでは、オーバーレイ表示の各設定の詳細 **について説明します**。</span><span class="sxs-lookup"><span data-stu-id="a0307-148">The following sections provide details for each of the **Overlay display settings**.</span></span>  

### <a name="show-line-numbers"></a><span data-ttu-id="a0307-149">行番号の表示</span><span class="sxs-lookup"><span data-stu-id="a0307-149">Show line numbers</span></span>  

<span data-ttu-id="a0307-150">既定では、正と負の行番号がグリッド オーバーレイに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0307-150">By default, the positive and negative line numbers are displayed on the grid overlay.</span></span>  

<span data-ttu-id="a0307-151">グリッド オーバーレイ内の負の数値の詳細については、「CSS Grid を使用した線ベースの [配置」に移動します][MdnLineBasedPlacementCssGrid]。</span><span class="sxs-lookup"><span data-stu-id="a0307-151">For more information about negative numbers in the grid overlay, navigate to [Line-based placement with CSS Grid][MdnLineBasedPlacementCssGrid].</span></span>  

:::image type="complex" source="../media/grid-show-line-numbers.msft.png" alt-text="行番号の表示" lightbox="../media/grid-show-line-numbers.msft.png":::
   <span data-ttu-id="a0307-153">行番号の表示</span><span class="sxs-lookup"><span data-stu-id="a0307-153">Display line numbers</span></span>  
:::image-end:::  

### <a name="hide-line-labels"></a><span data-ttu-id="a0307-154">線ラベルを非表示にする</span><span class="sxs-lookup"><span data-stu-id="a0307-154">Hide line labels</span></span>  

<span data-ttu-id="a0307-155">[線 **のラベルを非表示にする** ] を選択して、行番号を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="a0307-155">Choose **Hide line labels** to hide the line numbers.</span></span>  

:::image type="complex" source="../media/grid-hide-line-labels.msft.png" alt-text="線ラベルを非表示にする" lightbox="../media/grid-hide-line-labels.msft.png":::
   <span data-ttu-id="a0307-157">線ラベルを非表示にする</span><span class="sxs-lookup"><span data-stu-id="a0307-157">Hide line labels</span></span>  
:::image-end:::  

### <a name="show-line-names"></a><span data-ttu-id="a0307-158">行名の表示</span><span class="sxs-lookup"><span data-stu-id="a0307-158">Show line names</span></span>  

<span data-ttu-id="a0307-159">グリッド オーバーレイの行名の詳細については、「名前付きグリッド線を使用 [したレイアウト」に移動します][MdnLayoutUsingNamedGridLines]。</span><span class="sxs-lookup"><span data-stu-id="a0307-159">For more information about line names in the grid overlay, navigate to [Layout using named grid lines][MdnLayoutUsingNamedGridLines].</span></span>  

<span data-ttu-id="a0307-160">[ **行名の表示]** を選択して、数字の代わりに行名を表示します。</span><span class="sxs-lookup"><span data-stu-id="a0307-160">Choose **Show line names** to view the line names instead of numbers.</span></span>  <span data-ttu-id="a0307-161">この例では、4 行に名前 `left` `middle1` 、、、 `middle2` および を指定します `right` 。</span><span class="sxs-lookup"><span data-stu-id="a0307-161">In the example, 4 lines have names: `left`, `middle1`, `middle2`, and `right`.</span></span>  

<!--In the demo, **orange** element spans from left to right, with `grid-column: left` and `grid-column: right` CSS.  Showing line names makes it easier to visualize the start and end position of the element.  -->  

:::image type="complex" source="../media/grid-show-line-names.msft.png" alt-text="行名の表示" lightbox="../media/grid-show-line-names.msft.png":::
   **<span data-ttu-id="a0307-163">行名の表示</span><span class="sxs-lookup"><span data-stu-id="a0307-163">Show line names</span></span>**  
:::image-end:::  

### <a name="show-track-sizes"></a><span data-ttu-id="a0307-164">トラックのサイズを表示する</span><span class="sxs-lookup"><span data-stu-id="a0307-164">Show track sizes</span></span>  

<span data-ttu-id="a0307-165">グリッドの **トラック サイズを表示** するには、[トラックサイズを表示する] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a0307-165">Enable the **Show track sizes** checkbox to view the track sizes of the grid.</span></span>  

<span data-ttu-id="a0307-166">DevTools は、 `[authored size]` 各 `[computed size]` 行ラベルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0307-166">DevTools displays `[authored size]` and `[computed size]` in each line label.</span></span>  

| <span data-ttu-id="a0307-167">Size</span><span class="sxs-lookup"><span data-stu-id="a0307-167">Size</span></span> | <span data-ttu-id="a0307-168">詳細</span><span class="sxs-lookup"><span data-stu-id="a0307-168">Details</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="a0307-169">オーサリングされたサイズ</span><span class="sxs-lookup"><span data-stu-id="a0307-169">authored size</span></span>** | <span data-ttu-id="a0307-170">stylesheet \(defined\ではない場合は省略) で定義されているサイズ。</span><span class="sxs-lookup"><span data-stu-id="a0307-170">The size defined in stylesheet \(omitted if not defined\).</span></span> |  
| **<span data-ttu-id="a0307-171">計算されたサイズ</span><span class="sxs-lookup"><span data-stu-id="a0307-171">computed size</span></span>** | <span data-ttu-id="a0307-172">画面の実際のサイズ。</span><span class="sxs-lookup"><span data-stu-id="a0307-172">The actual size on screen.</span></span> |  

<span data-ttu-id="a0307-173">デモでは、列 `snack-box` のサイズは CSS で定義 `grid-template-columns:1fr 2fr;` されます。</span><span class="sxs-lookup"><span data-stu-id="a0307-173">In the demo, the `snack-box` column sizes are defined in the `grid-template-columns:1fr 2fr;` CSS.</span></span>  <span data-ttu-id="a0307-174">したがって、列の行ラベルには、作成サイズと計算サイズの両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0307-174">Therefore, the column line labels display both authored and computed sizes.</span></span>  

| <span data-ttu-id="a0307-175">トラックのサイズ</span><span class="sxs-lookup"><span data-stu-id="a0307-175">Track size</span></span> | <span data-ttu-id="a0307-176">オーサリングされたサイズ</span><span class="sxs-lookup"><span data-stu-id="a0307-176">Authored size</span></span> | <span data-ttu-id="a0307-177">計算されたサイズ</span><span class="sxs-lookup"><span data-stu-id="a0307-177">Computed size</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="a0307-178">**1fr &#x2022;** **96.66px**</span><span class="sxs-lookup"><span data-stu-id="a0307-178">**1fr** &#x2022; **96.66px**</span></span> | <span data-ttu-id="a0307-179">1fr</span><span class="sxs-lookup"><span data-stu-id="a0307-179">1fr</span></span> | <span data-ttu-id="a0307-180">96.66px</span><span class="sxs-lookup"><span data-stu-id="a0307-180">96.66px</span></span> |  
| <span data-ttu-id="a0307-181">**2fr &#x2022;** **193.32px**</span><span class="sxs-lookup"><span data-stu-id="a0307-181">**2fr** &#x2022; **193.32px**</span></span> | <span data-ttu-id="a0307-182">2fr</span><span class="sxs-lookup"><span data-stu-id="a0307-182">2fr</span></span> | <span data-ttu-id="a0307-183">193.32px</span><span class="sxs-lookup"><span data-stu-id="a0307-183">193.32px</span></span> |  

<span data-ttu-id="a0307-184">行行ラベルは、スタイルシートで定義されている行サイズが無く、計算されたサイズのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="a0307-184">The row line labels display only computed sizes, since there are no row sizes defined in the stylesheet.</span></span>  

| <span data-ttu-id="a0307-185">トラックのサイズ</span><span class="sxs-lookup"><span data-stu-id="a0307-185">Track size</span></span> | <span data-ttu-id="a0307-186">オーサリングされたサイズ</span><span class="sxs-lookup"><span data-stu-id="a0307-186">Authored size</span></span> | <span data-ttu-id="a0307-187">計算されたサイズ</span><span class="sxs-lookup"><span data-stu-id="a0307-187">Computed size</span></span> |  
|:--- |:--- |:--- |  
| **<span data-ttu-id="a0307-188">80px</span><span class="sxs-lookup"><span data-stu-id="a0307-188">80px</span></span>** | &nbsp;| <span data-ttu-id="a0307-189">80px</span><span class="sxs-lookup"><span data-stu-id="a0307-189">80px</span></span> |  
| **<span data-ttu-id="a0307-190">80px</span><span class="sxs-lookup"><span data-stu-id="a0307-190">80px</span></span>** | &nbsp;| <span data-ttu-id="a0307-191">80px</span><span class="sxs-lookup"><span data-stu-id="a0307-191">80px</span></span> |  

:::image type="complex" source="../media/grid-show-track-sizes.msft.png" alt-text="トラックのサイズを表示する" lightbox="../media/grid-show-track-sizes.msft.png":::
   **<span data-ttu-id="a0307-193">トラックのサイズを表示する</span><span class="sxs-lookup"><span data-stu-id="a0307-193">Show track sizes</span></span>**  
:::image-end:::  

### <a name="show-area-names"></a><span data-ttu-id="a0307-194">エリア名の表示</span><span class="sxs-lookup"><span data-stu-id="a0307-194">Show area names</span></span>  

<span data-ttu-id="a0307-195">エリア名を表示するには、[エリア名を表示 **] チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="a0307-195">To view the area names, enable the **Show area names** checkbox.</span></span>  <span data-ttu-id="a0307-196">この例では、グリッドには、上、下**1、** 下 2 の 3 つの\*\*\*\*\*\*領域があります\*\*。</span><span class="sxs-lookup"><span data-stu-id="a0307-196">In the example, there are 3 areas in the grid: **top**, **bottom1** and **bottom2**.</span></span>  

:::image type="complex" source="../media/grid-show-area-names.msft.png" alt-text="エリア名の表示" lightbox="../media/grid-show-area-names.msft.png":::
   **<span data-ttu-id="a0307-198">エリア名の表示</span><span class="sxs-lookup"><span data-stu-id="a0307-198">Show area names</span></span>**  
:::image-end:::  

### <a name="extend-grid-lines"></a><span data-ttu-id="a0307-199">グリッド線を拡張する</span><span class="sxs-lookup"><span data-stu-id="a0307-199">Extend grid lines</span></span>  

<span data-ttu-id="a0307-200">[グリッド線 **の拡張]** チェック ボックスをオンにすると、グリッド線を各軸に沿ってビューポートの端まで拡張できます。</span><span class="sxs-lookup"><span data-stu-id="a0307-200">Enable the **Extend grid lines** checkbox to extend the grid lines to the edge of the viewport along each axis.</span></span>  

:::image type="complex" source="../media/grid-extend-grid-lines.msft.png" alt-text="グリッド線を拡張する" lightbox="../media/grid-extend-grid-lines.msft.png":::
   **<span data-ttu-id="a0307-202">グリッド線を拡張する</span><span class="sxs-lookup"><span data-stu-id="a0307-202">Extend grid lines</span></span>**  
:::image-end:::  

## <a name="grid-overlays"></a><span data-ttu-id="a0307-203">グリッド オーバーレイ</span><span class="sxs-lookup"><span data-stu-id="a0307-203">Grid overlays</span></span>  

<span data-ttu-id="a0307-204">[ **グリッド オーバーレイ] セクション** には、ページ上に存在するグリッドの一覧が含まれる。各グリッドには、さまざまなオプションと共に、チェック ボックスが付きます。</span><span class="sxs-lookup"><span data-stu-id="a0307-204">The **Grid overlays** section contains a list of grids that are present on the page, each with a checkbox, along with various options.</span></span>  

### <a name="enable-overlay-views-of-multiple-grids"></a><span data-ttu-id="a0307-205">複数のグリッドのオーバーレイ ビューを有効にする</span><span class="sxs-lookup"><span data-stu-id="a0307-205">Enable overlay views of multiple grids</span></span>  

<span data-ttu-id="a0307-206">複数のグリッドのオーバーレイ グリッドを表示するには、グリッドの各名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a0307-206">To display the overlay grid for multiple grids, choose the checkbox next to each name of the grid.</span></span>  <span data-ttu-id="a0307-207">この例では、それぞれ異なる色で表される 2 つのグリッド オーバーレイが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="a0307-207">In the example, there are 2 grid overlays enabled that are each represented with different colors.</span></span>  

*   `main`  
*   `div.snack-box`  
    
:::image type="complex" source="../media/grid-grid-overlays.msft.png" alt-text="複数のグリッドのオーバーレイ ビューを有効にする" lightbox="../media/grid-grid-overlays.msft.png":::
   <span data-ttu-id="a0307-209">複数のグリッドのオーバーレイ ビューを有効にする</span><span class="sxs-lookup"><span data-stu-id="a0307-209">Enable overlay views of multiple grids</span></span>  
:::image-end:::  

### <a name="customize-the-grid-overlay-color"></a><span data-ttu-id="a0307-210">グリッド オーバーレイの色をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="a0307-210">Customize the grid overlay color</span></span>  

<span data-ttu-id="a0307-211">カラー ピッカーを開き、グリッド オーバーレイの色をカスタマイズするには、グリッド オーバーレイの名前の横にあるボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="a0307-211">To open the color picker and customize the grid overlay color, choose the box next to the name of the grid overlay.</span></span>  

:::image type="complex" source="../media/grid-grid-overlays-color.msft.png" alt-text="グリッド オーバーレイの色をカスタマイズする" lightbox="../media/grid-grid-overlays-color.msft.png":::
   <span data-ttu-id="a0307-213">グリッド オーバーレイの色をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="a0307-213">Customize the grid overlay color</span></span>  
:::image-end:::  

### <a name="highlight-the-grid"></a><span data-ttu-id="a0307-214">グリッドを強調表示する</span><span class="sxs-lookup"><span data-stu-id="a0307-214">Highlight the grid</span></span>  

<span data-ttu-id="a0307-215">[要素] ツールで\*\*\*\* HTML 要素を強調表示し、Web ページ上でスクロールするには、[要素] パネル**\(** [要素] パネル アイコン \) の [要素の表示] アイコンで [要素の表示] 要素 ![ ](../media/show-element-in-element-panel-icon.msft.png) を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0307-215">To highlight the HTML element in the **Elements** tool and scroll to it on the webpage, choose the **Show element in the Elements panel** \(![Show element in the Elements panel icon](../media/show-element-in-element-panel-icon.msft.png)\) icon.</span></span>  

:::image type="complex" source="../media/grid-grid-overlays-highlight.msft.png" alt-text="グリッドを強調表示する" lightbox="../media/grid-grid-overlays-highlight.msft.png":::
   <span data-ttu-id="a0307-217">グリッドを強調表示する</span><span class="sxs-lookup"><span data-stu-id="a0307-217">Highlight the grid</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="a0307-218">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="a0307-218">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open/index.md "Microsoft Edge DevTools を開く | Microsoft Docs"  

[JecFyiDemoCssGridFruit]: https://jec.fyi/demo/css-grid-fruit "CSS グリッド |jec.fyi"  
[JecFyiDemoCssGridSnack]: https://jec.fyi/demo/css-grid-snack "CSS グリッド |jec.fyi"  

[MdnCssGridLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout "CSS グリッド レイアウト |MDN"  
[MdnLayoutUsingNamedGridLines]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout/Layout_using_Named_Grid_Lines "名前付きグリッド線を使用した|MDN"  
[MdnLineBasedPlacementCssGrid]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout/Line-based_Placement_with_CSS_Grid "CSS Grid を使用した行ベースの配置|MDN"  

> [!NOTE]
> <span data-ttu-id="a0307-225">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="a0307-225">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="a0307-226">[Jecelyn Yeen][JecelynYeen] \(デベロッパー アドボケイト、Chrome DevTools\) によって作成された元のページは[こちら](https://developers.google.com/web/tools/chrome-devtools/css/grid)にあります。</span><span class="sxs-lookup"><span data-stu-id="a0307-226">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/grid) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="a0307-228">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="a0307-228">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors#jecelyn-yeen  
