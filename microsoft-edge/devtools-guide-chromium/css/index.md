---
description: Microsoft Edge DevTools を使用してページの CSS を表示および変更する方法について説明します。
title: CSS の表示と変更の概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: b3d19d34f329fec7a3903fb37e8be3558ba4d31d
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399093"
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

# <a name="get-started-with-viewing-and-changing-css"></a><span data-ttu-id="3b0e0-104">CSS の表示と変更の概要</span><span class="sxs-lookup"><span data-stu-id="3b0e0-104">Get started with viewing and changing CSS</span></span>  

<span data-ttu-id="3b0e0-105">Microsoft Edge DevTools を使用してページの CSS を表示および変更する基本を学習するには、次の対話型チュートリアルを実行します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-105">Complete these interactive tutorials to learn the basics of viewing and changing the CSS for a page using Microsoft Edge DevTools.</span></span>  

## <a name="open-css-examples"></a><span data-ttu-id="3b0e0-106">オープン CSS の例</span><span class="sxs-lookup"><span data-stu-id="3b0e0-106">Open CSS Examples</span></span>  

1.  <span data-ttu-id="3b0e0-107">`Control`\(Windows,Linux\) または `Command` \(macOS\) を保持し **、[CSS の例**] を選択して新しいウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-107">Hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and choose **CSS Examples** to open in a new window.</span></span>  
    
    [<span data-ttu-id="3b0e0-108">CSS の例</span><span class="sxs-lookup"><span data-stu-id="3b0e0-108">CSS Examples</span></span>][GlitchDevToolsCssExamples]  
    
    > [!NOTE]
    > <span data-ttu-id="3b0e0-109">DevTools ウィンドウをビューポート \(次の図\に表示)の右側にドッキングする場合は [、[DevTools][DevToolsCustomizePlacement] のカスタマイズと制御] を **選択します** `...` 。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-109">If you want to [dock your DevTools window][DevToolsCustomizePlacement] to the right of your viewport \(displayed in the following figure\), choose **Customize and control DevTools** `...`.</span></span>  <span data-ttu-id="3b0e0-110">**[DevTools のカスタマイズ**と制御] ドロップダウン メニューの [**ドック**側] セクションで、[右へドック]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-110">On the **Customize and control DevTools** drop-down menu, in the **Dock side** section, choose **Dock to right**.</span></span>  
    
## <a name="view-the-css-for-an-element"></a><span data-ttu-id="3b0e0-111">要素の CSS を表示する</span><span class="sxs-lookup"><span data-stu-id="3b0e0-111">View the CSS for an element</span></span>  

