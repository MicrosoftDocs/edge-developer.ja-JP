---
description: '[要素の状態の切り替え] を使用して、[スタイル] ウィンドウで、ホバー状態の間のテキストのコントラストなど、要素のすべての状態のアクセシビリティを検査します。'
title: 要素のすべての状態のアクセシビリティを確認する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 129a89f94925de24a4e649bd91f513de031d6b4a
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597524"
---
# <a name="verify-accessibility-of-all-states-of-elements"></a><span data-ttu-id="83824-104">要素のすべての状態のアクセシビリティを確認する</span><span class="sxs-lookup"><span data-stu-id="83824-104">Verify accessibility of all states of elements</span></span>

<!-- 5. STYLES: TOGGLE STATE -->

<span data-ttu-id="83824-105">状態中のテキストの色のコントラストなど、要素のすべての状態のアクセシビリティを確認 `hover` します。</span><span class="sxs-lookup"><span data-stu-id="83824-105">Check the accessibility of all states of elements, such as text color contrast during the `hover` state.</span></span>  <span data-ttu-id="83824-106">検査 **ツールは** 、一度に 1 つの状態のアクセシビリティの問題を報告します。</span><span class="sxs-lookup"><span data-stu-id="83824-106">The **Inspect** tool reports accessibility issues for one state at a time.</span></span>  <span data-ttu-id="83824-107">要素のさまざまな状態のアクセシビリティを確認するには、[スタイル] タブ\*\*\*\* で、この記事で説明するように**\:hov** (**Toggle Element State**) を選択します。</span><span class="sxs-lookup"><span data-stu-id="83824-107">To check accessibility of the various states of elements, in the **Styles** tab, select **\:hov** (**Toggle Element State**), as described in this article.</span></span> <span data-ttu-id="83824-108">まず、[検査] ツールを使用して状態\*\*\*\* シミュレーションが必要な理由を示し、次に状態シミュレーションの使い方を示します。</span><span class="sxs-lookup"><span data-stu-id="83824-108">We first show why state simulation is necessary using the **Inspect** tool, and then we show how to use state simulation.</span></span>


## <a name="checking-text-color-contrast-in-the-default-state"></a><span data-ttu-id="83824-109">既定の状態でテキストの色のコントラストを確認する</span><span class="sxs-lookup"><span data-stu-id="83824-109">Checking text color contrast in the default state</span></span>

<!-- Inspect tool: information overlay: Accessibility section: Contrast row -->

<span data-ttu-id="83824-110">[問題] ツールの色コントラストの自動テスト\*\*\*\* に加えて、[検査] ツールを\*\*\*\* 使用して、個々のページ要素のコントラストが十分かどうかを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="83824-110">In addition to the automatic color-contrast tests in the **Issues** tool, you can also use the **Inspect** tool to check whether individual page elements have enough contrast.</span></span>  <span data-ttu-id="83824-111">コントラスト情報を使用できる場合は、[ **検査** ] オーバーレイにコントラスト比とチェック ボックス項目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="83824-111">If contrast information is available, the **Inspect** overlay shows the contrast ratio and a checkbox item.</span></span>  <span data-ttu-id="83824-112">緑色のチェック マーク アイコンは十分なコントラストを示し、黄色の警告アイコンはコントラストが十分でなかったと示します。</span><span class="sxs-lookup"><span data-stu-id="83824-112">A green check mark icon indicates there's enough contrast, and a yellow alert icon indicates that there's not enough contrast.</span></span>

<span data-ttu-id="83824-113">たとえば、サイドバーのナビゲーション メニューのリンクには十分なコントラストがあります。</span><span class="sxs-lookup"><span data-stu-id="83824-113">For example, the links in the sidebar navigation menu have enough contrast.</span></span>  <span data-ttu-id="83824-114">ただし、[寄附金**の**状態] セクションの緑色の **[** 犬] リスト アイテムには十分なコントラストが存在しないので、[検査] オーバーレイで警告が**表示されます。**</span><span class="sxs-lookup"><span data-stu-id="83824-114">But the green **Dogs** list item in the **Donation status** section doesn't have enough contrast, and so is flagged by a warning in the **Inspect** overlay.</span></span>

