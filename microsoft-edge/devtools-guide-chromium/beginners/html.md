---
description: HTML と DOM を使ってみる
title: '初心者向けの DevTools: HTML と DOM の使用を開始する'
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: f17b68845ef746fa2612cdf4d02cc7e1003baabb
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125301"
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

# <span data-ttu-id="33fa7-104">初心者向けの DevTools: HTML と DOM の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="33fa7-104">DevTools for beginners: Get started with HTML and the DOM</span></span>  

<span data-ttu-id="33fa7-105">これは、web 開発の基礎について説明する一連のチュートリアルの最初のものです。</span><span class="sxs-lookup"><span data-stu-id="33fa7-105">This is the first in a series of tutorials that teach you the basics of web development.</span></span>  <span data-ttu-id="33fa7-106">また、生産性を向上させるための、Microsoft Edge DevTools という web 開発者ツールのセットについても説明します。</span><span class="sxs-lookup"><span data-stu-id="33fa7-106">You will also learn about a set of web developer tools called Microsoft Edge DevTools that can increase your productivity.</span></span>  

<span data-ttu-id="33fa7-107">この特定のチュートリアルでは、HTML と DOM について説明します。</span><span class="sxs-lookup"><span data-stu-id="33fa7-107">In this particular tutorial, you learn about HTML and the DOM.</span></span>  <span data-ttu-id="33fa7-108">HTML は、web 開発の中核となるテクノロジの1つです。</span><span class="sxs-lookup"><span data-stu-id="33fa7-108">HTML is one of the core technologies of web development.</span></span>  <span data-ttu-id="33fa7-109">これは、web ページの構造とコンテンツを制御するための言語です。</span><span class="sxs-lookup"><span data-stu-id="33fa7-109">It is the language that controls the structure and content of webpages.</span></span>  <span data-ttu-id="33fa7-110">DOM は web ページの構造とコンテンツにも関連していますが、詳細については後で説明します。</span><span class="sxs-lookup"><span data-stu-id="33fa7-110">The DOM is also related to the structure and content of webpages, but you'll learn more about that later.</span></span>  

## <span data-ttu-id="33fa7-111">目標</span><span class="sxs-lookup"><span data-stu-id="33fa7-111">Goals</span></span>  

<span data-ttu-id="33fa7-112">独自の web サイトを実際に構築することで、web 開発について学習します。</span><span class="sxs-lookup"><span data-stu-id="33fa7-112">You are going to learn web development by actually building your own website.</span></span>  <span data-ttu-id="33fa7-113">*初心者向けの Devtools*ですべてのチュートリアルを完了すると、次の図のように完成したサイトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-113">By the time you complete all of the tutorials in the *DevTools for Beginners* series, your finished site will look like in the following figure.</span></span>  

:::image type="complex" source="../media/beginners-html-finished.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-finished.msft.png":::
   <span data-ttu-id="33fa7-115">完成したサイト</span><span class="sxs-lookup"><span data-stu-id="33fa7-115">The finished site</span></span>  
:::image-end:::  

<span data-ttu-id="33fa7-116">このチュートリアルを終了すると、次のことがわかります。</span><span class="sxs-lookup"><span data-stu-id="33fa7-116">By the end of this tutorial, you will understand:</span></span>  

*   <span data-ttu-id="33fa7-117">HTML と DOM は、web ページに表示されるコンテンツを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="33fa7-117">How HTML and the DOM create the content that you see on webpages.</span></span>  
*   <span data-ttu-id="33fa7-118">Microsoft Edge の DevTools を使って、HTML と DOM の変更を試す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="33fa7-118">How Microsoft Edge DevTools can help you experiment with HTML and DOM changes.</span></span>  
*   <span data-ttu-id="33fa7-119">HTML と DOM の違い。</span><span class="sxs-lookup"><span data-stu-id="33fa7-119">The difference between HTML and the DOM.</span></span>  

<span data-ttu-id="33fa7-120">実際の web サイトも用意されています。</span><span class="sxs-lookup"><span data-stu-id="33fa7-120">You'll also have a real website!</span></span>  <span data-ttu-id="33fa7-121">このサイトを使って、履歴書やブログを主催することができます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-121">You can use this site to host your resume or blog.</span></span>  

## <span data-ttu-id="33fa7-122">前提条件</span><span class="sxs-lookup"><span data-stu-id="33fa7-122">Prerequisites</span></span>  

