---
description: HTML と DOM の使用を開始する
title: '初級者向け DevTools: HTML と DOM の使用を開始する'
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools
ms.openlocfilehash: 6ca27b720a17928545712666e43495c4da2fb880
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397931"
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

# <a name="devtools-for-beginners-get-started-with-html-and-the-dom"></a><span data-ttu-id="c3dba-104">初級者向け DevTools: HTML と DOM の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="c3dba-104">DevTools for beginners: Get started with HTML and the DOM</span></span>  

<span data-ttu-id="c3dba-105">これは、Web 開発の基本を教える一連のチュートリアルの最初の例です。</span><span class="sxs-lookup"><span data-stu-id="c3dba-105">This is the first in a series of tutorials that teach you the basics of web development.</span></span>  <span data-ttu-id="c3dba-106">生産性を向上させる可能性がある、Microsoft Edge DevTools という名前の一連の Web 開発者ツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c3dba-106">Learn about a set of web developer tools, named Microsoft Edge DevTools, that may increase your productivity.</span></span>  

<span data-ttu-id="c3dba-107">この特定のチュートリアルでは、HTML と DOM について学習します。</span><span class="sxs-lookup"><span data-stu-id="c3dba-107">In this particular tutorial, you learn about HTML and the DOM.</span></span>  <span data-ttu-id="c3dba-108">HTML は、Web 開発のコア テクノロジの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="c3dba-108">HTML is one of the core technologies of web development.</span></span>  <span data-ttu-id="c3dba-109">Web ページの構造とコンテンツを制御する言語です。</span><span class="sxs-lookup"><span data-stu-id="c3dba-109">It is the language that controls the structure and content of webpages.</span></span>  <span data-ttu-id="c3dba-110">DOM は Web ページの構造とコンテンツにも関連しています。詳細については、後で説明します。</span><span class="sxs-lookup"><span data-stu-id="c3dba-110">The DOM is also related to the structure and content of webpages, learn more about that later.</span></span>  

## <a name="goals"></a><span data-ttu-id="c3dba-111">目標</span><span class="sxs-lookup"><span data-stu-id="c3dba-111">Goals</span></span>  

<span data-ttu-id="c3dba-112">実際に独自の Web サイトを構築して Web 開発を学ぶつもりです。</span><span class="sxs-lookup"><span data-stu-id="c3dba-112">You are going to learn web development by actually building your own website.</span></span>  <span data-ttu-id="c3dba-113">**DevTools for Beginners**シリーズのすべてのチュートリアルを完了すると、完成したサイトは次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="c3dba-113">By the time you complete all of the tutorials in the **DevTools for Beginners** series, your finished site may look like the following figure.</span></span>  

:::image type="complex" source="../media/beginners-html-finished.msft.png" alt-text="完成したサイト" lightbox="../media/beginners-html-finished.msft.png":::
   <span data-ttu-id="c3dba-115">完成したサイト</span><span class="sxs-lookup"><span data-stu-id="c3dba-115">The finished site</span></span>  
:::image-end:::  

<span data-ttu-id="c3dba-116">このチュートリアルの最後には、次のトピックを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3dba-116">By the end of this tutorial, you should understand the following topics.</span></span>  

*   <span data-ttu-id="c3dba-117">HTML と DOM が Web ページに表示されるコンテンツを作成する方法。</span><span class="sxs-lookup"><span data-stu-id="c3dba-117">How HTML and the DOM create the content that are displayed on webpages.</span></span>  
*   <span data-ttu-id="c3dba-118">Microsoft Edge DevTools が HTML と DOM の変更を試すのに役立つ方法。</span><span class="sxs-lookup"><span data-stu-id="c3dba-118">How Microsoft Edge DevTools may help you experiment with HTML and DOM changes.</span></span>  
*   <span data-ttu-id="c3dba-119">HTML と DOM の違い。</span><span class="sxs-lookup"><span data-stu-id="c3dba-119">The difference between HTML and the DOM.</span></span>  

