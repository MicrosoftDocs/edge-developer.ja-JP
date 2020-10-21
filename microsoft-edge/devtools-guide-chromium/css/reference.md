---
description: Microsoft Edge DevTools での CSS の表示と変更に関する新しいワークフローについてご確認ください。
title: CCS リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: a4c8d5ed7f3cf84f20b4b73531f871e17921b186
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125224"
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

# <span data-ttu-id="3aa42-104">CCS リファレンス</span><span class="sxs-lookup"><span data-stu-id="3aa42-104">CSS reference</span></span>  

<span data-ttu-id="3aa42-105">CSS の表示と変更に関連する Microsoft Edge DevTools 機能の次の包括的なリファレンスで、新しいワークフローについてご確認ください。</span><span class="sxs-lookup"><span data-stu-id="3aa42-105">Discover new workflows in the following comprehensive reference of Microsoft Edge DevTools features related to viewing and changing CSS.</span></span>  

<span data-ttu-id="3aa42-106">基本的な説明については、「 [CSS の表示と変更の概要][DevToolsCSSGetStarted] 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3aa42-106">See [Get Started with Viewing and Changing CSS][DevToolsCSSGetStarted] to learn the basics.</span></span>  

## <span data-ttu-id="3aa42-107">要素を選択する</span><span class="sxs-lookup"><span data-stu-id="3aa42-107">Select an element</span></span>  

<span data-ttu-id="3aa42-108">DevTools の **要素** パネルでは、一度に1つの要素の CSS を表示したり、変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-108">The **Elements** panel of DevTools lets you view or change the CSS of one element at a time.</span></span>  <span data-ttu-id="3aa42-109">選択した要素が **DOM ツリー**で強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-109">The selected element is highlighted in the **DOM Tree**.</span></span>  <span data-ttu-id="3aa42-110">要素のスタイルが [ **スタイル** ] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-110">The styles of the element are shown in the **Styles** pane.</span></span>  <span data-ttu-id="3aa42-111">チュートリアルについては、「 [要素の CSS を表示][DevToolsCSSGetStartedTutorial] する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3aa42-111">See [View the CSS for an element][DevToolsCSSGetStartedTutorial] for a tutorial.</span></span>  

> [!NOTE]
> <span data-ttu-id="3aa42-112">次の図では、 `h1` **DOM ツリー** で強調表示されている要素が選択されています。</span><span class="sxs-lookup"><span data-stu-id="3aa42-112">In the following figure, the `h1` element that is highlighted in the **DOM Tree** is the selected element.</span></span>  <span data-ttu-id="3aa42-113">右側では、要素のスタイルが [ **スタイル** ] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-113">On the right, the styles of the element are shown in the **Styles** pane.</span></span>  <span data-ttu-id="3aa42-114">左側では、要素はビューポートで強調表示されていますが、現在は **DOM ツリー**の上にマウスが置かれているためです。</span><span class="sxs-lookup"><span data-stu-id="3aa42-114">On the left, the element is highlighted in the viewport, but only because the mouse is currently hovering over it in the **DOM Tree**.</span></span>  

:::image type="complex" source="../media/css-elements-styles-h1.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-h1.msft.png":::
   <span data-ttu-id="3aa42-116">選択された要素の例</span><span class="sxs-lookup"><span data-stu-id="3aa42-116">An example of a selected element</span></span>  
:::image-end:::  

<span data-ttu-id="3aa42-117">次の操作のいずれかを使用して、要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-117">Use one the following actions to select an element.</span></span>  

