---
title: DOM の表示と変更を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 6d41b072a8bd19ae728cc02b43eb2f843d91b332
ms.sourcegitcommit: 2fa65cca74c5214601900579c0ce9f946ad8a27e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "10991203"
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





# <span data-ttu-id="5bc09-103">DOM の表示と変更を開始する</span><span class="sxs-lookup"><span data-stu-id="5bc09-103">Get started with viewing and changing the DOM</span></span>   



<span data-ttu-id="5bc09-104">Microsoft Edge DevTools を使用して、ページの DOM を表示して変更する基本的な方法については、次の対話型チュートリアルを実行してください。</span><span class="sxs-lookup"><span data-stu-id="5bc09-104">Complete these interactive tutorials to learn the basics of viewing and changing the DOM of a page using Microsoft Edge DevTools.</span></span>  

<span data-ttu-id="5bc09-105">このチュートリアルでは、DOM と HTML の違いを知っていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="5bc09-105">This tutorial assumes that you know the difference between the DOM and HTML.</span></span>  <span data-ttu-id="5bc09-106">説明については [、「付録: HTML と DOM の比較](#appendix-html-versus-the-dom) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bc09-106">See [Appendix: HTML versus the DOM](#appendix-html-versus-the-dom) for an explanation.</span></span>  

## <span data-ttu-id="5bc09-107">DOM の例を開く</span><span class="sxs-lookup"><span data-stu-id="5bc09-107">Open DOM examples</span></span>  

1.  <span data-ttu-id="5bc09-108">`Control`\ (Windows \) または `Command` \ (macOS \) を保持し、[ **DOM の例**] をクリックして新しいタブで開きます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-108">Hold `Control` \(Windows\) or `Command` \(macOS\) and click **DOM Examples** to open in a new tab.</span></span>  
    
    [<span data-ttu-id="5bc09-109">DOM の例</span><span class="sxs-lookup"><span data-stu-id="5bc09-109">DOM Examples</span></span>][GlitchDomExamples]  
    
## <span data-ttu-id="5bc09-110">DOM ノードの表示</span><span class="sxs-lookup"><span data-stu-id="5bc09-110">View DOM nodes</span></span>   

<span data-ttu-id="5bc09-111">[要素] パネルの DOM ツリーでは、DevTools で DOM に関連するすべてのアクティビティを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-111">The DOM Tree of the Elements panel is where you do all DOM-related activities in DevTools.</span></span>  

### <span data-ttu-id="5bc09-112">ノードを検査する</span><span class="sxs-lookup"><span data-stu-id="5bc09-112">Inspect a node</span></span>   

<span data-ttu-id="5bc09-113">特定の DOM ノードに関心がある場合は、[ **検査** ] を使うと、devtools をすばやく開いてそのノードを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-113">When you are interested in a particular DOM node, **Inspect** is a fast way to open DevTools and investigate that node.</span></span>  

1.  <span data-ttu-id="5bc09-114">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-114">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5bc09-115">[ **ノードの検査**] で、[ **Michelangelo** ] を右クリックし、[ **検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-115">Under **Inspect a Node**, right-click **Michelangelo** and select **Inspect**.</span></span>  
    
    :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png":::
       <span data-ttu-id="5bc09-117">ノードを検査する</span><span class="sxs-lookup"><span data-stu-id="5bc09-117">Inspect a node</span></span>  
    :::image-end:::  
    
    1.  <span data-ttu-id="5bc09-118">DevTools の [ **要素** ] パネルが開きます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-118">The **Elements** panel of DevTools opens.</span></span>  `<li>Michelangelo</li>` <span data-ttu-id="5bc09-119">が強調表示さ **れてい**ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-119">is highlighted in the **DOM Tree**.</span></span>  
        
        :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png" alt-text="Michelangelo ノードを強調表示する" lightbox="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png":::
           <span data-ttu-id="5bc09-121">ノードを強調表示する `Michelangelo`</span><span class="sxs-lookup"><span data-stu-id="5bc09-121">Highlight the `Michelangelo` node</span></span>  
        :::image-end:::  
        
        1.  <span data-ttu-id="5bc09-122">**Inspect** ![ ][ImageInspectIcon] Devtools の左上隅にある検査 (検査 \) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5bc09-122">Click the **Inspect** \(![Inspect][ImageInspectIcon]\) icon in the top-left corner of DevTools.</span></span>  
            
            :::image type="complex" source="../media/dom-elements-highlighted-select-element-page-inspect.msft.png" alt-text="[検査] アイコン" lightbox="../media/dom-elements-highlighted-select-element-page-inspect.msft.png":::
               <span data-ttu-id="5bc09-124">[ **検査** ] アイコン</span><span class="sxs-lookup"><span data-stu-id="5bc09-124">The **Inspect** icon</span></span>  
            :::image-end:::  
            
1.  <span data-ttu-id="5bc09-125">[ **ノードの検査**] で、[ **東京** ] のテキストをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5bc09-125">Under **Inspect a Node**, click the **Tokyo** text.</span></span>  <span data-ttu-id="5bc09-126">これで、 `<li>Tokyo</li>` DOM ツリーで強調表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5bc09-126">Now, `<li>Tokyo</li>` is highlighted in the DOM Tree.</span></span>  

<span data-ttu-id="5bc09-127">ノードの [検査] は、ノードのスタイルを表示して変更するための最初の手順でもあります。</span><span class="sxs-lookup"><span data-stu-id="5bc09-127">Inspecting a node is also the first step towards viewing and changing the styles of a node.</span></span>  <span data-ttu-id="5bc09-128">「 [CSS の表示と変更」の「使用を開始する」を][DevToolsCssGetStarted]参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bc09-128">See [Get Started With Viewing And Changing CSS][DevToolsCssGetStarted].</span></span>  

### <span data-ttu-id="5bc09-129">キーボードで DOM ツリー内を移動する</span><span class="sxs-lookup"><span data-stu-id="5bc09-129">Navigate the DOM Tree with a keyboard</span></span>   

<span data-ttu-id="5bc09-130">DOM ツリーでノードを選択すると、DOM ツリーをキーボードで移動できます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-130">Once you have selected a node in the DOM Tree, you may navigate the DOM Tree with your keyboard.</span></span>  

1.  <span data-ttu-id="5bc09-131">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-131">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5bc09-132">[ **DOM ツリーのキーボードでの操作**] で、[ **Ringo** ] を右クリックし、[ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-132">Under **Navigate the DOM Tree with a Keyboard**, right-click **Ringo** and select **Inspect**.</span></span>  `<li>Ringo</li>` <span data-ttu-id="5bc09-133">が選択されます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-133">is selected in the DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png" alt-text="Ringo ノードを検査する" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png":::
       <span data-ttu-id="5bc09-135">ノードを検査する `Ringo`</span><span class="sxs-lookup"><span data-stu-id="5bc09-135">Inspect the `Ringo` node</span></span>  
    :::image-end:::  
    
    1.  <span data-ttu-id="5bc09-136">`Up`方向キーを2回押します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-136">Press the `Up` arrow key 2 times.</span></span>  `<ul>` <span data-ttu-id="5bc09-137"> がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-137">is selected.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png" alt-text="Ul ノードを検査する" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png":::
           <span data-ttu-id="5bc09-139">ノードを検査する `ul`</span><span class="sxs-lookup"><span data-stu-id="5bc09-139">Inspect the `ul` node</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="5bc09-140">`Left`方向キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-140">Press the `Left` arrow key.</span></span>  <span data-ttu-id="5bc09-141">`<ul>`リストが折りたたまれます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-141">The `<ul>` list collapses.</span></span>  
    1.  <span data-ttu-id="5bc09-142">`Left`もう一度方向キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-142">Press the `Left` arrow key again.</span></span>  <span data-ttu-id="5bc09-143">ノードの親 `<ul>` が選択されます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-143">The parent of the `<ul>` node is selected.</span></span>  <span data-ttu-id="5bc09-144">この場合は、 `<div>` ID を使用し `navigate-the-dom-tree-with-a-keyboard-1` ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-144">In this case it is the `<div>` with the ID `navigate-the-dom-tree-with-a-keyboard-1`.</span></span>  
    1.  <span data-ttu-id="5bc09-145">`Down`方向キーを2回押して、折りたたんだリストをもう一度選択し `<ul>` ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-145">Press the `Down` arrow key 2 times so that you have re-selected the `<ul>` list that you just collapsed.</span></span>  <span data-ttu-id="5bc09-146">次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5bc09-146">It should look like this:</span></span> `<ul>... </ul>`  
    1.  <span data-ttu-id="5bc09-147">`Right`方向キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-147">Press the `Right` arrow key.</span></span>  <span data-ttu-id="5bc09-148">リストが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-148">The list expands.</span></span>  

### <span data-ttu-id="5bc09-149">スクロールして表示する</span><span class="sxs-lookup"><span data-stu-id="5bc09-149">Scroll into view</span></span>   

<span data-ttu-id="5bc09-150">DOM ツリーを表示しているときに、現在ビューポート内にない DOM ノードに興味を持っていることがあります。</span><span class="sxs-lookup"><span data-stu-id="5bc09-150">When viewing the DOM Tree, you may find yourself interested in a DOM node that is not currently in the viewport.</span></span>  <span data-ttu-id="5bc09-151">たとえば、ページの一番下までスクロールして、ページの上部にあるノードに関心を持っているとし `<h1>` ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-151">For example, suppose that you scrolled to the bottom of the page, and you are interested in the `<h1>` node at the top of the page.</span></span>  <span data-ttu-id="5bc09-152">**ビューをスクロール** すると、ビューポートをすばやく移動して、ノードを表示できます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-152">**Scroll into view** lets you quickly reposition the viewport so that you are able to see the node.</span></span>  

1.  <span data-ttu-id="5bc09-153">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-153">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5bc09-154">[ **スクロール**して表示] で、[ **Magritte** ] を右クリックし、[ **検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-154">Under **Scroll into View**, right-click **Magritte** and select **Inspect**.</span></span>  
1.  <span data-ttu-id="5bc09-155">DOM の [例] ページの一番下までスクロールします。</span><span class="sxs-lookup"><span data-stu-id="5bc09-155">Scroll to the bottom of the DOM Examples page.</span></span>  
1.  <span data-ttu-id="5bc09-156">`<li>Magritte</li>`それでも、ノードは DOM ツリーで選択されます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-156">The `<li>Magritte</li>` node should still be selected in your DOM Tree.</span></span>  <span data-ttu-id="5bc09-157">表示されていない場合は、戻って、もう一度 [表示](#scroll-into-view) してみてください。</span><span class="sxs-lookup"><span data-stu-id="5bc09-157">If not, go back to [Scroll into view](#scroll-into-view) and start over.</span></span>  
1.  <span data-ttu-id="5bc09-158">ノードを右クリックし `<li>Magritte</li>` て、[ **ビューにスクロール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-158">Right-click the `<li>Magritte</li>` node and select **Scroll into view**.</span></span>  <span data-ttu-id="5bc09-159">ビューポートがスクロールして、 **Magritte** ノードが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="5bc09-159">Your viewport scrolls back up so that you may see the **Magritte** node.</span></span>  <span data-ttu-id="5bc09-160">[スクロールして**表示**する] オプションが表示されない場合は、「[付録: オプションが見つから](#appendix-missing-options)ない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bc09-160">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see the **Scroll into view** option.</span></span>
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="スクロールして表示する" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       **<span data-ttu-id="5bc09-162">スクロールして表示する</span><span class="sxs-lookup"><span data-stu-id="5bc09-162">Scroll into view</span></span>**  
    :::image-end:::  

### <span data-ttu-id="5bc09-163">ノードを検索する</span><span class="sxs-lookup"><span data-stu-id="5bc09-163">Search for nodes</span></span>   

<span data-ttu-id="5bc09-164">DOM ツリーは、文字列、CSS セレクター、または XPath セレクターで検索できます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-164">You may search the DOM Tree by string, CSS selector, or XPath selector.</span></span>  

1.  <span data-ttu-id="5bc09-165">カーソルを [ **要素** ] パネルにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="5bc09-165">Focus your cursor on the **Elements** panel.</span></span>  
1.  <span data-ttu-id="5bc09-166">`Control` + `F` \ (Windows \) または `Command` + `F` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-166">Press `Control`+`F` \(Windows\) or `Command`+`F` \(macOS\).</span></span>  <span data-ttu-id="5bc09-167">検索バーは DOM ツリーの下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-167">The Search bar opens at the bottom of the DOM Tree.</span></span>  
1.  <span data-ttu-id="5bc09-168">「`The Moon is a Harsh Mistress`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-168">Type `The Moon is a Harsh Mistress`.</span></span>  <span data-ttu-id="5bc09-169">DOM ツリーの最後の文が強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="5bc09-169">The last sentence is highlighted in the DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-search-nodes-highlight.msft.png" alt-text="検索バーでクエリを強調表示する" lightbox="../media/dom-elements-highlighted-search-nodes-highlight.msft.png":::
       <span data-ttu-id="5bc09-171">検索バーでクエリを強調表示する</span><span class="sxs-lookup"><span data-stu-id="5bc09-171">Highlight the query in the Search bar</span></span>  
    :::image-end:::  
    
<span data-ttu-id="5bc09-172">上で説明したように、検索バーは CSS と XPath のセレクターもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5bc09-172">As mentioned above, the Search bar also supports CSS and XPath selectors.</span></span>  

## <span data-ttu-id="5bc09-173">DOM を編集する</span><span class="sxs-lookup"><span data-stu-id="5bc09-173">Edit the DOM</span></span>   

<span data-ttu-id="5bc09-174">その場で DOM を編集して、それらの変更がページにどのように影響するかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-174">You may edit the DOM on the fly and see how those changes affect the page.</span></span>  

### <span data-ttu-id="5bc09-175">コンテンツを編集する</span><span class="sxs-lookup"><span data-stu-id="5bc09-175">Edit content</span></span>   

<span data-ttu-id="5bc09-176">ノードのコンテンツを編集するには、DOM ツリーでコンテンツをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="5bc09-176">To edit the content of a node, double-click the content in the DOM Tree.</span></span>  

1.  <span data-ttu-id="5bc09-177">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-177">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5bc09-178">[ **コンテンツの編集**] で [ **micん le** ] を右クリックし、[ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-178">Under **Edit Content**, right-click **Michelle** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="5bc09-179">DOM ツリーで、をダブルクリック `Michelle` します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-179">In the DOM Tree, double-click `Michelle`.</span></span>  <span data-ttu-id="5bc09-180">つまり、との間のテキストをダブルクリック `<li>` し `</li>` ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-180">In other words, double-click the text between `<li>` and `</li>`.</span></span>  <span data-ttu-id="5bc09-181">テキストが強調表示され、選択されていることが示されます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-181">The text is highlighted to indicate that it is selected.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-content.msft.png" alt-text="テキストを編集する" lightbox="../media/dom-elements-highlighted-edit-content.msft.png":::
           <span data-ttu-id="5bc09-183">テキストを編集する</span><span class="sxs-lookup"><span data-stu-id="5bc09-183">Edit the text</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="5bc09-184">を削除し `Michelle` て入力し、 `Leela` enter キーを押して `Enter` 変更を確定します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-184">Delete `Michelle`, type `Leela`, then press `Enter` to confirm the change.</span></span>  <span data-ttu-id="5bc09-185">DOM 内のテキストは、 **MicLeela le**から**Leela**に変更されます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-185">The text in the DOM changes from **Michelle** to **Leela**.</span></span>  

### <span data-ttu-id="5bc09-186">属性を編集する</span><span class="sxs-lookup"><span data-stu-id="5bc09-186">Edit attributes</span></span>   

<span data-ttu-id="5bc09-187">属性を編集するには、属性の名前または値をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="5bc09-187">To edit attributes, double-click the attribute name or value.</span></span>  <span data-ttu-id="5bc09-188">手順に従って、ノードに属性を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-188">Follow the instructions to learn how to add attributes to a node.</span></span>  

1.  <span data-ttu-id="5bc09-189">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-189">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5bc09-190">[ **属性の編集**] で、[ **Howard** ] を右クリックし、[ **検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-190">Under **Edit Attributes**, right-click **Howard** and select **Inspect**.</span></span>  
1.  <span data-ttu-id="5bc09-191">ダブルクリック `<li>` します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-191">Double-click `<li>`.</span></span>  <span data-ttu-id="5bc09-192">テキストが強調表示され、ノードが選択されていることが示されます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-192">The text is highlighted to indicate that the node is selected.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png" alt-text="ノードを編集する" lightbox="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png":::
       <span data-ttu-id="5bc09-194">ノードを編集する</span><span class="sxs-lookup"><span data-stu-id="5bc09-194">Edit the node</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="5bc09-195">方向キーを押して、スペースを追加し、 `Right` 「」と入力して `style="background-color:gold"` 、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-195">Press the `Right` arrow key, add a space, type `style="background-color:gold"`, and then press `Enter`.</span></span>  <span data-ttu-id="5bc09-196">ノードの背景色が金色に変わります。</span><span class="sxs-lookup"><span data-stu-id="5bc09-196">The background color of the node changes to gold.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png" alt-text="ノードにスタイル属性を追加する" lightbox="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png":::
       <span data-ttu-id="5bc09-198">`style`ノードに属性を追加する</span><span class="sxs-lookup"><span data-stu-id="5bc09-198">Add a `style` attribute to the node</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="5bc09-199">ノードの種類を編集する</span><span class="sxs-lookup"><span data-stu-id="5bc09-199">Edit node type</span></span>   

<span data-ttu-id="5bc09-200">ノードの種類を編集するには、型をダブルクリックし、新しい型を入力します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-200">To edit the type of a node, double-click the type and then type in the new type.</span></span>  

1.  <span data-ttu-id="5bc09-201">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-201">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5bc09-202">[ **ノードの種類の編集**] で、[ **Hank** ] を右クリックし、[ **検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-202">Under **Edit Node Type**, right-click **Hank** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="5bc09-203">ダブルクリック `<li>` します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-203">Double-click `<li>`.</span></span>  <span data-ttu-id="5bc09-204">テキスト `li` が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-204">The text `li` is highlighted.</span></span>  
    1.  <span data-ttu-id="5bc09-205">を削除し `li` て、を入力し `button` `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-205">Delete `li`, type `button`, then press `Enter`.</span></span>  <span data-ttu-id="5bc09-206">`<li>`ノードがノードに変わり `<button>` ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-206">The `<li>` node changes to a `<button>` node.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-node-type-button.msft.png" alt-text="ノードの種類を [ボタン] に変更する" lightbox="../media/dom-elements-highlighted-edit-node-type-button.msft.png":::
           <span data-ttu-id="5bc09-208">ノードの種類を変更する</span><span class="sxs-lookup"><span data-stu-id="5bc09-208">Change the node type to</span></span> `button`  
        :::image-end:::  
        
### <span data-ttu-id="5bc09-209">DOM ノードの順序を変更する</span><span class="sxs-lookup"><span data-stu-id="5bc09-209">Reorder DOM nodes</span></span>   

<span data-ttu-id="5bc09-210">ノードをドラッグして順序を変更します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-210">Drag nodes to reorder them.</span></span>  

1.  <span data-ttu-id="5bc09-211">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-211">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5bc09-212">[ **DOM ノードの順序**変更] で、[ **Elvis Presley** ] を右クリックし、[ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-212">Under **Reorder DOM Nodes**, right-click **Elvis Presley** and select **Inspect**.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="5bc09-213">これは、リスト内の最後のアイテムです。</span><span class="sxs-lookup"><span data-stu-id="5bc09-213">It is the last item in the list.</span></span>  
    
    1.  <span data-ttu-id="5bc09-214">DOM ツリーで、 `<li>Elvis Presley</li>` 一覧の一番上までドラッグします。</span><span class="sxs-lookup"><span data-stu-id="5bc09-214">In the DOM Tree, drag `<li>Elvis Presley</li>` to the top of the list.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-reorder-dom-nodes.msft.png" alt-text="ノードを一覧の一番上にドラッグする" lightbox="../media/dom-elements-reorder-dom-nodes.msft.png":::
           <span data-ttu-id="5bc09-216">ノードを一覧の一番上にドラッグする</span><span class="sxs-lookup"><span data-stu-id="5bc09-216">Drag the node to the top of the list</span></span>  
        :::image-end:::  
        
### <span data-ttu-id="5bc09-217">強制状態</span><span class="sxs-lookup"><span data-stu-id="5bc09-217">Force state</span></span>   

<span data-ttu-id="5bc09-218">ノードは、、、、、などの状態に保つことができ `:active` `:hover` `:focus` `:visited` `:focus-within` ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-218">You are able to force nodes to remain in states including `:active`, `:hover`, `:focus`, `:visited`, and `:focus-within`.</span></span>  

1.  <span data-ttu-id="5bc09-219">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-219">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5bc09-220">[ **状態の強制**] で、 **その中の閣下**をポイントします。</span><span class="sxs-lookup"><span data-stu-id="5bc09-220">Under **Force state**, hover over **The Lord of the Flies**.</span></span>  <span data-ttu-id="5bc09-221">背景色がオレンジ色になります。</span><span class="sxs-lookup"><span data-stu-id="5bc09-221">The background color becomes orange.</span></span>  
    1.  <span data-ttu-id="5bc09-222">**フライの閣下**を右クリックして、[**検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-222">Right-click **The Lord of the Flies** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="5bc09-223">右クリック `<li class="demo--hover">The Lord of the Flies</li>` し、[**状態の強制**  >  **: hover**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-223">Right-click `<li class="demo--hover">The Lord of the Flies</li>` and select **Force State** > **:hover**.</span></span>  <span data-ttu-id="5bc09-224">このオプションが表示されない場合は、「 [付録: オプション](#appendix-missing-options) を表示しない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bc09-224">See [Appendix: Missing options](#appendix-missing-options) if you do not see this option.</span></span>  <span data-ttu-id="5bc09-225">実際には、ノードの上にカーソルを置いていない場合でも、背景色はオレンジにとどまります。</span><span class="sxs-lookup"><span data-stu-id="5bc09-225">The background color remains orange even though you are not actually hovering over the node.</span></span>  

### <span data-ttu-id="5bc09-226">ノードを非表示にする</span><span class="sxs-lookup"><span data-stu-id="5bc09-226">Hide a node</span></span>   

<span data-ttu-id="5bc09-227">を押すと `H` 、ノードが非表示になります。</span><span class="sxs-lookup"><span data-stu-id="5bc09-227">Press `H` to hide a node.</span></span>  

1.  <span data-ttu-id="5bc09-228">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-228">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5bc09-229">[ **ノードを非表示にする**] で、[ **宛先] の星** を右クリックし、[ **検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-229">Under **Hide a node**, right-click **The Stars My Destination** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="5bc09-230">キーを押し `H` ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-230">Press the `H` key.</span></span>  <span data-ttu-id="5bc09-231">ノードが非表示になっています。</span><span class="sxs-lookup"><span data-stu-id="5bc09-231">The node is hidden.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-hide-a-node.msft.png" alt-text="非表示になった後のノードが DOM ツリーのどのように見えるか" lightbox="../media/dom-elements-highlighted-hide-a-node.msft.png":::
           <span data-ttu-id="5bc09-233">非表示になった後のノードが DOM ツリーのどのように見えるか</span><span class="sxs-lookup"><span data-stu-id="5bc09-233">What the node looks like in the DOM Tree after it is hidden</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="5bc09-234">キーを `H` もう一度押します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-234">Press the `H` key again.</span></span>  <span data-ttu-id="5bc09-235">ノードが再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-235">The node is shown again.</span></span>  

### <span data-ttu-id="5bc09-236">ノードを削除する</span><span class="sxs-lookup"><span data-stu-id="5bc09-236">Delete a node</span></span>   

<span data-ttu-id="5bc09-237">を押して `Delete` ノードを削除します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-237">Press `Delete` to delete a node.</span></span>  

1.  <span data-ttu-id="5bc09-238">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-238">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5bc09-239">[ **ノードの削除**] で、[ **Foundation** ] を右クリックし、[ **検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-239">Under **Delete a Node**, right-click **Foundation** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="5bc09-240">キーを押し `Delete` ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-240">Press the `Delete` key.</span></span>  <span data-ttu-id="5bc09-241">ノードが削除されます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-241">The node is deleted.</span></span>  
    1.  <span data-ttu-id="5bc09-242">`Control` + `Z` \ (Windows \) または `Command` + `Z` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-242">Press `Control`+`Z` \(Windows\) or `Command`+`Z` \(macOS\).</span></span>  <span data-ttu-id="5bc09-243">直前の操作が取り消され、ノードが再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-243">The last action is undone and the node reappears.</span></span>  

## <span data-ttu-id="5bc09-244">コンソールのアクセスノード</span><span class="sxs-lookup"><span data-stu-id="5bc09-244">Access nodes in the Console</span></span>   

<span data-ttu-id="5bc09-245">DevTools では、コンソールから DOM ノードにアクセスしたり、各デバイスへの JavaScript 参照を取得したりするためのショートカットキーをいくつか用意しています。</span><span class="sxs-lookup"><span data-stu-id="5bc09-245">DevTools provides a few shortcuts for accessing DOM nodes from the Console, or getting JavaScript references to each one.</span></span>  

### <span data-ttu-id="5bc09-246">$0 で現在選択されているノードを参照する</span><span class="sxs-lookup"><span data-stu-id="5bc09-246">Reference the currently-selected node with $0</span></span>   

<span data-ttu-id="5bc09-247">ノードを検査すると、 `== $0` ノードの横のテキストは、この変数を持つ本体でこのノードを参照できることを意味 `$0` します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-247">When you inspect a node, the `== $0` text next to the node means that you may reference this node in the Console with the variable `$0`.</span></span>  

1.  <span data-ttu-id="5bc09-248">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-248">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5bc09-249">[ **$0 で現在選択さ**れているノードを参照する] で、 **暗さの左側** を右クリックして [ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-249">Under **Reference the currently-selected node with $0**, right-click **The Left Hand of Darkness** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="5bc09-250">キーを押して、 `Escape` 本体の引き出しを開きます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-250">Press the `Escape` key to open the Console Drawer.</span></span>  
    1.  <span data-ttu-id="5bc09-251">キーを入力 `$0` して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-251">Type `$0` and press the `Enter` key.</span></span>  <span data-ttu-id="5bc09-252">この式の結果は、の `$0` 評価を示して `<li>The Left Hand of Darkness</li>` います。</span><span class="sxs-lookup"><span data-stu-id="5bc09-252">The result of the expression shows that `$0` evaluates to `<li>The Left Hand of Darkness</li>`.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png" alt-text="本体の最初の $0 式の結果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png":::
            <span data-ttu-id="5bc09-254">本体の最初の式の結果 `$0` **Console**</span><span class="sxs-lookup"><span data-stu-id="5bc09-254">The result of the first `$0` expression in the **Console**</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="5bc09-255">結果にマウスポインターを合わせます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-255">Hover over the result.</span></span>  <span data-ttu-id="5bc09-256">ビューポートで、ノードが強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="5bc09-256">The node is highlighted in the viewport.</span></span>  
    1.  <span data-ttu-id="5bc09-257">`<li>Dune</li>`DOM ツリー内をクリックし、 `$0` コンソールをもう一度入力して、 `Enter` もう一度押します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-257">Click `<li>Dune</li>` in the DOM Tree, type `$0` in the Console again, and then press `Enter` again.</span></span>  <span data-ttu-id="5bc09-258">次に、の `$0` ようにに評価さ `<li>Dune</li>` れます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-258">Now, `$0` evaluates to `<li>Dune</li>`.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png" alt-text="コンソールでの2番目の $0 式の結果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png":::
           <span data-ttu-id="5bc09-260">コンソールの2番目の `$0` 式の**Console**結果</span><span class="sxs-lookup"><span data-stu-id="5bc09-260">The result of the second `$0` expression in the **Console**</span></span>  
        :::image-end:::  
        
### <span data-ttu-id="5bc09-261">グローバル変数として保存する</span><span class="sxs-lookup"><span data-stu-id="5bc09-261">Store as global variable</span></span>   

<span data-ttu-id="5bc09-262">何度もノードを参照する必要がある場合は、それをグローバル変数として保存します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-262">If you need to refer back to a node many times, store it as a global variable.</span></span>  

1.  <span data-ttu-id="5bc09-263">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-263">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5bc09-264">[ **グローバル変数として保存**] で、 **大きなスリープ状態** を右クリックし、[ **検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-264">Under **Store as global variable**, right-click **The Big Sleep** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="5bc09-265">DOM ツリーを右クリック `<li>The Big Sleep</li>` して、[ **グローバル変数として保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-265">Right-click `<li>The Big Sleep</li>` in the DOM Tree and select **Store as global variable**.</span></span>  <span data-ttu-id="5bc09-266">このオプションが表示されない場合は、「 [付録: オプション](#appendix-missing-options) を表示しない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bc09-266">See [Appendix: Missing options](#appendix-missing-options) if you do not see this option.</span></span>  
    1.  <span data-ttu-id="5bc09-267">`temp1`コンソールに入力して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-267">Type `temp1` in the Console and then press `Enter`.</span></span>  <span data-ttu-id="5bc09-268">この式の結果は、変数がノードに評価されることを示します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-268">The result of the expression shows that the variable evaluates to the node.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png" alt-text="Temp1 式の結果" lightbox="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png":::
           <span data-ttu-id="5bc09-270">式の結果 `temp1`</span><span class="sxs-lookup"><span data-stu-id="5bc09-270">The result of the `temp1` expression</span></span>  
        :::image-end:::  
        
### <span data-ttu-id="5bc09-271">JS パスをコピーする</span><span class="sxs-lookup"><span data-stu-id="5bc09-271">Copy JS path</span></span>   

<span data-ttu-id="5bc09-272">自動テストで参照する必要がある場合は、JavaScript のパスをノードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="5bc09-272">Copy the JavaScript path to a node when you need to reference it in an automated test.</span></span>  

1.  <span data-ttu-id="5bc09-273">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-273">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5bc09-274">[ **JS パスのコピー**] で、 **兄弟 Karamazov** を右クリックして [ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-274">Under **Copy JS path**, right-click **The Brothers Karamazov** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="5bc09-275">DOM ツリーを右クリック `<li>The Brothers Karamazov</li>` して、[ **Copy**  >  **コピーコピー JS Path**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-275">Right-click `<li>The Brothers Karamazov</li>` in the DOM Tree and select **Copy** > **Copy JS Path**.</span></span>  <span data-ttu-id="5bc09-276">`document.querySelector()`ノードに解決される式がクリップボードにコピーされました。</span><span class="sxs-lookup"><span data-stu-id="5bc09-276">A `document.querySelector()` expression that resolves to the node has been copied to your clipboard.</span></span>  
    1.  <span data-ttu-id="5bc09-277">`Control` + `V` 式をコンソールに貼り付けるには、\ (Windows \) または `Command` + `V` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-277">Press `Control`+`V` \(Windows\) or `Command`+`V` \(macOS\) to paste the expression into the Console.</span></span>  
    1.  <span data-ttu-id="5bc09-278">を押して `Enter` 式を評価します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-278">Press `Enter` to evaluate the expression.</span></span>
        
        :::image type="complex" source="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png" alt-text="JS パスの式をコピーした結果" lightbox="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png":::
           <span data-ttu-id="5bc09-280">**JS パス**の式をコピーした結果</span><span class="sxs-lookup"><span data-stu-id="5bc09-280">The result of the **Copy JS Path** expression</span></span>  
        :::image-end:::  
        
## <span data-ttu-id="5bc09-281">DOM の中断の変更</span><span class="sxs-lookup"><span data-stu-id="5bc09-281">Break on DOM changes</span></span>   

<span data-ttu-id="5bc09-282">DevTools を使うと、JavaScript が DOM を変更したときにページの JavaScript を一時停止することができます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-282">DevTools enables you to pause the JavaScript of a page when the JavaScript modifies the DOM.</span></span>  

### <span data-ttu-id="5bc09-283">属性の変更の中断</span><span class="sxs-lookup"><span data-stu-id="5bc09-283">Break on attribute modifications</span></span>   

<span data-ttu-id="5bc09-284">ノードの任意の属性を変更する JavaScript を一時停止する場合は、属性変更ブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-284">Use attribute modification breakpoints when you want to pause the JavaScript that causes any attribute of a node to change.</span></span>  

1.  <span data-ttu-id="5bc09-285">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-285">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5bc09-286">[ **属性の変更を中断**] で、[ **Sauerkraut** ] を右クリックし、[ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-286">Under **Break on attribute modifications**, right-click **Sauerkraut** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="5bc09-287">DOM ツリーで右クリック `<li id="target">Sauerkraut</li>` し、[属性**の変更を中断**] を選択し  >  **Attribute Modifications**ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-287">In the DOM Tree, right-click `<li id="target">Sauerkraut</li>` and select **Break On** > **Attribute Modifications**.</span></span>  <span data-ttu-id="5bc09-288">このオプションが表示されない場合は、「 [付録: 省略](#appendix-missing-options) 可能なオプション」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bc09-288">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see this option.</span></span>
        
        :::image type="complex" source="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png" alt-text="属性の変更の中断" lightbox="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png":::
           **<span data-ttu-id="5bc09-290">属性の変更の中断</span><span class="sxs-lookup"><span data-stu-id="5bc09-290">Break on attribute modifications</span></span>**  
        :::image-end:::  
        
    1.  <span data-ttu-id="5bc09-291">次の手順では、ページのコードを一時停止するボタンをクリックするように指示されます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-291">In the next step you are going to be instructed to click a button that pauses the code of the page.</span></span>  <span data-ttu-id="5bc09-292">ページが一時停止されると、ページをスクロールすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="5bc09-292">After the page is paused you are no longer able to scroll the page.</span></span>  <span data-ttu-id="5bc09-293">**Resume Script** ![ ][ImageResumeScriptIcon] ページを再びスクロールできるようにするには、[スクリプトの再開] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5bc09-293">You must click **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\) in order to make the page scrollable again.</span></span>
        
        :::image type="complex" source="../media/dom-break-attribute-modifications-sources-paused-on.msft.png" alt-text="スクリプトの実行を再開する場所" lightbox="../media/dom-break-attribute-modifications-sources-paused-on.msft.png":::
           <span data-ttu-id="5bc09-295">スクリプトの実行を再開する場所</span><span class="sxs-lookup"><span data-stu-id="5bc09-295">Where to resume script running</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="5bc09-296">上の [ **背景の設定** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5bc09-296">Click the **Set Background** button above.</span></span>  <span data-ttu-id="5bc09-297">これにより `style` 、ノードの属性がに設定され `background-color:thistle` ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-297">This sets the `style` attribute of the node to `background-color:thistle`.</span></span>  <span data-ttu-id="5bc09-298">DevTools はページを一時停止し、属性が変更されたコードを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-298">DevTools pauses the page and highlights the code that caused the attribute to change.</span></span>  
    1.  <span data-ttu-id="5bc09-299">**Resume Script** ![ ][ImageResumeScriptIcon] 前に説明したように、[スクリプトの再開] をクリックします (スクリプトを再開します)。</span><span class="sxs-lookup"><span data-stu-id="5bc09-299">Click **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\), as mentioned earlier.</span></span>  
    
### <span data-ttu-id="5bc09-300">ノード削除時の中断</span><span class="sxs-lookup"><span data-stu-id="5bc09-300">Break on node removal</span></span>   

<span data-ttu-id="5bc09-301">特定のノードが削除されたときに一時停止する場合は、ノード削除のブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-301">If you want to pause when a particular node is removed, use node removal breakpoints.</span></span>  

1.  <span data-ttu-id="5bc09-302">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-302">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5bc09-303">[ **ノード削除時の中断**] で、[ **Neuromancer** ] を右クリックし、[ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-303">Under **Break on Node Removal**, right-click **Neuromancer** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="5bc09-304">DOM ツリーで右クリック `<li id="target">Neuromancer</li>` し、[ノード**の削除時に中断**] を選択し  >  **Node Removal**ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-304">In the DOM Tree, right-click `<li id="target">Neuromancer</li>` and select **Break On** > **Node Removal**.</span></span>  <span data-ttu-id="5bc09-305">このオプションが表示されない場合は、「 [付録: 省略](#appendix-missing-options) 可能なオプション」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bc09-305">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see this option.</span></span>  
    1.  <span data-ttu-id="5bc09-306">上の [ **削除** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5bc09-306">Click the **Delete** button above.</span></span>  <span data-ttu-id="5bc09-307">DevTools はページを一時停止し、ノードの削除を引き起こしたコードを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-307">DevTools pauses the page and highlights the code that caused the node to be removed.</span></span>  
    1.  <span data-ttu-id="5bc09-308">[ **スクリプトの再開** ] ![ をクリックします (スクリプトを再開し ][ImageResumeScriptIcon] ます)。</span><span class="sxs-lookup"><span data-stu-id="5bc09-308">Click **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\).</span></span>  
    
### <span data-ttu-id="5bc09-309">サブツリーの変更の中断</span><span class="sxs-lookup"><span data-stu-id="5bc09-309">Break on subtree modifications</span></span>   

<span data-ttu-id="5bc09-310">ノードにサブツリーの変更のブレークポイントを配置すると、ノードの子孫が追加または削除されると、DevTools によってページが一時停止します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-310">After you put a subtree modification breakpoint on a node, DevTools pauses the page when any of the descendants of the node are added or removed.</span></span>  

1.  <span data-ttu-id="5bc09-311">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-311">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="5bc09-312">[ **サブツリーの変更の中断**] で、[ **詳細] の炎** を右クリックして [ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-312">Under **Break on Subtree Modifications**, right-click **A Fire Upon The Deep** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="5bc09-313">DOM ツリーで、上のノードである右クリック `<ul id="target">` `<li>A Fire Upon the Deep</li>` し、[サブツリーの変更を**中断**] を選択し  >  **Subtree Modifications**ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-313">In the DOM Tree, right-click `<ul id="target">`, which is the node above `<li>A Fire Upon the Deep</li>`, and select **Break On** > **Subtree Modifications**.</span></span>  <span data-ttu-id="5bc09-314">このオプションが表示されない場合は、「 [付録: 省略](#appendix-missing-options) 可能なオプション」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bc09-314">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see this option.</span></span>  
    1.  <span data-ttu-id="5bc09-315">[ **子の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5bc09-315">Click **Add Child**.</span></span>  <span data-ttu-id="5bc09-316">ノードがリストに追加されたため、コードは一時停止し `<li>` ます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-316">The code pauses because a `<li>` node was added to the list.</span></span>  
    1.  <span data-ttu-id="5bc09-317">[ **スクリプトの再開** ] ![ をクリックします (スクリプトを再開し ][ImageResumeScriptIcon] ます)。</span><span class="sxs-lookup"><span data-stu-id="5bc09-317">Click **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\).</span></span>  
    
## <span data-ttu-id="5bc09-318">次のステップ</span><span class="sxs-lookup"><span data-stu-id="5bc09-318">Next steps</span></span>   

<span data-ttu-id="5bc09-319">これは、DevTools の DOM 関連のほとんどの機能について説明しています。</span><span class="sxs-lookup"><span data-stu-id="5bc09-319">That covers most of the DOM-related features in DevTools.</span></span>  <span data-ttu-id="5bc09-320">残りの部分については、DOM ツリーのノードを右クリックし、このチュートリアルで説明していないその他のオプションを試してみることができます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-320">You are able to discover the rest of them by right-clicking nodes in the DOM Tree and experimenting with the other options that were not covered in this tutorial.</span></span>  <span data-ttu-id="5bc09-321">「 [要素パネルのショートカットキー][DevToolsShortcutsElements]」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5bc09-321">See also [Elements panel keyboard shortcuts][DevToolsShortcutsElements].</span></span>  

<span data-ttu-id="5bc09-322">[Microsoft Edge DevTools のホームページ][MicrosoftEdgeDevTools]をチェックして、devtools で実行できるその他の情報をすべて見つけてください。</span><span class="sxs-lookup"><span data-stu-id="5bc09-322">Check out the [Microsoft Edge DevTools homepage][MicrosoftEdgeDevTools] to discover everything else you are able to do with DevTools.</span></span>  

<!--See [Community](../index#community) if you want to contact the DevTools team or get help from the DevTools community.  -->  



## <span data-ttu-id="5bc09-323">付録: HTML と DOM の比較</span><span class="sxs-lookup"><span data-stu-id="5bc09-323">Appendix: HTML versus the DOM</span></span>   

<span data-ttu-id="5bc09-324">以下のセクションでは、HTML と DOM の違いについて簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-324">The following section quickly explains the difference between HTML and the DOM.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="5bc09-325">Web ブラウザーを使用してページを要求すると、サーバーは次のコードスニペットのような HTML を返します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-325">When you use a web browser to request a page, the server returns HTML like the following code snippet</span></span>  

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
      <span data-ttu-id="5bc09-326">ブラウザーは HTML を解析し、次のようなオブジェクトのツリーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-326">The browser parses the HTML and creates a tree of objects like the following list.</span></span>  
      
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

<span data-ttu-id="5bc09-327">ページのコンテンツを表す、このオブジェクトのツリーは DOM と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-327">This tree of objects, or nodes, representing the content of the page is called the DOM.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="5bc09-328">HTML と同じように見えますが、HTML の下部で参照されているスクリプトが次のコードスニペットを実行していることを考えてみてください。</span><span class="sxs-lookup"><span data-stu-id="5bc09-328">Right now it looks the same as the HTML, but suppose that the script referenced at the bottom of the HTML runs the following code snippet.</span></span>  
      
      ```javascript
      const h1 = document.querySelector('h1');
      h1.parentElement.removeChild(h1);
      const p = document.createElement('p');
      p.textContent = 'Wildcard!';
      document.body.appendChild(p);
      ```  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="5bc09-329">このコードは、 `h1` ノードを削除し、別の `p` ノードを DOM に追加します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-329">That code removes the `h1` node and adds another `p` node to the DOM.</span></span>  <span data-ttu-id="5bc09-330">これで、完全な DOM に次のリストが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5bc09-330">The complete DOM now displays the following list.</span></span>  
      
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

<span data-ttu-id="5bc09-331">ページの HTML が DOM とは異なるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5bc09-331">The HTML for the page is now different than the DOM.</span></span>  <span data-ttu-id="5bc09-332">つまり、HTML は初期ページコンテンツを表し、DOM は現在のページコンテンツを表します。</span><span class="sxs-lookup"><span data-stu-id="5bc09-332">In other words, HTML represents initial page content, and the DOM represents current page content.</span></span>  <span data-ttu-id="5bc09-333">JavaScript がノードを追加、削除、または編集すると、DOM は HTML とは異なります。</span><span class="sxs-lookup"><span data-stu-id="5bc09-333">When JavaScript adds, removes, or edits nodes, the DOM becomes different than the HTML.</span></span>  

<span data-ttu-id="5bc09-334">詳細について [は、「DOM の概要][MDNIntroductionToDOM] 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bc09-334">See [Introduction to the DOM][MDNIntroductionToDOM] to learn more.</span></span>  

<!--
## Appendix: Scroll into view   

This is a continuation of the [Scroll into view](#scroll-into-view) section.  Follow the instructions below to complete the section.  

1.  The `<li>Magritte</li>` node should still be selected in your DOM Tree.  If not, go back to [Scroll into view](#scroll-into-view) and start over.  
1.  Right-click the `<li>Magritte</li>` node and select **Scroll into view**.  Your viewport scrolls back up so that you may see the **Magritte** node.  See [Appendix: Missing options](#appendix-missing-options) if you are not able to see the **Scroll into view** option.
    
    > ##### Figure 19  
    > Scroll into view  
    > :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="Scroll into view" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
   Scroll into view  
:::image-end:::  
    -->  

## <span data-ttu-id="5bc09-335">付録: オプションが表示されない</span><span class="sxs-lookup"><span data-stu-id="5bc09-335">Appendix: Missing options</span></span>   

<span data-ttu-id="5bc09-336">このチュートリアルで説明する多くの手順では、DOM ツリーのノードを右クリックし、ポップアップ表示されるコンテキストメニューからオプションを選択するように指示されています。</span><span class="sxs-lookup"><span data-stu-id="5bc09-336">Many of the instructions in this tutorial instruct you to right-click a node in the DOM Tree and then select an option from the context menu that pops up.</span></span>  <span data-ttu-id="5bc09-337">コンテキストメニューに [指定] オプションが表示されない場合は、ノードのテキストを右クリックしてみてください。</span><span class="sxs-lookup"><span data-stu-id="5bc09-337">If you do not see the specified option in the context menu, try right-clicking away from the node text.</span></span>  

:::image type="complex" source="../media/dom-elements-highlighted-right-click-right-side.msft.png" alt-text="すべてのオプションが表示されない場合は、ここをクリックします。" lightbox="../media/dom-elements-highlighted-right-click-right-side.msft.png":::
   <span data-ttu-id="5bc09-339">すべてのオプションが表示されない場合は、ここをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5bc09-339">Where to click if you are not seeing all the options</span></span>  
:::image-end:::  

<!-- image links -->  

[ImageInspectIcon]: ../media/inspect-icon.msft.png  
[ImageResumeScriptIcon]: ../media/resume-script-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge \ (Chromium \) 開発者ツール |Microsoft ドキュメント"  
[DevToolsCssGetStarted]: ../css/index.md "CSS の表示と変更の概要 |Microsoft ドキュメント"  
[DevToolsShortcutsElements]: ../shortcuts.md#elements-panel-keyboard-shortcuts "要素パネルのキーボードショートカット-Microsoft Edge DevTools のキーボードショートカット |Microsoft ドキュメント"  

[GlitchDomExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/dom "Microsoft Edge (Chromium) DevTools DOM の例 |故障"

[MDNIntroductionToDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM の概要 |MDN"  

> [!NOTE]
> <span data-ttu-id="5bc09-345">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="5bc09-345">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="5bc09-346">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/dom/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="5bc09-346">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/dom/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="5bc09-348">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="5bc09-348">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
