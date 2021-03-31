---
description: このガイドでは、Windows で段階的な Web アプリを構築するための PWA の基本とツールの概要について説明します。
title: 段階的な Web アプリの使用を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: 段階的な Web アプリ, PWA, Edge, Windows, PWABuilder, Web マニフェスト, サービス ワーカー, プッシュ
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 9a76399616ab7645b82242b94dd4757b73b37f60
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234348"
---
# <span data-ttu-id="dffb8-104">段階的な Web アプリの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="dffb8-104">Get started with Progressive Web Apps</span></span>  

<span data-ttu-id="dffb8-105">段階的な Web アプリ \(PWA\) は[][WikiProgressiveEnhancement]、ホーム画面から起動するインストール、オフライン サポート、プッシュ通知など、サポート プラットフォームやブラウザー エンジン上のネイティブ アプリのような機能によって段階的に拡張される単純な Web アプリです。</span><span class="sxs-lookup"><span data-stu-id="dffb8-105">Progressive Web Apps \(PWAs\) are simply web apps that are [progressively enhanced][WikiProgressiveEnhancement] with native app-like features on supporting platforms and browser engines, such as launch-from-homescreen installation, offline support, and push notifications.</span></span>  <span data-ttu-id="dffb8-106">Microsoft Edge \(EdgeHTML\) エンジンを搭載した Windows 10 では、PAS は、ユニバーサル [Windows][WindowsUwpGetStartedWhat] プラットフォーム アプリとしてブラウザー ウィンドウとは別に実行できるという利点があります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-106">On Windows 10 with the Microsoft Edge \(EdgeHTML\) engine, PWAs enjoy the added advantage of running independently of the browser window as [Universal Windows Platform][WindowsUwpGetStartedWhat] apps.</span></span>  

<span data-ttu-id="dffb8-107">このガイドでは、Microsoft Visual Studio と一部の PWA Builder ユーティリティを使用して簡単な Web アプリを PWA として構築することで、PWA の基本の概要を `localhost` 説明します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-107">This guide gives you an overview of PWA basics by building a simple `localhost` web app as a PWA using Microsoft Visual Studio and some PWA Builder utilities.</span></span>  <span data-ttu-id="dffb8-108">完成した製品は、PAS をサポートするブラウザーでも同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-108">The finished product works similarly across any browser that supports PWAs.</span></span>  

> [!TIP]
> <span data-ttu-id="dffb8-109">既存のサイトを PWA に変換し、Windows 10 および他のアプリ プラットフォーム用にパッケージ化する簡単な方法については [、PWA Builder を確認してください][PwaBuilder]。</span><span class="sxs-lookup"><span data-stu-id="dffb8-109">For a quick way to convert an existing site to a PWA and package it for Windows 10 and other app platforms, review [PWA Builder][PwaBuilder].</span></span>  

## <span data-ttu-id="dffb8-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="dffb8-110">Prerequisites</span></span>  

<span data-ttu-id="dffb8-111">WEB 開発 IDE を使用して PAS を構築できます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-111">You may build PWAs with any web development IDE.</span></span>  <span data-ttu-id="dffb8-112">以下は、Windows 開発者エコシステムでの PWA ツール サポートについて説明する、このガイドの前提条件に限定されます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-112">The following are only prerequisites for this guide, which walks you through PWA tooling support in the Windows developer ecosystem.</span></span>  

*   <span data-ttu-id="dffb8-113">コミュニティ [2017][VisualStudioDownloads]の \(free\) Visual Studioダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="dffb8-113">Download the \(free\) [Visual Studio Community 2017][VisualStudioDownloads].</span></span>  <span data-ttu-id="dffb8-114">Professional エディション、Enterprise エディション、Preview エディション [を使用][VisualStudioPreview] する場合があります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-114">You may also use the Professional, Enterprise, or [Preview][VisualStudioPreview] editions.</span></span>  <span data-ttu-id="dffb8-115">新しいVisual Studioから、次のワークロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-115">From the Visual Studio Installer, choose the following Workloads.</span></span>  
    
    *   **<span data-ttu-id="dffb8-116">ユニバーサル Windows プラットフォーム開発</span><span class="sxs-lookup"><span data-stu-id="dffb8-116">Universal Windows Platform development</span></span>**  
    *   **<span data-ttu-id="dffb8-117">Node.js開発</span><span class="sxs-lookup"><span data-stu-id="dffb8-117">Node.js development</span></span>**  

## <span data-ttu-id="dffb8-118">基本的な Web アプリをセットアップする</span><span class="sxs-lookup"><span data-stu-id="dffb8-118">Set up a basic web app</span></span>  

<span data-ttu-id="dffb8-119">簡単にするために、Visual StudioNode.js [ および Express][VisualStudioNodeJsTutorial] アプリ テンプレートを使用して、ページを提供する Web アプリ `localhost` を作成 `index.html` します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-119">For the sake of simplicity, use the Visual Studio [Node.js and Express app][VisualStudioNodeJsTutorial] template to create `localhost` web app that serves up an `index.html` page.</span></span>  <span data-ttu-id="dffb8-120">PWA として開発している魅力的でフル機能の Web アプリのプレースホルダーとして、これを想像してください。</span><span class="sxs-lookup"><span data-stu-id="dffb8-120">Imagine this as a placeholder for the compelling, full-featured web app that you are developing as a PWA.</span></span>  

1.  <span data-ttu-id="dffb8-121">新Visual Studioを起動し、新しいプロジェクトを開始します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-121">Launch Visual Studio, and start a new project.</span></span>  
    *   <span data-ttu-id="dffb8-122">**ファイル**  > **新規**  > **Project...**</span><span class="sxs-lookup"><span data-stu-id="dffb8-122">**File** > **New** > **Project...**</span></span>  
    *   `Ctrl`+`Shift`+`N`  
1.  <span data-ttu-id="dffb8-123">**[JavaScript] で、[** 基本] Node.js **Express 4 アプリケーション] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dffb8-123">Under **JavaScript**, select **Basic Node.js Express 4 Application**.</span></span>  <span data-ttu-id="dffb8-124">名前と場所を設定し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dffb8-124">Set the name and location and choose **OK**.</span></span>  
    
    ![新しいNode.js Express 4 プロジェクト テンプレートを選択Visual Studio][ImageVsNodejsExpressTemplate]  
    
1.  <span data-ttu-id="dffb8-126">新しいプロジェクトが読み込まれると、[**ビルド**\( \) ] と [ `Ctrl` + `Shift` + `B` **デバッグの開始**] \( `F5` \) を選択します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-126">Once your new project loads, choose **Build** \(`Ctrl`+`Shift`+`B`\) and **Start Debugging** \(`F5`\).</span></span>  <span data-ttu-id="dffb8-127">参照するときにファイル `index.html` が読み込まれるのを確認します `http://localhost:1337` 。</span><span class="sxs-lookup"><span data-stu-id="dffb8-127">Verify that your `index.html` file loads when you browse to `http://localhost:1337`.</span></span>  
    
    ![localhost での新しいサイトの実行][ImageVsNodejsExpressIndex]  

## <span data-ttu-id="dffb8-129">アプリを PWA に変換する</span><span class="sxs-lookup"><span data-stu-id="dffb8-129">Turn your app into a PWA</span></span>  

<span data-ttu-id="dffb8-130">次に、Web アプリの基本的な [PWA][PwaEdgehtmlIndexRequirements] 要件 *(Web アプリ*マニフェスト *、HTTPS、* サービス ワーカー) を *関連付ける必要があります*。</span><span class="sxs-lookup"><span data-stu-id="dffb8-130">Now it is time to wire up the basic [PWA requirements][PwaEdgehtmlIndexRequirements] for your web app: a *Web App Manifest*, *HTTPS* and *Service Workers*.</span></span>  

### <span data-ttu-id="dffb8-131">Web アプリ マニフェスト</span><span class="sxs-lookup"><span data-stu-id="dffb8-131">Web App Manifest</span></span>  

