---
title: ワークスペースを使用してファイルを編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/20/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 8a31dd9fbfe492cf8eaacc654f7d501925f730f2
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942179"
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

# <span data-ttu-id="c960c-103">ワークスペースを使用してファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="c960c-103">Edit files with Workspaces</span></span>  

> [!NOTE]
> <span data-ttu-id="c960c-104">このチュートリアルの目標は、ワークスペースの設定と使用に関する実用的な演習を提供することで、独自のプロジェクトでワークスペースを使用できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="c960c-104">The goal of this tutorial is to provide hands-on practice in setting up and using Workspaces, so that you are able to use Workspaces in your own projects.</span></span>  <span data-ttu-id="c960c-105">ワークスペースを有効にした後で、DevTools 内で行ったソース コードに対する変更をローカル コンピューター上で保存できます。</span><span class="sxs-lookup"><span data-stu-id="c960c-105">You are able to save the changes to the source code, on your local computer, that you made within DevTools after you enable Workspaces.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="c960c-106">**前提条件**: このチュートリアルを開始する前に、次の操作を実行する方法を理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="c960c-106">**Prerequisites**: Before beginning this tutorial, you should know how to perform the following actions.</span></span>  
> 
> *   [<span data-ttu-id="c960c-107">Web ページを作成するには、html、CSS、JavaScript を使用する</span><span class="sxs-lookup"><span data-stu-id="c960c-107">Use html, CSS, and JavaScript to build a web page</span></span>][MDNWebGettingStarted]  
> *   [<span data-ttu-id="c960c-108">DevTools を使用して CSS に基本的な変更を加える</span><span class="sxs-lookup"><span data-stu-id="c960c-108">Use DevTools to make basic changes to CSS</span></span>][DevToolsCssIndex]  
> *   [<span data-ttu-id="c960c-109">ローカル HTTP Web サーバーを実行する</span><span class="sxs-lookup"><span data-stu-id="c960c-109">Run a local HTTP web server</span></span>][MDNSimpleLocalHTTPServer]  

## <span data-ttu-id="c960c-110">概要</span><span class="sxs-lookup"><span data-stu-id="c960c-110">Overview</span></span>  

<span data-ttu-id="c960c-111">ワークスペースを使用すると、Devtools で行う変更をコンピューター上の同じファイルのローカル コピーに保存できます。</span><span class="sxs-lookup"><span data-stu-id="c960c-111">Workspaces enable you to save a change that you make in Devtools to a local copy of the same file on your computer.</span></span>  <span data-ttu-id="c960c-112">このチュートリアルでは、コンピューターに次の設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="c960c-112">For this tutorial, you should have the following settings on your machine.</span></span>  

*   <span data-ttu-id="c960c-113">サイトのソース コードがデスクトップにあります。</span><span class="sxs-lookup"><span data-stu-id="c960c-113">You have the source code for your site on your desktop.</span></span>  
*   <span data-ttu-id="c960c-114">サイトがアクセスできるように、ソース コード ディレクトリからローカルの Web サーバーを実行している `localhost:8080` 場合。</span><span class="sxs-lookup"><span data-stu-id="c960c-114">You are running a local web server from the source code directory, so that the site is accessible at `localhost:8080`.</span></span>  
*   <span data-ttu-id="c960c-115">Microsoft Edge で `localhost:8080` 開き、DevTools を使用してサイトの CSS を変更します。</span><span class="sxs-lookup"><span data-stu-id="c960c-115">You opened `localhost:8080` in Microsoft Edge, and you are using DevTools to change the CSS of the site.</span></span>  

<span data-ttu-id="c960c-116">ワークスペースが有効になっていると、DevTools 内で行った CSS の変更は、デスクトップ上のソース コードに保存されます。</span><span class="sxs-lookup"><span data-stu-id="c960c-116">With Workspaces enabled, the CSS changes that you make within DevTools are saved to the source code on your desktop.</span></span>  

## <span data-ttu-id="c960c-117">制限事項</span><span class="sxs-lookup"><span data-stu-id="c960c-117">Limitations</span></span>  

<span data-ttu-id="c960c-118">モダン フレームワークを使用している場合、ソース コードはできるだけすばやく実行されるように最適化されている形式からソース コードを変換できることがあります。</span><span class="sxs-lookup"><span data-stu-id="c960c-118">If you are using a modern framework, it probably transforms your source code from a format that is easy to maintain into a format that is optimized to run as quickly as possible.</span></span>  

