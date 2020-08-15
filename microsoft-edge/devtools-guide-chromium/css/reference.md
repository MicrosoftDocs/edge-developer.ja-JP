---
title: CCS リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/14/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 908e32140d9deb89489089442055e188cd2d9378
ms.sourcegitcommit: 054ad92f0b8f9a15da1e3aed32e8f4379b10860f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2020
ms.locfileid: "10931424"
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

# <span data-ttu-id="e2532-103">CSS リファレンス</span><span class="sxs-lookup"><span data-stu-id="e2532-103">CSS reference</span></span>  

<span data-ttu-id="e2532-104">CSS の表示と変更に関連する Microsoft Edge DevTools 機能の次の包括的なリファレンスで、新しいワークフローについてご確認ください。</span><span class="sxs-lookup"><span data-stu-id="e2532-104">Discover new workflows in the following comprehensive reference of Microsoft Edge DevTools features related to viewing and changing CSS.</span></span>  

<span data-ttu-id="e2532-105">基本的な説明については、「 [CSS の表示と変更の概要][DevToolsCSSGetStarted] 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2532-105">See [Get Started with Viewing and Changing CSS][DevToolsCSSGetStarted] to learn the basics.</span></span>  

## <span data-ttu-id="e2532-106">要素を選択する</span><span class="sxs-lookup"><span data-stu-id="e2532-106">Select an element</span></span>  

<span data-ttu-id="e2532-107">DevTools の **要素** パネルでは、一度に1つの要素の CSS を表示したり、変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="e2532-107">The **Elements** panel of DevTools lets you view or change the CSS of one element at a time.</span></span>  <span data-ttu-id="e2532-108">選択した要素が **DOM ツリー**で強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2532-108">The selected element is highlighted in the **DOM Tree**.</span></span>  <span data-ttu-id="e2532-109">要素のスタイルが [ **スタイル** ] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2532-109">The styles of the element are shown in the **Styles** pane.</span></span>  <span data-ttu-id="e2532-110">チュートリアルについては、「 [要素の CSS を表示][DevToolsCSSGetStartedTutorial] する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e2532-110">See [View the CSS for an element][DevToolsCSSGetStartedTutorial] for a tutorial.</span></span>  

> [!NOTE]
> <span data-ttu-id="e2532-111">次の図では、 `h1` **DOM ツリー** で強調表示されている要素が選択されています。</span><span class="sxs-lookup"><span data-stu-id="e2532-111">In the following figure, the `h1` element that is highlighted in the **DOM Tree** is the selected element.</span></span>  <span data-ttu-id="e2532-112">右側では、要素のスタイルが [ **スタイル** ] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2532-112">On the right, the styles of the element are shown in the **Styles** pane.</span></span>  <span data-ttu-id="e2532-113">左側では、要素はビューポートで強調表示されていますが、現在は **DOM ツリー**の上にマウスが置かれているためです。</span><span class="sxs-lookup"><span data-stu-id="e2532-113">On the left, the element is highlighted in the viewport, but only because the mouse is currently hovering over it in the **DOM Tree**.</span></span>  

:::image type="complex" source="../media/css-elements-styles-h1.msft.png" alt-text="選択された要素の例" lightbox="../media/css-elements-styles-h1.msft.png":::
   <span data-ttu-id="e2532-115">選択された要素の例</span><span class="sxs-lookup"><span data-stu-id="e2532-115">An example of a selected element</span></span>  
:::image-end:::  

<span data-ttu-id="e2532-116">次の操作のいずれかを使用して、要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2532-116">Use one the following actions to select an element.</span></span>  

