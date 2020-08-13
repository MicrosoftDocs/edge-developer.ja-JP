---
title: ワークスペースを使用してファイルを編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/31/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 7cafa2b186d151a478fa532cdac49ae46f2120c3
ms.sourcegitcommit: 4bc904c5d54347185f275bd76441975be471c320
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2020
ms.locfileid: "10926554"
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

# <span data-ttu-id="52c3b-103">ワークスペースを使用してファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="52c3b-103">Edit Files With Workspaces</span></span>  

> [!NOTE]
> <span data-ttu-id="52c3b-104">このチュートリアルの目標は、ワークスペースのセットアップと使用に関する実践的な練習を行い、独自のプロジェクトでワークスペースを使用できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="52c3b-104">The goal of this tutorial is to provide hands-on practice in setting up and using Workspaces, so that you are able to use Workspaces in your own projects.</span></span>  <span data-ttu-id="52c3b-105">ワークスペースを有効にした後、DevTools で作成したソースコードの変更をローカルコンピューターに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-105">You are able to save the changes to the source code, on your local computer, that you made within DevTools after you enable Workspaces.</span></span>  

> [!CAUTION]
> <span data-ttu-id="52c3b-106">**前提条件**: このチュートリアルを始める前に、次の方法を理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="52c3b-106">**Prerequisites**: Before beginning this tutorial, you should know how to:</span></span>  
> *   [<span data-ttu-id="52c3b-107">HTML、CSS、JavaScript を使って web ページを作成する</span><span class="sxs-lookup"><span data-stu-id="52c3b-107">Use HTML, CSS, and JavaScript to build a web page</span></span>][MDNWebGettingStarted]  
> *   [<span data-ttu-id="52c3b-108">DevTools を使って CSS の基本的な変更を行う</span><span class="sxs-lookup"><span data-stu-id="52c3b-108">Use DevTools to make basic changes to CSS</span></span>][DevToolsCssIndex]  
> *   [<span data-ttu-id="52c3b-109">ローカル HTTP web サーバーを実行する</span><span class="sxs-lookup"><span data-stu-id="52c3b-109">Run a local HTTP web server</span></span>][MDNSimpleLocalHTTPServer]  

## <span data-ttu-id="52c3b-110">概要</span><span class="sxs-lookup"><span data-stu-id="52c3b-110">Overview</span></span>  

<span data-ttu-id="52c3b-111">ワークスペースを使用すると、Devtools で行った変更を、コンピューター上の同じファイルのローカルコピーに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-111">Workspaces enable you to save a change that you make in Devtools to a local copy of the same file on your computer.</span></span>  <span data-ttu-id="52c3b-112">たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="52c3b-112">For example, suppose:</span></span>  

*   <span data-ttu-id="52c3b-113">自分のサイトのソースコードはデスクトップにあります。</span><span class="sxs-lookup"><span data-stu-id="52c3b-113">You have the source code for your site on your desktop.</span></span>  
*   <span data-ttu-id="52c3b-114">ソースコードディレクトリからローカル web サーバーを実行しているため、サイトにアクセスできるように `localhost:8080` なります。</span><span class="sxs-lookup"><span data-stu-id="52c3b-114">You are running a local web server from the source code directory, so that the site is accessible at `localhost:8080`.</span></span>  
*   <span data-ttu-id="52c3b-115">`localhost:8080`Microsoft Edge で開かれており、DevTools を使ってサイトの CSS を変更しています。</span><span class="sxs-lookup"><span data-stu-id="52c3b-115">You opened `localhost:8080`  in Microsoft Edge, and you are using DevTools to change the CSS of the site.</span></span>  

<span data-ttu-id="52c3b-116">ワークスペースを有効にすると、DevTools で行った CSS の変更が、デスクトップのソースコードに保存されます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-116">With Workspaces enabled, the CSS changes that you make within DevTools are saved to the source code on your desktop.</span></span>  