<span data-ttu-id="c960c-119">通常、ワークスペースは、最適化されたコードを元のソース コードにマップして元のコードに [マ][TreehouseBlogSourceMaps]ップすることができます。</span><span class="sxs-lookup"><span data-stu-id="c960c-119">Workspaces is usually able to map the optimized code back to your original source code with the help of [source maps][TreehouseBlogSourceMaps].</span></span>  <span data-ttu-id="c960c-120">しかし、各国でのソース マップの使用方法には、フレームワーク間のさまざまなバリエーションがあります。</span><span class="sxs-lookup"><span data-stu-id="c960c-120">But there is a lot of variation between frameworks over how each uses source maps.</span></span>  <span data-ttu-id="c960c-121">Devtools は、すべてのバリエーションをサポートするのが簡単です。</span><span class="sxs-lookup"><span data-stu-id="c960c-121">Devtools simply does support all of the variations.</span></span>  

<span data-ttu-id="c960c-122">ワークスペースは、次のフレームワークでは動作しないことを知っています。</span><span class="sxs-lookup"><span data-stu-id="c960c-122">Workspaces is known to not work with the following framework.</span></span>  

*   <span data-ttu-id="c960c-123">再度正アクティブ化アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="c960c-123">Create React App</span></span>  

    <!-- If you run into issues while using Workspaces with your framework of choice, or you get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  
    
## <span data-ttu-id="c960c-124">関連する機能: ローカル オーバーライド</span><span class="sxs-lookup"><span data-stu-id="c960c-124">Related feature: Local overrides</span></span>  

<span data-ttu-id="c960c-125">**ローカル オーバーライド** はワークスペースにおける別の DevTools 機能です。</span><span class="sxs-lookup"><span data-stu-id="c960c-125">**Local Overrides** is another DevTools feature that is similar to Workspaces.</span></span>  <span data-ttu-id="c960c-126">ページの変更を試してみて、ページの読み込み全体で変更を確認する必要がある場合は、ローカル オーバーライドを使用しますが、ページのソース コードに変更をマッピングすることはごまくわかりません。</span><span class="sxs-lookup"><span data-stu-id="c960c-126">Use Local Overrides when you want to experiment with changes to a page, and you need to see the changes across page loads, but you do not care about mapping your changes to the source code of the page.</span></span>  

<!--Todo: add section when content is ready  -->  

## <span data-ttu-id="c960c-127">手順 1: セットアップ</span><span class="sxs-lookup"><span data-stu-id="c960c-127">Step 1: Set up</span></span>  

<span data-ttu-id="c960c-128">ワークスペースでの操作性を高めているには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c960c-128">Complete the following actions, to get hands-on experience with Workspaces.</span></span>  

### <span data-ttu-id="c960c-129">デモを設定する</span><span class="sxs-lookup"><span data-stu-id="c960c-129">Set up the demo</span></span>  

1.  <span data-ttu-id="c960c-130">[デモを開きます][GlitchWorkspacesDemo]。</span><span class="sxs-lookup"><span data-stu-id="c960c-130">[Open the demo][GlitchWorkspacesDemo].</span></span>  <!--In the top-left of the editor, a randomly-generated project name is displayed.  -->  
    
    :::image type="complex" source="../media/workspaces-glitch-workspaces-demo-source.msft.png" alt-text="グリッチ プロジェクト" lightbox="../media/workspaces-glitch-workspaces-demo-source.msft.png":::
       <span data-ttu-id="c960c-132">グリッチ プロジェクト</span><span class="sxs-lookup"><span data-stu-id="c960c-132">A Glitch project</span></span>  
    :::image-end:::  
    
    <!--1.  Choose the project name.  -->  
    <!--1.  Select **Advanced Options** > **Download Project**.  
    
    :::image type="complex" source="../media/workspaces-glitch-advanced-options-download-project.msft.png" alt-text="The Download Project button" lightbox="../media/workspaces-glitch-advanced-options-download-project.msft.png":::
       The Download Project button  
    :::image-end:::  

    -->  
    <!--1.  Close the tab.  -->  
    <!--1.  Unzip the source code and move the unzipped `app` directory to your desktop.  For the rest of this tutorial the unzipped directory is referred to as `~/Desktop/app`.  -->  
    