<span data-ttu-id="33fa7-123">このチュートリアルを実行する前に、次の前提条件を完了してください。</span><span class="sxs-lookup"><span data-stu-id="33fa7-123">Before attempting this tutorial, complete the following prerequisites:</span></span>  

*   <span data-ttu-id="33fa7-124">HTML に慣れていない場合は、「 [html の概要][MDNGettingStartedHtml]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33fa7-124">If you are unfamiliar with HTML, read [Getting Started with HTML][MDNGettingStartedHtml].</span></span>  
*   <span data-ttu-id="33fa7-125">[Microsoft Edge][MicrosoftEdgeInsider] web ブラウザーをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="33fa7-125">Download the [Microsoft Edge][MicrosoftEdgeInsider] web browser.</span></span>  <span data-ttu-id="33fa7-126">このチュートリアルでは、microsoft edge DevTools と呼ばれる web 開発ツールのセットを使用して、Microsoft Edge に組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="33fa7-126">This tutorial uses a set of web development tools, called the Microsoft Edge DevTools, that are built into Microsoft Edge.</span></span>  

## <span data-ttu-id="33fa7-127">コードを設定する</span><span class="sxs-lookup"><span data-stu-id="33fa7-127">Set up your code</span></span>  

<span data-ttu-id="33fa7-128">サイトは、"エラー" と呼ばれるオンラインコードエディターで作成します。</span><span class="sxs-lookup"><span data-stu-id="33fa7-128">You are going to build your site in an online code editor called Glitch.</span></span>  