## <span data-ttu-id="52c3b-117">制限事項</span><span class="sxs-lookup"><span data-stu-id="52c3b-117">Limitations</span></span>  

<span data-ttu-id="52c3b-118">モダンフレームワークを使用している場合は、可能な限り早く実行するために最適化された形式に簡単に保持できる形式からソースコードを変換する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="52c3b-118">If you are using a modern framework, it probably transforms your source code from a format that is easy to maintain into a format that is optimized to run as quickly as possible.</span></span>  
<span data-ttu-id="52c3b-119">通常、ワークスペースでは、最適化されたコードを[ソースマップ][TreehouseBlogSourceMaps]のヘルプを使用して元のソースコードに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-119">Workspaces is usually able to map the optimized code back to your original source code with the help of [source maps][TreehouseBlogSourceMaps].</span></span>  <span data-ttu-id="52c3b-120">ただし、フレームワーク間のソースマップの使い方については、さまざまなバリエーションがあります。</span><span class="sxs-lookup"><span data-stu-id="52c3b-120">But there is a lot of variation between frameworks over how they use source maps.</span></span>  <span data-ttu-id="52c3b-121">Devtools は、すべてのバリエーションをサポートしているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="52c3b-121">Devtools simply does not support all of the variations.</span></span>  

<span data-ttu-id="52c3b-122">ワークスペースは、次のフレームワークでは動作しないことがわかっています。</span><span class="sxs-lookup"><span data-stu-id="52c3b-122">Workspaces is known to not work with these frameworks:</span></span>  

*   <span data-ttu-id="52c3b-123">反応するアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="52c3b-123">Create React App</span></span>  
    
    <!-- If you run into issues while using Workspaces with your framework of choice, or you get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  
    
## <span data-ttu-id="52c3b-124">関連する機能: ローカルの上書き</span><span class="sxs-lookup"><span data-stu-id="52c3b-124">Related feature: Local Overrides</span></span>  

<span data-ttu-id="52c3b-125">**ローカルオーバーライド**は、ワークスペースに似た別の devtools 機能です。</span><span class="sxs-lookup"><span data-stu-id="52c3b-125">**Local Overrides** is another DevTools feature that is similar to Workspaces.</span></span>  <span data-ttu-id="52c3b-126">ページに対する変更を試す必要があり、ページの読み込み全体でそれらの変更を確認する必要がある場合は、ローカルの上書きを使用しますが、ページのソースコードへの変更のマッピングについては注意してください。</span><span class="sxs-lookup"><span data-stu-id="52c3b-126">Use Local Overrides when you want to experiment with changes to a page, and you need to see those changes across page loads, but you do not care about mapping your changes to the source code of the page.</span></span>  

<!--Todo: add section when content is ready  -->  

## <span data-ttu-id="52c3b-127">手順 1: セットアップ</span><span class="sxs-lookup"><span data-stu-id="52c3b-127">Step 1: Set-up</span></span>  

<span data-ttu-id="52c3b-128">このチュートリアルを実行して、ワークスペースの実践的なエクスペリエンスを実現します。</span><span class="sxs-lookup"><span data-stu-id="52c3b-128">Complete this tutorial to get hands-on experience with Workspaces.</span></span>  

### <span data-ttu-id="52c3b-129">デモを設定する</span><span class="sxs-lookup"><span data-stu-id="52c3b-129">Set up the demo</span></span>  

