---
description: DevTools で CSS を表示および変更するための新しいワークフロー Microsoft Edge確認します。
title: CCS リファレンス
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 0680b08c9809698c1db6c186a7be76a93c31df4b
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564477"
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
# <a name="css-reference"></a><span data-ttu-id="758f0-104">CCS リファレンス</span><span class="sxs-lookup"><span data-stu-id="758f0-104">CSS reference</span></span>  

<span data-ttu-id="758f0-105">CSS の表示と変更に関連する DevTools Microsoft Edgeの包括的な参照で、新しいワークフローを確認します。</span><span class="sxs-lookup"><span data-stu-id="758f0-105">Discover new workflows in the following comprehensive reference of Microsoft Edge DevTools features related to viewing and changing CSS.</span></span>  

<span data-ttu-id="758f0-106">基本を学習するには、[CSS の表示と変更[はじめにに移動します][DevToolsCSSGetStarted]。</span><span class="sxs-lookup"><span data-stu-id="758f0-106">To learn the basics, navigate to [Get Started with Viewing and Changing CSS][DevToolsCSSGetStarted].</span></span>  

## <a name="choose-an-element"></a><span data-ttu-id="758f0-107">要素を選択する</span><span class="sxs-lookup"><span data-stu-id="758f0-107">Choose an element</span></span>  

<span data-ttu-id="758f0-108">**DevTools**の Elements ツールを使用すると、一度に 1 つの要素の CSS を表示または変更できます。</span><span class="sxs-lookup"><span data-stu-id="758f0-108">The **Elements** tool of DevTools lets you view or change the CSS of one element at a time.</span></span>  <span data-ttu-id="758f0-109">選択した要素が DOM ツリーで **強調表示されます**。</span><span class="sxs-lookup"><span data-stu-id="758f0-109">The selected element is highlighted in the **DOM Tree**.</span></span>  <span data-ttu-id="758f0-110">要素のスタイルが [スタイル] ウィンドウ **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="758f0-110">The styles of the element are shown in the **Styles** pane.</span></span>  <span data-ttu-id="758f0-111">チュートリアルでは、[要素の [CSS を表示する] に移動します][DevToolsCSSGetStartedTutorial]。</span><span class="sxs-lookup"><span data-stu-id="758f0-111">For a tutorial, navigate to [View the CSS for an element][DevToolsCSSGetStartedTutorial].</span></span>  

> [!NOTE]
> <span data-ttu-id="758f0-112">次の図では `h1` **、DOM** ツリーで強調表示されている要素が選択された要素です。</span><span class="sxs-lookup"><span data-stu-id="758f0-112">In the following figure, the `h1` element that is highlighted in the **DOM Tree** is the selected element.</span></span>  <span data-ttu-id="758f0-113">右側の要素のスタイルが [スタイル] ウィンドウに **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="758f0-113">On the right, the styles of the element are shown in the **Styles** pane.</span></span>  <span data-ttu-id="758f0-114">左側では、要素はビューポートで強調表示されますが、マウスが **現在 DOM**ツリーでマウスポインターを置くためです。</span><span class="sxs-lookup"><span data-stu-id="758f0-114">On the left, the element is highlighted in the viewport, but only because the mouse is currently hovering over it in the **DOM Tree**.</span></span>  

:::image type="complex" source="../media/css-elements-styles-h1.msft.png" alt-text="選択した要素の例" lightbox="../media/css-elements-styles-h1.msft.png":::
   <span data-ttu-id="758f0-116">選択した要素の例</span><span class="sxs-lookup"><span data-stu-id="758f0-116">An example of a selected element</span></span>  
:::image-end:::  

<span data-ttu-id="758f0-117">要素を選択するには、次のいずれかのアクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="758f0-117">Use one the following actions to select an element.</span></span>  

*   <span data-ttu-id="758f0-118">ビューポートで、要素にマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="758f0-118">In your viewport, hover on the element, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
*   <span data-ttu-id="758f0-119">DevTools で、[要素を選択] \( Select **an** element \) を選択するか ![ ](../media/select-an-element-icon.msft.png) `Control` + `Shift` + `C` 、\(Windows、 Linux\) または `Command` + `Shift` + `C` \(macOS\) を選択し、ビューポートで要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="758f0-119">In DevTools, choose **Select an element** \(![Select an element](../media/select-an-element-icon.msft.png)\) or select `Control`+`Shift`+`C` \(Windows, Linux\) or `Command`+`Shift`+`C` \(macOS\), and then choose the element in the viewport.</span></span>  
*   <span data-ttu-id="758f0-120">DevTools で、DOM ツリーの要素を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="758f0-120">In DevTools, choose the element in the **DOM Tree**.</span></span>  
*   <span data-ttu-id="758f0-121">DevTools で、コンソールのようなクエリを実行し、結果にマウス ポインターを置き、コンテキスト メニュー `document.querySelector('p')` \(右クリック\) を開き、[要素] パネルで [表示] を**選択します**。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="758f0-121">In DevTools, run a query like `document.querySelector('p')` in the **Console**, hover on the result, open the contextual menu \(right-click\), and choose **Reveal in Elements panel**.</span></span>  

## <a name="view-css"></a><span data-ttu-id="758f0-122">CSS の表示</span><span class="sxs-lookup"><span data-stu-id="758f0-122">View CSS</span></span>  

### <a name="view-the-external-stylesheet-where-a-rule-is-defined"></a><span data-ttu-id="758f0-123">ルールが定義されている外部スタイルシートを表示する</span><span class="sxs-lookup"><span data-stu-id="758f0-123">View the external stylesheet where a rule is defined</span></span>  

<span data-ttu-id="758f0-124">[スタイル **] ウィンドウ** で、CSS ルールの横にあるリンクを選択して、ルールを定義する外部スタイルシートを開きます。</span><span class="sxs-lookup"><span data-stu-id="758f0-124">In the **Styles** pane, choose the link next to a CSS rule to open the external stylesheet that defines the rule.</span></span>  <span data-ttu-id="758f0-125">スタイルシートは、[ソース] ツール **の [エディター** ] ウィンドウ **で開** きます。</span><span class="sxs-lookup"><span data-stu-id="758f0-125">The stylesheet opens in the **Editor** pane of the **Sources** tool.</span></span>  

<span data-ttu-id="758f0-126">スタイルシートが minified の場合は、[エディター] ウィンドウの下部にある [ **書式]** ![ ](../media/format-icon.msft.png) \( Format \) ボタン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="758f0-126">If the stylesheet is minified, choose the **Format** \(![Format](../media/format-icon.msft.png)\) button, at the bottom of the **Editor** pane.</span></span>  <span data-ttu-id="758f0-127">詳細については、「ミニマリストの JavaScript ファイルをプリティプリントで再フォーマット [する」に移動します][DevToolsJavascriptReferenceFormat]。</span><span class="sxs-lookup"><span data-stu-id="758f0-127">For more information, navigate to [Reformat a minified JavaScript file with pretty-print][DevToolsJavascriptReferenceFormat].</span></span>  

> [!NOTE]
> <span data-ttu-id="758f0-128">次の図では、選択した後、CSS ルールが定義されている `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` 行 2 `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css` `.content h1:first-of-type` に移動します。</span><span class="sxs-lookup"><span data-stu-id="758f0-128">In the following figure, after you choose `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` you are taken to line 2 of `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css`, where the `.content h1:first-of-type` CSS rule is defined.</span></span>  

<!--todo:  replace "Master" phrasing in code snippet, if possible.  -->  

:::image type="complex" source="../media/css-elements-styles-h1-highlight.msft.png" alt-text="ルールが定義されているスタイルシートの表示" lightbox="../media/css-elements-styles-h1-highlight.msft.png":::
  <span data-ttu-id="758f0-130">ルールが定義されているスタイルシートの表示</span><span class="sxs-lookup"><span data-stu-id="758f0-130">Viewing the stylesheet where a rule is defined</span></span>  
:::image-end:::  

### <a name="view-only-the-css-that-is-actually-applied-to-an-element"></a><span data-ttu-id="758f0-131">要素に実際に適用される CSS のみを表示する</span><span class="sxs-lookup"><span data-stu-id="758f0-131">View only the CSS that is actually applied to an element</span></span>  

<span data-ttu-id="758f0-132">[ **スタイル** ] パネルには、オーバーライドされた宣言を含む、要素に適用されるすべてのルールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="758f0-132">The **Styles** panel shows you all of the rules that apply to an element, including declarations that have been overridden.</span></span>  <span data-ttu-id="758f0-133">オーバーライドされた宣言に興味がない場合は、[計算] パネル\*\*\*\* を使用して、要素に実際に適用されている CSS のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="758f0-133">When you are not interested in overridden declarations, use the **Computed** panel to view only the CSS that is actually being applied to an element.</span></span>  

1.  <span data-ttu-id="758f0-134">[要素を選択します](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="758f0-134">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="758f0-135">[要素] **ツールの [** 計算] パネル **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="758f0-135">Navigate to the **Computed** panel in the **Elements** tool.</span></span>  

> [!NOTE]
> <span data-ttu-id="758f0-136">ワイドな DevTools ウィンドウでは、[ **計算] パネル** は存在しません。</span><span class="sxs-lookup"><span data-stu-id="758f0-136">On a wide DevTools window, the **Computed** panel does not exist.</span></span>  <span data-ttu-id="758f0-137">[計算] パネル **の内容** が [スタイル] パネル **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="758f0-137">The contents of the **Computed** panel are shown on the **Styles** panel.</span></span>  

<span data-ttu-id="758f0-138">継承されたプロパティは不透明です。</span><span class="sxs-lookup"><span data-stu-id="758f0-138">Inherited properties are opaque.</span></span>  <span data-ttu-id="758f0-139">継承された値を表示するには、[すべて表示] **チェック ボックスを** オンにします。</span><span class="sxs-lookup"><span data-stu-id="758f0-139">To display all inherited values, select the **Show All** checkbox.</span></span>  

> [!NOTE]
> <span data-ttu-id="758f0-140">次の図では、[計算] **パネル** に、現在選択されている要素に適用されている CSS プロパティが表示 `h1` されます。</span><span class="sxs-lookup"><span data-stu-id="758f0-140">In the following figure, the **Computed** panel shows the CSS properties being applied to the currently-selected `h1` element.</span></span>  

:::image type="complex" source="../media/css-elements-computed-h1.msft.png" alt-text="[計算] パネル" lightbox="../media/css-elements-computed-h1.msft.png":::
   <span data-ttu-id="758f0-142">[ **計算]** パネル</span><span class="sxs-lookup"><span data-stu-id="758f0-142">The **Computed** panel</span></span>  
:::image-end:::  

### <a name="view-css-properties-in-alphabetical-order"></a><span data-ttu-id="758f0-143">CSS プロパティをアルファベット順に表示する</span><span class="sxs-lookup"><span data-stu-id="758f0-143">View CSS properties in alphabetical order</span></span>  

<span data-ttu-id="758f0-144">[計算 **] パネルを使用** します。</span><span class="sxs-lookup"><span data-stu-id="758f0-144">Use the **Computed** panel.</span></span>  <span data-ttu-id="758f0-145">[要素 [に実際に適用される CSS のみを表示する] に移動します](#view-only-the-css-that-is-actually-applied-to-an-element)。</span><span class="sxs-lookup"><span data-stu-id="758f0-145">Navigate to [View only the CSS that is actually applied to an element](#view-only-the-css-that-is-actually-applied-to-an-element).</span></span>  

### <a name="view-inherited-css-properties"></a><span data-ttu-id="758f0-146">継承された CSS プロパティの表示</span><span class="sxs-lookup"><span data-stu-id="758f0-146">View inherited CSS properties</span></span>  

<span data-ttu-id="758f0-147">[計算] **パネルの** [すべて表示 **] チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="758f0-147">Check the **Show All** checkbox in the **Computed** panel.</span></span>  <span data-ttu-id="758f0-148">[要素 [に実際に適用される CSS のみを表示する] に移動します](#view-only-the-css-that-is-actually-applied-to-an-element)。</span><span class="sxs-lookup"><span data-stu-id="758f0-148">Navigate to [View only the CSS that is actually applied to an element](#view-only-the-css-that-is-actually-applied-to-an-element).</span></span>  

### <a name="view-the-box-model-for-an-element"></a><span data-ttu-id="758f0-149">要素のボックス モデルを表示する</span><span class="sxs-lookup"><span data-stu-id="758f0-149">View the box model for an element</span></span>  

<span data-ttu-id="758f0-150">要素の [ボックス モデルを表示][MDNBoxModel] するには、[スタイル] パネル **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="758f0-150">To view [the box model][MDNBoxModel] of an element, navigate to the **Styles** panel.</span></span>  <span data-ttu-id="758f0-151">DevTools ウィンドウが狭い場合、 **ボックス モデル** 図はパネルの下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="758f0-151">If your DevTools window is narrow, the **Box Model** diagram is at the bottom of the panel.</span></span>  

<span data-ttu-id="758f0-152">値を変更するには、値を選択して編集します。</span><span class="sxs-lookup"><span data-stu-id="758f0-152">Choose and edit on a value to change a value.</span></span>  

> [!NOTE]
> <span data-ttu-id="758f0-153">次の図では、[スタイル **]** パネルのボックス モデル **図に、** 現在選択されている要素のボックス モデルが表示 `h1` されています。</span><span class="sxs-lookup"><span data-stu-id="758f0-153">In the following figure, the **Box Model** diagram in the **Styles** panel shows the box model for the currently selected `h1` element.</span></span>  

:::image type="complex" source="../media/css-elements-styles-h1-2.msft.png" alt-text="Box モデル図" lightbox="../media/css-elements-styles-h1-2.msft.png":::
   <span data-ttu-id="758f0-155">Box**モデル図**</span><span class="sxs-lookup"><span data-stu-id="758f0-155">The **Box Model** diagram</span></span>  
:::image-end:::  

### <a name="search-and-filter-the-css-of-an-element"></a><span data-ttu-id="758f0-156">要素の CSS を検索してフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="758f0-156">Search and filter the CSS of an element</span></span>  

<span data-ttu-id="758f0-157">[スタイル]**パネルと**[計算\*\*\*\*] パネル**の [** フィルター] テキスト ボックスを使用して、特定の CSS プロパティまたは値を検索します。</span><span class="sxs-lookup"><span data-stu-id="758f0-157">Use the **Filter** text box on the **Styles** and **Computed** panels to search for specific CSS properties or values.</span></span>  

<span data-ttu-id="758f0-158">[計算] パネルで継承されたプロパティも **検索** するには、[すべて表示] **チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="758f0-158">To also search inherited properties in the **Computed** panel, check the **Show All** checkbox.</span></span>  

> [!NOTE]
> <span data-ttu-id="758f0-159">次の図では **、[スタイル]** パネルがフィルター処理され、検索クエリを含むルールだけが表示されます `color` 。</span><span class="sxs-lookup"><span data-stu-id="758f0-159">In the following figure, the **Styles** panel is filtered to only show rules that include the search query `color`.</span></span>  

:::image type="complex" source="../media/css-elements-styles-filter-color.msft.png" alt-text="[スタイル] パネルをフィルター処理する" lightbox="../media/css-elements-styles-filter-color.msft.png":::
   <span data-ttu-id="758f0-161">[スタイル] **パネルをフィルター** 処理する</span><span class="sxs-lookup"><span data-stu-id="758f0-161">Filter the **Styles** panel</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="758f0-162">次の図では、[ **計算** ] パネルがフィルター処理され、検索クエリを含む宣言だけが表示されます `100%` 。</span><span class="sxs-lookup"><span data-stu-id="758f0-162">In the following figure, the **Computed** panel is filtered to only show declarations that include the search query `100%`.</span></span>  

:::image type="complex" source="../media/css-elements-computed-filter-100.msft.png" alt-text="[計算] パネルをフィルター処理する" lightbox="../media/css-elements-computed-filter-100.msft.png":::
   <span data-ttu-id="758f0-164">[計算 **] パネルをフィルター** 処理する</span><span class="sxs-lookup"><span data-stu-id="758f0-164">Filter the **Computed** panel</span></span>  
:::image-end:::  

### <a name="toggle-a-pseudo-class"></a><span data-ttu-id="758f0-165">疑似クラスの切り替え</span><span class="sxs-lookup"><span data-stu-id="758f0-165">Toggle a pseudo-class</span></span>  

<span data-ttu-id="758f0-166">次のアクションを実行して、など、擬似クラス `:active` `:focus` `:hover` を切り替える `:visited` 。</span><span class="sxs-lookup"><span data-stu-id="758f0-166">Complete the following actions to toggle a pseudo-class like `:active`, `:focus`, `:hover`, or `:visited`.</span></span>  

1.  <span data-ttu-id="758f0-167">[要素を選択します](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="758f0-167">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="758f0-168">[要素] **ツール** で、[スタイル] パネル **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="758f0-168">On the **Elements** tool, navigate to the **Styles** panel.</span></span>  
1.  <span data-ttu-id="758f0-169">**[:hov] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="758f0-169">Choose **:hov**.</span></span>  
1.  <span data-ttu-id="758f0-170">有効にする擬似クラスを確認します。</span><span class="sxs-lookup"><span data-stu-id="758f0-170">Check the pseudo-class that you want to enable.</span></span>  

> [!NOTE]
> <span data-ttu-id="758f0-171">次の図では、擬似クラス `:hover` を切り替える。</span><span class="sxs-lookup"><span data-stu-id="758f0-171">In the following figure, toggle the `:hover` pseudo-class.</span></span>  <span data-ttu-id="758f0-172">ビューポートで、要素が実際にホバーされていない場合でも、宣言が要素に適用されている `background-color: cornflowerblue` のを確認します。</span><span class="sxs-lookup"><span data-stu-id="758f0-172">In the viewport verify that the `background-color: cornflowerblue` declaration is being applied to the element, even though the element is not actually being hovered over.</span></span>  

:::image type="complex" source="../media/css-elements-styles-hov-hover.msft.png" alt-text=":hover 擬似クラスを切り替える" lightbox="../media/css-elements-styles-hov-hover.msft.png":::
   <span data-ttu-id="758f0-174">擬似クラス `:hover` を切り替える</span><span class="sxs-lookup"><span data-stu-id="758f0-174">Toggle the `:hover` pseudo-class</span></span>  
:::image-end:::  

<span data-ttu-id="758f0-175">対話型チュートリアルの場合は、[クラスに擬似 [状態を追加する] に移動します][DevToolsCSSGetStartedAddPseudoState]。</span><span class="sxs-lookup"><span data-stu-id="758f0-175">For an interactive tutorial, navigate to [Add a pseudostate to a class][DevToolsCSSGetStartedAddPseudoState].</span></span>  

### <a name="view-a-page-in-print-mode"></a><span data-ttu-id="758f0-176">印刷モードでページを表示する</span><span class="sxs-lookup"><span data-stu-id="758f0-176">View a page in print mode</span></span>  

<span data-ttu-id="758f0-177">印刷モードでページを表示するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="758f0-177">Complete the following actions to view a page in print mode.</span></span>  

1.  <span data-ttu-id="758f0-178">[コマンド メニューを開きます][DevToolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="758f0-178">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="758f0-179">入力を開始 `Rendering` して選択します `Show Rendering` 。</span><span class="sxs-lookup"><span data-stu-id="758f0-179">Start typing `Rendering` and select `Show Rendering`.</span></span>  
1.  <span data-ttu-id="758f0-180">[CSS **メディアのエミュレート] ドロップダウンで** 、[印刷] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="758f0-180">For the **Emulate CSS Media** dropdown, choose **print**.</span></span>  

### <a name="view-used-and-unused-css-with-the-coverage-tool"></a><span data-ttu-id="758f0-181">カバレッジ ツールを使用して、使用されている CSS と未使用の CSS を表示する</span><span class="sxs-lookup"><span data-stu-id="758f0-181">View used and unused CSS with the Coverage tool</span></span>  

<span data-ttu-id="758f0-182">[ **カバレッジ]** ツールには、ページが実際に使用する CSS が表示されます。</span><span class="sxs-lookup"><span data-stu-id="758f0-182">The **Coverage** tool shows you what CSS a page actually uses.</span></span>  

1.  <span data-ttu-id="758f0-183">`Control` + `Shift` + `P` DevTools のフォーカス中に \(Windows、Linux\) または `Command` + `Shift` + `P` \(macOS\)[][DevToolsCommandMenu]を選択してコマンド メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="758f0-183">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) while DevTools is in focus to [open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="758f0-184">入力を開始し `coverage` 、[カバレッジの **表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="758f0-184">Start typing `coverage` and choose **Show Coverage**.</span></span>  <span data-ttu-id="758f0-185">[ **カバレッジ]** ツールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="758f0-185">The **Coverage** tool appears.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-command-menu-coverage.msft.png" alt-text="コマンド メニューからカバレッジ ツールを開く" lightbox="../media/css-console-command-menu-coverage.msft.png":::
             <span data-ttu-id="758f0-187">コマンド メニュー **からカバレッジ** ツールを **開く**</span><span class="sxs-lookup"><span data-stu-id="758f0-187">Open the **Coverage** tool from the **Command Menu**</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-qs-coverage-empty.msft.png" alt-text="カバレッジ ツール" lightbox="../media/css-console-qs-coverage-empty.msft.png":::
             <span data-ttu-id="758f0-189">カバレッジ**ツール**</span><span class="sxs-lookup"><span data-stu-id="758f0-189">The **Coverage** tool</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="758f0-190">[ **インストルメントカバレッジの開始] を選択し、** ページ \( インストルメントカバレッジの開始とページの更新 ![ \) を更新 ](../media/refresh-icon.msft.png) します。</span><span class="sxs-lookup"><span data-stu-id="758f0-190">Choose **Start instrumenting coverage and refresh the page** \(![Start instrumenting coverage and refresh the page](../media/refresh-icon.msft.png)\).</span></span>  <span data-ttu-id="758f0-191">ページが更新され、カバレッジ ツール **は** 、ブラウザーが読み込む各ファイルから使用される CSS \(および JavaScript\) の量の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="758f0-191">The page refreshes and the **Coverage** tool provides an overview of how much CSS \(and JavaScript\) is used from each file that the browser loads.</span></span>  <span data-ttu-id="758f0-192">緑色は、使用されている CSS を表します。</span><span class="sxs-lookup"><span data-stu-id="758f0-192">Green represents used CSS.</span></span>  <span data-ttu-id="758f0-193">赤は未使用の CSS を表します。</span><span class="sxs-lookup"><span data-stu-id="758f0-193">Red represents unused CSS.</span></span>  
    
    :::image type="complex" source="../media/css-console-qs-coverage-run.msft.png" alt-text="CSS (および JavaScript) の使用と未使用の量の概要" lightbox="../media/css-console-qs-coverage-run.msft.png":::
       <span data-ttu-id="758f0-195">CSS \(and JavaScript\) の使用と使用の概要</span><span class="sxs-lookup"><span data-stu-id="758f0-195">An overview of how much CSS \(and JavaScript\) is used and unused</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="758f0-196">使用する CSS の行の内訳を表示するには、CSS ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="758f0-196">To display a line-by-line breakdown of what CSS is used, choose a CSS file.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="758f0-197">次の図では、145 行から 147 行、149 行から 151 行が使用されているのに対し、 `b66bc881.site-ltr.css` 行 163 ~ 166 は使用されます。</span><span class="sxs-lookup"><span data-stu-id="758f0-197">In the following figure, lines 145 to 147 and 149 to 151 of `b66bc881.site-ltr.css` are unused, whereas lines 163 to 166 are used.</span></span>  
    
    :::image type="complex" source="../media/css-sources-css-coverage.msft.png" alt-text="使用されている CSS と未使用の CSS の行別の内訳" lightbox="../media/css-sources-css-coverage.msft.png":::
       <span data-ttu-id="758f0-199">使用されている CSS と未使用の CSS の行別の内訳</span><span class="sxs-lookup"><span data-stu-id="758f0-199">A line-by-line breakdown of used and unused CSS</span></span>  
    :::image-end:::  
    
### <a name="force-print-preview-mode"></a><span data-ttu-id="758f0-200">印刷プレビュー モードの強制</span><span class="sxs-lookup"><span data-stu-id="758f0-200">Force print preview mode</span></span>  

<span data-ttu-id="758f0-201">[[DevTools を印刷プレビュー モードにする] に移動します][DevToolsCssPrintPreview]。</span><span class="sxs-lookup"><span data-stu-id="758f0-201">Navigate to [Force DevTools into Print Preview mode][DevToolsCssPrintPreview].</span></span>  

## <a name="change-css"></a><span data-ttu-id="758f0-202">CSS を変更する</span><span class="sxs-lookup"><span data-stu-id="758f0-202">Change CSS</span></span>  

<!-- todo s/CSS declaration/declaration/ -->  

### <a name="add-a-css-declaration-to-an-element"></a><span data-ttu-id="758f0-203">要素に CSS 宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="758f0-203">Add a CSS declaration to an element</span></span>  

<span data-ttu-id="758f0-204">宣言の順序は、要素のスタイルに影響します。次の一覧を使用して、さまざまな方法で宣言を追加できます。</span><span class="sxs-lookup"><span data-stu-id="758f0-204">The order of declarations affects how an element is styled, use the following list to help you add declarations in different ways.</span></span>  

*   <span data-ttu-id="758f0-205">[インライン宣言を追加します](#add-an-inline-declaration)。</span><span class="sxs-lookup"><span data-stu-id="758f0-205">[Add a inline declaration](#add-an-inline-declaration).</span></span>  <span data-ttu-id="758f0-206">要素の HTML `style` に属性を追加するのと同じです。</span><span class="sxs-lookup"><span data-stu-id="758f0-206">Equivalent to adding a `style` attribute to the HTML of an element.</span></span>  
*   <span data-ttu-id="758f0-207">[スタイル ルールに宣言を追加します](#add-a-declaration-to-a-style-rule)。</span><span class="sxs-lookup"><span data-stu-id="758f0-207">[Add a declaration to a style rule](#add-a-declaration-to-a-style-rule).</span></span>  

**<span data-ttu-id="758f0-208">どのワークフローを使用する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="758f0-208">What workflow should you use?</span></span>** <span data-ttu-id="758f0-209">ほとんどのシナリオでは、インライン宣言ワークフローを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="758f0-209">For most scenarios, you probably want to use the inline declaration workflow.</span></span>  <span data-ttu-id="758f0-210">インライン宣言は外部の宣言よりも高い固有性を持つので、インライン ワークフローによって、予期される要素で変更が確実に有効になります。</span><span class="sxs-lookup"><span data-stu-id="758f0-210">Inline declarations have higher specificity than external ones, so the inline workflow ensures that the changes take effect in your expected element.</span></span>  <span data-ttu-id="758f0-211">詳細については、「セレクターの種類」 [に移動します][MDNSelectorTypes]。</span><span class="sxs-lookup"><span data-stu-id="758f0-211">For more information about specificity, navigate to [Selector Types][MDNSelectorTypes].</span></span>  

<span data-ttu-id="758f0-212">要素のスタイルをデバッグする場合に、宣言が異なる場所で定義されている場合の処理を具体的にテストする必要がある場合は、他のワークフローを使用します。</span><span class="sxs-lookup"><span data-stu-id="758f0-212">If you are debugging any styles of the element and you need to specifically test what happens when a declaration is defined in different places, use the other workflow.</span></span>  

#### <a name="add-an-inline-declaration"></a><span data-ttu-id="758f0-213">インライン宣言の追加</span><span class="sxs-lookup"><span data-stu-id="758f0-213">Add an inline declaration</span></span>  

<span data-ttu-id="758f0-214">インライン宣言を追加するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="758f0-214">Complete the following actions to add an inline declaration.</span></span>  

1.  <span data-ttu-id="758f0-215">[要素を選択します](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="758f0-215">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="758f0-216">[スタイル **] ウィンドウ** で、element.style セクションの角かっこ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="758f0-216">In the **Styles** pane, choose between the brackets of the **element.style** section.</span></span>  <span data-ttu-id="758f0-217">カーソルの焦点が合い、テキストを入力できます。</span><span class="sxs-lookup"><span data-stu-id="758f0-217">The cursor focuses, allowing you to enter text.</span></span>  
1.  <span data-ttu-id="758f0-218">プロパティ名を入力して選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="758f0-218">Enter a property name and select `Enter`.</span></span>  
1.  <span data-ttu-id="758f0-219">そのプロパティの有効な値を入力し、を選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="758f0-219">Enter a valid value for that property and select `Enter`.</span></span>  <span data-ttu-id="758f0-220">DOM ツリー **で、** 属性が `style` 要素に追加されたと確認します。</span><span class="sxs-lookup"><span data-stu-id="758f0-220">In the **DOM Tree**, verify that a `style` attribute has been added to the element.</span></span>  

> [!NOTE]
> <span data-ttu-id="758f0-221">次の図では、選択 `margin-top` した `background-color` 要素にプロパティとプロパティが適用されています。</span><span class="sxs-lookup"><span data-stu-id="758f0-221">In the following figure, the `margin-top` and `background-color` properties have been applied to the selected element.</span></span>  <span data-ttu-id="758f0-222">DOM ツリー **で** 、宣言が要素の属性に反映 `style` されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="758f0-222">In the **DOM Tree** verify that the declarations are reflected in the `style` attribute for an element.</span></span>  

:::image type="complex" source="../media/css-elements-styles-margin-top-background-color.msft.png" alt-text="インライン宣言の追加" lightbox="../media/css-elements-styles-margin-top-background-color.msft.png":::
   <span data-ttu-id="758f0-224">インライン宣言の追加</span><span class="sxs-lookup"><span data-stu-id="758f0-224">Add inline declarations</span></span>  
:::image-end:::  

#### <a name="add-a-declaration-to-a-style-rule"></a><span data-ttu-id="758f0-225">スタイル ルールに宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="758f0-225">Add a declaration to a style rule</span></span>  

<span data-ttu-id="758f0-226">既存のスタイル ルールに宣言を追加するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="758f0-226">Complete the following actions to add a declaration to an existing style rule.</span></span>  

1.  <span data-ttu-id="758f0-227">[要素を選択します](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="758f0-227">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="758f0-228">[スタイル **] ウィンドウ** で、宣言を追加するスタイル ルールのかっこを選択します。</span><span class="sxs-lookup"><span data-stu-id="758f0-228">In the **Styles** pane, choose between the brackets of the style rule to which you want to add the declaration.</span></span>  <span data-ttu-id="758f0-229">カーソルの焦点が合い、テキストを入力できます。</span><span class="sxs-lookup"><span data-stu-id="758f0-229">The cursor focuses, allowing you to enter text.</span></span>  
1.  <span data-ttu-id="758f0-230">プロパティ名を入力して選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="758f0-230">Enter a property name and select `Enter`.</span></span>  
1.  <span data-ttu-id="758f0-231">そのプロパティの有効な値を入力し、を選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="758f0-231">Enter a valid value for that property and select `Enter`.</span></span>  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style.msft.png" alt-text="スタイル ルールへの宣言の追加" lightbox="../media/css-elements-styles-border-bottom-style.msft.png":::
   <span data-ttu-id="758f0-233">スタイル ルール `border-bottom-style:groove` に宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="758f0-233">Add the `border-bottom-style:groove` declaration to a style rule</span></span>  
:::image-end:::  

### <a name="change-a-declaration-name-or-value"></a><span data-ttu-id="758f0-234">宣言の名前または値を変更する</span><span class="sxs-lookup"><span data-stu-id="758f0-234">Change a declaration name or value</span></span>  

<span data-ttu-id="758f0-235">宣言の名前または値を選択して編集し、変更します。</span><span class="sxs-lookup"><span data-stu-id="758f0-235">Choose and edit the name or value of a declaration to change it.</span></span>  <span data-ttu-id="758f0-236">値を 、または単位で迅速にインクリメントまたはデクリメントするショートカットについては、キーボード ショートカットを使用して宣言値を変更 `0.1` `1` `10` `100` [するに移動します](#change-declaration-values-with-keyboard-shortcuts)。</span><span class="sxs-lookup"><span data-stu-id="758f0-236">For shortcuts for quickly incrementing or decrementing a value by `0.1`, `1`, `10`, or `100` units, navigate to [Change declaration values with keyboard shortcuts](#change-declaration-values-with-keyboard-shortcuts).</span></span>  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style-dropdown.msft.png" alt-text="宣言の値の変更" lightbox="../media/css-elements-styles-border-bottom-style-dropdown.msft.png":::
   <span data-ttu-id="758f0-238">宣言の値を変更 `border-bottom-style` する</span><span class="sxs-lookup"><span data-stu-id="758f0-238">Change the value of the `border-bottom-style` declaration</span></span>  
:::image-end:::  

### <a name="change-declaration-values-with-keyboard-shortcuts"></a><span data-ttu-id="758f0-239">キーボード ショートカットを使用して宣言値を変更する</span><span class="sxs-lookup"><span data-stu-id="758f0-239">Change declaration values with keyboard shortcuts</span></span>  

<span data-ttu-id="758f0-240">宣言の値を編集する場合は、次のキーボード ショートカットを使用して、値を特定の量ずつ増やします。</span><span class="sxs-lookup"><span data-stu-id="758f0-240">While editing the value of a declaration, you may use the following keyboard shortcuts to increment the value by a specific amount.</span></span>  

*   <span data-ttu-id="758f0-241">`Alt` + `Up` \(Windows、Linux\) または `Option` + `Up` \(macOS\) を選択して増分します `0.1` 。</span><span class="sxs-lookup"><span data-stu-id="758f0-241">Select `Alt`+`Up` \(Windows, Linux\) or `Option`+`Up` \(macOS\) to increment by `0.1`.</span></span>  
*   <span data-ttu-id="758f0-242">現在 `Up` の値がとの `1` 間の場合、またはによって値を `0.1` 変更する場合に `-1` 選択します `1` 。</span><span class="sxs-lookup"><span data-stu-id="758f0-242">Select `Up` to change the value by `1`, or by `0.1` if the current value is between `-1` and `1`.</span></span>  
*   <span data-ttu-id="758f0-243">によって `Shift` + `Up` 増分する場合に選択します `10` 。</span><span class="sxs-lookup"><span data-stu-id="758f0-243">Select `Shift`+`Up` to increment by `10`.</span></span>  
*   <span data-ttu-id="758f0-244">`Shift` + `Page Up` \(Windows、Linux\) または `Shift` + `Command` + `Up` \(macOS\) を選択して値をインクリメントします `100` 。</span><span class="sxs-lookup"><span data-stu-id="758f0-244">Select `Shift`+`Page Up` \(Windows, Linux\) or `Shift`+`Command`+`Up` \(macOS\) to increment the value by `100`.</span></span>  

<span data-ttu-id="758f0-245">デクレメントも機能します。</span><span class="sxs-lookup"><span data-stu-id="758f0-245">Decrementing also works.</span></span>  <span data-ttu-id="758f0-246">上記の各インスタンスを `Up` . `Down`</span><span class="sxs-lookup"><span data-stu-id="758f0-246">Just replace each instance of `Up` mentioned above with `Down`.</span></span>  

### <a name="add-a-class-to-an-element"></a><span data-ttu-id="758f0-247">要素にクラスを追加する</span><span class="sxs-lookup"><span data-stu-id="758f0-247">Add a class to an element</span></span>  

<span data-ttu-id="758f0-248">要素にクラスを追加するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="758f0-248">Complete the following actions to add a class to an element.</span></span>  

1.  <span data-ttu-id="758f0-249">[DOM ツリーで要素](#choose-an-element)**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="758f0-249">[Select the element](#choose-an-element) in the **DOM Tree**.</span></span>  
1.  <span data-ttu-id="758f0-250">**[.cls] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="758f0-250">Choose **.cls**.</span></span>  
1.  <span data-ttu-id="758f0-251">[新しいクラスの追加] テキスト ボックスにクラス **の名前を** 入力します。</span><span class="sxs-lookup"><span data-stu-id="758f0-251">Enter the name of the class in the **Add New Class** text box.</span></span>  
1.  <span data-ttu-id="758f0-252">`Enter` を選択します。</span><span class="sxs-lookup"><span data-stu-id="758f0-252">Select `Enter`.</span></span>  

:::image type="complex" source="../media/css-elements-styles-filter-classes.msft.png" alt-text="[要素クラス] ウィンドウ" lightbox="../media/css-elements-styles-filter-classes.msft.png":::
   <span data-ttu-id="758f0-254">[ **要素クラス]** ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="758f0-254">The **Element Classes** pane</span></span>  
:::image-end:::  

### <a name="toggle-a-class"></a><span data-ttu-id="758f0-255">クラスを切り替える</span><span class="sxs-lookup"><span data-stu-id="758f0-255">Toggle a class</span></span>  

<span data-ttu-id="758f0-256">次のアクションを実行して、要素のクラスを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="758f0-256">Complete the following actions to enable or disable a class on an element.</span></span>  

1.  <span data-ttu-id="758f0-257">[DOM ツリーで要素](#choose-an-element)**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="758f0-257">[Select the element](#choose-an-element) in the **DOM Tree**.</span></span>  
1.  <span data-ttu-id="758f0-258">[要素クラス **] ウィンドウを開** きます。</span><span class="sxs-lookup"><span data-stu-id="758f0-258">Open the **Element Classes** pane.</span></span>  <span data-ttu-id="758f0-259">[要素に [クラスを追加する] に移動します](#add-a-class-to-an-element)。</span><span class="sxs-lookup"><span data-stu-id="758f0-259">Navigate to [Add a class to an element](#add-a-class-to-an-element).</span></span>  <span data-ttu-id="758f0-260">[新しい **クラスの追加]** テキスト ボックスの下には、特定の要素に適用されるクラスすべてが表示されます。</span><span class="sxs-lookup"><span data-stu-id="758f0-260">Below the **Add New Class** text box are all of the classes applied to the specific element.</span></span>  
1.  <span data-ttu-id="758f0-261">オンまたはオフにするクラスの横にあるチェック ボックスをオンまたはオフに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="758f0-261">Toggle the checkbox next to the class that you want to turn on or off.</span></span>  

### <a name="add-a-style-rule"></a><span data-ttu-id="758f0-262">スタイル ルールの追加</span><span class="sxs-lookup"><span data-stu-id="758f0-262">Add a style rule</span></span>  

<span data-ttu-id="758f0-263">新しいスタイル ルールを追加するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="758f0-263">Complete the following actions to add a new style rule.</span></span>  

1.  <span data-ttu-id="758f0-264">[要素を選択します](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="758f0-264">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="758f0-265">[ **新しいスタイル ルール** \( ![ 新しいスタイル ルール ](../media/new-style-rule-icon.msft.png) \] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="758f0-265">Choose **New Style Rule** \(![New Style Rule](../media/new-style-rule-icon.msft.png)\).</span></span>  <span data-ttu-id="758f0-266">DevTools は、element.style ルールの下に新 **しいルールを挿入** します。</span><span class="sxs-lookup"><span data-stu-id="758f0-266">DevTools inserts a new rule beneath the **element.style** rule.</span></span>  

> [!NOTE]
> <span data-ttu-id="758f0-267">次の図では、[新しいスタイル ルール] を選択した後に、 `h1.devsite-page-title` スタイル ルール **が追加されます**。</span><span class="sxs-lookup"><span data-stu-id="758f0-267">In the following figure, DevTools adds the `h1.devsite-page-title` style rule after you choose **New Style Rule**.</span></span>  

:::image type="complex" source="../media/css-elements-styles-style-new.msft.png" alt-text="新しいスタイル ルールを追加する" lightbox="../media/css-elements-styles-style-new.msft.png":::
   <span data-ttu-id="758f0-269">新しいスタイル ルールを追加する</span><span class="sxs-lookup"><span data-stu-id="758f0-269">Add a new style rule</span></span>  
:::image-end:::  

#### <a name="choose-which-stylesheet-to-add-a-rule-to"></a><span data-ttu-id="758f0-270">ルールを追加するスタイルシートを選択する</span><span class="sxs-lookup"><span data-stu-id="758f0-270">Choose which stylesheet to add a rule to</span></span>  

<span data-ttu-id="758f0-271">新 [しいスタイル ルールを追加する場合](#add-a-style-rule)は、新しいスタイル ルール \( New Style **Rule** \) を選択して保持し、スタイル ルールを追加するスタイルシート ![ ](../media/new-style-rule-icon.msft.png) を選択します。</span><span class="sxs-lookup"><span data-stu-id="758f0-271">When [adding a new style rule](#add-a-style-rule), choose and hold **New Style Rule** \(![New Style Rule](../media/new-style-rule-icon.msft.png)\) to choose which stylesheet to add the style rule to.</span></span>  

:::image type="complex" source="../media/css-elements-styles-style-new-select-existing.msft.png" alt-text="スタイルシートを選択する" lightbox="../media/css-elements-styles-style-new-select-existing.msft.png":::
   <span data-ttu-id="758f0-273">スタイルシートを選択する</span><span class="sxs-lookup"><span data-stu-id="758f0-273">Choose a stylesheet</span></span>  
:::image-end:::  

#### <a name="add-a-style-rule-to-a-specific-location"></a><span data-ttu-id="758f0-274">特定の場所にスタイル ルールを追加する</span><span class="sxs-lookup"><span data-stu-id="758f0-274">Add a style rule to a specific location</span></span>  

<span data-ttu-id="758f0-275">[スタイル] パネルの特定の場所にスタイル ルールを追加するには、次のアクション **を実行** します。</span><span class="sxs-lookup"><span data-stu-id="758f0-275">Complete the following actions to add a style rule to a specific location in the **Styles** panel.</span></span>  

1.  <span data-ttu-id="758f0-276">新しいスタイル ルールを追加するスタイル ルールの上にマウス ポインターを移動します。</span><span class="sxs-lookup"><span data-stu-id="758f0-276">Hover on the style rule that is directly above where you want to add your new style rule.</span></span>  
1.  <span data-ttu-id="758f0-277">[[その他の **操作] ツールバーを表示** します](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="758f0-277">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="758f0-278">[下 **にスタイル ルールを挿入]** を選択します。\( [スタイル ルール ![ の下に挿入] アイコン ](../media/new-style-rule-icon.msft.png) \)。</span><span class="sxs-lookup"><span data-stu-id="758f0-278">Choose **Insert Style Rule Below** \(![Insert Style Rule Below icon](../media/new-style-rule-icon.msft.png)\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-insert-style-rule-below.msft.png" alt-text="下のスタイル ルールの挿入" lightbox="../media/css-elements-styles-insert-style-rule-below.msft.png":::
   **<span data-ttu-id="758f0-280">下のスタイル ルールの挿入</span><span class="sxs-lookup"><span data-stu-id="758f0-280">Insert Style Rule Below</span></span>**  
:::image-end:::  

### <a name="reveal-the-more-actions-toolbar"></a><span data-ttu-id="758f0-281">[その他の操作] ツールバーを表示する</span><span class="sxs-lookup"><span data-stu-id="758f0-281">Reveal the More Actions toolbar</span></span>  

<span data-ttu-id="758f0-282">[ **その他の操作]** ツールバーでは、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="758f0-282">The **More Actions** toolbar lets you perform the following actions.</span></span>  

*   <span data-ttu-id="758f0-283">フォーカスするスタイル ルールの直下にスタイル ルールを挿入します。</span><span class="sxs-lookup"><span data-stu-id="758f0-283">Insert a style rule directly below the one you are focused on.</span></span>  
*   <span data-ttu-id="758f0-284">フォーカスしている `background-color` スタイル ルールに 、または `color` `box-shadow` `text-shadow` 宣言を追加します。</span><span class="sxs-lookup"><span data-stu-id="758f0-284">Add a `background-color`, `color`, `box-shadow`, or `text-shadow` declaration to the style rule you are focused on.</span></span>  

<span data-ttu-id="758f0-285">次のアクションを実行して、[その他の操作] **ツールバーを表示** します。</span><span class="sxs-lookup"><span data-stu-id="758f0-285">Complete the following actions to reveal the **More Actions** toolbar.</span></span>  

1.  <span data-ttu-id="758f0-286">[スタイル **] パネル** で、スタイル ルールをポイントします。</span><span class="sxs-lookup"><span data-stu-id="758f0-286">In the **Styles** panel, hover on a style rule.</span></span>  <span data-ttu-id="758f0-287">**その他の** アクション \( \) は、スタイル ルール セクションの右下 `...` に表示されます。</span><span class="sxs-lookup"><span data-stu-id="758f0-287">**More Actions** \(`...`\) is revealed in the bottom-right of the style rule section.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="758f0-288">次の図では、スタイル ルールにカーソルを合わせると、[その他のアクション] が [スタイル ルール] セクションの右下 `.header-holder.has-default-focus` に表示されます。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="758f0-288">In the following figure, hover on the `.header-holder.has-default-focus` style rule and **More Actions** is revealed in the bottom-right of the style rule section.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-new-rule-styles.msft.png" alt-text="その他のアクションを表示する" lightbox="../media/css-elements-styles-new-rule-styles.msft.png":::
       <span data-ttu-id="758f0-290">他 **のアクションを表示** する \( `...` \)</span><span class="sxs-lookup"><span data-stu-id="758f0-290">Reveal **More Actions** \(`...`\)</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="758f0-291">上記のアクション **を表示するには** 、 `...` その他のアクション \( \) にカーソルを合わせる。</span><span class="sxs-lookup"><span data-stu-id="758f0-291">Hover on **More Actions** \(`...`\) to reveal the actions mentioned above.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="758f0-292">[ **スタイル ルールの下に挿入]** アクションは、[その他のアクション] にカーソルを合わせると **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="758f0-292">The **Insert Style Rule Below** action is revealed after hovering over **More Actions**.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png" alt-text="[その他の操作] ツールバー" lightbox="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png":::
       <span data-ttu-id="758f0-294">[ **その他の操作]** ツールバー</span><span class="sxs-lookup"><span data-stu-id="758f0-294">The **More Actions** toolbar</span></span>  
    :::image-end:::  
    
### <a name="toggle-a-declaration"></a><span data-ttu-id="758f0-295">宣言を切り替える</span><span class="sxs-lookup"><span data-stu-id="758f0-295">Toggle a declaration</span></span>  

<span data-ttu-id="758f0-296">folllwoing アクションを完了して、\(または off\) の 1 つの宣言を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="758f0-296">Complete the folllwoing actions to toggle a single declaration on \(or off\).</span></span>  

1.  <span data-ttu-id="758f0-297">[要素を選択します](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="758f0-297">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="758f0-298">[スタイル **] ウィンドウ** で、宣言を定義するルールをポイントします。</span><span class="sxs-lookup"><span data-stu-id="758f0-298">In the **Styles** pane, hover on the rule that defines the declaration.</span></span>  <span data-ttu-id="758f0-299">各宣言の横にチェック ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="758f0-299">A checkbox appears next to each declaration.</span></span>  
1.  <span data-ttu-id="758f0-300">宣言の横にあるチェックボックスを \(または uncheck\) にチェックします。</span><span class="sxs-lookup"><span data-stu-id="758f0-300">Check \(or uncheck\) the checkbox next to the declaration.</span></span>  <span data-ttu-id="758f0-301">宣言のチェックを外した場合、DevTools は宣言をクロスアウトして、アクティブでなくなったと示します。</span><span class="sxs-lookup"><span data-stu-id="758f0-301">When you uncheck a declaration, DevTools crosses it out to indicate that it is no longer active.</span></span>  

> [!NOTE]
> <span data-ttu-id="758f0-302">次の図では、現在 `margin-top` 選択されている要素のプロパティがオフに切り替えされています。</span><span class="sxs-lookup"><span data-stu-id="758f0-302">In the following figure, the `margin-top` property for the currently selected element has been toggled off.</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-deactivated.msft.png" alt-text="宣言を切り替える" lightbox="../media/css-elements-styles-rule-deactivated.msft.png":::
   <span data-ttu-id="758f0-304">宣言を切り替える</span><span class="sxs-lookup"><span data-stu-id="758f0-304">Toggle a declaration</span></span>  
:::image-end:::  

### <a name="add-a-background-color-declaration"></a><span data-ttu-id="758f0-305">背景色の宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="758f0-305">Add a background-color declaration</span></span>  

<span data-ttu-id="758f0-306">要素に宣言を追加するには、次 `background-color` のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="758f0-306">Complete the following actions to add a `background-color` declaration to an element.</span></span>  

1.  <span data-ttu-id="758f0-307">宣言を追加するスタイル ルールにカーソルを `background-color` 合わせる。</span><span class="sxs-lookup"><span data-stu-id="758f0-307">Hover on the style rule that you want to add the `background-color` declaration to.</span></span>  
1.  <span data-ttu-id="758f0-308">[[その他の **操作] ツールバーを表示** します](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="758f0-308">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="758f0-309">[ **背景色の追加** ]\( ![ [背景色の追加] アイコン ](../media/add-background-color-icon.msft.png) \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="758f0-309">Choose **Add Background Color** \(![Add Background Color icon](../media/add-background-color-icon.msft.png)\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-background-color.msft.png" alt-text="背景色の追加" lightbox="../media/css-elements-styles-rule-add-background-color.msft.png":::
   **<span data-ttu-id="758f0-311">背景色の追加</span><span class="sxs-lookup"><span data-stu-id="758f0-311">Add Background Color</span></span>**  
:::image-end:::  

### <a name="add-a-color-declaration"></a><span data-ttu-id="758f0-312">色の宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="758f0-312">Add a color declaration</span></span>  

<span data-ttu-id="758f0-313">要素に宣言を追加するには、次 `color` のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="758f0-313">Complete the following actions to add a `color` declaration to an element.</span></span>  

1.  <span data-ttu-id="758f0-314">宣言を追加するスタイル ルールにカーソルを `color` 合わせる。</span><span class="sxs-lookup"><span data-stu-id="758f0-314">Hover on the style rule that you want to add the `color` declaration to.</span></span>  
1.  <span data-ttu-id="758f0-315">[[その他の **操作] ツールバーを表示** します](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="758f0-315">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="758f0-316">[ **色の追加** ] \( ![ [色の追加] ](../media/add-color-icon.msft.png) アイコン \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="758f0-316">Choose **Add Color** \(![Add Color icon](../media/add-color-icon.msft.png)\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-color.msft.png" alt-text="色の追加" lightbox="../media/css-elements-styles-rule-add-color.msft.png":::
   **<span data-ttu-id="758f0-318">色の追加</span><span class="sxs-lookup"><span data-stu-id="758f0-318">Add Color</span></span>**  
:::image-end:::  

### <a name="add-a-box-shadow-declaration"></a><span data-ttu-id="758f0-319">ボックス シャドウ宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="758f0-319">Add a box-shadow declaration</span></span>  

<span data-ttu-id="758f0-320">要素に宣言を追加するには、次 `box-shadow` のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="758f0-320">Complete the follwoing actions to add a `box-shadow` declaration to an element.</span></span>  

1.  <span data-ttu-id="758f0-321">宣言を追加するスタイル ルールにカーソルを `box-shadow` 合わせる。</span><span class="sxs-lookup"><span data-stu-id="758f0-321">Hover on the style rule that you want to add the `box-shadow` declaration to.</span></span>  
1.  <span data-ttu-id="758f0-322">[[その他の **操作] ツールバーを表示** します](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="758f0-322">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="758f0-323">[Add **Box Shadow** \( ![ Add Box Shadow icon ](../media/add-box-shadow-icon.msft.png) \] )を選択します。</span><span class="sxs-lookup"><span data-stu-id="758f0-323">Choose **Add Box Shadow** \(![Add Box Shadow icon](../media/add-box-shadow-icon.msft.png)\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-box-shadow.msft.png" alt-text="ボックス シャドウの追加" lightbox="../media/css-elements-styles-rule-add-box-shadow.msft.png":::
   **<span data-ttu-id="758f0-325">ボックス シャドウの追加</span><span class="sxs-lookup"><span data-stu-id="758f0-325">Add Box Shadow</span></span>**  
:::image-end:::  

### <a name="add-a-text-shadow-declaration"></a><span data-ttu-id="758f0-326">テキスト シャドウ宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="758f0-326">Add a text-shadow declaration</span></span>  

<span data-ttu-id="758f0-327">要素に宣言を追加するには、次 `text-shadow` のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="758f0-327">Complete the following actions to add a `text-shadow` declaration to an element.</span></span>  

1.  <span data-ttu-id="758f0-328">宣言を追加するスタイル ルールにカーソルを `text-shadow` 合わせる。</span><span class="sxs-lookup"><span data-stu-id="758f0-328">Hover on the style rule that you want to add the `text-shadow` declaration to.</span></span>  
1.  <span data-ttu-id="758f0-329">[[その他の **操作] ツールバーを表示** します](#reveal-the-more-actions-toolbar)。</span><span class="sxs-lookup"><span data-stu-id="758f0-329">[Reveal the **More Actions** toolbar](#reveal-the-more-actions-toolbar).</span></span>  
1.  <span data-ttu-id="758f0-330">[テキスト **シャドウの追加** ]\( ![ [テキスト シャドウの追加] アイコン ](../media/add-text-shadow-icon.msft.png) \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="758f0-330">Choose **Add Text Shadow** \(![Add Text Shadow icon](../media/add-text-shadow-icon.msft.png)\).</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-add-text-shadow.msft.png" alt-text="テキスト シャドウの追加" lightbox="../media/css-elements-styles-rule-add-text-shadow.msft.png":::
   **<span data-ttu-id="758f0-332">テキスト シャドウの追加</span><span class="sxs-lookup"><span data-stu-id="758f0-332">Add Text Shadow</span></span>**  
:::image-end:::  

### <a name="change-colors-with-the-color-picker"></a><span data-ttu-id="758f0-333">カラー ピッカーを使用して色を変更する</span><span class="sxs-lookup"><span data-stu-id="758f0-333">Change colors with the Color Picker</span></span>  

<span data-ttu-id="758f0-334">Color **Picker は** 、変更と宣言のための GUI `color` `background-color` を提供します。</span><span class="sxs-lookup"><span data-stu-id="758f0-334">The **Color Picker** provides a GUI for changing `color` and `background-color` declarations.</span></span>  

<span data-ttu-id="758f0-335">次のアクションを実行して、カラー ピッカー **を開きます**。</span><span class="sxs-lookup"><span data-stu-id="758f0-335">Complete the following actions to open the **Color Picker**.</span></span>  

1.  <span data-ttu-id="758f0-336">[要素を選択します](#choose-an-element)。</span><span class="sxs-lookup"><span data-stu-id="758f0-336">[Select an element](#choose-an-element).</span></span>  
1.  <span data-ttu-id="758f0-337">[スタイル **] パネル** で、変更する `color` 、 `background-color` 、または類似の宣言を探します。</span><span class="sxs-lookup"><span data-stu-id="758f0-337">In the **Styles** panel, find the `color`, `background-color`, or similar declaration that you want to change.</span></span>  <span data-ttu-id="758f0-338">、 、または類似の値の左側には、色のプレビューである小さな `color` `background-color` 四角形があります。</span><span class="sxs-lookup"><span data-stu-id="758f0-338">To the left of the `color`, `background-color`, or similar value, there is a small square which is a preview of the color.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="758f0-339">次の図では、左側の小さい四角形 `rgba(0, 0, 0, 0.7)` は、その色のプレビューです。</span><span class="sxs-lookup"><span data-stu-id="758f0-339">In the following figure, the small square to the left of `rgba(0, 0, 0, 0.7)` is a preview of that color.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-rule-overlay-color-box.msft.png" alt-text="色のプレビュー" lightbox="../media/css-elements-styles-rule-overlay-color-box.msft.png":::
       <span data-ttu-id="758f0-341">色のプレビュー</span><span class="sxs-lookup"><span data-stu-id="758f0-341">Color preview</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="758f0-342">プレビューを選択してカラー ピッカー **を開きます**。</span><span class="sxs-lookup"><span data-stu-id="758f0-342">Choose the preview to open the **Color Picker**.</span></span>  
    
    :::image type="complex" source="../media/css-elements-styles-rule-color-picker.msft.png" alt-text="カラー ピッカー" lightbox="../media/css-elements-styles-rule-color-picker.msft.png":::
       <span data-ttu-id="758f0-344">カラー **ピッカー**</span><span class="sxs-lookup"><span data-stu-id="758f0-344">The **Color Picker**</span></span>  
    :::image-end:::  
    
<span data-ttu-id="758f0-345">カラー ピッカーの各 UI 要素の次の図と一覧の **descries を示します**。</span><span class="sxs-lookup"><span data-stu-id="758f0-345">The following figure and list descries of each of the UI elements of the **Color Picker**.</span></span>  

:::image type="complex" source="../media/css-elements-styles-rule-color-picker-annotated.msft.png" alt-text="注釈付きカラー ピッカー" lightbox="../media/css-elements-styles-rule-color-picker-annotated.msft.png":::
   <span data-ttu-id="758f0-347">[ **カラー ピッカー]**(注釈付き)</span><span class="sxs-lookup"><span data-stu-id="758f0-347">The **Color Picker**, annotated</span></span>  
:::image-end:::  

:::row:::
   :::column span="1":::
      <span data-ttu-id="758f0-348">1</span><span class="sxs-lookup"><span data-stu-id="758f0-348">1</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="758f0-349">網掛け</span><span class="sxs-lookup"><span data-stu-id="758f0-349">Shades</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="758f0-350">2</span><span class="sxs-lookup"><span data-stu-id="758f0-350">2</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="758f0-351">スポイト</span><span class="sxs-lookup"><span data-stu-id="758f0-351">Eyedropper</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="758f0-352">詳細については、[スポイトを使用してページから色をサンプリング [する] に移動します](#sample-a-color-off-the-page-with-the-eyedropper)。</span><span class="sxs-lookup"><span data-stu-id="758f0-352">For more information, navigate to [Sample a color off the page with the Eyedropper](#sample-a-color-off-the-page-with-the-eyedropper).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="758f0-353">3</span><span class="sxs-lookup"><span data-stu-id="758f0-353">3</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="758f0-354">クリップボードにコピー</span><span class="sxs-lookup"><span data-stu-id="758f0-354">Copy To Clipboard</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="758f0-355">表示値 **をクリップボード** にコピーします。</span><span class="sxs-lookup"><span data-stu-id="758f0-355">Copy the **Display Value** to your clipboard.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="758f0-356">4</span><span class="sxs-lookup"><span data-stu-id="758f0-356">4</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="758f0-357">表示値</span><span class="sxs-lookup"><span data-stu-id="758f0-357">Display Value</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="758f0-358">色の RGBA、HSLA、または 16 進表記。</span><span class="sxs-lookup"><span data-stu-id="758f0-358">The RGBA, HSLA, or Hex representation of the color.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="758f0-359">5</span><span class="sxs-lookup"><span data-stu-id="758f0-359">5</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="758f0-360">カラー パレット</span><span class="sxs-lookup"><span data-stu-id="758f0-360">Color Palette</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="758f0-361">1 つの四角形を選択して、その四角形に色を変更します。</span><span class="sxs-lookup"><span data-stu-id="758f0-361">Choose one of the squares to change the color to that square.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="758f0-362">6</span><span class="sxs-lookup"><span data-stu-id="758f0-362">6</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="758f0-363">Hue</span><span class="sxs-lookup"><span data-stu-id="758f0-363">Hue</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="758f0-364">7</span><span class="sxs-lookup"><span data-stu-id="758f0-364">7</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="758f0-365">Opacity</span><span class="sxs-lookup"><span data-stu-id="758f0-365">Opacity</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="758f0-366">8</span><span class="sxs-lookup"><span data-stu-id="758f0-366">8</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="758f0-367">値切り替え機能の表示</span><span class="sxs-lookup"><span data-stu-id="758f0-367">Display Value Switcher</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="758f0-368">現在の色の RGBA、HSLA、および 16 進表記を切り替える。</span><span class="sxs-lookup"><span data-stu-id="758f0-368">Toggle between the RGBA, HSLA, and Hex representations of the current color.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="758f0-369">9</span><span class="sxs-lookup"><span data-stu-id="758f0-369">9</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="758f0-370">カラー パレット スイッチラー</span><span class="sxs-lookup"><span data-stu-id="758f0-370">Color Palette Switcher</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="758f0-371">マテリアル デザイン パレット [、カスタム パレット][MaterialDesignColorSystem]、またはページカラー パレットを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="758f0-371">Toggle between the [Material Design palette][MaterialDesignColorSystem], a custom palette, or a page colors palette.</span></span>  <span data-ttu-id="758f0-372">DevTools は、スタイルシートで見つけた色に基づいてページ カラー パレットを生成します。</span><span class="sxs-lookup"><span data-stu-id="758f0-372">DevTools generates the page color palette based on the colors that it finds in your stylesheets.</span></span>  
   :::column-end:::
:::row-end:::  

#### <a name="sample-a-color-off-the-page-with-the-eyedropper"></a><span data-ttu-id="758f0-373">スポイトを使用してページ外の色をサンプリングする</span><span class="sxs-lookup"><span data-stu-id="758f0-373">Sample a color off the page with the Eyedropper</span></span>  

<span data-ttu-id="758f0-374">カラー ピッカー **を開く場合**、 **既定では** [スポイト]\( ![ ](../media/eyedropper-icon.msft.png) Eyedropper \) がオンになっています。</span><span class="sxs-lookup"><span data-stu-id="758f0-374">When you open the **Color Picker**, the **Eyedropper** \(![Eyedropper](../media/eyedropper-icon.msft.png)\) is on by default.</span></span>  <span data-ttu-id="758f0-375">次のアクションを実行して、選択した色をページの他の色に変更します。</span><span class="sxs-lookup"><span data-stu-id="758f0-375">Complete the following actions to change the selected color to some other color on the page.</span></span>  

1.  <span data-ttu-id="758f0-376">ビューポートのターゲットの色にカーソルを合わせる。</span><span class="sxs-lookup"><span data-stu-id="758f0-376">Hover on the target color in the viewport.</span></span>  
1.  <span data-ttu-id="758f0-377">確認を選択します。</span><span class="sxs-lookup"><span data-stu-id="758f0-377">Choose to confirm.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="758f0-378">次の図では、 **カラー ピッカーは** 現在の色の値を示しています `rgba(0,0,0,0.7)` 。これは黒に近い値です。</span><span class="sxs-lookup"><span data-stu-id="758f0-378">In the following figure, the **Color Picker** shows a current color value of `rgba(0,0,0,0.7)`, which is close to black.</span></span>  <span data-ttu-id="758f0-379">特定の色は、選択後にビューポートで現在強調表示されている黒のバージョンに変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="758f0-379">The specific color should change to the version of black that is currently highlighted in the viewport after you chose it.</span></span>  
    
    :::image type="complex" source="../media/css-color-picker-eye-dropper.msft.png" alt-text="スポイトの使用" lightbox="../media/css-color-picker-eye-dropper.msft.png":::
       <span data-ttu-id="758f0-381">スポイトの使用</span><span class="sxs-lookup"><span data-stu-id="758f0-381">Using the Eyedropper</span></span>  
    :::image-end:::  
    
<!--todo:  add the section on the Angle clock section for What's New 88.  -->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="758f0-382">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="758f0-382">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "[DevTools コマンド メニュー] Microsoft Edgeを使用してコマンドを実行|Microsoft Docs"  
[DevToolsCSSGetStarted]: ../css/index.md "はじめにCSS の表示と変更を使用|Microsoft Docs"  
[DevToolsCSSGetStartedAddPseudoState]: ../css/index.md#add-a-pseudostate-to-a-class "クラスに擬似状態を追加する - CSS はじめにを表示して変更する|Microsoft Docs"  
[DevToolsCSSGetStartedTutorial]: ../css/index.md#view-the-css-for-an-element "要素の CSS を表示する - CSS はじめにを表示して変更|Microsoft Docs"  
[DevToolsCssPrintPreview]: ../css/print-preview.md "DevTools Microsoft Edge印刷プレビュー モード (CSS 印刷メディアの種類) を強制的に|Microsoft Docs"  
[DevToolsJavascriptReferenceFormat]: ../javascript/reference.md#reformat-a-minified-javascript-file-with-pretty-print "ミニマ化された JavaScript ファイルをプリティプリントで再フォーマットする - デバッガー ファイルを使用|Microsoft Docs"  

[MaterialDesignColorSystem]: https://material.io/guidelines/style/color.html#color-color-palette "カラー システム - マテリアル デザイン"  
[MDNBoxModel]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Box_model "ボックス モデルの|MDN"  
[MDNSelectorTypes]: https://developer.mozilla.org/docs/Web/CSS/Specificity#Selector_Types "セレクターの種類 - 固有|MDN"  

> [!NOTE]
> <span data-ttu-id="758f0-392">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="758f0-392">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="758f0-393">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/css/reference) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="758f0-393">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="758f0-395">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="758f0-395">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  