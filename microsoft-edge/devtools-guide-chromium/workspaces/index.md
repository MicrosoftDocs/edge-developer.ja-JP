---
title: ワークスペースを使用してファイルを編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/27/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 612e85b8b00a78a40e53ac5c33d187fdae174024
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601853"
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







# <span data-ttu-id="5a5a1-103">ワークスペースを使用してファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="5a5a1-103">Edit Files With Workspaces</span></span>   



> [!NOTE]
> <span data-ttu-id="5a5a1-104">このチュートリアルの目標は、ワークスペースのセットアップと使用に関する実践的な練習を行い、独自のプロジェクトでワークスペースを使用できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-104">The goal of this tutorial is to provide hands-on practice in setting up and using Workspaces, so that you are able to use Workspaces in your own projects.</span></span>  <span data-ttu-id="5a5a1-105">ワークスペースを有効にした後、DevTools で作成したソースコードの変更をローカルコンピューターに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-105">You are able to save the changes to the source code, on your local computer, that you made within DevTools after you enable Workspaces.</span></span>  

> [!CAUTION]
> <span data-ttu-id="5a5a1-106">**前提条件**: このチュートリアルを始める前に、次の方法を理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-106">**Prerequisites**: Before beginning this tutorial, you should know how to:</span></span>  
> *   [<span data-ttu-id="5a5a1-107">HTML、CSS、JavaScript を使って web ページを作成する</span><span class="sxs-lookup"><span data-stu-id="5a5a1-107">Use HTML, CSS, and JavaScript to build a web page</span></span>][MDNWebGettingStarted]  
> *   [<span data-ttu-id="5a5a1-108">DevTools を使って CSS の基本的な変更を行う</span><span class="sxs-lookup"><span data-stu-id="5a5a1-108">Use DevTools to make basic changes to CSS</span></span>][DevToolsCssIndex]  
> *   [<span data-ttu-id="5a5a1-109">ローカル HTTP web サーバーを実行する</span><span class="sxs-lookup"><span data-stu-id="5a5a1-109">Run a local HTTP web server</span></span>][MDNSimpleLocalHTTPServer]  

## <span data-ttu-id="5a5a1-110">概要</span><span class="sxs-lookup"><span data-stu-id="5a5a1-110">Overview</span></span>   

<span data-ttu-id="5a5a1-111">ワークスペースを使用すると、Devtools で行った変更を、コンピューター上の同じファイルのローカルコピーに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-111">Workspaces enable you to save a change that you make in Devtools to a local copy of the same file on your computer.</span></span>  <span data-ttu-id="5a5a1-112">たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-112">For example, suppose:</span></span>  

*   <span data-ttu-id="5a5a1-113">自分のサイトのソースコードはデスクトップにあります。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-113">You have the source code for your site on your desktop.</span></span>  
*   <span data-ttu-id="5a5a1-114">ソースコードディレクトリからローカル web サーバーを実行しているため、サイトにアクセスできるように `localhost:8080` なります。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-114">You are running a local web server from the source code directory, so that the site is accessible at `localhost:8080`.</span></span>  
*   <span data-ttu-id="5a5a1-115">`localhost:8080`Microsoft Edge で開かれており、DevTools を使ってサイトの CSS を変更しています。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-115">You opened `localhost:8080`  in Microsoft Edge, and you are using DevTools to change the CSS of the site.</span></span>  

<span data-ttu-id="5a5a1-116">ワークスペースを有効にすると、DevTools で行った CSS の変更が、デスクトップのソースコードに保存されます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-116">With Workspaces enabled, the CSS changes that you make within DevTools are saved to the source code on your desktop.</span></span>  

## <span data-ttu-id="5a5a1-117">制限事項</span><span class="sxs-lookup"><span data-stu-id="5a5a1-117">Limitations</span></span>   