1.  <span data-ttu-id="52c3b-130">[デモを開き][GlitchWorkspacesDemo]ます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-130">[Open the demo][GlitchWorkspacesDemo].</span></span>  <!--In the top-left of the editor, a randomly-generated project name is displayed.  -->  
    
    :::image type="complex" source="../media/workspaces-glitch-workspaces-demo-source.msft.png" alt-text="エラープロジェクト" lightbox="../media/workspaces-glitch-workspaces-demo-source.msft.png":::
       <span data-ttu-id="52c3b-132">エラープロジェクト</span><span class="sxs-lookup"><span data-stu-id="52c3b-132">A Glitch project</span></span>  
    :::image-end:::  
    
    <!--1.  Choose the project name.  -->
    <!--1.  Select **Advanced Options** > **Download Project**.  
    
    :::image type="complex" source="../media/workspaces-glitch-advanced-options-download-project.msft.png" alt-text="The Download Project button" lightbox="../media/workspaces-glitch-advanced-options-download-project.msft.png":::
       The Download Project button  
    :::image-end:::  
    -->
    <!--1.  Close the tab.  -->
    <!--1.  Unzip the source code and move the unzipped `app` directory to your desktop.  For the rest of this tutorial this directory is referred to as `~/Desktop/app`.  -->  
    
1.  <span data-ttu-id="52c3b-133">`app`デスクトップにディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="52c3b-133">Create an `app` directory on your desktop.</span></span>  <span data-ttu-id="52c3b-134">ディレクトリ内のファイルのコピーを保存 `workspaces-demo` します。</span><span class="sxs-lookup"><span data-stu-id="52c3b-134">Save copies of the files in the `workspaces-demo` directory.</span></span>  <span data-ttu-id="52c3b-135">このチュートリアルの残りの部分では、というディレクトリがと呼ばれて `~/Desktop/app` います。</span><span class="sxs-lookup"><span data-stu-id="52c3b-135">For the rest of this tutorial this directory is referred to as `~/Desktop/app`.</span></span>  
1.  <span data-ttu-id="52c3b-136">でローカル web サーバーを起動 `~/Desktop/app` します。</span><span class="sxs-lookup"><span data-stu-id="52c3b-136">Start a local web server in `~/Desktop/app`.</span></span>  <span data-ttu-id="52c3b-137">以下は、起動のためのサンプルコードです `SimpleHTTPServer` が、好きなサーバーを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-137">Below is some sample code for starting up `SimpleHTTPServer`, but you may use whatever server you prefer.</span></span>  
    
    :::row:::
       :::column span="":::
          ```bash
          cd ~/Desktop/app
          python -m SimpleHTTPServer # Python 2
          ```  
       :::column-end:::
       :::column span="":::
          ```bash
          cd ~/Desktop/app
          python -m http.server # Python 3
          ```  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="52c3b-138">Microsoft Edge でタブを開き、ローカルでホストされているバージョンのサイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="52c3b-138">Open a tab in Microsoft Edge and go to locally-hosted version of the site.</span></span>  <span data-ttu-id="52c3b-139">またはのような URL を使用してアクセスできる必要があり `localhost:8080` `http://0.0.0.0:8080` ます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-139">You should be able to access it using a URL like `localhost:8080` or `http://0.0.0.0:8080`.</span></span>  <span data-ttu-id="52c3b-140">正確な[ポート番号][WikiPortURLs]は異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="52c3b-140">The exact [port number][WikiPortURLs] may be different.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo.msft.png" alt-text="デモ" lightbox="../media/workspaces-workspaces-demo.msft.png":::
       <span data-ttu-id="52c3b-142">デモ</span><span class="sxs-lookup"><span data-stu-id="52c3b-142">The demo</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="52c3b-143">DevTools のセットアップ</span><span class="sxs-lookup"><span data-stu-id="52c3b-143">Set up DevTools</span></span>  

