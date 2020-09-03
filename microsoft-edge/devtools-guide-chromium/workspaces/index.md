---
description: DevTools で行った変更をディスクに保存する方法について説明します。
title: ワークスペースを使用してファイルを編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: fd72021e75c536fa38c27ae17e4b1678eb4ca85f
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992723"
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

# <span data-ttu-id="67dba-104">ワークスペースを使用してファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="67dba-104">Edit files with Workspaces</span></span>  

> [!NOTE]
> <span data-ttu-id="67dba-105">このチュートリアルの目標は、ワークスペースのセットアップと使用に関する実践的な練習を行い、独自のプロジェクトでワークスペースを使用できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="67dba-105">The goal of this tutorial is to provide hands-on practice in setting up and using Workspaces, so that you are able to use Workspaces in your own projects.</span></span>  <span data-ttu-id="67dba-106">ワークスペースを有効にした後、DevTools で作成したソースコードの変更をローカルコンピューターに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="67dba-106">You are able to save the changes to the source code, on your local computer, that you made within DevTools after you enable Workspaces.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="67dba-107">**前提条件**: このチュートリアルを始める前に、次の操作を実行する方法について理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="67dba-107">**Prerequisites**: Before beginning this tutorial, you should know how to perform the following actions.</span></span>  
> 
> *   [<span data-ttu-id="67dba-108">Html、CSS、JavaScript を使って web ページを作成する</span><span class="sxs-lookup"><span data-stu-id="67dba-108">Use html, CSS, and JavaScript to build a web page</span></span>][MDNWebGettingStarted]  
> *   [<span data-ttu-id="67dba-109">DevTools を使って CSS の基本的な変更を行う</span><span class="sxs-lookup"><span data-stu-id="67dba-109">Use DevTools to make basic changes to CSS</span></span>][DevToolsCssIndex]  
> *   [<span data-ttu-id="67dba-110">ローカル HTTP web サーバーを実行する</span><span class="sxs-lookup"><span data-stu-id="67dba-110">Run a local HTTP web server</span></span>][MDNSimpleLocalHTTPServer]  

## <span data-ttu-id="67dba-111">概要</span><span class="sxs-lookup"><span data-stu-id="67dba-111">Overview</span></span>  

<span data-ttu-id="67dba-112">ワークスペースを使用すると、Devtools で行った変更を、コンピューター上の同じファイルのローカルコピーに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="67dba-112">Workspaces enable you to save a change that you make in Devtools to a local copy of the same file on your computer.</span></span>  <span data-ttu-id="67dba-113">このチュートリアルでは、コンピューターに次の設定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="67dba-113">For this tutorial, you should have the following settings on your machine.</span></span>  

*   <span data-ttu-id="67dba-114">自分のサイトのソースコードはデスクトップにあります。</span><span class="sxs-lookup"><span data-stu-id="67dba-114">You have the source code for your site on your desktop.</span></span>  
*   <span data-ttu-id="67dba-115">ソースコードディレクトリからローカル web サーバーを実行しているため、サイトにアクセスできるように `localhost:8080` なります。</span><span class="sxs-lookup"><span data-stu-id="67dba-115">You are running a local web server from the source code directory, so that the site is accessible at `localhost:8080`.</span></span>  
*   <span data-ttu-id="67dba-116">`localhost:8080`Microsoft Edge で開かれており、DevTools を使ってサイトの CSS を変更しています。</span><span class="sxs-lookup"><span data-stu-id="67dba-116">You opened `localhost:8080` in Microsoft Edge, and you are using DevTools to change the CSS of the site.</span></span>  

<span data-ttu-id="67dba-117">ワークスペースを有効にすると、DevTools で行った CSS の変更が、デスクトップのソースコードに保存されます。</span><span class="sxs-lookup"><span data-stu-id="67dba-117">With Workspaces enabled, the CSS changes that you make within DevTools are saved to the source code on your desktop.</span></span>  

## <span data-ttu-id="67dba-118">制限事項</span><span class="sxs-lookup"><span data-stu-id="67dba-118">Limitations</span></span>  

<span data-ttu-id="67dba-119">モダンフレームワークを使用している場合は、可能な限り早く実行するために最適化された形式に簡単に保持できる形式からソースコードを変換する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="67dba-119">If you are using a modern framework, it probably transforms your source code from a format that is easy to maintain into a format that is optimized to run as quickly as possible.</span></span>  

