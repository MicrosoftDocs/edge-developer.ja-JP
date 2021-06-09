---
description: Web ページにカーソルを合わせると、アクセシビリティの問題を検出するには、[検査] ツールを使用します。
title: '[検査] ツールを使用して、Web ページの上にカーソルを移動してアクセシビリティの問題を検出する'
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: c95116d38e5b0bda88af43ef8bfde4204b8cb372
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597498"
---
# <a name="use-the-inspect-tool-to-detect-accessibility-issues-by-hovering-over-the-webpage"></a><span data-ttu-id="d3413-104">[検査] ツールを使用して、Web ページの上にカーソルを移動してアクセシビリティの問題を検出する</span><span class="sxs-lookup"><span data-stu-id="d3413-104">Use the Inspect tool to detect accessibility issues by hovering over the webpage</span></span>

<span data-ttu-id="d3413-105">[ **検査]** ツールは、レンダリングされた Web ページにカーソルを合わせると、アクセシビリティ情報を含む個々の要素に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="d3413-105">The **Inspect** tool displays information about individual elements as you hover over the rendered webpage, including accessibility information.</span></span>
<span data-ttu-id="d3413-106">これに対し **、Issues ツールは** Web ページ全体の問題を自動的に報告します。</span><span class="sxs-lookup"><span data-stu-id="d3413-106">In contrast, the **Issues** tool automatically reports issues for the entire webpage.</span></span>

<span data-ttu-id="d3413-107">ツール **の** 検査ボタン \( ![ Inspect ](../media/inspect-icon.msft.png) \) は、DevTools の左上隅にあります。</span><span class="sxs-lookup"><span data-stu-id="d3413-107">The **Inspect** tool button \(![Inspect](../media/inspect-icon.msft.png)\) is in the upper-left corner of DevTools.</span></span>  <span data-ttu-id="d3413-108">[ツールの検査] **ボタンを** 選択すると、ボタンが青に変り、検査ツールがアクティブ **であることを** 示します。</span><span class="sxs-lookup"><span data-stu-id="d3413-108">When you select the **Inspect** tool button, the button turns blue, indicating that the **Inspect** tool is active.</span></span>

<span data-ttu-id="d3413-109">[検査] **ツール** がアクティブな場合、レンダリングされた Web ページ上の任意の要素の上にホバーすると、[検査] オーバーレイが **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="d3413-109">When the **Inspect** tool is active, hovering over any element on the rendered webpage displays the **Inspect** overlay.</span></span> <span data-ttu-id="d3413-110">このオーバーレイには、その要素に関する一般的な情報とアクセシビリティ情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3413-110">This overlay displays general information and accessibility information about that element.</span></span>  <span data-ttu-id="d3413-111">[ **検査] オーバーレイの** [アクセシビリティ] **セクション** には、テキストの色のコントラスト、スクリーン リーダーのテキスト、キーボードのサポートに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3413-111">The **Accessibility** section of the **Inspect** overlay displays information about text-color contrast, screen reader text, and keyboard support.</span></span>

:::image type="complex" source="../media/a11y-testing-basics-inspector-overlay.msft.png" alt-text="要素の領域をマルチカラー オーバーレイとして表示し、要素の詳細を大きな情報オーバーレイとして表示する検査ツール" lightbox="../media/a11y-testing-basics-inspector-overlay.msft.png":::
    <span data-ttu-id="d3413-113">要素 **の** 領域をマルチカラー オーバーレイとして表示し、要素の詳細を大きな情報オーバーレイとして表示する検査ツール</span><span class="sxs-lookup"><span data-stu-id="d3413-113">The **Inspect** tool, showing the element's area as a multicolor overlay, and showing the element's details as a large information overlay</span></span>
:::image-end:::


## <a name="check-individual-elements-for-text-contrast-screen-reader-text-and-keyboard-support"></a><span data-ttu-id="d3413-114">テキストのコントラスト、スクリーン リーダーのテキスト、キーボードのサポートについて個々の要素を確認する</span><span class="sxs-lookup"><span data-stu-id="d3413-114">Check individual elements for text contrast, screen reader text, and keyboard support</span></span>

<!-- Inspect tool: Accessibility section of overlay -->