1.  <span data-ttu-id="c960c-133">デスクトップに `app` ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c960c-133">Create an `app` directory on your desktop.</span></span>  <span data-ttu-id="c960c-134">ディレクトリからディレクトリ `workspaces-demo` にファイルのコピーを `app` 保存します。</span><span class="sxs-lookup"><span data-stu-id="c960c-134">Save copies of the files from the `workspaces-demo` directory to the `app` directory.</span></span>  <span data-ttu-id="c960c-135">チュートリアルの残りの場合、ディレクトリは "リテンシック" と評価されます `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="c960c-135">For the rest of the tutorial, the directory is referred to as `~/Desktop/app`.</span></span>  
1.  <span data-ttu-id="c960c-136">ローカル Web サーバーを開始します `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="c960c-136">Start a local web server in `~/Desktop/app`.</span></span>  <span data-ttu-id="c960c-137">以下は、起動時のサンプル コードですが `SimpleHTTPServer` 、どのサーバーを使用するのかを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c960c-137">Below is some sample code for starting up `SimpleHTTPServer`, but you may use whatever server you prefer.</span></span>  
    
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
    
1.  <span data-ttu-id="c960c-138">Microsoft Edge でタブを開き、ローカルでホストされているバージョンのサイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="c960c-138">Open a tab in Microsoft Edge and go to locally-hosted version of the site.</span></span>  <span data-ttu-id="c960c-139">URL やその URL を使ってアクセス `localhost:8080` できます `http://0.0.0.0:8080` 。</span><span class="sxs-lookup"><span data-stu-id="c960c-139">You should be able to access it using a URL like `localhost:8080` or `http://0.0.0.0:8080`.</span></span>  <span data-ttu-id="c960c-140">正しいポート [番号が異][WikiPortURLs] なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c960c-140">The exact [port number][WikiPortURLs] may be different.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo.msft.png" alt-text="デモ" lightbox="../media/workspaces-workspaces-demo.msft.png":::
       <span data-ttu-id="c960c-142">デモ</span><span class="sxs-lookup"><span data-stu-id="c960c-142">The demo</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="c960c-143">DevTools のセットアップ</span><span class="sxs-lookup"><span data-stu-id="c960c-143">Set up DevTools</span></span>  

1.  <span data-ttu-id="c960c-144">`Control` + `Shift` + `J` \(Windows\) または `Command` + `Option` + `J` \(macOS\) を選択して DevTools**の本体**パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c960c-144">Select `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) to open the **Console** panel of DevTools.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-console.msft.png" alt-text="本体パネル" lightbox="../media/workspaces-workspaces-demo-console.msft.png":::
       <span data-ttu-id="c960c-146">本 **体パ** ネル</span><span class="sxs-lookup"><span data-stu-id="c960c-146">The **Console** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c960c-147">[ソース] **タブを選** びます。</span><span class="sxs-lookup"><span data-stu-id="c960c-147">Choose the **Sources** tab.</span></span>  
1.  <span data-ttu-id="c960c-148">**[Filesystem] タブを選**びます。</span><span class="sxs-lookup"><span data-stu-id="c960c-148">Choose the **Filesystem** tab.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem.msft.png" alt-text="[ファイルシステム] タブ" lightbox="../media/workspaces-workspaces-demo-sources-filesystem.msft.png":::
       <span data-ttu-id="c960c-150">**[ファイルシステム]** タブ</span><span class="sxs-lookup"><span data-stu-id="c960c-150">The **Filesystem** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c960c-151">[ワ **ークスペースにフォルダーを追加] を選びます**。</span><span class="sxs-lookup"><span data-stu-id="c960c-151">Choose **Add Folder To Workspace**.</span></span>  