:::row:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-enough-contrast.msft.png" alt-text="[検査] オーバーレイに示すように、サイドバー ナビゲーション メニューのリンクには十分なコントラストがあります。" lightbox="../media/a11y-testing-enough-contrast.msft.png":::
            <span data-ttu-id="83824-116">[検査] オーバーレイに示すように、サイドバー ナビゲーション メニューのリンクには十分なコントラスト **があります** 。</span><span class="sxs-lookup"><span data-stu-id="83824-116">The links in the sidebar navigation menu have enough contrast, as shown in the **Inspect** overlay</span></span> :::image-end:::
    :::column-end:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-not-enough-contrast.msft.png" alt-text="十分なコントラストを持つ要素は、Inspect オーバーレイの警告によってフラグが設定されます。" lightbox="../media/a11y-testing-not-enough-contrast.msft.png":::
            <span data-ttu-id="83824-118">十分なコントラストを持つ要素は、Inspect オーバーレイの警告によって **フラグが設定** されます。</span><span class="sxs-lookup"><span data-stu-id="83824-118">An element that doesn't have enough contrast is flagged by a warning in the **Inspect** overlay</span></span> :::image-end:::
    :::column-end:::
:::row-end:::
        

## <a name="hovering-when-the-inspect-tool-is-active-doesnt-show-the-text-color-contrast-for-the-hover-state"></a><span data-ttu-id="83824-119">[検査] ツールがアクティブなときにホバーしても、ホバー状態のテキストと色のコントラストが表示される</span><span class="sxs-lookup"><span data-stu-id="83824-119">Hovering when the Inspect tool is active doesn't show the text-color contrast for the hover state</span></span>

<span data-ttu-id="83824-120">検査 **ツールの** 情報オーバーレイは、1 つの状態のみを表します。</span><span class="sxs-lookup"><span data-stu-id="83824-120">The **Inspect** tool's information overlay only represents a single state.</span></span>  <span data-ttu-id="83824-121">ページ上の要素の状態は異なる場合があります。そのすべてがテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="83824-121">Elements on the page can have different states, all of which need to be tested.</span></span>  <span data-ttu-id="83824-122">たとえば、アクセシビリティ テストデモ ページのメニューの上にマウス ポインターを置くと、色を変更するアニメーションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="83824-122">For example, when you hover the mouse pointer over the menu of the accessibility-testing demo page, you get an animation that changes the colors.</span></span> <span data-ttu-id="83824-123">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="83824-123">Perform the following steps.</span></span>

1.  <span data-ttu-id="83824-124">アクセシビリティ テスト [のデモ Web ページを新しい][DevToolsA11yErrorsDemopage] タブで開きます。</span><span class="sxs-lookup"><span data-stu-id="83824-124">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab.</span></span>

1.  <span data-ttu-id="83824-125">サイドバーのナビゲーション メニューの青いメニュー項目にカーソルを合わせる。</span><span class="sxs-lookup"><span data-stu-id="83824-125">Hover over the blue menu items in the sidebar navigation menu.</span></span>  <span data-ttu-id="83824-126">各アイテムにアニメーションが含めら注意してください。</span><span class="sxs-lookup"><span data-stu-id="83824-126">Notice that each item has an animation.</span></span>

    :::image type="complex" source="../media/a11y-testing-hover.msft.png" alt-text="マウス ポインターがマウス ポインターの上にあるとき、異なる色を示すメニュー項目" lightbox="../media/a11y-testing-hover.msft.png":::
        <span data-ttu-id="83824-128">マウス ポインターがマウス ポインターの上にあるとき、異なる色を示すメニュー項目</span><span class="sxs-lookup"><span data-stu-id="83824-128">The menu item showing different colors when the mouse pointer is over it</span></span>
    :::image-end:::
    
<span data-ttu-id="83824-129">次に、[検査] ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="83824-129">Now, use the Inspect tool.</span></span> <span data-ttu-id="83824-130">[検査] ツールを使用すると、メニュー項目の上にマウス ポインターを置くと、メニュー項目のアニメーションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="83824-130">When the Inspect tool is used, animations on the menu items won't run when you hover over them.</span></span>  <span data-ttu-id="83824-131">[検査] ツールを使用すると、スタイルの状態がトリガーされないので、コントラスト比をテストするためにメニュー項目の状態に `hover` `hover` 到達できない。</span><span class="sxs-lookup"><span data-stu-id="83824-131">When using the Inspect tool, you can't reach the `hover` state on menu items to test the contrast ratio, because the `hover` state in your styles isn't triggered.</span></span>  
    