1.  <span data-ttu-id="d3413-115">ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="d3413-115">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="d3413-116">アイコンが **強調表示** (青) の場合は、DevTools の左上隅にある [検査\( Inspect \) ] ![ ](../media/inspect-icon.msft.png) ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="d3413-116">Select the **Inspect** \(![Inspect](../media/inspect-icon.msft.png)\) button in the top-left corner of DevTools so that the icon is highlighted (blue).</span></span>

    :::image type="complex" source="../media/a11y-testing-basics-inspector.msft.png" alt-text="[検査] ツールを有効にする場合は、[検査] ボタン" lightbox="../media/a11y-testing-basics-inspector.msft.png":::
        <span data-ttu-id="d3413-118">[検査] ツールを **有効にする** 場合は、[ **検査]** ボタン</span><span class="sxs-lookup"><span data-stu-id="d3413-118">To turn on the **Inspect** tool, select the **Inspect** button</span></span>
    :::image-end:::

1.  <span data-ttu-id="d3413-119">レンダリングされたデモ Web ページの任意の要素にカーソルを合わせる。</span><span class="sxs-lookup"><span data-stu-id="d3413-119">Hover over any element in the rendered demo webpage.</span></span>  <span data-ttu-id="d3413-120">[ **検査]** ツールは、レンダリングされた Web ページ内の要素の下に情報オーバーレイを表示します。</span><span class="sxs-lookup"><span data-stu-id="d3413-120">The **Inspect** tool shows an information overlay below the element within the rendered webpage.</span></span>

    :::image type="complex" source="../media/a11y-testing-basics-inspector-overlay.msft.png" alt-text="要素のレイアウトをマルチカラー オーバーレイとして表示し、要素の詳細を大きな情報オーバーレイとして表示する検査ツール" lightbox="../media/a11y-testing-basics-inspector-overlay.msft.png":::
        <span data-ttu-id="d3413-122">要素 **の** レイアウトをマルチカラー オーバーレイとして表示し、要素の詳細を大きな情報オーバーレイとして表示する検査ツール</span><span class="sxs-lookup"><span data-stu-id="d3413-122">The **Inspect** tool, showing the element's layout as a multicolor overlay, and showing the element's details as a large information overlay</span></span>
    :::image-end:::

<span data-ttu-id="d3413-123">Inspect オーバーレイの下部 **には、** 次の情報を含む **アクセシビリティ** セクションがあります。</span><span class="sxs-lookup"><span data-stu-id="d3413-123">The bottom part of the **Inspect** overlay has an **Accessibility** section that contains the following information:</span></span>

*   <span data-ttu-id="d3413-124">**コントラスト** は、低ビジョンのユーザーが要素を理解できるかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="d3413-124">**Contrast** defines whether an element can be understood by people with low vision.</span></span>  <span data-ttu-id="d3413-125">[WCAG ガイドライン][WCAG]で定義されているコントラスト比は、十分なコントラスト (緑色のチェック マーク アイコン) または十分ではない (オレンジ色の感嘆符アイコン) かどうかを示します。 [][W3CContrastRatio]</span><span class="sxs-lookup"><span data-stu-id="d3413-125">The [contrast ratio][W3CContrastRatio] as defined by the [WCAG Guidelines][WCAG] indicates whether there is enough contrast (a green check mark icon) or not enough (an orange exclamation-point icon).</span></span>

*   <span data-ttu-id="d3413-126">**名前** と **役割は** 、スクリーン リーダーなどの支援テクノロジが要素について報告する機能です。</span><span class="sxs-lookup"><span data-stu-id="d3413-126">**Name** and **Role** are what assistive technology such as screen readers will report about the element.</span></span>
    *   <span data-ttu-id="d3413-127">Name **は** 、要素のテキスト コンテンツ `a` です。</span><span class="sxs-lookup"><span data-stu-id="d3413-127">The **Name** is the text content of an `a` element.</span></span>  <span data-ttu-id="d3413-128">要素の場合 `<a href="/">About Us</a>` 、 **検査ツールに** 表示される名前は "About Us" です。</span><span class="sxs-lookup"><span data-stu-id="d3413-128">For the element `<a href="/">About Us</a>`, the **Name** shown in the Inspect tool is "About Us".</span></span>
    *   <span data-ttu-id="d3413-129">要素**の Role。**</span><span class="sxs-lookup"><span data-stu-id="d3413-129">The **Role** of the element.</span></span>  <span data-ttu-id="d3413-130">これは、通常、要素名です `article` `img` 。、、 `link` `heading` などです。</span><span class="sxs-lookup"><span data-stu-id="d3413-130">This is usually the element name, such as `article`, `img` , `link`, or `heading`.</span></span>  <span data-ttu-id="d3413-131">要素 `div` と `span` を . と呼ばれます `generic` 。</span><span class="sxs-lookup"><span data-stu-id="d3413-131">The `div` and `span` elements are referred to as `generic`.</span></span>

