---
description: ネイティブアプリ機能により、Windows 版の PWA を段階的に強化
title: Windows の PWA (EdgeHTML) をカスタマイズする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: プログレッシブ web アプリ、PWA、Edge、Windows、WinRT、UWP、EdgeHTML
ms.openlocfilehash: 8ba682b03182194a773568254b66c3616bf4c3e2
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882787"
---
# <span data-ttu-id="8b139-104">Windows の PWA (EdgeHTML) をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="8b139-104">Tailor your PWA (EdgeHTML) for Windows</span></span>  

<span data-ttu-id="8b139-105">Windows 10 にインストールされた microsoft は、[ユニバーサル Windows プラットフォーム \ (UWP \)][WindowsUWPGetStartedGuide]アプリとして実行することにより、次のようなものも含め、windows アプリのサンドボックスセキュリティと[windows ランタイム \ (WinRT \)][UwpApiIndex] api へのフルアクセスを含む[すべてのメリット][PwaIndexWindows10]を享受できます。</span><span class="sxs-lookup"><span data-stu-id="8b139-105">PWAs installed on Windows 10 enjoy [all the benefits][PwaIndexWindows10] of running as [Universal Windows Platform \(UWP\)][WindowsUWPGetStartedGuide] apps, including protection through Windows app sandboxing security and full access to [Windows Runtime \(WinRT\))][UwpApiIndex] APIs, including those for:</span></span>  

*   <span data-ttu-id="8b139-106">デバイスの機能を制御する (カメラ、マイク、GPS など)</span><span class="sxs-lookup"><span data-stu-id="8b139-106">Controlling device features \(such as camera, microphone, GPS\)</span></span>  
*   <span data-ttu-id="8b139-107">ユーザーリソースにアクセスする (予定表、連絡先、ドキュメント、音楽など)</span><span class="sxs-lookup"><span data-stu-id="8b139-107">Accessing user resources \(such as calendar, contacts, documents, music\)</span></span>  
*   <span data-ttu-id="8b139-108">Cortana の音声コマンドによるアプリの起動と移動</span><span class="sxs-lookup"><span data-stu-id="8b139-108">Launching / navigating your app through Cortana voice commands</span></span>  
*   <span data-ttu-id="8b139-109">Windows OS との統合 (Windows アクションセンター、デスクトップタスクバー、およびコンテキストメニューを介して)</span><span class="sxs-lookup"><span data-stu-id="8b139-109">Integrating with the Windows OS \(through the Windows Action Center, desktop taskbar, and context menus\)</span></span>  

<span data-ttu-id="8b139-110">...これは、Windows の PWA \ (EdgeHTML \) に追加される可能性のほんの一部にすぎません。</span><span class="sxs-lookup"><span data-stu-id="8b139-110">... and these are only a few of the added possibilities for your PWA \(EdgeHTML\) on Windows!</span></span>  

<span data-ttu-id="8b139-111">このガイドでは、Windows 10 アプリとして PWA \ (EdgeHTML) をインストール、実行、強化する方法について説明します。ただし、クロスブラウザーとクロスプラットフォームの互換性を確保します。</span><span class="sxs-lookup"><span data-stu-id="8b139-111">This guide shows you how to install, run, and enhance your PWA \(EdgeHTML\) as a Windows 10 app, while still ensuring cross-browser and cross-platform compatibility.</span></span>  

## <span data-ttu-id="8b139-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="8b139-112">Prerequisites</span></span>  

*   <span data-ttu-id="8b139-113">Live または localhost サイトのいずれかである既存の PWA \ (またはホストされた web アプリ)。</span><span class="sxs-lookup"><span data-stu-id="8b139-113">An existing PWA \(or hosted web app\), either a live or localhost site.</span></span>  <span data-ttu-id="8b139-114">このガイドでは、 [「プログレッシブ Web アプリの使用を開始][PwaGetStarted]する」のサンプルの PWA について説明します。</span><span class="sxs-lookup"><span data-stu-id="8b139-114">This guide uses the sample PWA from [Get started with Progressive Web Apps][PwaGetStarted].</span></span>  
*   <span data-ttu-id="8b139-115">\ (無料版) の[Visual Studio コミュニティ 2017][MicrosoftVisualStudio|::ref1::|]をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8b139-115">Download the \(free\) [Visual Studio Community 2017][MicrosoftVisualStudio|::ref1::|].</span></span>  <span data-ttu-id="8b139-116">プロフェッショナル、エンタープライズ、または[プレビュー][MicrosoftVisualStudioPreview]の各エディションを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8b139-116">You are also able to use the Professional, Enterprise, or [Preview][MicrosoftVisualStudioPreview] editions.</span></span>  <span data-ttu-id="8b139-117">Visual Studio インストーラーで、次のワークロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="8b139-117">From the Visual Studio Installer, choose the following Workloads:</span></span>  
    *   **<span data-ttu-id="8b139-118">ユニバーサル Windows プラットフォーム開発</span><span class="sxs-lookup"><span data-stu-id="8b139-118">Universal Windows Platform development</span></span>**  

## <span data-ttu-id="8b139-119">ユニバーサル Windows アプリをセットアップして実行する</span><span class="sxs-lookup"><span data-stu-id="8b139-119">Set up and run your Universal Windows app</span></span>  

<span data-ttu-id="8b139-120">Windows 10 アプリとしてインストールされた PWA \ (EdgeHTML \) は、ブラウザーとは独立して \ ( `WWAHost.exe` プロセス \) ウィンドウで実行されます。</span><span class="sxs-lookup"><span data-stu-id="8b139-120">A PWA \(EdgeHTML\) installed as a Windows 10 app runs independently from the browser, in a standalone \(`WWAHost.exe` process\) window.</span></span>  <span data-ttu-id="8b139-121">これを有効にするには、ホストされた web アプリを含む軽量のアプリラッパーが必要です。これは、Visual Studio プロジェクトテンプレートを使用してすばやく設定することができ `Progressive Web App (Universal Windows)` ます。</span><span class="sxs-lookup"><span data-stu-id="8b139-121">Enabling this simply requires a lightweight app wrapper that contains your hosted web app, which you are able to quickly set up using the Visual Studio `Progressive Web App (Universal Windows)` project template.</span></span>  <span data-ttu-id="8b139-122">\ (ネイティブの Windows ランタイム API 要求の送信を含むすべてのアプリロジックは、元の web アプリコードでも引き続き発生します)。</span><span class="sxs-lookup"><span data-stu-id="8b139-122">\(All your app logic, including sending native Windows Runtime API requests, still happens in your original web app code.\)</span></span>  

<span data-ttu-id="8b139-123">Visual Studio で Windows アプリ開発環境をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="8b139-123">Set up your Windows app development environment in Visual Studio.</span></span>  

