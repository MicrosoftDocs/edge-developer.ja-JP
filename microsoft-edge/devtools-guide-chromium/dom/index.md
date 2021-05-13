---
description: ノードの表示、ノードの検索、ノードの編集、コンソール内の参照ノードの表示方法、ノードの変更点の割り当てなど。
title: DOM の表示と変更の開始
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 66078844730ebb22664c9ce89517511d7eb99ee7
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564288"
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
# <a name="get-started-with-viewing-and-changing-the-dom"></a><span data-ttu-id="c6fda-104">DOM の表示と変更の開始</span><span class="sxs-lookup"><span data-stu-id="c6fda-104">Get started with viewing and changing the DOM</span></span>  

<span data-ttu-id="c6fda-105">これらの対話型チュートリアルを完了して、DevTools を使用してページの DOM を表示および変更するMicrosoft Edgeします。</span><span class="sxs-lookup"><span data-stu-id="c6fda-105">Complete these interactive tutorials to learn the basics of viewing and changing the DOM of a page using Microsoft Edge DevTools.</span></span>  

<span data-ttu-id="c6fda-106">このチュートリアルでは、DOM と HTML の違いを知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6fda-106">This tutorial assumes that you know the difference between the DOM and HTML.</span></span>  <span data-ttu-id="c6fda-107">説明については [、「付録: HTML と DOM」](#appendix-html-versus-the-dom) に移動します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-107">Navigate to [Appendix: HTML versus the DOM](#appendix-html-versus-the-dom) for an explanation.</span></span>  

## <a name="open-dom-examples"></a><span data-ttu-id="c6fda-108">オープン DOM の例</span><span class="sxs-lookup"><span data-stu-id="c6fda-108">Open DOM examples</span></span>  

1.  <span data-ttu-id="c6fda-109">`Control`\(Windows、Linux\) または `Command` \(macOS\) を保持し **、[DOM の例**] を選択して新しいタブを開きます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-109">Hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and choose **DOM Examples** to open in a new tab.</span></span>  
    
    [<span data-ttu-id="c6fda-110">DOM の例</span><span class="sxs-lookup"><span data-stu-id="c6fda-110">DOM Examples</span></span>][GlitchDomExamples]  
    
## <a name="view-dom-nodes"></a><span data-ttu-id="c6fda-111">DOM ノードの表示</span><span class="sxs-lookup"><span data-stu-id="c6fda-111">View DOM nodes</span></span>  

<span data-ttu-id="c6fda-112">要素パネルの DOM ツリーは、DevTools で DOM 関連のすべてのアクティビティを実行する場所です。</span><span class="sxs-lookup"><span data-stu-id="c6fda-112">The DOM Tree of the Elements panel is where you do all DOM-related activities in DevTools.</span></span>  

### <a name="inspect-a-node"></a><span data-ttu-id="c6fda-113">ノードの検査</span><span class="sxs-lookup"><span data-stu-id="c6fda-113">Inspect a node</span></span>  

<span data-ttu-id="c6fda-114">特定の DOM ノードに興味がある場合 **、Inspect** は DevTools を開いてそのノードを調査する高速な方法です。</span><span class="sxs-lookup"><span data-stu-id="c6fda-114">When you are interested in a particular DOM node, **Inspect** is a fast way to open DevTools and investigate that node.</span></span>  

1.  <span data-ttu-id="c6fda-115">[DOM の例を開きます](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="c6fda-115">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="c6fda-116">[ **ノードの検査] で**、ミケランジェロを **右クリックし** 、[検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-116">Under **Inspect a Node**, right-choose **Michelangelo** and choose **Inspect**.</span></span>  
    
    :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png" alt-text="ノードの検査" lightbox="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png":::
       <span data-ttu-id="c6fda-118">ノードの検査</span><span class="sxs-lookup"><span data-stu-id="c6fda-118">Inspect a node</span></span>  
    :::image-end:::  
    
    1.  <span data-ttu-id="c6fda-119">**DevTools**の Elements ツールが開きます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-119">The **Elements** tool of DevTools opens.</span></span>  `<li>Michelangelo</li>` <span data-ttu-id="c6fda-120">は DOM ツリー で **強調表示されます**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-120">is highlighted in the **DOM Tree**.</span></span>  
        
        :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png" alt-text="ミケランジェロ ノードを強調表示する" lightbox="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png":::
           <span data-ttu-id="c6fda-122">ノードを強調表示 `Michelangelo` する</span><span class="sxs-lookup"><span data-stu-id="c6fda-122">Highlight the `Michelangelo` node</span></span>  
        :::image-end:::  
        
        1.  <span data-ttu-id="c6fda-123">DevTools **の** 左上隅にある ![ [検査 ](../media/inspect-icon.msft.png) \( Inspect \) ] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-123">Choose the **Inspect** \(![Inspect](../media/inspect-icon.msft.png)\) icon in the top-left corner of DevTools.</span></span>  
            
            :::image type="complex" source="../media/dom-elements-highlighted-select-element-page-inspect.msft.png" alt-text="[検査] アイコン" lightbox="../media/dom-elements-highlighted-select-element-page-inspect.msft.png":::
               <span data-ttu-id="c6fda-125">[ **検査]** アイコン</span><span class="sxs-lookup"><span data-stu-id="c6fda-125">The **Inspect** icon</span></span>  
            :::image-end:::  
            
1.  <span data-ttu-id="c6fda-126">[ **ノードの検査] で**、[東京] テキスト **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-126">Under **Inspect a Node**, choose the **Tokyo** text.</span></span>  <span data-ttu-id="c6fda-127">これで `<li>Tokyo</li>` 、DOM ツリーで強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-127">Now, `<li>Tokyo</li>` is highlighted in the DOM Tree.</span></span>  

<span data-ttu-id="c6fda-128">ノードの検査は、ノードのスタイルを表示および変更する最初の手順です。</span><span class="sxs-lookup"><span data-stu-id="c6fda-128">Inspecting a node is also the first step towards viewing and changing the styles of a node.</span></span>  <span data-ttu-id="c6fda-129">CSS の表示[とはじめにを使用して、ユーザー設定に移動します][DevToolsCssGetStarted]。</span><span class="sxs-lookup"><span data-stu-id="c6fda-129">Navigate to [Get Started With Viewing And Changing CSS][DevToolsCssGetStarted].</span></span>  

### <a name="navigate-the-dom-tree-with-a-keyboard"></a><span data-ttu-id="c6fda-130">キーボードを使用して DOM ツリーを移動する</span><span class="sxs-lookup"><span data-stu-id="c6fda-130">Navigate the DOM Tree with a keyboard</span></span>  

<span data-ttu-id="c6fda-131">DOM ツリーでノードを選択したら、キーボードで DOM ツリーを移動できます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-131">Once you have selected a node in the DOM Tree, you may navigate the DOM Tree with your keyboard.</span></span>  

1.  <span data-ttu-id="c6fda-132">[DOM の例を開きます](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="c6fda-132">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="c6fda-133">[ **キーボードを使用して DOM ツリーを移動する]** で **、[Ringo]** を右クリックし、[検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-133">Under **Navigate the DOM Tree with a Keyboard**, right-choose **Ringo** and choose **Inspect**.</span></span>  `<li>Ringo</li>` <span data-ttu-id="c6fda-134">が DOM ツリーで選択されています。</span><span class="sxs-lookup"><span data-stu-id="c6fda-134">is selected in the DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png" alt-text="Ringo ノードの検査" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png":::
       <span data-ttu-id="c6fda-136">ノードの `Ringo` 検査</span><span class="sxs-lookup"><span data-stu-id="c6fda-136">Inspect the `Ringo` node</span></span>  
    :::image-end:::  
    
    1.  <span data-ttu-id="c6fda-137">矢印キー `Up` を 2 回選択します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-137">Select the `Up` arrow key 2 times.</span></span>  `<ul>` <span data-ttu-id="c6fda-138"> がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-138">is selected.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png" alt-text="ul ノードの検査" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png":::
           <span data-ttu-id="c6fda-140">ノードの `ul` 検査</span><span class="sxs-lookup"><span data-stu-id="c6fda-140">Inspect the `ul` node</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="c6fda-141">矢印キー `Left` を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-141">Select the `Left` arrow key.</span></span>  <span data-ttu-id="c6fda-142">リスト `<ul>` が折りたたむ。</span><span class="sxs-lookup"><span data-stu-id="c6fda-142">The `<ul>` list collapses.</span></span>  
    1.  <span data-ttu-id="c6fda-143">矢印キーを `Left` 再度選択します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-143">Select the `Left` arrow key again.</span></span>  <span data-ttu-id="c6fda-144">ノードの親 `<ul>` が選択されています。</span><span class="sxs-lookup"><span data-stu-id="c6fda-144">The parent of the `<ul>` node is selected.</span></span>  <span data-ttu-id="c6fda-145">この例では、ID `<div>` を使用します `navigate-the-dom-tree-with-a-keyboard-1` 。</span><span class="sxs-lookup"><span data-stu-id="c6fda-145">In this case it is the `<div>` with the ID `navigate-the-dom-tree-with-a-keyboard-1`.</span></span>  
    1.  <span data-ttu-id="c6fda-146">矢印キーを 2 回選択して、折りたたむだけのリスト `Down` `<ul>` を再選択します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-146">Select the `Down` arrow key 2 times so that you have re-selected the `<ul>` list that you just collapsed.</span></span>  <span data-ttu-id="c6fda-147">次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c6fda-147">It should look like this:</span></span> `<ul>... </ul>`  
    1.  <span data-ttu-id="c6fda-148">矢印キー `Right` を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-148">Select the `Right` arrow key.</span></span>  <span data-ttu-id="c6fda-149">リストが展開されます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-149">The list expands.</span></span>  

### <a name="scroll-into-view"></a><span data-ttu-id="c6fda-150">ビューにスクロールする</span><span class="sxs-lookup"><span data-stu-id="c6fda-150">Scroll into view</span></span>  

<span data-ttu-id="c6fda-151">DOM ツリーを表示すると、現在ビューポートに表示されていない DOM ノードに興味を持つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="c6fda-151">When viewing the DOM Tree, you may find yourself interested in a DOM node that is not currently in the viewport.</span></span>  <span data-ttu-id="c6fda-152">たとえば、ページの下部までスクロールし、ページの上部にあるノードに興味を `<h1>` 持ったとします。</span><span class="sxs-lookup"><span data-stu-id="c6fda-152">For example, suppose that you scrolled to the bottom of the page, and you are interested in the `<h1>` node at the top of the page.</span></span>  <span data-ttu-id="c6fda-153">**ビューにスクロールすると** 、ビューポートの位置をすばやく変更して、ノードを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-153">**Scroll into view** lets you quickly reposition the viewport so that you are able to review the node.</span></span>  

1.  <span data-ttu-id="c6fda-154">[DOM の例を開きます](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="c6fda-154">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="c6fda-155">[ **表示にスクロール] で**、[Magritte] を **右クリックし、[** 検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-155">Under **Scroll into View**, right-choose **Magritte** and choose **Inspect**.</span></span>  
1.  <span data-ttu-id="c6fda-156">[DOM の例] ページの下部までスクロールします。</span><span class="sxs-lookup"><span data-stu-id="c6fda-156">Scroll to the bottom of the DOM Examples page.</span></span>  
1.  <span data-ttu-id="c6fda-157">ノード `<li>Magritte</li>` は DOM ツリーで選択されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6fda-157">The `<li>Magritte</li>` node should still be selected in your DOM Tree.</span></span>  <span data-ttu-id="c6fda-158">表示されていない場合は、[スクロールして表示 [] に戻り、](#scroll-into-view) 最初から開始します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-158">If not, go back to [Scroll into view](#scroll-into-view) and start over.</span></span>  
1.  <span data-ttu-id="c6fda-159">ノードにマウス `<li>Magritte</li>` ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[表示にスクロール] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-159">Hover on the `<li>Magritte</li>` node, open the contextual menu \(right-click\), and choose **Scroll into view**.</span></span>  <span data-ttu-id="c6fda-160">ビューポートがスクロールして **、Magritte ノードを確認** できます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-160">Your viewport scrolls back up so that you may review the **Magritte** node.</span></span>  <span data-ttu-id="c6fda-161">[付録 [: 表示にスクロール] オプション](#appendix-missing-options) を確認できない場合は、不足 **しているオプションに移動** します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-161">Navigate to [Appendix: Missing options](#appendix-missing-options) if you are not able to review the **Scroll into view** option.</span></span>
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="ビューにスクロールする" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       **<span data-ttu-id="c6fda-163">ビューにスクロールする</span><span class="sxs-lookup"><span data-stu-id="c6fda-163">Scroll into view</span></span>**  
    :::image-end:::  

### <a name="search-for-nodes"></a><span data-ttu-id="c6fda-164">ノードの検索</span><span class="sxs-lookup"><span data-stu-id="c6fda-164">Search for nodes</span></span>  

<span data-ttu-id="c6fda-165">DOM ツリーは、文字列、CSS セレクター、または XPath セレクターで検索できます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-165">You may search the DOM Tree by string, CSS selector, or XPath selector.</span></span>  

1.  <span data-ttu-id="c6fda-166">[要素] ツールにカーソル **を移動** します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-166">Focus your cursor on the **Elements** tool.</span></span>  
1.  <span data-ttu-id="c6fda-167">`Control` + `F` \(Windows Linux\) または `Command` + `F` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-167">Select `Control`+`F` \(Windows, Linux\) or `Command`+`F` \(macOS\).</span></span>  <span data-ttu-id="c6fda-168">DOM ツリーの下部に検索バーが開きます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-168">The Search bar opens at the bottom of the DOM Tree.</span></span>  
1.  <span data-ttu-id="c6fda-169">「`The Moon is a Harsh Mistress`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-169">Type `The Moon is a Harsh Mistress`.</span></span>  <span data-ttu-id="c6fda-170">最後の文は DOM ツリーで強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-170">The last sentence is highlighted in the DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-search-nodes-highlight.msft.png" alt-text="検索バーでクエリを強調表示する" lightbox="../media/dom-elements-highlighted-search-nodes-highlight.msft.png":::
       <span data-ttu-id="c6fda-172">検索バーでクエリを強調表示する</span><span class="sxs-lookup"><span data-stu-id="c6fda-172">Highlight the query in the Search bar</span></span>  
    :::image-end:::  
    
<span data-ttu-id="c6fda-173">前述のように、検索バーは CSS および XPath セレクターもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c6fda-173">As mentioned above, the Search bar also supports CSS and XPath selectors.</span></span>  

## <a name="edit-the-dom"></a><span data-ttu-id="c6fda-174">DOM の編集</span><span class="sxs-lookup"><span data-stu-id="c6fda-174">Edit the DOM</span></span>  

<span data-ttu-id="c6fda-175">その場合は、DOM を編集し、変更がページに与える影響を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-175">You may edit the DOM on the fly and review how the changes affect the page.</span></span>  

### <a name="edit-content"></a><span data-ttu-id="c6fda-176">コンテンツの編集</span><span class="sxs-lookup"><span data-stu-id="c6fda-176">Edit content</span></span>  

<span data-ttu-id="c6fda-177">ノードのコンテンツを編集するには、DOM ツリー内のコンテンツをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6fda-177">To edit the content of a node, double-click the content in the DOM Tree.</span></span>  

1.  <span data-ttu-id="c6fda-178">[DOM の例を開きます](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="c6fda-178">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="c6fda-179">[コンテンツ **の編集] で**、ミシェルを **右クリックし** 、[検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-179">Under **Edit Content**, right-choose **Michelle** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="c6fda-180">DOM ツリーで、をダブルクリックします `Michelle` 。</span><span class="sxs-lookup"><span data-stu-id="c6fda-180">In the DOM Tree, double-click `Michelle`.</span></span>  <span data-ttu-id="c6fda-181">つまり、テキストの間をダブルクリックし、 `<li>` をクリックします `</li>` 。</span><span class="sxs-lookup"><span data-stu-id="c6fda-181">In other words, double-click the text between `<li>` and `</li>`.</span></span>  <span data-ttu-id="c6fda-182">テキストが強調表示され、選択されているテキストが示されます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-182">The text is highlighted to indicate that it is selected.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-content.msft.png" alt-text="テキストを編集する" lightbox="../media/dom-elements-highlighted-edit-content.msft.png":::
           <span data-ttu-id="c6fda-184">テキストを編集する</span><span class="sxs-lookup"><span data-stu-id="c6fda-184">Edit the text</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="c6fda-185">[削除 `Michelle` ] を `Leela` クリックし、次に選択 `Enter` して変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-185">Delete `Michelle`, type `Leela`, then select `Enter` to confirm the change.</span></span>  <span data-ttu-id="c6fda-186">DOM のテキストがミシェルから**Leela に\*\*\*\*変わります**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-186">The text in the DOM changes from **Michelle** to **Leela**.</span></span>  

### <a name="edit-attributes"></a><span data-ttu-id="c6fda-187">属性の編集</span><span class="sxs-lookup"><span data-stu-id="c6fda-187">Edit attributes</span></span>  

<span data-ttu-id="c6fda-188">属性を編集するには、属性名または値をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6fda-188">To edit attributes, double-click the attribute name or value.</span></span>  <span data-ttu-id="c6fda-189">指示に従って、ノードに属性を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-189">Follow the instructions to learn how to add attributes to a node.</span></span>  

1.  <span data-ttu-id="c6fda-190">[DOM の例を開きます](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="c6fda-190">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="c6fda-191">[属性 **の編集]** で **、[Howard] を右クリックし、[** 検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-191">Under **Edit Attributes**, right-choose **Howard** and choose **Inspect**.</span></span>  
1.  <span data-ttu-id="c6fda-192">ダブルクリック `<li>` します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-192">Double-click `<li>`.</span></span>  <span data-ttu-id="c6fda-193">テキストが強調表示され、ノードが選択されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-193">The text is highlighted to indicate that the node is selected.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png" alt-text="ノードの編集" lightbox="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png":::
       <span data-ttu-id="c6fda-195">ノードの編集</span><span class="sxs-lookup"><span data-stu-id="c6fda-195">Edit the node</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c6fda-196">矢印キー `Right` を選択し、スペースを追加し、型 `style="background-color:gold"` を入力して、を選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="c6fda-196">Select the `Right` arrow key, add a space, type `style="background-color:gold"`, and then select `Enter`.</span></span>  <span data-ttu-id="c6fda-197">ノードの背景色が金色に変わります。</span><span class="sxs-lookup"><span data-stu-id="c6fda-197">The background color of the node changes to gold.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png" alt-text="ノードに style 属性を追加する" lightbox="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png":::
       <span data-ttu-id="c6fda-199">ノードに `style` 属性を追加する</span><span class="sxs-lookup"><span data-stu-id="c6fda-199">Add a `style` attribute to the node</span></span>  
    :::image-end:::  
    
### <a name="edit-node-type"></a><span data-ttu-id="c6fda-200">ノードの種類の編集</span><span class="sxs-lookup"><span data-stu-id="c6fda-200">Edit node type</span></span>  

<span data-ttu-id="c6fda-201">ノードの種類を編集するには、その種類をダブルクリックし、新しい種類を入力します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-201">To edit the type of a node, double-click the type and then type in the new type.</span></span>  

1.  <span data-ttu-id="c6fda-202">[DOM の例を開きます](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="c6fda-202">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="c6fda-203">[ **ノードの種類の編集] で**、Hank を **右クリックし、[** 検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-203">Under **Edit Node Type**, right-choose **Hank** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="c6fda-204">ダブルクリック `<li>` します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-204">Double-click `<li>`.</span></span>  <span data-ttu-id="c6fda-205">テキストが `li` 強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-205">The text `li` is highlighted.</span></span>  
    1.  <span data-ttu-id="c6fda-206">[削除 `li` ] をクリック `button` し、[入力] を選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="c6fda-206">Delete `li`, type `button`, then select `Enter`.</span></span>  <span data-ttu-id="c6fda-207">ノード `<li>` がノードに変更 `<button>` されます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-207">The `<li>` node changes to a `<button>` node.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-node-type-button.msft.png" alt-text="ノードの種類をボタンに変更する" lightbox="../media/dom-elements-highlighted-edit-node-type-button.msft.png":::
           <span data-ttu-id="c6fda-209">ノードの種類をに変更する</span><span class="sxs-lookup"><span data-stu-id="c6fda-209">Change the node type to</span></span> `button`  
        :::image-end:::  
        
### <a name="reorder-dom-nodes"></a><span data-ttu-id="c6fda-210">DOM ノードの並べ替え</span><span class="sxs-lookup"><span data-stu-id="c6fda-210">Reorder DOM nodes</span></span>  

<span data-ttu-id="c6fda-211">ノードをドラッグして並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-211">Drag nodes to reorder them.</span></span>  

1.  <span data-ttu-id="c6fda-212">[DOM の例を開きます](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="c6fda-212">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="c6fda-213">[DOM **ノードの並べ替え**] で **、Elvis Presley を右クリックし、[** 検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-213">Under **Reorder DOM Nodes**, right-choose **Elvis Presley** and choose **Inspect**.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="c6fda-214">リスト内の最後のアイテムです。</span><span class="sxs-lookup"><span data-stu-id="c6fda-214">It is the last item in the list.</span></span>  
    
    1.  <span data-ttu-id="c6fda-215">DOM ツリーで、リスト `<li>Elvis Presley</li>` の一番上にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="c6fda-215">In the DOM Tree, drag `<li>Elvis Presley</li>` to the top of the list.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-reorder-dom-nodes.msft.png" alt-text="ノードをリストの一番上にドラッグする" lightbox="../media/dom-elements-reorder-dom-nodes.msft.png":::
           <span data-ttu-id="c6fda-217">ノードをリストの一番上にドラッグする</span><span class="sxs-lookup"><span data-stu-id="c6fda-217">Drag the node to the top of the list</span></span>  
        :::image-end:::  
        
### <a name="force-state"></a><span data-ttu-id="c6fda-218">強制状態</span><span class="sxs-lookup"><span data-stu-id="c6fda-218">Force state</span></span>  

<span data-ttu-id="c6fda-219">ノードを強制的に状態 (、 など) `:active` `:hover` `:focus` `:visited` に維持できます `:focus-within` 。</span><span class="sxs-lookup"><span data-stu-id="c6fda-219">You are able to force nodes to remain in states including `:active`, `:hover`, `:focus`, `:visited`, and `:focus-within`.</span></span>  

1.  <span data-ttu-id="c6fda-220">[DOM の例を開きます](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="c6fda-220">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="c6fda-221">[ **強制状態] で**、[ハエ **の主] にマウス ポインターを移動します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-221">Under **Force state**, hover on **The Lord of the Flies**.</span></span>  <span data-ttu-id="c6fda-222">背景色がオレンジ色になります。</span><span class="sxs-lookup"><span data-stu-id="c6fda-222">The background color becomes orange.</span></span>  
    1.  <span data-ttu-id="c6fda-223">[ハ **エの主] にマウス ポインターを置き**、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-223">Hover on **The Lord of the Flies**, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="c6fda-224">をポイント `<li class="demo--hover">The Lord of the Flies</li>` し、コンテキスト メニュー \(右クリック\) を開き、[**強制状態**:ホバー]  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-224">Hover on `<li class="demo--hover">The Lord of the Flies</li>`, open the contextual menu \(right-click\), and choose **Force State** > **:hover**.</span></span>  <span data-ttu-id="c6fda-225">オプションが [表示されない場合は](#appendix-missing-options) 、[付録: 不足しているオプション] に移動します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-225">Navigate to [Appendix: Missing options](#appendix-missing-options) if the option is not displayed.</span></span>  <span data-ttu-id="c6fda-226">実際にノードの上をホバーしていない場合でも、背景色はオレンジ色のままです。</span><span class="sxs-lookup"><span data-stu-id="c6fda-226">The background color remains orange even though you are not actually hovering over the node.</span></span>  

### <a name="hide-a-node"></a><span data-ttu-id="c6fda-227">ノードを非表示にする</span><span class="sxs-lookup"><span data-stu-id="c6fda-227">Hide a node</span></span>  

<span data-ttu-id="c6fda-228">ノード `H` を非表示にする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-228">Select `H` to hide a node.</span></span>  

1.  <span data-ttu-id="c6fda-229">[DOM の例を開きます](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="c6fda-229">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="c6fda-230">[ **ノードを非表示にする] で**、[星の移動先] **を右クリックし、[** 検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-230">Under **Hide a node**, right-choose **The Stars My Destination** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="c6fda-231">キーを選択 `H` します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-231">Select the `H` key.</span></span>  <span data-ttu-id="c6fda-232">ノードは非表示です。</span><span class="sxs-lookup"><span data-stu-id="c6fda-232">The node is hidden.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-hide-a-node.msft.png" alt-text="DOM ツリーが非表示にされた後のノードの外観" lightbox="../media/dom-elements-highlighted-hide-a-node.msft.png":::
           <span data-ttu-id="c6fda-234">DOM ツリーが非表示にされた後のノードの外観</span><span class="sxs-lookup"><span data-stu-id="c6fda-234">What the node looks like in the DOM Tree after it is hidden</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="c6fda-235">もう一度 `H` キーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-235">Select the `H` key again.</span></span>  <span data-ttu-id="c6fda-236">ノードが再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-236">The node is shown again.</span></span>  

### <a name="delete-a-node"></a><span data-ttu-id="c6fda-237">ノードの削除</span><span class="sxs-lookup"><span data-stu-id="c6fda-237">Delete a node</span></span>  

<span data-ttu-id="c6fda-238">ノード `Delete` を削除する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-238">Select `Delete` to delete a node.</span></span>  

1.  <span data-ttu-id="c6fda-239">[DOM の例を開きます](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="c6fda-239">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="c6fda-240">[ **ノードの削除] で、[Foundation]** を右クリック **し、[検査** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-240">Under **Delete a Node**, right-choose **Foundation** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="c6fda-241">キーを選択 `Delete` します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-241">Select the `Delete` key.</span></span>  <span data-ttu-id="c6fda-242">ノードが削除されます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-242">The node is deleted.</span></span>  
    1.  <span data-ttu-id="c6fda-243">`Control` + `Z` \(Windows Linux\) または `Command` + `Z` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-243">Select `Control`+`Z` \(Windows, Linux\) or `Command`+`Z` \(macOS\).</span></span>  <span data-ttu-id="c6fda-244">最後のアクションは元に戻され、ノードが再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-244">The last action is undone and the node reappears.</span></span>  

## <a name="access-nodes-in-the-console"></a><span data-ttu-id="c6fda-245">コンソールのノードにアクセスする</span><span class="sxs-lookup"><span data-stu-id="c6fda-245">Access nodes in the Console</span></span>  

<span data-ttu-id="c6fda-246">DevTools には、コンソールから DOM ノードにアクセスしたり、各ノードへの JavaScript 参照を取得したりするために、いくつかのショートカットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c6fda-246">DevTools provides a few shortcuts for accessing DOM nodes from the Console, or getting JavaScript references to each one.</span></span>  

### <a name="reference-the-currently-selected-node-with-0"></a><span data-ttu-id="c6fda-247">現在選択されているノードを $0 で参照する</span><span class="sxs-lookup"><span data-stu-id="c6fda-247">Reference the currently-selected node with $0</span></span>  

<span data-ttu-id="c6fda-248">ノードを検査する場合、ノードの横にあるテキストは、このノードを変数と一緒にコンソールで参照 `== $0` できる可能性を意味します `$0` 。</span><span class="sxs-lookup"><span data-stu-id="c6fda-248">When you inspect a node, the `== $0` text next to the node means that you may reference this node in the Console with the variable `$0`.</span></span>  

1.  <span data-ttu-id="c6fda-249">[DOM の例を開きます](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="c6fda-249">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="c6fda-250">[ **現在選択されているノードを $0**で参照する] で、[ダークネスの左手] を右クリックし、[ **検査]** を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-250">Under **Reference the currently-selected node with $0**, right-choose **The Left Hand of Darkness** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="c6fda-251">キーを `Escape` 選択してコンソール ドロワーを開きます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-251">Select the `Escape` key to open the Console Drawer.</span></span>  
    1.  <span data-ttu-id="c6fda-252">キー `$0` を入力して選択 `Enter` します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-252">Type `$0` and select the `Enter` key.</span></span>  <span data-ttu-id="c6fda-253">式の結果は、 に `$0` 評価されます `<li>The Left Hand of Darkness</li>` 。</span><span class="sxs-lookup"><span data-stu-id="c6fda-253">The result of the expression shows that `$0` evaluates to `<li>The Left Hand of Darkness</li>`.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png" alt-text="コンソールの最初の $0 式の結果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png":::
            <span data-ttu-id="c6fda-255">コンソールの最初の `$0` 式の **結果**</span><span class="sxs-lookup"><span data-stu-id="c6fda-255">The result of the first `$0` expression in the **Console**</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="c6fda-256">結果にカーソルを合わせる。</span><span class="sxs-lookup"><span data-stu-id="c6fda-256">Hover on the result.</span></span>  <span data-ttu-id="c6fda-257">ノードがビューポートで強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-257">The node is highlighted in the viewport.</span></span>  
    1.  <span data-ttu-id="c6fda-258">DOM `<li>Dune</li>` ツリーで選択し、もう一 `$0` 度コンソールを入力してから、もう一度選択 `Enter` します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-258">Choose `<li>Dune</li>` in the DOM Tree, type `$0` in the Console again, and then select `Enter` again.</span></span>  <span data-ttu-id="c6fda-259">次に `$0` 、に評価します `<li>Dune</li>` 。</span><span class="sxs-lookup"><span data-stu-id="c6fda-259">Now, `$0` evaluates to `<li>Dune</li>`.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png" alt-text="コンソールの 2 番目の $0 式の結果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png":::
           <span data-ttu-id="c6fda-261">コンソールの 2 番目 `$0` の式の **結果**</span><span class="sxs-lookup"><span data-stu-id="c6fda-261">The result of the second `$0` expression in the **Console**</span></span>  
        :::image-end:::  
        
### <a name="store-as-global-variable"></a><span data-ttu-id="c6fda-262">グローバル変数として格納する</span><span class="sxs-lookup"><span data-stu-id="c6fda-262">Store as global variable</span></span>  

<span data-ttu-id="c6fda-263">ノードを何度も参照する必要がある場合は、グローバル変数として格納します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-263">If you need to refer back to a node many times, store it as a global variable.</span></span>  

1.  <span data-ttu-id="c6fda-264">[DOM の例を開きます](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="c6fda-264">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="c6fda-265">[**グローバル変数として格納]** で\*\*\*\*、[ビッグ スリープ] をポイントし、コンテキスト メニュー \(右クリック\) を開き、[検査] を選択**します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-265">Under **Store as global variable**, hover on **The Big Sleep**, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="c6fda-266">DOM ツリー `<li>The Big Sleep</li>` でマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[グローバル変数として **保存] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-266">Hover on `<li>The Big Sleep</li>` in the DOM Tree, open the contextual menu \(right-click\), and choose **Store as global variable**.</span></span>  <span data-ttu-id="c6fda-267">オプションが [表示されない場合は](#appendix-missing-options) 、[付録: 不足しているオプション] に移動します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-267">Navigate to [Appendix: Missing options](#appendix-missing-options) if the option is not displayed.</span></span>  
    1.  <span data-ttu-id="c6fda-268">コンソール `temp1` に入力し、[] を選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="c6fda-268">Type `temp1` in the Console and then select `Enter`.</span></span>  <span data-ttu-id="c6fda-269">式の結果は、変数がノードに評価されます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-269">The result of the expression shows that the variable evaluates to the node.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png" alt-text="temp1 式の結果" lightbox="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png":::
           <span data-ttu-id="c6fda-271">式の `temp1` 結果</span><span class="sxs-lookup"><span data-stu-id="c6fda-271">The result of the `temp1` expression</span></span>  
        :::image-end:::  
        
### <a name="copy-js-path"></a><span data-ttu-id="c6fda-272">JS パスのコピー</span><span class="sxs-lookup"><span data-stu-id="c6fda-272">Copy JS path</span></span>  

<span data-ttu-id="c6fda-273">自動化されたテストで JavaScript パスを参照する必要がある場合は、ノードに JavaScript パスをコピーします。</span><span class="sxs-lookup"><span data-stu-id="c6fda-273">Copy the JavaScript path to a node when you need to reference it in an automated test.</span></span>  

1.  <span data-ttu-id="c6fda-274">[DOM の例を開きます](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="c6fda-274">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="c6fda-275">[JS **パスのコピー]** で、兄弟 **Karamazov**にマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-275">Under **Copy JS path**, hover on **The Brothers Karamazov**, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="c6fda-276">DOM ツリー `<li>The Brothers Karamazov</li>` でマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[コピー JS パス]\*\*\*\*  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-276">Hover on `<li>The Brothers Karamazov</li>` in the DOM Tree, open the contextual menu \(right-click\), and choose **Copy** > **Copy JS Path**.</span></span>  <span data-ttu-id="c6fda-277">ノード `document.querySelector()` に解決される式がクリップボードにコピーされています。</span><span class="sxs-lookup"><span data-stu-id="c6fda-277">A `document.querySelector()` expression that resolves to the node has been copied to your clipboard.</span></span>  
    1.  <span data-ttu-id="c6fda-278">`Control` + `V` \(Windows、Linux\) または \(macOS\) を選択して、式をコンソール `Command` + `V` に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-278">Select `Control`+`V` \(Windows, Linux\) or `Command`+`V` \(macOS\) to paste the expression into the Console.</span></span>  
    1.  <span data-ttu-id="c6fda-279">式 `Enter` を評価する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-279">Select `Enter` to evaluate the expression.</span></span>
        
        :::image type="complex" source="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png" alt-text="Copy JS Path 式の結果" lightbox="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png":::
           <span data-ttu-id="c6fda-281">Copy JS **Path** 式の結果</span><span class="sxs-lookup"><span data-stu-id="c6fda-281">The result of the **Copy JS Path** expression</span></span>  
        :::image-end:::  
        
## <a name="break-on-dom-changes"></a><span data-ttu-id="c6fda-282">DOM の変更に対するブレーク</span><span class="sxs-lookup"><span data-stu-id="c6fda-282">Break on DOM changes</span></span>  

<span data-ttu-id="c6fda-283">DevTools を使用すると、JavaScript が DOM を変更するときにページの JavaScript を一時停止できます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-283">DevTools enables you to pause the JavaScript of a page when the JavaScript modifies the DOM.</span></span>  

### <a name="break-on-attribute-modifications"></a><span data-ttu-id="c6fda-284">属性の変更時のブレーク</span><span class="sxs-lookup"><span data-stu-id="c6fda-284">Break on attribute modifications</span></span>  

<span data-ttu-id="c6fda-285">ノードの属性が変更される JavaScript を一時停止する場合は、属性変更ブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-285">Use attribute modification breakpoints when you want to pause the JavaScript that causes any attribute of a node to change.</span></span>  

1.  <span data-ttu-id="c6fda-286">[DOM の例を開きます](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="c6fda-286">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="c6fda-287">[ **属性の変更時にブレーク]** で **、Sauerkraut を右クリックし、[** 検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-287">Under **Break on attribute modifications**, right-choose **Sauerkraut** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="c6fda-288">DOM ツリーで、マウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[属性の変更時にブレーク `<li id="target">Sauerkraut</li>` **]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-288">In the DOM Tree, hover on `<li id="target">Sauerkraut</li>`, open the contextual menu \(right-click\), and choose **Break On** > **Attribute Modifications**.</span></span>  <span data-ttu-id="c6fda-289">オプションが [表示されない場合は](#appendix-missing-options) 、[付録: 不足しているオプション] に移動します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-289">Navigate to [Appendix: Missing options](#appendix-missing-options) if the option is not displayed.</span></span>
        
        :::image type="complex" source="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png" alt-text="属性の変更時のブレーク" lightbox="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png":::
           **<span data-ttu-id="c6fda-291">属性の変更時のブレーク</span><span class="sxs-lookup"><span data-stu-id="c6fda-291">Break on attribute modifications</span></span>**  
        :::image-end:::  
        
    1.  <span data-ttu-id="c6fda-292">次の手順では、ページのコードを一時停止するボタンを選択するように指示されます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-292">In the next step you are going to be instructed to choose a button that pauses the code of the page.</span></span>  <span data-ttu-id="c6fda-293">ページが一時停止すると、ページをスクロールできなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c6fda-293">After the page is paused you are no longer able to scroll the page.</span></span>  <span data-ttu-id="c6fda-294">ページを再 **びスクロール可能** にするには、[スクリプトの再開] ![ \( Resume Script ](../media/resume-script-icon.msft.png) \) を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6fda-294">You must choose **Resume Script** \(![Resume Script](../media/resume-script-icon.msft.png)\) in order to make the page scrollable again.</span></span>
        
        :::image type="complex" source="../media/dom-break-attribute-modifications-sources-paused-on.msft.png" alt-text="スクリプトの実行を再開する場所" lightbox="../media/dom-break-attribute-modifications-sources-paused-on.msft.png":::
           <span data-ttu-id="c6fda-296">スクリプトの実行を再開する場所</span><span class="sxs-lookup"><span data-stu-id="c6fda-296">Where to resume script running</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="c6fda-297">上の [ **背景の設定]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-297">Choose the **Set Background** button above.</span></span>  <span data-ttu-id="c6fda-298">これにより、ノード `style` の属性がに設定されます `background-color:thistle` 。</span><span class="sxs-lookup"><span data-stu-id="c6fda-298">This sets the `style` attribute of the node to `background-color:thistle`.</span></span>  <span data-ttu-id="c6fda-299">DevTools はページを一時停止し、属性が変更されたコードを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-299">DevTools pauses the page and highlights the code that caused the attribute to change.</span></span>  
    1.  <span data-ttu-id="c6fda-300">前述 **したように、[スクリプトの再開** ]\( ![ Resume Script ](../media/resume-script-icon.msft.png) \)を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-300">Choose **Resume Script** \(![Resume Script](../media/resume-script-icon.msft.png)\), as mentioned earlier.</span></span>  
    
### <a name="break-on-node-removal"></a><span data-ttu-id="c6fda-301">ノードの削除時のブレーク</span><span class="sxs-lookup"><span data-stu-id="c6fda-301">Break on node removal</span></span>  

<span data-ttu-id="c6fda-302">特定のノードを削除するときに一時停止する場合は、ノード削除ブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-302">If you want to pause when a particular node is removed, use node removal breakpoints.</span></span>  

1.  <span data-ttu-id="c6fda-303">[DOM の例を開きます](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="c6fda-303">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="c6fda-304">[ **ノードの削除時にブレーク]** で、[ニューロマンサー] を **右クリックし、[** 検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-304">Under **Break on Node Removal**, right-choose **Neuromancer** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="c6fda-305">DOM ツリーで、マウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[ノードの削除] を `<li id="target">Neuromancer</li>` \*\*\*\*  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-305">In the DOM Tree, hover on `<li id="target">Neuromancer</li>`, open the contextual menu \(right-click\), and choose **Break On** > **Node Removal**.</span></span>  <span data-ttu-id="c6fda-306">オプションが [表示されない場合は](#appendix-missing-options) 、[付録: 不足しているオプション] に移動します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-306">Navigate to [Appendix: Missing options](#appendix-missing-options) if the option is not displayed.</span></span>  
    1.  <span data-ttu-id="c6fda-307">上の [ **削除]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-307">Choose the **Delete** button above.</span></span>  <span data-ttu-id="c6fda-308">DevTools はページを一時停止し、ノードを削除したコードを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-308">DevTools pauses the page and highlights the code that caused the node to be removed.</span></span>  
    1.  <span data-ttu-id="c6fda-309">[ **スクリプトの再開** \( ![ Resume Script ](../media/resume-script-icon.msft.png) \) ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-309">Choose **Resume Script** \(![Resume Script](../media/resume-script-icon.msft.png)\).</span></span>  
    
### <a name="break-on-subtree-modifications"></a><span data-ttu-id="c6fda-310">サブツリーの変更時のブレーク</span><span class="sxs-lookup"><span data-stu-id="c6fda-310">Break on subtree modifications</span></span>  

<span data-ttu-id="c6fda-311">サブツリー変更ブレークポイントをノードに置いた後、ノードの子孫が追加または削除されると、DevTools はページを一時停止します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-311">After you put a subtree modification breakpoint on a node, DevTools pauses the page when any of the descendants of the node are added or removed.</span></span>  

1.  <span data-ttu-id="c6fda-312">[DOM の例を開きます](#open-dom-examples)。</span><span class="sxs-lookup"><span data-stu-id="c6fda-312">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="c6fda-313">[ **サブツリーの変更時にブレーク] で**、[深部の火] を右クリック **し、[** 検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-313">Under **Break on Subtree Modifications**, right-choose **A Fire Upon The Deep** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="c6fda-314">DOM ツリーで、上のノードにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[サブツリーの変更時にブレーク] `<ul id="target">` `<li>A Fire Upon the Deep</li>` \*\*\*\*  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-314">In the DOM Tree, hover on `<ul id="target">`, which is the node above `<li>A Fire Upon the Deep</li>`, open the contextual menu \(right-click\), and choose **Break On** > **Subtree Modifications**.</span></span>  <span data-ttu-id="c6fda-315">オプションが表示されない場合は、[付録: 不足 [しているオプション] に移動します](#appendix-missing-options)。</span><span class="sxs-lookup"><span data-stu-id="c6fda-315">If the option is not displayed, navigate to [Appendix: Missing options](#appendix-missing-options).</span></span>  
    1.  <span data-ttu-id="c6fda-316">[子 **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6fda-316">Choose **Add Child**.</span></span>  <span data-ttu-id="c6fda-317">ノードがリストに追加された `<li>` ため、コードは一時停止します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-317">The code pauses because a `<li>` node was added to the list.</span></span>  
    1.  <span data-ttu-id="c6fda-318">[ **スクリプトの再開** \( ![ Resume Script ](../media/resume-script-icon.msft.png) \) ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-318">Choose **Resume Script** \(![Resume Script](../media/resume-script-icon.msft.png)\).</span></span>  
    
## <a name="next-steps"></a><span data-ttu-id="c6fda-319">次の手順</span><span class="sxs-lookup"><span data-stu-id="c6fda-319">Next steps</span></span>  

<span data-ttu-id="c6fda-320">これは、DevTools の DOM 関連の機能のほとんどをカバーしています。</span><span class="sxs-lookup"><span data-stu-id="c6fda-320">That covers most of the DOM-related features in DevTools.</span></span>  <span data-ttu-id="c6fda-321">他の機能を見つけるには、DOM ツリーのノードをホバーし、コンテキスト メニュー \(右クリック\) を開き、このチュートリアルで説明していない他のオプションを試します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-321">You are able to discover the rest of the features by hovering on nodes in the DOM Tree, opening the contextual menu \(right-click\), and experimenting with the other options that were not covered in this tutorial.</span></span>  <span data-ttu-id="c6fda-322">[要素] [パネルのキーボード ショートカットに移動します][DevToolsShortcutsElements]。</span><span class="sxs-lookup"><span data-stu-id="c6fda-322">Navigate to [Elements panel keyboard shortcuts][DevToolsShortcutsElements].</span></span>  

<span data-ttu-id="c6fda-323">DevTools の[Microsoft Edgeをチェックして、DevTools][MicrosoftEdgeDevTools]で行えるその他のすべてを見つめ出してください。</span><span class="sxs-lookup"><span data-stu-id="c6fda-323">Check out the [Microsoft Edge DevTools homepage][MicrosoftEdgeDevTools] to discover everything else you are able to do with DevTools.</span></span>  

<!--Navigate to [Community](../index#community) if you want to contact the DevTools team or get help from the DevTools community.  -->  

## <a name="appendix-html-versus-the-dom"></a><span data-ttu-id="c6fda-324">付録: HTML と DOM の比較</span><span class="sxs-lookup"><span data-stu-id="c6fda-324">Appendix: HTML versus the DOM</span></span>  

<span data-ttu-id="c6fda-325">次のセクションでは、HTML と DOM の違いについて簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-325">The following section quickly explains the difference between HTML and the DOM.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="c6fda-326">Web ブラウザーを使用してページを要求すると、サーバーは次のコード スニペットのような HTML を返します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-326">When you use a web browser to request a page, the server returns HTML like the following code snippet</span></span>  

      ```html
      <!doctype html>
      <html>
          <head>
              <title>Hello, world!</title>
          </head>
          <body>
              <h1>Hello, world!</h1>
              <p>This is a hypertext document on the World Wide Web.</p>
              <script src="/script.js" async></script>
          </body>
      </html>
      ```  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="c6fda-327">ブラウザーは HTML を解析し、次のリストのようなオブジェクトのツリーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-327">The browser parses the HTML and creates a tree of objects like the following list.</span></span>  
      
      ```dom
      html
          head
              title
          body
              h1
              p
              script
      ```  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="c6fda-328">ページのコンテンツを表すオブジェクトまたはノードのこのツリーを DOM と呼ぶ。</span><span class="sxs-lookup"><span data-stu-id="c6fda-328">This tree of objects, or nodes, representing the content of the page is called the DOM.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="c6fda-329">現時点では HTML と同じように見えますが、HTML の下部で参照されるスクリプトで次のコード スニペットが実行されるとします。</span><span class="sxs-lookup"><span data-stu-id="c6fda-329">Right now it looks the same as the HTML, but suppose that the script referenced at the bottom of the HTML runs the following code snippet.</span></span>  
      
      ```javascript
      const h1 = document.querySelector('h1');
      h1.parentElement.removeChild(h1);
      const p = document.createElement('p');
      p.textContent = 'Wildcard!';
      document.body.appendChild(p);
      ```  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="c6fda-330">そのコードはノードを削除 `h1` し、DOM に `p` 別のノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-330">That code removes the `h1` node and adds another `p` node to the DOM.</span></span>  <span data-ttu-id="c6fda-331">これで、完全な DOM に次の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-331">The complete DOM now displays the following list.</span></span>  
      
      ```dom
      html
          head
              title
          body
              p
              script
              p
      ```  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="c6fda-332">ページの HTML が DOM と異なっています。</span><span class="sxs-lookup"><span data-stu-id="c6fda-332">The HTML for the page is now different than the DOM.</span></span>  <span data-ttu-id="c6fda-333">つまり、HTML は初期ページ コンテンツを表し、DOM は現在のページ コンテンツを表します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-333">In other words, HTML represents initial page content, and the DOM represents current page content.</span></span>  <span data-ttu-id="c6fda-334">JavaScript がノードを追加、削除、または編集すると、DOM は HTML とは異なります。</span><span class="sxs-lookup"><span data-stu-id="c6fda-334">When JavaScript adds, removes, or edits nodes, the DOM becomes different than the HTML.</span></span>  

<span data-ttu-id="c6fda-335">詳細については [、「DOM の概要」][MDNIntroductionToDOM] に移動します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-335">Navigate to [Introduction to the DOM][MDNIntroductionToDOM] to learn more.</span></span>  

<!--
## Appendix: Scroll into view  

This is a continuation of the [Scroll into view](#scroll-into-view) section.  Follow the instructions below to complete the section.  

1.  The `<li>Magritte</li>` node should still be selected in your DOM Tree.  If not, go back to [Scroll into view](#scroll-into-view) and start over.  
1.  Hover on the `<li>Magritte</li>` node, open the contextual menu \(right-click\), and choose **Scroll into view**.  Your viewport scrolls back up so that the **Magritte** node is displayed.  If you the **Scroll into view** option is not displayed, navigate to [Appendix: Missing options](#appendix-missing-options).
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="Scroll into view" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       Scroll into view  
    :::image-end:::  
    -->  

## <a name="appendix-missing-options"></a><span data-ttu-id="c6fda-336">付録: 不足しているオプション</span><span class="sxs-lookup"><span data-stu-id="c6fda-336">Appendix: Missing options</span></span>  

<span data-ttu-id="c6fda-337">このチュートリアルの手順の多くは、DOM ツリーのノードにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、ポップアップするコンテキスト メニューからオプションを選択するように指示します。</span><span class="sxs-lookup"><span data-stu-id="c6fda-337">Many of the instructions in this tutorial instruct you to hover on a node in the DOM Tree, open the contextual menu \(right-click\), and then choose an option from the context menu that pops up.</span></span>  <span data-ttu-id="c6fda-338">コンテキスト メニューの指定したオプションが表示されない場合は、ノード のテキストから離れて、コンテキスト メニュー \(右クリック\) を開きます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-338">If the specified option in the context menu is not displayed, try hovering away from the node text and opening the contextual menu \(right-click\).</span></span>  

:::image type="complex" source="../media/dom-elements-highlighted-right-click-right-side.msft.png" alt-text="すべてのオプションが表示されない場合の選択先" lightbox="../media/dom-elements-highlighted-right-click-right-side.msft.png":::
   <span data-ttu-id="c6fda-340">すべてのオプションが表示されない場合の選択先</span><span class="sxs-lookup"><span data-stu-id="c6fda-340">Where to choose if all of the options are not displayed</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="c6fda-341">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="c6fda-341">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge \(Chromium\) Developer Tools |Microsoft Docs"  
[DevToolsCssGetStarted]: ../css/index.md "はじめにCSS の表示と変更を使用|Microsoft Docs"  
[DevToolsShortcutsElements]: ../shortcuts/index.md#elements-tool-keyboard-shortcuts "要素ツールのキーボード ショートカット - DevTools Microsoft Edge キーボード ショートカット |Microsoft Docs"  

[GlitchDomExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/dom "Microsoft Edge (Chromium) DevTools DOM の例 |Glitch"

[MDNIntroductionToDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM の概要|MDN"  

> [!NOTE]
> <span data-ttu-id="c6fda-347">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="c6fda-347">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c6fda-348">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/dom/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="c6fda-348">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/dom/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="c6fda-350">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="c6fda-350">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
