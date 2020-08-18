---
description: このガイドでは、Windows でプログレッシブ web アプリを構築するための PWA の基本とツールの概要について説明します。
title: プログレッシブ Web アプリの使用を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: プログレッシブ web アプリ、PWA、Edge、Windows、PWABuilder、web マニフェスト、サービスワーカー、プッシュ
ms.openlocfilehash: 84d7c753cfece1591348e06b6728939187e37482
ms.sourcegitcommit: ef6d6adae1f4d18a219fa3e17f91b95b40367a40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "10934906"
---
# <span data-ttu-id="46d85-104">プログレッシブ Web アプリの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="46d85-104">Get started with Progressive Web Apps</span></span>  

<span data-ttu-id="46d85-105">プログレッシブ Web アプリ \ (PWAs \) は、ホーム画面のインストール、オフラインサポート、プッシュ通知などのプラットフォームやブラウザーエンジンでのネイティブアプリのような機能によって [段階的に強化][WikiProgressiveEnhancement] された web アプリです。</span><span class="sxs-lookup"><span data-stu-id="46d85-105">Progressive Web Apps \(PWAs\) are simply web apps that are [progressively enhanced][WikiProgressiveEnhancement] with native app-like features on supporting platforms and browser engines, such as launch-from-homescreen installation, offline support, and push notifications.</span></span>  <span data-ttu-id="46d85-106">Microsoft Edge \ (EdgeHTML \) エンジンを搭載した Windows 10 では、ブラウザーウィンドウを [ユニバーサル Windows プラットフォーム][WindowsUwpGetStartedWhat] アプリとして実行することによって、pwas の機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="46d85-106">On Windows 10 with the Microsoft Edge \(EdgeHTML\) engine, PWAs enjoy the added advantage of running independently of the browser window as [Universal Windows Platform][WindowsUwpGetStartedWhat] apps.</span></span>  

<span data-ttu-id="46d85-107">このガイドでは、 `localhost` Microsoft Visual Studio といくつかの Pwa ビルダーユーティリティを使って、pwa としてシンプルな web アプリを作成することによって、pwa の基本的な概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="46d85-107">This guide gives you an overview of PWA basics by building a simple `localhost` web app as a PWA using Microsoft Visual Studio and some PWA Builder utilities.</span></span>  <span data-ttu-id="46d85-108">完成した製品は、PWAs をサポートするすべてのブラウザーで同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="46d85-108">The finished product works similarly across any browser that supports PWAs.</span></span>  

> [!TIP]
> <span data-ttu-id="46d85-109">既存のサイトを PWA に変換して、Windows 10 およびその他のアプリプラットフォーム用にパッケージ化する簡単な方法については、「 [Pwa ビルダー][PwaBuilder]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46d85-109">For a quick way to convert an existing site to a PWA and package it for Windows 10 and other app platforms, review [PWA Builder][PwaBuilder].</span></span>  

## <span data-ttu-id="46d85-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="46d85-110">Prerequisites</span></span>  

<span data-ttu-id="46d85-111">PWAs は、どの web 開発 IDE でも構築できます。</span><span class="sxs-lookup"><span data-stu-id="46d85-111">You may build PWAs with any web development IDE.</span></span>  <span data-ttu-id="46d85-112">次に示すのは、Windows 開発者エコシステムでの PWA ツールのサポートについて説明する、このガイドの前提条件のみです。</span><span class="sxs-lookup"><span data-stu-id="46d85-112">The following are only prerequisites for this guide, which walks you through PWA tooling support in the Windows developer ecosystem.</span></span>  

*   <span data-ttu-id="46d85-113">\ (無料版) の [Visual Studio コミュニティ 2017][VisualStudioDownloads]をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="46d85-113">Download the \(free\) [Visual Studio Community 2017][VisualStudioDownloads].</span></span>  <span data-ttu-id="46d85-114">プロフェッショナル、エンタープライズ、または [プレビュー][VisualStudioPreview] の各エディションを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="46d85-114">You may also use the Professional, Enterprise, or [Preview][VisualStudioPreview] editions.</span></span>  <span data-ttu-id="46d85-115">Visual Studio インストーラーで、次のワークロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="46d85-115">From the Visual Studio Installer, choose the following Workloads.</span></span>  
    
    *   **<span data-ttu-id="46d85-116">ユニバーサル Windows プラットフォーム開発</span><span class="sxs-lookup"><span data-stu-id="46d85-116">Universal Windows Platform development</span></span>**  
    *   **<span data-ttu-id="46d85-117">Node.js 開発</span><span class="sxs-lookup"><span data-stu-id="46d85-117">Node.js development</span></span>**  

## <span data-ttu-id="46d85-118">基本的な web アプリをセットアップする</span><span class="sxs-lookup"><span data-stu-id="46d85-118">Set up a basic web app</span></span>  

<span data-ttu-id="46d85-119">わかりやすくするために、Visual Studio [Node.js とエクスプレスアプリ][VisualStudioNodeJsTutorial] テンプレートを使用して、ページを構成する web アプリを作成し `localhost` `index.html` ます。</span><span class="sxs-lookup"><span data-stu-id="46d85-119">For the sake of simplicity, use the Visual Studio [Node.js and Express app][VisualStudioNodeJsTutorial] template to create `localhost` web app that serves up an `index.html` page.</span></span>  <span data-ttu-id="46d85-120">これは、PWA として開発する、魅力的で多機能なフル機能の web アプリのプレースホルダーとして考えることができます。</span><span class="sxs-lookup"><span data-stu-id="46d85-120">Imagine this as a placeholder for the compelling, full-featured web app that you are developing as a PWA.</span></span>  

1.  <span data-ttu-id="46d85-121">Visual Studio を起動し、新しいプロジェクトを開始します。</span><span class="sxs-lookup"><span data-stu-id="46d85-121">Launch Visual Studio, and start a new project.</span></span>  
    *   <span data-ttu-id="46d85-122">**ファイル**  > **新規**  > **プロジェクト**</span><span class="sxs-lookup"><span data-stu-id="46d85-122">**File** > **New** > **Project...**</span></span>  
    *   `Ctrl`+`Shift`+`N`  
