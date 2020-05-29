---
description: Chromium Extension の概要と、オプション、コンテンツの挿入、バックグラウンドスクリプト、ストレージなどを含む完全な画像表示拡張機能を段階的に構築する方法について説明します。
title: Microsoft Edge (Chromium) の拡張機能の概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/05/2019
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、web 開発、html、css、javascript、開発者、拡張機能
ms.openlocfilehash: a271514f39ed8bbe379116c33e23c973d3eb6adb
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "10569576"
---
# <span data-ttu-id="4d4c1-104">Microsoft Edge \ (Chromium \) Extensions の概要</span><span class="sxs-lookup"><span data-stu-id="4d4c1-104">Getting Started With Microsoft Edge \(Chromium\) Extensions</span></span>  

<span data-ttu-id="4d4c1-105">最初の拡張機能の構築に直接ジャンプする場合は、「day Extension の NASA 写真の作成」のパート1に進みます。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-105">If you want to jump directly into building your first Extension, go to part 1 of building a NASA picture of the day Extension.</span></span>  

<span data-ttu-id="4d4c1-106">拡張機能の概念とアーキテクチャについて詳しく理解していない場合は、読み進めて、すべての拡張機能について学習してください。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-106">If you are not familiar with the Extension concepts and architecture, continue reading, and learn all about what Extensions are.</span></span>  <span data-ttu-id="4d4c1-107">この情報は、背後にある動機とアーキテクチャを理解しているため、より簡単に拡張機能を構築するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-107">This information helps you build Extensions much easier since you understand the motivations and architecture behind them.</span></span>  

## <span data-ttu-id="4d4c1-108">日の内線番号の NASA 画像を作成する</span><span class="sxs-lookup"><span data-stu-id="4d4c1-108">Build a NASA picture of the day Extension</span></span>  

<span data-ttu-id="4d4c1-109">各セクションには、完了した拡張ソースインストールパッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-109">Each section has the completed Extension source installation package referenced in it.</span></span>  

*   [<span data-ttu-id="4d4c1-110">その日の NASA の絵を飛び出すシンプルな拡張機能を構築する</span><span class="sxs-lookup"><span data-stu-id="4d4c1-110">Build a simple Extension that pops up NASA picture of the day</span></span>](part1-simple-extension.md)  
    *   <span data-ttu-id="4d4c1-111">マニフェストの作成</span><span class="sxs-lookup"><span data-stu-id="4d4c1-111">Creating a Manifest</span></span>  
    *   <span data-ttu-id="4d4c1-112">拡張機能のアイコンを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4d4c1-112">Assign Extension icons</span></span>  
    *   <span data-ttu-id="4d4c1-113">ポップアップウィンドウの表示</span><span class="sxs-lookup"><span data-stu-id="4d4c1-113">Displaying a Pop-up Window</span></span>  
    *   <span data-ttu-id="4d4c1-114">ブラウザーで拡張機能をローカルで実行する (サイドローディング \)</span><span class="sxs-lookup"><span data-stu-id="4d4c1-114">Run your Extension locally in your browser \(side-loading\)</span></span>  

*   [<span data-ttu-id="4d4c1-115">ページ本文タグの下に、NASA 図を動的に挿入する</span><span class="sxs-lookup"><span data-stu-id="4d4c1-115">Dynamically insert NASA picture below the page body tag</span></span>](part2-content-scripts.md)  
    *   <span data-ttu-id="4d4c1-116">動的コンテンツスクリプトを挿入する JavaScript を作成する</span><span class="sxs-lookup"><span data-stu-id="4d4c1-116">Create JavaScript that inserts dynamic content script</span></span>  
    *   <span data-ttu-id="4d4c1-117">コンテンツスクリプトを取得するページをマニフェストで定義する</span><span class="sxs-lookup"><span data-stu-id="4d4c1-117">Define in manifest which pages get content script</span></span>  
    *   <span data-ttu-id="4d4c1-118">コンテンツスクリプトを宣言して挿入する</span><span class="sxs-lookup"><span data-stu-id="4d4c1-118">Inject content script declaratively</span></span>  
    *   <span data-ttu-id="4d4c1-119">ポップアップのボタンを追加してコンテンツスクリプトにメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="4d4c1-119">Add a Button on Pop-up to send a message to content script</span></span>  
    *   <span data-ttu-id="4d4c1-120">コンテンツスクリプト内でメッセージを受信する</span><span class="sxs-lookup"><span data-stu-id="4d4c1-120">Receive a message inside a content script</span></span>  

