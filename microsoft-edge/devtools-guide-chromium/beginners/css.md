---
title: '初心者向けの DevTools: CSS の使用を開始する'
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/14/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 6e005f4107764a13934f0c8f3b3cde0ab9bf98c2
ms.sourcegitcommit: 054ad92f0b8f9a15da1e3aed32e8f4379b10860f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2020
ms.locfileid: "10931730"
---
<!-- Copyright Katherine Jackson 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# <span data-ttu-id="ae0b7-103">初心者向けの DevTools: CSS の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="ae0b7-103">DevTools for beginners: Get started with CSS</span></span>  

<span data-ttu-id="ae0b7-104">このチュートリアルでは、CSS を使用して web ページのスタイルを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-104">In this tutorial, you learn how to use CSS to style a web page.</span></span>  <span data-ttu-id="ae0b7-105">また、Microsoft Edge DevTools を使用して CSS の変更を試す方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-105">You also learn how to use Microsoft Edge DevTools to experiment with CSS changes.</span></span>  

<span data-ttu-id="ae0b7-106">次の記事は、web 開発と Microsoft Edge DevTools の基礎について説明している一連のチュートリアルの2番目のチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-106">The following article is the second tutorial in a series of tutorials that teaches you the basics of web development and Microsoft Edge DevTools.</span></span>  <span data-ttu-id="ae0b7-107">実際に自分の web サイトを構築することで、実践的なエクスペリエンスを実現できます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-107">You gain hands-on experience by actually building your own website.</span></span>  <span data-ttu-id="ae0b7-108">2番目のチュートリアルに従う前に、最初のチュートリアルを完了する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-108">You do not have to complete the first tutorial before following the second.</span></span>  <span data-ttu-id="ae0b7-109">[コードを設定](#set-up-your-code) すると、セットアップ方法が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-109">[Set up your code](#set-up-your-code) shows you how to get set up.</span></span>  

> [!NOTE]
> <span data-ttu-id="ae0b7-110">このチュートリアルは、基本的な初心者向けに設計されており、 **web 開発の基礎** と、開発者向けの基本的なツールを使用した CSS の基本的な使い方に重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-110">This tutorial is designed for absolute beginners and focuses on both the **fundamentals of web development** and the basics of using DevTools to experiment with CSS.</span></span>  <span data-ttu-id="ae0b7-111">開発ツールにのみ重点を置いたチュートリアルが必要な場合は、「 [CSS の表示と変更の概要][DevtoolsCssIndex]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-111">If you want a tutorial that only focuses on DevTools, see [Get Started with Viewing and Changing CSS][DevtoolsCssIndex].</span></span>  

<span data-ttu-id="ae0b7-112">チュートリアルの最初に、サイトは次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-112">At the beginning of the tutorial, your site should look like the following figure.</span></span>  

:::image type="complex" source="../media/beginners-css-intro1.msft.png" alt-text="現在のサイトの外観" lightbox="../media/beginners-css-intro1.msft.png":::
   <span data-ttu-id="ae0b7-114">現在のサイトの外観</span><span class="sxs-lookup"><span data-stu-id="ae0b7-114">What your site currently looks like</span></span>  
:::image-end:::  

<span data-ttu-id="ae0b7-115">チュートリアルを完了したら、サイトは次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-115">After you complete the tutorial, you site should look like the following figure.</span></span>  

:::image type="complex" source="../media/beginners-css-intro2.msft.png" alt-text="チュートリアルの最後にサイトがどのように表示されるか" lightbox="../media/beginners-css-intro2.msft.png":::
   <span data-ttu-id="ae0b7-117">チュートリアルの最後にサイトがどのように表示されるか</span><span class="sxs-lookup"><span data-stu-id="ae0b7-117">What your site should look like at the end of the tutorial</span></span>  
:::image-end:::  

## <span data-ttu-id="ae0b7-118">目標</span><span class="sxs-lookup"><span data-stu-id="ae0b7-118">Goals</span></span>  

<span data-ttu-id="ae0b7-119">以下の概念とタスクについて詳しく理解するには、このチュートリアルに従ってください。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-119">Follow this tutorial to better understand the following concepts and tasks.</span></span>  

*   <span data-ttu-id="ae0b7-120">CSS を使用して web ページのスタイルを適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-120">How to use CSS to style a web page.</span></span>  
*   <span data-ttu-id="ae0b7-121">Microsoft Edge DevTools を使って CSS を試す方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-121">How to use Microsoft Edge DevTools to experiment with CSS.</span></span>  
*   <span data-ttu-id="ae0b7-122">CSS と CSS フレームワークの違い。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-122">The difference between CSS and CSS frameworks.</span></span>  

<span data-ttu-id="ae0b7-123">実際の web サイトを作成しています。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-123">You are building a real website.</span></span>  

## <span data-ttu-id="ae0b7-124">前提条件</span><span class="sxs-lookup"><span data-stu-id="ae0b7-124">Prerequisites</span></span>  

<span data-ttu-id="ae0b7-125">このチュートリアルを実行する前に、次の前提条件を完了してください。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-125">Before attempting this tutorial, complete the following prerequisites.</span></span>  

*   <span data-ttu-id="ae0b7-126">[[Html と dom の使用を開始][DevtoolsBeginnersHtml]する] または [dom] の概要については、このチュートリアルで説明するように、HTML と dom について理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-126">Complete [Get Started with HTML and the DOM][DevtoolsBeginnersHtml] or make sure that you have an understanding of HTML and the DOM similar to what is taught in that tutorial.</span></span>  
*   <span data-ttu-id="ae0b7-127">[Microsoft Edge][MicrosoftEdgeInsider] web ブラウザーをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-127">Download the [Microsoft Edge][MicrosoftEdgeInsider] web browser.</span></span>  <span data-ttu-id="ae0b7-128">次のチュートリアルでは、microsoft edge DevTools と呼ばれる web 開発ツールのセットを使用して、Microsoft Edge に組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-128">The following tutorial uses a set of web development tools, called the Microsoft Edge DevTools, that are built into Microsoft Edge.</span></span>  

## <span data-ttu-id="ae0b7-129">コードを設定する</span><span class="sxs-lookup"><span data-stu-id="ae0b7-129">Set up your code</span></span>  

<span data-ttu-id="ae0b7-130">サイトを作成するには、最初に次の操作を実行してコードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-130">To create your site, you must first complete the following actions to set up your code.</span></span>  

> [!NOTE]
> <span data-ttu-id="ae0b7-131">一連の最初のチュートリアルを既に完了している場合は、次のセクションに進んでください。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-131">If you have already completed the first tutorial in the series, skip to the next section.</span></span>  <span data-ttu-id="ae0b7-132">「 [HTML と DOM の使用を開始][DevtoolsBeginnersHtml]する」のチュートリアルで説明したコードの使用を続けます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-132">Continue using your code from the last tutorial, [Get Started with HTML and the DOM][DevtoolsBeginnersHtml].</span></span>  

1.  <span data-ttu-id="ae0b7-133">[ソースコード][GlitchCookedAmphibianIndex]を開きます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-133">Open the [source code][GlitchCookedAmphibianIndex].</span></span>  <span data-ttu-id="ae0b7-134">ブラウザーの [フォーカス] タブは [ **編集] タブ**として参照されます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-134">The in-focus tab of your browser is referenced as the **editing tab**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-setup1.msft.png" alt-text="[編集] タブ" lightbox="../media/beginners-css-setup1.msft.png":::
       <span data-ttu-id="ae0b7-136">[ **編集** ] タブ</span><span class="sxs-lookup"><span data-stu-id="ae0b7-136">The **editing** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-137">[ **クック-水陸両用機**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-137">Choose **cooked-amphibian**.</span></span>  <span data-ttu-id="ae0b7-138">メニューがポップアップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-138">A menu pops up.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-setup2.msft.png" alt-text="[プロジェクトのオプション] メニュー" lightbox="../media/beginners-css-setup2.msft.png":::
       <span data-ttu-id="ae0b7-140">[プロジェクトのオプション] メニュー</span><span class="sxs-lookup"><span data-stu-id="ae0b7-140">The Project Options menu</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="ae0b7-141">[ **Remix Project**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-141">Choose **Remix Project**.</span></span>  <span data-ttu-id="ae0b7-142">エラー編集可能なプロジェクトのコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-142">Glitch creates a copy of the project that you are able to edit.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="ae0b7-143">エラー新しいプロジェクトに対してランダムな名前を生成します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-143">Glitch generates a random name for the new project.</span></span>  
    
1.  <span data-ttu-id="ae0b7-144">[ **表示** ] を選択し、 **新しいウィンドウで**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-144">Choose **Show** and select **In a New Window**.</span></span>  <span data-ttu-id="ae0b7-145">サイトのライブビューで別のタブが開きます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-145">Another tab opens with a live view of your site.</span></span>  <span data-ttu-id="ae0b7-146">ブラウザーの [フォーカス] タブは、[ **ライブ] タブ**として参照されます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-146">The in-focus tab of your browser is referenced as the **live tab**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-setup3.msft.png" alt-text="[ライブ] タブ" lightbox="../media/beginners-css-setup3.msft.png":::
       <span data-ttu-id="ae0b7-148">[ **ライブ] タブ**</span><span class="sxs-lookup"><span data-stu-id="ae0b7-148">The **live tab**</span></span>  
    :::image-end:::  

## <span data-ttu-id="ae0b7-149">CSS について</span><span class="sxs-lookup"><span data-stu-id="ae0b7-149">Understand CSS</span></span>  

<span data-ttu-id="ae0b7-150">**CSS** は、web ページのレイアウトとスタイルを決定するコンピューターの言語です。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-150">**CSS** is a computer language that determines the layout and styling of web pages.</span></span>  <span data-ttu-id="ae0b7-151">次の図は、罫線が付いた段落を示しています。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-151">The following figure is a paragraph with a border.</span></span>  

:::image type="complex" source="../media/beginners-css-red_paragraph.msft.png" alt-text="テキストは CSS でスタイル設定されています" lightbox="../media/beginners-css-red_paragraph.msft.png":::
   <span data-ttu-id="ae0b7-153">テキストは CSS でスタイル設定されています</span><span class="sxs-lookup"><span data-stu-id="ae0b7-153">The text has been styled with CSS</span></span>  
:::image-end:::  

<span data-ttu-id="ae0b7-154">次のコードスニペットは、前の図で段落を作成するために使用される HTML と CSS のコードです。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-154">The following code snippet is the HTML and CSS code used to create the paragraph in the previous figure.</span></span>  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

`style="border: 1px dashed red; padding: 5px;"` <span data-ttu-id="ae0b7-155">おそらく、新しくなったようです。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-155">probably looks new to you.</span></span>  <span data-ttu-id="ae0b7-156">その他の方法については、こちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-156">The rest should look familiar.</span></span>  <span data-ttu-id="ae0b7-157">表示されない場合は、次のセクションの手順を実行する前に、「 [HTML と DOM で作業を開始][DevtoolsBeginnersHtml] する」を完了してください。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-157">If not, complete [Get Started with HTML and the DOM][DevtoolsBeginnersHtml] before attempting the following sections.</span></span>  

## <span data-ttu-id="ae0b7-158">インラインスタイルを追加する</span><span class="sxs-lookup"><span data-stu-id="ae0b7-158">Add inline styles</span></span>  

<span data-ttu-id="ae0b7-159">**インラインスタイル**を使って1つの要素にスタイルを適用するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-159">Complete the following actions to use **inline styles** to apply styles to a single element.</span></span>  

1.  <span data-ttu-id="ae0b7-160">[編集] タブに戻り、[開く] をクリックし `index.html` ます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-160">Go back to the editing tab and open `index.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-inline1.msft.png" alt-text="index.html" lightbox="../media/beginners-css-inline1.msft.png":::
       <span data-ttu-id="ae0b7-162">[ `index.html` 編集] タブで開く</span><span class="sxs-lookup"><span data-stu-id="ae0b7-162">Open `index.html` in the editing tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-163">`style="background-color: aliceblue;"`にを追加 `<nav>` します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-163">Add `style="background-color: aliceblue;"` to your `<nav>`.</span></span>  <span data-ttu-id="ae0b7-164">以下のコードブロックでは、コードの4行目が変更する必要があるものです。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-164">In the code block below, the fourth line of code is the one you need to change.</span></span>  <span data-ttu-id="ae0b7-165">残りの部分はそのままで、新しいコードを適切な場所に配置することができます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-165">The rest is just there, so you are able to ensure that you are putting the new code in the right place.</span></span>  
    
    ```html
    <header>
        <p>Welcome to my site!</p>
    </header>
    <nav style="background-color: aliceblue;">
        <ul>
            <li><a href="/">Home</a></li>
            ...
        ...
    ...
    ```  
    
1.  <span data-ttu-id="ae0b7-166">[ **ライブ] タブ** に移動して変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-166">Go to the **live tab** to see the changes!</span></span>  <span data-ttu-id="ae0b7-167">セクションの背景 `<nav>` が青色になります。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-167">The background of the `<nav>` section is now blue.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-inline2.msft.png" alt-text="ホームと連絡先のリンクの背景色が青になりました" lightbox="../media/beginners-css-inline2.msft.png":::
       <span data-ttu-id="ae0b7-169">**ホーム**と**連絡先**のリンクの背景色が青になりました</span><span class="sxs-lookup"><span data-stu-id="ae0b7-169">The background color behind the **Home** and **Contact** links is now blue</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="ae0b7-170">内部のスタイルシートを使用して、1つのページでスタイルを再利用する</span><span class="sxs-lookup"><span data-stu-id="ae0b7-170">Re-use styles on a single page with internal stylesheets</span></span>  

<span data-ttu-id="ae0b7-171">前のコードスニペットでは、インラインスタイルは1つのタグにスタイルを適用していま `<p>` した。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-171">In a previous code snippet, an inline style applied a style to a single `<p>` tag.</span></span>  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

<span data-ttu-id="ae0b7-172">`<p>`Web ページ上のすべての要素に同じようなスタイルを適用する必要がある場合はどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="ae0b7-172">What if you wanted all of the `<p>` elements on your webpage to be styled the same way?</span></span>  <span data-ttu-id="ae0b7-173">コードをコピーして、サイトのすべての1つのタグに貼り付ける必要があり `<p>` ます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-173">You would have to copy and paste the code into every single `<p>` tag on your site.</span></span>  <span data-ttu-id="ae0b7-174">これは多くの時間と労力を備えています。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-174">That is a lot of time and effort.</span></span>  <span data-ttu-id="ae0b7-175">編集を行う必要がある場合は、すべてのタグをもう一度変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-175">And, if you needed to make an edit, you would have to change every tag again.</span></span>  <span data-ttu-id="ae0b7-176">複数の要素に適用されるように、 **内部のスタイルシート** を使用して CSS を1つ作成するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-176">Complete the following actions to use an **Internal stylesheet** to write your CSS once so that it applies to multiple elements.</span></span>  

1.  <span data-ttu-id="ae0b7-177">「ライブ」タブで、「 **コンタクト** 」を選択して、コンタクトページに移動します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-177">In the live tab, choose **Contact** to go to the contact page.</span></span>  <span data-ttu-id="ae0b7-178">[ **ホーム** ] と [ **連絡先**] のフォントを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-178">Notice the font of **Home** and **Contact**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-internal1.msft.png" alt-text="[連絡先] ページ" lightbox="../media/beginners-css-internal1.msft.png":::
       <span data-ttu-id="ae0b7-180">[連絡先] ページ</span><span class="sxs-lookup"><span data-stu-id="ae0b7-180">The Contact page</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-181">[ **エディター] タブ**で、に移動 `contact.html` します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-181">In the **editor tab**, go to `contact.html`.</span></span>  
1.  <span data-ttu-id="ae0b7-182">次のコードをに追加 `contact.html` します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-182">Add the following code to `contact.html`.</span></span>  <span data-ttu-id="ae0b7-183">追加する必要があるのは、[で始まる] `<style>` と [末尾] の行 `</style>` だけです。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-183">Remember, the lines starting with `<style>` and ending with `</style>` are what you need to add.</span></span>  <span data-ttu-id="ae0b7-184">その他のコードは、新しいコードを配置する場所を知っているだけです。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-184">The other code is just there so you know where to put the new code.</span></span>  
    
    ```html
    ...
        <head>
            ...
            <meta name="viewport" content="width=device-width, initial-scale=1">
            <style>
                li a {
                  font-family: 'Courier New', Courier, Serif;
                }
            </style>
            ...
        </head>
        ...
    ...
    ```  
    
1.  <span data-ttu-id="ae0b7-185">[ **ライブ] タブ**に戻ります。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-185">Go back to the **live tab**.</span></span>  
1.  <span data-ttu-id="ae0b7-186">[ **連絡先** ] を選択して、連絡先ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-186">Choose **Contact** to go back to the contact page.</span></span>  <span data-ttu-id="ae0b7-187">[ **ホーム** ] と [ **連絡先** ] のフォントが変更されました。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-187">The font of **Home** and **Contact** has changed.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-internal2.msft.png" alt-text="自宅と連絡先のリンクのフォントが変更されました" lightbox="../media/beginners-css-internal2.msft.png":::
       <span data-ttu-id="ae0b7-189">**自宅**と**連絡先**のリンクのフォントが変更されました</span><span class="sxs-lookup"><span data-stu-id="ae0b7-189">The font of the **Home** and **Contact** links has changed</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="ae0b7-190">内部のスタイルシートについて</span><span class="sxs-lookup"><span data-stu-id="ae0b7-190">Understand internal stylesheets</span></span>  

<span data-ttu-id="ae0b7-191">内部スタイルシートは **セレクター**を使ってスタイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-191">Internal stylesheets apply styles using **selectors**.</span></span>  <span data-ttu-id="ae0b7-192">セレクターは、1つ以上の HTML 要素に適用される可能性があるパターンです。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-192">Selectors are patterns that may apply to one or more HTML elements.</span></span>  <span data-ttu-id="ae0b7-193">前のコードスニペットでは、次のスタイルが追加されています。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-193">The previous code snippet added the following style.</span></span>  

```html
<style>
    li a {
      font-family: 'Courier New', Courier, Serif;
    }
</style>
```  

`li a` <span data-ttu-id="ae0b7-194">は、"要素を含むすべての要素" に変換するセレクターです `<li>` `<a>` 。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-194">is a selector that translates to "any `<li>` element that contains an `<a>` element".</span></span>  <span data-ttu-id="ae0b7-195">各タググループはパターンと一致するため、ブラウザーは **ホーム** と **連絡先** のリンクのフォントを変更します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-195">The browser changes the font of the **Home** and **Contact** links because each of the tag groups match the pattern.</span></span>  

```html
<li><a href="/">Home</a></li>
<li><a href="/contact.html">Contact</a></li>
```  

`font-family: 'Courier New', Courier, serif` <span data-ttu-id="ae0b7-196">は **宣言**です。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-196">is a **declaration**.</span></span>  <span data-ttu-id="ae0b7-197">宣言は、次の2つの部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-197">A declaration is made of following two parts.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="ae0b7-198">プロパティー</span><span class="sxs-lookup"><span data-stu-id="ae0b7-198">property</span></span>**  
   :::column-end:::
   :::column span="1":::
      `font-family`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="ae0b7-199">プロパティでは、要素のスタイルを変更できる一般的な方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-199">The property describes a general way that you are able to change the style of the element.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="ae0b7-200">value</span><span class="sxs-lookup"><span data-stu-id="ae0b7-200">value</span></span>**  
   :::column-end:::
   :::column span="1":::
      `'Courier New', Courier, serif`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="ae0b7-201">この値は、要素のスタイルを変更する方法を正確に記述します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-201">The value describes exactly how the style of the element should change.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="ae0b7-202">たとえば、次のような指示が表示されます。 `font-family: 'Courier New', Courier, serif` "パターンと一致する要素のフォント `li a` を設定 `'Courier New'` します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-202">For example, `font-family: 'Courier New', Courier, serif` gives the browser the following instruction:  "Set the font of elements that match the pattern `li a` to `'Courier New'`.</span></span>  <span data-ttu-id="ae0b7-203">そのフォントが利用できない場合は、を使用 `Courier` します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-203">If that font is not available, use `Courier`.</span></span>  <span data-ttu-id="ae0b7-204">利用できない場合は、 `serif` 「」を使用します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-204">If that is not available, use `serif`."</span></span>  

### <span data-ttu-id="ae0b7-205">複数のセレクターをルールセットに追加する</span><span class="sxs-lookup"><span data-stu-id="ae0b7-205">Add multiple selectors to a ruleset</span></span>  

<span data-ttu-id="ae0b7-206">以下に示すような CSS コードのブロックは、 **ルールセット**と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-206">A block of CSS code like what you see below is called a **ruleset**.</span></span>  

```css
li a {
  font-family: 'Courier New', Courier, monospace;
}
```  

<span data-ttu-id="ae0b7-207">コンマを使用して複数のセレクターをルールセットに追加するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-207">Complete the following actions to use commas to add multiple selectors to a ruleset.</span></span>  

1.  <span data-ttu-id="ae0b7-208">[ **エディター] タブ**で、を開き `contact.html` ます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-208">In the **editor tab**, open `contact.html`.</span></span>  
1.  <span data-ttu-id="ae0b7-209">`li a`種類 `, h1` の後。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-209">After `li a` type `, h1`.</span></span>  
    
    ```html
    <style>
        li a, h1 {
          font-family: 'Courier New', Courier, Serif;
        }
    </style>
    ```  
    
    <span data-ttu-id="ae0b7-210">前のコードスニペットは、パターンと一致する要素のスタイルを示すのと同じように、ブラウザーに対して要素のスタイルを `<h1>` 適用し `li a` ます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-210">The previous code snippet tells the browser to style `<h1>` elements the same way that it styles elements that match the pattern `li a`.</span></span>  
    
1.  <span data-ttu-id="ae0b7-211">[ **ライブ] タブ**に移動します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-211">Go to the **live tab**.</span></span>  
1.  <span data-ttu-id="ae0b7-212">**連絡先のリンクを**選択して、連絡先ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-212">Choose the **Contact** link to go back to the contact page.</span></span>  <span data-ttu-id="ae0b7-213">今すぐ **連絡してください。**</span><span class="sxs-lookup"><span data-stu-id="ae0b7-213">Now, **Contact Me!**</span></span> <span data-ttu-id="ae0b7-214">ナビゲーションリンクと同じフォントに設定されています。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-214">has the same font as the navigation links.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-multiple1.msft.png" alt-text="「連絡」というテキストが表示されます。  自宅と連絡先のリンクと同じフォントになりました" lightbox="../media/beginners-css-multiple1.msft.png":::
       <span data-ttu-id="ae0b7-217">「連絡」というテキストが表示されます **。**</span><span class="sxs-lookup"><span data-stu-id="ae0b7-217">The text **Contact Me!**</span></span> <span data-ttu-id="ae0b7-218">**自宅**と**連絡先**のリンクと同じフォントになりました</span><span class="sxs-lookup"><span data-stu-id="ae0b7-218">now has the same font as the **Home** and **Contact** links</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="ae0b7-219">DevTools を使って実験する</span><span class="sxs-lookup"><span data-stu-id="ae0b7-219">Experiment with DevTools</span></span>  

<span data-ttu-id="ae0b7-220">今後、web 開発の専門家になるために、引き続き、CSS が複雑になることがあります。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-220">As you continue your journey to become an expert in web development, you may find that CSS is tricky.</span></span>  <span data-ttu-id="ae0b7-221">CSS を作成して、1つの方法で表示することも考えられますが、ブラウザーはまったく異なるものになります。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-221">You may write some CSS and expect it to display one way, but the browser does something completely different.</span></span>  <span data-ttu-id="ae0b7-222">Microsoft Edge DevTools を使うと、簡単に変更を試すことができ、変更内容がページにどのように影響するかをすぐに確認できます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-222">Microsoft Edge DevTools makes it easy to experiment with changes and immediately see how the changes affect the page.</span></span>  

### <span data-ttu-id="ae0b7-223">DevTools で既存の rulest に宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="ae0b7-223">Add a declaration to an existing rulest in DevTools</span></span>  

<span data-ttu-id="ae0b7-224">既存の要素のスタイルに対して反復処理を行うには、次の操作を実行し、既存のルールセットに宣言を追加します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-224">Complete the following actions to iterate on the style of an existing element, add a declaration to an existing ruleset.</span></span>  

1.  <span data-ttu-id="ae0b7-225">[ **ホーム** ] リンク上にマウスポインターを置いて、コンテキストメニュー \ (右クリック \) を開き、[ **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-225">Hover on the **Home** link, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add1.msft.png" alt-text="[ホーム] リンクを検査する" lightbox="../media/beginners-css-add1.msft.png":::
       <span data-ttu-id="ae0b7-227">[ホーム] リンクを検査する</span><span class="sxs-lookup"><span data-stu-id="ae0b7-227">Inspect the Home link</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="ae0b7-228">DevTools はページの横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-228">DevTools opens up alongside your page.</span></span>  <span data-ttu-id="ae0b7-229">[ホーム] リンクを表すコード `<a href="/">Home</a>` は、DOM ツリーで青色で強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-229">The code that represents the Home link, `<a href="/">Home</a>` is highlighted blue in the DOM Tree.</span></span>  <span data-ttu-id="ae0b7-230">コードスニペットとプレビューについては、「 [HTML と DOM の概要][DevtoolsBeginnersHtml]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-230">The code snippet and preview should be familiar from [Get Started with HTML and the DOM][DevtoolsBeginnersHtml].</span></span>  
    
    :::row:::
       :::column span="":::
          <span data-ttu-id="ae0b7-231">次の図では、 `font-family: 'Courier New', Courier, serif` 以前に追加した宣言 `contact.html` が DOM ツリーの下にある [ **スタイル** ] タブに表示されています。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-231">In the following figure, the `font-family: 'Courier New', Courier, serif` declaration that you previously added to `contact.html` is seen in the **Styles** tab below the DOM Tree.</span></span>  
          
          :::image type="complex" source="../media/beginners-css-add2.msft.png" alt-text="[スタイル] タブが DOM ツリーの下にある" lightbox="../media/beginners-css-add2.msft.png":::
             <span data-ttu-id="ae0b7-233">[ **スタイル** ] タブが DOM ツリーの下にある</span><span class="sxs-lookup"><span data-stu-id="ae0b7-233">The **Styles** tab is below the DOM Tree</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="ae0b7-234">DevTools ウィンドウが広くなっている場合、[スタイル] タブは DOM ツリーの右側にあります。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-234">If your DevTools window is wide, the Styles tab is to the right of the DOM Tree.</span></span>  
          
          :::image type="complex" source="../media/beginners-css-add3.msft.png" alt-text="[スタイル] タブは DOM ツリーの右側にあります。" lightbox="../media/beginners-css-add3.msft.png":::
             <span data-ttu-id="ae0b7-236">[ **スタイル** ] タブは DOM ツリーの右側にあります。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-236">The **Styles** tab is to the right of the DOM Tree</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="ae0b7-237">新しい宣言を追加するには、下の空の行を選び `font-family: 'Courier New', Courier, Serif` ます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-237">Choose the empty line below `font-family: 'Courier New', Courier, Serif` to add a new declaration.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add4.msft.png" alt-text="新しい宣言を追加する" lightbox="../media/beginners-css-add4.msft.png":::
       <span data-ttu-id="ae0b7-239">新しい宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="ae0b7-239">Add a new declaration</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-240">入力 `color` して、を選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-240">Type `color` and select `Enter`.</span></span>  <span data-ttu-id="ae0b7-241">入力時にオートコンプリート UI によってオプションが提示されます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-241">The autocomplete UI suggests options as you type.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add5.msft.png" alt-text="テキストの色" lightbox="../media/beginners-css-add5.msft.png":::
       <span data-ttu-id="ae0b7-243">型</span><span class="sxs-lookup"><span data-stu-id="ae0b7-243">Type</span></span> `color`  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-244">入力 `magenta` して、を選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-244">Type `magenta` and select `Enter`.</span></span>  <span data-ttu-id="ae0b7-245">連絡先ページのすべてのテキストがマジェンタ色になりました。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-245">All of the text on the contact page is now magenta.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add6.msft.png" alt-text="「マゼンタ」と入力" lightbox="../media/beginners-css-add6.msft.png":::
       <span data-ttu-id="ae0b7-247">型</span><span class="sxs-lookup"><span data-stu-id="ae0b7-247">Type</span></span> `magenta`  
    :::image-end:::  
    
### <span data-ttu-id="ae0b7-248">DevTools で宣言を編集する</span><span class="sxs-lookup"><span data-stu-id="ae0b7-248">Edit a declaration in DevTools</span></span>  

<span data-ttu-id="ae0b7-249">DevTools で既存の宣言を編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-249">Complete the following actions to edit existing declarations in DevTools.</span></span>  

1.  <span data-ttu-id="ae0b7-250">の横にあるマゼンタの正方形を選び `magenta` ます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-250">Choose the magenta square next to `magenta`.</span></span>  <span data-ttu-id="ae0b7-251">カラーピッカーがポップアップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-251">A color picker pops up.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-edit1.msft.png" alt-text="色のパレット" lightbox="../media/beginners-css-edit1.msft.png":::
       <span data-ttu-id="ae0b7-253">色のパレット</span><span class="sxs-lookup"><span data-stu-id="ae0b7-253">The Color Picker</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-254">カラーピッカーを使用して、フォントのテキストを好みの色に変更します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-254">Use the color picker to change the font text to a color that you like.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-edit2.msft.png" alt-text="カラーピッカーを使用してフォントの色を紫色に変更する" lightbox="../media/beginners-css-edit2.msft.png":::
       <span data-ttu-id="ae0b7-256">カラーピッカーを使用してフォントの色を紫色に変更する</span><span class="sxs-lookup"><span data-stu-id="ae0b7-256">Change the font color to purple with the Color Picker</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="ae0b7-257">DevTools で新しいルールセットを追加する</span><span class="sxs-lookup"><span data-stu-id="ae0b7-257">Add a new ruleset in DevTools</span></span>  

<span data-ttu-id="ae0b7-258">DevTools で新しいルールセットを追加するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-258">Complete the following actions to add new rulesets in DevTools.</span></span>  

1.  <span data-ttu-id="ae0b7-259">Cls の隣にある [**新しいスタイルルール**] \ ( ![ 新しいスタイルルール ][ImageNewStyleRuleIcon] ) **.cls**を選びます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-259">Choose **New Style Rule** \(![New Style Rule][ImageNewStyleRuleIcon]\) which is next to **.cls**.</span></span>  <span data-ttu-id="ae0b7-260">空のルールセットが `a` セレクターとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-260">An empty ruleset appears with `a` as the selector.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule1.msft.png" alt-text="新しいルールを追加する" lightbox="../media/beginners-css-rule1.msft.png":::
       <span data-ttu-id="ae0b7-262">新しいルールを追加する</span><span class="sxs-lookup"><span data-stu-id="ae0b7-262">Add a new rule</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-263">置換後 `a` の文字列 `a:hover`</span><span class="sxs-lookup"><span data-stu-id="ae0b7-263">Replace `a` with `a:hover`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule2.msft.png" alt-text="を "a/a" に変更する" lightbox="../media/beginners-css-rule2.msft.png":::
       <span data-ttu-id="ae0b7-265">置換後 `a` の文字列</span><span class="sxs-lookup"><span data-stu-id="ae0b7-265">Replace `a` with</span></span> `a:hover`  
    :::image-end:::  
    
    `:hover` <span data-ttu-id="ae0b7-266">は **擬似クラス**です。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-266">is a **pseudo-class**.</span></span>  <span data-ttu-id="ae0b7-267">特殊な状態を入力する可能性のあるスタイル要素には、擬似クラスを使います。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-267">Use pseudo-classes for style elements that may enter special states.</span></span>  <span data-ttu-id="ae0b7-268">たとえば、スタイルは、 `a:hover` 要素の上にマウスポインターを置いた場合にのみ有効になり `<a>` ます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-268">For example, the `a:hover` style only takes effect when you are hovering over an `<a>` element.</span></span>  
    
1.  <span data-ttu-id="ae0b7-269">角かっこの間を選択して新しい宣言を追加します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-269">Choose between the brackets to add a new declaration.</span></span>  
1.  <span data-ttu-id="ae0b7-270">`background-color`宣言の名前を入力して、を選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-270">Type `background-color` for the declaration name and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule3.msft.png" alt-text="背景色を入力する" lightbox="../media/beginners-css-rule3.msft.png":::
       <span data-ttu-id="ae0b7-272">型</span><span class="sxs-lookup"><span data-stu-id="ae0b7-272">Type</span></span> `background-color`  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-273">`green`[宣言] の値を入力して、を選択し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-273">Type `green` for the declaration value and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule4.msft.png" alt-text="「緑」と入力" lightbox="../media/beginners-css-rule4.msft.png":::
       <span data-ttu-id="ae0b7-275">型</span><span class="sxs-lookup"><span data-stu-id="ae0b7-275">Type</span></span> `green`  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-276">[ **ホーム** ] リンクの上にマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-276">Hover your mouse over the **Home** link.</span></span>  <span data-ttu-id="ae0b7-277">リンクの背景が緑色になります。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-277">The background of the link turns green.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule5.msft.png" alt-text="[ホーム] リンクをポイントすると、緑色の背景が表示されます。" lightbox="../media/beginners-css-rule5.msft.png":::
       <span data-ttu-id="ae0b7-279">[ホーム] リンクをポイントすると、緑色の背景が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-279">Hover over the Home link to reveal its green background</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="ae0b7-280">外部のスタイルシートを含むページ間でスタイルを再利用する</span><span class="sxs-lookup"><span data-stu-id="ae0b7-280">Re-use styles across pages with external stylesheets</span></span>  

<span data-ttu-id="ae0b7-281">前の手順では、次のコードスニペットを内部のスタイルシートとして追加しました `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-281">In a previous step, you added the following code snippet as an internal stylesheet to `contact.html`.</span></span>  

```html
...
    ...
        ...
        <style>
            li a, h1 {
              font-family: 'Courier New', Courier, Serif;
            }
        </style>
        ...
    ...
...
```  

<span data-ttu-id="ae0b7-282">同じ方法でスタイルを適用する場合は、どうすればよい `index.html` ですか。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-282">What if you wanted to style `index.html` the same way?</span></span>  <span data-ttu-id="ae0b7-283">スタイルを適用するには、多数のページが必要な場合はどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-283">What if you had a large number of pages to which you wanted to apply your styles?</span></span>  <span data-ttu-id="ae0b7-284">内部のスタイルシートをコピーして、サイトのすべての単一の web ページに貼り付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-284">You would have to copy and paste the internal stylesheet into every single web page on your site.</span></span>  <span data-ttu-id="ae0b7-285">CSS を一度作成して複数のページに適用できるように、 **外部のスタイルシート** を追加するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-285">Complete the following actions to add an **External stylesheet** to allow you to write your CSS once and apply it to multiple pages.</span></span>  

1.  <span data-ttu-id="ae0b7-286">まず、[ライブ] タブをもう一度読み込んで、DevTools で行った変更を削除します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-286">First, reload the live tab to remove the changes that you made in DevTools.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external1.msft.png" alt-text=" ページを更新すると、DevTools で行った変更は廃止されます。" lightbox="../media/beginners-css-external1.msft.png":::
        <span data-ttu-id="ae0b7-288">ページを更新すると、DevTools で行った変更は廃止されます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-288">After you refresh the page, the changes that were made in DevTools are gone</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-289">[ **エディター] タブ** に戻り、を開き `contact.html` ます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-289">Go back to the **editor tab** and open `contact.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external2.msft.png" alt-text="contact.html" lightbox="../media/beginners-css-external2.msft.png":::
       <span data-ttu-id="ae0b7-291">contact.html</span><span class="sxs-lookup"><span data-stu-id="ae0b7-291">contact.html</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-292">およびを `<style>` `</style>` 含む、and を含むすべてのデータを削除し `<style>` `</style>` ます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-292">Delete everything between `<style>` and `</style>`, including `<style>` and `</style>`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external3.msft.png" alt-text="スタイルタグが削除されました" lightbox="../media/beginners-css-external3.msft.png":::
       <span data-ttu-id="ae0b7-294">スタイルタグが削除されました</span><span class="sxs-lookup"><span data-stu-id="ae0b7-294">The style tag has been removed</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-295">`index.html`タグから移動して削除し `style="background-color: aliceblue;"` `<nav>` ます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-295">Go to `index.html` and remove `style="background-color: aliceblue;"` from the `<nav>` tag.</span></span>  <span data-ttu-id="ae0b7-296">これで、以前にサイトに追加した CSS がすべて削除されました。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-296">You have now removed all of the CSS that you previously added to your site.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external4.msft.png" alt-text="インラインスタイルが nav 要素から削除されている" lightbox="../media/beginners-css-external4.msft.png":::
       <span data-ttu-id="ae0b7-298">インラインスタイルが nav 要素から削除されている</span><span class="sxs-lookup"><span data-stu-id="ae0b7-298">The inline style has been removed from the nav element</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-299">[ **新しいファイル**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-299">Choose **New File**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external5.msft.png" alt-text="[新しいファイル] ダイアログ" lightbox="../media/beginners-css-external5.msft.png":::
       <span data-ttu-id="ae0b7-301">[新しいファイル] ダイアログ</span><span class="sxs-lookup"><span data-stu-id="ae0b7-301">The new file dialog</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-302">[置換後 `cool-file.js` の文字列 `style.css` ] を選び、[ **ファイルの追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-302">Replace `cool-file.js` with `style.css` and choose **Add File**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external6.msft.png" alt-text="「スタイル .css」と入力します。" lightbox="../media/beginners-css-external6.msft.png":::
       <span data-ttu-id="ae0b7-304">型</span><span class="sxs-lookup"><span data-stu-id="ae0b7-304">Type</span></span> `style.css`  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-305">次のコードスニペットをファイルに追加し `style.css` ます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-305">Add the following code snippet to your `style.css` file.</span></span>  
    
    ```css
    li a, h1 {
      font-family: 'Courier New', Courier, Serif;
    }
    a:hover {
      background-color: green;
    }
    nav {
      background-color: aliceblue;
    }
    ```  
    
    :::image type="complex" source="../media/beginners-css-external7.msft.png" alt-text=".Css にコードを追加する" lightbox="../media/beginners-css-external7.msft.png":::
       <span data-ttu-id="ae0b7-307">コードを追加</span><span class="sxs-lookup"><span data-stu-id="ae0b7-307">Add code to</span></span> `style.css`  
    :::image-end:::  
    
    <span data-ttu-id="ae0b7-308">外部のスタイルシートが作成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-308">Ensure that you have created an external stylesheet.</span></span> <span data-ttu-id="ae0b7-309">HTML では、存在することは認識されません。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-309">Your HTML is not aware that it exists.</span></span>  
    
1.  <span data-ttu-id="ae0b7-310">[開く] `index.html` を選びます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-310">Open `index.html`.</span></span>  
1.  <span data-ttu-id="ae0b7-311">`<link rel="stylesheet" href="style.css">`HTML に追加します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-311">Add `<link rel="stylesheet" href="style.css">` to your HTML.</span></span>  
    
    ```html
    <head>
        ...
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href="style.css">
    </head>
    ```  
    
    :::image type="complex" source="../media/beginners-css-external8.msft.png" alt-text="スタイル .css へのリンク" lightbox="../media/beginners-css-external8.msft.png":::
       <span data-ttu-id="ae0b7-313">へのリンク</span><span class="sxs-lookup"><span data-stu-id="ae0b7-313">Link to</span></span> `style.css`  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-314">ファイルを開き、 `contact.html` そこにリンクを追加します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-314">Open the `contact.html` file and add the link there.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external9.msft.png" alt-text="contact.html のスタイル .css へのリンク" lightbox="../media/beginners-css-external9.msft.png":::
       <span data-ttu-id="ae0b7-316">[リンク先] `style.css`</span><span class="sxs-lookup"><span data-stu-id="ae0b7-316">Link to `style.css` in</span></span> `contact.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-317">[ **ライブ] タブ**に移動します。 これで、ホームページの最後のセクションと青色のナビゲーションセクションのフォントが変わりました。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-317">Go to the **live tab**.  The home page now has the same font from the last section and a blue navigation section.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external10.msft.png" alt-text="ホームページ" lightbox="../media/beginners-css-external10.msft.png":::
       <span data-ttu-id="ae0b7-319">ホームページ</span><span class="sxs-lookup"><span data-stu-id="ae0b7-319">The home page</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-320">[ **連絡先** ] リンクを選択して、連絡先ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-320">Choose the **Contact** link to go to the contact page.</span></span>  <span data-ttu-id="ae0b7-321">連絡先ページは、ホームページと同じ書式設定になっています。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-321">The contact page has the same formatting as the home page.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external11.msft.png" alt-text="[連絡先] ページ" lightbox="../media/beginners-css-external11.msft.png":::
       <span data-ttu-id="ae0b7-323">[連絡先] ページ</span><span class="sxs-lookup"><span data-stu-id="ae0b7-323">The contact page</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="ae0b7-324">CSS フレームワークを使う</span><span class="sxs-lookup"><span data-stu-id="ae0b7-324">Use a CSS framework</span></span>  

<span data-ttu-id="ae0b7-325">**CSS フレームワーク** は、魅力的な web サイトを簡単に作成できる他の開発者によって構築されたスタイルのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-325">**CSS frameworks** are collections of styles built by other developers that make it easier to create attractive web sites.</span></span>  <span data-ttu-id="ae0b7-326">独自のスタイルを定義する代わりに、フレームワークによって、ページ要素で使うことができるスタイルのコレクションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-326">Instead of defining styles yourself, a framework provides you a collection of styles that you are able to use on your page elements.</span></span>  

1.  <span data-ttu-id="ae0b7-327">次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-327">Copy the following code:</span></span>  
    
    ```html
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.1/css/bootstrap.min.css">
    ```  
    
1.  <span data-ttu-id="ae0b7-328">[編集] タブに移動し、コードを貼り付け `contact.html` ます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-328">Go to the editing tab and paste the code into `contact.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-framework1.msft.png" alt-text="contact.html のフレームワークへのリンク" lightbox="../media/beginners-css-framework1.msft.png":::
       <span data-ttu-id="ae0b7-330">フレームワークへのリンク</span><span class="sxs-lookup"><span data-stu-id="ae0b7-330">Link to the framework in</span></span> `contact.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-331">ファイルを開き、 `index.html` そこにコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-331">Open the `index.html` file and add the code there.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-framework2.msft.png" alt-text="index.html のフレームワークへのリンク" lightbox="../media/beginners-css-framework2.msft.png":::
       <span data-ttu-id="ae0b7-333">フレームワークへのリンク</span><span class="sxs-lookup"><span data-stu-id="ae0b7-333">Link to the framework in</span></span> `index.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-334">[ライブ] タブに戻り、変更内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-334">Go back to the live tab to view your changes.</span></span>  <span data-ttu-id="ae0b7-335">要素の背景色 `<nav>` と要素のフォントは同じであるのに、 `<li>` 他の `<a>` 要素のフォントが変更されています。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-335">While the background color of the `<nav>` element and the font of the `<li>` and `<a>` elements are the same, the font of the other elements has changed.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-framework3.msft.png" alt-text="フレームワークによって変更されたホームページのフォントの一部" lightbox="../media/beginners-css-framework3.msft.png":::
       <span data-ttu-id="ae0b7-337">フレームワークによって変更されたホームページのフォントの一部</span><span class="sxs-lookup"><span data-stu-id="ae0b7-337">Some of the font on the home page changed because of the framework</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="ae0b7-338">クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="ae0b7-338">Use a class</span></span>  

<span data-ttu-id="ae0b7-339">最後のセクションでは、web ページにブートストラップを追加して、サイトの要素のフォントを変更しました。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-339">In the last section, you added Bootstrap to your web pages, which changed the fonts of some of the elements on your site.</span></span>  <span data-ttu-id="ae0b7-340">CSS フレームワークを使うと、わずかなコードでページに大きな変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-340">CSS frameworks help you make major changes to your page with very little code.</span></span>  <span data-ttu-id="ae0b7-341">ヘッダーを変更するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-341">Complete the following actions to change your header.</span></span>  

1.  <span data-ttu-id="ae0b7-342">次のコードスニペットをコピーします。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-342">Copy the following code snippet.</span></span>  
    
    ```html
    class="jumbotron jumbotron-fluid"  
    ```  
    
1.  <span data-ttu-id="ae0b7-343">前のコードスニペットをタグに追加 `<header>` `index.html` します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-343">Add the previous code snippet to your `<header>` tag in `index.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-jumbotron1.msft.png" alt-text="index.html でクラスを追加する" lightbox="../media/beginners-css-jumbotron1.msft.png":::
       <span data-ttu-id="ae0b7-345">クラスを追加する</span><span class="sxs-lookup"><span data-stu-id="ae0b7-345">Add classes in</span></span> `index.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-346">タグにコードを追加 `<header>` `contact.html` します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-346">Add the code to your `<header>` tag in `contact.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-jumbotron2.msft.png" alt-text="contact.html でクラスを追加する" lightbox="../media/beginners-css-jumbotron2.msft.png":::
       <span data-ttu-id="ae0b7-348">クラスを追加する</span><span class="sxs-lookup"><span data-stu-id="ae0b7-348">Add classes in</span></span> `contact.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-349">[ライブ] タブで変更内容を表示します。 ヘッダーの周りに大きな灰色のボックスがあります。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-349">View your changes in the live tab.  There is a big, grey box around your header.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-jumbotron3.msft.png" alt-text="ヘッダーの周りに大きな灰色のボックスがあるようになりました" lightbox="../media/beginners-css-jumbotron3.msft.png":::
       <span data-ttu-id="ae0b7-351">ヘッダーの周りに大きな灰色のボックスがあるようになりました</span><span class="sxs-lookup"><span data-stu-id="ae0b7-351">The header now has a big, grey box around it</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="ae0b7-352">クラスについて</span><span class="sxs-lookup"><span data-stu-id="ae0b7-352">Understand classes</span></span>  

<span data-ttu-id="ae0b7-353">クラスを使うと、スタイルのコレクションを任意の要素に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-353">Classes let you assign collections of styles to arbitrary elements.</span></span>  <span data-ttu-id="ae0b7-354">属性を設定した後で要素にいくつかのスタイルを適用するには、次のコードスニペットを使用し `<header>` `class` `jumbotron` ます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-354">Use the following code snippet to apply several styles to the `<header>` element after you set the `class` attribute to `jumbotron`.</span></span>  

```css
.jumbotron {
  padding: 2rem 1rem;
  margin-bottom: 2rem;
  background-color: #e9ecef;
  border-radius: .3rem;
}
```  

<span data-ttu-id="ae0b7-355">クラスの1つの利点は、目的の要素にスタイルを適用できることです。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-355">One advantage of a class is that it lets you apply styles to whatever elements you want.</span></span>  <span data-ttu-id="ae0b7-356">たとえば、一部の要素の背景色を紫色に設定し、すべての要素では設定しないとし `<p>` `<p>` ます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-356">For example, suppose you want to set the background color of some `<p>` elements to purple, but not all `<p>` elements.</span></span>  <span data-ttu-id="ae0b7-357">クラスでスタイルを定義するには、次のコードスニペットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-357">Use the following code snippet to define the style in a class.</span></span>  

```css
.custom-background {
  background-color: purple;
}
```  

<span data-ttu-id="ae0b7-358">次に、スタイルを適用する要素のみにクラスを適用し `<p>` ます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-358">Next, apply the class to only the `<p>` elements that you want to style.</span></span>  

```html
<p>The text is not purple.</p>
<p class="custom-background">The text is purple.</p>
<p>The text is not purple.</p>
<p class="custom-background">The text is purple.</p>
```  

### <span data-ttu-id="ae0b7-359">要素の配置</span><span class="sxs-lookup"><span data-stu-id="ae0b7-359">Align elements</span></span>  

<span data-ttu-id="ae0b7-360">ブートストラップに対して次の操作を実行し、要素を配置するためのクラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-360">Complete the following actions to bootstrap and provide classes for aligning elements.</span></span>  

1.  <span data-ttu-id="ae0b7-361">[エディター] タブに戻り、を開き `index.html` ます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-361">Go back to the editor tab and open `index.html`.</span></span>  
1.  <span data-ttu-id="ae0b7-362">`class="container-fluid"`タグに追加 `<body>` します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-362">Add `class="container-fluid"` to your `<body>` tag.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align1.msft.png" alt-text="コンテナー-流体クラスを追加する" lightbox="../media/beginners-css-align1.msft.png":::
       <span data-ttu-id="ae0b7-364">クラスを追加する `container-fluid`</span><span class="sxs-lookup"><span data-stu-id="ae0b7-364">Add the `container-fluid` class</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-365">`<nav>`と `<main>` の要素を折り返し `<div class="row">` ます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-365">Wrap your `<nav>` and `<main>` elements in `<div class="row">`.</span></span>  <span data-ttu-id="ae0b7-366">`</div>` `</main>` 新しいノートシールを正しく閉じるには、[指定の日時以降] をオンにしてください。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-366">Make sure to put `</div>` after `</main>` in order to properly close the new tag.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align2.msft.png" alt-text="行を追加する" lightbox="../media/beginners-css-align2.msft.png":::
       <span data-ttu-id="ae0b7-368">行を追加する</span><span class="sxs-lookup"><span data-stu-id="ae0b7-368">Add a row</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-369">`class="col-3"` `<nav>` タグとタグに追加 `class="col-9"` `<main>` します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-369">Add `class="col-3"` to your `<nav>` tag and `class="col-9"` to your `<main>` tag.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align3.msft.png" alt-text="列3と列9のクラスを追加する" lightbox="../media/beginners-css-align3.msft.png":::
       <span data-ttu-id="ae0b7-371">`col-3`クラスとクラスを追加する `col-9`</span><span class="sxs-lookup"><span data-stu-id="ae0b7-371">Add the `col-3` and `col-9` classes</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ae0b7-372">[ライブ] タブで変更内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-372">View your changes in the live tab.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align4.msft.png" alt-text="これで、ナビゲーションコンテンツがメインコンテンツの左になりました" lightbox="../media/beginners-css-align4.msft.png":::
       <span data-ttu-id="ae0b7-374">これで、ナビゲーションコンテンツがメインコンテンツの左になりました</span><span class="sxs-lookup"><span data-stu-id="ae0b7-374">The nav content is now to the left of the main content</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="ae0b7-375">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ae0b7-375">Next steps</span></span>  

<span data-ttu-id="ae0b7-376">おめでとうございます。これで完了です。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-376">Congratulations, you are done.</span></span>  

*   <span data-ttu-id="ae0b7-377">Web 開発に適した方法は、さらに多くのサイトを構築することです。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-377">The best way to get better at web development is to build more sites.</span></span>  <span data-ttu-id="ae0b7-378">問題を壊す心配はありません。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-378">Do not worry about breaking stuff.</span></span>  <span data-ttu-id="ae0b7-379">今まで以上に楽しく、できる限り学習しましょう。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-379">Just have fun and learn as much as possible along the way.</span></span>  
*   <span data-ttu-id="ae0b7-380">Web ページのスタイル設定の詳細については、「 [CSS の概要][MDNCssFirstSteps]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-380">To learn more about styling web pages, see [Introduction to CSS][MDNCssFirstSteps].</span></span>  
*   <span data-ttu-id="ae0b7-381">DevTools を使ってページの CSS を試す方法の詳細については、「 [css の表示と変更の概要][DevtoolsCssIndex]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-381">To learn more about how to use DevTools to experiment with the CSS of a page, see [Get Started with Viewing and Changing CSS][DevtoolsCssIndex].</span></span>  

<!--- image links --->  

[ImageNewStyleRuleIcon]: ../media/new-style-rule-icon.msft.png  

<!--- links  --->  

[DevtoolsBeginnersHtml]: ./html.md "初心者向けの DevTools: HTML と DOM の使用を開始する |Microsoft ドキュメント"  
[DevtoolsCssIndex]: ../css/index.md "CSS の表示と変更の概要 |Microsoft ドキュメント"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge Insider"  

[GlitchCookedAmphibianIndex]: https://glitch.com/edit/#!/cooked-amphibian?path=index.html "index.html-クック-水陸両用機 |故障"  

[MDNCssFirstSteps]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS "CSS の最初のステップ |MDN"  

> [!NOTE]
> <span data-ttu-id="ae0b7-387">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-387">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="ae0b7-388">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/beginners/css) にあり、 [Katherine Jackson][KatherineJackson] \ (テクニカルライターインターン、Chrome devtools) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-388">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/beginners/css) and is authored by [Katherine Jackson][KatherineJackson] \(Technical Writer Intern, Chrome DevTools\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="ae0b7-390">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="ae0b7-390">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