<span data-ttu-id="dffb8-132">[Web App マニフェストは][MDNWebAppManifest]、名前、作成者、エントリ ページの URL、1 つ以上のアイコンなど、アプリを記述する JSON メタデータ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="dffb8-132">A [Web App Manifest][MDNWebAppManifest] is a JSON metadata file describing your app, including the name, author, entry page URL, and one or more icons.</span></span>  <span data-ttu-id="dffb8-133">標準ベースのスキーマに[][W3cWebAppManifest]従うので、PWA をサポートするプラットフォーム、OS、デバイスの組み合わせにインストールする PWA の Web アプリ マニフェストを 1 つしか指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-133">Because it follows a [standards-based schema][W3cWebAppManifest], you must only supply a single web app manifest for the PWA that you are installing on any platform, OS, and device combination that supports PWAs.</span></span>  <span data-ttu-id="dffb8-134">Windows エコシステムでは、Web アプリ マニフェストが Bing Web インデクサーに対して、PWA が [Microsoft Store][PwaEdgehtmlMicrosoftStore]に自動的に含まれる候補として知らされます。この場合、Windows 10 アプリとしてアクティブな月次ユーザーは 7 億人近くに達する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-134">In the Windows ecosystem, your web app manifest signals to the Bing web indexer that your PWA is a candidate for automatic inclusion in the [Microsoft Store][PwaEdgehtmlMicrosoftStore], where it may reach nearly 700 million active monthly users as a Windows 10 app.</span></span>  

<span data-ttu-id="dffb8-135">既存のライブ サイトの場合は、PWA Builder を使用して Web アプリ マニフェスト [を生成できます][PwaBuilder]。</span><span class="sxs-lookup"><span data-stu-id="dffb8-135">If this were an existing live site, you may generate a web app manifest using [PWA Builder][PwaBuilder].</span></span>  <span data-ttu-id="dffb8-136">まだ未発行のプロジェクトである場合は、サンプル マニフェストをコピーします。</span><span class="sxs-lookup"><span data-stu-id="dffb8-136">Since it is still an unpublished project, copy a sample manifest.</span></span>  

1.  <span data-ttu-id="dffb8-137">ソリューション エクスプローラー Visual Studio、パブリック フォルダーを右クリックし**、[新しいファイル の追加**  >  **...]** を選択し、アイテム名 `manifest.json` として指定します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-137">In the Visual Studio *Solution Explorer*, right-click the *public* folder and select **Add** > **New File...**, specifying `manifest.json` as the item name.</span></span>  
1.  <span data-ttu-id="dffb8-138">ファイル内 `manifest.json` で、次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="dffb8-138">In the `manifest.json` file, copy the following code.</span></span>  

    ```json
    {
        "dir": "ltr",
        "lang": "en-us",
        "name": "My Sample PWA",
        "scope": "/",
        "display": "browser",
        "start_url": "https://PLACEHOLDER-FOR-PWA-URL",
        "short_name": "SamplePWA",
        "theme_color": "transparent",
        "description": "A sample PWA for testing purposes",
        "orientation": "any",
        "background_color": "transparent",
        "related_applications": [],
        "prefer_related_applications": false,
        "icons": []
    }
    ```  
    
    <span data-ttu-id="dffb8-139">実際の PWA では、次の手順では**、名前**、start_url、short_name、*説明*、アイコン*\(* アイコンは次の手順で説明します\) をカスタマイズします。 </span><span class="sxs-lookup"><span data-stu-id="dffb8-139">In a real PWA, the next step is to customize *name*, *start_url*, *short_name*, *description*, and *icons* \(icons are covered in the next step\).</span></span>  
    
    <span data-ttu-id="dffb8-140">さまざまなメンバー値と関連する目的の詳細については、Web アプリ マニフェストの [リファレンスを参照][MDNWebAppManifest] してください。</span><span class="sxs-lookup"><span data-stu-id="dffb8-140">To learn more about the different member values and associated purposes, see the [Web App Manifest][MDNWebAppManifest] reference.</span></span>  
    
1.  <span data-ttu-id="dffb8-141">次に、PWA Builder App Image Generator を使用して、空の配列に実際のイメージ `icons` パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-141">Next, fill in the empty `icons` array with actual image paths by using the PWA Builder App Image Generator.</span></span>  
    
    1.  <span data-ttu-id="dffb8-142">Web ブラウザーを使用して、このサンプル [512x512 PWA イメージをダウンロードします][ImagePwa]。</span><span class="sxs-lookup"><span data-stu-id="dffb8-142">Using a web browser, download this [sample 512x512 PWA image][ImagePwa].</span></span>  
    1.  <span data-ttu-id="dffb8-143">PWA Builder[アプリ][PwaBuilderAppImageGenerator]イメージ ジェネレーターに移動し、入力イメージとして保存したイメージを選択し、[ダウンロード] `pwa.png` ボタン**を選択**します。 </span><span class="sxs-lookup"><span data-stu-id="dffb8-143">Go to the PWA Builder [App Image Generator][PwaBuilderAppImageGenerator], and select the `pwa.png` image you just saved as the **Input Image** and then choose the **Download** button.</span></span>  
    1.  <span data-ttu-id="dffb8-144">**zip** ファイル **を開** いて展開します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-144">**Open** and **Extract** the zip file.</span></span>  
    1.  <span data-ttu-id="dffb8-145">ソリューション エクスプローラー Visual Studioフォルダーを右クリックし、エクスプローラーでフォルダー `public` **を開きます**。</span><span class="sxs-lookup"><span data-stu-id="dffb8-145">In the Visual Studio Solution Explorer, right-click the `public` folder and **Open Folder in File Explorer**.</span></span>  <span data-ttu-id="dffb8-146">という名前の **新しいフォルダーを** 作成します `images` 。</span><span class="sxs-lookup"><span data-stu-id="dffb8-146">Create a **New folder** named `images`.</span></span>  
    1.  <span data-ttu-id="dffb8-147">すべてのプラットフォーム フォルダー \( , など\) を展開した zip からフォルダーにコピーし、エクスプローラー `android` `chrome` `windows10` `images` ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-147">Copy all of the platform folders \(`android`, `chrome`, `windows10`, and so on\) from your extracted zip to the `images` folder and close the file explorer window.</span></span>  <span data-ttu-id="dffb8-148">Visual Studio プロジェクト \(ソリューション エクスプローラーでフォルダーを右クリックし、[既存のフォルダーの追加] を選択します\) にフォルダーを `images`   >   追加します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-148">Add the folders to your Visual Studio project \(in Solution Explorer, right-click `images` folder and select **Add** > **Existing folder...** for each of the folders\).</span></span>  
    1.  <span data-ttu-id="dffb8-149">抽出された zip ファイルの \(Visual Studio エディター\) を開き、配列をプロジェクト `icons.json` `"icons": [...]` `manifest.json` のファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="dffb8-149">Open \(with Visual Studio or any editor\) the `icons.json` file from the extracted zip and copy the `"icons": [...]` array into the `manifest.json` file of your project.</span></span>  

1.  <span data-ttu-id="dffb8-150">次に、Web アプリ マニフェストをアプリに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-150">Now you must associate your web app manifest with your app.</span></span>  <span data-ttu-id="dffb8-151">編集用に \(in folder\) ファイルを開き、スタイルシートのリンクの直後にこの行 `layout.pug` `views` を追加します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-151">Open the `layout.pug` file \(in `views` folder\) for editing, and add this line right after the stylesheet link.</span></span>  <span data-ttu-id="dffb8-152">\(\の簡単な Node [pug][PugAttributes] テンプレートの簡単な `<link rel='manifest' href='/manifest.json'>` 例です)。</span><span class="sxs-lookup"><span data-stu-id="dffb8-152">\(It is simply the Node [pug][PugAttributes] template shorthand for `<link rel='manifest' href='/manifest.json'>`\).</span></span>  
    
    ```html
    link(rel='manifest', href='/manifest.json')
    ```  
    
<span data-ttu-id="dffb8-153">これで、Web アプリはマニフェストとホーム画面対応のアプリ アイコンを提供する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="dffb8-153">With all that in place, your web app is now serving up a manifest and homescreen-ready app icons!</span></span>  <span data-ttu-id="dffb8-154">アプリ \( `F5` \) を実行し、マニフェストを読み込もうとします。</span><span class="sxs-lookup"><span data-stu-id="dffb8-154">Try running your app \(`F5`\) and loading up the manifest.</span></span>  

![localhost からの Web アプリ マニフェストの読み込み][ImageVsNodejsExpressManifest]  

<span data-ttu-id="dffb8-156">アイコンの 1 つ。</span><span class="sxs-lookup"><span data-stu-id="dffb8-156">And one of your icons.</span></span>  

