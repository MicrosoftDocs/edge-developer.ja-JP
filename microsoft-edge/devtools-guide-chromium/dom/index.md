---
description: ノードの表示、ノードの検索、ノードの編集、コンソールの参照ノード、ノードの変更の中断などについて説明します。
title: DOM の表示と変更を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 8c0b544f2c4717a01d09c287f1167c81456a97f3
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125028"
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

# <span data-ttu-id="6f35e-104">DOM の表示と変更を開始する</span><span class="sxs-lookup"><span data-stu-id="6f35e-104">Get started with viewing and changing the DOM</span></span>  

<span data-ttu-id="6f35e-105">Microsoft Edge DevTools を使用して、ページの DOM を表示して変更する基本的な方法については、次の対話型チュートリアルを実行してください。</span><span class="sxs-lookup"><span data-stu-id="6f35e-105">Complete these interactive tutorials to learn the basics of viewing and changing the DOM of a page using Microsoft Edge DevTools.</span></span>  

<span data-ttu-id="6f35e-106">このチュートリアルでは、DOM と HTML の違いを知っていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="6f35e-106">This tutorial assumes that you know the difference between the DOM and HTML.</span></span>  <span data-ttu-id="6f35e-107">説明については [、「付録: HTML と DOM の比較](#appendix-html-versus-the-dom) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f35e-107">See [Appendix: HTML versus the DOM](#appendix-html-versus-the-dom) for an explanation.</span></span>  

## <span data-ttu-id="6f35e-108">DOM の例を開く</span><span class="sxs-lookup"><span data-stu-id="6f35e-108">Open DOM examples</span></span>  

1.  <span data-ttu-id="6f35e-109">" `Control` \ (Windows, Linux \)" または " `Command` \ (macOS \)" を保持し、[ **DOM の例** ] を選んで新しいタブで開きます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-109">Hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and choose **DOM Examples** to open in a new tab.</span></span>  
    
    [<span data-ttu-id="6f35e-110">DOM の例</span><span class="sxs-lookup"><span data-stu-id="6f35e-110">DOM Examples</span></span>][GlitchDomExamples]  
    
## <span data-ttu-id="6f35e-111">DOM ノードの表示</span><span class="sxs-lookup"><span data-stu-id="6f35e-111">View DOM nodes</span></span>  

<span data-ttu-id="6f35e-112">[要素] パネルの DOM ツリーでは、DevTools で DOM に関連するすべてのアクティビティを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-112">The DOM Tree of the Elements panel is where you do all DOM-related activities in DevTools.</span></span>  

### <span data-ttu-id="6f35e-113">ノードを検査する</span><span class="sxs-lookup"><span data-stu-id="6f35e-113">Inspect a node</span></span>  

<span data-ttu-id="6f35e-114">特定の DOM ノードに関心がある場合は、[ **検査** ] を使うと、devtools をすばやく開いてそのノードを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-114">When you are interested in a particular DOM node, **Inspect** is a fast way to open DevTools and investigate that node.</span></span>  

1.  <span data-ttu-id="6f35e-115">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-115">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="6f35e-116">[ **ノードの検査**] で、[ **Michelangelo** ] を右クリックし、[ **検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-116">Under **Inspect a Node**, right-choose **Michelangelo** and choose **Inspect**.</span></span>  
    
    :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png":::
       <span data-ttu-id="6f35e-118">ノードを検査する</span><span class="sxs-lookup"><span data-stu-id="6f35e-118">Inspect a node</span></span>  
    :::image-end:::  
    
    1.  <span data-ttu-id="6f35e-119">DevTools の [ **要素** ] パネルが開きます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-119">The **Elements** panel of DevTools opens.</span></span>  `<li>Michelangelo</li>` <span data-ttu-id="6f35e-120">が強調表示さ **れてい**ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-120">is highlighted in the **DOM Tree**.</span></span>  
        
        :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png":::
           <span data-ttu-id="6f35e-122">ノードを強調表示する `Michelangelo`</span><span class="sxs-lookup"><span data-stu-id="6f35e-122">Highlight the `Michelangelo` node</span></span>  
        :::image-end:::  
        
        1.  <span data-ttu-id="6f35e-123">**Inspect** ![ ][ImageInspectIcon] Devtools の左上隅にある検査 (検査 \) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f35e-123">Click the **Inspect** \(![Inspect][ImageInspectIcon]\) icon in the top-left corner of DevTools.</span></span>  
            
            :::image type="complex" source="../media/dom-elements-highlighted-select-element-page-inspect.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-select-element-page-inspect.msft.png":::
               <span data-ttu-id="6f35e-125">[ **検査** ] アイコン</span><span class="sxs-lookup"><span data-stu-id="6f35e-125">The **Inspect** icon</span></span>  
            :::image-end:::  
            
1.  <span data-ttu-id="6f35e-126">[ **ノードの検査**] で、[ **東京** ] のテキストをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f35e-126">Under **Inspect a Node**, click the **Tokyo** text.</span></span>  <span data-ttu-id="6f35e-127">これで、 `<li>Tokyo</li>` DOM ツリーで強調表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6f35e-127">Now, `<li>Tokyo</li>` is highlighted in the DOM Tree.</span></span>  

<span data-ttu-id="6f35e-128">ノードの [検査] は、ノードのスタイルを表示して変更するための最初の手順でもあります。</span><span class="sxs-lookup"><span data-stu-id="6f35e-128">Inspecting a node is also the first step towards viewing and changing the styles of a node.</span></span>  <span data-ttu-id="6f35e-129">「 [CSS の表示と変更」の「使用を開始する」を][DevToolsCssGetStarted]参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f35e-129">See [Get Started With Viewing And Changing CSS][DevToolsCssGetStarted].</span></span>  

### <span data-ttu-id="6f35e-130">キーボードで DOM ツリー内を移動する</span><span class="sxs-lookup"><span data-stu-id="6f35e-130">Navigate the DOM Tree with a keyboard</span></span>  

<span data-ttu-id="6f35e-131">DOM ツリーでノードを選択すると、DOM ツリーをキーボードで移動できます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-131">Once you have selected a node in the DOM Tree, you may navigate the DOM Tree with your keyboard.</span></span>  

1.  <span data-ttu-id="6f35e-132">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-132">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="6f35e-133">[ **DOM ツリーをキーボードで操作**] で、[ **Ringo** ] を右クリックし、[ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-133">Under **Navigate the DOM Tree with a Keyboard**, right-choose **Ringo** and choose **Inspect**.</span></span>  `<li>Ringo</li>` <span data-ttu-id="6f35e-134">が選択されます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-134">is selected in the DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png":::
       <span data-ttu-id="6f35e-136">ノードを検査する `Ringo`</span><span class="sxs-lookup"><span data-stu-id="6f35e-136">Inspect the `Ringo` node</span></span>  
    :::image-end:::  
    
    1.  <span data-ttu-id="6f35e-137">`Up`方向キーを2回押します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-137">Press the `Up` arrow key 2 times.</span></span>  `<ul>` <span data-ttu-id="6f35e-138"> がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-138">is selected.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png":::
           <span data-ttu-id="6f35e-140">ノードを検査する `ul`</span><span class="sxs-lookup"><span data-stu-id="6f35e-140">Inspect the `ul` node</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="6f35e-141">`Left`方向キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-141">Press the `Left` arrow key.</span></span>  <span data-ttu-id="6f35e-142">`<ul>`リストが折りたたまれます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-142">The `<ul>` list collapses.</span></span>  
    1.  <span data-ttu-id="6f35e-143">`Left`もう一度方向キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-143">Press the `Left` arrow key again.</span></span>  <span data-ttu-id="6f35e-144">ノードの親 `<ul>` が選択されます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-144">The parent of the `<ul>` node is selected.</span></span>  <span data-ttu-id="6f35e-145">この場合は、 `<div>` ID を使用し `navigate-the-dom-tree-with-a-keyboard-1` ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-145">In this case it is the `<div>` with the ID `navigate-the-dom-tree-with-a-keyboard-1`.</span></span>  
    1.  <span data-ttu-id="6f35e-146">`Down`方向キーを2回押して、折りたたんだリストをもう一度選択し `<ul>` ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-146">Press the `Down` arrow key 2 times so that you have re-selected the `<ul>` list that you just collapsed.</span></span>  <span data-ttu-id="6f35e-147">次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6f35e-147">It should look like this:</span></span> `<ul>... </ul>`  
    1.  <span data-ttu-id="6f35e-148">`Right`方向キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-148">Press the `Right` arrow key.</span></span>  <span data-ttu-id="6f35e-149">リストが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-149">The list expands.</span></span>  

### <span data-ttu-id="6f35e-150">スクロールして表示する</span><span class="sxs-lookup"><span data-stu-id="6f35e-150">Scroll into view</span></span>  

<span data-ttu-id="6f35e-151">DOM ツリーを表示しているときに、現在ビューポート内にない DOM ノードに興味を持っていることがあります。</span><span class="sxs-lookup"><span data-stu-id="6f35e-151">When viewing the DOM Tree, you may find yourself interested in a DOM node that is not currently in the viewport.</span></span>  <span data-ttu-id="6f35e-152">たとえば、ページの一番下までスクロールして、ページの上部にあるノードに関心を持っているとし `<h1>` ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-152">For example, suppose that you scrolled to the bottom of the page, and you are interested in the `<h1>` node at the top of the page.</span></span>  <span data-ttu-id="6f35e-153">**ビューをスクロール** すると、ビューポートをすばやく移動して、ノードを表示できます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-153">**Scroll into view** lets you quickly reposition the viewport so that you are able to see the node.</span></span>  

1.  <span data-ttu-id="6f35e-154">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-154">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="6f35e-155">[ **スクロール**して表示] で、[ **Magritte** ] を右クリックし、[ **検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-155">Under **Scroll into View**, right-choose **Magritte** and choose **Inspect**.</span></span>  
1.  <span data-ttu-id="6f35e-156">DOM の [例] ページの一番下までスクロールします。</span><span class="sxs-lookup"><span data-stu-id="6f35e-156">Scroll to the bottom of the DOM Examples page.</span></span>  
1.  <span data-ttu-id="6f35e-157">`<li>Magritte</li>`それでも、ノードは DOM ツリーで選択されます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-157">The `<li>Magritte</li>` node should still be selected in your DOM Tree.</span></span>  <span data-ttu-id="6f35e-158">表示されていない場合は、戻って、もう一度 [表示](#scroll-into-view) してみてください。</span><span class="sxs-lookup"><span data-stu-id="6f35e-158">If not, go back to [Scroll into view](#scroll-into-view) and start over.</span></span>  
1.  <span data-ttu-id="6f35e-159">ノードを右クリック `<li>Magritte</li>` し、[ **ビューにスクロール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-159">Right-click the `<li>Magritte</li>` node and choose **Scroll into view**.</span></span>  <span data-ttu-id="6f35e-160">ビューポートがスクロールして、 **Magritte** ノードが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="6f35e-160">Your viewport scrolls back up so that you may see the **Magritte** node.</span></span>  <span data-ttu-id="6f35e-161">[スクロールして**表示**する] オプションが表示されない場合は、「[付録: オプションが見つから](#appendix-missing-options)ない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f35e-161">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see the **Scroll into view** option.</span></span>
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       **<span data-ttu-id="6f35e-163">スクロールして表示する</span><span class="sxs-lookup"><span data-stu-id="6f35e-163">Scroll into view</span></span>**  
    :::image-end:::  

### <span data-ttu-id="6f35e-164">ノードを検索する</span><span class="sxs-lookup"><span data-stu-id="6f35e-164">Search for nodes</span></span>  

<span data-ttu-id="6f35e-165">DOM ツリーは、文字列、CSS セレクター、または XPath セレクターで検索できます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-165">You may search the DOM Tree by string, CSS selector, or XPath selector.</span></span>  

1.  <span data-ttu-id="6f35e-166">カーソルを [ **要素** ] パネルにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="6f35e-166">Focus your cursor on the **Elements** panel.</span></span>  
1.  <span data-ttu-id="6f35e-167">`Control` + `F` \ (Windows, Linux \) または `Command` + `F` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-167">Select `Control`+`F` \(Windows, Linux\) or `Command`+`F` \(macOS\).</span></span>  <span data-ttu-id="6f35e-168">検索バーは DOM ツリーの下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-168">The Search bar opens at the bottom of the DOM Tree.</span></span>  
1.  <span data-ttu-id="6f35e-169">「`The Moon is a Harsh Mistress`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-169">Type `The Moon is a Harsh Mistress`.</span></span>  <span data-ttu-id="6f35e-170">DOM ツリーの最後の文が強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="6f35e-170">The last sentence is highlighted in the DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-search-nodes-highlight.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-search-nodes-highlight.msft.png":::
       <span data-ttu-id="6f35e-172">検索バーでクエリを強調表示する</span><span class="sxs-lookup"><span data-stu-id="6f35e-172">Highlight the query in the Search bar</span></span>  
    :::image-end:::  
    
<span data-ttu-id="6f35e-173">上で説明したように、検索バーは CSS と XPath のセレクターもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6f35e-173">As mentioned above, the Search bar also supports CSS and XPath selectors.</span></span>  

## <span data-ttu-id="6f35e-174">DOM を編集する</span><span class="sxs-lookup"><span data-stu-id="6f35e-174">Edit the DOM</span></span>  

<span data-ttu-id="6f35e-175">その場で DOM を編集して、それらの変更がページにどのように影響するかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-175">You may edit the DOM on the fly and see how those changes affect the page.</span></span>  

### <span data-ttu-id="6f35e-176">コンテンツを編集する</span><span class="sxs-lookup"><span data-stu-id="6f35e-176">Edit content</span></span>  

<span data-ttu-id="6f35e-177">ノードのコンテンツを編集するには、DOM ツリーでコンテンツをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f35e-177">To edit the content of a node, double-click the content in the DOM Tree.</span></span>  

1.  <span data-ttu-id="6f35e-178">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-178">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="6f35e-179">[ **コンテンツの編集**] で、[ **マイク** ] を右クリックし、[ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-179">Under **Edit Content**, right-choose **Michelle** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="6f35e-180">DOM ツリーで、をダブルクリック `Michelle` します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-180">In the DOM Tree, double-click `Michelle`.</span></span>  <span data-ttu-id="6f35e-181">つまり、との間のテキストをダブルクリック `<li>` し `</li>` ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-181">In other words, double-click the text between `<li>` and `</li>`.</span></span>  <span data-ttu-id="6f35e-182">テキストが強調表示され、選択されていることが示されます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-182">The text is highlighted to indicate that it is selected.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-content.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-edit-content.msft.png":::
           <span data-ttu-id="6f35e-184">テキストを編集する</span><span class="sxs-lookup"><span data-stu-id="6f35e-184">Edit the text</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="6f35e-185">[削除] を選択し、 `Michelle` 入力し `Leela` て、 `Enter` 変更内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-185">Delete `Michelle`, type `Leela`, then select `Enter` to confirm the change.</span></span>  <span data-ttu-id="6f35e-186">DOM 内のテキストは、 **MicLeela le**から**Leela**に変更されます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-186">The text in the DOM changes from **Michelle** to **Leela**.</span></span>  

### <span data-ttu-id="6f35e-187">属性を編集する</span><span class="sxs-lookup"><span data-stu-id="6f35e-187">Edit attributes</span></span>  

<span data-ttu-id="6f35e-188">属性を編集するには、属性の名前または値をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f35e-188">To edit attributes, double-click the attribute name or value.</span></span>  <span data-ttu-id="6f35e-189">手順に従って、ノードに属性を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-189">Follow the instructions to learn how to add attributes to a node.</span></span>  

1.  <span data-ttu-id="6f35e-190">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-190">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="6f35e-191">[ **属性の編集**] で、[ **Howard** ] を右クリックし、[ **検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-191">Under **Edit Attributes**, right-choose **Howard** and choose **Inspect**.</span></span>  
1.  <span data-ttu-id="6f35e-192">ダブルクリック `<li>` します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-192">Double-click `<li>`.</span></span>  <span data-ttu-id="6f35e-193">テキストが強調表示され、ノードが選択されていることが示されます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-193">The text is highlighted to indicate that the node is selected.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png":::
       <span data-ttu-id="6f35e-195">ノードを編集する</span><span class="sxs-lookup"><span data-stu-id="6f35e-195">Edit the node</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6f35e-196">方向キーを押して、スペースを追加し、 `Right` 「」と入力し `style="background-color:gold"` て、を選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-196">Press the `Right` arrow key, add a space, type `style="background-color:gold"`, and then select `Enter`.</span></span>  <span data-ttu-id="6f35e-197">ノードの背景色が金色に変わります。</span><span class="sxs-lookup"><span data-stu-id="6f35e-197">The background color of the node changes to gold.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png":::
       <span data-ttu-id="6f35e-199">`style`ノードに属性を追加する</span><span class="sxs-lookup"><span data-stu-id="6f35e-199">Add a `style` attribute to the node</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="6f35e-200">ノードの種類を編集する</span><span class="sxs-lookup"><span data-stu-id="6f35e-200">Edit node type</span></span>  

<span data-ttu-id="6f35e-201">ノードの種類を編集するには、型をダブルクリックし、新しい型を入力します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-201">To edit the type of a node, double-click the type and then type in the new type.</span></span>  

1.  <span data-ttu-id="6f35e-202">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-202">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="6f35e-203">[ **ノードの種類の編集**] で、[ **Hank** ] を右クリックし、[ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-203">Under **Edit Node Type**, right-choose **Hank** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="6f35e-204">ダブルクリック `<li>` します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-204">Double-click `<li>`.</span></span>  <span data-ttu-id="6f35e-205">テキスト `li` が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-205">The text `li` is highlighted.</span></span>  
    1.  <span data-ttu-id="6f35e-206">を削除して、を入力し、 `li` `button` を選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-206">Delete `li`, type `button`, then select `Enter`.</span></span>  <span data-ttu-id="6f35e-207">`<li>`ノードがノードに変わり `<button>` ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-207">The `<li>` node changes to a `<button>` node.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-node-type-button.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-edit-node-type-button.msft.png":::
           <span data-ttu-id="6f35e-209">ノードの種類を変更する</span><span class="sxs-lookup"><span data-stu-id="6f35e-209">Change the node type to</span></span> `button`  
        :::image-end:::  
        
### <span data-ttu-id="6f35e-210">DOM ノードの順序を変更する</span><span class="sxs-lookup"><span data-stu-id="6f35e-210">Reorder DOM nodes</span></span>  

<span data-ttu-id="6f35e-211">ノードをドラッグして順序を変更します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-211">Drag nodes to reorder them.</span></span>  

1.  <span data-ttu-id="6f35e-212">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-212">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="6f35e-213">[ **DOM ノードの並べ替え**] で、[ **Elvis Presley** ] を右クリックし、[ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-213">Under **Reorder DOM Nodes**, right-choose **Elvis Presley** and choose **Inspect**.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="6f35e-214">これは、リスト内の最後のアイテムです。</span><span class="sxs-lookup"><span data-stu-id="6f35e-214">It is the last item in the list.</span></span>  
    
    1.  <span data-ttu-id="6f35e-215">DOM ツリーで、 `<li>Elvis Presley</li>` 一覧の一番上までドラッグします。</span><span class="sxs-lookup"><span data-stu-id="6f35e-215">In the DOM Tree, drag `<li>Elvis Presley</li>` to the top of the list.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-reorder-dom-nodes.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-reorder-dom-nodes.msft.png":::
           <span data-ttu-id="6f35e-217">ノードを一覧の一番上にドラッグする</span><span class="sxs-lookup"><span data-stu-id="6f35e-217">Drag the node to the top of the list</span></span>  
        :::image-end:::  
        
### <span data-ttu-id="6f35e-218">強制状態</span><span class="sxs-lookup"><span data-stu-id="6f35e-218">Force state</span></span>  

<span data-ttu-id="6f35e-219">ノードは、、、、、などの状態に保つことができ `:active` `:hover` `:focus` `:visited` `:focus-within` ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-219">You are able to force nodes to remain in states including `:active`, `:hover`, `:focus`, `:visited`, and `:focus-within`.</span></span>  

1.  <span data-ttu-id="6f35e-220">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-220">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="6f35e-221">[ **状態の強制**] で、 **その中の閣下**をポイントします。</span><span class="sxs-lookup"><span data-stu-id="6f35e-221">Under **Force state**, hover over **The Lord of the Flies**.</span></span>  <span data-ttu-id="6f35e-222">背景色がオレンジ色になります。</span><span class="sxs-lookup"><span data-stu-id="6f35e-222">The background color becomes orange.</span></span>  
    1.  <span data-ttu-id="6f35e-223">**フライの閣下**を右クリックして、[**検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-223">Right-choose **The Lord of the Flies** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="6f35e-224">右クリック `<li class="demo--hover">The Lord of the Flies</li>` して、[**状態の強制**  >  **: hover**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-224">Right-click `<li class="demo--hover">The Lord of the Flies</li>` and choose **Force State** > **:hover**.</span></span>  <span data-ttu-id="6f35e-225">このオプションが表示されない場合は、「 [付録: オプション](#appendix-missing-options) を表示しない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f35e-225">See [Appendix: Missing options](#appendix-missing-options) if you do not see this option.</span></span>  <span data-ttu-id="6f35e-226">実際には、ノードの上にカーソルを置いていない場合でも、背景色はオレンジにとどまります。</span><span class="sxs-lookup"><span data-stu-id="6f35e-226">The background color remains orange even though you are not actually hovering over the node.</span></span>  

### <span data-ttu-id="6f35e-227">ノードを非表示にする</span><span class="sxs-lookup"><span data-stu-id="6f35e-227">Hide a node</span></span>  

<span data-ttu-id="6f35e-228">`H`ノードを非表示にする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-228">Select `H` to hide a node.</span></span>  

1.  <span data-ttu-id="6f35e-229">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-229">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="6f35e-230">[ **ノードを非表示にする**] で、[ **宛先の星** ] を右クリックし、[ **検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-230">Under **Hide a node**, right-choose **The Stars My Destination** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="6f35e-231">キーを押し `H` ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-231">Press the `H` key.</span></span>  <span data-ttu-id="6f35e-232">ノードが非表示になっています。</span><span class="sxs-lookup"><span data-stu-id="6f35e-232">The node is hidden.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-hide-a-node.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-hide-a-node.msft.png":::
           <span data-ttu-id="6f35e-234">非表示になった後のノードが DOM ツリーのどのように見えるか</span><span class="sxs-lookup"><span data-stu-id="6f35e-234">What the node looks like in the DOM Tree after it is hidden</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="6f35e-235">キーを `H` もう一度押します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-235">Press the `H` key again.</span></span>  <span data-ttu-id="6f35e-236">ノードが再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-236">The node is shown again.</span></span>  

### <span data-ttu-id="6f35e-237">ノードを削除する</span><span class="sxs-lookup"><span data-stu-id="6f35e-237">Delete a node</span></span>  

<span data-ttu-id="6f35e-238">`Delete`ノードを削除する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-238">Select `Delete` to delete a node.</span></span>  

1.  <span data-ttu-id="6f35e-239">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-239">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="6f35e-240">[ **ノードの削除**] で、[ **Foundation** ] を右クリックし、[ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-240">Under **Delete a Node**, right-choose **Foundation** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="6f35e-241">キーを押し `Delete` ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-241">Press the `Delete` key.</span></span>  <span data-ttu-id="6f35e-242">ノードが削除されます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-242">The node is deleted.</span></span>  
    1.  <span data-ttu-id="6f35e-243">`Control` + `Z` \ (Windows, Linux \) または `Command` + `Z` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-243">Select `Control`+`Z` \(Windows, Linux\) or `Command`+`Z` \(macOS\).</span></span>  <span data-ttu-id="6f35e-244">直前の操作が取り消され、ノードが再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-244">The last action is undone and the node reappears.</span></span>  

## <span data-ttu-id="6f35e-245">コンソールのアクセスノード</span><span class="sxs-lookup"><span data-stu-id="6f35e-245">Access nodes in the Console</span></span>  

<span data-ttu-id="6f35e-246">DevTools では、コンソールから DOM ノードにアクセスしたり、各デバイスへの JavaScript 参照を取得したりするためのショートカットキーをいくつか用意しています。</span><span class="sxs-lookup"><span data-stu-id="6f35e-246">DevTools provides a few shortcuts for accessing DOM nodes from the Console, or getting JavaScript references to each one.</span></span>  

### <span data-ttu-id="6f35e-247">$0 で現在選択されているノードを参照する</span><span class="sxs-lookup"><span data-stu-id="6f35e-247">Reference the currently-selected node with $0</span></span>  

<span data-ttu-id="6f35e-248">ノードを検査すると、 `== $0` ノードの横のテキストは、この変数を持つ本体でこのノードを参照できることを意味 `$0` します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-248">When you inspect a node, the `== $0` text next to the node means that you may reference this node in the Console with the variable `$0`.</span></span>  

1.  <span data-ttu-id="6f35e-249">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-249">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="6f35e-250">[ **$0 で現在選択さ**れているノードを参照する] で、 **暗さの左側** を右クリックして [ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-250">Under **Reference the currently-selected node with $0**, right-choose **The Left Hand of Darkness** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="6f35e-251">キーを押して、 `Escape` 本体の引き出しを開きます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-251">Press the `Escape` key to open the Console Drawer.</span></span>  
    1.  <span data-ttu-id="6f35e-252">キーを入力 `$0` して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-252">Type `$0` and press the `Enter` key.</span></span>  <span data-ttu-id="6f35e-253">この式の結果は、の `$0` 評価を示して `<li>The Left Hand of Darkness</li>` います。</span><span class="sxs-lookup"><span data-stu-id="6f35e-253">The result of the expression shows that `$0` evaluates to `<li>The Left Hand of Darkness</li>`.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png":::
            <span data-ttu-id="6f35e-255">本体の最初の式の結果 `$0` **Console**</span><span class="sxs-lookup"><span data-stu-id="6f35e-255">The result of the first `$0` expression in the **Console**</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="6f35e-256">結果にマウスポインターを合わせます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-256">Hover over the result.</span></span>  <span data-ttu-id="6f35e-257">ビューポートで、ノードが強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="6f35e-257">The node is highlighted in the viewport.</span></span>  
    1.  <span data-ttu-id="6f35e-258">`<li>Dune</li>`DOM ツリー内をクリックし、 `$0` コンソールをもう一度入力して、 `Enter` もう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-258">Click `<li>Dune</li>` in the DOM Tree, type `$0` in the Console again, and then select `Enter` again.</span></span>  <span data-ttu-id="6f35e-259">次に、の `$0` ようにに評価さ `<li>Dune</li>` れます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-259">Now, `$0` evaluates to `<li>Dune</li>`.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png":::
           <span data-ttu-id="6f35e-261">コンソールの2番目の `$0` 式の**Console**結果</span><span class="sxs-lookup"><span data-stu-id="6f35e-261">The result of the second `$0` expression in the **Console**</span></span>  
        :::image-end:::  
        
### <span data-ttu-id="6f35e-262">グローバル変数として保存する</span><span class="sxs-lookup"><span data-stu-id="6f35e-262">Store as global variable</span></span>  

<span data-ttu-id="6f35e-263">何度もノードを参照する必要がある場合は、それをグローバル変数として保存します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-263">If you need to refer back to a node many times, store it as a global variable.</span></span>  

1.  <span data-ttu-id="6f35e-264">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-264">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="6f35e-265">[ **グローバル変数として保存**] で、 **大きいスリープ** を右クリックし、[ **検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-265">Under **Store as global variable**, right-choose **The Big Sleep** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="6f35e-266">DOM ツリーを右クリックして、 `<li>The Big Sleep</li>` [ **グローバル変数として保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-266">Right-click `<li>The Big Sleep</li>` in the DOM Tree and choose **Store as global variable**.</span></span>  <span data-ttu-id="6f35e-267">このオプションが表示されない場合は、「 [付録: オプション](#appendix-missing-options) を表示しない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f35e-267">See [Appendix: Missing options](#appendix-missing-options) if you do not see this option.</span></span>  
    1.  <span data-ttu-id="6f35e-268">`temp1`コンソールに入力して、を選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-268">Type `temp1` in the Console and then select `Enter`.</span></span>  <span data-ttu-id="6f35e-269">この式の結果は、変数がノードに評価されることを示します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-269">The result of the expression shows that the variable evaluates to the node.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png":::
           <span data-ttu-id="6f35e-271">式の結果 `temp1`</span><span class="sxs-lookup"><span data-stu-id="6f35e-271">The result of the `temp1` expression</span></span>  
        :::image-end:::  
        
### <span data-ttu-id="6f35e-272">JS パスをコピーする</span><span class="sxs-lookup"><span data-stu-id="6f35e-272">Copy JS path</span></span>  

<span data-ttu-id="6f35e-273">自動テストで参照する必要がある場合は、JavaScript のパスをノードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="6f35e-273">Copy the JavaScript path to a node when you need to reference it in an automated test.</span></span>  

1.  <span data-ttu-id="6f35e-274">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-274">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="6f35e-275">[ **JS パスのコピー**] で、[ **兄弟 Karamazov** ] を右クリックし、[ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-275">Under **Copy JS path**, right-choose **The Brothers Karamazov** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="6f35e-276">DOM ツリーを右クリック `<li>The Brothers Karamazov</li>` して、[ **Copy**  >  **copy copy JS Path**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-276">Right-click `<li>The Brothers Karamazov</li>` in the DOM Tree and choose **Copy** > **Copy JS Path**.</span></span>  <span data-ttu-id="6f35e-277">`document.querySelector()`ノードに解決される式がクリップボードにコピーされました。</span><span class="sxs-lookup"><span data-stu-id="6f35e-277">A `document.querySelector()` expression that resolves to the node has been copied to your clipboard.</span></span>  
    1.  <span data-ttu-id="6f35e-278">`Control` + `V` 式をコンソールに貼り付けるには、\ (Windows, Linux \) または `Command` + `V` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-278">Select `Control`+`V` \(Windows, Linux\) or `Command`+`V` \(macOS\) to paste the expression into the Console.</span></span>  
    1.  <span data-ttu-id="6f35e-279">`Enter`式を評価する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-279">Select `Enter` to evaluate the expression.</span></span>
        
        :::image type="complex" source="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png":::
           <span data-ttu-id="6f35e-281">**JS パス**の式をコピーした結果</span><span class="sxs-lookup"><span data-stu-id="6f35e-281">The result of the **Copy JS Path** expression</span></span>  
        :::image-end:::  
        
## <span data-ttu-id="6f35e-282">DOM の中断の変更</span><span class="sxs-lookup"><span data-stu-id="6f35e-282">Break on DOM changes</span></span>  

<span data-ttu-id="6f35e-283">DevTools を使うと、JavaScript が DOM を変更したときにページの JavaScript を一時停止することができます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-283">DevTools enables you to pause the JavaScript of a page when the JavaScript modifies the DOM.</span></span>  

### <span data-ttu-id="6f35e-284">属性の変更の中断</span><span class="sxs-lookup"><span data-stu-id="6f35e-284">Break on attribute modifications</span></span>  

<span data-ttu-id="6f35e-285">ノードの任意の属性を変更する JavaScript を一時停止する場合は、属性変更ブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-285">Use attribute modification breakpoints when you want to pause the JavaScript that causes any attribute of a node to change.</span></span>  

1.  <span data-ttu-id="6f35e-286">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-286">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="6f35e-287">[ **属性の変更を中断**] で、[ **Sauerkraut** ] を右クリックし、[ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-287">Under **Break on attribute modifications**, right-choose **Sauerkraut** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="6f35e-288">DOM ツリーで右クリックし、[ `<li id="target">Sauerkraut</li>` 属性**の変更を中断**] を選び  >  **Attribute Modifications**ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-288">In the DOM Tree, right-click `<li id="target">Sauerkraut</li>` and choose **Break On** > **Attribute Modifications**.</span></span>  <span data-ttu-id="6f35e-289">このオプションが表示されない場合は、「 [付録: 省略](#appendix-missing-options) 可能なオプション」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f35e-289">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see this option.</span></span>
        
        :::image type="complex" source="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png":::
           **<span data-ttu-id="6f35e-291">属性の変更の中断</span><span class="sxs-lookup"><span data-stu-id="6f35e-291">Break on attribute modifications</span></span>**  
        :::image-end:::  
        
    1.  <span data-ttu-id="6f35e-292">次の手順では、ページのコードを一時停止するボタンをクリックするように指示されます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-292">In the next step you are going to be instructed to click a button that pauses the code of the page.</span></span>  <span data-ttu-id="6f35e-293">ページが一時停止されると、ページをスクロールすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="6f35e-293">After the page is paused you are no longer able to scroll the page.</span></span>  <span data-ttu-id="6f35e-294">**Resume Script** ![ ][ImageResumeScriptIcon] ページを再びスクロールできるようにするには、[スクリプトの再開] (スクリプトの再開 \) を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f35e-294">You must choose **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\) in order to make the page scrollable again.</span></span>
        
        :::image type="complex" source="../media/dom-break-attribute-modifications-sources-paused-on.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-break-attribute-modifications-sources-paused-on.msft.png":::
           <span data-ttu-id="6f35e-296">スクリプトの実行を再開する場所</span><span class="sxs-lookup"><span data-stu-id="6f35e-296">Where to resume script running</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="6f35e-297">上の [ **背景の設定** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f35e-297">Click the **Set Background** button above.</span></span>  <span data-ttu-id="6f35e-298">これにより `style` 、ノードの属性がに設定され `background-color:thistle` ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-298">This sets the `style` attribute of the node to `background-color:thistle`.</span></span>  <span data-ttu-id="6f35e-299">DevTools はページを一時停止し、属性が変更されたコードを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-299">DevTools pauses the page and highlights the code that caused the attribute to change.</span></span>  
    1.  <span data-ttu-id="6f35e-300">**Resume Script** ![ ][ImageResumeScriptIcon] 前に説明したように、[スクリプトの再開] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-300">Choose **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\), as mentioned earlier.</span></span>  
    
### <span data-ttu-id="6f35e-301">ノード削除時の中断</span><span class="sxs-lookup"><span data-stu-id="6f35e-301">Break on node removal</span></span>  

<span data-ttu-id="6f35e-302">特定のノードが削除されたときに一時停止する場合は、ノード削除のブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-302">If you want to pause when a particular node is removed, use node removal breakpoints.</span></span>  

1.  <span data-ttu-id="6f35e-303">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-303">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="6f35e-304">[ **ノード削除時の中断**] で、[ **Neuromancer** ] を右クリックし、[ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-304">Under **Break on Node Removal**, right-choose **Neuromancer** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="6f35e-305">DOM ツリーで右クリックし、[ `<li id="target">Neuromancer</li>` ノード**の削除時に中断**] を選択し  >  **Node Removal**ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-305">In the DOM Tree, right-click `<li id="target">Neuromancer</li>` and choose **Break On** > **Node Removal**.</span></span>  <span data-ttu-id="6f35e-306">このオプションが表示されない場合は、「 [付録: 省略](#appendix-missing-options) 可能なオプション」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f35e-306">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see this option.</span></span>  
    1.  <span data-ttu-id="6f35e-307">上の [ **削除** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f35e-307">Click the **Delete** button above.</span></span>  <span data-ttu-id="6f35e-308">DevTools はページを一時停止し、ノードの削除を引き起こしたコードを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-308">DevTools pauses the page and highlights the code that caused the node to be removed.</span></span>  
    1.  <span data-ttu-id="6f35e-309">[ **スクリプトの再開** ] を選択し ![ ます (スクリプトを再開 ][ImageResumeScriptIcon] します)。</span><span class="sxs-lookup"><span data-stu-id="6f35e-309">Choose **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\).</span></span>  
    
### <span data-ttu-id="6f35e-310">サブツリーの変更の中断</span><span class="sxs-lookup"><span data-stu-id="6f35e-310">Break on subtree modifications</span></span>  

<span data-ttu-id="6f35e-311">ノードにサブツリーの変更のブレークポイントを配置すると、ノードの子孫が追加または削除されると、DevTools によってページが一時停止します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-311">After you put a subtree modification breakpoint on a node, DevTools pauses the page when any of the descendants of the node are added or removed.</span></span>  

1.  <span data-ttu-id="6f35e-312">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-312">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="6f35e-313">[ **サブツリーの変更の中断**] で、[詳細] の下に **ある炎を** 右クリックし、[ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-313">Under **Break on Subtree Modifications**, right-choose **A Fire Upon The Deep** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="6f35e-314">DOM ツリーで、上のノードである右クリックし、[ `<ul id="target">` `<li>A Fire Upon the Deep</li>` サブツリー**の**変更による中断] を選択し  >  **Subtree Modifications**ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-314">In the DOM Tree, right-click `<ul id="target">`, which is the node above `<li>A Fire Upon the Deep</li>`, and choose **Break On** > **Subtree Modifications**.</span></span>  <span data-ttu-id="6f35e-315">このオプションが表示されない場合は、「 [付録: 省略](#appendix-missing-options) 可能なオプション」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f35e-315">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see this option.</span></span>  
    1.  <span data-ttu-id="6f35e-316">[ **子の追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-316">Choose **Add Child**.</span></span>  <span data-ttu-id="6f35e-317">ノードがリストに追加されたため、コードは一時停止し `<li>` ます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-317">The code pauses because a `<li>` node was added to the list.</span></span>  
    1.  <span data-ttu-id="6f35e-318">[ **スクリプトの再開** ] を選択し ![ ます (スクリプトを再開 ][ImageResumeScriptIcon] します)。</span><span class="sxs-lookup"><span data-stu-id="6f35e-318">Choose **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\).</span></span>  
    
## <span data-ttu-id="6f35e-319">次のステップ</span><span class="sxs-lookup"><span data-stu-id="6f35e-319">Next steps</span></span>  

<span data-ttu-id="6f35e-320">これは、DevTools の DOM 関連のほとんどの機能について説明しています。</span><span class="sxs-lookup"><span data-stu-id="6f35e-320">That covers most of the DOM-related features in DevTools.</span></span>  <span data-ttu-id="6f35e-321">残りの部分については、DOM ツリーのノードを右クリックし、このチュートリアルで説明していないその他のオプションを試してみることができます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-321">You are able to discover the rest of them by right-clicking nodes in the DOM Tree and experimenting with the other options that were not covered in this tutorial.</span></span>  <span data-ttu-id="6f35e-322">「 [要素パネルのショートカットキー][DevToolsShortcutsElements]」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6f35e-322">See also [Elements panel keyboard shortcuts][DevToolsShortcutsElements].</span></span>  

<span data-ttu-id="6f35e-323">[Microsoft Edge DevTools のホームページ][MicrosoftEdgeDevTools]をチェックして、devtools で実行できるその他の情報をすべて見つけてください。</span><span class="sxs-lookup"><span data-stu-id="6f35e-323">Check out the [Microsoft Edge DevTools homepage][MicrosoftEdgeDevTools] to discover everything else you are able to do with DevTools.</span></span>  

<!--See [Community](../index#community) if you want to contact the DevTools team or get help from the DevTools community.  -->  

## <span data-ttu-id="6f35e-324">付録: HTML と DOM の比較</span><span class="sxs-lookup"><span data-stu-id="6f35e-324">Appendix: HTML versus the DOM</span></span>  

<span data-ttu-id="6f35e-325">以下のセクションでは、HTML と DOM の違いについて簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-325">The following section quickly explains the difference between HTML and the DOM.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="6f35e-326">Web ブラウザーを使用してページを要求すると、サーバーは次のコードスニペットのような HTML を返します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-326">When you use a web browser to request a page, the server returns HTML like the following code snippet</span></span>  

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
      <span data-ttu-id="6f35e-327">ブラウザーは HTML を解析し、次のようなオブジェクトのツリーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-327">The browser parses the HTML and creates a tree of objects like the following list.</span></span>  
      
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

<span data-ttu-id="6f35e-328">ページのコンテンツを表す、このオブジェクトのツリーは DOM と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-328">This tree of objects, or nodes, representing the content of the page is called the DOM.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="6f35e-329">HTML と同じように見えますが、HTML の下部で参照されているスクリプトが次のコードスニペットを実行していることを考えてみてください。</span><span class="sxs-lookup"><span data-stu-id="6f35e-329">Right now it looks the same as the HTML, but suppose that the script referenced at the bottom of the HTML runs the following code snippet.</span></span>  
      
      ```javascript
      const h1 = document.querySelector('h1');
      h1.parentElement.removeChild(h1);
      const p = document.createElement('p');
      p.textContent = 'Wildcard!';
      document.body.appendChild(p);
      ```  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="6f35e-330">このコードは、 `h1` ノードを削除し、別の `p` ノードを DOM に追加します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-330">That code removes the `h1` node and adds another `p` node to the DOM.</span></span>  <span data-ttu-id="6f35e-331">これで、完全な DOM に次のリストが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6f35e-331">The complete DOM now displays the following list.</span></span>  
      
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

<span data-ttu-id="6f35e-332">ページの HTML が DOM とは異なるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6f35e-332">The HTML for the page is now different than the DOM.</span></span>  <span data-ttu-id="6f35e-333">つまり、HTML は初期ページコンテンツを表し、DOM は現在のページコンテンツを表します。</span><span class="sxs-lookup"><span data-stu-id="6f35e-333">In other words, HTML represents initial page content, and the DOM represents current page content.</span></span>  <span data-ttu-id="6f35e-334">JavaScript がノードを追加、削除、または編集すると、DOM は HTML とは異なります。</span><span class="sxs-lookup"><span data-stu-id="6f35e-334">When JavaScript adds, removes, or edits nodes, the DOM becomes different than the HTML.</span></span>  

<span data-ttu-id="6f35e-335">詳細について [は、「DOM の概要][MDNIntroductionToDOM] 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f35e-335">See [Introduction to the DOM][MDNIntroductionToDOM] to learn more.</span></span>  

<!--
## Appendix: Scroll into view  

This is a continuation of the [Scroll into view](#scroll-into-view) section.  Follow the instructions below to complete the section.  

1.  The `<li>Magritte</li>` node should still be selected in your DOM Tree.  If not, go back to [Scroll into view](#scroll-into-view) and start over.  
1.  Right-click the `<li>Magritte</li>` node and choose **Scroll into view**.  Your viewport scrolls back up so that you may see the **Magritte** node.  See [Appendix: Missing options](#appendix-missing-options) if you are not able to see the **Scroll into view** option.
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       Scroll into view  
    :::image-end:::  
    -->  

## <span data-ttu-id="6f35e-336">付録: オプションが表示されない</span><span class="sxs-lookup"><span data-stu-id="6f35e-336">Appendix: Missing options</span></span>  

<span data-ttu-id="6f35e-337">このチュートリアルで説明する多くの手順では、DOM ツリーのノードを右クリックし、ポップアップ表示されるコンテキストメニューからオプションを選択するように指示されています。</span><span class="sxs-lookup"><span data-stu-id="6f35e-337">Many of the instructions in this tutorial instruct you to right-click a node in the DOM Tree and then select an option from the context menu that pops up.</span></span>  <span data-ttu-id="6f35e-338">コンテキストメニューに [指定] オプションが表示されない場合は、ノードのテキストを右クリックしてみてください。</span><span class="sxs-lookup"><span data-stu-id="6f35e-338">If you do not see the specified option in the context menu, try right-clicking away from the node text.</span></span>  

:::image type="complex" source="../media/dom-elements-highlighted-right-click-right-side.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-elements-highlighted-right-click-right-side.msft.png":::
   <span data-ttu-id="6f35e-340">すべてのオプションが表示されない場合は、ここをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f35e-340">Where to click if you are not seeing all the options</span></span>  
:::image-end:::  

## <span data-ttu-id="6f35e-341">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="6f35e-341">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

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
> <span data-ttu-id="6f35e-347">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="6f35e-347">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="6f35e-348">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/dom/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="6f35e-348">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/dom/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="6f35e-350">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="6f35e-350">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
