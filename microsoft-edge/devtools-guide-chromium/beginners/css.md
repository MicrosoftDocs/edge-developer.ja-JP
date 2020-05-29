---
title: 初心者向けの DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 0064f0427b6bd5689e888cccfe2c650492898bb2
ms.sourcegitcommit: 8bfa239274e7a4856b961b9cf163b08d96463c10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "10581595"
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

# <span data-ttu-id="7b390-103">初心者向けの DevTools: CSS の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="7b390-103">DevTools For Beginners: Get Started with CSS</span></span>   

<span data-ttu-id="7b390-104">このチュートリアルでは、CSS を使用して web ページのスタイルを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7b390-104">In this tutorial, you learn how to use CSS to style a web page.</span></span>  <span data-ttu-id="7b390-105">また、Microsoft Edge DevTools を使用して CSS の変更を試す方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="7b390-105">You also learn how to use Microsoft Edge DevTools to experiment with CSS changes.</span></span>  

<span data-ttu-id="7b390-106">これは、web 開発と Microsoft Edge DevTools の基礎について説明する一連のチュートリアルの2番目のチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="7b390-106">This is the second tutorial in a series of tutorials that teaches you the basics of web development and Microsoft Edge DevTools.</span></span>  <span data-ttu-id="7b390-107">実際に自分の web サイトを構築することで、実践的なエクスペリエンスを実現できます。</span><span class="sxs-lookup"><span data-stu-id="7b390-107">You gain hands-on experience by actually building your own website.</span></span>  <span data-ttu-id="7b390-108">この操作を行う前に、最初のチュートリアルを完了する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7b390-108">You don't have to complete the first tutorial before doing this one.</span></span>  <span data-ttu-id="7b390-109">ここから開始できます。</span><span class="sxs-lookup"><span data-stu-id="7b390-109">You can start here.</span></span>  <span data-ttu-id="7b390-110">[コードを設定](#set-up-your-code)すると、セットアップ方法が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b390-110">[Set up your code](#set-up-your-code) shows you how to get set up.</span></span>  

> [!NOTE]
> <span data-ttu-id="7b390-111">このチュートリアルは、基本的な初心者向けに設計されており、 **web 開発の基礎**と、開発者向けの基本的なツールを使用した CSS の基本的な使い方に重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="7b390-111">This tutorial is designed for absolute beginners and focuses on both the **fundamentals of web development** and the basics of using DevTools to experiment with CSS.</span></span>  <span data-ttu-id="7b390-112">開発ツールにのみ重点を置いたチュートリアルが必要な場合は、「 [CSS の表示と変更の概要][DevtoolsCssIndex]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b390-112">If you want a tutorial that only focuses on DevTools, see [Get Started with Viewing and Changing CSS][DevtoolsCssIndex].</span></span>  

<span data-ttu-id="7b390-113">現在、サイトは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b390-113">Currently your site looks like this:</span></span>  

> ##### <span data-ttu-id="7b390-114">図 1</span><span class="sxs-lookup"><span data-stu-id="7b390-114">Figure 1</span></span>  
> <span data-ttu-id="7b390-115">現在のサイトの外観</span><span class="sxs-lookup"><span data-stu-id="7b390-115">What your site currently looks like</span></span>  
> ![現在のサイトの外観][ImageCssIntro1]  

<span data-ttu-id="7b390-117">チュートリアルを完了すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="7b390-117">After completing the tutorial, it will look like this:</span></span>  

> ##### <span data-ttu-id="7b390-118">図 2</span><span class="sxs-lookup"><span data-stu-id="7b390-118">Figure 2</span></span>  
> <span data-ttu-id="7b390-119">チュートリアルの最後にサイトがどのように表示されるか</span><span class="sxs-lookup"><span data-stu-id="7b390-119">What your site will look like at the end of the tutorial</span></span>  
> ![チュートリアルの最後にサイトがどのように表示されるか][ImageCssIntro2]  

## <span data-ttu-id="7b390-121">目標</span><span class="sxs-lookup"><span data-stu-id="7b390-121">Goals</span></span>   

<span data-ttu-id="7b390-122">このチュートリアルを終了すると、次のことがわかります。</span><span class="sxs-lookup"><span data-stu-id="7b390-122">By the end of this tutorial, you will understand:</span></span>  

*   <span data-ttu-id="7b390-123">CSS を使用して web ページのスタイルを適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7b390-123">How to use CSS to style a web page.</span></span>  
*   <span data-ttu-id="7b390-124">Microsoft Edge DevTools を使って CSS を試す方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="7b390-124">How to use Microsoft Edge DevTools to experiment with CSS.</span></span>  
*   <span data-ttu-id="7b390-125">CSS と CSS フレームワークの違い。</span><span class="sxs-lookup"><span data-stu-id="7b390-125">The difference between CSS and CSS frameworks.</span></span>  

<span data-ttu-id="7b390-126">実際の web サイトも用意されています。</span><span class="sxs-lookup"><span data-stu-id="7b390-126">You'll also have a real website!</span></span>  

## <span data-ttu-id="7b390-127">前提条件</span><span class="sxs-lookup"><span data-stu-id="7b390-127">Prerequisites</span></span>   

<span data-ttu-id="7b390-128">このチュートリアルを実行する前に、次の前提条件を完了してください。</span><span class="sxs-lookup"><span data-stu-id="7b390-128">Before attempting this tutorial, complete the following prerequisites:</span></span>  

*   <span data-ttu-id="7b390-129">「 [Html と dom の概要][DevToolsBeginnersHtml]」をご覧になるか、このチュートリアルで説明していることと同じように HTML と dom を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7b390-129">Complete [Get Started with HTML and the DOM][DevToolsBeginnersHtml] or make sure that you have an understanding of HTML and the DOM similar to what's taught in that tutorial.</span></span>  
*   <span data-ttu-id="7b390-130">[Microsoft Edge][MicrosoftEdgeInsider] web ブラウザーをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="7b390-130">Download the [Microsoft Edge][MicrosoftEdgeInsider] web browser.</span></span>  <span data-ttu-id="7b390-131">このチュートリアルでは、microsoft edge DevTools と呼ばれる web 開発ツールのセットを使用して、Microsoft Edge に組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="7b390-131">This tutorial uses a set of web development tools, called the Microsoft Edge DevTools, that are built into Microsoft Edge.</span></span>  

## <span data-ttu-id="7b390-132">コードを設定する</span><span class="sxs-lookup"><span data-stu-id="7b390-132">Set up your code</span></span>   

<span data-ttu-id="7b390-133">サイトの作成を開始するには、コードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b390-133">In order to start creating your site, you need to set up your code:</span></span>  

1.  **<span data-ttu-id="7b390-134">このシリーズの最初のチュートリアルを既に完了している場合は、このセクションをスキップしてください。</span><span class="sxs-lookup"><span data-stu-id="7b390-134">If you have already completed the first tutorial in this series, skip this section!</span></span>  <span data-ttu-id="7b390-135">「 [HTML と DOM の使用を開始][DevToolsBeginnersHtml]する」のチュートリアルで説明したコードの使用を続けます。</span><span class="sxs-lookup"><span data-stu-id="7b390-135">Continue using your code from the last tutorial, [Get Started with HTML and the DOM][DevToolsBeginnersHtml].</span></span>**  
1.  <span data-ttu-id="7b390-136">[ソースコード][GlitchCookedAmphibianIndex]を開きます。</span><span class="sxs-lookup"><span data-stu-id="7b390-136">Open the [source code][GlitchCookedAmphibianIndex].</span></span>  <span data-ttu-id="7b390-137">ブラウザーのこのタブは、[**編集] タブ**と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="7b390-137">This tab of your browser will be called the **editing tab**.</span></span>  
    
    > ##### <span data-ttu-id="7b390-138">図 3</span><span class="sxs-lookup"><span data-stu-id="7b390-138">Figure 3</span></span>  
    > <span data-ttu-id="7b390-139">[編集] タブ</span><span class="sxs-lookup"><span data-stu-id="7b390-139">The editing tab</span></span>  
    > ![[編集] タブ][ImageCssSetup1]  
    
1.  <span data-ttu-id="7b390-141">[**クック-水陸両用] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="7b390-141">Click **cooked-amphibian**.</span></span>  <span data-ttu-id="7b390-142">メニューがポップアップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b390-142">A menu pops up.</span></span>  
    
    > ##### <span data-ttu-id="7b390-143">図 4</span><span class="sxs-lookup"><span data-stu-id="7b390-143">Figure 4</span></span>  
    > <span data-ttu-id="7b390-144">[プロジェクトのオプション] メニュー</span><span class="sxs-lookup"><span data-stu-id="7b390-144">The Project Options menu</span></span>  
    > ![[プロジェクトのオプション] メニュー][ImageCssSetup2]  

1.  <span data-ttu-id="7b390-146">[ **Remix Project**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b390-146">Click **Remix Project**.</span></span>  <span data-ttu-id="7b390-147">エラー編集可能なプロジェクトのコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="7b390-147">Glitch creates a copy of the project that you can edit.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="7b390-148">エラー新しいプロジェクトに対してランダムな名前を生成します。</span><span class="sxs-lookup"><span data-stu-id="7b390-148">Glitch generates a random name for the new project.</span></span>  
    
1.  <span data-ttu-id="7b390-149">[**表示**] をクリックして、**新しいウィンドウで**を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b390-149">Click **Show** and select **In a New Window**.</span></span>  <span data-ttu-id="7b390-150">サイトのライブビューで別のタブが開きます。</span><span class="sxs-lookup"><span data-stu-id="7b390-150">Another tab opens with a live view of your site.</span></span>  <span data-ttu-id="7b390-151">ブラウザのこのタブは、「**ライブ」タブ**と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="7b390-151">This tab of your browser will be called the **live tab**.</span></span>  
    
    > ##### <span data-ttu-id="7b390-152">図 5</span><span class="sxs-lookup"><span data-stu-id="7b390-152">Figure 5</span></span>  
    > <span data-ttu-id="7b390-153">[ライブ] タブ</span><span class="sxs-lookup"><span data-stu-id="7b390-153">The live tab</span></span>  
    > ![[ライブ] タブ][ImageCssSetup3]  

## <span data-ttu-id="7b390-155">CSS について</span><span class="sxs-lookup"><span data-stu-id="7b390-155">Understand CSS</span></span>   

<span data-ttu-id="7b390-156">**CSS**は、web ページのレイアウトとスタイルを決定するコンピューターの言語です。</span><span class="sxs-lookup"><span data-stu-id="7b390-156">**CSS** is a computer language that determines the layout and styling of web pages.</span></span>  <span data-ttu-id="7b390-157">たとえば、次のように罫線が付いた段落を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7b390-157">For example, here is a paragraph with a border:</span></span>  

> ##### <span data-ttu-id="7b390-158">図 6</span><span class="sxs-lookup"><span data-stu-id="7b390-158">Figure 6</span></span>  
> <span data-ttu-id="7b390-159">CSS でスタイルが設定されています</span><span class="sxs-lookup"><span data-stu-id="7b390-159">This has been styled with CSS</span></span>  
> ![CSS でスタイルが設定されています][ImageCssStyled]  

<span data-ttu-id="7b390-161">この段落を作成するために使用される HTML と CSS のコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7b390-161">Here is the HTML and CSS code used to create that paragraph:</span></span>  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

`style="border: 1px dashed red; padding: 5px;"` <span data-ttu-id="7b390-162">おそらく、新しくなったようです。</span><span class="sxs-lookup"><span data-stu-id="7b390-162">probably looks new to you.</span></span>  <span data-ttu-id="7b390-163">その他の方法については、こちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7b390-163">The rest should look familiar.</span></span>  <span data-ttu-id="7b390-164">表示されない場合は、このチュートリアルを実行する前に、「 [HTML と DOM での作業を開始][DevToolsBeginnersHtml]する」を完了してください。</span><span class="sxs-lookup"><span data-stu-id="7b390-164">If not, complete [Get Started with HTML and the DOM][DevToolsBeginnersHtml] before attempting this tutorial.</span></span>  

## <span data-ttu-id="7b390-165">インラインスタイルを追加する</span><span class="sxs-lookup"><span data-stu-id="7b390-165">Add inline styles</span></span>   

<span data-ttu-id="7b390-166">1つの要素にスタイルを適用する場合は、**インラインスタイル**を使います。</span><span class="sxs-lookup"><span data-stu-id="7b390-166">Use **inline styles** when you want to apply styles to a single element.</span></span>  <span data-ttu-id="7b390-167">今すぐお試しください:</span><span class="sxs-lookup"><span data-stu-id="7b390-167">Try it now:</span></span>  

1.  <span data-ttu-id="7b390-168">[編集] タブに戻り、[開く] をクリックし `index.html` ます。</span><span class="sxs-lookup"><span data-stu-id="7b390-168">Go back to the editing tab and open `index.html`.</span></span>  
    
    > ##### <span data-ttu-id="7b390-169">図 7</span><span class="sxs-lookup"><span data-stu-id="7b390-169">Figure 7</span></span>  
    > `index.html`  
    > ![index.html][ImageCssInline1]  

1.  <span data-ttu-id="7b390-171">`style="background-color: aliceblue;"`にを追加 `<nav>` します。</span><span class="sxs-lookup"><span data-stu-id="7b390-171">Add `style="background-color: aliceblue;"` to your `<nav>`.</span></span>  <span data-ttu-id="7b390-172">以下のコードブロックでは、コードの4行目が変更する必要があるものです。</span><span class="sxs-lookup"><span data-stu-id="7b390-172">In the code block below, the fourth line of code is the one you need to change.</span></span>  <span data-ttu-id="7b390-173">残りの部分は、新しいコードが適切な場所に配置されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7b390-173">The rest is just there so you can be sure that you're putting the new code in the right place.</span></span>  
    
    ```html
    ...
        ...
            <header>
                <p>Welcome to my site!</p>
            </header>
            <nav style="background-color: aliceblue;">
                <ul>
                    <li><a href="/">Home</a></li>
                    ...
                ...
            ...
        ...
    ...
    ```  

1.  <span data-ttu-id="7b390-174">[**ライブ] タブ**に移動して変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="7b390-174">Go to the **live tab** to see the changes!</span></span>  <span data-ttu-id="7b390-175">セクションの背景 `<nav>` が青色になります。</span><span class="sxs-lookup"><span data-stu-id="7b390-175">The background of the `<nav>` section is now blue.</span></span>  
    
    > ##### <span data-ttu-id="7b390-176">図 8</span><span class="sxs-lookup"><span data-stu-id="7b390-176">Figure 8</span></span>  
    > <span data-ttu-id="7b390-177">ホームと連絡先のリンクの背景色が青になりました</span><span class="sxs-lookup"><span data-stu-id="7b390-177">The background color behind the Home and Contact links is now blue</span></span>  
    > ![ホームと連絡先のリンクの背景色が青になりました][ImageCssInline2]  

## <span data-ttu-id="7b390-179">内部のスタイルシートを使用して、1つのページでスタイルを再利用する</span><span class="sxs-lookup"><span data-stu-id="7b390-179">Re-use styles on a single page with internal stylesheets</span></span>   

<span data-ttu-id="7b390-180">以前は、次のような1つのタグにスタイルを適用したインラインスタイルが表示されていました `<p>` 。</span><span class="sxs-lookup"><span data-stu-id="7b390-180">Earlier, you saw an inline style that applied a style to a single `<p>` tag like this:</span></span>  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

<span data-ttu-id="7b390-181">`<p>`Web ページ上のすべての要素に同じようなスタイルを適用する必要がある場合はどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="7b390-181">What if you wanted all of the `<p>` elements on your webpage to be styled the same way?</span></span>  <span data-ttu-id="7b390-182">サイトのすべてのタグにコードをコピーして貼り付ける必要があり `<p>` ます。</span><span class="sxs-lookup"><span data-stu-id="7b390-182">You'd have to copy and paste the code into every single `<p>` tag on your site.</span></span>  <span data-ttu-id="7b390-183">これは多くの時間と労力を備えています。</span><span class="sxs-lookup"><span data-stu-id="7b390-183">That's a lot of time and effort.</span></span>  <span data-ttu-id="7b390-184">編集を行う必要がある場合は、すべてのタグをもう一度変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b390-184">And, if you needed to make an edit, you'd have to change every tag again.</span></span>  <span data-ttu-id="7b390-185">**内部のスタイルシート**を使用すると、複数の要素に適用されるように CSS を1回作成できます。</span><span class="sxs-lookup"><span data-stu-id="7b390-185">**Internal stylesheets** allow you to write your CSS once so that it applies to multiple elements.</span></span>  <span data-ttu-id="7b390-186">今すぐお試しください:</span><span class="sxs-lookup"><span data-stu-id="7b390-186">Try it now:</span></span>  

1.  <span data-ttu-id="7b390-187">「ライブ」タブで「**コンタクト**」をクリックして、コンタクトページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7b390-187">In the live tab, click **Contact** to go to the contact page.</span></span>  <span data-ttu-id="7b390-188">[**ホーム**] と [**連絡先**] のフォントを確認します。</span><span class="sxs-lookup"><span data-stu-id="7b390-188">Notice the font of **Home** and **Contact**.</span></span>  
    
    > ##### <span data-ttu-id="7b390-189">図 9</span><span class="sxs-lookup"><span data-stu-id="7b390-189">Figure 9</span></span>  
    > <span data-ttu-id="7b390-190">[連絡先] ページ</span><span class="sxs-lookup"><span data-stu-id="7b390-190">The Contact page</span></span>  
    > ![[連絡先] ページ][ImageCssInternal1]  

1.  <span data-ttu-id="7b390-192">[**エディター] タブ**で、に移動 `contact.html` します。</span><span class="sxs-lookup"><span data-stu-id="7b390-192">In the **editor tab**, go to `contact.html`.</span></span>  
1.  <span data-ttu-id="7b390-193">次のコードをに追加 `contact.html` します。</span><span class="sxs-lookup"><span data-stu-id="7b390-193">Add the following code to `contact.html`.</span></span>  <span data-ttu-id="7b390-194">追加する必要があるのは、[で始まる] `<style>` と [末尾] の行 `</style>` だけです。</span><span class="sxs-lookup"><span data-stu-id="7b390-194">Remember, the lines starting with `<style>` and ending with `</style>` are what you need to add.</span></span>  <span data-ttu-id="7b390-195">その他のコードは、新しいコードを配置する場所を知っているだけです。</span><span class="sxs-lookup"><span data-stu-id="7b390-195">The other code is just there so you know where to put the new code.</span></span>  
    
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
    
1.  <span data-ttu-id="7b390-196">[**ライブ] タブ**に戻ります。</span><span class="sxs-lookup"><span data-stu-id="7b390-196">Go back to the **live tab**.</span></span>  
1.  <span data-ttu-id="7b390-197">[**連絡先**] をクリックして、連絡先ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="7b390-197">Click **Contact** to go back to the contact page.</span></span>  <span data-ttu-id="7b390-198">[**ホーム**] と [**連絡先**] のフォントが変更されました。</span><span class="sxs-lookup"><span data-stu-id="7b390-198">The font of **Home** and **Contact** has changed.</span></span>  
    
    > ##### <span data-ttu-id="7b390-199">図 10</span><span class="sxs-lookup"><span data-stu-id="7b390-199">Figure 10</span></span>  
    > <span data-ttu-id="7b390-200">自宅と連絡先のリンクのフォントが変更されました</span><span class="sxs-lookup"><span data-stu-id="7b390-200">The font of the Home and Contact links has changed</span></span>  
    > ![自宅と連絡先のリンクのフォントが変更されました][ImageCssInternal2]  
    
### <span data-ttu-id="7b390-202">内部のスタイルシートについて</span><span class="sxs-lookup"><span data-stu-id="7b390-202">Understand internal stylesheets</span></span>   

<span data-ttu-id="7b390-203">内部スタイルシートは**セレクター**を使ってスタイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="7b390-203">Internal stylesheets apply styles using **selectors**.</span></span>  <span data-ttu-id="7b390-204">セレクターは、1つ以上の HTML 要素に適用される可能性があるパターンです。</span><span class="sxs-lookup"><span data-stu-id="7b390-204">Selectors are patterns that may apply to one or more HTML elements.</span></span>  <span data-ttu-id="7b390-205">たとえば、上記のコードでは、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="7b390-205">For example, in the previous code:</span></span>  

```html
...
    ...
        ...
        <style>
            li a {
              font-family: 'Courier New', Courier, Serif;
            }
        </style>
        ...
    ...
...
```  

`li a` <span data-ttu-id="7b390-206">は、"any を含む any" に変換するセレクターです `<li>` `<a>` 。</span><span class="sxs-lookup"><span data-stu-id="7b390-206">is a selector that translates to "any `<li>` that contains an `<a>`".</span></span>  <span data-ttu-id="7b390-207">[**ホーム**] と [**連絡先**] のリンクは、このパターンと一致するため、ブラウザーによって変更されます。</span><span class="sxs-lookup"><span data-stu-id="7b390-207">The browser changes the font of the **Home** and **Contact** links because they match this pattern.</span></span>  

```html
...
    ...
        ...
            ...
                <li><a href="/">Home</a></li>
                <li><a href="/contact.html">Contact</a></li>
                ...
            ...
        ...
    ...
...
```  

`font-family: 'Courier New', Courier, serif` <span data-ttu-id="7b390-208">は**宣言**です。</span><span class="sxs-lookup"><span data-stu-id="7b390-208">is a **declaration**.</span></span>  <span data-ttu-id="7b390-209">宣言は、**プロパティ**と**値**の2つの部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="7b390-209">A declaration is made of two parts: a **property** and a **value**.</span></span>  `font-family` <span data-ttu-id="7b390-210">はプロパティであり、 `'Courier New', Courier, serif` そのプロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="7b390-210">is the property, and `'Courier New', Courier, serif` is the value of that property.</span></span>  <span data-ttu-id="7b390-211">このプロパティでは、要素のスタイルを変更する一般的な方法について説明します。値は、どのように変化するかを示します。</span><span class="sxs-lookup"><span data-stu-id="7b390-211">The property describes a general way that you can change the element's style, and the value says how exactly it should change.</span></span>  <span data-ttu-id="7b390-212">たとえば、次のような指示が表示されます。 `font-family: 'Courier New', Courier, serif` "パターンと一致する要素のフォント `li a` を設定 `'Courier New'` します。</span><span class="sxs-lookup"><span data-stu-id="7b390-212">For example, `font-family: 'Courier New', Courier, serif` gives the browser this instruction:  "Set the font of elements that match the pattern `li a` to `'Courier New'`.</span></span>  <span data-ttu-id="7b390-213">そのフォントが利用できない場合は、を使用 `Courier` します。</span><span class="sxs-lookup"><span data-stu-id="7b390-213">If that font isn't available, use `Courier`.</span></span>  <span data-ttu-id="7b390-214">利用できない場合は、 `serif` 「」を使用してください。</span><span class="sxs-lookup"><span data-stu-id="7b390-214">If that isn't available, use `serif`."</span></span>  

### <span data-ttu-id="7b390-215">複数のセレクターをルールセットに追加する</span><span class="sxs-lookup"><span data-stu-id="7b390-215">Add multiple selectors to a ruleset</span></span>   

<span data-ttu-id="7b390-216">以下に示すような CSS コードのブロックは、**ルールセット**と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="7b390-216">A block of CSS code like what you see below is called a **ruleset**.</span></span>  

```css
li a {
  font-family: 'Courier New', Courier, monospace;
}
```  

<span data-ttu-id="7b390-217">コンマを使用して、複数のセレクターをルールセットに追加します。</span><span class="sxs-lookup"><span data-stu-id="7b390-217">Use commas to add multiple selectors to a ruleset.</span></span>  <span data-ttu-id="7b390-218">今すぐお試しください:</span><span class="sxs-lookup"><span data-stu-id="7b390-218">Try it now:</span></span>  

1.  <span data-ttu-id="7b390-219">[**エディター] タブ**で、を開き `contact.html` ます。</span><span class="sxs-lookup"><span data-stu-id="7b390-219">In the **editor tab**, open `contact.html`.</span></span>  
1.  <span data-ttu-id="7b390-220">`li a`種類 `, h1` の後。</span><span class="sxs-lookup"><span data-stu-id="7b390-220">After `li a` type `, h1`.</span></span>  

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

    <span data-ttu-id="7b390-221">これにより、ブラウザーは、 `<h1>` パターンと一致する要素のスタイルを適用する場合と同じ方法で要素のスタイルを適用し `li a` ます。</span><span class="sxs-lookup"><span data-stu-id="7b390-221">This tells the browser to style `<h1>` elements the same way that it styles elements that match the pattern `li a`.</span></span>  
    
1.  <span data-ttu-id="7b390-222">[**ライブ] タブ**に移動します。</span><span class="sxs-lookup"><span data-stu-id="7b390-222">Go to the **live tab**.</span></span>  
1.  <span data-ttu-id="7b390-223">**連絡先のリンクを**クリックして、連絡先ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="7b390-223">Click the **Contact** link to go back to the contact page.</span></span>  <span data-ttu-id="7b390-224">今すぐ**連絡してください。**</span><span class="sxs-lookup"><span data-stu-id="7b390-224">Now, **Contact Me!**</span></span> <span data-ttu-id="7b390-225">ナビゲーションリンクと同じフォントに設定されています。</span><span class="sxs-lookup"><span data-stu-id="7b390-225">has the same font as the navigation links.</span></span>  
    
    > ##### <span data-ttu-id="7b390-226">図 11</span><span class="sxs-lookup"><span data-stu-id="7b390-226">Figure 11</span></span>  
    > <span data-ttu-id="7b390-227">「連絡してください」というテキスト</span><span class="sxs-lookup"><span data-stu-id="7b390-227">The text 'Contact Me!'</span></span> <span data-ttu-id="7b390-228">自宅と連絡先のリンクと同じフォントになりました</span><span class="sxs-lookup"><span data-stu-id="7b390-228">now has the same font as the Home and Contact links</span></span>  
    > ![「連絡」というテキストが表示されます。][ImageCssMultiple1]  

## <span data-ttu-id="7b390-231">DevTools を使って実験する</span><span class="sxs-lookup"><span data-stu-id="7b390-231">Experiment with DevTools</span></span>   

<span data-ttu-id="7b390-232">引き続きマスタ web 開発に進んでいくと、CSS が複雑になる可能性があることがわかります。</span><span class="sxs-lookup"><span data-stu-id="7b390-232">As you continue your journey to master web development, you'll find that CSS can be tricky.</span></span>  <span data-ttu-id="7b390-233">CSS を作成し、1つの方法で表示することを想定していますが、ブラウザーではまったく異なるものがあります。</span><span class="sxs-lookup"><span data-stu-id="7b390-233">You'll write some CSS and expect it to display one way, but the browser does something completely different.</span></span>  <span data-ttu-id="7b390-234">Microsoft Edge DevTools を使うと、簡単に変更を試すことができ、それらの変更がページにどのように影響するかをすぐに確認できます。</span><span class="sxs-lookup"><span data-stu-id="7b390-234">Microsoft Edge DevTools makes it easy to experiment with changes and immediately see how those changes affect the page.</span></span>  

### <span data-ttu-id="7b390-235">DevTools で既存の rulest に宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="7b390-235">Add a declaration to an existing rulest in DevTools</span></span>   

<span data-ttu-id="7b390-236">既存の要素のスタイルに対して反復処理を行う場合は、既存のルールセットに宣言を追加します。</span><span class="sxs-lookup"><span data-stu-id="7b390-236">When you want to iterate on the style of an existing element, add a declaration to an existing ruleset.</span></span>  <span data-ttu-id="7b390-237">今すぐお試しください:</span><span class="sxs-lookup"><span data-stu-id="7b390-237">Try it now:</span></span>  

1.  <span data-ttu-id="7b390-238">[**ホーム**] リンクを右クリックし、[**検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b390-238">Right-click the **Home** link and select **Inspect**.</span></span>  
    
    > ##### <span data-ttu-id="7b390-239">図 12</span><span class="sxs-lookup"><span data-stu-id="7b390-239">Figure 12</span></span>  
    > <span data-ttu-id="7b390-240">[ホーム] リンクを調べる</span><span class="sxs-lookup"><span data-stu-id="7b390-240">Inspecting the Home link</span></span>  
    > ![[ホーム] リンクを調べる][ImageCssAdd1]  
    
    <span data-ttu-id="7b390-242">DevTools はページの横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b390-242">DevTools opens up alongside your page.</span></span>  <span data-ttu-id="7b390-243">[ホーム] リンクを表すコード `<a href="/">Home</a>` は、DOM ツリーで青色で強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="7b390-243">The code that represents the Home link, `<a href="/">Home</a>` is highlighted blue in the DOM Tree.</span></span>  <span data-ttu-id="7b390-244">これは[、「HTML と DOM の使用を開始][DevToolsBeginnersHtml]する」に精通している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b390-244">This should be familiar from [Get Started with HTML and the DOM][DevToolsBeginnersHtml].</span></span>  <span data-ttu-id="7b390-245">DOM ツリーの下にある [**スタイル**] タブには、 `font-family: 'Courier New', Courier, serif` 前に追加した宣言が表示され `contact.html` ます。</span><span class="sxs-lookup"><span data-stu-id="7b390-245">In the **Styles** tab below the DOM Tree you can see the `font-family: 'Courier New', Courier, serif` declaration that you added to `contact.html` earlier.</span></span>  
    
    > ##### <span data-ttu-id="7b390-246">図 13</span><span class="sxs-lookup"><span data-stu-id="7b390-246">Figure 13</span></span>  
    > <span data-ttu-id="7b390-247">[スタイル] タブが DOM ツリーの下にある</span><span class="sxs-lookup"><span data-stu-id="7b390-247">The Styles tab is below the DOM Tree</span></span>  
    > ![[スタイル] タブが DOM ツリーの下にある][ImageCssAdd2]  
    
    <span data-ttu-id="7b390-249">DevTools ウィンドウが広くなっている場合、[スタイル] タブは DOM ツリーの右側にあります。</span><span class="sxs-lookup"><span data-stu-id="7b390-249">If your DevTools window is wide, the Styles tab is to the right of the DOM Tree.</span></span>  
    
    > ##### <span data-ttu-id="7b390-250">図 14</span><span class="sxs-lookup"><span data-stu-id="7b390-250">Figure 14</span></span>  
    > <span data-ttu-id="7b390-251">[スタイル] タブは DOM ツリーの右側にあります。</span><span class="sxs-lookup"><span data-stu-id="7b390-251">The Styles tab is to the right of the DOM Tree</span></span>  
    > ![[スタイル] タブは DOM ツリーの右側にあります。][ImageCssAdd3]  
    
1.  <span data-ttu-id="7b390-253">新しい宣言を追加するには、下の空白をクリックし `font-family: 'Courier New', Courier, Serif` ます。</span><span class="sxs-lookup"><span data-stu-id="7b390-253">Click the whitespace below `font-family: 'Courier New', Courier, Serif` to add a new declaration.</span></span>  
    
    > ##### <span data-ttu-id="7b390-254">図 15</span><span class="sxs-lookup"><span data-stu-id="7b390-254">Figure 15</span></span>  
    > <span data-ttu-id="7b390-255">新しい宣言を追加する</span><span class="sxs-lookup"><span data-stu-id="7b390-255">Adding a new declaration</span></span>  
    > ![新しい宣言を追加する][ImageCssAdd4]  
    
1.  <span data-ttu-id="7b390-257">入力 `color` して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="7b390-257">Type `color` and then press `Enter`.</span></span>  <span data-ttu-id="7b390-258">入力時にオートコンプリート UI によってオプションが提示されます。</span><span class="sxs-lookup"><span data-stu-id="7b390-258">The autocomplete UI suggests options as you type.</span></span>  
    
    > ##### <span data-ttu-id="7b390-259">図 16</span><span class="sxs-lookup"><span data-stu-id="7b390-259">Figure 16</span></span>  
    > <span data-ttu-id="7b390-260">入力</span><span class="sxs-lookup"><span data-stu-id="7b390-260">Typing</span></span> `color`  
    > ![入力時の色][ImageCssAdd5]  

1.  <span data-ttu-id="7b390-262">入力 `magenta` して、 `Enter` もう一度押します。</span><span class="sxs-lookup"><span data-stu-id="7b390-262">Type `magenta` and then press `Enter` again.</span></span>  <span data-ttu-id="7b390-263">連絡先ページのすべてのテキストがマジェンタ色になりました。</span><span class="sxs-lookup"><span data-stu-id="7b390-263">All of the text on the contact page is now magenta.</span></span>  
    
    > ##### <span data-ttu-id="7b390-264">図 17</span><span class="sxs-lookup"><span data-stu-id="7b390-264">Figure 17</span></span>  
    > <span data-ttu-id="7b390-265">入力</span><span class="sxs-lookup"><span data-stu-id="7b390-265">Typing</span></span> `magenta`  
    > ![マゼンタの入力][ImageCssAdd6]  
    
### <span data-ttu-id="7b390-267">DevTools で宣言を編集する</span><span class="sxs-lookup"><span data-stu-id="7b390-267">Edit a declaration in DevTools</span></span>   

<span data-ttu-id="7b390-268">また、DevTools で既存の宣言を編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="7b390-268">You can also edit existing declarations in DevTools.</span></span>  <span data-ttu-id="7b390-269">今すぐお試しください:</span><span class="sxs-lookup"><span data-stu-id="7b390-269">Try it now:</span></span>  

1.  <span data-ttu-id="7b390-270">の横にあるマゼンタの正方形をクリックし `magenta` ます。</span><span class="sxs-lookup"><span data-stu-id="7b390-270">Click the magenta square next to `magenta`.</span></span>  <span data-ttu-id="7b390-271">カラーピッカーがポップアップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b390-271">A color picker pops up.</span></span>  
    
    > ##### <span data-ttu-id="7b390-272">図18</span><span class="sxs-lookup"><span data-stu-id="7b390-272">Figure 18</span></span>  
    > <span data-ttu-id="7b390-273">色のパレット</span><span class="sxs-lookup"><span data-stu-id="7b390-273">The Color Picker</span></span>  
    > ![色のパレット][ImageCssEdit1]  
    
1.  <span data-ttu-id="7b390-275">カラーピッカーを使用して、フォントのテキストを好みの色に変更します。</span><span class="sxs-lookup"><span data-stu-id="7b390-275">Use the color picker to change the font text to a color that you like.</span></span>  
    
    > ##### <span data-ttu-id="7b390-276">図19</span><span class="sxs-lookup"><span data-stu-id="7b390-276">Figure 19</span></span>  
    > <span data-ttu-id="7b390-277">カラーピッカーを使用してフォントの色を紫色に変更する</span><span class="sxs-lookup"><span data-stu-id="7b390-277">Changing the font color to purple with the Color Picker</span></span>  
    > ![カラーピッカーを使用してフォントの色を紫色に変更する][ImageCssEdit2]  

### <span data-ttu-id="7b390-279">DevTools で新しいルールセットを追加する</span><span class="sxs-lookup"><span data-stu-id="7b390-279">Add a new ruleset in DevTools</span></span>   

<span data-ttu-id="7b390-280">DevTools で新しいルールセットを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="7b390-280">You can also add new rulesets in DevTools.</span></span>  <span data-ttu-id="7b390-281">今すぐお試しください:</span><span class="sxs-lookup"><span data-stu-id="7b390-281">Try it now:</span></span>  

1.  <span data-ttu-id="7b390-282">[**新しいスタイルルール**] をクリックし ![ ][ImageNewStyleRuleIcon] **ます。** これは、cls の横にあります。</span><span class="sxs-lookup"><span data-stu-id="7b390-282">Click **New Style Rule** ![New Style Rule][ImageNewStyleRuleIcon] which is next to **.cls**.</span></span>  <span data-ttu-id="7b390-283">空のルールセットが `a` セレクターとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b390-283">An empty ruleset appears with `a` as the selector.</span></span>  
    
    > ##### <span data-ttu-id="7b390-284">図20</span><span class="sxs-lookup"><span data-stu-id="7b390-284">Figure 20</span></span>  
    > <span data-ttu-id="7b390-285">新しいルールを追加する</span><span class="sxs-lookup"><span data-stu-id="7b390-285">Adding a new rule</span></span>  
    > ![新しいルールを追加する][ImageCssRule1]  
    
1.  <span data-ttu-id="7b390-287">置換後 `a` の文字列 `a:hover`</span><span class="sxs-lookup"><span data-stu-id="7b390-287">Replace `a` with `a:hover`.</span></span>  
    
    > ##### <span data-ttu-id="7b390-288">図21</span><span class="sxs-lookup"><span data-stu-id="7b390-288">Figure 21</span></span>  
    > <span data-ttu-id="7b390-289">置換 `a`</span><span class="sxs-lookup"><span data-stu-id="7b390-289">Replacing `a` with</span></span> `a:hover`  
    > ![A を @ に置換する][ImageCssRule2]  
    
    `:hover` <span data-ttu-id="7b390-291">は**擬似クラス**です。</span><span class="sxs-lookup"><span data-stu-id="7b390-291">is a **pseudo-class**.</span></span>  <span data-ttu-id="7b390-292">疑似クラスを使って、特殊な状態を入力するときに要素のスタイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="7b390-292">Use pseudo-classes to style elements when they enter special states.</span></span>  <span data-ttu-id="7b390-293">たとえば、スタイルは、 `a:hover` 要素の上にマウスポインターを置いた場合にのみ有効になり `<a>` ます。</span><span class="sxs-lookup"><span data-stu-id="7b390-293">For example, the `a:hover` style only takes effect when you're hovering over an `<a>` element.</span></span>  
    
1.  <span data-ttu-id="7b390-294">かっこの間をクリックして新しい宣言を追加します。</span><span class="sxs-lookup"><span data-stu-id="7b390-294">Click between the brackets to add a new declaration.</span></span>  
1.  <span data-ttu-id="7b390-295">`background-color`宣言の名前を入力し、enter キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="7b390-295">Type `background-color` for the declaration name and then press `Enter`.</span></span>  
    
    > ##### <span data-ttu-id="7b390-296">図22</span><span class="sxs-lookup"><span data-stu-id="7b390-296">Figure 22</span></span>  
    > <span data-ttu-id="7b390-297">入力</span><span class="sxs-lookup"><span data-stu-id="7b390-297">Typing</span></span> `background-color`  
    > ![背景色の入力][ImageCssRule3]  
    
1.  <span data-ttu-id="7b390-299">`green`宣言の値を入力して、キーを押し `Enter` ます。</span><span class="sxs-lookup"><span data-stu-id="7b390-299">Type `green` for the declaration value and then press `Enter`.</span></span>  
    
    > ##### <span data-ttu-id="7b390-300">図23</span><span class="sxs-lookup"><span data-stu-id="7b390-300">Figure 23</span></span>  
    > <span data-ttu-id="7b390-301">入力</span><span class="sxs-lookup"><span data-stu-id="7b390-301">Typing</span></span> `green`  
    > ![緑の入力][ImageCssRule4]  
    
1.  <span data-ttu-id="7b390-303">[**ホーム**] リンクの上にマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="7b390-303">Hover your mouse over the **Home** link.</span></span>  <span data-ttu-id="7b390-304">リンクの背景が緑色になります。</span><span class="sxs-lookup"><span data-stu-id="7b390-304">The background of the link turns green.</span></span>  
    
    > ##### <span data-ttu-id="7b390-305">図24</span><span class="sxs-lookup"><span data-stu-id="7b390-305">Figure 24</span></span>  
    > <span data-ttu-id="7b390-306">ホームリンク上にマウスポインターを移動すると、緑色の背景が表示される</span><span class="sxs-lookup"><span data-stu-id="7b390-306">Hovering over the Home link to reveal its green background</span></span>  
    > ![ホームリンク上にマウスポインターを移動すると、緑色の背景が表示される][ImageCssRule5]  
    
## <span data-ttu-id="7b390-308">外部のスタイルシートを含むページ間でスタイルを再利用する</span><span class="sxs-lookup"><span data-stu-id="7b390-308">Re-use styles across pages with external stylesheets</span></span>   

<span data-ttu-id="7b390-309">以前のバージョンでは、次のような内部スタイルシートが追加されました `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="7b390-309">Earlier you added this internal stylesheet to `contact.html`:</span></span>  

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

<span data-ttu-id="7b390-310">同じ方法でスタイルを適用する場合は、どうすればよい `index.html` ですか。</span><span class="sxs-lookup"><span data-stu-id="7b390-310">What if you wanted to style `index.html` the same way?</span></span>  <span data-ttu-id="7b390-311">*数千個*のページがあって、それらすべてにそれらのスタイルを適用したい場合はどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="7b390-311">What if you had a *thousand* pages and you wanted to apply these styles to all of them?</span></span>  <span data-ttu-id="7b390-312">この内部スタイルシートをコピーして、サイトのすべての web ページに貼り付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b390-312">You'd have to copy and paste this internal stylesheet into every single web page on your site.</span></span>  <span data-ttu-id="7b390-313">**外部のスタイルシート**を使用すると、CSS を複数のページに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="7b390-313">**External stylesheets** allow you to write your CSS once yet apply it to multiple pages.</span></span>  <span data-ttu-id="7b390-314">今すぐお試しください:</span><span class="sxs-lookup"><span data-stu-id="7b390-314">Try it now:</span></span>  

1.  <span data-ttu-id="7b390-315">まず、[ライブ] タブをもう一度読み込んで、DevTools で行った変更を削除します。</span><span class="sxs-lookup"><span data-stu-id="7b390-315">First, reload the live tab to remove the changes that you made in DevTools.</span></span>  
    
    > ##### <span data-ttu-id="7b390-316">図25</span><span class="sxs-lookup"><span data-stu-id="7b390-316">Figure 25</span></span>  
    >  <span data-ttu-id="7b390-317">ページを再読み込みした後、DevTools で行った変更は廃止されました</span><span class="sxs-lookup"><span data-stu-id="7b390-317">After reloading the page the changes that were made in DevTools are gone</span></span>  
    > ![ <span data-ttu-id="7b390-318">ページを再読み込みした後、DevTools で行った変更は廃止されました</span><span class="sxs-lookup"><span data-stu-id="7b390-318">After reloading the page the changes that were made in DevTools are gone</span></span>][ImageCssExternal01]  
    
1.  <span data-ttu-id="7b390-319">[**エディター] タブ**に戻り、を開き `contact.html` ます。</span><span class="sxs-lookup"><span data-stu-id="7b390-319">Go back to the **editor tab** and open `contact.html`.</span></span>  
    
    > ##### <span data-ttu-id="7b390-320">図26</span><span class="sxs-lookup"><span data-stu-id="7b390-320">Figure 26</span></span>  
    > `contact.html`  
    > ![連絡先 .html][ImageCssExternal02]  
    
1.  <span data-ttu-id="7b390-322">およびを `<style>` `</style>` 含む、and を含むすべてのデータを削除し `<style>` `</style>` ます。</span><span class="sxs-lookup"><span data-stu-id="7b390-322">Delete everything between `<style>` and `</style>`, including `<style>` and `</style>`.</span></span>  
    
    > ##### <span data-ttu-id="7b390-323">図27</span><span class="sxs-lookup"><span data-stu-id="7b390-323">Figure 27</span></span>  
    > <span data-ttu-id="7b390-324">スタイルタグが削除されました</span><span class="sxs-lookup"><span data-stu-id="7b390-324">The style tag has been removed</span></span>  
    > ![スタイルタグが削除されました][ImageCssExternal03]  
    
1.  <span data-ttu-id="7b390-326">`index.html`タグから移動して削除し `style="background-color: aliceblue;"` `<nav>` ます。</span><span class="sxs-lookup"><span data-stu-id="7b390-326">Go to `index.html` and remove `style="background-color: aliceblue;"` from the `<nav>` tag.</span></span>  <span data-ttu-id="7b390-327">これで、以前にサイトに追加した CSS がすべて削除されました。</span><span class="sxs-lookup"><span data-stu-id="7b390-327">You have now removed all of the CSS that you previously added to your site.</span></span>  
    
    > ##### <span data-ttu-id="7b390-328">図28</span><span class="sxs-lookup"><span data-stu-id="7b390-328">Figure 28</span></span>  
    > <span data-ttu-id="7b390-329">インラインスタイルが nav 要素から削除されている</span><span class="sxs-lookup"><span data-stu-id="7b390-329">The inline style has been removed from the nav element</span></span>  
    > ![インラインスタイルが nav 要素から削除されている][ImageCssExternal04]  

1.  <span data-ttu-id="7b390-331">[**新しいファイル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b390-331">Click **New File**.</span></span>  
    
    > ##### <span data-ttu-id="7b390-332">図29</span><span class="sxs-lookup"><span data-stu-id="7b390-332">Figure 29</span></span>  
    > <span data-ttu-id="7b390-333">[新しいファイル] ダイアログ</span><span class="sxs-lookup"><span data-stu-id="7b390-333">The new file dialog</span></span>  
    > ![[新しいファイル] ダイアログ][ImageCssExternal05]  
    
1.  <span data-ttu-id="7b390-335">置換 `cool-file.js` `style.css` 後、[**ファイルの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b390-335">Replace `cool-file.js` with `style.css` and then click **Add File**.</span></span>  
    
    > ##### <span data-ttu-id="7b390-336">図30</span><span class="sxs-lookup"><span data-stu-id="7b390-336">Figure 30</span></span>  
    > <span data-ttu-id="7b390-337">入力</span><span class="sxs-lookup"><span data-stu-id="7b390-337">Typing</span></span> `style.css`  
    > ![入力スタイル .css][ImageCssExternal06]  
    
1.  <span data-ttu-id="7b390-339">次のコードに貼り付け `style.css` ます。</span><span class="sxs-lookup"><span data-stu-id="7b390-339">Paste this code into `style.css`:</span></span>  
    
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
    
    > ##### <span data-ttu-id="7b390-340">図31</span><span class="sxs-lookup"><span data-stu-id="7b390-340">Figure 31</span></span>  
    > <span data-ttu-id="7b390-341">コードの追加</span><span class="sxs-lookup"><span data-stu-id="7b390-341">Adding code to</span></span> `style.css`  
    > ![スタイル .css へのコードの追加][ImageCssExternal07]  
    
    <span data-ttu-id="7b390-343">この時点では、外部のスタイルシートを作成しましたが、HTML ではまだ存在していることがわかりません。</span><span class="sxs-lookup"><span data-stu-id="7b390-343">At this point, you have created an external stylesheet, but your HTML doesn't know that it exists, yet.</span></span>  
    
1.  <span data-ttu-id="7b390-344">[開く] `index.html` を選びます。</span><span class="sxs-lookup"><span data-stu-id="7b390-344">Open `index.html`.</span></span>  
1.  <span data-ttu-id="7b390-345">`<link rel="stylesheet" href="style.css">`HTML に追加します。</span><span class="sxs-lookup"><span data-stu-id="7b390-345">Add `<link rel="stylesheet" href="style.css">` to your HTML.</span></span>  
    
    ```html
    ...
        <head>
            ...
            <meta name="viewport" content="width=device-width, initial-scale=1">
            <link rel="stylesheet" href="style.css">
        </head>
        ...
    ...
    ```  

    > ##### <span data-ttu-id="7b390-346">図32</span><span class="sxs-lookup"><span data-stu-id="7b390-346">Figure 32</span></span>  
    > <span data-ttu-id="7b390-347">リンク先</span><span class="sxs-lookup"><span data-stu-id="7b390-347">Linking to</span></span> `style.css`  
    > ![スタイル .css へのリンク][ImageCssExternal08]  

1.  <span data-ttu-id="7b390-349">リンクも `contact.html` そこに移動して追加します。</span><span class="sxs-lookup"><span data-stu-id="7b390-349">Go to `contact.html` and add the link there, too.</span></span>  
    
    > ##### <span data-ttu-id="7b390-350">図33</span><span class="sxs-lookup"><span data-stu-id="7b390-350">Figure 33</span></span>  
    > <span data-ttu-id="7b390-351">リンク先 `style.css`</span><span class="sxs-lookup"><span data-stu-id="7b390-351">Linking to `style.css` in</span></span> `contact.html`  
    > ![.Html でスタイル .css へのリンク][ImageCssExternal09]  

1.  <span data-ttu-id="7b390-353">[**ライブ] タブ**に移動します。 これで、ホームページの最後のセクションと青色のナビゲーションセクションのフォントが変わりました。</span><span class="sxs-lookup"><span data-stu-id="7b390-353">Go to the **live tab**.  The home page now has the same font from the last section and a blue navigation section.</span></span>  
    
    > ##### <span data-ttu-id="7b390-354">図34</span><span class="sxs-lookup"><span data-stu-id="7b390-354">Figure 34</span></span>  
    > <span data-ttu-id="7b390-355">ホームページ</span><span class="sxs-lookup"><span data-stu-id="7b390-355">The home page</span></span>  
    > ![ホームページ][ImageCssExternal10]  
    
1.  <span data-ttu-id="7b390-357">**連絡先**のリンクをクリックして、連絡先ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="7b390-357">Click the **Contact** link to go to the contact page.</span></span>  <span data-ttu-id="7b390-358">連絡先ページは、ホームページと同じ書式設定になっています。</span><span class="sxs-lookup"><span data-stu-id="7b390-358">The contact page has the same formatting as the home page.</span></span>  
    
    > ##### <span data-ttu-id="7b390-359">図35</span><span class="sxs-lookup"><span data-stu-id="7b390-359">Figure 35</span></span>  
    > <span data-ttu-id="7b390-360">[連絡先] ページ</span><span class="sxs-lookup"><span data-stu-id="7b390-360">The contact page</span></span>  
    > ![[連絡先] ページ][ImageCssExternal11]  
    
## <span data-ttu-id="7b390-362">CSS フレームワークを使う</span><span class="sxs-lookup"><span data-stu-id="7b390-362">Use a CSS framework</span></span>   

<span data-ttu-id="7b390-363">**CSS フレームワーク**は、魅力的な web サイトを簡単に作成できる他の開発者によって構築されたスタイルのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="7b390-363">**CSS frameworks** are collections of styles built by other developers that make it easier to create attractive web sites.</span></span>  <span data-ttu-id="7b390-364">独自のスタイルを定義する代わりに、フレームワークによって、ページ要素で使うことができるスタイルのコレクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="7b390-364">Instead of defining styles yourself, a framework gives you a collection of styles that you can use on your page elements.</span></span>  

1.  <span data-ttu-id="7b390-365">次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="7b390-365">Copy the following code:</span></span>  
    
    ```html
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.1/css/bootstrap.min.css">
    ```  
    
1.  <span data-ttu-id="7b390-366">[編集] タブに移動し、コードを貼り付け `contact.html` ます。</span><span class="sxs-lookup"><span data-stu-id="7b390-366">Go to the editing tab and paste the code into `contact.html`.</span></span>  
    
    > ##### <span data-ttu-id="7b390-367">図36</span><span class="sxs-lookup"><span data-stu-id="7b390-367">Figure 36</span></span>  
    > <span data-ttu-id="7b390-368">フレームワークへのリンク</span><span class="sxs-lookup"><span data-stu-id="7b390-368">Linking to the framework in</span></span> `contact.html`  
    > ![.Html でのフレームワークへのリンク][ImageCssFramework1]  
    
1.  <span data-ttu-id="7b390-370">同様にコードを貼り付け `index.html` ます。</span><span class="sxs-lookup"><span data-stu-id="7b390-370">Paste the code into `index.html`, as well.</span></span>  
    
    > ##### <span data-ttu-id="7b390-371">図37</span><span class="sxs-lookup"><span data-stu-id="7b390-371">Figure 37</span></span>  
    > <span data-ttu-id="7b390-372">フレームワークへのリンク</span><span class="sxs-lookup"><span data-stu-id="7b390-372">Linking to the framework in</span></span> `index.html`  
    > ![Html のフレームワークへのリンク][ImageCssFramework2]  
    
1.  <span data-ttu-id="7b390-374">[ライブ] タブに戻り、変更内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="7b390-374">Go back to the live tab to view your changes.</span></span>  <span data-ttu-id="7b390-375">要素の背景色とフォントが同じであるのに、 `<nav>` `li a` 他の要素のフォントが変更されています。</span><span class="sxs-lookup"><span data-stu-id="7b390-375">While the background color of the `<nav>` and the font of the `li a` elements are the same, the font of the other elements has changed.</span></span>  
    
    > ##### <span data-ttu-id="7b390-376">図38</span><span class="sxs-lookup"><span data-stu-id="7b390-376">Figure 38</span></span>  
    > <span data-ttu-id="7b390-377">フレームワークによってホームページの一部のフォントが変更されている</span><span class="sxs-lookup"><span data-stu-id="7b390-377">Some of the font on the home page has changed because of the framework</span></span>  
    > ![フレームワークによってホームページの一部のフォントが変更されている][ImageCssFramework3]  

### <span data-ttu-id="7b390-379">クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="7b390-379">Use a class</span></span>   

<span data-ttu-id="7b390-380">最後のセクションでは、web ページにブートストラップを追加して、サイトの要素のフォントを変更しました。</span><span class="sxs-lookup"><span data-stu-id="7b390-380">In the last section, you added Bootstrap to your web pages, which changed the fonts of some of the elements on your site.</span></span>  <span data-ttu-id="7b390-381">CSS フレームワークを使うと、非常にわずかなコードでページに大きな変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="7b390-381">CSS frameworks can help you make major changes to your page with very little code.</span></span>  <span data-ttu-id="7b390-382">ヘッダーを変更して、今すぐ試してみてください。</span><span class="sxs-lookup"><span data-stu-id="7b390-382">Try it now by changing your header:</span></span>  

1.  <span data-ttu-id="7b390-383">次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="7b390-383">Copy this code:</span></span>  
    
    ```html
    class="jumbotron jumbotron-fluid"  
    ```  
    
1.  <span data-ttu-id="7b390-384">このコードを `<header>` のタグに追加 `index.html` します。</span><span class="sxs-lookup"><span data-stu-id="7b390-384">Add this code to your `<header>` tag in `index.html`.</span></span>  
    
    > ##### <span data-ttu-id="7b390-385">図39</span><span class="sxs-lookup"><span data-stu-id="7b390-385">Figure 39</span></span>  
    > <span data-ttu-id="7b390-386">クラスの追加</span><span class="sxs-lookup"><span data-stu-id="7b390-386">Adding classes in</span></span> `index.html`  
    > ![Html にクラスを追加する][ImageCssJumbotron1]  
    
1.  <span data-ttu-id="7b390-388">コードを `<header>` タグに `contact.html` も追加します。</span><span class="sxs-lookup"><span data-stu-id="7b390-388">Add the code to your `<header>` tag in `contact.html`, too.</span></span>  
    
    > ##### <span data-ttu-id="7b390-389">図40</span><span class="sxs-lookup"><span data-stu-id="7b390-389">Figure 40</span></span>  
    > <span data-ttu-id="7b390-390">クラスの追加</span><span class="sxs-lookup"><span data-stu-id="7b390-390">Adding classes in</span></span> `contact.html`  
    > ![連絡先 .html にクラスを追加する][ImageCssJumbotron2]  
    
1.  <span data-ttu-id="7b390-392">[ライブ] タブで変更内容を表示します。 ここでは、ヘッダーの周りに大きな灰色のボックスが表示されています。</span><span class="sxs-lookup"><span data-stu-id="7b390-392">View your changes in the live tab.  There's a big, grey box around your header now.</span></span>  
    
    > ##### <span data-ttu-id="7b390-393">図41</span><span class="sxs-lookup"><span data-stu-id="7b390-393">Figure 41</span></span>  
    > <span data-ttu-id="7b390-394">ヘッダーの周りに大きな灰色のボックスがあるようになりました</span><span class="sxs-lookup"><span data-stu-id="7b390-394">The header now has a big, grey box around it</span></span>  
    > ![ヘッダーの周りに大きな灰色のボックスがあるようになりました][ImageCssJumbotron3]  
    
### <span data-ttu-id="7b390-396">クラスについて</span><span class="sxs-lookup"><span data-stu-id="7b390-396">Understand classes</span></span>   

<span data-ttu-id="7b390-397">クラスを使うと、スタイルのコレクションを任意の要素に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="7b390-397">Classes let you assign collections of styles to arbitrary elements.</span></span>  <span data-ttu-id="7b390-398">たとえば、 `class` `<header>` 次の `jumbotron` スタイルが適用されるようにタグの属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="7b390-398">For example, setting the `class` attribute of the `<header>` tags to `jumbotron` applied the following styles to them:</span></span>  

```css
.jumbotron {
  padding: 2rem 1rem;
  margin-bottom: 2rem;
  background-color: #e9ecef;
  border-radius: .3rem;
}
```  

<span data-ttu-id="7b390-399">クラスの利点の1つは、目的の要素にスタイルを適用できることです。</span><span class="sxs-lookup"><span data-stu-id="7b390-399">One advantage of classes is that they let you apply styles to whatever elements you want.</span></span>  <span data-ttu-id="7b390-400">たとえば、*一部*の要素の背景色を紫色に設定し、そのすべてではない場合を考え `<p>` ます。 *all*</span><span class="sxs-lookup"><span data-stu-id="7b390-400">For example, suppose you want to set the background color of *some* `<p>` elements to purple, but not *all* of them.</span></span>  <span data-ttu-id="7b390-401">クラスでスタイルを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="7b390-401">You could define the style in a class:</span></span>  

```css
.custom-background {
  background-color: purple;
}
```  

<span data-ttu-id="7b390-402">次に、スタイルを適用する要素のみにクラスを適用し `<p>` ます。</span><span class="sxs-lookup"><span data-stu-id="7b390-402">And then apply the class to only the `<p>` elements that you want to style:</span></span>  

```html
...
    ...
        ...
        <p>This won't be purple.</p>
        <p class="custom-background">This will be purple.</p>
        <p>This won't be purple.</p>
        <p class="custom-background">This will be purple.</p>
        ...
    ...
...
```  

### <span data-ttu-id="7b390-403">要素の配置</span><span class="sxs-lookup"><span data-stu-id="7b390-403">Align elements</span></span>   

<span data-ttu-id="7b390-404">また、ブートストラップには要素を配置するためのクラスも用意されています。</span><span class="sxs-lookup"><span data-stu-id="7b390-404">Bootstrap also provides classes for aligning elements.</span></span>  <span data-ttu-id="7b390-405">今すぐお試しください:</span><span class="sxs-lookup"><span data-stu-id="7b390-405">Try it now:</span></span>  

1.  <span data-ttu-id="7b390-406">[エディター] タブに戻り、を開き `index.html` ます。</span><span class="sxs-lookup"><span data-stu-id="7b390-406">Go back to the editor tab and open `index.html`.</span></span>  
1.  <span data-ttu-id="7b390-407">`class="container-fluid"`タグに追加 `<body>` します。</span><span class="sxs-lookup"><span data-stu-id="7b390-407">Add `class="container-fluid"` to your `<body>` tag.</span></span>  
    
    > ##### <span data-ttu-id="7b390-408">図42</span><span class="sxs-lookup"><span data-stu-id="7b390-408">Figure 42</span></span>  
    > <span data-ttu-id="7b390-409">クラスの追加 `container-fluid`</span><span class="sxs-lookup"><span data-stu-id="7b390-409">Adding the `container-fluid` class</span></span>  
    > ![コンテナー-流体クラスの追加][ImageCssAlign1]  

1.  <span data-ttu-id="7b390-411">`<nav>`と `<main>` の要素を折り返し `<div class="row">` ます。</span><span class="sxs-lookup"><span data-stu-id="7b390-411">Wrap your `<nav>` and `<main>` elements in `<div class="row">`.</span></span>  <span data-ttu-id="7b390-412">`</div>` `</main>` 新しいノートシールを正しく閉じるには、[指定の日時以降] をオンにしてください。</span><span class="sxs-lookup"><span data-stu-id="7b390-412">Make sure to put `</div>` after `</main>` in order to properly close the new tag.</span></span>  
    
    > ##### <span data-ttu-id="7b390-413">図43</span><span class="sxs-lookup"><span data-stu-id="7b390-413">Figure 43</span></span>  
    > <span data-ttu-id="7b390-414">行の追加</span><span class="sxs-lookup"><span data-stu-id="7b390-414">Adding a row</span></span>  
    > ![行の追加][ImageCssAlign2]  
    
1.  <span data-ttu-id="7b390-416">`class="col-3"` `<nav>` タグとタグに追加 `class="col-9"` `<main>` します。</span><span class="sxs-lookup"><span data-stu-id="7b390-416">Add `class="col-3"` to your `<nav>` tag and `class="col-9"` to your `<main>` tag.</span></span>  
    
    > ##### <span data-ttu-id="7b390-417">図44</span><span class="sxs-lookup"><span data-stu-id="7b390-417">Figure 44</span></span>  
    > <span data-ttu-id="7b390-418">`col-3`クラスを追加 `col-9` する</span><span class="sxs-lookup"><span data-stu-id="7b390-418">Adding the `col-3` and `col-9` classes</span></span>  
    > ![列3と列9のクラスを追加する][ImageCssAlign3]  
    
1.  <span data-ttu-id="7b390-420">[ライブ] タブで変更内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="7b390-420">View your changes in the live tab.</span></span>  
    
    > ##### <span data-ttu-id="7b390-421">図45</span><span class="sxs-lookup"><span data-stu-id="7b390-421">Figure 45</span></span>  
    > <span data-ttu-id="7b390-422">これで、ナビゲーションコンテンツがメインコンテンツの左になりました</span><span class="sxs-lookup"><span data-stu-id="7b390-422">The nav content is now to the left of the main content</span></span>  
    > ![これで、ナビゲーションコンテンツがメインコンテンツの左になりました][ImageCssAlign4]  
    
## <span data-ttu-id="7b390-424">次のステップ</span><span class="sxs-lookup"><span data-stu-id="7b390-424">Next steps</span></span>   

<span data-ttu-id="7b390-425">お疲れさまでした。</span><span class="sxs-lookup"><span data-stu-id="7b390-425">Congratulations!</span></span>  <span data-ttu-id="7b390-426">これで完了です。</span><span class="sxs-lookup"><span data-stu-id="7b390-426">You're done!</span></span>  

*   <span data-ttu-id="7b390-427">Web 開発に適した方法は、さらに多くのサイトを構築することです。</span><span class="sxs-lookup"><span data-stu-id="7b390-427">The best way to get better at web development is to build more sites.</span></span>  <span data-ttu-id="7b390-428">問題を壊す心配は無用です。</span><span class="sxs-lookup"><span data-stu-id="7b390-428">Don't worry about breaking stuff.</span></span>  <span data-ttu-id="7b390-429">今まで以上に便利な機能をご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="7b390-429">Just have fun and learn as much as you can along the way.</span></span>  
*   <span data-ttu-id="7b390-430">Web ページのスタイル設定の詳細については、「 [CSS の概要][MDNCssFirstSteps]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7b390-430">Check out [Introduction to CSS][MDNCssFirstSteps] to learn lots more about styling web pages.</span></span>  
*   <span data-ttu-id="7b390-431">「CSS の[表示と変更の概要」チュートリアルの概要][DevtoolsCssIndex]については、「devtools を使ってページの css を試す方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b390-431">Work through our [Get Started with Viewing and Changing CSS][DevtoolsCssIndex] tutorial to learn more about how you can use DevTools to experiment with a page's CSS.</span></span>  

<!--- image links --->  

[ImageNewStyleRuleIcon]: /microsoft-edge/devtools-guide-chromium/media/new-style-rule-icon.msft.png  

[ImageCssIntro1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-intro1.msft.png "図 1: サイトが現在どのように見えるか"  
[ImageCssIntro2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-intro2.msft.png "図 2: チュートリアルの最後にサイトがどのように表示されるか"  
[ImageCssSetup1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-setup1.msft.png "図 3: [編集] タブ"  
[ImageCssSetup2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-setup2.msft.png "図 4: [プロジェクトのオプション] メニュー"  
[ImageCssSetup3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-setup3.msft.png "図 5: [ライブ] タブ"  
[ImageCssStyled]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-red_paragraph.msft.png "図 6: CSS でスタイルが適用されている"  
[ImageCssInline1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-inline1.msft.png "図 7: .html"  
[ImageCssInline2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-inline2.msft.png "図 8: ホームと連絡先のリンクの背景色が青になりました"  
[ImageCssInternal1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-internal1.msft.png "図 9: 連絡先ページ"  
[ImageCssInternal2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-internal2.msft.png "図 10: ホームと連絡先のリンクのフォントが変更されている"  
[ImageCssMultiple1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-multiple1.msft.png "図 11: "連絡先" というテキストは、[ホーム] と [連絡先] のリンクと同じフォントになりました"  
[ImageCssAdd1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add1.msft.png "図 12: ホームリンクを調べる"  
[ImageCssAdd2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add2.msft.png "図 13: [スタイル] タブが DOM ツリーの下にある"  
[ImageCssAdd3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add3.msft.png "図 14: [スタイル] タブは DOM ツリーの右にあります。"  
[ImageCssAdd4]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add4.msft.png "図 15: 新しい宣言を追加する"
[ImageCssAdd5]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add5.msft.png "図 16: 色を入力する"  
[ImageCssAdd6]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add6.msft.png "図 17: マゼンタを入力する"  
[ImageCssEdit1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-edit1.msft.png "図 18: 色のパレット"  
[ImageCssEdit2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-edit2.msft.png "図 19: カラーピッカーを使用してフォントの色を紫色に変更する"  
[ImageCssRule1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-rule1.msft.png "図 20: 新しいルールを追加する"  
[ImageCssRule2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-rule2.msft.png "図 21: a を「a」に置き換える"  
[ImageCssRule3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-rule3.msft.png "図 22: 背景色を入力する"  
[ImageCssRule4]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-rule4.msft.png "図 23: 緑で入力する"  
[ImageCssRule5]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-rule5.msft.png "図 24: ホームリンクをポイントして、緑色の背景を表示する"  
[ImageCssExternal01]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external1.msft.png "図 25: ページを再読み込みした後に、DevTools で行った変更が廃止される"  
[ImageCssExternal02]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external2.msft.png "図 26: 連絡先 .html"  
[ImageCssExternal03]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external3.msft.png "図 27: スタイルタグが削除されている"  
[ImageCssExternal04]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external4.msft.png "図 28: インラインスタイルが nav 要素から削除されている"  
[ImageCssExternal05]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external5.msft.png "図 29: [新しいファイル] ダイアログボックス"  
[ImageCssExternal06]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external6.msft.png "図 30: css の入力"  
[ImageCssExternal07]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external7.msft.png "図 31: スタイルにコードを追加する"  
[ImageCssExternal08]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external8.msft.png "図 32: スタイル .css へのリンク"  
[ImageCssExternal09]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external9.msft.png "図 33: .html でのスタイル .css へのリンク"  
[ImageCssExternal10]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external10.msft.png "図 34: ホームページ"  
[ImageCssExternal11]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external11.msft.png "図 35: 連絡先ページ"  
[ImageCssFramework1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-framework1.msft.png "図 36: 「.html でのフレームワークへのリンク」"  
[ImageCssFramework2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-framework2.msft.png "図 37: html のフレームワークへのリンク"  
[ImageCssFramework3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-framework3.msft.png "図 38: フレームワークによってホームページの一部のフォントが変更されている"  
[ImageCssJumbotron1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-jumbotron1.msft.png "図 39: .html にクラスを追加する"  
[ImageCssJumbotron2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-jumbotron2.msft.png "図 40: .html にクラスを追加する"  
[ImageCssJumbotron3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-jumbotron3.msft.png "図 41: ヘッダーの周りに大きな灰色のボックスがある"  
[ImageCssAlign1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-align1.msft.png "図 42: コンテナーの流体クラスを追加する"  
[ImageCssAlign2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-align2.msft.png "図 43: 行を追加する"  
[ImageCssAlign3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-align3.msft.png "図 44: 列3と列9のクラスを追加する"  
[ImageCssAlign4]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-align4.msft.png "図 45: ナビゲーションコンテンツがメインコンテンツの左側にある"  

<!--- links  --->  

[DevToolsBeginnersHtml]: html.md "初心者向けの DevTools: HTML と DOM の使用を開始する"  
[DevtoolsCssIndex]: ../css/index.md "CSS の表示と変更を始める"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge Insider"  

[GlitchCookedAmphibianIndex]: https://glitch.com/edit/#!/cooked-amphibian?path=index.html "html: 作成済み-水陸両用機 |故障"  

[MDNCssFirstSteps]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS "CSS の最初のステップ |MDN"  

> [!NOTE]
> <span data-ttu-id="7b390-482">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="7b390-482">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="7b390-483">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/beginners/css)にあり、 [Katherine Jackson][KatherineJackson] \ (テクニカルライターインターン、Chrome devtools) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="7b390-483">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/beginners/css) and is authored by [Katherine Jackson][KatherineJackson] \(Technical Writer Intern, Chrome DevTools\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="7b390-485">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="7b390-485">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