1.  <span data-ttu-id="8b139-124">Windows の [設定] で、[開発者モード][WindowsUWPGetStartedEnable]を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8b139-124">In your Windows Settings, turn on [Developer mode][WindowsUWPGetStartedEnable].</span></span>  <span data-ttu-id="8b139-125">\ ( `developer mode` Windows searchbar に入力して検索します。 \)</span><span class="sxs-lookup"><span data-stu-id="8b139-125">\(Type `developer mode` in the Windows searchbar to find it.\)</span></span>  
1.  <span data-ttu-id="8b139-126">Visual Studio を起動し、**新しいプロジェクトを作成し**ます。</span><span class="sxs-lookup"><span data-stu-id="8b139-126">Launch Visual Studio and **Create a new project...**</span></span>  
1.  <span data-ttu-id="8b139-127">C# **Windows アプリケーションパッケージプロジェクト**テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="8b139-127">Select the C# **Windows Application Packaging Project** template.</span></span>  <span data-ttu-id="8b139-128">以前のバージョンの Visual Studio を使っている場合は、[ホストされている**Web アプリ (ユニバーサル windows)** ] または [**プログレッシブ Web アプリ (ユニバーサル windows)**] の下で相当するテンプレートを見つけます。</span><span class="sxs-lookup"><span data-stu-id="8b139-128">If you are using a previous version of Visual Studio, find the equivalent template under **Hosted Web App (Universal Windows)** or **Progressive Web App (Universal Windows)**.</span></span>  
1.  <span data-ttu-id="8b139-129">既定の Windows 10 `Target version` \ (最新のリリース) と `Minimum version` \ (ビルド10586以降) を選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b139-129">Select the default Windows 10 `Target version` \(most recent release\) and `Minimum version` \(build 10586 or higher\) and click **OK**.</span></span>  

    ![UWP プロジェクトターゲットビルドの Visual Studio 選択ダイアログ](media/vs-target-min-version.png)  

    <span data-ttu-id="8b139-131">新しいプロジェクトが package.appxmanifest デザイナーを開き、読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="8b139-131">Your new project loads with the package.appxmanifest designer open.</span></span>  <span data-ttu-id="8b139-132">ここでは、パッケージ id、パッケージの依存関係、必要な機能、ビジュアル要素、拡張性ポイントなど、アプリの詳細を構成します。</span><span class="sxs-lookup"><span data-stu-id="8b139-132">This is where you configure the details of your app, including package identity, package dependencies, required capabilities, visual elements, and extensibility points.</span></span>  <span data-ttu-id="8b139-133">これは、アプリの開発中に使用される、簡単に構成可能な一時バージョンのアプリパッケージマニフェストです。</span><span class="sxs-lookup"><span data-stu-id="8b139-133">This is an easily configurable, temporary version of the app package manifest used during app development.</span></span>  
    <span data-ttu-id="8b139-134">アプリプロジェクトをビルドすると、 [Visual Studio][UwpSchemasAppxpackageUapmanifestschemaGeneratePackageManifest]によって、このメタデータから AppxManifest.xmlファイルが生成されます。これは、アプリをインストールして実行するために使われます。</span><span class="sxs-lookup"><span data-stu-id="8b139-134">When you build your app project, [Visual Studio generates an AppxManifest.xml][UwpSchemasAppxpackageUapmanifestschemaGeneratePackageManifest] file from this metadata, which is used to install and run your app.</span></span>  <span data-ttu-id="8b139-135">ファイルを更新するたびに、 `package.appxmanifest` 必ずプロジェクトを再ビルドして、実行時に両方が反映されるようにしてください `AppxManifest.xml` 。</span><span class="sxs-lookup"><span data-stu-id="8b139-135">Whenever you update your `package.appxmanifest` file, be sure to rebuild the project so both are reflected in your `AppxManifest.xml` at runtime.</span></span>  

