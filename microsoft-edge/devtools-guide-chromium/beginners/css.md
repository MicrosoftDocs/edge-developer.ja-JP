---
description: CSS の使用を開始する
title: '初級者向け DevTools: CSS の使用を開始する'
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools
ms.openlocfilehash: 6a7135e144123917535e7c43e6a3cd608ec0c8a7
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439438"
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

# <a name="devtools-for-beginners-get-started-with-css"></a><span data-ttu-id="9f54e-104">初級者向け DevTools: CSS の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="9f54e-104">DevTools for beginners: Get started with CSS</span></span>  

<span data-ttu-id="9f54e-105">このチュートリアルでは、CSS を使用して Web ページのスタイルを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-105">In this tutorial, you learn how to use CSS to style a web page.</span></span>  <span data-ttu-id="9f54e-106">また、Microsoft Edge DevTools を使用して CSS の変更を試す方法も説明します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-106">You also learn how to use Microsoft Edge DevTools to experiment with CSS changes.</span></span>  

<span data-ttu-id="9f54e-107">次の記事は、Web 開発と Microsoft Edge DevTools の基本を説明する一連のチュートリアルの 2 番目のチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="9f54e-107">The following article is the second tutorial in a series of tutorials that teaches you the basics of web development and Microsoft Edge DevTools.</span></span>  <span data-ttu-id="9f54e-108">実際に独自の Web サイトを構築することで、実践的なエクスペリエンスを得る。</span><span class="sxs-lookup"><span data-stu-id="9f54e-108">You gain hands-on experience by actually building your own website.</span></span>  <span data-ttu-id="9f54e-109">2 番目のチュートリアルに従う前に、最初のチュートリアルを完了する必要はもうない。</span><span class="sxs-lookup"><span data-stu-id="9f54e-109">You do not have to complete the first tutorial before following the second.</span></span>  <span data-ttu-id="9f54e-110">[コードを設定すると、](#set-up-your-code) セットアップ方法が示されます。</span><span class="sxs-lookup"><span data-stu-id="9f54e-110">[Set up your code](#set-up-your-code) shows you how to get set up.</span></span>  

> [!NOTE]
> <span data-ttu-id="9f54e-111">このチュートリアルは、完全な初心者向けの設計で **、Web** 開発の基本と DevTools を使用して CSS を実験する基本の両方に焦点を当てしています。</span><span class="sxs-lookup"><span data-stu-id="9f54e-111">This tutorial is designed for absolute beginners and focuses on both the **fundamentals of web development** and the basics of using DevTools to experiment with CSS.</span></span>  <span data-ttu-id="9f54e-112">DevTools にのみ焦点を当てたチュートリアルが必要な場合は、[CSS の表示と変更を開始する] [に移動します][DevtoolsCssIndex]。</span><span class="sxs-lookup"><span data-stu-id="9f54e-112">If you want a tutorial that only focuses on DevTools, navigate to [Get Started with Viewing and Changing CSS][DevtoolsCssIndex].</span></span>  

<span data-ttu-id="9f54e-113">チュートリアルの冒頭で、サイトは次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="9f54e-113">At the beginning of the tutorial, your site should look like the following figure.</span></span>  

:::image type="complex" source="../media/beginners-css-intro1.msft.png" alt-text="サイトの現在の外観" lightbox="../media/beginners-css-intro1.msft.png":::
   <span data-ttu-id="9f54e-115">サイトの現在の外観</span><span class="sxs-lookup"><span data-stu-id="9f54e-115">What your site currently looks like</span></span>  
:::image-end:::  

<span data-ttu-id="9f54e-116">チュートリアルを完了すると、サイトは次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="9f54e-116">After you complete the tutorial, you site should look like the following figure.</span></span>  

:::image type="complex" source="../media/beginners-css-intro2.msft.png" alt-text="チュートリアルの最後のサイトの外観" lightbox="../media/beginners-css-intro2.msft.png":::
   <span data-ttu-id="9f54e-118">チュートリアルの最後のサイトの外観</span><span class="sxs-lookup"><span data-stu-id="9f54e-118">What your site should look like at the end of the tutorial</span></span>  
:::image-end:::  

## <a name="goals"></a><span data-ttu-id="9f54e-119">目標</span><span class="sxs-lookup"><span data-stu-id="9f54e-119">Goals</span></span>  

<span data-ttu-id="9f54e-120">このチュートリアルに従って、以下の概念とタスクについて理解してください。</span><span class="sxs-lookup"><span data-stu-id="9f54e-120">Follow this tutorial to better understand the following concepts and tasks.</span></span>  

*   <span data-ttu-id="9f54e-121">CSS を使用して Web ページのスタイルを設定する方法。</span><span class="sxs-lookup"><span data-stu-id="9f54e-121">How to use CSS to style a web page.</span></span>  
*   <span data-ttu-id="9f54e-122">Microsoft Edge DevTools を使用して CSS を試す方法。</span><span class="sxs-lookup"><span data-stu-id="9f54e-122">How to use Microsoft Edge DevTools to experiment with CSS.</span></span>  
*   <span data-ttu-id="9f54e-123">CSS フレームワークと CSS フレームワークの違い。</span><span class="sxs-lookup"><span data-stu-id="9f54e-123">The difference between CSS and CSS frameworks.</span></span>  

<span data-ttu-id="9f54e-124">実際の Web サイトを作成しています。</span><span class="sxs-lookup"><span data-stu-id="9f54e-124">You are building a real website.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="9f54e-125">前提条件</span><span class="sxs-lookup"><span data-stu-id="9f54e-125">Prerequisites</span></span>  

<span data-ttu-id="9f54e-126">このチュートリアルを試す前に、次の前提条件を満たしてください。</span><span class="sxs-lookup"><span data-stu-id="9f54e-126">Before attempting this tutorial, complete the following prerequisites.</span></span>  

*   <span data-ttu-id="9f54e-127">[HTML [と DOM の][DevtoolsBeginnersHtml] 使用を開始する] を完了するか、HTML と DOM について理解し、そのチュートリアルで教えられたものに似たものにしてください。</span><span class="sxs-lookup"><span data-stu-id="9f54e-127">Complete [Get Started with HTML and the DOM][DevtoolsBeginnersHtml] or make sure that you have an understanding of HTML and the DOM similar to what is taught in that tutorial.</span></span>  
*   <span data-ttu-id="9f54e-128">Microsoft [Edge Web ブラウザーを][MicrosoftEdgeInsider] ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9f54e-128">Download the [Microsoft Edge][MicrosoftEdgeInsider] web browser.</span></span>  <span data-ttu-id="9f54e-129">次のチュートリアルでは、Microsoft Edge に組み込む Microsoft Edge DevTools と呼ばれる一連の Web 開発ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-129">The following tutorial uses a set of web development tools, called the Microsoft Edge DevTools, that are built into Microsoft Edge.</span></span>  

## <a name="set-up-your-code"></a><span data-ttu-id="9f54e-130">コードを設定する</span><span class="sxs-lookup"><span data-stu-id="9f54e-130">Set up your code</span></span>  

<span data-ttu-id="9f54e-131">サイトを作成するには、まず次のアクションを実行してコードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f54e-131">To create your site, you must first complete the following actions to set up your code.</span></span>  

> [!NOTE]
> <span data-ttu-id="9f54e-132">シリーズの最初のチュートリアルを既に完了している場合は、次のセクションに進んでください。</span><span class="sxs-lookup"><span data-stu-id="9f54e-132">If you have already completed the first tutorial in the series, skip to the next section.</span></span>  <span data-ttu-id="9f54e-133">最後のチュートリアル「HTML と DOM の使用を開始する」のコード [を引き続き使用します][DevtoolsBeginnersHtml]。</span><span class="sxs-lookup"><span data-stu-id="9f54e-133">Continue using your code from the last tutorial, [Get Started with HTML and the DOM][DevtoolsBeginnersHtml].</span></span>  

1.  <span data-ttu-id="9f54e-134">ソース コード [を開きます][GlitchCookedAmphibianIndex]。</span><span class="sxs-lookup"><span data-stu-id="9f54e-134">Open the [source code][GlitchCookedAmphibianIndex].</span></span>  <span data-ttu-id="9f54e-135">ブラウザーのフォーカス内タブは、編集タブとして **参照されます**。</span><span class="sxs-lookup"><span data-stu-id="9f54e-135">The in-focus tab of your browser is referenced as the **editing tab**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-setup1.msft.png" alt-text="[編集] タブ" lightbox="../media/beginners-css-setup1.msft.png":::
       <span data-ttu-id="9f54e-137">[ **編集]** タブ</span><span class="sxs-lookup"><span data-stu-id="9f54e-137">The **editing** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-138">調理 **された両生類を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9f54e-138">Choose **cooked-amphibian**.</span></span>  <span data-ttu-id="9f54e-139">メニューがポップアップします。</span><span class="sxs-lookup"><span data-stu-id="9f54e-139">A menu pops up.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-setup2.msft.png" alt-text="[プロジェクト オプション] メニュー" lightbox="../media/beginners-css-setup2.msft.png":::
       <span data-ttu-id="9f54e-141">[プロジェクト オプション] メニュー</span><span class="sxs-lookup"><span data-stu-id="9f54e-141">The Project Options menu</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="9f54e-142">**[Remix Project] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9f54e-142">Choose **Remix Project**.</span></span>  <span data-ttu-id="9f54e-143">Glitch は、編集できるプロジェクトのコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-143">Glitch creates a copy of the project that you are able to edit.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="9f54e-144">Glitch は、新しいプロジェクトのランダムな名前を生成します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-144">Glitch generates a random name for the new project.</span></span>  
    
1.  <span data-ttu-id="9f54e-145">[表示 **] を** 選択し、[ **新しいウィンドウ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9f54e-145">Choose **Show** and choose **In a New Window**.</span></span>  <span data-ttu-id="9f54e-146">別のタブが開き、サイトのライブ ビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f54e-146">Another tab opens with a live view of your site.</span></span>  <span data-ttu-id="9f54e-147">ブラウザーのフォーカス内タブは、ライブ タブとして **参照されます**。</span><span class="sxs-lookup"><span data-stu-id="9f54e-147">The in-focus tab of your browser is referenced as the **live tab**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-setup3.msft.png" alt-text="[ライブ] タブ" lightbox="../media/beginners-css-setup3.msft.png":::
       <span data-ttu-id="9f54e-149">[ライブ **] タブ**</span><span class="sxs-lookup"><span data-stu-id="9f54e-149">The **live tab**</span></span>  
    :::image-end:::  

## <a name="understand-css"></a><span data-ttu-id="9f54e-150">CSS について</span><span class="sxs-lookup"><span data-stu-id="9f54e-150">Understand CSS</span></span>  

<span data-ttu-id="9f54e-151">**CSS** は、Web ページのレイアウトとスタイルを決定するコンピューター言語です。</span><span class="sxs-lookup"><span data-stu-id="9f54e-151">**CSS** is a computer language that determines the layout and styling of web pages.</span></span>  <span data-ttu-id="9f54e-152">次の図は、罫線を持つ段落です。</span><span class="sxs-lookup"><span data-stu-id="9f54e-152">The following figure is a paragraph with a border.</span></span>  

:::image type="complex" source="../media/beginners-css-red_paragraph.msft.png" alt-text="テキストは CSS でスタイル設定されています" lightbox="../media/beginners-css-red_paragraph.msft.png":::
   <span data-ttu-id="9f54e-154">テキストは CSS でスタイル設定されています</span><span class="sxs-lookup"><span data-stu-id="9f54e-154">The text has been styled with CSS</span></span>  
:::image-end:::  

<span data-ttu-id="9f54e-155">次のコード スニペットは、前の図の段落を作成するために使用される HTML コードと CSS コードです。</span><span class="sxs-lookup"><span data-stu-id="9f54e-155">The following code snippet is the HTML and CSS code used to create the paragraph in the previous figure.</span></span>  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

`style="border: 1px dashed red; padding: 5px;"` <span data-ttu-id="9f54e-156">おそらく、新しく見えます。</span><span class="sxs-lookup"><span data-stu-id="9f54e-156">probably looks new to you.</span></span>  <span data-ttu-id="9f54e-157">残りの部分は見慣れたものに見える必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f54e-157">The rest should look familiar.</span></span>  <span data-ttu-id="9f54e-158">完了していない場合は [、HTML と DOM の][DevtoolsBeginnersHtml] 使用を開始してから、次のセクションを試してください。</span><span class="sxs-lookup"><span data-stu-id="9f54e-158">If not, complete [Get Started with HTML and the DOM][DevtoolsBeginnersHtml] before attempting the following sections.</span></span>  

## <a name="add-inline-styles"></a><span data-ttu-id="9f54e-159">インライン スタイルの追加</span><span class="sxs-lookup"><span data-stu-id="9f54e-159">Add inline styles</span></span>  

<span data-ttu-id="9f54e-160">インライン スタイルを使用して 1 つの **要素に** スタイルを適用するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-160">Complete the following actions to use **inline styles** to apply styles to a single element.</span></span>  

1.  <span data-ttu-id="9f54e-161">編集タブに戻り、開きます `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="9f54e-161">Go back to the editing tab and open `index.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-inline1.msft.png" alt-text="index.html" lightbox="../media/beginners-css-inline1.msft.png":::
       <span data-ttu-id="9f54e-163">編集 `index.html` タブで開く</span><span class="sxs-lookup"><span data-stu-id="9f54e-163">Open `index.html` in the editing tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-164">に `style="background-color: aliceblue;"` 追加します `<nav>` 。</span><span class="sxs-lookup"><span data-stu-id="9f54e-164">Add `style="background-color: aliceblue;"` to your `<nav>`.</span></span>  <span data-ttu-id="9f54e-165">次のコード ブロックでは、4 行目のコードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f54e-165">In the code block below, the fourth line of code is the one you need to change.</span></span>  <span data-ttu-id="9f54e-166">残りはただそこにあるので、新しいコードを適切な場所に配置することができます。</span><span class="sxs-lookup"><span data-stu-id="9f54e-166">The rest is just there, so you are able to ensure that you are putting the new code in the right place.</span></span>  
    
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
    
1.  <span data-ttu-id="9f54e-167">変更を表示するには、ライブ タブに **移動します**。 これで、セクションの `<nav>` 背景が青になります。</span><span class="sxs-lookup"><span data-stu-id="9f54e-167">To display the changes, navigate to the **live tab**.  The background of the `<nav>` section is now blue.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-inline2.msft.png" alt-text="[ホーム] リンクと [連絡先] リンクの背景の背景色が青色に変更されました" lightbox="../media/beginners-css-inline2.msft.png":::
       <span data-ttu-id="9f54e-169">[ホーム] リンクと [連絡先]**リンクの背景\*\*\*\*の背景色**が青色に変更されました</span><span class="sxs-lookup"><span data-stu-id="9f54e-169">The background color behind the **Home** and **Contact** links is now blue</span></span>  
    :::image-end:::  
    
## <a name="re-use-styles-on-a-single-page-with-internal-stylesheets"></a><span data-ttu-id="9f54e-170">内部スタイルシートを使用して 1 つのページでスタイルを再使用する</span><span class="sxs-lookup"><span data-stu-id="9f54e-170">Re-use styles on a single page with internal stylesheets</span></span>  

<span data-ttu-id="9f54e-171">前のコード スニペットでは、インライン スタイルが 1 つのタグにスタイルを適用 `<p>` しました。</span><span class="sxs-lookup"><span data-stu-id="9f54e-171">In a previous code snippet, an inline style applied a style to a single `<p>` tag.</span></span>  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

<span data-ttu-id="9f54e-172">Web ページのすべての要素を同じスタイルにしたい `<p>` 場合は、どうしますか?</span><span class="sxs-lookup"><span data-stu-id="9f54e-172">What if you wanted all of the `<p>` elements on your webpage to be styled the same way?</span></span>  <span data-ttu-id="9f54e-173">サイト上のすべてのタグにコードをコピーして貼り `<p>` 付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f54e-173">You have to copy and paste the code into every single `<p>` tag on your site.</span></span>  <span data-ttu-id="9f54e-174">これは多くの時間と労力です。</span><span class="sxs-lookup"><span data-stu-id="9f54e-174">That is a lot of time and effort.</span></span>  <span data-ttu-id="9f54e-175">また、編集が必要な場合は、すべてのタグを再度変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f54e-175">And, if you needed to make an edit, you have to change every tag again.</span></span>  <span data-ttu-id="9f54e-176">次のアクションを実行して、 **内部** スタイルシートを使用して CSS を 1 回書き込み、複数の要素に適用します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-176">Complete the following actions to use an **Internal stylesheet** to write your CSS once so that it applies to multiple elements.</span></span>  

1.  <span data-ttu-id="9f54e-177">[ライブ] タブで、[連絡先] **を選択** して連絡先ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-177">In the live tab, choose **Contact** to navigate to the contact page.</span></span>  <span data-ttu-id="9f54e-178">ホームと連絡先の **フォントに** 注意 **してください**。</span><span class="sxs-lookup"><span data-stu-id="9f54e-178">Notice the font of **Home** and **Contact**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-internal1.msft.png" alt-text="[連絡先] ページ" lightbox="../media/beginners-css-internal1.msft.png":::
       <span data-ttu-id="9f54e-180">[連絡先] ページ</span><span class="sxs-lookup"><span data-stu-id="9f54e-180">The Contact page</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-181">エディター タブ **で、** を開きます `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="9f54e-181">In the **editor tab**, open `contact.html`.</span></span>  
1.  <span data-ttu-id="9f54e-182">に次のコードを追加します `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="9f54e-182">Add the following code to `contact.html`.</span></span>  <span data-ttu-id="9f54e-183">最初から終わる行は、追加 `<style>` `</style>` する必要がある行です。</span><span class="sxs-lookup"><span data-stu-id="9f54e-183">Remember, the lines starting with `<style>` and ending with `</style>` are what you need to add.</span></span>  <span data-ttu-id="9f54e-184">もう 1 つのコードはただそこにあるので、新しいコードをどこに置くのか分かっている。</span><span class="sxs-lookup"><span data-stu-id="9f54e-184">The other code is just there so you know where to put the new code.</span></span>  
    
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
    
1.  <span data-ttu-id="9f54e-185">[ライブ] タブに **戻る**。</span><span class="sxs-lookup"><span data-stu-id="9f54e-185">Go back to the **live tab**.</span></span>  
1.  <span data-ttu-id="9f54e-186">[連絡先 **] を** 選択して、連絡先ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="9f54e-186">Choose **Contact** to go back to the contact page.</span></span>  <span data-ttu-id="9f54e-187">ホームと連絡先**のフォント\*\*\*\*が**変更されました。</span><span class="sxs-lookup"><span data-stu-id="9f54e-187">The font of **Home** and **Contact** has changed.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-internal2.msft.png" alt-text="ホーム リンクと連絡先リンクのフォントが変更されました" lightbox="../media/beginners-css-internal2.msft.png":::
       <span data-ttu-id="9f54e-189">ホーム リンクと**連絡先リンクの\*\*\*\*フォント**が変更されました</span><span class="sxs-lookup"><span data-stu-id="9f54e-189">The font of the **Home** and **Contact** links has changed</span></span>  
    :::image-end:::  
    
### <a name="understand-internal-stylesheets"></a><span data-ttu-id="9f54e-190">内部スタイルシートについて</span><span class="sxs-lookup"><span data-stu-id="9f54e-190">Understand internal stylesheets</span></span>  

<span data-ttu-id="9f54e-191">内部スタイルシートは、セレクターを使用してスタイル **を適用します**。</span><span class="sxs-lookup"><span data-stu-id="9f54e-191">Internal stylesheets apply styles using **selectors**.</span></span>  <span data-ttu-id="9f54e-192">セレクターは、1 つ以上の HTML 要素に適用できるパターンです。</span><span class="sxs-lookup"><span data-stu-id="9f54e-192">Selectors are patterns that may apply to one or more HTML elements.</span></span>  <span data-ttu-id="9f54e-193">前のコード スニペットでは、次のスタイルが追加されました。</span><span class="sxs-lookup"><span data-stu-id="9f54e-193">The previous code snippet added the following style.</span></span>  

```html
<style>
    li a {
      font-family: 'Courier New', Courier, Serif;
    }
</style>
```  

`li a` <span data-ttu-id="9f54e-194">は、"要素を含む任意の `<li>` 要素" に変換されるセレクター `<a>` です。</span><span class="sxs-lookup"><span data-stu-id="9f54e-194">is a selector that translates to "any `<li>` element that contains an `<a>` element".</span></span>  <span data-ttu-id="9f54e-195">各タグ グループがパターンと\*\*\*\* 一致\*\*\*\* する場合、ブラウザーはホーム リンクと連絡先リンクのフォントを変更します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-195">The browser changes the font of the **Home** and **Contact** links because each of the tag groups match the pattern.</span></span>  

```html
<li><a href="/">Home</a></li>
<li><a href="/contact.html">Contact</a></li>
```  

`font-family: 'Courier New', Courier, serif` <span data-ttu-id="9f54e-196">は 宣言 **です**。</span><span class="sxs-lookup"><span data-stu-id="9f54e-196">is a **declaration**.</span></span>  <span data-ttu-id="9f54e-197">宣言は、次の 2 つの部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="9f54e-197">A declaration is made of following two parts.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="9f54e-198">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9f54e-198">property</span></span>**  
   :::column-end:::
   :::column span="1":::
      `font-family`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="9f54e-199">プロパティは、要素のスタイルを変更できる一般的な方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-199">The property describes a general way that you are able to change the style of the element.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="9f54e-200">value</span><span class="sxs-lookup"><span data-stu-id="9f54e-200">value</span></span>**  
   :::column-end:::
   :::column span="1":::
      `'Courier New', Courier, serif`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="9f54e-201">この値は、要素のスタイルがどのように変更されるのかを正確に示します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-201">The value describes exactly how the style of the element should change.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="9f54e-202">たとえば、ブラウザーに次の指示を与えます。"パターンに一致する要素のフォント `font-family: 'Courier New', Courier, serif` をに設定 `li a` します `'Courier New'` 。</span><span class="sxs-lookup"><span data-stu-id="9f54e-202">For example, `font-family: 'Courier New', Courier, serif` gives the browser the following instruction:  "Set the font of elements that match the pattern `li a` to `'Courier New'`.</span></span>  <span data-ttu-id="9f54e-203">そのフォントが使用できない場合は、 を使用します `Courier` 。</span><span class="sxs-lookup"><span data-stu-id="9f54e-203">If that font is not available, use `Courier`.</span></span>  <span data-ttu-id="9f54e-204">使用できない場合は、 `serif` を使用します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-204">If that is not available, use `serif`."</span></span>  

### <a name="add-multiple-selectors-to-a-ruleset"></a><span data-ttu-id="9f54e-205">ルール セットに複数のセレクターを追加する</span><span class="sxs-lookup"><span data-stu-id="9f54e-205">Add multiple selectors to a ruleset</span></span>  

<span data-ttu-id="9f54e-206">次のコード スニペットのような CSS コードのブロックをルール セットと **呼ぶ**。</span><span class="sxs-lookup"><span data-stu-id="9f54e-206">A block of CSS code like the following code snippet is called a **ruleset**.</span></span>  

```css
li a {
  font-family: 'Courier New', Courier, monospace;
}
```  

<span data-ttu-id="9f54e-207">コンマを使用して複数のセレクターをルール セットに追加するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-207">Complete the following actions to use commas to add multiple selectors to a ruleset.</span></span>  

1.  <span data-ttu-id="9f54e-208">エディター タブ **で、** を開きます `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="9f54e-208">In the **editor tab**, open `contact.html`.</span></span>  
1.  <span data-ttu-id="9f54e-209">After `li a` type `, h1` .</span><span class="sxs-lookup"><span data-stu-id="9f54e-209">After `li a` type `, h1`.</span></span>  
    
    ```html
    <style>
        li a, h1 {
          font-family: 'Courier New', Courier, Serif;
        }
    </style>
    ```  
    
    <span data-ttu-id="9f54e-210">前のコード スニペットは、パターンに一致する要素のスタイルを設定するのと同じ方法で要素のスタイルを設定 `<h1>` するブラウザーに指示します `li a` 。</span><span class="sxs-lookup"><span data-stu-id="9f54e-210">The previous code snippet tells the browser to style `<h1>` elements the same way that it styles elements that match the pattern `li a`.</span></span>  
    
1.  <span data-ttu-id="9f54e-211">[ライブ] タブ **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="9f54e-211">Navigate to the **live tab**.</span></span>  
1.  <span data-ttu-id="9f54e-212">[連絡先] **リンクを** 選択して、連絡先ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="9f54e-212">Choose the **Contact** link to go back to the contact page.</span></span>  <span data-ttu-id="9f54e-213">今、 **お問い合わせください!**</span><span class="sxs-lookup"><span data-stu-id="9f54e-213">Now, **Contact Me!**</span></span> <span data-ttu-id="9f54e-214">ナビゲーション リンクと同じフォントを持つ。</span><span class="sxs-lookup"><span data-stu-id="9f54e-214">has the same font as the navigation links.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-multiple1.msft.png" alt-text="テキスト [お問い合わせ]  ホームリンクと連絡先リンクと同じフォントが表示される" lightbox="../media/beginners-css-multiple1.msft.png":::
       <span data-ttu-id="9f54e-217">テキスト [ **お問い合わせ]**</span><span class="sxs-lookup"><span data-stu-id="9f54e-217">The text **Contact Me!**</span></span> <span data-ttu-id="9f54e-218">ホームリンクと連絡先リンクと同 **じ** フォント **が表示** される</span><span class="sxs-lookup"><span data-stu-id="9f54e-218">now has the same font as the **Home** and **Contact** links</span></span>  
    :::image-end:::  
    
## <a name="experiment-with-devtools"></a><span data-ttu-id="9f54e-219">DevTools の実験</span><span class="sxs-lookup"><span data-stu-id="9f54e-219">Experiment with DevTools</span></span>  

<span data-ttu-id="9f54e-220">Web 開発の専門家になるための旅を続ける中で、CSS は難しいと思うかもしれません。</span><span class="sxs-lookup"><span data-stu-id="9f54e-220">As you continue your journey to become an expert in web development, you may find that CSS is tricky.</span></span>  <span data-ttu-id="9f54e-221">一部の CSS を記述し、1 つの方法で表示すると予想できますが、ブラウザーは完全に異なる動作をします。</span><span class="sxs-lookup"><span data-stu-id="9f54e-221">You may write some CSS and expect it to display one way, but the browser does something completely different.</span></span>  <span data-ttu-id="9f54e-222">Microsoft Edge DevTools を使用すると、変更を簡単に試し、変更がページに与える影響をすぐに表示できます。</span><span class="sxs-lookup"><span data-stu-id="9f54e-222">Microsoft Edge DevTools makes it easy to experiment with changes and immediately display how the changes affect the page.</span></span>  

### <a name="add-a-declaration-to-an-existing-rulest-in-devtools"></a><span data-ttu-id="9f54e-223">DevTools の既存のルールに宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="9f54e-223">Add a declaration to an existing rulest in DevTools</span></span>  

<span data-ttu-id="9f54e-224">次のアクションを実行して、既存の要素のスタイルを反復処理し、既存のルール セットに宣言を追加します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-224">Complete the following actions to iterate on the style of an existing element, add a declaration to an existing ruleset.</span></span>  

1.  <span data-ttu-id="9f54e-225">[ホーム] リンク **をポイント** し、コンテキスト メニュー \(右クリック\) を開き、[検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9f54e-225">Hover on the **Home** link, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add1.msft.png" alt-text="[ホーム] リンクの検査" lightbox="../media/beginners-css-add1.msft.png":::
       <span data-ttu-id="9f54e-227">[ホーム] リンクの検査</span><span class="sxs-lookup"><span data-stu-id="9f54e-227">Inspect the Home link</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="9f54e-228">DevTools がページと一緒に開きます。</span><span class="sxs-lookup"><span data-stu-id="9f54e-228">DevTools opens up alongside your page.</span></span>  <span data-ttu-id="9f54e-229">[ホーム] リンクを表すコードは `<a href="/">Home</a>` 、DOM ツリーで青色で強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f54e-229">The code that represents the Home link, `<a href="/">Home</a>` is highlighted blue in the DOM Tree.</span></span>  <span data-ttu-id="9f54e-230">コード スニペットとプレビューは、HTML と DOM の使い始 [めからよく知っている必要があります][DevtoolsBeginnersHtml]。</span><span class="sxs-lookup"><span data-stu-id="9f54e-230">The code snippet and preview should be familiar from [Get Started with HTML and the DOM][DevtoolsBeginnersHtml].</span></span>  
    
    :::row:::
       :::column span="":::
          <span data-ttu-id="9f54e-231">次の図では、以前に追加した宣言が DOM ツリーの下の [スタイル] タブ `font-family: 'Courier New', Courier, serif` `contact.html` に表示されます。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9f54e-231">In the following figure, the `font-family: 'Courier New', Courier, serif` declaration that you previously added to `contact.html` is displayed in the **Styles** tab below the DOM Tree.</span></span>  
          
          :::image type="complex" source="../media/beginners-css-add2.msft.png" alt-text="[スタイル] タブは DOM ツリーの下にあります" lightbox="../media/beginners-css-add2.msft.png":::
             <span data-ttu-id="9f54e-233">[ **スタイル]** タブは DOM ツリーの下にあります</span><span class="sxs-lookup"><span data-stu-id="9f54e-233">The **Styles** tab is below the DOM Tree</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="9f54e-234">DevTools ウィンドウが広い場合、[スタイル] タブは DOM ツリーの右側にあります。</span><span class="sxs-lookup"><span data-stu-id="9f54e-234">If your DevTools window is wide, the Styles tab is to the right of the DOM Tree.</span></span>  
          
          :::image type="complex" source="../media/beginners-css-add3.msft.png" alt-text="[スタイル] タブは DOM ツリーの右側にあります。" lightbox="../media/beginners-css-add3.msft.png":::
             <span data-ttu-id="9f54e-236">[ **スタイル]** タブは DOM ツリーの右側にあります。</span><span class="sxs-lookup"><span data-stu-id="9f54e-236">The **Styles** tab is to the right of the DOM Tree</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="9f54e-237">新しい宣言を追加するには `font-family: 'Courier New', Courier, Serif` 、下の空の行を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-237">Choose the empty line below `font-family: 'Courier New', Courier, Serif` to add a new declaration.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add4.msft.png" alt-text="新しい宣言を追加する" lightbox="../media/beginners-css-add4.msft.png":::
       <span data-ttu-id="9f54e-239">新しい宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="9f54e-239">Add a new declaration</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-240">`color` を入力して、`Enter` を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-240">Type `color` and select `Enter`.</span></span>  <span data-ttu-id="9f54e-241">オートコンプリート UI は、入力時にオプションを提案します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-241">The autocomplete UI suggests options as you type.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add5.msft.png" alt-text="型の色" lightbox="../media/beginners-css-add5.msft.png":::
       <span data-ttu-id="9f54e-243">型</span><span class="sxs-lookup"><span data-stu-id="9f54e-243">Type</span></span> `color`  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-244">`magenta` を入力して、`Enter` を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-244">Type `magenta` and select `Enter`.</span></span>  <span data-ttu-id="9f54e-245">連絡先ページのすべてのテキストが magenta です。</span><span class="sxs-lookup"><span data-stu-id="9f54e-245">All of the text on the contact page is now magenta.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add6.msft.png" alt-text="タイプ magenta" lightbox="../media/beginners-css-add6.msft.png":::
       <span data-ttu-id="9f54e-247">型</span><span class="sxs-lookup"><span data-stu-id="9f54e-247">Type</span></span> `magenta`  
    :::image-end:::  
    
### <a name="edit-a-declaration-in-devtools"></a><span data-ttu-id="9f54e-248">DevTools で宣言を編集する</span><span class="sxs-lookup"><span data-stu-id="9f54e-248">Edit a declaration in DevTools</span></span>  

<span data-ttu-id="9f54e-249">DevTools で既存の宣言を編集するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-249">Complete the following actions to edit existing declarations in DevTools.</span></span>  

1.  <span data-ttu-id="9f54e-250">の横にあるマゼンタの四角形を選択します `magenta` 。</span><span class="sxs-lookup"><span data-stu-id="9f54e-250">Choose the magenta square next to `magenta`.</span></span>  <span data-ttu-id="9f54e-251">カラー ピッカーがポップアップします。</span><span class="sxs-lookup"><span data-stu-id="9f54e-251">A color picker pops up.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-edit1.msft.png" alt-text="カラー ピッカー" lightbox="../media/beginners-css-edit1.msft.png":::
       <span data-ttu-id="9f54e-253">カラー ピッカー</span><span class="sxs-lookup"><span data-stu-id="9f54e-253">The Color Picker</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-254">カラー ピッカーを使用して、フォント テキストを好きな色に変更します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-254">Use the color picker to change the font text to a color that you like.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-edit2.msft.png" alt-text="Color Picker を使用してフォントの色を紫に変更する" lightbox="../media/beginners-css-edit2.msft.png":::
       <span data-ttu-id="9f54e-256">Color Picker を使用してフォントの色を紫に変更する</span><span class="sxs-lookup"><span data-stu-id="9f54e-256">Change the font color to purple with the Color Picker</span></span>  
    :::image-end:::  
    
### <a name="add-a-new-ruleset-in-devtools"></a><span data-ttu-id="9f54e-257">DevTools に新しいルールセットを追加する</span><span class="sxs-lookup"><span data-stu-id="9f54e-257">Add a new ruleset in DevTools</span></span>  

<span data-ttu-id="9f54e-258">DevTools に新しいルールセットを追加するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-258">Complete the following actions to add new rulesets in DevTools.</span></span>  

1.  <span data-ttu-id="9f54e-259">.cls **の横にある** [新しいスタイル ルール \( 新しいスタイル ルール ![ ](../media/new-style-rule-icon.msft.png) **\) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9f54e-259">Choose **New Style Rule** \(![New Style Rule](../media/new-style-rule-icon.msft.png)\) which is next to **.cls**.</span></span>  <span data-ttu-id="9f54e-260">セレクターとして空のルール セット `a` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f54e-260">An empty ruleset appears with `a` as the selector.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule1.msft.png" alt-text="新しいルールを追加する" lightbox="../media/beginners-css-rule1.msft.png":::
       <span data-ttu-id="9f54e-262">新しいルールを追加する</span><span class="sxs-lookup"><span data-stu-id="9f54e-262">Add a new rule</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-263">に `a` 置き換える `a:hover` 。</span><span class="sxs-lookup"><span data-stu-id="9f54e-263">Replace `a` with `a:hover`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule2.msft.png" alt-text="a を a:hover に置き換える" lightbox="../media/beginners-css-rule2.msft.png":::
       <span data-ttu-id="9f54e-265">に置き `a` 換える</span><span class="sxs-lookup"><span data-stu-id="9f54e-265">Replace `a` with</span></span> `a:hover`  
    :::image-end:::  
    
    `:hover` <span data-ttu-id="9f54e-266">は **擬似 クラス です**。</span><span class="sxs-lookup"><span data-stu-id="9f54e-266">is a **pseudo-class**.</span></span>  <span data-ttu-id="9f54e-267">特殊な状態に入る可能性があるスタイル要素には、擬似クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-267">Use pseudo-classes for style elements that may enter special states.</span></span>  <span data-ttu-id="9f54e-268">たとえば、スタイル `a:hover` は要素の上にカーソルを置く場合にのみ有効 `<a>` になります。</span><span class="sxs-lookup"><span data-stu-id="9f54e-268">For example, the `a:hover` style only takes effect when you are hovering over an `<a>` element.</span></span>  
    
1.  <span data-ttu-id="9f54e-269">かっこの中から選択して、新しい宣言を追加します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-269">Choose between the brackets to add a new declaration.</span></span>  
1.  <span data-ttu-id="9f54e-270">宣言 `background-color` 名を入力し、を選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="9f54e-270">Type `background-color` for the declaration name and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule3.msft.png" alt-text="背景色を入力する" lightbox="../media/beginners-css-rule3.msft.png":::
       <span data-ttu-id="9f54e-272">型</span><span class="sxs-lookup"><span data-stu-id="9f54e-272">Type</span></span> `background-color`  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-273">宣言 `green` 値を入力し、を選択します `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="9f54e-273">Type `green` for the declaration value and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule4.msft.png" alt-text="緑と入力します" lightbox="../media/beginners-css-rule4.msft.png":::
       <span data-ttu-id="9f54e-275">型</span><span class="sxs-lookup"><span data-stu-id="9f54e-275">Type</span></span> `green`  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-276">[ホーム] リンクの上にマウス **ポインターを移動** します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-276">Hover your mouse over the **Home** link.</span></span>  <span data-ttu-id="9f54e-277">リンクの背景が緑色に変わります。</span><span class="sxs-lookup"><span data-stu-id="9f54e-277">The background of the link turns green.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule5.msft.png" alt-text="[ホーム] リンクにカーソルを合わせると、緑色の背景が表示されます。" lightbox="../media/beginners-css-rule5.msft.png":::
       <span data-ttu-id="9f54e-279">[ホーム] リンクにカーソルを合わせると、緑色の背景が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f54e-279">Hover on the Home link to reveal its green background</span></span>  
    :::image-end:::  
    
## <a name="re-use-styles-across-pages-with-external-stylesheets"></a><span data-ttu-id="9f54e-280">外部スタイルシートを使用してページ間でスタイルを再使用する</span><span class="sxs-lookup"><span data-stu-id="9f54e-280">Re-use styles across pages with external stylesheets</span></span>  

<span data-ttu-id="9f54e-281">前の手順では、次のコード スニペットを内部スタイルシートとして追加しました `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="9f54e-281">In a previous step, you added the following code snippet as an internal stylesheet to `contact.html`.</span></span>  

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

<span data-ttu-id="9f54e-282">同じスタイルにしたい `index.html` 場合は、</span><span class="sxs-lookup"><span data-stu-id="9f54e-282">What if you wanted to style `index.html` the same way?</span></span>  <span data-ttu-id="9f54e-283">スタイルを適用するページ数が多い場合は、どうしますか?</span><span class="sxs-lookup"><span data-stu-id="9f54e-283">What if you had a large number of pages to which you wanted to apply your styles?</span></span>  <span data-ttu-id="9f54e-284">内部スタイルシートをコピーして、サイト上のすべての Web ページに貼り付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f54e-284">You have to copy and paste the internal stylesheet into every single web page on your site.</span></span>  <span data-ttu-id="9f54e-285">次のアクションを実行して外部スタイルシート **を** 追加し、CSS を 1 回書き込み、複数のページに適用できます。</span><span class="sxs-lookup"><span data-stu-id="9f54e-285">Complete the following actions to add an **External stylesheet** to allow you to write your CSS once and apply it to multiple pages.</span></span>  

1.  <span data-ttu-id="9f54e-286">まず、ライブ タブを更新して、DevTools で行った変更を削除します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-286">First, refresh the live tab to remove the changes that you made in DevTools.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external1.msft.png" alt-text=" ページを更新すると、DevTools で行われた変更はなくなりました" lightbox="../media/beginners-css-external1.msft.png":::
        <span data-ttu-id="9f54e-288">ページを更新すると、DevTools で行われた変更はなくなりました</span><span class="sxs-lookup"><span data-stu-id="9f54e-288">After you refresh the page, the changes that were made in DevTools are gone</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-289">[エディター] タブに **戻り、開** きます `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="9f54e-289">Go back to the **editor tab** and open `contact.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external2.msft.png" alt-text="contact.html" lightbox="../media/beginners-css-external2.msft.png":::
       <span data-ttu-id="9f54e-291">contact.html</span><span class="sxs-lookup"><span data-stu-id="9f54e-291">contact.html</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-292">の間、および `<style>` `</style>` 、 を含むすべてを `<style>` 削除します `</style>` 。</span><span class="sxs-lookup"><span data-stu-id="9f54e-292">Delete everything between `<style>` and `</style>`, including `<style>` and `</style>`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external3.msft.png" alt-text="スタイル タグが削除されました" lightbox="../media/beginners-css-external3.msft.png":::
       <span data-ttu-id="9f54e-294">スタイル タグが削除されました</span><span class="sxs-lookup"><span data-stu-id="9f54e-294">The style tag has been removed</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-295">タグ `index.html` を開 `style="background-color: aliceblue;"` いて削除 `<nav>` します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-295">Open `index.html` and remove `style="background-color: aliceblue;"` from the `<nav>` tag.</span></span>  <span data-ttu-id="9f54e-296">これで、以前にサイトに追加した CSS のすべてが削除されました。</span><span class="sxs-lookup"><span data-stu-id="9f54e-296">You have now removed all of the CSS that you previously added to your site.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external4.msft.png" alt-text="インライン スタイルが nav 要素から削除されました" lightbox="../media/beginners-css-external4.msft.png":::
       <span data-ttu-id="9f54e-298">インライン スタイルが nav 要素から削除されました</span><span class="sxs-lookup"><span data-stu-id="9f54e-298">The inline style has been removed from the nav element</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-299">[新 **しいファイル] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9f54e-299">Choose **New File**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external5.msft.png" alt-text="新しいファイル ダイアログ" lightbox="../media/beginners-css-external5.msft.png":::
       <span data-ttu-id="9f54e-301">新しいファイル ダイアログ</span><span class="sxs-lookup"><span data-stu-id="9f54e-301">The new file dialog</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-302">に `cool-file.js` 置き換 `style.css` え、[ファイルの追加 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9f54e-302">Replace `cool-file.js` with `style.css` and choose **Add File**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external6.msft.png" alt-text="type style.css" lightbox="../media/beginners-css-external6.msft.png":::
       <span data-ttu-id="9f54e-304">型</span><span class="sxs-lookup"><span data-stu-id="9f54e-304">Type</span></span> `style.css`  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-305">次のコード スニペットをファイルに追加 `style.css` します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-305">Add the following code snippet to your `style.css` file.</span></span>  
    
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
    
    :::image type="complex" source="../media/beginners-css-external7.msft.png" alt-text="style.css にコードを追加する" lightbox="../media/beginners-css-external7.msft.png":::
       <span data-ttu-id="9f54e-307">コードを追加する</span><span class="sxs-lookup"><span data-stu-id="9f54e-307">Add code to</span></span> `style.css`  
    :::image-end:::  
    
    <span data-ttu-id="9f54e-308">外部スタイルシートが作成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f54e-308">Ensure that you have created an external stylesheet.</span></span> <span data-ttu-id="9f54e-309">HTML が存在することを認識しません。</span><span class="sxs-lookup"><span data-stu-id="9f54e-309">Your HTML is not aware that it exists.</span></span>  
    
1.  <span data-ttu-id="9f54e-310">を `index.html` 開きます。</span><span class="sxs-lookup"><span data-stu-id="9f54e-310">Open `index.html`.</span></span>  
1.  <span data-ttu-id="9f54e-311">`<link rel="stylesheet" href="style.css">`HTML に追加します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-311">Add `<link rel="stylesheet" href="style.css">` to your HTML.</span></span>  
    
    ```html
    <head>
        ...
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href="style.css">
    </head>
    ```  
    
    :::image type="complex" source="../media/beginners-css-external8.msft.png" alt-text="style.css へのリンク" lightbox="../media/beginners-css-external8.msft.png":::
       <span data-ttu-id="9f54e-313">リンク先</span><span class="sxs-lookup"><span data-stu-id="9f54e-313">Link to</span></span> `style.css`  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-314">ファイルを `contact.html` 開き、そこにリンクを追加します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-314">Open the `contact.html` file and add the link there.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external9.msft.png" alt-text="l の style.css へのリンクcontact.htmします。" lightbox="../media/beginners-css-external9.msft.png":::
       <span data-ttu-id="9f54e-316">への `style.css` リンク</span><span class="sxs-lookup"><span data-stu-id="9f54e-316">Link to `style.css` in</span></span> `contact.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-317">[ライブ] タブ **に移動します**。 ホーム ページには、最後のセクションと青いナビゲーション セクションのフォントが同じになります。</span><span class="sxs-lookup"><span data-stu-id="9f54e-317">Navigate to the **live tab**.  The home page now has the same font from the last section and a blue navigation section.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external10.msft.png" alt-text="ホーム ページ" lightbox="../media/beginners-css-external10.msft.png":::
       <span data-ttu-id="9f54e-319">ホーム ページ</span><span class="sxs-lookup"><span data-stu-id="9f54e-319">The home page</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-320">[連絡先] **リンクを** 選択して、連絡先ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-320">Choose the **Contact** link to navigate to the contact page.</span></span>  <span data-ttu-id="9f54e-321">連絡先ページの書式はホーム ページと同じです。</span><span class="sxs-lookup"><span data-stu-id="9f54e-321">The contact page has the same formatting as the home page.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external11.msft.png" alt-text="連絡先ページ" lightbox="../media/beginners-css-external11.msft.png":::
       <span data-ttu-id="9f54e-323">連絡先ページ</span><span class="sxs-lookup"><span data-stu-id="9f54e-323">The contact page</span></span>  
    :::image-end:::  
    
## <a name="use-a-css-framework"></a><span data-ttu-id="9f54e-324">CSS フレームワークの使用</span><span class="sxs-lookup"><span data-stu-id="9f54e-324">Use a CSS framework</span></span>  

<span data-ttu-id="9f54e-325">**CSS フレームワークは、** 他の開発者によって構築されたスタイルのコレクションで、魅力的な Web サイトを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="9f54e-325">**CSS frameworks** are collections of styles built by other developers that make it easier to create attractive web sites.</span></span>  <span data-ttu-id="9f54e-326">フレームワークは、自分でスタイルを定義する代わりに、ページ要素で使用できるスタイルのコレクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-326">Instead of defining styles yourself, a framework provides you a collection of styles that you are able to use on your page elements.</span></span>  

1.  <span data-ttu-id="9f54e-327">次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="9f54e-327">Copy the following code:</span></span>  
    
    ```html
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.1/css/bootstrap.min.css">
    ```  
    
1.  <span data-ttu-id="9f54e-328">編集タブを開き、コードをに貼り付けます `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="9f54e-328">Open the editing tab and paste the code into `contact.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-framework1.msft.png" alt-text="l のフレームワークへのリンクcontact.htmします。" lightbox="../media/beginners-css-framework1.msft.png":::
       <span data-ttu-id="9f54e-330">のフレームワークへのリンク</span><span class="sxs-lookup"><span data-stu-id="9f54e-330">Link to the framework in</span></span> `contact.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-331">ファイルを `index.html` 開き、そこにコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-331">Open the `index.html` file and add the code there.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-framework2.msft.png" alt-text="l のフレームワークへのリンクindex.htmします。" lightbox="../media/beginners-css-framework2.msft.png":::
       <span data-ttu-id="9f54e-333">のフレームワークへのリンク</span><span class="sxs-lookup"><span data-stu-id="9f54e-333">Link to the framework in</span></span> `index.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-334">[ライブ] タブに戻り、変更を表示します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-334">Go back to the live tab to view your changes.</span></span>  <span data-ttu-id="9f54e-335">要素の背景色と要素のフォントは同じですが、他の要素のフォント `<nav>` `<li>` `<a>` は変更されています。</span><span class="sxs-lookup"><span data-stu-id="9f54e-335">While the background color of the `<nav>` element and the font of the `<li>` and `<a>` elements are the same, the font of the other elements has changed.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-framework3.msft.png" alt-text="フレームワークのためにホーム ページのフォントの一部が変更されました" lightbox="../media/beginners-css-framework3.msft.png":::
       <span data-ttu-id="9f54e-337">フレームワークのためにホーム ページのフォントの一部が変更されました</span><span class="sxs-lookup"><span data-stu-id="9f54e-337">Some of the font on the home page changed because of the framework</span></span>  
    :::image-end:::  
    
### <a name="use-a-class"></a><span data-ttu-id="9f54e-338">クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="9f54e-338">Use a class</span></span>  

<span data-ttu-id="9f54e-339">最後のセクションでは、ブートストラップを Web ページに追加し、サイトの一部の要素のフォントを変更しました。</span><span class="sxs-lookup"><span data-stu-id="9f54e-339">In the last section, you added Bootstrap to your web pages, which changed the fonts of some of the elements on your site.</span></span>  <span data-ttu-id="9f54e-340">CSS フレームワークは、コードが非常に少ないページに大きな変更を加えるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9f54e-340">CSS frameworks help you make major changes to your page with very little code.</span></span>  <span data-ttu-id="9f54e-341">ヘッダーを変更するには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-341">Complete the following actions to change your header.</span></span>  

1.  <span data-ttu-id="9f54e-342">次のコード スニペットをコピーします。</span><span class="sxs-lookup"><span data-stu-id="9f54e-342">Copy the following code snippet.</span></span>  
    
    ```html
    class="jumbotron jumbotron-fluid"  
    ```  
    
1.  <span data-ttu-id="9f54e-343">前のコード スニペットをタグに `<header>` 追加します `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="9f54e-343">Add the previous code snippet to your `<header>` tag in `index.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-jumbotron1.msft.png" alt-text="l のクラスをindex.htmする" lightbox="../media/beginners-css-jumbotron1.msft.png":::
       <span data-ttu-id="9f54e-345">にクラスを追加する</span><span class="sxs-lookup"><span data-stu-id="9f54e-345">Add classes in</span></span> `index.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-346">でタグにコード `<header>` を追加します `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="9f54e-346">Add the code to your `<header>` tag in `contact.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-jumbotron2.msft.png" alt-text="l のクラスをcontact.htmする" lightbox="../media/beginners-css-jumbotron2.msft.png":::
       <span data-ttu-id="9f54e-348">にクラスを追加する</span><span class="sxs-lookup"><span data-stu-id="9f54e-348">Add classes in</span></span> `contact.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-349">[ライブ] タブで変更を表示します。 ヘッダーの周りに大きな灰色のボックスがあります。</span><span class="sxs-lookup"><span data-stu-id="9f54e-349">View your changes in the live tab.  There is a big, grey box around your header.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-jumbotron3.msft.png" alt-text="ヘッダーの周囲に大きな灰色のボックスが表示される" lightbox="../media/beginners-css-jumbotron3.msft.png":::
       <span data-ttu-id="9f54e-351">ヘッダーの周囲に大きな灰色のボックスが表示される</span><span class="sxs-lookup"><span data-stu-id="9f54e-351">The header now has a big, grey box around it</span></span>  
    :::image-end:::  
    
### <a name="understand-classes"></a><span data-ttu-id="9f54e-352">クラスについて</span><span class="sxs-lookup"><span data-stu-id="9f54e-352">Understand classes</span></span>  

<span data-ttu-id="9f54e-353">クラスを使用すると、スタイルのコレクションを任意の要素に割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="9f54e-353">Classes let you assign collections of styles to arbitrary elements.</span></span>  <span data-ttu-id="9f54e-354">属性をに設定した後、要素にいくつかのスタイルを適用するには、次の `<header>` コード `class` スニペットを使用します `jumbotron` 。</span><span class="sxs-lookup"><span data-stu-id="9f54e-354">Use the following code snippet to apply several styles to the `<header>` element after you set the `class` attribute to `jumbotron`.</span></span>  

```css
.jumbotron {
  padding: 2rem 1rem;
  margin-bottom: 2rem;
  background-color: #e9ecef;
  border-radius: .3rem;
}
```  

<span data-ttu-id="9f54e-355">クラスの利点の 1 つは、必要な要素にスタイルを適用できる方法です。</span><span class="sxs-lookup"><span data-stu-id="9f54e-355">One advantage of a class is that it lets you apply styles to whatever elements you want.</span></span>  <span data-ttu-id="9f54e-356">たとえば、一部の要素の背景色を紫に設定するとしますが、すべての要素 `<p>` には設定 `<p>` できないとします。</span><span class="sxs-lookup"><span data-stu-id="9f54e-356">For example, suppose you want to set the background color of some `<p>` elements to purple, but not all `<p>` elements.</span></span>  <span data-ttu-id="9f54e-357">クラスのスタイルを定義するには、次のコード スニペットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-357">Use the following code snippet to define the style in a class.</span></span>  

```css
.custom-background {
  background-color: purple;
}
```  

<span data-ttu-id="9f54e-358">次に、スタイルを設定する `<p>` 要素にのみクラスを適用します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-358">Next, apply the class to only the `<p>` elements that you want to style.</span></span>  

```html
<p>The text is not purple.</p>
<p class="custom-background">The text is purple.</p>
<p>The text is not purple.</p>
<p class="custom-background">The text is purple.</p>
```  

### <a name="align-elements"></a><span data-ttu-id="9f54e-359">要素を整列する</span><span class="sxs-lookup"><span data-stu-id="9f54e-359">Align elements</span></span>  

<span data-ttu-id="9f54e-360">次のアクションを実行して、要素を整列するクラスをブートストラップして提供します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-360">Complete the following actions to bootstrap and provide classes for aligning elements.</span></span>  

1.  <span data-ttu-id="9f54e-361">[エディター] タブに戻り、開きます `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="9f54e-361">Go back to the editor tab and open `index.html`.</span></span>  
1.  <span data-ttu-id="9f54e-362">タグ `class="container-fluid"` に追加 `<body>` します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-362">Add `class="container-fluid"` to your `<body>` tag.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align1.msft.png" alt-text="コンテナー流体クラスを追加する" lightbox="../media/beginners-css-align1.msft.png":::
       <span data-ttu-id="9f54e-364">クラスを追加 `container-fluid` する</span><span class="sxs-lookup"><span data-stu-id="9f54e-364">Add the `container-fluid` class</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-365">and 要素 `<nav>` を `<main>` 折り返します `<div class="row">` 。</span><span class="sxs-lookup"><span data-stu-id="9f54e-365">Wrap your `<nav>` and `<main>` elements in `<div class="row">`.</span></span>  <span data-ttu-id="9f54e-366">新しいタグを `</div>` 適切に `</main>` 閉じるには、必ず後に置く必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f54e-366">Make sure to put `</div>` after `</main>` in order to properly close the new tag.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align2.msft.png" alt-text="行の追加" lightbox="../media/beginners-css-align2.msft.png":::
       <span data-ttu-id="9f54e-368">行の追加</span><span class="sxs-lookup"><span data-stu-id="9f54e-368">Add a row</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-369">タグ `class="col-3"` と `<nav>` タグ `class="col-9"` に追加 `<main>` します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-369">Add `class="col-3"` to your `<nav>` tag and `class="col-9"` to your `<main>` tag.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align3.msft.png" alt-text="col-3 クラスと col-9 クラスを追加する" lightbox="../media/beginners-css-align3.msft.png":::
       <span data-ttu-id="9f54e-371">and クラス `col-3` を `col-9` 追加する</span><span class="sxs-lookup"><span data-stu-id="9f54e-371">Add the `col-3` and `col-9` classes</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9f54e-372">[ライブ] タブで変更を表示します。</span><span class="sxs-lookup"><span data-stu-id="9f54e-372">View your changes in the live tab.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align4.msft.png" alt-text="ナビゲーション コンテンツがメイン コンテンツの左側に表示される" lightbox="../media/beginners-css-align4.msft.png":::
       <span data-ttu-id="9f54e-374">ナビゲーション コンテンツがメイン コンテンツの左側に表示される</span><span class="sxs-lookup"><span data-stu-id="9f54e-374">The nav content is now to the left of the main content</span></span>  
    :::image-end:::  
    
## <a name="next-steps"></a><span data-ttu-id="9f54e-375">次の手順</span><span class="sxs-lookup"><span data-stu-id="9f54e-375">Next steps</span></span>  

<span data-ttu-id="9f54e-376">おめでとうございます。完了です。</span><span class="sxs-lookup"><span data-stu-id="9f54e-376">Congratulations, you are done.</span></span>  

*   <span data-ttu-id="9f54e-377">Web 開発を向上する最善の方法は、より多くのサイトを構築する方法です。</span><span class="sxs-lookup"><span data-stu-id="9f54e-377">The best way to get better at web development is to build more sites.</span></span>  <span data-ttu-id="9f54e-378">壊れる心配はありません。</span><span class="sxs-lookup"><span data-stu-id="9f54e-378">Do not worry about breaking stuff.</span></span>  <span data-ttu-id="9f54e-379">ただ、楽しみを持って、道に沿って可能な限り多くを学ぶ。</span><span class="sxs-lookup"><span data-stu-id="9f54e-379">Just have fun and learn as much as possible along the way.</span></span>  
*   <span data-ttu-id="9f54e-380">Web ページのスタイル設定の詳細については、「CSS の概要 [」に移動します][MDNCssFirstSteps]。</span><span class="sxs-lookup"><span data-stu-id="9f54e-380">To learn more about styling web pages, navigate to [Introduction to CSS][MDNCssFirstSteps].</span></span>  
*   <span data-ttu-id="9f54e-381">DevTools を使用してページの CSS を試す方法の詳細については、「CSS の表示と変更を開始する」に [移動します][DevtoolsCssIndex]。</span><span class="sxs-lookup"><span data-stu-id="9f54e-381">To learn more about how to use DevTools to experiment with the CSS of a page, navigate to [Get Started with Viewing and Changing CSS][DevtoolsCssIndex].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="9f54e-382">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="9f54e-382">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!--- links  --->  

[DevtoolsBeginnersHtml]: ./html.md "初級向け DevTools: HTML と DOM の使用を開始する | Microsoft Docs"  
[DevtoolsCssIndex]: ../css/index.md "CSS の表示と変更の開始|Microsoft Docs"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge Insider"  

[GlitchCookedAmphibianIndex]: https://glitch.com/edit/#!/cooked-amphibian?path=index.html "index.html - 調理された両生類|Glitch"  

[MDNCssFirstSteps]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS "CSS の最初の手順|MDN"  

> [!NOTE]
> <span data-ttu-id="9f54e-388">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="9f54e-388">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9f54e-389">元のページ [はここで見](https://developers.google.com/web/tools/chrome-devtools/beginners/css) つかり、キャ [サ][KatherineJackson] リン・ジャクソン \(Technical Writer Intern, Chrome DevTools\) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="9f54e-389">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/beginners/css) and is authored by [Katherine Jackson][KatherineJackson] \(Technical Writer Intern, Chrome DevTools\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="9f54e-391">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="9f54e-391">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