*   <span data-ttu-id="d3413-132">**キーボードフォーカス可能は** 、ユーザーが入力デバイスに関係なく要素に到達できるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d3413-132">**Keyboard-focusable** indicates whether users can reach the element regardless of input device.</span></span>
    *   <span data-ttu-id="d3413-133">緑色のチェック マーク アイコンは、要素がキーボードフォーカス可能な状態を示します。</span><span class="sxs-lookup"><span data-stu-id="d3413-133">A green check mark icon indicates that the element is keyboard-focusable.</span></span>
    *   <span data-ttu-id="d3413-134">斜めの線が付く灰色の円は、要素がキーボードフォーカス可能でなかったかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d3413-134">A gray circle with diagonal line indicates that the element isn't keyboard-focusable.</span></span>


## <a name="additional-information-in-the-inspect-overlay"></a><span data-ttu-id="d3413-135">[検査] オーバーレイの追加情報</span><span class="sxs-lookup"><span data-stu-id="d3413-135">Additional information in the Inspect overlay</span></span>

<!-- general info about the Inspect tool, not particularly focused on accessibility -->

<span data-ttu-id="d3413-136">[ユーザー補助]**セクションの**上にある Inspect\*\*\*\* オーバーレイの上部には、要素の次の詳細が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3413-136">The top part of the **Inspect** overlay, which is above the **Accessibility** section, lists the following details of the element.</span></span>