## <span data-ttu-id="4d4c1-121">拡張子が導入される前のブラウザーについて</span><span class="sxs-lookup"><span data-stu-id="4d4c1-121">Understanding the browser before Extensions are introduced</span></span>  

### <span data-ttu-id="4d4c1-122">各ブラウザータブは、他のすべてのタブから分離されます。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-122">Each browser tab is isolated from every other tab</span></span>  

<span data-ttu-id="4d4c1-123">Microsoft Edge \ (Chromium \) の拡張機能について理解するには、最初に、Microsoft Edge のような、複数のタブブラウザーを完全に理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-123">To understand what a Microsoft Edge \(Chromium\) Extension is, we first need to fully understand what a multi tab browser, like Microsoft Edge does primarily.</span></span>  <span data-ttu-id="4d4c1-124">最初に、ブラウザーの各タブは、他のブラウザーのタブ \ (またはスレッド \) から効果的に分離される個々のスレッドで実行されます。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-124">To start, each browser tab runs in an individual thread that effectively isolates it from other browser tabs \(or threads\).</span></span>  

![[ブラウザー] タブごとに1つのスレッド](media/index-image1-browsertabs.png)  

### <span data-ttu-id="4d4c1-126">各タブは1つの GET 要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-126">Each tab handles one GET request</span></span>  

<span data-ttu-id="4d4c1-127">各タブは、基本的には URL (uniform resource locator とも呼ばれます) を使って、通常は HTML ドキュメントである1つのデータストリームを取得します。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-127">Each tab essentially use the URL \(also known as the uniform resource locator\) to get a single stream of data which is typically an HTML document.</span></span>  <span data-ttu-id="4d4c1-128">この1つのストリーム \ (またはページ \) には、(JavaScript にはタグ、画像参照、CSS 参照などのような) 命令が含まれていることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-128">That single stream \(or page\), often includes instructions \(like JavaScript include tags, image references, CSS references, and more\).</span></span>  <span data-ttu-id="4d4c1-129">最終的には、必要なすべてのリソースが1つのタブページにダウンロードされ、通常は [ブラウザー] タブに表示される視覚エフェクトが完全に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-129">Ultimately, all the resources needed are downloaded to that one tab page and typically a visualization appears which we see in the browser tab completely rendered.</span></span>  

### <span data-ttu-id="4d4c1-130">各タブからのすべての通信がリモートサーバーになります。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-130">All communication from each tab is to remote servers</span></span>  

<span data-ttu-id="4d4c1-131">各タブが分離環境で実行されることを理解していると、これらのタブは互いに独立していますが、より多くのインターネットを利用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-131">Understanding that each tab runs in an isolated environment means that these tabs are isolated from each other, but not the greater internet.</span></span>  <span data-ttu-id="4d4c1-132">通常、これらのタブはプログラミング言語である JavaScript を実行しているため、ブラウザータブの一番上の URL バーに入力された最初の GET 要求の元のサーバーとして考える必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-132">Typically, these tabs, running JavaScript as there programming language, communicate back to the server, that should be thought of as the originating server for that first GET request that was entered into the URL bar at the top of the browser tab.</span></span>  

## <span data-ttu-id="4d4c1-133">拡張モデルによって、すべての要素が逆になります。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-133">The Extension model turns everything upside down</span></span>  

<span data-ttu-id="4d4c1-134">タブページと同様に、拡張機能は個々のスレッドで実行されます。これは、すべてのタブページスレッドから完全に分離されています。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-134">An Extension, just like tab pages, runs in a individual thread which is completely isolated from all tab page threads that are discussed.</span></span>  <span data-ttu-id="4d4c1-135">通常、リモートサーバーに対して1つの GET 要求を発行して、そのデータの視覚エフェクトをブラウザーで表示すると、それ以外の場合は、ブラウザーのタブから確立されたインターネット接続の反対側にあるサーバーとなります。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-135">Unlike the tabs whose job is to typically issue a single GET request to a remote server, then display a visualization of that data in the browser, the Extension, on the other hand is the server, that previously resided on the other end of the internet connection made from a browser tab.</span></span>  