1.  <span data-ttu-id="52c3b-144">[ `Control` + `Shift` + `J` \ (Windows \)] または [ `Command` + `Option` + `J` \ (macOS \)] を選択して、devtools の**コンソール**パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-144">Select `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) to open the **Console** panel of DevTools.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-console.msft.png" alt-text="コンソールパネル" lightbox="../media/workspaces-workspaces-demo-console.msft.png":::
       <span data-ttu-id="52c3b-146">**コンソール**パネル</span><span class="sxs-lookup"><span data-stu-id="52c3b-146">The **Console** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="52c3b-147">[**ソース**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="52c3b-147">Choose the **Sources** tab.</span></span>  
1.  <span data-ttu-id="52c3b-148">[ **Filesystem** ] タブを選びます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-148">Choose the **Filesystem** tab.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem.msft.png" alt-text="[Filesystem] タブ" lightbox="../media/workspaces-workspaces-demo-sources-filesystem.msft.png":::
       <span data-ttu-id="52c3b-150">[ **Filesystem** ] タブ</span><span class="sxs-lookup"><span data-stu-id="52c3b-150">The **Filesystem** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="52c3b-151">[**ワークスペースにフォルダーを追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-151">Choose **Add Folder To Workspace**.</span></span>  
1.  <span data-ttu-id="52c3b-152">Enter キーを押す `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="52c3b-152">Enter `~/Desktop/app`.</span></span>  
1.  <span data-ttu-id="52c3b-153">ディレクトリの読み取りと書き込みを行うための DevTools アクセス許可を与えるには、[**許可**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-153">Choose **Allow** to give DevTools permission to read and write to the directory.</span></span>  
    <span data-ttu-id="52c3b-154">[ **Filesystem** ] タブで、、、およびの横に緑の点が表示され `index.html` `script.js` `styles.css` ます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-154">In the **Filesystem** tab, there is now a green dot next to `index.html`, `script.js`, and `styles.css`.</span></span>  <span data-ttu-id="52c3b-155">これらの緑の点は、DevTools がページのネットワークリソースとの間のマッピングを確立したことを意味 `~/Desktop/app` します。</span><span class="sxs-lookup"><span data-stu-id="52c3b-155">These green dots mean that DevTools has established a mapping between the network resources of the page, and the files in `~/Desktop/app`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png" alt-text="[Filesystem] タブに、ローカルファイルとネットワーク間のマッピングが表示されるようになりました" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png":::
       <span data-ttu-id="52c3b-157">[ **Filesystem** ] タブに、ローカルファイルとネットワーク間のマッピングが表示されるようになりました</span><span class="sxs-lookup"><span data-stu-id="52c3b-157">The **Filesystem** tab now shows a mapping between the local files and the network ones</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="52c3b-158">手順 2: CSS の変更をディスクに保存する</span><span class="sxs-lookup"><span data-stu-id="52c3b-158">Step 2: Save a CSS change to disk</span></span>  

1.  <span data-ttu-id="52c3b-159">[開く] `styles.css` を選びます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-159">Open `styles.css`.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="52c3b-160">`color`要素のプロパティ `h1` はに設定され `fuchsia` ます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-160">The `color` property of `h1` elements is set to `fuchsia`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png" alt-text="テキストエディターでスタイルの css を表示する" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png":::
       <span data-ttu-id="52c3b-162">`styles.css`テキストエディターでの表示</span><span class="sxs-lookup"><span data-stu-id="52c3b-162">Viewing `styles.css` in a text editor</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="52c3b-163">[**要素**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="52c3b-163">Choose the **Elements** tab.</span></span>  
1.  <span data-ttu-id="52c3b-164">`color`要素のプロパティの値 `<h1>` を、お気に入りの色に変更します。</span><span class="sxs-lookup"><span data-stu-id="52c3b-164">Change the value of the `color` property of the `<h1>` element to your favorite color.</span></span>  
    <span data-ttu-id="52c3b-165">[ `<h1>` **スタイル**] ウィンドウで CSS ルールが適用されていることを確認するために、 **DOM ツリー**で要素を選ぶ必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="52c3b-165">Remember that you need to choose the `<h1>` element in the **DOM Tree** in order to see the CSS rules applied to it in the **Styles** pane.</span></span>  <span data-ttu-id="52c3b-166">[] の横にある緑の点は、 `styles.css:1` 加えた変更がマップされていることを意味 `~/Desktop/app/styles.css` します。</span><span class="sxs-lookup"><span data-stu-id="52c3b-166">The green dot next to `styles.css:1` means that any change that you make are mapped to `~/Desktop/app/styles.css`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-css.msft.png" alt-text="ファイルがリンクされていることを示す緑色のインジケーター" lightbox="../media/workspaces-workspaces-demo-elements-styles-css.msft.png":::
       <span data-ttu-id="52c3b-168">ファイルがリンクされていることを示す緑色のインジケーター</span><span class="sxs-lookup"><span data-stu-id="52c3b-168">The green indicator that the file is linked</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="52c3b-169">`styles.css`もう一度テキストエディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-169">Open `styles.css` in a text editor again.</span></span>  <span data-ttu-id="52c3b-170">`color`これで、プロパティが [お気に入りの色」に設定されました。</span><span class="sxs-lookup"><span data-stu-id="52c3b-170">The `color` property is now set to your favorite color.</span></span>  
1.  <span data-ttu-id="52c3b-171">ページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="52c3b-171">Reload the page.</span></span>  <span data-ttu-id="52c3b-172">要素の色 `<h1>` は、引き続き好みの色に設定されます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-172">The color of the `<h1>` element is still set to your favorite color.</span></span>  <span data-ttu-id="52c3b-173">これは、変更を加えたときに、DevTools によってディスクへの変更が保存されたためです。</span><span class="sxs-lookup"><span data-stu-id="52c3b-173">This works because when you made the change, DevTools saved the change to disk.</span></span>  <span data-ttu-id="52c3b-174">次に、ページを再ロードすると、ローカルサーバーは、ファイルの変更されたコピーをディスクから提供します。</span><span class="sxs-lookup"><span data-stu-id="52c3b-174">And then, when you reloaded the page, your local server served the modified copy of the file from disk.</span></span>  
    
## <span data-ttu-id="52c3b-175">手順 3: HTML の変更をディスクに保存する</span><span class="sxs-lookup"><span data-stu-id="52c3b-175">Step 3: Save an HTML change to disk</span></span>  

### <span data-ttu-id="52c3b-176">[要素] パネルで HTML を変更する</span><span class="sxs-lookup"><span data-stu-id="52c3b-176">Change HTML from the Elements Panel</span></span>  

<span data-ttu-id="52c3b-177">HTML は、要素パネルから変更できますが、DOM ツリーへの変更はディスクに保存されず、現在のブラウザーセッションのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="52c3b-177">You may make changes to the HTML from the Element Panel, but your changes to the DOM tree are not saved to disk and only effect the current browser session.</span></span>  
<span data-ttu-id="52c3b-178">DOM ツリーは HTML ではありません。</span><span class="sxs-lookup"><span data-stu-id="52c3b-178">The DOM tree is not HTML.</span></span>  

<!--### Try changing HTML from the Elements panel  

> [!WARNING]
> The workflow that you are about to try does not work.  You are trying it now so that you do not waste time later trying to figure out why it is not working.  

1.  Choose the **Elements** tab.  
1.  Double-click the text content of the `h1` element, which says `Workspaces Demo`, and replace it with `I ❤️  Cake`.  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-change-h1.msft.png" alt-text="Attempting to change HTML from the DOM Tree of the Elements panel" lightbox="../media/workspaces-workspaces-demo-change-h1.msft.png":::
       Attempting to change HTML from the **DOM Tree** of the **Elements** panel  
    :::image-end:::  
    
1.  Open `~/Desktop/app/index.html` in a text editor.  The change that you just made does not appear.  
1.  Reload the page.  The page reverts to its original title.  
    
#### Optional: Why it is not working  

> [!NOTE]
> This section describes why the workflow from [Try changing HTML from the Elements panel](#try-changing-html-from-the-elements-panel) does not work.  You should skip this section if you do not care why.  

*   The tree of nodes that you see on the **Elements** panel represents the [DOM][MDNWebAPIsDOM] of the page.  
*   To display a page, a browser fetches HTML over the network, parses the HTML, and then converts it into a tree of DOM nodes.  
*   If the page has any JavaScript, that JavaScript may add, delete, or change DOM nodes.  CSS may change the DOM, too, using the [`content`][MDNCSSContent] property.  
*   The browser eventually uses the DOM to determine what content it should present to browser users.  
*   Therefore, the final state of the page that users see may be very different from the HTML that the browser fetched.  
*   This makes it difficult for DevTools to resolve where a change made in the **Elements** panel should be saved, because the DOM is affected by HTML, JavaScript, and CSS.  

In short, the **DOM Tree** `!==` HTML.  
-->  

### <span data-ttu-id="52c3b-179">[ソース] パネルで HTML を変更する</span><span class="sxs-lookup"><span data-stu-id="52c3b-179">Change HTML from the Sources panel</span></span>  

<span data-ttu-id="52c3b-180">ページの HTML への変更を保存する場合は、[**ソース**] パネルを使用します。</span><span class="sxs-lookup"><span data-stu-id="52c3b-180">If you want to save a change to the HTML of the page, do it using the **Sources** panel.</span></span>  

1.  <span data-ttu-id="52c3b-181">[**ソース**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="52c3b-181">Choose the **Sources** tab.</span></span>  
1.  <span data-ttu-id="52c3b-182">[**ページ**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="52c3b-182">Choose the **Page** tab.</span></span>  
1.  <span data-ttu-id="52c3b-183">[ **(インデックス)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-183">Choose **(index)**.</span></span>  <span data-ttu-id="52c3b-184">ページの HTML が開きます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-184">The HTML for the page opens.</span></span>  
1.  <span data-ttu-id="52c3b-185">置換後 `<h1>Workspaces Demo</h1>` の文字列 `<h1>I ❤️  Cake</h1>`</span><span class="sxs-lookup"><span data-stu-id="52c3b-185">Replace `<h1>Workspaces Demo</h1>` with `<h1>I ❤️  Cake</h1>`.</span></span>  <span data-ttu-id="52c3b-186">次の図を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52c3b-186">See the following figure.</span></span>  
1.  <span data-ttu-id="52c3b-187">`Control` + `S` 変更を保存するには、\ (Windows \) または `Command` + `S` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="52c3b-187">Select `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save the change.</span></span>  
1.  <span data-ttu-id="52c3b-188">ページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="52c3b-188">Reload the page.</span></span>  <span data-ttu-id="52c3b-189">`<h1>`要素に新しいテキストが引き続き表示されています。</span><span class="sxs-lookup"><span data-stu-id="52c3b-189">The `<h1>` element is still displaying the new text.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-page-h1.msft.png" alt-text="[ソース] パネルでの HTML の変更" lightbox="../media/workspaces-workspaces-demo-sources-page-h1.msft.png":::
       <span data-ttu-id="52c3b-191">行12はに設定されています</span><span class="sxs-lookup"><span data-stu-id="52c3b-191">Line 12 has been set to</span></span> `I ❤️  Cake`  
    :::image-end:::  
    
1.  <span data-ttu-id="52c3b-192">[開く] `~/Desktop/app/index.html` を選びます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-192">Open `~/Desktop/app/index.html`.</span></span>  <span data-ttu-id="52c3b-193">`<h1>`要素に新しいテキストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="52c3b-193">The `<h1>` element contains the new text.</span></span>  
    
## <span data-ttu-id="52c3b-194">手順 4: JavaScript の変更をディスクに保存する</span><span class="sxs-lookup"><span data-stu-id="52c3b-194">Step 4: Save a JavaScript change to disk</span></span>  

<span data-ttu-id="52c3b-195">[**ソース**] パネルも JavaScript を変更する場所です。</span><span class="sxs-lookup"><span data-stu-id="52c3b-195">The **Sources** panel is also the place to make changes to JavaScript.</span></span>  <span data-ttu-id="52c3b-196">ただし、サイトを変更するときに、[**要素**] パネルや**コンソール**パネルなどの他のパネルにアクセスする必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="52c3b-196">But sometimes you need to access other panels, such as the **Elements** panel or the **Console** panel, while making changes to your site.</span></span>  <span data-ttu-id="52c3b-197">他のパネルと共に**ソース**パネルを開く方法があります。</span><span class="sxs-lookup"><span data-stu-id="52c3b-197">There is a way to have the **Sources** panel open alongside other panels.</span></span>  

1.  <span data-ttu-id="52c3b-198">[**要素**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="52c3b-198">Choose the **Elements** tab.</span></span>  
1.  <span data-ttu-id="52c3b-199">[ `Control` + `Shift` + `P` \ (Windows \)] または [ `Command` + `Shift` + `P` \ (macOS \)] を選びます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-199">Select `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  <span data-ttu-id="52c3b-200">**コマンドメニュー**が開きます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-200">The **Command Menu** opens.</span></span>  
1.  <span data-ttu-id="52c3b-201">入力して `QS` 、[**クイックソースの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="52c3b-201">Type `QS`, then select **Show Quick Source**.</span></span>  <span data-ttu-id="52c3b-202">[DevTools] ウィンドウの下部に、[**クイックソース**] タブが表示されています。 タブには `index.html` 、[**ソース**] パネルで最後に編集したファイルの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-202">At the bottom of your DevTools window there is now a **Quick Source** tab.  The tab is displaying the contents of `index.html`, which is the last file you edited in the **Sources** panel.</span></span>  <span data-ttu-id="52c3b-203">[**クイックソース**] タブでは、[**ソース**] パネルからエディターが表示されるため、他のパネルを開いたままファイルを編集できます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-203">The **Quick Source** tab gives you the editor from the **Sources** panel, so that you are able to edit files while having other panels open.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png" alt-text="[コマンド] メニューを使用して [クイックソース] タブを開く" lightbox="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png":::
       <span data-ttu-id="52c3b-205">**コマンドメニュー**を使用して [**クイックソース**] タブを開く</span><span class="sxs-lookup"><span data-stu-id="52c3b-205">Opening the **Quick Source** tab using the **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="52c3b-206">[ `Control` + `P` \ (Windows \)] または [ `Command` + `P` \ (macOS \)] を選択して、[**ファイルを開く**] ダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-206">Select `Control`+`P` \(Windows\) or `Command`+`P` \(macOS\) to open the **Open File** dialog.</span></span>  <span data-ttu-id="52c3b-207">次の図を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52c3b-207">See the following figure.</span></span>  
1.  <span data-ttu-id="52c3b-208">入力して `script` 、[**アプリ/script.js**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-208">Type `script`, then select **app/script.js**.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-script.msft.png" alt-text="[ファイルを開く] ダイアログボックスを使用して script.js を開く" lightbox="../media/workspaces-workspaces-demo-search-script.msft.png":::
       <span data-ttu-id="52c3b-210">[ `script.js` ファイルを**開く**] ダイアログボックスを開く</span><span class="sxs-lookup"><span data-stu-id="52c3b-210">Opening `script.js` using the **Open File** dialog</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="52c3b-211">`Save Changes To Disk With Workspaces`デモのリンクは、定期的にスタイル設定されています。</span><span class="sxs-lookup"><span data-stu-id="52c3b-211">The `Save Changes To Disk With Workspaces` link in the demo is styled regularly.</span></span>  
    
1.  <span data-ttu-id="52c3b-212">[**クイックソース**] タブを使用して、 **script.js**の下部に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="52c3b-212">Add the following code to the bottom of **script.js** using the **Quick Source** tab.</span></span>  
    
    ```javascript
    console.log('greetings from script.js');
    document.querySelector('a').style = 'font-style:italic';
    ```  
    
1.  <span data-ttu-id="52c3b-213">`Control` + `S` 変更を保存するには、\ (Windows \) または `Command` + `S` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="52c3b-213">Select `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save the change.</span></span>  
1.  <span data-ttu-id="52c3b-214">ページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="52c3b-214">Reload the page.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="52c3b-215">ページ上のリンクが斜体になりました。</span><span class="sxs-lookup"><span data-stu-id="52c3b-215">The link on the page is now italicized.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png" alt-text="ページ上のリンクが斜体になりました" lightbox="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png":::
       <span data-ttu-id="52c3b-217">ページ上のリンクが斜体になりました</span><span class="sxs-lookup"><span data-stu-id="52c3b-217">The link on the page is now italicized</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="52c3b-218">次のステップ</span><span class="sxs-lookup"><span data-stu-id="52c3b-218">Next steps</span></span>  

<span data-ttu-id="52c3b-219">このチュートリアルで学んだことを使用して、自分のプロジェクトでワークスペースをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="52c3b-219">Use what you have learned in this tutorial to set up Workspaces in your own project.</span></span>  <!-- If you run into any issues or are able to get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  

<!--  
If you have more feedback on these topics or anything else, please use any of the channels below:  

*   [Mailing List][AlphabetGroupsAlphabetBrowserDevTools]  
*   [Twitter][TwitterAlphabetBrowserDevTools]  
-->  

<!-- links -->  

[DevToolsCssIndex]: ../css/index.md# "CSS の表示と変更の概要 |Microsoft ドキュメント"  

<!--[LocalOverrides]: ../whats-new/2018/01/devtools#overrides -->  

<!--[AlphabetGroupsAlphabetBrowserDevTools]: https://groups.alphabet.com/forum/#!forum/alphabet-browser-developer-tools "Alphabet Browser DevTools - Alphabet Groups"  -->  

[GlitchWorkspacesDemo]: https://glitch.com/edit/#!/microsoft-edge-chromium-devtools?path=workspaces-demo/index.html:1:0 "ワークスペースデモファイル |故障"  

[MDNCSSContent]: https://developer.mozilla.org/docs/Web/CSS/content "コンテンツ-CSS: カスケードスタイルシート |MDN"  
[MDNWebGettingStarted]: https://developer.mozilla.org/docs/Learn/Getting_started_with_the_web "Web の概要 |MDN"  
[MDNSimpleLocalHTTPServer]: https://developer.mozilla.org/docs/Learn/Common_questions/set_up_a_local_testing_server#Running_a_simple_local_HTTP_server "簡単なローカル HTTP サーバーを実行する |MDN"  
[MDNWebAPIsDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM の概要-Web Api |MDN"  

<!--[StackOverflowAlphabetBrowserDevTools]: https://stackoverflow.com/questions/ask?tags=alphabet-browser-devtools "Alphabet Browser DevTools - Stack Overflow"  -->

[TreehouseBlogSourceMaps]: https://blog.teamtreehouse.com/introduction-source-maps "ソースマップの概要 |Treehouse ブログ"  

<!-- [TwitterAlphabetBrowserDevTools]: https://twitter.com/alphabetbrowserdevtools "Alphabet Browser DevTools \(@AlphabetBrowserDevTools\) | Twitter"  -->

[WikiPortURLs]: https://en.wikipedia.org/wiki/Port_(computer_networking)#Use_in_URLs "ポート \ (コンピューターネットワーク \)-Wikipedia"  

> [!NOTE]
> <span data-ttu-id="52c3b-228">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="52c3b-228">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="52c3b-229">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/workspaces/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="52c3b-229">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/workspaces/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="52c3b-231">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="52c3b-231">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