1.  <span data-ttu-id="3b0e0-112">[CSS の例を開きます](#open-css-examples)。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-112">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="3b0e0-113">テキストにカーソルを `Inspect Me!` 合わせると、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-113">Hover on the `Inspect Me!` text, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="3b0e0-114">DevTools の [ **要素** ] ツールの **[DOM ツリー** ] パネルで、要素 `Inspect Me!` が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-114">In DevTools, on the **Elements** tool, in the **DOM Tree** panel, the `Inspect Me!` element is highlighted.</span></span>  
        
        :::image type="complex" source="../media/css-elements-inspect-me.msft.png" alt-text="検査された要素が DOM ツリーで強調表示されている" lightbox="../media/css-elements-inspect-me.msft.png":::
           <span data-ttu-id="3b0e0-116">検査された要素が DOM ツリーで **強調表示されている**</span><span class="sxs-lookup"><span data-stu-id="3b0e0-116">The inspected element is highlighted in the **DOM Tree**</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="3b0e0-117">要素で `Inspect Me!` 、属性の値を見つけて `data-message` コピーします。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-117">In the `Inspect Me!` element, find the value of the `data-message` attribute and copy it.</span></span>  
1.  <span data-ttu-id="3b0e0-118">ページの [値:] テキスト `data-message`  ボックスに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-118">On the page, in the **Value of `data-message`:** textbox, enter the value.</span></span>  
1.  <span data-ttu-id="3b0e0-119">テキストにカーソルを `Inspect Me!` 合わせると、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-119">Hover on the `Inspect Me!` text, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="3b0e0-120">DevTools の [要素] **ツールで** 、[スタイル] パネル **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-120">In DevTools, on the **Elements** tool, select the **Styles** panel.</span></span>  
    1.  <span data-ttu-id="3b0e0-121">[スタイル **] パネル** で、 `Inspect Me!` 要素が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-121">In the **Styles** panel, the `Inspect Me!` element is highlighted.</span></span>  
    1.  <span data-ttu-id="3b0e0-122">要素で `Inspect Me!` 、クラス ルール `aloha` を検索します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-122">In the `Inspect Me!` element, find the `aloha` class rule.</span></span>  
        
        > [!NOTE]
        > <span data-ttu-id="3b0e0-123">このルールは、要素に適用されるので表示 `Inspect Me!` されます。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-123">This rule is displayed, because it is being applied to the `Inspect Me!` element.</span></span>  
        
    1.  <span data-ttu-id="3b0e0-124">クラスで `aloha` 、スタイルの値を見つけて `padding` コピーします。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-124">In the `aloha` class, find the value for the `padding` style and copy it.</span></span>  
        
        :::image type="complex" source="../media/css-elements-inspect-me-styles.msft.png" alt-text="CSS クラスが検査済み要素に適用される場合は、[スタイル] パネルで強調表示されます。" lightbox="../media/css-elements-inspect-me-styles.msft.png":::
           <span data-ttu-id="3b0e0-126">CSS クラスは、[スタイル] パネルに表示されるなど、選択 `aloha` した要素に **適用** されます。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-126">CSS classes is applied to the selected element, such as `aloha`, are displayed in the **Styles** panel</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="3b0e0-127">ページの [値:] テキスト `padding`  ボックスに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-127">On the page, in the **Value of `padding`:** textbox, enter the value.</span></span>  

## <a name="add-a-css-declaration-to-an-element"></a><span data-ttu-id="3b0e0-128">要素に CSS 宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="3b0e0-128">Add a CSS declaration to an element</span></span>  

<span data-ttu-id="3b0e0-129">CSS 宣言 **を** 要素に変更または追加する場合は、[スタイル] パネルを使用します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-129">Use the **Styles** panel when you want to change or add CSS declarations to an element.</span></span>  

> [!NOTE]
> <span data-ttu-id="3b0e0-130">この手順を [実行する前に、「要素の CSS を表示する](#view-the-css-for-an-element) 」チュートリアルを完了します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-130">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="3b0e0-131">[CSS の例を開きます](#open-css-examples)。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-131">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="3b0e0-132">テキストにカーソルを `Add A Background Color To Me!` 合わせると、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-132">Hover on the `Add A Background Color To Me!` text, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
1.  <span data-ttu-id="3b0e0-133">[スタイル `element.style` ] パネルの上部付近 **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-133">Choose `element.style` near the top of the **Styles** panel.</span></span>  
1.  <span data-ttu-id="3b0e0-134">`background-color` を入力して、`Enter` を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-134">Type `background-color` and select `Enter`.</span></span>  
1.  <span data-ttu-id="3b0e0-135">`honeydew` を入力して、`Enter` を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-135">Type `honeydew` and select `Enter`.</span></span>  <span data-ttu-id="3b0e0-136">DOM ツリー **では、** 要素に適用されるインライン スタイル宣言が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-136">In the **DOM Tree**, an inline style declaration applied to the element is displayed.</span></span>  
    
    :::image type="complex" source="../media/css-elements-add-background-color-to-me-styles-p.msft.png" alt-text="[スタイル] パネルを使用して要素に CSS 宣言を追加する" lightbox="../media/css-elements-add-background-color-to-me-styles-p.msft.png":::
       <span data-ttu-id="3b0e0-138">宣言 `background-color:honeydew` は、[スタイル] パネルのセクションを使用 `element.style` して要素に **適用** されます。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-138">The `background-color:honeydew` declaration is applied to the element using the `element.style` section of the **Styles** panel</span></span>  
    :::image-end:::  
    
## <a name="add-a-css-class-to-an-element"></a><span data-ttu-id="3b0e0-139">要素に CSS クラスを追加する</span><span class="sxs-lookup"><span data-stu-id="3b0e0-139">Add a CSS class to an element</span></span>  

<span data-ttu-id="3b0e0-140">CSS クラスが要素に適用または要素から削除された場合の要素の外観を表示するには、[スタイル] パネルに **移動** します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-140">To display how an element looks when a CSS class is applied to or removed from an element, navigate to the **Styles** panel.</span></span>  

> [!NOTE]
> <span data-ttu-id="3b0e0-141">この手順を [実行する前に、「要素の CSS を表示する](#view-the-css-for-an-element) 」チュートリアルを完了します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-141">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="3b0e0-142">[CSS の例を開きます](#open-css-examples)。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-142">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="3b0e0-143">テキストにカーソルを `Add A Class To Me!` 合わせると、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-143">Hover on the `Add A Class To Me!` text, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
1.  <span data-ttu-id="3b0e0-144">**[.cls] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-144">Choose **.cls**.</span></span>  <span data-ttu-id="3b0e0-145">DevTools は、選択した要素にクラスを追加できるテキスト ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-145">DevTools reveals a text box where you may add classes to the selected element.</span></span>  
1.  <span data-ttu-id="3b0e0-146">[ `color_me` 新しいクラスの **追加] テキスト ボックスに** 入力し、[] を選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-146">Type `color_me` in the **Add new class** text box and then select `Enter`.</span></span>  <span data-ttu-id="3b0e0-147">[新しいクラスの追加] **テキスト** ボックスの下にチェック ボックスが表示され、クラスのオンとオフを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-147">A checkbox appears below the **Add new class** text box, where you may toggle the class on and off.</span></span>  <span data-ttu-id="3b0e0-148">要素に `Add A Class To Me!` 他のクラスが適用されている場合は、ここから各クラスを切り替えすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-148">If the `Add A Class To Me!` element has any other classes applied to it, you are also able to toggle each from here.</span></span>  
    
    :::image type="complex" source="../media/css-elements-add-a-class-to-me-styles-cls.msft.png" alt-text="要素にcolor_meクラスを適用する" lightbox="../media/css-elements-add-a-class-to-me-styles-cls.msft.png":::
       <span data-ttu-id="3b0e0-150">クラス `color_me` は、[スタイル] パネルの **.cls** セクションを使用して要素に **適用** されます。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-150">The `color_me` class is applied to the element using the **.cls** section of the **Styles** panel</span></span>  
    :::image-end:::  
    
## <a name="add-a-pseudostate-to-a-class"></a><span data-ttu-id="3b0e0-151">クラスに擬似状態を追加する</span><span class="sxs-lookup"><span data-stu-id="3b0e0-151">Add a pseudostate to a class</span></span>  

<span data-ttu-id="3b0e0-152">CSS 擬似 **状態を** 要素に完全に適用するには、[スタイル] パネルを使用します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-152">Use the **Styles** panel to permanently apply a CSS pseudostate to an element.</span></span>  <span data-ttu-id="3b0e0-153">DevTools `:active` は `:focus` 、、、、 `:hover` および をサポートしています `:visited` 。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-153">DevTools supports `:active`, `:focus`, `:hover`, and `:visited`.</span></span>  

> [!NOTE]
> <span data-ttu-id="3b0e0-154">この手順を [実行する前に、「要素の CSS を表示する](#view-the-css-for-an-element) 」チュートリアルを完了します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-154">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="3b0e0-155">[CSS の例を開きます](#open-css-examples)。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-155">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="3b0e0-156">テキストにカーソルを `Hover Over Me!` 合わせる。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-156">Hover on the `Hover Over Me!` text.</span></span>  <span data-ttu-id="3b0e0-157">背景色が変更されます。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-157">The background color changes.</span></span>  
1.  <span data-ttu-id="3b0e0-158">テキストにカーソルを `Hover Over Me!` 合わせると、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-158">Hover on the `Hover Over Me!` text, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
1.  <span data-ttu-id="3b0e0-159">[スタイル]**パネルで、[:hov] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-159">In the **Styles** panel, choose **:hov**.</span></span>  
1.  <span data-ttu-id="3b0e0-160">**[:hover] チェック ボックスを**オンにします。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-160">Check the **:hover** checkbox.</span></span>  <span data-ttu-id="3b0e0-161">要素の上に実際にカーソルを置かなくても、背景色は以前と同様に変化します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-161">The background color changes like before, even though you are not actually hovering over the element.</span></span>  
    
    :::image type="complex" source="../media/css-elements-hover-over-me-styles-hov-hover.msft.png" alt-text="要素のホバー擬似状態を切り替える" lightbox="../media/css-elements-hover-over-me-styles-hov-hover.msft.png":::
       <span data-ttu-id="3b0e0-163">要素の `:hover` 擬似状態を切り替える</span><span class="sxs-lookup"><span data-stu-id="3b0e0-163">Toggle the `:hover` pseudostate on an element</span></span>  
    :::image-end:::  
    
## <a name="change-the-dimensions-of-an-element"></a><span data-ttu-id="3b0e0-164">要素の寸法を変更する</span><span class="sxs-lookup"><span data-stu-id="3b0e0-164">Change the dimensions of an element</span></span>  

<span data-ttu-id="3b0e0-165">要素の**幅、高**さ、余白、余白、または罫線の長さを変更するには、[スタイル] パネルの [ボックス モデル] 対話型図を使用します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-165">Use the **Box Model** interactive diagram in the **Styles** panel to change the width, height, padding, margin, or border length of an element.</span></span>  

> [!NOTE]
> <span data-ttu-id="3b0e0-166">この手順を [実行する前に、「要素の CSS を表示する](#view-the-css-for-an-element) 」チュートリアルを完了します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-166">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="3b0e0-167">[CSS の例を開きます](#open-css-examples)。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-167">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="3b0e0-168">テキストにカーソルを `Change My Margin!` 合わせると、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-168">Hover on the `Change My Margin!` text, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
1.  <span data-ttu-id="3b0e0-169">[スタイル **] パネルのボックス** モデル図 **で** 、パディングをポイント **します**。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-169">In the **Box Model** diagram in the **Styles** panel, hover on **padding**.</span></span>  <span data-ttu-id="3b0e0-170">要素のパディングがビューポートで強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-170">The padding of an element is highlighted in the viewport.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="3b0e0-171">DevTools ウィンドウのサイズによっては、[スタイル] パネルの下部までスクロールしてボックス モデルを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-171">Depending on the size of your DevTools window, you may need to scroll to the bottom of the **Styles** panel to display the **Box Model**.</span></span>  

1.  <span data-ttu-id="3b0e0-172">現在、要素に左余白がないという意味の値を持つ Box **Model**の左余白を `-` ダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-172">Double-click the left margin in the **Box Model**, which currently has a value of `-` meaning that the element does not have a left-margin.</span></span>  
1.  <span data-ttu-id="3b0e0-173">`100px` を入力して、`Enter` を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-173">Type `100px` and select `Enter`.</span></span>  <span data-ttu-id="3b0e0-174">Box **Model の** 既定値はピクセルですが、その他の値 (例: 、 、 `25%` など) も受け入れ可能です `10vw` 。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-174">The **Box Model** defaults to pixels, but it also accepts other values, such as `25%`, or `10vw`.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/css-elements-change-my-margin-styles-padding.msft.png" alt-text="要素のパディングにカーソルを合わせる" lightbox="../media/css-elements-change-my-margin-styles-padding.msft.png":::
             <span data-ttu-id="3b0e0-176">要素のパディングにカーソルを合わせる</span><span class="sxs-lookup"><span data-stu-id="3b0e0-176">Hover on the padding of the element</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/css-elements-change-my-margin-styles-margin-edit.msft.png" alt-text="要素の左余白を変更する" lightbox="../media/css-elements-change-my-margin-styles-margin-edit.msft.png":::
             <span data-ttu-id="3b0e0-178">要素の左余白を変更する</span><span class="sxs-lookup"><span data-stu-id="3b0e0-178">Change the left-margin of the element</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## <a name="debugging-media-queries"></a><span data-ttu-id="3b0e0-179">メディア クエリのデバッグ</span><span class="sxs-lookup"><span data-stu-id="3b0e0-179">Debugging Media Queries</span></span>  

<span data-ttu-id="3b0e0-180">[メディア クエリは][MDNUsingMediaGueries] 、Web 製品を各ユーザーの構成設定の変更に対応させる方法です。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-180">[Media Queries][MDNUsingMediaGueries] are a way to make your web product react to changes in the configuration settings for each user.</span></span>  <span data-ttu-id="3b0e0-181">最も重要な使用例は、ビューポートの寸法に応じて製品に異なる CSS レイアウトを提供する方法です。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-181">The most significant use case is to provide your product a different CSS layout depending on the dimensions of the viewport.</span></span>  <span data-ttu-id="3b0e0-182">個別のレイアウトを使用すると、モバイル デバイス用の 1 列レイアウトと、利用可能な画面管理が多い場合の複数列レイアウトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-182">Using separate layouts allows for a one-column layout for mobile devices and multi-column layouts when there is more screen estate available.</span></span>  

<span data-ttu-id="3b0e0-183">CSS で定義したメディア クエリをデバッグまたはテストする場合は、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-183">If you want to debug or test the Media Queries you defined in your CSS, use the following steps.</span></span>  

1.  <span data-ttu-id="3b0e0-184">開発者ツールを開き、左上**の**2 番目のトグル デバイス ツールバー アイコンを選択するか `Ctrl` + `Shift` + `M` 、macOS\で \( `Cmd` + `Shift` + `M` を選択します)。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-184">Open the developer tools and select the **Toggle device toolbar** icon second on the top-left, or select `Ctrl`+`Shift`+`M` \(`Cmd`+`Shift`+`M` on macOS\).</span></span>  
    
    :::image type="complex" source="../media/css-elements-media-queries-open-device-toolbar.msft.png" alt-text="デバイス ツールバーを開く" lightbox="../media/css-elements-media-queries-open-device-toolbar.msft.png":::
       <span data-ttu-id="3b0e0-186">デバイス ツールバーを開く</span><span class="sxs-lookup"><span data-stu-id="3b0e0-186">Open the device toolbar</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3b0e0-187">デバイス ツール バーを開いた後、上部右側のメニューを選択し、[メディア `...` クエリの表示 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-187">With the device toolbar open, select the `...` menu on the top-right and choose **View Media Queries**.</span></span>  <span data-ttu-id="3b0e0-188">Web ページの上に表示される色付きバーは、さまざまなメディア クエリを表します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-188">The colored bars displayed above the webpage represent the different media queries.</span></span>  
    
    :::image type="complex" source="../media/css-elements-media-queries-showing-mq.msft.png" alt-text="デバイス ツールバーにメディア クエリを表示する" lightbox="../media/css-elements-media-queries-showing-mq.msft.png":::
       <span data-ttu-id="3b0e0-190">デバイス ツールバーにメディア クエリを表示する</span><span class="sxs-lookup"><span data-stu-id="3b0e0-190">Show Media Queries in Device Toolbar</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3b0e0-191">バーの境界にカーソルを合わせると、さまざまなメディア クエリの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-191">Hover on the boundaries in the bars to display the values of the different media queries.</span></span>  <span data-ttu-id="3b0e0-192">一致する Web ページのサイズを変更するには、それぞれを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-192">Choose each to resize the web page to match.</span></span>  
    
    :::image type="complex" source="../media/css-elements-media-queries-select-bar.msft.png" alt-text="プレビュー バーからメディア クエリを選択する" lightbox="../media/css-elements-media-queries-select-bar.msft.png":::
       <span data-ttu-id="3b0e0-194">プレビュー バーからメディア クエリを選択する</span><span class="sxs-lookup"><span data-stu-id="3b0e0-194">Choose Media Query from preview bar</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3b0e0-195">メディア クエリをデバッグし、エディターで CSS ファイルを開く場合は、いずれかのバー セグメントにカーソルを合わせ、コンテキスト メニュー \(右クリック\) を開き `Sources` 、を選択します `reveal in source code` 。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-195">To debug media queries and open the CSS file in the `Sources` editor; hover on any of the bar segments, open the contextual menu \(right-click\), and select `reveal in source code`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-media-queries-reveal-in-sources.msft.png" alt-text="ソース エディターでメディア クエリを表示する" lightbox="../media/css-elements-media-queries-reveal-in-sources.msft.png":::
       <span data-ttu-id="3b0e0-197">ソース エディターでメディア クエリを表示する</span><span class="sxs-lookup"><span data-stu-id="3b0e0-197">Reveal Media Queries in Sources Editor</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="3b0e0-198">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="3b0e0-198">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "Microsoft Edge DevTools の配置を変更する (Undock、Dock to Bottom、Dock to Left)"  

[GlitchDevToolsCssExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/css/examples/ecma.html "CSS の例 - Microsoft Edge (クロム) DevTools |Glitch"  

[MDNUsingMediaGueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries/Using_media_queries "メディア クエリの使用|MDN"  

> [!NOTE]
> <span data-ttu-id="3b0e0-202">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-202">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="3b0e0-203">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/css/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-203">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="3b0e0-205">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="3b0e0-205">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