![拡張モデルによってサーバーモデルが上下反転する](media/index-image3-upsidedown.png)  

<span data-ttu-id="4d4c1-137">これは、理解することが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-137">This is really important to understand.</span></span>  <span data-ttu-id="4d4c1-138">拡張機能を作成してブラウザーにインストールすると、ブラウザー内に存在し、そのブラウザーで実行されているすべてのタブページから分離されているスタンドアロンの web サーバーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-138">Once you create an Extension, and install it in your browser, you've created a standalone web server that is living and breathing inside of your browser but still isolated from every tab page running on that browser.</span></span>  

### <span data-ttu-id="4d4c1-139">拡張機能 web サーバーバンドル</span><span class="sxs-lookup"><span data-stu-id="4d4c1-139">The Extension web server bundle</span></span>  

<span data-ttu-id="4d4c1-140">拡張機能とは</span><span class="sxs-lookup"><span data-stu-id="4d4c1-140">So what is an Extension?</span></span> <span data-ttu-id="4d4c1-141">Web リソースのバンドル \ (または zip ファイルとも呼ばれます) は、web 開発者が web サーバーに発行したものとは異なるものです。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-141">It is a bundle \(or referred to as a zip file\) of web resources that are no different than what a web developer publishes to a web server.</span></span>  

<span data-ttu-id="4d4c1-142">この zip ファイルには、HTML、CSS、JavaScript、画像、および web ページを作成するために必要なすべてのアセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-142">That zip file includes HTML, CSS, JavaScript, images and all the necessary assets to make a web page.</span></span>  <span data-ttu-id="4d4c1-143">ただし、この zip ファイルのルートに必要な1つの追加ファイルと、そのファイルには名前が付いてい `manifest.json` ます。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-143">There is however, one extra file that is required in the root of this zip file, and that file is named `manifest.json`.</span></span>  <span data-ttu-id="4d4c1-144">これは拡張機能の青写真であり、拡張機能のバージョン、タイトル、実行する必要がある権限、その他の機能を含みます。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-144">It is the blueprint for your Extension that includes things like what is the version of your Extension, what is the title, what privileges does it need to run and lots more.</span></span>  

![Zip 形式のファイルの表示](media/index-image5-filemanager-view.png)  

### <span data-ttu-id="4d4c1-146">拡張機能サーバーの起動</span><span class="sxs-lookup"><span data-stu-id="4d4c1-146">Launching the Extension server</span></span>  

<span data-ttu-id="4d4c1-147">Web サーバーに展開すると、その web サーバー (Apache、IIS、NGINX など) が web バンドルに含まれているかどうかに関係ありません。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-147">When you deploy to a web server, that web server, whether it is Apache, IIS, NGINX or any other, contains your web bundle.</span></span>  <span data-ttu-id="4d4c1-148">ブラウザーがサーバー上の URL に移動すると、 `index.html` web サーバー上のファイルがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-148">When a browser navigates to a URL on a server, the `index.html` file on the web server is downloaded.</span></span>  <span data-ttu-id="4d4c1-149">ブラウザーでは、証明書、構成ファイルなどを使用しています。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-149">The browser navigated using certificates, configuration files, and more.</span></span>  <span data-ttu-id="4d4c1-150">`index.html`Web サーバー上の特定の場所に保存されているファイル。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-150">The `index.html` file stored at some special location on the web server.</span></span>   <span data-ttu-id="4d4c1-151">拡張機能について教えてください。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-151">How does your Extension do the same thing?</span></span>  <span data-ttu-id="4d4c1-152">特に、使用しているブラウザーのタブページは、この zip ファイル (拡張子 \) にアクセスできますか?</span><span class="sxs-lookup"><span data-stu-id="4d4c1-152">Particularly, how is the tab pages of your browser able to get to this zip file \(your Extension\)?</span></span>  <span data-ttu-id="4d4c1-153">これが、拡張ランタイムによって実行される操作です。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-153">That is what the Extension runtime does for you.</span></span>  