1.  <span data-ttu-id="33fa7-129">[ソースコード][GlitchAlluringShockIndex]を開きます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-129">Open the [source code][GlitchAlluringShockIndex].</span></span>  <span data-ttu-id="33fa7-130">このタブは、このチュートリアル全体で [ **エディター] タブ** と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-130">This tab will be called the **editor tab** throughout this tutorial.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup1.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-setup1.msft.png":::
       <span data-ttu-id="33fa7-132">[エディター] タブ</span><span class="sxs-lookup"><span data-stu-id="33fa7-132">The editor tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="33fa7-133">[ **Alluring-ショック**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-133">Choose **alluring-shock**.</span></span>  <span data-ttu-id="33fa7-134">[プロジェクトのオプション] メニューが、左上隅に表示されます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-134">The Project Options menu opens in the top-left corner.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup2.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-setup2.msft.png":::
       <span data-ttu-id="33fa7-136">[プロジェクトのオプション] メニュー</span><span class="sxs-lookup"><span data-stu-id="33fa7-136">The Project Options menu</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="33fa7-137">[ **Remix Project**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-137">Choose **Remix Project**.</span></span>  <span data-ttu-id="33fa7-138">エラー編集可能なプロジェクトのコピーを作成して、プロジェクトの新しい名前をランダムに生成します。</span><span class="sxs-lookup"><span data-stu-id="33fa7-138">Glitch creates a copy of the project that you can edit and randomly generates a new name for the project.</span></span>  <span data-ttu-id="33fa7-139">コンテンツは以前と同じです。</span><span class="sxs-lookup"><span data-stu-id="33fa7-139">The content is the same as before.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup3.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-setup3.msft.png":::
       <span data-ttu-id="33fa7-141">Remixed プロジェクト</span><span class="sxs-lookup"><span data-stu-id="33fa7-141">The remixed project</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="33fa7-142">このシリーズの次のチュートリアルを実行する場合は、[ **サインイン** ] を選択して、GitHub または Facebook アカウントでエラーにサインインします。</span><span class="sxs-lookup"><span data-stu-id="33fa7-142">If you plan on completing the next tutorial in this series, choose **Sign In** and sign in to Glitch with your GitHub or Facebook account.</span></span>  <span data-ttu-id="33fa7-143">サインインしない場合は、[編集] タブを閉じると、このプロジェクトを編集できなくなります。</span><span class="sxs-lookup"><span data-stu-id="33fa7-143">If you don't sign in you will lose the ability to edit this project once you close the editing tab.</span></span>  
1.  <span data-ttu-id="33fa7-144">[ **表示** ] を選択し、 **新しいウィンドウで**を選択します。</span><span class="sxs-lookup"><span data-stu-id="33fa7-144">Choose **Show** and choose **In a New Window**.</span></span>  <span data-ttu-id="33fa7-145">新しいタブが開き、実際のページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-145">A new tab opens, showing you the live page.</span></span>  <span data-ttu-id="33fa7-146">このタブは、このチュートリアル全体で「 **ライブ」タブ** と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-146">This tab will be called the **live tab** throughout this tutorial.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup4.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-setup4.msft.png":::
       <span data-ttu-id="33fa7-148">[ライブ] タブ</span><span class="sxs-lookup"><span data-stu-id="33fa7-148">The live tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="33fa7-149">コンテンツを追加する</span><span class="sxs-lookup"><span data-stu-id="33fa7-149">Add content</span></span>  

<span data-ttu-id="33fa7-150">サイトは非常に空です。</span><span class="sxs-lookup"><span data-stu-id="33fa7-150">Your site is pretty empty.</span></span>  <span data-ttu-id="33fa7-151">コンテンツを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="33fa7-151">Follow the steps below to add some content to it!</span></span>  

1.  <span data-ttu-id="33fa7-152">[ **エディター] タブ**で、を `<!-- You're "About Me" will go here.  -->` に置き換え `<h1>About Me</h1>` ます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-152">In the **editor tab**, replace `<!-- You're "About Me" will go here.  -->` with `<h1>About Me</h1>`.</span></span>  
    
    :::row:::
       :::column span="":::
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
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-add1.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-add1.msft.png":::
             <span data-ttu-id="33fa7-154">[エディター] タブの新しいコードが強調表示されている</span><span class="sxs-lookup"><span data-stu-id="33fa7-154">The new code is highlighted in the editor tab</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="33fa7-155">[ **ライブ] タブ**で変更内容を表示します。 テキスト `About Me` がページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-155">View your changes in the **live tab**.  The text `About Me` is visible on the page.</span></span>  <span data-ttu-id="33fa7-156">要素はセクションの見出しを表すため、テキストの残りの部分よりも大きくなり `<h1>` ます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-156">It's larger than the rest of the text, because the `<h1>` element represents a section heading.</span></span>  <span data-ttu-id="33fa7-157">Web ブラウザーでは、大きなフォントサイズで見出しが自動的にスタイル設定されます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-157">Your web browser automatically styles headings in larger font sizes.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-add2.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-add2.msft.png":::
       <span data-ttu-id="33fa7-159">新しい見出しが [ライブ] タブに表示される</span><span class="sxs-lookup"><span data-stu-id="33fa7-159">The new heading is visible in the live tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="33fa7-160">[ **エディター] タブ**に戻り、 `<p>I am learning HTML.  Recent accomplishments:</p>` 配置した位置の下の行に挿入 `<h1>About Me</h1>` します。</span><span class="sxs-lookup"><span data-stu-id="33fa7-160">Back in the **editor tab**, insert `<p>I am learning HTML.  Recent accomplishments:</p>` on the line below where you just put `<h1>About Me</h1>`.</span></span>  
    
    :::row:::
       :::column span="":::
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
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-add3.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-add3.msft.png":::
             <span data-ttu-id="33fa7-162">更新されたコードが [エディター] タブで強調表示される</span><span class="sxs-lookup"><span data-stu-id="33fa7-162">The updated code is highlighted in the editor tab</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="33fa7-163">[ **ライブ] タブ**で自分の変更内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="33fa7-163">View your change in the **live tab**.</span></span>  
1.  <span data-ttu-id="33fa7-164">[ **エディター] タブ**に戻り、実績のリストを追加します。</span><span class="sxs-lookup"><span data-stu-id="33fa7-164">Back in the **editor tab**, add a list of your accomplishments:</span></span>  
    
    :::row:::
       :::column span="":::
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
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-add4.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-add4.msft.png":::
             <span data-ttu-id="33fa7-166">更新されたコードは [エディター] タブでも強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="33fa7-166">The updated code is also highlighted in the editor tab</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="33fa7-167">この場合も、[ **ライブ] タブ** に戻り、新しいコンテンツが正しく表示されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="33fa7-167">Again, go back to the **live tab** to make sure that the new content is displaying correctly.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-add5.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-add5.msft.png":::
       <span data-ttu-id="33fa7-169">[ライブ] タブに新しいリストが表示される</span><span class="sxs-lookup"><span data-stu-id="33fa7-169">The new list is visible in the live tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="33fa7-170">Microsoft Edge DevTools でのコンテンツの変更を試す</span><span class="sxs-lookup"><span data-stu-id="33fa7-170">Experiment with content changes in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="33fa7-171">大量の HTML を含む大きなページを開発している場合は、変更を確認するために、[エディター] タブと [ライブ] タブの間を前後に移動することが必要になることがあります。特に、ページに何を入力したかがわからない場合は、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="33fa7-171">If you were developing a big page with a lot of HTML, you can imagine that it might be somewhat tedious to go back-and-forth between the editor tab and the live tab hundreds of times in order to see your changes, especially if you weren't sure what exactly to put on the page.</span></span>  <span data-ttu-id="33fa7-172">Microsoft Edge の DevTools を使うと、ライブタブを残したまま、コンテンツの変更を試すことができます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-172">Microsoft Edge DevTools can help you experiment with content changes without ever leaving the live tab.</span></span>  

### <span data-ttu-id="33fa7-173">HTML と DOM の違いについて</span><span class="sxs-lookup"><span data-stu-id="33fa7-173">Learn the difference between HTML and the DOM</span></span>  

<span data-ttu-id="33fa7-174">Microsoft Edge DevTools からコンテンツの編集を開始する前に、HTML と DOM の違いについて理解しておくと役立ちます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-174">Before you start editing your content from Microsoft Edge DevTools, it's helpful to understand the difference between HTML and the DOM.</span></span>  <span data-ttu-id="33fa7-175">次のような方法で学ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-175">The best way to learn is by example:</span></span>  

1.  <span data-ttu-id="33fa7-176">[ **ライブ] タブ**に移動します。 ページの下部にテキストが表示され `A new element!?!` ます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-176">Go to the **live tab**.  At the bottom of your page you see the text `A new element!?!`.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom1.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-dom1.msft.png":::
       <span data-ttu-id="33fa7-179">ページの下部に新しい要素としてテキストを入力!?!</span><span class="sxs-lookup"><span data-stu-id="33fa7-179">At the bottom of the page the text A new element!?!</span></span> <span data-ttu-id="33fa7-180">表示可能</span><span class="sxs-lookup"><span data-stu-id="33fa7-180">can be seen</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="33fa7-181">[ **エディター] タブ** に戻り、のテキストを検索し `index.html` ます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-181">Go back to the **editor tab** and try to find this text in `index.html`.</span></span>  <span data-ttu-id="33fa7-182">そうではありません。</span><span class="sxs-lookup"><span data-stu-id="33fa7-182">It's not there!</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom2.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-dom2.msft.png":::
       <span data-ttu-id="33fa7-185">謎のテキスト `A new element!?!` が見つからない</span><span class="sxs-lookup"><span data-stu-id="33fa7-185">The mystery text `A new element!?!` is nowhere to be found in</span></span> `index.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="33fa7-186">[ **ライブ] タブ**に戻り、右クリックして、[ `A new element!?!` **検査**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-186">Go back to the **live tab**, right-click `A new element!?!`, and choose **Inspect**.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom3.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-dom3.msft.png":::
       <span data-ttu-id="33fa7-188">一部のテキストを検査する</span><span class="sxs-lookup"><span data-stu-id="33fa7-188">Inspecting some text</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="33fa7-189">DevTools はページの横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-189">DevTools opens up alongside your page.</span></span>  `<div>A new element!?!</div>` <span data-ttu-id="33fa7-190">が青色で強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="33fa7-190">is highlighted blue.</span></span>  <span data-ttu-id="33fa7-191">DevTools のこの構造は HTML と同じような外観ですが、実際には **DOM ツリー**です。</span><span class="sxs-lookup"><span data-stu-id="33fa7-191">Although this structure in DevTools looks like your HTML, it is actually the **DOM Tree**.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom4.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-dom4.msft.png":::
       <span data-ttu-id="33fa7-193">ページの横に DevTools が開かれている</span><span class="sxs-lookup"><span data-stu-id="33fa7-193">DevTools is open alongside the page</span></span>  
    :::image-end:::  
    
<span data-ttu-id="33fa7-194">ページが読み込まれると、ブラウザーは HTML を使ってページの *最初* のコンテンツを作成します。</span><span class="sxs-lookup"><span data-stu-id="33fa7-194">When your page loads, the browser takes your HTML to create the *initial* content of the page.</span></span>  <span data-ttu-id="33fa7-195">DOM は、時間の経過と共に変化する可能性があるページの *現在* のコンテンツを表します。</span><span class="sxs-lookup"><span data-stu-id="33fa7-195">The DOM represents the *current* content of the page, which can change over time.</span></span>  <span data-ttu-id="33fa7-196">`<div>A new element!?!</div>`HTML の下部にタグがあるため、謎のコンテンツがページに追加され `<script src="new.js"></script>` ます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-196">The mysterious `<div>A new element!?!</div>` content is added to your page because of the `<script src="new.js"></script>` tag at the bottom of your HTML.</span></span>  <span data-ttu-id="33fa7-197">このタグを使うと、JavaScript コードが実行されます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-197">This tag causes some JavaScript code to run.</span></span>  <span data-ttu-id="33fa7-198">JavaScript の詳細については、後のチュートリアルで説明しますが、ここでは、ページのコンテンツを変更できるプログラミング言語と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-198">You'll learn more about JavaScript in a later tutorial, but for now think of it as a programming language that can change the content of your page.</span></span>  <span data-ttu-id="33fa7-199">この例では、JavaScript コードが `<div>A new element!?!</div>` ページに追加されています。</span><span class="sxs-lookup"><span data-stu-id="33fa7-199">In this particular case, JavaScript code adds `<div>A new element!?!</div>` to your page.</span></span>  <span data-ttu-id="33fa7-200">そのため、この謎のテキストは、実際のページには表示されますが、HTML では表示されません。</span><span class="sxs-lookup"><span data-stu-id="33fa7-200">That is why this mystery text is visible on your live page, but not in your HTML.</span></span>  

### <span data-ttu-id="33fa7-201">DOM を編集する</span><span class="sxs-lookup"><span data-stu-id="33fa7-201">Edit the DOM</span></span>  

<span data-ttu-id="33fa7-202">ライブタブを閉じずに、コンテンツの変更をすばやく試す場合は、DevTools をお試しください。</span><span class="sxs-lookup"><span data-stu-id="33fa7-202">If you want to quickly experiment with content changes without ever leaving the live tab, try DevTools.</span></span>  

1.  <span data-ttu-id="33fa7-203">DevTools で右クリックし、 `Your site!` [ **HTML として編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33fa7-203">In DevTools, right-click `Your site!` and choose **Edit as HTML**.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-edit1.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-edit1.msft.png":::
       <span data-ttu-id="33fa7-205">HTML としてのノードの編集</span><span class="sxs-lookup"><span data-stu-id="33fa7-205">Editing the node as HTML</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="33fa7-206">`<p>Your site!</p>`以下のコードで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-206">Replace `<p>Your site!</p>` with the code below.</span></span>  
    
    :::row:::
       :::column span="":::
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
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-edit2.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-edit2.msft.png":::
             <span data-ttu-id="33fa7-208">HTML としてのノードの更新</span><span class="sxs-lookup"><span data-stu-id="33fa7-208">Updating the node as HTML</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="33fa7-209">変更内容を `Control` + `Enter` 保存するには、\ (Windows, Linux \) または `Command` + `Enter` \ (macOS \) を選択します。または、ボックスの外側をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33fa7-209">Select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\) to save your changes, or click outside of the box.</span></span>  <span data-ttu-id="33fa7-210">変更は、ページのライブビューに自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-210">Your changes automatically show up in the live view of your page.</span></span>  <span data-ttu-id="33fa7-211">テキスト `Your site!` が新しいコンテンツに置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="33fa7-211">The text `Your site!` has been replaced with the new content.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-edit3.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-edit3.msft.png":::
       <span data-ttu-id="33fa7-213">ページ上の新しいコンテンツがすぐに表示される</span><span class="sxs-lookup"><span data-stu-id="33fa7-213">The new content shows up immediately on the page</span></span>  
    :::image-end:::  
    
<span data-ttu-id="33fa7-214">このワークフローは、コンテンツの変更を試す場合にのみ適しています。</span><span class="sxs-lookup"><span data-stu-id="33fa7-214">This workflow is only good for experimenting with content changes.</span></span>  <span data-ttu-id="33fa7-215">ページを再度読み込むか、タブを閉じると、変更内容は永久に失われます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-215">If you reload the page or close the tab, your changes will be gone forever.</span></span>  <span data-ttu-id="33fa7-216">このワークフローを使用していて、変更を保存する場合は、それらの変更を手動で HTML にコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="33fa7-216">If you're using this workflow and you want to save your changes, you need to manually copy those changes over to your HTML.</span></span>  <span data-ttu-id="33fa7-217">次のいくつかのセクションでは、DOM ツリーからコンテンツを変更するその他の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="33fa7-217">The next couple of sections show you some more ways that you can change content from the DOM Tree.</span></span>  

## <span data-ttu-id="33fa7-218">ノードの順序を変更する</span><span class="sxs-lookup"><span data-stu-id="33fa7-218">Reorder nodes</span></span>  

<span data-ttu-id="33fa7-219">DOM ノードの順序を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-219">You can also change the order of DOM nodes.</span></span>  <span data-ttu-id="33fa7-220">たとえば、web ページでは、ナビゲーションメニューは一番下に近い場所にあります。</span><span class="sxs-lookup"><span data-stu-id="33fa7-220">For example, on your web page the navigation menu is near the bottom.</span></span>  <span data-ttu-id="33fa7-221">一番上に移動するには:</span><span class="sxs-lookup"><span data-stu-id="33fa7-221">To move it to the top:</span></span>  

1.  <span data-ttu-id="33fa7-222">`<nav>`DevTools の**DOM ツリー**でノードを見つけます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-222">Find the `<nav>` node in the **DOM Tree** of DevTools.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-reorder1.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-reorder1.msft.png":::
       <span data-ttu-id="33fa7-224">DevTools でナビゲーションノードが青色で強調表示されている</span><span class="sxs-lookup"><span data-stu-id="33fa7-224">The nav node is highlighted blue in DevTools</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="33fa7-225">ノードを `<nav>` 一番上にドラッグして、ノードの下にある最初の子にし `<body>` ます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-225">Drag the `<nav>` node to the top, so that it's the first child below the `<body>` node.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-reorder2.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-reorder2.msft.png":::
             <span data-ttu-id="33fa7-227">ナビゲーションノードを一番上にドラッグする</span><span class="sxs-lookup"><span data-stu-id="33fa7-227">Dragging the nav node to the top</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="33fa7-228">`<nav>`これで、ノードがページの上部に表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="33fa7-228">The `<nav>` node is now displaying at the top of your page.</span></span>  
          
          :::image type="complex" source="../media/beginners-html-reorder3.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-reorder3.msft.png":::
             <span data-ttu-id="33fa7-230">ナビゲーションノードはページの一番上にあります</span><span class="sxs-lookup"><span data-stu-id="33fa7-230">The nav node is at the top of the page</span></span>  
          :::image-end:::  
       :::column-end:::
   :::row-end:::  
    
### <span data-ttu-id="33fa7-231">ノードを削除する</span><span class="sxs-lookup"><span data-stu-id="33fa7-231">Delete a node</span></span>  

<span data-ttu-id="33fa7-232">DOM ツリーからノードを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-232">You can also remove nodes from the DOM Tree.</span></span>  

1.  <span data-ttu-id="33fa7-233">**DOM ツリー**でをクリックし `<div>A new element!?!</div>` ます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-233">In the **DOM Tree**, click `<div>A new element!?!</div>`.</span></span>  <span data-ttu-id="33fa7-234">DevTools は、ノード青色を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="33fa7-234">DevTools highlights the node blue.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-delete1.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-delete1.msft.png":::
       <span data-ttu-id="33fa7-236">削除するノードの選択</span><span class="sxs-lookup"><span data-stu-id="33fa7-236">Selecting the node to be deleted</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="33fa7-237">キーボードの `Delete` キーを押します。</span><span class="sxs-lookup"><span data-stu-id="33fa7-237">Press the `Delete` key on your keyboard.</span></span>  <span data-ttu-id="33fa7-238">`<div>A new element!?!</div>`ノードが DOM ツリーから削除されます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-238">The `<div>A new element!?!</div>` node is removed from your DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-delete2.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-delete2.msft.png":::
       <span data-ttu-id="33fa7-240">ノードが削除されました</span><span class="sxs-lookup"><span data-stu-id="33fa7-240">The node has been deleted</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="33fa7-241">変更内容をコピーする</span><span class="sxs-lookup"><span data-stu-id="33fa7-241">Copy your changes</span></span>  

<span data-ttu-id="33fa7-242">まもなく完了です。</span><span class="sxs-lookup"><span data-stu-id="33fa7-242">You're almost done.</span></span>  <span data-ttu-id="33fa7-243">DevTools でページにいくつか変更を加えましたが、ソースコードにはまだ保存されていません。</span><span class="sxs-lookup"><span data-stu-id="33fa7-243">You've made a few changes to your page in DevTools, but they're not yet saved to your source code.</span></span>  

1.  <span data-ttu-id="33fa7-244">**[ライブ] タブ**を更新します。 DOM ツリーで行った変更が非表示になります。</span><span class="sxs-lookup"><span data-stu-id="33fa7-244">Refresh your **live tab**.  The changes that you made in the DOM Tree disappear.</span></span>  <span data-ttu-id="33fa7-245">特に、テキストは `Your site!` ページの一番上に表示され、テキストは `A new element!?!` 下に戻ります。</span><span class="sxs-lookup"><span data-stu-id="33fa7-245">In particular, the text `Your site!` returns to the top of the page, and the text `A new element!?!` returns to the bottom.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-copy1.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-copy1.msft.png":::
       <span data-ttu-id="33fa7-247">行った変更内容が失われる</span><span class="sxs-lookup"><span data-stu-id="33fa7-247">The changes that you've made are gone</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="33fa7-248">以下のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="33fa7-248">Copy the code below.</span></span>  
    
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
    
1.  <span data-ttu-id="33fa7-249">[ **エディター] タブ** に戻り、ファイルの内容を `index.html` コピーしたコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-249">Go back to the **editor tab** and replace the contents of your `index.html` file with the code that you just copied.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-copy2.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-copy2.msft.png":::
       <span data-ttu-id="33fa7-251">ファイルの `index.html` 外観</span><span class="sxs-lookup"><span data-stu-id="33fa7-251">How your `index.html` file should look</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="33fa7-252">次のステップ</span><span class="sxs-lookup"><span data-stu-id="33fa7-252">Next steps</span></span>  

*   <span data-ttu-id="33fa7-253">このシリーズの次のチュートリアルでは、「 [CSS の使用を開始][DevToolsBeginnersCss]する」を参照して、ページのスタイルを作成する方法と、Microsoft Edge devtools でスタイルの変更を試す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="33fa7-253">Complete the next tutorial in this series, [Get Started with CSS][DevToolsBeginnersCss], to learn how to style your page and experiment with style changes in Microsoft Edge DevTools.</span></span>  
*   <span data-ttu-id="33fa7-254">DOM の詳細について [は、「dom の概要][MDNIntroductionDom] 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33fa7-254">Read [Introduction to the DOM][MDNIntroductionDom] to learn more about the DOM.</span></span>  
*   <span data-ttu-id="33fa7-255">Web [開発の概要][CourseraIntroductionToWebDevelopment] など、実践的な web 開発環境を実現するコースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="33fa7-255">Check out a course like [Introduction to Web Development][CourseraIntroductionToWebDevelopment] to get more hands-on web development experience.</span></span>  

## <span data-ttu-id="33fa7-256">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="33fa7-256">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!--- links --->  

[DevToolsBeginnersCss]: ./css.md "初心者向けの DevTools: CSS の使用を開始する |Microsoft ドキュメント"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge Insider"  

[CourseraIntroductionToWebDevelopment]: https://www.coursera.org/learn/web-development "Web 開発の概要 |Coursera"  

[GlitchAlluringShockIndex]: https://glitch.com/edit/#!/alluring-shock?path=index.html "index.html-alluring-ショック |故障"  

[MDNGettingStartedHtml]: https://developer.mozilla.org/docs/Learn/HTML/Introduction_to_HTML/Getting_started "HTML の概要 |MDN"  
[MDNIntroductionDom]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM の概要 |MDN"  

> [!NOTE]
> <span data-ttu-id="33fa7-263">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="33fa7-263">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="33fa7-264">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/beginners/html) にあり、 [Katherine Jackson][KatherineJackson] \ (テクニカルライターインターン、Chrome devtools) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="33fa7-264">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/beginners/html) and is authored by [Katherine Jackson][KatherineJackson] \(Technical Writer Intern, Chrome DevTools\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="33fa7-266">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="33fa7-266">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
