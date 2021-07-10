---
description: はじめに DOM の使用
title: '初級者向け DevTools: HTML と DOM の使用を開始する'
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/01/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, Web 開発, f12 ツール, devtools, devtools for beginners, devtools HTML for beginners, devtools DOM for beginners, devtools html tutorial, devtools DOM tutorial, devtools DOM tutorial, devtools document object model tutorial
ms.openlocfilehash: a049ec500e22f89db3ab1e966b55d89c2ad682fe
ms.sourcegitcommit: 8f37c931ecde4d58223113f7e3b42d37cc3df97f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2021
ms.locfileid: "11643532"
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
# <a name="devtools-for-beginners-get-started-with-html-and-the-dom"></a><span data-ttu-id="0748c-104">初級者向け DevTools: HTML と DOM の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="0748c-104">DevTools for beginners: Get started with HTML and the DOM</span></span>  

<span data-ttu-id="0748c-105">これは、Web 開発の基本を教える一連のチュートリアルの最初の例です。</span><span class="sxs-lookup"><span data-stu-id="0748c-105">This is the first in a series of tutorials that teach you the basics of web development.</span></span> <span data-ttu-id="0748c-106">生産性を向上させる可能性がある、DevTools という名前Microsoft Edge一連の Web 開発者ツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0748c-106">Learn about a set of web developer tools, named Microsoft Edge DevTools, that may increase your productivity.</span></span>  

<span data-ttu-id="0748c-107">このチュートリアルでは、HTML と [Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model) \(DOM\) について説明します。</span><span class="sxs-lookup"><span data-stu-id="0748c-107">This tutorial describes HTML and the [Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model) \(DOM\).</span></span> <span data-ttu-id="0748c-108">HTML は、Web 開発のコア テクノロジの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="0748c-108">HTML is one of the core technologies of web development.</span></span> <span data-ttu-id="0748c-109">Web ページの構造とコンテンツを制御する言語です。</span><span class="sxs-lookup"><span data-stu-id="0748c-109">It is the language that controls the structure and content of webpages.</span></span> <span data-ttu-id="0748c-110">DOM は、Web ページの構造とコンテンツにも関連しています。詳細については、後で説明します。</span><span class="sxs-lookup"><span data-stu-id="0748c-110">The DOM is also related to the structure and content of webpages, which we learn more about later.</span></span>

## <a name="goals"></a><span data-ttu-id="0748c-111">目標</span><span class="sxs-lookup"><span data-stu-id="0748c-111">Goals</span></span>  

<span data-ttu-id="0748c-112">Web サイトを構築して Web 開発を学ぶつもりです。</span><span class="sxs-lookup"><span data-stu-id="0748c-112">You're going to learn web development by building a website.</span></span>  <span data-ttu-id="0748c-113">**DevTools for Beginners**シリーズのすべてのチュートリアルを完了すると、完成したサイトは次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="0748c-113">By the time you complete all of the tutorials in the **DevTools for Beginners** series, your finished site may look like the following figure.</span></span>  

:::image type="complex" source="media/beginners-html-finished.msft.png" alt-text="完成したサイト" lightbox="media/beginners-html-finished.msft.png":::
   <span data-ttu-id="0748c-115">完成したサイト</span><span class="sxs-lookup"><span data-stu-id="0748c-115">The finished site</span></span>  
:::image-end:::  

<span data-ttu-id="0748c-116">このチュートリアルの最後には、次の概念を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0748c-116">By the end of this tutorial, you should understand the following concepts.</span></span>  

*   <span data-ttu-id="0748c-117">HTML と DOM が Web ページに表示されるコンテンツを作成する方法。</span><span class="sxs-lookup"><span data-stu-id="0748c-117">How HTML and the DOM create the content displayed on webpages.</span></span>  
*   <span data-ttu-id="0748c-118">DevTools Microsoft Edge HTML と DOM の変更を試す方法。</span><span class="sxs-lookup"><span data-stu-id="0748c-118">How Microsoft Edge DevTools may help you experiment with HTML and DOM changes.</span></span>  
*   <span data-ttu-id="0748c-119">HTML と DOM の違い。</span><span class="sxs-lookup"><span data-stu-id="0748c-119">The difference between HTML and the DOM.</span></span>  