<span data-ttu-id="5a5a1-118">モダンフレームワークを使用している場合は、可能な限り早く実行するために最適化された形式に簡単に保持できる形式からソースコードを変換する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-118">If you are using a modern framework, it probably transforms your source code from a format that is easy to maintain into a format that is optimized to run as quickly as possible.</span></span>  
<span data-ttu-id="5a5a1-119">通常、ワークスペースでは、最適化されたコードを[ソースマップ][TreehouseBlogSourceMaps]のヘルプを使用して元のソースコードに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-119">Workspaces is usually able to map the optimized code back to your original source code with the help of [source maps][TreehouseBlogSourceMaps].</span></span>  <span data-ttu-id="5a5a1-120">ただし、フレームワーク間のソースマップの使い方については、さまざまなバリエーションがあります。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-120">But there is a lot of variation between frameworks over how they use source maps.</span></span>  <span data-ttu-id="5a5a1-121">Devtools では、すべてのバリエーションがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-121">Devtools simply does support all the variations.</span></span>  

<span data-ttu-id="5a5a1-122">ワークスペースは、次のフレームワークでは動作しないことがわかっています。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-122">Workspaces is known to not work with these frameworks:</span></span>  

*   <span data-ttu-id="5a5a1-123">反応するアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="5a5a1-123">Create React App</span></span>  

<!-- If you run into issues while using Workspaces with your framework of choice, or you get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  

## <span data-ttu-id="5a5a1-124">関連する機能: ローカルの上書き</span><span class="sxs-lookup"><span data-stu-id="5a5a1-124">Related feature: Local Overrides</span></span>   

<span data-ttu-id="5a5a1-125">**ローカルオーバーライド**は、ワークスペースに似た別の devtools 機能です。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-125">**Local Overrides** is another DevTools feature that is similar to Workspaces.</span></span>  <span data-ttu-id="5a5a1-126">ページに対する変更を試す必要があり、ページの読み込み全体でそれらの変更を確認する必要がある場合は、ローカルの上書きを使用しますが、ページのソースコードへの変更のマッピングについては注意してください。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-126">Use Local Overrides when you want to experiment with changes to a page, and you need to see those changes across page loads, but you do not care about mapping your changes to the source code of the page.</span></span>  

<!--Todo: add section when content is ready  -->  

## <span data-ttu-id="5a5a1-127">手順 1: セットアップ</span><span class="sxs-lookup"><span data-stu-id="5a5a1-127">Step 1: Setup</span></span>   

<span data-ttu-id="5a5a1-128">このチュートリアルを実行して、ワークスペースの実践的なエクスペリエンスを実現します。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-128">Complete this tutorial to get hands-on experience with Workspaces.</span></span>  

### <span data-ttu-id="5a5a1-129">デモを設定する</span><span class="sxs-lookup"><span data-stu-id="5a5a1-129">Set up the demo</span></span>   

1.  <span data-ttu-id="5a5a1-130">[デモを開き][GlitchWorkspacesDemo]ます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-130">[Open the demo][GlitchWorkspacesDemo].</span></span>  <!--In the top-left of the editor, a randomly-generated project name is displayed.  -->  
    
    > ##### <span data-ttu-id="5a5a1-131">図 1</span><span class="sxs-lookup"><span data-stu-id="5a5a1-131">Figure 1</span></span>  
    > <span data-ttu-id="5a5a1-132">プロジェクトのエラープロジェクト ![][ImageGlitchProject]</span><span class="sxs-lookup"><span data-stu-id="5a5a1-132">A Glitch project ![A Glitch project][ImageGlitchProject]</span></span>  
    
    <!--1.  Click the project name.  -->
    <!--1.  Select **Advanced Options** > **Download Project**.  
    
    > ##### Figure 2  
    > The Download Project button  
    > ![The Download Project button][ImageDownloadProjectButton]  
    -->
    <!--1.  Close the tab.  -->
    <!--1.  Unzip the source code and move the unzipped `app` directory to your desktop.  For the rest of this tutorial this directory is referred to as `~/Desktop/app`.  -->  
    