<span data-ttu-id="67dba-120">通常、ワークスペースでは、最適化されたコードを [ソースマップ][TreehouseBlogSourceMaps]のヘルプを使用して元のソースコードに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="67dba-120">Workspaces is usually able to map the optimized code back to your original source code with the help of [source maps][TreehouseBlogSourceMaps].</span></span>  <span data-ttu-id="67dba-121">ただし、フレームワーク間のソースマップの使用方法については、フレームワーク間に多くのバリエーションがあります。</span><span class="sxs-lookup"><span data-stu-id="67dba-121">But there is a lot of variation between frameworks over how each uses source maps.</span></span>  <span data-ttu-id="67dba-122">Devtools は、単純にすべてのバリエーションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="67dba-122">Devtools simply does support all of the variations.</span></span>  

<span data-ttu-id="67dba-123">ワークスペースは、次のフレームワークで動作しないことがわかっています。</span><span class="sxs-lookup"><span data-stu-id="67dba-123">Workspaces is known to not work with the following framework.</span></span>  

*   <span data-ttu-id="67dba-124">反応するアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="67dba-124">Create React App</span></span>  

    <!-- If you run into issues while using Workspaces with your framework of choice, or you get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  
    
## <span data-ttu-id="67dba-125">関連する機能: ローカルの上書き</span><span class="sxs-lookup"><span data-stu-id="67dba-125">Related feature: Local overrides</span></span>  

<span data-ttu-id="67dba-126">**ローカルオーバーライド** は、ワークスペースに似た別の devtools 機能です。</span><span class="sxs-lookup"><span data-stu-id="67dba-126">**Local Overrides** is another DevTools feature that is similar to Workspaces.</span></span>  <span data-ttu-id="67dba-127">ページの変更を試す必要がある場合は、ローカルの上書きを使用しますが、ページの読み込み全体で変更を確認する必要がありますが、ページのソースコードへの変更のマッピングについては注意してください。</span><span class="sxs-lookup"><span data-stu-id="67dba-127">Use Local Overrides when you want to experiment with changes to a page, and you need to see the changes across page loads, but you do not care about mapping your changes to the source code of the page.</span></span>  

<!--Todo: add section when content is ready  -->  

## <span data-ttu-id="67dba-128">手順 1: セットアップ</span><span class="sxs-lookup"><span data-stu-id="67dba-128">Step 1: Set up</span></span>  

<span data-ttu-id="67dba-129">次の操作を実行して、ワークスペースの実践的なエクスペリエンスを実現します。</span><span class="sxs-lookup"><span data-stu-id="67dba-129">Complete the following actions, to get hands-on experience with Workspaces.</span></span>  

### <span data-ttu-id="67dba-130">デモを設定する</span><span class="sxs-lookup"><span data-stu-id="67dba-130">Set up the demo</span></span>  

1.  <span data-ttu-id="67dba-131">[デモを開き][GlitchWorkspacesDemo]ます。</span><span class="sxs-lookup"><span data-stu-id="67dba-131">[Open the demo][GlitchWorkspacesDemo].</span></span>  <!--In the top-left of the editor, a randomly-generated project name is displayed.  -->  
    
    :::image type="complex" source="../media/workspaces-glitch-workspaces-demo-source.msft.png" alt-text="エラープロジェクト" lightbox="../media/workspaces-glitch-workspaces-demo-source.msft.png":::
       <span data-ttu-id="67dba-133">エラープロジェクト</span><span class="sxs-lookup"><span data-stu-id="67dba-133">A Glitch project</span></span>  
    :::image-end:::  
    
    <!--1.  Choose the project name.  -->  
    <!--1.  Select **Advanced Options** > **Download Project**.  
    
    :::image type="complex" source="../media/workspaces-glitch-advanced-options-download-project.msft.png" alt-text="The Download Project button" lightbox="../media/workspaces-glitch-advanced-options-download-project.msft.png":::
       The Download Project button  
    :::image-end:::  

    -->  
    <!--1.  Close the tab.  -->  
    <!--1.  Unzip the source code and move the unzipped `app` directory to your desktop.  For the rest of this tutorial the unzipped directory is referred to as `~/Desktop/app`.  -->  
    
