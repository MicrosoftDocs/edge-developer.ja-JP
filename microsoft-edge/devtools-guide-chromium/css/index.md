---
title: CSS の表示と変更を始める
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/27/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 85fceaa44b0143a82ca8f66ef8c63e1a9275dcd8
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601818"
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





# <span data-ttu-id="e9e77-103">CSS の表示と変更を始める</span><span class="sxs-lookup"><span data-stu-id="e9e77-103">Get Started With Viewing And Changing CSS</span></span>   



<span data-ttu-id="e9e77-104">Microsoft Edge DevTools を使用して、ページの CSS を表示して変更する基本的な方法については、次の対話型チュートリアルを実行してください。</span><span class="sxs-lookup"><span data-stu-id="e9e77-104">Complete these interactive tutorials to learn the basics of viewing and changing the CSS for a page using Microsoft Edge DevTools.</span></span>  

## <span data-ttu-id="e9e77-105">CSS の例を開く</span><span class="sxs-lookup"><span data-stu-id="e9e77-105">Open CSS Examples</span></span>  

1.  <span data-ttu-id="e9e77-106">`Control`\ (Windows \) または `Command` \ (macOS \) を保持し、[ **CSS の例**] をクリックして新しいウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-106">Hold `Control` \(Windows\) or `Command` \(macOS\) and click **CSS Examples** to open in a new window.</span></span>  
    
    [<span data-ttu-id="e9e77-107">CSS の例</span><span class="sxs-lookup"><span data-stu-id="e9e77-107">CSS Examples</span></span>][GlitchDevToolsCssExamples]  

