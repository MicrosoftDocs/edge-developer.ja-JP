---
description: DevTools 内で行われた変更をディスクに保存する方法について学習します。
title: Workspaces を使用してファイルを編集する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 開発、f12 ツール、devtools
ms.openlocfilehash: 17f9ced15dbacd62c9ffe40e4af889925a8155fb
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399247"
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

# <a name="edit-files-with-workspaces"></a><span data-ttu-id="6b07e-104">Workspaces を使用してファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="6b07e-104">Edit files with Workspaces</span></span>  

> [!NOTE]
> <span data-ttu-id="6b07e-105">このチュートリアルの目的は、ワークスペースをセットアップして使用する実践的な方法を提供し、独自のプロジェクトで Workspaces を使用する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="6b07e-105">The goal of this tutorial is to provide hands-on practice in setting up and using Workspaces, so that you are able to use Workspaces in your own projects.</span></span>  <span data-ttu-id="6b07e-106">Workspaces を有効にした後、DevTools 内で行ったソース コードへの変更をローカル コンピューターに保存できます。</span><span class="sxs-lookup"><span data-stu-id="6b07e-106">You are able to save the changes to the source code, on your local computer, that you made within DevTools after you enable Workspaces.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="6b07e-107">**前提条件**: このチュートリアルを開始する前に、次の操作を実行する方法を知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b07e-107">**Prerequisites**: Before beginning this tutorial, you should know how to perform the following actions.</span></span>  
> 
> *   [<span data-ttu-id="6b07e-108">html、CSS、JavaScript を使用して Web ページを作成する</span><span class="sxs-lookup"><span data-stu-id="6b07e-108">Use html, CSS, and JavaScript to build a web page</span></span>][MDNWebGettingStarted]  
> *   [<span data-ttu-id="6b07e-109">DevTools を使用して CSS に基本的な変更を加える</span><span class="sxs-lookup"><span data-stu-id="6b07e-109">Use DevTools to make basic changes to CSS</span></span>][DevToolsCssIndex]  
> *   [<span data-ttu-id="6b07e-110">ローカル HTTP Web サーバーの実行</span><span class="sxs-lookup"><span data-stu-id="6b07e-110">Run a local HTTP web server</span></span>][MDNSimpleLocalHTTPServer]  

## <a name="overview"></a><span data-ttu-id="6b07e-111">概要</span><span class="sxs-lookup"><span data-stu-id="6b07e-111">Overview</span></span>  

<span data-ttu-id="6b07e-112">ワークスペースを使用すると、Devtools で行った変更を、コンピューター上の同じファイルのローカル コピーに保存できます。</span><span class="sxs-lookup"><span data-stu-id="6b07e-112">Workspaces enable you to save a change that you make in Devtools to a local copy of the same file on your computer.</span></span>  <span data-ttu-id="6b07e-113">このチュートリアルでは、コンピューターに次の設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="6b07e-113">For this tutorial, you should have the following settings on your machine.</span></span>  

*   <span data-ttu-id="6b07e-114">デスクトップ上にサイトのソース コードがあります。</span><span class="sxs-lookup"><span data-stu-id="6b07e-114">You have the source code for your site on your desktop.</span></span>  
*   <span data-ttu-id="6b07e-115">ソース コード ディレクトリからローカル Web サーバーを実行して、サイトにアクセスできます `localhost:8080` 。</span><span class="sxs-lookup"><span data-stu-id="6b07e-115">You are running a local web server from the source code directory, so that the site is accessible at `localhost:8080`.</span></span>  
*   <span data-ttu-id="6b07e-116">Microsoft `localhost:8080` Edge で開き、DevTools を使用してサイトの CSS を変更しています。</span><span class="sxs-lookup"><span data-stu-id="6b07e-116">You opened `localhost:8080` in Microsoft Edge, and you are using DevTools to change the CSS of the site.</span></span>  

<span data-ttu-id="6b07e-117">Workspaces を有効にすると、DevTools 内で行った CSS の変更がデスクトップのソース コードに保存されます。</span><span class="sxs-lookup"><span data-stu-id="6b07e-117">With Workspaces enabled, the CSS changes that you make within DevTools are saved to the source code on your desktop.</span></span>  