<span data-ttu-id="83824-132">アニメーションが実行されていないことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="83824-132">To confirm that your animations don't run, perform the following steps.</span></span>
    
1.  <span data-ttu-id="83824-133">DevTools **の左上隅** にある [検査] ボタン \( [検査] ボタン \) を選択して、アイコンが ![ 強調表示 (青) ](../media/inspect-icon.msft.png) にします。</span><span class="sxs-lookup"><span data-stu-id="83824-133">Select the **Inspect** \(![the Inspect button](../media/inspect-icon.msft.png)\) button in the top-left corner of DevTools so that the icon is highlighted (blue).</span></span>

1.  <span data-ttu-id="83824-134">サイドバーのナビゲーション メニューの青いリンクにカーソルを合わせる。</span><span class="sxs-lookup"><span data-stu-id="83824-134">Hover over the blue links on the sidebar navigation menu.</span></span>  <span data-ttu-id="83824-135">メニュー項目のアニメーションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="83824-135">The animations for the menu items don't run.</span></span> <span data-ttu-id="83824-136">代わりに、メニュー項目は、flexbox オーバーレイの色と強調表示を使用して表示されます。</span><span class="sxs-lookup"><span data-stu-id="83824-136">Instead, the menu items are displayed using colors and highlights for the flexbox overlay.</span></span>

<span data-ttu-id="83824-137">ページ上の要素の状態が異なる可能性があるため、十分なテキストのコントラストを確認するには、この方法では十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="83824-137">Checking for sufficient text contrast this way isn't enough, because the elements on the page could have different states.</span></span>


## <a name="use-state-simulation-to-simulate-the-hover-state-of-an-animated-menu-item"></a><span data-ttu-id="83824-138">状態シミュレーションを使用して、アニメーションメニュー項目のホバー状態をシミュレートする</span><span class="sxs-lookup"><span data-stu-id="83824-138">Use state simulation to simulate the hover state of an animated menu item</span></span> 

<!-- Elements tool: Styles pane: Toggle Element State -->

<span data-ttu-id="83824-139">[検査 **]** ツールがアクティブな場合は、アニメーション要素の上にカーソルを置く代わりに、メニュー項目の状態をシミュレートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="83824-139">When the **Inspect** tool is active, instead of hovering over an animated element, you need to simulate the state of the menu item.</span></span>  <span data-ttu-id="83824-140">メニュー 項目の状態をシミュレートするには、[スタイル] ウィンドウの状態シミュレーション **を使用** します。</span><span class="sxs-lookup"><span data-stu-id="83824-140">To simulate the state of a menu item, use the state simulation in the **Styles** pane.</span></span>  <span data-ttu-id="83824-141">[ **スタイル]** ウィンドウには **\:hov** (**要素**の状態の切り替え) ボタンが表示され、Force 要素の状態というラベルが付いたチェック ボックスのグループ **が表示されます**。</span><span class="sxs-lookup"><span data-stu-id="83824-141">The **Styles** pane has a **\:hov** (**Toggle Element State**) button, which displays a group of checkboxes labeled **Force element state**.</span></span>

<span data-ttu-id="83824-142">[検査] ツールを使用している間にホバー状態を有効にする方法は次の方法です。</span><span class="sxs-lookup"><span data-stu-id="83824-142">To turn on the hover state while using the Inspect tool:</span></span>

1.  <span data-ttu-id="83824-143">まだ開いていない場合は、アクセシビリティ テストのデモ Web ページを [新しいタブ][DevToolsA11yErrorsDemopage] で開きます。 次に **、[F12] を** 選択して DevTools を開きます。</span><span class="sxs-lookup"><span data-stu-id="83824-143">If it's not open already, open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab.  Then select **F12** to open DevTools.</span></span>

1.  <span data-ttu-id="83824-144">DevTools **の左上隅** にある [ツールの検査] ボタン \( Inspect tool button \) を選択して、アイコンが強調表示 ![ ](../media/inspect-icon.msft.png) (青) にします。</span><span class="sxs-lookup"><span data-stu-id="83824-144">Select the **Inspect** \(![Inspect tool button](../media/inspect-icon.msft.png)\) button in the top-left corner of DevTools so that the icon is highlighted (blue).</span></span>