<span data-ttu-id="c3dba-120">また、実際の Web サイトがあります。</span><span class="sxs-lookup"><span data-stu-id="c3dba-120">You also have a real website.</span></span>  <span data-ttu-id="c3dba-121">サイトを使用して履歴書やブログをホストできます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-121">You may use the site to host your resume or blog.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="c3dba-122">前提条件</span><span class="sxs-lookup"><span data-stu-id="c3dba-122">Prerequisites</span></span>  

<span data-ttu-id="c3dba-123">このチュートリアルを試す前に、次の前提条件を満たしてください。</span><span class="sxs-lookup"><span data-stu-id="c3dba-123">Before attempting this tutorial, complete the following prerequisites:</span></span>  

*   <span data-ttu-id="c3dba-124">HTML に慣れていない場合は、「HTML の使用を [開始する」を参照してください][MDNGettingStartedHtml]。</span><span class="sxs-lookup"><span data-stu-id="c3dba-124">If you are unfamiliar with HTML, read [Getting Started with HTML][MDNGettingStartedHtml].</span></span>  
*   <span data-ttu-id="c3dba-125">Microsoft [Edge Web ブラウザーを][MicrosoftEdgeInsider] ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c3dba-125">Download the [Microsoft Edge][MicrosoftEdgeInsider] web browser.</span></span>  <span data-ttu-id="c3dba-126">このチュートリアルでは、Microsoft Edge に組み込まれる Microsoft Edge DevTools と呼ばれる一連の Web 開発ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="c3dba-126">This tutorial uses a set of web development tools, called the Microsoft Edge DevTools, that are built into Microsoft Edge.</span></span>  

## <a name="set-up-your-code"></a><span data-ttu-id="c3dba-127">コードを設定する</span><span class="sxs-lookup"><span data-stu-id="c3dba-127">Set up your code</span></span>  

<span data-ttu-id="c3dba-128">Glitch というオンライン コード エディターでサイトを構築します。</span><span class="sxs-lookup"><span data-stu-id="c3dba-128">You are going to build your site in an online code editor called Glitch.</span></span>  

1.  <span data-ttu-id="c3dba-129">ソース コード [を開きます][GlitchAlluringShockIndex]。</span><span class="sxs-lookup"><span data-stu-id="c3dba-129">Open the [source code][GlitchAlluringShockIndex].</span></span>  <span data-ttu-id="c3dba-130">このタブは、このチュートリアル全体 **で [エディター] タブ** と呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="c3dba-130">This tab is called the **editor tab** throughout this tutorial.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup1.msft.png" alt-text="[エディター] タブ" lightbox="../media/beginners-html-setup1.msft.png":::
       <span data-ttu-id="c3dba-132">[エディター] タブ</span><span class="sxs-lookup"><span data-stu-id="c3dba-132">The editor tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c3dba-133">**Alluring-shock を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c3dba-133">Choose **alluring-shock**.</span></span>  <span data-ttu-id="c3dba-134">左上隅に [プロジェクト オプション] メニューが開きます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-134">The Project Options menu opens in the top-left corner.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup2.msft.png" alt-text="[プロジェクト オプション] メニュー" lightbox="../media/beginners-html-setup2.msft.png":::
       <span data-ttu-id="c3dba-136">[プロジェクト オプション] メニュー</span><span class="sxs-lookup"><span data-stu-id="c3dba-136">The Project Options menu</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c3dba-137">**[Remix Project] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c3dba-137">Choose **Remix Project**.</span></span>  <span data-ttu-id="c3dba-138">Glitch は、編集できるプロジェクトのコピーを作成し、プロジェクトの新しい名前をランダムに生成します。</span><span class="sxs-lookup"><span data-stu-id="c3dba-138">Glitch creates a copy of the project that you may edit and randomly generates a new name for the project.</span></span>  <span data-ttu-id="c3dba-139">コンテンツは以前と同じです。</span><span class="sxs-lookup"><span data-stu-id="c3dba-139">The content is the same as before.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup3.msft.png" alt-text="リミックスされたプロジェクト" lightbox="../media/beginners-html-setup3.msft.png":::
       <span data-ttu-id="c3dba-141">リミックスされたプロジェクト</span><span class="sxs-lookup"><span data-stu-id="c3dba-141">The remixed project</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c3dba-142">このシリーズの次のチュートリアルを完了する予定の場合は、[ サインイン] を選択し、GitHub または Facebook アカウントでグリッチにサインインします。</span><span class="sxs-lookup"><span data-stu-id="c3dba-142">If you plan on completing the next tutorial in this series, choose **Sign In** and sign into Glitch with your GitHub or Facebook account.</span></span>  <span data-ttu-id="c3dba-143">アカウントにサインインしない場合は、編集タブを閉じてからプロジェクトを編集できません。</span><span class="sxs-lookup"><span data-stu-id="c3dba-143">If you choose to not sign into your account, you lose the ability to edit the project after you close the editing tab.</span></span>  