<span data-ttu-id="0748c-120">また、作業用の Web サイトも用意されています。</span><span class="sxs-lookup"><span data-stu-id="0748c-120">You will also have a working website.</span></span> <span data-ttu-id="0748c-121">サイトを使用して履歴書やブログをホストできます。</span><span class="sxs-lookup"><span data-stu-id="0748c-121">You may use the site to host your resume or blog.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="0748c-122">前提条件</span><span class="sxs-lookup"><span data-stu-id="0748c-122">Prerequisites</span></span>  

<span data-ttu-id="0748c-123">このチュートリアルを試す前に、次の前提条件を満たしてください。</span><span class="sxs-lookup"><span data-stu-id="0748c-123">Before attempting this tutorial, complete the following prerequisites:</span></span>  

*   <span data-ttu-id="0748c-124">HTML に慣れていない場合は、「HTML の使用を [開始する」を参照してください][MDNGettingStartedHtml]。</span><span class="sxs-lookup"><span data-stu-id="0748c-124">If you are unfamiliar with HTML, read [Getting Started with HTML][MDNGettingStartedHtml].</span></span>  
*   <span data-ttu-id="0748c-125">Web ブラウザー [Microsoft Edge][MicrosoftEdgeInsider]ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="0748c-125">Download the [Microsoft Edge][MicrosoftEdgeInsider] web browser.</span></span>  <span data-ttu-id="0748c-126">このチュートリアルでは、開発ツールに組み込Microsoft Edge DevTools と呼ばれる一連の web 開発Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="0748c-126">This tutorial uses a set of web development tools, called the Microsoft Edge DevTools, that are built into Microsoft Edge.</span></span>  

## <a name="set-up-your-code"></a><span data-ttu-id="0748c-127">コードを設定する</span><span class="sxs-lookup"><span data-stu-id="0748c-127">Set up your code</span></span>  

<span data-ttu-id="0748c-128">Glitch オンライン コード エディターでサイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0748c-128">You are going to build a site in the Glitch online code editor.</span></span>  

1.  <span data-ttu-id="0748c-129">ソース コード [を開きます][GlitchAlluringShockIndex]。</span><span class="sxs-lookup"><span data-stu-id="0748c-129">Open the [source code][GlitchAlluringShockIndex].</span></span> <span data-ttu-id="0748c-130">このタブは、このチュートリアル全体 **で [エディター] タブ** と呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="0748c-130">This tab is called the **editor tab** throughout this tutorial.</span></span>  
    
    :::image type="complex" source="media/beginners-html-setup1.msft.png" alt-text="[エディター] タブ" lightbox="media/beginners-html-setup1.msft.png":::
       <span data-ttu-id="0748c-132">[エディター] タブ</span><span class="sxs-lookup"><span data-stu-id="0748c-132">The editor tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0748c-133">**Alluring-shock を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0748c-133">Choose **alluring-shock**.</span></span> <span data-ttu-id="0748c-134">**[Project] メニューが**開きます。</span><span class="sxs-lookup"><span data-stu-id="0748c-134">The **Project Options** menu opens.</span></span>  
    
    :::image type="complex" source="media/beginners-html-setup2.msft.png" alt-text="[Project オプション] メニュー" lightbox="media/beginners-html-setup2.msft.png":::
       <span data-ttu-id="0748c-136">[Project オプション] メニュー</span><span class="sxs-lookup"><span data-stu-id="0748c-136">The Project Options menu</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0748c-137">**[Remix Project] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0748c-137">Choose **Remix Project**.</span></span> <span data-ttu-id="0748c-138">Glitch は、編集できるプロジェクトのコピーを作成し、プロジェクトの新しい名前をランダムに生成します。</span><span class="sxs-lookup"><span data-stu-id="0748c-138">Glitch creates a copy of the project that you may edit and randomly generates a new name for the project.</span></span> <span data-ttu-id="0748c-139">コンテンツは以前と同じです。</span><span class="sxs-lookup"><span data-stu-id="0748c-139">The content is the same as before.</span></span>  
    
    :::image type="complex" source="media/beginners-html-setup3.msft.png" alt-text="リミックスされたプロジェクト" lightbox="media/beginners-html-setup3.msft.png":::
       <span data-ttu-id="0748c-141">リミックスされたプロジェクト</span><span class="sxs-lookup"><span data-stu-id="0748c-141">The remixed project</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0748c-142">このシリーズの次のチュートリアルを完了する予定の場合は\*\*\*\*、[サインインして Glitch にサインインする] を選択して、Facebook、GitHub、または Google アカウントを使用します。またはマジック リンクを自分にメールで送信します。</span><span class="sxs-lookup"><span data-stu-id="0748c-142">If you plan to complete the next tutorial in this series, choose **Sign In** to Glitch using your Facebook, GitHub, or Google account; or email yourself a magic link.</span></span> <span data-ttu-id="0748c-143">アカウントにサインインしない場合は、[エディター] タブを閉じるとプロジェクトを編集できません。</span><span class="sxs-lookup"><span data-stu-id="0748c-143">If you choose not to sign in to an account, you cannot edit the project after closing the editor tab.</span></span>