1.  <span data-ttu-id="83824-145">表示された Web ページで、サイドバーのナビゲーション メニューで青い **Cats** リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="83824-145">In the rendered webpage, select the blue **Cats** link in the sidebar navigation menu.</span></span>  <span data-ttu-id="83824-146">要素 **ツールが** 開き、要素が `<a href="#cats">Cats</a>` 選択されます。</span><span class="sxs-lookup"><span data-stu-id="83824-146">The **Elements** tool opens, with the element `<a href="#cats">Cats</a>` selected.</span></span>

    :::image type="complex" source="../media/a11y-testing-inspecting-link-to-hover.msft.png" alt-text="要素ツールでホバー状態を持つ要素を検査する" lightbox="../media/a11y-testing-inspecting-link-to-hover.msft.png":::
        <span data-ttu-id="83824-148">要素ツールでホバー状態を持つ要素を検査する</span><span class="sxs-lookup"><span data-stu-id="83824-148">Inspecting the element that has a hover state in the Elements tool</span></span>
    :::image-end:::

1.  <span data-ttu-id="83824-149">[スタイル] **タブを選択** します。 選択した要素には、CSS に適用される状態がありますが、[スタイル] ウィンドウ `a` `hover` には **表示** されません。</span><span class="sxs-lookup"><span data-stu-id="83824-149">Select the **Styles** tab.  The selected `a` element has a `hover` state in the CSS that is applied to it, but that's not visible in the **Styles** pane.</span></span> 

1.  <span data-ttu-id="83824-150">[スタイル **] ウィンドウ** で、スタイル ルールの右側にある `#sidebar nav li a` リンクを選択 `styles.css` します。</span><span class="sxs-lookup"><span data-stu-id="83824-150">In the **Styles** pane, to the right of the style rule `#sidebar nav li a`, select the `styles.css` link.</span></span>  <span data-ttu-id="83824-151">[ **ソース] ツールが** 開きます。</span><span class="sxs-lookup"><span data-stu-id="83824-151">The **Sources** tool opens.</span></span>  <span data-ttu-id="83824-152">次に、CSS 擬似クラス ルールを検索します `#sidebar nav li a:hover` 。</span><span class="sxs-lookup"><span data-stu-id="83824-152">Then find the CSS pseudo-class rule `#sidebar nav li a:hover`.</span></span>  <span data-ttu-id="83824-153">このルールは、検査ツールがアクティブ **な場合** は実行されません。</span><span class="sxs-lookup"><span data-stu-id="83824-153">This rule doesn't run when the **Inspect** tool is active.</span></span>  <span data-ttu-id="83824-154">次の手順で、この状態ルールの実行をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="83824-154">We'll simulate running this state rule in the next steps.</span></span>

1.  <span data-ttu-id="83824-155">[要素] **ツールを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="83824-155">Select the **Elements** tool.</span></span>  <span data-ttu-id="83824-156">次に、[スタイル] **ウィンドウ** で **、[:hov] (** 要素の状態の切り替え)**ボタンを**選択します。</span><span class="sxs-lookup"><span data-stu-id="83824-156">Then in the **Styles** pane, select the **:hov** (**Toggle Element State**) button.</span></span>  <span data-ttu-id="83824-157">チェック **ボックスの Force 要素** の状態グループが表示されます。</span><span class="sxs-lookup"><span data-stu-id="83824-157">The **Force element state** group of checkboxes is displayed.</span></span>

    :::image type="complex" source="../media/a11y-testing-state-simulation.msft.png" alt-text="すべてのオプションを表示する状態シミュレーション ツール" lightbox="../media/a11y-testing-state-simulation.msft.png":::
        <span data-ttu-id="83824-159">すべてのオプションを表示する状態シミュレーション ツール</span><span class="sxs-lookup"><span data-stu-id="83824-159">The state simulation tool showing all the options</span></span>
    :::image-end:::

