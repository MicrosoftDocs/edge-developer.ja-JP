---
title: 初心者向けの DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/16/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 8695fe1b2c5d78bd074447acd26a1f01a5833b2d
ms.sourcegitcommit: 8bfa239274e7a4856b961b9cf163b08d96463c10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "10581588"
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

# <span data-ttu-id="c4867-103">初心者向けの DevTools: HTML と DOM の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="c4867-103">DevTools for Beginners: Get Started with HTML and the DOM</span></span>   

<span data-ttu-id="c4867-104">これは、web 開発の基礎について説明する一連のチュートリアルの最初のものです。</span><span class="sxs-lookup"><span data-stu-id="c4867-104">This is the first in a series of tutorials that teach you the basics of web development.</span></span>  <span data-ttu-id="c4867-105">また、生産性を向上させるための、Microsoft Edge DevTools という web 開発者ツールのセットについても説明します。</span><span class="sxs-lookup"><span data-stu-id="c4867-105">You will also learn about a set of web developer tools called Microsoft Edge DevTools that can increase your productivity.</span></span>  

<span data-ttu-id="c4867-106">この特定のチュートリアルでは、HTML と DOM について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4867-106">In this particular tutorial, you learn about HTML and the DOM.</span></span>  <span data-ttu-id="c4867-107">HTML は、web 開発の中核となるテクノロジの1つです。</span><span class="sxs-lookup"><span data-stu-id="c4867-107">HTML is one of the core technologies of web development.</span></span>  <span data-ttu-id="c4867-108">これは、web ページの構造とコンテンツを制御するための言語です。</span><span class="sxs-lookup"><span data-stu-id="c4867-108">It is the language that controls the structure and content of webpages.</span></span>  <span data-ttu-id="c4867-109">DOM は web ページの構造とコンテンツにも関連していますが、詳細については後で説明します。</span><span class="sxs-lookup"><span data-stu-id="c4867-109">The DOM is also related to the structure and content of webpages, but you'll learn more about that later.</span></span>  

## <span data-ttu-id="c4867-110">目標</span><span class="sxs-lookup"><span data-stu-id="c4867-110">Goals</span></span>   

<span data-ttu-id="c4867-111">独自の web サイトを実際に構築することで、web 開発について学習します。</span><span class="sxs-lookup"><span data-stu-id="c4867-111">You are going to learn web development by actually building your own website.</span></span>  <span data-ttu-id="c4867-112">*初心者向けの Devtools*でチュートリアルをすべて完了するまで、完成したサイトは**図 1**のようになります。</span><span class="sxs-lookup"><span data-stu-id="c4867-112">By the time you complete all of the tutorials in the *DevTools for Beginners* series, your finished site will look like **Figure 1**.</span></span>  

> ##### <span data-ttu-id="c4867-113">図 1</span><span class="sxs-lookup"><span data-stu-id="c4867-113">Figure 1</span></span>  
> <span data-ttu-id="c4867-114">完成したサイト</span><span class="sxs-lookup"><span data-stu-id="c4867-114">The finished site</span></span>  
> ![完成したサイト][ImageHtmlFinished]  

<span data-ttu-id="c4867-116">このチュートリアルを終了すると、次のことがわかります。</span><span class="sxs-lookup"><span data-stu-id="c4867-116">By the end of this tutorial, you will understand:</span></span>  

*   <span data-ttu-id="c4867-117">HTML と DOM は、web ページに表示されるコンテンツを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4867-117">How HTML and the DOM create the content that you see on webpages.</span></span>  
*   <span data-ttu-id="c4867-118">Microsoft Edge の DevTools を使って、HTML と DOM の変更を試す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4867-118">How Microsoft Edge DevTools can help you experiment with HTML and DOM changes.</span></span>  
*   <span data-ttu-id="c4867-119">HTML と DOM の違い。</span><span class="sxs-lookup"><span data-stu-id="c4867-119">The difference between HTML and the DOM.</span></span>  

<span data-ttu-id="c4867-120">実際の web サイトも用意されています。</span><span class="sxs-lookup"><span data-stu-id="c4867-120">You'll also have a real website!</span></span>  <span data-ttu-id="c4867-121">このサイトを使って、履歴書やブログを主催することができます。</span><span class="sxs-lookup"><span data-stu-id="c4867-121">You can use this site to host your resume or blog.</span></span>  

## <span data-ttu-id="c4867-122">前提条件</span><span class="sxs-lookup"><span data-stu-id="c4867-122">Prerequisites</span></span>   

<span data-ttu-id="c4867-123">このチュートリアルを実行する前に、次の前提条件を完了してください。</span><span class="sxs-lookup"><span data-stu-id="c4867-123">Before attempting this tutorial, complete the following prerequisites:</span></span>  