*   <span data-ttu-id="d3413-137">レイアウトの種類。</span><span class="sxs-lookup"><span data-stu-id="d3413-137">Layout type.</span></span> <span data-ttu-id="d3413-138">要素が flexbox またはグリッドを使用して配置されている場合、アイコン \(</span><span class="sxs-lookup"><span data-stu-id="d3413-138">If the element is positioned using a flexbox or grid, an icon \(</span></span>![グリッド レイアウト アイコン](../media/grid-icon.msft.png)<span data-ttu-id="d3413-140">\) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3413-140">\) is displayed.</span></span>
*   <span data-ttu-id="d3413-141">要素の名前 (、 `h1` `h2` `div` など)。</span><span class="sxs-lookup"><span data-stu-id="d3413-141">Name of the element, such as `h1`, `h2`, or `div`.</span></span>
*   <span data-ttu-id="d3413-142">要素のサイズをピクセル単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="d3413-142">The dimensions of the element in pixels.</span></span>
*   <span data-ttu-id="d3413-143">色見本 (または小さな色付き四角形) として、文字列 (など) としての色 `#336699` 。</span><span class="sxs-lookup"><span data-stu-id="d3413-143">The color as a color swatch (or a small, colored square) and as a string (such as `#336699`).</span></span>
*   <span data-ttu-id="d3413-144">サイズやフォント ファミリなどのフォント情報。</span><span class="sxs-lookup"><span data-stu-id="d3413-144">Font information, such as size and font families.</span></span>
*   <span data-ttu-id="d3413-145">余白とパディング (ピクセル単位)。</span><span class="sxs-lookup"><span data-stu-id="d3413-145">Margin and padding in pixels.</span></span>


## <a name="identify-nested-regions-using-color-highlighting"></a><span data-ttu-id="d3413-146">色の強調表示を使用して入れ子になった領域を識別する</span><span class="sxs-lookup"><span data-stu-id="d3413-146">Identify nested regions using color highlighting</span></span> 

<!-- general info about the Inspect tool, not particularly focused on accessibility -->

<span data-ttu-id="d3413-147">情報オーバーレイに加えて **、Inspect** ツールには、Elements ツールの DOM ツリーでのホバーに似た領域の色 **付けも提供** されます。</span><span class="sxs-lookup"><span data-stu-id="d3413-147">In addition to the information overlay, the **Inspect** tool also provides region-coloring that's similar to hovering in the DOM tree in the **Elements** tool.</span></span>

1.  <span data-ttu-id="d3413-148">ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="d3413-148">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="d3413-149">DevTools **の左上** 隅にある [検査] ボタン \( Inspect tool icon \) を選択して、ボタンが強調表示 ![ (青) ](../media/inspect-icon.msft.png) にします。</span><span class="sxs-lookup"><span data-stu-id="d3413-149">Select the **Inspect** button \(![Inspect tool icon](../media/inspect-icon.msft.png)\) in the top-left corner of DevTools, so that the button is highlighted (blue).</span></span>

1.  <span data-ttu-id="d3413-150">レンダリングされたデモ Web ページの別の部分にカーソルを合わせる。</span><span class="sxs-lookup"><span data-stu-id="d3413-150">Hover over different parts of the rendered demo webpage.</span></span>  <span data-ttu-id="d3413-151">Web ページ内の各要素が複数色のオーバーレイで表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3413-151">Each element in the webpage now displays with a multicolor overlay.</span></span> <span data-ttu-id="d3413-152">この複数色のオーバーレイは、要素内の入れ子になった領域を表示できます。</span><span class="sxs-lookup"><span data-stu-id="d3413-152">This multicolor overlay can display nested regions inside of an element.</span></span> <span data-ttu-id="d3413-153">たとえば、Cats の左余白にカーソルを **合わせるとします**。</span><span class="sxs-lookup"><span data-stu-id="d3413-153">For example, hover over the left margin of **Cats**.</span></span>  <span data-ttu-id="d3413-154">[ **検査]** ツールは、さまざまな色で **[Cats]** セクションのいくつかの四角形の部分を強調表示し、Web ページの CSS フレックスボックス定義の結果として得られたレイアウトを示します。</span><span class="sxs-lookup"><span data-stu-id="d3413-154">The **Inspect** tool highlights several rectangular portions of the **Cats** section with different colors, showing the layout that results from the CSS flexbox definitions on your webpage.</span></span>

:::image type="complex" source="../media/inspect-tool-flexbox-overlay.msft.png" alt-text="検査ツールを使用する場合のマルチカラー フレックスボックス オーバーレイと情報オーバーレイ" lightbox="../media/inspect-tool-flexbox-overlay.msft.png":::
    <span data-ttu-id="d3413-156">検査ツールを使用する場合のマルチカラー フレックスボックス オーバーレイと情報**オーバーレイ**</span><span class="sxs-lookup"><span data-stu-id="d3413-156">Multicolor flexbox overlay and information overlay when using the **Inspect** tool</span></span>
:::image-end:::

<span data-ttu-id="d3413-157">グリッド オーバーレイまたはフレックスボックス オーバーレイを構成するには、[ **要素** ] ツールで 、[レイアウト] タブ **を選択** します。 詳細については、「CSS グリッドの検査 [」に移動します](..\css\grid.md)。</span><span class="sxs-lookup"><span data-stu-id="d3413-157">To configure the grid overlay or flexbox overlay, in the **Elements** tool, select the **Layout** tab.  For more information, navigate to [Inspect CSS Grid](..\css\grid.md).</span></span>


## <a name="use-the-inspect-tool-to-hover-over-the-webpage-to-highlight-the-dom-and-css"></a><span data-ttu-id="d3413-158">[検査] ツールを使用して Web ページにカーソルを合わせると、DOM と CSS が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3413-158">Use the Inspect tool to hover over the webpage to highlight the DOM and CSS</span></span>

<!-- general info about the Inspect tool, not particularly focused on accessibility -->

1.  <span data-ttu-id="d3413-159">ブラウザーの [新しいタブでアクセシビリティ テストデモ Web][DevToolsA11yErrorsDemopage] ページを開き **、F12** を選択して DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="d3413-159">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser, and then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="d3413-160">DevTools **の左上** 隅にある [検査] ボタン \( Inspect tool \) を選択して、ボタンが強調表示 ![ (青) ](../media/inspect-icon.msft.png) にします。</span><span class="sxs-lookup"><span data-stu-id="d3413-160">Select the **Inspect** button \(![the Inspect tool](../media/inspect-icon.msft.png)\) in the top-left corner of DevTools, so that the button is highlighted (blue).</span></span>

1.  <span data-ttu-id="d3413-161">[要素] **ツールを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="d3413-161">Select the **Elements** tool.</span></span>

1.  <span data-ttu-id="d3413-162">[検査 **] ツール** がアクティブな状態で、レンダリングされた Web ページの別の部分にカーソルを合わせる。</span><span class="sxs-lookup"><span data-stu-id="d3413-162">With the **Inspect** tool active, hover over different parts of the rendered webpage.</span></span>  <span data-ttu-id="d3413-163">要素ツール **では** 、HTML DOM ツリーが自動的に展開され、カーソルを移動した要素に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3413-163">In the **Elements** tool, the HTML DOM tree automatically expands to show information about the element you hover over.</span></span>  <span data-ttu-id="d3413-164">ホバーしても、[スタイル] ウィンドウ **は** 更新されません。</span><span class="sxs-lookup"><span data-stu-id="d3413-164">Hovering doesn't cause the **Styles** pane to update.</span></span>

1.  <span data-ttu-id="d3413-165">レンダリングされた Web ページ内の任意の要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3413-165">Now select any element within the rendered webpage.</span></span>  <span data-ttu-id="d3413-166">要素 **ツールが** 自動的に開き、DOM ツリーに要素の HTML が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3413-166">The **Elements** tool automatically opens and displays the HTML of the element in the DOM tree.</span></span> <span data-ttu-id="d3413-167">ツールは、[スタイル] ウィンドウの要素に適用された CSS も **表示** します。</span><span class="sxs-lookup"><span data-stu-id="d3413-167">The tool also displays the applied CSS on the element in the **Styles** pane.</span></span>  <span data-ttu-id="d3413-168">レンダリングされた Web ページで要素を選択すると、[検査] ツールが **オフ** になります。</span><span class="sxs-lookup"><span data-stu-id="d3413-168">Selecting an element on the rendered webpage turns off the **Inspect** tool.</span></span>

:::image type="complex" source="../media/a11y-testing-basics-inspector-selected-element.msft.png" alt-text="選択した要素の詳細が [要素] ツールに表示されます。" lightbox="../media/a11y-testing-basics-inspector-selected-element.msft.png":::
    <span data-ttu-id="d3413-170">選択した要素の詳細が [要素] ツール **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="d3413-170">Details about the selected element are displayed in the **Elements** tool</span></span>
:::image-end:::

<span data-ttu-id="d3413-171">レンダリングされたページで要素を選択したら、[アクセシビリティ] タブ ([スタイル] タブの近\*\*\*\* く) を使用して\*\*\*\* アクセシビリティ ツリーを表示し、ソースオーダー ビューアーを**使用できます**。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="d3413-171">After selecting an element in the rendered page, you could then use the **Accessibility** tab (near the **Styles** tab) to view the **Accessibility Tree** and use the **Source Order Viewer**.</span></span>


## <a name="see-also"></a><span data-ttu-id="d3413-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3413-172">See also</span></span>

*  [<span data-ttu-id="d3413-173">ノードの検査</span><span class="sxs-lookup"><span data-stu-id="d3413-173">Inspect a node</span></span>](../dom/index.md#inspect-a-node)
*  [<span data-ttu-id="d3413-174">検査ツールを使用して既定の状態でテキストの色のコントラストを確認する</span><span class="sxs-lookup"><span data-stu-id="d3413-174">Check text-color contrast in the default state using the Inspect tool</span></span>](test-inspect-text-contrast.md)
*  [<span data-ttu-id="d3413-175">DevTools を使用したアクセシビリティ テストの概要</span><span class="sxs-lookup"><span data-stu-id="d3413-175">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="d3413-176">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="d3413-176">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
[W3CContrastRatio]: https://www.w3.org/TR/WCAG21/#dfn-contrast-ratio "コントラスト比|W3C"
[WCAG]: https://www.w3.org/TR/WCAG21/ "Web コンテンツ アクセシビリティ ガイドライン |W3C"