1.  <span data-ttu-id="5a5a1-133">`app`デスクトップにディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-133">Create an `app` directory on your desktop.</span></span>  <span data-ttu-id="5a5a1-134">ディレクトリ内のファイルのコピーを保存 `workspaces-demo` します。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-134">Save copies of the files in the `workspaces-demo` directory.</span></span>  <span data-ttu-id="5a5a1-135">このチュートリアルの残りの部分では、というディレクトリがと呼ばれて `~/Desktop/app` います。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-135">For the rest of this tutorial this directory is referred to as `~/Desktop/app`.</span></span>  
1.  <span data-ttu-id="5a5a1-136">でローカル web サーバーを起動 `~/Desktop/app` します。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-136">Start a local web server in `~/Desktop/app`.</span></span>  <span data-ttu-id="5a5a1-137">以下は、起動のためのサンプルコードです `SimpleHTTPServer` が、好きなサーバーを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-137">Below is some sample code for starting up `SimpleHTTPServer`, but you may use whatever server you prefer.</span></span>  
    
    ```bash
    cd ~/Desktop/app
    python -m SimpleHTTPServer # Python 2
    ```  
    
    ```bash
    cd ~/Desktop/app
    python -m http.server # Python 3
    ```  
    
1.  <span data-ttu-id="5a5a1-138">Microsoft Edge でタブを開き、ローカルでホストされているバージョンのサイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-138">Open a tab in Microsoft Edge and go to locally-hosted version of the site.</span></span>  <span data-ttu-id="5a5a1-139">またはのような URL を使用してアクセスできる必要があり `localhost:8080` `http://0.0.0.0:8080` ます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-139">You should be able to access it using a URL like `localhost:8080` or `http://0.0.0.0:8080`.</span></span>  <span data-ttu-id="5a5a1-140">正確な[ポート番号][WikiPortURLs]は異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-140">The exact [port number][WikiPortURLs] may be different.</span></span>  
    
    > ##### <span data-ttu-id="5a5a1-141">図 2</span><span class="sxs-lookup"><span data-stu-id="5a5a1-141">Figure 2</span></span>  
    > <span data-ttu-id="5a5a1-142">デモ</span><span class="sxs-lookup"><span data-stu-id="5a5a1-142">The demo</span></span>  
    > <span data-ttu-id="5a5a1-143">![デモ][ImageDemo]</span><span class="sxs-lookup"><span data-stu-id="5a5a1-143">![The demo][ImageDemo]</span></span>  

### <span data-ttu-id="5a5a1-144">DevTools のセットアップ</span><span class="sxs-lookup"><span data-stu-id="5a5a1-144">Set up DevTools</span></span>   

1.  <span data-ttu-id="5a5a1-145">`Control` + `Shift` + `J` \ (Windows \) または `Command` + `Option` + `J` \ (macOS \) キーを押して、devtools の**コンソール**パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-145">Press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) to open the **Console** panel of DevTools.</span></span>  
    
    > ##### <span data-ttu-id="5a5a1-146">図 3</span><span class="sxs-lookup"><span data-stu-id="5a5a1-146">Figure 3</span></span>  
    > <span data-ttu-id="5a5a1-147">**コンソール**パネル</span><span class="sxs-lookup"><span data-stu-id="5a5a1-147">The **Console** panel</span></span>  
    > <span data-ttu-id="5a5a1-148">![コンソールパネル][Imageconepanel]</span><span class="sxs-lookup"><span data-stu-id="5a5a1-148">![The Console panel][ImageConsolePanel]</span></span>  