*   <span data-ttu-id="c4867-124">HTML に慣れていない場合は、「 [html の概要][MDNGettingStartedHtml]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4867-124">If you're unfamiliar with HTML, read [Getting Started with HTML][MDNGettingStartedHtml].</span></span>  
*   <span data-ttu-id="c4867-125">[Microsoft Edge][MicrosoftEdgeInsider] web ブラウザーをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c4867-125">Download the [Microsoft Edge][MicrosoftEdgeInsider] web browser.</span></span>  <span data-ttu-id="c4867-126">このチュートリアルでは、microsoft edge DevTools と呼ばれる web 開発ツールのセットを使用して、Microsoft Edge に組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="c4867-126">This tutorial uses a set of web development tools, called the Microsoft Edge DevTools, that are built into Microsoft Edge.</span></span>  

## <span data-ttu-id="c4867-127">コードを設定する</span><span class="sxs-lookup"><span data-stu-id="c4867-127">Set up your code</span></span>   

<span data-ttu-id="c4867-128">このサイトは、「エラー」と呼ばれるオンラインコードエディターで作成します。</span><span class="sxs-lookup"><span data-stu-id="c4867-128">You're going to build your site in an online code editor called Glitch.</span></span>  

1.  <span data-ttu-id="c4867-129">[ソースコード][GlitchAlluringShockIndex]を開きます。</span><span class="sxs-lookup"><span data-stu-id="c4867-129">Open the [source code][GlitchAlluringShockIndex].</span></span>  <span data-ttu-id="c4867-130">このタブは、このチュートリアル全体で [**エディター] タブ**と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c4867-130">This tab will be called the **editor tab** throughout this tutorial.</span></span>  
    > ##### <span data-ttu-id="c4867-131">図 2</span><span class="sxs-lookup"><span data-stu-id="c4867-131">Figure 2</span></span>  
    > <span data-ttu-id="c4867-132">[エディター] タブ</span><span class="sxs-lookup"><span data-stu-id="c4867-132">The editor tab</span></span>  
    > ![[エディター] タブ][ImageHtmlSetup1]  

1.  <span data-ttu-id="c4867-134">[ **Alluring-ショック] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="c4867-134">Click **alluring-shock**.</span></span>  <span data-ttu-id="c4867-135">[プロジェクトのオプション] メニューが、左上隅に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4867-135">The Project Options menu opens in the top-left corner.</span></span>  
    
    > #### <span data-ttu-id="c4867-136">図 3</span><span class="sxs-lookup"><span data-stu-id="c4867-136">Figure 3</span></span>  
    > <span data-ttu-id="c4867-137">[プロジェクトのオプション] メニュー</span><span class="sxs-lookup"><span data-stu-id="c4867-137">The Project Options menu</span></span>  
    > ![[プロジェクトのオプション] メニュー][ImageHtmlSetup2]  
    