1.  <span data-ttu-id="67dba-134">`app`デスクトップにディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="67dba-134">Create an `app` directory on your desktop.</span></span>  <span data-ttu-id="67dba-135">ディレクトリからディレクトリにファイルのコピー `workspaces-demo` を保存 `app` します。</span><span class="sxs-lookup"><span data-stu-id="67dba-135">Save copies of the files from the `workspaces-demo` directory to the `app` directory.</span></span>  <span data-ttu-id="67dba-136">このチュートリアルの残りの部分では、ディレクトリをと呼び `~/Desktop/app` ます。</span><span class="sxs-lookup"><span data-stu-id="67dba-136">For the rest of the tutorial, the directory is referred to as `~/Desktop/app`.</span></span>  
1.  <span data-ttu-id="67dba-137">でローカル web サーバーを起動 `~/Desktop/app` します。</span><span class="sxs-lookup"><span data-stu-id="67dba-137">Start a local web server in `~/Desktop/app`.</span></span>  <span data-ttu-id="67dba-138">以下は、起動のためのサンプルコードです `SimpleHTTPServer` が、好きなサーバーを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="67dba-138">Below is some sample code for starting up `SimpleHTTPServer`, but you may use whatever server you prefer.</span></span>  
    
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
    
1.  <span data-ttu-id="67dba-139">Microsoft Edge でタブを開き、ローカルでホストされているバージョンのサイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="67dba-139">Open a tab in Microsoft Edge and go to locally-hosted version of the site.</span></span>  <span data-ttu-id="67dba-140">またはのような URL を使用してアクセスできる必要があり `localhost:8080` `http://0.0.0.0:8080` ます。</span><span class="sxs-lookup"><span data-stu-id="67dba-140">You should be able to access it using a URL like `localhost:8080` or `http://0.0.0.0:8080`.</span></span>  <span data-ttu-id="67dba-141">正確な [ポート番号][WikiPortURLs] は異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="67dba-141">The exact [port number][WikiPortURLs] may be different.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo.msft.png" alt-text="デモ" lightbox="../media/workspaces-workspaces-demo.msft.png":::
       <span data-ttu-id="67dba-143">デモ</span><span class="sxs-lookup"><span data-stu-id="67dba-143">The demo</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="67dba-144">DevTools のセットアップ</span><span class="sxs-lookup"><span data-stu-id="67dba-144">Set up DevTools</span></span>  

