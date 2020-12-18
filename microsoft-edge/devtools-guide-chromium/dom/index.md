---
description: ノードの表示方法、ノードの検索方法、ノードの編集方法、コンソール内の参照ノードの表示方法、ノードの変更時のブレーク方法などについて説明します。
title: DOM の表示と変更を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 5b12b984aed7e35ce11dd45e8bc33f5d5fd454f8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231105"
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

# <span data-ttu-id="4af9e-104">DOM の表示と変更を開始する</span><span class="sxs-lookup"><span data-stu-id="4af9e-104">Get started with viewing and changing the DOM</span></span>  

<span data-ttu-id="4af9e-105">これらの対話型チュートリアルを実行して、Microsoft Edge DevTools を使用してページの DOM を表示および変更する方法の基本について説明します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-105">Complete these interactive tutorials to learn the basics of viewing and changing the DOM of a page using Microsoft Edge DevTools.</span></span>  

<span data-ttu-id="4af9e-106">このチュートリアルでは、DOM と HTML の違いを知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4af9e-106">This tutorial assumes that you know the difference between the DOM and HTML.</span></span>  <span data-ttu-id="4af9e-107">説明については [、「付録: HTML と DOM」](#appendix-html-versus-the-dom) に移動します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-107">Navigate to [Appendix: HTML versus the DOM](#appendix-html-versus-the-dom) for an explanation.</span></span>  

## <span data-ttu-id="4af9e-108">DOM を開く例</span><span class="sxs-lookup"><span data-stu-id="4af9e-108">Open DOM examples</span></span>  

1.  <span data-ttu-id="4af9e-109">`Control`\(Windows, Linux\) または `Command` \(macOS\) を保持し **、[DOM の**例] を選択して新しいタブで開きます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-109">Hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and choose **DOM Examples** to open in a new tab.</span></span>  
    
    [<span data-ttu-id="4af9e-110">DOM の例</span><span class="sxs-lookup"><span data-stu-id="4af9e-110">DOM Examples</span></span>][GlitchDomExamples]  
    
## <span data-ttu-id="4af9e-111">DOM ノードの表示</span><span class="sxs-lookup"><span data-stu-id="4af9e-111">View DOM nodes</span></span>  

<span data-ttu-id="4af9e-112">要素パネルの DOM ツリーは、DevTools で DOM 関連のすべてのアクティビティを実行する場所です。</span><span class="sxs-lookup"><span data-stu-id="4af9e-112">The DOM Tree of the Elements panel is where you do all DOM-related activities in DevTools.</span></span>  

### <span data-ttu-id="4af9e-113">ノードを検査する</span><span class="sxs-lookup"><span data-stu-id="4af9e-113">Inspect a node</span></span>  

<span data-ttu-id="4af9e-114">特定の DOM ノードに関心がある場合 **、Inspect** は DevTools を開いてそのノードを調査する高速な方法です。</span><span class="sxs-lookup"><span data-stu-id="4af9e-114">When you are interested in a particular DOM node, **Inspect** is a fast way to open DevTools and investigate that node.</span></span>  

1.  <span data-ttu-id="4af9e-115">[DOM を開く例](#open-dom-examples)</span><span class="sxs-lookup"><span data-stu-id="4af9e-115">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="4af9e-116">[ **ノードの検査] で、Michel** **michel** を右クリックして [検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-116">Under **Inspect a Node**, right-choose **Michelangelo** and choose **Inspect**.</span></span>  
    
    :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png" alt-text="ノードを検査する" lightbox="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png":::
       <span data-ttu-id="4af9e-118">ノードを検査する</span><span class="sxs-lookup"><span data-stu-id="4af9e-118">Inspect a node</span></span>  
    :::image-end:::  
    
    1.  <span data-ttu-id="4af9e-119">DevTools **の要素** パネルが開きます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-119">The **Elements** panel of DevTools opens.</span></span>  `<li>Michelangelo</li>` <span data-ttu-id="4af9e-120">が DOM ツリーで **強調表示されます**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-120">is highlighted in the **DOM Tree**.</span></span>  
        
        :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png" alt-text="Michel michel ノードを強調表示する" lightbox="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png":::
           <span data-ttu-id="4af9e-122">ノードを強調表示 `Michelangelo` する</span><span class="sxs-lookup"><span data-stu-id="4af9e-122">Highlight the `Michelangelo` node</span></span>  
        :::image-end:::  
        
        1.  <span data-ttu-id="4af9e-123">DevTools **の左上隅** にある Inspect ![ \( Inspect ][ImageInspectIcon] \) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4af9e-123">Click the **Inspect** \(![Inspect][ImageInspectIcon]\) icon in the top-left corner of DevTools.</span></span>  
            
            :::image type="complex" source="../media/dom-elements-highlighted-select-element-page-inspect.msft.png" alt-text="[検査] アイコン" lightbox="../media/dom-elements-highlighted-select-element-page-inspect.msft.png":::
               <span data-ttu-id="4af9e-125">[ **検査]** アイコン</span><span class="sxs-lookup"><span data-stu-id="4af9e-125">The **Inspect** icon</span></span>  
            :::image-end:::  
            
1.  <span data-ttu-id="4af9e-126">[ **ノードの検査] で**、[東京] テキスト **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-126">Under **Inspect a Node**, click the **Tokyo** text.</span></span>  <span data-ttu-id="4af9e-127">これで `<li>Tokyo</li>` 、DOM ツリーで強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-127">Now, `<li>Tokyo</li>` is highlighted in the DOM Tree.</span></span>  

<span data-ttu-id="4af9e-128">ノードを検査する手順は、ノードのスタイルを表示および変更する最初の手順です。</span><span class="sxs-lookup"><span data-stu-id="4af9e-128">Inspecting a node is also the first step towards viewing and changing the styles of a node.</span></span>  <span data-ttu-id="4af9e-129">CSS の [表示と変更の開始に移動します][DevToolsCssGetStarted]。</span><span class="sxs-lookup"><span data-stu-id="4af9e-129">Navigate to [Get Started With Viewing And Changing CSS][DevToolsCssGetStarted].</span></span>  

### <span data-ttu-id="4af9e-130">キーボードを使用して DOM ツリー内を移動する</span><span class="sxs-lookup"><span data-stu-id="4af9e-130">Navigate the DOM Tree with a keyboard</span></span>  

<span data-ttu-id="4af9e-131">DOM ツリーでノードを選択したら、キーボードを使用して DOM ツリー内を移動できます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-131">Once you have selected a node in the DOM Tree, you may navigate the DOM Tree with your keyboard.</span></span>  

1.  <span data-ttu-id="4af9e-132">[DOM を開く例](#open-dom-examples)</span><span class="sxs-lookup"><span data-stu-id="4af9e-132">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="4af9e-133">[ **キーボードを使用して DOM ツリーを移動する]** で **、[Ringo]** を右クリックして [検査] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-133">Under **Navigate the DOM Tree with a Keyboard**, right-choose **Ringo** and choose **Inspect**.</span></span>  `<li>Ringo</li>` <span data-ttu-id="4af9e-134">が DOM ツリーで選択されています。</span><span class="sxs-lookup"><span data-stu-id="4af9e-134">is selected in the DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png" alt-text="[リング] ノードを検査する" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png":::
       <span data-ttu-id="4af9e-136">ノードを検査 `Ringo` する</span><span class="sxs-lookup"><span data-stu-id="4af9e-136">Inspect the `Ringo` node</span></span>  
    :::image-end:::  
    
    1.  <span data-ttu-id="4af9e-137">方向キー `Up` を 2 回押します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-137">Press the `Up` arrow key 2 times.</span></span>  `<ul>` <span data-ttu-id="4af9e-138"> がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-138">is selected.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png" alt-text="ul ノードを検査する" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png":::
           <span data-ttu-id="4af9e-140">ノードを検査 `ul` する</span><span class="sxs-lookup"><span data-stu-id="4af9e-140">Inspect the `ul` node</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="4af9e-141">方向キー `Left` を押します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-141">Press the `Left` arrow key.</span></span>  <span data-ttu-id="4af9e-142">リスト `<ul>` が折りたたむ。</span><span class="sxs-lookup"><span data-stu-id="4af9e-142">The `<ul>` list collapses.</span></span>  
    1.  <span data-ttu-id="4af9e-143">もう一度 `Left` 方向キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-143">Press the `Left` arrow key again.</span></span>  <span data-ttu-id="4af9e-144">ノードの親 `<ul>` が選択されます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-144">The parent of the `<ul>` node is selected.</span></span>  <span data-ttu-id="4af9e-145">この場合、ID `<div>` は次の ID です `navigate-the-dom-tree-with-a-keyboard-1` 。</span><span class="sxs-lookup"><span data-stu-id="4af9e-145">In this case it is the `<div>` with the ID `navigate-the-dom-tree-with-a-keyboard-1`.</span></span>  
    1.  <span data-ttu-id="4af9e-146">折りたたみしたリストを再選択するには、方向キーを `Down` 2 `<ul>` 回押します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-146">Press the `Down` arrow key 2 times so that you have re-selected the `<ul>` list that you just collapsed.</span></span>  <span data-ttu-id="4af9e-147">次のようになります。</span><span class="sxs-lookup"><span data-stu-id="4af9e-147">It should look like this:</span></span> `<ul>... </ul>`  
    1.  <span data-ttu-id="4af9e-148">方向キー `Right` を押します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-148">Press the `Right` arrow key.</span></span>  <span data-ttu-id="4af9e-149">リストが展開されます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-149">The list expands.</span></span>  

### <span data-ttu-id="4af9e-150">スクロールして表示</span><span class="sxs-lookup"><span data-stu-id="4af9e-150">Scroll into view</span></span>  

<span data-ttu-id="4af9e-151">DOM ツリーを表示するときに、現在ビューポートに含されていない DOM ノードに興味がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="4af9e-151">When viewing the DOM Tree, you may find yourself interested in a DOM node that is not currently in the viewport.</span></span>  <span data-ttu-id="4af9e-152">たとえば、ページの一番下までスクロールし、ページの上部にあるノードに関心を持った `<h1>` とします。</span><span class="sxs-lookup"><span data-stu-id="4af9e-152">For example, suppose that you scrolled to the bottom of the page, and you are interested in the `<h1>` node at the top of the page.</span></span>  <span data-ttu-id="4af9e-153">**ビュー内にスクロール** すると、ビューポートをすばやく再配置して、ノードを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-153">**Scroll into view** lets you quickly reposition the viewport so that you are able to review the node.</span></span>  

1.  <span data-ttu-id="4af9e-154">[DOM を開く例](#open-dom-examples)</span><span class="sxs-lookup"><span data-stu-id="4af9e-154">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="4af9e-155">[ **表示] にスクロールし**、[Magritte] を **右** クリックして [検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-155">Under **Scroll into View**, right-choose **Magritte** and choose **Inspect**.</span></span>  
1.  <span data-ttu-id="4af9e-156">DOM の [例] ページの下部までスクロールします。</span><span class="sxs-lookup"><span data-stu-id="4af9e-156">Scroll to the bottom of the DOM Examples page.</span></span>  
1.  <span data-ttu-id="4af9e-157">ノード `<li>Magritte</li>` は、DOM ツリーで引き続き選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4af9e-157">The `<li>Magritte</li>` node should still be selected in your DOM Tree.</span></span>  <span data-ttu-id="4af9e-158">表示されていない場合は、[スクロールして表示 [] に戻り、最初](#scroll-into-view) から最初から実行します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-158">If not, go back to [Scroll into view](#scroll-into-view) and start over.</span></span>  
1.  <span data-ttu-id="4af9e-159">ノードをポイントし、コンテキスト メニュー \(右クリック\) を開き、[スクロールして表示 `<li>Magritte</li>` **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-159">Hover on the `<li>Magritte</li>` node, open the contextual menu \(right-click\), and choose **Scroll into view**.</span></span>  <span data-ttu-id="4af9e-160">ビューポートが上にスクロールして **、Magritte ノードを確認** できます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-160">Your viewport scrolls back up so that you may review the **Magritte** node.</span></span>  <span data-ttu-id="4af9e-161">[付録 [: 表示にスクロール]](#appendix-missing-options) オプションを確認できない場合は、[付録: 不足しているオプション] **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-161">Navigate to [Appendix: Missing options](#appendix-missing-options) if you are not able to review the **Scroll into view** option.</span></span>
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="スクロールして表示" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       **<span data-ttu-id="4af9e-163">スクロールして表示</span><span class="sxs-lookup"><span data-stu-id="4af9e-163">Scroll into view</span></span>**  
    :::image-end:::  

### <span data-ttu-id="4af9e-164">ノードの検索</span><span class="sxs-lookup"><span data-stu-id="4af9e-164">Search for nodes</span></span>  

<span data-ttu-id="4af9e-165">DOM ツリーは、文字列、CSS セレクター、または XPath セレクターで検索できます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-165">You may search the DOM Tree by string, CSS selector, or XPath selector.</span></span>  

1.  <span data-ttu-id="4af9e-166">[要素] パネルにカーソル **を移動** します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-166">Focus your cursor on the **Elements** panel.</span></span>  
1.  <span data-ttu-id="4af9e-167">`Control` + `F` \(Windows,Linux\) または `Command` + `F` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-167">Select `Control`+`F` \(Windows, Linux\) or `Command`+`F` \(macOS\).</span></span>  <span data-ttu-id="4af9e-168">DOM ツリーの下部に検索バーが開きます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-168">The Search bar opens at the bottom of the DOM Tree.</span></span>  
1.  <span data-ttu-id="4af9e-169">「`The Moon is a Harsh Mistress`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-169">Type `The Moon is a Harsh Mistress`.</span></span>  <span data-ttu-id="4af9e-170">DOM ツリーで最後の文が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-170">The last sentence is highlighted in the DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-search-nodes-highlight.msft.png" alt-text="検索バーでクエリを強調表示する" lightbox="../media/dom-elements-highlighted-search-nodes-highlight.msft.png":::
       <span data-ttu-id="4af9e-172">検索バーでクエリを強調表示する</span><span class="sxs-lookup"><span data-stu-id="4af9e-172">Highlight the query in the Search bar</span></span>  
    :::image-end:::  
    
<span data-ttu-id="4af9e-173">前述のように、検索バーは CSS セレクターと XPath セレクターもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4af9e-173">As mentioned above, the Search bar also supports CSS and XPath selectors.</span></span>  

## <span data-ttu-id="4af9e-174">DOM を編集する</span><span class="sxs-lookup"><span data-stu-id="4af9e-174">Edit the DOM</span></span>  

<span data-ttu-id="4af9e-175">オンザフライで DOM を編集し、変更がページに与える影響を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-175">You may edit the DOM on the fly and review how the changes affect the page.</span></span>  

### <span data-ttu-id="4af9e-176">コンテンツを編集する</span><span class="sxs-lookup"><span data-stu-id="4af9e-176">Edit content</span></span>  

<span data-ttu-id="4af9e-177">ノードのコンテンツを編集するには、DOM ツリー内のコンテンツをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="4af9e-177">To edit the content of a node, double-click the content in the DOM Tree.</span></span>  

1.  <span data-ttu-id="4af9e-178">[DOM を開く例](#open-dom-examples)</span><span class="sxs-lookup"><span data-stu-id="4af9e-178">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="4af9e-179">[コンテンツ **の編集]** で **、Michelle** を右クリックして [検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-179">Under **Edit Content**, right-choose **Michelle** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="4af9e-180">DOM ツリーで、ダブルクリックします `Michelle` 。</span><span class="sxs-lookup"><span data-stu-id="4af9e-180">In the DOM Tree, double-click `Michelle`.</span></span>  <span data-ttu-id="4af9e-181">つまり、次の間にあるテキストを `<li>` ダブルクリックします `</li>` 。</span><span class="sxs-lookup"><span data-stu-id="4af9e-181">In other words, double-click the text between `<li>` and `</li>`.</span></span>  <span data-ttu-id="4af9e-182">テキストが強調表示され、選択されている状態が示されます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-182">The text is highlighted to indicate that it is selected.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-content.msft.png" alt-text="テキストを編集する" lightbox="../media/dom-elements-highlighted-edit-content.msft.png":::
           <span data-ttu-id="4af9e-184">テキストを編集する</span><span class="sxs-lookup"><span data-stu-id="4af9e-184">Edit the text</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="4af9e-185">[ `Michelle` 削除] を `Leela` 入力し、変更 `Enter` の確認を選択します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-185">Delete `Michelle`, type `Leela`, then select `Enter` to confirm the change.</span></span>  <span data-ttu-id="4af9e-186">DOM 内のテキストが **Michelle** から **Leela に変更されます**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-186">The text in the DOM changes from **Michelle** to **Leela**.</span></span>  

### <span data-ttu-id="4af9e-187">属性の編集</span><span class="sxs-lookup"><span data-stu-id="4af9e-187">Edit attributes</span></span>  

<span data-ttu-id="4af9e-188">属性を編集するには、属性の名前または値をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="4af9e-188">To edit attributes, double-click the attribute name or value.</span></span>  <span data-ttu-id="4af9e-189">指示に従って、ノードに属性を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-189">Follow the instructions to learn how to add attributes to a node.</span></span>  

1.  <span data-ttu-id="4af9e-190">[DOM を開く例](#open-dom-examples)</span><span class="sxs-lookup"><span data-stu-id="4af9e-190">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="4af9e-191">[ **属性の編集]** で **[Howard]** を右クリックし、[検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-191">Under **Edit Attributes**, right-choose **Howard** and choose **Inspect**.</span></span>  
1.  <span data-ttu-id="4af9e-192">ダブルクリック `<li>` します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-192">Double-click `<li>`.</span></span>  <span data-ttu-id="4af9e-193">テキストが強調表示され、ノードが選択されています。</span><span class="sxs-lookup"><span data-stu-id="4af9e-193">The text is highlighted to indicate that the node is selected.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png" alt-text="ノードを編集する" lightbox="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png":::
       <span data-ttu-id="4af9e-195">ノードを編集する</span><span class="sxs-lookup"><span data-stu-id="4af9e-195">Edit the node</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="4af9e-196">方向キー `Right` を押し、スペースを追加し、入力 `style="background-color:gold"` して、選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="4af9e-196">Press the `Right` arrow key, add a space, type `style="background-color:gold"`, and then select `Enter`.</span></span>  <span data-ttu-id="4af9e-197">ノードの背景色がゴールドに変更されます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-197">The background color of the node changes to gold.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png" alt-text="ノードに style 属性を追加する" lightbox="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png":::
       <span data-ttu-id="4af9e-199">ノード `style` に属性を追加する</span><span class="sxs-lookup"><span data-stu-id="4af9e-199">Add a `style` attribute to the node</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="4af9e-200">ノードの種類の編集</span><span class="sxs-lookup"><span data-stu-id="4af9e-200">Edit node type</span></span>  

<span data-ttu-id="4af9e-201">ノードの種類を編集するには、種類をダブルクリックし、新しい種類を入力します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-201">To edit the type of a node, double-click the type and then type in the new type.</span></span>  

1.  <span data-ttu-id="4af9e-202">[DOM を開く例](#open-dom-examples)</span><span class="sxs-lookup"><span data-stu-id="4af9e-202">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="4af9e-203">[**ノードの種類の編集] で\*\*\*\*、[Hank]** を右クリックして [検査] を**選択します**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-203">Under **Edit Node Type**, right-choose **Hank** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="4af9e-204">ダブルクリック `<li>` します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-204">Double-click `<li>`.</span></span>  <span data-ttu-id="4af9e-205">テキストが `li` 強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-205">The text `li` is highlighted.</span></span>  
    1.  <span data-ttu-id="4af9e-206">Delete `li` , type , then select `button` `Enter` .</span><span class="sxs-lookup"><span data-stu-id="4af9e-206">Delete `li`, type `button`, then select `Enter`.</span></span>  <span data-ttu-id="4af9e-207">ノード `<li>` がノードに変更 `<button>` されます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-207">The `<li>` node changes to a `<button>` node.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-node-type-button.msft.png" alt-text="ノードの種類をボタンに変更する" lightbox="../media/dom-elements-highlighted-edit-node-type-button.msft.png":::
           <span data-ttu-id="4af9e-209">ノードの種類を次に変更します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-209">Change the node type to</span></span> `button`  
        :::image-end:::  
        
### <span data-ttu-id="4af9e-210">DOM ノードを並べ替える</span><span class="sxs-lookup"><span data-stu-id="4af9e-210">Reorder DOM nodes</span></span>  

<span data-ttu-id="4af9e-211">ノードをドラッグして並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-211">Drag nodes to reorder them.</span></span>  

1.  <span data-ttu-id="4af9e-212">[DOM を開く例](#open-dom-examples)</span><span class="sxs-lookup"><span data-stu-id="4af9e-212">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="4af9e-213">[DOM **ノードの並べ替え**] で **、Elvis Presley** を右クリックして [検査] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-213">Under **Reorder DOM Nodes**, right-choose **Elvis Presley** and choose **Inspect**.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="4af9e-214">リスト内の最後のアイテムです。</span><span class="sxs-lookup"><span data-stu-id="4af9e-214">It is the last item in the list.</span></span>  
    
    1.  <span data-ttu-id="4af9e-215">DOM ツリーで、リスト `<li>Elvis Presley</li>` の一番上にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="4af9e-215">In the DOM Tree, drag `<li>Elvis Presley</li>` to the top of the list.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-reorder-dom-nodes.msft.png" alt-text="ノードをリストの一番上にドラッグします。" lightbox="../media/dom-elements-reorder-dom-nodes.msft.png":::
           <span data-ttu-id="4af9e-217">ノードをリストの一番上にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="4af9e-217">Drag the node to the top of the list</span></span>  
        :::image-end:::  
        
### <span data-ttu-id="4af9e-218">強制状態</span><span class="sxs-lookup"><span data-stu-id="4af9e-218">Force state</span></span>  

<span data-ttu-id="4af9e-219">ノードを強制的に状態 (、 など) `:active` `:hover` `:focus` `:visited` に維持することができます `:focus-within` 。</span><span class="sxs-lookup"><span data-stu-id="4af9e-219">You are able to force nodes to remain in states including `:active`, `:hover`, `:focus`, `:visited`, and `:focus-within`.</span></span>  

1.  <span data-ttu-id="4af9e-220">[DOM を開く例](#open-dom-examples)</span><span class="sxs-lookup"><span data-stu-id="4af9e-220">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="4af9e-221">[ **強制] 状態の**下で **、[Flies の指定] の上にマウス ポインターを移動します**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-221">Under **Force state**, hover over **The Lord of the Flies**.</span></span>  <span data-ttu-id="4af9e-222">背景色はオレンジ色になります。</span><span class="sxs-lookup"><span data-stu-id="4af9e-222">The background color becomes orange.</span></span>  
    1.  <span data-ttu-id="4af9e-223">**[Flies の指定] を右クリックし、[検査]** を**選択します**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-223">Right-choose **The Lord of the Flies** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="4af9e-224">右クリックし、 `<li class="demo--hover">The Lord of the Flies</li>` 強制状態\*\*\*\*  >  **:hover を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-224">Right-click `<li class="demo--hover">The Lord of the Flies</li>` and choose **Force State** > **:hover**.</span></span>  <span data-ttu-id="4af9e-225">オプションが [表示されない場合は、「付録:](#appendix-missing-options) 不足しているオプション」に移動します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-225">Navigate to [Appendix: Missing options](#appendix-missing-options) if the option is not displayed.</span></span>  <span data-ttu-id="4af9e-226">実際にノードの上にカーソルを置いなくても、背景色はオレンジ色のままです。</span><span class="sxs-lookup"><span data-stu-id="4af9e-226">The background color remains orange even though you are not actually hovering over the node.</span></span>  

### <span data-ttu-id="4af9e-227">ノードを非表示にする</span><span class="sxs-lookup"><span data-stu-id="4af9e-227">Hide a node</span></span>  

<span data-ttu-id="4af9e-228">ノード `H` を非表示にする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-228">Select `H` to hide a node.</span></span>  

1.  <span data-ttu-id="4af9e-229">[DOM を開く例](#open-dom-examples)</span><span class="sxs-lookup"><span data-stu-id="4af9e-229">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="4af9e-230">[ **ノードを非表示にする] で**、[星の宛先] を右クリック **し** 、[検査] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-230">Under **Hide a node**, right-choose **The Stars My Destination** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="4af9e-231">キーを押 `H` します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-231">Press the `H` key.</span></span>  <span data-ttu-id="4af9e-232">ノードは非表示です。</span><span class="sxs-lookup"><span data-stu-id="4af9e-232">The node is hidden.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-hide-a-node.msft.png" alt-text="DOM ツリーが非表示にされた後のノードの外観" lightbox="../media/dom-elements-highlighted-hide-a-node.msft.png":::
           <span data-ttu-id="4af9e-234">DOM ツリーが非表示にされた後のノードの外観</span><span class="sxs-lookup"><span data-stu-id="4af9e-234">What the node looks like in the DOM Tree after it is hidden</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="4af9e-235">もう一度 `H` キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-235">Press the `H` key again.</span></span>  <span data-ttu-id="4af9e-236">ノードが再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-236">The node is shown again.</span></span>  

### <span data-ttu-id="4af9e-237">ノードを削除する</span><span class="sxs-lookup"><span data-stu-id="4af9e-237">Delete a node</span></span>  

<span data-ttu-id="4af9e-238">ノード `Delete` を削除する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-238">Select `Delete` to delete a node.</span></span>  

1.  <span data-ttu-id="4af9e-239">[DOM を開く例](#open-dom-examples)</span><span class="sxs-lookup"><span data-stu-id="4af9e-239">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="4af9e-240">Under **Delete a Node,** right-choose **Foundation** and choose **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="4af9e-240">Under **Delete a Node**, right-choose **Foundation** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="4af9e-241">キーを押 `Delete` します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-241">Press the `Delete` key.</span></span>  <span data-ttu-id="4af9e-242">ノードが削除されます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-242">The node is deleted.</span></span>  
    1.  <span data-ttu-id="4af9e-243">`Control` + `Z` \(Windows,Linux\) または `Command` + `Z` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-243">Select `Control`+`Z` \(Windows, Linux\) or `Command`+`Z` \(macOS\).</span></span>  <span data-ttu-id="4af9e-244">最後の操作が取り消され、ノードが再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-244">The last action is undone and the node reappears.</span></span>  

## <span data-ttu-id="4af9e-245">コンソール内のアクセス ノード</span><span class="sxs-lookup"><span data-stu-id="4af9e-245">Access nodes in the Console</span></span>  

<span data-ttu-id="4af9e-246">DevTools には、コンソールから DOM ノードにアクセスしたり、各ノードへの JavaScript 参照を取得したりするために、いくつかのショートカットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4af9e-246">DevTools provides a few shortcuts for accessing DOM nodes from the Console, or getting JavaScript references to each one.</span></span>  

### <span data-ttu-id="4af9e-247">現在選択されているノードを $0 で参照する</span><span class="sxs-lookup"><span data-stu-id="4af9e-247">Reference the currently-selected node with $0</span></span>  

<span data-ttu-id="4af9e-248">ノードを検査する場合、ノードの横のテキストは、コンソールでこのノードを変数と一緒 `== $0` に参照できる可能性を意味します `$0` 。</span><span class="sxs-lookup"><span data-stu-id="4af9e-248">When you inspect a node, the `== $0` text next to the node means that you may reference this node in the Console with the variable `$0`.</span></span>  

1.  <span data-ttu-id="4af9e-249">[DOM を開く例](#open-dom-examples)</span><span class="sxs-lookup"><span data-stu-id="4af9e-249">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="4af9e-250">[Reference **the currently-selected node with $0] ($0**で現在選択されているノードを参照する) の下で **、[The Left Hand of The Left Hand of The Darkness]** を右クリックし **、[Inspect]**(検査) を選択します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-250">Under **Reference the currently-selected node with $0**, right-choose **The Left Hand of Darkness** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="4af9e-251">キーを押 `Escape` してコンソール ドロワーを開きます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-251">Press the `Escape` key to open the Console Drawer.</span></span>  
    1.  <span data-ttu-id="4af9e-252">キー `$0` を入力して押 `Enter` します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-252">Type `$0` and press the `Enter` key.</span></span>  <span data-ttu-id="4af9e-253">式の結果は、次の値 `$0` に評価されます `<li>The Left Hand of Darkness</li>` 。</span><span class="sxs-lookup"><span data-stu-id="4af9e-253">The result of the expression shows that `$0` evaluates to `<li>The Left Hand of Darkness</li>`.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png" alt-text="コンソール内の最初の $0 式の結果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png":::
            <span data-ttu-id="4af9e-255">コンソール内の最初の `$0` 式の **結果**</span><span class="sxs-lookup"><span data-stu-id="4af9e-255">The result of the first `$0` expression in the **Console**</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="4af9e-256">結果の上にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-256">Hover over the result.</span></span>  <span data-ttu-id="4af9e-257">ノードはビューポートで強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-257">The node is highlighted in the viewport.</span></span>  
    1.  <span data-ttu-id="4af9e-258">`<li>Dune</li>`DOM ツリーをクリックし、コンソール `$0` にもう一度入力して、もう一度選択 `Enter` します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-258">Click `<li>Dune</li>` in the DOM Tree, type `$0` in the Console again, and then select `Enter` again.</span></span>  <span data-ttu-id="4af9e-259">次に、 `$0` 次の値に評価されます `<li>Dune</li>` 。</span><span class="sxs-lookup"><span data-stu-id="4af9e-259">Now, `$0` evaluates to `<li>Dune</li>`.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png" alt-text="コンソール内の 2 番目の $0 式の結果" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png":::
           <span data-ttu-id="4af9e-261">コンソール内の 2 `$0` 番目の式の **結果**</span><span class="sxs-lookup"><span data-stu-id="4af9e-261">The result of the second `$0` expression in the **Console**</span></span>  
        :::image-end:::  
        
### <span data-ttu-id="4af9e-262">グローバル変数として格納する</span><span class="sxs-lookup"><span data-stu-id="4af9e-262">Store as global variable</span></span>  

<span data-ttu-id="4af9e-263">ノードを何度も参照する必要がある場合は、グローバル変数として保存します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-263">If you need to refer back to a node many times, store it as a global variable.</span></span>  

1.  <span data-ttu-id="4af9e-264">[DOM を開く例](#open-dom-examples)</span><span class="sxs-lookup"><span data-stu-id="4af9e-264">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="4af9e-265">Under **Store as global variable,** right-choose the Big **Sleep** and choose **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="4af9e-265">Under **Store as global variable**, right-choose **The Big Sleep** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="4af9e-266">DOM ツリーを `<li>The Big Sleep</li>` 右クリックし、[グローバル変数として **保存] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-266">Right-click `<li>The Big Sleep</li>` in the DOM Tree and choose **Store as global variable**.</span></span>  <span data-ttu-id="4af9e-267">オプションが [表示されない場合は、「付録:](#appendix-missing-options) 不足しているオプション」に移動します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-267">Navigate to [Appendix: Missing options](#appendix-missing-options) if the option is not displayed.</span></span>  
    1.  <span data-ttu-id="4af9e-268">コンソール `temp1` に入力し、次に選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="4af9e-268">Type `temp1` in the Console and then select `Enter`.</span></span>  <span data-ttu-id="4af9e-269">式の結果は、変数がノードに評価されるのを示します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-269">The result of the expression shows that the variable evaluates to the node.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png" alt-text="temp1 式の結果" lightbox="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png":::
           <span data-ttu-id="4af9e-271">式の `temp1` 結果</span><span class="sxs-lookup"><span data-stu-id="4af9e-271">The result of the `temp1` expression</span></span>  
        :::image-end:::  
        
### <span data-ttu-id="4af9e-272">JS パスをコピーする</span><span class="sxs-lookup"><span data-stu-id="4af9e-272">Copy JS path</span></span>  

<span data-ttu-id="4af9e-273">自動化されたテストで参照する必要がある場合は、JavaScript パスをノードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="4af9e-273">Copy the JavaScript path to a node when you need to reference it in an automated test.</span></span>  

1.  <span data-ttu-id="4af9e-274">[DOM を開く例](#open-dom-examples)</span><span class="sxs-lookup"><span data-stu-id="4af9e-274">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="4af9e-275">[JS **パスのコピー] の**下で **、[The 多くのMazov]** を右クリックし、[検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-275">Under **Copy JS path**, right-choose **The Brothers Karamazov** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="4af9e-276">DOM ツリーを `<li>The Brothers Karamazov</li>` 右クリックし、[コピー \*\*\*\* JS パス]  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-276">Right-click `<li>The Brothers Karamazov</li>` in the DOM Tree and choose **Copy** > **Copy JS Path**.</span></span>  <span data-ttu-id="4af9e-277">ノード `document.querySelector()` に解決される式がクリップボードにコピーされています。</span><span class="sxs-lookup"><span data-stu-id="4af9e-277">A `document.querySelector()` expression that resolves to the node has been copied to your clipboard.</span></span>  
    1.  <span data-ttu-id="4af9e-278">`Control` + `V` \(Windows,Linux\) または \(macOS\) を選択して、式をコンソール `Command` + `V` に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-278">Select `Control`+`V` \(Windows, Linux\) or `Command`+`V` \(macOS\) to paste the expression into the Console.</span></span>  
    1.  <span data-ttu-id="4af9e-279">式 `Enter` を評価するために選択します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-279">Select `Enter` to evaluate the expression.</span></span>
        
        :::image type="complex" source="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png" alt-text="JS パスのコピー式の結果" lightbox="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png":::
           <span data-ttu-id="4af9e-281">JS パスの **コピー式の** 結果</span><span class="sxs-lookup"><span data-stu-id="4af9e-281">The result of the **Copy JS Path** expression</span></span>  
        :::image-end:::  
        
## <span data-ttu-id="4af9e-282">DOM の変更時にブレーク</span><span class="sxs-lookup"><span data-stu-id="4af9e-282">Break on DOM changes</span></span>  

<span data-ttu-id="4af9e-283">DevTools を使用すると、JavaScript が DOM を変更するときにページの JavaScript を一時停止できます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-283">DevTools enables you to pause the JavaScript of a page when the JavaScript modifies the DOM.</span></span>  

### <span data-ttu-id="4af9e-284">属性の変更に対するブレーク</span><span class="sxs-lookup"><span data-stu-id="4af9e-284">Break on attribute modifications</span></span>  

<span data-ttu-id="4af9e-285">ノードの属性が変更される JavaScript を一時停止する場合は、属性変更ブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-285">Use attribute modification breakpoints when you want to pause the JavaScript that causes any attribute of a node to change.</span></span>  

1.  <span data-ttu-id="4af9e-286">[DOM を開く例](#open-dom-examples)</span><span class="sxs-lookup"><span data-stu-id="4af9e-286">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="4af9e-287">[Break **on attribute modifications] (属性の変更時**に Break) で、右クリックして **[Inspect]** を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-287">Under **Break on attribute modifications**, right-choose **Sauerkraut** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="4af9e-288">DOM ツリーで右クリックし、[属性の変更 `<li id="target">Sauerkraut</li>` **時にブレーク オン**  >  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-288">In the DOM Tree, right-click `<li id="target">Sauerkraut</li>` and choose **Break On** > **Attribute Modifications**.</span></span>  <span data-ttu-id="4af9e-289">オプションが [表示されない場合は、「付録:](#appendix-missing-options) 不足しているオプション」に移動します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-289">Navigate to [Appendix: Missing options](#appendix-missing-options) if the option is not displayed.</span></span>
        
        :::image type="complex" source="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png" alt-text="属性の変更に対するブレーク" lightbox="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png":::
           **<span data-ttu-id="4af9e-291">属性の変更を行う</span><span class="sxs-lookup"><span data-stu-id="4af9e-291">Break on attribute modifications</span></span>**  
        :::image-end:::  
        
    1.  <span data-ttu-id="4af9e-292">次の手順では、ページのコードを一時停止するボタンをクリックするように指示されます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-292">In the next step you are going to be instructed to click a button that pauses the code of the page.</span></span>  <span data-ttu-id="4af9e-293">ページを一時停止すると、ページをスクロールできなくなりました。</span><span class="sxs-lookup"><span data-stu-id="4af9e-293">After the page is paused you are no longer able to scroll the page.</span></span>  <span data-ttu-id="4af9e-294">ページを再 **びスクロール可能に** するには、Resume Script \( Resume Script \) を選択 ![ ][ImageResumeScriptIcon] する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4af9e-294">You must choose **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\) in order to make the page scrollable again.</span></span>
        
        :::image type="complex" source="../media/dom-break-attribute-modifications-sources-paused-on.msft.png" alt-text="スクリプトの実行を再開する場所" lightbox="../media/dom-break-attribute-modifications-sources-paused-on.msft.png":::
           <span data-ttu-id="4af9e-296">スクリプトの実行を再開する場所</span><span class="sxs-lookup"><span data-stu-id="4af9e-296">Where to resume script running</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="4af9e-297">上の [ **背景の設定]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4af9e-297">Click the **Set Background** button above.</span></span>  <span data-ttu-id="4af9e-298">これにより、ノード `style` の属性が設定されます `background-color:thistle` 。</span><span class="sxs-lookup"><span data-stu-id="4af9e-298">This sets the `style` attribute of the node to `background-color:thistle`.</span></span>  <span data-ttu-id="4af9e-299">DevTools はページを一時停止し、属性の変更を引き起こしたコードを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-299">DevTools pauses the page and highlights the code that caused the attribute to change.</span></span>  
    1.  <span data-ttu-id="4af9e-300">前述 **のように、[Resume Script** \( ![ Resume Script ][ImageResumeScriptIcon] \] (スクリプトの再開 \ ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-300">Choose **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\), as mentioned earlier.</span></span>  
    
### <span data-ttu-id="4af9e-301">ノードの削除時にブレーク</span><span class="sxs-lookup"><span data-stu-id="4af9e-301">Break on node removal</span></span>  

<span data-ttu-id="4af9e-302">特定のノードが削除された場合に一時停止する場合は、ノード削除のブレークポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-302">If you want to pause when a particular node is removed, use node removal breakpoints.</span></span>  

1.  <span data-ttu-id="4af9e-303">[DOM を開く例](#open-dom-examples)</span><span class="sxs-lookup"><span data-stu-id="4af9e-303">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="4af9e-304">[ **ノードの削除時にブレーク] で、[** ニューロマン **サー** ] を右クリックし、[検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-304">Under **Break on Node Removal**, right-choose **Neuromancer** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="4af9e-305">DOM ツリーで右クリックし、[ノード削除時に `<li id="target">Neuromancer</li>` **ブレーク]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-305">In the DOM Tree, right-click `<li id="target">Neuromancer</li>` and choose **Break On** > **Node Removal**.</span></span>  <span data-ttu-id="4af9e-306">オプションが [表示されない場合は、「付録:](#appendix-missing-options) 不足しているオプション」に移動します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-306">Navigate to [Appendix: Missing options](#appendix-missing-options) if the option is not displayed.</span></span>  
    1.  <span data-ttu-id="4af9e-307">上の [ **削除]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4af9e-307">Click the **Delete** button above.</span></span>  <span data-ttu-id="4af9e-308">DevTools はページを一時停止し、ノードを削除したコードを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-308">DevTools pauses the page and highlights the code that caused the node to be removed.</span></span>  
    1.  <span data-ttu-id="4af9e-309">[ \**スクリプトの再開\** ( ![ スクリプトの履歴書 \ ) を ][ImageResumeScriptIcon] 選択します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-309">Choose **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\).</span></span>  
    
### <span data-ttu-id="4af9e-310">サブツリーの変更時にブレークする</span><span class="sxs-lookup"><span data-stu-id="4af9e-310">Break on subtree modifications</span></span>  

<span data-ttu-id="4af9e-311">ノードにサブツリー変更ブレークポイントを設定すると、ノードの子孫が追加または削除されると、DevTools はページを一時停止します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-311">After you put a subtree modification breakpoint on a node, DevTools pauses the page when any of the descendants of the node are added or removed.</span></span>  

1.  <span data-ttu-id="4af9e-312">[DOM を開く例](#open-dom-examples)</span><span class="sxs-lookup"><span data-stu-id="4af9e-312">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="4af9e-313">Under **Break on Subtree Modifications,** right-choose **A Fire On the Deep** and choose **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="4af9e-313">Under **Break on Subtree Modifications**, right-choose **A Fire Upon The Deep** and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="4af9e-314">DOM ツリーで、上のノードである右クリックし、[サブツリーの変更時にブレーク `<ul id="target">` `<li>A Fire Upon the Deep</li>` **]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-314">In the DOM Tree, right-click `<ul id="target">`, which is the node above `<li>A Fire Upon the Deep</li>`, and choose **Break On** > **Subtree Modifications**.</span></span>  <span data-ttu-id="4af9e-315">オプションが [表示されない場合は、「付録:](#appendix-missing-options) 不足しているオプション」に移動します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-315">Navigate to [Appendix: Missing options](#appendix-missing-options) if the option is not displayed.</span></span>  
    1.  <span data-ttu-id="4af9e-316">[子 **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4af9e-316">Choose **Add Child**.</span></span>  <span data-ttu-id="4af9e-317">ノードがリストに追加 `<li>` されたため、コードは一時停止します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-317">The code pauses because a `<li>` node was added to the list.</span></span>  
    1.  <span data-ttu-id="4af9e-318">[ \**スクリプトの再開\** ( ![ スクリプトの履歴書 \ ) を ][ImageResumeScriptIcon] 選択します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-318">Choose **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\).</span></span>  
    
## <span data-ttu-id="4af9e-319">次のステップ</span><span class="sxs-lookup"><span data-stu-id="4af9e-319">Next steps</span></span>  

<span data-ttu-id="4af9e-320">DevTools の DOM 関連機能のほとんどについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-320">That covers most of the DOM-related features in DevTools.</span></span>  <span data-ttu-id="4af9e-321">DOM ツリーでノードを右クリックし、このチュートリアルでは説明していない他のオプションを試して、残りのノードを検出できます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-321">You are able to discover the rest of them by right-clicking nodes in the DOM Tree and experimenting with the other options that were not covered in this tutorial.</span></span>  <span data-ttu-id="4af9e-322">要素パネル [のキーボード ショートカットに移動します][DevToolsShortcutsElements]。</span><span class="sxs-lookup"><span data-stu-id="4af9e-322">Navigate to [Elements panel keyboard shortcuts][DevToolsShortcutsElements].</span></span>  

<span data-ttu-id="4af9e-323">[Microsoft Edge DevTools ホームページを参照して、DevTools][MicrosoftEdgeDevTools]で実行できるその他の操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-323">Check out the [Microsoft Edge DevTools homepage][MicrosoftEdgeDevTools] to discover everything else you are able to do with DevTools.</span></span>  

<!--Navigate to [Community](../index#community) if you want to contact the DevTools team or get help from the DevTools community.  -->  

## <span data-ttu-id="4af9e-324">付録: HTML と DOM</span><span class="sxs-lookup"><span data-stu-id="4af9e-324">Appendix: HTML versus the DOM</span></span>  

<span data-ttu-id="4af9e-325">次のセクションでは、HTML と DOM の違いについて簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-325">The following section quickly explains the difference between HTML and the DOM.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="4af9e-326">Web ブラウザーを使用してページを要求すると、サーバーは次のコード スニペットのような HTML を返します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-326">When you use a web browser to request a page, the server returns HTML like the following code snippet</span></span>  

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
      <span data-ttu-id="4af9e-327">ブラウザーは HTML を解析し、次のリストのようなオブジェクトのツリーを作成します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-327">The browser parses the HTML and creates a tree of objects like the following list.</span></span>  
      
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

<span data-ttu-id="4af9e-328">ページのコンテンツを表すオブジェクトまたはノードのこのツリーを DOM と呼ぶ。</span><span class="sxs-lookup"><span data-stu-id="4af9e-328">This tree of objects, or nodes, representing the content of the page is called the DOM.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="4af9e-329">現時点では HTML と同じように見えますが、HTML の下部で参照されるスクリプトが次のコード スニペットを実行するとします。</span><span class="sxs-lookup"><span data-stu-id="4af9e-329">Right now it looks the same as the HTML, but suppose that the script referenced at the bottom of the HTML runs the following code snippet.</span></span>  
      
      ```javascript
      const h1 = document.querySelector('h1');
      h1.parentElement.removeChild(h1);
      const p = document.createElement('p');
      p.textContent = 'Wildcard!';
      document.body.appendChild(p);
      ```  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="4af9e-330">このコードはノードを削除 `h1` し、DOM に `p` 別のノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-330">That code removes the `h1` node and adds another `p` node to the DOM.</span></span>  <span data-ttu-id="4af9e-331">これで、DOM の完全な一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-331">The complete DOM now displays the following list.</span></span>  
      
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

<span data-ttu-id="4af9e-332">ページの HTML が DOM と異なっています。</span><span class="sxs-lookup"><span data-stu-id="4af9e-332">The HTML for the page is now different than the DOM.</span></span>  <span data-ttu-id="4af9e-333">つまり、HTML は初期ページ コンテンツを表し、DOM は現在のページ コンテンツを表します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-333">In other words, HTML represents initial page content, and the DOM represents current page content.</span></span>  <span data-ttu-id="4af9e-334">JavaScript がノードを追加、削除、または編集すると、DOM は HTML とは異なります。</span><span class="sxs-lookup"><span data-stu-id="4af9e-334">When JavaScript adds, removes, or edits nodes, the DOM becomes different than the HTML.</span></span>  

<span data-ttu-id="4af9e-335">詳細については [、「DOM の概要」][MDNIntroductionToDOM] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-335">Navigate to [Introduction to the DOM][MDNIntroductionToDOM] to learn more.</span></span>  

<!--
## Appendix: Scroll into view  

This is a continuation of the [Scroll into view](#scroll-into-view) section.  Follow the instructions below to complete the section.  

1.  The `<li>Magritte</li>` node should still be selected in your DOM Tree.  If not, go back to [Scroll into view](#scroll-into-view) and start over.  
1.  Right-click the `<li>Magritte</li>` node and choose **Scroll into view**.  Your viewport scrolls back up so that you may see the **Magritte** node.  Navigate to [Appendix: Missing options](#appendix-missing-options) if you are not able to see the **Scroll into view** option.
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="Scroll into view" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       Scroll into view  
    :::image-end:::  
    -->  

## <span data-ttu-id="4af9e-336">付録: 不足しているオプション</span><span class="sxs-lookup"><span data-stu-id="4af9e-336">Appendix: Missing options</span></span>  

<span data-ttu-id="4af9e-337">このチュートリアルの手順の多くは、DOM ツリー内のノードを右クリックし、ポップアップ表示されるコンテキスト メニューからオプションを選択するように指示します。</span><span class="sxs-lookup"><span data-stu-id="4af9e-337">Many of the instructions in this tutorial instruct you to right-click a node in the DOM Tree and then select an option from the context menu that pops up.</span></span>  <span data-ttu-id="4af9e-338">コンテキスト メニューの指定されたオプションが表示されない場合は、ノードのテキストから右クリックしてみてください。</span><span class="sxs-lookup"><span data-stu-id="4af9e-338">If the specified option in the context menu is not displayed, try right-clicking away from the node text.</span></span>  

:::image type="complex" source="../media/dom-elements-highlighted-right-click-right-side.msft.png" alt-text="すべてのオプションが表示されない場合の選択先" lightbox="../media/dom-elements-highlighted-right-click-right-side.msft.png":::
   <span data-ttu-id="4af9e-340">すべてのオプションが表示されない場合の選択先</span><span class="sxs-lookup"><span data-stu-id="4af9e-340">Where to choose if all of the options are not displayed</span></span>  
:::image-end:::  

## <span data-ttu-id="4af9e-341">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="4af9e-341">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageInspectIcon]: ../media/inspect-icon.msft.png  
[ImageResumeScriptIcon]: ../media/resume-script-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge \(Chromium\) Developer Tools |Microsoft Docs"  
[DevToolsCssGetStarted]: ../css/index.md "CSS の表示と変更を開始する |Microsoft Docs"  
[DevToolsShortcutsElements]: ../shortcuts/index.md#elements-panel-keyboard-shortcuts "要素パネルのキーボード ショートカット - Microsoft Edge DevTools キーボード ショートカット |Microsoft Docs"  

[GlitchDomExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/dom "Microsoft Edge (Chromium) DevTools DOM の例 |Glitch"

[MDNIntroductionToDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM の概要 |MDN"  

> [!NOTE]
> <span data-ttu-id="4af9e-347">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="4af9e-347">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="4af9e-348">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/dom/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="4af9e-348">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/dom/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="4af9e-350">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="4af9e-350">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