1.  <span data-ttu-id="8b139-136">マニフェストデザイナーの [**アプリケーション**] パネルで、PWA の URL をとして入力し `Start page` ます。</span><span class="sxs-lookup"><span data-stu-id="8b139-136">In the manifest designer **Application** panel, enter the URL of your PWA as the `Start page`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8b139-137">サービスワーカーは、として指定されているすべての https \ (セキュリティで保護されたリモート \) url でサポートされてい `StartPage` ます。</span><span class="sxs-lookup"><span data-stu-id="8b139-137">Service workers are supported for all https \(secure, remote\) urls specified as the `StartPage`.</span></span>  <span data-ttu-id="8b139-138">ローカルのスタートページを指定する web アプリでは、サービスワーカーは既定でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8b139-138">Service workers are not supported by default for web apps that specify a local start page.</span></span>  <span data-ttu-id="8b139-139">このような場合に service worker のサポートを有効にするには、次のように明示的な[Applicationcontenturirules](#set-application-content-uri-rules-acurs)エントリをマニフェストに追加します。</span><span class="sxs-lookup"><span data-stu-id="8b139-139">To enable service worker support for these cases, add an explicit [ApplicationContentUriRules](#set-application-content-uri-rules-acurs) entry to the manifest, for example:</span></span> `<uap:Rule Match="http://web-platform.test/" Type="include" uap5:ServiceWorker="true"/>`  
    
    ![Package.appxmanifest designer のアプリケーションパネル](media/vs-manifest-application.png)  
    
    <span data-ttu-id="8b139-141">必要に応じて、を変更することもでき `Display name` `Description` ます。</span><span class="sxs-lookup"><span data-stu-id="8b139-141">You are able to also modify the `Display name` and `Description` as you like.</span></span>  
1.  <span data-ttu-id="8b139-142">このファイルをデスクトップに保存します (または、選択したコンピューターの別の512x512 画像を保存します)。</span><span class="sxs-lookup"><span data-stu-id="8b139-142">Save this file \(or another 512x512 image of your choosing\) to your desktop.</span></span>  
    <span data-ttu-id="8b139-143">次に、マニフェストデザイナーの**ビジュアルアセット**パネルで、[ `Source` フィールド **...** ] ボタンをクリックし、ソースファイルとして選択し、[**生成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b139-143">Then, in the manifest designer **Visual Assets** panel, click on the `Source` field **...** button, select it as your source file, and click **Generate**.</span></span>  <span data-ttu-id="8b139-144">\ ([ **OK]** をクリックして、既定のプレースホルダー画像を上書きします)。</span><span class="sxs-lookup"><span data-stu-id="8b139-144">\(Then click **OK** to overwrite the default placeholder images\).</span></span>  
    
    ![Package.appxmanifest designer のビジュアルアセットパネル](media/vs-manifest-visual-assets.png)  
    
    <span data-ttu-id="8b139-146">これにより、アプリをインストール、実行、起動、配布するための基本的なビジュアルアセットがストアに生成されます。</span><span class="sxs-lookup"><span data-stu-id="8b139-146">This generates the basic visual assets for installing, running, launching, and distributing your app in the store.</span></span>  
    <span data-ttu-id="8b139-147">欠けている `X` 画像を示す赤い \ (\) エラーが表示される場合は、[.. **.** ] ボタンをクリックして、生成された画像からファイルを手動で選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="8b139-147">If you see any red \(`X`\) errors indicating missing images, you are able to click on the **...** buttons to manually select a file from the generated images.</span></span>  
1.  <span data-ttu-id="8b139-148">マニフェストデザイナーの**コンテンツ uri**パネルで、 `http://example.com` PWA の場所 ( `Rule`  =  `include` と \ など) に置き換え `WinRT Access`  =  `All` ます。</span><span class="sxs-lookup"><span data-stu-id="8b139-148">In the manifest designer **Content URIs** panel, replace `http://example.com` with the location of your PWA \(such that `Rule` = `include` and `WinRT Access` = `All`\).</span></span>  
    <span data-ttu-id="8b139-149">これにより、PWA は、Windows 10 アプリとして実行されている場合に、ネイティブ Windows ランタイム \ (WinRT \) API 要求を送信する権限を付与することになります。これは、後で説明します。</span><span class="sxs-lookup"><span data-stu-id="8b139-149">This grants your PWA permission to send native Windows Runtime \(WinRT\) API requests when running as a Windows 10 app, which is covered a bit later.</span></span>   <span data-ttu-id="8b139-150">実際の PWA が WinRT アクセスを必要としない場合は、値をに切り替えることができ `WinRT Access` `None` ます。</span><span class="sxs-lookup"><span data-stu-id="8b139-150">If your actual PWA does not require WinRT access, you are able to switch the `WinRT Access` value to `None`.</span></span>  <span data-ttu-id="8b139-151">どちらの場合も、既定の文字列を PWA の URI に必ず指定してください `http://example.com` 。または、実行時にアプリが適切に読み込まれないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="8b139-151">Either way, be sure to sub out the default `http://example.com` string with the URI of your PWA, or your app is not able to properly load at runtime.</span></span>  
    <span data-ttu-id="8b139-152">Windows 10 アプリとして PWA を実行してデバッグする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="8b139-152">You are ready to run and debug your PWA as a Windows 10 app.</span></span>  <span data-ttu-id="8b139-153">このガイドの手順に localhost サイトを使用している場合は、実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8b139-153">If you are using a localhost site to step through this guide, make sure it is running.</span></span>  <span data-ttu-id="8b139-154">そうしたら</span><span class="sxs-lookup"><span data-stu-id="8b139-154">Then,</span></span>  
1.  <span data-ttu-id="8b139-155">ビルド \ ( `Ctrl` + `Shift` + `F5` \) を実行し、 `F5` 自分の PWA プロジェクトを \ (\) 実行します。</span><span class="sxs-lookup"><span data-stu-id="8b139-155">Build \(`Ctrl`+`Shift`+`F5`\) and Run \(`F5`\) your PWA project.</span></span>  <span data-ttu-id="8b139-156">これで web サイトがスタンドアロンアプリウィンドウで起動します。</span><span class="sxs-lookup"><span data-stu-id="8b139-156">Your website should now launch in a standalone app window.</span></span>  <span data-ttu-id="8b139-157">ホストされた web アプリだけでなく、Windows 10 にインストールされているプログレッシブ Web アプリとして実行されています。</span><span class="sxs-lookup"><span data-stu-id="8b139-157">Not only is it a hosted web app; it is running as a Progressive Web App installed on Windows 10!</span></span>  

    ![WWAHost.exe ウィンドウで実行されている PWA](media/wwahost.png)  

## <span data-ttu-id="8b139-159">Windows アプリとして PWA \ (EdgeHTML \) をデバッグする</span><span class="sxs-lookup"><span data-stu-id="8b139-159">Debug your PWA \(EdgeHTML\) as a Windows app</span></span>  

<span data-ttu-id="8b139-160">PWA \ (EdgeHTML \) は、段階的に強化されたホステッド web アプリであるため、通常の IDE とワークフローを使って、web アプリと同じようにサーバー側のコードをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="8b139-160">Because a PWA \(EdgeHTML\) is simply a progressively enhanced hosted web app, you are able to debug your server-side code the same as any web app, using your usual IDE and workflow.</span></span>  <span data-ttu-id="8b139-161">展開された変更は、次に起動したときに、インストールされている PWA に反映されます (ユニバーサル Windows アプリパッケージを再展開する必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="8b139-161">The changes you deploy live are reflected in your installed PWA the next time you launch it \(no need to redeploy your Universal Windows app package\).</span></span>

<span data-ttu-id="8b139-162">Windows 10 アプリでクライアント側のデバッグを行うには、アプリが必要 `Microsoft Edge DevTools Preview` です。</span><span class="sxs-lookup"><span data-stu-id="8b139-162">For client-side debugging within your Windows 10 app, you must have the `Microsoft Edge DevTools Preview` app.</span></span>  <span data-ttu-id="8b139-163">このスタンドアロンアプリには、ブラウザーの元の[Microsoft Edge devtools][DevToolsGuide] ( [PWA ツール][DevToolsGuideServiceWorkers]を含む)、基本的な[リモートデバッグ][DevToolsProtocol01ClientsEdgePreview]サポート、および EdgeHTML エンジンの実行中のインスタンスに接続するための[デバッグターゲットのセレクター][DevToolsGuideMicrosoftStoreApp] (Office のアドイン、Cortana、アプリ webviews など) のすべての機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8b139-163">This standalone app includes all the functionality of the original in-browser [Microsoft Edge DevTools][DevToolsGuide] \(including [PWA tools][DevToolsGuideServiceWorkers]\), plus basic [remote debugging][DevToolsProtocol01ClientsEdgePreview] support and a [Debug Target chooser][DevToolsGuideMicrosoftStoreApp] for attaching to any running instance of the EdgeHTML engine, including add-ins for Office, Cortana, app webviews, and of course, PWAs running on Windows.</span></span>  

<span data-ttu-id="8b139-164">ここでは、PWA \ (EdgeHTML) のデバッグをセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8b139-164">Here is how to set up debugging for your PWA \(EdgeHTML\).</span></span>  

1.  <span data-ttu-id="8b139-165">まだインストールしていない場合は、microsoft Store から[Microsoft Edge DevTools プレビュー][MicrosoftStoreEdgeDevtoolsPreview]アプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8b139-165">Install the [Microsoft Edge DevTools Preview][MicrosoftStoreEdgeDevtoolsPreview] app from the Microsoft Store if you do not already have it.</span></span>  
1.  <span data-ttu-id="8b139-166">PWA サイトを起動して実行している状態で、DevTools アプリを起動します。</span><span class="sxs-lookup"><span data-stu-id="8b139-166">With your PWA site up and running, launch the DevTools app.</span></span>  
1.  <span data-ttu-id="8b139-167">Visual Studio で、() コマンドを使用して Windows 10 アプリを起動し `Start Without Debugging` `Ctrl` + `F5` ます。</span><span class="sxs-lookup"><span data-stu-id="8b139-167">From Visual Studio, launch your Windows 10 app with the `Start Without Debugging` (`Ctrl`+`F5`) command.</span></span>  <span data-ttu-id="8b139-168">\ (Visual Studio デバッガーがアクティブな場合は、DevTools アプリが適切にアタッチされません)。</span><span class="sxs-lookup"><span data-stu-id="8b139-168">\(The DevTools app does not attach properly if the Visual Studio debugger is active.\)</span></span>  
1.  <span data-ttu-id="8b139-169">DevTools アプリで、ローカルデバッグターゲットの選択の [**更新**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b139-169">In the DevTools app, click the **Refresh** button in the Local debug target chooser.</span></span>  <span data-ttu-id="8b139-170">これで、PWA \ (EdgeHTML) サイトが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="8b139-170">Your PWA \(EdgeHTML\) site should now be listed.</span></span>  <span data-ttu-id="8b139-171">\ (ブラウザーウィンドウでも実行されている場合は、リスト内でそのサイトの最後のインスタンスになります)。</span><span class="sxs-lookup"><span data-stu-id="8b139-171">\(If it is also running in a browser window, it is the last instance of that site in the list.\)</span></span>  
1.  <span data-ttu-id="8b139-172">PWA の [\ (EdgeHTML \)] サイトの一覧をクリックして、新しい DevTools インスタンスタブを開き、デバッグを開始します。</span><span class="sxs-lookup"><span data-stu-id="8b139-172">Click on your PWA \(EdgeHTML\) site listing to open a new DevTools instance tab and start debugging.</span></span>  
    
    ![Microsoft Edge DevTools アプリでのローカルデバッグターゲットの選択](media/devtools-local.png)  
    
1.  <span data-ttu-id="8b139-174">DevTools が Windows アプリの PWA として実行されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8b139-174">You are able to verify that DevTools is attached to your PWA-running-as-Windows-app.</span></span>  <span data-ttu-id="8b139-175">DevTools**コンソール**で、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8b139-175">In the DevTools **Console**, type:</span></span>  
    
    ```shell
    window.Windows
    ```  
    
    <span data-ttu-id="8b139-176">`Windows Runtime`すべての[トップレベルの WinRT 名前空間](#find-windows-runtime-winrt-apis)を含むグローバルオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="8b139-176">This returns the global `Windows Runtime` object containing all of the [top-level WinRT namespaces](#find-windows-runtime-winrt-apis).</span></span>  <span data-ttu-id="8b139-177">これは、PWA \ (EdgeHTML \) のエントリポイントであり、[ユニバーサル Windows プラットフォーム][WindowsUWPIndex]を対象としており、windows 10 アプリとして実行される (ブラウザーの外部で実行されている) web アプリにのみ公開され `WWAHost.exe` ます。</span><span class="sxs-lookup"><span data-stu-id="8b139-177">This is your PWA \(EdgeHTML\) entrypoint to the [Universal Windows Platform][WindowsUWPIndex], and only exposed to web apps that run as Windows 10 apps (running outside the browser, in a `WWAHost.exe` process).</span></span>  
    
## <span data-ttu-id="8b139-178">Windows ランタイム (WinRT \) Api を検索する</span><span class="sxs-lookup"><span data-stu-id="8b139-178">Find Windows Runtime \(WinRT\) APIs</span></span>  

<span data-ttu-id="8b139-179">インストール済みの Windows アプリとして、 [PWA \ (EdgeHTML \) には、ネイティブの Windows ランタイム api へのフルアクセスがあり][WindowsRuntime]ます。使用する必要があるものを特定し、必要なアクセス許可を取得し、機能検出を利用して、サポートされている環境でその API 要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="8b139-179">As an installed Windows app, your [PWA \(EdgeHTML\) has full access to native Windows Runtime APIs][WindowsRuntime]; identify what you need to use, obtain the requisite permissions, and employ feature detection to send that API request on supported environments.</span></span>  <span data-ttu-id="8b139-180">このプロセスに従って、PWA の Windows デスクトップユーザーにプログレッシブエンハンスメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="8b139-180">Walk through this process to add a progressive enhancement for Windows desktop users of your PWA.</span></span>  

<span data-ttu-id="8b139-181">Windows PWA に必要なユニバーサル Windows プラットフォーム Api を特定する方法はいくつかあります。これには、windows デベロッパーセンターでの包括的な [UWP ドキュメント] の検索、Visual Studio を使った[uwp コードサンプル](#uwp-code-samples)のダウンロードと実行、windows での一般的なタスクのコードスニペットの参照が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8b139-181">There are a number of ways to identify the Universal Windows Platform APIs you need for your Windows PWA, including searching the comprehensive [UWP docs on Windows Dev Center][uwp/api/], downloading and running [UWP code samples](#uwp-code-samples) with Visual Studio, and browsing code snippets for common tasks for PWAs on Windows.</span></span>

<span data-ttu-id="8b139-182">Windows の PWA に必要なユニバーサル Windows プラットフォーム Api を特定するには、さまざまな方法があります。これには、windows デベロッパーセンターでの包括的な [UWP ドキュメント] の検索、Visual Studio による[uwp コードサンプル](#uwp-code-samples)のダウンロードと実行、一般的なタスクのコードスニペットの参照[(EdgeHTML)][PwaIndexWindows10]が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8b139-182">There are a number of ways to identify the Universal Windows Platform APIs you need for your Windows PWA, including searching the comprehensive [UWP docs on Windows Dev Center][uwp/api/], downloading and running [UWP code samples](#uwp-code-samples) with Visual Studio, and browsing code snippets for common tasks for [PWAs on Windows 10 (EdgeHTML)][PwaIndexWindows10].</span></span>  

<span data-ttu-id="8b139-183">全体的に、WinRT Api は C# と同じように動作するため、一般的な[ユニバーサル Windows プラットフォームのドキュメント][WindowsUWPIndex]と[API リファレンス][UwpApiIndex]に従って使用できます。</span><span class="sxs-lookup"><span data-stu-id="8b139-183">Overall, WinRT APIs work in JavaScript the same way they do in C#, so you may follow the general [Universal Windows Platform documentation][WindowsUWPIndex] and [API Reference][UwpApiIndex] for usage.</span></span>  <span data-ttu-id="8b139-184">ただし、次の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="8b139-184">However, please note the following differences:</span></span>  

*   <span data-ttu-id="8b139-185">JavaScript の WinRT 機能では、[さまざまな大文字と小文字の規則][ScriptingJsinrtUsingWinRTCasingConventions]が使用される</span><span class="sxs-lookup"><span data-stu-id="8b139-185">WinRT features in JavaScript use  [different casing conventions][ScriptingJsinrtUsingWinRTCasingConventions]</span></span>  
*   <span data-ttu-id="8b139-186">イベントは、クラスメソッドに渡される[文字列識別子として表され][ScriptingJsinrtHandlingWinRTEvents]ます。 `addEventListener` / `removeEventListener`</span><span class="sxs-lookup"><span data-stu-id="8b139-186">[Events are represented as string identifiers][ScriptingJsinrtHandlingWinRTEvents] passed to class `addEventListener`/`removeEventListener` methods</span></span>  
*   <span data-ttu-id="8b139-187">[非同期メソッド][ScriptingJsinrtUsingWinRT]は JavaScript Promise モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b139-187">[Asynchronous methods][ScriptingJsinrtUsingWinRT] use the JavaScript Promise model</span></span>  
*   <span data-ttu-id="8b139-188">`Windows.UI.Xaml`名前空間の api は JavaScript アプリではサポートされません。これは、代わりに[EdgeHTML][DevGuideWhatsNew] engine web レンダリングスタック (HTML, CSS) を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b139-188">APIs in the `Windows.UI.Xaml` namespace are not supported for JavaScript apps, which instead use the [EdgeHTML][DevGuideWhatsNew] engine web rendering stack \(HTML, CSS\)</span></span>  

<span data-ttu-id="8b139-189">詳しくは、「 [JavaScript での Windows ランタイムの使用][WindowRuntimeUsingJavascript]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8b139-189">For more details, see [Using the Windows Runtime in JavaScript][WindowRuntimeUsingJavascript].</span></span>  

### <span data-ttu-id="8b139-190">UWP コードサンプル</span><span class="sxs-lookup"><span data-stu-id="8b139-190">UWP code samples</span></span>  

<span data-ttu-id="8b139-191">一般的な Windows 10 アプリのシナリオの JavaScript の例を参照するには、 [「ユニバーサル Windows プラットフォーム \ (UWP \) コードサンプル][MicrosoftDeveloperWindowsSamples]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8b139-191">Check out the [Universal Windows Platform \(UWP\) Code Samples][MicrosoftDeveloperWindowsSamples] repo to browse JavaScript examples for common Windows 10 app scenarios.</span></span>  <span data-ttu-id="8b139-192">このサンプルの JS バージョンでは、 [WinJS][GithubWinjsWinjs]ライブラリを使ってサンプルテンプレートを構成していますが、このサンプルで示されている WinRT API 要求を送信するために WinJS は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8b139-192">Although the JS versions of these samples use the [WinJS][GithubWinjsWinjs] library to structure the sample template, WinJS is not required for sending the WinRT API requests demonstrated in these samples.</span></span>  

> [!NOTE]
> <span data-ttu-id="8b139-193">アプリのイベントをリッスンする必要がある場合 [`activated`][UwpApiWindowsUiWebuiWebapplicationActivated] は、次のネイティブ WINRT API を使ってこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8b139-193">If you need to listen for the [`activated`][UwpApiWindowsUiWebuiWebapplicationActivated] event for the app, you are able to do this using the following native WinRT API:</span></span>  
> 
> **<span data-ttu-id="8b139-194">使用するもの</span><span class="sxs-lookup"><span data-stu-id="8b139-194">Use this</span></span>**  
> 
> ```javascript
> Windows.UI.WebUI.WebUIApplication.addEventListener("activated", function (activatedEventArgs) {
>     // Check activatedEventArgs.kind and respond as needed
> });
> ```  
> 
> <span data-ttu-id="8b139-195">...この種類の WinJS 要求は、次のように使用されます。</span><span class="sxs-lookup"><span data-stu-id="8b139-195">... as opposed this type of WinJS request used in the samples:</span></span>  
> 
> **<span data-ttu-id="8b139-196">不適切な例</span><span class="sxs-lookup"><span data-stu-id="8b139-196">Not this</span></span>**  
> 
> ```javascript
>     var page = WinJS.UI.Pages.define("/html/scenario1-launched.html", {
>         ready: function (element, options) {
>             // Check options.activationKind and respond as needed
>         }
>     });
> ```  

## <span data-ttu-id="8b139-197">PWA から WinRT API 要求を送信する (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="8b139-197">Send WinRT API requests from your PWA (EdgeHTML)</span></span>  

<span data-ttu-id="8b139-198">この時点で、windows ユーザーの PWA 用のカスタムコンテキストメニュー (EdgeHTML \) を追加して、必要な Api を[windows のポップアップ][UwpApiWindowsUiPopups]名前空間で指定します。</span><span class="sxs-lookup"><span data-stu-id="8b139-198">At this point, pretend you want to add a custom context menu for Windows users of our PWA \(EdgeHTML\) and have identified the APIs you need in the [Windows.UI.Popups][UwpApiWindowsUiPopups] namespace.</span></span>  

<span data-ttu-id="8b139-199">Microsoft の PWA \ (EdgeHTML \) から WinRT Api 要求を送信するには、最初に Windows アプリパッケージマニフェスト \ (\) ファイルに必要な権限 (またはアプリケーションコンテンツ URI 規則) を[設定](#set-application-content-uri-rules-acurs)する必要があり `.appxmanifest` ます。</span><span class="sxs-lookup"><span data-stu-id="8b139-199">In order to send any WinRT APIs requests from our PWA \(EdgeHTML\), you first need to [establish the requisite permissions](#set-application-content-uri-rules-acurs) \(or, Application Content URI Rules\) in your Windows app package manifest \(`.appxmanifest`\) file.</span></span>  

<span data-ttu-id="8b139-200">これらの API 要求のいずれかで、画像や音楽などのユーザーリソース、またはカメラやマイクなどのデバイス機能へのアクセスが必要な場合は、Windows がユーザーにアクセス許可を求めるために、アプリパッケージマニフェストに[アプリ機能の宣言](#app-capability-declarations)を追加する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="8b139-200">If any of these API requests involve access to user resources like pictures or music, or to device features like the camera or microphone, you also need to add [app capability declarations](#app-capability-declarations) to the app package manifest in order for Windows to prompt the user for permission.</span></span>  <span data-ttu-id="8b139-201">後で PWA \ (EdgeHTML \) を Microsoft Store に公開した場合、これらの必要な[アプリのアクセス許可][MicrosoftSupportWindowsAppPermissions]についても、ストア登録情報に記載されています。</span><span class="sxs-lookup"><span data-stu-id="8b139-201">If you later publish your PWA \(EdgeHTML\) to the Microsoft Store, these required [App permissions][MicrosoftSupportWindowsAppPermissions] are also noted in your store listing.</span></span>  

#### <span data-ttu-id="8b139-202">アプリケーションコンテンツ URI 規則 (Acur) を設定する</span><span class="sxs-lookup"><span data-stu-id="8b139-202">Set Application Content URI Rules (ACURs)</span></span>  

<span data-ttu-id="8b139-203">Acur、つまり URL 許可リストと呼ばれている場合は、PWA \ (EdgeHTML \) の Url を Windows ランタイム Api に直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8b139-203">Through ACURs, otherwise known as a URL allow list, you are able to give the URLs of your PWA \(EdgeHTML\) direct access to Windows Runtime APIs.</span></span>  <span data-ttu-id="8b139-204">Windows OS レベルでは、web サーバーでホストされているコードがプラットフォーム API 要求を直接送信することを許可するように、適切なポリシーの境界が設定されています。</span><span class="sxs-lookup"><span data-stu-id="8b139-204">At the Windows OS level, the right policy bounds are set to allow code hosted on your web server to directly send platform API requests.</span></span>  <span data-ttu-id="8b139-205">PWA Url をとして指定するときに、アプリパッケージマニフェストファイルでこれらの境界を定義し `ApplicationContentUriRules` ます。</span><span class="sxs-lookup"><span data-stu-id="8b139-205">You define these bounds in the app package manifest file when you specify your PWA URLs as `ApplicationContentUriRules`.</span></span>  

<span data-ttu-id="8b139-206">ルールには、アプリのスタートページと、アプリページとして含めるその他のページを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b139-206">Your rules should include the start page for your app and any other pages you want included as app pages.</span></span>  <span data-ttu-id="8b139-207">ユーザーが自分のルールに含まれていない URL に移動した場合、Windows は、スタンドアロンの PWA \ (EdgeHTML \) ウィンドウ (プロセス \) ではなく、Microsoft Edge ブラウザーでターゲット URL を開き `WWAHost.exe` ます。</span><span class="sxs-lookup"><span data-stu-id="8b139-207">If your user navigates to a URL that is not included in your rules, Windows opens the target URL in the Microsoft Edge browser rather than your standalone PWA \(EdgeHTML\) window \(`WWAHost.exe` process\).</span></span>  <span data-ttu-id="8b139-208">特定の Url を除外することもできます。</span><span class="sxs-lookup"><span data-stu-id="8b139-208">You may also exclude specific URLs.</span></span>  

<span data-ttu-id="8b139-209">ルールに URL を指定するには、いくつかの方法があり `Match` ます。</span><span class="sxs-lookup"><span data-stu-id="8b139-209">There are several ways to specify a URL `Match` in your rules:</span></span>  

*   <span data-ttu-id="8b139-210">完全なホスト名</span><span class="sxs-lookup"><span data-stu-id="8b139-210">An exact hostname</span></span>  
*   <span data-ttu-id="8b139-211">任意のサブドメインを指定した URI を含むホスト名、またはサブドメインを指定した URI を除外したホスト名</span><span class="sxs-lookup"><span data-stu-id="8b139-211">A hostname for which a URI with any subdomain of that hostname is included or excluded</span></span>  
*   <span data-ttu-id="8b139-212">完全な URI</span><span class="sxs-lookup"><span data-stu-id="8b139-212">An exact URI</span></span>  
*   <span data-ttu-id="8b139-213">クエリプロパティを含む正確な URI</span><span class="sxs-lookup"><span data-stu-id="8b139-213">An exact URI containing a query property</span></span>  
*   <span data-ttu-id="8b139-214">対象に含めるルールの場合は、部分的なパスと、特定のファイル拡張子を示すワイルドカード</span><span class="sxs-lookup"><span data-stu-id="8b139-214">A partial path and a wildcard to indicate a particular file extension for an include rule</span></span>  
*   <span data-ttu-id="8b139-215">対象から除外する規則の場合は、相対パス</span><span class="sxs-lookup"><span data-stu-id="8b139-215">Relative paths for exclude rules</span></span>  

<span data-ttu-id="8b139-216">次に、ファイル内の Acur の例をいくつか示し `.appxmanifest` ます。</span><span class="sxs-lookup"><span data-stu-id="8b139-216">Here are a few examples of ACURs in a `.appxmanifest` file:</span></span>  

```xml
<Application
Id="App"
StartPage="https://contoso.com/home">
<uap:ApplicationContentUriRules>
    <uap:Rule Type="include" Match="https://contoso.com/" WindowsRuntimeAccess="all" />
    <uap:Rule Type="include" Match="https://*.contoso.com/" WindowsRuntimeAccess="all" />
    <uap:Rule Type="exclude" Match="https://contoso.com/excludethispage.aspx" />
</uap:ApplicationContentUriRules>
```  

<span data-ttu-id="8b139-217">アプリの Acur 内で定義されている Url には、属性を通じて Windows ランタイムへのアクセス許可を付与することができ `WindowsRuntimeAccess` ます。この属性は、次の値を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8b139-217">URLs defined within the ACURs for your app are able to be granted permission to the Windows Runtime through the `WindowsRuntimeAccess` attribute, which accepts the following values:</span></span>  

*   `all`<span data-ttu-id="8b139-218">: リモート JavaScript コードは、すべての WinRT Api とローカルのパッケージ化されたコンポーネントにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8b139-218">: Remote JavaScript code has access to all WinRT APIs and any local packaged components.</span></span>  <span data-ttu-id="8b139-219">[Windows \ (WinRT \))][UwpApiIndex]名前空間が挿入され、スクリプトエンジンに存在します。</span><span class="sxs-lookup"><span data-stu-id="8b139-219">The [Windows \(WinRT\))][UwpApiIndex] namespace is injected and present in the script engine.</span></span>  
*   `allowForWeb`<span data-ttu-id="8b139-220">: リモート JavaScript コードアクセスは、カスタム C++/C # コンポーネントなど、ローカルのパッケージ化されたコンポーネントに制限されています。</span><span class="sxs-lookup"><span data-stu-id="8b139-220">: Remote JavaScript code access is limited to local packaged components, including custom C++/C# components.</span></span>  
*   `none`<span data-ttu-id="8b139-221">設定.</span><span class="sxs-lookup"><span data-stu-id="8b139-221">: Default.</span></span>  <span data-ttu-id="8b139-222">指定された URL はプラットフォームにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="8b139-222">The specified URL has no platform access.</span></span>  

<span data-ttu-id="8b139-223">このチュートリアルでは、1ページのアプリで、必要な ACUR のみを既に設定しています (前のセットアップの手順6と、アプリセクション \[を実行し](#set-up-and-run-your-universal-windows-app)ます)。</span><span class="sxs-lookup"><span data-stu-id="8b139-223">In this tutorial, you already set the only ACUR that you need \(Step 6 of the previous [Set up and run your app](#set-up-and-run-your-universal-windows-app) section\) for your single-page app.</span></span>  <span data-ttu-id="8b139-224">これは、Visual Studio designer の**コンテンツ uri**パネルで確認でき `package.appxmanifest` ます。</span><span class="sxs-lookup"><span data-stu-id="8b139-224">You are able to confirm this from the **Content URIs** panel of the Visual Studio `package.appxmanifest` designer.</span></span>  

![Visual Studio package.appxmanifest designer のコンテンツ URI パネル](media/vs-appxmanifest-editor-acurs.png)  

<span data-ttu-id="8b139-226">`package.appxmanifest`Visual Studio ソリューションエクスプローラーでファイルを右クリックして [**コードの表示**] (\) を選択することにより、マニフェストの生の XML を表示することもでき `F7` ます。</span><span class="sxs-lookup"><span data-stu-id="8b139-226">You are also able to view the raw XML of your manifest by right-clicking your `package.appxmanifest` file in Visual Studio Solution Explorer and selecting **View Code** \(`F7`\).</span></span>  <span data-ttu-id="8b139-227">デザイナービューに戻るには、[**ビューデザイナー** \ (\)] を選択し `Shift` + `F7` ます。</span><span class="sxs-lookup"><span data-stu-id="8b139-227">To toggle back to the Designer view, select **View Designer** \(`Shift`+`F7`\).</span></span>  

#### <span data-ttu-id="8b139-228">アプリ機能の宣言</span><span class="sxs-lookup"><span data-stu-id="8b139-228">App capability declarations</span></span>  

<span data-ttu-id="8b139-229">アプリが、画像や音楽などのユーザーリソース、またはカメラやマイクなどのデバイスにプログラムでアクセスする必要がある場合は、対応する[アプリ機能の宣言][WindowsUwpPackagingAppCapabilities]をアプリパッケージマニフェストファイルに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b139-229">If your app needs programmatic access to user resources like pictures or music, or to devices like a camera or a microphone, you must include the corresponding [App capability declarations][WindowsUwpPackagingAppCapabilities] in your app package manifest file.</span></span>  <span data-ttu-id="8b139-230">アプリ機能の宣言には次の 3 つのカテゴリがあります。</span><span class="sxs-lookup"><span data-stu-id="8b139-230">There are three app capability declaration categories:</span></span>  

*   <span data-ttu-id="8b139-231">ストア アプリのほとんどのシナリオに適用される[一般的な用途の機能][WindowsUwpPackagingAppCapabilitiesGeneralUse]。</span><span class="sxs-lookup"><span data-stu-id="8b139-231">[General-use capabilities][WindowsUwpPackagingAppCapabilitiesGeneralUse] that apply to most common app scenarios.</span></span>  
*   <span data-ttu-id="8b139-232">アプリが周辺機器と内部デバイスにアクセスできるようにする[デバイス機能][WindowsUwpPackagingAppCapabilitiesDevice]。</span><span class="sxs-lookup"><span data-stu-id="8b139-232">[Device capabilities][WindowsUwpPackagingAppCapabilitiesDevice] that allow your app to access peripheral and internal devices.</span></span>  
*   <span data-ttu-id="8b139-233">エンタープライズシナリオをサポートし、Microsoft ストア会社のアカウントを必要とする[特殊な用途の機能][WindowsUwpPackagingAppCapabilitiesSpecialRestricted]。</span><span class="sxs-lookup"><span data-stu-id="8b139-233">[Special-use capabilities][WindowsUwpPackagingAppCapabilitiesSpecialRestricted] that support enterprise scenarios and require a Microsoft Store company account.</span></span>  <span data-ttu-id="8b139-234">会社のアカウントについて詳しくは、「[アカウントの種類、場所、料金][WindowsUwpPublishAccountTypesLocationsFees]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8b139-234">For more info about company accounts, see [Account types, locations, and fees][WindowsUwpPublishAccountTypesLocationsFees].</span></span>

<span data-ttu-id="8b139-235">Microsoft ストアアプリのページには、アプリパッケージマニフェストで宣言するすべての機能が一覧表示されているため、アプリで実際に使用する機能のみを指定するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="8b139-235">Your Microsoft Store app page lists all the capabilities you declare in your app package manifest, so be sure to only specify the capabilities that your app actually uses.</span></span>

<span data-ttu-id="8b139-236">一部の機能では、アプリが機密性の高いリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8b139-236">Some capabilities provide apps access to sensitive resources.</span></span>  <span data-ttu-id="8b139-237">これらのリソースは、ユーザーの個人データにアクセスしたり、ユーザーに課金したりできるため、機密性の高いリソースと見なされます。</span><span class="sxs-lookup"><span data-stu-id="8b139-237">These resources are considered sensitive because each is able to access the user's personal data or cost the user money.</span></span>  <span data-ttu-id="8b139-238">Windows 10[設定][BingResultsWindows10Settings]アプリで管理されるプライバシー設定により、ユーザーは機密性の高いリソースへのアクセスを動的に制御することができます。</span><span class="sxs-lookup"><span data-stu-id="8b139-238">Privacy settings, managed by the Windows 10 [Settings][BingResultsWindows10Settings] app, let the user dynamically control access to sensitive resources.</span></span>  <span data-ttu-id="8b139-239">したがって、機密性の高いリソースが常に利用できるとアプリでは想定していないことが重要です。</span><span class="sxs-lookup"><span data-stu-id="8b139-239">Thus, it is important that your app does not assume a sensitive resource is always available.</span></span>  <span data-ttu-id="8b139-240">機密性の高いリソースへのアクセスについて詳しくは、「[個人データにアクセスするアプリのガイドライン][WindowsUwp|::ref2::|Index]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8b139-240">For more info about accessing sensitive resources, see [Guidelines for privacy-aware apps][WindowsUwp|::ref2::|Index].</span></span>  

<span data-ttu-id="8b139-241">アクセスを要求するには、アプリのパッケージマニフェストで機能を宣言します。</span><span class="sxs-lookup"><span data-stu-id="8b139-241">You request access by declaring capabilities in the package manifest for your app.</span></span>  <span data-ttu-id="8b139-242">Visual Studio では、package.appxmanifest designer の [**機能**] パネルで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8b139-242">In Visual Studio, you are able to do this from the **Capabilities** panel of the package.appxmanifest designer.</span></span>  

![Visual Studio package.appxmanifest designer の [機能] パネル](media/vs-appxmanifest-editor-capabilities.png)  

<span data-ttu-id="8b139-244">このチュートリアルでは、既定のインターネット \ (クライアント \) 機能のみを使う必要があるため、これ以上の操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8b139-244">In this tutorial, only the default Internet \(Client\) capability is required, so no further action is needed.</span></span>  

### <span data-ttu-id="8b139-245">機能検出を使って WinRT を呼び出す</span><span class="sxs-lookup"><span data-stu-id="8b139-245">Use feature detection to invoke WinRT</span></span>  

<span data-ttu-id="8b139-246">すべてのプラットフォームで PWA のユーザーエクスペリエンスの品質を向上させるために、WinRT 機能検出を使って、Windows での PWA の操作性を段階的に向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="8b139-246">To ensure a quality baseline experience for your PWA audience across all platforms, you progressively enhance your PWA experience on Windows using WinRT feature detection.</span></span>  <span data-ttu-id="8b139-247">こうすることで、Windows 固有のコードが、WinRT Api が利用可能で適用可能なコンテキストでのみ実行されることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8b139-247">This way, you are able to be sure your Windows-specific code is only run in a context where WinRT APIs are available and applicable.</span></span>  

<span data-ttu-id="8b139-248">機能検出は、次のように、 `Windows` オブジェクト \ ( [WinRT 名前空間][UwpApiIndex]へのエントリポイント) を簡単に探している場合があります。</span><span class="sxs-lookup"><span data-stu-id="8b139-248">Feature detection may be as simple as looking for the `Windows` object \(the entrypoint to the [WinRT namespace][UwpApiIndex]\) as below:</span></span>  

```javascript
if(window.Windows){
    /*Run code that sends Windows API requests */
}
```  

<span data-ttu-id="8b139-249">ただし、すべての windows [10 デバイスの種類][UwpExtensionSdkDeviceFamiliesOverview]ですべての windows api を使用できるわけではありませんが、一般的に、送信する API 要求の名前空間をさらに限定するために、より具体的な機能検出を使うと便利です。</span><span class="sxs-lookup"><span data-stu-id="8b139-249">However, given that not all Windows APIs are available on all [Windows 10 device types][UwpExtensionSdkDeviceFamiliesOverview], it is generally useful to use more specific feature detection to further qualify the namespace of the API request you are sending:</span></span>  

```javascript
if(window.Windows && Windows.Media.SpeechRecognition){
    /*Run code that sends Windows API requests */
}
```  

<span data-ttu-id="8b139-250">この背景を使って、カスタムコンテキストメニューを実装するための WinRT コードを追加する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="8b139-250">With that background, you are ready to add some WinRT code to implement a custom context menu.</span></span>  <span data-ttu-id="8b139-251">サンプル PWA を使って[プログレッシブ Web アプリ][PwaGetStarted]を使い始める場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8b139-251">If you are using the sample PWA from [Get started with Progressive Web Apps][PwaGetStarted]:</span></span>

1.  <span data-ttu-id="8b139-252">Visual Studio を PWA サイトプロジェクトで開きます。</span><span class="sxs-lookup"><span data-stu-id="8b139-252">Open Visual Studio to your PWA site project.</span></span>

1.  <span data-ttu-id="8b139-253">ソリューションエクスプローラーで、ファイルを開き、 `views\layout.pug` 次の行をサービスワーカーの参照のすぐ下に追加し `script` ます。</span><span class="sxs-lookup"><span data-stu-id="8b139-253">In Solution Explorer, open the `views\layout.pug` file and add the following line, right below the `script` reference for your service worker:</span></span>
    
    ```xml
    script(src='/javascripts/site.js')
    ```  

1.  <span data-ttu-id="8b139-254">ソリューションエクスプローラーで、フォルダーを右クリックし、[ `javascripts` **Add**  >  **新しいファイル**の追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b139-254">In Solution Explorer, right-click on the `javascripts` folder and **Add** > **New File...**.</span></span>

1.  <span data-ttu-id="8b139-255">ファイルに名前 `site.js` を付けて、次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="8b139-255">Name your file: `site.js`, and copy in the following code:</span></span>
    
    ```javascript
    if (window.Windows && Windows.UI.Popups) {
        document.addEventListener('contextmenu', function (e) {

            // Build the context menu
            var menu = new Windows.UI.Popups.PopupMenu();
            menu.commands.append(new Windows.UI.Popups.UICommand("Option 1", null, 1));
            menu.commands.append(new Windows.UI.Popups.UICommandSeparator);
            menu.commands.append(new Windows.UI.Popups.UICommand("Option 2", null, 2));

            // Convert from webpage to WinRT coordinates
            function pageToWinRT(pageX, pageY) {
                var zoomFactor = document.documentElement.msContentZoomFactor;
                return {
                    x: (pageX - window.pageXOffset) * zoomFactor,
                    y: (pageY - window.pageYOffset) * zoomFactor
                };
            }

            // When the menu is invoked, execute the requested command
            menu.showAsync(pageToWinRT(e.pageX, e.pageY)).done(function (invokedCommand) {
                if (invokedCommand !== null) {
                    switch (invokedCommand.id) {
                        case 1:
                            console.log('Option 1 selected');
                            // Invoke code for option 1
                            break;
                        case 2:
                            console.log('Option 2 selected');
                            // Invoke code for option 2
                            break;
                        default:
                            break;
                    }
                } else {
                    // The command is null if no command was invoked.
                    console.log("Context menu dismissed");
                }
            });
        }, false);
    }
    ```

1.  <span data-ttu-id="8b139-256">ブラウザーで PWA を実行するときのコンテキストメニューの動作 ( `F5` pwa サイトプロジェクトから) と、windows アプリウィンドウの内部 ( `F5` ユニバーサル Windows アプリプロジェクトなど) を比較します。</span><span class="sxs-lookup"><span data-stu-id="8b139-256">Compare the context menu behavior when you run your PWA in the browser \(`F5` from your PWA site project\) versus from inside the Windows app window \(`F5` from your Universal Windows app project\).</span></span>  <span data-ttu-id="8b139-257">ブラウザーで右クリックすると、Microsoft Edge の既定のコンテキストメニューが `WWAHost.exe` 表示されます。プロセスでは、カスタムメニューが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8b139-257">In the browser, right-clicking gives you the Microsoft Edge default context menu, whereas in the `WWAHost.exe` process, your custom menu now appears.</span></span>  

    | <span data-ttu-id="8b139-258">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8b139-258">Microsoft Edge</span></span> | <span data-ttu-id="8b139-259">Windows 10 アプリ</span><span class="sxs-lookup"><span data-stu-id="8b139-259">Windows 10 app</span></span> |  
    |:--- |:---- |  
    | ![ブラウザーの既定のコンテキストメニュー](media/browser-context-menu.png) | ![アプリのカスタムコンテキストメニュー](media/app-context-menu.png) |  

<span data-ttu-id="8b139-262">この時点では、Windows で PWAs を段階的に強化するための堅固な基盤が用意されています。</span><span class="sxs-lookup"><span data-stu-id="8b139-262">Hopefully you now have a solid foundation for progressively enhancing your PWAs on Windows.</span></span>  <span data-ttu-id="8b139-263">質問がある場合や、何か不明確な点がある場合は、コメントを送信してください。</span><span class="sxs-lookup"><span data-stu-id="8b139-263">If you run into questions or anything is unclear, please send a comment!</span></span>  

## <span data-ttu-id="8b139-264">追加情報</span><span class="sxs-lookup"><span data-stu-id="8b139-264">Going further</span></span>

<span data-ttu-id="8b139-265">[Windows デベロッパーセンター][MicrosoftDeveloperWindowsApps]は、windows アプリ構築のすべての段階 ([[はじめ][MicrosoftDeveloperWindowsAppsGetStarted]に] から [設計]、[[設計][MicrosoftDeveloperWindowsAppsDesign]]、[[開発][MicrosoftDeveloperWindowsAppsDevelop]]、[Microsoft Store への[発行][MicrosoftDeveloperStorePublishApps]] まで) を網羅した包括的なリファレンスです。</span><span class="sxs-lookup"><span data-stu-id="8b139-265">The [Windows Dev Center][MicrosoftDeveloperWindowsApps] is your complete reference for all stages of Windows app building, from [getting started][MicrosoftDeveloperWindowsAppsGetStarted], to [designing][MicrosoftDeveloperWindowsAppsDesign], [developing][MicrosoftDeveloperWindowsAppsDevelop], and [publishing][MicrosoftDeveloperStorePublishApps] to the Microsoft Store.</span></span>  

<span data-ttu-id="8b139-266">ユニバーサル Windows プラットフォーム \ (UWP) の一般的な概要と、さまざまな Windows 10 デバイスファミリのターゲットを設定する方法については、「[ユニバーサル Windows プラットフォームの概要][WindowsUWPGetStartedGuide]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b139-266">For a general overview on the Universal Windows Platform \(UWP\) and how to target different Windows 10 device families, see [Intro to the Universal Windows Platform][WindowsUWPGetStartedGuide].</span></span>  

<span data-ttu-id="8b139-267">準備ができたら、次のようにして、 [Microsoft ストアに PWA を提出](./microsoft-store.md)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8b139-267">And when you are ready, here is how \(and why!\) to [Submit your PWA to the Microsoft Store](./microsoft-store.md).</span></span>  

<!-- image links -->  

<!-- links -->  

[PwaGetStarted]: ./get-started.md "プログレッシブ Web アプリの使用を開始する"  
[PwaIndexWindows10]: ./index.md#pwas-on-windows-10-edgehtml "PWAs は Windows 10 (EdgeHTML) にあります。 Windows のプログレッシブ Web アプリ"  
[DevToolsGuide]: ../devtools-guide.md "Microsoft Edge (EdgeHTML) 開発者ツール"  
[DevToolsGuideMicrosoftStoreApp]: ../devtools-guide.md#microsoft-store-app "Microsoft ストアアプリ-Microsoft Edge (EdgeHTML) 開発者ツール"  
[DevToolsGuideServiceWorkers]: ../devtools-guide/service-workers.md "サービス ワーカー"  
[DevToolsProtocol01ClientsEdgePreview]: ../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge の DevTools プレビュー - DevTools プロトコル クライアント"  
[DevGuideWhatsNew]: ../dev-guide/whats-new.md "EdgeHTML の新機能"  
[WindowsRuntime]: ../windows-runtime/index.md "JavaScript の Windows ランタイム (WinRT)"  
[WindowRuntimeUsingJavascript]: ../windows-runtime/using-the-windows-runtime-in-javascript.md "JavaScript での Windows ランタイムの使用"  

[ScriptingJsinrtHandlingWinRTEvents]: /scripting/jswinrt/handling-windows-runtime-events-in-javascript "JavaScript での Windows ランタイムイベントの処理"  
[ScriptingJsinrtUsingWinRT]: /scripting/jswinrt/using-windows-runtime-asynchronous-methods "Windows ランタイム非同期メソッドの使用"  
[ScriptingJsinrtUsingWinRTCasingConventions]:  /scripting/jswinrt/using-the-windows-runtime-in-javascript#casing-conventions-with-windows-runtime-features "Windows ランタイム機能を使用した大文字と小文字の規則-JavaScript での Windows ランタイムの使用"  
[UwpApiIndex]: /uwp/api/index "Windows UWP の名前空間"  
[UwpApiWindowsUiPopups]: /uwp/api/windows.ui.popups "Windows UI のポップアップ名前空間"  
[UwpApiWindowsUiWebuiWebapplicationActivated]: /uwp/api/windows.ui.webui.webuiapplication.activated "WebUIApplication イベント"  
[UwpExtensionSdkDeviceFamiliesOverview]: /uwp/extension-sdks/device-families-overview "デバイスファミリの概要"  
[UwpSchemasAppxpackageUapmanifestschemaGeneratePackageManifest]: /uwp/schemas/appxpackage/uapmanifestschema/generate-package-manifest "Visual Studio でアプリパッケージマニフェストが生成される方法"  
[WindowsUWPIndex]: /windows/uwp/index "ユニバーサル Windows プラットフォームのドキュメント"  
[WindowsUWPGetStartedGuide]: /windows/uwp/get-started/universal-application-platform-guide "ユニバーサル Windows プラットフォーム (UWP) アプリとは何ですか?"  
[WindowsUWPGetStartedEnable]: /windows/uwp/get-started/enable-your-device-for-development "デバイスを開発用に有効にする"  
[WindowsUwpSecurityIndex]: /windows/uwp/security/index "証券"  
[WindowsUwpPublishAccountTypesLocationsFees]: /windows/uwp/publish/account-types-locations-and-fees "アカウントの種類、場所、料金"  
[WindowsUwpPackagingAppCapabilitiesSpecialRestricted]: /windows/uwp/packaging/app-capability-declarations#special-and-restricted-capabilities "制限された機能"  
[WindowsUwpPackagingAppCapabilitiesDevice]: /windows/uwp/packaging/app-capability-declarations#device-capabilities "デバイスの機能"  
[WindowsUwpPackagingAppCapabilitiesGeneralUse]: /windows/uwp/packaging/app-capability-declarations#general-use-capabilities "一般的な用途の機能"  
[WindowsUwpPackagingAppCapabilities]: /windows/uwp/packaging/app-capability-declarations "アプリ機能の宣言"  

[BingResultsWindows10Settings]: https://binged.it/2lOGSH0 "windows 10 の設定-Bing"  
[GithubWinjsWinjs]: https://github.com/winjs/winjs "winjs/winjs |GitHub"  
[MicrosoftDeveloperStorePublishApps]: https://developer.microsoft.com/store/publish-apps/index "Windows アプリとゲームを公開する"  
[MicrosoftDeveloperWindowsApps]: https://developer.microsoft.com/windows/apps/index "ユニバーサル Windows プラットフォームのドキュメント"  
[MicrosoftDeveloperWindowsAppsDesign]: https://developer.microsoft.com/windows/apps/design/index "Windows アプリの設計とコードの作成"  
[MicrosoftDeveloperWindowsAppsDevelop]: https://developer.microsoft.com/windows/apps/develop/index "UWP アプリの開発"  
[MicrosoftDeveloperWindowsAppsGetStarted]: https://developer.microsoft.com/windows/apps/getstarted/index "Windows 10 アプリの使用を開始する"  
[MicrosoftDeveloperWindowsSamples]: https://developer.microsoft.com/windows/samples "コードサンプル"  
[MicrosoftStoreEdgeDevtoolsPreview]: https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj "Microsoft Edge DevTools プレビュー"  
[MicrosoftSupportWindowsAppPermissions]: https://support.microsoft.com/help/10557/windows-10-app-permissions "アプリのアクセス許可"  
[MicrosoftVisualStudioDownloads]: https://visualstudio.microsoft.com/downloads "入手"  
[MicrosoftVisualStudioPreview]: https://visualstudio.microsoft.com/vs/preview "Visual Studio Preview"  