1.  <span data-ttu-id="0748c-144">[新**しい**  \>  **ウィンドウに表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0748c-144">Choose **Show** \> **In a New Window**.</span></span>  <span data-ttu-id="0748c-145">新しいタブが開き、ライブ ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0748c-145">A new tab opens, showing the live page.</span></span> <span data-ttu-id="0748c-146">このタブは、このチュートリアル全体で **ライブ タブ** と呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="0748c-146">This tab is called the **live tab** throughout this tutorial.</span></span>  
    
    :::image type="complex" source="media/beginners-html-setup4.msft.png" alt-text="[ライブ] タブ" lightbox="media/beginners-html-setup4.msft.png":::
       <span data-ttu-id="0748c-148">[ライブ] タブ</span><span class="sxs-lookup"><span data-stu-id="0748c-148">The live tab</span></span>  
    :::image-end:::  
    
## <a name="add-content"></a><span data-ttu-id="0748c-149">コンテンツの追加</span><span class="sxs-lookup"><span data-stu-id="0748c-149">Add content</span></span>  

<span data-ttu-id="0748c-150">サイトには、より多くの情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="0748c-150">Your site needs more information.</span></span> <span data-ttu-id="0748c-151">コンテンツを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0748c-151">Complete the following steps to add some content.</span></span>  

1. <span data-ttu-id="0748c-152">[エディター **] タブで、** に置き `<!-- You're "About Me" will go here.  -->` 換えます `<h1>About Me</h1>` 。</span><span class="sxs-lookup"><span data-stu-id="0748c-152">In the **editor tab**, replace `<!-- You're "About Me" will go here.  -->` with `<h1>About Me</h1>`.</span></span>  
    
    ```html
        ...
        <body>
            <p> Your site!</p>
                <main>
                    <h1>About Me</h1>
                </main>
        ...
    ```  
    
    :::image type="complex" source="media/beginners-html-add1.msft.png" alt-text="新しいコードが [エディター] タブで強調表示されます。" lightbox="media/beginners-html-add1.msft.png":::
        <span data-ttu-id="0748c-154">新しいコードが [エディター] タブで強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="0748c-154">The new code is highlighted in the editor tab</span></span>  
    :::image-end:::  
    
1. <span data-ttu-id="0748c-155">[ライブ] タブで変更 **を表示します**。テキストは `About Me` ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0748c-155">View your changes in the **live tab**. The text `About Me` is visible on the page.</span></span> <span data-ttu-id="0748c-156">要素は見出し 1 を表すので、テキストは周囲 `<h1>` のテキストよりも大きくなります。</span><span class="sxs-lookup"><span data-stu-id="0748c-156">The text is larger than the surrounding text because the `<h1>` element represents a Heading 1.</span></span>  <span data-ttu-id="0748c-157">Web ブラウザーは、大きなフォント サイズで見出しのスタイルを自動的に設定します。</span><span class="sxs-lookup"><span data-stu-id="0748c-157">Your web browser automatically styles headings in larger font sizes.</span></span>  
    
    :::image type="complex" source="media/beginners-html-add2.msft.png" alt-text="新しい見出しがライブ タブに表示される" lightbox="media/beginners-html-add2.msft.png":::
       <span data-ttu-id="0748c-159">新しい見出しがライブ タブに表示される</span><span class="sxs-lookup"><span data-stu-id="0748c-159">The new heading is visible in the live tab</span></span>  
    :::image-end:::  
    
1. <span data-ttu-id="0748c-160">[エディター] タブ **に戻り、** 下 `<p>I am learning web development. Recent accomplishments:</p>` の行に挿入します  `<h1>About Me</h1>` 。</span><span class="sxs-lookup"><span data-stu-id="0748c-160">Back in the **editor tab**, insert `<p>I am learning web development. Recent accomplishments:</p>` on the line below  `<h1>About Me</h1>`.</span></span>  
    
    ```html
    ...
        <body>
            <p> Your site!</p>
                <main>
                    <h1>About Me</h1>
                    <p>I am learning web development. Recent accomplishments:</p>
                </main>
    ...
    ```  

    :::image type="complex" source="media/beginners-html-add3.msft.png" alt-text="更新されたコードが [エディター] タブで強調表示されます。" lightbox="media/beginners-html-add3.msft.png":::
        <span data-ttu-id="0748c-162">更新されたコードが [エディター] タブで強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="0748c-162">The updated code is highlighted in the editor tab</span></span>  
    :::image-end:::  
    
1. <span data-ttu-id="0748c-163">[ライブ] タブで変更 **を表示します**。</span><span class="sxs-lookup"><span data-stu-id="0748c-163">View your change in the **live tab**.</span></span>

1. <span data-ttu-id="0748c-164">[エディター] タブ **に戻り**、次のコードを使用して業績の一覧を追加します。</span><span class="sxs-lookup"><span data-stu-id="0748c-164">Back in the **editor tab**, add a list of your accomplishments using the following code.</span></span>
    
    ```html
    ...
    <p>I am learning web development.  Recent accomplishments:</p>
        <ul>
            <li>Learned how to set up my code in Glitch.</li>
            <li>Added content to my HTML.</li>
            <li>TODO: Learn how to use Microsoft Edge DevTools to experiment with content changes.</li>
            <li>TODO: Learn the difference between HTML and the DOM.</li>
        </ul>
    ...
    ```  

    :::image type="complex" source="media/beginners-html-add4.msft.png" alt-text="更新されたコードは、エディター タブでも強調表示されます。" lightbox="media/beginners-html-add4.msft.png":::
        <span data-ttu-id="0748c-166">更新されたコードは、エディター タブでも強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="0748c-166">The updated code is also highlighted in the editor tab</span></span>  
    :::image-end:::  

1. <span data-ttu-id="0748c-167">[ライブ] **タブを表示** して、新しいコンテンツが正しく表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="0748c-167">View the **live tab** to make sure that the new content displays correctly.</span></span>  
    
    :::image type="complex" source="media/beginners-html-add5.msft.png" alt-text="新しいリストがライブ タブに表示される" lightbox="media/beginners-html-add5.msft.png":::
       <span data-ttu-id="0748c-169">新しいリストがライブ タブに表示される</span><span class="sxs-lookup"><span data-stu-id="0748c-169">The new list is visible in the live tab</span></span>  
    :::image-end:::  
    
## <a name="experiment-with-content-changes-in-microsoft-edge-devtools"></a><span data-ttu-id="0748c-170">DevTools でコンテンツの変更Microsoft Edgeする</span><span class="sxs-lookup"><span data-stu-id="0748c-170">Experiment with content changes in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="0748c-171">HTML の多いページを開発している場合は、エディター タブとライブ タブの間を行き来して変更を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0748c-171">If you are developing a page with a lot of HTML, it becomes tedious to go back-and-forth between the editor tab and the live tab to see your changes.</span></span> <span data-ttu-id="0748c-172">Microsoft EdgeDevTools は、ライブ タブを離れることなくコンテンツの変更を**試すのに役立ちます**。</span><span class="sxs-lookup"><span data-stu-id="0748c-172">Microsoft Edge DevTools helps you experiment with content changes without ever leaving the **live tab**.</span></span>  

### <a name="learn-the-difference-between-html-and-the-dom"></a><span data-ttu-id="0748c-173">HTML と DOM の違いを学ぶ</span><span class="sxs-lookup"><span data-stu-id="0748c-173">Learn the difference between HTML and the DOM</span></span>  

<span data-ttu-id="0748c-174">DevTools Microsoft Edge編集する前に、HTML と DOM の違いを理解しましょう。</span><span class="sxs-lookup"><span data-stu-id="0748c-174">Before editing content from Microsoft Edge DevTools, let's understand the difference between HTML and the DOM.</span></span> <span data-ttu-id="0748c-175">次の手順に進み、例について説明します。</span><span class="sxs-lookup"><span data-stu-id="0748c-175">Proceed with the following steps to learn from an example.</span></span>

1. <span data-ttu-id="0748c-176">[ライブ] タブ **に移動します**。ページの下部にテキストが表示 `A new element!?!` されます。</span><span class="sxs-lookup"><span data-stu-id="0748c-176">Navigate to the **live tab**. At the bottom of your page, the text `A new element!?!` displays.</span></span>  

    <!--
        :::image type="complex" source="media/beginners-html-dom1.msft.png" alt-text="At the bottom of the page the text A new element!?! displays" lightbox="media/beginners-html-dom1.msft.png":::
        At the bottom of the page the text `A new element!?!` is displays  
        :::image-end:::
    -->
    
1. <span data-ttu-id="0748c-177">[エディター] **タブを開** き、テキストを探します `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="0748c-177">Open the **editor tab** and try to find the text in `index.html`.</span></span> <span data-ttu-id="0748c-178">テキストは、このビューには表示されません。</span><span class="sxs-lookup"><span data-stu-id="0748c-178">The text does not display in this view.</span></span>  

    <!--
        :::image type="complex" source="media/beginners-html-dom2.msft.png" alt-text="The mystery text A new element!?! is not found in index.html" lightbox="media/beginners-html-dom2.msft.png":::
        The mystery text `A new element!?!` is not found in `index.html`  
        :::image-end:::
    -->

1. <span data-ttu-id="0748c-179">ライブ タブを **開き、** マウス ポインター `A new element!?!` を置き、コンテキスト メニュー (右クリック) を開き、[検査] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0748c-179">Open the **live tab**, hover over `A new element!?!`, open the contextual menu (right-click) and then choose **Inspect**.</span></span>  
    
    :::image type="complex" source="media/beginners-html-dom3.msft.png" alt-text="テキストの検査" lightbox="media/beginners-html-dom3.msft.png":::
       <span data-ttu-id="0748c-181">テキストの検査</span><span class="sxs-lookup"><span data-stu-id="0748c-181">Inspecting some text</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="0748c-182">DevTools がページと一緒に開きます。</span><span class="sxs-lookup"><span data-stu-id="0748c-182">DevTools opens up alongside your page.</span></span> `<div>A new element!?!</div>` <span data-ttu-id="0748c-183">が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="0748c-183">is highlighted.</span></span> <span data-ttu-id="0748c-184">DevTools のこの構造は HTML のように見えますが **、DOM ツリーです**。</span><span class="sxs-lookup"><span data-stu-id="0748c-184">Although this structure in DevTools looks like HTML, it is the **DOM Tree**.</span></span>  
    
    :::image type="complex" source="media/beginners-html-dom4.msft.png" alt-text="DevTools がページと一緒に開いている" lightbox="media/beginners-html-dom4.msft.png":::
       <span data-ttu-id="0748c-186">DevTools がページと一緒に開いている</span><span class="sxs-lookup"><span data-stu-id="0748c-186">DevTools is open alongside the page</span></span>  
    :::image-end:::  
    
<span data-ttu-id="0748c-187">ページが読み込まれると、ブラウザーは HTML を使用してページの初期コンテンツを作成します。</span><span class="sxs-lookup"><span data-stu-id="0748c-187">When your page loads, the browser uses the HTML to create the initial content of the page.</span></span> <span data-ttu-id="0748c-188">DOM はページの現在のコンテンツを表します。時間の流中に変化する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0748c-188">The DOM represents the current content of the page, which may change over time.</span></span> 

<span data-ttu-id="0748c-189">HTML の下部にタグが付けられているため、コンテンツがページ `<div>A new element!?!</div>` `<script src="new.js"></script>` に追加されます。</span><span class="sxs-lookup"><span data-stu-id="0748c-189">The `<div>A new element!?!</div>` content is added to your page because of the `<script src="new.js"></script>` tag at the bottom of your HTML.</span></span> <span data-ttu-id="0748c-190">このタグを使用すると、一部の JavaScript コードが実行されます。</span><span class="sxs-lookup"><span data-stu-id="0748c-190">This tag causes some JavaScript code to run.</span></span> <span data-ttu-id="0748c-191">JavaScript の詳細については、後のチュートリアル [を参照してください](../javascript/index.md)。</span><span class="sxs-lookup"><span data-stu-id="0748c-191">Learn more about JavaScript in a [later tutorial](../javascript/index.md).</span></span>

<span data-ttu-id="0748c-192">今のところは、ページの内容を変更するスクリプト言語と考えておきます。</span><span class="sxs-lookup"><span data-stu-id="0748c-192">For now, think of it as a scripting language that may change the content of your page.</span></span> <span data-ttu-id="0748c-193">この場合、JavaScript コードがページ `<div>A new element!?!</div>` に追加されます。</span><span class="sxs-lookup"><span data-stu-id="0748c-193">In this case, JavaScript code adds `<div>A new element!?!</div>` to your page.</span></span> <span data-ttu-id="0748c-194">このテキストはライブ タブに **表示されますが** 、HTML には表示されません。</span><span class="sxs-lookup"><span data-stu-id="0748c-194">That is why this text is displayed in the **live** tab, but not in the HTML.</span></span>  

### <a name="edit-the-dom"></a><span data-ttu-id="0748c-195">DOM の編集</span><span class="sxs-lookup"><span data-stu-id="0748c-195">Edit the DOM</span></span>  

<span data-ttu-id="0748c-196">ライブ タブを離れることなくコンテンツの変更をすばやく試す場合は、DevTools を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="0748c-196">If you want to quickly experiment with content changes without ever leaving the live tab, try DevTools.</span></span>  

1.  <span data-ttu-id="0748c-197">DevTools で、マウス ポインターを置き、コンテキスト メニュー (右クリック) を開き `Your site!` **、[HTML として編集] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0748c-197">In DevTools, hover over `Your site!`, open the contextual menu (right-click) and choose **Edit as HTML**.</span></span>  
    
1.  <span data-ttu-id="0748c-198">次のコードで `<p>Your site!</p>` を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0748c-198">Replace `<p>Your site!</p>` with the following code.</span></span>  

```html
    ...
    <header>
        <p><b>Welcome to my site!</b></p>
        <button>Download my resume</button>
    </header>
    ...
```  

:::image type="complex" source="media/beginners-html-edit2.msft.png" alt-text="HTML としてノードを更新する" lightbox="media/beginners-html-edit2.msft.png":::
    <span data-ttu-id="0748c-200">HTML としてノードを更新する</span><span class="sxs-lookup"><span data-stu-id="0748c-200">Updating the node as HTML</span></span>  
<span data-ttu-id="0748c-201">::image-end:::</span><span class="sxs-lookup"><span data-stu-id="0748c-201">::image-end:::</span></span>  

1.  <span data-ttu-id="0748c-202">`Control` + `Enter` \(Windows、Linux\) または `Command` + \(macOS\) を選択して変更を保存するか、ボックスの外側 `Enter` を選択します。</span><span class="sxs-lookup"><span data-stu-id="0748c-202">Select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\) to save your changes, or select outside the box.</span></span> <span data-ttu-id="0748c-203">変更がページのライブ ビューに自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0748c-203">Your changes automatically show up in the live view of your page.</span></span> <span data-ttu-id="0748c-204">テキストが `Your site!` 新しいコンテンツに置き換えられた。</span><span class="sxs-lookup"><span data-stu-id="0748c-204">The text `Your site!` has been replaced with the new content.</span></span>  
    
    :::image type="complex" source="media/beginners-html-edit3.msft.png" alt-text="新しいコンテンツがページにすぐに表示される" lightbox="media/beginners-html-edit3.msft.png":::
       <span data-ttu-id="0748c-206">新しいコンテンツがページにすぐに表示される</span><span class="sxs-lookup"><span data-stu-id="0748c-206">The new content shows up immediately on the page</span></span>  
    :::image-end:::  
    
<span data-ttu-id="0748c-207">このワークフローは、コンテンツの変更を試す場合にのみ適しています。</span><span class="sxs-lookup"><span data-stu-id="0748c-207">This workflow is only suitable for experimenting with content changes.</span></span> <span data-ttu-id="0748c-208">ページを更新するか、タブを閉じると、変更は失われます。</span><span class="sxs-lookup"><span data-stu-id="0748c-208">If you refresh the page or close the tab, your changes are lost.</span></span> <span data-ttu-id="0748c-209">変更を保存する場合は、コードを HTML ファイルに手動でコピーします。</span><span class="sxs-lookup"><span data-stu-id="0748c-209">If you want to save your changes, manually copy the code to your HTML file.</span></span> <span data-ttu-id="0748c-210">次の 2 つのセクションでは、DOM ツリーからコンテンツを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0748c-210">The next couple of sections show you some more ways to change content from the DOM Tree.</span></span>  

## <a name="reorder-nodes"></a><span data-ttu-id="0748c-211">ノードの並べ替え</span><span class="sxs-lookup"><span data-stu-id="0748c-211">Reorder nodes</span></span>

<span data-ttu-id="0748c-212">DOM ノードの順序を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="0748c-212">You may also change the order of DOM nodes.</span></span> <span data-ttu-id="0748c-213">たとえば、Web ページでは、ナビゲーション メニューが下部の近くに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0748c-213">For example, on your web page the navigation menu is near the bottom.</span></span> <span data-ttu-id="0748c-214">上部に移動するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0748c-214">To move it to the top, perform the following steps.</span></span>  

1.  <span data-ttu-id="0748c-215">`<nav>`DevTools の**DOM ツリーで**ノードを検索します。</span><span class="sxs-lookup"><span data-stu-id="0748c-215">Find the `<nav>` node in the **DOM Tree** of DevTools.</span></span>  
    
    :::image type="complex" source="media/beginners-html-reorder1.msft.png" alt-text="ナビゲーション ノードが DevTools で強調表示されている" lightbox="media/beginners-html-reorder1.msft.png":::
       <span data-ttu-id="0748c-217">ナビゲーション ノードが DevTools で強調表示されている</span><span class="sxs-lookup"><span data-stu-id="0748c-217">The nav node is highlighted in DevTools</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0748c-218">ノードを `<nav>` 上にドラッグして、ノードがノードの後ろの最初の子 `<body>` になります。</span><span class="sxs-lookup"><span data-stu-id="0748c-218">Drag the `<nav>` node to the top, so that the node is the first child after the `<body>` node.</span></span>  
    
    :::image type="complex" source="media/beginners-html-reorder3.msft.png" alt-text="ナビゲーション ノードがページの上部にある" lightbox="media/beginners-html-reorder3.msft.png":::
        <span data-ttu-id="0748c-220">ナビゲーション ノードがページの上部にある</span><span class="sxs-lookup"><span data-stu-id="0748c-220">The nav node is at the top of the page</span></span>  
    :::image-end:::  
    
### <a name="delete-a-node"></a><span data-ttu-id="0748c-221">ノードの削除</span><span class="sxs-lookup"><span data-stu-id="0748c-221">Delete a node</span></span>

<span data-ttu-id="0748c-222">DOM ツリーからノードを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="0748c-222">You may also remove nodes from the DOM Tree.</span></span> <span data-ttu-id="0748c-223">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0748c-223">Perform the following steps.</span></span>

1.  <span data-ttu-id="0748c-224">DOM ツリー **で、** を選択します `<div>A new element!?!</div>` 。</span><span class="sxs-lookup"><span data-stu-id="0748c-224">In the **DOM Tree**, choose `<div>A new element!?!</div>`.</span></span> <span data-ttu-id="0748c-225">DevTools はノードを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="0748c-225">DevTools highlights the node.</span></span> 
    
1.  <span data-ttu-id="0748c-226">キーボードの `Delete` キーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0748c-226">Select the `Delete` key on your keyboard.</span></span>  <span data-ttu-id="0748c-227">ノード `<div>A new element!?!</div>` は DOM ツリーから削除されます。</span><span class="sxs-lookup"><span data-stu-id="0748c-227">The `<div>A new element!?!</div>` node is removed from the DOM Tree.</span></span>  
    
    :::image type="complex" source="media/beginners-html-delete2.msft.png" alt-text="ノードが削除されました" lightbox="media/beginners-html-delete2.msft.png":::
       <span data-ttu-id="0748c-229">ノードが削除されました</span><span class="sxs-lookup"><span data-stu-id="0748c-229">The node has been deleted</span></span>  
    :::image-end:::  
    
## <a name="copy-your-changes"></a><span data-ttu-id="0748c-230">変更をコピーする</span><span class="sxs-lookup"><span data-stu-id="0748c-230">Copy your changes</span></span>  

<span data-ttu-id="0748c-231">もう少しで完了です。</span><span class="sxs-lookup"><span data-stu-id="0748c-231">You're almost done.</span></span> <span data-ttu-id="0748c-232">DevTools でページにいくつかの変更を加えたが、ソース コードには保存されません。</span><span class="sxs-lookup"><span data-stu-id="0748c-232">You made a few changes to the page in DevTools, but they're not saved to your source code.</span></span>  

1.  <span data-ttu-id="0748c-233">[ライブ] **タブを更新します**。DOM ツリーで行った変更は消えます。</span><span class="sxs-lookup"><span data-stu-id="0748c-233">Refresh the **live tab**. The changes that you made in the DOM Tree disappear.</span></span> <span data-ttu-id="0748c-234">特に、テキスト `Your site!` はページの上部に戻り、テキストは `A new element!?!` 下部に戻ります。</span><span class="sxs-lookup"><span data-stu-id="0748c-234">In particular, the text `Your site!` returns to the top of the page, and the text `A new element!?!` returns to the bottom.</span></span>  
    
    :::image type="complex" source="media/beginners-html-copy1.msft.png" alt-text="行った変更はなくなりました" lightbox="media/beginners-html-copy1.msft.png":::
       <span data-ttu-id="0748c-236">行った変更はなくなりました</span><span class="sxs-lookup"><span data-stu-id="0748c-236">The changes that you made are gone</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0748c-237">次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="0748c-237">Copy the following code.</span></span>  
    
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
    
1.  <span data-ttu-id="0748c-238">[エディター] タブ **に戻り** 、ファイルの内容をコピー `index.html` したコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0748c-238">Go back to the **editor tab** and replace the content of your `index.html` file with the code that you copied.</span></span>  
    
    :::image type="complex" source="media/beginners-html-copy2.msft.png" alt-text="l ファイルindex.htmの外観" lightbox="media/beginners-html-copy2.msft.png":::
       <span data-ttu-id="0748c-240">ファイルの `index.html` 外観</span><span class="sxs-lookup"><span data-stu-id="0748c-240">How your `index.html` file should look</span></span>  
    :::image-end:::  
    
## <a name="next-steps"></a><span data-ttu-id="0748c-241">次のステップ</span><span class="sxs-lookup"><span data-stu-id="0748c-241">Next steps</span></span>  

*   <span data-ttu-id="0748c-242">このシリーズの次のチュートリアルはじめに[CSS][DevToolsBeginnersCss]を使用して、ページのスタイルを設定し、DevTools でスタイルの変更を試Microsoft Edgeします。</span><span class="sxs-lookup"><span data-stu-id="0748c-242">Complete the next tutorial in this series, [Get Started with CSS][DevToolsBeginnersCss], to learn how to style your page and experiment with style changes in Microsoft Edge DevTools.</span></span>  
*   <span data-ttu-id="0748c-243">DOM [の詳細については、「DOM の][MDNIntroductionDom] 概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0748c-243">Read [Introduction to the DOM][MDNIntroductionDom] to learn more about the DOM.</span></span>  
*   <span data-ttu-id="0748c-244">詳細な実践的な Web 開発 [エクスペリエンスについては、「Web 開発の][CourseraIntroductionToWebDevelopment] 概要」のようなコースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0748c-244">Check out a course like [Introduction to Web Development][CourseraIntroductionToWebDevelopment] for more hands-on web development experience.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="0748c-245">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="0748c-245">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!--- links --->  

[DevToolsBeginnersCss]: ./css.md "初級者向け DevTools: CSS はじめにを使用|Microsoft Docs"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge Insider"  

[CourseraIntroductionToWebDevelopment]: https://www.coursera.org/learn/web-development "Web 開発の概要|Coursera"  

[GlitchAlluringShockIndex]: https://glitch.com/edit/#!/alluring-shock?path=index.html "index.html - アリング ショック |Glitch"  

[MDNGettingStartedHtml]: https://developer.mozilla.org/docs/Learn/HTML/Introduction_to_HTML/Getting_started "HTML ファイルの使用を開始|MDN"  
[MDNIntroductionDom]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM の概要|MDN"  

> [!NOTE]
> <span data-ttu-id="0748c-252">このページの一部の情報は、[Google によって作成および共有][GoogleSitePolicies]されている著作物に基づいており、[Creative Commons Attribution 4.0 International License][CCA4IL] に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="0748c-252">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0748c-253">元のページはここで [見](https://developers.google.com/web/tools/chrome-devtools/beginners/html) つかり、キャ [サ][KatherineJackson] リン・ジャクソン \(Technical Writer Intern, Chrome DevTools\) によって作成されました。</span><span class="sxs-lookup"><span data-stu-id="0748c-253">The original page was found [here](https://developers.google.com/web/tools/chrome-devtools/beginners/html) and was authored by [Katherine Jackson][KatherineJackson] \(Technical Writer Intern, Chrome DevTools\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="0748c-255">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="0748c-255">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors  