## <a name="limitations"></a><span data-ttu-id="6b07e-118">制限事項</span><span class="sxs-lookup"><span data-stu-id="6b07e-118">Limitations</span></span>  

<span data-ttu-id="6b07e-119">モダン フレームワークを使用している場合は、ソース コードを保守しやすい形式から、可能な限り迅速に実行するために最適化された形式に変換される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6b07e-119">If you are using a modern framework, it probably transforms your source code from a format that is easy to maintain into a format that is optimized to run as quickly as possible.</span></span>  

<span data-ttu-id="6b07e-120">ワークスペースは、通常、ソース マップの助けを借りて、最適化されたコードを元のソース コードに [マップすることができます][TreehouseBlogSourceMaps]。</span><span class="sxs-lookup"><span data-stu-id="6b07e-120">Workspaces is usually able to map the optimized code back to your original source code with the help of [source maps][TreehouseBlogSourceMaps].</span></span>  <span data-ttu-id="6b07e-121">ただし、各ソース マップの使い方に関して、フレームワーク間には多くのバリエーションがあります。</span><span class="sxs-lookup"><span data-stu-id="6b07e-121">But there is a lot of variation between frameworks over how each uses source maps.</span></span>  <span data-ttu-id="6b07e-122">Devtools は単にすべてのバリエーションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="6b07e-122">Devtools simply does support all of the variations.</span></span>  

<span data-ttu-id="6b07e-123">ワークスペースは、次のフレームワークでは動作しません。</span><span class="sxs-lookup"><span data-stu-id="6b07e-123">Workspaces is known to not work with the following framework.</span></span>  

*   <span data-ttu-id="6b07e-124">React アプリの作成</span><span class="sxs-lookup"><span data-stu-id="6b07e-124">Create React App</span></span>  

    <!-- If you run into issues while using Workspaces with your framework of choice, or you get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  
    
## <a name="related-feature-local-overrides"></a><span data-ttu-id="6b07e-125">関連機能: ローカルオーバーライド</span><span class="sxs-lookup"><span data-stu-id="6b07e-125">Related feature: Local overrides</span></span>  

<span data-ttu-id="6b07e-126">**ローカル オーバーライドは** 、Workspaces に似た別の DevTools 機能です。</span><span class="sxs-lookup"><span data-stu-id="6b07e-126">**Local Overrides** is another DevTools feature that is similar to Workspaces.</span></span>  <span data-ttu-id="6b07e-127">Web ページの変更を試し、Web ページの読み込み間で変更を表示する必要がある場合はローカルオーバーライドを使用しますが、変更を Web ページのソース コードにマッピングする場合は気にしません。</span><span class="sxs-lookup"><span data-stu-id="6b07e-127">Use Local Overrides when you want to experiment with changes to a webpage, and you need to display the changes across webpage loads, but you do not care about mapping your changes to the source code of the webpage.</span></span>  

<!--Todo: add section when content is ready  -->  

## <a name="step-1-set-up"></a><span data-ttu-id="6b07e-128">手順 1: セットアップ</span><span class="sxs-lookup"><span data-stu-id="6b07e-128">Step 1: Set up</span></span>  

<span data-ttu-id="6b07e-129">Workspaces で実践的なエクスペリエンスを得るには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="6b07e-129">Complete the following actions, to get hands-on experience with Workspaces.</span></span>  

### <a name="set-up-the-demo"></a><span data-ttu-id="6b07e-130">デモのセットアップ</span><span class="sxs-lookup"><span data-stu-id="6b07e-130">Set up the demo</span></span>  

1.  <span data-ttu-id="6b07e-131">[デモを開きます][GlitchWorkspacesDemo]。</span><span class="sxs-lookup"><span data-stu-id="6b07e-131">[Open the demo][GlitchWorkspacesDemo].</span></span>  <!--In the top-left of the editor, a randomly-generated project name is displayed.  -->  
    
    :::image type="complex" source="../media/workspaces-glitch-workspaces-demo-source.msft.png" alt-text="Glitch プロジェクト" lightbox="../media/workspaces-glitch-workspaces-demo-source.msft.png":::
       <span data-ttu-id="6b07e-133">Glitch プロジェクト</span><span class="sxs-lookup"><span data-stu-id="6b07e-133">A Glitch project</span></span>  
    :::image-end:::  
    
    <!--1.  Choose the project name.  -->  
    <!--1.  Choose **Advanced Options** > **Download Project**.  
    
    :::image type="complex" source="../media/workspaces-glitch-advanced-options-download-project.msft.png" alt-text="The Download Project button" lightbox="../media/workspaces-glitch-advanced-options-download-project.msft.png":::
       The Download Project button  
    :::image-end:::  

    -->  
    <!--1.  Close the tab.  -->  
    <!--1.  Unzip the source code and move the unzipped `app` directory to your desktop.  For the rest of this tutorial the unzipped directory is referred to as `~/Desktop/app`.  -->  
    
