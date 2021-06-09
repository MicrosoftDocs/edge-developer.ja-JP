---
description: ページ上の [検査] ツールの情報オーバーレイを使用して、既定の状態でテキストの色のコントラストを確認します。このオーバーレイには、コントラスト情報を含むアクセシビリティ セクションがあります。
title: 検査ツールを使用して既定の状態でテキストの色のコントラストを確認する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: ade9fd6d685f6f7cea6311b1645a527ece352a38
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597494"
---
# <a name="check-text-color-contrast-in-the-default-state-using-the-inspect-tool"></a><span data-ttu-id="8f99a-104">検査ツールを使用して既定の状態でテキストの色のコントラストを確認する</span><span class="sxs-lookup"><span data-stu-id="8f99a-104">Check text-color contrast in the default state using the Inspect tool</span></span>

<!-- Inspect tool: information overlay: Accessibility section: Contrast row -->

<span data-ttu-id="8f99a-105">[検査] ツールを使用して、既定の状態でテキストの色のコントラスト **を確認** します。</span><span class="sxs-lookup"><span data-stu-id="8f99a-105">Check text color contrast in the default state by using the **Inspect** tool.</span></span>  <span data-ttu-id="8f99a-106">Web**ページ上**の検査ツールの情報オーバーレイには、コントラスト情報を含む**アクセシビリティ\*\*\*\*セクションがあります**。</span><span class="sxs-lookup"><span data-stu-id="8f99a-106">The **Inspect** tool's information overlay on the webpage has an **Accessibility** section that includes **Contrast** information.</span></span>

<span data-ttu-id="8f99a-107">[検査] ツールの情報オーバーレイを使用して既定の状態のテキストと色のコントラストを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8f99a-107">To check text-color contrast in the default state using the Inspect tool's information overlay, perform the following steps.</span></span>

<!-- Inspect tool -->
<span data-ttu-id="8f99a-108">テキストを含む要素の場合、 **検査** ツールの情報オーバーレイには次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f99a-108">For elements that have text, the **Inspect** tool's information overlay shows the following:</span></span>
*  <span data-ttu-id="8f99a-109">テキストと背景色のコントラスト比。</span><span class="sxs-lookup"><span data-stu-id="8f99a-109">The contrast ratio of text versus background colors.</span></span>
*  <span data-ttu-id="8f99a-110">十分なコントラストを持つ要素の緑色のチェック マーク アイコン。</span><span class="sxs-lookup"><span data-stu-id="8f99a-110">A green check mark icon for elements with enough contrast.</span></span>
*  <span data-ttu-id="8f99a-111">コントラストが十分ではない要素の黄色の警告アイコン。</span><span class="sxs-lookup"><span data-stu-id="8f99a-111">A yellow alert icon for elements that don't have enough contrast.</span></span>

<span data-ttu-id="8f99a-112">場合によっては、ブラウザーを明るいテーマまたは暗いテーマに設定すると、コントラストが影響を受ける場合があります。</span><span class="sxs-lookup"><span data-stu-id="8f99a-112">In some cases, contrast is affected by setting the browser to light theme or dark theme.</span></span>

<span data-ttu-id="8f99a-113">例として、デモ ページでは、サイドバー ナビゲーション メニューの青いリンクのコントラストは十分ですが、[寄附金の\*\*\*\* 状態] セクションの緑色の **[犬**] リンクには十分なコントラストが含めではありません。</span><span class="sxs-lookup"><span data-stu-id="8f99a-113">As an example, on the demo page, the blue links of the sidebar navigation menu have enough contrast, but the green **Dogs** link in the **Donation status** section does not have enough contrast.</span></span>  <span data-ttu-id="8f99a-114">次のように、検査ツールを **使用して** これらの要素を確認します。</span><span class="sxs-lookup"><span data-stu-id="8f99a-114">Review those elements using the **Inspect** tool, as follows:</span></span>

1.  <span data-ttu-id="8f99a-115">アクセシビリティ テスト [のデモ Web ページを新しい][DevToolsA11yErrorsDemopage] タブで開きます。 次に **、[F12] を** 選択して DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="8f99a-115">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab.  Then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="8f99a-116">DevTools **の左上** 隅にある [検査] ボタン \( Inspect button \) ボタンを選択して、アイコンが強調表示 ![ (青) ](../media/inspect-icon.msft.png) にします。</span><span class="sxs-lookup"><span data-stu-id="8f99a-116">Select the **Inspect** \(![Inspect button](../media/inspect-icon.msft.png)\) button in the top-left corner of DevTools so that the icon is highlighted (blue).</span></span>

1.  <span data-ttu-id="8f99a-117">レンダリングされた Web ページで、サイドバー ナビゲーション メニューの青い **Cats** リンクにカーソルを合わせる。</span><span class="sxs-lookup"><span data-stu-id="8f99a-117">In the rendered webpage, hover over the blue **Cats** link of the sidebar navigation menu.</span></span>  <span data-ttu-id="8f99a-118">[ **検査]** ツールの情報オーバーレイが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f99a-118">The **Inspect** tool's information overlay appears.</span></span>  <span data-ttu-id="8f99a-119">情報オーバーレイ **の [アクセシビリティ** ] セクションで、緑のチェックマークが **[** コントラスト] 行に表示され、この要素のテキストの色と背景色のコントラストが十分であることを示します。</span><span class="sxs-lookup"><span data-stu-id="8f99a-119">In the **Accessibility** section of the information overlay, a green checkmark appears on the **Contrast** row, indicating that this element has enough contrast of text color versus background color.</span></span>

    :::image type="complex" source="../media/a11y-testing-enough-contrast.msft.png" alt-text="[検査] ツールに示すように、メニュー項目には十分なコントラストがあります。" lightbox="../media/a11y-testing-enough-contrast.msft.png":::
        <span data-ttu-id="8f99a-121">[検査] ツールに示すように、メニュー項目には十分なコントラストがあります。</span><span class="sxs-lookup"><span data-stu-id="8f99a-121">The menu items have enough contrast, as shown in the Inspect tool</span></span>
    :::image-end:::

