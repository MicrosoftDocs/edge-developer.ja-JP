---
title: CSS の表示と変更の概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 1780e80259d3ed28f6735e11099ad5796c381a95
ms.sourcegitcommit: f010f43604bd4363af6827f79dbc071b9afcb667
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2020
ms.locfileid: "10708595"
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

# <span data-ttu-id="937ea-103">CSS の表示と変更の概要</span><span class="sxs-lookup"><span data-stu-id="937ea-103">Get Started With Viewing And Changing CSS</span></span>  

<span data-ttu-id="937ea-104">Microsoft Edge DevTools を使用して、ページの CSS を表示して変更する基本的な方法については、次の対話型チュートリアルを実行してください。</span><span class="sxs-lookup"><span data-stu-id="937ea-104">Complete these interactive tutorials to learn the basics of viewing and changing the CSS for a page using Microsoft Edge DevTools.</span></span>  

## <span data-ttu-id="937ea-105">CSS の例を開く</span><span class="sxs-lookup"><span data-stu-id="937ea-105">Open CSS Examples</span></span>  

1.  <span data-ttu-id="937ea-106">`Control`\ (Windows \) または `Command` \ (macOS \) を保持し、[ **CSS の例**] を選択して新しいウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="937ea-106">Hold `Control` \(Windows\) or `Command` \(macOS\) and select **CSS Examples** to open in a new window.</span></span>  
    
    [<span data-ttu-id="937ea-107">CSS の例</span><span class="sxs-lookup"><span data-stu-id="937ea-107">CSS Examples</span></span>][GlitchDevToolsCssExamples]  
    
    > [!NOTE]
    > <span data-ttu-id="937ea-108">[Devtools ウィンドウ][DevToolsCustomizePlacement]をビューポートの右側 (次の図のように表示) にドッキングする場合は、[ **Devtools のカスタマイズと制御**] を選び `...` ます。</span><span class="sxs-lookup"><span data-stu-id="937ea-108">If you want to [dock your DevTools window][DevToolsCustomizePlacement] to the right of your viewport \(displayed in following figure\), select **Customize and control DevTools** `...`.</span></span>  <span data-ttu-id="937ea-109">[ **DevTools のカスタマイズと制御**] ドロップダウンメニューの [ **dock** ] セクションで、[ **dock to right**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="937ea-109">On the **Customize and control DevTools** drop-down menu, in the **Dock side** section, select **Dock to right**.</span></span>  
    
## <span data-ttu-id="937ea-110">要素の CSS を表示する</span><span class="sxs-lookup"><span data-stu-id="937ea-110">View the CSS for an element</span></span>  

1.  <span data-ttu-id="937ea-111">[CSS の例を開き](#open-css-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="937ea-111">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="937ea-112">テキストをポイントし `Inspect Me!` 、コンテキストメニューを開き (\ を右クリック) して、[**検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="937ea-112">Hover on the `Inspect Me!` text, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="937ea-113">DevTools の [**要素**] パネルで、[ **DOM Tree** ] タブの `Inspect Me!` 要素が強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="937ea-113">In DevTools, on the **Elements** panel, in the **DOM Tree** tab, the `Inspect Me!` element is highlighted.</span></span>  
        
        :::image type="complex" source="../media/css-elements-inspect-me.msft.png" alt-text="DOM ツリーで、検査された要素が強調表示される" lightbox="../media/css-elements-inspect-me.msft.png":::
           <span data-ttu-id="937ea-115">図 1: **DOM ツリー**で、検査された要素が強調表示されている</span><span class="sxs-lookup"><span data-stu-id="937ea-115">Figure 1:  The inspected element is highlighted in the **DOM Tree**</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="937ea-116">要素で、 `Inspect Me!` 属性の値を見つけ `data-message` てコピーします。</span><span class="sxs-lookup"><span data-stu-id="937ea-116">In the `Inspect Me!` element, find the value of the `data-message` attribute and copy it.</span></span>  
1.  <span data-ttu-id="937ea-117">ページの [**値] `data-message` :** textbox で、値を入力します。</span><span class="sxs-lookup"><span data-stu-id="937ea-117">On the page, in the **Value of `data-message`:** textbox, enter the value.</span></span>  
1.  <span data-ttu-id="937ea-118">テキストをポイントし `Inspect Me!` 、コンテキストメニューを開き (\ を右クリック) して、[**検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="937ea-118">Hover on the `Inspect Me!` text, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="937ea-119">[DevTools] の [**要素**] パネルで、[**スタイル**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="937ea-119">In DevTools, on the **Elements** panel, select the **Styles** tab.</span></span>  
    1.  <span data-ttu-id="937ea-120">[**スタイル**] タブに、 `Inspect Me!` 要素が強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="937ea-120">In the **Styles** tab, the `Inspect Me!` element is highlighted.</span></span>  
    1.  <span data-ttu-id="937ea-121">要素で、 `Inspect Me!` クラスの規則を見つけ `aloha` ます。</span><span class="sxs-lookup"><span data-stu-id="937ea-121">In the `Inspect Me!` element, find the `aloha` class rule.</span></span>  
        
        > [!NOTE]
        > <span data-ttu-id="937ea-122">この規則は、要素に適用されているために表示され `Inspect Me!` ます。</span><span class="sxs-lookup"><span data-stu-id="937ea-122">You see this rule because it is being applied to the `Inspect Me!` element.</span></span>  
        
    1.  <span data-ttu-id="937ea-123">クラスで、 `aloha` スタイルの値を見つけ `padding` てコピーします。</span><span class="sxs-lookup"><span data-stu-id="937ea-123">In the `aloha` class, find the value for the `padding` style and copy it.</span></span>  
        
        :::image type="complex" source="../media/css-elements-inspect-me-styles.msft.png" alt-text="[スタイル] タブの [検査] 要素に適用されている CSS クラスが強調表示されている" lightbox="../media/css-elements-inspect-me-styles.msft.png":::
           <span data-ttu-id="937ea-125">図 2: 選択した要素に適用される CSS クラス ( `aloha` [**スタイル**] タブに表示される)</span><span class="sxs-lookup"><span data-stu-id="937ea-125">Figure 2:  CSS classes being applied to the selected element, such as `aloha`, are displayed in the **Styles** tab</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="937ea-126">ページの [**値] `padding` :** textbox で、値を入力します。</span><span class="sxs-lookup"><span data-stu-id="937ea-126">On the page, in the **Value of `padding`:** textbox, enter the value.</span></span>  

## <span data-ttu-id="937ea-127">要素に CSS 宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="937ea-127">Add a CSS declaration to an element</span></span>  

<span data-ttu-id="937ea-128">要素に CSS 宣言を変更したり追加したりするときは、[**スタイル**] タブを使います。</span><span class="sxs-lookup"><span data-stu-id="937ea-128">Use the **Styles** tab when you want to change or add CSS declarations to an element.</span></span>  

> [!NOTE]
> <span data-ttu-id="937ea-129">この操作を行う前に、[要素のチュートリアルの CSS の表示](#view-the-css-for-an-element)を完了します。</span><span class="sxs-lookup"><span data-stu-id="937ea-129">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="937ea-130">[CSS の例を開き](#open-css-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="937ea-130">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="937ea-131">テキストをポイントし `Add A Background Color To Me!` 、コンテキストメニューを開き (\ を右クリック) して、[**検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="937ea-131">Hover on the `Add A Background Color To Me!` text, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
1.  <span data-ttu-id="937ea-132">[ `element.style` **スタイル**] タブの上部付近を選択します。</span><span class="sxs-lookup"><span data-stu-id="937ea-132">Select `element.style` near the top of the **Styles** tab.</span></span>  
1.  <span data-ttu-id="937ea-133">入力 `background-color` して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="937ea-133">Type `background-color` and press `Enter`.</span></span>  
1.  <span data-ttu-id="937ea-134">入力 `honeydew` して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="937ea-134">Type `honeydew` and press `Enter`.</span></span>  <span data-ttu-id="937ea-135">**DOM ツリー**で、インラインスタイル宣言が要素に適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="937ea-135">In the **DOM Tree** you should see that an inline style declaration was applied to the element.</span></span>  
    
    :::image type="complex" source="../media/css-elements-add-background-color-to-me-styles-p.msft.png" alt-text="[スタイル] タブを使用した要素への CSS 宣言の追加" lightbox="../media/css-elements-add-background-color-to-me-styles-p.msft.png":::
       <span data-ttu-id="937ea-137">図 3: `background-color:honeydew` 宣言は `element.style` 、[**スタイル**] タブのセクションを使って要素に適用されています。</span><span class="sxs-lookup"><span data-stu-id="937ea-137">Figure 3:  The `background-color:honeydew` declaration has been applied to the element using the `element.style` section of the **Styles** tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="937ea-138">CSS クラスを要素に追加する</span><span class="sxs-lookup"><span data-stu-id="937ea-138">Add a CSS class to an element</span></span>  

<span data-ttu-id="937ea-139">[**スタイル**] タブを使って、要素に対して CSS クラスを適用または削除したときの要素の外観を確認します。</span><span class="sxs-lookup"><span data-stu-id="937ea-139">Use the **Styles** tab to see how an element looks when a CSS class is applied to or removed from an element.</span></span>  

> [!NOTE]
> <span data-ttu-id="937ea-140">この操作を行う前に、[要素のチュートリアルの CSS の表示](#view-the-css-for-an-element)を完了します。</span><span class="sxs-lookup"><span data-stu-id="937ea-140">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="937ea-141">[CSS の例を開き](#open-css-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="937ea-141">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="937ea-142">テキストをポイントし `Add A Class To Me!` 、コンテキストメニューを開き (\ を右クリック) して、[**検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="937ea-142">Hover on the `Add A Class To Me!` text, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
1.  <span data-ttu-id="937ea-143">**Cls**を選びます。</span><span class="sxs-lookup"><span data-stu-id="937ea-143">Select **.cls**.</span></span>  <span data-ttu-id="937ea-144">DevTools は、選択した要素にクラスを追加できるテキストボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="937ea-144">DevTools reveals a text box where you may add classes to the selected element.</span></span>  
1.  <span data-ttu-id="937ea-145">`color_me`[**新しいクラスの追加**] テキストボックスに入力して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="937ea-145">Type `color_me` in the **Add new class** text box and then press `Enter`.</span></span>  <span data-ttu-id="937ea-146">[**新しいクラスの追加**] テキストボックスの下に、クラスのオンとオフを切り替えることができるチェックボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="937ea-146">A checkbox appears below the **Add new class** text box, where you may toggle the class on and off.</span></span>  <span data-ttu-id="937ea-147">`Add A Class To Me!`要素に他のクラスが適用されている場合は、それぞれのクラスをここから切り替えることもできます。</span><span class="sxs-lookup"><span data-stu-id="937ea-147">If the `Add A Class To Me!` element has any other classes applied to it, you are also able to toggle each from here.</span></span>  
    
    :::image type="complex" source="../media/css-elements-add-a-class-to-me-styles-cls.msft.png" alt-text="要素への color_me クラスの適用" lightbox="../media/css-elements-add-a-class-to-me-styles-cls.msft.png":::
       <span data-ttu-id="937ea-149">図 4: `color_me` [**スタイル**] タブの [ **cls** ] セクションを使用して、クラスが要素に適用されている</span><span class="sxs-lookup"><span data-stu-id="937ea-149">Figure 4:  The `color_me` class has been applied to the element using the **.cls** section of the **Styles** tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="937ea-150">疑似状態をクラスに追加する</span><span class="sxs-lookup"><span data-stu-id="937ea-150">Add a pseudostate to a class</span></span>  

<span data-ttu-id="937ea-151">[**スタイル**] タブを使って、CSS の疑似条件を要素に永続的に適用します。</span><span class="sxs-lookup"><span data-stu-id="937ea-151">Use the **Styles** tab to permanently apply a CSS pseudostate to an element.</span></span>  <span data-ttu-id="937ea-152">Devtools では、、、、という機能がサポートさ `:active` `:focus` `:hover` れてい `:visited` ます。</span><span class="sxs-lookup"><span data-stu-id="937ea-152">DevTools supports `:active`, `:focus`, `:hover`, and `:visited`.</span></span>  

> [!NOTE]
> <span data-ttu-id="937ea-153">この操作を行う前に、[要素のチュートリアルの CSS の表示](#view-the-css-for-an-element)を完了します。</span><span class="sxs-lookup"><span data-stu-id="937ea-153">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="937ea-154">[CSS の例を開き](#open-css-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="937ea-154">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="937ea-155">テキストの上にマウスポインターを置き `Hover Over Me!` ます。</span><span class="sxs-lookup"><span data-stu-id="937ea-155">Hover over the `Hover Over Me!` text.</span></span>  <span data-ttu-id="937ea-156">背景色が変更されます。</span><span class="sxs-lookup"><span data-stu-id="937ea-156">The background color changes.</span></span>  
1.  <span data-ttu-id="937ea-157">テキストをポイントし `Hover Over Me!` 、コンテキストメニューを開き (\ を右クリック) して、[**検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="937ea-157">Hover on the `Hover Over Me!` text, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
1.  <span data-ttu-id="937ea-158">[**スタイル**] タブで、 **: hov**を選びます。</span><span class="sxs-lookup"><span data-stu-id="937ea-158">In the **Styles** tab, select **:hov**.</span></span>  
1.  <span data-ttu-id="937ea-159">[ **: Hover** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="937ea-159">Check the **:hover** checkbox.</span></span>  <span data-ttu-id="937ea-160">実際には、要素の上にマウスポインターを置いていない場合でも背景色は変わります。</span><span class="sxs-lookup"><span data-stu-id="937ea-160">The background color changes like before, even though you are not actually hovering over the element.</span></span>  
    
    :::image type="complex" source="../media/css-elements-hover-over-me-styles-hov-hover.msft.png" alt-text="要素の hover 擬似状態の切り替え" lightbox="../media/css-elements-hover-over-me-styles-hov-hover.msft.png":::
       <span data-ttu-id="937ea-162">図 5: `:hover` 要素の擬似状態の切り替え</span><span class="sxs-lookup"><span data-stu-id="937ea-162">Figure 5:  Toggling the `:hover` pseudostate on an element</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="937ea-163">要素のサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="937ea-163">Change the dimensions of an element</span></span>  

<span data-ttu-id="937ea-164">[**スタイル**] タブの**Box モデル**対話型ダイアグラムを使用して、要素の幅、高さ、パディング、余白、または境界線の長さを変更します。</span><span class="sxs-lookup"><span data-stu-id="937ea-164">Use the **Box Model** interactive diagram in the **Styles** tab to change the width, height, padding, margin, or border length of an element.</span></span>  

> [!NOTE]
> <span data-ttu-id="937ea-165">この操作を行う前に、[要素のチュートリアルの CSS の表示](#view-the-css-for-an-element)を完了します。</span><span class="sxs-lookup"><span data-stu-id="937ea-165">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="937ea-166">[CSS の例を開き](#open-css-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="937ea-166">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="937ea-167">テキストをポイントし `Change My Margin!` 、コンテキストメニューを開き (\ を右クリック) して、[**検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="937ea-167">Hover on the `Change My Margin!` text, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
1.  <span data-ttu-id="937ea-168">**ボックスモデル**図の [**スタイル**] タブで、**パディング**の上にマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="937ea-168">In the **Box Model** diagram in the **Styles** tab, hover over **padding**.</span></span>  <span data-ttu-id="937ea-169">ビューポートで要素のパディングが強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="937ea-169">The padding of an element is highlighted in the viewport.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="937ea-170">DevTools ウィンドウのサイズによっては、[**スタイル**] タブの下部にスクロールして、**ボックスモデル**を表示しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="937ea-170">Depending on the size of your DevTools window, you may need to scroll to the bottom of the **Styles** tab to see the **Box Model**.</span></span>  

1.  <span data-ttu-id="937ea-171">**ボックスモデル**の左余白をダブルクリックします。現在のところ、 `-` 要素には左余白がない意味の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="937ea-171">Double-click the left margin in the **Box Model**, which currently has a value of `-` meaning that the element does not have a left-margin.</span></span>  
1.  <span data-ttu-id="937ea-172">入力 `100px` して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="937ea-172">Type `100px` and press `Enter`.</span></span>  <span data-ttu-id="937ea-173">**ボックスモデル**の既定値はピクセルですが、やなどの他の値も受け取り `25%` `10vw` ます。</span><span class="sxs-lookup"><span data-stu-id="937ea-173">The **Box Model** defaults to pixels, but it also accepts other values, such as `25%`, or `10vw`.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/css-elements-change-my-margin-styles-padding.msft.png" alt-text="要素のパディングの上にマウスポインターを置いたところ" lightbox="../media/css-elements-change-my-margin-styles-padding.msft.png":::
             <span data-ttu-id="937ea-175">図 6: 要素のパディングの上にマウスポインターを置いたところ</span><span class="sxs-lookup"><span data-stu-id="937ea-175">Figure 6:  Hovering over the padding of the element</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/css-elements-change-my-margin-styles-margin-edit.msft.png" alt-text="要素の左余白を変更する" lightbox="../media/css-elements-change-my-margin-styles-margin-edit.msft.png":::
             <span data-ttu-id="937ea-177">図 7: 要素の左余白を変更する</span><span class="sxs-lookup"><span data-stu-id="937ea-177">Figure 7:  Changing the left-margin of the element</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## <span data-ttu-id="937ea-178">メディアクエリのデバッグ</span><span class="sxs-lookup"><span data-stu-id="937ea-178">Debugging Media Queries</span></span>  

<span data-ttu-id="937ea-179">[メディアクエリ][MDNUsingMediaGueries]は、web 製品が各ユーザーの構成設定の変更に反応するようにするための手段です。</span><span class="sxs-lookup"><span data-stu-id="937ea-179">[Media Queries][MDNUsingMediaGueries] are a way to make your web product react to changes in the configuration settings for each user.</span></span>  <span data-ttu-id="937ea-180">最も重要なユースケースは、ビューポートのサイズに応じて、さまざまな CSS レイアウトで製品を提供することです。</span><span class="sxs-lookup"><span data-stu-id="937ea-180">The most significant use case is to provide your product a different CSS layout depending on the dimensions of the viewport.</span></span>  <span data-ttu-id="937ea-181">別のレイアウトを使用すると、モバイルデバイスと複数列のレイアウトのための1段のレイアウトが可能になります。利用可能な画面領域が増えます。</span><span class="sxs-lookup"><span data-stu-id="937ea-181">Using separate layouts allows for a one-column layout for mobile devices and multi-column layouts when there is more screen estate available.</span></span>  

<span data-ttu-id="937ea-182">CSS で定義したメディアクエリをデバッグまたはテストする場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="937ea-182">If you want to debug or test the Media Queries you defined in your CSS, use the following steps.</span></span>  

1.  <span data-ttu-id="937ea-183">開発者ツールを開き、左上の [**デバイスの切り替え] ツールバー**アイコンをクリックするか、 `Ctrl` + `Shift` + `M` \ ( `Cmd` + `Shift` + `M` macOS の場合) を押します。</span><span class="sxs-lookup"><span data-stu-id="937ea-183">Open the developer tools and select the **Toggle device toolbar** icon second on the top-left, or press `Ctrl`+`Shift`+`M` \(`Cmd`+`Shift`+`M` on macOS\).</span></span>  
    
    :::image type="complex" source="../media/css-elements-media-queries-open-device-toolbar.msft.png" alt-text="デバイスのツールバーを開く" lightbox="../media/css-elements-media-queries-open-device-toolbar.msft.png":::
       <span data-ttu-id="937ea-185">図 8: デバイスのツールバーを開く</span><span class="sxs-lookup"><span data-stu-id="937ea-185">Figure 8:  Opening the device toolbar</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="937ea-186">デバイスツールバーを開き、右上のメニューを選択して、 `...` [**メディアクエリの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="937ea-186">With the device toolbar open, select the `...` menu on the top-right and select **View Media Queries**.</span></span>  <span data-ttu-id="937ea-187">ページの表示の上に、さまざまなメディアクエリを示す色付きのバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="937ea-187">You should see colored bars above the display of the page that represent the different media queries.</span></span>  
    
    :::image type="complex" source="../media/css-elements-media-queries-showing-mq.msft.png" alt-text="デバイスツールバーでメディアクエリを表示する" lightbox="../media/css-elements-media-queries-showing-mq.msft.png":::
       <span data-ttu-id="937ea-189">図 9: デバイスのツールバーでメディアクエリを表示する</span><span class="sxs-lookup"><span data-stu-id="937ea-189">Figure 9:  Showing Media Queries in Device Toolbar</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="937ea-190">バーの境界線にマウスポインターを置くと、さまざまなメディアクエリの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="937ea-190">Hover over the boundaries in the bars to see the values of the different media queries.</span></span> <span data-ttu-id="937ea-191">一致させる web ページのサイズを変更するには、それぞれを選びます。</span><span class="sxs-lookup"><span data-stu-id="937ea-191">Select each to resize the web page to match.</span></span>  
    
    :::image type="complex" source="../media/css-elements-media-queries-select-bar.msft.png" alt-text="プレビューバーからメディアクエリを選ぶ" lightbox="../media/css-elements-media-queries-select-bar.msft.png":::
       <span data-ttu-id="937ea-193">図 10: プレビューバーからメディアクエリを選ぶ</span><span class="sxs-lookup"><span data-stu-id="937ea-193">Figure 10:  Selecting Media Query from preview bar</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="937ea-194">メディアクエリをデバッグして、エディターで CSS ファイルを開くには、 `Sources` いずれかのバーセグメントにマウスポインターを合わせて、コンテキストメニュー \ (右クリック \) を開いて、を選択し `reveal in source code` ます。</span><span class="sxs-lookup"><span data-stu-id="937ea-194">To debug media queries and open the CSS file in the `Sources` editor; hover on any of the bar segments, open the contextual menu \(right-click\), and select `reveal in source code`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-media-queries-reveal-in-sources.msft.png" alt-text="ソースエディターでメディアクエリを見つける" lightbox="../media/css-elements-media-queries-reveal-in-sources.msft.png":::
       <span data-ttu-id="937ea-196">図 11: ソースエディターでメディアクエリを見つける</span><span class="sxs-lookup"><span data-stu-id="937ea-196">Figure 11:  Revealing Media Queries in Sources Editor</span></span>  
    :::image-end:::  
    
<!-- links -->  

[DevToolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "Microsoft Edge DevTools の配置を変更する (ドッキング解除、下へのドッキング、左へのドッキング)"  

[GlitchDevToolsCssExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/css/examples/ecma.html "CSS の例-Microsoft Edge (Chromium) DevTools |故障"  

[MDNUsingMediaGueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries/Using_media_queries "メディアクエリを使用する |MDN"  

> [!NOTE]
> <span data-ttu-id="937ea-200">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="937ea-200">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="937ea-201">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/css/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="937ea-201">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="937ea-203">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="937ea-203">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
