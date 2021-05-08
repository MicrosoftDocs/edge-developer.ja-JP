---
description: WebView2 コントロールをデバッグする方法について説明します。
title: WebView2 アプリケーションのデバッグを開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、Webview2、Webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、エッジ html
ms.openlocfilehash: f895634d5e005bb07579d9a5f41c6a988cd78a33
ms.sourcegitcommit: e3cd336c9448277e0dde3b9da1521b5cbc7c44d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "11536608"
---
# <a name="get-started-debugging-webview2-apps"></a><span data-ttu-id="d9b2e-104">WebView2 アプリのデバッグを開始する</span><span class="sxs-lookup"><span data-stu-id="d9b2e-104">Get started debugging WebView2 apps</span></span>  

<span data-ttu-id="d9b2e-105">WebView2 コントロールMicrosoft Edge目的は、Web アプリ開発機能とネイティブ アプリ開発機能とツールの両方を組み合わせることです。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-105">The goal of the Microsoft Edge WebView2 control is to combine the best of both the web and native app development features and tools.</span></span>  <span data-ttu-id="d9b2e-106">WebView2 アプリを開発する場合は、アプリをデバッグする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-106">When you develop your WebView2 app, you should debug your app.</span></span>  <span data-ttu-id="d9b2e-107">この記事では、WebView2 アプリで Web コードとネイティブ コードの両方をデバッグするために使用するさまざまなツールの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-107">This article outlines the different tools to use to debug both your web and native code in your WebView2 app.</span></span>  

## [<a name="microsoft-edge-devtools"></a><span data-ttu-id="d9b2e-108">Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="d9b2e-108">Microsoft Edge DevTools</span></span>](#tab/devtools)  

<span data-ttu-id="d9b2e-109">[WebView2 Microsoft Edge (Chromium)][DevtoolsGuideChromiumMain]開発者ツールを使用して、WebView2 コントロールに表示される Web コンテンツをデバッグする場合と同じ方法で、webView2 コントロールに表示される別の web ページをデバッグMicrosoft Edge。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-109">Use [Microsoft Edge (Chromium) Developer Tools][DevtoolsGuideChromiumMain] to debug web content displayed in WebView2 controls, in the same way that you may debug for another webpage displayed in Microsoft Edge.</span></span>  <span data-ttu-id="d9b2e-110">DevTools を開く場合は、WebView コントロールにフォーカスを設定し、次のいずれかのアクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-110">To open the DevTools, set focus on the WebView control and then use one of the following actions.</span></span>  

*   <span data-ttu-id="d9b2e-111">`F12` を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-111">Select `F12`.</span></span>  
*   <span data-ttu-id="d9b2e-112">を選択します `Ctrl` + `Shift` + `I` 。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-112">Select `Ctrl`+`Shift`+`I`.</span></span>  
*   <span data-ttu-id="d9b2e-113">コンテキスト メニュー \(右クリック\) を開き、 を選択します `Inspect` 。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-113">Open the context menu \(right-click\) and choose `Inspect`.</span></span>  
    
<span data-ttu-id="d9b2e-114">詳細については [、「DevTools の概要」に移動します][DevtoolsGuideChromiumMain]。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-114">For more information, navigate to [DevTools overview][DevtoolsGuideChromiumMain].</span></span>  

:::image type="complex" source="./media/f12.png" alt-text="DevTools のデバッグ" lightbox="./media/f12.png":::
   <span data-ttu-id="d9b2e-116">DevTools のデバッグ</span><span class="sxs-lookup"><span data-stu-id="d9b2e-116">DevTools debugging</span></span>  
:::image-end:::  

## [<a name="visual-studio"></a><span data-ttu-id="d9b2e-117">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d9b2e-117">Visual Studio</span></span>](#tab/visualstudio)  

