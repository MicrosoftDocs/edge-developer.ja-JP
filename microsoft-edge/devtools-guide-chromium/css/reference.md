---
title: CCS リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/27/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 4f0370b83d8c939476a1ed378dbdf750101c9527
ms.sourcegitcommit: 0048eb692d49eab4755c0c3ef6866e6a9122d579
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "10843971"
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







# <span data-ttu-id="0b039-103">CCS リファレンス</span><span class="sxs-lookup"><span data-stu-id="0b039-103">CSS Reference</span></span>   



<span data-ttu-id="0b039-104">CSS の表示と変更に関連する Microsoft Edge DevTools 機能の包括的な参照で、新しいワークフローを見つけます。</span><span class="sxs-lookup"><span data-stu-id="0b039-104">Discover new workflows in this comprehensive reference of Microsoft Edge DevTools features related to viewing and changing CSS.</span></span>  

<span data-ttu-id="0b039-105">基本的な説明については、「 [CSS の表示と変更の概要][DevToolsCSSGetStarted]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b039-105">See [Get Started with Viewing and Changing CSS][DevToolsCSSGetStarted] to learn the basics.</span></span>  

## <span data-ttu-id="0b039-106">要素を選択する</span><span class="sxs-lookup"><span data-stu-id="0b039-106">Select an element</span></span>   

<span data-ttu-id="0b039-107">DevTools の**要素**パネルでは、一度に1つの要素の CSS を表示したり、変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="0b039-107">The **Elements** panel of DevTools lets you view or change the CSS of one element at a time.</span></span>  <span data-ttu-id="0b039-108">選択した要素が**DOM ツリー**で強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b039-108">The selected element is highlighted in the **DOM Tree**.</span></span>  <span data-ttu-id="0b039-109">要素のスタイルが [**スタイル**] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b039-109">The styles of the element are shown in the **Styles** pane.</span></span>  <span data-ttu-id="0b039-110">チュートリアルについては、「[要素の CSS を表示][DevToolsCSSGetStartedTutorial]する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0b039-110">See [View the CSS for an element][DevToolsCSSGetStartedTutorial] for a tutorial.</span></span>  