1.  <span data-ttu-id="c4867-139">[ **Remix Project**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4867-139">Click **Remix Project**.</span></span>  <span data-ttu-id="c4867-140">エラー編集可能なプロジェクトのコピーを作成して、プロジェクトの新しい名前をランダムに生成します。</span><span class="sxs-lookup"><span data-stu-id="c4867-140">Glitch creates a copy of the project that you can edit and randomly generates a new name for the project.</span></span>  <span data-ttu-id="c4867-141">コンテンツは以前と同じです。</span><span class="sxs-lookup"><span data-stu-id="c4867-141">The content is the same as before.</span></span>  
    
    > ##### <span data-ttu-id="c4867-142">図 4</span><span class="sxs-lookup"><span data-stu-id="c4867-142">Figure 4</span></span>  
    > <span data-ttu-id="c4867-143">Remixed プロジェクト</span><span class="sxs-lookup"><span data-stu-id="c4867-143">The remixed project</span></span>  
    > ![Remixed プロジェクト][ImageHtmlSetup3]  
    
1.  <span data-ttu-id="c4867-145">このシリーズの次のチュートリアルを実行する場合は、[**サインイン**] をクリックして、GitHub または Facebook アカウントでエラーにサインインします。</span><span class="sxs-lookup"><span data-stu-id="c4867-145">If you plan on completing the next tutorial in this series, click **Sign In** and sign in to Glitch with your GitHub or Facebook account.</span></span>  <span data-ttu-id="c4867-146">サインインしない場合は、[編集] タブを閉じると、このプロジェクトを編集できなくなります。</span><span class="sxs-lookup"><span data-stu-id="c4867-146">If you don't sign in you will lose the ability to edit this project once you close the editing tab.</span></span>  
1.  <span data-ttu-id="c4867-147">[**表示**] をクリックして、**新しいウィンドウで**を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4867-147">Click **Show** and select **In a New Window**.</span></span>  <span data-ttu-id="c4867-148">新しいタブが開き、実際のページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4867-148">A new tab opens, showing you the live page.</span></span>  <span data-ttu-id="c4867-149">このタブは、このチュートリアル全体で「**ライブ」タブ**と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c4867-149">This tab will be called the **live tab** throughout this tutorial.</span></span>  
    
    > ##### <span data-ttu-id="c4867-150">図 5</span><span class="sxs-lookup"><span data-stu-id="c4867-150">Figure 5</span></span>  
    > <span data-ttu-id="c4867-151">[ライブ] タブ</span><span class="sxs-lookup"><span data-stu-id="c4867-151">The live tab</span></span>  
    > ![[ライブ] タブ][ImageHtmlSetup4]  
    
## <span data-ttu-id="c4867-153">コンテンツを追加する</span><span class="sxs-lookup"><span data-stu-id="c4867-153">Add content</span></span>   

<span data-ttu-id="c4867-154">サイトは非常に空です。</span><span class="sxs-lookup"><span data-stu-id="c4867-154">Your site is pretty empty.</span></span>  <span data-ttu-id="c4867-155">コンテンツを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c4867-155">Follow the steps below to add some content to it!</span></span>  

1.  <span data-ttu-id="c4867-156">[**エディター] タブ**で、を `<!-- You're "About Me" will go here.  -->` に置き換え `<h1>About Me</h1>` ます。</span><span class="sxs-lookup"><span data-stu-id="c4867-156">In the **editor tab**, replace `<!-- You're "About Me" will go here.  -->` with `<h1>About Me</h1>`.</span></span>  
    
    ```html
    ...
        ...
        <body>
            <p> Your site!</p>
            <main>
                <h1>About Me</h1>
            </main>
            ...
        ...
    ...
    ```  
    
    > ##### <span data-ttu-id="c4867-157">図 6</span><span class="sxs-lookup"><span data-stu-id="c4867-157">Figure 6</span></span>  
    > <span data-ttu-id="c4867-158">[エディター] タブの新しいコードが強調表示されている</span><span class="sxs-lookup"><span data-stu-id="c4867-158">The new code is highlighted in the editor tab</span></span>  
    > ![[エディター] タブの新しいコードが強調表示されている][ImageHtmlAdd1]  
    
1.  <span data-ttu-id="c4867-160">[**ライブ] タブ**で変更内容を表示します。 テキスト `About Me` がページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4867-160">View your changes in the **live tab**.  The text `About Me` is visible on the page.</span></span>  <span data-ttu-id="c4867-161">要素はセクションの見出しを表すため、テキストの残りの部分よりも大きくなり `<h1>` ます。</span><span class="sxs-lookup"><span data-stu-id="c4867-161">It's larger than the rest of the text, because the `<h1>` element represents a section heading.</span></span>  <span data-ttu-id="c4867-162">Web ブラウザーでは、大きなフォントサイズで見出しが自動的にスタイル設定されます。</span><span class="sxs-lookup"><span data-stu-id="c4867-162">Your web browser automatically styles headings in larger font sizes.</span></span>  
    
    > ##### <span data-ttu-id="c4867-163">図 7</span><span class="sxs-lookup"><span data-stu-id="c4867-163">Figure 7</span></span>  
    > <span data-ttu-id="c4867-164">新しい見出しが [ライブ] タブに表示される</span><span class="sxs-lookup"><span data-stu-id="c4867-164">The new heading is visible in the live tab</span></span>  
    > ![新しい見出しが [ライブ] タブに表示される][ImageHtmlAdd2]  
    
1.  <span data-ttu-id="c4867-166">[**エディター] タブ**に戻り、 `<p>I am learning HTML.  Recent accomplishments:</p>` 配置した位置の下の行に挿入 `<h1>About Me</h1>` します。</span><span class="sxs-lookup"><span data-stu-id="c4867-166">Back in the **editor tab**, insert `<p>I am learning HTML.  Recent accomplishments:</p>` on the line below where you just put `<h1>About Me</h1>`.</span></span>  
    
    ```html
    ...
        ...
        <body>
            <p> Your site!</p>
            <main>
                <h1>About Me</h1>
                <p>I am learning web development.  Recent accomplishments:</p>
            </main>
            ...
        ...
    ...
    ```  

    > ##### <span data-ttu-id="c4867-167">図 8</span><span class="sxs-lookup"><span data-stu-id="c4867-167">Figure 8</span></span>  
    > <span data-ttu-id="c4867-168">[エディター] タブの新しいコードが強調表示されている</span><span class="sxs-lookup"><span data-stu-id="c4867-168">The new code is highlighted in the editor tab</span></span>  
    > ![[エディター] タブの新しいコードが強調表示されている][ImageHtmlAdd3]  
    
1.  <span data-ttu-id="c4867-170">[**ライブ] タブ**で自分の変更内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="c4867-170">View your change in the **live tab**.</span></span>  
1.  <span data-ttu-id="c4867-171">[**エディター] タブ**に戻り、実績のリストを追加します。</span><span class="sxs-lookup"><span data-stu-id="c4867-171">Back in the **editor tab**, add a list of your accomplishments:</span></span>  
    
    ```html
    ...
        ...
            ...
            <p>I am learning web development.  Recent accomplishments:</p>
            <ul>
                <li>Learned how to set up my code in Glitch.</li>
                <li>Added content to my HTML.</li>
                <li>TODO: Learn how to use Microsoft Edge DevTools to experiment with content changes.</li>
                <li>TODO: Learn the difference between HTML and the DOM.</li>
            </ul>
            ...
        ...
    ...
    ```  
    
    > ##### <span data-ttu-id="c4867-172">図 9</span><span class="sxs-lookup"><span data-stu-id="c4867-172">Figure 9</span></span>  
    > <span data-ttu-id="c4867-173">[エディター] タブの新しいコードが強調表示されている</span><span class="sxs-lookup"><span data-stu-id="c4867-173">The new code is highlighted in the editor tab</span></span>  
    > ![[エディター] タブの新しいコードが強調表示されている][ImageHtmlAdd4]  
    
1.  <span data-ttu-id="c4867-175">この場合も、[**ライブ] タブ**に戻り、新しいコンテンツが正しく表示されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c4867-175">Again, go back to the **live tab** to make sure that the new content is displaying correctly.</span></span>  
    
    > ##### <span data-ttu-id="c4867-176">図 10</span><span class="sxs-lookup"><span data-stu-id="c4867-176">Figure 10</span></span>  
    > <span data-ttu-id="c4867-177">[ライブ] タブに新しいリストが表示される</span><span class="sxs-lookup"><span data-stu-id="c4867-177">The new list is visible in the live tab</span></span>  
    > ![[ライブ] タブに新しいリストが表示される][ImageHtmlAdd5]  
    
## <span data-ttu-id="c4867-179">Microsoft Edge DevTools でのコンテンツの変更を試す</span><span class="sxs-lookup"><span data-stu-id="c4867-179">Experiment with content changes in Microsoft Edge DevTools</span></span>   

<span data-ttu-id="c4867-180">大量の HTML を含む大きなページを開発している場合は、変更を確認するために、[エディター] タブと [ライブ] タブの間を前後に移動することが必要になることがあります。特に、ページに何を入力したかがわからない場合は、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="c4867-180">If you were developing a big page with a lot of HTML, you can imagine that it might be somewhat tedious to go back-and-forth between the editor tab and the live tab hundreds of times in order to see your changes, especially if you weren't sure what exactly to put on the page.</span></span>  <span data-ttu-id="c4867-181">Microsoft Edge の DevTools を使うと、ライブタブを残したまま、コンテンツの変更を試すことができます。</span><span class="sxs-lookup"><span data-stu-id="c4867-181">Microsoft Edge DevTools can help you experiment with content changes without ever leaving the live tab.</span></span>  

### <span data-ttu-id="c4867-182">HTML と DOM の違いについて</span><span class="sxs-lookup"><span data-stu-id="c4867-182">Learn the difference between HTML and the DOM</span></span>   

<span data-ttu-id="c4867-183">Microsoft Edge DevTools からコンテンツの編集を開始する前に、HTML と DOM の違いについて理解しておくと役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c4867-183">Before you start editing your content from Microsoft Edge DevTools, it's helpful to understand the difference between HTML and the DOM.</span></span>  <span data-ttu-id="c4867-184">次のような方法で学ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="c4867-184">The best way to learn is by example:</span></span>  

1.  <span data-ttu-id="c4867-185">[**ライブ] タブ**に移動します。 ページの下部にテキストが表示され `A new element!?!` ます。</span><span class="sxs-lookup"><span data-stu-id="c4867-185">Go to the **live tab**.  At the bottom of your page you see the text `A new element!?!`.</span></span>  
    
    > ###### <span data-ttu-id="c4867-186">図 11</span><span class="sxs-lookup"><span data-stu-id="c4867-186">Figure 11</span></span>  
    > <span data-ttu-id="c4867-187">ページの下部にテキストが `A new element!?!` 表示される</span><span class="sxs-lookup"><span data-stu-id="c4867-187">At the bottom of the page the text `A new element!?!` can be seen</span></span>  
    > ![ページの下部に新しい要素としてテキストを入力!?!][ImageHtmlDom1]  
    
1.  <span data-ttu-id="c4867-190">[**エディター] タブ**に戻り、のテキストを検索し `index.html` ます。</span><span class="sxs-lookup"><span data-stu-id="c4867-190">Go back to the **editor tab** and try to find this text in `index.html`.</span></span>  <span data-ttu-id="c4867-191">そうではありません。</span><span class="sxs-lookup"><span data-stu-id="c4867-191">It's not there!</span></span>  
    
    > ##### <span data-ttu-id="c4867-192">図 12</span><span class="sxs-lookup"><span data-stu-id="c4867-192">Figure 12</span></span>  
    > <span data-ttu-id="c4867-193">謎のテキスト `A new element!?!` が見つからない</span><span class="sxs-lookup"><span data-stu-id="c4867-193">The mystery text `A new element!?!` is nowhere to be found in</span></span> `index.html`  
    > ![新しい要素の謎のテキスト!?!][ImageHtmlDom2]  
    
1.  <span data-ttu-id="c4867-196">[**ライブ] タブ**に戻り、右クリックし `A new element!?!` て [**検査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4867-196">Go back to the **live tab**, right-click `A new element!?!`, and select **Inspect**.</span></span>  
    
    > ##### <span data-ttu-id="c4867-197">図 13</span><span class="sxs-lookup"><span data-stu-id="c4867-197">Figure 13</span></span>  
    > <span data-ttu-id="c4867-198">一部のテキストを検査する</span><span class="sxs-lookup"><span data-stu-id="c4867-198">Inspecting some text</span></span>  
    > ![一部のテキストを検査する][ImageHtmlDom3]  
    
    <span data-ttu-id="c4867-200">DevTools はページの横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4867-200">DevTools opens up alongside your page.</span></span>  `<div>A new element!?!</div>` <span data-ttu-id="c4867-201">が青色で強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="c4867-201">is highlighted blue.</span></span>  <span data-ttu-id="c4867-202">DevTools のこの構造は HTML と同じような外観ですが、実際には**DOM ツリー**です。</span><span class="sxs-lookup"><span data-stu-id="c4867-202">Although this structure in DevTools looks like your HTML, it is actually the **DOM Tree**.</span></span>  
    
    > ##### <span data-ttu-id="c4867-203">図 14</span><span class="sxs-lookup"><span data-stu-id="c4867-203">Figure 14</span></span>  
    > <span data-ttu-id="c4867-204">ページの横に DevTools が開かれている</span><span class="sxs-lookup"><span data-stu-id="c4867-204">DevTools is open alongside the page</span></span>  
    > ![ページの横に DevTools が開かれている][ImageHtmlDom4]  
    
<span data-ttu-id="c4867-206">ページが読み込まれると、ブラウザーは HTML を使ってページの*最初*のコンテンツを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4867-206">When your page loads, the browser takes your HTML to create the *initial* content of the page.</span></span>  <span data-ttu-id="c4867-207">DOM は、時間の経過と共に変化する可能性があるページの*現在*のコンテンツを表します。</span><span class="sxs-lookup"><span data-stu-id="c4867-207">The DOM represents the *current* content of the page, which can change over time.</span></span>  <span data-ttu-id="c4867-208">`<div>A new element!?!</div>`HTML の下部にタグがあるため、謎のコンテンツがページに追加され `<script src="new.js"></script>` ます。</span><span class="sxs-lookup"><span data-stu-id="c4867-208">The mysterious `<div>A new element!?!</div>` content is added to your page because of the `<script src="new.js"></script>` tag at the bottom of your HTML.</span></span>  <span data-ttu-id="c4867-209">このタグを使うと、JavaScript コードが実行されます。</span><span class="sxs-lookup"><span data-stu-id="c4867-209">This tag causes some JavaScript code to run.</span></span>  <span data-ttu-id="c4867-210">JavaScript の詳細については、後のチュートリアルで説明しますが、ここでは、ページのコンテンツを変更できるプログラミング言語と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="c4867-210">You'll learn more about JavaScript in a later tutorial, but for now think of it as a programming language that can change the content of your page.</span></span>  <span data-ttu-id="c4867-211">この例では、JavaScript コードが `<div>A new element!?!</div>` ページに追加されています。</span><span class="sxs-lookup"><span data-stu-id="c4867-211">In this particular case, JavaScript code adds `<div>A new element!?!</div>` to your page.</span></span>  <span data-ttu-id="c4867-212">そのため、この謎のテキストは、実際のページには表示されますが、HTML では表示されません。</span><span class="sxs-lookup"><span data-stu-id="c4867-212">That is why this mystery text is visible on your live page, but not in your HTML.</span></span>  

### <span data-ttu-id="c4867-213">DOM を編集する</span><span class="sxs-lookup"><span data-stu-id="c4867-213">Edit the DOM</span></span>   

<span data-ttu-id="c4867-214">ライブタブを閉じずに、コンテンツの変更をすばやく試す場合は、DevTools をお試しください。</span><span class="sxs-lookup"><span data-stu-id="c4867-214">If you want to quickly experiment with content changes without ever leaving the live tab, try DevTools.</span></span>  

1.  <span data-ttu-id="c4867-215">DevTools で右クリックし、 `Your site!` [ **HTML として編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4867-215">In DevTools, right-click `Your site!` and select **Edit as HTML**.</span></span>  

    > ##### <span data-ttu-id="c4867-216">図 15</span><span class="sxs-lookup"><span data-stu-id="c4867-216">Figure 15</span></span>  
    > <span data-ttu-id="c4867-217">HTML としてのノードの編集</span><span class="sxs-lookup"><span data-stu-id="c4867-217">Editing the node as HTML</span></span>  
    > ![HTML としてのノードの編集][ImageHtmlEdit1]  
    
1.  <span data-ttu-id="c4867-219">`<p>Your site!</p>`以下のコードで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c4867-219">Replace `<p>Your site!</p>` with the code below.</span></span>  
    
    ```html
    ...
        ...
            ...
            <header>
                <p><b>Welcome to my site!</b></p>
                <button>Download my resume</button>
            </header>
            ...
        ...
    ...
    ```  
    
    > ##### <span data-ttu-id="c4867-220">図 16</span><span class="sxs-lookup"><span data-stu-id="c4867-220">Figure 16</span></span>  
    > <span data-ttu-id="c4867-221">HTML としてのノードの編集</span><span class="sxs-lookup"><span data-stu-id="c4867-221">Editing the node as HTML</span></span>  
    > ![HTML としてのノードの編集][ImageHtmlEdit2]  
    
1.  <span data-ttu-id="c4867-223">`Control` + `Enter` \ (Windows \) または `Command` + `Enter` \ (macOS \) を押して変更内容を保存するか、ボックスの外側をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4867-223">Press `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\) to save your changes, or click outside of the box.</span></span>  <span data-ttu-id="c4867-224">変更は、ページのライブビューに自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4867-224">Your changes automatically show up in the live view of your page.</span></span>  <span data-ttu-id="c4867-225">テキスト `Your site!` が新しいコンテンツに置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="c4867-225">The text `Your site!` has been replaced with the new content.</span></span>  
    
    > ##### <span data-ttu-id="c4867-226">図 17</span><span class="sxs-lookup"><span data-stu-id="c4867-226">Figure 17</span></span>  
    > <span data-ttu-id="c4867-227">ページ上の新しいコンテンツがすぐに表示される</span><span class="sxs-lookup"><span data-stu-id="c4867-227">The new content shows up immediately on the page</span></span>  
    > ![ページ上の新しいコンテンツがすぐに表示される][ImageHtmlEdit3]  
    
<span data-ttu-id="c4867-229">このワークフローは、コンテンツの変更を試す場合にのみ適しています。</span><span class="sxs-lookup"><span data-stu-id="c4867-229">This workflow is only good for experimenting with content changes.</span></span>  <span data-ttu-id="c4867-230">ページを再度読み込むか、タブを閉じると、変更内容は永久に失われます。</span><span class="sxs-lookup"><span data-stu-id="c4867-230">If you reload the page or close the tab, your changes will be gone forever.</span></span>  <span data-ttu-id="c4867-231">このワークフローを使用していて、変更を保存する場合は、それらの変更を手動で HTML にコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4867-231">If you're using this workflow and you want to save your changes, you need to manually copy those changes over to your HTML.</span></span>  <span data-ttu-id="c4867-232">次のいくつかのセクションでは、DOM ツリーからコンテンツを変更するその他の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4867-232">The next couple of sections show you some more ways that you can change content from the DOM Tree.</span></span>  

## <span data-ttu-id="c4867-233">ノードの順序を変更する</span><span class="sxs-lookup"><span data-stu-id="c4867-233">Reorder nodes</span></span>   

<span data-ttu-id="c4867-234">DOM ノードの順序を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="c4867-234">You can also change the order of DOM nodes.</span></span>  <span data-ttu-id="c4867-235">たとえば、web ページでは、ナビゲーションメニューは一番下に近い場所にあります。</span><span class="sxs-lookup"><span data-stu-id="c4867-235">For example, on your web page the navigation menu is near the bottom.</span></span>  <span data-ttu-id="c4867-236">一番上に移動するには:</span><span class="sxs-lookup"><span data-stu-id="c4867-236">To move it to the top:</span></span>  

1.  <span data-ttu-id="c4867-237">`<nav>`DevTools の**DOM ツリー**でノードを見つけます。</span><span class="sxs-lookup"><span data-stu-id="c4867-237">Find the `<nav>` node in the **DOM Tree** of DevTools.</span></span>  
    
    > ##### <span data-ttu-id="c4867-238">図18</span><span class="sxs-lookup"><span data-stu-id="c4867-238">Figure 18</span></span>  
    > <span data-ttu-id="c4867-239">DevTools でナビゲーションノードが青色で強調表示されている</span><span class="sxs-lookup"><span data-stu-id="c4867-239">The nav node is highlighted blue in DevTools</span></span>  
    > ![DevTools でナビゲーションノードが青色で強調表示されている][ImageHtmlReorder1]  
    
1.  <span data-ttu-id="c4867-241">ノードを `<nav>` 一番上にドラッグして、ノードの下にある最初の子にし `<body>` ます。</span><span class="sxs-lookup"><span data-stu-id="c4867-241">Drag the `<nav>` node to the top, so that it's the first child below the `<body>` node.</span></span>  
    > ##### <span data-ttu-id="c4867-242">図19</span><span class="sxs-lookup"><span data-stu-id="c4867-242">Figure 19</span></span>  
    > <span data-ttu-id="c4867-243">ナビゲーションノードを一番上にドラッグする</span><span class="sxs-lookup"><span data-stu-id="c4867-243">Dragging the nav node to the top</span></span>  
    > ![ナビゲーションノードを一番上にドラッグする][ImageHtmlReorder2]  
    
    <span data-ttu-id="c4867-245">`<nav>`これで、ノードがページの上部に表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c4867-245">The `<nav>` node is now displaying at the top of your page.</span></span>  
    
    > ##### <span data-ttu-id="c4867-246">図20</span><span class="sxs-lookup"><span data-stu-id="c4867-246">Figure 20</span></span>  
    > <span data-ttu-id="c4867-247">ナビゲーションノードはページの一番上にあります</span><span class="sxs-lookup"><span data-stu-id="c4867-247">The nav node is at the top of the page</span></span>  
    > ![ナビゲーションノードはページの一番上にあります][ImageHtmlReorder3]  
    
### <span data-ttu-id="c4867-249">ノードを削除する</span><span class="sxs-lookup"><span data-stu-id="c4867-249">Delete a node</span></span>   

<span data-ttu-id="c4867-250">DOM ツリーからノードを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="c4867-250">You can also remove nodes from the DOM Tree.</span></span>  

1.  <span data-ttu-id="c4867-251">**DOM ツリー**でをクリックし `<div>A new element!?!</div>` ます。</span><span class="sxs-lookup"><span data-stu-id="c4867-251">In the **DOM Tree**, click `<div>A new element!?!</div>`.</span></span>  <span data-ttu-id="c4867-252">DevTools は、ノード青色を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="c4867-252">DevTools highlights the node blue.</span></span>  
    
    > ##### <span data-ttu-id="c4867-253">図21</span><span class="sxs-lookup"><span data-stu-id="c4867-253">Figure 21</span></span>  
    > <span data-ttu-id="c4867-254">削除するノードの選択</span><span class="sxs-lookup"><span data-stu-id="c4867-254">Selecting the node to be deleted</span></span>  
    > ![削除するノードの選択][ImageHtmlDelete1]  
    
1.  <span data-ttu-id="c4867-256">キーボードの `Delete` キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c4867-256">Press the `Delete` key on your keyboard.</span></span>  <span data-ttu-id="c4867-257">`<div>A new element!?!</div>`ノードが DOM ツリーから削除されます。</span><span class="sxs-lookup"><span data-stu-id="c4867-257">The `<div>A new element!?!</div>` node is removed from your DOM Tree.</span></span>  
    
    > ##### <span data-ttu-id="c4867-258">図22</span><span class="sxs-lookup"><span data-stu-id="c4867-258">Figure 22</span></span>  
    > <span data-ttu-id="c4867-259">ノードが削除されました</span><span class="sxs-lookup"><span data-stu-id="c4867-259">The node has been deleted</span></span>  
    > ![ノードが削除されました][ImageHtmlDelete2]  
    
## <span data-ttu-id="c4867-261">変更内容をコピーする</span><span class="sxs-lookup"><span data-stu-id="c4867-261">Copy your changes</span></span>   

<span data-ttu-id="c4867-262">まもなく完了です。</span><span class="sxs-lookup"><span data-stu-id="c4867-262">You're almost done.</span></span>  <span data-ttu-id="c4867-263">DevTools でページにいくつか変更を加えましたが、ソースコードにはまだ保存されていません。</span><span class="sxs-lookup"><span data-stu-id="c4867-263">You've made a few changes to your page in DevTools, but they're not yet saved to your source code.</span></span>  

1.  <span data-ttu-id="c4867-264">**[ライブ] タブ**を更新します。 DOM ツリーで行った変更が非表示になります。</span><span class="sxs-lookup"><span data-stu-id="c4867-264">Refresh your **live tab**.  The changes that you made in the DOM Tree disappear.</span></span>  <span data-ttu-id="c4867-265">特に、テキストは `Your site!` ページの一番上に表示され、テキストは `A new element!?!` 下に戻ります。</span><span class="sxs-lookup"><span data-stu-id="c4867-265">In particular, the text `Your site!` returns to the top of the page, and the text `A new element!?!` returns to the bottom.</span></span>  
    
    > ##### <span data-ttu-id="c4867-266">図23</span><span class="sxs-lookup"><span data-stu-id="c4867-266">Figure 23</span></span>  
    > <span data-ttu-id="c4867-267">行った変更内容が失われる</span><span class="sxs-lookup"><span data-stu-id="c4867-267">The changes that you've made are gone</span></span>  
    > ![行った変更内容が失われる][ImageHtmlCopy1]  

1.  <span data-ttu-id="c4867-269">以下のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="c4867-269">Copy the code below.</span></span>  
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="utf-8">
            <meta http-equiv="X-UA-Compatible" content="IE=edge">
            <meta name="viewport" content="width=device-width, initial-scale=1">
        </head>
        <body>
            <header>
                <p>Welcome to my site!</p>
            </header>
            <nav>
                <ul>
                    <li><a href="/">Home</a></li>
                    <li><a href="/contact.html">Contact</a></li>
                </ul>
            </nav>
            <main>
                <h1>About Me</h1>
                <p>I am learning web development.  Recent accomplishments:</p>
                <ul>
                    <li>Learned how to set up my code in Glitch.</li>
                    <li>Added content to my HTML.</li>
                    <li>Learned how to use Microsoft Edge DevTools to experiment with content changes.</li>
                    <li>Learned the difference between HTML and the DOM.</li>
                </ul>
            </main>
        </body>
    </html>
    ```  
      
1.  <span data-ttu-id="c4867-270">[**エディター] タブ**に戻り、ファイルの内容を `index.html` コピーしたコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c4867-270">Go back to the **editor tab** and replace the contents of your `index.html` file with the code that you just copied.</span></span>  
    
    > ##### <span data-ttu-id="c4867-271">図24</span><span class="sxs-lookup"><span data-stu-id="c4867-271">Figure 24</span></span>  
    > <span data-ttu-id="c4867-272">ファイルの `index.html` 外観</span><span class="sxs-lookup"><span data-stu-id="c4867-272">How your `index.html` file should look</span></span>  
    > ![Index ファイルの外観][ImageHtmlCopy2]  
    
## <span data-ttu-id="c4867-274">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c4867-274">Next steps</span></span>   

*   <span data-ttu-id="c4867-275">このシリーズの次のチュートリアルでは、「 [CSS の使用を開始][DevToolsBeginnersCss]する」を参照して、ページのスタイルを作成する方法と、Microsoft Edge devtools でスタイルの変更を試す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4867-275">Complete the next tutorial in this series, [Get Started with CSS][DevToolsBeginnersCss], to learn how to style your page and experiment with style changes in Microsoft Edge DevTools.</span></span>  
*   <span data-ttu-id="c4867-276">DOM の詳細について[は、「dom の概要][MDNIntroductionDom]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4867-276">Read [Introduction to the DOM][MDNIntroductionDom] to learn more about the DOM.</span></span>  
*   <span data-ttu-id="c4867-277">Web[開発の概要][CourseraIntroductionToWebDevelopment]など、実践的な web 開発環境を実現するコースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c4867-277">Check out a course like [Introduction to Web Development][CourseraIntroductionToWebDevelopment] to get more hands-on web development experience.</span></span>  

<!--- image links --->  

[ImageHtmlFinished]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-finished.msft.png "図 1: 完成したサイト"  
[ImageHtmlSetup1]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-setup1.msft.png "図 2: [エディター] タブ"  
[ImageHtmlSetup2]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-setup2.msft.png "図 3: [プロジェクトのオプション] メニュー"  
[ImageHtmlSetup3]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-setup3.msft.png "図 4: 再混在プロジェクト"  
[ImageHtmlSetup4]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-setup4.msft.png "図 5: [ライブ] タブ"  
[ImageHtmlAdd1]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-add1.msft.png "図 6: 新しいコードが [エディター] タブで強調表示される"  
[ImageHtmlAdd2]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-add2.msft.png "図 7: 新しい見出しが [ライブ] タブに表示される"  
[ImageHtmlAdd3]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-add3.msft.png "図 8: 新しいコードが [エディター] タブで強調表示される"  
[ImageHtmlAdd4]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-add4.msft.png "図 9: 新しいコードが [エディター] タブで強調表示されている"  
[ImageHtmlAdd5]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-add5.msft.png "図 10: 新しいリストが [ライブ] タブに表示される"  
[ImageHtmlDom1]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-dom1.msft.png "図 11: ページの下部に新しい要素としてテキストを入力!?!表示可能"  
[ImageHtmlDom2]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-dom2.msft.png "図 12: 新しい要素である謎のテキスト!?!は .html で見つからない"  
[ImageHtmlDom3]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-dom3.msft.png "図 13: 一部のテキストを検査する"  
[ImageHtmlDom4]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-dom4.msft.png "図 14: DevTools がページと共に開かれている"  
[ImageHtmlEdit1]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-edit1.msft.png "図 15: HTML としてノードを編集する"  
[ImageHtmlEdit2]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-edit2.msft.png "図 16: ノードを HTML として編集する"  
[ImageHtmlEdit3]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-edit3.msft.png "図 17: 新しいコンテンツがページにすぐに表示される"  
[ImageHtmlReorder1]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-reorder1.msft.png "図 18: DevTools でナビゲーションノードが強調表示されている"  
[ImageHtmlReorder2]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-reorder2.msft.png "図 19: ナビゲーションノードを一番上にドラッグする"  
[ImageHtmlReorder3]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-reorder3.msft.png "図 20: ナビゲーションノードはページの一番上にあります。"  
[ImageHtmlDelete1]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-delete1.msft.png "図 21: 削除するノードの選択"  
[ImageHtmlDelete2]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-delete2.msft.png "図 22: ノードが削除されている"  
[ImageHtmlCopy1]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-copy1.msft.png "図 23: 行った変更内容が失われる"  
[ImageHtmlCopy2]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-copy2.msft.png "図 24: html ファイルがどのように表示されるようにするか"  

<!--- links --->  

[DevToolsBeginnersCss]: /microsoft-edge/devtools-guide-chromium/beginners/css "初心者向けの DevTools: CSS の使用を開始する"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge Insider"  

[CourseraIntroductionToWebDevelopment]: https://www.coursera.org/learn/web-development "Web 開発の概要 |Coursera"  

[GlitchAlluringShockIndex]: https://glitch.com/edit/#!/alluring-shock?path=index.html "alluring-ショック |故障"  

[MDNGettingStartedHtml]: https://developer.mozilla.org/docs/Learn/HTML/Introduction_to_HTML/Getting_started "HTML の概要 |MDN"  
[MDNIntroductionDom]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM の概要 |MDN"  

> [!NOTE]
> <span data-ttu-id="c4867-308">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4867-308">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c4867-309">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/beginners/html)にあり、 [Katherine Jackson][KatherineJackson] \ (テクニカルライターインターン、Chrome devtools) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="c4867-309">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/beginners/html) and is authored by [Katherine Jackson][KatherineJackson] \(Technical Writer Intern, Chrome DevTools\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="c4867-311">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="c4867-311">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