1.  <span data-ttu-id="6b07e-134">デスクトップに `app` ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b07e-134">Create an `app` directory on your desktop.</span></span>  <span data-ttu-id="6b07e-135">ディレクトリからディレクトリにファイル `workspaces-demo` のコピーを保存 `app` します。</span><span class="sxs-lookup"><span data-stu-id="6b07e-135">Save copies of the files from the `workspaces-demo` directory to the `app` directory.</span></span>  <span data-ttu-id="6b07e-136">チュートリアルの残りの部分では、ディレクトリはと呼ばれます `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="6b07e-136">For the rest of the tutorial, the directory is referred to as `~/Desktop/app`.</span></span>  
1.  <span data-ttu-id="6b07e-137">でローカル Web サーバーを起動します `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="6b07e-137">Start a local web server in `~/Desktop/app`.</span></span>  <span data-ttu-id="6b07e-138">以下に、起動用のサンプル コードを示しますが、必要な `SimpleHTTPServer` サーバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b07e-138">Below is some sample code for starting up `SimpleHTTPServer`, but you may use whatever server you prefer.</span></span>  
    
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
    
1.  <span data-ttu-id="6b07e-139">Microsoft Edge でタブを開き、ローカルでホストされているバージョンのサイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="6b07e-139">Open a tab in Microsoft Edge and navigate to locally-hosted version of the site.</span></span>  <span data-ttu-id="6b07e-140">URL を使用してアクセスできる必要 `localhost:8080` があります `http://0.0.0.0:8080` 。</span><span class="sxs-lookup"><span data-stu-id="6b07e-140">You should be able to access it using a URL like `localhost:8080` or `http://0.0.0.0:8080`.</span></span>  <span data-ttu-id="6b07e-141">正確な [ポート番号は][WikiPortURLs] 異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6b07e-141">The exact [port number][WikiPortURLs] may be different.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo.msft.png" alt-text="デモ" lightbox="../media/workspaces-workspaces-demo.msft.png":::
       <span data-ttu-id="6b07e-143">デモ</span><span class="sxs-lookup"><span data-stu-id="6b07e-143">The demo</span></span>  
    :::image-end:::  
    
### <a name="set-up-devtools"></a><span data-ttu-id="6b07e-144">DevTools のセットアップ</span><span class="sxs-lookup"><span data-stu-id="6b07e-144">Set up DevTools</span></span>  

1.  <span data-ttu-id="6b07e-145">`Control` + `Shift` + `J` \(Windows, Linux\) または `Command` + `Option` + `J` \(macOS\) を選択して、DevTools の**コンソール**パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6b07e-145">Select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\) to open the **Console** panel of DevTools.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-console.msft.png" alt-text="[コンソール] パネル" lightbox="../media/workspaces-workspaces-demo-console.msft.png":::
       <span data-ttu-id="6b07e-147">[ **コンソール]** パネル</span><span class="sxs-lookup"><span data-stu-id="6b07e-147">The **Console** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6b07e-148">[ソース] **ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="6b07e-148">Choose the **Sources** tool.</span></span>  
1.  <span data-ttu-id="6b07e-149">[ファイルシステム] **パネルを選択** します。</span><span class="sxs-lookup"><span data-stu-id="6b07e-149">Choose the **Filesystem** panel.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem.msft.png" alt-text="[ファイルシステム] パネル" lightbox="../media/workspaces-workspaces-demo-sources-filesystem.msft.png":::
       <span data-ttu-id="6b07e-151">[ **ファイルシステム]** パネル</span><span class="sxs-lookup"><span data-stu-id="6b07e-151">The **Filesystem** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6b07e-152">[ワークスペース **にフォルダーを追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6b07e-152">Choose **Add Folder To Workspace**.</span></span>  