<span data-ttu-id="d9b2e-118">Visual Studio WebView2 アプリでは、Web およびネイティブ コード用のさまざまなデバッグ ツールが提供されます。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-118">Visual Studio provides various debugging tools for web and native code in WebView2 apps.</span></span>  <span data-ttu-id="d9b2e-119">[Visual Studio] セクションでは、主に WebView コントロールのデバッグを行っていますが、WebView コントロールのデバッグ方法Visual Studio使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-119">In the Visual Studio section, the primary focus is debugging WebView controls, however the other methods of debugging in Visual Studio are available as usual.</span></span>  <span data-ttu-id="d9b2e-120">Win32 アプリまたはアドインでのみ Web およびネイティブ コードをデバッグするには、次Officeを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-120">Use the following process to debug web and native code in Win32 apps or Office Add-ins only.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="d9b2e-121">ネイティブ デバッガーが接続されたVisual Studioでアプリをデバッグすると、開発者ツールの代わりにネイティブ デバッガーが `F12` トリガーされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-121">When you debug your app in Visual Studio with the native debugger attached, selecting `F12` may trigger the native debugger instead of Developer Tools.</span></span>  <span data-ttu-id="d9b2e-122">状況 `Ctrl` + `Shift` + `I` を回避するには、コンテキスト メニュー \(右クリック\) を選択するか、または使用します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-122">Select `Ctrl`+`Shift`+`I`, or use the context menu \(right-click\) to avoid the situation.</span></span>  

<span data-ttu-id="d9b2e-123">開始する前に、次の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-123">Before you begin, ensure the following requirements are met.</span></span>  

*   <span data-ttu-id="d9b2e-124">スクリプトをデバッグするには、アプリをアプリ内から起動するVisual Studio。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-124">To debug scripts, the app must be launched from within Visual Studio.</span></span>  
*   <span data-ttu-id="d9b2e-125">実行中の WebView2 プロセスにデバッガーを接続することはできません。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-125">You cannot attach a debugger to a running WebView2 process.</span></span>  
*   <span data-ttu-id="d9b2e-126">2019 Visual Studio 16.4 プレビュー 2 以降をインストールします。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-126">Install Visual Studio 2019 version 16.4 Preview 2 or later.</span></span>  
    
<span data-ttu-id="d9b2e-127">スクリプト デバッガー ツールをインストールし、スクリプト デバッガー ツールをVisual Studio。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-127">Install and set up the script debugger tools in Visual Studio.</span></span>  