![Square71x71Logo アプリロゴが localhost から読み込み中][ImageVsNodejsExpressIcon]  

<span data-ttu-id="dffb8-158">アプリをライブ (実際の \) で公開すると、Bing 検索エンジンはアプリを自動パッケージ化し、インストール可能な Windows 10 アプリとして `start_url` [Microsoft Store][PwaEdgehtmlMicrosoftStore] に提出する候補として識別されます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-158">If you publish the app live \(with an actual `start_url`\), the Bing search engine now identifies it as a candidate for [automatic packaging and submission to the Microsoft Store][PwaEdgehtmlMicrosoftStore] as an installable Windows 10 app.</span></span>  <span data-ttu-id="dffb8-159">ファイル上のmanifest.js、Bing がスキャンする段階的 [な Web アプリ][WindowsBlogsPwaEdge] の品質シグナル (以下の項目を含む) が含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-159">Ensure that your manifest.json file includes the [Quality signals for Progressive Web Apps][WindowsBlogsPwaEdge] for which Bing scans including the following items.</span></span>   

*   `name`  
*   `description`  
*   <span data-ttu-id="dffb8-160">少なくとも 1 つのアイコン 512px 正方形以上 \(アプリのスプラッシュ画面、ストア登録情報、タイル画像を自動生成するのに十分な解像度の画像ソースを確保するために\)。</span><span class="sxs-lookup"><span data-stu-id="dffb8-160">At least one icon 512px square or larger \(to ensure an image source of sufficient resolution for auto-generating the splash screen of your app, store listing, tile image, and so on\).</span></span>  