*   <span data-ttu-id="e2532-117">ビューポートで、要素にマウスポインターを合わせて、コンテキストメニュー \ (右クリック \) を開き、[ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e2532-117">In your viewport, hover on the element, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
*   <span data-ttu-id="e2532-118">Devtools で、[**要素の選択**] \ (要素を選択) を選択する ![ ][ImageSelectAnElementIcon] か `Control` + `Shift` + `C` 、\ (Windows \) または `Command` + `Shift` + `C` \ (macOS \) を選択し、ビューポートで要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2532-118">In DevTools, choose **Select an element** \(![Select an element][ImageSelectAnElementIcon]\) or select `Control`+`Shift`+`C` \(Windows\) or `Command`+`Shift`+`C` \(macOS\), and then choose the element in the viewport.</span></span>  
*   <span data-ttu-id="e2532-119">DevTools で、 **DOM ツリー**の要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2532-119">In DevTools, choose the element in the **DOM Tree**.</span></span>  
*   <span data-ttu-id="e2532-120">DevTools で、コンソールのようなクエリを実行し、 `document.querySelector('p')` その結果にポインターを置いてコンテキストメニューを開き (\ を右クリックし)、[**要素パネルで**表示] を選択します。 **Console**</span><span class="sxs-lookup"><span data-stu-id="e2532-120">In DevTools, run a query like `document.querySelector('p')` in the **Console**, hover on the result, open the contextual menu \(right-click\), and select **Reveal in Elements panel**.</span></span>  

## <span data-ttu-id="e2532-121">CSS の表示</span><span class="sxs-lookup"><span data-stu-id="e2532-121">View CSS</span></span>  

### <span data-ttu-id="e2532-122">ルールが定義されている外部のスタイルシートを表示する</span><span class="sxs-lookup"><span data-stu-id="e2532-122">View the external stylesheet where a rule is defined</span></span>  

<span data-ttu-id="e2532-123">[ **スタイル** ] ウィンドウで、CSS ルールの隣にあるリンクを選んで、ルールを定義する外部のスタイルシートを開きます。</span><span class="sxs-lookup"><span data-stu-id="e2532-123">In the **Styles** pane, choose the link next to a CSS rule to open the external stylesheet that defines the rule.</span></span>  

<span data-ttu-id="e2532-124">スタイルシートが縮小されている場合は、「縮小版の [ファイルを読みやすくする][DevToolsJavascriptReferenceFormat]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2532-124">If the stylesheet is minified, see [Make a minified file readable][DevToolsJavascriptReferenceFormat].</span></span>  

> [!NOTE]
> <span data-ttu-id="e2532-125">次の図では、選択する `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` と `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css` 、 `.content h1:first-of-type` CSS ルールが定義されている [2 行目] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e2532-125">In the following figure, after you choose `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` you are taken to line 2 of `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css`, where the `.content h1:first-of-type` CSS rule is defined.</span></span>  

<!--todo:  replace "Master" phrasing in code snippet, if possible.  -->  

:::image type="complex" source="../media/css-elements-styles-h1-highlight.msft.png" alt-text="ルールが定義されているスタイルシートの表示" lightbox="../media/css-elements-styles-h1-highlight.msft.png":::
  <span data-ttu-id="e2532-127">ルールが定義されているスタイルシートの表示</span><span class="sxs-lookup"><span data-stu-id="e2532-127">Viewing the stylesheet where a rule is defined</span></span>  
:::image-end:::  

### <span data-ttu-id="e2532-128">実際に要素に適用されている CSS のみを表示する</span><span class="sxs-lookup"><span data-stu-id="e2532-128">View only the CSS that is actually applied to an element</span></span>  

<span data-ttu-id="e2532-129">[ **スタイル** ] タブには、オーバーライドされた宣言など、要素に適用されるすべての規則が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2532-129">The **Styles** tab shows you all of the rules that apply to an element, including declarations that have been overridden.</span></span>  <span data-ttu-id="e2532-130">オーバーライドされた宣言に関心がない場合は、[ **計算** ] タブを使用して、実際に要素に適用されている CSS のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="e2532-130">When you are not interested in overridden declarations, use the **Computed** tab to view only the CSS that is actually being applied to an element.</span></span>  

1.  <span data-ttu-id="e2532-131">[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="e2532-131">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="e2532-132">[**要素**] パネルの [**計算**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="e2532-132">Go to the **Computed** tab in the **Elements** panel.</span></span>  

> [!NOTE]
> <span data-ttu-id="e2532-133">横長の DevTools ウィンドウでは、[ **計算** ] タブは存在しません。</span><span class="sxs-lookup"><span data-stu-id="e2532-133">On a wide DevTools window, the **Computed** tab does not exist.</span></span>  <span data-ttu-id="e2532-134">[ **計算** ] タブの内容は、[ **スタイル** ] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2532-134">The contents of the **Computed** tab are shown on the **Styles** tab.</span></span>  

<span data-ttu-id="e2532-135">継承されたプロパティは不透明です。</span><span class="sxs-lookup"><span data-stu-id="e2532-135">Inherited properties are opaque.</span></span>  <span data-ttu-id="e2532-136">継承されたすべての値を表示するには、[ **すべて表示** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e2532-136">Check the **Show All** checkbox to see all inherited values.</span></span>  

> [!NOTE]
> <span data-ttu-id="e2532-137">次の図では、[ **計算** ] タブに、現在選択されている要素に適用されている CSS プロパティが表示されて `h1` います。</span><span class="sxs-lookup"><span data-stu-id="e2532-137">In the following figure, the **Computed** tab shows the CSS properties being applied to the currently-selected `h1` element.</span></span>  

:::image type="complex" source="../media/css-elements-computed-h1.msft.png" alt-text="[計算] タブ" lightbox="../media/css-elements-computed-h1.msft.png":::
   <span data-ttu-id="e2532-139">[ **計算** ] タブ</span><span class="sxs-lookup"><span data-stu-id="e2532-139">The **Computed** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="e2532-140">CSS プロパティがアルファベット順に表示される</span><span class="sxs-lookup"><span data-stu-id="e2532-140">View CSS properties in alphabetical order</span></span>  

<span data-ttu-id="e2532-141">[ **計算** ] タブを使用します。 「 [要素に実際に適用されている CSS のみを表示する](#view-only-the-css-that-is-actually-applied-to-an-element)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2532-141">Use the **Computed** tab.  See [View only the CSS that is actually applied to an element](#view-only-the-css-that-is-actually-applied-to-an-element).</span></span>  

### <span data-ttu-id="e2532-142">継承した CSS プロパティを表示する</span><span class="sxs-lookup"><span data-stu-id="e2532-142">View inherited CSS properties</span></span>  

<span data-ttu-id="e2532-143">[**計算**] タブの [**すべて表示**] チェックボックスをオンにします。 「[要素に実際に適用されている CSS のみを表示する](#view-only-the-css-that-is-actually-applied-to-an-element)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2532-143">Check the **Show All** checkbox in the **Computed** tab.  See [View only the CSS that is actually applied to an element](#view-only-the-css-that-is-actually-applied-to-an-element).</span></span>  

### <span data-ttu-id="e2532-144">要素のボックスモデルを表示する</span><span class="sxs-lookup"><span data-stu-id="e2532-144">View the box model for an element</span></span>  

<span data-ttu-id="e2532-145">要素の [ボックスモデル][MDNBoxModel] を表示するには、[ **スタイル** ] タブに移動します。 DevTools ウィンドウが狭い場合、 **ボックスモデル** 図はタブの下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2532-145">To view [the box model][MDNBoxModel] of an element, go to the **Styles** tab.  If your DevTools window is narrow, the **Box Model** diagram is at the bottom of the tab.</span></span>  

<span data-ttu-id="e2532-146">値を変更するには、値を選んで編集します。</span><span class="sxs-lookup"><span data-stu-id="e2532-146">Choose and edit on a value to change a value.</span></span>  

> [!NOTE]
> <span data-ttu-id="e2532-147">次の図では、[**スタイル**] タブの**ボックスモデル**図は、現在選択されている要素のボックスモデルを示して `h1` います。</span><span class="sxs-lookup"><span data-stu-id="e2532-147">In the following figure, the **Box Model** diagram in the **Styles** tab shows the box model for the currently selected `h1` element.</span></span>  

:::image type="complex" source="../media/css-elements-styles-h1-2.msft.png" alt-text="ボックスモデル図" lightbox="../media/css-elements-styles-h1-2.msft.png":::
   <span data-ttu-id="e2532-149">**ボックスモデル**図</span><span class="sxs-lookup"><span data-stu-id="e2532-149">The **Box Model** diagram</span></span>  
:::image-end:::  

### <span data-ttu-id="e2532-150">要素の CSS を検索してフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="e2532-150">Search and filter the CSS of an element</span></span>  

<span data-ttu-id="e2532-151">[**スタイル**] および [**計算**] タブの [**フィルター** ] テキストボックスを使用して、特定の CSS プロパティまたは値を検索します。</span><span class="sxs-lookup"><span data-stu-id="e2532-151">Use the **Filter** text box on the **Styles** and **Computed** tabs to search for specific CSS properties or values.</span></span>  

<span data-ttu-id="e2532-152">[ **計算** ] タブで継承されたプロパティも検索するには、[ **すべて表示** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e2532-152">To also search inherited properties in the **Computed** tab, check the **Show All** checkbox.</span></span>  

> [!NOTE]
> <span data-ttu-id="e2532-153">次の図では、[ **スタイル** ] タブをフィルター処理して、検索クエリを含むルールのみを表示してい `color` ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-153">In the following figure, the **Styles** tab is filtered to only show rules that include the search query `color`.</span></span>  

:::image type="complex" source="../media/css-elements-styles-filter-color.msft.png" alt-text="[スタイル] タブをフィルター処理する" lightbox="../media/css-elements-styles-filter-color.msft.png":::
   <span data-ttu-id="e2532-155">[ **スタイル** ] タブをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="e2532-155">Filter the **Styles** tab</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="e2532-156">次の図では、[ **計算** ] タブをフィルター処理して、検索クエリを含む宣言のみが表示されるようにしてい `100%` ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-156">In the following figure, the **Computed** tab is filtered to only show declarations that include the search query `100%`.</span></span>  

:::image type="complex" source="../media/css-elements-computed-filter-100.msft.png" alt-text="計算されたタブをフィルター処理する" lightbox="../media/css-elements-computed-filter-100.msft.png":::
   <span data-ttu-id="e2532-158">**計算**されたタブをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="e2532-158">Filter the **Computed** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="e2532-159">擬似クラスの切り替え</span><span class="sxs-lookup"><span data-stu-id="e2532-159">Toggle a pseudo-class</span></span>  

<span data-ttu-id="e2532-160">次の操作を実行して、、、、またはなどの擬似クラスを切り替え `:active` `:focus` `:hover` `:visited` ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-160">Complete the following actions to toggle a pseudo-class like `:active`, `:focus`, `:hover`, or `:visited`.</span></span>  

1.  <span data-ttu-id="e2532-161">[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="e2532-161">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="e2532-162">[ **要素** ] パネルで、[ **スタイル** ] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="e2532-162">On the **Elements** panel, go to the **Styles** tab.</span></span>  
1.  <span data-ttu-id="e2532-163">[ **: Hov**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e2532-163">Choose **:hov**.</span></span>  
1.  <span data-ttu-id="e2532-164">有効にする擬似クラスを確認します。</span><span class="sxs-lookup"><span data-stu-id="e2532-164">Check the pseudo-class that you want to enable.</span></span>  

> [!NOTE]
> <span data-ttu-id="e2532-165">次の図では、 `:hover` 擬似クラスを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="e2532-165">In the following figure, toggle the `:hover` pseudo-class.</span></span>  <span data-ttu-id="e2532-166">ビューポートで、宣言が要素に適用されていることを確認し `background-color: cornflowerblue` ます。これは、要素が実際にマウスをポイントしていない場合でも同様です。</span><span class="sxs-lookup"><span data-stu-id="e2532-166">In the viewport verify that the `background-color: cornflowerblue` declaration is being applied to the element, even though the element is not actually being hovered over.</span></span>  

:::image type="complex" source="../media/css-elements-styles-hov-hover.msft.png" alt-text="切り替え: hover 擬似クラス" lightbox="../media/css-elements-styles-hov-hover.msft.png":::
   <span data-ttu-id="e2532-168">`:hover`擬似クラスの切り替え</span><span class="sxs-lookup"><span data-stu-id="e2532-168">Toggle the `:hover` pseudo-class</span></span>  
:::image-end:::  

<span data-ttu-id="e2532-169">インタラクティブなチュートリアルについては、「 [クラスに疑似状態を追加する][DevToolsCSSGetStartedAddPseudoState]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e2532-169">For an interactive tutorial, see [Add a pseudostate to a class][DevToolsCSSGetStartedAddPseudoState].</span></span>  

### <span data-ttu-id="e2532-170">印刷モードでページを表示する</span><span class="sxs-lookup"><span data-stu-id="e2532-170">View a page in print mode</span></span>  

<span data-ttu-id="e2532-171">印刷モードでページを表示するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2532-171">Complete the following actions to view a page in print mode.</span></span>  

1.  <span data-ttu-id="e2532-172">[コマンドメニューを開き][DevToolsCommandMenu]ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-172">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="e2532-173">入力を開始し `Rendering` 、を選択し `Show Rendering` ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-173">Start typing `Rendering` and select `Show Rendering`.</span></span>  
1.  <span data-ttu-id="e2532-174">[ **CSS メディアのエミュレート** ] ドロップダウンで、[ **印刷**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e2532-174">For the **Emulate CSS Media** dropdown, select **print**.</span></span>  

### <span data-ttu-id="e2532-175">[カバレッジ] タブで使用済みおよび未使用の CSS を表示する</span><span class="sxs-lookup"><span data-stu-id="e2532-175">View used and unused CSS with the Coverage tab</span></span>  

<span data-ttu-id="e2532-176">[カバレッジ] タブには、ページで実際に使用されている CSS が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2532-176">The Coverage tab shows you what CSS a page actually uses.</span></span>  

1.  <span data-ttu-id="e2532-177">`Control` + `Shift` + `P` `Command` + `Shift` + `P` Devtools がフォーカスされているときに[、][DevToolsCommandMenu][\ (Windows \)] または [\ (macOS \)] を選びます。コマンドメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="e2532-177">Select `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) while DevTools is in focus to [open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="e2532-178">入力 `coverage` を開始し、[ **カバレッジの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2532-178">Start typing `coverage` and select **Show Coverage**.</span></span>  <span data-ttu-id="e2532-179">[カバー] タブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2532-179">The Coverage tab appears.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-command-menu-coverage.msft.png" alt-text="[コマンド] メニューから [カバレッジ] タブを開く" lightbox="../media/css-console-command-menu-coverage.msft.png":::
             <span data-ttu-id="e2532-181">[**コマンド] メニュー**から [**カバレッジ**] タブを開く</span><span class="sxs-lookup"><span data-stu-id="e2532-181">Open the **Coverage** tab from the **Command Menu**</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-qs-coverage-empty.msft.png" alt-text="[カバレッジ] タブ" lightbox="../media/css-console-qs-coverage-empty.msft.png":::
             <span data-ttu-id="e2532-183">[ **カバレッジ** ] タブ</span><span class="sxs-lookup"><span data-stu-id="e2532-183">The **Coverage** tab</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="e2532-184">[ **インストルメントの開始] を選択し、ページを更新** し ![ ます (インストルメント化を開始し、ページを更新し ][ImageRefreshIcon] ます)。</span><span class="sxs-lookup"><span data-stu-id="e2532-184">Choose **Start instrumenting coverage and refresh the page** \(![Start instrumenting coverage and refresh the page][ImageRefreshIcon]\).</span></span>  <span data-ttu-id="e2532-185">ページの更新と [カバレッジ] タブには、ブラウザーが読み込む各ファイルからの CSS (および JavaScript \) の使用量の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2532-185">The page refreshes and the Coverage tab provides an overview of how much CSS \(and JavaScript\) is used from each file that the browser loads.</span></span>  <span data-ttu-id="e2532-186">緑色は、使用されている CSS を表します。</span><span class="sxs-lookup"><span data-stu-id="e2532-186">Green represents used CSS.</span></span>  <span data-ttu-id="e2532-187">赤は未使用の CSS を示します。</span><span class="sxs-lookup"><span data-stu-id="e2532-187">Red represents unused CSS.</span></span>  
    
    :::image type="complex" source="../media/css-console-qs-coverage-run.msft.png" alt-text="CSS (および JavaScript) が使用されていて未使用かどうかの概要" lightbox="../media/css-console-qs-coverage-run.msft.png":::
       <span data-ttu-id="e2532-189">CSS (および JavaScript \) が使用されていて未使用である割合の概要</span><span class="sxs-lookup"><span data-stu-id="e2532-189">An overview of how much CSS \(and JavaScript\) is used and unused</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="e2532-190">CSS ファイルを選択すると、使用する CSS の行ごとの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2532-190">Choose a CSS file to see a line-by-line breakdown of what CSS it uses.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="e2532-191">次の図では、145 ~ 147、149から151の行 `b66bc881.site-ltr.css` は未使用であり、行163から166に使用されています。</span><span class="sxs-lookup"><span data-stu-id="e2532-191">In the following figure, lines 145 to 147 and 149 to 151 of `b66bc881.site-ltr.css` are unused, whereas lines 163 to 166 are used.</span></span>  
    
    :::image type="complex" source="../media/css-sources-css-coverage.msft.png" alt-text="使用されている、未使用の CSS の行単位の内訳" lightbox="../media/css-sources-css-coverage.msft.png":::
       <span data-ttu-id="e2532-193">使用されている、未使用の CSS の行単位の内訳</span><span class="sxs-lookup"><span data-stu-id="e2532-193">A line-by-line breakdown of used and unused CSS</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="e2532-194">印刷プレビューモードの強制</span><span class="sxs-lookup"><span data-stu-id="e2532-194">Force print preview mode</span></span>  

<span data-ttu-id="e2532-195">「 [DevTools を印刷プレビューモードに強制][DevToolsCssPrintPreview]する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e2532-195">See [Force DevTools into Print Preview mode][DevToolsCssPrintPreview].</span></span>  

## <span data-ttu-id="e2532-196">CSS を変更する</span><span class="sxs-lookup"><span data-stu-id="e2532-196">Change CSS</span></span>  

<!-- todo s/CSS declaration/declaration/ -->  

### <span data-ttu-id="e2532-197">要素に CSS 宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="e2532-197">Add a CSS declaration to an element</span></span>  

<span data-ttu-id="e2532-198">宣言の順序は要素のスタイルに影響を及ぼし、さまざまな方法で宣言を追加するために、次の一覧を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2532-198">The order of declarations affects how an element is styled, use the following list to help you add declarations in different ways.</span></span>  

*   <span data-ttu-id="e2532-199">[インライン宣言を追加](#add-an-inline-declaration)します。</span><span class="sxs-lookup"><span data-stu-id="e2532-199">[Add a inline declaration](#add-an-inline-declaration).</span></span>  <span data-ttu-id="e2532-200">要素の HTML に属性を追加することと同じです `style` 。</span><span class="sxs-lookup"><span data-stu-id="e2532-200">Equivalent to adding a `style` attribute to the HTML of an element.</span></span>  
*   <span data-ttu-id="e2532-201">[スタイルルールに宣言を追加](#add-a-declaration-to-a-style-rule)します。</span><span class="sxs-lookup"><span data-stu-id="e2532-201">[Add a declaration to a style rule](#add-a-declaration-to-a-style-rule).</span></span>  

**<span data-ttu-id="e2532-202">使用するワークフロー</span><span class="sxs-lookup"><span data-stu-id="e2532-202">What workflow should you use?</span></span>** <span data-ttu-id="e2532-203">ほとんどのシナリオでは、通常、インライン宣言ワークフローを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2532-203">For most scenarios, you probably want to use the inline declaration workflow.</span></span>  <span data-ttu-id="e2532-204">インライン宣言の内容が外部の宣言よりも高いため、インラインワークフローによって予期される要素で変更が有効になります。</span><span class="sxs-lookup"><span data-stu-id="e2532-204">Inline declarations have higher specificity than external ones, so the inline workflow ensures that the changes take effect in your expected element.</span></span>  <span data-ttu-id="e2532-205">特異性の詳細については、「 [セレクターの種類][MDNSelectorTypes]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2532-205">For more information about specificity, see [Selector Types][MDNSelectorTypes].</span></span>  

<span data-ttu-id="e2532-206">要素のスタイルをデバッグしていて、宣言がさまざまな場所で定義されている場合に何が起こるかを明確にテストする必要がある場合は、他のワークフローを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2532-206">If you are debugging any styles of the element and you need to specifically test what happens when a declaration is defined in different places, use the other workflow.</span></span>  

#### <span data-ttu-id="e2532-207">インライン宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="e2532-207">Add an inline declaration</span></span>  

<span data-ttu-id="e2532-208">インライン宣言を追加するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2532-208">Complete the following actions to add an inline declaration.</span></span>  

1.  <span data-ttu-id="e2532-209">[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="e2532-209">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="e2532-210">[**スタイル**] ウィンドウで、[スタイル] セクションのかっこを選択します **。**</span><span class="sxs-lookup"><span data-stu-id="e2532-210">In the **Styles** pane, choose between the brackets of the **element.style** section.</span></span>  <span data-ttu-id="e2532-211">カーソルがフォーカスされ、テキストの入力が可能になります。</span><span class="sxs-lookup"><span data-stu-id="e2532-211">The cursor focuses, allowing you to enter text.</span></span>  
1.  <span data-ttu-id="e2532-212">プロパティ名を入力して、を選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-212">Enter a property name and select `Enter`.</span></span>  
1.  <span data-ttu-id="e2532-213">そのプロパティの有効な値を入力して、を選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-213">Enter a valid value for that property and select `Enter`.</span></span>  <span data-ttu-id="e2532-214">**DOM ツリー**で、 `style` 属性が要素に追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e2532-214">In the **DOM Tree**, verify that a `style` attribute has been added to the element.</span></span>  

> [!NOTE]
> <span data-ttu-id="e2532-215">次の図では、 `margin-top` と `background-color` プロパティが選択された要素に適用されています。</span><span class="sxs-lookup"><span data-stu-id="e2532-215">In the following figure, the `margin-top` and `background-color` properties have been applied to the selected element.</span></span>  <span data-ttu-id="e2532-216">**DOM ツリー**で、宣言が要素の属性に反映されていることを確認し `style` ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-216">In the **DOM Tree** verify that the declarations are reflected in the `style` attribute for an element.</span></span>  

:::image type="complex" source="../media/css-elements-styles-margin-top-background-color.msft.png" alt-text="インライン宣言を追加する" lightbox="../media/css-elements-styles-margin-top-background-color.msft.png":::
   <span data-ttu-id="e2532-218">インライン宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="e2532-218">Add inline declarations</span></span>  
:::image-end:::  

#### <span data-ttu-id="e2532-219">スタイルルールに宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="e2532-219">Add a declaration to a style rule</span></span>  

<span data-ttu-id="e2532-220">既存のスタイルルールに宣言を追加するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2532-220">Complete the following actions to add a declaration to an existing style rule.</span></span>  

1.  <span data-ttu-id="e2532-221">[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="e2532-221">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="e2532-222">[ **スタイル** ] ウィンドウで、宣言を追加するスタイルルールのかっこの間を選びます。</span><span class="sxs-lookup"><span data-stu-id="e2532-222">In the **Styles** pane, choose between the brackets of the style rule to which you want to add the declaration.</span></span>  <span data-ttu-id="e2532-223">カーソルがフォーカスされ、テキストの入力が可能になります。</span><span class="sxs-lookup"><span data-stu-id="e2532-223">The cursor focuses, allowing you to enter text.</span></span>  
1.  <span data-ttu-id="e2532-224">プロパティ名を入力して、を選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-224">Enter a property name and select `Enter`.</span></span>  
1.  <span data-ttu-id="e2532-225">そのプロパティの有効な値を入力して、を選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-225">Enter a valid value for that property and select `Enter`.</span></span>  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style.msft.png" alt-text="スタイルルールへの宣言の追加" lightbox="../media/css-elements-styles-border-bottom-style.msft.png":::
   <span data-ttu-id="e2532-227">`border-bottom-style:groove`スタイルルールに宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="e2532-227">Add the `border-bottom-style:groove` declaration to a style rule</span></span>  
:::image-end:::  

### <span data-ttu-id="e2532-228">宣言の名前または値を変更する</span><span class="sxs-lookup"><span data-stu-id="e2532-228">Change a declaration name or value</span></span>  

<span data-ttu-id="e2532-229">宣言の名前または値を選んで編集し、それを変更します。</span><span class="sxs-lookup"><span data-stu-id="e2532-229">Choose and edit the name or value of a declaration to change it.</span></span>  <span data-ttu-id="e2532-230">すばやく値を増減するためのショートカットキーについては、「 [宣言の値を変更](#change-declaration-values-with-keyboard-shortcuts) する」を参照してください `0.1` `1` `10` `100` 。</span><span class="sxs-lookup"><span data-stu-id="e2532-230">See [Change declaration values with keyboard shortcuts](#change-declaration-values-with-keyboard-shortcuts) for shortcuts for quickly incrementing or decrementing a value by `0.1`, `1`, `10`, or `100` units.</span></span>  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style-dropdown.msft.png" alt-text="宣言の値を変更する" lightbox="../media/css-elements-styles-border-bottom-style-dropdown.msft.png":::
   <span data-ttu-id="e2532-232">宣言の値を変更する `border-bottom-style`</span><span class="sxs-lookup"><span data-stu-id="e2532-232">Change the value of the `border-bottom-style` declaration</span></span>  
:::image-end:::  

### <span data-ttu-id="e2532-233">キーボードショートカットを使用して宣言の値を変更する</span><span class="sxs-lookup"><span data-stu-id="e2532-233">Change declaration values with keyboard shortcuts</span></span>  

<span data-ttu-id="e2532-234">宣言の値を編集しているときに、次のショートカットキーを使用して、指定した値だけ値をインクリメントすることができます。</span><span class="sxs-lookup"><span data-stu-id="e2532-234">While editing the value of a declaration, you may use the following keyboard shortcuts to increment the value by a specific amount.</span></span>  

*   <span data-ttu-id="e2532-235">[ `Alt` + `Up` \ (Windows \)] または [ `Option` + `Up` \ (macOS \) `0.1` ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e2532-235">Select `Alt`+`Up` \(Windows\) or `Option`+`Up` \(macOS\) to increment by `0.1`.</span></span>  
*   <span data-ttu-id="e2532-236">値を選択 `Up` する `1` か、 `0.1` 現在の値が and の間にある場合は、を選択し `-1` `1` ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-236">Select `Up` to change the value by `1`, or by `0.1` if the current value is between `-1` and `1`.</span></span>  
*   <span data-ttu-id="e2532-237">[増分] を選択し `Shift` + `Up` `10` ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-237">Select `Shift`+`Up` to increment by `10`.</span></span>  
*   <span data-ttu-id="e2532-238">`Shift` + `Page Up` 値を増やすには、\ (Windows \) または `Shift` + `Command` + `Up` \ (macOS \) `100` を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2532-238">Select `Shift`+`Page Up` \(Windows\) or `Shift`+`Command`+`Up` \(macOS\) to increment the value by `100`.</span></span>  

<span data-ttu-id="e2532-239">減分も動作します。</span><span class="sxs-lookup"><span data-stu-id="e2532-239">Decrementing also works.</span></span>  <span data-ttu-id="e2532-240">`Up`上記で説明した各インスタンスをに置き換え `Down` ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-240">Just replace each instance of `Up` mentioned above with `Down`.</span></span>  

### <span data-ttu-id="e2532-241">要素にクラスを追加する</span><span class="sxs-lookup"><span data-stu-id="e2532-241">Add a class to an element</span></span>  

<span data-ttu-id="e2532-242">要素にクラスを追加するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2532-242">Complete the following actions to add a class to an element.</span></span>  

1.  <span data-ttu-id="e2532-243">**DOM ツリー**で[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="e2532-243">[Select the element](#select-an-element) in the **DOM Tree**.</span></span>  
1.  <span data-ttu-id="e2532-244">**Cls**を選びます。</span><span class="sxs-lookup"><span data-stu-id="e2532-244">Choose **.cls**.</span></span>  
1.  <span data-ttu-id="e2532-245">[ **Add New class** ] テキストボックスにクラスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2532-245">Enter the name of the class in the **Add New Class** text box.</span></span>  
1.  <span data-ttu-id="e2532-246">を選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-246">Select `Enter`.</span></span>  

:::image type="complex" source="../media/css-elements-styles-filter-classes.msft.png" alt-text="[要素クラス] ウィンドウ" lightbox="../media/css-elements-styles-filter-classes.msft.png":::
   <span data-ttu-id="e2532-248">[ **要素クラス** ] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="e2532-248">The **Element Classes** pane</span></span>  
:::image-end:::  

### <span data-ttu-id="e2532-249">クラスの切り替え</span><span class="sxs-lookup"><span data-stu-id="e2532-249">Toggle a class</span></span>  

<span data-ttu-id="e2532-250">要素のクラスを有効または無効にするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2532-250">Complete the following actions to enable or disable a class on an element.</span></span>  

1.  <span data-ttu-id="e2532-251">**DOM ツリー**で[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="e2532-251">[Select the element](#select-an-element) in the **DOM Tree**.</span></span>  
1.  <span data-ttu-id="e2532-252">[ **要素クラス** ] ペインを開きます。</span><span class="sxs-lookup"><span data-stu-id="e2532-252">Open the **Element Classes** pane.</span></span>  <span data-ttu-id="e2532-253">「 [要素にクラスを追加する」を](#add-a-class-to-an-element)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e2532-253">See [Add a class to an element](#add-a-class-to-an-element).</span></span>  <span data-ttu-id="e2532-254">[ **新しいクラスの追加** ] テキストボックスの下には、特定の要素に適用されるすべてのクラスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2532-254">Below the **Add New Class** text box are all of the classes that are being applied to the specific element.</span></span>  
1.  <span data-ttu-id="e2532-255">有効または無効にするクラスの横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e2532-255">Toggle the checkbox next to the class that you want to enable or disable.</span></span>  

### <span data-ttu-id="e2532-256">スタイルルールを追加する</span><span class="sxs-lookup"><span data-stu-id="e2532-256">Add a style rule</span></span>  

<span data-ttu-id="e2532-257">新しいスタイルルールを追加するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2532-257">Complete the following actions to add a new style rule.</span></span>  

1.  <span data-ttu-id="e2532-258">[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="e2532-258">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="e2532-259">[ **新しいスタイルルール** ] ([ ![ 新しいスタイルルール]) を選び ][ImageNewStyleRuleIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-259">Choose **New Style Rule** \(![New Style Rule][ImageNewStyleRuleIcon]\).</span></span>  <span data-ttu-id="e2532-260">DevTools は、 **要素のスタイル** ルールの下に新しいルールを挿入します。</span><span class="sxs-lookup"><span data-stu-id="e2532-260">DevTools inserts a new rule beneath the **element.style** rule.</span></span>  

> [!NOTE]
> <span data-ttu-id="e2532-261">次の図では、 `h1.devsite-page-title` **新しいスタイルルール**を選択すると、devtools でスタイルルールが追加されます。</span><span class="sxs-lookup"><span data-stu-id="e2532-261">In the following figure, DevTools adds the `h1.devsite-page-title` style rule after you choose **New Style Rule**.</span></span>  

:::image type="complex" source="../media/css-elements-styles-style-new.msft.png" alt-text="新しいスタイルルールを追加する" lightbox="../media/css-elements-styles-style-new.msft.png":::
   <span data-ttu-id="e2532-263">新しいスタイルルールを追加する</span><span class="sxs-lookup"><span data-stu-id="e2532-263">Add a new style rule</span></span>  
:::image-end:::  

#### <span data-ttu-id="e2532-264">ルールを追加するスタイルを選択する</span><span class="sxs-lookup"><span data-stu-id="e2532-264">Choose which stylesheet to add a rule to</span></span>  

<span data-ttu-id="e2532-265">[新しいスタイルルールを追加](#add-a-style-rule)するときに、[**新しい**スタイルルール] (新しいスタイルルール) を選んで保持して、 ![ ][ImageNewStyleRuleIcon] スタイルルールを追加するスタイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2532-265">When [adding a new style rule](#add-a-style-rule), choose and hold **New Style Rule** \(![New Style Rule][ImageNewStyleRuleIcon]\) to choose which stylesheet to add the style rule to.</span></span>  

:::image type="complex" source="../media/css-elements-styles-style-new-select-existing.msft.png" alt-text="スタイルシートを選択する" lightbox="../media/css-elements-styles-style-new-select-existing.msft.png":::
   <span data-ttu-id="e2532-267">スタイルシートを選択する</span><span class="sxs-lookup"><span data-stu-id="e2532-267">Choose a stylesheet</span></span>  
:::image-end:::  

#### <span data-ttu-id="e2532-268">特定の場所にスタイルルールを追加する</span><span class="sxs-lookup"><span data-stu-id="e2532-268">Add a style rule to a specific location</span></span>  

<span data-ttu-id="e2532-269">[ **スタイル** ] タブの特定の場所にスタイルルールを追加するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2532-269">Complete the following actions to add a style rule to a specific location in the **Styles** tab.</span></span>  

1.  <span data-ttu-id="e2532-270">新しいスタイルルールを追加する場所のすぐ上のスタイルルールにマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="e2532-270">Hover over the style rule that is directly above where you want to add your new style rule.</span></span>  
1.  <span data-ttu-id="e2532-271">[[ **その他の操作** ] ツールバーを](#reveal-the-more-actions-toolbar)表示します。</span><span class="sxs-lookup"><span data-stu-id="e2532-271">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="e2532-272">[ **スタイルルールの挿入** ] を選択します (下に ![ スタイルルールを挿入 ][ImageNewStyleRuleIcon] します)。</span><span class="sxs-lookup"><span data-stu-id="e2532-272">Choose **Insert Style Rule Below** \(![Insert Style Rule Below][ImageNewStyleRuleIcon]\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-insert-style-rule-below.msft.png" alt-text="下にスタイルルールを挿入する" lightbox="../media/css-elements-styles-insert-style-rule-below.msft.png":::
   **<span data-ttu-id="e2532-274">下にスタイルルールを挿入する</span><span class="sxs-lookup"><span data-stu-id="e2532-274">Insert Style Rule Below</span></span>**  
:::image-end:::  

### <span data-ttu-id="e2532-275">[その他の操作] ツールバーを表示する</span><span class="sxs-lookup"><span data-stu-id="e2532-275">Reveal the More Actions toolbar</span></span>  

<span data-ttu-id="e2532-276">[ **その他の操作** ] ツールバーを使用すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e2532-276">The **More Actions** toolbar lets you perform the following actions.</span></span>  

*   <span data-ttu-id="e2532-277">優先するスタイルルールのすぐ下にスタイルルールを挿入します。</span><span class="sxs-lookup"><span data-stu-id="e2532-277">Insert a style rule directly below the one you are focused on.</span></span>  
*   <span data-ttu-id="e2532-278">`background-color` `color` `box-shadow` `text-shadow` フォーカスされているスタイルルールに、、、、または宣言を追加します。</span><span class="sxs-lookup"><span data-stu-id="e2532-278">Add a `background-color`, `color`, `box-shadow`, or `text-shadow` declaration to the style rule you are focused on.</span></span>  

<span data-ttu-id="e2532-279">[ **その他の操作** ] ツールバーを表示するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2532-279">Complete the following actions to reveal the **More Actions** toolbar.</span></span>  

1.  <span data-ttu-id="e2532-280">[ **スタイル** ] タブで、スタイルルールの上にマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="e2532-280">In the **Styles** tab, hover over a style rule.</span></span>  <span data-ttu-id="e2532-281">**More Actions** `...` [スタイルルール] セクションの右下にある [その他のアクション] \ (\) が公開されます。</span><span class="sxs-lookup"><span data-stu-id="e2532-281">**More Actions** \(`...`\) is revealed in the bottom-right of the style rule section.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="e2532-282">次の図では、スタイルルールにマウスポインターを合わせる `.header-holder.has-default-focus` と、[スタイルルール] セクションの右下に [ **その他のアクション** ] が現れています。</span><span class="sxs-lookup"><span data-stu-id="e2532-282">In the following figure, hover over the `.header-holder.has-default-focus` style rule and **More Actions** is revealed in the bottom-right of the style rule section.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-new-rule-styles.msft.png" alt-text="その他のアクションを表示" lightbox="../media/css-elements-styles-new-rule-styles.msft.png":::
       <span data-ttu-id="e2532-284">**その他のアクション**を表示 \ ( `...` \)</span><span class="sxs-lookup"><span data-stu-id="e2532-284">Reveal **More Actions** \(`...`\)</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="e2532-285">上で**More Actions** `...` 説明した操作を表示するには、[その他のアクション] (\) をポイントします。</span><span class="sxs-lookup"><span data-stu-id="e2532-285">Hover over **More Actions** \(`...`\) to reveal the actions mentioned above.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="e2532-286">[ **次のスタイルルールの挿入** アクションを実行すると、 **その他の操作**をマウスでポイントしたときに、次のように</span><span class="sxs-lookup"><span data-stu-id="e2532-286">The **Insert Style Rule Below** action is revealed after hovering over **More Actions**.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png" alt-text="[その他の操作] ツールバー" lightbox="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png":::
       <span data-ttu-id="e2532-288">[ **その他の操作** ] ツールバー</span><span class="sxs-lookup"><span data-stu-id="e2532-288">The **More Actions** toolbar</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="e2532-289">宣言を切り替える</span><span class="sxs-lookup"><span data-stu-id="e2532-289">Toggle a declaration</span></span>  

<span data-ttu-id="e2532-290">Folllwoing アクションを完了して \ (またはオフ) の1つの宣言を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="e2532-290">Complete the folllwoing actions to toggle a single declaration on \(or off\).</span></span>  

1.  <span data-ttu-id="e2532-291">[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="e2532-291">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="e2532-292">[ **スタイル** ] ウィンドウで、宣言を定義するルールの上にマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="e2532-292">In the **Styles** pane, hover over the rule that defines the declaration.</span></span>  <span data-ttu-id="e2532-293">各宣言の横にチェックボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2532-293">A checkbox appears next to each declaration.</span></span>  
1.  <span data-ttu-id="e2532-294">宣言の横にあるチェックボックスをオン (またはオフ) にします。</span><span class="sxs-lookup"><span data-stu-id="e2532-294">Check \(or uncheck\) the checkbox next to the declaration.</span></span>  <span data-ttu-id="e2532-295">宣言をオフにすると、DevTools がその宣言を超えて、アクティブでなくなったことを示します。</span><span class="sxs-lookup"><span data-stu-id="e2532-295">When you uncheck a declaration, DevTools crosses it out to indicate that it is no longer active.</span></span>  

> [!NOTE]
> <span data-ttu-id="e2532-296">次の図では、 `margin-top` 現在選択されている要素のプロパティがトグルオフになっています。</span><span class="sxs-lookup"><span data-stu-id="e2532-296">In the following figure, the `margin-top` property for the currently selected element has been toggled off.</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-deactivated.msft.png" alt-text="宣言を切り替える" lightbox="../media/css-elements-styles-rule-deactivated.msft.png":::
   <span data-ttu-id="e2532-298">宣言を切り替える</span><span class="sxs-lookup"><span data-stu-id="e2532-298">Toggle a declaration</span></span>  
:::image-end:::  

### <span data-ttu-id="e2532-299">背景色の宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="e2532-299">Add a background-color declaration</span></span>  

<span data-ttu-id="e2532-300">要素に宣言を追加するには、次の操作を実行し `background-color` ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-300">Complete the following actions to add a `background-color` declaration to an element.</span></span>  

1.  <span data-ttu-id="e2532-301">宣言を追加するスタイルルールの上にマウスポインターを置き `background-color` ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-301">Hover over the style rule that you want to add the `background-color` declaration to.</span></span>  
1.  <span data-ttu-id="e2532-302">[[ **その他の操作** ] ツールバーを](#reveal-the-more-actions-toolbar)表示します。</span><span class="sxs-lookup"><span data-stu-id="e2532-302">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="e2532-303">[ **背景色の追加** ] ( ![ 背景色 ][ImageAddBackgroundColorIcon] の追加) を選びます。</span><span class="sxs-lookup"><span data-stu-id="e2532-303">Choose **Add Background Color** \(![Add Background Color][ImageAddBackgroundColorIcon]\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-background-color.msft.png" alt-text="背景色を追加する" lightbox="../media/css-elements-styles-rule-add-background-color.msft.png":::
   **<span data-ttu-id="e2532-305">背景色を追加する</span><span class="sxs-lookup"><span data-stu-id="e2532-305">Add Background Color</span></span>**  
:::image-end:::  

### <span data-ttu-id="e2532-306">色の宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="e2532-306">Add a color declaration</span></span>  

<span data-ttu-id="e2532-307">要素に宣言を追加するには、次の操作を実行し `color` ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-307">Complete the following actions to add a `color` declaration to an element.</span></span>  

1.  <span data-ttu-id="e2532-308">宣言を追加するスタイルルールの上にマウスポインターを置き `color` ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-308">Hover over the style rule that you want to add the `color` declaration to.</span></span>  
1.  <span data-ttu-id="e2532-309">[[ **その他の操作** ] ツールバーを](#reveal-the-more-actions-toolbar)表示します。</span><span class="sxs-lookup"><span data-stu-id="e2532-309">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="e2532-310">[ **色の追加** ] ( ![ 色 ][ImageAddColorIcon] の追加 \) を選びます。</span><span class="sxs-lookup"><span data-stu-id="e2532-310">Choose **Add Color** \(![Add Color][ImageAddColorIcon]\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-color.msft.png" alt-text="色を追加する" lightbox="../media/css-elements-styles-rule-add-color.msft.png":::
   **<span data-ttu-id="e2532-312">色を追加する</span><span class="sxs-lookup"><span data-stu-id="e2532-312">Add Color</span></span>**  
:::image-end:::  

### <span data-ttu-id="e2532-313">ボックスシャドウ宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="e2532-313">Add a box-shadow declaration</span></span>  

<span data-ttu-id="e2532-314">要素に宣言を追加するには、次の操作を実行し `box-shadow` ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-314">Complete the follwoing actions to add a `box-shadow` declaration to an element.</span></span>  

1.  <span data-ttu-id="e2532-315">宣言を追加するスタイルルールの上にマウスポインターを置き `box-shadow` ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-315">Hover over the style rule that you want to add the `box-shadow` declaration to.</span></span>  
1.  <span data-ttu-id="e2532-316">[[ **その他の操作** ] ツールバーを](#reveal-the-more-actions-toolbar)表示します。</span><span class="sxs-lookup"><span data-stu-id="e2532-316">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="e2532-317">[ **Add Box shadow** ] ( ![ ボックスの影を追加) を選び ][ImageAddBoxShadowIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-317">Choose **Add Box Shadow** \(![Add Box Shadow][ImageAddBoxShadowIcon]\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-box-shadow.msft.png" alt-text="ボックスの影を追加する" lightbox="../media/css-elements-styles-rule-add-box-shadow.msft.png":::
   **<span data-ttu-id="e2532-319">ボックスの影を追加する</span><span class="sxs-lookup"><span data-stu-id="e2532-319">Add Box Shadow</span></span>**  
:::image-end:::  

### <span data-ttu-id="e2532-320">テキストシャドウの宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="e2532-320">Add a text-shadow declaration</span></span>  

<span data-ttu-id="e2532-321">要素に宣言を追加するには、次の操作を実行し `text-shadow` ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-321">Complete the following actions to add a `text-shadow` declaration to an element.</span></span>  

1.  <span data-ttu-id="e2532-322">宣言を追加するスタイルルールの上にマウスポインターを置き `text-shadow` ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-322">Hover over the style rule that you want to add the `text-shadow` declaration to.</span></span>  
1.  <span data-ttu-id="e2532-323">[[ **その他の操作** ] ツールバーを](#reveal-the-more-actions-toolbar)表示します。</span><span class="sxs-lookup"><span data-stu-id="e2532-323">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="e2532-324">[ **テキストの影** を追加] \ ( ![ テキストの影を追加) を選択し ][ImageAddTextShadowIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-324">Choose **Add Text Shadow** \(![Add Text Shadow][ImageAddTextShadowIcon]\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-text-shadow.msft.png" alt-text="テキストの影を追加する" lightbox="../media/css-elements-styles-rule-add-text-shadow.msft.png":::
   **<span data-ttu-id="e2532-326">テキストの影を追加する</span><span class="sxs-lookup"><span data-stu-id="e2532-326">Add Text Shadow</span></span>**  
:::image-end:::  

### <span data-ttu-id="e2532-327">カラーピッカーを使用して色を変更する</span><span class="sxs-lookup"><span data-stu-id="e2532-327">Change colors with the Color Picker</span></span>  

<span data-ttu-id="e2532-328">**カラーピッカー**は、変更と宣言のための GUI を提供し `color` `background-color` ます。</span><span class="sxs-lookup"><span data-stu-id="e2532-328">The **Color Picker** provides a GUI for changing `color` and `background-color` declarations.</span></span>  

<span data-ttu-id="e2532-329">次の操作を実行して、 **カラーピッカー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="e2532-329">Complete the following actions to open the **Color Picker**.</span></span>  

1.  <span data-ttu-id="e2532-330">[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="e2532-330">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="e2532-331">[ **スタイル** ] タブで、変更する、 `color` `background-color` または同様の宣言を見つけます。</span><span class="sxs-lookup"><span data-stu-id="e2532-331">In the **Styles** tab, find the `color`, `background-color`, or similar declaration that you want to change.</span></span>  <span data-ttu-id="e2532-332">、、 `color` `background-color` または同様の値の左側に、色のプレビューである小さな四角形が表示されています。</span><span class="sxs-lookup"><span data-stu-id="e2532-332">To the left of the `color`, `background-color`, or similar value, there is a small square which is a preview of the color.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="e2532-333">次の図では、左側の小さな四角形 `rgba(0, 0, 0, 0.7)` がその色のプレビューです。</span><span class="sxs-lookup"><span data-stu-id="e2532-333">In the following figure, the small square to the left of `rgba(0, 0, 0, 0.7)` is a preview of that color.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-rule-overlay-color-box.msft.png" alt-text="色のプレビュー" lightbox="../media/css-elements-styles-rule-overlay-color-box.msft.png":::
       <span data-ttu-id="e2532-335">色のプレビュー</span><span class="sxs-lookup"><span data-stu-id="e2532-335">Color preview</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="e2532-336">プレビューを選択して、 **カラーピッカー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="e2532-336">Choose the preview to open the **Color Picker**.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-rule-color-picker.msft.png" alt-text="色のパレット" lightbox="../media/css-elements-styles-rule-color-picker.msft.png":::
       <span data-ttu-id="e2532-338">**色のパレット**</span><span class="sxs-lookup"><span data-stu-id="e2532-338">The **Color Picker**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="e2532-339">次の図と、 **カラーピッカー**の各 UI 要素のはを示します。</span><span class="sxs-lookup"><span data-stu-id="e2532-339">The following figure and list descries of each of the UI elements of the **Color Picker**.</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-color-picker-annotated.msft.png" alt-text="カラーピッカーの注釈" lightbox="../media/css-elements-styles-rule-color-picker-annotated.msft.png":::
   <span data-ttu-id="e2532-341">**カラーピッカー**の注釈</span><span class="sxs-lookup"><span data-stu-id="e2532-341">The **Color Picker**, annotated</span></span>  
:::image-end:::  

:::row:::
   :::column span="1":::
      <span data-ttu-id="e2532-342">件</span><span class="sxs-lookup"><span data-stu-id="e2532-342">1</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="e2532-343">明るい</span><span class="sxs-lookup"><span data-stu-id="e2532-343">Shades</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="e2532-344">両面</span><span class="sxs-lookup"><span data-stu-id="e2532-344">2</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="e2532-345">スポイト</span><span class="sxs-lookup"><span data-stu-id="e2532-345">Eyedropper</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="e2532-346">詳細については、「スポイトを使用して [ページの色を設定する](#sample-a-color-off-the-page-with-the-eyedropper)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2532-346">For more information, see [Sample a color off the page with the Eyedropper](#sample-a-color-off-the-page-with-the-eyedropper).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="e2532-347">-</span><span class="sxs-lookup"><span data-stu-id="e2532-347">3</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="e2532-348">クリップボードにコピー</span><span class="sxs-lookup"><span data-stu-id="e2532-348">Copy To Clipboard</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="e2532-349">**表示値**をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="e2532-349">Copy the **Display Value** to your clipboard.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="e2532-350">4d</span><span class="sxs-lookup"><span data-stu-id="e2532-350">4</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="e2532-351">表示値</span><span class="sxs-lookup"><span data-stu-id="e2532-351">Display Value</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="e2532-352">色の RGBA、HSLA、または16進表現。</span><span class="sxs-lookup"><span data-stu-id="e2532-352">The RGBA, HSLA, or Hex representation of the color.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="e2532-353">個</span><span class="sxs-lookup"><span data-stu-id="e2532-353">5</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="e2532-354">カラー パレット</span><span class="sxs-lookup"><span data-stu-id="e2532-354">Color Palette</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="e2532-355">四角形のいずれかを選んで、その四角形に色を変更します。</span><span class="sxs-lookup"><span data-stu-id="e2532-355">Choose one of the squares to change the color to that square.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="e2532-356">=</span><span class="sxs-lookup"><span data-stu-id="e2532-356">6</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="e2532-357">色相</span><span class="sxs-lookup"><span data-stu-id="e2532-357">Hue</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="e2532-358">日</span><span class="sxs-lookup"><span data-stu-id="e2532-358">7</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="e2532-359">Opacity</span><span class="sxs-lookup"><span data-stu-id="e2532-359">Opacity</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="e2532-360">個</span><span class="sxs-lookup"><span data-stu-id="e2532-360">8</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="e2532-361">値の表示スイッチャー</span><span class="sxs-lookup"><span data-stu-id="e2532-361">Display Value Switcher</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="e2532-362">現在の色の RGBA、HSLA、16進表現を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="e2532-362">Toggle between the RGBA, HSLA, and Hex representations of the current color.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="e2532-363">ファイブ</span><span class="sxs-lookup"><span data-stu-id="e2532-363">9</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="e2532-364">カラーパレットスイッチャー</span><span class="sxs-lookup"><span data-stu-id="e2532-364">Color Palette Switcher</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="e2532-365">[マテリアルデザインパレット][MaterialDesignColorSystem]、カスタムパレット、またはページカラーパレットを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="e2532-365">Toggle between the [Material Design palette][MaterialDesignColorSystem], a custom palette, or a page colors palette.</span></span>  <span data-ttu-id="e2532-366">DevTools は、スタイルシートで検出された色に基づいてページカラーパレットを生成します。</span><span class="sxs-lookup"><span data-stu-id="e2532-366">DevTools generates the page color palette based on the colors that it finds in your stylesheets.</span></span>  
   :::column-end:::
:::row-end:::  

#### <span data-ttu-id="e2532-367">スポイトを使用してページの色を設定する</span><span class="sxs-lookup"><span data-stu-id="e2532-367">Sample a color off the page with the Eyedropper</span></span>  

<span data-ttu-id="e2532-368">**カラーピッカー**を開くと、**スポイト**( ![ スポイト ][ImageEyedropperIcon] ) がデフォルトでオンになります。</span><span class="sxs-lookup"><span data-stu-id="e2532-368">When you open the **Color Picker**, the **Eyedropper** \(![Eyedropper][ImageEyedropperIcon]\) is on by default.</span></span>  <span data-ttu-id="e2532-369">選択した色をページ上の別の色に変更するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2532-369">Complete the following actions to change the selected color to some other color on the page.</span></span>  

1.  <span data-ttu-id="e2532-370">ビューポートのターゲットの色の上にマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="e2532-370">Hover over the target color in the viewport.</span></span>  
1.  <span data-ttu-id="e2532-371">[確認] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e2532-371">Choose to confirm.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="e2532-372">次の図では、 **色のパレット** に現在の色の値が表示されてい `rgba(0,0,0,0.7)` ます。これは黒に近くなります。</span><span class="sxs-lookup"><span data-stu-id="e2532-372">In the following figure, the **Color Picker** shows a current color value of `rgba(0,0,0,0.7)`, which is close to black.</span></span>  <span data-ttu-id="e2532-373">特定の色を、選択した後にビューポートで現在強調表示されている黒のバージョンに変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2532-373">The specific color should change to the version of black that is currently highlighted in the viewport after you chose it.</span></span>  
    
    :::image type="complex" source="../media/css-color-picker-eye-dropper.msft.png" alt-text="スポイトを使用する" lightbox="../media/css-color-picker-eye-dropper.msft.png":::
       <span data-ttu-id="e2532-375">スポイトを使用する</span><span class="sxs-lookup"><span data-stu-id="e2532-375">Using the Eyedropper</span></span>  
    :::image-end:::  
    
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
> <span data-ttu-id="e2532-385">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="e2532-385">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="e2532-386">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/css/reference) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="e2532-386">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="e2532-388">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="e2532-388">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