> [!NOTE]
> <span data-ttu-id="0b039-111">[図 1](#figure-1)では、 `h1` **DOM ツリー**で強調表示されている要素が選択されています。</span><span class="sxs-lookup"><span data-stu-id="0b039-111">In [Figure 1](#figure-1), the `h1` element that is highlighted in the **DOM Tree** is the selected element.</span></span>  <span data-ttu-id="0b039-112">右側では、要素のスタイルが [**スタイル**] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b039-112">On the right, the styles of the element are shown in the **Styles** pane.</span></span>  <span data-ttu-id="0b039-113">左側では、要素はビューポートで強調表示されていますが、現在は**DOM ツリー**の上にマウスが置かれているためです。</span><span class="sxs-lookup"><span data-stu-id="0b039-113">On the left, the element is highlighted in the viewport, but only because the mouse is currently hovering over it in the **DOM Tree**.</span></span>  

> ##### <span data-ttu-id="0b039-114">図 1</span><span class="sxs-lookup"><span data-stu-id="0b039-114">Figure 1</span></span>  
> <span data-ttu-id="0b039-115">選択された要素の例</span><span class="sxs-lookup"><span data-stu-id="0b039-115">An example of a selected element</span></span>  
> ![選択された要素の例][ImageSelectedElement]  

<span data-ttu-id="0b039-117">要素を選ぶには、さまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="0b039-117">There are many ways to select an element:</span></span>  

*   <span data-ttu-id="0b039-118">ビューポートで要素を右クリックし、[**検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b039-118">In your viewport, right-click the element and select **Inspect**.</span></span>  
*   <span data-ttu-id="0b039-119">Devtools で、[**要素の選択**] をクリックし、 ![ 要素を選択する ][ImageSelectAnElementIcon] か、 `Control` + `Shift` + `C` \ (Windows \) または `Command` + `Shift` + `C` \ (macOS \) を押して、ビューポート内の要素をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0b039-119">In DevTools, click **Select an element** ![Select an element][ImageSelectAnElementIcon] or press `Control`+`Shift`+`C` \(Windows\) or `Command`+`Shift`+`C` \(macOS\), and then click the element in the viewport.</span></span>  
*   <span data-ttu-id="0b039-120">DevTools で、 **DOM ツリー**の要素をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0b039-120">In DevTools, click the element in the **DOM Tree**.</span></span>  
*   <span data-ttu-id="0b039-121">DevTools で、コンソールのようなクエリを実行し、 `document.querySelector('p')` 結果を右クリックして、[**要素パネルで**表示] を選択します。 **Console**</span><span class="sxs-lookup"><span data-stu-id="0b039-121">In DevTools, run a query like `document.querySelector('p')` in the **Console**, right-click the result, and then select **Reveal in Elements panel**.</span></span>  

## <span data-ttu-id="0b039-122">CSS の表示</span><span class="sxs-lookup"><span data-stu-id="0b039-122">View CSS</span></span>   

### <span data-ttu-id="0b039-123">ルールが定義されている外部のスタイルシートを表示する</span><span class="sxs-lookup"><span data-stu-id="0b039-123">View the external stylesheet where a rule is defined</span></span>   

<span data-ttu-id="0b039-124">[**スタイル**] ウィンドウで、CSS ルールの隣にあるリンクをクリックして、ルールを定義する外部のスタイルシートを開きます。</span><span class="sxs-lookup"><span data-stu-id="0b039-124">In the **Styles** pane, click the link next to a CSS rule to open the external stylesheet that defines the rule.</span></span>  

<span data-ttu-id="0b039-125">スタイルシートが縮小されている場合は、「縮小版の[ファイルを読みやすくする][DevToolsJavascriptReferenceFormat]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b039-125">If the stylesheet is minified, see [Make a minified file readable][DevToolsJavascriptReferenceFormat].</span></span>  

> [!NOTE]
> <span data-ttu-id="0b039-126">[図 2](#figure-2)では、をクリックすると `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css` 、CSS ルールが定義されているの2行目に移動し `.content h1:first-of-type` ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-126">In [Figure 2](#figure-2), clicking `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` takes you to line 2 of `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css`, where the `.content h1:first-of-type` CSS rule is defined.</span></span>  

> ##### <span data-ttu-id="0b039-127">図 2</span><span class="sxs-lookup"><span data-stu-id="0b039-127">Figure 2</span></span>  
> <span data-ttu-id="0b039-128">ルールが定義されているスタイルシートの表示</span><span class="sxs-lookup"><span data-stu-id="0b039-128">Viewing the stylesheet where a rule is defined</span></span>  
> ![ルールが定義されているスタイルシートの表示][ImageViewRuleStylesheet]  

### <span data-ttu-id="0b039-130">実際に要素に適用されている CSS のみを表示する</span><span class="sxs-lookup"><span data-stu-id="0b039-130">View only the CSS that is actually applied to an element</span></span>   

<span data-ttu-id="0b039-131">[**スタイル**] タブには、オーバーライドされた宣言など、要素に適用されるすべての規則が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b039-131">The **Styles** tab shows you all of the rules that apply to an element, including declarations that have been overridden.</span></span>  <span data-ttu-id="0b039-132">オーバーライドされた宣言に関心がない場合は、[**計算**] タブを使用して、実際に要素に適用されている CSS のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="0b039-132">When you are not interested in overridden declarations, use the **Computed** tab to view only the CSS that is actually being applied to an element.</span></span>  

1.  <span data-ttu-id="0b039-133">[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="0b039-133">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="0b039-134">[**要素**] パネルの [**計算**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="0b039-134">Go to the **Computed** tab in the **Elements** panel.</span></span>  

> [!NOTE]
> <span data-ttu-id="0b039-135">横長の DevTools ウィンドウでは、[**計算**] タブは存在しません。</span><span class="sxs-lookup"><span data-stu-id="0b039-135">On a wide DevTools window, the **Computed** tab does not exist.</span></span>  <span data-ttu-id="0b039-136">[**計算**] タブの内容は、[**スタイル**] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b039-136">The contents of the **Computed** tab are shown on the **Styles** tab.</span></span>  

<span data-ttu-id="0b039-137">継承されたプロパティは不透明です。</span><span class="sxs-lookup"><span data-stu-id="0b039-137">Inherited properties are opaque.</span></span>  <span data-ttu-id="0b039-138">継承されたすべての値を表示するには、[**すべて表示**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0b039-138">Check the **Show All** checkbox to see all inherited values.</span></span>  

> [!NOTE]
> <span data-ttu-id="0b039-139">[図 3](#figure-3)では、[**計算**] タブには、現在選択されている要素に適用されている CSS プロパティが表示され `h1` ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-139">In [Figure 3](#figure-3), the **Computed** tab shows the CSS properties being applied to the currently-selected `h1` element.</span></span>  

> ##### <span data-ttu-id="0b039-140">図 3</span><span class="sxs-lookup"><span data-stu-id="0b039-140">Figure 3</span></span>  
> <span data-ttu-id="0b039-141">[**計算**] タブ</span><span class="sxs-lookup"><span data-stu-id="0b039-141">The **Computed** tab</span></span>  
> ![[計算] タブ][ImageComputedTab]  

### <span data-ttu-id="0b039-143">CSS プロパティがアルファベット順に表示される</span><span class="sxs-lookup"><span data-stu-id="0b039-143">View CSS properties in alphabetical order</span></span>   

<span data-ttu-id="0b039-144">[**計算**] タブを使用します。 「[要素に実際に適用されている CSS のみを表示する](#view-only-the-css-that-is-actually-applied-to-an-element)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b039-144">Use the **Computed** tab.  See [View only the CSS that is actually applied to an element](#view-only-the-css-that-is-actually-applied-to-an-element).</span></span>  

### <span data-ttu-id="0b039-145">継承した CSS プロパティを表示する</span><span class="sxs-lookup"><span data-stu-id="0b039-145">View inherited CSS properties</span></span>   

<span data-ttu-id="0b039-146">[**計算**] タブの [**すべて表示**] チェックボックスをオンにします。 「[要素に実際に適用されている CSS のみを表示する](#view-only-the-css-that-is-actually-applied-to-an-element)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b039-146">Check the **Show All** checkbox in the **Computed** tab.  See [View only the CSS that is actually applied to an element](#view-only-the-css-that-is-actually-applied-to-an-element).</span></span>  

### <span data-ttu-id="0b039-147">要素のボックスモデルを表示する</span><span class="sxs-lookup"><span data-stu-id="0b039-147">View the box model for an element</span></span>   

<span data-ttu-id="0b039-148">要素の[ボックスモデル][MDNBoxModel]を表示するには、[**スタイル**] タブに移動します。 DevTools ウィンドウが狭い場合、**ボックスモデル**図はタブの下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b039-148">To view [the box model][MDNBoxModel] of an element, go to the **Styles** tab.  If your DevTools window is narrow, the **Box Model** diagram is at the bottom of the tab.</span></span>  

<span data-ttu-id="0b039-149">値を変更するには、その値をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="0b039-149">To change a value, double-click on it.</span></span>  

> [!NOTE]
> <span data-ttu-id="0b039-150">[図 4](#figure-4)では、[**スタイル**] タブの**ボックスモデル**図は、現在選択されている要素のボックスモデルを示して `h1` います。</span><span class="sxs-lookup"><span data-stu-id="0b039-150">In [Figure 4](#figure-4), the **Box Model** diagram in the **Styles** tab shows the box model for the currently selected `h1` element.</span></span>  

> ##### <span data-ttu-id="0b039-151">図 4</span><span class="sxs-lookup"><span data-stu-id="0b039-151">Figure 4</span></span>  
> <span data-ttu-id="0b039-152">**ボックスモデル**図</span><span class="sxs-lookup"><span data-stu-id="0b039-152">The **Box Model** diagram</span></span>  
> ![ボックスモデル図][ImageBoxModel]  

### <span data-ttu-id="0b039-154">要素の CSS を検索してフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="0b039-154">Search and filter the CSS of an element</span></span>   

<span data-ttu-id="0b039-155">[**スタイル**] および [**計算**] タブの [**フィルター** ] テキストボックスを使用して、特定の CSS プロパティまたは値を検索します。</span><span class="sxs-lookup"><span data-stu-id="0b039-155">Use the **Filter** text box on the **Styles** and **Computed** tabs to search for specific CSS properties or values.</span></span>  

<span data-ttu-id="0b039-156">[**計算**] タブで継承されたプロパティも検索するには、[**すべて表示**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0b039-156">To also search inherited properties in the **Computed** tab, check the **Show All** checkbox.</span></span>  

> [!NOTE]
> <span data-ttu-id="0b039-157">[図 5](#figure-5)では、[**スタイル**] タブをフィルター処理して、検索クエリを含むルールのみを表示し `color` ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-157">In [Figure 5](#figure-5), the **Styles** tab is filtered to only show rules that include the search query `color`.</span></span>  

> ##### <span data-ttu-id="0b039-158">図 5</span><span class="sxs-lookup"><span data-stu-id="0b039-158">Figure 5</span></span>  
> <span data-ttu-id="0b039-159">[**スタイル**] タブのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="0b039-159">Filtering the **Styles** tab</span></span>  
> ![[スタイル] タブのフィルター処理][ImageStylesFilter]  

> [!NOTE]
> <span data-ttu-id="0b039-161">[図 6](#figure-6)では、[**計算**] タブにフィルターが適用され、検索クエリを含む宣言のみが表示され `100%` ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-161">In [Figure 6](#figure-6), the **Computed** tab is filtered to only show declarations that include the search query `100%`.</span></span>  

> ##### <span data-ttu-id="0b039-162">図 6</span><span class="sxs-lookup"><span data-stu-id="0b039-162">Figure 6</span></span>  
> <span data-ttu-id="0b039-163">**計算**されたタブのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="0b039-163">Filtering the **Computed** tab</span></span>  
> ![計算されたタブのフィルター処理][ImageComputerFilter]  

### <span data-ttu-id="0b039-165">擬似クラスの切り替え</span><span class="sxs-lookup"><span data-stu-id="0b039-165">Toggle a pseudo-class</span></span>   

<span data-ttu-id="0b039-166">擬似クラスを、、、、またはのように切り替えるに `:active` `:focus` は、次の操作を `:hover` `:visited` 行います。</span><span class="sxs-lookup"><span data-stu-id="0b039-166">To toggle a pseudo-class like `:active`, `:focus`, `:hover`, or `:visited`:</span></span>  

1.  <span data-ttu-id="0b039-167">[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="0b039-167">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="0b039-168">[**要素**] パネルで、[**スタイル**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="0b039-168">On the **Elements** panel, go to the **Styles** tab.</span></span>  
1.  <span data-ttu-id="0b039-169">[ **: Hov**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0b039-169">Click **:hov**.</span></span>  
1.  <span data-ttu-id="0b039-170">有効にする擬似クラスを確認します。</span><span class="sxs-lookup"><span data-stu-id="0b039-170">Check the pseudo-class that you want to enable.</span></span>  

> [!NOTE]
> <span data-ttu-id="0b039-171">[図 7](#figure-7)で、 `:hover` 擬似クラスを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="0b039-171">In [Figure 7](#figure-7), toggle the `:hover` pseudo-class.</span></span>  <span data-ttu-id="0b039-172">ビューポートで、宣言が要素に適用されていることを確認し `background-color: cornflowerblue` ます。これは、要素が実際にマウスをポイントしていない場合でも同様です。</span><span class="sxs-lookup"><span data-stu-id="0b039-172">In the viewport verify that the `background-color: cornflowerblue` declaration is being applied to the element, even though the element is not actually being hovered over.</span></span>  

> ##### <span data-ttu-id="0b039-173">図 7</span><span class="sxs-lookup"><span data-stu-id="0b039-173">Figure 7</span></span>  
> <span data-ttu-id="0b039-174">`:hover`擬似クラスの切り替え</span><span class="sxs-lookup"><span data-stu-id="0b039-174">Toggling the `:hover` pseudo-class</span></span>  
> ![: Hover 擬似クラスの切り替え][ImagePseudoClass]  

<span data-ttu-id="0b039-176">インタラクティブなチュートリアルについては、「[クラスに疑似状態を追加する][DevToolsCSSGetStartedAddPseudoState]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0b039-176">See [Add a pseudostate to a class][DevToolsCSSGetStartedAddPseudoState] for an interactive tutorial.</span></span> 

### <span data-ttu-id="0b039-177">印刷モードでページを表示する</span><span class="sxs-lookup"><span data-stu-id="0b039-177">View a page in print mode</span></span>   

<span data-ttu-id="0b039-178">印刷モードでページを表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0b039-178">To view a page in print mode:</span></span>  
1.  <span data-ttu-id="0b039-179">[コマンドメニューを開き][DevToolsCommandMenu]ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-179">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="0b039-180">入力を開始し `Rendering` 、を選択し `Show Rendering` ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-180">Start typing `Rendering` and select `Show Rendering`.</span></span>  
1.  <span data-ttu-id="0b039-181">[ **CSS メディアのエミュレート**] ドロップダウンで、[**印刷**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="0b039-181">For the **Emulate CSS Media** dropdown, select **print**.</span></span>  

### <span data-ttu-id="0b039-182">[カバレッジ] タブで使用済みおよび未使用の CSS を表示する</span><span class="sxs-lookup"><span data-stu-id="0b039-182">View used and unused CSS with the Coverage tab</span></span>   

<span data-ttu-id="0b039-183">[カバレッジ] タブには、ページで実際に使用されている CSS が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b039-183">The Coverage tab shows you what CSS a page actually uses.</span></span>  

1.  <span data-ttu-id="0b039-184">`Control` + `Shift` + `P` `Command` + `Shift` + `P` コマンドメニューを開くには、devtools がフォーカスされている状態で、\ (Windows \) または \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="0b039-184">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) while DevTools is in focus to open the Command Menu.</span></span>  
1.  <span data-ttu-id="0b039-185">入力 `coverage` を開始し、[**カバレッジの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b039-185">Start typing `coverage` and select **Show Coverage**.</span></span>  <span data-ttu-id="0b039-186">[カバー] タブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b039-186">The Coverage tab appears.</span></span>  
    
    > ##### <span data-ttu-id="0b039-187">図 8</span><span class="sxs-lookup"><span data-stu-id="0b039-187">Figure 8</span></span>  
    > <span data-ttu-id="0b039-188">[コマンド] メニューから [カバレッジ] タブを開く</span><span class="sxs-lookup"><span data-stu-id="0b039-188">Opening the Coverage tab from the Command Menu</span></span>  
    > ![[コマンド] メニューから [カバレッジ] タブを開く][ImageCommandMenu]  
    
    > ##### <span data-ttu-id="0b039-190">図 9</span><span class="sxs-lookup"><span data-stu-id="0b039-190">Figure 9</span></span>  
    > <span data-ttu-id="0b039-191">[カバレッジ] タブ</span><span class="sxs-lookup"><span data-stu-id="0b039-191">The Coverage tab</span></span>  
    > ![[カバレッジ] タブ][ImageCoverageEmpty]  
    
1.  <span data-ttu-id="0b039-193">[インストルメント化の開始] をクリックし **、ページを更新**して ![ インストルメントの範囲を開始し、ページを更新し ][ImageRefreshIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-193">Click **Start instrumenting coverage and refresh the page** ![Start instrumenting coverage and refresh the page][ImageRefreshIcon].</span></span>  <span data-ttu-id="0b039-194">ページの更新と [カバレッジ] タブには、ブラウザーが読み込む各ファイルからの CSS (および JavaScript \) の使用量の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b039-194">The page refreshes and the Coverage tab provides an overview of how much CSS \(and JavaScript\) is used from each file that the browser loads.</span></span>  <span data-ttu-id="0b039-195">緑色は、使用されている CSS を表します。</span><span class="sxs-lookup"><span data-stu-id="0b039-195">Green represents used CSS.</span></span>  <span data-ttu-id="0b039-196">赤は未使用の CSS を示します。</span><span class="sxs-lookup"><span data-stu-id="0b039-196">Red represents unused CSS.</span></span>  
    
    > ##### <span data-ttu-id="0b039-197">図 10</span><span class="sxs-lookup"><span data-stu-id="0b039-197">Figure 10</span></span>  
    > <span data-ttu-id="0b039-198">CSS (および JavaScript) が使用されていて未使用かどうかの概要</span><span class="sxs-lookup"><span data-stu-id="0b039-198">An overview of how much CSS (and JavaScript) is used and unused</span></span>  
    > ![CSS (および JavaScript) が使用されていて未使用かどうかの概要][ImageCoverageOverview]  

1.  <span data-ttu-id="0b039-200">CSS ファイルをクリックすると、使用する CSS の1行ずつの分解が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b039-200">Click a CSS file to see a line-by-line breakdown of what CSS it uses.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="0b039-201">[図 11](#figure-11)では、145から147、149から151まで `b66bc881.site-ltr.css` は使用されていませんが、行163から166に使用されています。</span><span class="sxs-lookup"><span data-stu-id="0b039-201">In [Figure 11](#figure-11), lines 145 to 147 and 149 to 151 of `b66bc881.site-ltr.css` are unused, whereas lines 163 to 166 are used.</span></span>  
    
    > ##### <span data-ttu-id="0b039-202">図 11</span><span class="sxs-lookup"><span data-stu-id="0b039-202">Figure 11</span></span>  
    > <span data-ttu-id="0b039-203">使用されている、未使用の CSS の行単位の内訳</span><span class="sxs-lookup"><span data-stu-id="0b039-203">A line-by-line breakdown of used and unused CSS</span></span>  
    > ![使用されている、未使用の CSS の行単位の内訳][ImageCoverageDetail]  
    
### <span data-ttu-id="0b039-205">印刷プレビューモードの強制</span><span class="sxs-lookup"><span data-stu-id="0b039-205">Force print preview mode</span></span>   

<span data-ttu-id="0b039-206">「 [DevTools を印刷プレビューモードに強制][DevToolsCssPrintPreview]する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0b039-206">See [Force DevTools Into Print Preview Mode][DevToolsCssPrintPreview].</span></span>  

## <span data-ttu-id="0b039-207">CSS を変更する</span><span class="sxs-lookup"><span data-stu-id="0b039-207">Change CSS</span></span>   

<!-- todo s/CSS declaration/declaration/ -->  

### <span data-ttu-id="0b039-208">要素に CSS 宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="0b039-208">Add a CSS declaration to an element</span></span>   

<span data-ttu-id="0b039-209">宣言の順序は要素のスタイルに影響を与えるため、宣言をさまざまな方法で追加することができます。</span><span class="sxs-lookup"><span data-stu-id="0b039-209">Since the order of declarations affects how an element is styled, you may add declarations in different ways:</span></span>  

*   <span data-ttu-id="0b039-210">[インライン宣言を追加](#add-an-inline-declaration)します。</span><span class="sxs-lookup"><span data-stu-id="0b039-210">[Add a inline declaration](#add-an-inline-declaration).</span></span>  <span data-ttu-id="0b039-211">要素の HTML に属性を追加することと同じです `style` 。</span><span class="sxs-lookup"><span data-stu-id="0b039-211">Equivalent to adding a `style` attribute to the HTML of an element.</span></span>  
*   <span data-ttu-id="0b039-212">[スタイルルールに宣言を追加](#add-a-declaration-to-a-style-rule)します。</span><span class="sxs-lookup"><span data-stu-id="0b039-212">[Add a declaration to a style rule](#add-a-declaration-to-a-style-rule).</span></span>  

**<span data-ttu-id="0b039-213">使用するワークフロー</span><span class="sxs-lookup"><span data-stu-id="0b039-213">What workflow should you use?</span></span>** <span data-ttu-id="0b039-214">ほとんどのシナリオでは、通常、インライン宣言ワークフローを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b039-214">For most scenarios, you probably want to use the inline declaration workflow.</span></span>  <span data-ttu-id="0b039-215">インライン宣言は外部の宣言よりも高いため、インラインワークフローによって、変更が予期したとおりに要素に反映されるようになります。</span><span class="sxs-lookup"><span data-stu-id="0b039-215">Inline declarations have higher specificity than external ones, so the inline workflow ensures that the changes take effect in the element as you would expect.</span></span>  <span data-ttu-id="0b039-216">詳細については、「[セレクターの種類][MDNSelectorTypes]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b039-216">See [Selector Types][MDNSelectorTypes] for more on specificity.</span></span>  

<span data-ttu-id="0b039-217">要素のスタイルをデバッグしていて、宣言がさまざまな場所で定義されている場合に何が起こるかを明確にテストする必要がある場合は、他のワークフローを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b039-217">If you are debugging any styles of the element and you need to specifically test what happens when a declaration is defined in different places, use the other workflow.</span></span>  

#### <span data-ttu-id="0b039-218">インライン宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="0b039-218">Add an inline declaration</span></span>   

<span data-ttu-id="0b039-219">インライン宣言を追加するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0b039-219">To add an inline declaration:</span></span>  

1.  <span data-ttu-id="0b039-220">[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="0b039-220">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="0b039-221">[**スタイル**] ウィンドウで、[**スタイル**] セクションのかっこの間をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0b039-221">In the **Styles** pane, click between the brackets of the **element.style** section.</span></span>  <span data-ttu-id="0b039-222">カーソルがフォーカスされ、テキストの入力が可能になります。</span><span class="sxs-lookup"><span data-stu-id="0b039-222">The cursor focuses, allowing you to enter text.</span></span>  
1.  <span data-ttu-id="0b039-223">プロパティ名を入力し、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-223">Enter a property name and press `Enter`.</span></span>  
1.  <span data-ttu-id="0b039-224">そのプロパティに有効な値を入力して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-224">Enter a valid value for that property and press `Enter`.</span></span>  <span data-ttu-id="0b039-225">**DOM ツリー**で、 `style` 属性が要素に追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0b039-225">In the **DOM Tree**, verify that a `style` attribute has been added to the element.</span></span>  

> [!NOTE]
> <span data-ttu-id="0b039-226">[図 12](#figure-12)では、 `margin-top` 選択した `background-color` 要素に and プロパティが適用されています。</span><span class="sxs-lookup"><span data-stu-id="0b039-226">In [Figure 12](#figure-12), the `margin-top` and `background-color` properties have been applied to the selected element.</span></span>  <span data-ttu-id="0b039-227">**DOM ツリー**で、宣言が要素の属性に反映されていることを確認し `style` ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-227">In the **DOM Tree** verify that the declarations are reflected in the `style` attribute for an element.</span></span>  

> ##### <span data-ttu-id="0b039-228">図 12</span><span class="sxs-lookup"><span data-stu-id="0b039-228">Figure 12</span></span>  
> <span data-ttu-id="0b039-229">インライン宣言の追加</span><span class="sxs-lookup"><span data-stu-id="0b039-229">Adding inline declarations</span></span>  
> ![インライン宣言の追加][ImageInlineDeclarations]  

#### <span data-ttu-id="0b039-231">スタイルルールに宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="0b039-231">Add a declaration to a style rule</span></span>   

<span data-ttu-id="0b039-232">既存のスタイルルールに宣言を追加するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0b039-232">To add a declaration to an existing style rule:</span></span>  

1.  <span data-ttu-id="0b039-233">[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="0b039-233">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="0b039-234">[**スタイル**] ウィンドウで、宣言を追加するスタイルルールのかっこの間をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0b039-234">In the **Styles** pane, click between the brackets of the style rule to which you want to add the declaration.</span></span>  <span data-ttu-id="0b039-235">カーソルがフォーカスされ、テキストの入力が可能になります。</span><span class="sxs-lookup"><span data-stu-id="0b039-235">The cursor focuses, allowing you to enter text.</span></span>  
1.  <span data-ttu-id="0b039-236">プロパティ名を入力し、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-236">Enter a property name and press `Enter`.</span></span>  
1.  <span data-ttu-id="0b039-237">そのプロパティに有効な値を入力して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-237">Enter a valid value for that property and press `Enter`.</span></span>  

> ##### <span data-ttu-id="0b039-238">図 13</span><span class="sxs-lookup"><span data-stu-id="0b039-238">Figure 13</span></span>  
> <span data-ttu-id="0b039-239">`border-bottom-style:groove`スタイルルールへの宣言の追加</span><span class="sxs-lookup"><span data-stu-id="0b039-239">Adding the `border-bottom-style:groove` declaration to a style rule</span></span>  
> ![スタイルルールへの宣言の追加][ImageAddDeclarationExistingRule]  

### <span data-ttu-id="0b039-241">宣言の名前または値を変更する</span><span class="sxs-lookup"><span data-stu-id="0b039-241">Change a declaration name or value</span></span>   

<span data-ttu-id="0b039-242">宣言の名前または値をダブルクリックして変更します。</span><span class="sxs-lookup"><span data-stu-id="0b039-242">Double-click the name or value of a declaration to change it.</span></span>  <span data-ttu-id="0b039-243">すばやく値を増減するためのショートカットキーについては、「[宣言の値を変更](#change-declaration-values-with-keyboard-shortcuts)する」を参照してください `0.1` `1` `10` `100` 。</span><span class="sxs-lookup"><span data-stu-id="0b039-243">See [Change declaration values with keyboard shortcuts](#change-declaration-values-with-keyboard-shortcuts) for shortcuts for quickly incrementing or decrementing a value by `0.1`, `1`, `10`, or `100` units.</span></span>  

> ##### <span data-ttu-id="0b039-244">図 14</span><span class="sxs-lookup"><span data-stu-id="0b039-244">Figure 14</span></span>  
> <span data-ttu-id="0b039-245">の値を変更する</span><span class="sxs-lookup"><span data-stu-id="0b039-245">Changing the value of the</span></span> `border-bottom-style`  
> ![宣言の値を変更する][ImageAddDeclarationExistingRule2]  

### <span data-ttu-id="0b039-247">キーボードショートカットを使用して宣言の値を変更する</span><span class="sxs-lookup"><span data-stu-id="0b039-247">Change declaration values with keyboard shortcuts</span></span>   

<span data-ttu-id="0b039-248">宣言の値を編集しているときに、次のショートカットキーを使用して、値を固定金額でインクリメントできます。</span><span class="sxs-lookup"><span data-stu-id="0b039-248">While editing the value of a declaration, you may use the following keyboard shortcuts to increment the value by a fixed amount:</span></span>  

*   <span data-ttu-id="0b039-249">[ `Alt` + `Up` \ (Windows \)] または [ `Option` + `Up` \ (macOS \)] を押して、増分 `0.1` します。</span><span class="sxs-lookup"><span data-stu-id="0b039-249">Press `Alt`+`Up` \(Windows\) or `Option`+`Up` \(macOS\) to increment by `0.1`.</span></span>  
*   <span data-ttu-id="0b039-250">キーを押して、 `Up` 値をから `1` 、または現在の値の間の範囲に変更し `0.1` `-1` `1` ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-250">Press `Up` to change the value by `1`, or by `0.1` if the current value is between `-1` and `1`.</span></span>  
*   <span data-ttu-id="0b039-251">を押し `Shift` + `Up` てインクリメント `10` します。</span><span class="sxs-lookup"><span data-stu-id="0b039-251">Press `Shift`+`Up` to increment by `10`.</span></span>  
*   <span data-ttu-id="0b039-252">`Shift` + `Page Up` \ (Windows \) または `Shift` + `Command` + `Up` \ (macOS \) キーを押して、値を増やし `100` ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-252">Press `Shift`+`Page Up` \(Windows\) or `Shift`+`Command`+`Up` \(macOS\) to increment the value by `100`.</span></span>  

<span data-ttu-id="0b039-253">減分も動作します。</span><span class="sxs-lookup"><span data-stu-id="0b039-253">Decrementing also works.</span></span>  <span data-ttu-id="0b039-254">`Up`上記で説明した各インスタンスをに置き換え `Down` ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-254">Just replace each instance of `Up` mentioned above with `Down`.</span></span>  

### <span data-ttu-id="0b039-255">要素にクラスを追加する</span><span class="sxs-lookup"><span data-stu-id="0b039-255">Add a class to an element</span></span>   

<span data-ttu-id="0b039-256">要素にクラスを追加するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0b039-256">To add a class to an element:</span></span>  

1.  <span data-ttu-id="0b039-257">**DOM ツリー**で[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="0b039-257">[Select the element](#select-an-element) in the **DOM Tree**.</span></span>  
1.  <span data-ttu-id="0b039-258">[ **Cls**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0b039-258">Click **.cls**.</span></span>  
1.  <span data-ttu-id="0b039-259">[ **Add New class** ] テキストボックスにクラスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0b039-259">Enter the name of the class in the **Add New Class** text box.</span></span>  
1.  <span data-ttu-id="0b039-260">キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-260">Press `Enter`.</span></span>  

> ##### <span data-ttu-id="0b039-261">図 15</span><span class="sxs-lookup"><span data-stu-id="0b039-261">Figure 15</span></span>  
> <span data-ttu-id="0b039-262">[**要素クラス**] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="0b039-262">The **Element Classes** pane</span></span>  
> ![[要素クラス] ウィンドウ][ImageElementClasses]  

### <span data-ttu-id="0b039-264">クラスの切り替え</span><span class="sxs-lookup"><span data-stu-id="0b039-264">Toggle a class</span></span>   

<span data-ttu-id="0b039-265">要素のクラスを有効または無効にするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0b039-265">To enable or disable a class on an element:</span></span>  

1.  <span data-ttu-id="0b039-266">**DOM ツリー**で[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="0b039-266">[Select the element](#select-an-element) in the **DOM Tree**.</span></span>  
1.  <span data-ttu-id="0b039-267">[**要素クラス**] ペインを開きます。</span><span class="sxs-lookup"><span data-stu-id="0b039-267">Open the **Element Classes** pane.</span></span>  <span data-ttu-id="0b039-268">「[要素にクラスを追加する」を](#add-a-class-to-an-element)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0b039-268">See [Add a class to an element](#add-a-class-to-an-element).</span></span>  <span data-ttu-id="0b039-269">[**新しいクラスの追加**] テキストボックスの下には、この要素に適用されているすべてのクラスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b039-269">Below the **Add New Class** text box are all of the classes that are being applied to this element.</span></span>  
1.  <span data-ttu-id="0b039-270">有効または無効にするクラスの横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0b039-270">Toggle the checkbox next to the class that you want to enable or disable.</span></span>  

### <span data-ttu-id="0b039-271">スタイルルールを追加する</span><span class="sxs-lookup"><span data-stu-id="0b039-271">Add a style rule</span></span>   

<span data-ttu-id="0b039-272">新しいスタイルルールを追加するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0b039-272">To add a new style rule:</span></span>  

1.  <span data-ttu-id="0b039-273">[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="0b039-273">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="0b039-274">[**新しいスタイルルール**] をクリックし ![ ][ImageNewStyleRuleIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-274">Click **New Style Rule** ![New Style Rule][ImageNewStyleRuleIcon].</span></span>  <span data-ttu-id="0b039-275">DevTools は、**要素のスタイル**ルールの下に新しいルールを挿入します。</span><span class="sxs-lookup"><span data-stu-id="0b039-275">DevTools inserts a new rule beneath the **element.style** rule.</span></span>  

> [!NOTE]
> <span data-ttu-id="0b039-276">[図 16](#figure-16)では、 `h1.devsite-page-title` [**新しいスタイルルール**] をクリックした後でスタイルルールが追加されます。</span><span class="sxs-lookup"><span data-stu-id="0b039-276">In [Figure 16](#figure-16), DevTools adds the `h1.devsite-page-title` style rule after clicking **New Style Rule**.</span></span>  

> ##### <span data-ttu-id="0b039-277">図 16</span><span class="sxs-lookup"><span data-stu-id="0b039-277">Figure 16</span></span>  
> <span data-ttu-id="0b039-278">新しいスタイルルールを追加する</span><span class="sxs-lookup"><span data-stu-id="0b039-278">Adding a new style rule</span></span>  
> ![新しいスタイルルールを追加する][ImageStyleRule]  

#### <span data-ttu-id="0b039-280">ルールを追加するスタイルを選択する</span><span class="sxs-lookup"><span data-stu-id="0b039-280">Choose which stylesheet to add a rule to</span></span>   

<span data-ttu-id="0b039-281">[新しいスタイルルールを追加](#add-a-style-rule)するときに、[**新しい**スタイルルール] をクリックしたままにして、 ![ ][ImageNewStyleRuleIcon] スタイルルールを追加するスタイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="0b039-281">When [adding a new style rule](#add-a-style-rule), click and hold **New Style Rule** ![New Style Rule][ImageNewStyleRuleIcon] to choose which stylesheet to add the style rule to.</span></span>  

> ##### <span data-ttu-id="0b039-282">図 17</span><span class="sxs-lookup"><span data-stu-id="0b039-282">Figure 17</span></span>  
> <span data-ttu-id="0b039-283">スタイルシートの選択</span><span class="sxs-lookup"><span data-stu-id="0b039-283">Choosing a stylesheet</span></span>  
> ![スタイルシートの選択][ImageChooseStylesheet]  

#### <span data-ttu-id="0b039-285">特定の場所にスタイルルールを追加する</span><span class="sxs-lookup"><span data-stu-id="0b039-285">Add a style rule to a specific location</span></span>   

<span data-ttu-id="0b039-286">[**スタイル**] タブの特定の場所にスタイルルールを追加するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0b039-286">To add a style rule to a specific location in the **Styles** tab:</span></span>  

1.  <span data-ttu-id="0b039-287">新しいスタイルルールを追加する場所のすぐ上のスタイルルールにマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="0b039-287">Hover over the style rule that is directly above where you want to add your new style rule.</span></span>  
1.  <span data-ttu-id="0b039-288">[[**その他の操作**] ツールバーを](#reveal-the-more-actions-toolbar)表示します。</span><span class="sxs-lookup"><span data-stu-id="0b039-288">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="0b039-289">[スタイルルールの挿入] の下にある [**スタイルルール**の挿入] をクリックし ![ ][ImageNewStyleRuleIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-289">Click **Insert Style Rule Below** ![Insert Style Rule Below][ImageNewStyleRuleIcon].</span></span>  

> ##### <span data-ttu-id="0b039-290">図18</span><span class="sxs-lookup"><span data-stu-id="0b039-290">Figure 18</span></span>  
> **<span data-ttu-id="0b039-291">下にスタイルルールを挿入する</span><span class="sxs-lookup"><span data-stu-id="0b039-291">Insert Style Rule Below</span></span>**  
> ![下にスタイルルールを挿入する][ImageInsertStyleRuleBelow]  

### <span data-ttu-id="0b039-293">[その他の操作] ツールバーを表示する</span><span class="sxs-lookup"><span data-stu-id="0b039-293">Reveal the More Actions toolbar</span></span>   

<span data-ttu-id="0b039-294">[**その他のアクション**] ツールバーでは、次の操作を実行できます</span><span class="sxs-lookup"><span data-stu-id="0b039-294">The **More Actions** toolbar lets you:</span></span>  

*   <span data-ttu-id="0b039-295">優先するスタイルルールのすぐ下にスタイルルールを挿入します。</span><span class="sxs-lookup"><span data-stu-id="0b039-295">Insert a style rule directly below the one you are focused on.</span></span>  
*   <span data-ttu-id="0b039-296">`background-color` `color` `box-shadow` `text-shadow` フォーカスされているスタイルルールに、、、、または宣言を追加します。</span><span class="sxs-lookup"><span data-stu-id="0b039-296">Add a `background-color`, `color`, `box-shadow`, or `text-shadow` declaration to the style rule you are focused on.</span></span>  

<span data-ttu-id="0b039-297">[**その他の操作**] ツールバーを表示するには:</span><span class="sxs-lookup"><span data-stu-id="0b039-297">To reveal the **More Actions** toolbar:</span></span>  

1.  <span data-ttu-id="0b039-298">[**スタイル**] タブで、スタイルルールの上にマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="0b039-298">In the **Styles** tab, hover over a style rule.</span></span>  <span data-ttu-id="0b039-299">**その他の操作** `...`[スタイルルール] セクションの右下に公開されます。</span><span class="sxs-lookup"><span data-stu-id="0b039-299">**More Actions** `...` is revealed in the bottom-right of the style rule section.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="0b039-300">[図 19](#figure-19)では、スタイルルールにマウスポインター `.header-holder.has-default-focus` を合わせると、[スタイルルール] セクションの右下に [**その他のアクション**] が現れます。</span><span class="sxs-lookup"><span data-stu-id="0b039-300">In [Figure 19](#figure-19), hover over the `.header-holder.has-default-focus` style rule and **More Actions** is revealed in the bottom-right of the style rule section.</span></span>  
    
    > ##### <span data-ttu-id="0b039-301">図19</span><span class="sxs-lookup"><span data-stu-id="0b039-301">Figure 19</span></span>  
    > <span data-ttu-id="0b039-302">**その他のアクション**を見つける</span><span class="sxs-lookup"><span data-stu-id="0b039-302">Revealing **More Actions**</span></span>  
    > ![その他のアクションを見つける][ImageRevealMore]  
    
1.  <span data-ttu-id="0b039-304">他の**アクション**をマウスでポイント `...` すると、上記のアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b039-304">Hover over **More Actions** `...` to reveal the actions mentioned above.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="0b039-305">[**次のスタイルルールの挿入**アクションを実行すると、**その他の操作**をマウスでポイントしたときに、次のように</span><span class="sxs-lookup"><span data-stu-id="0b039-305">The **Insert Style Rule Below** action is revealed after hovering over **More Actions**.</span></span>  
    
    > ##### <span data-ttu-id="0b039-306">図20</span><span class="sxs-lookup"><span data-stu-id="0b039-306">Figure 20</span></span>  
    > <span data-ttu-id="0b039-307">[**その他の操作**] ツールバー</span><span class="sxs-lookup"><span data-stu-id="0b039-307">The **More Actions** toolbar</span></span>  
    > ![[その他の操作] ツールバー][ImageInsertStyleRuleBelow2]  
    
### <span data-ttu-id="0b039-309">宣言を切り替える</span><span class="sxs-lookup"><span data-stu-id="0b039-309">Toggle a declaration</span></span>   

<span data-ttu-id="0b039-310">1つの宣言のオンとオフを切り替えるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0b039-310">To toggle a single declaration on or off:</span></span>  

1.  <span data-ttu-id="0b039-311">[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="0b039-311">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="0b039-312">[**スタイル**] ウィンドウで、宣言を定義するルールの上にマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="0b039-312">In the **Styles** pane, hover over the rule that defines the declaration.</span></span>  <span data-ttu-id="0b039-313">各宣言の横にチェックボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b039-313">Checkboxes appear next to each declaration.</span></span>  
1.  <span data-ttu-id="0b039-314">宣言の横にあるチェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="0b039-314">Check or uncheck the checkbox next to the declaration.</span></span>  <span data-ttu-id="0b039-315">宣言をオフにすると、DevTools がその宣言を超えて、アクティブでなくなったことを示します。</span><span class="sxs-lookup"><span data-stu-id="0b039-315">When you uncheck a declaration, DevTools crosses it out to indicate that it is no longer active.</span></span>  

> [!NOTE]
> <span data-ttu-id="0b039-316">[図 21](#figure-21)では、 `margin-top` 現在選択されている要素のプロパティがトグルオフになっています。</span><span class="sxs-lookup"><span data-stu-id="0b039-316">In [Figure 21](#figure-21), the `margin-top` property for the currently selected element has been toggled off.</span></span>  

> ##### <span data-ttu-id="0b039-317">図21</span><span class="sxs-lookup"><span data-stu-id="0b039-317">Figure 21</span></span>  
> <span data-ttu-id="0b039-318">宣言の切り替え</span><span class="sxs-lookup"><span data-stu-id="0b039-318">Toggling a declaration</span></span>  
> ![宣言の切り替え][ImageToggleDeclaration]  

### <span data-ttu-id="0b039-320">背景色の宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="0b039-320">Add a background-color declaration</span></span>   

<span data-ttu-id="0b039-321">要素に宣言を追加するには、 `background-color` 次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0b039-321">To add a `background-color` declaration to an element:</span></span>  

1.  <span data-ttu-id="0b039-322">宣言を追加するスタイルルールの上にマウスポインターを置き `background-color` ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-322">Hover over the style rule that you want to add the `background-color` declaration to.</span></span>  
1.  <span data-ttu-id="0b039-323">[[**その他の操作**] ツールバーを](#reveal-the-more-actions-toolbar)表示します。</span><span class="sxs-lookup"><span data-stu-id="0b039-323">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="0b039-324">[**背景**色の追加] をクリックし ![ ][ImageAddBackgroundColorIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-324">Click **Add Background Color** ![Add Background Color][ImageAddBackgroundColorIcon].</span></span>  

> ##### <span data-ttu-id="0b039-325">図22</span><span class="sxs-lookup"><span data-stu-id="0b039-325">Figure 22</span></span>  
> **<span data-ttu-id="0b039-326">背景色を追加する</span><span class="sxs-lookup"><span data-stu-id="0b039-326">Add Background Color</span></span>**  
> ![背景色を追加する][ImageAddBackgroundColor]  

### <span data-ttu-id="0b039-328">色の宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="0b039-328">Add a color declaration</span></span>   

<span data-ttu-id="0b039-329">要素に宣言を追加するには、 `color` 次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0b039-329">To add a `color` declaration to an element:</span></span>  

1.  <span data-ttu-id="0b039-330">宣言を追加するスタイルルールの上にマウスポインターを置き `color` ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-330">Hover over the style rule that you want to add the `color` declaration to.</span></span>  
1.  <span data-ttu-id="0b039-331">[[**その他の操作**] ツールバーを](#reveal-the-more-actions-toolbar)表示します。</span><span class="sxs-lookup"><span data-stu-id="0b039-331">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="0b039-332">[**色の追加]** をクリックし ![ ][ImageAddColorIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-332">Click **Add Color** ![Add Color][ImageAddColorIcon].</span></span>  

> ##### <span data-ttu-id="0b039-333">図23</span><span class="sxs-lookup"><span data-stu-id="0b039-333">Figure 23</span></span>  
> **<span data-ttu-id="0b039-334">色を追加する</span><span class="sxs-lookup"><span data-stu-id="0b039-334">Add Color</span></span>**  
> ![色を追加する][ImageAddColor]  

### <span data-ttu-id="0b039-336">ボックスシャドウ宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="0b039-336">Add a box-shadow declaration</span></span>   

<span data-ttu-id="0b039-337">要素に宣言を追加するには、 `box-shadow` 次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0b039-337">To add a `box-shadow` declaration to an element:</span></span>  

1.  <span data-ttu-id="0b039-338">宣言を追加するスタイルルールの上にマウスポインターを置き `box-shadow` ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-338">Hover over the style rule that you want to add the `box-shadow` declaration to.</span></span>  
1.  <span data-ttu-id="0b039-339">[[**その他の操作**] ツールバーを](#reveal-the-more-actions-toolbar)表示します。</span><span class="sxs-lookup"><span data-stu-id="0b039-339">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="0b039-340">[**追加ボックスシャドウ**の追加] をクリックし ![ ][ImageAddBoxShadowIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-340">Click **Add Box Shadow** ![Add Box Shadow][ImageAddBoxShadowIcon].</span></span>  

> ##### <span data-ttu-id="0b039-341">図24</span><span class="sxs-lookup"><span data-stu-id="0b039-341">Figure 24</span></span>  
> **<span data-ttu-id="0b039-342">ボックスの影を追加する</span><span class="sxs-lookup"><span data-stu-id="0b039-342">Add Box Shadow</span></span>**  
> ![ボックスの影を追加する][ImageAddBoxShadow]  

### <span data-ttu-id="0b039-344">テキストシャドウの宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="0b039-344">Add a text-shadow declaration</span></span>   

<span data-ttu-id="0b039-345">要素に宣言を追加するには、 `text-shadow` 次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0b039-345">To add a `text-shadow` declaration to an element:</span></span>  

1.  <span data-ttu-id="0b039-346">宣言を追加するスタイルルールの上にマウスポインターを置き `text-shadow` ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-346">Hover over the style rule that you want to add the `text-shadow` declaration to.</span></span>  
1.  <span data-ttu-id="0b039-347">[[**その他の操作**] ツールバーを](#reveal-the-more-actions-toolbar)表示します。</span><span class="sxs-lookup"><span data-stu-id="0b039-347">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="0b039-348">[**テキストの影**を追加する] をクリックし ![ ][ImageAddTextShadowIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-348">Click **Add Text Shadow** ![Add Text Shadow][ImageAddTextShadowIcon].</span></span>  

> ##### <span data-ttu-id="0b039-349">図25</span><span class="sxs-lookup"><span data-stu-id="0b039-349">Figure 25</span></span>  
> **<span data-ttu-id="0b039-350">テキストの影を追加する</span><span class="sxs-lookup"><span data-stu-id="0b039-350">Add Text Shadow</span></span>**  
> ![テキストの影を追加する][ImageAddTextShadow]  

### <span data-ttu-id="0b039-352">カラーピッカーを使用して色を変更する</span><span class="sxs-lookup"><span data-stu-id="0b039-352">Change colors with the Color Picker</span></span>   

<span data-ttu-id="0b039-353">**カラーピッカー**は、変更と宣言のための GUI を提供し `color` `background-color` ます。</span><span class="sxs-lookup"><span data-stu-id="0b039-353">The **Color Picker** provides a GUI for changing `color` and `background-color` declarations.</span></span>  

<span data-ttu-id="0b039-354">**カラーピッカー**を開くには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0b039-354">To open the **Color Picker**:</span></span>  

1.  <span data-ttu-id="0b039-355">[要素を選択](#select-an-element)します。</span><span class="sxs-lookup"><span data-stu-id="0b039-355">[Select an element](#select-an-element).</span></span>  
1.  <span data-ttu-id="0b039-356">[**スタイル**] タブで、変更する、 `color` `background-color` または同様の宣言を見つけます。</span><span class="sxs-lookup"><span data-stu-id="0b039-356">In the **Styles** tab, find the `color`, `background-color`, or similar declaration that you want to change.</span></span>  <span data-ttu-id="0b039-357">、、 `color` `background-color` または同様の値の左側に、色のプレビューである小さな四角形が表示されています。</span><span class="sxs-lookup"><span data-stu-id="0b039-357">To the left of the `color`, `background-color`, or similar value, there is a small square which is a preview of the color.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="0b039-358">[図 26](#figure-26)では、左側の小さな四角形 `rgba(0, 0, 0, 0.7)` はその色のプレビューです。</span><span class="sxs-lookup"><span data-stu-id="0b039-358">In [Figure 26](#figure-26), the small square to the left of `rgba(0, 0, 0, 0.7)` is a preview of that color.</span></span>  
    
    > ##### <span data-ttu-id="0b039-359">図26</span><span class="sxs-lookup"><span data-stu-id="0b039-359">Figure 26</span></span>  
    > <span data-ttu-id="0b039-360">色のプレビュー</span><span class="sxs-lookup"><span data-stu-id="0b039-360">Color preview</span></span>  
    > ![色のプレビュー][ImageColorPreview]  
    
1.  <span data-ttu-id="0b039-362">プレビューをクリックして、**カラーピッカー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="0b039-362">Click the preview to open the **Color Picker**.</span></span>  
    
    > ##### <span data-ttu-id="0b039-363">図27</span><span class="sxs-lookup"><span data-stu-id="0b039-363">Figure 27</span></span>  
    > <span data-ttu-id="0b039-364">**色のパレット**</span><span class="sxs-lookup"><span data-stu-id="0b039-364">The **Color Picker**</span></span>  
    > ![色のパレット][ImageColorPicker]  
    
<span data-ttu-id="0b039-366">次に、**色のパレット**の各 UI 要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0b039-366">Here is a description of each of the UI elements of the **Color Picker**:</span></span>  

> ##### <span data-ttu-id="0b039-367">図28</span><span class="sxs-lookup"><span data-stu-id="0b039-367">Figure 28</span></span>  
> <span data-ttu-id="0b039-368">カラーピッカーの注釈</span><span class="sxs-lookup"><span data-stu-id="0b039-368">The Color Picker, annotated</span></span>  
> ![カラーピッカーの注釈][ImageColorPickerAnnotated]  

1.  <span data-ttu-id="0b039-370">**網掛け**。</span><span class="sxs-lookup"><span data-stu-id="0b039-370">**Shades**.</span></span>  
1.  <span data-ttu-id="0b039-371">**スポイト**。</span><span class="sxs-lookup"><span data-stu-id="0b039-371">**Eyedropper**.</span></span>  <span data-ttu-id="0b039-372">スポイトを使用して[ページの色を設定する方法を](#sample-a-color-off-the-page-with-the-eyedropper)参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b039-372">See [Sample a color off the page with the Eyedropper](#sample-a-color-off-the-page-with-the-eyedropper).</span></span>  
1.  <span data-ttu-id="0b039-373">**クリップボードにコピー**します。</span><span class="sxs-lookup"><span data-stu-id="0b039-373">**Copy To Clipboard**.</span></span>  <span data-ttu-id="0b039-374">**表示値**をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="0b039-374">Copy the **Display Value** to your clipboard.</span></span>  
1.  <span data-ttu-id="0b039-375">**表示値**。</span><span class="sxs-lookup"><span data-stu-id="0b039-375">**Display Value**.</span></span>  <span data-ttu-id="0b039-376">色の RGBA、HSLA、または16進表現。</span><span class="sxs-lookup"><span data-stu-id="0b039-376">The RGBA, HSLA, or Hex representation of the color.</span></span>  
1.  <span data-ttu-id="0b039-377">**カラーパレット**。</span><span class="sxs-lookup"><span data-stu-id="0b039-377">**Color Palette**.</span></span>  <span data-ttu-id="0b039-378">これらの四角形のいずれかをクリックして、その四角形の色を変更します。</span><span class="sxs-lookup"><span data-stu-id="0b039-378">Click one of these squares to change the color to that square.</span></span>  
1.  <span data-ttu-id="0b039-379">**色相**。</span><span class="sxs-lookup"><span data-stu-id="0b039-379">**Hue**.</span></span>  
1.  <span data-ttu-id="0b039-380">**Opacity**。</span><span class="sxs-lookup"><span data-stu-id="0b039-380">**Opacity**.</span></span>  
1.  <span data-ttu-id="0b039-381">**値スイッチャーを表示**します。</span><span class="sxs-lookup"><span data-stu-id="0b039-381">**Display Value Switcher**.</span></span>  <span data-ttu-id="0b039-382">現在の色の RGBA、HSLA、16進表現を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="0b039-382">Toggle between the RGBA, HSLA, and Hex representations of the current color.</span></span>  
1.  <span data-ttu-id="0b039-383">**カラーパレットスイッチャー**。</span><span class="sxs-lookup"><span data-stu-id="0b039-383">**Color Palette Switcher**.</span></span>  <span data-ttu-id="0b039-384">[マテリアルデザインパレット][MaterialDesignColorSystem]、カスタムパレット、またはページカラーパレットを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="0b039-384">Toggle between the [Material Design palette][MaterialDesignColorSystem], a custom palette, or a page colors palette.</span></span>  <span data-ttu-id="0b039-385">DevTools は、スタイルシートで検出された色に基づいてページカラーパレットを生成します。</span><span class="sxs-lookup"><span data-stu-id="0b039-385">DevTools generates the page color palette based on the colors that it finds in your stylesheets.</span></span>  

#### <span data-ttu-id="0b039-386">スポイトを使用してページの色を設定する</span><span class="sxs-lookup"><span data-stu-id="0b039-386">Sample a color off the page with the Eyedropper</span></span>   

<span data-ttu-id="0b039-387">**カラーピッカー**を開くと、**スポイト** ![ スポイト ][ImageEyedropperIcon] がデフォルトでオンになります。</span><span class="sxs-lookup"><span data-stu-id="0b039-387">When you open the **Color Picker**, the **Eyedropper** ![Eyedropper][ImageEyedropperIcon] is on by default.</span></span>  <span data-ttu-id="0b039-388">選択した色をページ上の別の色に変更するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0b039-388">To change the selected color to some other color on the page:</span></span>  

1.  <span data-ttu-id="0b039-389">ビューポートのターゲットの色の上にマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="0b039-389">Hover over the target color in the viewport.</span></span>  
1.  <span data-ttu-id="0b039-390">クリックして確認します。</span><span class="sxs-lookup"><span data-stu-id="0b039-390">Click to confirm.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="0b039-391">[図 29](#figure-29)では、**色のパレット**に現在の色の値が表示されてい `rgba(0,0,0,0.7)` ます。これは黒に近い値です。</span><span class="sxs-lookup"><span data-stu-id="0b039-391">In [Figure 29](#figure-29), the **Color Picker** shows a current color value of `rgba(0,0,0,0.7)`, which is close to black.</span></span>  <span data-ttu-id="0b039-392">この色は、黒がクリックされたときにビューポートで現在強調表示されている黒に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b039-392">This color should change to the black that is currently highlighted in the viewport once the black was clicked.</span></span>  
    
    > ##### <span data-ttu-id="0b039-393">図29</span><span class="sxs-lookup"><span data-stu-id="0b039-393">Figure 29</span></span>  
    > <span data-ttu-id="0b039-394">スポイトを使用する</span><span class="sxs-lookup"><span data-stu-id="0b039-394">Using the Eyedropper</span></span>  
    > ![スポイトを使用する][ImageUsingEyedropper]  
    
 



<!-- image links -->  

[ImageAddBackgroundColorIcon]: /microsoft-edge/devtools-guide-chromium/media/add-background-color-icon.msft.png  
[ImageAddBoxShadowIcon]: /microsoft-edge/devtools-guide-chromium/media/add-box-shadow-icon.msft.png  
[ImageAddColorIcon]: /microsoft-edge/devtools-guide-chromium/media/add-color-icon.msft.png  
[ImageAddTextShadowIcon]: /microsoft-edge/devtools-guide-chromium/media/add-text-shadow-icon.msft.png  
[ImageEyedropperIcon]: /microsoft-edge/devtools-guide-chromium/media/eyedropper-icon.msft.png  
[ImageNewStyleRuleIcon]: /microsoft-edge/devtools-guide-chromium/media/new-style-rule-icon.msft.png  
[ImageRefreshIcon]: /microsoft-edge/devtools-guide-chromium/media/refresh-icon.msft.png  
[ImageSelectAnElementIcon]: /microsoft-edge/devtools-guide-chromium/media/select-an-element-icon.msft.png  

[ImageSelectedElement]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-h1.msft.png "図 1: 選択した要素の例"  
[ImageViewRuleStylesheet]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-h1-highlight.msft.png "図 2: ルールが定義されているスタイルシートの表示"  
[ImageComputedTab]: /microsoft-edge/devtools-guide-chromium/media/css-elements-computed-h1.msft.png "図 3: 計算されたタブ"  
[ImageBoxModel]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-h1-2.msft.png "図 4: ボックスモデル図"  
[ImageStylesFilter]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-filter-color.msft.png "図 5: [スタイル] タブのフィルター処理"  
[ImageComputerFilter]: /microsoft-edge/devtools-guide-chromium/media/css-elements-computed-filter-100.msft.png "図 6: 計算されたタブのフィルター処理"  
[ImagePseudoClass]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-hov-hover.msft.png "図 7: ホバー擬似クラスの切り替え"  
[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/css-console-command-menu-coverage.msft.png "図 8: [コマンド] メニューから [カバレッジ] タブを開く"  
[ImageCoverageEmpty]: /microsoft-edge/devtools-guide-chromium/media/css-console-qs-coverage-empty.msft.png "図 9: [カバレッジ] タブ"  
[ImageCoverageOverview]: /microsoft-edge/devtools-guide-chromium/media/css-console-qs-coverage-run.msft.png "図 10: 使用されている CSS (および JavaScript) の概要"  
[ImageCoverageDetail]: /microsoft-edge/devtools-guide-chromium/media/css-sources-css-coverage.msft.png "図 11: 使用されている CSS と未使用の CSS の行単位の内訳"  
[ImageInlineDeclarations]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-margin-top-background-color.msft.png "図 12: インライン宣言の追加"  
[ImageAddDeclarationExistingRule]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-border-bottom-style.msft.png "図 13: スタイルルールへの宣言の追加"  
[ImageAddDeclarationExistingRule2]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-border-bottom-style-dropdown.msft.png "図 14: 宣言の値を変更する"  
[ImageElementClasses]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-filter-classes.msft.png "図 15: [要素クラス] ウィンドウ"  
[ImageStyleRule]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-style-new.msft.png "図 16: 新しいスタイルルールを追加する"  
[ImageChooseStylesheet]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-style-new-select-exisiting.msft.png "図 17: スタイルシートの選択"  
[ImageInsertStyleRuleBelow]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-insert-style-rule-below.msft.png "図 18: スタイルルールを下に挿入する"  
[ImageRevealMore]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-new-rule-styles.msft.png "図 19: その他の操作を確認する"  
[ImageInsertStyleRuleBelow2]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png "図 20: [その他の操作] ツールバー"  
[ImageToggleDeclaration]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-deactivated.msft.png "図 21: 宣言の切り替え"  
[ImageAddBackgroundColor]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-add-background-color.msft.png "図 22: 背景色を追加する"  
[ImageAddColor]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-add-color.msft.png "図 23: 色を追加する"  
[ImageAddBoxShadow]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-add-box-shadow.msft.png "図 24: ボックスの影を追加する"  
[ImageAddTextShadow]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-add-text-shadow.msft.png "図 25: テキストの影を追加する"  
[ImageColorPreview]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-overlay-color-box.msft.png "図 26: 色のプレビュー"  
[ImageColorPicker]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-color-picker.msft.png "図 27: 色のパレット"  
[ImageColorPickerAnnotated]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-color-picker-annotated.msft.png "図 28: カラーピッカーの注釈"  
[ImageUsingEyedropper]: /microsoft-edge/devtools-guide-chromium/media/css-color-picker-eye-dropper.msft.png "図 29: スポイトを使用する"  

<!-- links -->  

[DevToolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index "Microsoft Edge DevTools コマンドメニューを使用してコマンドを実行する"  
[DevToolsCSSGetStarted]: /microsoft-edge/devtools-guide-chromium/css/index "CSS の表示と変更を始める"  
[DevToolsCSSGetStartedAddPseudoState]: /microsoft-edge/devtools-guide-chromium/css/index#add-a-pseudostate-to-a-class "クラスに疑似状態を追加する-CSS の表示と変更の概要"  
[DevToolsCSSGetStartedTutorial]: /microsoft-edge/devtools-guide-chromium/css/index#view-the-css-for-an-element "要素の CSS を表示する-CSS の表示と変更の概要"  
[DevToolsCssPrintPreview]: /microsoft-edge/devtools-guide-chromium/css/print-preview "Microsoft Edge の DevTools を印刷プレビューモード (CSS 印刷メディアの種類) に強制する"  
[DevToolsJavascriptReferenceFormat]: /microsoft-edge/devtools-guide-chromium/javascript/reference#make-a-minified-file-readable "指定したミニファイルを読みやすくします。 JavaScript のデバッグ参照"  

[MaterialDesignColorSystem]: https://material.io/guidelines/style/color.html#color-color-palette "カラーシステム-マテリアルデザイン"  
[MDNBoxModel]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Box_model "ボックスモデル |MDN"  
[MDNSelectorTypes]: https://developer.mozilla.org/docs/Web/CSS/Specificity#Selector_Types "セレクターの種類-特異性 |MDN"  

> [!NOTE]
> <span data-ttu-id="0b039-434">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="0b039-434">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0b039-435">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/css/reference)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="0b039-435">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="0b039-437">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="0b039-437">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