1.  <span data-ttu-id="d9b2e-128">C++ によるデスクトップ開発で **JavaScript 診断** コンポーネントをインストールするには、 **次のアクションを実行します**。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-128">Complete the following actions to install the **JavaScript diagnostics** component in **Desktop development with C++**.</span></span>  
    
    1.  <span data-ttu-id="d9b2e-129">[エクスプローラー] バー Windows入力します `Visual Studio Installer` 。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-129">In the Windows Explorer bar, type `Visual Studio Installer`.</span></span>  
    1.  <span data-ttu-id="d9b2e-130">**[Visual Studio インストーラー]** を選択して開きます。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-130">Choose **Visual Studio Installer** to open it.</span></span>  
    1.  <span data-ttu-id="d9b2e-131">[追加] Visual Studio インストーラーインストールされているバージョンで、[その他]\*\*\*\* ボタンを選択し、[変更] を**選択します**。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-131">In the Visual Studio Installer, on the installed version, choose the **More** button, and then choose **Modify**.</span></span>  
    1.  <span data-ttu-id="d9b2e-132">[Visual Studio] の **[ワークロード] で\*\*\*\*、[C++ のデスクトップ開発] 設定を選択**します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-132">In Visual Studio, under **Workloads**, choose the **Desktop Development in C++** setting.</span></span>  
        
        :::image type="complex" source="./media/workloads.png" alt-text="Visual Studio[ワークロードの変更] 画面" lightbox="./media/workloads.png":::
            <span data-ttu-id="d9b2e-134">Visual Studio[ワークロードの変更] 画面</span><span class="sxs-lookup"><span data-stu-id="d9b2e-134">Visual Studio Modifying Workloads Screen</span></span>
        :::image-end:::  
        
    1.  <span data-ttu-id="d9b2e-135">[個別 **のコンポーネント] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-135">Choose **Individual components**.</span></span>  
    1.  <span data-ttu-id="d9b2e-136">検索ボックスに「 」 と入力 `JavaScript diagnostics` します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-136">In the search box, enter `JavaScript diagnostics`.</span></span>  
    1.  <span data-ttu-id="d9b2e-137">**[JavaScript 診断] 設定を選択**します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-137">Choose the **JavaScript diagnostics** setting.</span></span>  
    1.  <span data-ttu-id="d9b2e-138">[変更 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-138">Choose **Modify**.</span></span> 
        
        :::image type="complex" source="./media/indivcomp.png" alt-text="Visual Studio[個々のコンポーネントの変更] タブ" lightbox="./media/indivcomp.png":::
           <span data-ttu-id="d9b2e-140">Visual Studio[個々のコンポーネントの変更] タブ</span><span class="sxs-lookup"><span data-stu-id="d9b2e-140">Visual Studio Modifying Individual Components Tab</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="d9b2e-141">WebView2 アプリのスクリプト デバッグを有効にする。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-141">Enable script debugging for WebView2 apps.</span></span>  
    1.  <span data-ttu-id="d9b2e-142">WebView2 プロジェクトで、コンテキスト メニュー \(右クリック\) を開き、[プロパティ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-142">In your WebView2 project, open the context menu \(right-click\), and choose **Properties**.</span></span>  
    1.  <span data-ttu-id="d9b2e-143">[構成プロパティ **] で、[** デバッグ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-143">Under the **Configuration Properties**, choose **Debugging**.</span></span>  
    1.  <span data-ttu-id="d9b2e-144">[デバッガーの**種類] で\*\*\*\*、[JavaScript (WebView2) ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-144">Under the **Debugger Type**, choose **JavaScript (WebView2)**.</span></span>  
        
        :::image type="complex" source="./media/enbjs.png" alt-text="Visual Studio構成プロパティのデバッグ" lightbox="./media/enbjs.png":::
           <span data-ttu-id="d9b2e-146">Visual Studio**デバッグ**構成プロパティ</span><span class="sxs-lookup"><span data-stu-id="d9b2e-146">Visual Studio **Debugging** Configuration Property</span></span>  
        :::image-end:::  
        
<span data-ttu-id="d9b2e-147">WebView2 アプリをデバッグするには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-147">Complete the following actions to debug your WebView2 app.</span></span>  

1.  <span data-ttu-id="d9b2e-148">ソース コードでブレークポイントを設定するには、行番号の左側にマウス ポインターを置き、ブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-148">To set a breakpoint in your source code, hover to the left of the line number, and choose to set a breakpoint.</span></span>  <span data-ttu-id="d9b2e-149">JS/TS デバッグ アダプターは、ソース パスマッピングを実行しない。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-149">The JS/TS debug adapter does not perform source path mapping.</span></span>  <span data-ttu-id="d9b2e-150">WebView2 に関連付けられたまったく同じパスを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-150">You must open the exact same path associated with your WebView2.</span></span>  
    
    :::image type="complex" source="./media/breakpoint.png" alt-text="Visual Studioブレークポイントの追加" lightbox="./media/breakpoint.png"::: 
       <span data-ttu-id="d9b2e-152">Visual Studioブレークポイントの追加</span><span class="sxs-lookup"><span data-stu-id="d9b2e-152">Visual Studio add breakpoint</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d9b2e-153">デバッガーを実行するには、プラットフォームのビット サイズを選択し、[ローカル デバッガー] の横にある緑色の再生**ボタンWindowsします**。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-153">To run the debugger, choose the bit size of the platform, and then choose the green play button next to **Local Windows Debugger**.</span></span>  <span data-ttu-id="d9b2e-154">アプリが実行され、デバッガーは作成された最初の WebView2 プロセスに接続します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-154">The app runs and the debugger connects to the first WebView2 process that is created.</span></span>  
    
    :::image type="complex" source="./media/run.png" alt-text=" Visual Studioローカル Windows デバッガー" lightbox="./media/run.png"::: 
       <span data-ttu-id="d9b2e-156">Visual Studio ローカル**Windows デバッガー**</span><span class="sxs-lookup"><span data-stu-id="d9b2e-156">Visual Studio **Local Windows Debugger**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d9b2e-157">デバッグ コンソール **で、** デバッガーからの出力を見つける。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-157">In the **Debug Console**, find the output from the debugger.</span></span>  
    
    :::image type="complex" source="./media/console.png" alt-text=" Visual Studioデバッグ コンソール" lightbox="./media/console.png"::: 
       <span data-ttu-id="d9b2e-159">Visual Studio デバッグ**コンソール**</span><span class="sxs-lookup"><span data-stu-id="d9b2e-159">Visual Studio **Debug Console**</span></span>  
    :::image-end:::  
    
## [<a name="visual-studio-code"></a><span data-ttu-id="d9b2e-160">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d9b2e-160">Visual Studio Code</span></span>](#tab/visualstudiocode)  

<span data-ttu-id="d9b2e-161">WebView2 Microsoft Visual Studio実行するスクリプトをデバッグするには、コードコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-161">Use Microsoft Visual Studio Code to debug scripts that run in WebView2 controls.</span></span>  <!--Ensure that you're using Visual Studio Code version [insert build here] or later.  -->  

<span data-ttu-id="d9b2e-162">このVisual Studio Code、次のアクションを実行してコードをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-162">In Visual Studio Code, complete the following actions to debug your code.</span></span> 

1.  <span data-ttu-id="d9b2e-163">プロジェクトにファイルが必要 `launch.json` です。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-163">Your project is required to have a `launch.json` file.</span></span>  <span data-ttu-id="d9b2e-164">プロジェクトにファイルが含されていない場合は、次のコード スニペットを `launch.json` コピーし、新しいファイルを作成 `launch.json` します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-164">If your project doesn't have a `launch.json` file, copy the following code snippet and create a new `launch.json` file.</span></span>  
    
    ```json
        "name": "Hello debug world",
        "type": "pwa-msedge",
        "port": 9222, // The port value is optional, and the default value is 9222.
        "request": "launch",
        "runtimeExecutable": "C:/path/to/your/webview2/app.exe",
        "env": {
            // Customize for your app location if needed
            "Path": "%path%;e:/path/to/your/app/location; "
        },
        "useWebView": true,
        // The following two lines setup source path mapping, where `url` is the start page of your app, and `webRoot` is the top level directory with all your code files.
        "url": "file:///${workspaceFolder}/path/to/your/toplevel/foo.html",
        "webRoot": "${workspaceFolder}/path/to/your/assets"
    ```  
    
    > [!NOTE]
    > <span data-ttu-id="d9b2e-165">Visual Studio Codeパス マッピングには URL が必要なので、アプリは開始時にコマンド ライン パラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-165">Visual Studio Code source path mapping now requires the URL, so your app now receives a command-line parameter when it starts.</span></span>  <span data-ttu-id="d9b2e-166">必要に応じて、パラメーター `url` を無視しても問題ない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-166">You may safely ignore the `url` parameter if needed.</span></span>  
    
1.  <span data-ttu-id="d9b2e-167">ソース コードでブレークポイントを設定するには、行にカーソルを合わせると、</span><span class="sxs-lookup"><span data-stu-id="d9b2e-167">To set a breakpoint in your source code, hover on the line, and select</span></span> `F9`
    
    :::image type="complex" source="./media/breakpointvs.png" alt-text="ブレークポイントが設定されているVisual Studio Code" lightbox="./media/breakpointvs.png":::
       <span data-ttu-id="d9b2e-169">ブレークポイントが設定されているVisual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d9b2e-169">Breakpoint is set in Visual Studio Code</span></span>  
    :::image-end:::
    
1.  <span data-ttu-id="d9b2e-170">コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-170">Run the code.</span></span>  
    1.  <span data-ttu-id="d9b2e-171">[実行 **] タブ** で、ドロップダウン メニューから起動構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-171">On the **Run** tab, choose the launch configuration from the dropdown menu.</span></span>  
    1.  <span data-ttu-id="d9b2e-172">アプリのデバッグを開始するには、[デバッグの開始] を選択します。これは、起動構成ドロップダウンの横にある緑色の三角形です。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-172">To start debugging your app, choose Start Debugging, which is the green triangle next to the launch configuration drop down.</span></span>  
        
        :::image type="complex" source="./media/runvs.png" alt-text=" Visual Studio Code[実行] タブ" lightbox="./media/runvs.png":::
           <span data-ttu-id="d9b2e-174">Visual Studio Code[実行] タブ</span><span class="sxs-lookup"><span data-stu-id="d9b2e-174">Visual Studio Code Run tab</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="d9b2e-175">デバッグ **出力とエラー** を表示するには、[デバッグ コンソール] を開きます。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-175">Open **Debug Console** to view the debug output and errors.</span></span>  
    
    :::image type="complex" source="./media/resultsvs.png" alt-text=" Visual Studio Codeデバッグ コンソール" lightbox="./media/resultsvs.png":::
       <span data-ttu-id="d9b2e-177">Visual Studio Codeデバッグ コンソール</span><span class="sxs-lookup"><span data-stu-id="d9b2e-177">Visual Studio Code Debug Console</span></span>  
    :::image-end:::  
    
<span data-ttu-id="d9b2e-178">**高度な設定:**</span><span class="sxs-lookup"><span data-stu-id="d9b2e-178">**Advanced Settings**:</span></span>  

*   <span data-ttu-id="d9b2e-179">ターゲット Webview のデバッグ。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-179">Targeted Webview debugging.</span></span> 
    
    <span data-ttu-id="d9b2e-180">一部の WebView2 アプリでは、複数の WebView2 コントロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-180">In some WebView2 apps, you may use more than one WebView2 control.</span></span> <span data-ttu-id="d9b2e-181">この状況でデバッグする WebView2 コントロールを選択するには、ターゲット Webview2 デバッグを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-181">To pick the WebView2 control to debug in this situation you can use targeted webview2 debugging</span></span> 
    
    <span data-ttu-id="d9b2e-182">ターゲット `launch.json` Webview デバッグを使用するには、次のアクションを開いて完了します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-182">Open `launch.json` and complete the following actions to use targeted Webview debugging.</span></span>  
    
    1.  <span data-ttu-id="d9b2e-183">パラメーターが `useWebview` に設定されているを確認します `true` 。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-183">Confirm that the `useWebview` parameter is set to `true`.</span></span>  
    1.  <span data-ttu-id="d9b2e-184">パラメーターを追加 `urlFilter` します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-184">Add the `urlFilter` parameter.</span></span>  <span data-ttu-id="d9b2e-185">WebView2 コントロールが URL に移動すると、URL に表示される文字列を比較するためにパラメーター値 `urlFilter` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-185">When the WebView2 control navigates to a URL, the `urlFilter` parameter value is used to compare strings that appear in the URL.</span></span>  
    
    ```json
    "useWebview": "true",
    "urlFilter": "*index.ts",
    
    // Other urlFilter options.
    
    urlFilter="*index.ts"    // Match any url that ends with index.ts, and ignore all leading characters. 
    urlFilter="*index*"      // Match any url that contains the string index anywhere in the URL.  
    urlFilter="file://C:/path/to/my/index.ts," // To match explicit file called index.ts.  
    ```  
    
    <span data-ttu-id="d9b2e-186">アプリをデバッグするときに、レンダリング プロセスの最初からコードをステップ実行する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-186">When debugging your app, you may need to step through the code from the beginning of the rendering process.</span></span> <span data-ttu-id="d9b2e-187">サイトで Web ページをレンダリングし、ソース コードにアクセスできない場合は、認識されていないパラメーターは Web ページで無視されますので、このオプション `?=value`  を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-187">If you are rendering webpages on sites and you don't have access to the source code, you can use the `?=value` option, because webpages ignore unrecognized parameters.</span></span>   
    
    > [!IMPORTANT]
    > <span data-ttu-id="d9b2e-188">URL で最初の一致が見つかったら、デバッガーは停止します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-188">After the first match is found in the URL, the debugger stops.</span></span>  <span data-ttu-id="d9b2e-189">CDP ポートは、すべての WebView2 コントロールで共有され、1 つのポート番号を使用するので、2 つの WebView2 コントロールを同時にデバッグすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-189">You cannot debug two WebView2 controls at the same time because the CDP port is shared by all WebView2 controls, and uses a single port number.</span></span>  
    
*   <span data-ttu-id="d9b2e-190">実行中のプロセスのデバッグ</span><span class="sxs-lookup"><span data-stu-id="d9b2e-190">Debug running processes</span></span>  
    
    <span data-ttu-id="d9b2e-191">実行中の WebView2 プロセスにデバッガーを接続する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-191">You may need to attach the debugger to running WebView2 processes.</span></span> <span data-ttu-id="d9b2e-192">これを行うには、 `launch.json` にパラメーターを `request` 更新します `attach` 。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-192">To do that, in `launch.json`, update the `request` parameter to `attach`.</span></span>
    
    ```json
        "name": "Hello debugging world",
        "type": "pwa-msedge",
        "port": 9222, 
        "request": "attach",
        "runtimeExecutable": "C:/path/to/your/webview2/app.exe",  
        "env": {
            "Path": "%path%;e:/path/to/your/build/location; "  
        },
        "useWebView": true
    ```  
    
    <span data-ttu-id="d9b2e-193">WebView2 コントロールは、WebView2 コントロールのデバッグを許可するために CDP ポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-193">Your WebView2 control must open the CDP port to allow debugging of the WebView2 control.</span></span>  <span data-ttu-id="d9b2e-194">デバッガーを開始する前に、1 つの WebView2 コントロールだけが Chrome Developer Protocol (CDP) ポートを開いているか確認するために、コードをビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-194">Your code must be built to ensure that only one WebView2 control has a Chrome Developer Protocol (CDP) port open, before starting the debugger.</span></span>  
    
*   <span data-ttu-id="d9b2e-195">デバッグ トレース オプション</span><span class="sxs-lookup"><span data-stu-id="d9b2e-195">Debug tracing options</span></span>  
    
    <span data-ttu-id="d9b2e-196">デバッグ トレース `trace` を有効にするには、launch.jsにパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-196">Add the `trace` parameter to launch.json to enable debug tracing.</span></span>  
    
    1.  <span data-ttu-id="d9b2e-197">パラメーターを `trace` 追加します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-197">Add `trace` parameter.</span></span>  
        
        :::row:::
           :::column span="":::
              ```json
                "name": "Hello debugging world",
                "type": "pwa-msedge",
                "port": 9222, 
                "request": "attach",
                "runtimeExecutable": "C:/path/to/your/webview2/app.exe",  
                "env": {
                "Path": "%path%;e:/path/to/your/build/location; "  
                },
                "useWebView": true
                ,"trace": true  // Turn on  debug tracing, and save the output to a log file.
              ```  
              
              :::image type="complex" source="./media/tracelog.png" alt-text=" デバッグ出力をログ ファイルに保存します。" lightbox="./media/tracelog.png":::
                 <span data-ttu-id="d9b2e-199">デバッグ出力をログ ファイルに保存する</span><span class="sxs-lookup"><span data-stu-id="d9b2e-199">Save debug output to a log file</span></span>  
              :::image-end:::  
           :::column-end:::
           :::column span="":::
              ```json
              ,"trace": "verbose"  // Turn on verbose tracing in the Debug Output pane.
              ```  
              
              :::image type="complex" source="./media/verbose.png" alt-text=" 詳細出力" lightbox="./media/verbose.png":::
                 <span data-ttu-id="d9b2e-201">Visual Studio Code詳細なトレースを有効にして出力をデバッグする</span><span class="sxs-lookup"><span data-stu-id="d9b2e-201">Visual Studio Code Debug Output with verbose tracing turned on</span></span>  
              :::image-end:::  
           :::column-end:::
        :::row-end:::  
        
*   <span data-ttu-id="d9b2e-202">アドインOfficeデバッグします。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-202">Debug Office Add-ins.</span></span>  
    
    <span data-ttu-id="d9b2e-203">アドインをデバッグするOffice、アドインソース コードを別のインスタンスで開Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-203">If you're debugging Office Add-ins, open the add-in source code in a separate instance of Visual Studio Code.</span></span>  <span data-ttu-id="d9b2e-204">WebView2 launch.jsを開き、次のコード スニペットを追加して、デバッガーをアドインにOfficeします。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-204">Open launch.json in your WebView2 app and add the following code snippet to attach the debugger to the Office add-in.</span></span>
    
    ```json
    ,"debugServer": 4711
    ```  
    
*   <span data-ttu-id="d9b2e-205">デバッガーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d9b2e-205">Troubleshooting the debugger</span></span>  
    
    <span data-ttu-id="d9b2e-206">デバッガーを使用すると、次のシナリオが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-206">You may encounter the following scenarios when using the debugger.</span></span>  
    
    *   <span data-ttu-id="d9b2e-207">デバッガーはブレークポイントで停止しないし、デバッグ出力があります。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-207">The debugger doesn't stop at the breakpoint, and you have debug output.</span></span>  <span data-ttu-id="d9b2e-208">この問題を解決するには、ブレークポイントを持つファイルが WebView2 コントロールで使用されるファイルと同じことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-208">To solve the issue, confirm that the file with the breakpoint is the same file that's used by the WebView2 control.</span></span>  <span data-ttu-id="d9b2e-209">デバッガーはソース パスマッピングを実行しない。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-209">The debugger doesn't perform source path mapping.</span></span>  
    *   <span data-ttu-id="d9b2e-210">実行中のプロセスに接続できないので、タイムアウト エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-210">You can't attach to a running process, and you get a timeout error.</span></span>  <span data-ttu-id="d9b2e-211">この問題を解決するには、WebView2 コントロールが CDP ポートを開いているか確認します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-211">To solve the issue, confirm that the WebView2 control opened the CDP port.</span></span>  <span data-ttu-id="d9b2e-212">レジストリ内  `additionalBrowserArguments`  の値が正しいか、オプションが正しいか確認します。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-212">Ensure your `additionalBrowserArguments` value in the registry is correct, or the options are correct.</span></span>  <span data-ttu-id="d9b2e-213">詳細については [、「additionalBrowserArguments for dotnet」][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments] および [「additionalBrowserArguments for Win32」に移動します][Webview2ReferenceWin32Webview2IdlParameters]。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-213">For more information, navigate to [additionalBrowserArguments for dotnet][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments] and [additionalBrowserArguments for Win32][Webview2ReferenceWin32Webview2IdlParameters].</span></span>  
    
* * *  

## <a name="see-also"></a><span data-ttu-id="d9b2e-214">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9b2e-214">See also</span></span>  

*   <span data-ttu-id="d9b2e-215">WebView2 の使用を開始するには [、「WebView2 Getting Started Guides」に移動します][Webview2MainGettingStarted]。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-215">To get started using WebView2, navigate to [WebView2 Getting Started Guides][Webview2MainGettingStarted].</span></span>  
*   <span data-ttu-id="d9b2e-216">WebView2 機能の包括的な例については[、WebView2Samples][GithubMicrosoftedgeWebview2samples] repo on GitHub。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-216">For a comprehensive example of WebView2 capabilities, navigate to the [WebView2Samples][GithubMicrosoftedgeWebview2samples] repo on GitHub.</span></span>
*   <span data-ttu-id="d9b2e-217">WebView2 API の詳細については、「API リファレンス」 [に移動します][Webview2ApiReference]。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-217">For more detailed information about WebView2 APIs, navigate to [API reference][Webview2ApiReference].</span></span>
*   <span data-ttu-id="d9b2e-218">WebView2 の詳細については [、「WebView2 Resources」に移動します][Webview2MainNextSteps]。</span><span class="sxs-lookup"><span data-stu-id="d9b2e-218">For more information about WebView2, navigate to [WebView2 Resources][Webview2MainNextSteps].</span></span>
    
## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a><span data-ttu-id="d9b2e-219">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="d9b2e-219">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments]: /dotnet/api/microsoft.web.webview2.core.corewebview2environmentoptions.additionalbrowserarguments "CoreWebView2EnvironmentOptions.AdditionalBrowserArguments プロパティ (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[Webview2ReferenceWin32Webview2IdlParameters]: /microsoft-edge/webview2/reference/win32/webview2-idl#createcorewebview2environmentwithoptions  "CreateCoreWebView2Environment - Globals |Microsoft Docs"  
[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft EdgeWebView2 API リファレンス |Microsoft Docs"  
[Webview2MainNextSteps]: ../index.md#next-steps "次の手順 - WebView2 (プレビュー) Microsoft Edgeの概要|Microsoft Docs"  
[Webview2MainGettingStarted]: ../index.md#getting-started "はじめに - WebView2 (プレビュー) Microsoft Edgeの概要|Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  