1.  <span data-ttu-id="83824-160">**[:hover] チェック ボックスを**オンにします。</span><span class="sxs-lookup"><span data-stu-id="83824-160">Select the **:hover** checkbox.</span></span>  <span data-ttu-id="83824-161">DOM では、要素の左側に黄色のドットが表示され、要素がシミュレートされた状態 `<a href="#cats">Cats</a>` であることを示します。</span><span class="sxs-lookup"><span data-stu-id="83824-161">In the DOM, to the left of the element `<a href="#cats">Cats</a>`, a yellow dot appears, indicating that the element has a simulated state.</span></span>  <span data-ttu-id="83824-162">[ **キャッツ** ] メニュー項目が、ポインターをホバーした場合と同様に Web ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="83824-162">The **Cats** menu item now appears in the webpage as if the pointer were hovering over it.</span></span>  <span data-ttu-id="83824-163">メニュー項目のアニメーションが実行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="83824-163">The animation on the menu item might run.</span></span>

    :::image type="complex" source="../media/a11y-testing-hover-simulated.msft.png" alt-text="ホバー状態をシミュレートする DevTools" lightbox="../media/a11y-testing-hover-simulated.msft.png":::
        <span data-ttu-id="83824-165">ホバー状態をシミュレートする DevTools</span><span class="sxs-lookup"><span data-stu-id="83824-165">DevTools simulating a hover state</span></span>
    :::image-end:::

    <span data-ttu-id="83824-166">シミュレートされた状態を適用した後、次のように、もう\*\*\*\* 一度[検査] ツールを使用して、ユーザーが上にカーソルを置いた場合の要素のコントラストを確認できます。</span><span class="sxs-lookup"><span data-stu-id="83824-166">After the simulated state is applied, you can use the **Inspect** tool again to check the contrast of the element when the user hovers over it, as follows.</span></span>

1.  <span data-ttu-id="83824-167">DevTools **の左上隅** にある [検査] \( Inspector icon \) ボタンを選択して、アイコンが強調表示 ![ ](../media/inspect-icon.msft.png) (青) にします。</span><span class="sxs-lookup"><span data-stu-id="83824-167">Select the **Inspect** \(![Inspector icon](../media/inspect-icon.msft.png)\) button in the top-left corner of DevTools so that the icon is highlighted (blue).</span></span>

1.  <span data-ttu-id="83824-168">サイドバーのナビゲーション メニューの青 **い Cats** リンクの上にカーソルを合わせる。</span><span class="sxs-lookup"><span data-stu-id="83824-168">Hover over the blue **Cats** link in the sidebar navigation menu.</span></span>  <span data-ttu-id="83824-169">シミュレートされたホバー アニメーションのため、リンクは薄い青色になります。</span><span class="sxs-lookup"><span data-stu-id="83824-169">The link is now light blue, because of the simulated hover animation.</span></span>  <span data-ttu-id="83824-170">[**検査]** ツールの情報オーバーレイが表示され、[コントラスト] 行にオレンジ\*\*\*\* 色の感嘆符が表示され、コントラストが十分に高くなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="83824-170">The **Inspect** tool's information overlay appears, showing an orange exclamation point in the **Contrast** row, indicating that the contrast isn't high enough.</span></span>

    :::image type="complex" source="../media/a11y-testing-hover-contrast-testing.msft.png" alt-text="シミュレートされたホバー状態の要素のコントラストをテストする" lightbox="../media/a11y-testing-hover-contrast-testing.msft.png":::
        <span data-ttu-id="83824-172">シミュレートされたホバー状態の要素のコントラストをテストする</span><span class="sxs-lookup"><span data-stu-id="83824-172">Testing the contrast of an element in a simulated hover state</span></span>
    :::image-end:::

<span data-ttu-id="83824-173">状態シミュレーションは、キーボード ユーザーのニーズなど、さまざまなユーザー ニーズを考慮したかどうかを確認する場合にも便利です。</span><span class="sxs-lookup"><span data-stu-id="83824-173">State simulation is also a good way to check whether you considered different user needs, such as the needs of keyboard users.</span></span>  <span data-ttu-id="83824-174">Force 要素の **状態チェック** ボックスを使用すると、状態をシミュレートして、フォーカスがあるときに UI が変更されていない `:focus` 状態を検出できます。</span><span class="sxs-lookup"><span data-stu-id="83824-174">By using the **Force element state** checkboxes, you can simulate the `:focus` state to discover that the UI remains unchanged when it has focus.</span></span> <span data-ttu-id="83824-175">要素にフォーカスがある場合のインジケーターの不足は問題です。</span><span class="sxs-lookup"><span data-stu-id="83824-175">This lack of an indicator when an element has focus is a problem.</span></span>


## <a name="see-also"></a><span data-ttu-id="83824-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="83824-176">See also</span></span>

*  [<span data-ttu-id="83824-177">DevTools を使用したアクセシビリティ テストの概要</span><span class="sxs-lookup"><span data-stu-id="83824-177">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="83824-178">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="83824-178">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "アクセシビリティテストのデモ web ページ |GitHub"