1.  <span data-ttu-id="67dba-145">[ `Control` + `Shift` + `J` \ (Windows \)] または [ `Command` + `Option` + `J` \ (macOS \)] を選択して、devtools の**コンソール**パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="67dba-145">Select `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) to open the **Console** panel of DevTools.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-console.msft.png" alt-text="コンソールパネル" lightbox="../media/workspaces-workspaces-demo-console.msft.png":::
       <span data-ttu-id="67dba-147">**コンソール**パネル</span><span class="sxs-lookup"><span data-stu-id="67dba-147">The **Console** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="67dba-148">[ **ソース** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="67dba-148">Choose the **Sources** tab.</span></span>  
1.  <span data-ttu-id="67dba-149">[ **Filesystem** ] タブを選びます。</span><span class="sxs-lookup"><span data-stu-id="67dba-149">Choose the **Filesystem** tab.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem.msft.png" alt-text="[Filesystem] タブ" lightbox="../media/workspaces-workspaces-demo-sources-filesystem.msft.png":::
       <span data-ttu-id="67dba-151">[ **Filesystem** ] タブ</span><span class="sxs-lookup"><span data-stu-id="67dba-151">The **Filesystem** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="67dba-152">[ **ワークスペースにフォルダーを追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="67dba-152">Choose **Add Folder To Workspace**.</span></span>  
1.  <span data-ttu-id="67dba-153">「`~/Desktop/app`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="67dba-153">Type `~/Desktop/app`.</span></span>  
1.  <span data-ttu-id="67dba-154">ディレクトリの読み取りと書き込みを行うための DevTools アクセス許可を与えるには、[ **許可** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="67dba-154">Choose **Allow** to give DevTools permission to read and write to the directory.</span></span>  
    <span data-ttu-id="67dba-155">[ **Filesystem** ] タブで、、、およびの横に緑の点が表示され `index.html` `script.js` `styles.css` ます。</span><span class="sxs-lookup"><span data-stu-id="67dba-155">In the **Filesystem** tab, there is now a green dot next to `index.html`, `script.js`, and `styles.css`.</span></span>  <span data-ttu-id="67dba-156">これらの緑の点は、DevTools がページのネットワークリソースとの間のマッピングを確立したことを意味 `~/Desktop/app` します。</span><span class="sxs-lookup"><span data-stu-id="67dba-156">These green dots mean that DevTools has established a mapping between the network resources of the page, and the files in `~/Desktop/app`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png" alt-text="[Filesystem] タブに、ローカルファイルとネットワーク間のマッピングが表示されるようになりました" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png":::
       <span data-ttu-id="67dba-158">[ **Filesystem** ] タブに、ローカルファイルとネットワーク間のマッピングが表示されるようになりました</span><span class="sxs-lookup"><span data-stu-id="67dba-158">The **Filesystem** tab now shows a mapping between the local files and the network ones</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="67dba-159">手順 2: CSS の変更をディスクに保存する</span><span class="sxs-lookup"><span data-stu-id="67dba-159">Step 2: Save a CSS change to disk</span></span>  

1.  <span data-ttu-id="67dba-160">[開く] `styles.css` を選びます。</span><span class="sxs-lookup"><span data-stu-id="67dba-160">Open `styles.css`.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="67dba-161">`color`要素のプロパティ `h1` はに設定され `fuchsia` ます。</span><span class="sxs-lookup"><span data-stu-id="67dba-161">The `color` property of `h1` elements is set to `fuchsia`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png" alt-text="テキストエディターでスタイル .css を表示する" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png":::
       <span data-ttu-id="67dba-163">`styles.css`テキストエディターで表示する</span><span class="sxs-lookup"><span data-stu-id="67dba-163">View `styles.css` in a text editor</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="67dba-164">[ **要素** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="67dba-164">Choose the **Elements** tab.</span></span>  
1.  <span data-ttu-id="67dba-165">`color`要素のプロパティの値 `<h1>` を、お気に入りの色に変更します。</span><span class="sxs-lookup"><span data-stu-id="67dba-165">Change the value of the `color` property of the `<h1>` element to your favorite color.</span></span>  
    <span data-ttu-id="67dba-166">[ `<h1>` **スタイル**] ウィンドウで CSS ルールが適用されていることを確認するために、 **DOM ツリー**で要素を選ぶ必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="67dba-166">Remember that you need to choose the `<h1>` element in the **DOM Tree** in order to see the CSS rules applied to it in the **Styles** pane.</span></span>  <span data-ttu-id="67dba-167">[] の横にある緑の点は、 `styles.css:1` 加えた変更がマップされていることを意味 `~/Desktop/app/styles.css` します。</span><span class="sxs-lookup"><span data-stu-id="67dba-167">The green dot next to `styles.css:1` means that any change that you make are mapped to `~/Desktop/app/styles.css`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-css.msft.png" alt-text="ファイルがリンクされていることを示す緑色のインジケーター" lightbox="../media/workspaces-workspaces-demo-elements-styles-css.msft.png":::
       <span data-ttu-id="67dba-169">ファイルがリンクされていることを示す緑色のインジケーター</span><span class="sxs-lookup"><span data-stu-id="67dba-169">The green indicator that the file is linked</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="67dba-170">`styles.css`もう一度テキストエディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="67dba-170">Open `styles.css` in a text editor again.</span></span>  <span data-ttu-id="67dba-171">`color`これで、プロパティが [お気に入りの色」に設定されました。</span><span class="sxs-lookup"><span data-stu-id="67dba-171">The `color` property is now set to your favorite color.</span></span>  
1.  <span data-ttu-id="67dba-172">ページを最新の情報に更新してください。</span><span class="sxs-lookup"><span data-stu-id="67dba-172">Refresh the page.</span></span>  <span data-ttu-id="67dba-173">要素の色 `<h1>` は、引き続き好みの色に設定されます。</span><span class="sxs-lookup"><span data-stu-id="67dba-173">The color of the `<h1>` element is still set to your favorite color.</span></span>  <span data-ttu-id="67dba-174">この変更は更新されています。これにより、DevTools を変更したときに、ディスクへの変更が保存されたためです。</span><span class="sxs-lookup"><span data-stu-id="67dba-174">The change remains across a refresh, because when you made the change DevTools saved the change to disk.</span></span>  <span data-ttu-id="67dba-175">次に、ページを更新すると、ローカルサーバーは、ファイルの変更されたコピーをディスクから配信しました。</span><span class="sxs-lookup"><span data-stu-id="67dba-175">And then, when you refreshed the page, your local server served the modified copy of the file from disk.</span></span>  
    
## <span data-ttu-id="67dba-176">手順 3: HTML の変更をディスクに保存する</span><span class="sxs-lookup"><span data-stu-id="67dba-176">Step 3: Save an HTML change to disk</span></span>  

### <span data-ttu-id="67dba-177">[要素] パネルで HTML を変更する</span><span class="sxs-lookup"><span data-stu-id="67dba-177">Change HTML from the Elements Panel</span></span>  

<span data-ttu-id="67dba-178">Html は、要素パネルから変更できますが、DOM ツリーへの変更はディスクに保存されず、現在のブラウザーセッションのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="67dba-178">You may make changes to the html from the Element Panel, but your changes to the DOM tree are not saved to disk and only effect the current browser session.</span></span>  

<span data-ttu-id="67dba-179">DOM ツリーは html ではありません。</span><span class="sxs-lookup"><span data-stu-id="67dba-179">The DOM tree is not html.</span></span>  

<!--### Try changing HTML from the Elements panel  

> [!WARNING]
> The workflow that you are about to try does not work.  You are trying it now so that you do not waste time later trying to figure out why it is not working.  

1.  Choose the **Elements** tab.  
1.  Choose and edit the text content of the `h1` element, which says `Workspaces Demo`, and replace it with `I ❤️  Cake`.  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-change-h1.msft.png" alt-text="Attempt to change html from the DOM Tree of the Elements panel" lightbox="../media/workspaces-workspaces-demo-change-h1.msft.png":::
       Attempt to change html from the DOM Tree of the **Elements** panel  
    :::image-end:::  
    
1.  Open `~/Desktop/app/index.html` in a text editor.  The change that you just made does not appear.  
1.  Refresh the page.  The page reverts to the original title.  
    
#### Optional: Why it is not working  

> [!NOTE]
> This section describes why the workflow from [Try changing html from the Elements panel](#try-changing-html-from-the-elements-panel) does not work.  You should skip this section if you do not care why.  

*   The tree of nodes that you see on the **Elements** panel represents the [DOM][MDNWebAPIsDOM] of the page.  
*   To display a page, a browser fetches html over the network, parses the html, and then converts it into a tree of DOM nodes.  
*   If the page has any JavaScript, that JavaScript may add, delete, or change DOM nodes.  CSS may change the DOM, too, using the [`content`][MDNCSSContent] property.  
*   The browser eventually uses the DOM to determine what content it should present to browser users.  
*   Therefore, the final state of the page that users see may be very different from the html that the browser fetched.  
*   This makes it difficult for DevTools to resolve where a change made in the **Elements** panel should be saved, because the DOM is affected by HTML, JavaScript, and CSS.  

In short, the **DOM Tree** `!==` HTML.  
-->  

### <span data-ttu-id="67dba-180">[ソース] パネルで HTML を変更する</span><span class="sxs-lookup"><span data-stu-id="67dba-180">Change HTML from the Sources panel</span></span>  

<span data-ttu-id="67dba-181">ページの html への変更を保存する場合は、[ **ソース** ] パネルを使用します。</span><span class="sxs-lookup"><span data-stu-id="67dba-181">If you want to save a change to the html of the page, do it using the **Sources** panel.</span></span>  

1.  <span data-ttu-id="67dba-182">[ **ソース** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="67dba-182">Choose the **Sources** tab.</span></span>  
1.  <span data-ttu-id="67dba-183">[ **ページ** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="67dba-183">Choose the **Page** tab.</span></span>  
1.  <span data-ttu-id="67dba-184">[ **(インデックス)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="67dba-184">Choose **(index)**.</span></span>  <span data-ttu-id="67dba-185">ページの HTML が開きます。</span><span class="sxs-lookup"><span data-stu-id="67dba-185">The HTML for the page opens.</span></span>  
1.  <span data-ttu-id="67dba-186">置換後 `<h1>Workspaces Demo</h1>` の文字列 `<h1>I ❤️  Cake</h1>`</span><span class="sxs-lookup"><span data-stu-id="67dba-186">Replace `<h1>Workspaces Demo</h1>` with `<h1>I ❤️  Cake</h1>`.</span></span>  <span data-ttu-id="67dba-187">次の図を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67dba-187">See the following figure.</span></span>  
1.  <span data-ttu-id="67dba-188">`Control` + `S` 変更を保存するには、\ (Windows \) または `Command` + `S` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="67dba-188">Select `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save the change.</span></span>  
1.  <span data-ttu-id="67dba-189">ページを最新の情報に更新してください。</span><span class="sxs-lookup"><span data-stu-id="67dba-189">Refresh the page.</span></span>  <span data-ttu-id="67dba-190">`<h1>`要素に新しいテキストが引き続き表示されています。</span><span class="sxs-lookup"><span data-stu-id="67dba-190">The `<h1>` element is still displaying the new text.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-page-h1.msft.png" alt-text="[ソース] パネルで HTML を変更する" lightbox="../media/workspaces-workspaces-demo-sources-page-h1.msft.png":::
       <span data-ttu-id="67dba-192">[ **ソース** ] パネルで HTML を変更する</span><span class="sxs-lookup"><span data-stu-id="67dba-192">Change HTML from the **Sources** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="67dba-193">[開く] `~/Desktop/app/index.html` を選びます。</span><span class="sxs-lookup"><span data-stu-id="67dba-193">Open `~/Desktop/app/index.html`.</span></span>  <span data-ttu-id="67dba-194">`<h1>`要素に新しいテキストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="67dba-194">The `<h1>` element contains the new text.</span></span>  
    