1.  <span data-ttu-id="5a5a1-149">[**ソース**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-149">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="5a5a1-150">[ **Filesystem** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-150">Click the **Filesystem** tab.</span></span>  
    
    > ##### <span data-ttu-id="5a5a1-151">図 4</span><span class="sxs-lookup"><span data-stu-id="5a5a1-151">Figure 4</span></span>  
    > <span data-ttu-id="5a5a1-152">[ **Filesystem** ] タブ</span><span class="sxs-lookup"><span data-stu-id="5a5a1-152">The **Filesystem** tab</span></span>  
    > <span data-ttu-id="5a5a1-153">![Filesystem] タブ[ImageFilesystem]</span><span class="sxs-lookup"><span data-stu-id="5a5a1-153">![The Filesystem tab][ImageFilesystem]</span></span>  

1.  <span data-ttu-id="5a5a1-154">[**フォルダーをワークスペースに追加] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-154">Click **Add Folder To Workspace**.</span></span>  
1.  <span data-ttu-id="5a5a1-155">を選択し `~/Desktop/app` ます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-155">Select `~/Desktop/app`.</span></span>  
1.  <span data-ttu-id="5a5a1-156">[**許可**] をクリックして、ディレクトリの読み取りと書き込みを行うための devtools 権限を与えます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-156">Click **Allow** to give DevTools permission to read and write to the directory.</span></span>  
    <span data-ttu-id="5a5a1-157">[ **Filesystem** ] タブで、、、およびの横に緑の点が表示され `index.html` `script.js` `styles.css` ます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-157">In the **Filesystem** tab, there is now a green dot next to `index.html`, `script.js`, and `styles.css`.</span></span>  <span data-ttu-id="5a5a1-158">これらの緑の点は、DevTools がページのネットワークリソースとの間のマッピングを確立したことを意味 `~/Desktop/app` します。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-158">These green dots mean that DevTools has established a mapping between the network resources of the page, and the files in `~/Desktop/app`.</span></span>  
    
    > ##### <span data-ttu-id="5a5a1-159">図 5</span><span class="sxs-lookup"><span data-stu-id="5a5a1-159">Figure 5</span></span>  
    > <span data-ttu-id="5a5a1-160">[ **Filesystem** ] タブに、ローカルファイルとネットワーク間のマッピングが表示されるようになりました</span><span class="sxs-lookup"><span data-stu-id="5a5a1-160">The **Filesystem** tab now shows a mapping between the local files and the network ones</span></span>  
    > <span data-ttu-id="5a5a1-161">![Filesystem] タブに、ローカルファイルとネットワーク間のマッピングが表示されるようになりました。[ImageMapping]</span><span class="sxs-lookup"><span data-stu-id="5a5a1-161">![The Filesystem tab now shows a mapping between the local files and the network ones][ImageMapping]</span></span>  

## <span data-ttu-id="5a5a1-162">手順 2: CSS の変更をディスクに保存する</span><span class="sxs-lookup"><span data-stu-id="5a5a1-162">Step 2: Save a CSS change to disk</span></span>   

1.  <span data-ttu-id="5a5a1-163">[開く] `styles.css` を選びます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-163">Open `styles.css`.</span></span>  
    
    > [!NOTE]
    ><span data-ttu-id="5a5a1-164">`color`要素のプロパティ `h1` はに設定され `fuchsia` ます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-164">The `color` property of `h1` elements is set to `fuchsia`.</span></span>
    
    > ##### <span data-ttu-id="5a5a1-165">図 6</span><span class="sxs-lookup"><span data-stu-id="5a5a1-165">Figure 6</span></span>  
    > <span data-ttu-id="5a5a1-166">`styles.css`テキストエディターでの表示</span><span class="sxs-lookup"><span data-stu-id="5a5a1-166">Viewing `styles.css` in a text editor</span></span>  
    > <span data-ttu-id="5a5a1-167">![テキストエディターでスタイルの css を表示][ImageStylesFuchsia]</span><span class="sxs-lookup"><span data-stu-id="5a5a1-167">![Viewing styles.css in a text editor][ImageStylesFuchsia]</span></span>  


1.  <span data-ttu-id="5a5a1-168">[**要素**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-168">Click the **Elements** tab.</span></span>  
1.  <span data-ttu-id="5a5a1-169">`color`要素のプロパティの値 `<h1>` を、お気に入りの色に変更します。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-169">Change the value of the `color` property of the `<h1>` element to your favorite color.</span></span>  
    <span data-ttu-id="5a5a1-170">[ `<h1>` **スタイル**] ウィンドウで CSS ルールが適用されていることを確認するために、 **DOM ツリー**の要素をクリックする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-170">Remember that you need to click the `<h1>` element in the **DOM Tree** in order to see the CSS rules applied to it in the **Styles** pane.</span></span>  <span data-ttu-id="5a5a1-171">[] の横にある緑の点は、 `styles.css:1` 加えた変更がマップされていることを意味 `~/Desktop/app/styles.css` します。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-171">The green dot next to `styles.css:1` means that any change that you make are mapped to `~/Desktop/app/styles.css`.</span></span>  
    
    > ##### <span data-ttu-id="5a5a1-172">図 7</span><span class="sxs-lookup"><span data-stu-id="5a5a1-172">Figure 7</span></span>  
    > <span data-ttu-id="5a5a1-173">ファイルがリンクされていることを示す緑色のインジケーター</span><span class="sxs-lookup"><span data-stu-id="5a5a1-173">The green indicator that the file is linked</span></span>  
    > <span data-ttu-id="5a5a1-174">![ファイルがリンクされていることを示す緑色のインジケーター][Imageのスタイル緑]</span><span class="sxs-lookup"><span data-stu-id="5a5a1-174">![The green indicator that the file is linked][ImageStylesGreen]</span></span>  

1.  <span data-ttu-id="5a5a1-175">`styles.css`もう一度テキストエディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-175">Open `styles.css` in a text editor again.</span></span>  <span data-ttu-id="5a5a1-176">`color`これで、プロパティが [お気に入りの色」に設定されました。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-176">The `color` property is now set to your favorite color.</span></span>  
1.  <span data-ttu-id="5a5a1-177">ページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-177">Reload the page.</span></span>  <span data-ttu-id="5a5a1-178">要素の色 `<h1>` は、引き続き好みの色に設定されます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-178">The color of the `<h1>` element is still set to your favorite color.</span></span>  <span data-ttu-id="5a5a1-179">これは、変更を加えたときに、DevTools によってディスクへの変更が保存されたためです。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-179">This works because when you made the change, DevTools saved the change to disk.</span></span>  <span data-ttu-id="5a5a1-180">次に、ページを再ロードすると、ローカルサーバーは、ファイルの変更されたコピーをディスクから提供します。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-180">And then, when you reloaded the page, your local server served the modified copy of the file from disk.</span></span>  

## <span data-ttu-id="5a5a1-181">手順 3: HTML の変更をディスクに保存する</span><span class="sxs-lookup"><span data-stu-id="5a5a1-181">Step 3: Save an HTML change to disk</span></span>   

### <span data-ttu-id="5a5a1-182">[要素] パネルで HTML を変更する</span><span class="sxs-lookup"><span data-stu-id="5a5a1-182">Change HTML from the Elements Panel</span></span>  

<span data-ttu-id="5a5a1-183">HTML は、要素パネルから変更できますが、DOM ツリーへの変更はディスクに保存されず、現在のブラウザーセッションのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-183">You may make changes to the HTML from the Element Panel, but your changes to the DOM tree are not saved to disk and only effect the current browser session.</span></span>  
<span data-ttu-id="5a5a1-184">DOM ツリーは HTML ではありません。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-184">The DOM tree is not HTML.</span></span>  

<!--### Try changing HTML from the Elements panel   

> [!WARNING]
> The workflow that you are about to try does not work.  You are trying it now so that you do not waste time later trying to figure out why it is not working.  

1.  Click the **Elements** tab.  
1.  Double click the text content of the `h1` element, which says `Workspaces Demo`, and replace it with `I ❤️  Cake`.  
    
    > ##### Old Figure 9  
    > Attempting to change HTML from the **DOM Tree** of the **Elements** panel  
    > ![Attempting to change HTML from the DOM Tree of the Elements panel][ImageElementsCake]  

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
### <span data-ttu-id="5a5a1-185">[ソース] パネルで HTML を変更する</span><span class="sxs-lookup"><span data-stu-id="5a5a1-185">Change HTML from the Sources panel</span></span>   

<span data-ttu-id="5a5a1-186">ページの HTML への変更を保存する場合は、[**ソース**] パネルを使用します。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-186">If you want to save a change to the HTML of the page, do it using the **Sources** panel.</span></span>  

1.  <span data-ttu-id="5a5a1-187">[**ソース**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-187">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="5a5a1-188">[**ページ**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-188">Click the **Page** tab.</span></span>  
1.  <span data-ttu-id="5a5a1-189">[ **(インデックス)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-189">Click **(index)**.</span></span>  <span data-ttu-id="5a5a1-190">ページの HTML が開きます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-190">The HTML for the page opens.</span></span>  
1.  <span data-ttu-id="5a5a1-191">置換後 `<h1>Workspaces Demo</h1>` の文字列 `<h1>I ❤️  Cake</h1>`</span><span class="sxs-lookup"><span data-stu-id="5a5a1-191">Replace `<h1>Workspaces Demo</h1>` with `<h1>I ❤️  Cake</h1>`.</span></span>  <span data-ttu-id="5a5a1-192">[図 8](#figure-8)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-192">See [Figure 8](#figure-8).</span></span>  
1.  <span data-ttu-id="5a5a1-193">`Control` + `S` \ (Windows \) または `Command` + `S` \ (macOS \) を押して、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-193">Press `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save the change.</span></span>  
1.  <span data-ttu-id="5a5a1-194">ページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-194">Reload the page.</span></span>  <span data-ttu-id="5a5a1-195">`<h1>`要素に新しいテキストが引き続き表示されています。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-195">The `<h1>` element is still displaying the new text.</span></span>  
    
    > ##### <span data-ttu-id="5a5a1-196">図 8</span><span class="sxs-lookup"><span data-stu-id="5a5a1-196">Figure 8</span></span>  
    > <span data-ttu-id="5a5a1-197">行12はに設定されています</span><span class="sxs-lookup"><span data-stu-id="5a5a1-197">Line 12 has been set to</span></span> `I ❤️  Cake`  
    > <span data-ttu-id="5a5a1-198">![ソースパネルから HTML を変更します][ImageSourcesCakeHTML]</span><span class="sxs-lookup"><span data-stu-id="5a5a1-198">![Changing HTML from the Sources panel][ImageSourcesCakeHTML]</span></span>  

1.  <span data-ttu-id="5a5a1-199">[開く] `~/Desktop/app/index.html` を選びます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-199">Open `~/Desktop/app/index.html`.</span></span>  <span data-ttu-id="5a5a1-200">`<h1>`要素に新しいテキストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-200">The `<h1>` element contains the new text.</span></span>  

## <span data-ttu-id="5a5a1-201">手順 4: JavaScript の変更をディスクに保存する</span><span class="sxs-lookup"><span data-stu-id="5a5a1-201">Step 4: Save a JavaScript change to disk</span></span>   

<span data-ttu-id="5a5a1-202">[**ソース**] パネルも JavaScript を変更する場所です。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-202">The **Sources** panel is also the place to make changes to JavaScript.</span></span>  <span data-ttu-id="5a5a1-203">ただし、サイトを変更するときに、[**要素**] パネルや**コンソール**パネルなどの他のパネルにアクセスする必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-203">But sometimes you need to access other panels, such as the **Elements** panel or the **Console** panel, while making changes to your site.</span></span>  <span data-ttu-id="5a5a1-204">他のパネルと共に**ソース**パネルを開く方法があります。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-204">There is a way to have the **Sources** panel open alongside other panels.</span></span>  

1.  <span data-ttu-id="5a5a1-205">[**要素**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-205">Click the **Elements** tab.</span></span>  
1.  <span data-ttu-id="5a5a1-206">`Control` + `Shift` + `P` \ (Windows \) または `Command` + `Shift` + `P` \ (macOS \) を押します。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-206">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  <span data-ttu-id="5a5a1-207">**コマンドメニュー**が開きます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-207">The **Command Menu** opens.</span></span>  
1.  <span data-ttu-id="5a5a1-208">入力して `QS` 、[**クイックソースの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-208">Type `QS`, then select **Show Quick Source**.</span></span>  <span data-ttu-id="5a5a1-209">[DevTools] ウィンドウの下部に、[**クイックソース**] タブが表示されています。 タブには `index.html` 、[**ソース**] パネルで最後に編集したファイルの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-209">At the bottom of your DevTools window there is now a **Quick Source** tab.  The tab is displaying the contents of `index.html`, which is the last file you edited in the **Sources** panel.</span></span>  <span data-ttu-id="5a5a1-210">[**クイックソース**] タブでは、[**ソース**] パネルからエディターが表示されるため、他のパネルを開いたままファイルを編集できます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-210">The **Quick Source** tab gives you the editor from the **Sources** panel, so that you are able to edit files while having other panels open.</span></span>  
    
    > ##### <span data-ttu-id="5a5a1-211">図 9</span><span class="sxs-lookup"><span data-stu-id="5a5a1-211">Figure 9</span></span>  
    > <span data-ttu-id="5a5a1-212">**コマンドメニュー**を使用して [**クイックソース**] タブを開く</span><span class="sxs-lookup"><span data-stu-id="5a5a1-212">Opening the **Quick Source** tab using the **Command Menu**</span></span>  
    > <span data-ttu-id="5a5a1-213">![コマンドメニューを使用してクイックソース] タブを開く[ImageCommandMenuQuickSource]</span><span class="sxs-lookup"><span data-stu-id="5a5a1-213">![Opening the Quick Source tab using Command Menu][ImageCommandMenuQuickSource]</span></span>  

1.  <span data-ttu-id="5a5a1-214">`Control` + `P` \ (Windows \) または `Command` + `P` \ (macOS \) キーを押して、[**ファイルを開く**] ダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-214">Press `Control`+`P` \(Windows\) or `Command`+`P` \(macOS\) to open the **Open File** dialog.</span></span>  <span data-ttu-id="5a5a1-215">[図 10](#figure-10)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-215">See [Figure 10](#figure-10).</span></span>  
1.  <span data-ttu-id="5a5a1-216">入力して `script` 、[ **app/script**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-216">Type `script`, then select **app/script.js**.</span></span>  
    
    > ##### <span data-ttu-id="5a5a1-217">図 10</span><span class="sxs-lookup"><span data-stu-id="5a5a1-217">Figure 10</span></span>  
    > <span data-ttu-id="5a5a1-218">[ `script.js` ファイルを**開く**] ダイアログボックスを開く</span><span class="sxs-lookup"><span data-stu-id="5a5a1-218">Opening `script.js` using the **Open File** dialog</span></span>  
    > <span data-ttu-id="5a5a1-219">![ファイルを開く] ダイアログボックスを使ってスクリプトを開く[ImageOpenFileDialog]</span><span class="sxs-lookup"><span data-stu-id="5a5a1-219">![Opening script.js using the Open File dialog][ImageOpenFileDialog]</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="5a5a1-220">`Save Changes To Disk With Workspaces`デモのリンクは、定期的にスタイル設定されています。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-220">The `Save Changes To Disk With Workspaces` link in the demo is styled regularly.</span></span>  
    
1.  <span data-ttu-id="5a5a1-221">[**クイックソース**] タブを使用して、次のコードを**スクリプト .js**の一番下に追加します。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-221">Add the following code to the bottom of **script.js** using the **Quick Source** tab.</span></span>  
    
    ```javascript
    console.log('greetings from script.js');
    document.querySelector('a').style = 'font-style:italic';
    ```  
    
1.  <span data-ttu-id="5a5a1-222">`Control` + `S` \ (Windows \) または `Command` + `S` \ (macOS \) を押して、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-222">Press `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save the change.</span></span>  
1.  <span data-ttu-id="5a5a1-223">ページを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-223">Reload the page.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="5a5a1-224">ページ上のリンクが斜体になりました。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-224">The link on the page is now italic.</span></span>
    
    > ##### <span data-ttu-id="5a5a1-225">図 11</span><span class="sxs-lookup"><span data-stu-id="5a5a1-225">Figure 11</span></span>  
    > <span data-ttu-id="5a5a1-226">ページ上のリンクが斜体になりました</span><span class="sxs-lookup"><span data-stu-id="5a5a1-226">The link on the page is now italic</span></span>  
    > <span data-ttu-id="5a5a1-227">![ページのリンクが斜体になりました][ImageScriptItalic]</span><span class="sxs-lookup"><span data-stu-id="5a5a1-227">![The link on the page is now italic][ImageScriptItalic]</span></span>  

## <span data-ttu-id="5a5a1-228">次のステップ</span><span class="sxs-lookup"><span data-stu-id="5a5a1-228">Next steps</span></span>   

<span data-ttu-id="5a5a1-229">このチュートリアルで学んだことを使用して、自分のプロジェクトでワークスペースをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-229">Use what you have learned in this tutorial to set up Workspaces in your own project.</span></span>  <!-- If you run into any issues or are able to get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->

 <!--  -->



<!-- 
If you have more feedback on these topics or anything else, please use any of the channels below:
*   [Mailing List][AlphabetGroupsAlphabetBrowserDevTools]  
*   [Twitter][TwitterAlphabetBrowserDevTools]  
-->

<!-- image links -->  

[ImageGlitchProject]: /microsoft-edge/devtools-guide-chromium/media/workspaces-glitch-workspaces-demo-source.msft.png "図 1: ランダムに生成された名前を持つエラープロジェクト"  
<!--[ImageDownloadProjectButton]: /microsoft-edge/devtools-guide-chromium/media/workspaces-glitch-advanced-options-download-project.msft.png "old Figure 2: The Download Project button"  -->  
[ImageDemo]:/microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo.msft.png "図 2: デモ"  
[Imageconepanel]:/microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-console.msft.png "図 3: コンソールパネル"
[ImageConsolePanel]: /microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-console.msft.png "Figure 3: The Console panel"  
[イメージファイルシステム]:/microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-sources-filesystem.msft.png "図 4: ファイルシステムタブ"
[ImageFilesystem]: /microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-sources-filesystem.msft.png "Figure 4: The Filesystem tab"  
[ImageMapping]:/microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png "図 5: [ファイルシステム] タブに、ローカルファイルとネットワーク間のマッピングが表示されるようになりました  
[ImageStylesFuchsia]:/microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-sources-filesystem-css.msft.png "図 6: テキストエディターでの styles の表示"  
[Imageスタイル緑]:/microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-elements-styles-css.msft.png "図 7: ファイルがリンクされていることを示す緑色のインジケーター"
[ImageStylesGreen]: /microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-elements-styles-css.msft.png "Figure 7: The green indicator that the file is linked"  
[ImageSourcesCakeHTML]:/microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-sources-page-h1.msft.png "図 8: ソースパネルからの HTML の変更"  
<!--[ImageElementsCake]: /microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-change-h1.msft.png "Old Figure 9: Attempting to change HTML from the DOM Tree of the Elements panel"  -->  
[ImageCommandMenuQuickSource]:/microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-search-show-quick-source.msft.png "図 9: コマンドメニューを使用して [クイックソース] タブを開く  
[ImageOpenFileDialog]:/microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-search-script.msft.png "図 10: [ファイルを開く] ダイアログボックスを使ってスクリプトを開く  
[ImageScriptItalic]:/microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png "図 11: ページのリンクが斜体になっている  

<!-- links -->  

[DevToolsCssIndex]: /microsoft-edge/devtools-guide-chromium/css/index "CSS の表示と変更を始める"  

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
> <span data-ttu-id="5a5a1-249">このページの一部は、 [Google によっ][GoogleSitePolicies]て作成および共有され、[クリエイティブコモンズの「4.0 インターナショナルライセンス][CCA4IL]」で説明されている用語に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-249">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="5a5a1-250">元のページは[ここ](https://developers.google.com/web/tools/chrome-devtools/workspaces/index)にあり、 [Kayce Basques][KayceBasques]テクニカルライター、Chrome Devtools \ & Lighthouse \) で作成されています。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-250">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/workspaces/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブコモンズライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="5a5a1-252">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="5a5a1-252">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