1.  <span data-ttu-id="8f99a-122">レンダリングされた Web ページの [寄附状況] **セクション** で、[犬] リンクの上に **マウス ポインターを合** わせる。</span><span class="sxs-lookup"><span data-stu-id="8f99a-122">In the rendered webpage, in the **Donation Status** section, hover over the **Dogs** link.</span></span>  <span data-ttu-id="8f99a-123">[**検査**] ツールの情報オーバーレイには、コントラスト行にオレンジ色\*\*\*\* の感嘆符が表示され、この要素にはテキストと背景色のコントラストが十分に存在しないという点が示されます。</span><span class="sxs-lookup"><span data-stu-id="8f99a-123">The **Inspect** tool's information overlay shows an orange exclamation point on the **Contrast** row, indicating that this element doesn't have enough contrast of text versus background colors.</span></span>

    :::image type="complex" source="../media/a11y-testing-not-enough-contrast.msft.png" alt-text="検査ツールの警告に示すように、コントラストが十分ではない要素" lightbox="../media/a11y-testing-not-enough-contrast.msft.png":::
        <span data-ttu-id="8f99a-125">検査ツールの警告に示すように、コントラストが十分ではない要素</span><span class="sxs-lookup"><span data-stu-id="8f99a-125">An element that doesn't have enough contrast, as shown by the warning in the Inspect tool</span></span>
    :::image-end:::


## <a name="different-options-to-inspect-text-color-contrast-in-devtools"></a><span data-ttu-id="8f99a-126">DevTools でテキストと色のコントラストを検査するためのさまざまなオプション</span><span class="sxs-lookup"><span data-stu-id="8f99a-126">Different options to inspect text-color contrast in DevTools</span></span>

<span data-ttu-id="8f99a-127">テキストの色のコントラストを調するには、次の DevTools 機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="8f99a-127">Use the following DevTools features to inspect text-color contrast.</span></span>

*  <span data-ttu-id="8f99a-128">[検査 **] ツール** (Web ページ上の情報オーバーレイとして) を使用して、個々のページ要素に十分なテキストと色のコントラストが設定されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8f99a-128">Use the **Inspect** tool (as an information overlay on the webpage) to check whether an individual page element has enough text-color contrast.</span></span>  <span data-ttu-id="8f99a-129">検査 **ツール** の情報オーバーレイには、 **コントラスト情報行** を含むアクセシビリティ **セクションが** 含まれます。</span><span class="sxs-lookup"><span data-stu-id="8f99a-129">The **Inspect** tool's information overlay includes an **Accessibility** section that has a **Contrast** information row.</span></span>  <span data-ttu-id="8f99a-130">[ **検査] ツール** には、現在の状態のテキストコントラスト情報だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f99a-130">The **Inspect** tool only shows text-contrast information for the current state.</span></span>  <span data-ttu-id="8f99a-131">この方法については、現在の記事で説明します。</span><span class="sxs-lookup"><span data-stu-id="8f99a-131">This approach is described in the current article.</span></span>

*  <span data-ttu-id="8f99a-132">テキスト **と背景色** のコントラストが十分ではない場合、Issues ツールは Web ページ全体の色コントラストの問題を自動的に報告します。</span><span class="sxs-lookup"><span data-stu-id="8f99a-132">The **Issues** tool automatically reports any color-contrast issues for the entire webpage, when text and background color don't contrast enough.</span></span>  <span data-ttu-id="8f99a-133">この方法については、「テキストの色 [に十分なコントラストが含まれるか確認する」を参照してください](test-issues-tool.md#verify-that-text-colors-have-enough-contrast)。</span><span class="sxs-lookup"><span data-stu-id="8f99a-133">This approach is described in [Verify that text colors have enough contrast](test-issues-tool.md#verify-that-text-colors-have-enough-contrast).</span></span>

*  <span data-ttu-id="8f99a-134">「要素のすべての状態のアクセシビリティを確認する」で説明されているスタイル ウィンドウで Toggle Element State を使用して、状態などの既定以外の状態 `hover` [をエミュレートします](test-inspect-states.md)。 \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8f99a-134">Emulate a non-default state, such as the `hover` state, by using **Toggle Element State** in the **Styles** pane, described in [Verify accessibility of all states of elements](test-inspect-states.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="8f99a-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f99a-135">See also</span></span>

*  [<span data-ttu-id="8f99a-136">要素のすべての状態のアクセシビリティを確認する</span><span class="sxs-lookup"><span data-stu-id="8f99a-136">Verify accessibility of all states of elements</span></span>][DevtoolsAccessibilityTestInspectStates]
*  [<span data-ttu-id="8f99a-137">[検査] ツールを使用して、Web ページの上にカーソルを移動してアクセシビリティの問題を検出する</span><span class="sxs-lookup"><span data-stu-id="8f99a-137">Use the Inspect tool to detect accessibility issues by hovering over the webpage</span></span>](test-inspect-tool.md)
*  [<span data-ttu-id="8f99a-138">DevTools を使用したアクセシビリティ テストの概要</span><span class="sxs-lookup"><span data-stu-id="8f99a-138">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="8f99a-139">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="8f99a-139">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevtoolsAccessibilityTestInspectStates]: test-inspect-states.md "要素のすべての状態のアクセシビリティを確認|Microsoft Docs"
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