1.  <span data-ttu-id="c960c-152">「`~/Desktop/app`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="c960c-152">Type `~/Desktop/app`.</span></span>  
1.  <span data-ttu-id="c960c-153">[Allow to Give to DevTools permission to read and writs to read and write to the directory] **([Allow** to DevTools] を選び、ディレクトリの読み取りと書き込みを許可します。</span><span class="sxs-lookup"><span data-stu-id="c960c-153">Choose **Allow** to give DevTools permission to read and write to the directory.</span></span>  
    <span data-ttu-id="c960c-154">[ **ファイルシステム]** タブには、緑のドットが隣り合 `index.html` わせ表示 `script.js` されます `styles.css` 。</span><span class="sxs-lookup"><span data-stu-id="c960c-154">In the **Filesystem** tab, there is now a green dot next to `index.html`, `script.js`, and `styles.css`.</span></span>  <span data-ttu-id="c960c-155">これらの緑のドットは、DevTools がページのネットワーク リソースとその中のファイル間のマッピングを決定したことを意味します `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="c960c-155">These green dots mean that DevTools has established a mapping between the network resources of the page, and the files in `~/Desktop/app`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png" alt-text="[ファイル] タブに、ローカル ファイルとネットワーク ネットワークの間のマッピングが表示されるようになりました" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png":::
       <span data-ttu-id="c960c-157">[ **ファイル] タブ** に、ローカル ファイルとネットワーク ネットワークの間のマッピングが表示されるようになりました</span><span class="sxs-lookup"><span data-stu-id="c960c-157">The **Filesystem** tab now shows a mapping between the local files and the network ones</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="c960c-158">手順 2: CSS をディスクに変更する</span><span class="sxs-lookup"><span data-stu-id="c960c-158">Step 2: Save a CSS change to disk</span></span>  

1.  <span data-ttu-id="c960c-159">開 `styles.css` きます。</span><span class="sxs-lookup"><span data-stu-id="c960c-159">Open `styles.css`.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="c960c-160">要素 `color` のプロパティ `h1` は設定されています `fuchsia` 。</span><span class="sxs-lookup"><span data-stu-id="c960c-160">The `color` property of `h1` elements is set to `fuchsia`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png" alt-text="テキスト エディターでスタイル.css を表示する" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png":::
       <span data-ttu-id="c960c-162">テキスト `styles.css` エディターで表示する</span><span class="sxs-lookup"><span data-stu-id="c960c-162">View `styles.css` in a text editor</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c960c-163">[要素 **] タブを選** びます。</span><span class="sxs-lookup"><span data-stu-id="c960c-163">Choose the **Elements** tab.</span></span>  
1.  <span data-ttu-id="c960c-164">要素のプロパティ `color` の値を `<h1>` お気に入りの色に変更します。</span><span class="sxs-lookup"><span data-stu-id="c960c-164">Change the value of the `color` property of the `<h1>` element to your favorite color.</span></span>  
    <span data-ttu-id="c960c-165">[スタイル] ウィンドウに CSS ルールが適用されている CSS ルールを表示するには `<h1>` **、DOM ツ** リーで要素を **選ぶ必要** があります。</span><span class="sxs-lookup"><span data-stu-id="c960c-165">Remember that you need to choose the `<h1>` element in the **DOM Tree** in order to see the CSS rules applied to it in the **Styles** pane.</span></span>  <span data-ttu-id="c960c-166">横にある緑色のドットは、行う変更がマップされている `styles.css:1` ことを意味します `~/Desktop/app/styles.css` 。</span><span class="sxs-lookup"><span data-stu-id="c960c-166">The green dot next to `styles.css:1` means that any change that you make are mapped to `~/Desktop/app/styles.css`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-css.msft.png" alt-text="ファイルがリンクされている緑のインジケーター" lightbox="../media/workspaces-workspaces-demo-elements-styles-css.msft.png":::
       <span data-ttu-id="c960c-168">ファイルがリンクされている緑のインジケーター</span><span class="sxs-lookup"><span data-stu-id="c960c-168">The green indicator that the file is linked</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c960c-169">もう `styles.css` 一度テキスト エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="c960c-169">Open `styles.css` in a text editor again.</span></span>  <span data-ttu-id="c960c-170">これ `color` で、このプロパティはお気に入りの色に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c960c-170">The `color` property is now set to your favorite color.</span></span>  
1.  <span data-ttu-id="c960c-171">ページを最新の情報に更新してください。</span><span class="sxs-lookup"><span data-stu-id="c960c-171">Refresh the page.</span></span>  <span data-ttu-id="c960c-172">要素の色は `<h1>` 、引き続きお気に入りの色に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c960c-172">The color of the `<h1>` element is still set to your favorite color.</span></span>  <span data-ttu-id="c960c-173">変更内容はディスクに保存されたため、更新中も維維します。</span><span class="sxs-lookup"><span data-stu-id="c960c-173">The change remains across a refresh, because when you made the change DevTools saved the change to disk.</span></span>  <span data-ttu-id="c960c-174">そして、ページを更新すると、ローカル サーバーはディスクから変更されたファイルのコピーを開示しました。</span><span class="sxs-lookup"><span data-stu-id="c960c-174">And then, when you refreshed the page, your local server served the modified copy of the file from disk.</span></span>  
    
## <span data-ttu-id="c960c-175">手順 3: ディスクに HTML 変更を保存する</span><span class="sxs-lookup"><span data-stu-id="c960c-175">Step 3: Save an HTML change to disk</span></span>  

### <span data-ttu-id="c960c-176">[要素パネル] から HTML を変更する</span><span class="sxs-lookup"><span data-stu-id="c960c-176">Change HTML from the Elements Panel</span></span>  

<span data-ttu-id="c960c-177">要素パネルから HTML を変更できますが、DOM ツリーの変更はディスクに保存されず、現在のブラウザーの操作のみが有効です。</span><span class="sxs-lookup"><span data-stu-id="c960c-177">You may make changes to the html from the Element Panel, but your changes to the DOM tree are not saved to disk and only effect the current browser session.</span></span>  

<span data-ttu-id="c960c-178">DOM ツライは html ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c960c-178">The DOM tree is not html.</span></span>  

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

### <span data-ttu-id="c960c-179">[ソース] パネルから HTML を変更する</span><span class="sxs-lookup"><span data-stu-id="c960c-179">Change HTML from the Sources panel</span></span>  

<span data-ttu-id="c960c-180">ページの html への変更を保存する場合は、[ソース] パネル **で行** います。</span><span class="sxs-lookup"><span data-stu-id="c960c-180">If you want to save a change to the html of the page, do it using the **Sources** panel.</span></span>  

1.  <span data-ttu-id="c960c-181">[ソース] **タブを選** びます。</span><span class="sxs-lookup"><span data-stu-id="c960c-181">Choose the **Sources** tab.</span></span>  
1.  <span data-ttu-id="c960c-182">[ページ] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="c960c-182">Choose the **Page** tab.</span></span>  
1.  <span data-ttu-id="c960c-183">**[(索引) を選びます] を選びます**。</span><span class="sxs-lookup"><span data-stu-id="c960c-183">Choose **(index)**.</span></span>  <span data-ttu-id="c960c-184">ページの HTML が開きます。</span><span class="sxs-lookup"><span data-stu-id="c960c-184">The HTML for the page opens.</span></span>  
1.  <span data-ttu-id="c960c-185">置換 `<h1>Workspaces Demo</h1>` の文字列 `<h1>I ❤️  Cake</h1>`</span><span class="sxs-lookup"><span data-stu-id="c960c-185">Replace `<h1>Workspaces Demo</h1>` with `<h1>I ❤️  Cake</h1>`.</span></span>  <span data-ttu-id="c960c-186">次の図を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c960c-186">See the following figure.</span></span>  
1.  <span data-ttu-id="c960c-187">`Control` + `S` \(Windows\) または `Command` + `S` \(macOS\) を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c960c-187">Select `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save the change.</span></span>  
1.  <span data-ttu-id="c960c-188">ページを最新の情報に更新してください。</span><span class="sxs-lookup"><span data-stu-id="c960c-188">Refresh the page.</span></span>  <span data-ttu-id="c960c-189">要素 `<h1>` には新しいテキストが引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="c960c-189">The `<h1>` element is still displaying the new text.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-page-h1.msft.png" alt-text="[ソース] パネルから HTML を変更する" lightbox="../media/workspaces-workspaces-demo-sources-page-h1.msft.png":::
       <span data-ttu-id="c960c-191">[ソース] パネル **から HTML を** 変更する</span><span class="sxs-lookup"><span data-stu-id="c960c-191">Change HTML from the **Sources** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c960c-192">開 `~/Desktop/app/index.html` きます。</span><span class="sxs-lookup"><span data-stu-id="c960c-192">Open `~/Desktop/app/index.html`.</span></span>  <span data-ttu-id="c960c-193">要素 `<h1>` には新しいテキストが含まれている。</span><span class="sxs-lookup"><span data-stu-id="c960c-193">The `<h1>` element contains the new text.</span></span>  
    
## <span data-ttu-id="c960c-194">手順 4: JavaScript の変更をディスクに保存する</span><span class="sxs-lookup"><span data-stu-id="c960c-194">Step 4: Save a JavaScript change to disk</span></span>  

<span data-ttu-id="c960c-195">[ **ソース]** パネルは、JavaScript に変更を加える場所です。</span><span class="sxs-lookup"><span data-stu-id="c960c-195">The **Sources** panel is also the place to make changes to JavaScript.</span></span>  <span data-ttu-id="c960c-196">ただし、場合によっては、[ **要素** ] パネルや **[本** 体] パネルなど、他のパネルにアクセスしなけやすくなり、サイトに変更を加える必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="c960c-196">But sometimes you need to access other panels, such as the **Elements** panel or the **Console** panel, while making changes to your site.</span></span>  <span data-ttu-id="c960c-197">[ソース] パネル**Sources**を他のパネルと一度に開く方法があります。</span><span class="sxs-lookup"><span data-stu-id="c960c-197">There is a way to have the **Sources** panel open alongside other panels.</span></span>  

1.  <span data-ttu-id="c960c-198">[要素 **] タブを選** びます。</span><span class="sxs-lookup"><span data-stu-id="c960c-198">Choose the **Elements** tab.</span></span>  
1.  <span data-ttu-id="c960c-199">`Control` + `Shift` + `P` \(Windows\) または `Command` + `Shift` + `P` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="c960c-199">Select `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  <span data-ttu-id="c960c-200">コマンド **メニューが** 開きます。</span><span class="sxs-lookup"><span data-stu-id="c960c-200">The **Command Menu** opens.</span></span>  
1.  <span data-ttu-id="c960c-201">「クイック `QS` ソースの **表示」を選びます**。</span><span class="sxs-lookup"><span data-stu-id="c960c-201">Type `QS`, then select **Show Quick Source**.</span></span>  <span data-ttu-id="c960c-202">[開発ツール] ウィンドウの下部に 、[クイック ソース] タブ **が表示されています** 。 タブには、[ソース] パネルで最後に編集したファイルである `index.html` **内容が** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="c960c-202">At the bottom of your DevTools window there is now a **Quick Source** tab.  The tab is displaying the contents of `index.html`, which is the last file you edited in the **Sources** panel.</span></span>  <span data-ttu-id="c960c-203">[**クイック ソース]** タブには [ソース]**Sources**パネルからエディターが表示されるので、他のパネルを開いている間にファイルを編集できます。</span><span class="sxs-lookup"><span data-stu-id="c960c-203">The **Quick Source** tab gives you the editor from the **Sources** panel, so that you are able to edit files while having other panels open.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png" alt-text="[コマンド] メニューを使用して [クイック ソース] タブを開く" lightbox="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png":::
       <span data-ttu-id="c960c-205">[コマンド] **メニューを使用して [** クイック ソース] **タブを開く**</span><span class="sxs-lookup"><span data-stu-id="c960c-205">Open the **Quick Source** tab using **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c960c-206">`Control` + `P` \(Windows\) または `Command` + `P` \(macOS\) を選択して、[ファイルを**開く] ダイアログを開**きます。</span><span class="sxs-lookup"><span data-stu-id="c960c-206">Select `Control`+`P` \(Windows\) or `Command`+`P` \(macOS\) to open the **Open File** dialog.</span></span>  <span data-ttu-id="c960c-207">次の図を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c960c-207">See the following figure.</span></span>  
1.  <span data-ttu-id="c960c-208">「 `script` 入力してアプリ \*\*/またはアプリ/ボタンscript.js。 \*\*</span><span class="sxs-lookup"><span data-stu-id="c960c-208">Type `script`, then select **app/script.js**.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-script.msft.png" alt-text="[ファイルを開script.js] ダイアログ ボックスを使用して、タブを開く" lightbox="../media/workspaces-workspaces-demo-search-script.msft.png":::
       <span data-ttu-id="c960c-210">[ファイル `script.js` を開 **く] ダイアログ ボックスを使って開** く</span><span class="sxs-lookup"><span data-stu-id="c960c-210">Open `script.js` using the **Open File** dialog</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="c960c-211">デ `Save Changes To Disk With Workspaces` モのリンクは定的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c960c-211">The `Save Changes To Disk With Workspaces` link in the demo is styled regularly.</span></span>  
    
1.  <span data-ttu-id="c960c-212">[クイック ソース] タブを使用**して、script.jsの下部に次の\*\*\*\*コードを追加**します。</span><span class="sxs-lookup"><span data-stu-id="c960c-212">Add the following code to the bottom of **script.js** using the **Quick Source** tab.</span></span>  
    
    ```javascript
    console.log('greetings from script.js');
    document.querySelector('a').style = 'font-style:italic';
    ```  
    
1.  <span data-ttu-id="c960c-213">`Control` + `S` \(Windows\) または `Command` + `S` \(macOS\) を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c960c-213">Select `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save the change.</span></span>  
1.  <span data-ttu-id="c960c-214">ページを最新の情報に更新してください。</span><span class="sxs-lookup"><span data-stu-id="c960c-214">Refresh the page.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="c960c-215">ページ上のリンクがイタリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="c960c-215">The link on the page is now italicized.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png" alt-text="ページ上のリンクがイタリアル化されるようになりました" lightbox="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png":::
       <span data-ttu-id="c960c-217">ページ上のリンクがイタリアル化されるようになりました</span><span class="sxs-lookup"><span data-stu-id="c960c-217">The link on the page is now italicized</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="c960c-218">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c960c-218">Next steps</span></span>  

<span data-ttu-id="c960c-219">このチュートリアルで学習したものを使用して、自分のプロジェクトでワークスペースを設定します。</span><span class="sxs-lookup"><span data-stu-id="c960c-219">Use what you have learned in this tutorial to set up Workspaces in your own project.</span></span>  <!-- If you run into any issues or are able to get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  

<!--  
If you have more feedback on the topics or anything else, please use any of the channels below:  

*   [Mailing List][AlphabetGroupsAlphabetBrowserDevTools]  
*   [Twitter][TwitterAlphabetBrowserDevTools]  
    -->  

<!-- links -->  

[DevToolsCssIndex]: ../css/index.md "CSS の表示と変更を開始する |Microsoft ドキュメント"  

<!--[LocalOverrides]: ../whats-new/2018/01/devtools#overrides -->  

<!--[AlphabetGroupsAlphabetBrowserDevTools]: https://groups.alphabet.com/forum/#!forum/alphabet-browser-developer-tools "Alphabet Browser DevTools - Alphabet Groups"  -->  

[GlitchWorkspacesDemo]: https://glitch.com/edit/#!/microsoft-edge-chromium-devtools?path=workspaces-demo/index.html:1:0 "ワークスペース デモ ファイル |グリトチ"  

[MDNCSSContent]: https://developer.mozilla.org/docs/Web/CSS/content "コンテンツ - CSS:カスケード スタイル シート |MDN"  
[MDNWebGettingStarted]: https://developer.mozilla.org/docs/Learn/Getting_started_with_the_web "Web の使用を開始する |MDN"  
[MDNSimpleLocalHTTPServer]: https://developer.mozilla.org/docs/Learn/Common_questions/set_up_a_local_testing_server#Running_a_simple_local_HTTP_server "簡単なローカル HTTP サーバーを実行する |MDN"  
[MDNWebAPIsDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM - Web API の概要 |MDN"  

<!--[StackOverflowAlphabetBrowserDevTools]: https://stackoverflow.com/questions/ask?tags=alphabet-browser-devtools "Alphabet Browser DevTools - Stack Overflow"  -->

[TreehouseBlogSourceMaps]: https://blog.teamtreehouse.com/introduction-source-maps "ソース マップの概要 |Treehouse ブログ"  

<!-- [TwitterAlphabetBrowserDevTools]: https://twitter.com/alphabetbrowserdevtools "Alphabet Browser DevTools \(@AlphabetBrowserDevTools\) | Twitter"  -->

[WikiPortURLs]: https://en.wikipedia.org/wiki/Port_(computer_networking)#Use_in_URLs "ポート \(コンピューター ネットワーク\) - Wikipedia"  

> [!NOTE]
> <span data-ttu-id="c960c-228">このページの一部は [、Google][GoogleSitePolicies] によって作成され共有された作業および共有に基づいて変更され、クリエイティブ コモンス属性 [4.0 国際ライセンス][CCA4IL]で説明されている用語に応じた使用されます。</span><span class="sxs-lookup"><span data-stu-id="c960c-228">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c960c-229">ここには元のページが表示[され](https://developers.google.com/web/tools/chrome-devtools/workspaces/index)[、Kayce Basques][KayceBasques] \(テクニカル ライター, Chrome DevTools \& Lighthouse\) によって作成されます。</span><span class="sxs-lookup"><span data-stu-id="c960c-229">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/workspaces/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![クリエイティブ コブル ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="c960c-231">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="c960c-231">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
