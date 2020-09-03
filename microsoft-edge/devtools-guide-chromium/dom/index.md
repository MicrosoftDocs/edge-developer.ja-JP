---
description: ノードの表示、ノードの検索、ノードの編集、コンソールの参照ノード、ノードの変更の中断などについて説明します。
title: DOM の表示と変更を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 555e627b70f0cc5e50c0676cf90067c2709a9ae3
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992954"
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





# <span data-ttu-id="9007c-104">DOM の表示と変更を開始する</span><span class="sxs-lookup"><span data-stu-id="9007c-104">Get started with viewing and changing the DOM</span></span>   



<span data-ttu-id="9007c-105">Microsoft Edge DevTools を使用して、ページの DOM を表示して変更する基本的な方法については、次の対話型チュートリアルを実行してください。</span><span class="sxs-lookup"><span data-stu-id="9007c-105">Complete these interactive tutorials to learn the basics of viewing and changing the DOM of a page using Microsoft Edge DevTools.</span></span>  

<span data-ttu-id="9007c-106">このチュートリアルでは、DOM と HTML の違いを知っていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="9007c-106">This tutorial assumes that you know the difference between the DOM and HTML.</span></span>  <span data-ttu-id="9007c-107">説明については [、「付録: HTML と DOM の比較](#appendix-html-versus-the-dom) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9007c-107">See [Appendix: HTML versus the DOM](#appendix-html-versus-the-dom) for an explanation.</span></span>  

## <span data-ttu-id="9007c-108">DOM の例を開く</span><span class="sxs-lookup"><span data-stu-id="9007c-108">Open DOM examples</span></span>  

1.  <span data-ttu-id="9007c-109">`Control`\ (Windows \) または `Command` \ (macOS \) を保持し、[ **DOM の例**] をクリックして新しいタブで開きます。</span><span class="sxs-lookup"><span data-stu-id="9007c-109">Hold `Control` \(Windows\) or `Command` \(macOS\) and click **DOM Examples** to open in a new tab.</span></span>  
    
    [<span data-ttu-id="9007c-110">DOM の例</span><span class="sxs-lookup"><span data-stu-id="9007c-110">DOM Examples</span></span>][GlitchDomExamples]  
    
## <span data-ttu-id="9007c-111">DOM ノードの表示</span><span class="sxs-lookup"><span data-stu-id="9007c-111">View DOM nodes</span></span>   

<span data-ttu-id="9007c-112">[要素] パネルの DOM ツリーでは、DevTools で DOM に関連するすべてのアクティビティを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9007c-112">The DOM Tree of the Elements panel is where you do all DOM-related activities in DevTools.</span></span>  

### <span data-ttu-id="9007c-113">ノードを検査する</span><span class="sxs-lookup"><span data-stu-id="9007c-113">Inspect a node</span></span>   

<span data-ttu-id="9007c-114">特定の DOM ノードに関心がある場合は、[ **検査** ] を使うと、devtools をすばやく開いてそのノードを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="9007c-114">When you are interested in a particular DOM node, **Inspect** is a fast way to open DevTools and investigate that node.</span></span>  

1.  <span data-ttu-id="9007c-115">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-115">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9007c-116">[ **ノードの検査**] で、[ **Michelangelo** ] を右クリックし、[ **検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9007c-116">Under **Inspect a Node**, right-click **Michelangelo** and select **Inspect**.</span></span>  
    
    :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png":::
       <span data-ttu-id="9007c-118">ノードを検査する</span><span class="sxs-lookup"><span data-stu-id="9007c-118">Inspect a node</span></span>  
    :::image-end:::  
    
    1.  <span data-ttu-id="9007c-119">DevTools の [ **要素** ] パネルが開きます。</span><span class="sxs-lookup"><span data-stu-id="9007c-119">The **Elements** panel of DevTools opens.</span></span>  `<li>Michelangelo</li>` <span data-ttu-id="9007c-120">が強調表示さ **れてい**ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-120">is highlighted in the **DOM Tree**.</span></span>  
        
        :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png" alt-text="Michelangelo ノードを強調表示する" lightbox="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png":::
           <span data-ttu-id="9007c-122">ノードを強調表示する `Michelangelo`</span><span class="sxs-lookup"><span data-stu-id="9007c-122">Highlight the `Michelangelo` node</span></span>  
        :::image-end:::  
        
        1.  <span data-ttu-id="9007c-123">**Inspect** ![ ][ImageInspectIcon] Devtools の左上隅にある検査 (検査 \) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9007c-123">Click the **Inspect** \(![Inspect][ImageInspectIcon]\) icon in the top-left corner of DevTools.</span></span>  
            
            :::image type="complex" source="../media/dom-elements-highlighted-select-element-page-inspect.msft.png" alt-text="[検査] アイコン" lightbox="../media/dom-elements-highlighted-select-element-page-inspect.msft.png":::
               <span data-ttu-id="9007c-125">[ **検査** ] アイコン</span><span class="sxs-lookup"><span data-stu-id="9007c-125">The **Inspect** icon</span></span>  
            :::image-end:::  
            
1.  <span data-ttu-id="9007c-126">[ **ノードの検査**] で、[ **東京** ] のテキストをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9007c-126">Under **Inspect a Node**, click the **Tokyo** text.</span></span>  <span data-ttu-id="9007c-127">これで、 `<li>Tokyo</li>` DOM ツリーで強調表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9007c-127">Now, `<li>Tokyo</li>` is highlighted in the DOM Tree.</span></span>  

<span data-ttu-id="9007c-128">ノードの [検査] は、ノードのスタイルを表示して変更するための最初の手順でもあります。</span><span class="sxs-lookup"><span data-stu-id="9007c-128">Inspecting a node is also the first step towards viewing and changing the styles of a node.</span></span>  <span data-ttu-id="9007c-129">「 [CSS の表示と変更」の「使用を開始する」を][DevToolsCssGetStarted]参照してください。</span><span class="sxs-lookup"><span data-stu-id="9007c-129">See [Get Started With Viewing And Changing CSS][DevToolsCssGetStarted].</span></span>  

### <span data-ttu-id="9007c-130">キーボードで DOM ツリー内を移動する</span><span class="sxs-lookup"><span data-stu-id="9007c-130">Navigate the DOM Tree with a keyboard</span></span>   

<span data-ttu-id="9007c-131">DOM ツリーでノードを選択すると、DOM ツリーをキーボードで移動できます。</span><span class="sxs-lookup"><span data-stu-id="9007c-131">Once you have selected a node in the DOM Tree, you may navigate the DOM Tree with your keyboard.</span></span>  

1.  <span data-ttu-id="9007c-132">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-132">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9007c-133">[ **DOM ツリーのキーボードでの操作**] で、[ **Ringo** ] を右クリックし、[ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9007c-133">Under **Navigate the DOM Tree with a Keyboard**, right-click **Ringo** and select **Inspect**.</span></span>  `<li>Ringo</li>` <span data-ttu-id="9007c-134">が選択されます。</span><span class="sxs-lookup"><span data-stu-id="9007c-134">is selected in the DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png" alt-text="Ringo ノードを検査する" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png":::
       <span data-ttu-id="9007c-136">ノードを検査する `Ringo`</span><span class="sxs-lookup"><span data-stu-id="9007c-136">Inspect the `Ringo` node</span></span>  
    :::image-end:::  
    
    1.  <span data-ttu-id="9007c-137">`Up`方向キーを2回押します。</span><span class="sxs-lookup"><span data-stu-id="9007c-137">Press the `Up` arrow key 2 times.</span></span>  `<ul>` <span data-ttu-id="9007c-138"> がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9007c-138">is selected.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png" alt-text="Ul ノードを検査する" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png":::
           <span data-ttu-id="9007c-140">ノードを検査する `ul`</span><span class="sxs-lookup"><span data-stu-id="9007c-140">Inspect the `ul` node</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="9007c-141">`Left`方向キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9007c-141">Press the `Left` arrow key.</span></span>  <span data-ttu-id="9007c-142">`<ul>`リストが折りたたまれます。</span><span class="sxs-lookup"><span data-stu-id="9007c-142">The `<ul>` list collapses.</span></span>  
    1.  <span data-ttu-id="9007c-143">`Left`もう一度方向キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9007c-143">Press the `Left` arrow key again.</span></span>  <span data-ttu-id="9007c-144">ノードの親 `<ul>` が選択されます。</span><span class="sxs-lookup"><span data-stu-id="9007c-144">The parent of the `<ul>` node is selected.</span></span>  <span data-ttu-id="9007c-145">この場合は、 `<div>` ID を使用し `navigate-the-dom-tree-with-a-keyboard-1` ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-145">In this case it is the `<div>` with the ID `navigate-the-dom-tree-with-a-keyboard-1`.</span></span>  
    1.  <span data-ttu-id="9007c-146">`Down`方向キーを2回押して、折りたたんだリストをもう一度選択し `<ul>` ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-146">Press the `Down` arrow key 2 times so that you have re-selected the `<ul>` list that you just collapsed.</span></span>  <span data-ttu-id="9007c-147">次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9007c-147">It should look like this:</span></span> `<ul>... </ul>`  
    1.  <span data-ttu-id="9007c-148">`Right`方向キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9007c-148">Press the `Right` arrow key.</span></span>  <span data-ttu-id="9007c-149">リストが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="9007c-149">The list expands.</span></span>  

### <span data-ttu-id="9007c-150">スクロールして表示する</span><span class="sxs-lookup"><span data-stu-id="9007c-150">Scroll into view</span></span>   

<span data-ttu-id="9007c-151">DOM ツリーを表示しているときに、現在ビューポート内にない DOM ノードに興味を持っていることがあります。</span><span class="sxs-lookup"><span data-stu-id="9007c-151">When viewing the DOM Tree, you may find yourself interested in a DOM node that is not currently in the viewport.</span></span>  <span data-ttu-id="9007c-152">たとえば、ページの一番下までスクロールして、ページの上部にあるノードに関心を持っているとし `<h1>` ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-152">For example, suppose that you scrolled to the bottom of the page, and you are interested in the `<h1>` node at the top of the page.</span></span>  <span data-ttu-id="9007c-153">**ビューをスクロール** すると、ビューポートをすばやく移動して、ノードを表示できます。</span><span class="sxs-lookup"><span data-stu-id="9007c-153">**Scroll into view** lets you quickly reposition the viewport so that you are able to see the node.</span></span>  

1.  <span data-ttu-id="9007c-154">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-154">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9007c-155">[ **スクロール**して表示] で、[ **Magritte** ] を右クリックし、[ **検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9007c-155">Under **Scroll into View**, right-click **Magritte** and select **Inspect**.</span></span>  
1.  <span data-ttu-id="9007c-156">DOM の [例] ページの一番下までスクロールします。</span><span class="sxs-lookup"><span data-stu-id="9007c-156">Scroll to the bottom of the DOM Examples page.</span></span>  
1.  <span data-ttu-id="9007c-157">`<li>Magritte</li>`それでも、ノードは DOM ツリーで選択されます。</span><span class="sxs-lookup"><span data-stu-id="9007c-157">The `<li>Magritte</li>` node should still be selected in your DOM Tree.</span></span>  <span data-ttu-id="9007c-158">表示されていない場合は、戻って、もう一度 [表示](#scroll-into-view) してみてください。</span><span class="sxs-lookup"><span data-stu-id="9007c-158">If not, go back to [Scroll into view](#scroll-into-view) and start over.</span></span>  
1.  <span data-ttu-id="9007c-159">ノードを右クリックし `<li>Magritte</li>` て、[ **ビューにスクロール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9007c-159">Right-click the `<li>Magritte</li>` node and select **Scroll into view**.</span></span>  <span data-ttu-id="9007c-160">ビューポートがスクロールして、 **Magritte** ノードが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="9007c-160">Your viewport scrolls back up so that you may see the **Magritte** node.</span></span>  <span data-ttu-id="9007c-161">[スクロールして**表示**する] オプションが表示されない場合は、「[付録: オプションが見つから](#appendix-missing-options)ない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9007c-161">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see the **Scroll into view** option.</span></span>
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="スクロールして表示する" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       **<span data-ttu-id="9007c-163">スクロールして表示する</span><span class="sxs-lookup"><span data-stu-id="9007c-163">Scroll into view</span></span>**  
    :::image-end:::  

### <span data-ttu-id="9007c-164">ノードを検索する</span><span class="sxs-lookup"><span data-stu-id="9007c-164">Search for nodes</span></span>   

<span data-ttu-id="9007c-165">DOM ツリーは、文字列、CSS セレクター、または XPath セレクターで検索できます。</span><span class="sxs-lookup"><span data-stu-id="9007c-165">You may search the DOM Tree by string, CSS selector, or XPath selector.</span></span>  

1.  <span data-ttu-id="9007c-166">カーソルを [ **要素** ] パネルにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="9007c-166">Focus your cursor on the **Elements** panel.</span></span>  
1.  <span data-ttu-id="9007c-167">`Control` + `F` \ (Windows \) または `Command` + `F` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="9007c-167">Press `Control`+`F` \(Windows\) or `Command`+`F` \(macOS\).</span></span>  <span data-ttu-id="9007c-168">検索バーは DOM ツリーの下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9007c-168">The Search bar opens at the bottom of the DOM Tree.</span></span>  
1.  <span data-ttu-id="9007c-169">「`The Moon is a Harsh Mistress`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9007c-169">Type `The Moon is a Harsh Mistress`.</span></span>  <span data-ttu-id="9007c-170">DOM ツリーの最後の文が強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="9007c-170">The last sentence is highlighted in the DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-search-nodes-highlight.msft.png" alt-text="検索バーでクエリを強調表示する" lightbox="../media/dom-elements-highlighted-search-nodes-highlight.msft.png":::
       <span data-ttu-id="9007c-172">検索バーでクエリを強調表示する</span><span class="sxs-lookup"><span data-stu-id="9007c-172">Highlight the query in the Search bar</span></span>  
    :::image-end:::  
    
<span data-ttu-id="9007c-173">上で説明したように、検索バーは CSS と XPath のセレクターもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9007c-173">As mentioned above, the Search bar also supports CSS and XPath selectors.</span></span>  

## <span data-ttu-id="9007c-174">DOM を編集する</span><span class="sxs-lookup"><span data-stu-id="9007c-174">Edit the DOM</span></span>   

<span data-ttu-id="9007c-175">その場で DOM を編集して、それらの変更がページにどのように影響するかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="9007c-175">You may edit the DOM on the fly and see how those changes affect the page.</span></span>  

### <span data-ttu-id="9007c-176">コンテンツを編集する</span><span class="sxs-lookup"><span data-stu-id="9007c-176">Edit content</span></span>   

<span data-ttu-id="9007c-177">ノードのコンテンツを編集するには、DOM ツリーでコンテンツをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="9007c-177">To edit the content of a node, double-click the content in the DOM Tree.</span></span>  

1.  <span data-ttu-id="9007c-178">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-178">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9007c-179">[ **コンテンツの編集**] で [ **micん le** ] を右クリックし、[ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9007c-179">Under **Edit Content**, right-click **Michelle** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="9007c-180">DOM ツリーで、をダブルクリック `Michelle` します。</span><span class="sxs-lookup"><span data-stu-id="9007c-180">In the DOM Tree, double-click `Michelle`.</span></span>  <span data-ttu-id="9007c-181">つまり、との間のテキストをダブルクリック `<li>` し `</li>` ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-181">In other words, double-click the text between `<li>` and `</li>`.</span></span>  <span data-ttu-id="9007c-182">テキストが強調表示され、選択されていることが示されます。</span><span class="sxs-lookup"><span data-stu-id="9007c-182">The text is highlighted to indicate that it is selected.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-content.msft.png" alt-text="テキストを編集する" lightbox="../media/dom-elements-highlighted-edit-content.msft.png":::
           <span data-ttu-id="9007c-184">テキストを編集する</span><span class="sxs-lookup"><span data-stu-id="9007c-184">Edit the text</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="9007c-185">を削除し `Michelle` て入力し、 `Leela` enter キーを押して `Enter` 変更を確定します。</span><span class="sxs-lookup"><span data-stu-id="9007c-185">Delete `Michelle`, type `Leela`, then press `Enter` to confirm the change.</span></span>  <span data-ttu-id="9007c-186">DOM 内のテキストは、 **MicLeela le**から**Leela**に変更されます。</span><span class="sxs-lookup"><span data-stu-id="9007c-186">The text in the DOM changes from **Michelle** to **Leela**.</span></span>  

### <span data-ttu-id="9007c-187">属性を編集する</span><span class="sxs-lookup"><span data-stu-id="9007c-187">Edit attributes</span></span>   

<span data-ttu-id="9007c-188">属性を編集するには、属性の名前または値をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="9007c-188">To edit attributes, double-click the attribute name or value.</span></span>  <span data-ttu-id="9007c-189">手順に従って、ノードに属性を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9007c-189">Follow the instructions to learn how to add attributes to a node.</span></span>  

1.  <span data-ttu-id="9007c-190">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-190">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9007c-191">[ **属性の編集**] で、[ **Howard** ] を右クリックし、[ **検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9007c-191">Under **Edit Attributes**, right-click **Howard** and select **Inspect**.</span></span>  
1.  <span data-ttu-id="9007c-192">ダブルクリック `<li>` します。</span><span class="sxs-lookup"><span data-stu-id="9007c-192">Double-click `<li>`.</span></span>  <span data-ttu-id="9007c-193">テキストが強調表示され、ノードが選択されていることが示されます。</span><span class="sxs-lookup"><span data-stu-id="9007c-193">The text is highlighted to indicate that the node is selected.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png" alt-text="ノードを編集する" lightbox="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png":::
       <span data-ttu-id="9007c-195">ノードを編集する</span><span class="sxs-lookup"><span data-stu-id="9007c-195">Edit the node</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9007c-196">方向キーを押して、スペースを追加し、 `Right` 「」と入力して `style="background-color:gold"` 、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-196">Press the `Right` arrow key, add a space, type `style="background-color:gold"`, and then press `Enter`.</span></span>  <span data-ttu-id="9007c-197">ノードの背景色が金色に変わります。</span><span class="sxs-lookup"><span data-stu-id="9007c-197">The background color of the node changes to gold.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png" alt-text="ノードにスタイル属性を追加する" lightbox="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png":::
       <span data-ttu-id="9007c-199">`style`ノードに属性を追加する</span><span class="sxs-lookup"><span data-stu-id="9007c-199">Add a `style` attribute to the node</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="9007c-200">ノードの種類を編集する</span><span class="sxs-lookup"><span data-stu-id="9007c-200">Edit node type</span></span>   

<span data-ttu-id="9007c-201">ノードの種類を編集するには、型をダブルクリックし、新しい型を入力します。</span><span class="sxs-lookup"><span data-stu-id="9007c-201">To edit the type of a node, double-click the type and then type in the new type.</span></span>  

1.  <span data-ttu-id="9007c-202">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-202">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9007c-203">[ **ノードの種類の編集**] で、[ **Hank** ] を右クリックし、[ **検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9007c-203">Under **Edit Node Type**, right-click **Hank** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="9007c-204">ダブルクリック `<li>` します。</span><span class="sxs-lookup"><span data-stu-id="9007c-204">Double-click `<li>`.</span></span>  <span data-ttu-id="9007c-205">テキスト `li` が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="9007c-205">The text `li` is highlighted.</span></span>  
    1.  <span data-ttu-id="9007c-206">を削除し `li` て、を入力し `button` `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-206">Delete `li`, type `button`, then press `Enter`.</span></span>  <span data-ttu-id="9007c-207">`<li>`ノードがノードに変わり `<button>` ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-207">The `<li>` node changes to a `<button>` node.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-node-type-button.msft.png" alt-text="ノードの種類を [ボタン] に変更する" lightbox="../media/dom-elements-highlighted-edit-node-type-button.msft.png":::
           <span data-ttu-id="9007c-209">ノードの種類を変更する</span><span class="sxs-lookup"><span data-stu-id="9007c-209">Change the node type to</span></span> `button`  
        :::image-end:::  
        
### <span data-ttu-id="9007c-210">DOM ノードの順序を変更する</span><span class="sxs-lookup"><span data-stu-id="9007c-210">Reorder DOM nodes</span></span>   

<span data-ttu-id="9007c-211">ノードをドラッグして順序を変更します。</span><span class="sxs-lookup"><span data-stu-id="9007c-211">Drag nodes to reorder them.</span></span>  

1.  <span data-ttu-id="9007c-212">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-212">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9007c-213">[ **DOM ノードの順序**変更] で、[ **Elvis Presley** ] を右クリックし、[ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9007c-213">Under **Reorder DOM Nodes**, right-click **Elvis Presley** and select **Inspect**.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="9007c-214">これは、リスト内の最後のアイテムです。</span><span class="sxs-lookup"><span data-stu-id="9007c-214">It is the last item in the list.</span></span>  
    
    1.  <span data-ttu-id="9007c-215">DOM ツリーで、 `<li>Elvis Presley</li>` 一覧の一番上までドラッグします。</span><span class="sxs-lookup"><span data-stu-id="9007c-215">In the DOM Tree, drag `<li>Elvis Presley</li>` to the top of the list.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-reorder-dom-nodes.msft.png" alt-text="ノードを一覧の一番上にドラッグする" lightbox="../media/dom-elements-reorder-dom-nodes.msft.png":::
           <span data-ttu-id="9007c-217">ノードを一覧の一番上にドラッグする</span><span class="sxs-lookup"><span data-stu-id="9007c-217">Drag the node to the top of the list</span></span>  
        :::image-end:::  
        
### <span data-ttu-id="9007c-218">強制状態</span><span class="sxs-lookup"><span data-stu-id="9007c-218">Force state</span></span>   

<span data-ttu-id="9007c-219">ノードは、、、、、などの状態に保つことができ `:active` `:hover` `:focus` `:visited` `:focus-within` ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-219">You are able to force nodes to remain in states including `:active`, `:hover`, `:focus`, `:visited`, and `:focus-within`.</span></span>  

1.  <span data-ttu-id="9007c-220">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-220">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9007c-221">[ **状態の強制**] で、 **その中の閣下**をポイントします。</span><span class="sxs-lookup"><span data-stu-id="9007c-221">Under **Force state**, hover over **The Lord of the Flies**.</span></span>  <span data-ttu-id="9007c-222">背景色がオレンジ色になります。</span><span class="sxs-lookup"><span data-stu-id="9007c-222">The background color becomes orange.</span></span>  
    1.  <span data-ttu-id="9007c-223">**フライの閣下**を右クリックして、[**検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9007c-223">Right-click **The Lord of the Flies** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="9007c-224">右クリック `<li class="demo--hover">The Lord of the Flies</li>` し、[**状態の強制**  >  **: hover**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9007c-224">Right-click `<li class="demo--hover">The Lord of the Flies</li>` and select **Force State** > **:hover**.</span></span>  <span data-ttu-id="9007c-225">このオプションが表示されない場合は、「 [付録: オプション](#appendix-missing-options) を表示しない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9007c-225">See [Appendix: Missing options](#appendix-missing-options) if you do not see this option.</span></span>  <span data-ttu-id="9007c-226">実際には、ノードの上にカーソルを置いていない場合でも、背景色はオレンジにとどまります。</span><span class="sxs-lookup"><span data-stu-id="9007c-226">The background color remains orange even though you are not actually hovering over the node.</span></span>  

### <span data-ttu-id="9007c-227">ノードを非表示にする</span><span class="sxs-lookup"><span data-stu-id="9007c-227">Hide a node</span></span>   

<span data-ttu-id="9007c-228">を押すと `H` 、ノードが非表示になります。</span><span class="sxs-lookup"><span data-stu-id="9007c-228">Press `H` to hide a node.</span></span>  

1.  <span data-ttu-id="9007c-229">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-229">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9007c-230">[ **ノードを非表示にする**] で、[ **宛先] の星** を右クリックし、[ **検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9007c-230">Under **Hide a node**, right-click **The Stars My Destination** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="9007c-231">キーを押し `H` ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-231">Press the `H` key.</span></span>  <span data-ttu-id="9007c-232">ノードが非表示になっています。</span><span class="sxs-lookup"><span data-stu-id="9007c-232">The node is hidden.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-hide-a-node.msft.png" alt-text="非表示になった後のノードが DOM ツリーのどのように見えるか" lightbox="../media/dom-elements-highlighted-hide-a-node.msft.png":::
           <span data-ttu-id="9007c-234">非表示になった後のノードが DOM ツリーのどのように見えるか</span><span class="sxs-lookup"><span data-stu-id="9007c-234">What the node looks like in the DOM Tree after it is hidden</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="9007c-235">キーを `H` もう一度押します。</span><span class="sxs-lookup"><span data-stu-id="9007c-235">Press the `H` key again.</span></span>  <span data-ttu-id="9007c-236">ノードが再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="9007c-236">The node is shown again.</span></span>  

### <span data-ttu-id="9007c-237">ノードを削除する</span><span class="sxs-lookup"><span data-stu-id="9007c-237">Delete a node</span></span>   

<span data-ttu-id="9007c-238">を押して `Delete` ノードを削除します。</span><span class="sxs-lookup"><span data-stu-id="9007c-238">Press `Delete` to delete a node.</span></span>  

1.  <span data-ttu-id="9007c-239">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-239">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9007c-240">[ **ノードの削除**] で、[ **Foundation** ] を右クリックし、[ **検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9007c-240">Under **Delete a Node**, right-click **Foundation** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="9007c-241">キーを押し `Delete` ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-241">Press the `Delete` key.</span></span>  <span data-ttu-id="9007c-242">ノードが削除されます。</span><span class="sxs-lookup"><span data-stu-id="9007c-242">The node is deleted.</span></span>  
    1.  <span data-ttu-id="9007c-243">`Control` + `Z` \ (Windows \) または `Command` + `Z` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="9007c-243">Press `Control`+`Z` \(Windows\) or `Command`+`Z` \(macOS\).</span></span>  <span data-ttu-id="9007c-244">直前の操作が取り消され、ノードが再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="9007c-244">The last action is undone and the node reappears.</span></span>  

## <span data-ttu-id="9007c-245">コンソールのアクセスノード</span><span class="sxs-lookup"><span data-stu-id="9007c-245">Access nodes in the Console</span></span>   

<span data-ttu-id="9007c-246">DevTools では、コンソールから DOM ノードにアクセスしたり、各デバイスへの JavaScript 参照を取得したりするためのショートカットキーをいくつか用意しています。</span><span class="sxs-lookup"><span data-stu-id="9007c-246">DevTools provides a few shortcuts for accessing DOM nodes from the Console, or getting JavaScript references to each one.</span></span>  

### <span data-ttu-id="9007c-247">$0 で現在選択されているノードを参照する</span><span class="sxs-lookup"><span data-stu-id="9007c-247">Reference the currently-selected node with $0</span></span>   

<span data-ttu-id="9007c-248">ノードを検査すると、 `== $0` ノードの横のテキストは、この変数を持つ本体でこのノードを参照できることを意味 `$0` します。</span><span class="sxs-lookup"><span data-stu-id="9007c-248">When you inspect a node, the `== $0` text next to the node means that you may reference this node in the Console with the variable `$0`.</span></span>  

1.  <span data-ttu-id="9007c-249">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-249">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9007c-250">[ **$0 で現在選択さ**れているノードを参照する] で、 **暗さの左側** を右クリックして [ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9007c-250">Under **Reference the currently-selected node with $0**, right-click **The Left Hand of Darkness** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="9007c-251">キーを押して、 `Escape` 本体の引き出しを開きます。</span><span class="sxs-lookup"><span data-stu-id="9007c-251">Press the `Escape` key to open the Console Drawer.</span></span>  
    1.  <span data-ttu-id="9007c-252">キーを入力 `$0` して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-252">Type `$0` and press the `Enter` key.</span></span>  <span data-ttu-id="9007c-253">この式の結果は、の `$0` 評価を示して `<li>The Left Hand of Darkness</li>` います。</span><span class="sxs-lookup"><span data-stu-id="9007c-253">The result of the expression shows that `$0` evaluates to `<li>The Left Hand of Darkness</li>`.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png" alt-text="本体の最初の $0 式の結果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png":::
            <span data-ttu-id="9007c-255">本体の最初の式の結果 `$0` **Console**</span><span class="sxs-lookup"><span data-stu-id="9007c-255">The result of the first `$0` expression in the **Console**</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="9007c-256">結果にマウスポインターを合わせます。</span><span class="sxs-lookup"><span data-stu-id="9007c-256">Hover over the result.</span></span>  <span data-ttu-id="9007c-257">ビューポートで、ノードが強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="9007c-257">The node is highlighted in the viewport.</span></span>  
    1.  <span data-ttu-id="9007c-258">`<li>Dune</li>`DOM ツリー内をクリックし、 `$0` コンソールをもう一度入力して、 `Enter` もう一度押します。</span><span class="sxs-lookup"><span data-stu-id="9007c-258">Click `<li>Dune</li>` in the DOM Tree, type `$0` in the Console again, and then press `Enter` again.</span></span>  <span data-ttu-id="9007c-259">次に、の `$0` ようにに評価さ `<li>Dune</li>` れます。</span><span class="sxs-lookup"><span data-stu-id="9007c-259">Now, `$0` evaluates to `<li>Dune</li>`.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png" alt-text="コンソールでの2番目の $0 式の結果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png":::
           <span data-ttu-id="9007c-261">コンソールの2番目の `$0` 式の**Console**結果</span><span class="sxs-lookup"><span data-stu-id="9007c-261">The result of the second `$0` expression in the **Console**</span></span>  
        :::image-end:::  
        
### <span data-ttu-id="9007c-262">グローバル変数として保存する</span><span class="sxs-lookup"><span data-stu-id="9007c-262">Store as global variable</span></span>   

<span data-ttu-id="9007c-263">何度もノードを参照する必要がある場合は、それをグローバル変数として保存します。</span><span class="sxs-lookup"><span data-stu-id="9007c-263">If you need to refer back to a node many times, store it as a global variable.</span></span>  

1.  <span data-ttu-id="9007c-264">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-264">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9007c-265">[ **グローバル変数として保存**] で、 **大きなスリープ状態** を右クリックし、[ **検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9007c-265">Under **Store as global variable**, right-click **The Big Sleep** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="9007c-266">DOM ツリーを右クリック `<li>The Big Sleep</li>` して、[ **グローバル変数として保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9007c-266">Right-click `<li>The Big Sleep</li>` in the DOM Tree and select **Store as global variable**.</span></span>  <span data-ttu-id="9007c-267">このオプションが表示されない場合は、「 [付録: オプション](#appendix-missing-options) を表示しない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9007c-267">See [Appendix: Missing options](#appendix-missing-options) if you do not see this option.</span></span>  
    1.  <span data-ttu-id="9007c-268">`temp1`コンソールに入力して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-268">Type `temp1` in the Console and then press `Enter`.</span></span>  <span data-ttu-id="9007c-269">この式の結果は、変数がノードに評価されることを示します。</span><span class="sxs-lookup"><span data-stu-id="9007c-269">The result of the expression shows that the variable evaluates to the node.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png" alt-text="Temp1 式の結果" lightbox="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png":::
           <span data-ttu-id="9007c-271">式の結果 `temp1`</span><span class="sxs-lookup"><span data-stu-id="9007c-271">The result of the `temp1` expression</span></span>  
        :::image-end:::  
        
### <span data-ttu-id="9007c-272">JS パスをコピーする</span><span class="sxs-lookup"><span data-stu-id="9007c-272">Copy JS path</span></span>   

<span data-ttu-id="9007c-273">自動テストで参照する必要がある場合は、JavaScript のパスをノードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="9007c-273">Copy the JavaScript path to a node when you need to reference it in an automated test.</span></span>  

1.  <span data-ttu-id="9007c-274">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-274">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9007c-275">[ **JS パスのコピー**] で、 **兄弟 Karamazov** を右クリックして [ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9007c-275">Under **Copy JS path**, right-click **The Brothers Karamazov** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="9007c-276">DOM ツリーを右クリック `<li>The Brothers Karamazov</li>` して、[ **Copy**  >  **コピーコピー JS Path**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9007c-276">Right-click `<li>The Brothers Karamazov</li>` in the DOM Tree and select **Copy** > **Copy JS Path**.</span></span>  <span data-ttu-id="9007c-277">`document.querySelector()`ノードに解決される式がクリップボードにコピーされました。</span><span class="sxs-lookup"><span data-stu-id="9007c-277">A `document.querySelector()` expression that resolves to the node has been copied to your clipboard.</span></span>  
    1.  <span data-ttu-id="9007c-278">`Control` + `V` 式をコンソールに貼り付けるには、\ (Windows \) または `Command` + `V` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="9007c-278">Press `Control`+`V` \(Windows\) or `Command`+`V` \(macOS\) to paste the expression into the Console.</span></span>  
    1.  <span data-ttu-id="9007c-279">を押して `Enter` 式を評価します。</span><span class="sxs-lookup"><span data-stu-id="9007c-279">Press `Enter` to evaluate the expression.</span></span>
        
        :::image type="complex" source="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png" alt-text="JS パスの式をコピーした結果" lightbox="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png":::
           <span data-ttu-id="9007c-281">**JS パス**の式をコピーした結果</span><span class="sxs-lookup"><span data-stu-id="9007c-281">The result of the **Copy JS Path** expression</span></span>  
        :::image-end:::  
        
## <span data-ttu-id="9007c-282">DOM の中断の変更</span><span class="sxs-lookup"><span data-stu-id="9007c-282">Break on DOM changes</span></span>   

<span data-ttu-id="9007c-283">DevTools を使うと、JavaScript が DOM を変更したときにページの JavaScript を一時停止することができます。</span><span class="sxs-lookup"><span data-stu-id="9007c-283">DevTools enables you to pause the JavaScript of a page when the JavaScript modifies the DOM.</span></span>  

### <span data-ttu-id="9007c-284">属性の変更の中断</span><span class="sxs-lookup"><span data-stu-id="9007c-284">Break on attribute modifications</span></span>   

<span data-ttu-id="9007c-285">ノードの任意の属性を変更する JavaScript を一時停止する場合は、属性変更ブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="9007c-285">Use attribute modification breakpoints when you want to pause the JavaScript that causes any attribute of a node to change.</span></span>  

1.  <span data-ttu-id="9007c-286">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-286">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9007c-287">[ **属性の変更を中断**] で、[ **Sauerkraut** ] を右クリックし、[ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9007c-287">Under **Break on attribute modifications**, right-click **Sauerkraut** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="9007c-288">DOM ツリーで右クリック `<li id="target">Sauerkraut</li>` し、[属性**の変更を中断**] を選択し  >  **Attribute Modifications**ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-288">In the DOM Tree, right-click `<li id="target">Sauerkraut</li>` and select **Break On** > **Attribute Modifications**.</span></span>  <span data-ttu-id="9007c-289">このオプションが表示されない場合は、「 [付録: 省略](#appendix-missing-options) 可能なオプション」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9007c-289">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see this option.</span></span>
        
        :::image type="complex" source="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png" alt-text="属性の変更の中断" lightbox="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png":::
           **<span data-ttu-id="9007c-291">属性の変更の中断</span><span class="sxs-lookup"><span data-stu-id="9007c-291">Break on attribute modifications</span></span>**  
        :::image-end:::  
        
    1.  <span data-ttu-id="9007c-292">次の手順では、ページのコードを一時停止するボタンをクリックするように指示されます。</span><span class="sxs-lookup"><span data-stu-id="9007c-292">In the next step you are going to be instructed to click a button that pauses the code of the page.</span></span>  <span data-ttu-id="9007c-293">ページが一時停止されると、ページをスクロールすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="9007c-293">After the page is paused you are no longer able to scroll the page.</span></span>  <span data-ttu-id="9007c-294">**Resume Script** ![ ][ImageResumeScriptIcon] ページを再びスクロールできるようにするには、[スクリプトの再開] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9007c-294">You must click **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\) in order to make the page scrollable again.</span></span>
        
        :::image type="complex" source="../media/dom-break-attribute-modifications-sources-paused-on.msft.png" alt-text="スクリプトの実行を再開する場所" lightbox="../media/dom-break-attribute-modifications-sources-paused-on.msft.png":::
           <span data-ttu-id="9007c-296">スクリプトの実行を再開する場所</span><span class="sxs-lookup"><span data-stu-id="9007c-296">Where to resume script running</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="9007c-297">上の [ **背景の設定** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9007c-297">Click the **Set Background** button above.</span></span>  <span data-ttu-id="9007c-298">これにより `style` 、ノードの属性がに設定され `background-color:thistle` ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-298">This sets the `style` attribute of the node to `background-color:thistle`.</span></span>  <span data-ttu-id="9007c-299">DevTools はページを一時停止し、属性が変更されたコードを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="9007c-299">DevTools pauses the page and highlights the code that caused the attribute to change.</span></span>  
    1.  <span data-ttu-id="9007c-300">**Resume Script** ![ ][ImageResumeScriptIcon] 前に説明したように、[スクリプトの再開] をクリックします (スクリプトを再開します)。</span><span class="sxs-lookup"><span data-stu-id="9007c-300">Click **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\), as mentioned earlier.</span></span>  
    
### <span data-ttu-id="9007c-301">ノード削除時の中断</span><span class="sxs-lookup"><span data-stu-id="9007c-301">Break on node removal</span></span>   

<span data-ttu-id="9007c-302">特定のノードが削除されたときに一時停止する場合は、ノード削除のブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="9007c-302">If you want to pause when a particular node is removed, use node removal breakpoints.</span></span>  

1.  <span data-ttu-id="9007c-303">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-303">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9007c-304">[ **ノード削除時の中断**] で、[ **Neuromancer** ] を右クリックし、[ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9007c-304">Under **Break on Node Removal**, right-click **Neuromancer** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="9007c-305">DOM ツリーで右クリック `<li id="target">Neuromancer</li>` し、[ノード**の削除時に中断**] を選択し  >  **Node Removal**ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-305">In the DOM Tree, right-click `<li id="target">Neuromancer</li>` and select **Break On** > **Node Removal**.</span></span>  <span data-ttu-id="9007c-306">このオプションが表示されない場合は、「 [付録: 省略](#appendix-missing-options) 可能なオプション」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9007c-306">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see this option.</span></span>  
    1.  <span data-ttu-id="9007c-307">上の [ **削除** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9007c-307">Click the **Delete** button above.</span></span>  <span data-ttu-id="9007c-308">DevTools はページを一時停止し、ノードの削除を引き起こしたコードを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="9007c-308">DevTools pauses the page and highlights the code that caused the node to be removed.</span></span>  
    1.  <span data-ttu-id="9007c-309">[ **スクリプトの再開** ] ![ をクリックします (スクリプトを再開し ][ImageResumeScriptIcon] ます)。</span><span class="sxs-lookup"><span data-stu-id="9007c-309">Click **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\).</span></span>  
    
### <span data-ttu-id="9007c-310">サブツリーの変更の中断</span><span class="sxs-lookup"><span data-stu-id="9007c-310">Break on subtree modifications</span></span>   

<span data-ttu-id="9007c-311">ノードにサブツリーの変更のブレークポイントを配置すると、ノードの子孫が追加または削除されると、DevTools によってページが一時停止します。</span><span class="sxs-lookup"><span data-stu-id="9007c-311">After you put a subtree modification breakpoint on a node, DevTools pauses the page when any of the descendants of the node are added or removed.</span></span>  

1.  <span data-ttu-id="9007c-312">[DOM の例を開き](#open-dom-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-312">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="9007c-313">[ **サブツリーの変更の中断**] で、[ **詳細] の炎** を右クリックして [ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9007c-313">Under **Break on Subtree Modifications**, right-click **A Fire Upon The Deep** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="9007c-314">DOM ツリーで、上のノードである右クリック `<ul id="target">` `<li>A Fire Upon the Deep</li>` し、[サブツリーの変更を**中断**] を選択し  >  **Subtree Modifications**ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-314">In the DOM Tree, right-click `<ul id="target">`, which is the node above `<li>A Fire Upon the Deep</li>`, and select **Break On** > **Subtree Modifications**.</span></span>  <span data-ttu-id="9007c-315">このオプションが表示されない場合は、「 [付録: 省略](#appendix-missing-options) 可能なオプション」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9007c-315">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see this option.</span></span>  
    1.  <span data-ttu-id="9007c-316">[ **子の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9007c-316">Click **Add Child**.</span></span>  <span data-ttu-id="9007c-317">ノードがリストに追加されたため、コードは一時停止し `<li>` ます。</span><span class="sxs-lookup"><span data-stu-id="9007c-317">The code pauses because a `<li>` node was added to the list.</span></span>  
    1.  <span data-ttu-id="9007c-318">[ **スクリプトの再開** ] ![ をクリックします (スクリプトを再開し ][ImageResumeScriptIcon] ます)。</span><span class="sxs-lookup"><span data-stu-id="9007c-318">Click **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\).</span></span>  
    
## <span data-ttu-id="9007c-319">次のステップ</span><span class="sxs-lookup"><span data-stu-id="9007c-319">Next steps</span></span>   

<span data-ttu-id="9007c-320">これは、DevTools の DOM 関連のほとんどの機能について説明しています。</span><span class="sxs-lookup"><span data-stu-id="9007c-320">That covers most of the DOM-related features in DevTools.</span></span>  <span data-ttu-id="9007c-321">残りの部分については、DOM ツリーのノードを右クリックし、このチュートリアルで説明していないその他のオプションを試してみることができます。</span><span class="sxs-lookup"><span data-stu-id="9007c-321">You are able to discover the rest of them by right-clicking nodes in the DOM Tree and experimenting with the other options that were not covered in this tutorial.</span></span>  <span data-ttu-id="9007c-322">「 [要素パネルのショートカットキー][DevToolsShortcutsElements]」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9007c-322">See also [Elements panel keyboard shortcuts][DevToolsShortcutsElements].</span></span>  

<span data-ttu-id="9007c-323">[Microsoft Edge DevTools のホームページ][MicrosoftEdgeDevTools]をチェックして、devtools で実行できるその他の情報をすべて見つけてください。</span><span class="sxs-lookup"><span data-stu-id="9007c-323">Check out the [Microsoft Edge DevTools homepage][MicrosoftEdgeDevTools] to discover everything else you are able to do with DevTools.</span></span>  

<!--See [Community](../index#community) if you want to contact the DevTools team or get help from the DevTools community.  -->  



## <span data-ttu-id="9007c-324">付録: HTML と DOM の比較</span><span class="sxs-lookup"><span data-stu-id="9007c-324">Appendix: HTML versus the DOM</span></span>   

<span data-ttu-id="9007c-325">以下のセクションでは、HTML と DOM の違いについて簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="9007c-325">The following section quickly explains the difference between HTML and the DOM.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="9007c-326">Web ブラウザーを使用してページを要求すると、サーバーは次のコードスニペットのような HTML を返します。</span><span class="sxs-lookup"><span data-stu-id="9007c-326">When you use a web browser to request a page, the server returns HTML like the following code snippet</span></span>  

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
      <span data-ttu-id="9007c-327">ブラウザーは HTML を解析し、次のようなオブジェクトのツリーを作成します。</span><span class="sxs-lookup"><span data-stu-id="9007c-327">The browser parses the HTML and creates a tree of objects like the following list.</span></span>  
      
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

<span data-ttu-id="9007c-328">ページのコンテンツを表す、このオブジェクトのツリーは DOM と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9007c-328">This tree of objects, or nodes, representing the content of the page is called the DOM.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="9007c-329">HTML と同じように見えますが、HTML の下部で参照されているスクリプトが次のコードスニペットを実行していることを考えてみてください。</span><span class="sxs-lookup"><span data-stu-id="9007c-329">Right now it looks the same as the HTML, but suppose that the script referenced at the bottom of the HTML runs the following code snippet.</span></span>  
      
      ```javascript
      const h1 = document.querySelector('h1');
      h1.parentElement.removeChild(h1);
      const p = document.createElement('p');
      p.textContent = 'Wildcard!';
      document.body.appendChild(p);
      ```  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="9007c-330">このコードは、 `h1` ノードを削除し、別の `p` ノードを DOM に追加します。</span><span class="sxs-lookup"><span data-stu-id="9007c-330">That code removes the `h1` node and adds another `p` node to the DOM.</span></span>  <span data-ttu-id="9007c-331">これで、完全な DOM に次のリストが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9007c-331">The complete DOM now displays the following list.</span></span>  
      
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

<span data-ttu-id="9007c-332">ページの HTML が DOM とは異なるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9007c-332">The HTML for the page is now different than the DOM.</span></span>  <span data-ttu-id="9007c-333">つまり、HTML は初期ページコンテンツを表し、DOM は現在のページコンテンツを表します。</span><span class="sxs-lookup"><span data-stu-id="9007c-333">In other words, HTML represents initial page content, and the DOM represents current page content.</span></span>  <span data-ttu-id="9007c-334">JavaScript がノードを追加、削除、または編集すると、DOM は HTML とは異なります。</span><span class="sxs-lookup"><span data-stu-id="9007c-334">When JavaScript adds, removes, or edits nodes, the DOM becomes different than the HTML.</span></span>  

<span data-ttu-id="9007c-335">詳細について [は、「DOM の概要][MDNIntroductionToDOM] 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9007c-335">See [Introduction to the DOM][MDNIntroductionToDOM] to learn more.</span></span>  

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

## <span data-ttu-id="9007c-336">付録: オプションが表示されない</span><span class="sxs-lookup"><span data-stu-id="9007c-336">Appendix: Missing options</span></span>   

<span data-ttu-id="9007c-337">このチュートリアルで説明する多くの手順では、DOM ツリーのノードを右クリックし、ポップアップ表示されるコンテキストメニューからオプションを選択するように指示されています。</span><span class="sxs-lookup"><span data-stu-id="9007c-337">Many of the instructions in this tutorial instruct you to right-click a node in the DOM Tree and then select an option from the context menu that pops up.</span></span>  <span data-ttu-id="9007c-338">コンテキストメニューに [指定] オプションが表示されない場合は、ノードのテキストを右クリックしてみてください。</span><span class="sxs-lookup"><span data-stu-id="9007c-338">If you do not see the specified option in the context menu, try right-clicking away from the node text.</span></span>  

:::image type="complex" source="../media/dom-elements-highlighted-right-click-right-side.msft.png" alt-text="すべてのオプションが表示されない場合は、ここをクリックします。" lightbox="../media/dom-elements-highlighted-right-click-right-side.msft.png":::
   <span data-ttu-id="9007c-340">すべてのオプションが表示されない場合は、ここをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9007c-340">Where to click if you are not seeing all the options</span></span>  
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
> <span data-ttu-id="9007c-346">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="9007c-346">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9007c-347">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/dom/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="9007c-347">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/dom/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="9007c-349">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="9007c-349">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