1.  <span data-ttu-id="c3dba-144">[表示 **] を** 選択し、[ **新しいウィンドウ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c3dba-144">Choose **Show** and choose **In a New Window**.</span></span>  <span data-ttu-id="c3dba-145">新しいタブが開き、ライブ ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-145">A new tab opens, showing you the live page.</span></span>  <span data-ttu-id="c3dba-146">このタブは、このチュートリアル全体で **ライブ タブ** と呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="c3dba-146">This tab is called the **live tab** throughout this tutorial.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup4.msft.png" alt-text="[ライブ] タブ" lightbox="../media/beginners-html-setup4.msft.png":::
       <span data-ttu-id="c3dba-148">[ライブ] タブ</span><span class="sxs-lookup"><span data-stu-id="c3dba-148">The live tab</span></span>  
    :::image-end:::  
    
## <a name="add-content"></a><span data-ttu-id="c3dba-149">コンテンツの追加</span><span class="sxs-lookup"><span data-stu-id="c3dba-149">Add content</span></span>  

<span data-ttu-id="c3dba-150">サイトがかなり空です。</span><span class="sxs-lookup"><span data-stu-id="c3dba-150">Your site is pretty empty.</span></span>  <span data-ttu-id="c3dba-151">以下の手順に従って、コンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="c3dba-151">Follow the steps below to add some content to it.</span></span>  

1.  <span data-ttu-id="c3dba-152">[エディター **] タブで、** に置き `<!-- You're "About Me" will go here.  -->` 換えます `<h1>About Me</h1>` 。</span><span class="sxs-lookup"><span data-stu-id="c3dba-152">In the **editor tab**, replace `<!-- You're "About Me" will go here.  -->` with `<h1>About Me</h1>`.</span></span>  
    
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
          :::image type="complex" source="../media/beginners-html-add1.msft.png" alt-text="新しいコードが [エディター] タブで強調表示されます。" lightbox="../media/beginners-html-add1.msft.png":::
             <span data-ttu-id="c3dba-154">新しいコードが [エディター] タブで強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-154">The new code is highlighted in the editor tab</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="c3dba-155">[ライブ] タブで変更 **を表示します**。 テキストは `About Me` ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-155">View your changes in the **live tab**.  The text `About Me` is visible on the page.</span></span>  <span data-ttu-id="c3dba-156">要素はセクション見出しを表すので、周囲のテキストよりも `<h1>` 大きいテキスト。</span><span class="sxs-lookup"><span data-stu-id="c3dba-156">The text larger than the surrounding text, because the `<h1>` element represents a section heading.</span></span>  <span data-ttu-id="c3dba-157">Web ブラウザーは、大きなフォント サイズで見出しのスタイルを自動的に設定します。</span><span class="sxs-lookup"><span data-stu-id="c3dba-157">Your web browser automatically styles headings in larger font sizes.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-add2.msft.png" alt-text="新しい見出しがライブ タブに表示される" lightbox="../media/beginners-html-add2.msft.png":::
       <span data-ttu-id="c3dba-159">新しい見出しがライブ タブに表示される</span><span class="sxs-lookup"><span data-stu-id="c3dba-159">The new heading is visible in the live tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c3dba-160">[エディター] タブ **に戻り**、下の行に `<p>I am learning HTML.  Recent accomplishments:</p>` 挿入します `<h1>About Me</h1>` 。</span><span class="sxs-lookup"><span data-stu-id="c3dba-160">Back in the **editor tab**, insert `<p>I am learning HTML.  Recent accomplishments:</p>` on the line below where you just put `<h1>About Me</h1>`.</span></span>  
    
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
          :::image type="complex" source="../media/beginners-html-add3.msft.png" alt-text="更新されたコードが [エディター] タブで強調表示されます。" lightbox="../media/beginners-html-add3.msft.png":::
             <span data-ttu-id="c3dba-162">更新されたコードが [エディター] タブで強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-162">The updated code is highlighted in the editor tab</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="c3dba-163">[ライブ] タブで変更 **を表示します**。</span><span class="sxs-lookup"><span data-stu-id="c3dba-163">View your change in the **live tab**.</span></span>  
1.  <span data-ttu-id="c3dba-164">[エディター] タブ **に戻り**、業績の一覧を追加します。</span><span class="sxs-lookup"><span data-stu-id="c3dba-164">Back in the **editor tab**, add a list of your accomplishments:</span></span>  
    
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
          :::image type="complex" source="../media/beginners-html-add4.msft.png" alt-text="更新されたコードは、エディター タブでも強調表示されます。" lightbox="../media/beginners-html-add4.msft.png":::
             <span data-ttu-id="c3dba-166">更新されたコードは、エディター タブでも強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-166">The updated code is also highlighted in the editor tab</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="c3dba-167">再度、ライブ タブに **戻** り、新しいコンテンツが正しく表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3dba-167">Again, go back to the **live tab** to make sure that the new content is displaying correctly.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-add5.msft.png" alt-text="新しいリストがライブ タブに表示される" lightbox="../media/beginners-html-add5.msft.png":::
       <span data-ttu-id="c3dba-169">新しいリストがライブ タブに表示される</span><span class="sxs-lookup"><span data-stu-id="c3dba-169">The new list is visible in the live tab</span></span>  
    :::image-end:::  
    
## <a name="experiment-with-content-changes-in-microsoft-edge-devtools"></a><span data-ttu-id="c3dba-170">Microsoft Edge DevTools でコンテンツの変更を試す</span><span class="sxs-lookup"><span data-stu-id="c3dba-170">Experiment with content changes in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="c3dba-171">多くの HTML を含む大きなページを開発している場合は、変更を表示するために、エディター タブとライブ タブの間を何百回も行き来する必要があります。特に、ページに正確に何を置く必要があるのか分からない場合は、何百回も行き来する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3dba-171">If you were developing a big page with a lot of HTML, it is somewhat tedious to go back-and-forth between the editor tab and the live tab hundreds of times in order to display your changes, especially if you are unsure what exactly to put on the page.</span></span>  <span data-ttu-id="c3dba-172">Microsoft Edge DevTools は、ライブ タブを離れることなくコンテンツの変更を **試すのに役立ちます**。</span><span class="sxs-lookup"><span data-stu-id="c3dba-172">Microsoft Edge DevTools helps you experiment with content changes without ever leaving the **live tab**.</span></span>  

### <a name="learn-the-difference-between-html-and-the-dom"></a><span data-ttu-id="c3dba-173">HTML と DOM の違いを学ぶ</span><span class="sxs-lookup"><span data-stu-id="c3dba-173">Learn the difference between HTML and the DOM</span></span>  

<span data-ttu-id="c3dba-174">Microsoft Edge DevTools からコンテンツの編集を開始する前に、HTML と DOM の違いを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3dba-174">Before you start editing your content from Microsoft Edge DevTools, you should understand the difference between HTML and the DOM.</span></span>  <span data-ttu-id="c3dba-175">最適な学習方法は、次の例です。</span><span class="sxs-lookup"><span data-stu-id="c3dba-175">The best way to learn is by example:</span></span>  

1.  <span data-ttu-id="c3dba-176">[ライブ] タブ **に移動します**。 ページの下部にテキストが `A new element!?!` 表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-176">Navigate to the **live tab**.  At the bottom of your page, the text `A new element!?!` is displayed.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom1.msft.png" alt-text="ページの下部にあるテキスト A 新しい要素!?! が表示されます" lightbox="../media/beginners-html-dom1.msft.png":::
       <span data-ttu-id="c3dba-179">ページの下部にテキストが `A new element!?!` 表示されます</span><span class="sxs-lookup"><span data-stu-id="c3dba-179">At the bottom of the page the text `A new element!?!` is displayed</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c3dba-180">[エディター] タブに **戻り、** テキストを探します `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="c3dba-180">Go back to the **editor tab** and try to find the text in `index.html`.</span></span>  <span data-ttu-id="c3dba-181">テキストがそこには表示されない。</span><span class="sxs-lookup"><span data-stu-id="c3dba-181">The text is not there.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom2.msft.png" alt-text="謎のテキスト 新しい要素!?! は l のどこにもindex.htmはありません。" lightbox="../media/beginners-html-dom2.msft.png":::
       <span data-ttu-id="c3dba-184">謎のテキスト `A new element!?!` はどこにも見つかりません</span><span class="sxs-lookup"><span data-stu-id="c3dba-184">The mystery text `A new element!?!` is nowhere to be found in</span></span> `index.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="c3dba-185">ライブ タブに **戻り**、マウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き `A new element!?!` 、[検査] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="c3dba-185">Go back to the **live tab**, hover on `A new element!?!`, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom3.msft.png" alt-text="テキストの検査" lightbox="../media/beginners-html-dom3.msft.png":::
       <span data-ttu-id="c3dba-187">テキストの検査</span><span class="sxs-lookup"><span data-stu-id="c3dba-187">Inspecting some text</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="c3dba-188">DevTools がページと一緒に開きます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-188">DevTools opens up alongside your page.</span></span>  `<div>A new element!?!</div>` <span data-ttu-id="c3dba-189">は青色で強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-189">is highlighted blue.</span></span>  <span data-ttu-id="c3dba-190">DevTools のこの構造は HTML のように見えますが、実際には **DOM ツリーです**。</span><span class="sxs-lookup"><span data-stu-id="c3dba-190">Although this structure in DevTools looks like your HTML, it is actually the **DOM Tree**.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom4.msft.png" alt-text="DevTools がページと一緒に開いている" lightbox="../media/beginners-html-dom4.msft.png":::
       <span data-ttu-id="c3dba-192">DevTools がページと一緒に開いている</span><span class="sxs-lookup"><span data-stu-id="c3dba-192">DevTools is open alongside the page</span></span>  
    :::image-end:::  
    
<span data-ttu-id="c3dba-193">ページが読み込まれると、ブラウザーは HTML を使用してページ *の初期コンテンツ* を作成します。</span><span class="sxs-lookup"><span data-stu-id="c3dba-193">When your page loads, the browser takes your HTML to create the *initial* content of the page.</span></span>  <span data-ttu-id="c3dba-194">DOM はページの現在 *の* コンテンツを表します。時間の流中に変化する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c3dba-194">The DOM represents the *current* content of the page, which may change over time.</span></span>  <span data-ttu-id="c3dba-195">HTML の下部にあるタグのために、ページに不思議なコンテンツ `<div>A new element!?!</div>` `<script src="new.js"></script>` が追加されます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-195">The mysterious `<div>A new element!?!</div>` content is added to your page because of the `<script src="new.js"></script>` tag at the bottom of your HTML.</span></span>  <span data-ttu-id="c3dba-196">このタグを使用すると、一部の JavaScript コードが実行されます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-196">This tag causes some JavaScript code to run.</span></span>  <span data-ttu-id="c3dba-197">JavaScript の詳細については、後のチュートリアルで説明しますが、今のところは、ページの内容を変更するプログラミング言語と考えておきます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-197">Learn more about JavaScript in a later tutorial, but for now think of it as a programming language that may change the content of your page.</span></span>  <span data-ttu-id="c3dba-198">この特定のケースでは、JavaScript コードがページ `<div>A new element!?!</div>` に追加されます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-198">In this particular case, JavaScript code adds `<div>A new element!?!</div>` to your page.</span></span>  <span data-ttu-id="c3dba-199">この謎のテキストはライブ ページに表示されますが、HTML には表示されません。</span><span class="sxs-lookup"><span data-stu-id="c3dba-199">That is why this mystery text is visible on your live page, but not in your HTML.</span></span>  

### <a name="edit-the-dom"></a><span data-ttu-id="c3dba-200">DOM の編集</span><span class="sxs-lookup"><span data-stu-id="c3dba-200">Edit the DOM</span></span>  

<span data-ttu-id="c3dba-201">ライブ タブを離れることなくコンテンツの変更をすばやく試す場合は、DevTools を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="c3dba-201">If you want to quickly experiment with content changes without ever leaving the live tab, try DevTools.</span></span>  

1.  <span data-ttu-id="c3dba-202">DevTools で、マウス ポインターを置き、コンテキスト メニュー `Your site!` \(右クリック\) を開き **、[HTML として編集] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c3dba-202">In DevTools, hover on `Your site!`, open the contextual menu \(right-click\), and choose **Edit as HTML**.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-edit1.msft.png" alt-text="HTML としてノードを編集する" lightbox="../media/beginners-html-edit1.msft.png":::
       <span data-ttu-id="c3dba-204">HTML としてノードを編集する</span><span class="sxs-lookup"><span data-stu-id="c3dba-204">Editing the node as HTML</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c3dba-205">以下 `<p>Your site!</p>` のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-205">Replace `<p>Your site!</p>` with the code below.</span></span>  
    
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
          :::image type="complex" source="../media/beginners-html-edit2.msft.png" alt-text="HTML としてノードを更新する" lightbox="../media/beginners-html-edit2.msft.png":::
             <span data-ttu-id="c3dba-207">HTML としてノードを更新する</span><span class="sxs-lookup"><span data-stu-id="c3dba-207">Updating the node as HTML</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="c3dba-208">`Control` + `Enter` \(Windows, Linux\) または `Command` + \(macOS\) を選択して変更を保存するか、ボックスの外側 `Enter` を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3dba-208">Select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\) to save your changes, or choose outside of the box.</span></span>  <span data-ttu-id="c3dba-209">変更がページのライブ ビューに自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-209">Your changes automatically show up in the live view of your page.</span></span>  <span data-ttu-id="c3dba-210">テキストが `Your site!` 新しいコンテンツに置き換えられた。</span><span class="sxs-lookup"><span data-stu-id="c3dba-210">The text `Your site!` has been replaced with the new content.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-edit3.msft.png" alt-text="新しいコンテンツがページにすぐに表示される" lightbox="../media/beginners-html-edit3.msft.png":::
       <span data-ttu-id="c3dba-212">新しいコンテンツがページにすぐに表示される</span><span class="sxs-lookup"><span data-stu-id="c3dba-212">The new content shows up immediately on the page</span></span>  
    :::image-end:::  
    
<span data-ttu-id="c3dba-213">このワークフローは、コンテンツの変更を試す場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-213">This workflow is only good for experimenting with content changes.</span></span>  <span data-ttu-id="c3dba-214">ページを更新するか、タブを閉じると、変更は永遠に消えてしまいます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-214">If you refresh the page or close the tab, your changes are gone forever.</span></span>  <span data-ttu-id="c3dba-215">このワークフローを使用して変更を保存する場合は、それらの変更を手動で HTML にコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3dba-215">If you're using this workflow and you want to save your changes, you need to manually copy those changes over to your HTML.</span></span>  <span data-ttu-id="c3dba-216">次のセクションでは、DOM ツリーからコンテンツを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c3dba-216">The next couple of sections show you some more ways that you may change content from the DOM Tree.</span></span>  

## <a name="reorder-nodes"></a><span data-ttu-id="c3dba-217">ノードの並べ替え</span><span class="sxs-lookup"><span data-stu-id="c3dba-217">Reorder nodes</span></span>  

<span data-ttu-id="c3dba-218">DOM ノードの順序を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-218">You may also change the order of DOM nodes.</span></span>  <span data-ttu-id="c3dba-219">たとえば、Web ページでは、ナビゲーション メニューが下部の近くに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-219">For example, on your web page the navigation menu is near the bottom.</span></span>  <span data-ttu-id="c3dba-220">上部に移動するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="c3dba-220">To move it to the top:</span></span>  

1.  <span data-ttu-id="c3dba-221">`<nav>`DevTools の**DOM ツリーで**ノードを検索します。</span><span class="sxs-lookup"><span data-stu-id="c3dba-221">Find the `<nav>` node in the **DOM Tree** of DevTools.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-reorder1.msft.png" alt-text="ナビゲーション ノードが DevTools で青色で強調表示されている" lightbox="../media/beginners-html-reorder1.msft.png":::
       <span data-ttu-id="c3dba-223">ナビゲーション ノードが DevTools で青色で強調表示されている</span><span class="sxs-lookup"><span data-stu-id="c3dba-223">The nav node is highlighted blue in DevTools</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c3dba-224">ノードを `<nav>` 上にドラッグして、ノードがノードの最初の子 `<body>` になります。</span><span class="sxs-lookup"><span data-stu-id="c3dba-224">Drag the `<nav>` node to the top, so that the node is the first child of the `<body>` node.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-reorder2.msft.png" alt-text="ナビゲーション ノードを上にドラッグする" lightbox="../media/beginners-html-reorder2.msft.png":::
             <span data-ttu-id="c3dba-226">ナビゲーション ノードを上にドラッグする</span><span class="sxs-lookup"><span data-stu-id="c3dba-226">Dragging the nav node to the top</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="c3dba-227">これで `<nav>` 、ページの上部にノードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-227">The `<nav>` node is now displaying at the top of your page.</span></span>  
          
          :::image type="complex" source="../media/beginners-html-reorder3.msft.png" alt-text="ナビゲーション ノードがページの上部にある" lightbox="../media/beginners-html-reorder3.msft.png":::
             <span data-ttu-id="c3dba-229">ナビゲーション ノードがページの上部にある</span><span class="sxs-lookup"><span data-stu-id="c3dba-229">The nav node is at the top of the page</span></span>  
          :::image-end:::  
       :::column-end:::
   :::row-end:::  
    
### <a name="delete-a-node"></a><span data-ttu-id="c3dba-230">ノードの削除</span><span class="sxs-lookup"><span data-stu-id="c3dba-230">Delete a node</span></span>  

<span data-ttu-id="c3dba-231">DOM ツリーからノードを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-231">You may also remove nodes from the DOM Tree.</span></span>  

1.  <span data-ttu-id="c3dba-232">DOM ツリー **で、** を選択します `<div>A new element!?!</div>` 。</span><span class="sxs-lookup"><span data-stu-id="c3dba-232">In the **DOM Tree**, choose `<div>A new element!?!</div>`.</span></span>  <span data-ttu-id="c3dba-233">DevTools はノードを青色で強調表示します。</span><span class="sxs-lookup"><span data-stu-id="c3dba-233">DevTools highlights the node blue.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-delete1.msft.png" alt-text="削除するノードを選択する" lightbox="../media/beginners-html-delete1.msft.png":::
       <span data-ttu-id="c3dba-235">削除するノードを選択する</span><span class="sxs-lookup"><span data-stu-id="c3dba-235">Choose the node to be deleted</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c3dba-236">キーボードの `Delete` キーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c3dba-236">Select the `Delete` key on your keyboard.</span></span>  <span data-ttu-id="c3dba-237">ノード `<div>A new element!?!</div>` は DOM ツリーから削除されます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-237">The `<div>A new element!?!</div>` node is removed from your DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-delete2.msft.png" alt-text="ノードが削除されました" lightbox="../media/beginners-html-delete2.msft.png":::
       <span data-ttu-id="c3dba-239">ノードが削除されました</span><span class="sxs-lookup"><span data-stu-id="c3dba-239">The node has been deleted</span></span>  
    :::image-end:::  
    
## <a name="copy-your-changes"></a><span data-ttu-id="c3dba-240">変更をコピーする</span><span class="sxs-lookup"><span data-stu-id="c3dba-240">Copy your changes</span></span>  

<span data-ttu-id="c3dba-241">もう少しで完了です。</span><span class="sxs-lookup"><span data-stu-id="c3dba-241">You're almost done.</span></span>  <span data-ttu-id="c3dba-242">DevTools でページにいくつかの変更を加えたが、まだソース コードに保存されていない。</span><span class="sxs-lookup"><span data-stu-id="c3dba-242">You've made a few changes to your page in DevTools, but they're not yet saved to your source code.</span></span>  

1.  <span data-ttu-id="c3dba-243">ライブ タブ **を更新します**。 DOM ツリーで行った変更は消えます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-243">Refresh your **live tab**.  The changes that you made in the DOM Tree disappear.</span></span>  <span data-ttu-id="c3dba-244">特に、テキスト `Your site!` はページの上部に戻り、テキストは `A new element!?!` 下部に戻ります。</span><span class="sxs-lookup"><span data-stu-id="c3dba-244">In particular, the text `Your site!` returns to the top of the page, and the text `A new element!?!` returns to the bottom.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-copy1.msft.png" alt-text="行った変更は消えました" lightbox="../media/beginners-html-copy1.msft.png":::
       <span data-ttu-id="c3dba-246">行った変更は消えました</span><span class="sxs-lookup"><span data-stu-id="c3dba-246">The changes that you've made are gone</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c3dba-247">以下のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="c3dba-247">Copy the code below.</span></span>  
    
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
    
1.  <span data-ttu-id="c3dba-248">[エディター] タブ **に戻り** 、ファイルの内容をコピーしたコード `index.html` に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c3dba-248">Go back to the **editor tab** and replace the contents of your `index.html` file with the code that you just copied.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-copy2.msft.png" alt-text="l ファイルindex.htmの外観" lightbox="../media/beginners-html-copy2.msft.png":::
       <span data-ttu-id="c3dba-250">ファイルの `index.html` 外観</span><span class="sxs-lookup"><span data-stu-id="c3dba-250">How your `index.html` file should look</span></span>  
    :::image-end:::  
    
## <a name="next-steps"></a><span data-ttu-id="c3dba-251">次の手順</span><span class="sxs-lookup"><span data-stu-id="c3dba-251">Next steps</span></span>  

*   <span data-ttu-id="c3dba-252">このシリーズの次のチュートリアル [「CSS][DevToolsBeginnersCss]の使用を開始する」を実行して、ページのスタイルを設定し、Microsoft Edge DevTools でスタイルの変更を試す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c3dba-252">Complete the next tutorial in this series, [Get Started with CSS][DevToolsBeginnersCss], to learn how to style your page and experiment with style changes in Microsoft Edge DevTools.</span></span>  
*   <span data-ttu-id="c3dba-253">DOM [の詳細については、「DOM の][MDNIntroductionDom] 概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3dba-253">Read [Introduction to the DOM][MDNIntroductionDom] to learn more about the DOM.</span></span>  
*   <span data-ttu-id="c3dba-254">Web 開発の概要 [のようなコースをチェック][CourseraIntroductionToWebDevelopment] して、より実践的な Web 開発エクスペリエンスを得る。</span><span class="sxs-lookup"><span data-stu-id="c3dba-254">Check out a course like [Introduction to Web Development][CourseraIntroductionToWebDevelopment] to get more hands-on web development experience.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="c3dba-255">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="c3dba-255">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!--- links --->  

[DevToolsBeginnersCss]: ./css.md "初級者向け DevTools: CSS の使用を開始|Microsoft Docs"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge Insider"  

[CourseraIntroductionToWebDevelopment]: https://www.coursera.org/learn/web-development "Web 開発の概要|Coursera"  

[GlitchAlluringShockIndex]: https://glitch.com/edit/#!/alluring-shock?path=index.html "index.html - アリング ショック |Glitch"  

[MDNGettingStartedHtml]: https://developer.mozilla.org/docs/Learn/HTML/Introduction_to_HTML/Getting_started "HTML ファイルの使用を開始|MDN"  
[MDNIntroductionDom]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM の概要|MDN"  

> [!NOTE]
> <span data-ttu-id="c3dba-262">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="c3dba-262">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c3dba-263">元のページ [はここで見](https://developers.google.com/web/tools/chrome-devtools/beginners/html) つかり、キャ [サ][KatherineJackson] リン・ジャクソン \(Technical Writer Intern, Chrome DevTools\) によって作成されています。</span><span class="sxs-lookup"><span data-stu-id="c3dba-263">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/beginners/html) and is authored by [Katherine Jackson][KatherineJackson] \(Technical Writer Intern, Chrome DevTools\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="c3dba-265">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="c3dba-265">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