> [!NOTE]
> <span data-ttu-id="e9e77-108">ツールビュー ([図 1](#figure-1)\) の右側に[devtools ウィンドウをドッキング][DevToolsCustomizePlacement]する場合は、[ **devtools のカスタマイズと制御**] をクリックし `...` ます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-108">If you want to [dock your DevTools window][DevToolsCustomizePlacement] to the right of your viewport \(displayed in [Figure 1](#figure-1)\), click **Customize and control DevTools** `...`.</span></span>  <span data-ttu-id="e9e77-109">[ **DevTools のカスタマイズと制御**] ドロップダウンメニューの [ **dock** ] セクションで、[ **dock to right**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-109">On the **Customize and control DevTools** drop-down menu, in the **Dock side** section, select **Dock to right**.</span></span>  
    
## <span data-ttu-id="e9e77-110">要素の CSS を表示する</span><span class="sxs-lookup"><span data-stu-id="e9e77-110">View the CSS for an element</span></span>   

1.  <span data-ttu-id="e9e77-111">[CSS の例を開き](#open-css-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-111">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="e9e77-112">テキストを右クリック `Inspect Me!` し、[**検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e9e77-112">Right-click the `Inspect Me!` text and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="e9e77-113">DevTools の [**要素**] パネルで、[ **DOM Tree** ] タブの `Inspect Me!` 要素が強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="e9e77-113">In DevTools, on the **Elements** panel, in the **DOM Tree** tab, the `Inspect Me!` element is highlighted.</span></span>  
        
        > ##### <span data-ttu-id="e9e77-114">図 1</span><span class="sxs-lookup"><span data-stu-id="e9e77-114">Figure 1</span></span>  
        > <span data-ttu-id="e9e77-115">**DOM ツリー**で、検査された要素が強調表示される</span><span class="sxs-lookup"><span data-stu-id="e9e77-115">The inspected element is highlighted in the **DOM Tree**</span></span>  
        > ![DOM ツリーで、検査された要素が強調表示される][ImageInspect]  
        
    1.  <span data-ttu-id="e9e77-117">要素で、 `Inspect Me!` 属性の値を見つけ `data-message` てコピーします。</span><span class="sxs-lookup"><span data-stu-id="e9e77-117">In the `Inspect Me!` element, find the value of the `data-message` attribute and copy it.</span></span>  
1.  <span data-ttu-id="e9e77-118">ページの [**値] `data-message` :** textbox で、値を入力します。</span><span class="sxs-lookup"><span data-stu-id="e9e77-118">On the page, in the **Value of `data-message`:** textbox, enter the value.</span></span>  
1.  <span data-ttu-id="e9e77-119">テキストを右クリック `Inspect Me!` し、[**検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e9e77-119">Right-click the `Inspect Me!` text and select **Inspect**.</span></span>  
    
    1.  <span data-ttu-id="e9e77-120">[DevTools] の [**要素**] パネルで、[**スタイル**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="e9e77-120">In DevTools, on the **Elements** panel, select the **Styles** tab.</span></span>  
    1.  <span data-ttu-id="e9e77-121">[**スタイル**] タブに、 `Inspect Me!` 要素が強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="e9e77-121">In the **Styles** tab, the `Inspect Me!` element is highlighted.</span></span>  
    1.  <span data-ttu-id="e9e77-122">要素で、 `Inspect Me!` クラスの規則を見つけ `aloha` ます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-122">In the `Inspect Me!` element, find the `aloha` class rule.</span></span>  
        
        > [!NOTE]
        > <span data-ttu-id="e9e77-123">この規則は、要素に適用されているために表示され `Inspect Me!` ます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-123">You see this rule because it is being applied to the `Inspect Me!` element.</span></span>  
        
    1.  <span data-ttu-id="e9e77-124">クラスで、 `aloha` スタイルの値を見つけ `padding` てコピーします。</span><span class="sxs-lookup"><span data-stu-id="e9e77-124">In the `aloha` class, find the value for the `padding` style and copy it.</span></span>  
        
        > ##### <span data-ttu-id="e9e77-125">図 2</span><span class="sxs-lookup"><span data-stu-id="e9e77-125">Figure 2</span></span>  
        > <span data-ttu-id="e9e77-126">選択した要素に適用される CSS クラス (など) `aloha` が [**スタイル**] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-126">CSS classes being applied to the selected element, such as `aloha`, are displayed in the **Styles** tab</span></span>  
        > ![[スタイル] タブの [検査] 要素に適用されている CSS クラスが強調表示されている][ImageAloha]  
        
1.  <span data-ttu-id="e9e77-128">ページの [**値] `padding` :** textbox で、値を入力します。</span><span class="sxs-lookup"><span data-stu-id="e9e77-128">On the page, in the **Value of `padding`:** textbox, enter the value.</span></span>  

## <span data-ttu-id="e9e77-129">要素に CSS 宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="e9e77-129">Add a CSS declaration to an element</span></span>   

<span data-ttu-id="e9e77-130">要素に CSS 宣言を変更したり追加したりするときは、[**スタイル**] タブを使います。</span><span class="sxs-lookup"><span data-stu-id="e9e77-130">Use the **Styles** tab when you want to change or add CSS declarations to an element.</span></span>  

> [!NOTE]
> <span data-ttu-id="e9e77-131">この操作を行う前に、[要素のチュートリアルの CSS の表示](#view-the-css-for-an-element)を完了します。</span><span class="sxs-lookup"><span data-stu-id="e9e77-131">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="e9e77-132">[CSS の例を開き](#open-css-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-132">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="e9e77-133">テキストを右クリック `Add A Background Color To Me!` し、[**検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e9e77-133">Right-click the `Add A Background Color To Me!` text and select **Inspect**.</span></span>  
1.  <span data-ttu-id="e9e77-134">[ `element.style` **スタイル**] タブの上部にあるをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9e77-134">Click `element.style` near the top of the **Styles** tab.</span></span>  
1.  <span data-ttu-id="e9e77-135">入力 `background-color` して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-135">Type `background-color` and press `Enter`.</span></span>  
1.  <span data-ttu-id="e9e77-136">入力 `honeydew` して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-136">Type `honeydew` and press `Enter`.</span></span>  <span data-ttu-id="e9e77-137">**DOM ツリー**で、インラインスタイル宣言が要素に適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e9e77-137">In the **DOM Tree** you should see that an inline style declaration was applied to the element.</span></span>  

> ##### <span data-ttu-id="e9e77-138">図 3</span><span class="sxs-lookup"><span data-stu-id="e9e77-138">Figure 3</span></span>  
> <span data-ttu-id="e9e77-139">`background-color:honeydew`宣言は `element.style` 、[**スタイル**] タブのセクションを使って要素に適用されています。</span><span class="sxs-lookup"><span data-stu-id="e9e77-139">The `background-color:honeydew` declaration has been applied to the element using the `element.style` section of the **Styles** tab</span></span>  
> ![[スタイル] タブを使用した要素への CSS 宣言の追加][ImageDeclaration]  

## <span data-ttu-id="e9e77-141">CSS クラスを要素に追加する</span><span class="sxs-lookup"><span data-stu-id="e9e77-141">Add a CSS class to an element</span></span>   

<span data-ttu-id="e9e77-142">[**スタイル**] タブを使って、要素に対して CSS クラスを適用または削除したときの要素の外観を確認します。</span><span class="sxs-lookup"><span data-stu-id="e9e77-142">Use the **Styles** tab to see how an element looks when a CSS class is applied to or removed from an element.</span></span>  

> [!NOTE]
> <span data-ttu-id="e9e77-143">この操作を行う前に、[要素のチュートリアルの CSS の表示](#view-the-css-for-an-element)を完了します。</span><span class="sxs-lookup"><span data-stu-id="e9e77-143">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="e9e77-144">[CSS の例を開き](#open-css-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-144">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="e9e77-145">要素を右クリック `Add A Class To Me!` し、[**検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e9e77-145">Right-click the `Add A Class To Me!` element and select **Inspect**.</span></span>  
1.  <span data-ttu-id="e9e77-146">[ **Cls**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9e77-146">Click **.cls**.</span></span>  <span data-ttu-id="e9e77-147">DevTools は、選択した要素にクラスを追加できるテキストボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="e9e77-147">DevTools reveals a text box where you may add classes to the selected element.</span></span>  
1.  <span data-ttu-id="e9e77-148">`color_me`[**新しいクラスの追加**] テキストボックスに入力して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-148">Type `color_me` in the **Add new class** text box and then press `Enter`.</span></span>  <span data-ttu-id="e9e77-149">[**新しいクラスの追加**] テキストボックスの下に、クラスのオンとオフを切り替えることができるチェックボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-149">A checkbox appears below the **Add new class** text box, where you may toggle the class on and off.</span></span>  <span data-ttu-id="e9e77-150">`Add A Class To Me!`要素に他のクラスが適用されている場合は、それぞれのクラスをここから切り替えることもできます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-150">If the `Add A Class To Me!` element has any other classes applied to it, you are also able to toggle each from here.</span></span>  

> ##### <span data-ttu-id="e9e77-151">図 4</span><span class="sxs-lookup"><span data-stu-id="e9e77-151">Figure 4</span></span>  
> <span data-ttu-id="e9e77-152">この `color_me` クラスは、[**スタイル**] タブの [cls] セクションを使って要素に適用されてい**ます。**</span><span class="sxs-lookup"><span data-stu-id="e9e77-152">The `color_me` class has been applied to the element using the **.cls** section of the **Styles** tab</span></span>  
> ![要素への color_me クラスの適用][ImageApplyClass]  

## <span data-ttu-id="e9e77-154">疑似状態をクラスに追加する</span><span class="sxs-lookup"><span data-stu-id="e9e77-154">Add a pseudostate to a class</span></span>   

<span data-ttu-id="e9e77-155">[**スタイル**] タブを使って、CSS の疑似条件を要素に永続的に適用します。</span><span class="sxs-lookup"><span data-stu-id="e9e77-155">Use the **Styles** tab to permanently apply a CSS pseudostate to an element.</span></span>  <span data-ttu-id="e9e77-156">Devtools では、、、、という機能がサポートさ `:active` `:focus` `:hover` れてい `:visited` ます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-156">DevTools supports `:active`, `:focus`, `:hover`, and `:visited`.</span></span>  

> [!NOTE]
> <span data-ttu-id="e9e77-157">この操作を行う前に、[要素のチュートリアルの CSS の表示](#view-the-css-for-an-element)を完了します。</span><span class="sxs-lookup"><span data-stu-id="e9e77-157">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="e9e77-158">[CSS の例を開き](#open-css-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-158">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="e9e77-159">テキストの上にマウスポインターを置き `Hover Over Me!` ます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-159">Hover over the `Hover Over Me!` text.</span></span>  <span data-ttu-id="e9e77-160">背景色が変更されます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-160">The background color changes.</span></span>  
1.  <span data-ttu-id="e9e77-161">テキストを右クリック `Hover Over Me!` し、[**検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e9e77-161">Right-click the `Hover Over Me!` text and select **Inspect**.</span></span>  
1.  <span data-ttu-id="e9e77-162">[**スタイル**] タブで、 **: hov**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9e77-162">In the **Styles** tab, click **:hov**.</span></span>  
1.  <span data-ttu-id="e9e77-163">[ **: Hover** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e9e77-163">Check the **:hover** checkbox.</span></span>  <span data-ttu-id="e9e77-164">実際には、要素の上にマウスポインターを置いていない場合でも背景色は変わります。</span><span class="sxs-lookup"><span data-stu-id="e9e77-164">The background color changes like before, even though you are not actually hovering over the element.</span></span>  

> ##### <span data-ttu-id="e9e77-165">図 5</span><span class="sxs-lookup"><span data-stu-id="e9e77-165">Figure 5</span></span>  
> <span data-ttu-id="e9e77-166">`:hover`要素の擬似状態の切り替え</span><span class="sxs-lookup"><span data-stu-id="e9e77-166">Toggling the `:hover` pseudostate on an element</span></span>  
> ![要素の hover 擬似状態の切り替え][ImageSetHover]  

## <span data-ttu-id="e9e77-168">要素のサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="e9e77-168">Change the dimensions of an element</span></span>   

<span data-ttu-id="e9e77-169">[**スタイル**] タブの**Box モデル**対話型ダイアグラムを使用して、要素の幅、高さ、パディング、余白、または境界線の長さを変更します。</span><span class="sxs-lookup"><span data-stu-id="e9e77-169">Use the **Box Model** interactive diagram in the **Styles** tab to change the width, height, padding, margin, or border length of an element.</span></span>  

> [!NOTE]
> <span data-ttu-id="e9e77-170">この操作を行う前に、[要素のチュートリアルの CSS の表示](#view-the-css-for-an-element)を完了します。</span><span class="sxs-lookup"><span data-stu-id="e9e77-170">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="e9e77-171">[CSS の例を開き](#open-css-examples)ます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-171">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="e9e77-172">要素を右クリック `Change My Margin!` し、[**検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e9e77-172">Right-click the `Change My Margin!` element and select **Inspect**.</span></span>  
1.  <span data-ttu-id="e9e77-173">**ボックスモデル**図の [**スタイル**] タブで、**パディング**の上にマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-173">In the **Box Model** diagram in the **Styles** tab, hover over **padding**.</span></span>  <span data-ttu-id="e9e77-174">ビューポートで要素のパディングが強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="e9e77-174">The padding of an element is highlighted in the viewport.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="e9e77-175">DevTools ウィンドウのサイズによっては、[**スタイル**] タブの下部にスクロールして、**ボックスモデル**を表示しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e9e77-175">Depending on the size of your DevTools window, you may need to scroll to the bottom of the **Styles** tab to see the **Box Model**.</span></span>  

1.  <span data-ttu-id="e9e77-176">**ボックスモデル**の左余白をダブルクリックします。現在のところ、 `-` 要素には左余白がない意味の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e9e77-176">Double-click the left margin in the **Box Model**, which currently has a value of `-` meaning that the element does not have a left-margin.</span></span>  
1.  <span data-ttu-id="e9e77-177">入力 `100px` して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-177">Type `100px` and press `Enter`.</span></span>  <span data-ttu-id="e9e77-178">**ボックスモデル**の既定値はピクセルですが、やなどの他の値も受け取り `25%` `10vw` ます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-178">The **Box Model** defaults to pixels, but it also accepts other values, such as `25%`, or `10vw`.</span></span>  

> ##### <span data-ttu-id="e9e77-179">図 6</span><span class="sxs-lookup"><span data-stu-id="e9e77-179">Figure 6</span></span>  
> <span data-ttu-id="e9e77-180">要素のパディングの上にマウスポインターを置いたところ</span><span class="sxs-lookup"><span data-stu-id="e9e77-180">Hovering over the padding of the element</span></span>  
> ![要素のパディングの上にマウスポインターを置いたところ][ImageShowPadding]  

> ##### <span data-ttu-id="e9e77-182">図 7</span><span class="sxs-lookup"><span data-stu-id="e9e77-182">Figure 7</span></span>  
> <span data-ttu-id="e9e77-183">要素の左余白を変更する</span><span class="sxs-lookup"><span data-stu-id="e9e77-183">Changing the left-margin of the element</span></span>  
> ![要素の左余白を変更する][ImageChangeMargin]  

 



<!-- image links -->  

[ImageInspect]: /microsoft-edge/devtools-guide-chromium/media/css-elements-inspect-me.msft.png "図 1: DOM ツリーで、検査された要素が強調表示されている"  
[ImageAloha]: /microsoft-edge/devtools-guide-chromium/media/css-elements-inspect-me-styles.msft.png "図 2: 検査対象要素に適用されている CSS クラスが、[スタイル] タブで強調表示される"  
[ImageDeclaration]: /microsoft-edge/devtools-guide-chromium/media/css-elements-add-background-color-to-me-styles-p.msft.png "図 3: [スタイル] タブを使用して要素に CSS 宣言を追加する"  
[ImageApplyClass]: /microsoft-edge/devtools-guide-chromium/media/css-elements-add-a-class-to-me-styles-cls.msft.png "図 4: 要素への color_me クラスの適用"  
[ImageSetHover]: /microsoft-edge/devtools-guide-chromium/media/css-elements-hover-over-me-styles-hov-hover.msft.png "図 5: 要素の hover 擬似開始の切り替え"  
[ImageShowPadding]: /microsoft-edge/devtools-guide-chromium/media/css-elements-change-my-margin-styles-padding.msft.png "図 6: 要素のパディングの上にマウスポインターを置いたところ"  
[ImageChangeMargin]: /microsoft-edge/devtools-guide-chromium/media/css-elements-change-my-margin-styles-margin-edit.msft.png "図 7: 要素の左余白を変更する"  

<!-- links -->  

[DevToolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "Microsoft Edge DevTools の配置を変更する (ドッキング解除、下へのドッキング、左へのドッキング)"  

[GlitchDevToolsCssExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/css/examples/ecma.html "CSS の例-Microsoft Edge (Chromium) DevTools |故障"  

> [!NOTE]
> <span data-ttu-id="e9e77-194">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="e9e77-194">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="e9e77-195">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/css/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="e9e77-195">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="e9e77-197">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="e9e77-197">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