1.  <span data-ttu-id="6b07e-153">「`~/Desktop/app`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6b07e-153">Type `~/Desktop/app`.</span></span>  
1.  <span data-ttu-id="6b07e-154">[ **許可] を** 選択して、ディレクトリへの読み取りおよび書き込みのアクセス許可を DevTools に付与します。</span><span class="sxs-lookup"><span data-stu-id="6b07e-154">Choose **Allow** to give DevTools permission to read and write to the directory.</span></span>  
    <span data-ttu-id="6b07e-155">[ファイルシステム **] パネル** で、 、 と の横に緑 `index.html` の `script.js` ドットが表示されます `styles.css` 。</span><span class="sxs-lookup"><span data-stu-id="6b07e-155">In the **Filesystem** panel, there is now a green dot next to `index.html`, `script.js`, and `styles.css`.</span></span>  <span data-ttu-id="6b07e-156">これらの緑色の点は、DevTools がページのネットワーク リソースと内のファイルとの間にマッピングを確立したという意味です `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="6b07e-156">These green dots mean that DevTools has established a mapping between the network resources of the page, and the files in `~/Desktop/app`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png" alt-text="[ファイルシステム] パネルに、ローカル ファイルとネットワーク ファイルのマッピングが表示されます。" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png":::
       <span data-ttu-id="6b07e-158">[ **ファイルシステム]** パネルに、ローカル ファイルとネットワーク ファイルのマッピングが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b07e-158">The **Filesystem** panel now shows a mapping between the local files and the network ones</span></span>  
    :::image-end:::  
    
## <a name="step-2-save-a-css-change-to-disk"></a><span data-ttu-id="6b07e-159">手順 2: CSS の変更をディスクに保存する</span><span class="sxs-lookup"><span data-stu-id="6b07e-159">Step 2: Save a CSS change to disk</span></span>  

1.  <span data-ttu-id="6b07e-160">を `styles.css` 開きます。</span><span class="sxs-lookup"><span data-stu-id="6b07e-160">Open `styles.css`.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="6b07e-161">要素 `color` のプロパティ `h1` は に設定されます `fuchsia` 。</span><span class="sxs-lookup"><span data-stu-id="6b07e-161">The `color` property of `h1` elements is set to `fuchsia`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png" alt-text="テキスト エディターで styles.css を表示する" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png":::
       <span data-ttu-id="6b07e-163">テキスト `styles.css` エディターでの表示</span><span class="sxs-lookup"><span data-stu-id="6b07e-163">View `styles.css` in a text editor</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6b07e-164">[要素] **ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="6b07e-164">Choose the **Elements** tool.</span></span>  
1.  <span data-ttu-id="6b07e-165">要素のプロパティの値 `color` を、お気に `<h1>` 入りの色に変更します。</span><span class="sxs-lookup"><span data-stu-id="6b07e-165">Change the value of the `color` property of the `<h1>` element to your favorite color.</span></span>  
    <span data-ttu-id="6b07e-166">スタイル ウィンドウに適用される CSS ルールを表示するには `<h1>` **、DOM ツリー** で要素を選択する **必要** があります。</span><span class="sxs-lookup"><span data-stu-id="6b07e-166">Remember that you need to choose the `<h1>` element in the **DOM Tree** in order to display the CSS rules applied to it in the **Styles** pane.</span></span>  <span data-ttu-id="6b07e-167">次の緑の点 `styles.css:1` は、変更がマップされる点を意味します `~/Desktop/app/styles.css` 。</span><span class="sxs-lookup"><span data-stu-id="6b07e-167">The green dot next to `styles.css:1` means that any change that you make are mapped to `~/Desktop/app/styles.css`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-css.msft.png" alt-text="ファイルがリンクされている緑色のインジケーター" lightbox="../media/workspaces-workspaces-demo-elements-styles-css.msft.png":::
       <span data-ttu-id="6b07e-169">ファイルがリンクされている緑色のインジケーター</span><span class="sxs-lookup"><span data-stu-id="6b07e-169">The green indicator that the file is linked</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6b07e-170">テキスト `styles.css` エディターで再度開きます。</span><span class="sxs-lookup"><span data-stu-id="6b07e-170">Open `styles.css` in a text editor again.</span></span>  <span data-ttu-id="6b07e-171">この `color` プロパティは、お気に入りの色に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6b07e-171">The `color` property is now set to your favorite color.</span></span>  
1.  <span data-ttu-id="6b07e-172">ページを最新の情報に更新してください。</span><span class="sxs-lookup"><span data-stu-id="6b07e-172">Refresh the page.</span></span>  <span data-ttu-id="6b07e-173">要素の色は `<h1>` 、引き続きお気に入りの色に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6b07e-173">The color of the `<h1>` element is still set to your favorite color.</span></span>  <span data-ttu-id="6b07e-174">変更を行った場合、DevTools によって変更がディスクに保存されたため、更新後も変更はそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="6b07e-174">The change remains across a refresh, because when you made the change DevTools saved the change to disk.</span></span>  <span data-ttu-id="6b07e-175">次に、ページを更新すると、ローカル サーバーがディスクからファイルの変更されたコピーを提供しました。</span><span class="sxs-lookup"><span data-stu-id="6b07e-175">And then, when you refreshed the page, your local server served the modified copy of the file from disk.</span></span>  
    
## <a name="step-3-save-an-html-change-to-disk"></a><span data-ttu-id="6b07e-176">手順 3: HTML の変更をディスクに保存する</span><span class="sxs-lookup"><span data-stu-id="6b07e-176">Step 3: Save an HTML change to disk</span></span>  

### <a name="change-html-from-the-elements-panel"></a><span data-ttu-id="6b07e-177">要素パネルから HTML を変更する</span><span class="sxs-lookup"><span data-stu-id="6b07e-177">Change HTML from the Elements Panel</span></span>  

<span data-ttu-id="6b07e-178">要素パネルから html に変更を加える場合がありますが、DOM ツリーへの変更はディスクに保存されません。現在のブラウザー セッションにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="6b07e-178">You may make changes to the html from the Element Panel, but your changes to the DOM tree are not saved to disk and only effect the current browser session.</span></span>  

<span data-ttu-id="6b07e-179">DOM ツリーは html ではありません。</span><span class="sxs-lookup"><span data-stu-id="6b07e-179">The DOM tree is not html.</span></span>  

<!--### Try changing HTML from the Elements panel  

> [!WARNING]
> The workflow that you are about to try does not work.  You are trying it now so that you do not waste time later trying to figure out why it is not working.  

1.  Choose the **Elements** tool.  
1.  Choose and edit the text content of the `h1` element, which says `Workspaces Demo`, and replace it with `I ❤️  Cake`.  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-change-h1.msft.png" alt-text="Attempt to change html from the DOM Tree of the Elements panel" lightbox="../media/workspaces-workspaces-demo-change-h1.msft.png":::
       Attempt to change html from the DOM Tree of the **Elements** tool  
    :::image-end:::  
    
1.  Open `~/Desktop/app/index.html` in a text editor.  The change that you just made does not appear.  
1.  Refresh the page.  The page reverts to the original title.  
    
#### Optional: Why it is not working  

> [!NOTE]
> This section describes why the workflow from [Try changing html from the Elements panel](#try-changing-html-from-the-elements-panel) does not work.  You should skip this section if you do not care why.  

*   The tree of nodes that are displayed on the **Elements** tool represents the [DOM][MDNWebAPIsDOM] of the page.  
*   To display a page, a browser fetches html over the network, parses the html, and then converts it into a tree of DOM nodes.  
*   If the page has any JavaScript, that JavaScript may add, delete, or change DOM nodes.  CSS may change the DOM, too, using the [`content`][MDNCSSContent] property.  
*   The browser eventually uses the DOM to determine what content it should present to browser users.  
*   Therefore, the final state of the webpage displayed for users may be very different from the html that the browser fetched.  
*   This makes it difficult for DevTools to resolve where a change made in the **Elements** tool should be saved, because the DOM is affected by HTML, JavaScript, and CSS.  

In short, the **DOM Tree** `!==` HTML.  
-->  

### <a name="change-html-from-the-sources-panel"></a><span data-ttu-id="6b07e-180">[ソース] パネルから HTML を変更する</span><span class="sxs-lookup"><span data-stu-id="6b07e-180">Change HTML from the Sources panel</span></span>  

<span data-ttu-id="6b07e-181">ページの html に対する変更を保存する場合は、[ソース] パネルを **使用して変更を行** います。</span><span class="sxs-lookup"><span data-stu-id="6b07e-181">If you want to save a change to the html of the page, do it using the **Sources** panel.</span></span>  

1.  <span data-ttu-id="6b07e-182">[ソース] **ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="6b07e-182">Choose the **Sources** tool.</span></span>  
1.  <span data-ttu-id="6b07e-183">[ページ] **パネルを選択** します。</span><span class="sxs-lookup"><span data-stu-id="6b07e-183">Choose the **Page** panel.</span></span>  
1.  <span data-ttu-id="6b07e-184">( **インデックス) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6b07e-184">Choose **(index)**.</span></span>  <span data-ttu-id="6b07e-185">ページの HTML が開きます。</span><span class="sxs-lookup"><span data-stu-id="6b07e-185">The HTML for the page opens.</span></span>  
1.  <span data-ttu-id="6b07e-186">に `<h1>Workspaces Demo</h1>` 置き換える `<h1>I ❤️  Cake</h1>` 。</span><span class="sxs-lookup"><span data-stu-id="6b07e-186">Replace `<h1>Workspaces Demo</h1>` with `<h1>I ❤️  Cake</h1>`.</span></span>  <span data-ttu-id="6b07e-187">次の図を確認します。</span><span class="sxs-lookup"><span data-stu-id="6b07e-187">Review the following figure.</span></span>  
1.  <span data-ttu-id="6b07e-188">`Control` + `S` \(Windows, Linux\) または `Command` + `S` \(macOS\) を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="6b07e-188">Select `Control`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save the change.</span></span>  
1.  <span data-ttu-id="6b07e-189">ページを最新の情報に更新してください。</span><span class="sxs-lookup"><span data-stu-id="6b07e-189">Refresh the page.</span></span>  <span data-ttu-id="6b07e-190">要素 `<h1>` は引き続き新しいテキストを表示しています。</span><span class="sxs-lookup"><span data-stu-id="6b07e-190">The `<h1>` element is still displaying the new text.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-page-h1.msft.png" alt-text="[ソース] パネルから HTML を変更する" lightbox="../media/workspaces-workspaces-demo-sources-page-h1.msft.png":::
       <span data-ttu-id="6b07e-192">[ソース] パネルから HTML **を変更** する</span><span class="sxs-lookup"><span data-stu-id="6b07e-192">Change HTML from the **Sources** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6b07e-193">を `~/Desktop/app/index.html` 開きます。</span><span class="sxs-lookup"><span data-stu-id="6b07e-193">Open `~/Desktop/app/index.html`.</span></span>  <span data-ttu-id="6b07e-194">要素 `<h1>` には、新しいテキストが含まれる。</span><span class="sxs-lookup"><span data-stu-id="6b07e-194">The `<h1>` element contains the new text.</span></span>  
    
## <a name="step-4-save-a-javascript-change-to-disk"></a><span data-ttu-id="6b07e-195">手順 4: JavaScript の変更をディスクに保存する</span><span class="sxs-lookup"><span data-stu-id="6b07e-195">Step 4: Save a JavaScript change to disk</span></span>  

<span data-ttu-id="6b07e-196">[ **ソース]** パネルは、JavaScript に変更を加える場所にもなっています。</span><span class="sxs-lookup"><span data-stu-id="6b07e-196">The **Sources** panel is also the place to make changes to JavaScript.</span></span>  <span data-ttu-id="6b07e-197">ただし、サイトに変更を加えたときに、[**要素**] ツールや[コンソール] パネルなどの他のパネルにアクセスする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="6b07e-197">But sometimes you need to access other panels, such as the **Elements** tool or the **Console** panel, while making changes to your site.</span></span>  <span data-ttu-id="6b07e-198">ソース パネルを他のパネル **と** 一緒に開く方法があります。</span><span class="sxs-lookup"><span data-stu-id="6b07e-198">There is a way to have the **Sources** panel open alongside other panels.</span></span>  

1.  <span data-ttu-id="6b07e-199">[要素] **ツールを選択** します。</span><span class="sxs-lookup"><span data-stu-id="6b07e-199">Choose the **Elements** tool.</span></span>  
1.  <span data-ttu-id="6b07e-200">`Control` + `Shift` + `P` \(Windows, Linux\) または `Command` + `Shift` + `P` \(macOS\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="6b07e-200">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  <span data-ttu-id="6b07e-201">[ **コマンド] メニューが** 開きます。</span><span class="sxs-lookup"><span data-stu-id="6b07e-201">The **Command Menu** opens.</span></span>  
1.  <span data-ttu-id="6b07e-202">[入力 `QS` ] をクリックし、[ **クイック ソースの表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6b07e-202">Type `QS`, then choose **Show Quick Source**.</span></span>  <span data-ttu-id="6b07e-203">DevTools ウィンドウの下部にクイック ソース **パネルが表示** されます。</span><span class="sxs-lookup"><span data-stu-id="6b07e-203">At the bottom of your DevTools window there is now a **Quick Source** panel.</span></span>  <span data-ttu-id="6b07e-204">パネルには、ソース パネルで編集した最後のファイルであるコンテンツ `index.html` **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="6b07e-204">The panel is displaying the contents of `index.html`, which is the last file you edited in the **Sources** panel.</span></span>  <span data-ttu-id="6b07e-205">[**クイック ソース]** パネルには、[ソース] パネルからエディターが表示されます。これにより、他のパネルを開いている間にファイルを編集できます。</span><span class="sxs-lookup"><span data-stu-id="6b07e-205">The **Quick Source** panel gives you the editor from the **Sources** panel, so that you are able to edit files while having other panels open.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png" alt-text="コマンド メニューを使用してクイック ソース パネルを開く" lightbox="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png":::
       <span data-ttu-id="6b07e-207">コマンド メニュー **を使用してクイック ソース** パネル **を開く**</span><span class="sxs-lookup"><span data-stu-id="6b07e-207">Open the **Quick Source** panel using **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6b07e-208">`Control` + `P` \(Windows, Linux\) または `Command` + `P` \(macOS\) を選択して、[ファイルを開く]**ダイアログを開**きます。</span><span class="sxs-lookup"><span data-stu-id="6b07e-208">Select `Control`+`P` \(Windows, Linux\) or `Command`+`P` \(macOS\) to open the **Open File** dialog.</span></span>  <span data-ttu-id="6b07e-209">次の図を確認します。</span><span class="sxs-lookup"><span data-stu-id="6b07e-209">Review the following figure.</span></span>  
1.  <span data-ttu-id="6b07e-210">[入力 `script` ] をクリックし、[アプリ/script.js] をscript.js。 </span><span class="sxs-lookup"><span data-stu-id="6b07e-210">Type `script`, then choose **app/script.js**.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-script.msft.png" alt-text="[ファイルscript.jsダイアログを使用してファイルを開く" lightbox="../media/workspaces-workspaces-demo-search-script.msft.png":::
       <span data-ttu-id="6b07e-212">[ファイル `script.js` を開く] **ダイアログを使用して開** く</span><span class="sxs-lookup"><span data-stu-id="6b07e-212">Open `script.js` using the **Open File** dialog</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="6b07e-213">デモ `Save Changes To Disk With Workspaces` のリンクは、定期的にスタイル設定されます。</span><span class="sxs-lookup"><span data-stu-id="6b07e-213">The `Save Changes To Disk With Workspaces` link in the demo is styled regularly.</span></span>  
    
1.  <span data-ttu-id="6b07e-214">[クイック ソース] パネルを 使用して、script.jsコード**を下部に追加**します。</span><span class="sxs-lookup"><span data-stu-id="6b07e-214">Add the following code to the bottom of **script.js** using the **Quick Source** panel.</span></span>  
    
    ```javascript
    console.log('greetings from script.js');
    document.querySelector('a').style = 'font-style:italic';
    ```  
    
1.  <span data-ttu-id="6b07e-215">`Control` + `S` \(Windows, Linux\) または `Command` + `S` \(macOS\) を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="6b07e-215">Select `Control`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save the change.</span></span>  
1.  <span data-ttu-id="6b07e-216">ページを最新の情報に更新してください。</span><span class="sxs-lookup"><span data-stu-id="6b07e-216">Refresh the page.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="6b07e-217">ページ上のリンクが、現在は italicized です。</span><span class="sxs-lookup"><span data-stu-id="6b07e-217">The link on the page is now italicized.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png" alt-text="ページ上のリンクが italicized に変更されました" lightbox="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png":::
       <span data-ttu-id="6b07e-219">ページ上のリンクが italicized に変更されました</span><span class="sxs-lookup"><span data-stu-id="6b07e-219">The link on the page is now italicized</span></span>  
    :::image-end:::  
    
## <a name="next-steps"></a><span data-ttu-id="6b07e-220">次の手順</span><span class="sxs-lookup"><span data-stu-id="6b07e-220">Next steps</span></span>  

<span data-ttu-id="6b07e-221">このチュートリアルで学んだことを使用して、独自のプロジェクトで Workspaces を設定します。</span><span class="sxs-lookup"><span data-stu-id="6b07e-221">Use what you have learned in this tutorial to set up Workspaces in your own project.</span></span>  <!-- If you run into any issues or are able to get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  

<!--  
If you have more feedback on the topics or anything else, please use any of the channels below:  

*   [Mailing List][AlphabetGroupsAlphabetBrowserDevTools]  
*   [Twitter][TwitterAlphabetBrowserDevTools]  -->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="6b07e-222">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="6b07e-222">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsCssIndex]: ../css/index.md "CSS ファイルの表示と変更の|Microsoft Docs"  

<!--[LocalOverrides]: ../whats-new/2018/01/devtools#overrides -->  

<!--[AlphabetGroupsAlphabetBrowserDevTools]: https://groups.alphabet.com/forum/#!forum/alphabet-browser-developer-tools "Alphabet Browser DevTools - Alphabet Groups"  -->  

[GlitchWorkspacesDemo]: https://glitch.com/edit/#!/microsoft-edge-chromium-devtools?path=workspaces-demo/index.html:1:0 "Workspaces のデモ ファイル|Glitch"  

[MDNCSSContent]: https://developer.mozilla.org/docs/Web/CSS/content "コンテンツ - CSS: カスケード スタイル シート |MDN"  
[MDNWebGettingStarted]: https://developer.mozilla.org/docs/Learn/Getting_started_with_the_web "Web アプリケーションの|MDN"  
[MDNSimpleLocalHTTPServer]: https://developer.mozilla.org/docs/Learn/Common_questions/set_up_a_local_testing_server#Running_a_simple_local_HTTP_server "単純なローカル HTTP サーバー を実行|MDN"  
[MDNWebAPIsDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM の概要 - Web API |MDN"  

<!--[StackOverflowAlphabetBrowserDevTools]: https://stackoverflow.com/questions/ask?tags=alphabet-browser-devtools "Alphabet Browser DevTools - Stack Overflow"  -->

[TreehouseBlogSourceMaps]: https://blog.teamtreehouse.com/introduction-source-maps "ソース マップの概要|Treehouse ブログ"  

<!-- [TwitterAlphabetBrowserDevTools]: https://twitter.com/alphabetbrowserdevtools "Alphabet Browser DevTools \(@AlphabetBrowserDevTools\) | Twitter"  -->

[WikiPortURLs]: https://en.wikipedia.org/wiki/Port_(computer_networking)#Use_in_URLs "Port \(computer networking\) - Wikipedia"  

> [!NOTE]
> <span data-ttu-id="6b07e-231">このページの一部は、 [Google によっ て作成および共有された][GoogleSitePolicies]作業に基づく変更で、「[Creative Commons Attribution 4.0 International License][CCA4IL]」で記載されている条項に従って使用されます。</span><span class="sxs-lookup"><span data-stu-id="6b07e-231">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="6b07e-232">元のページは [ここ](https://developers.google.com/web/tools/chrome-devtools/workspaces/index) にあり、 [Kayce Basques][KayceBasques] \(Chrome DevTools \& Lighthouse\ のテクニカル ライター) が作成しました。</span><span class="sxs-lookup"><span data-stu-id="6b07e-232">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/workspaces/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons ライセンス][CCby4Image]][CCA4IL]  
<span data-ttu-id="6b07e-234">この著作物は、[Creative Commons Attribution 4.0 International License][CCA4IL] に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="6b07e-234">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
