---
title: DOM の表示と変更を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 4dee8b4e3ea927e72c0f98517f264b2c1d453013
ms.sourcegitcommit: 531ec8aa1f89b28bc4d271e8e995f846f2392bc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "10607448"
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





# <span data-ttu-id="5e346-103">DOM の表示と変更を開始する</span><span class="sxs-lookup"><span data-stu-id="5e346-103">Get Started With Viewing And Changing The DOM</span></span>   



<span data-ttu-id="5e346-104">Microsoft Edge DevTools を使用して、ページの DOM を表示して変更する基本的な方法については、次の対話型チュートリアルを実行してください。</span><span class="sxs-lookup"><span data-stu-id="5e346-104">Complete these interactive tutorials to learn the basics of viewing and changing the DOM of a page using Microsoft Edge DevTools.</span></span>  

<span data-ttu-id="5e346-105">このチュートリアルでは、DOM と HTML の違いを知っていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="5e346-105">This tutorial assumes that you know the difference between the DOM and HTML.</span></span>  <span data-ttu-id="5e346-106">説明については[、「付録: HTML と DOM の比較](#appendix-html-versus-the-dom)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e346-106">See [Appendix: HTML versus the DOM](#appendix-html-versus-the-dom) for an explanation.</span></span>  

## <span data-ttu-id="5e346-107">DOM の例を開く</span><span class="sxs-lookup"><span data-stu-id="5e346-107">Open DOM Examples</span></span>  

1.  <span data-ttu-id="5e346-108">`Control`\ (Windows \) または `Command` \ (macOS \) を保持し、[ **DOM の例**] をクリックして新しいタブで開きます。</span><span class="sxs-lookup"><span data-stu-id="5e346-108">Hold `Control` \(Windows\) or `Command` \(macOS\) and click **DOM Examples** to open in a new tab.</span></span>  
    
    [<span data-ttu-id="5e346-109">DOM の例</span><span class="sxs-lookup"><span data-stu-id="5e346-109">DOM Examples</span></span>][GlitchDomExamples]  
    
## <span data-ttu-id="5e346-110">DOM ノードの表示</span><span class="sxs-lookup"><span data-stu-id="5e346-110">View DOM nodes</span></span>   

<span data-ttu-id="5e346-111">[要素] パネルの DOM ツリーでは、DevTools で DOM に関連するすべてのアクティビティを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5e346-111">The DOM Tree of the Elements panel is where you do all DOM-related activities in DevTools.</span></span>  

### <span data-ttu-id="5e346-112">ノードを検査する</span><span class="sxs-lookup"><span data-stu-id="5e346-112">Inspect a node</span></span>   

<span data-ttu-id="5e346-113">特定の DOM ノードに関心がある場合は、[**検査**] を使うと、devtools をすばやく開いてそのノードを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="5e346-113">When you are interested in a particular DOM node, **Inspect** is a fast way to open DevTools and investigate that node.</span></span>  

1.  <span data-ttu-id="5e346-114">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-114">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5e346-115">[**ノードの検査**] で、[ **Michelangelo** ] を右クリックし、[**検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e346-115">Under **Inspect a Node**, right-click **Michelangelo** and select **Inspect**.</span></span>  
    
    > ##### <span data-ttu-id="5e346-116">図 1</span><span class="sxs-lookup"><span data-stu-id="5e346-116">Figure 1</span></span>  
    > <span data-ttu-id="5e346-117">ノードを検査する</span><span class="sxs-lookup"><span data-stu-id="5e346-117">Inspecting a node</span></span>  
    > ![ノードを検査する][ImageInspectingNode]  
    
    1.  <span data-ttu-id="5e346-119">DevTools の [**要素**] パネルが開きます。</span><span class="sxs-lookup"><span data-stu-id="5e346-119">The **Elements** panel of DevTools opens.</span></span>  `<li>Michelangelo</li>` <span data-ttu-id="5e346-120">が強調表示さ**れてい**ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-120">is highlighted in the **DOM Tree**.</span></span>  
        
        > ##### <span data-ttu-id="5e346-121">図 2</span><span class="sxs-lookup"><span data-stu-id="5e346-121">Figure 2</span></span>  
        > <span data-ttu-id="5e346-122">Michelangelo ノードの強調表示</span><span class="sxs-lookup"><span data-stu-id="5e346-122">Highlighting the Michelangelo node</span></span>  
        > ![Michelangelo ノードの強調表示][ImageHighlightingMichelangeloNode]  
        
        1.  <span data-ttu-id="5e346-124">**Inspect** ![ ][ImageInspectIcon] Devtools の左上隅にある検査検査アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e346-124">Click the **Inspect** ![Inspect][ImageInspectIcon] icon in the top-left corner of DevTools.</span></span>  
            
            > ##### <span data-ttu-id="5e346-125">図 3</span><span class="sxs-lookup"><span data-stu-id="5e346-125">Figure 3</span></span>  
            > <span data-ttu-id="5e346-126">[検査] アイコン</span><span class="sxs-lookup"><span data-stu-id="5e346-126">The Inspect icon</span></span>  
            > ![[検査] アイコン][ImageInspect]  
            
1.  <span data-ttu-id="5e346-128">[**ノードの検査**] で、[**東京**] のテキストをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e346-128">Under **Inspect a Node**, click the **Tokyo** text.</span></span>  <span data-ttu-id="5e346-129">これで、 `<li>Tokyo</li>` DOM ツリーで強調表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5e346-129">Now, `<li>Tokyo</li>` is highlighted in the DOM Tree.</span></span>  

<span data-ttu-id="5e346-130">ノードの [検査] は、ノードのスタイルを表示して変更するための最初の手順でもあります。</span><span class="sxs-lookup"><span data-stu-id="5e346-130">Inspecting a node is also the first step towards viewing and changing the styles of a node.</span></span>  <span data-ttu-id="5e346-131">「 [CSS の表示と変更」の「使用を開始する」を][DevToolsCssGetStarted]参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e346-131">See [Get Started With Viewing And Changing CSS][DevToolsCssGetStarted].</span></span>  

### <span data-ttu-id="5e346-132">キーボードで DOM ツリー内を移動する</span><span class="sxs-lookup"><span data-stu-id="5e346-132">Navigate the DOM Tree with a keyboard</span></span>   

<span data-ttu-id="5e346-133">DOM ツリーでノードを選択すると、DOM ツリーをキーボードで移動できます。</span><span class="sxs-lookup"><span data-stu-id="5e346-133">Once you have selected a node in the DOM Tree, you may navigate the DOM Tree with your keyboard.</span></span>  

1.  <span data-ttu-id="5e346-134">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-134">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5e346-135">[ **DOM ツリーのキーボードでの操作**] で、[ **Ringo** ] を右クリックし、[**検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5e346-135">Under **Navigate the DOM Tree with a Keyboard**, right-click **Ringo** and select **Inspect**.</span></span>  `<li>Ringo</li>` <span data-ttu-id="5e346-136">が選択されます。</span><span class="sxs-lookup"><span data-stu-id="5e346-136">is selected in the DOM Tree.</span></span>  
    
    > ##### <span data-ttu-id="5e346-137">図 4</span><span class="sxs-lookup"><span data-stu-id="5e346-137">Figure 4</span></span>  
    > <span data-ttu-id="5e346-138">Ringo ノードの検査</span><span class="sxs-lookup"><span data-stu-id="5e346-138">Inspecting the Ringo node</span></span>  
    > ![Ringo ノードの検査][ImageInspectingRingoNode]  
    
    1.  <span data-ttu-id="5e346-140">`Up`方向キーを2回押します。</span><span class="sxs-lookup"><span data-stu-id="5e346-140">Press the `Up` arrow key 2 times.</span></span>  `<ul>` <span data-ttu-id="5e346-141"> がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5e346-141">is selected.</span></span>  
        
        > ##### <span data-ttu-id="5e346-142">図 5</span><span class="sxs-lookup"><span data-stu-id="5e346-142">Figure 5</span></span>  
        > <span data-ttu-id="5e346-143">Ul ノードの検査</span><span class="sxs-lookup"><span data-stu-id="5e346-143">Inspecting the ul node</span></span>  
        > ![Ul ノードの検査][ImageInspectingUlNode]  
        
    1.  <span data-ttu-id="5e346-145">`Left`方向キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5e346-145">Press the `Left` arrow key.</span></span>  <span data-ttu-id="5e346-146">`<ul>`リストが折りたたまれます。</span><span class="sxs-lookup"><span data-stu-id="5e346-146">The `<ul>` list collapses.</span></span>  
    1.  <span data-ttu-id="5e346-147">`Left`もう一度方向キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5e346-147">Press the `Left` arrow key again.</span></span>  <span data-ttu-id="5e346-148">ノードの親 `<ul>` が選択されます。</span><span class="sxs-lookup"><span data-stu-id="5e346-148">The parent of the `<ul>` node is selected.</span></span>  <span data-ttu-id="5e346-149">この場合は、 `<div>` ID を使用し `navigate-the-dom-tree-with-a-keyboard-1` ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-149">In this case it is the `<div>` with the ID `navigate-the-dom-tree-with-a-keyboard-1`.</span></span>  
    1.  <span data-ttu-id="5e346-150">`Down`方向キーを2回押して、折りたたんだリストをもう一度選択し `<ul>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-150">Press the `Down` arrow key 2 times so that you have re-selected the `<ul>` list that you just collapsed.</span></span>  <span data-ttu-id="5e346-151">次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5e346-151">It should look like this:</span></span> `<ul>... </ul>`  
    1.  <span data-ttu-id="5e346-152">`Right`方向キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5e346-152">Press the `Right` arrow key.</span></span>  <span data-ttu-id="5e346-153">リストが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="5e346-153">The list expands.</span></span>  

### <span data-ttu-id="5e346-154">スクロールして表示する</span><span class="sxs-lookup"><span data-stu-id="5e346-154">Scroll into view</span></span>   

<span data-ttu-id="5e346-155">DOM ツリーを表示しているときに、現在ビューポート内にない DOM ノードに興味を持っていることがあります。</span><span class="sxs-lookup"><span data-stu-id="5e346-155">When viewing the DOM Tree, you may find yourself interested in a DOM node that is not currently in the viewport.</span></span>  <span data-ttu-id="5e346-156">たとえば、ページの一番下までスクロールして、ページの上部にあるノードに関心を持っているとし `<h1>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-156">For example, suppose that you scrolled to the bottom of the page, and you are interested in the `<h1>` node at the top of the page.</span></span>  <span data-ttu-id="5e346-157">**ビューをスクロール**すると、ビューポートをすばやく移動して、ノードを表示できます。</span><span class="sxs-lookup"><span data-stu-id="5e346-157">**Scroll into view** lets you quickly reposition the viewport so that you are able to see the node.</span></span>  

1.  <span data-ttu-id="5e346-158">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-158">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5e346-159">[**スクロール**して表示] で、[ **Magritte** ] を右クリックし、[**検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e346-159">Under **Scroll into View**, right-click **Magritte** and select **Inspect**.</span></span>  
1.  <span data-ttu-id="5e346-160">DOM の [例] ページの一番下までスクロールします。</span><span class="sxs-lookup"><span data-stu-id="5e346-160">Scroll to the bottom of the DOM Examples page.</span></span>  
1.  <span data-ttu-id="5e346-161">`<li>Magritte</li>`それでも、ノードは DOM ツリーで選択されます。</span><span class="sxs-lookup"><span data-stu-id="5e346-161">The `<li>Magritte</li>` node should still be selected in your DOM Tree.</span></span>  <span data-ttu-id="5e346-162">表示されていない場合は、戻って、もう一度[表示](#scroll-into-view)してみてください。</span><span class="sxs-lookup"><span data-stu-id="5e346-162">If not, go back to [Scroll into view](#scroll-into-view) and start over.</span></span>  
1.  <span data-ttu-id="5e346-163">ノードを右クリックし `<li>Magritte</li>` て、[**ビューにスクロール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e346-163">Right-click the `<li>Magritte</li>` node and select **Scroll into view**.</span></span>  <span data-ttu-id="5e346-164">ビューポートがスクロールして、 **Magritte**ノードが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="5e346-164">Your viewport scrolls back up so that you may see the **Magritte** node.</span></span>  <span data-ttu-id="5e346-165">[スクロールして**表示**する] オプションが表示されない場合は、「[付録: オプションが見つから](#appendix-missing-options)ない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e346-165">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see the **Scroll into view** option.</span></span>
    
    > ##### <span data-ttu-id="5e346-166">図 6</span><span class="sxs-lookup"><span data-stu-id="5e346-166">Figure 6</span></span>  
    > <span data-ttu-id="5e346-167">スクロールして表示する</span><span class="sxs-lookup"><span data-stu-id="5e346-167">Scroll into view</span></span>  
    > ![スクロールして表示する][ImageScrollView]  

### <span data-ttu-id="5e346-169">ノードを検索する</span><span class="sxs-lookup"><span data-stu-id="5e346-169">Search for nodes</span></span>   

<span data-ttu-id="5e346-170">DOM ツリーは、文字列、CSS セレクター、または XPath セレクターで検索できます。</span><span class="sxs-lookup"><span data-stu-id="5e346-170">You may search the DOM Tree by string, CSS selector, or XPath selector.</span></span>  

1.  <span data-ttu-id="5e346-171">カーソルを [**要素**] パネルにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="5e346-171">Focus your cursor on the **Elements** panel.</span></span>  
1.  <span data-ttu-id="5e346-172">`Control` + `F` \ (Windows \) または `Command` + `F` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="5e346-172">Press `Control`+`F` \(Windows\) or `Command`+`F` \(macOS\).</span></span>  <span data-ttu-id="5e346-173">検索バーは DOM ツリーの下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e346-173">The Search bar opens at the bottom of the DOM Tree.</span></span>  
1.  <span data-ttu-id="5e346-174">「`The Moon is a Harsh Mistress`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="5e346-174">Type `The Moon is a Harsh Mistress`.</span></span>  <span data-ttu-id="5e346-175">DOM ツリーの最後の文が強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="5e346-175">The last sentence is highlighted in the DOM Tree.</span></span>  
    
    > ##### <span data-ttu-id="5e346-176">図 7</span><span class="sxs-lookup"><span data-stu-id="5e346-176">Figure 7</span></span>  
    > <span data-ttu-id="5e346-177">検索バーでクエリを強調表示する</span><span class="sxs-lookup"><span data-stu-id="5e346-177">Highlighting the query in the Search bar</span></span>  
    > ![検索バーでクエリを強調表示する][ImageHighlightingQuerySearchBar]  
    
<span data-ttu-id="5e346-179">上で説明したように、検索バーは CSS と XPath のセレクターもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5e346-179">As mentioned above, the Search bar also supports CSS and XPath selectors.</span></span>  

## <span data-ttu-id="5e346-180">DOM を編集する</span><span class="sxs-lookup"><span data-stu-id="5e346-180">Edit the DOM</span></span>   

<span data-ttu-id="5e346-181">その場で DOM を編集して、それらの変更がページにどのように影響するかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5e346-181">You may edit the DOM on the fly and see how those changes affect the page.</span></span>  

### <span data-ttu-id="5e346-182">コンテンツを編集する</span><span class="sxs-lookup"><span data-stu-id="5e346-182">Edit content</span></span>   

<span data-ttu-id="5e346-183">ノードのコンテンツを編集するには、DOM ツリーでコンテンツをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e346-183">To edit the content of a node, double-click the content in the DOM Tree.</span></span>  

1.  <span data-ttu-id="5e346-184">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-184">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5e346-185">[**コンテンツの編集**] で [ **micん le** ] を右クリックし、[**検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5e346-185">Under **Edit Content**, right-click **Michelle** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="5e346-186">DOM ツリーで、をダブルクリック `Michelle` します。</span><span class="sxs-lookup"><span data-stu-id="5e346-186">In the DOM Tree, double-click `Michelle`.</span></span>  <span data-ttu-id="5e346-187">つまり、との間のテキストをダブルクリック `<li>` し `</li>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-187">In other words, double-click the text between `<li>` and `</li>`.</span></span>  <span data-ttu-id="5e346-188">テキストが強調表示され、選択されていることが示されます。</span><span class="sxs-lookup"><span data-stu-id="5e346-188">The text is highlighted to indicate that it is selected.</span></span>  
        
        > ##### <span data-ttu-id="5e346-189">図 8</span><span class="sxs-lookup"><span data-stu-id="5e346-189">Figure 8</span></span>  
        > <span data-ttu-id="5e346-190">テキストを編集する</span><span class="sxs-lookup"><span data-stu-id="5e346-190">Editing the text</span></span>  
        > ![テキストを編集する][ImageEditingText]  
        
    1.  <span data-ttu-id="5e346-192">を削除し `Michelle` て入力し、 `Leela` enter キーを押して `Enter` 変更を確定します。</span><span class="sxs-lookup"><span data-stu-id="5e346-192">Delete `Michelle`, type `Leela`, then press `Enter` to confirm the change.</span></span>  <span data-ttu-id="5e346-193">DOM 内のテキストは、 **MicLeela le**から**Leela**に変更されます。</span><span class="sxs-lookup"><span data-stu-id="5e346-193">The text in the DOM changes from **Michelle** to **Leela**.</span></span>  

### <span data-ttu-id="5e346-194">属性を編集する</span><span class="sxs-lookup"><span data-stu-id="5e346-194">Edit attributes</span></span>   

<span data-ttu-id="5e346-195">属性を編集するには、属性の名前または値をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e346-195">To edit attributes, double-click the attribute name or value.</span></span>  <span data-ttu-id="5e346-196">手順に従って、ノードに属性を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5e346-196">Follow the instructions to learn how to add attributes to a node.</span></span>  

1.  <span data-ttu-id="5e346-197">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-197">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5e346-198">[**属性の編集**] で、[ **Howard** ] を右クリックし、[**検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e346-198">Under **Edit Attributes**, right-click **Howard** and select **Inspect**.</span></span>  

1.  <span data-ttu-id="5e346-199">ダブルクリック `<li>` します。</span><span class="sxs-lookup"><span data-stu-id="5e346-199">Double-click `<li>`.</span></span>  <span data-ttu-id="5e346-200">テキストが強調表示され、ノードが選択されていることが示されます。</span><span class="sxs-lookup"><span data-stu-id="5e346-200">The text is highlighted to indicate that the node is selected.</span></span>  
    
    > ##### <span data-ttu-id="5e346-201">図 9</span><span class="sxs-lookup"><span data-stu-id="5e346-201">Figure 9</span></span>  
    > <span data-ttu-id="5e346-202">ノードを編集する</span><span class="sxs-lookup"><span data-stu-id="5e346-202">Editing the node</span></span>  
    > ![ノードを編集する][ImageEditingNode]  
    
1.  <span data-ttu-id="5e346-204">方向キーを押して、スペースを追加し、 `Right` 「」と入力して `style="background-color:gold"` 、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-204">Press the `Right` arrow key, add a space, type `style="background-color:gold"`, and then press `Enter`.</span></span>  <span data-ttu-id="5e346-205">ノードの背景色が金色に変わります。</span><span class="sxs-lookup"><span data-stu-id="5e346-205">The background color of the node changes to gold.</span></span>  
    
    > ##### <span data-ttu-id="5e346-206">図 10</span><span class="sxs-lookup"><span data-stu-id="5e346-206">Figure 10</span></span>  
    > <span data-ttu-id="5e346-207">ノードへのスタイル属性の追加</span><span class="sxs-lookup"><span data-stu-id="5e346-207">Adding a style attribute to the node</span></span>  
    > ![ノードへのスタイル属性の追加][ImageAddingStyleAttributeNode]  
    
### <span data-ttu-id="5e346-209">ノードの種類を編集する</span><span class="sxs-lookup"><span data-stu-id="5e346-209">Edit node type</span></span>   

<span data-ttu-id="5e346-210">ノードの種類を編集するには、型をダブルクリックし、新しい型を入力します。</span><span class="sxs-lookup"><span data-stu-id="5e346-210">To edit the type of a node, double-click the type and then type in the new type.</span></span>  

1.  <span data-ttu-id="5e346-211">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-211">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5e346-212">[**ノードの種類の編集**] で、[ **Hank** ] を右クリックし、[**検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e346-212">Under **Edit Node Type**, right-click **Hank** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="5e346-213">ダブルクリック `<li>` します。</span><span class="sxs-lookup"><span data-stu-id="5e346-213">Double-click `<li>`.</span></span>  <span data-ttu-id="5e346-214">テキスト `li` が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e346-214">The text `li` is highlighted.</span></span>  
    1.  <span data-ttu-id="5e346-215">を削除し `li` て、を入力し `button` `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-215">Delete `li`, type `button`, then press `Enter`.</span></span>  <span data-ttu-id="5e346-216">`<li>`ノードがノードに変わり `<button>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-216">The `<li>` node changes to a `<button>` node.</span></span>  
        
        > ##### <span data-ttu-id="5e346-217">図 11</span><span class="sxs-lookup"><span data-stu-id="5e346-217">Figure 11</span></span>  
        > <span data-ttu-id="5e346-218">[ノードの種類の変更] ボタン</span><span class="sxs-lookup"><span data-stu-id="5e346-218">Changing the node type to button</span></span>  
        > ![[ノードの種類の変更] ボタン][ImageChangingNodeButton]  
        
### <span data-ttu-id="5e346-220">DOM ノードの順序を変更する</span><span class="sxs-lookup"><span data-stu-id="5e346-220">Reorder DOM nodes</span></span>   

<span data-ttu-id="5e346-221">ノードをドラッグして順序を変更します。</span><span class="sxs-lookup"><span data-stu-id="5e346-221">Drag nodes to reorder them.</span></span>  

1.  <span data-ttu-id="5e346-222">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-222">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5e346-223">[ **DOM ノードの順序**変更] で、[ **Elvis Presley** ] を右クリックし、[**検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5e346-223">Under **Reorder DOM Nodes**, right-click **Elvis Presley** and select **Inspect**.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="5e346-224">これは、リスト内の最後のアイテムです。</span><span class="sxs-lookup"><span data-stu-id="5e346-224">It is the last item in the list.</span></span>  
    
    1.  <span data-ttu-id="5e346-225">DOM ツリーで、 `<li>Elvis Presley</li>` 一覧の一番上までドラッグします。</span><span class="sxs-lookup"><span data-stu-id="5e346-225">In the DOM Tree, drag `<li>Elvis Presley</li>` to the top of the list.</span></span>  
        
        > ##### <span data-ttu-id="5e346-226">図 12</span><span class="sxs-lookup"><span data-stu-id="5e346-226">Figure 12</span></span>  
        > <span data-ttu-id="5e346-227">ノードを一覧の一番上にドラッグする</span><span class="sxs-lookup"><span data-stu-id="5e346-227">Dragging the node to the top of the list</span></span>  
        > ![ノードを一覧の一番上にドラッグする][ImageDraggingNodeTopList]  
        
### <span data-ttu-id="5e346-229">強制状態</span><span class="sxs-lookup"><span data-stu-id="5e346-229">Force state</span></span>   

<span data-ttu-id="5e346-230">ノードは、、、、、などの状態に保つことができ `:active` `:hover` `:focus` `:visited` `:focus-within` ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-230">You are able to force nodes to remain in states including `:active`, `:hover`, `:focus`, `:visited`, and `:focus-within`.</span></span>  

1.  <span data-ttu-id="5e346-231">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-231">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5e346-232">[**状態の強制**] で、**その中の閣下**をポイントします。</span><span class="sxs-lookup"><span data-stu-id="5e346-232">Under **Force state**, hover over **The Lord of the Flies**.</span></span>  <span data-ttu-id="5e346-233">背景色がオレンジ色になります。</span><span class="sxs-lookup"><span data-stu-id="5e346-233">The background color becomes orange.</span></span>  
    1.  <span data-ttu-id="5e346-234">**フライの閣下**を右クリックして、[**検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5e346-234">Right-click **The Lord of the Flies** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="5e346-235">右クリック `<li class="demo--hover">The Lord of the Flies</li>` し、[**状態の強制**  >  **: hover**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5e346-235">Right-click `<li class="demo--hover">The Lord of the Flies</li>` and select **Force State** > **:hover**.</span></span>  <span data-ttu-id="5e346-236">このオプションが表示されない場合は、「[付録: オプション](#appendix-missing-options)を表示しない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e346-236">See [Appendix: Missing options](#appendix-missing-options) if you do not see this option.</span></span>  <span data-ttu-id="5e346-237">実際には、ノードの上にカーソルを置いていない場合でも、背景色はオレンジにとどまります。</span><span class="sxs-lookup"><span data-stu-id="5e346-237">The background color remains orange even though you are not actually hovering over the node.</span></span>  

### <span data-ttu-id="5e346-238">ノードを非表示にする</span><span class="sxs-lookup"><span data-stu-id="5e346-238">Hide a node</span></span>   

<span data-ttu-id="5e346-239">を押すと `H` 、ノードが非表示になります。</span><span class="sxs-lookup"><span data-stu-id="5e346-239">Press `H` to hide a node.</span></span>  

1.  <span data-ttu-id="5e346-240">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-240">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5e346-241">[**ノードを非表示にする**] で、[**宛先] の星**を右クリックし、[**検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e346-241">Under **Hide a node**, right-click **The Stars My Destination** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="5e346-242">キーを押し `H` ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-242">Press the `H` key.</span></span>  <span data-ttu-id="5e346-243">ノードが非表示になっています。</span><span class="sxs-lookup"><span data-stu-id="5e346-243">The node is hidden.</span></span>  
        
        > ##### <span data-ttu-id="5e346-244">図 13</span><span class="sxs-lookup"><span data-stu-id="5e346-244">Figure 13</span></span>  
        > <span data-ttu-id="5e346-245">非表示になった後のノードが DOM ツリーのどのように見えるか</span><span class="sxs-lookup"><span data-stu-id="5e346-245">What the node looks like in the DOM Tree after it is hidden</span></span>  
        > ![非表示になった後のノードが DOM ツリーのどのように見えるか][ImageNodeDomTreeAfterHidden]  
        
    1.  <span data-ttu-id="5e346-247">キーを `H` もう一度押します。</span><span class="sxs-lookup"><span data-stu-id="5e346-247">Press the `H` key again.</span></span>  <span data-ttu-id="5e346-248">ノードが再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e346-248">The node is shown again.</span></span>  

### <span data-ttu-id="5e346-249">ノードを削除する</span><span class="sxs-lookup"><span data-stu-id="5e346-249">Delete a node</span></span>   

<span data-ttu-id="5e346-250">を押して `Delete` ノードを削除します。</span><span class="sxs-lookup"><span data-stu-id="5e346-250">Press `Delete` to delete a node.</span></span>  

1.  <span data-ttu-id="5e346-251">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-251">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5e346-252">[**ノードの削除**] で、[ **Foundation** ] を右クリックし、[**検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e346-252">Under **Delete a Node**, right-click **Foundation** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="5e346-253">キーを押し `Delete` ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-253">Press the `Delete` key.</span></span>  <span data-ttu-id="5e346-254">ノードが削除されます。</span><span class="sxs-lookup"><span data-stu-id="5e346-254">The node is deleted.</span></span>  
    1.  <span data-ttu-id="5e346-255">`Control` + `Z` \ (Windows \) または `Command` + `Z` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="5e346-255">Press `Control`+`Z` \(Windows\) or `Command`+`Z` \(macOS\).</span></span>  <span data-ttu-id="5e346-256">直前の操作が取り消され、ノードが再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e346-256">The last action is undone and the node reappears.</span></span>  

## <span data-ttu-id="5e346-257">コンソールのアクセスノード</span><span class="sxs-lookup"><span data-stu-id="5e346-257">Access nodes in the Console</span></span>   

<span data-ttu-id="5e346-258">DevTools では、コンソールから DOM ノードにアクセスしたり、各デバイスへの JavaScript 参照を取得したりするためのショートカットキーをいくつか用意しています。</span><span class="sxs-lookup"><span data-stu-id="5e346-258">DevTools provides a few shortcuts for accessing DOM nodes from the Console, or getting JavaScript references to each one.</span></span>  

### <span data-ttu-id="5e346-259">$0 で現在選択されているノードを参照する</span><span class="sxs-lookup"><span data-stu-id="5e346-259">Reference the currently-selected node with $0</span></span>   

<span data-ttu-id="5e346-260">ノードを検査すると、 `== $0` ノードの横のテキストは、この変数を持つ本体でこのノードを参照できることを意味 `$0` します。</span><span class="sxs-lookup"><span data-stu-id="5e346-260">When you inspect a node, the `== $0` text next to the node means that you may reference this node in the Console with the variable `$0`.</span></span>  

1.  <span data-ttu-id="5e346-261">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-261">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5e346-262">[ **$0 で現在選択さ**れているノードを参照する] で、**暗さの左側**を右クリックして [**検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5e346-262">Under **Reference the currently-selected node with $0**, right-click **The Left Hand of Darkness** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="5e346-263">キーを押して、 `Escape` 本体の引き出しを開きます。</span><span class="sxs-lookup"><span data-stu-id="5e346-263">Press the `Escape` key to open the Console Drawer.</span></span>  
    1.  <span data-ttu-id="5e346-264">キーを入力 `$0` して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-264">Type `$0` and press the `Enter` key.</span></span>  <span data-ttu-id="5e346-265">この式の結果は、の `$0` 評価を示して `<li>The Left Hand of Darkness</li>` います。</span><span class="sxs-lookup"><span data-stu-id="5e346-265">The result of the expression shows that `$0` evaluates to `<li>The Left Hand of Darkness</li>`.</span></span>  
        
        > ##### <span data-ttu-id="5e346-266">図 14</span><span class="sxs-lookup"><span data-stu-id="5e346-266">Figure 14</span></span>  
        > <span data-ttu-id="5e346-267">本体の最初の式の結果 `$0`</span><span class="sxs-lookup"><span data-stu-id="5e346-267">The result of the first `$0` expression in the Console</span></span>  
        > ![本体の最初の $0 式の結果][ImageFirstConsole]  
        
    1.  <span data-ttu-id="5e346-269">結果にマウスポインターを合わせます。</span><span class="sxs-lookup"><span data-stu-id="5e346-269">Hover over the result.</span></span>  <span data-ttu-id="5e346-270">ビューポートで、ノードが強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="5e346-270">The node is highlighted in the viewport.</span></span>  
    1.  <span data-ttu-id="5e346-271">`<li>Dune</li>`DOM ツリー内をクリックし、 `$0` コンソールをもう一度入力して、 `Enter` もう一度押します。</span><span class="sxs-lookup"><span data-stu-id="5e346-271">Click `<li>Dune</li>` in the DOM Tree, type `$0` in the Console again, and then press `Enter` again.</span></span>  <span data-ttu-id="5e346-272">次に、の `$0` ようにに評価さ `<li>Dune</li>` れます。</span><span class="sxs-lookup"><span data-stu-id="5e346-272">Now, `$0` evaluates to `<li>Dune</li>`.</span></span>  
        
        > ##### <span data-ttu-id="5e346-273">図 15</span><span class="sxs-lookup"><span data-stu-id="5e346-273">Figure 15</span></span>  
        > <span data-ttu-id="5e346-274">本体の2番目の式の結果、本体の2番目の `$0` $0 式の結果が返されます。 ![][ImageSecondConsole]</span><span class="sxs-lookup"><span data-stu-id="5e346-274">The result of the second `$0` expression in the Console ![The result of the second $0 expression in the Console][ImageSecondConsole]</span></span>  
        
### <span data-ttu-id="5e346-275">グローバル変数として保存する</span><span class="sxs-lookup"><span data-stu-id="5e346-275">Store as global variable</span></span>   

<span data-ttu-id="5e346-276">何度もノードを参照する必要がある場合は、それをグローバル変数として保存します。</span><span class="sxs-lookup"><span data-stu-id="5e346-276">If you need to refer back to a node many times, store it as a global variable.</span></span>  

1.  <span data-ttu-id="5e346-277">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-277">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5e346-278">[**グローバル変数として保存**] で、**大きなスリープ状態**を右クリックし、[**検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e346-278">Under **Store as global variable**, right-click **The Big Sleep** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="5e346-279">DOM ツリーを右クリック `<li>The Big Sleep</li>` して、[**グローバル変数として保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5e346-279">Right-click `<li>The Big Sleep</li>` in the DOM Tree and select **Store as global variable**.</span></span>  <span data-ttu-id="5e346-280">このオプションが表示されない場合は、「[付録: オプション](#appendix-missing-options)を表示しない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e346-280">See [Appendix: Missing options](#appendix-missing-options) if you do not see this option.</span></span>  
    1.  <span data-ttu-id="5e346-281">`temp1`コンソールに入力して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-281">Type `temp1` in the Console and then press `Enter`.</span></span>  <span data-ttu-id="5e346-282">この式の結果は、変数がノードに評価されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5e346-282">The result of the expression shows that the variable evaluates to the node.</span></span>  
        
        > ##### <span data-ttu-id="5e346-283">図 16</span><span class="sxs-lookup"><span data-stu-id="5e346-283">Figure 16</span></span>  
        > <span data-ttu-id="5e346-284">Temp1 式の結果</span><span class="sxs-lookup"><span data-stu-id="5e346-284">The result of the temp1 expression</span></span>  
        > ![Temp1 式の結果][ImageResultTemp1]  
        
### <span data-ttu-id="5e346-286">JS パスをコピーする</span><span class="sxs-lookup"><span data-stu-id="5e346-286">Copy JS path</span></span>   

<span data-ttu-id="5e346-287">自動テストで参照する必要がある場合は、JavaScript のパスをノードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="5e346-287">Copy the JavaScript path to a node when you need to reference it in an automated test.</span></span>  

1.  <span data-ttu-id="5e346-288">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-288">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5e346-289">[ **JS パスのコピー**] で、**兄弟 Karamazov**を右クリックして [**検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5e346-289">Under **Copy JS path**, right-click **The Brothers Karamazov** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="5e346-290">DOM ツリーを右クリック `<li>The Brothers Karamazov</li>` して、[ **Copy**  >  **コピーコピー JS Path**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5e346-290">Right-click `<li>The Brothers Karamazov</li>` in the DOM Tree and select **Copy** > **Copy JS Path**.</span></span>  <span data-ttu-id="5e346-291">`document.querySelector()`ノードに解決される式がクリップボードにコピーされました。</span><span class="sxs-lookup"><span data-stu-id="5e346-291">A `document.querySelector()` expression that resolves to the node has been copied to your clipboard.</span></span>  
    1.  <span data-ttu-id="5e346-292">`Control` + `V` 式をコンソールに貼り付けるには、\ (Windows \) または `Command` + `V` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="5e346-292">Press `Control`+`V` \(Windows\) or `Command`+`V` \(macOS\) to paste the expression into the Console.</span></span>  
    1.  <span data-ttu-id="5e346-293">を押して `Enter` 式を評価します。</span><span class="sxs-lookup"><span data-stu-id="5e346-293">Press `Enter` to evaluate the expression.</span></span>
        
        > ##### <span data-ttu-id="5e346-294">図 17</span><span class="sxs-lookup"><span data-stu-id="5e346-294">Figure 17</span></span>  
        > <span data-ttu-id="5e346-295">JS パスの式をコピーした結果</span><span class="sxs-lookup"><span data-stu-id="5e346-295">The result of the Copy JS Path expression</span></span>  
        > ![JS パスの式をコピーした結果][ImageResultCopyJSPath]  
        
## <span data-ttu-id="5e346-297">DOM の中断の変更</span><span class="sxs-lookup"><span data-stu-id="5e346-297">Break on DOM changes</span></span>   

<span data-ttu-id="5e346-298">DevTools を使うと、JavaScript が DOM を変更したときにページの JavaScript を一時停止することができます。</span><span class="sxs-lookup"><span data-stu-id="5e346-298">DevTools enables you to pause the JavaScript of a page when the JavaScript modifies the DOM.</span></span>  

### <span data-ttu-id="5e346-299">属性の変更の中断</span><span class="sxs-lookup"><span data-stu-id="5e346-299">Break on attribute modifications</span></span>   

<span data-ttu-id="5e346-300">ノードの任意の属性を変更する JavaScript を一時停止する場合は、属性変更ブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="5e346-300">Use attribute modification breakpoints when you want to pause the JavaScript that causes any attribute of a node to change.</span></span>  

1.  <span data-ttu-id="5e346-301">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-301">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5e346-302">[**属性の変更を中断**] で、[ **Sauerkraut** ] を右クリックし、[**検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5e346-302">Under **Break on attribute modifications**, right-click **Sauerkraut** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="5e346-303">DOM ツリーで右クリック `<li id="target">Sauerkraut</li>` し、[属性**の変更を中断**] を選択し  >  **Attribute Modifications**ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-303">In the DOM Tree, right-click `<li id="target">Sauerkraut</li>` and select **Break On** > **Attribute Modifications**.</span></span>  <span data-ttu-id="5e346-304">このオプションが表示されない場合は、「[付録: 省略](#appendix-missing-options)可能なオプション」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e346-304">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see this option.</span></span>
        
        > ##### <span data-ttu-id="5e346-305">図18</span><span class="sxs-lookup"><span data-stu-id="5e346-305">Figure 18</span></span>  
        > <span data-ttu-id="5e346-306">属性の変更の中断</span><span class="sxs-lookup"><span data-stu-id="5e346-306">Break on attribute modifications</span></span>  
        > ![属性の変更の中断][ImageBreakAttributeModification]  
        
    1.  <span data-ttu-id="5e346-308">次の手順では、ページのコードを一時停止するボタンをクリックするように指示されます。</span><span class="sxs-lookup"><span data-stu-id="5e346-308">In the next step you are going to be instructed to click a button that pauses the code of the page.</span></span>  <span data-ttu-id="5e346-309">ページが一時停止されると、ページをスクロールすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="5e346-309">After the page is paused you are no longer able to scroll the page.</span></span>  <span data-ttu-id="5e346-310">**Resume Script** ![ ][ImageResumeScriptIcon] ページを再び表示できるようにするには、[スクリプト再開スクリプトの再開] をクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e346-310">You must click **Resume Script** ![Resume Script][ImageResumeScriptIcon] in order to make the page scrollable again.</span></span>
        
        > ##### <span data-ttu-id="5e346-311">図19</span><span class="sxs-lookup"><span data-stu-id="5e346-311">Figure 19</span></span>  
        > <span data-ttu-id="5e346-312">スクリプトの実行を再開する場所</span><span class="sxs-lookup"><span data-stu-id="5e346-312">Where to resume script running</span></span>  
        > ![スクリプトの実行を再開する場所][ImageResumeScript]  
        
    1.  <span data-ttu-id="5e346-314">上の [**背景の設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e346-314">Click the **Set Background** button above.</span></span>  <span data-ttu-id="5e346-315">これにより `style` 、ノードの属性がに設定され `background-color:thistle` ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-315">This sets the `style` attribute of the node to `background-color:thistle`.</span></span>  <span data-ttu-id="5e346-316">DevTools はページを一時停止し、属性が変更されたコードを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="5e346-316">DevTools pauses the page and highlights the code that caused the attribute to change.</span></span>  
    1.  <span data-ttu-id="5e346-317">**Resume Script** ![ ][ImageResumeScriptIcon] 前に説明したように、[スクリプト再開スクリプト] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e346-317">Click **Resume Script** ![Resume Script][ImageResumeScriptIcon], as mentioned earlier.</span></span>  
    
### <span data-ttu-id="5e346-318">ノード削除時の中断</span><span class="sxs-lookup"><span data-stu-id="5e346-318">Break on node removal</span></span>   

<span data-ttu-id="5e346-319">特定のノードが削除されたときに一時停止する場合は、ノード削除のブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="5e346-319">If you want to pause when a particular node is removed, use node removal breakpoints.</span></span>  

1.  <span data-ttu-id="5e346-320">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-320">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5e346-321">[**ノード削除時の中断**] で、[ **Neuromancer** ] を右クリックし、[**検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5e346-321">Under **Break on Node Removal**, right-click **Neuromancer** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="5e346-322">DOM ツリーで右クリック `<li id="target">Neuromancer</li>` し、[ノード**の削除時に中断**] を選択し  >  **Node Removal**ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-322">In the DOM Tree, right-click `<li id="target">Neuromancer</li>` and select **Break On** > **Node Removal**.</span></span>  <span data-ttu-id="5e346-323">このオプションが表示されない場合は、「[付録: 省略](#appendix-missing-options)可能なオプション」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e346-323">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see this option.</span></span>  
    1.  <span data-ttu-id="5e346-324">上の [**削除**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e346-324">Click the **Delete** button above.</span></span>  <span data-ttu-id="5e346-325">DevTools はページを一時停止し、ノードの削除を引き起こしたコードを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="5e346-325">DevTools pauses the page and highlights the code that caused the node to be removed.</span></span>  
    1.  <span data-ttu-id="5e346-326">[**スクリプト** ![ 再開スクリプトの再開] をクリックし ][ImageResumeScriptIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-326">Click **Resume Script** ![Resume Script][ImageResumeScriptIcon].</span></span>  
    
### <span data-ttu-id="5e346-327">サブツリーの変更の中断</span><span class="sxs-lookup"><span data-stu-id="5e346-327">Break on subtree modifications</span></span>   

<span data-ttu-id="5e346-328">ノードにサブツリーの変更のブレークポイントを配置すると、ノードの子孫が追加または削除されると、DevTools によってページが一時停止します。</span><span class="sxs-lookup"><span data-stu-id="5e346-328">After you put a subtree modification breakpoint on a node, DevTools pauses the page when any of the descendants of the node are added or removed.</span></span>  

1.  <span data-ttu-id="5e346-329">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-329">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5e346-330">[**サブツリーの変更の中断**] で、[**詳細] の炎**を右クリックして [**検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5e346-330">Under **Break on Subtree Modifications**, right-click **A Fire Upon The Deep** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="5e346-331">DOM ツリーで、上のノードである右クリック `<ul id="target">` `<li>A Fire Upon the Deep</li>` し、[サブツリーの変更を**中断**] を選択し  >  **Subtree Modifications**ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-331">In the DOM Tree, right-click `<ul id="target">`, which is the node above `<li>A Fire Upon the Deep</li>`, and select **Break On** > **Subtree Modifications**.</span></span>  <span data-ttu-id="5e346-332">このオプションが表示されない場合は、「[付録: 省略](#appendix-missing-options)可能なオプション」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e346-332">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see this option.</span></span>  
    1.  <span data-ttu-id="5e346-333">[**子の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e346-333">Click **Add Child**.</span></span>  <span data-ttu-id="5e346-334">ノードがリストに追加されたため、コードは一時停止し `<li>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-334">The code pauses because a `<li>` node was added to the list.</span></span>  
    1.  <span data-ttu-id="5e346-335">[**スクリプト** ![ 再開スクリプトの再開] をクリックし ][ImageResumeScriptIcon] ます。</span><span class="sxs-lookup"><span data-stu-id="5e346-335">Click **Resume Script** ![Resume Script][ImageResumeScriptIcon].</span></span>  
    
## <span data-ttu-id="5e346-336">次のステップ</span><span class="sxs-lookup"><span data-stu-id="5e346-336">Next steps</span></span>   

<span data-ttu-id="5e346-337">これは、DevTools の DOM 関連のほとんどの機能について説明しています。</span><span class="sxs-lookup"><span data-stu-id="5e346-337">That covers most of the DOM-related features in DevTools.</span></span>  <span data-ttu-id="5e346-338">残りの部分については、DOM ツリーのノードを右クリックし、このチュートリアルで説明していないその他のオプションを試してみることができます。</span><span class="sxs-lookup"><span data-stu-id="5e346-338">You are able to discover the rest of them by right-clicking nodes in the DOM Tree and experimenting with the other options that were not covered in this tutorial.</span></span>  <span data-ttu-id="5e346-339">「[要素パネルのショートカットキー][DevToolsShortcutsElements]」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5e346-339">See also [Elements panel keyboard shortcuts][DevToolsShortcutsElements].</span></span>  

<span data-ttu-id="5e346-340">[Microsoft Edge DevTools のホームページ][MicrosoftEdgeDevTools]をチェックして、devtools で実行できるその他の情報をすべて見つけてください。</span><span class="sxs-lookup"><span data-stu-id="5e346-340">Check out the [Microsoft Edge DevTools homepage][MicrosoftEdgeDevTools] to discover everything else you are able to do with DevTools.</span></span>  

<!--See [Community](../index#community) if you want to contact the DevTools team or get help from the DevTools community.  -->  



## <span data-ttu-id="5e346-341">付録: HTML と DOM の比較</span><span class="sxs-lookup"><span data-stu-id="5e346-341">Appendix: HTML versus the DOM</span></span>   

<span data-ttu-id="5e346-342">このセクションでは、HTML と DOM の違いについて簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="5e346-342">This section quickly explains the difference between HTML and the DOM.</span></span>  

<span data-ttu-id="5e346-343">Web ブラウザーを使ってページを要求すると、サーバーは次のような HTML を返します。</span><span class="sxs-lookup"><span data-stu-id="5e346-343">When you use a web browser to request a page, the server returns HTML like this:</span></span>  

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

<span data-ttu-id="5e346-344">ブラウザーは HTML を解析し、次のようなオブジェクトのツリーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5e346-344">The browser parses the HTML and creates a tree of objects like this:</span></span>  

```dom
html
  head
    title
  body
    h1
    p
    script
```  

<span data-ttu-id="5e346-345">ページのコンテンツを表す、このオブジェクトのツリーは DOM と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="5e346-345">This tree of objects, or nodes, representing the content of the page is called the DOM.</span></span>  <span data-ttu-id="5e346-346">HTML と同じように見えますが、HTML の下部で参照されているスクリプトが次のコードを実行したとします。</span><span class="sxs-lookup"><span data-stu-id="5e346-346">Right now it looks the same as the HTML, but suppose that the script referenced at the bottom of the HTML runs this code:</span></span>  

```javascript
const h1 = document.querySelector('h1');
h1.parentElement.removeChild(h1);
const p = document.createElement('p');
p.textContent = 'Wildcard!';
document.body.appendChild(p);
```  

<span data-ttu-id="5e346-347">このコードは、 `h1` ノードを削除し、別の `p` ノードを DOM に追加します。</span><span class="sxs-lookup"><span data-stu-id="5e346-347">That code removes the `h1` node and adds another `p` node to the DOM.</span></span>  <span data-ttu-id="5e346-348">完全な DOM は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5e346-348">The complete DOM now looks like this:</span></span>  

```dom
html
  head
    title
  body
    p
    script
    p
```  

<span data-ttu-id="5e346-349">ページの HTML が DOM とは異なるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5e346-349">The HTML for the page is now different than the DOM.</span></span>  <span data-ttu-id="5e346-350">つまり、HTML は初期ページコンテンツを表し、DOM は現在のページコンテンツを表します。</span><span class="sxs-lookup"><span data-stu-id="5e346-350">In other words, HTML represents initial page content, and the DOM represents current page content.</span></span>  <span data-ttu-id="5e346-351">JavaScript がノードを追加、削除、または編集すると、DOM は HTML とは異なります。</span><span class="sxs-lookup"><span data-stu-id="5e346-351">When JavaScript adds, removes, or edits nodes, the DOM becomes different than the HTML.</span></span>  

<span data-ttu-id="5e346-352">詳細について[は、「DOM の概要][MDNIntroductionToDOM]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e346-352">See [Introduction to the DOM][MDNIntroductionToDOM] to learn more.</span></span>  

<!--
## Appendix: Scroll into view   

This is a continuation of the [Scroll into view](#scroll-into-view) section.  Follow the instructions below to complete the section.  

1.  The `<li>Magritte</li>` node should still be selected in your DOM Tree.  If not, go back to [Scroll into view](#scroll-into-view) and start over.  
1.  Right-click the `<li>Magritte</li>` node and select **Scroll into view**.  Your viewport scrolls back up so that you may see the **Magritte** node.  See [Appendix: Missing options](#appendix-missing-options) if you are not able to see the **Scroll into view** option.
    
    > ##### Figure 19  
    > Scroll into view  
    > ![Scroll into view][ImageScrollView]  
    -->  

## <span data-ttu-id="5e346-353">付録: オプションが表示されない</span><span class="sxs-lookup"><span data-stu-id="5e346-353">Appendix: Missing options</span></span>   

<span data-ttu-id="5e346-354">このチュートリアルで説明する多くの手順では、DOM ツリーのノードを右クリックし、ポップアップ表示されるコンテキストメニューからオプションを選択するように指示されています。</span><span class="sxs-lookup"><span data-stu-id="5e346-354">Many of the instructions in this tutorial instruct you to right-click a node in the DOM Tree and then select an option from the context menu that pops up.</span></span>  <span data-ttu-id="5e346-355">コンテキストメニューに [指定] オプションが表示されない場合は、ノードのテキストを右クリックしてみてください。</span><span class="sxs-lookup"><span data-stu-id="5e346-355">If you do not see the specified option in the context menu, try right-clicking away from the node text.</span></span>  

> ##### <span data-ttu-id="5e346-356">図20</span><span class="sxs-lookup"><span data-stu-id="5e346-356">Figure 20</span></span>  
> <span data-ttu-id="5e346-357">すべてのオプションが表示されない場合は、ここをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e346-357">Where to click if you are not seeing all the options</span></span>  
> ![すべてのオプションが表示されない場合は、ここをクリックします。][ImageNotSeeingAllOptions]  

<!-- image links -->  

[ImageInspectIcon]: /microsoft-edge/devtools-guide-chromium/media/inspect-icon.msft.png  
[ImageResumeScriptIcon]: /microsoft-edge/devtools-guide-chromium/media/resume-script-icon.msft.png  

[ImageInspectingNode]: /microsoft-edge/devtools-guide-chromium/media/dom-glitch-dom-examples-michelangelo-inspect.msft.png "図 1: ノードを検査する"  
[ImageHighlightingMichelangeloNode]: /microsoft-edge/devtools-guide-chromium/media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png "図 2: Michelangelo ノードの強調表示"  
[ImageInspect]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-select-element-page-inspect.msft.png "図 3: [検査] アイコン"  
[ImageInspectingRingoNode]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png "図 4: Ringo ノードを調べる"  
[ImageInspectingUlNode]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png "図 5: ul ノードの検査"  
[ImageScrollView]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png "図 6: スクロールして表示する"  
[ImageHighlightingQuerySearchBar]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-search-nodes-highlight.msft.png "図 7: 検索バーでクエリを強調表示する"  
[ImageEditingText]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-edit-content.msft.png "図 8: テキストを編集する"  
[ImageEditingNode]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-edit-attributes-highlighted.msft.png "図 9: ノードを編集する"  
[ImageAddingStyleAttributeNode]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-edit-attributes-inline-css.msft.png "図 10: スタイル属性をノードに追加する"  
[ImageChangingNodeButton]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-edit-node-type-button.msft.png "図 11: ノードの種類をボタンに変更する"  
[ImageDraggingNodeTopList]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-reorder-dom-nodes.msft.png "図 12: ノードを一覧の一番上にドラッグする"  
[ImageNodeDomTreeAfterHidden]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-hide-a-node.msft.png "図 13: 非表示になった後のノードが DOM ツリーでどのように見えるか"  
[ImageFirstConsole]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png "図 14: 本体の最初の $0 の式の結果"  
[ImageSecondConsole]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png "図 15: 本体の2つ目の $0 式の結果"  
[ImageResultTemp1]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png "図 16: temp1 式の結果"  
[ImageResultCopyJSPath]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png "図 17: コピーされた JS パス式の結果"  
[ImageBreakAttributeModification]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png "図 18: 属性の変更時の中断"  
[ImageResumeScript]: /microsoft-edge/devtools-guide-chromium/media/dom-break-attribute-modifications-sources-paused-on.msft.png "図 19: スクリプトの実行を再開する場所"  
[ImageNotSeeingAllOptions]: /microsoft-edge/devtools-guide-chromium/media/dom-elements-highlighted-right-click-right-side.msft.png "図 20: すべてのオプションが表示されていない場合は、ここをクリックします。"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge \ (Chromium) 開発者ツール"  
[DevToolsCssGetStarted]: /microsoft-edge/devtools-guide-chromium/css/index "CSS の表示と変更を始める"  
[DevToolsShortcutsElements]: /microsoft-edge/devtools-guide-chromium/shortcuts#elements-panel-keyboard-shortcuts "要素パネルのキーボードショートカット-Microsoft Edge DevTools のショートカットキー"  

[GlitchDomExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/dom "Microsoft Edge (Chromium) DevTools DOM の例 |故障"

[MDNIntroductionToDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM の概要 |MDN"  

> [!NOTE]
> <span data-ttu-id="5e346-384">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="5e346-384">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="5e346-385">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/dom/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome devtools & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="5e346-385">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/dom/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools & Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="5e346-387">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="5e346-387">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