## <span data-ttu-id="67dba-195">手順 4: JavaScript の変更をディスクに保存する</span><span class="sxs-lookup"><span data-stu-id="67dba-195">Step 4: Save a JavaScript change to disk</span></span>  

<span data-ttu-id="67dba-196">[ **ソース** ] パネルも JavaScript を変更する場所です。</span><span class="sxs-lookup"><span data-stu-id="67dba-196">The **Sources** panel is also the place to make changes to JavaScript.</span></span>  <span data-ttu-id="67dba-197">ただし、サイトを変更するときに、[ **要素** ] パネルや **コンソール** パネルなどの他のパネルにアクセスする必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="67dba-197">But sometimes you need to access other panels, such as the **Elements** panel or the **Console** panel, while making changes to your site.</span></span>  <span data-ttu-id="67dba-198">他のパネルと共に **ソース** パネルを開く方法があります。</span><span class="sxs-lookup"><span data-stu-id="67dba-198">There is a way to have the **Sources** panel open alongside other panels.</span></span>  

1.  <span data-ttu-id="67dba-199">[ **要素** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="67dba-199">Choose the **Elements** tab.</span></span>  
1.  <span data-ttu-id="67dba-200">[ `Control` + `Shift` + `P` \ (Windows \)] または [ `Command` + `Shift` + `P` \ (macOS \)] を選びます。</span><span class="sxs-lookup"><span data-stu-id="67dba-200">Select `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  <span data-ttu-id="67dba-201">**コマンドメニュー**が開きます。</span><span class="sxs-lookup"><span data-stu-id="67dba-201">The **Command Menu** opens.</span></span>  
1.  <span data-ttu-id="67dba-202">入力して `QS` 、[ **クイックソースの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="67dba-202">Type `QS`, then select **Show Quick Source**.</span></span>  <span data-ttu-id="67dba-203">[DevTools] ウィンドウの下部に、[ **クイックソース** ] タブが表示されています。 タブには `index.html` 、[ **ソース** ] パネルで最後に編集したファイルの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="67dba-203">At the bottom of your DevTools window there is now a **Quick Source** tab.  The tab is displaying the contents of `index.html`, which is the last file you edited in the **Sources** panel.</span></span>  <span data-ttu-id="67dba-204">[ **クイックソース** ] タブでは、[ **ソース** ] パネルからエディターが表示されるため、他のパネルを開いたままファイルを編集できます。</span><span class="sxs-lookup"><span data-stu-id="67dba-204">The **Quick Source** tab gives you the editor from the **Sources** panel, so that you are able to edit files while having other panels open.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png" alt-text="コマンドメニューを使用して [クイックソース] タブを開く" lightbox="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png":::
       <span data-ttu-id="67dba-206">**コマンドメニュー**を使用して [**クイックソース**] タブを開く</span><span class="sxs-lookup"><span data-stu-id="67dba-206">Open the **Quick Source** tab using **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="67dba-207">[ `Control` + `P` \ (Windows \)] または [ `Command` + `P` \ (macOS \)] を選択して、[**ファイルを開く**] ダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="67dba-207">Select `Control`+`P` \(Windows\) or `Command`+`P` \(macOS\) to open the **Open File** dialog.</span></span>  <span data-ttu-id="67dba-208">次の図を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67dba-208">See the following figure.</span></span>  
1.  <span data-ttu-id="67dba-209">入力して `script` 、[ **アプリ/script.js**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="67dba-209">Type `script`, then select **app/script.js**.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-script.msft.png" alt-text="[ファイルを開く] ダイアログボックスを使用して script.js を開く" lightbox="../media/workspaces-workspaces-demo-search-script.msft.png":::
       <span data-ttu-id="67dba-211">[ `script.js` ファイルを **開く** ] ダイアログボックスを使って開く</span><span class="sxs-lookup"><span data-stu-id="67dba-211">Open `script.js` using the **Open File** dialog</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="67dba-212">`Save Changes To Disk With Workspaces`デモのリンクは、定期的にスタイル設定されています。</span><span class="sxs-lookup"><span data-stu-id="67dba-212">The `Save Changes To Disk With Workspaces` link in the demo is styled regularly.</span></span>  
    
1.  <span data-ttu-id="67dba-213">[**クイックソース**] タブを使用して、 **script.js**の下部に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="67dba-213">Add the following code to the bottom of **script.js** using the **Quick Source** tab.</span></span>  
    
    ```javascript
    console.log('greetings from script.js');
    document.querySelector('a').style = 'font-style:italic';
    ```  
    
1.  <span data-ttu-id="67dba-214">`Control` + `S` 変更を保存するには、\ (Windows \) または `Command` + `S` \ (macOS \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="67dba-214">Select `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save the change.</span></span>  
1.  <span data-ttu-id="67dba-215">ページを最新の情報に更新してください。</span><span class="sxs-lookup"><span data-stu-id="67dba-215">Refresh the page.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="67dba-216">ページ上のリンクが斜体になりました。</span><span class="sxs-lookup"><span data-stu-id="67dba-216">The link on the page is now italicized.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png" alt-text="ページ上のリンクが斜体になりました" lightbox="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png":::
       <span data-ttu-id="67dba-218">ページ上のリンクが斜体になりました</span><span class="sxs-lookup"><span data-stu-id="67dba-218">The link on the page is now italicized</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="67dba-219">次のステップ</span><span class="sxs-lookup"><span data-stu-id="67dba-219">Next steps</span></span>  

<span data-ttu-id="67dba-220">このチュートリアルで学んだことを使用して、自分のプロジェクトでワークスペースをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="67dba-220">Use what you have learned in this tutorial to set up Workspaces in your own project.</span></span>  <!-- If you run into any issues or are able to get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  

<!--  
If you have more feedback on the topics or anything else, please use any of the channels below:  

*   [Mailing List][AlphabetGroupsAlphabetBrowserDevTools]  
*   [Twitter][TwitterAlphabetBrowserDevTools]  
    -->  

<!-- links -->  

[DevToolsCssIndex]: ../css/index.md "CSS の表示と変更の概要 |Microsoft ドキュメント"  

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
> <span data-ttu-id="67dba-229">このページの一部は、 [Google によっ][GoogleSitePolicies] て作成および共有され、 [クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="67dba-229">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="67dba-230">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/workspaces/index) にあり、 [Kayce Basques][KayceBasques] テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="67dba-230">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/workspaces/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="67dba-232">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="67dba-232">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