*   <span data-ttu-id="3aa42-118">ビューポートで、要素にマウスポインターを合わせて、コンテキストメニュー \ (右クリック \) を開き、[ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-118">In your viewport, hover on the element, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
*   <span data-ttu-id="3aa42-119">Devtools で、[**要素の選択**] \ (要素を選択) を選択する ![ か、 ][ImageSelectAnElementIcon] `Control` + `Shift` + `C` \ (Windows、Linux \) または `Command` + `Shift` + `C` \ (macOS \) を選択し、ビューポートで要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-119">In DevTools, choose **Select an element** \(![Select an element][ImageSelectAnElementIcon]\) or select `Control`+`Shift`+`C` \(Windows, Linux\) or `Command`+`Shift`+`C` \(macOS\), and then choose the element in the viewport.</span></span>  
*   <span data-ttu-id="3aa42-120">DevTools で、 **DOM ツリー**の要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-120">In DevTools, choose the element in the **DOM Tree**.</span></span>  
*   <span data-ttu-id="3aa42-121">DevTools で、コンソールのようなクエリを実行し、 `document.querySelector('p')` その結果にポインターを置いてコンテキストメニューを開き (\ を右クリックし)、[**要素パネルで**表示] を選択します。 **Console**</span><span class="sxs-lookup"><span data-stu-id="3aa42-121">In DevTools, run a query like `document.querySelector('p')` in the **Console**, hover on the result, open the contextual menu \(right-click\), and choose **Reveal in Elements panel**.</span></span>  

## <span data-ttu-id="3aa42-122">CSS の表示</span><span class="sxs-lookup"><span data-stu-id="3aa42-122">View CSS</span></span>  

### <span data-ttu-id="3aa42-123">ルールが定義されている外部のスタイルシートを表示する</span><span class="sxs-lookup"><span data-stu-id="3aa42-123">View the external stylesheet where a rule is defined</span></span>  

<span data-ttu-id="3aa42-124">[ **スタイル** ] ウィンドウで、CSS ルールの隣にあるリンクを選んで、ルールを定義する外部のスタイルシートを開きます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-124">In the **Styles** pane, choose the link next to a CSS rule to open the external stylesheet that defines the rule.</span></span>  

<span data-ttu-id="3aa42-125">スタイルシートが縮小されている場合は、 [ファイルを読み][DevToolsJavascriptReferenceFormat]やすくするために移動します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-125">If the stylesheet is minified, navigate to [Make a minified file readable][DevToolsJavascriptReferenceFormat].</span></span>  

> [!NOTE]
> <span data-ttu-id="3aa42-126">次の図では、選択する `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` と `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css` 、 `.content h1:first-of-type` CSS ルールが定義されている [2 行目] に移動します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-126">In the following figure, after you choose `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` you are taken to line 2 of `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css`, where the `.content h1:first-of-type` CSS rule is defined.</span></span>  

<!--todo:  replace "Master" phrasing in code snippet, if possible.  -->  

:::image type="complex" source="../media/css-elements-styles-h1-highlight.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-h1-highlight.msft.png":::
  <span data-ttu-id="3aa42-128">ルールが定義されているスタイルシートの表示</span><span class="sxs-lookup"><span data-stu-id="3aa42-128">Viewing the stylesheet where a rule is defined</span></span>  
:::image-end:::  

### <span data-ttu-id="3aa42-129">実際に要素に適用されている CSS のみを表示する</span><span class="sxs-lookup"><span data-stu-id="3aa42-129">View only the CSS that is actually applied to an element</span></span>  

<span data-ttu-id="3aa42-130">[ **スタイル** ] タブには、オーバーライドされた宣言など、要素に適用されるすべての規則が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-130">The **Styles** tab shows you all of the rules that apply to an element, including declarations that have been overridden.</span></span>  <span data-ttu-id="3aa42-131">オーバーライドされた宣言に関心がない場合は、[ **計算** ] タブを使用して、実際に要素に適用されている CSS のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-131">When you are not interested in overridden declarations, use the **Computed** tab to view only the CSS that is actually being applied to an element.</span></span>  

1.  <span data-ttu-id="3aa42-132">[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-132">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="3aa42-133">[**要素**] パネルの [**計算**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-133">Go to the **Computed** tab in the **Elements** panel.</span></span>  

> [!NOTE]
> <span data-ttu-id="3aa42-134">横長の DevTools ウィンドウでは、[ **計算** ] タブは存在しません。</span><span class="sxs-lookup"><span data-stu-id="3aa42-134">On a wide DevTools window, the **Computed** tab does not exist.</span></span>  <span data-ttu-id="3aa42-135">[ **計算** ] タブの内容は、[ **スタイル** ] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-135">The contents of the **Computed** tab are shown on the **Styles** tab.</span></span>  

<span data-ttu-id="3aa42-136">継承されたプロパティは不透明です。</span><span class="sxs-lookup"><span data-stu-id="3aa42-136">Inherited properties are opaque.</span></span>  <span data-ttu-id="3aa42-137">継承されたすべての値を表示するには、[ **すべて表示** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3aa42-137">Check the **Show All** checkbox to see all inherited values.</span></span>  

> [!NOTE]
> <span data-ttu-id="3aa42-138">次の図では、[ **計算** ] タブに、現在選択されている要素に適用されている CSS プロパティが表示されて `h1` います。</span><span class="sxs-lookup"><span data-stu-id="3aa42-138">In the following figure, the **Computed** tab shows the CSS properties being applied to the currently-selected `h1` element.</span></span>  

:::image type="complex" source="../media/css-elements-computed-h1.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-computed-h1.msft.png":::
   <span data-ttu-id="3aa42-140">[ **計算** ] タブ</span><span class="sxs-lookup"><span data-stu-id="3aa42-140">The **Computed** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="3aa42-141">CSS プロパティがアルファベット順に表示される</span><span class="sxs-lookup"><span data-stu-id="3aa42-141">View CSS properties in alphabetical order</span></span>  

<span data-ttu-id="3aa42-142">[ **計算** ] タブを使用します。 「 [要素に実際に適用されている CSS のみを表示する](#view-only-the-css-that-is-actually-applied-to-an-element)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3aa42-142">Use the **Computed** tab.  See [View only the CSS that is actually applied to an element](#view-only-the-css-that-is-actually-applied-to-an-element).</span></span>  

### <span data-ttu-id="3aa42-143">継承した CSS プロパティを表示する</span><span class="sxs-lookup"><span data-stu-id="3aa42-143">View inherited CSS properties</span></span>  

<span data-ttu-id="3aa42-144">[**計算**] タブの [**すべて表示**] チェックボックスをオンにします。 「[要素に実際に適用されている CSS のみを表示する](#view-only-the-css-that-is-actually-applied-to-an-element)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3aa42-144">Check the **Show All** checkbox in the **Computed** tab.  See [View only the CSS that is actually applied to an element](#view-only-the-css-that-is-actually-applied-to-an-element).</span></span>  

### <span data-ttu-id="3aa42-145">要素のボックスモデルを表示する</span><span class="sxs-lookup"><span data-stu-id="3aa42-145">View the box model for an element</span></span>  

<span data-ttu-id="3aa42-146">要素の [ボックスモデル][MDNBoxModel] を表示するには、[ **スタイル** ] タブに移動します。 DevTools ウィンドウが狭い場合、 **ボックスモデル** 図はタブの下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-146">To view [the box model][MDNBoxModel] of an element, go to the **Styles** tab.  If your DevTools window is narrow, the **Box Model** diagram is at the bottom of the tab.</span></span>  

<span data-ttu-id="3aa42-147">値を変更するには、値を選んで編集します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-147">Choose and edit on a value to change a value.</span></span>  

> [!NOTE]
> <span data-ttu-id="3aa42-148">次の図では、[**スタイル**] タブの**ボックスモデル**図は、現在選択されている要素のボックスモデルを示して `h1` います。</span><span class="sxs-lookup"><span data-stu-id="3aa42-148">In the following figure, the **Box Model** diagram in the **Styles** tab shows the box model for the currently selected `h1` element.</span></span>  

:::image type="complex" source="../media/css-elements-styles-h1-2.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-h1-2.msft.png":::
   <span data-ttu-id="3aa42-150">**ボックスモデル**図</span><span class="sxs-lookup"><span data-stu-id="3aa42-150">The **Box Model** diagram</span></span>  
:::image-end:::  

### <span data-ttu-id="3aa42-151">要素の CSS を検索してフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="3aa42-151">Search and filter the CSS of an element</span></span>  

<span data-ttu-id="3aa42-152">[**スタイル**] および [**計算**] タブの [**フィルター** ] テキストボックスを使用して、特定の CSS プロパティまたは値を検索します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-152">Use the **Filter** text box on the **Styles** and **Computed** tabs to search for specific CSS properties or values.</span></span>  

<span data-ttu-id="3aa42-153">[ **計算** ] タブで継承されたプロパティも検索するには、[ **すべて表示** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3aa42-153">To also search inherited properties in the **Computed** tab, check the **Show All** checkbox.</span></span>  

> [!NOTE]
> <span data-ttu-id="3aa42-154">次の図では、[ **スタイル** ] タブをフィルター処理して、検索クエリを含むルールのみを表示してい `color` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-154">In the following figure, the **Styles** tab is filtered to only show rules that include the search query `color`.</span></span>  

:::image type="complex" source="../media/css-elements-styles-filter-color.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-filter-color.msft.png":::
   <span data-ttu-id="3aa42-156">[ **スタイル** ] タブをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="3aa42-156">Filter the **Styles** tab</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="3aa42-157">次の図では、[ **計算** ] タブをフィルター処理して、検索クエリを含む宣言のみが表示されるようにしてい `100%` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-157">In the following figure, the **Computed** tab is filtered to only show declarations that include the search query `100%`.</span></span>  

:::image type="complex" source="../media/css-elements-computed-filter-100.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-computed-filter-100.msft.png":::
   <span data-ttu-id="3aa42-159">**計算**されたタブをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="3aa42-159">Filter the **Computed** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="3aa42-160">擬似クラスの切り替え</span><span class="sxs-lookup"><span data-stu-id="3aa42-160">Toggle a pseudo-class</span></span>  

<span data-ttu-id="3aa42-161">次の操作を実行して、、、、またはなどの擬似クラスを切り替え `:active` `:focus` `:hover` `:visited` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-161">Complete the following actions to toggle a pseudo-class like `:active`, `:focus`, `:hover`, or `:visited`.</span></span>  

1.  <span data-ttu-id="3aa42-162">[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-162">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="3aa42-163">[ **要素** ] パネルで、[ **スタイル** ] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-163">On the **Elements** panel, go to the **Styles** tab.</span></span>  
1.  <span data-ttu-id="3aa42-164">[ **: Hov**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-164">Choose **:hov**.</span></span>  
1.  <span data-ttu-id="3aa42-165">有効にする擬似クラスを確認します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-165">Check the pseudo-class that you want to enable.</span></span>  

> [!NOTE]
> <span data-ttu-id="3aa42-166">次の図では、 `:hover` 擬似クラスを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-166">In the following figure, toggle the `:hover` pseudo-class.</span></span>  <span data-ttu-id="3aa42-167">ビューポートで、宣言が要素に適用されていることを確認し `background-color: cornflowerblue` ます。これは、要素が実際にマウスをポイントしていない場合でも同様です。</span><span class="sxs-lookup"><span data-stu-id="3aa42-167">In the viewport verify that the `background-color: cornflowerblue` declaration is being applied to the element, even though the element is not actually being hovered over.</span></span>  

:::image type="complex" source="../media/css-elements-styles-hov-hover.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-hov-hover.msft.png":::
   <span data-ttu-id="3aa42-169">`:hover`擬似クラスの切り替え</span><span class="sxs-lookup"><span data-stu-id="3aa42-169">Toggle the `:hover` pseudo-class</span></span>  
:::image-end:::  

<span data-ttu-id="3aa42-170">インタラクティブなチュートリアルについては、「 [クラスに擬似状態を追加][DevToolsCSSGetStartedAddPseudoState]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3aa42-170">For an interactive tutorial, navigate to [Add a pseudostate to a class][DevToolsCSSGetStartedAddPseudoState].</span></span>  

### <span data-ttu-id="3aa42-171">印刷モードでページを表示する</span><span class="sxs-lookup"><span data-stu-id="3aa42-171">View a page in print mode</span></span>  

<span data-ttu-id="3aa42-172">印刷モードでページを表示するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-172">Complete the following actions to view a page in print mode.</span></span>  

1.  <span data-ttu-id="3aa42-173">[コマンドメニューを開き][DevToolsCommandMenu]ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-173">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="3aa42-174">入力を開始し `Rendering` 、を選択し `Show Rendering` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-174">Start typing `Rendering` and select `Show Rendering`.</span></span>  
1.  <span data-ttu-id="3aa42-175">[ **CSS メディアのエミュレート** ] ドロップダウンで、[ **印刷**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-175">For the **Emulate CSS Media** dropdown, choose **print**.</span></span>  

### <span data-ttu-id="3aa42-176">[カバレッジ] タブで使用済みおよび未使用の CSS を表示する</span><span class="sxs-lookup"><span data-stu-id="3aa42-176">View used and unused CSS with the Coverage tab</span></span>  

<span data-ttu-id="3aa42-177">[カバレッジ] タブには、ページで実際に使用されている CSS が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-177">The Coverage tab shows you what CSS a page actually uses.</span></span>  

1.  <span data-ttu-id="3aa42-178">`Control` + `Shift` + `P` Devtools がフォーカスされているときに、[\ (Windows, Linux \)] または [ `Command` + `Shift` + `P` \ (macOS \)] を選びます。[コマンドメニューを開き][DevToolsCommandMenu]ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-178">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) while DevTools is in focus to [open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="3aa42-179">入力 `coverage` を開始し、[ **カバレッジの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-179">Start typing `coverage` and choose **Show Coverage**.</span></span>  <span data-ttu-id="3aa42-180">[カバー] タブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-180">The Coverage tab appears.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-command-menu-coverage.msft.png" alt-text="選択された要素の例" lightbox="../media/css-console-command-menu-coverage.msft.png":::
             <span data-ttu-id="3aa42-182">[**コマンド] メニュー**から [**カバレッジ**] タブを開く</span><span class="sxs-lookup"><span data-stu-id="3aa42-182">Open the **Coverage** tab from the **Command Menu**</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-qs-coverage-empty.msft.png" alt-text="選択された要素の例" lightbox="../media/css-console-qs-coverage-empty.msft.png":::
             <span data-ttu-id="3aa42-184">[ **カバレッジ** ] タブ</span><span class="sxs-lookup"><span data-stu-id="3aa42-184">The **Coverage** tab</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="3aa42-185">[ **インストルメントの開始] を選択し、ページを更新** し ![ ます (インストルメント化を開始し、ページを更新し ][ImageRefreshIcon] ます)。</span><span class="sxs-lookup"><span data-stu-id="3aa42-185">Choose **Start instrumenting coverage and refresh the page** \(![Start instrumenting coverage and refresh the page][ImageRefreshIcon]\).</span></span>  <span data-ttu-id="3aa42-186">ページの更新と [カバレッジ] タブには、ブラウザーが読み込む各ファイルからの CSS (および JavaScript \) の使用量の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-186">The page refreshes and the Coverage tab provides an overview of how much CSS \(and JavaScript\) is used from each file that the browser loads.</span></span>  <span data-ttu-id="3aa42-187">緑色は、使用されている CSS を表します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-187">Green represents used CSS.</span></span>  <span data-ttu-id="3aa42-188">赤は未使用の CSS を示します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-188">Red represents unused CSS.</span></span>  
    
    :::image type="complex" source="../media/css-console-qs-coverage-run.msft.png" alt-text="選択された要素の例" lightbox="../media/css-console-qs-coverage-run.msft.png":::
       <span data-ttu-id="3aa42-190">CSS (および JavaScript \) が使用されていて未使用である割合の概要</span><span class="sxs-lookup"><span data-stu-id="3aa42-190">An overview of how much CSS \(and JavaScript\) is used and unused</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="3aa42-191">CSS ファイルを選択すると、使用する CSS の行ごとの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-191">Choose a CSS file to see a line-by-line breakdown of what CSS it uses.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="3aa42-192">次の図では、145 ~ 147、149から151の行 `b66bc881.site-ltr.css` は未使用であり、行163から166に使用されています。</span><span class="sxs-lookup"><span data-stu-id="3aa42-192">In the following figure, lines 145 to 147 and 149 to 151 of `b66bc881.site-ltr.css` are unused, whereas lines 163 to 166 are used.</span></span>  
    
    :::image type="complex" source="../media/css-sources-css-coverage.msft.png" alt-text="選択された要素の例" lightbox="../media/css-sources-css-coverage.msft.png":::
       <span data-ttu-id="3aa42-194">使用されている、未使用の CSS の行単位の内訳</span><span class="sxs-lookup"><span data-stu-id="3aa42-194">A line-by-line breakdown of used and unused CSS</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="3aa42-195">印刷プレビューモードの強制</span><span class="sxs-lookup"><span data-stu-id="3aa42-195">Force print preview mode</span></span>  

<span data-ttu-id="3aa42-196">「 [DevTools を印刷プレビューモードに強制][DevToolsCssPrintPreview]する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3aa42-196">See [Force DevTools into Print Preview mode][DevToolsCssPrintPreview].</span></span>  

## <span data-ttu-id="3aa42-197">CSS を変更する</span><span class="sxs-lookup"><span data-stu-id="3aa42-197">Change CSS</span></span>  

<!-- todo s/CSS declaration/declaration/ -->  

### <span data-ttu-id="3aa42-198">要素に CSS 宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="3aa42-198">Add a CSS declaration to an element</span></span>  

<span data-ttu-id="3aa42-199">宣言の順序は要素のスタイルに影響を及ぼし、さまざまな方法で宣言を追加するために、次の一覧を使用します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-199">The order of declarations affects how an element is styled, use the following list to help you add declarations in different ways.</span></span>  

*   <span data-ttu-id="3aa42-200">[インライン宣言を追加](#add-an-inline-declaration)します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-200">[Add a inline declaration](#add-an-inline-declaration).</span></span>  <span data-ttu-id="3aa42-201">要素の HTML に属性を追加することと同じです `style` 。</span><span class="sxs-lookup"><span data-stu-id="3aa42-201">Equivalent to adding a `style` attribute to the HTML of an element.</span></span>  
*   <span data-ttu-id="3aa42-202">[スタイルルールに宣言を追加](#add-a-declaration-to-a-style-rule)します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-202">[Add a declaration to a style rule](#add-a-declaration-to-a-style-rule).</span></span>  

**<span data-ttu-id="3aa42-203">使用するワークフロー</span><span class="sxs-lookup"><span data-stu-id="3aa42-203">What workflow should you use?</span></span>** <span data-ttu-id="3aa42-204">ほとんどのシナリオでは、通常、インライン宣言ワークフローを使用します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-204">For most scenarios, you probably want to use the inline declaration workflow.</span></span>  <span data-ttu-id="3aa42-205">インライン宣言の内容が外部の宣言よりも高いため、インラインワークフローによって予期される要素で変更が有効になります。</span><span class="sxs-lookup"><span data-stu-id="3aa42-205">Inline declarations have higher specificity than external ones, so the inline workflow ensures that the changes take effect in your expected element.</span></span>  <span data-ttu-id="3aa42-206">特異性の詳細については、「 [Selector の種類][MDNSelectorTypes]に移動する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3aa42-206">For more information about specificity, navigate to [Selector Types][MDNSelectorTypes].</span></span>  

<span data-ttu-id="3aa42-207">要素のスタイルをデバッグしていて、宣言がさまざまな場所で定義されている場合に何が起こるかを明確にテストする必要がある場合は、他のワークフローを使用します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-207">If you are debugging any styles of the element and you need to specifically test what happens when a declaration is defined in different places, use the other workflow.</span></span>  

#### <span data-ttu-id="3aa42-208">インライン宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="3aa42-208">Add an inline declaration</span></span>  

<span data-ttu-id="3aa42-209">インライン宣言を追加するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-209">Complete the following actions to add an inline declaration.</span></span>  

1.  <span data-ttu-id="3aa42-210">[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-210">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="3aa42-211">[**スタイル**] ウィンドウで、[スタイル] セクションのかっこを選択します **。**</span><span class="sxs-lookup"><span data-stu-id="3aa42-211">In the **Styles** pane, choose between the brackets of the **element.style** section.</span></span>  <span data-ttu-id="3aa42-212">カーソルがフォーカスされ、テキストの入力が可能になります。</span><span class="sxs-lookup"><span data-stu-id="3aa42-212">The cursor focuses, allowing you to enter text.</span></span>  
1.  <span data-ttu-id="3aa42-213">プロパティ名を入力して、を選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-213">Enter a property name and select `Enter`.</span></span>  
1.  <span data-ttu-id="3aa42-214">そのプロパティの有効な値を入力して、を選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-214">Enter a valid value for that property and select `Enter`.</span></span>  <span data-ttu-id="3aa42-215">**DOM ツリー**で、 `style` 属性が要素に追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-215">In the **DOM Tree**, verify that a `style` attribute has been added to the element.</span></span>  

> [!NOTE]
> <span data-ttu-id="3aa42-216">次の図では、 `margin-top` と `background-color` プロパティが選択された要素に適用されています。</span><span class="sxs-lookup"><span data-stu-id="3aa42-216">In the following figure, the `margin-top` and `background-color` properties have been applied to the selected element.</span></span>  <span data-ttu-id="3aa42-217">**DOM ツリー**で、宣言が要素の属性に反映されていることを確認し `style` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-217">In the **DOM Tree** verify that the declarations are reflected in the `style` attribute for an element.</span></span>  

:::image type="complex" source="../media/css-elements-styles-margin-top-background-color.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-margin-top-background-color.msft.png":::
   <span data-ttu-id="3aa42-219">インライン宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="3aa42-219">Add inline declarations</span></span>  
:::image-end:::  

#### <span data-ttu-id="3aa42-220">スタイルルールに宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="3aa42-220">Add a declaration to a style rule</span></span>  

<span data-ttu-id="3aa42-221">既存のスタイルルールに宣言を追加するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-221">Complete the following actions to add a declaration to an existing style rule.</span></span>  

1.  <span data-ttu-id="3aa42-222">[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-222">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="3aa42-223">[ **スタイル** ] ウィンドウで、宣言を追加するスタイルルールのかっこの間を選びます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-223">In the **Styles** pane, choose between the brackets of the style rule to which you want to add the declaration.</span></span>  <span data-ttu-id="3aa42-224">カーソルがフォーカスされ、テキストの入力が可能になります。</span><span class="sxs-lookup"><span data-stu-id="3aa42-224">The cursor focuses, allowing you to enter text.</span></span>  
1.  <span data-ttu-id="3aa42-225">プロパティ名を入力して、を選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-225">Enter a property name and select `Enter`.</span></span>  
1.  <span data-ttu-id="3aa42-226">そのプロパティの有効な値を入力して、を選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-226">Enter a valid value for that property and select `Enter`.</span></span>  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-border-bottom-style.msft.png":::
   <span data-ttu-id="3aa42-228">`border-bottom-style:groove`スタイルルールに宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="3aa42-228">Add the `border-bottom-style:groove` declaration to a style rule</span></span>  
:::image-end:::  

### <span data-ttu-id="3aa42-229">宣言の名前または値を変更する</span><span class="sxs-lookup"><span data-stu-id="3aa42-229">Change a declaration name or value</span></span>  

<span data-ttu-id="3aa42-230">宣言の名前または値を選んで編集し、それを変更します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-230">Choose and edit the name or value of a declaration to change it.</span></span>  <span data-ttu-id="3aa42-231">すばやく値を増減するためのショートカットキーについては、「 [宣言の値を変更](#change-declaration-values-with-keyboard-shortcuts) する」を参照してください `0.1` `1` `10` `100` 。</span><span class="sxs-lookup"><span data-stu-id="3aa42-231">See [Change declaration values with keyboard shortcuts](#change-declaration-values-with-keyboard-shortcuts) for shortcuts for quickly incrementing or decrementing a value by `0.1`, `1`, `10`, or `100` units.</span></span>  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style-dropdown.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-border-bottom-style-dropdown.msft.png":::
   <span data-ttu-id="3aa42-233">宣言の値を変更する `border-bottom-style`</span><span class="sxs-lookup"><span data-stu-id="3aa42-233">Change the value of the `border-bottom-style` declaration</span></span>  
:::image-end:::  

### <span data-ttu-id="3aa42-234">キーボードショートカットを使用して宣言の値を変更する</span><span class="sxs-lookup"><span data-stu-id="3aa42-234">Change declaration values with keyboard shortcuts</span></span>  

<span data-ttu-id="3aa42-235">宣言の値を編集しているときに、次のショートカットキーを使用して、指定した値だけ値をインクリメントすることができます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-235">While editing the value of a declaration, you may use the following keyboard shortcuts to increment the value by a specific amount.</span></span>  

*   <span data-ttu-id="3aa42-236">`Alt` + `Up` 増やすには、\ (Windows, Linux \) または `Option` + `Up` \ (macOS \) を選択し `0.1` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-236">Select `Alt`+`Up` \(Windows, Linux\) or `Option`+`Up` \(macOS\) to increment by `0.1`.</span></span>  
*   <span data-ttu-id="3aa42-237">値を選択 `Up` する `1` か、 `0.1` 現在の値が and の間にある場合は、を選択し `-1` `1` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-237">Select `Up` to change the value by `1`, or by `0.1` if the current value is between `-1` and `1`.</span></span>  
*   <span data-ttu-id="3aa42-238">[増分] を選択し `Shift` + `Up` `10` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-238">Select `Shift`+`Up` to increment by `10`.</span></span>  
*   <span data-ttu-id="3aa42-239">`Shift` + `Page Up` 値をインクリメントするには、\ (Windows, Linux \) または `Shift` + `Command` + `Up` \ (macOS \) `100` を選択します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-239">Select `Shift`+`Page Up` \(Windows, Linux\) or `Shift`+`Command`+`Up` \(macOS\) to increment the value by `100`.</span></span>  

<span data-ttu-id="3aa42-240">減分も動作します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-240">Decrementing also works.</span></span>  <span data-ttu-id="3aa42-241">`Up`上記で説明した各インスタンスをに置き換え `Down` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-241">Just replace each instance of `Up` mentioned above with `Down`.</span></span>  

### <span data-ttu-id="3aa42-242">要素にクラスを追加する</span><span class="sxs-lookup"><span data-stu-id="3aa42-242">Add a class to an element</span></span>  

<span data-ttu-id="3aa42-243">要素にクラスを追加するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-243">Complete the following actions to add a class to an element.</span></span>  

1.  <span data-ttu-id="3aa42-244">**DOM ツリー**で[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-244">[Select the element](#select-an-element) in the **DOM Tree**.</span></span>  
1.  <span data-ttu-id="3aa42-245">**Cls**を選びます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-245">Choose **.cls**.</span></span>  
1.  <span data-ttu-id="3aa42-246">[ **Add New class** ] テキストボックスにクラスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-246">Enter the name of the class in the **Add New Class** text box.</span></span>  
1.  <span data-ttu-id="3aa42-247">を選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-247">Select `Enter`.</span></span>  

:::image type="complex" source="../media/css-elements-styles-filter-classes.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-filter-classes.msft.png":::
   <span data-ttu-id="3aa42-249">[ **要素クラス** ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="3aa42-249">The **Element Classes** pane</span></span>  
:::image-end:::  

### <span data-ttu-id="3aa42-250">クラスの切り替え</span><span class="sxs-lookup"><span data-stu-id="3aa42-250">Toggle a class</span></span>  

<span data-ttu-id="3aa42-251">要素のクラスを有効または無効にするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-251">Complete the following actions to enable or disable a class on an element.</span></span>  

1.  <span data-ttu-id="3aa42-252">**DOM ツリー**で[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-252">[Select the element](#select-an-element) in the **DOM Tree**.</span></span>  
1.  <span data-ttu-id="3aa42-253">[ **要素クラス** ] ペインを開きます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-253">Open the **Element Classes** pane.</span></span>  <span data-ttu-id="3aa42-254">「 [要素にクラスを追加する」を](#add-a-class-to-an-element)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3aa42-254">See [Add a class to an element](#add-a-class-to-an-element).</span></span>  <span data-ttu-id="3aa42-255">[ **新しいクラスの追加** ] テキストボックスの下には、特定の要素に適用されるすべてのクラスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-255">Below the **Add New Class** text box are all of the classes that are being applied to the specific element.</span></span>  
1.  <span data-ttu-id="3aa42-256">有効または無効にするクラスの横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3aa42-256">Toggle the checkbox next to the class that you want to enable or disable.</span></span>  

### <span data-ttu-id="3aa42-257">スタイルルールを追加する</span><span class="sxs-lookup"><span data-stu-id="3aa42-257">Add a style rule</span></span>  

<span data-ttu-id="3aa42-258">新しいスタイルルールを追加するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-258">Complete the following actions to add a new style rule.</span></span>  

1.  <span data-ttu-id="3aa42-259">[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-259">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="3aa42-260">[ **新しいスタイルルール** ] ([ ![ 新しいスタイルルール]) を選び ][ImageNewStyleRuleIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-260">Choose **New Style Rule** \(![New Style Rule][ImageNewStyleRuleIcon]\).</span></span>  <span data-ttu-id="3aa42-261">DevTools は、 **要素のスタイル** ルールの下に新しいルールを挿入します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-261">DevTools inserts a new rule beneath the **element.style** rule.</span></span>  

> [!NOTE]
> <span data-ttu-id="3aa42-262">次の図では、 `h1.devsite-page-title` **新しいスタイルルール**を選択すると、devtools でスタイルルールが追加されます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-262">In the following figure, DevTools adds the `h1.devsite-page-title` style rule after you choose **New Style Rule**.</span></span>  

:::image type="complex" source="../media/css-elements-styles-style-new.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-style-new.msft.png":::
   <span data-ttu-id="3aa42-264">新しいスタイルルールを追加する</span><span class="sxs-lookup"><span data-stu-id="3aa42-264">Add a new style rule</span></span>  
:::image-end:::  

#### <span data-ttu-id="3aa42-265">ルールを追加するスタイルを選択する</span><span class="sxs-lookup"><span data-stu-id="3aa42-265">Choose which stylesheet to add a rule to</span></span>  

<span data-ttu-id="3aa42-266">[新しいスタイルルールを追加](#add-a-style-rule)するときに、[**新しい**スタイルルール] (新しいスタイルルール) を選んで保持して、 ![ ][ImageNewStyleRuleIcon] スタイルルールを追加するスタイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-266">When [adding a new style rule](#add-a-style-rule), choose and hold **New Style Rule** \(![New Style Rule][ImageNewStyleRuleIcon]\) to choose which stylesheet to add the style rule to.</span></span>  

:::image type="complex" source="../media/css-elements-styles-style-new-select-existing.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-style-new-select-existing.msft.png":::
   <span data-ttu-id="3aa42-268">スタイルシートを選択する</span><span class="sxs-lookup"><span data-stu-id="3aa42-268">Choose a stylesheet</span></span>  
:::image-end:::  

#### <span data-ttu-id="3aa42-269">特定の場所にスタイルルールを追加する</span><span class="sxs-lookup"><span data-stu-id="3aa42-269">Add a style rule to a specific location</span></span>  

<span data-ttu-id="3aa42-270">[ **スタイル** ] タブの特定の場所にスタイルルールを追加するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-270">Complete the following actions to add a style rule to a specific location in the **Styles** tab.</span></span>  

1.  <span data-ttu-id="3aa42-271">新しいスタイルルールを追加する場所のすぐ上のスタイルルールにマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-271">Hover over the style rule that is directly above where you want to add your new style rule.</span></span>  
1.  <span data-ttu-id="3aa42-272">[[ **その他の操作** ] ツールバーを](#reveal-the-more-actions-toolbar)表示します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-272">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="3aa42-273">[ **スタイルルールの挿入** ] を選択します (下に ![ スタイルルールを挿入し ][ImageNewStyleRuleIcon] ます)。</span><span class="sxs-lookup"><span data-stu-id="3aa42-273">Choose **Insert Style Rule Below** \(![Insert Style Rule Below icon][ImageNewStyleRuleIcon]\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-insert-style-rule-below.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-insert-style-rule-below.msft.png":::
   **<span data-ttu-id="3aa42-275">下にスタイルルールを挿入する</span><span class="sxs-lookup"><span data-stu-id="3aa42-275">Insert Style Rule Below</span></span>**  
:::image-end:::  

### <span data-ttu-id="3aa42-276">[その他の操作] ツールバーを表示する</span><span class="sxs-lookup"><span data-stu-id="3aa42-276">Reveal the More Actions toolbar</span></span>  

<span data-ttu-id="3aa42-277">[ **その他の操作** ] ツールバーを使用すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-277">The **More Actions** toolbar lets you perform the following actions.</span></span>  

*   <span data-ttu-id="3aa42-278">優先するスタイルルールのすぐ下にスタイルルールを挿入します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-278">Insert a style rule directly below the one you are focused on.</span></span>  
*   <span data-ttu-id="3aa42-279">`background-color` `color` `box-shadow` `text-shadow` フォーカスされているスタイルルールに、、、、または宣言を追加します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-279">Add a `background-color`, `color`, `box-shadow`, or `text-shadow` declaration to the style rule you are focused on.</span></span>  

<span data-ttu-id="3aa42-280">[ **その他の操作** ] ツールバーを表示するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-280">Complete the following actions to reveal the **More Actions** toolbar.</span></span>  

1.  <span data-ttu-id="3aa42-281">[ **スタイル** ] タブで、スタイルルールの上にマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-281">In the **Styles** tab, hover over a style rule.</span></span>  <span data-ttu-id="3aa42-282">**More Actions** `...` [スタイルルール] セクションの右下にある [その他のアクション] \ (\) が公開されます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-282">**More Actions** \(`...`\) is revealed in the bottom-right of the style rule section.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="3aa42-283">次の図では、スタイルルールにマウスポインターを合わせる `.header-holder.has-default-focus` と、[スタイルルール] セクションの右下に [ **その他のアクション** ] が現れています。</span><span class="sxs-lookup"><span data-stu-id="3aa42-283">In the following figure, hover over the `.header-holder.has-default-focus` style rule and **More Actions** is revealed in the bottom-right of the style rule section.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-new-rule-styles.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-new-rule-styles.msft.png":::
       <span data-ttu-id="3aa42-285">**その他のアクション**を表示 \ ( `...` \)</span><span class="sxs-lookup"><span data-stu-id="3aa42-285">Reveal **More Actions** \(`...`\)</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3aa42-286">上で**More Actions** `...` 説明した操作を表示するには、[その他のアクション] (\) をポイントします。</span><span class="sxs-lookup"><span data-stu-id="3aa42-286">Hover over **More Actions** \(`...`\) to reveal the actions mentioned above.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="3aa42-287">[ **次のスタイルルールの挿入** アクションを実行すると、 **その他の操作**をマウスでポイントしたときに、次のように</span><span class="sxs-lookup"><span data-stu-id="3aa42-287">The **Insert Style Rule Below** action is revealed after hovering over **More Actions**.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png":::
       <span data-ttu-id="3aa42-289">[ **その他の操作** ] ツールバー</span><span class="sxs-lookup"><span data-stu-id="3aa42-289">The **More Actions** toolbar</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="3aa42-290">宣言を切り替える</span><span class="sxs-lookup"><span data-stu-id="3aa42-290">Toggle a declaration</span></span>  

<span data-ttu-id="3aa42-291">Folllwoing アクションを完了して \ (またはオフ) の1つの宣言を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-291">Complete the folllwoing actions to toggle a single declaration on \(or off\).</span></span>  

1.  <span data-ttu-id="3aa42-292">[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-292">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="3aa42-293">[ **スタイル** ] ウィンドウで、宣言を定義するルールの上にマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-293">In the **Styles** pane, hover over the rule that defines the declaration.</span></span>  <span data-ttu-id="3aa42-294">各宣言の横にチェックボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-294">A checkbox appears next to each declaration.</span></span>  
1.  <span data-ttu-id="3aa42-295">宣言の横にあるチェックボックスをオン (またはオフ) にします。</span><span class="sxs-lookup"><span data-stu-id="3aa42-295">Check \(or uncheck\) the checkbox next to the declaration.</span></span>  <span data-ttu-id="3aa42-296">宣言をオフにすると、DevTools がその宣言を超えて、アクティブでなくなったことを示します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-296">When you uncheck a declaration, DevTools crosses it out to indicate that it is no longer active.</span></span>  

> [!NOTE]
> <span data-ttu-id="3aa42-297">次の図では、 `margin-top` 現在選択されている要素のプロパティがトグルオフになっています。</span><span class="sxs-lookup"><span data-stu-id="3aa42-297">In the following figure, the `margin-top` property for the currently selected element has been toggled off.</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-deactivated.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-rule-deactivated.msft.png":::
   <span data-ttu-id="3aa42-299">宣言を切り替える</span><span class="sxs-lookup"><span data-stu-id="3aa42-299">Toggle a declaration</span></span>  
:::image-end:::  

### <span data-ttu-id="3aa42-300">背景色の宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="3aa42-300">Add a background-color declaration</span></span>  

<span data-ttu-id="3aa42-301">要素に宣言を追加するには、次の操作を実行し `background-color` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-301">Complete the following actions to add a `background-color` declaration to an element.</span></span>  

1.  <span data-ttu-id="3aa42-302">宣言を追加するスタイルルールの上にマウスポインターを置き `background-color` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-302">Hover over the style rule that you want to add the `background-color` declaration to.</span></span>  
1.  <span data-ttu-id="3aa42-303">[[ **その他の操作** ] ツールバーを](#reveal-the-more-actions-toolbar)表示します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-303">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="3aa42-304">[ **背景色の追加** ] を選択し ![ ます (背景色の追加アイコン ][ImageAddBackgroundColorIcon] \)。</span><span class="sxs-lookup"><span data-stu-id="3aa42-304">Choose **Add Background Color** \(![Add Background Color icon][ImageAddBackgroundColorIcon]\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-background-color.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-rule-add-background-color.msft.png":::
   **<span data-ttu-id="3aa42-306">背景色を追加する</span><span class="sxs-lookup"><span data-stu-id="3aa42-306">Add Background Color</span></span>**  
:::image-end:::  

### <span data-ttu-id="3aa42-307">色の宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="3aa42-307">Add a color declaration</span></span>  

<span data-ttu-id="3aa42-308">要素に宣言を追加するには、次の操作を実行し `color` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-308">Complete the following actions to add a `color` declaration to an element.</span></span>  

1.  <span data-ttu-id="3aa42-309">宣言を追加するスタイルルールの上にマウスポインターを置き `color` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-309">Hover over the style rule that you want to add the `color` declaration to.</span></span>  
1.  <span data-ttu-id="3aa42-310">[[ **その他の操作** ] ツールバーを](#reveal-the-more-actions-toolbar)表示します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-310">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="3aa42-311">[ **色の追加** ![ ] (色の追加アイコン ][ImageAddColorIcon] \) を選びます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-311">Choose **Add Color** \(![Add Color icon][ImageAddColorIcon]\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-color.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-rule-add-color.msft.png":::
   **<span data-ttu-id="3aa42-313">色を追加する</span><span class="sxs-lookup"><span data-stu-id="3aa42-313">Add Color</span></span>**  
:::image-end:::  

### <span data-ttu-id="3aa42-314">ボックスシャドウ宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="3aa42-314">Add a box-shadow declaration</span></span>  

<span data-ttu-id="3aa42-315">要素に宣言を追加するには、次の操作を実行し `box-shadow` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-315">Complete the follwoing actions to add a `box-shadow` declaration to an element.</span></span>  

1.  <span data-ttu-id="3aa42-316">宣言を追加するスタイルルールの上にマウスポインターを置き `box-shadow` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-316">Hover over the style rule that you want to add the `box-shadow` declaration to.</span></span>  
1.  <span data-ttu-id="3aa42-317">[[ **その他の操作** ] ツールバーを](#reveal-the-more-actions-toolbar)表示します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-317">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="3aa42-318">[ **Add Box shadow** ] ( ![ box shadow icon を追加) を選び ][ImageAddBoxShadowIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-318">Choose **Add Box Shadow** \(![Add Box Shadow icon][ImageAddBoxShadowIcon]\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-box-shadow.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-rule-add-box-shadow.msft.png":::
   **<span data-ttu-id="3aa42-320">ボックスの影を追加する</span><span class="sxs-lookup"><span data-stu-id="3aa42-320">Add Box Shadow</span></span>**  
:::image-end:::  

### <span data-ttu-id="3aa42-321">テキストシャドウの宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="3aa42-321">Add a text-shadow declaration</span></span>  

<span data-ttu-id="3aa42-322">要素に宣言を追加するには、次の操作を実行し `text-shadow` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-322">Complete the following actions to add a `text-shadow` declaration to an element.</span></span>  

1.  <span data-ttu-id="3aa42-323">宣言を追加するスタイルルールの上にマウスポインターを置き `text-shadow` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-323">Hover over the style rule that you want to add the `text-shadow` declaration to.</span></span>  
1.  <span data-ttu-id="3aa42-324">[[ **その他の操作** ] ツールバーを](#reveal-the-more-actions-toolbar)表示します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-324">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="3aa42-325">[ **テキストの影** を追加 ![ ] を選び ][ImageAddTextShadowIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-325">Choose **Add Text Shadow** \(![Add Text Shadow icon][ImageAddTextShadowIcon]\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-text-shadow.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-rule-add-text-shadow.msft.png":::
   **<span data-ttu-id="3aa42-327">テキストの影を追加する</span><span class="sxs-lookup"><span data-stu-id="3aa42-327">Add Text Shadow</span></span>**  
:::image-end:::  

### <span data-ttu-id="3aa42-328">カラーピッカーを使用して色を変更する</span><span class="sxs-lookup"><span data-stu-id="3aa42-328">Change colors with the Color Picker</span></span>  

<span data-ttu-id="3aa42-329">**カラーピッカー**は、変更と宣言のための GUI を提供し `color` `background-color` ます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-329">The **Color Picker** provides a GUI for changing `color` and `background-color` declarations.</span></span>  

<span data-ttu-id="3aa42-330">次の操作を実行して、 **カラーピッカー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-330">Complete the following actions to open the **Color Picker**.</span></span>  

1.  <span data-ttu-id="3aa42-331">[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-331">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="3aa42-332">[ **スタイル** ] タブで、変更する、 `color` `background-color` または同様の宣言を見つけます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-332">In the **Styles** tab, find the `color`, `background-color`, or similar declaration that you want to change.</span></span>  <span data-ttu-id="3aa42-333">、、 `color` `background-color` または同様の値の左側に、色のプレビューである小さな四角形が表示されています。</span><span class="sxs-lookup"><span data-stu-id="3aa42-333">To the left of the `color`, `background-color`, or similar value, there is a small square which is a preview of the color.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="3aa42-334">次の図では、左側の小さな四角形 `rgba(0, 0, 0, 0.7)` がその色のプレビューです。</span><span class="sxs-lookup"><span data-stu-id="3aa42-334">In the following figure, the small square to the left of `rgba(0, 0, 0, 0.7)` is a preview of that color.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-rule-overlay-color-box.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-rule-overlay-color-box.msft.png":::
       <span data-ttu-id="3aa42-336">色のプレビュー</span><span class="sxs-lookup"><span data-stu-id="3aa42-336">Color preview</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3aa42-337">プレビューを選択して、 **カラーピッカー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-337">Choose the preview to open the **Color Picker**.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-rule-color-picker.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-rule-color-picker.msft.png":::
       <span data-ttu-id="3aa42-339">**色のパレット**</span><span class="sxs-lookup"><span data-stu-id="3aa42-339">The **Color Picker**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="3aa42-340">次の図と、 **カラーピッカー**の各 UI 要素のはを示します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-340">The following figure and list descries of each of the UI elements of the **Color Picker**.</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-color-picker-annotated.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-rule-color-picker-annotated.msft.png":::
   <span data-ttu-id="3aa42-342">**カラーピッカー**の注釈</span><span class="sxs-lookup"><span data-stu-id="3aa42-342">The **Color Picker**, annotated</span></span>  
:::image-end:::  

:::row:::
   :::column span="1":::
      <span data-ttu-id="3aa42-343">件</span><span class="sxs-lookup"><span data-stu-id="3aa42-343">1</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="3aa42-344">明るい</span><span class="sxs-lookup"><span data-stu-id="3aa42-344">Shades</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="3aa42-345">両面</span><span class="sxs-lookup"><span data-stu-id="3aa42-345">2</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="3aa42-346">スポイト</span><span class="sxs-lookup"><span data-stu-id="3aa42-346">Eyedropper</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="3aa42-347">詳細については、「 [スポイトを使用してページに色を](#sample-a-color-off-the-page-with-the-eyedropper)設定する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3aa42-347">For more information, navigate to [Sample a color off the page with the Eyedropper](#sample-a-color-off-the-page-with-the-eyedropper).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="3aa42-348">-</span><span class="sxs-lookup"><span data-stu-id="3aa42-348">3</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="3aa42-349">クリップボードにコピー</span><span class="sxs-lookup"><span data-stu-id="3aa42-349">Copy To Clipboard</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="3aa42-350">**表示値**をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="3aa42-350">Copy the **Display Value** to your clipboard.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="3aa42-351">4d</span><span class="sxs-lookup"><span data-stu-id="3aa42-351">4</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="3aa42-352">表示値</span><span class="sxs-lookup"><span data-stu-id="3aa42-352">Display Value</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="3aa42-353">色の RGBA、HSLA、または16進表現。</span><span class="sxs-lookup"><span data-stu-id="3aa42-353">The RGBA, HSLA, or Hex representation of the color.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="3aa42-354">個</span><span class="sxs-lookup"><span data-stu-id="3aa42-354">5</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="3aa42-355">カラー パレット</span><span class="sxs-lookup"><span data-stu-id="3aa42-355">Color Palette</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="3aa42-356">四角形のいずれかを選んで、その四角形に色を変更します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-356">Choose one of the squares to change the color to that square.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="3aa42-357">=</span><span class="sxs-lookup"><span data-stu-id="3aa42-357">6</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="3aa42-358">色相</span><span class="sxs-lookup"><span data-stu-id="3aa42-358">Hue</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="3aa42-359">日</span><span class="sxs-lookup"><span data-stu-id="3aa42-359">7</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="3aa42-360">Opacity</span><span class="sxs-lookup"><span data-stu-id="3aa42-360">Opacity</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="3aa42-361">個</span><span class="sxs-lookup"><span data-stu-id="3aa42-361">8</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="3aa42-362">値の表示スイッチャー</span><span class="sxs-lookup"><span data-stu-id="3aa42-362">Display Value Switcher</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="3aa42-363">現在の色の RGBA、HSLA、16進表現を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-363">Toggle between the RGBA, HSLA, and Hex representations of the current color.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="3aa42-364">ファイブ</span><span class="sxs-lookup"><span data-stu-id="3aa42-364">9</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="3aa42-365">カラーパレットスイッチャー</span><span class="sxs-lookup"><span data-stu-id="3aa42-365">Color Palette Switcher</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="3aa42-366">[マテリアルデザインパレット][MaterialDesignColorSystem]、カスタムパレット、またはページカラーパレットを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-366">Toggle between the [Material Design palette][MaterialDesignColorSystem], a custom palette, or a page colors palette.</span></span>  <span data-ttu-id="3aa42-367">DevTools は、スタイルシートで検出された色に基づいてページカラーパレットを生成します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-367">DevTools generates the page color palette based on the colors that it finds in your stylesheets.</span></span>  
   :::column-end:::
:::row-end:::  

#### <span data-ttu-id="3aa42-368">スポイトを使用してページの色を設定する</span><span class="sxs-lookup"><span data-stu-id="3aa42-368">Sample a color off the page with the Eyedropper</span></span>  

<span data-ttu-id="3aa42-369">**カラーピッカー**を開くと、**スポイト**( ![ スポイト ][ImageEyedropperIcon] ) がデフォルトでオンになります。</span><span class="sxs-lookup"><span data-stu-id="3aa42-369">When you open the **Color Picker**, the **Eyedropper** \(![Eyedropper][ImageEyedropperIcon]\) is on by default.</span></span>  <span data-ttu-id="3aa42-370">選択した色をページ上の別の色に変更するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3aa42-370">Complete the following actions to change the selected color to some other color on the page.</span></span>  

1.  <span data-ttu-id="3aa42-371">ビューポートのターゲットの色の上にマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-371">Hover over the target color in the viewport.</span></span>  
1.  <span data-ttu-id="3aa42-372">[確認] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-372">Choose to confirm.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="3aa42-373">次の図では、 **色のパレット** に現在の色の値が表示されてい `rgba(0,0,0,0.7)` ます。これは黒に近くなります。</span><span class="sxs-lookup"><span data-stu-id="3aa42-373">In the following figure, the **Color Picker** shows a current color value of `rgba(0,0,0,0.7)`, which is close to black.</span></span>  <span data-ttu-id="3aa42-374">特定の色を、選択した後にビューポートで現在強調表示されている黒のバージョンに変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3aa42-374">The specific color should change to the version of black that is currently highlighted in the viewport after you chose it.</span></span>  
    
    :::image type="complex" source="../media/css-color-picker-eye-dropper.msft.png" alt-text="選択された要素の例" lightbox="../media/css-color-picker-eye-dropper.msft.png":::
       <span data-ttu-id="3aa42-376">スポイトを使用する</span><span class="sxs-lookup"><span data-stu-id="3aa42-376">Using the Eyedropper</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="3aa42-377">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="3aa42-377">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageAddBackgroundColorIcon]: ../media/add-background-color-icon.msft.png  
[ImageAddBoxShadowIcon]: ../media/add-box-shadow-icon.msft.png  
[ImageAddColorIcon]: ../media/add-color-icon.msft.png  
[ImageAddTextShadowIcon]: ../media/add-text-shadow-icon.msft.png  
[ImageEyedropperIcon]: ../media/eyedropper-icon.msft.png  
[ImageNewStyleRuleIcon]: ../media/new-style-rule-icon.msft.png  
[ImageRefreshIcon]: ../media/refresh-icon.msft.png  
[ImageSelectAnElementIcon]: ../media/select-an-element-icon.msft.png  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する |Microsoft ドキュメント"  
[DevToolsCSSGetStarted]: ../css/index.md "CSS の表示と変更の概要 |Microsoft ドキュメント"  
[DevToolsCSSGetStartedAddPseudoState]: ../css/index.md#add-a-pseudostate-to-a-class "クラスに擬似状態を追加する-CSS の表示と変更を開始する |Microsoft ドキュメント"  
[DevToolsCSSGetStartedTutorial]: ../css/index.md#view-the-css-for-an-element "要素の CSS を表示する-CSS の表示と変更の概要 |Microsoft ドキュメント"  
[DevToolsCssPrintPreview]: ../css/print-preview.md "Microsoft Edge DevTools を印刷プレビューモードで強制する (CSS 印刷メディアの種類) |Microsoft ドキュメント"  
[DevToolsJavascriptReferenceFormat]: ../javascript/reference.md#make-a-minified-file-readable "ファイルを読みやすくする-JavaScript のデバッグ参照 |Microsoft ドキュメント"  

[MaterialDesignColorSystem]: https://material.io/guidelines/style/color.html#color-color-palette "カラーシステム-マテリアルデザイン"  
[MDNBoxModel]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Box_model "ボックスモデル |MDN"  
[MDNSelectorTypes]: https://developer.mozilla.org/docs/Web/CSS/Specificity#Selector_Types "セレクターの種類-特異性 |MDN"  

> [!NOTE]
> <span data-ttu-id="3aa42-387">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="3aa42-387">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="3aa42-388">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/css/reference) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="3aa42-388">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="3aa42-390">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="3aa42-390">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