<span data-ttu-id="dffb8-161">さらに[、HTTPS、サービス](#https)[ワーカーを使用](#service-workers)し[、Microsoft Store ポリシーに準拠します][LegalWindowsAgrementsMicrosoftStorePolicies]。</span><span class="sxs-lookup"><span data-stu-id="dffb8-161">In addition, use [HTTPS](#https), [service workers](#service-workers), and comply with [Microsoft Store Policies][LegalWindowsAgrementsMicrosoftStorePolicies].</span></span>  

### <span data-ttu-id="dffb8-162">HTTPS</span><span class="sxs-lookup"><span data-stu-id="dffb8-162">HTTPS</span></span>  

<span data-ttu-id="dffb8-163">[サービス][MDNServiceWorkerApi]ワーカーや、サービス ワーカー \(キャッシュ、プッシュ、バックグラウンド同期 API[][MDNCache]など) と一[][MDNSyncManager]緒に動作する他の主要な PWA テクノロジは、セキュリティで保護された接続 (ライブ サイトまたはデバッグ用の[HTTPS)][WikiHttps]でのみ動作します。 [][MDNPushApi] `localhost`</span><span class="sxs-lookup"><span data-stu-id="dffb8-163">[Service Workers][MDNServiceWorkerApi] and other key PWA technologies that work with service workers \(such as the [Cache][MDNCache], [Push][MDNPushApi], and [Background Sync][MDNSyncManager] APIs\) only work across secure connections, which means [HTTPS][WikiHttps] for live sites or `localhost` for debugging purposes.</span></span>  

<span data-ttu-id="dffb8-164">この Web [アプリを][VisualStudioNodejsTutorialPublishAzureAppService] ライブ サイト \として公開する場合 ( [たとえば、Azure][AzureCreateFreeAccount]無料アカウント \を設定)、サーバーが HTTPS 用に構成されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-164">If you [publish this web app as a live site][VisualStudioNodejsTutorialPublishAzureAppService] \(for example, by setting up an [Azure free account][AzureCreateFreeAccount]\), you must ensure your server is configured for HTTPS.</span></span>  <span data-ttu-id="dffb8-165">Microsoft Azure [App Service を使用して][AzureWebApps] サイトをホストする場合、既定では HTTPS 経由で提供されます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-165">If you use the [Microsoft Azure App Service][AzureWebApps] to host your site, it is served over HTTPS by default.</span></span>  

<span data-ttu-id="dffb8-166">このガイドでは、引き続 `http://localhost` きライブ サイトのプレースホルダーとして使用してください `https://` 。</span><span class="sxs-lookup"><span data-stu-id="dffb8-166">For this guide, continue using `http://localhost` as a placeholder for a live site served over `https://`.</span></span>  

### <span data-ttu-id="dffb8-167">サービス ワーカー</span><span class="sxs-lookup"><span data-stu-id="dffb8-167">Service Workers</span></span>  

<span data-ttu-id="dffb8-168">サービス ワーカーは、PAS の主要なテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="dffb8-168">Service Workers is the key technology behind PWAs.</span></span> <span data-ttu-id="dffb8-169">サービス ワーカーは、PWA とネットワークの間のプロキシとして機能し、オフライン シナリオを処理し、サーバー プッシュ通知に応答し、バックグラウンド タスクを実行するインストール済みネイティブ アプリとして Web サイトを機能できます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-169">Service Workers act as a proxy between your PWA and the network to enable your website to function as an installed native app that serves up offline scenarios, responds to server push notifications, and runs background tasks.</span></span>  <span data-ttu-id="dffb8-170">サービス ワーカーは、新しいパフォーマンス戦略も開始します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-170">Service workers also open up new performance strategies.</span></span>  <span data-ttu-id="dffb8-171">Web サイトのページ読み込みパフォーマンスを微調整するために、サービス ワーカー キャッシュを使用するために完全な Web アプリを実装する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dffb8-171">You are not required to implement a full web app to use the service worker cache for fine-tuned page load performance for your website.</span></span>  

<span data-ttu-id="dffb8-172">サービス ワーカーは、Web アプリを起動する通常のスクリプトと共に提供される JavaScript ファイルから実行されるイベント駆動バックグラウンド スレッドです。</span><span class="sxs-lookup"><span data-stu-id="dffb8-172">Service workers are event-driven background threads that run from JavaScript files served up alongside the regular scripts that power your web app.</span></span>  <span data-ttu-id="dffb8-173">サービス ワーカーはメイン UI スレッドで実行されないので[、UI][MDNWorkerPrototypePostMessage]スレッドとワーカー スレッドはイベント ハンドラーを使用して[][MDNDedicatedWorkerGlobalScopePostMessage]通信することができますが、サービス ワーカーは DOM にアクセスできます `postMessage()` `onmessage` 。</span><span class="sxs-lookup"><span data-stu-id="dffb8-173">Because Service workers do not run on the main UI thread, service workers do not have DOM access, though the [UI thread][MDNWorkerPrototypePostMessage] and a [worker thread][MDNDedicatedWorkerGlobalScopePostMessage] is able to communicate using `postMessage()` and `onmessage` event handlers.</span></span>  

<span data-ttu-id="dffb8-174">サービス ワーカーをアプリに関連付ける場合は、サイト \(またはサイト内の指定したパス) の URL の生成元に登録します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-174">You associate a service worker with your app by registering it to the URL origin of your site \(or a specified path within it\).</span></span>  <span data-ttu-id="dffb8-175">登録すると、サービス ワーカー ファイルがユーザー コンピューターにダウンロードされ、インストールされ、アクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-175">Once registered, the service worker file is then downloaded, installed, and activated on the user machine.</span></span>  <span data-ttu-id="dffb8-176">さらに、MDN Web ドキュメントには、サービス[][MDNUsingServiceWorkers]ワーカーの使用に関する包括的なガイドと詳細なサービス ワーカー [API][MDNServiceWorkerApi]リファレンスがあります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-176">For more, MDN web docs has a comprehensive guide on [Using Service Workers][MDNUsingServiceWorkers] and a detailed [Service Worker API][MDNServiceWorkerApi] reference.</span></span>  

<span data-ttu-id="dffb8-177">このチュートリアルでは、PWA Builder のオフライン ページ [サービス ワーカー スクリプトを使用します][PwaBuilderServiceWorker]。</span><span class="sxs-lookup"><span data-stu-id="dffb8-177">For this tutorial, use the Offline page service worker script on [PWA Builder][PwaBuilderServiceWorker].</span></span>  <span data-ttu-id="dffb8-178">まず、パフォーマンス要件やネットワーク帯域幅など、より多くの機能を備え、スクリプトをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="dffb8-178">Start by customizing the script with more functionality according to your performance requirements, network bandwidth, and so on.</span></span>  <span data-ttu-id="dffb8-179">Mozilla [が提供する Service Worker Cookbook][ServiceWorkerCookbook]  で、便利なサービス ワーカー キャッシュに関する多くのアイデアを確認します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-179">Review the [Service Worker Cookbook][ServiceWorkerCookbook]  provided by Mozilla for a number of useful service worker caching ideas.</span></span>  

1.  <span data-ttu-id="dffb8-180">\(default\) オフライン ページ サービス ワーカーを開いて選択し、[サービス ワーカーのダウンロード [https://www.pwabuilder.com/serviceworker][PwaBuilderServiceWorker] **] ボタンをクリック**します。 </span><span class="sxs-lookup"><span data-stu-id="dffb8-180">Open [https://www.pwabuilder.com/serviceworker][PwaBuilderServiceWorker] and select the \(default\) **Offline page** service worker and click the **Download service worker** button.</span></span>  
1.  <span data-ttu-id="dffb8-181">ダウンロード フォルダーを開き、次の 2 つのファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="dffb8-181">Open the download folder and copy the following two files</span></span>  

    *   <span data-ttu-id="dffb8-182">ServiceWorker1\pwabuilder-sw-register.js</span><span class="sxs-lookup"><span data-stu-id="dffb8-182">ServiceWorker1\pwabuilder-sw-register.js</span></span>  
    *   <span data-ttu-id="dffb8-183">ServiceWorker1\pwabuilder-sw.js</span><span class="sxs-lookup"><span data-stu-id="dffb8-183">ServiceWorker1\pwabuilder-sw.js</span></span>  
    
    <span data-ttu-id="dffb8-184">ファイルを Web アプリ `public` プロジェクトのフォルダー Visual Studio保存します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-184">Save the files to the `public` folder of your Visual Studio web app project.</span></span>  <span data-ttu-id="dffb8-185">\(ファイルVisual Studioエクスプローラーを開き、フォルダーに移動 `Ctrl` + `O` `public` するために使用します。)</span><span class="sxs-lookup"><span data-stu-id="dffb8-185">\(From Visual Studio, use `Ctrl`+`O` to open file explorer to your project and navigate to the `public` folder\).</span></span>  
    
    <span data-ttu-id="dffb8-186">ソリューション エクスプローラーでファイルを `public/pwabuilder-sw.js` 開き、次の値を変更 `offlineFallbackPage` します `offline.html` 。</span><span class="sxs-lookup"><span data-stu-id="dffb8-186">In Solution Explorer, open the `public/pwabuilder-sw.js` file, and change the value of `offlineFallbackPage` to `offline.html`.</span></span>  
    
    ```javascript
    const offlineFallbackPage = "offline.html";
    ```
    
    <span data-ttu-id="dffb8-187">これらのファイルの両方のコードを確認して、指定されたページ \( \) をキャッシュし、ネットワーク フェッチが失敗した場合にサービス ワーカーを提供するサービス ワーカーを登録する方法の Gist を取得する価値があります。 `offline.html`</span><span class="sxs-lookup"><span data-stu-id="dffb8-187">It is worth reviewing the code in both of these files, to get the gist of how to register a service worker that caches a designated page \(`offline.html`\) and serves it when a network fetch fails.</span></span>  <span data-ttu-id="dffb8-188">次に、アプリの `offline.html` オフライン機能のプレースホルダーとして単純なページを作成します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-188">Next, create a simple `offline.html` page as a placeholder for the offline functionality of your app.</span></span>  
    
1.  <span data-ttu-id="dffb8-189">ソリューション エクスプローラーでファイルを開 `views/layout.pug` き、リンク タグの下に次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-189">In Solution Explorer, open the `views/layout.pug` file, and add the following line below your link tags.</span></span>  
    
    ```html
    script(src='/pwabuilder-sw-register.js' type='module')
    ```  
    
    <span data-ttu-id="dffb8-190">サイトがサービス ワーカー登録スクリプトを読み込み、実行します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-190">Your site loads and runs your service worker registration script.</span></span>  
    
1.  <span data-ttu-id="dffb8-191">ソリューション エクスプローラーで、フォルダーを右クリックし、[新しいファイルの `public` 追加  >  **] を選択します**。 名前を `offline.html` 付け、本文 `<title>` の内容を追加します (例: 次のコード)。</span><span class="sxs-lookup"><span data-stu-id="dffb8-191">In Solution Explorer, right-click on the `public` folder and select **Add** > **New File...**.  Name it `offline.html`, and add a `<title>` and some body content, for example the following code.</span></span>  
    
    ```html
    <!DOCTYPE html>
    
    <html xmlns="http://www.w3.org/1999/xhtml">
    <head>
        <meta charset="utf-8" />
        <title>Offline mode</title>
    </head>
    <body>
        You are now offline.
    </body>
    </html>
    ```  
    
    <span data-ttu-id="dffb8-192">この時点で、フォルダーには `public` 3 つの新しいファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="dffb8-192">At this point, your `public` folder should have three new files.</span></span>  
    
    ![ソリューションのパブリック フォルダーに追加されたファイル][ImageVsNodejsExpressPublic]  
    
1.  <span data-ttu-id="dffb8-194">ソリューション エクスプローラーでファイルを開き、最後のコマンド \( \) の直前に次の `routes\index.js` コードを追加 `module.exports = router;` します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-194">In Solution Explorer, open the `routes\index.js` file, and add the following code just before the final command \(`module.exports = router;`\).</span></span>  
    
    ```javascript
    router.get('/offline.html', function (req, res) {
        res.sendFile('public/offline.html');
    });
    ```  
    
    <span data-ttu-id="dffb8-195">これにより、アプリはファイル \(サービス ワーカーがオフライン キャッシュ用にフェッチするときに) サービスを提供 `offline.html` するように指示します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-195">This instructs your app to serve the `offline.html` file \(when your service worker fetches it for the offline cache\).</span></span>  
    
1.  <span data-ttu-id="dffb8-196">PWA をテストしてください。</span><span class="sxs-lookup"><span data-stu-id="dffb8-196">Test out your PWA!</span></span>  <span data-ttu-id="dffb8-197">\( `Ctrl` + `Shift` + `B` \) をビルドして \( \) を実行し、Web アプリを実行して Microsoft Edge を `F5` 起動し、ページを開 `localhost` きます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-197">Build \(`Ctrl`+`Shift`+`B`\) and Run \(`F5`\) your web app to launch Microsoft Edge and open your `localhost` page.</span></span>  <span data-ttu-id="dffb8-198">次に、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-198">Then complete the following steps.</span></span>  
    
    1.  <span data-ttu-id="dffb8-199">Edge DevTools**コンソール**\( \) を開 `Ctrl` + `Shift` + `J` き、サービス ワーカーが登録されたのを確認します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-199">Open the Edge DevTools **Console** \(`Ctrl`+`Shift`+`J`\) and verify the Service worker was registered.</span></span>  
    1.  <span data-ttu-id="dffb8-200">デバッガー パネル **で** 、[Service **Workers]** コントロールを展開し、オリジンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="dffb8-200">In the **Debugger** panel, expand the **Service Workers** control and click on your origin.</span></span>  <span data-ttu-id="dffb8-201">サービス ワーカー **の概要で**、サービス ワーカーがアクティブ化され、実行中になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-201">In the **Service Worker Overview**, verify your service worker is activated and running.</span></span>  
        
        ![Edge DevTools Service Worker の概要][ImageDevtoolsSwOverview]  
        
    1.  <span data-ttu-id="dffb8-203">[ **キャッシュ] コントロール** を展開し、ページ `offline.html` がキャッシュに入っているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-203">Expand the **Cache** control and verify that the `offline.html` page is cached.</span></span>  
        
        ![Edge DevTools サービス ワーカー キャッシュ][ImageDevtoolsSwCache]  
        
1.  <span data-ttu-id="dffb8-205">オフライン アプリとして PWA を試してみる時間です。</span><span class="sxs-lookup"><span data-stu-id="dffb8-205">Time to try your PWA as an offline app!</span></span>  <span data-ttu-id="dffb8-206">In Visual Studio, **Stop Debugging** `Shift` + `F5` \( \) your web app, then open Microsoft Edge \(or refresh\) to the localhost address of your website.</span><span class="sxs-lookup"><span data-stu-id="dffb8-206">In Visual Studio, **Stop Debugging** \(`Shift`+`F5`\) your web app, then open Microsoft Edge \(or refresh\) to the localhost address of your website.</span></span>  <span data-ttu-id="dffb8-207">これで、ページ \(サービス ワーカーとオフライン キャッシュ\) を読 `offline.html` み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-207">It should now load the `offline.html` page \(thanks to your service worker and offline cache\)!</span></span>  
    
    ![offline.htmMicrosoft Edge に http://localhost:1337 読み込まれたファイル][ImageOfflineHtml]  

## <span data-ttu-id="dffb8-209">プッシュ通知を追加する</span><span class="sxs-lookup"><span data-stu-id="dffb8-209">Add push notifications</span></span>  

<span data-ttu-id="dffb8-210">プッシュ [API][MDNPushApi] を使用してメッセージング サービスをサブスクライブし、通知 [API][MDNNotificationsApi] を使用してメッセージの受信時にトースト メッセージを表示するクライアント側のプッシュ通知のサポートを追加することで、PWA をよりアプリに似たものにします。</span><span class="sxs-lookup"><span data-stu-id="dffb8-210">Make your PWA more app-like by adding client-side support for push notifications using the [Push API][MDNPushApi] to subscribe to a messaging service and the [Notifications API][MDNNotificationsApi] to display a toast message upon receiving a message.</span></span>  <span data-ttu-id="dffb8-211">サービス ワーカーと同様に、これらはクロスブラウザーで動作する標準ベースの API なので、PAP がサポートされているすべての場所で動作するには、コードを 1 回記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-211">As with Service Workers, these are standards-based APIs that work cross-browser, so you only have to write the code once for it to work everywhere PWAs are supported.</span></span>  <span data-ttu-id="dffb8-212">サーバー側では [、Web プッシュ][NPMWebPush] オープン ソース ライブラリを使用して、さまざまなブラウザーにプッシュ メッセージを配信する場合に関係する違いを処理します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-212">On the server side, use the [Web-Push][NPMWebPush] open-source library to handle the differences involved in delivering push messages to various browsers.</span></span>  

<span data-ttu-id="dffb8-213">以下は、Mozilla が提供する Service [Worker Cookbook][ServiceWorkerCookbookPushRichDemo] の Push Rich Demo を基にしています。これは、他の多くの便利な Web プッシュおよびサービス ワーカーのレシピを確認する価値があります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-213">The following is adapted from the Push Rich Demo in [Service Worker Cookbook][ServiceWorkerCookbookPushRichDemo] provided by Mozilla, which is worth checking out for a number of other useful Web Push and service worker recipes.</span></span>  

### <span data-ttu-id="dffb8-214">手順 1 - NPM Web プッシュ ライブラリをインストールする</span><span class="sxs-lookup"><span data-stu-id="dffb8-214">Step 1 - Install the NPM web-push library</span></span>  

<span data-ttu-id="dffb8-215">ソリューション Visual Studioで、プロジェクトを右クリックし、[対話型ウィンドウ] Node.js **開**きます。 その中に、次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-215">In Visual Studio Solution Explorer, right-click your project and **Open Node.js Interactive Window...**.  In it, type the following code.</span></span>  

```javascript
.npm install web-push
```  

<span data-ttu-id="dffb8-216">これにより [、Web プッシュ ライブラリがインストール][NPMWebPush] されます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-216">This installs the [Web-Push][NPMWebPush] library.</span></span>  <span data-ttu-id="dffb8-217">次に、ファイルを開き、他の要件ステートメントの後に次の行をファイルの一番上 `index.js` に追加します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-217">Then, open up your `index.js` file, and add the following line to the top of your file after the other requirement statements.</span></span>  

```javascript
var webpush = require('web-push');
```  

### <span data-ttu-id="dffb8-218">手順 2 - サーバーの VAPID キーを生成する</span><span class="sxs-lookup"><span data-stu-id="dffb8-218">Step 2 - Generate VAPID keys for your server</span></span>  

<span data-ttu-id="dffb8-219">次に、サーバーが PWA クライアントにプッシュ メッセージを送信するために VAPID \(任意のアプリケーション サーバー識別\) キーを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-219">Next you must generate VAPID \(Voluntary Application Server Identification\) keys for your server to send push messages to the PWA client.</span></span>  <span data-ttu-id="dffb8-220">これを行う必要があるのは\(つまり、サーバーに必要な VAPID キーのペアが 1 つだけ\) 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="dffb8-220">You only have to do this once \(that is, your server only requires a single pair of VAPID keys\).</span></span>  <span data-ttu-id="dffb8-221">[対話型Node.jsウィンドウで、次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-221">In the Node.js Interactive Window, type the following code.</span></span>  

```javascript
var webpush = require('web-push');
webpush.generateVAPIDKeys();
```  

<span data-ttu-id="dffb8-222">出力の結果、公開キーとプライベート キーを含む JSON オブジェクトが作成され、サーバー ロジックにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-222">The output should result in a JSON object containing a public and private key, which you copy into your server logic.</span></span>  

<span data-ttu-id="dffb8-223">ファイルの最後の \( \) 行の直前に、次 `index.js` `module.exports = router` のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-223">In your `index.js` file, just before the final  \(`module.exports = router`\) line, add the following code.</span></span>  

```javascript
const vapidKeys = {
    publicKey: '',
    privateKey: ''
};

webpush.setVapidDetails(
    'mailto:pwa@example.com',
    vapidKeys.publicKey,
    vapidKeys.privateKey
);
```  

<span data-ttu-id="dffb8-224">生成した `publicKey` `privateKey` 値と値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="dffb8-224">Copy the `publicKey` and `privateKey` values that you just generated.</span></span>  <span data-ttu-id="dffb8-225">アドレスも自由にカスタマイズできます (このサンプルを実行するために必要 `mailto` ありません\)。</span><span class="sxs-lookup"><span data-stu-id="dffb8-225">Feel free to customize the `mailto` address as well \(though it is not required in order to run this sample\).</span></span>  

<span data-ttu-id="dffb8-226">[Mozilla Services][MozillaServicesSendingVapidWebPushNotificationsPush]のエンジニアリング ブログには、VAPID と WebPush の詳細な説明が用意されています。その詳細については、このブログを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dffb8-226">The [Mozilla Services engineering blog][MozillaServicesSendingVapidWebPushNotificationsPush] has a nice explainer on VAPID and WebPush if you are interested in the details of how it works behind the scenes.</span></span>  

### <span data-ttu-id="dffb8-227">手順 3 - プッシュ関連のサーバー要求を処理する</span><span class="sxs-lookup"><span data-stu-id="dffb8-227">Step 3 - Handle push-related server requests</span></span>  

<span data-ttu-id="dffb8-228">次に、PWA クライアントからのプッシュ関連の要求を処理するルートを設定します。たとえば、VAPID 公開キーの処理や、プッシュを受信するクライアントの登録を含みます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-228">Now set up routes for handling push-related requests from the PWA client, including serving up the VAPID public key and registering the client to receive pushes.</span></span>  

<span data-ttu-id="dffb8-229">実際のシナリオでは、プッシュ通知はサーバー ロジックのイベントから発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-229">In a real scenario, a push notification likely originates from an event in your server logic.</span></span>  <span data-ttu-id="dffb8-230">ここでの作業を簡略化するには、PWA ホームページにプッシュ通知ボタンを追加してサーバーからプッシュを生成し、それらの要求を処理するエンドポイント `/sendNotification` \(サーバー ルート\)を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-230">To simplify things here, you must add a **Push Notification** button to our PWA homepage for generating pushes from our server, and a `/sendNotification` endpoint \(server route\)for handling those requests.</span></span>  

<span data-ttu-id="dffb8-231">ファイルで、[ `index.js` 手順 2][#step-2---generate-vapid-keys-for-your-server] で追加した VAPID 初期化コードの直後に、次のルートを追加します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-231">In your `index.js` file, append the following routes just after the VAPID initialization code you added in [Step 2][#step-2---generate-vapid-keys-for-your-server].</span></span>  

```javascript
router.get('/vapidPublicKey', function (req, res) {
    res.send(vapidKeys.publicKey);
});

router.post('/register', function (req, res) {
    // A real world application stores the subscription info.
    res.sendStatus(201);
});

router.post('/sendNotification', function (req, res) {
    const subscription = req.body.subscription;
    const payload = 'payload';
    const options = null;
    
    webpush.sendNotification(subscription, payload, options)
        .then(function () {
            res.sendStatus(201);
        })
        .catch(function (error) {
            res.sendStatus(500);
            console.log(error);
        });
});
```  

<span data-ttu-id="dffb8-232">サーバー側のコードを配置して、PWA クライアントのプッシュ通知を実行します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-232">With the server-side code in place, plumb in push notifications on the PWA client.</span></span>  

### <span data-ttu-id="dffb8-233">手順 4 - プッシュ通知をサブスクライブする</span><span class="sxs-lookup"><span data-stu-id="dffb8-233">Step 4 - Subscribe to push notifications</span></span>  

<span data-ttu-id="dffb8-234">PWA ネットワーク プロキシとしての役割の一環として、サービス ワーカーはプッシュ イベントとトースト通知の操作を処理します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-234">As part of their role as PWA network proxies, service workers handle push events and toast notification interactions.</span></span>  <span data-ttu-id="dffb8-235">ただし、最初にサービス ワーカーをセットアップする \(または登録\) の場合と同様に、PWA をサーバー プッシュ通知にサブスクライブすると、PWA のメイン UI スレッドで実行され、ネットワーク接続が必要になります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-235">However, as it is with first setting up \(or registering\) a service worker, subscribing the PWA to server push notifications happens on the main UI thread of the PWA and requires network connectivity.</span></span>  <span data-ttu-id="dffb8-236">プッシュ通知をサブスクライブするにはアクティブなサービス ワーカー登録が必要です。そのため、プッシュ通知をサブスクライブする前に、サービス ワーカーがインストールされアクティブなことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-236">Subscribing to push notifications requires an active service worker registration, so you must first verify that your service worker is installed and active before trying to subscribe it to push notifications.</span></span>  

<span data-ttu-id="dffb8-237">新しいプッシュ サブスクリプションを作成する前に、Microsoft Edge は、ユーザーが通知を受信するための PWA アクセス許可を付与したのか確認します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-237">Before a new push subscription is created, Microsoft Edge check if the user granted the PWA permission to receive notifications.</span></span>  <span data-ttu-id="dffb8-238">設定されていない場合は、ブラウザーからアクセス許可を求めるメッセージがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-238">If not, the user is prompted by the browser for permission.</span></span>  <span data-ttu-id="dffb8-239">アクセス許可が拒否された場合は、要求がスローされます。そのため、処理 `registration.pushManager.subscribe` `DOMException` する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-239">If the permission is denied, the request to `registration.pushManager.subscribe` throws a `DOMException`, so you must handle it.</span></span>  <span data-ttu-id="dffb8-240">アクセス許可の管理について詳しくは [、Microsoft Edge のプッシュ通知に関するページをご覧ください][WindowsBlogsWebNotificationsEdge]。</span><span class="sxs-lookup"><span data-stu-id="dffb8-240">For more on permission management, see [Push Notifications in Microsoft Edge][WindowsBlogsWebNotificationsEdge].</span></span>  

<span data-ttu-id="dffb8-241">ファイルに `pwabuilder-sw-register.js` 、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-241">In your `pwabuilder-sw-register.js` file, append the following code.</span></span>  

```javascript
// Subscribe this PWA to push notifications from the server
navigator.serviceWorker.ready
    .then(function (registration) {
        // Check if the user has an existing subscription
        return registration.pushManager.getSubscription()
            .then(async function (subscription) {
                if (subscription) {
                    return subscription;
                }
                
                // Otherwise subscribe with the server public key
                const response = await fetch('./vapidPublicKey');
                const vapidPublicKey = await response.text();
                const convertedVapidKey = urlBase64ToUint8Array(vapidPublicKey);
                
                return registration.pushManager.subscribe({
                    userVisibleOnly: true,
                    applicationServerKey: convertedVapidKey
                });
            });
    }).then(function (subscription) {
        // Send the subscription details to the server
        fetch('./register', {
            method: 'post',
            headers: {
                'Content-type': 'application/json'
            },
            body: JSON.stringify({
                subscription: subscription
            }),
        });
        
        // Create a button to mimic server pushes for testing purposes
        var button = document.createElement('input');
        button.type = 'button';
        button.id = 'notify';
        button.value = 'Send Notification';
        document.body.appendChild(button);
        document.getElementById('notify').addEventListener('click', function () {
            fetch('./sendNotification', {
                method: 'post',
                headers: {
                    'Content-type': 'application/json'
                },
                body: JSON.stringify({
                    subscription: subscription
                }),
            });
        });
    });

// Utility function for browser interoperability
function urlBase64ToUint8Array(base64String) {
    var padding = '='.repeat((4 - base64String.length % 4) % 4);
    var base64 = (base64String + padding)
        .replace(/\-/g, '+')
        .replace(/_/g, '/');
        
    var rawData = window.atob(base64);
    var outputArray = new Uint8Array(rawData.length);
    
    for (var i = 0; i < rawData.length; ++i) {
        outputArray[i] = rawData.charCodeAt(i);
    }
    return outputArray;
}
```  

<span data-ttu-id="dffb8-242">API の動作とさまざまな関連オプションの詳細については [、PushManager][MDNPushManager] インターフェイスの MDN ドキュメントと [Web プッシュ][NPMWebPushUsage] ライブラリの NPM ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dffb8-242">Review the MDN documentation on the [PushManager][MDNPushManager] interface and NPM docs on the [Web-Push][NPMWebPushUsage] library for more details on how the APIs work and various related options.</span></span>  

### <span data-ttu-id="dffb8-243">手順 5 - プッシュイベント ハンドラーと notificationclick イベント ハンドラーを設定する</span><span class="sxs-lookup"><span data-stu-id="dffb8-243">Step 5 - Set up push and notificationclick event handlers</span></span>  

<span data-ttu-id="dffb8-244">プッシュ サブスクリプションを設定すると、残りの作業はサービス ワーカーで行います。</span><span class="sxs-lookup"><span data-stu-id="dffb8-244">With our push subscription set up, the remainder of the work happens in the service worker.</span></span>  <span data-ttu-id="dffb8-245">まず、サーバーから送信されるプッシュ イベントのハンドラーを設定し、プッシュ データペイロードを表示するトースト通知 \(アクセス許可が付与されている場合\) で応答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-245">First you must set up a handler for server-sent push events, and respond with a toast notification \(if permission was granted\) displaying the push data payload.</span></span>  <span data-ttu-id="dffb8-246">次に、トーストのクリック ハンドラーを追加して通知を閉じ、現在開いているウィンドウの一覧を並べ替え、目的の PWA クライアント ページを開く、フォーカスする、またはフォーカスを設定します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-246">Next you add a click handler for the toast to dismiss the notification and sort through a list of currently open windows to open, focus, or open and focus the intended PWA client page.</span></span>  

<span data-ttu-id="dffb8-247">ファイルに `pwabuilder-sw.js` 、次のハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-247">In your `pwabuilder-sw.js` file, append the following handlers.</span></span>  

```javascript
//Respond to a server push with a user notification
self.addEventListener('push', function (event) {
    if ("granted" === Notification.permission) {
        var payload = event.data ? event.data.text() : 'no payload';
        const promiseChain = self.registration.showNotification('Sample PWA', {
            body: payload,
            icon: 'images/windows10/Square44x44Logo.scale-100.png'
        });
        //Ensure the toast notification is displayed before exiting this function
        event.waitUntil(promiseChain);
    }
});
    
//Respond to the user clicking the toast notification
self.addEventListener('notificationclick', function (event) {
    console.log('On notification click: ', event.notification.tag);
    event.notification.close();
    
    // This looks to see if the current is already open and focuses it
    event.waitUntil(clients.matchAll({
        type: 'window'
    }).then(function (clientList) {
        for (var i = 0; i < clientList.length; i++) {
            var client = clientList[i];
            if (client.url == 'http://localhost:1337/' && 'focus' in client)
                return client.focus();
        }
        if (clients.openWindow)
            return clients.openWindow('/');
    }));
});
```  

### <span data-ttu-id="dffb8-248">手順 6 - 試してみる</span><span class="sxs-lookup"><span data-stu-id="dffb8-248">Step 6 - Try it out</span></span>  

<span data-ttu-id="dffb8-249">PWA でプッシュ通知をテストする時間です。</span><span class="sxs-lookup"><span data-stu-id="dffb8-249">Time to test push notifications in your PWA!</span></span>  

1.  <span data-ttu-id="dffb8-250">ブラウザーで `F5` \( \) PWA を実行します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-250">Run \(`F5`\) your PWA in the browser.</span></span>  <span data-ttu-id="dffb8-251">サービス ワーカー コード \( \) を変更したので、DevTools Debugger \( \) をサービス ワーカーの概要パネルに開き、サービス ワーカーの登録を解除し、ページを再読み込み \( \) して再登録する必要があります (または `pwabuilder-sw.js` `F12`  `F5` **[\]** をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="dffb8-251">Because you modified the service worker code \(`pwabuilder-sw.js`\), you must open the DevTools Debugger \(`F12`\) to the **Service Worker Overview** panel and **Unregister** the service worker and reload \(`F5`\) the page to re-register it \(or you click **Update**\).</span></span>  <span data-ttu-id="dffb8-252">実稼働シナリオでは、ブラウザーは定期的にサービス ワーカー更新プログラムをチェックし、バックグラウンドで更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="dffb8-252">In a production scenario, the browser checks regularly check for service worker updates and install the updates in the background.</span></span>  <span data-ttu-id="dffb8-253">すぐに結果を得る場合は、ここに強制的に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-253">You should force it here for immediate results.</span></span>  
    
    <span data-ttu-id="dffb8-254">サービス ワーカーがアクティブ化し、PWA をサブスクライブして通知をプッシュしようとすると、ページの下部にアクセス許可ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-254">As your service worker activates and attempts to subscribe your PWA to push notifications, you should see a permission dialog at the bottom of the page.</span></span>  
    
    ![通知を有効にするためのアクセス許可ダイアログ][ImageNotificationPermission]  
    
    <span data-ttu-id="dffb8-256">[ **はい]** を選択して、PWA のトースト通知を有効にします。</span><span class="sxs-lookup"><span data-stu-id="dffb8-256">Choose **Yes** to enable toast notifications for your PWA.</span></span>  
    
1.  <span data-ttu-id="dffb8-257">[サービス ワーカーの概要] ウィンドウで、プッシュ ボタンを  **選択** してみてください。</span><span class="sxs-lookup"><span data-stu-id="dffb8-257">From the Service Worker Overview pane, try choosing the  **Push** button.</span></span>  <span data-ttu-id="dffb8-258">\(hard-coded "Test push message from DevTools"\) ペイロードを含むトースト通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-258">A toast notification with the \(hard-coded "Test push message from DevTools"\) payload should appear.</span></span>  
    
    ![DevTools からの通知のプッシュ][ImageDevtoolsPush]  
    
1.  <span data-ttu-id="dffb8-260">次に、PWA のホーム **ページ** で [通知の送信] ボタンを選択してみてください。</span><span class="sxs-lookup"><span data-stu-id="dffb8-260">Next try choosing the **Send Notification** button on the homepage of your PWA.</span></span>  <span data-ttu-id="dffb8-261">今回は、サーバーからのペイロードを含むトーストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-261">This time a toast with the payload from your server appears.</span></span>  
    
    ![PWA サーバーから通知をプッシュする][ImagePwaPush]  
    
    <span data-ttu-id="dffb8-263">トースト通知を \(または activate\) クリックしない場合は、数秒後に閉じ、Windows アクション センターでキューに登録されます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-263">If you do not click \(or activate\) a toast notification, it is dismissed after several seconds and queue up in your Windows Action Center.</span></span>  
    
    ![Windows アクション センターでの通知][ImageWindowsActionCenter]  
    
    <span data-ttu-id="dffb8-265">PWA プッシュ通知の基本を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-265">You have the basics of PWA push notifications.</span></span>  <span data-ttu-id="dffb8-266">実際のアプリでは、次の手順は、プッシュ サブスクリプションを管理および保存し、ネットワークを通して[][NPMWebPushEncrypt]送信されるペイロード データを適切に暗号化する方法で実装されます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-266">In a real app, the next steps are implemented in a way to manage and store push subscriptions and to properly [encrypt][NPMWebPushEncrypt] payload data being sent across the wire.</span></span>  
    
## <span data-ttu-id="dffb8-267">追加情報</span><span class="sxs-lookup"><span data-stu-id="dffb8-267">Going further</span></span>  

<span data-ttu-id="dffb8-268">このガイドでは、Visual Studio、PWA Builder、Edge DevTools など、段階的 Web App と Microsoft PWA 開発ツールの基本的な構造について説明しました。</span><span class="sxs-lookup"><span data-stu-id="dffb8-268">This guide demonstrated the basic anatomy of a Progressive Web App and Microsoft PWA development tools including Visual Studio, PWA Builder, and Edge DevTools.</span></span>  

<span data-ttu-id="dffb8-269">もちろん、レスポンシブ デザイン、ディープ リンク、クロスブラウザー テスト、その他のベスト プラクティス[(アプリ][Webhint]の機能は言うまでもなく[][BrowserStackTestEdgeBrowser]\) など、ここに記載されている以上の優れた[PWA][PwaEdgehtmlIndexRequirements]を作成する方法は他に多く含まれていますが、このガイドでは、PWA の基本と入門に関するアイデアをしっかりと紹介しています。</span><span class="sxs-lookup"><span data-stu-id="dffb8-269">Of course, there is a lot more that goes into [making a great PWA][PwaEdgehtmlIndexRequirements] beyond what you read here, including responsive design, deep-linking, [cross-browser testing][BrowserStackTestEdgeBrowser] and other [best practices][Webhint] \(not to mention your app functionality!\), but hopefully this guide gave you a solid introduction of PWA basics and some ideas on getting started.</span></span>  <span data-ttu-id="dffb8-270">Windows を使用した PWA 開発に関してさらに質問がある場合や、Visual Studioご質問がある場合は、コメントを残してください。</span><span class="sxs-lookup"><span data-stu-id="dffb8-270">If you have further questions on PWA development with Windows or with Visual Studio, please leave a comment!</span></span>  

<span data-ttu-id="dffb8-271">他の PWA ガイドを確認して、顧客エンゲージメントを向上し、OS と統合されたよりシームレスなアプリ エクスペリエンスを提供する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-271">Review the other PWA guides to learn how to increase customer engagement and provide a more seamless, OS-integrated app experience.</span></span>  

*   <span data-ttu-id="dffb8-272">[Windows の調整][PwaEdgehtmlWindowsFeatures]。</span><span class="sxs-lookup"><span data-stu-id="dffb8-272">[Windows tailoring][PwaEdgehtmlWindowsFeatures].</span></span> <span data-ttu-id="dffb8-273">単純な機能検出を使用すると、Windows 10 のネイティブ API **(Windows** スタート メニューのタイル通知やタスク バージャンプリストをカスタマイズする API や、写真、音楽、カレンダーなどのユーザー リソースを操作する \(アクセス許可時\) など) を使って、Windows 10 ユーザー向け PWA を徐々に強化できます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-273">Using simple feature detection, you may progressively enhance your PWA for Windows 10 customers through native Windows Runtime \(WinRT\) APIs, such as those for customizing Windows **Start** menu tile notifications and taskbar jumplists, and \(upon permission\) working with user resources, such as photos, music, and calendar.</span></span>  
*   <span data-ttu-id="dffb8-274">[Microsoft Store の PAS][PwaEdgehtmlMicrosoftStore]。</span><span class="sxs-lookup"><span data-stu-id="dffb8-274">[PWAs in the Microsoft Store][PwaEdgehtmlMicrosoftStore].</span></span>  <span data-ttu-id="dffb8-275">アプリ ストアの配布の利点と、PWA を提出する方法について詳しくは、以下をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dffb8-275">Learn more about the benefits of app store distribution and how to submit your PWA.</span></span>  

## <span data-ttu-id="dffb8-276">関連項目</span><span class="sxs-lookup"><span data-stu-id="dffb8-276">See also</span></span>  

*   <span data-ttu-id="dffb8-277">[MDN Web ドキュメントの段階的な Web アプリ][MDNProgressiveWebApps] - 段階的な Web アプリの優れたガイド。</span><span class="sxs-lookup"><span data-stu-id="dffb8-277">[Progressive Web Apps on MDN web docs][MDNProgressiveWebApps] - Excellent guide on Progressive Web Apps.</span></span>  
*   <span data-ttu-id="dffb8-278">[Web.dev 上の段階的な Web][WebDevProgressiveWebApps] アプリ - 段階的な Web アプリの優れたガイド。</span><span class="sxs-lookup"><span data-stu-id="dffb8-278">[Progressive Web Apps on web.dev][WebDevProgressiveWebApps] - Excellent guide on Progressive Web Apps.</span></span>  
*   <span data-ttu-id="dffb8-279">[段階的な Web アプリの機能][ProgressiveWebApps] - PAS の実際の例を紹介します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-279">[Progressive Web Apps rocks][ProgressiveWebApps] - Showcases real-world examples of PWAs.</span></span>  
*   <span data-ttu-id="dffb8-280">[段階的な Web][HackerNewsProgressiveWebApps] アプリとしてのハッカーニュース リーダー - サンプル \(Hacker News reader\) PWA を実装するためのさまざまなフレームワークとパフォーマンス パターンを比較します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-280">[Hacker News readers as Progressive Web Apps][HackerNewsProgressiveWebApps] - Compares different frameworks and performance patterns for implementing a sample \(Hacker News reader\) PWA.</span></span>  

<!-- image links -->  

[ImageDevtoolsPush]: ./media/devtools-push.png  
[ImageDevtoolsSwCache]: ./media/devtools-cache.png  
[ImageDevtoolsSwOverview]: ./media/devtools-sw-overview.png  
[ImageNotificationPermission]: ./media/notification-permission.png  
[ImageOfflineHtml]: ./media/offline-html.png  
[ImagePwa]: ./media/pwa.png  
[ImagePwaPush]: ./media/pwa-push.png  
[ImageVsNodejsExpressIcon]: ./media/vs-nodejs-express-icon.png  
[ImageVsNodejsExpressIndex]: ./media/vs-nodejs-express-index.png  
[ImageVsNodejsExpressManifest]: ./media/vs-nodejs-express-manifest.png  
[ImageVsNodejsExpressPublic]: ./media/vs-nodejs-express-public.png  
[ImageVsNodejsExpressTemplate]: ./media/vs-nodejs-express-template.png  
[ImageWindowsActionCenter]: ./media/windows-action-center.png  

<!-- links -->  

[PwaEdgehtmlIndexRequirements]: ../progressive-web-apps/index.md#requirements "要件 - Windows の段階的な Web アプリ \(EdgeHTML\) |Microsoft Docs"  
[PwaEdgehtmlMicrosoftStore]: ../progressive-web-apps/microsoft-store.md "Microsoft Store の段階的な Web アプリ \(EdgeHTML\)|Microsoft Docs"  
[PwaEdgehtmlWindowsFeatures]: ../progressive-web-apps/windows-features.md "Windows 用に PWA \(EdgeHTML\) を調整する |Microsoft Docs"  

[LegalWindowsAgrementsMicrosoftStorePolicies]: /legal/windows/agreements/store-policies "Microsoft Store ポリシー |Microsoft Docs"  

[VisualStudioNodeJsTutorial]: /visualstudio/nodejs/tutorial-nodejs "チュートリアル: Node.js アプリと Express アプリを作成Visual Studio |Microsoft Docs"  
[VisualStudioNodejsTutorialPublishAzureAppService]: /visualstudio/nodejs/tutorial-nodejs#optional-publish-to-azure-app-service "Azure App Service に発行する - Node.jsアプリと Express アプリを作成Visual Studio |Microsoft Docs"  

[WindowsUwpGetStartedWhat]: /windows/uwp/get-started/whats-a-uwp "ユニバーサル Windows プラットフォーム \(UWP\) アプリとは |Microsoft Docs"  

[AzureCreateFreeAccount]: https://azure.microsoft.com/free "Azure 無料アカウントを作成する |Microsoft Azure"  
[AzureWebApps]: https://azure.microsoft.com/services/app-service/web "Web アプリ |Microsoft Azure"  

<!--[DeveloperEdgeToolsRemote]: https://developer.microsoft.com/microsoft-edge/tools/remote/ "page not found"  -->  

[WindowsBlogsPwaEdge]: https://blogs.windows.com/msedgedev/2018/02/06/welcoming-progressive-web-apps-edge-windows-10/#4UOdrDJj3124VIkc.97 "Microsoft Edge と Windows 10 への段階的な Web アプリの歓迎 |Windows ブログ"  
[WindowsBlogsWebNotificationsEdge]: https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge#UAbvU2ymUlHO8EUV.97 "Microsoft Edge での Web 通知 |Windows ブログ"  

[VisualStudioDownloads]: https://www.visualstudio.com/downloads "ダウンロード |Visual Studio"  
[VisualStudioFree]: https://visualstudio.microsoft.com/free-developer-offers "無料の開発者ソフトウェア & サービス |Visual Studio"  
[VisualStudioPreview]: https://www.visualstudio.com/vs/preview "Visual Studio プレビュー"  

[BrowserStackTestEdgeBrowser]: https://www.browserstack.com/test-on-microsoft-edge-browser "Windows 10 での Microsoft Edge ブラウザーの無料テスト |BrowserStack"  

[HackerNewsProgressiveWebApps]: https://hnpwa.com "段階的な Web アプリとしてのハッカーニュースリーダー"  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "Cache |MDN"  
[MDNDedicatedWorkerGlobalScopePostMessage]: https://developer.mozilla.org/docs/Web/API/DedicatedWorkerGlobalScope/postMessage "DedicatedWorkerGlobalScope.postMessage\(\) |MDN"  
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNProgressiveWebApps]: https://developer.mozilla.org/Apps/Progressive "段階的な Web アプリ \(PAS) |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "プッシュ API |MDN"  
[MDNPushManager]: https://developer.mozilla.org/docs/Web/API/PushManager "PushManager |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "サービス ワーカー API |MDN"  
[MDNSyncManager]: https://developer.mozilla.org/docs/Web/API/SyncManager "SyncManager |MDN"  
[MDNUsingServiceWorkers]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers "サービス ワーカーの使用 |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web アプリ マニフェスト |MDN"  
[MDNWorkerPrototypePostMessage]: https://developer.mozilla.org/docs/Web/API/Worker/postMessage "Worker.prototype.postMessage\(\) |MDN"  

[MozillaServicesSendingVapidWebPushNotificationsPush]: https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service "Mozilla のプッシュ サービスを介して VAPID によって識別された WebPush 通知を送信する |Mozilla Services"  

[NPMWebPush]: https://www.npmjs.com/package/web-push "web-push |npm"  
[NPMWebPushEncrypt]: https://www.npmjs.com/package/web-push#encryptuserpublickey-userauth-payload-contentencoding "encrypt(userPublicKey, userAuth, payload, contentEncoding) - web-push |NPM"  
[NPMWebPushUsage]: https://www.npmjs.com/package/web-push#usage "使用法 - Web プッシュ |NPM"  

[ProgressiveWebApps]: https://pwa.rocks "段階的な Web アプリ"  

[PugAttributes]: https://pugjs.org/language/attributes.html "属性 |Pug"  

[PwaBuilder]: https://www.pwabuilder.com "PWA Builder"  
[PwaBuilderAppImageGenerator]: https://www.pwabuilder.com/imageGenerator "アプリ イメージ ジェネレーター"  
[PwaBuilderServiceWorker]: https://www.pwabuilder.com/serviceworker "サービス ワーカー |PWA Builder"  

[ServiceWorkerCookbook]: https://serviceworke.rs "ServiceWorker Cookbook"  
[ServiceWorkerCookbookPushRichDemo]: https://serviceworke.rs/push-rich_demo.html "プッシュ リッチ デモ |ServiceWorker Cookbook"  

[W3cWebAppManifest]: https://www.w3.org/TR/appmanifest "Web アプリ マニフェスト |W3C"  

[Webhint]: https://sonarwhal.com "webhint は、Web のベスト プラクティスに関するヒントエンジンです。" 
 
[MDNWebWorkers]: https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers "Web ワーカーの使用" 

[WebDevProgressiveWebApps]: https://developers.google.com/web/progressive-web-apps "段階的な Web アプリ |web.dev"  

[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS |Wikipedia"  
[WikiProgressiveEnhancement]: https://en.wikipedia.org/wiki/Progressive_enhancement "段階的な機能強化 |Wikipedia"  