1.  <span data-ttu-id="46d85-123">[ **JavaScript**] で、[ **Basic Node.js Express 4 アプリケーション**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="46d85-123">Under **JavaScript**, select **Basic Node.js Express 4 Application**.</span></span>  <span data-ttu-id="46d85-124">名前と場所を設定して、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="46d85-124">Set the name and location and choose **OK**.</span></span>  
    
    ![Visual Studio で Node.js Express 4 プロジェクトテンプレートを選択する][ImageVsNodejsExpressTemplate]  
    
1.  <span data-ttu-id="46d85-126">新しいプロジェクトが読み込まれたら、[**ビルド**\ (\)] を選択 `Ctrl` + `Shift` + `B` して、「(\) の**デバッグを開始**し `F5` ます。</span><span class="sxs-lookup"><span data-stu-id="46d85-126">Once your new project loads, choose **Build** \(`Ctrl`+`Shift`+`B`\) and **Start Debugging** \(`F5`\).</span></span>  <span data-ttu-id="46d85-127">参照するときにファイルが読み込まれることを確認し `index.html` `http://localhost:1337` ます。</span><span class="sxs-lookup"><span data-stu-id="46d85-127">Verify that your `index.html` file loads when you browse to `http://localhost:1337`.</span></span>  
    
    ![新しいサイトを localhost で実行する][ImageVsNodejsExpressIndex]  

## <span data-ttu-id="46d85-129">アプリを PWA にする</span><span class="sxs-lookup"><span data-stu-id="46d85-129">Turn your app into a PWA</span></span>  

<span data-ttu-id="46d85-130">ここで、web アプリの基本的な [PWA 要件][PwaEdgehtmlIndexRequirements] ( *web アプリマニフェスト*、 *HTTPS* 、 *サービスワーカー*) を作成します。</span><span class="sxs-lookup"><span data-stu-id="46d85-130">Now it is time to wire up the basic [PWA requirements][PwaEdgehtmlIndexRequirements] for your web app: a *Web App Manifest*, *HTTPS* and *Service Workers*.</span></span>  

### <span data-ttu-id="46d85-131">Web アプリマニフェスト</span><span class="sxs-lookup"><span data-stu-id="46d85-131">Web App Manifest</span></span>  

<span data-ttu-id="46d85-132">[Web アプリマニフェスト][MDNWebAppManifest]は、アプリについて説明する JSON メタデータファイルです。名前、作成者、エントリページの URL、1つまたは複数のアイコンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="46d85-132">A [Web App Manifest][MDNWebAppManifest] is a JSON metadata file describing your app, including the name, author, entry page URL, and one or more icons.</span></span>  <span data-ttu-id="46d85-133">[標準ベースのスキーマ][W3cWebAppManifest]に従っているため、pcl がサポートされているプラットフォーム、OS、およびデバイスの組み合わせにインストールする1つの web アプリマニフェストのみを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d85-133">Because it follows a [standards-based schema][W3cWebAppManifest], you must only supply a single web app manifest for the PWA that you are installing on any platform, OS, and device combination that supports PWAs.</span></span>  <span data-ttu-id="46d85-134">Windows エコシステムでは、自分の PWA が [Microsoft Store][PwaEdgehtmlMicrosoftStore]に自動追加の候補として表示されるように、web アプリマニフェストが Bing web インデクサーに通知されます。ここでは、windows 10 アプリとして、約7億のアクティブなユーザーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="46d85-134">In the Windows ecosystem, your web app manifest signals to the Bing web indexer that your PWA is a candidate for automatic inclusion in the [Microsoft Store][PwaEdgehtmlMicrosoftStore], where it may reach nearly 700 million active monthly users as a Windows 10 app.</span></span>  

<span data-ttu-id="46d85-135">既存のライブサイトの場合は、 [PWA ビルダー][PwaBuilder]を使って web アプリマニフェストを生成できます。</span><span class="sxs-lookup"><span data-stu-id="46d85-135">If this were an existing live site, you may generate a web app manifest using [PWA Builder][PwaBuilder].</span></span>  <span data-ttu-id="46d85-136">まだ未公開のプロジェクトであるため、サンプルマニフェストをコピーしてください。</span><span class="sxs-lookup"><span data-stu-id="46d85-136">Since it is still an unpublished project, copy a sample manifest.</span></span>  

1.  <span data-ttu-id="46d85-137">Visual Studio*ソリューションエクスプローラー*で、*パブリック*フォルダーを右クリックし、[新しいファイルの**追加**...] を選択し  >  **New File...** `manifest.json` て、項目名として指定します。</span><span class="sxs-lookup"><span data-stu-id="46d85-137">In the Visual Studio *Solution Explorer*, right-click the *public* folder and select **Add** > **New File...**, specifying `manifest.json` as the item name.</span></span>  
1.  <span data-ttu-id="46d85-138">ファイルで `manifest.json` 、次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="46d85-138">In the `manifest.json` file, copy the following code.</span></span>  

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
    
    <span data-ttu-id="46d85-139">実際の PWA では、次の手順では、 *名前*、 *start_url*、 *short_name*、 *説明*、 *アイコン* をカスタマイズします (アイコンについては、次の手順で説明します)。</span><span class="sxs-lookup"><span data-stu-id="46d85-139">In a real PWA, the next step is to customize *name*, *start_url*, *short_name*, *description*, and *icons* \(icons are covered in the next step\).</span></span>  
    
    <span data-ttu-id="46d85-140">さまざまなメンバー値と関連の目的について詳しくは、「 [Web アプリマニフェスト][MDNWebAppManifest] のリファレンス」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="46d85-140">To learn more about the different member values and associated purposes, see the [Web App Manifest][MDNWebAppManifest] reference.</span></span>  
    
1.  <span data-ttu-id="46d85-141">次に、 `icons` PWA ビルダーアプリのイメージジェネレーターを使って、空の配列に実際の画像パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="46d85-141">Next, fill in the empty `icons` array with actual image paths by using the PWA Builder App Image Generator.</span></span>  
    
    1.  <span data-ttu-id="46d85-142">Web ブラウザーを使用して、次の [サンプル 512x512 PWA イメージ][ImagePwa]をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="46d85-142">Using a web browser, download this [sample 512x512 PWA image][ImagePwa].</span></span>  
    1.  <span data-ttu-id="46d85-143">PWA ビルダー [アプリのイメージジェネレーター][PwaBuilderAppImageGenerator]に移動し `pwa.png` て、 **入力イメージ** として保存した画像を選択し、[ **ダウンロード** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="46d85-143">Go to the PWA Builder [App Image Generator][PwaBuilderAppImageGenerator], and select the `pwa.png` image you just saved as the **Input Image** and then choose the **Download** button.</span></span>  
    1.  <span data-ttu-id="46d85-144">Zip ファイルを**開い**て**抽出**します。</span><span class="sxs-lookup"><span data-stu-id="46d85-144">**Open** and **Extract** the zip file.</span></span>  
    1.  <span data-ttu-id="46d85-145">Visual Studio ソリューションエクスプローラーで、フォルダーを右クリック `public` し、 **エクスプローラーでフォルダーを開き**ます。</span><span class="sxs-lookup"><span data-stu-id="46d85-145">In the Visual Studio Solution Explorer, right-click the `public` folder and **Open Folder in File Explorer**.</span></span>  <span data-ttu-id="46d85-146">という名前の **新しいフォルダー** を作成 `images` します。</span><span class="sxs-lookup"><span data-stu-id="46d85-146">Create a **New folder** named `images`.</span></span>  
    1.  <span data-ttu-id="46d85-147">抽出した zip からフォルダーにすべてのプラットフォームフォルダー \ (、など) をコピーして、[ `android` `chrome` `windows10` `images` ファイルエクスプローラー] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="46d85-147">Copy all of the platform folders \(`android`, `chrome`, `windows10`, and so on\) from your extracted zip to the `images` folder and close the file explorer window.</span></span>  <span data-ttu-id="46d85-148">フォルダーを Visual Studio プロジェクトに追加します (ソリューションエクスプローラーで、フォルダーを右クリックし、 `images` [既存のフォルダーの**追加**] を選択します  >  **Existing folder...** )。</span><span class="sxs-lookup"><span data-stu-id="46d85-148">Add the folders to your Visual Studio project \(in Solution Explorer, right-click `images` folder and select **Add** > **Existing folder...** for each of the folders\).</span></span>  
    1.  <span data-ttu-id="46d85-149">抽出した zip からファイルを (Visual Studio または任意のエディターを使って) 開いて、 `icons.json` `"icons": [...]` プロジェクトのファイルに配列をコピーし `manifest.json` ます。</span><span class="sxs-lookup"><span data-stu-id="46d85-149">Open \(with Visual Studio or any editor\) the `icons.json` file from the extracted zip and copy the `"icons": [...]` array into the `manifest.json` file of your project.</span></span>  

1.  <span data-ttu-id="46d85-150">これで、web アプリマニフェストをアプリに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d85-150">Now you must associate your web app manifest with your app.</span></span>  <span data-ttu-id="46d85-151">`layout.pug`ファイル \ ( `views` フォルダー \) を編集用に開き、[スタイルシート] リンクの直後にこの行を追加します。</span><span class="sxs-lookup"><span data-stu-id="46d85-151">Open the `layout.pug` file \(in `views` folder\) for editing, and add this line right after the stylesheet link.</span></span>  <span data-ttu-id="46d85-152">\ (単なるノード [pug][PugAttributes] テンプレート略記 `<link rel='manifest' href='/manifest.json'>` )。</span><span class="sxs-lookup"><span data-stu-id="46d85-152">\(It is simply the Node [pug][PugAttributes] template shorthand for `<link rel='manifest' href='/manifest.json'>`\).</span></span>  
    
    ```html
    link(rel='manifest', href='/manifest.json')
    ```  
    
<span data-ttu-id="46d85-153">これまでと同じように、web アプリが、マニフェストとホーム画面対応のアプリのアイコンを提供しています。</span><span class="sxs-lookup"><span data-stu-id="46d85-153">With all that in place, your web app is now serving up a manifest and homescreen-ready app icons!</span></span>  <span data-ttu-id="46d85-154">アプリ \ ( `F5` \) を実行して、マニフェストを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="46d85-154">Try running your app \(`F5`\) and loading up the manifest.</span></span>  

![Localhost からの Web アプリマニフェストの読み込み][ImageVsNodejsExpressManifest]  

<span data-ttu-id="46d85-156">アイコンの1つを選びます。</span><span class="sxs-lookup"><span data-stu-id="46d85-156">And one of your icons.</span></span>  

![Localhost からの Square71x71Logo アプリロゴの読み込み][ImageVsNodejsExpressIcon]  

<span data-ttu-id="46d85-158">(実際の \) アプリを公開している場合 `start_url` 、Bing 検索エンジンは、インストール可能な Windows 10 アプリとして [Microsoft Store への自動パッケージと申請][PwaEdgehtmlMicrosoftStore] の候補として識別されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="46d85-158">If you publish the app live \(with an actual `start_url`\), the Bing search engine now identifies it as a candidate for [automatic packaging and submission to the Microsoft Store][PwaEdgehtmlMicrosoftStore] as an installable Windows 10 app.</span></span>  <span data-ttu-id="46d85-159">ファイルの manifest.jsには、次の項目を含む Bing スキャン用の [プログレッシブ Web アプリの品質シグナル][WindowsBlogsPwaEdge] が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="46d85-159">Ensure that your manifest.json file includes the [Quality signals for Progressive Web Apps][WindowsBlogsPwaEdge] for which Bing scans including the following items.</span></span>   

*   `name`  
*   `description`  
*   <span data-ttu-id="46d85-160">少なくとも1つのアイコン (512 px 四方以上) \ (アプリのスプラッシュ画面を自動生成するための十分な解像度の画像ソース、ストア登録情報、タイル画像など)。</span><span class="sxs-lookup"><span data-stu-id="46d85-160">At least one icon 512px square or larger \(to ensure an image source of sufficient resolution for auto-generating the splash screen of your app, store listing, tile image, and so on\).</span></span>  

<span data-ttu-id="46d85-161">さらに、 [HTTPS](#https)、 [サービス員](#service-workers)、 [Microsoft ストアのポリシー][LegalWindowsAgrementsMicrosoftStorePolicies]に準拠することもできます。</span><span class="sxs-lookup"><span data-stu-id="46d85-161">In addition, use [HTTPS](#https), [service workers](#service-workers), and comply with [Microsoft Store Policies][LegalWindowsAgrementsMicrosoftStorePolicies].</span></span>  

### <span data-ttu-id="46d85-162">HTTPS</span><span class="sxs-lookup"><span data-stu-id="46d85-162">HTTPS</span></span>  

<span data-ttu-id="46d85-163">[サービスワーカーと、][MDNServiceWorkerApi] service Worker ( [キャッシュ][MDNCache]、 [プッシュ][MDNPushApi]、 [バックグラウンド同期][MDNSyncManager] api など) で動作する PWA テクノロジはセキュリティで保護された接続にのみ機能します。これは、ライブサイトまたはデバッグ目的で [HTTPS][WikiHttps] を意味 `localhost` します。</span><span class="sxs-lookup"><span data-stu-id="46d85-163">[Service Workers][MDNServiceWorkerApi] and other key PWA technologies that work with service workers \(such as the [Cache][MDNCache], [Push][MDNPushApi], and [Background Sync][MDNSyncManager] APIs\) only work across secure connections, which means [HTTPS][WikiHttps] for live sites or `localhost` for debugging purposes.</span></span>  

<span data-ttu-id="46d85-164">[この web アプリを実際のサイトとして発行][VisualStudioNodejsTutorialPublishAzureAppService]する場合 (たとえば、 [Azure free アカウント][AzureCreateFreeAccount]をセットアップした場合) は、サーバーが HTTPS 用に構成されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d85-164">If you [publish this web app as a live site][VisualStudioNodejsTutorialPublishAzureAppService] \(for example, by setting up an [Azure free account][AzureCreateFreeAccount]\), you must ensure your server is configured for HTTPS.</span></span>  <span data-ttu-id="46d85-165">[Microsoft Azure App Service][AzureWebApps]を使ってサイトをホストしている場合、既定では HTTPS 経由で提供されます。</span><span class="sxs-lookup"><span data-stu-id="46d85-165">If you use the [Microsoft Azure App Service][AzureWebApps] to host your site, it is served over HTTPS by default.</span></span>  

<span data-ttu-id="46d85-166">このガイドでは、稼働中の `http://localhost` ライブサイトのプレースホルダーとして引き続き使用 `https://` します。</span><span class="sxs-lookup"><span data-stu-id="46d85-166">For this guide, continue using `http://localhost` as a placeholder for a live site served over `https://`.</span></span>  

### <span data-ttu-id="46d85-167">サービス ワーカー</span><span class="sxs-lookup"><span data-stu-id="46d85-167">Service Workers</span></span>  

<span data-ttu-id="46d85-168">サービスワーカーは、PWAs の主要テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="46d85-168">Service Workers is the key technology behind PWAs.</span></span> <span data-ttu-id="46d85-169">サービスワーカーは、PWA とネットワークの間のプロキシとして機能し、web サイトが、オフラインシナリオを処理し、サーバープッシュ通知に応答し、バックグラウンドタスクを実行するインストール済みのネイティブアプリとして機能することを可能にします。</span><span class="sxs-lookup"><span data-stu-id="46d85-169">Service Workers act as a proxy between your PWA and the network to enable your website to function as an installed native app that serves up offline scenarios, responds to server push notifications, and runs background tasks.</span></span>  <span data-ttu-id="46d85-170">サービス担当者には、新しいパフォーマンス戦略も開かれます。</span><span class="sxs-lookup"><span data-stu-id="46d85-170">Service workers also open up new performance strategies.</span></span>  <span data-ttu-id="46d85-171">Web サイトのページ読み込みパフォーマンスを微調整するために、サービスワーカーキャッシュを使用するために、完全な web アプリを実装する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="46d85-171">You are not required to implement a full web app to use the service worker cache for fine-tuned page load performance for your website.</span></span>  

<span data-ttu-id="46d85-172">サービスワーカーは、web アプリを起動する通常のスクリプトと共に対応する JavaScript ファイルから実行されるイベント駆動型のバックグラウンドスレッドです。</span><span class="sxs-lookup"><span data-stu-id="46d85-172">Service workers are event-driven background threads that run from JavaScript files served up alongside the regular scripts that power your web app.</span></span>  <span data-ttu-id="46d85-173">サービスワーカーはメイン UI スレッドでは実行されないため、 [ui スレッド][MDNWorkerPrototypePostMessage] と [ワーカースレッド][MDNDedicatedWorkerGlobalScopePostMessage] は、 `postMessage()` およびイベントハンドラーを使って通信できますが、その場合、サービスワーカーには DOM アクセスはありません `onmessage` 。</span><span class="sxs-lookup"><span data-stu-id="46d85-173">Because Service workers do not run on the main UI thread, service workers do not have DOM access, though the [UI thread][MDNWorkerPrototypePostMessage] and a [worker thread][MDNDedicatedWorkerGlobalScopePostMessage] is able to communicate using `postMessage()` and `onmessage` event handlers.</span></span>  

<span data-ttu-id="46d85-174">サービスワーカーを、サイトの URL の起点 (またはその中の指定したパス) に登録することで、アプリに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="46d85-174">You associate a service worker with your app by registering it to the URL origin of your site \(or a specified path within it\).</span></span>  <span data-ttu-id="46d85-175">登録が完了すると、service worker ファイルが、ユーザーのコンピューターにダウンロード、インストール、アクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="46d85-175">Once registered, the service worker file is then downloaded, installed, and activated on the user machine.</span></span>  <span data-ttu-id="46d85-176">さらに、MDN web ドキュメントには、 [サービスワーカー][MDNUsingServiceWorkers] と詳細な [service worker API][MDNServiceWorkerApi] リファレンスの包括的なガイドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="46d85-176">For more, MDN web docs has a comprehensive guide on [Using Service Workers][MDNUsingServiceWorkers] and a detailed [Service Worker API][MDNServiceWorkerApi] reference.</span></span>  

<span data-ttu-id="46d85-177">このチュートリアルでは、 [PWA ビルダー][PwaBuilderServiceWorker]でオフラインページサービスワーカースクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="46d85-177">For this tutorial, use the Offline page service worker script on [PWA Builder][PwaBuilderServiceWorker].</span></span>  <span data-ttu-id="46d85-178">パフォーマンス要件、ネットワーク帯域幅などに応じて、より多くの機能を備えたスクリプトをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="46d85-178">Start by customizing the script with more functionality according to your performance requirements, network bandwidth, and so on.</span></span>  <span data-ttu-id="46d85-179">Mozilla が提供する [サービス][ServiceWorkerCookbook]  の担当者を確認して、いくつかの便利なサービス作業者のキャッシュアイデアを確認してください。</span><span class="sxs-lookup"><span data-stu-id="46d85-179">Review the [Service Worker Cookbook][ServiceWorkerCookbook]  provided by Mozilla for a number of useful service worker caching ideas.</span></span>  

1.  <span data-ttu-id="46d85-180">[https://www.pwabuilder.com/serviceworker][PwaBuilderServiceWorker]\ (既定の)**オフラインページ**サービスワーカーを開いて選択し、[**サービスワーカーのダウンロード**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d85-180">Open [https://www.pwabuilder.com/serviceworker][PwaBuilderServiceWorker] and select the \(default\) **Offline page** service worker and click the **Download service worker** button.</span></span>  
1.  <span data-ttu-id="46d85-181">[ダウンロード] フォルダーを開いて、次の2つのファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="46d85-181">Open the download folder and copy the following two files</span></span>  

    *   <span data-ttu-id="46d85-182">ServiceWorker1\pwabuilder-sw-register.js</span><span class="sxs-lookup"><span data-stu-id="46d85-182">ServiceWorker1\pwabuilder-sw-register.js</span></span>  
    *   <span data-ttu-id="46d85-183">ServiceWorker1\pwabuilder-sw.js</span><span class="sxs-lookup"><span data-stu-id="46d85-183">ServiceWorker1\pwabuilder-sw.js</span></span>  
    
    <span data-ttu-id="46d85-184">`public`Visual Studio web app プロジェクトのフォルダーにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="46d85-184">Save the files to the `public` folder of your Visual Studio web app project.</span></span>  <span data-ttu-id="46d85-185">\ (Visual Studio から、エクスプローラーを使っ `Ctrl` + `O` てプロジェクトを開き、フォルダーに移動し `public` ます)。</span><span class="sxs-lookup"><span data-stu-id="46d85-185">\(From Visual Studio, use `Ctrl`+`O` to open file explorer to your project and navigate to the `public` folder\).</span></span>  
    
    <span data-ttu-id="46d85-186">ソリューションエクスプローラーで、 `public/pwabuilder-sw.js` ファイルを開き、の値 `offlineFallbackPage` をに変更し `offline.html` ます。</span><span class="sxs-lookup"><span data-stu-id="46d85-186">In Solution Explorer, open the `public/pwabuilder-sw.js` file, and change the value of `offlineFallbackPage` to `offline.html`.</span></span>  
    
    ```javascript
    const offlineFallbackPage = "offline.html";
    ```
    
    <span data-ttu-id="46d85-187">この2つのファイルの両方のコードを確認して、指定したページをキャッシュし、ネットワークの取得に失敗したときにそのサービスを提供するサービスワーカーを登録する方法について説明し `offline.html` ます。</span><span class="sxs-lookup"><span data-stu-id="46d85-187">It is worth reviewing the code in both of these files, to get the gist of how to register a service worker that caches a designated page \(`offline.html`\) and serves it when a network fetch fails.</span></span>  <span data-ttu-id="46d85-188">次に、 `offline.html` アプリのオフライン機能のプレースホルダーとして簡単なページを作成します。</span><span class="sxs-lookup"><span data-stu-id="46d85-188">Next, create a simple `offline.html` page as a placeholder for the offline functionality of your app.</span></span>  
    
1.  <span data-ttu-id="46d85-189">ソリューションエクスプローラーで、 `views/layout.pug` ファイルを開き、リンクタグの下に次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="46d85-189">In Solution Explorer, open the `views/layout.pug` file, and add the following line below your link tags.</span></span>  
    
    ```html
    script(src='/pwabuilder-sw-register.js' type='module')
    ```  
    
    <span data-ttu-id="46d85-190">サイトがサービスワーカー登録スクリプトを読み込んで実行します。</span><span class="sxs-lookup"><span data-stu-id="46d85-190">Your site loads and runs your service worker registration script.</span></span>  
    
1.  <span data-ttu-id="46d85-191">ソリューションエクスプローラーで、フォルダーを右クリックし、 `public` [ **Add**  >  **新しいファイル**の追加...] を選択します。 次のコードのように、その名前を入力し、 `offline.html` `<title>` 本文の内容をいくつか追加します。</span><span class="sxs-lookup"><span data-stu-id="46d85-191">In Solution Explorer, right-click on the `public` folder and select **Add** > **New File...**.  Name it `offline.html`, and add a `<title>` and some body content, for example the following code.</span></span>  
    
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
    
    <span data-ttu-id="46d85-192">この時点で、フォルダーには `public` 3 つの新しいファイルが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d85-192">At this point, your `public` folder should have three new files.</span></span>  
    
    ![ソリューションのパブリックフォルダーに追加されたファイル][ImageVsNodejsExpressPublic]  
    
1.  <span data-ttu-id="46d85-194">ソリューションエクスプローラーで、 `routes\index.js` ファイルを開き、最後のコマンド \ (\) の直前に次のコードを追加し `module.exports = router;` ます。</span><span class="sxs-lookup"><span data-stu-id="46d85-194">In Solution Explorer, open the `routes\index.js` file, and add the following code just before the final command \(`module.exports = router;`\).</span></span>  
    
    ```javascript
    router.get('/offline.html', function (req, res) {
        res.sendFile('public/offline.html');
    });
    ```  
    
    <span data-ttu-id="46d85-195">これにより、アプリは `offline.html` (サービスワーカーがオフラインキャッシュ用にファイルを取得するときに) ファイルを提供するように指示されます。</span><span class="sxs-lookup"><span data-stu-id="46d85-195">This instructs your app to serve the `offline.html` file \(when your service worker fetches it for the offline cache\).</span></span>  
    
1.  <span data-ttu-id="46d85-196">PWA をテストする</span><span class="sxs-lookup"><span data-stu-id="46d85-196">Test out your PWA!</span></span>  <span data-ttu-id="46d85-197">`Ctrl` + `Shift` + `B` Microsoft Edge を起動してページを開くには、\ (\) をビルドし、 `F5` web アプリを実行し `localhost` ます。</span><span class="sxs-lookup"><span data-stu-id="46d85-197">Build \(`Ctrl`+`Shift`+`B`\) and Run \(`F5`\) your web app to launch Microsoft Edge and open your `localhost` page.</span></span>  <span data-ttu-id="46d85-198">次に、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="46d85-198">Then complete the following steps.</span></span>  
    
    1.  <span data-ttu-id="46d85-199">Edge devtools**コンソール**\ ( `Ctrl` + `Shift` + `J` \) を開き、サービスワーカーが登録されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="46d85-199">Open the Edge DevTools **Console** \(`Ctrl`+`Shift`+`J`\) and verify the Service worker was registered.</span></span>  
    1.  <span data-ttu-id="46d85-200">**デバッガ**パネルで、[ **Service worker** ] コントロールを展開し、原点をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d85-200">In the **Debugger** panel, expand the **Service Workers** control and click on your origin.</span></span>  <span data-ttu-id="46d85-201">**サービスワーカーの概要**で、サービスワーカーがアクティブ化され、実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="46d85-201">In the **Service Worker Overview**, verify your service worker is activated and running.</span></span>  
        
        ![Edge DevTools サービスワーカーの概要][ImageDevtoolsSwOverview]  
        
    1.  <span data-ttu-id="46d85-203">**キャッシュ**コントロールを展開して、 `offline.html` ページがキャッシュされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="46d85-203">Expand the **Cache** control and verify that the `offline.html` page is cached.</span></span>  
        
        ![Edge DevTools サービスワーカーキャッシュ][ImageDevtoolsSwCache]  
        
1.  <span data-ttu-id="46d85-205">PWA をオフラインアプリとして試す時間</span><span class="sxs-lookup"><span data-stu-id="46d85-205">Time to try your PWA as an offline app!</span></span>  <span data-ttu-id="46d85-206">Visual Studio で、web アプリの**デバッグを停止** `Shift` + `F5` して、Microsoft Edge \ (または [更新]) を web サイトの localhost アドレスに開きます。</span><span class="sxs-lookup"><span data-stu-id="46d85-206">In Visual Studio, **Stop Debugging** \(`Shift`+`F5`\) your web app, then open Microsoft Edge \(or refresh\) to the localhost address of your website.</span></span>  <span data-ttu-id="46d85-207">これでページを読み込むことが `offline.html` できます (サービスワーカーとオフラインキャッシュに感謝します)。</span><span class="sxs-lookup"><span data-stu-id="46d85-207">It should now load the `offline.html` page \(thanks to your service worker and offline cache\)!</span></span>  
    
    ![http://localhost:1337Microsoft Edge で offline.html を読み込む][ImageOfflineHtml]  

## <span data-ttu-id="46d85-209">プッシュ通知を追加する</span><span class="sxs-lookup"><span data-stu-id="46d85-209">Add push notifications</span></span>  

<span data-ttu-id="46d85-210">PWA をさらにアプリにするには、 [プッシュ API][MDNPushApi] を使ってメッセージサービスをサブスクライブするプッシュ通知のクライアント側サポートを追加し、 [通知 API][MDNNotificationsApi] を使ってメッセージの受信時にトーストメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="46d85-210">Make your PWA more app-like by adding client-side support for push notifications using the [Push API][MDNPushApi] to subscribe to a messaging service and the [Notifications API][MDNNotificationsApi] to display a toast message upon receiving a message.</span></span>  <span data-ttu-id="46d85-211">サービスワーカーの場合と同様に、これらはブラウザー間で動作する標準ベースの Api であるため、コードを1回記述するだけで、すべての機能がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="46d85-211">As with Service Workers, these are standards-based APIs that work cross-browser, so you only have to write the code once for it to work everywhere PWAs are supported.</span></span>  <span data-ttu-id="46d85-212">サーバー側で、 [Web プッシュ][NPMWebPush] ソースライブラリを使って、さまざまなブラウザーへのプッシュメッセージの配信に関連する違いを処理します。</span><span class="sxs-lookup"><span data-stu-id="46d85-212">On the server side, use the [Web-Push][NPMWebPush] open-source library to handle the differences involved in delivering push messages to various browsers.</span></span>  

<span data-ttu-id="46d85-213">以下は、Mozilla が提供する [Service Worker][ServiceWorkerCookbookPushRichDemo] のレシピのプッシュリッチデモに適用されています。これは、その他多くの便利な Web プッシュとサービス worker のレシピを確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="46d85-213">The following is adapted from the Push Rich Demo in [Service Worker Cookbook][ServiceWorkerCookbookPushRichDemo] provided by Mozilla, which is worth checking out for a number of other useful Web Push and service worker recipes.</span></span>  

### <span data-ttu-id="46d85-214">手順 1-NPM web プッシュライブラリをインストールする</span><span class="sxs-lookup"><span data-stu-id="46d85-214">Step 1 - Install the NPM web-push library</span></span>  

<span data-ttu-id="46d85-215">Visual Studio ソリューションエクスプローラーで、プロジェクトを右クリックし **Node.js 対話型のウィンドウを開く]** をクリックします。 次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="46d85-215">In Visual Studio Solution Explorer, right-click your project and **Open Node.js Interactive Window...**.  In it, type the following code.</span></span>  

```javascript
.npm install web-push
```  

<span data-ttu-id="46d85-216">これに [より、Web プッシュ][NPMWebPush] ライブラリがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="46d85-216">This installs the [Web-Push][NPMWebPush] library.</span></span>  <span data-ttu-id="46d85-217">次に、 `index.js` ファイルを開き、他の要件ステートメントの後に、ファイルの先頭に次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="46d85-217">Then, open up your `index.js` file, and add the following line to the top of your file after the other requirement statements.</span></span>  

```javascript
var webpush = require('web-push');
```  

### <span data-ttu-id="46d85-218">手順 2-サーバーの VAPID キーを生成する</span><span class="sxs-lookup"><span data-stu-id="46d85-218">Step 2 - Generate VAPID keys for your server</span></span>  

<span data-ttu-id="46d85-219">次に、プッシュメッセージを PWA クライアントに送信するために、サーバーに対して VAPID を生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d85-219">Next you must generate VAPID \(Voluntary Application Server Identification\) keys for your server to send push messages to the PWA client.</span></span>  <span data-ttu-id="46d85-220">この操作は1回だけ実行する必要があります (つまり、サーバーでは VAPID keys の1つのペアしか必要ありません)。</span><span class="sxs-lookup"><span data-stu-id="46d85-220">You only have to do this once \(that is, your server only requires a single pair of VAPID keys\).</span></span>  <span data-ttu-id="46d85-221">対話型の Node.js ウィンドウで、次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="46d85-221">In the Node.js Interactive Window, type the following code.</span></span>  

```javascript
var webpush = require('web-push');
webpush.generateVAPIDKeys();
```  

<span data-ttu-id="46d85-222">出力結果として、公開キーと秘密キーを含む JSON オブジェクトが作成され、サーバーロジックにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="46d85-222">The output should result in a JSON object containing a public and private key, which you copy into your server logic.</span></span>  

<span data-ttu-id="46d85-223">ファイルの `index.js` 最終 \ (\) の直前に、 `module.exports = router` 次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="46d85-223">In your `index.js` file, just before the final  \(`module.exports = router`\) line, add the following code.</span></span>  

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

<span data-ttu-id="46d85-224">`publicKey`生成した and 値をコピーし `privateKey` ます。</span><span class="sxs-lookup"><span data-stu-id="46d85-224">Copy the `publicKey` and `privateKey` values that you just generated.</span></span>  <span data-ttu-id="46d85-225">アドレスは自由にカスタマイズでき `mailto` ます (ただし、このサンプルを実行するためには必須ではありません)。</span><span class="sxs-lookup"><span data-stu-id="46d85-225">Feel free to customize the `mailto` address as well \(though it is not required in order to run this sample\).</span></span>  

<span data-ttu-id="46d85-226">[Mozilla サービスエンジニアリングのブログ][MozillaServicesSendingVapidWebPushNotificationsPush]では、バックグラウンドでの機能について詳しく知りたい場合は、VAPID と webpush の優れた explainer をご利用ください。</span><span class="sxs-lookup"><span data-stu-id="46d85-226">The [Mozilla Services engineering blog][MozillaServicesSendingVapidWebPushNotificationsPush] has a nice explainer on VAPID and WebPush if you are interested in the details of how it works behind the scenes.</span></span>  

### <span data-ttu-id="46d85-227">手順 3-プッシュ関連のサーバー要求を処理する</span><span class="sxs-lookup"><span data-stu-id="46d85-227">Step 3 - Handle push-related server requests</span></span>  

<span data-ttu-id="46d85-228">それでは、VAPID 公開キーの提供、プッシュを受け取るクライアントの登録など、PWA クライアントからプッシュ関連の要求を処理するためのルートをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="46d85-228">Now set up routes for handling push-related requests from the PWA client, including serving up the VAPID public key and registering the client to receive pushes.</span></span>  

<span data-ttu-id="46d85-229">実際のシナリオでは、プッシュ通知はサーバーロジックのイベントから発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="46d85-229">In a real scenario, a push notification likely originates from an event in your server logic.</span></span>  <span data-ttu-id="46d85-230">ここで簡単にするために、PWA のホームページに **プッシュ通知** ボタンを追加して、skype のサーバーからプッシュを生成したり、 `/sendNotification` これらの要求を処理するためのエンドポイント \ (サーバールート) を作成したりする必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d85-230">To simplify things here, you must add a **Push Notification** button to our PWA homepage for generating pushes from our server, and a `/sendNotification` endpoint \(server route\)for handling those requests.</span></span>  

<span data-ttu-id="46d85-231">ファイル内に `index.js` 、追加した VAPID 初期化コードの直後に、[手順 2 #step] から [---の VAPID キーを生成します] の後に次のルートを追加します。</span><span class="sxs-lookup"><span data-stu-id="46d85-231">In your `index.js` file, append the following routes just after the VAPID initialization code you added in [Step 2][#step-2---generate-vapid-keys-for-your-server].</span></span>  

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

<span data-ttu-id="46d85-232">サーバー側のコードが配置されている場合は、PWA クライアントでプッシュ通知を plumb します。</span><span class="sxs-lookup"><span data-stu-id="46d85-232">With the server-side code in place, plumb in push notifications on the PWA client.</span></span>  

### <span data-ttu-id="46d85-233">手順 4-プッシュ通知への登録</span><span class="sxs-lookup"><span data-stu-id="46d85-233">Step 4 - Subscribe to push notifications</span></span>  

<span data-ttu-id="46d85-234">サービスワーカーは PWA ネットワークプロキシとしての役割の一部として、プッシュイベントとトースト通知操作を処理します。</span><span class="sxs-lookup"><span data-stu-id="46d85-234">As part of their role as PWA network proxies, service workers handle push events and toast notification interactions.</span></span>  <span data-ttu-id="46d85-235">ただし、初めて (または \ を登録する) サービスワーカーを設定するときに、PWA のプッシュ通知が pwa のメイン UI スレッドで行われ、ネットワーク接続が必要になります。</span><span class="sxs-lookup"><span data-stu-id="46d85-235">However, as it is with first setting up \(or registering\) a service worker, subscribing the PWA to server push notifications happens on the main UI thread of the PWA and requires network connectivity.</span></span>  <span data-ttu-id="46d85-236">プッシュ通知をサブスクライブするには、アクティブなサービスワーカーの登録が必要であるため、まずサービスワーカーがインストールされてアクティブであることを確認してから、プッシュ通知にサブスクライブしてください。</span><span class="sxs-lookup"><span data-stu-id="46d85-236">Subscribing to push notifications requires an active service worker registration, so you must first verify that your service worker is installed and active before trying to subscribe it to push notifications.</span></span>  

<span data-ttu-id="46d85-237">新しいプッシュサブスクリプションが作成される前に、Microsoft Edge では、ユーザーが通知を受信できるように PWA 権限を付与しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="46d85-237">Before a new push subscription is created, Microsoft Edge check if the user granted the PWA permission to receive notifications.</span></span>  <span data-ttu-id="46d85-238">許可されていない場合は、ブラウザーからアクセス許可を求められます。</span><span class="sxs-lookup"><span data-stu-id="46d85-238">If not, the user is prompted by the browser for permission.</span></span>  <span data-ttu-id="46d85-239">アクセス許可が拒否された場合は、a を例外とし `registration.pushManager.subscribe` `DOMException` て処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d85-239">If the permission is denied, the request to `registration.pushManager.subscribe` throws a `DOMException`, so you must handle it.</span></span>  <span data-ttu-id="46d85-240">権限の管理について詳しくは、「 [Microsoft Edge でのプッシュ通知][WindowsBlogsWebNotificationsEdge]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="46d85-240">For more on permission management, see [Push Notifications in Microsoft Edge][WindowsBlogsWebNotificationsEdge].</span></span>  

<span data-ttu-id="46d85-241">ファイルに `pwabuilder-sw-register.js` 次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="46d85-241">In your `pwabuilder-sw-register.js` file, append the following code.</span></span>  

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

<span data-ttu-id="46d85-242">Api のしくみおよび関連するさまざまなオプションの詳細については、 [「][NPMWebPushUsage] office online ライブラリの[pushmanager][MDNPushManager]インターフェイスと NPM ドキュメント」の MDN ドキュメントを確認してください。</span><span class="sxs-lookup"><span data-stu-id="46d85-242">Review the MDN documentation on the [PushManager][MDNPushManager] interface and NPM docs on the [Web-Push][NPMWebPushUsage] library for more details on how the APIs work and various related options.</span></span>  

### <span data-ttu-id="46d85-243">手順 5-プッシュと notificationclick クリックイベントハンドラーを設定する</span><span class="sxs-lookup"><span data-stu-id="46d85-243">Step 5 - Set up push and notificationclick event handlers</span></span>  

<span data-ttu-id="46d85-244">プッシュサブスクリプションを設定すると、残りの作業はサービスワーカーで行われます。</span><span class="sxs-lookup"><span data-stu-id="46d85-244">With our push subscription set up, the remainder of the work happens in the service worker.</span></span>  <span data-ttu-id="46d85-245">最初に、プッシュデータペイロードを表示する、サーバー側で送信されたプッシュイベントのハンドラーを設定して、トースト通知によって応答します (権限が付与されている場合)。</span><span class="sxs-lookup"><span data-stu-id="46d85-245">First you must set up a handler for server-sent push events, and respond with a toast notification \(if permission was granted\) displaying the push data payload.</span></span>  <span data-ttu-id="46d85-246">次に、トーストのクリックハンドラーを追加して通知を消去し、現在開いているウィンドウの一覧を並べ替えて、意図した PWA クライアントページを開き、フォーカスして、フォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="46d85-246">Next you add a click handler for the toast to dismiss the notification and sort through a list of currently open windows to open, focus, or open and focus the intended PWA client page.</span></span>  

<span data-ttu-id="46d85-247">ファイルで `pwabuilder-sw.js` 、次のハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="46d85-247">In your `pwabuilder-sw.js` file, append the following handlers.</span></span>  

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

### <span data-ttu-id="46d85-248">手順 6-お試しください</span><span class="sxs-lookup"><span data-stu-id="46d85-248">Step 6 - Try it out</span></span>  

<span data-ttu-id="46d85-249">PWA でプッシュ通知をテストする時間</span><span class="sxs-lookup"><span data-stu-id="46d85-249">Time to test push notifications in your PWA!</span></span>  

1.  <span data-ttu-id="46d85-250">`F5`ブラウザーで PWA (\) を実行します。</span><span class="sxs-lookup"><span data-stu-id="46d85-250">Run \(`F5`\) your PWA in the browser.</span></span>  <span data-ttu-id="46d85-251">サービスワーカーコード \ (\) を変更したので `pwabuilder-sw.js` 、DevTools デバッガー \ ( `F12` \) を **サービスワーカーの概要** パネルに開いて、サービスワーカーの **登録を解除** し `F5` 、ページを再登録する必要があります (または、[ **更新**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="46d85-251">Because you modified the service worker code \(`pwabuilder-sw.js`\), you must open the DevTools Debugger \(`F12`\) to the **Service Worker Overview** panel and **Unregister** the service worker and reload \(`F5`\) the page to re-register it \(or you click **Update**\).</span></span>  <span data-ttu-id="46d85-252">運用シナリオでは、ブラウザーは、service worker の更新プログラムが定期的にチェックされ、バックグラウンドで更新プログラムをインストールすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="46d85-252">In a production scenario, the browser checks regularly check for service worker updates and install the updates in the background.</span></span>  <span data-ttu-id="46d85-253">すぐに結果が得られるように、ここで強制する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d85-253">You should force it here for immediate results.</span></span>  
    
    <span data-ttu-id="46d85-254">サービスワーカーがアクティブ化して PWA のプッシュ通知をサブスクライブしようとすると、ページの下部に [アクセス許可] ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="46d85-254">As your service worker activates and attempts to subscribe your PWA to push notifications, you should see a permission dialog at the bottom of the page.</span></span>  
    
    ![通知を有効にするためのアクセス許可ダイアログ][ImageNotificationPermission]  
    
    <span data-ttu-id="46d85-256">**[はい]** を選択して、PWA のトースト通知を有効にします。</span><span class="sxs-lookup"><span data-stu-id="46d85-256">Choose **Yes** to enable toast notifications for your PWA.</span></span>  
    
1.  <span data-ttu-id="46d85-257">[Service Worker の概要] ウィンドウで、[  **プッシュ** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="46d85-257">From the Service Worker Overview pane, try choosing the  **Push** button.</span></span>  <span data-ttu-id="46d85-258">\ (DevTools "\) ペイロードからのハードコード付きの" テストプッシュメッセージ "というトースト通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="46d85-258">A toast notification with the \(hard-coded "Test push message from DevTools"\) payload should appear.</span></span>  
    
    ![DevTools から通知をプッシュする][ImageDevtoolsPush]  
    
1.  <span data-ttu-id="46d85-260">次に、PWA のホームページで [ **通知の送信** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="46d85-260">Next try choosing the **Send Notification** button on the homepage of your PWA.</span></span>  <span data-ttu-id="46d85-261">今回は、サーバーからのペイロードを使ってトーストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="46d85-261">This time a toast with the payload from your server appears.</span></span>  
    
    ![PWA サーバーから通知をプッシュする][ImagePwaPush]  
    
    <span data-ttu-id="46d85-263">トースト通知をオンにしない場合は、数秒後に非表示になり、Windows アクションセンターでキューに入れられます。</span><span class="sxs-lookup"><span data-stu-id="46d85-263">If you do not click \(or activate\) a toast notification, it is dismissed after several seconds and queue up in your Windows Action Center.</span></span>  
    
    ![Windows アクションセンターでの通知][ImageWindowsActionCenter]  
    
    <span data-ttu-id="46d85-265">PWA プッシュ通知の基本的な機能があります。</span><span class="sxs-lookup"><span data-stu-id="46d85-265">You have the basics of PWA push notifications.</span></span>  <span data-ttu-id="46d85-266">実際のアプリでは、次の手順は、プッシュサブスクリプションを管理および保存し、ネットワーク経由で送信されるペイロードデータを適切に [暗号化][NPMWebPushEncrypt] する方法で実装されています。</span><span class="sxs-lookup"><span data-stu-id="46d85-266">In a real app, the next steps are implemented in a way to manage and store push subscriptions and to properly [encrypt][NPMWebPushEncrypt] payload data being sent across the wire.</span></span>  
    
## <span data-ttu-id="46d85-267">追加情報</span><span class="sxs-lookup"><span data-stu-id="46d85-267">Going further</span></span>  

<span data-ttu-id="46d85-268">このガイドでは、Visual Studio、PWA ビルダー、Edge DevTools などのプログレッシブ Web アプリと Microsoft PWA 開発ツールの基本的な構造について説明します。</span><span class="sxs-lookup"><span data-stu-id="46d85-268">This guide demonstrated the basic anatomy of a Progressive Web App and Microsoft PWA development tools including Visual Studio, PWA Builder, and Edge DevTools.</span></span>  

<span data-ttu-id="46d85-269">もちろん、お客様には、応答性の高いデザイン、ディープリンク、[クロスブラウザーテスト][BrowserStackTestEdgeBrowser]などの[ベストプラクティス][Webhint](アプリの機能については説明しません) を含めて、ここで紹介した機能以外にも[pwa][PwaEdgehtmlIndexRequirements]を追加する必要があります。このガイドでは、pwa の基本的な概要と作業開始について説明します。</span><span class="sxs-lookup"><span data-stu-id="46d85-269">Of course, there is a lot more that goes into [making a great PWA][PwaEdgehtmlIndexRequirements] beyond what you read here, including responsive design, deep-linking, [cross-browser testing][BrowserStackTestEdgeBrowser] and other [best practices][Webhint] \(not to mention your app functionality!\), but hopefully this guide gave you a solid introduction of PWA basics and some ideas on getting started.</span></span>  <span data-ttu-id="46d85-270">Windows または Visual Studio での PWA 開発についてさらに質問がある場合は、コメントを残してください。</span><span class="sxs-lookup"><span data-stu-id="46d85-270">If you have further questions on PWA development with Windows or with Visual Studio, please leave a comment!</span></span>  

<span data-ttu-id="46d85-271">他の PWA ガイドを確認して、カスタマーエンゲージメントを向上させ、OS に統合されたアプリのエクスペリエンスをさらに向上させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="46d85-271">Review the other PWA guides to learn how to increase customer engagement and provide a more seamless, OS-integrated app experience.</span></span>  

*   <span data-ttu-id="46d85-272">[Windows の調整][PwaEdgehtmlWindowsFeatures]。</span><span class="sxs-lookup"><span data-stu-id="46d85-272">[Windows tailoring][PwaEdgehtmlWindowsFeatures].</span></span> <span data-ttu-id="46d85-273">簡単な機能の検出を使用すると、windows 10 ユーザー向けの PWA (Windows の [ **スタート** ] メニューのタイル通知とタスクバーの jumplists をカスタマイズするための方法、および \ (許可されている場合)、写真、音楽、予定表などのユーザーリソースの操作などの、windows 10 を実行しているユーザーを段階的に強化できます。</span><span class="sxs-lookup"><span data-stu-id="46d85-273">Using simple feature detection, you may progressively enhance your PWA for Windows 10 customers through native Windows Runtime \(WinRT\) APIs, such as those for customizing Windows **Start** menu tile notifications and taskbar jumplists, and \(upon permission\) working with user resources, such as photos, music, and calendar.</span></span>  
*   <span data-ttu-id="46d85-274">[Microsoft ストアで Pwas][PwaEdgehtmlMicrosoftStore]。</span><span class="sxs-lookup"><span data-stu-id="46d85-274">[PWAs in the Microsoft Store][PwaEdgehtmlMicrosoftStore].</span></span>  <span data-ttu-id="46d85-275">アプリストアの配布の利点と PWA の提出方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="46d85-275">Learn more about the benefits of app store distribution and how to submit your PWA.</span></span>  

## <span data-ttu-id="46d85-276">関連項目</span><span class="sxs-lookup"><span data-stu-id="46d85-276">See also</span></span>  

*   <span data-ttu-id="46d85-277">[MDN web ドキュメントのプログレッシブ Web アプリ][MDNProgressiveWebApps] -プログレッシブ web アプリに関する優れたガイドです。</span><span class="sxs-lookup"><span data-stu-id="46d85-277">[Progressive Web Apps on MDN web docs][MDNProgressiveWebApps] - Excellent guide on Progressive Web Apps.</span></span>  
*   <span data-ttu-id="46d85-278">プログレッシブ web アプリ向けの[プログレッシブ][WebDevProgressiveWebApps]web アプリ。プログレッシブ web アプリでの優れたガイドです。</span><span class="sxs-lookup"><span data-stu-id="46d85-278">[Progressive Web Apps on web.dev][WebDevProgressiveWebApps] - Excellent guide on Progressive Web Apps.</span></span>  
*   <span data-ttu-id="46d85-279">[プログレッシブ Web アプリ][ProgressiveWebApps] は、pwas の現実世界の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="46d85-279">[Progressive Web Apps rocks][ProgressiveWebApps] - Showcases real-world examples of PWAs.</span></span>  
*   <span data-ttu-id="46d85-280">[[プログレッシブ Web アプリとしてのハッカーニュースリーダー][HackerNewsProgressiveWebApps] ]: サンプル \ (ハッカーたち News READER) PWA を実装するためのさまざまなフレームワークとパフォーマンスパターンを比較します。</span><span class="sxs-lookup"><span data-stu-id="46d85-280">[Hacker News readers as Progressive Web Apps][HackerNewsProgressiveWebApps] - Compares different frameworks and performance patterns for implementing a sample \(Hacker News reader\) PWA.</span></span>  

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

[PwaEdgehtmlIndexRequirements]: ../progressive-web-apps-edgehtml/index.md#requirements "要件-プログレッシブ Web アプリ \ (EdgeHTML) Windows"  
[PwaEdgehtmlMicrosoftStore]: ../progressive-web-apps-edgehtml/microsoft-store.md "Microsoft Store でのプログレッシブ Web アプリ \ (EdgeHTML)"  
[PwaEdgehtmlWindowsFeatures]: ../progressive-web-apps-edgehtml/windows-features.md "Windows 用の PWA \ (EdgeHTML) をカスタマイズする"  

[LegalWindowsAgrementsMicrosoftStorePolicies]: /legal/windows/agreements/store-policies "Microsoft Store のポリシー |Microsoft ドキュメント"  

[VisualStudioNodeJsTutorial]: /visualstudio/nodejs/tutorial-nodejs "チュートリアル: Visual Studio で Node.js と Express アプリを作成する |Microsoft ドキュメント"  
[VisualStudioNodejsTutorialPublishAzureAppService]: /visualstudio/nodejs/tutorial-nodejs#optional-publish-to-azure-app-service "Azure App Service に発行する-Visual Studio で Node.js と Express App を作成する |Microsoft ドキュメント"  

[WindowsUwpGetStartedWhat]: /windows/uwp/get-started/whats-a-uwp "ユニバーサル Windows プラットフォーム (UWP) アプリとは何ですか? |Microsoft ドキュメント"  

[AzureCreateFreeAccount]: https://azure.microsoft.com/free "Azure 無料アカウントの作成 |Microsoft Azure"  
[AzureWebApps]: https://azure.microsoft.com/services/app-service/web "Web アプリ |Microsoft Azure"  

<!--[DeveloperEdgeToolsRemote]: https://developer.microsoft.com/microsoft-edge/tools/remote/ "page not found"  -->  

[WindowsBlogsPwaEdge]: https://blogs.windows.com/msedgedev/2018/02/06/welcoming-progressive-web-apps-edge-windows-10/#4UOdrDJj3124VIkc.97 "Microsoft Edge と Windows 10 へのプログレッシブ Web アプリのウェルカム |Windows ブログ"  
[WindowsBlogsWebNotificationsEdge]: https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge#UAbvU2ymUlHO8EUV.97 "Microsoft Edge での Web 通知 |Windows ブログ"  

[VisualStudioDownloads]: https://www.visualstudio.com/downloads "ダウンロード |Visual Studio"  
[VisualStudioFree]: https://visualstudio.microsoft.com/free-developer-offers "無料の開発者向けソフトウェア & サービス |Visual Studio"  
[VisualStudioPreview]: https://www.visualstudio.com/vs/preview "Visual Studio Preview"  

[BrowserStackTestEdgeBrowser]: https://www.browserstack.com/test-on-microsoft-edge-browser "Windows 10 での Microsoft Edge ブラウザーの無料テスト |BrowserStack"  

[HackerNewsProgressiveWebApps]: https://hnpwa.com "プログレッシブ Web アプリとしてのハッカーニュースリーダー"  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "キャッシュ |MDN"  
[MDNDedicatedWorkerGlobalScopePostMessage]: https://developer.mozilla.org/docs/Web/API/DedicatedWorkerGlobalScope/postMessage "DedicatedWorkerGlobalScope postMessage \ (\) |MDN"  
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNProgressiveWebApps]: https://developer.mozilla.org/Apps/Progressive "プログレッシブ web アプリ \ (PWAs) |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "プッシュ API |MDN"  
[MDNPushManager]: https://developer.mozilla.org/docs/Web/API/PushManager "PushManager |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "Service Worker API |MDN"  
[MDNSyncManager]: https://developer.mozilla.org/docs/Web/API/SyncManager "SyncManager |MDN"  
[MDNUsingServiceWorkers]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers "サービスワーカーを使用する |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web アプリマニフェスト |MDN"  
[MDNWorkerPrototypePostMessage]: https://developer.mozilla.org/docs/Web/API/Worker/postMessage "PostMessage \ (\) |MDN"  

[MozillaServicesSendingVapidWebPushNotificationsPush]: https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service "VAPID を Mozilla のプッシュサービス経由で識別された Web プッシュ通知を送信しています。 |Mozilla サービス"  

[NPMWebPush]: https://www.npmjs.com/package/web-push "web-プッシュ |npm"  
[NPMWebPushEncrypt]: https://www.npmjs.com/package/web-push#encryptuserpublickey-userauth-payload-contentencoding "暗号化 (userPublicKey、Userpublickey、payload、contentEncoding)-web-プッシュ |NPM"  
[NPMWebPushUsage]: https://www.npmjs.com/package/web-push#usage "使用状況-web-プッシュ |NPM"  

[ProgressiveWebApps]: https://pwa.rocks "プログレッシブ Web アプリ"  

[PugAttributes]: https://pugjs.org/language/attributes.html "属性 |Pug"  

[PwaBuilder]: https://www.pwabuilder.com "PWA ビルダー"  
[PwaBuilderAppImageGenerator]: https://www.pwabuilder.com/imageGenerator "アプリのイメージジェネレーター"  
[PwaBuilderServiceWorker]: https://www.pwabuilder.com/serviceworker "サービスワーカー |PWA ビルダー"  

[ServiceWorkerCookbook]: https://serviceworke.rs "ServiceWorker の料理"  
[ServiceWorkerCookbookPushRichDemo]: https://serviceworke.rs/push-rich_demo.html "充実したデモのプッシュ |ServiceWorker の料理"  

[W3cWebAppManifest]: https://www.w3.org/TR/appmanifest "Web アプリマニフェスト |勧告"  

[Webhint]: https://sonarwhal.com "web ベストプラクティスのヒントエンジンの web ヒント" 
 
[MDNWebWorkers]: https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers "Web ワーカーの使用" 

[WebDevProgressiveWebApps]: https://developers.google.com/web/progressive-web-apps "プログレッシブ Web アプリ |web.xml"  

[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS |Wikipedia"  
[WikiProgressiveEnhancement]: https://en.wikipedia.org/wiki/Progressive_enhancement "プログレッシブエンハンスメント |Wikipedia"  