<span data-ttu-id="4d4c1-154">拡張子は、名前の中の URL \ (uniform resource locator) からのすべてのファイルを提供し `extension://{some-long-unique-identifier}/index.html` ます。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-154">The extension serves the files all from the URL \(uniform resource locator\) at the name `extension://{some-long-unique-identifier}/index.html`.</span></span>  <span data-ttu-id="4d4c1-155">角かっこで囲んだ名前は、インストールした `{some-long-unique-identifier}` 拡張機能に割り当てられている一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-155">The name I put in brackets, `{some-long-unique-identifier}` is a unique identifier assigned to the Extension that you installed.</span></span>  <span data-ttu-id="4d4c1-156">つまり、10個の一意の拡張機能がブラウザーにインストールされている場合、各拡張機能には、ブラウザー内にインストールされている zip ファイル \ (または拡張バンドル \) を指す一意の識別子があります。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-156">That means, if you have 10 unique Extensions installed on your browser, each Extension has a unique identifier that points at the zip file \(or Extension bundle\) installed inside your browser.</span></span>  

<!--![Unique URLS for Extensions](media/index-image4-uniqueurls.png)  -->  

<!--todo: add image for unique URLs  -->  

### <span data-ttu-id="4d4c1-157">拡張機能は、タブとブラウザーのツールバーを使って管理および通信を行う</span><span class="sxs-lookup"><span data-stu-id="4d4c1-157">Extensions manage and communicate with tabs and the browser toolbar</span></span>  

<span data-ttu-id="4d4c1-158">拡張機能はブラウザーのツールバーで動作します。各ページは、すべてのタブページの DOM を操作するだけでなく安全な方法で管理できます。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-158">Extensions interact with the browsers toolbar, each is able to manage all the other running tab pages in a safe way, as well as manipulating the DOM of all those tab pages.</span></span>  <span data-ttu-id="4d4c1-159">Chromium browser に組み込まれているメッセージ API は、拡張機能とタブページ間の通信を可能にして、これを適切に行うことができるようにするものです。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-159">Built into the Chromium browser is a message API that allows for communications between the Extensions and the tab pages to allow this to happen gracefully.</span></span>  <span data-ttu-id="4d4c1-160">この API は、Extensions API とも呼ばれます。これには、通知管理、ストレージ管理など、多くの機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-160">This API, also known as the Extensions API gives a lots of capabilities including notification management, storage management, and much more.</span></span>  

<span data-ttu-id="4d4c1-161">Web サーバーの場合と同様に、拡張機能は、ブラウザーが実行されているときに、常に (通知を待機している状態のまま) 実行することができます。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-161">Just like web servers, Extensions are able to continually run \(or sleep waiting for notifications\) all the time that the browser is running.</span></span>  <span data-ttu-id="4d4c1-162">ブラウザーのオーケストレータとして拡張機能を考えることができます。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-162">You may think of an Extension as an orchestrator for the browser.</span></span>  <span data-ttu-id="4d4c1-163">この場合も、拡張子はタブページから完全に分離されますが、Extensions API、および拡張機能に割り当てられているオプトインアクセス許可によって、ブラウザーで実行されているすべてのタブページを実質制御することができます。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-163">Again, the Extension runs completely isolated from the tab pages, but through the Extensions API, and opt-in permissions granted to the Extension, each Extension is able to virtually control any and all tab pages running in the browser.</span></span>  

### <span data-ttu-id="4d4c1-164">拡張機能は、インストール時のセキュリティモデルでオプトインを提供します。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-164">Extensions provide an opt-in at install time security model</span></span>  

<span data-ttu-id="4d4c1-165">拡張子を指定すると、ファイル内の宣言によって、 `manifest.json` 拡張機能をインストールして、異なるレベルの権限を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-165">Each Extension, through a declaration in the `manifest.json` file allows the person installing the Extension to give it different levels of authority.</span></span>  <span data-ttu-id="4d4c1-166">この機関は、拡張機能がユーザーによってインストールされた場合に、拡張機能で任意の情報を抽出し、そのデータを拡張機能で処理できるようにします。</span><span class="sxs-lookup"><span data-stu-id="4d4c1-166">This authority allows Extensions, when installed by a user, to opt-in so that the Extension is able to extract any information, and process that data through the Extension.</span></span>  

<!-- image links -->  

<!-- links -->  
