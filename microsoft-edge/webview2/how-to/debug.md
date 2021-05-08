---
description: WebView2 コントロールをデバッグする方法について説明します。
title: WebView2 アプリケーションのデバッグを開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、Webview2、Webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、エッジ html
ms.openlocfilehash: 01cd67897f7041bca0cedcee2cc3242f3ebcc962
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "11536036"
---
# <a name="get-started-debugging-webview2-apps"></a><span data-ttu-id="49dc2-104">WebView2 アプリのデバッグを開始する</span><span class="sxs-lookup"><span data-stu-id="49dc2-104">Get started debugging WebView2 apps</span></span>  

<span data-ttu-id="49dc2-105">Microsoft Edge WebView2 コントロールの目的は、Web アプリ開発機能とネイティブ アプリ開発機能とツールの両方を組み合わせることです。</span><span class="sxs-lookup"><span data-stu-id="49dc2-105">The goal of the Microsoft Edge WebView2 control is to combine the best of both the web and native app development features and tools.</span></span>  <span data-ttu-id="49dc2-106">WebView2 アプリを開発する場合は、アプリをデバッグする必要があります。</span><span class="sxs-lookup"><span data-stu-id="49dc2-106">When you develop your WebView2 app, you should debug your app.</span></span>  <span data-ttu-id="49dc2-107">この記事では、WebView2 アプリで Web コードとネイティブ コードの両方をデバッグするために使用するさまざまなツールの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-107">This article outlines the different tools to use to debug both your web and native code in your WebView2 app.</span></span>  

## [<a name="microsoft-edge-devtools"></a><span data-ttu-id="49dc2-108">Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="49dc2-108">Microsoft Edge DevTools</span></span>](#tab/devtools)  

<span data-ttu-id="49dc2-109">[Microsoft Edge (クロム)][DevtoolsGuideChromiumMain]開発者ツールを使用して、WebView2 コントロールに表示される Web コンテンツを、Microsoft Edge に表示される別の Web ページでデバッグするのと同じ方法でデバッグします。</span><span class="sxs-lookup"><span data-stu-id="49dc2-109">Use [Microsoft Edge (Chromium) Developer Tools][DevtoolsGuideChromiumMain] to debug web content displayed in WebView2 controls, in the same way that you may debug for another webpage displayed in Microsoft Edge.</span></span>  <span data-ttu-id="49dc2-110">DevTools を開く場合は、WebView コントロールにフォーカスを設定し、次のいずれかのアクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-110">To open the DevTools, set focus on the WebView control and then use one of the following actions.</span></span>  

*   <span data-ttu-id="49dc2-111">`F12` を選択します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-111">Select `F12`.</span></span>  
*   <span data-ttu-id="49dc2-112">を選択します `Ctrl` + `Shift` + `I` 。</span><span class="sxs-lookup"><span data-stu-id="49dc2-112">Select `Ctrl`+`Shift`+`I`.</span></span>  
*   <span data-ttu-id="49dc2-113">コンテキスト メニュー \(右クリック\) を開き、 を選択します `Inspect` 。</span><span class="sxs-lookup"><span data-stu-id="49dc2-113">Open the context menu \(right-click\) and choose `Inspect`.</span></span>  
    
<span data-ttu-id="49dc2-114">詳細については [、「DevTools の概要」に移動します][DevtoolsGuideChromiumMain]。</span><span class="sxs-lookup"><span data-stu-id="49dc2-114">For more information, navigate to [DevTools overview][DevtoolsGuideChromiumMain].</span></span>  

:::image type="complex" source="./media/f12.png" alt-text="DevTools のデバッグ" lightbox="./media/f12.png":::
   <span data-ttu-id="49dc2-116">DevTools のデバッグ</span><span class="sxs-lookup"><span data-stu-id="49dc2-116">DevTools debugging</span></span>  
:::image-end:::    

## [<a name="visual-studio"></a><span data-ttu-id="49dc2-117">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="49dc2-117">Visual Studio</span></span>](#tab/visualstudio)  

<span data-ttu-id="49dc2-118">Visual Studio WebView2 アプリでは、Web およびネイティブ コード用のさまざまなデバッグ ツールが提供されます。</span><span class="sxs-lookup"><span data-stu-id="49dc2-118">Visual Studio provides various debugging tools for web and native code in WebView2 apps.</span></span>  <span data-ttu-id="49dc2-119">[Visual Studio] セクションでは、主に WebView コントロールのデバッグを行います。ただし、WebView コントロールのデバッグ方法Visual Studio通常どおり使用できます。</span><span class="sxs-lookup"><span data-stu-id="49dc2-119">In the Visual Studio section, the primary focus is debugging WebView controls, however the other methods of debugging in Visual Studio are available as usual.</span></span>  <span data-ttu-id="49dc2-120">Win32 アプリまたはアドインでのみ Web およびネイティブ コードをデバッグするには、次Officeを使用します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-120">Use the following process to debug web and native code in Win32 apps or Office Add-ins only.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="49dc2-121">ネイティブ デバッガーが接続されたVisual Studioでアプリをデバッグすると、開発者ツールの代わりにネイティブ デバッガーが `F12` トリガーされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="49dc2-121">When you debug your app in Visual Studio with the native debugger attached, selecting `F12` may trigger the native debugger instead of Developer Tools.</span></span>  <span data-ttu-id="49dc2-122">状況 `Ctrl` + `Shift` + `I` を回避するには、コンテキスト メニュー \(右クリック\) を選択するか、または使用します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-122">Select `Ctrl`+`Shift`+`I`, or use the context menu \(right-click\) to avoid the situation.</span></span>  

<span data-ttu-id="49dc2-123">開始する前に、次の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="49dc2-123">Before you begin, ensure the following requirements are met.</span></span>  

*   <span data-ttu-id="49dc2-124">スクリプトをデバッグするには、アプリをアプリ内から起動するVisual Studio。</span><span class="sxs-lookup"><span data-stu-id="49dc2-124">To debug scripts, the app must be launched from within Visual Studio.</span></span>  
*   <span data-ttu-id="49dc2-125">実行中の WebView2 プロセスにデバッガーを接続することはできません。</span><span class="sxs-lookup"><span data-stu-id="49dc2-125">You cannot attach a debugger to a running WebView2 process.</span></span>  
*   <span data-ttu-id="49dc2-126">2019 Visual Studio 16.4 プレビュー 2 以降をインストールします。</span><span class="sxs-lookup"><span data-stu-id="49dc2-126">Install Visual Studio 2019 version 16.4 Preview 2 or later.</span></span>  
    
<span data-ttu-id="49dc2-127">スクリプト デバッガー ツールをインストールし、スクリプト デバッガー ツールをVisual Studio。</span><span class="sxs-lookup"><span data-stu-id="49dc2-127">Install and set up the script debugger tools in Visual Studio.</span></span>  

1.  <span data-ttu-id="49dc2-128">C++ によるデスクトップ開発で **JavaScript 診断** コンポーネントをインストールするには、 **次のアクションを実行します**。</span><span class="sxs-lookup"><span data-stu-id="49dc2-128">Complete the following actions to install the **JavaScript diagnostics** component in **Desktop development with C++**.</span></span>  
    1.  <span data-ttu-id="49dc2-129">Windows エクスプローラー バーに「 」 と入力 `Visual Studio Installer` します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-129">In the Windows Explorer bar, type `Visual Studio Installer`.</span></span>  
    1.  <span data-ttu-id="49dc2-130">[インストーラー **Visual Studio開く** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-130">Choose **Visual Studio Installer** to open it.</span></span>  
    1.  <span data-ttu-id="49dc2-131">[インストーラー] Visual Studioインストールされているバージョンで、[その他] ボタン\*\*\*\* を選択し、[変更] を**選択します**。</span><span class="sxs-lookup"><span data-stu-id="49dc2-131">In the Visual Studio Installer, on the installed version, choose the **More** button, and then choose **Modify**.</span></span>  
    1.  <span data-ttu-id="49dc2-132">[Visual Studio] の **[ワークロード] で\*\*\*\*、[C++ のデスクトップ開発] 設定を選択**します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-132">In Visual Studio, under **Workloads**, choose the **Desktop Development in C++** setting.</span></span>  
        
        :::image type="complex" source="./media/workloads.png" alt-text="Visual Studioワークロードの変更画面" lightbox="./media/workloads.png":::
            <span data-ttu-id="49dc2-134">Visual Studioワークロードの変更画面</span><span class="sxs-lookup"><span data-stu-id="49dc2-134">Visual Studio Modifying Workloads Screen</span></span>
        :::image-end:::  
        
    1.  <span data-ttu-id="49dc2-135">[個別 **のコンポーネント] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="49dc2-135">Choose **Individual components**.</span></span>  
    1.  <span data-ttu-id="49dc2-136">検索ボックスに「 」 と入力 `JavaScript diagnostics` します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-136">In the search box, enter `JavaScript diagnostics`.</span></span>  
    1.  <span data-ttu-id="49dc2-137">**[JavaScript 診断] 設定を選択**します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-137">Choose the **JavaScript diagnostics** setting.</span></span>  
    1.  <span data-ttu-id="49dc2-138">[変更 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="49dc2-138">Choose **Modify**.</span></span> 
        
        :::image type="complex" source="./media/indiv-comp.png" alt-text="Visual Studio個々のコンポーネントの変更] タブ" lightbox="./media/indiv-comp.png":::
           <span data-ttu-id="49dc2-140">Visual Studio個々のコンポーネントの変更] タブ</span><span class="sxs-lookup"><span data-stu-id="49dc2-140">Visual Studio Modifying Individual Components Tab</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="49dc2-141">WebView2 アプリのスクリプト デバッグを有効にする。</span><span class="sxs-lookup"><span data-stu-id="49dc2-141">Enable script debugging for WebView2 apps.</span></span>  
    1.  <span data-ttu-id="49dc2-142">WebView2 プロジェクトで、コンテキスト メニュー \(右クリック\) を開き、[プロパティ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="49dc2-142">In your WebView2 project, open the context menu \(right-click\), and choose **Properties**.</span></span>  
    1.  <span data-ttu-id="49dc2-143">[構成プロパティ **] で、[** デバッグ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="49dc2-143">Under the **Configuration Properties**, choose **Debugging**.</span></span>  
    1.  <span data-ttu-id="49dc2-144">[デバッガーの**種類] で\*\*\*\*、[JavaScript (WebView2) ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="49dc2-144">Under the **Debugger Type**, choose **JavaScript (WebView2)**.</span></span>  
        
        :::image type="complex" source="./media/enb-js.png" alt-text="Visual Studioデバッグ構成プロパティ" lightbox="./media/enb-js.png":::
           <span data-ttu-id="49dc2-146">Visual Studio **デバッグ構成** プロパティ</span><span class="sxs-lookup"><span data-stu-id="49dc2-146">Visual Studio **Debugging** Configuration Property</span></span>  
        :::image-end:::  
        
<span data-ttu-id="49dc2-147">WebView2 アプリをデバッグするには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-147">Complete the following actions to debug your WebView2 app.</span></span>  

1.  <span data-ttu-id="49dc2-148">ソース コードでブレークポイントを設定するには、行番号の左側にマウス ポインターを置き、ブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-148">To set a breakpoint in your source code, hover to the left of the line number, and choose to set a breakpoint.</span></span>  <span data-ttu-id="49dc2-149">JS/TS デバッグ アダプターは、ソース パスマッピングを実行しない。</span><span class="sxs-lookup"><span data-stu-id="49dc2-149">The JS/TS debug adapter does not perform source path mapping.</span></span>  <span data-ttu-id="49dc2-150">WebView2 に関連付けられたまったく同じパスを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="49dc2-150">You must open the exact same path associated with your WebView2.</span></span>  
    
    :::image type="complex" source="./media/breakpoint.png" alt-text="Visual Studioブレークポイントの追加" lightbox="./media/breakpoint.png"::: 
       <span data-ttu-id="49dc2-152">Visual Studioブレークポイントの追加</span><span class="sxs-lookup"><span data-stu-id="49dc2-152">Visual Studio add breakpoint</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="49dc2-153">デバッガーを実行するには、プラットフォームのビット サイズを選択し、[ローカル Windows デバッガー] の横にある緑色の再生ボタン **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="49dc2-153">To run the debugger, choose the bit size of the platform, and then choose the green play button next to **Local Windows Debugger**.</span></span>  <span data-ttu-id="49dc2-154">アプリが実行され、デバッガーは作成された最初の WebView2 プロセスに接続します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-154">The app runs and the debugger connects to the first WebView2 process that is created.</span></span>  
    
    :::image type="complex" source="./media/run.png" alt-text=" Visual Studio Windows デバッガー" lightbox="./media/run.png"::: 
       <span data-ttu-id="49dc2-156">Visual Studio Windows **デバッガー**</span><span class="sxs-lookup"><span data-stu-id="49dc2-156">Visual Studio **Local Windows Debugger**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="49dc2-157">デバッグ コンソール **で、** デバッガーからの出力を見つける。</span><span class="sxs-lookup"><span data-stu-id="49dc2-157">In the **Debug Console**, find the output from the debugger.</span></span>  
    
    :::image type="complex" source="./media/console.png" alt-text=" Visual Studio デバッグ コンソール" lightbox="./media/console.png"::: 
       <span data-ttu-id="49dc2-159">Visual Studio デバッグ **コンソール**</span><span class="sxs-lookup"><span data-stu-id="49dc2-159">Visual Studio **Debug Console**</span></span>  
    :::image-end:::  
    
## [<a name="visual-studio-code"></a><span data-ttu-id="49dc2-160">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="49dc2-160">Visual Studio Code</span></span>](#tab/visualstudiocode)  

<span data-ttu-id="49dc2-161">Microsoft Visual Studioコードを使用して、WebView2 コントロールで実行されるスクリプトをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="49dc2-161">Use Microsoft Visual Studio Code to debug scripts that run in WebView2 controls.</span></span>  <!--Ensure that you're using Visual Studio Code version [insert build here] or later.  -->  

<span data-ttu-id="49dc2-162">[Visual Studioコード] で、次のアクションを実行してコードをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="49dc2-162">In Visual Studio Code, complete the following actions to debug your code.</span></span> 

1.  <span data-ttu-id="49dc2-163">プロジェクトにファイルが必要 `launch.json` です。</span><span class="sxs-lookup"><span data-stu-id="49dc2-163">Your project is required to have a `launch.json` file.</span></span>  <span data-ttu-id="49dc2-164">プロジェクトにファイルが含されていない場合は、次のコード スニペットを `launch.json` コピーし、新しいファイルを作成 `launch.json` します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-164">If your project doesn't have a `launch.json` file, copy the following code snippet and create a new `launch.json` file.</span></span>  
    
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
    > <span data-ttu-id="49dc2-165">Visual Studioコード ソース パスマッピングには URL が必要になります。そのため、アプリの起動時にコマンド ライン パラメーターが受信されます。</span><span class="sxs-lookup"><span data-stu-id="49dc2-165">Visual Studio Code source path mapping now requires the URL, so your app now receives a command-line parameter when it starts.</span></span>  <span data-ttu-id="49dc2-166">必要に応じて、パラメーター `url` を無視しても問題ない場合があります。</span><span class="sxs-lookup"><span data-stu-id="49dc2-166">You may safely ignore the `url` parameter if needed.</span></span>  
    
1.  <span data-ttu-id="49dc2-167">ソース コードでブレークポイントを設定するには、行にカーソルを合わせると、</span><span class="sxs-lookup"><span data-stu-id="49dc2-167">To set a breakpoint in your source code, hover on the line, and select</span></span> `F9`
    
    :::image type="complex" source="./media/breakpoint-vs.png" alt-text="ブレークポイントはコードでVisual Studioされます" lightbox="./media/breakpoint-vs.png":::
       <span data-ttu-id="49dc2-169">ブレークポイントはコードでVisual Studioされます</span><span class="sxs-lookup"><span data-stu-id="49dc2-169">Breakpoint is set in Visual Studio Code</span></span>  
    :::image-end:::
    
1.  <span data-ttu-id="49dc2-170">コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-170">Run the code.</span></span>  
    1.  <span data-ttu-id="49dc2-171">[実行 **] タブ** で、ドロップダウン メニューから起動構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-171">On the **Run** tab, choose the launch configuration from the dropdown menu.</span></span>  
    1.  <span data-ttu-id="49dc2-172">アプリのデバッグを開始するには、[デバッグの開始] を選択します。これは、起動構成ドロップダウンの横にある緑色の三角形です。</span><span class="sxs-lookup"><span data-stu-id="49dc2-172">To start debugging your app, choose Start Debugging, which is the green triangle next to the launch configuration drop down.</span></span>  
        
        :::image type="complex" source="./media/run-vs.png" alt-text=" Visual Studio [コードの実行] タブ" lightbox="./media/run-vs.png":::
           <span data-ttu-id="49dc2-174">Visual Studio [コードの実行] タブ</span><span class="sxs-lookup"><span data-stu-id="49dc2-174">Visual Studio Code Run tab</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="49dc2-175">デバッグ **出力とエラー** を表示するには、[デバッグ コンソール] を開きます。</span><span class="sxs-lookup"><span data-stu-id="49dc2-175">Open **Debug Console** to view the debug output and errors.</span></span>  
    
    :::image type="complex" source="./media/results-vs.png" alt-text=" Visual Studio コード デバッグ コンソール" lightbox="./media/results-vs.png":::
       <span data-ttu-id="49dc2-177">Visual Studio コード デバッグ コンソール</span><span class="sxs-lookup"><span data-stu-id="49dc2-177">Visual Studio Code Debug Console</span></span>  
    :::image-end:::  
    
<span data-ttu-id="49dc2-178">**詳細設定**:</span><span class="sxs-lookup"><span data-stu-id="49dc2-178">**Advanced Settings**:</span></span>  

*   <span data-ttu-id="49dc2-179">ターゲット Webview のデバッグ。</span><span class="sxs-lookup"><span data-stu-id="49dc2-179">Targeted Webview debugging.</span></span> 
    
    <span data-ttu-id="49dc2-180">一部の WebView2 アプリでは、複数の WebView2 コントロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="49dc2-180">In some WebView2 apps, you may use more than one WebView2 control.</span></span> <span data-ttu-id="49dc2-181">この状況でデバッグする WebView2 コントロールを選択するには、ターゲット Webview2 デバッグを使用できます。</span><span class="sxs-lookup"><span data-stu-id="49dc2-181">To pick the WebView2 control to debug in this situation you can use targeted webview2 debugging</span></span> 
    
    <span data-ttu-id="49dc2-182">ターゲット `launch.json` Webview デバッグを使用するには、次のアクションを開いて完了します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-182">Open `launch.json` and complete the following actions to use targeted Webview debugging.</span></span>  
    
    1.  <span data-ttu-id="49dc2-183">パラメーターが `useWebview` に設定されているを確認します `true` 。</span><span class="sxs-lookup"><span data-stu-id="49dc2-183">Confirm that the `useWebview` parameter is set to `true`.</span></span>  
    1.  <span data-ttu-id="49dc2-184">パラメーターを追加 `urlFilter` します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-184">Add the `urlFilter` parameter.</span></span>  <span data-ttu-id="49dc2-185">WebView2 コントロールが URL に移動すると、URL に表示される文字列を比較するためにパラメーター値 `urlFilter` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="49dc2-185">When the WebView2 control navigates to a URL, the `urlFilter` parameter value is used to compare strings that appear in the URL.</span></span>  
        
    ```json
    "useWebview": "true",
    "urlFilter": "*index.ts",
    
    // Other urlFilter options.
    
    urlFilter="*index.ts"    // Match any url that ends with index.ts, and ignore all leading characters. 
    urlFilter="*index*"      // Match any url that contains the string index anywhere in the URL.  
    urlFilter="file://C:/path/to/my/index.ts," // To match explicit file called index.ts.  
    ```  
    
    <span data-ttu-id="49dc2-186">アプリをデバッグするときに、レンダリング プロセスの最初からコードをステップ実行する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="49dc2-186">When debugging your app, you may need to step through the code from the beginning of the rendering process.</span></span> <span data-ttu-id="49dc2-187">サイトで Web ページをレンダリングし、ソース コードにアクセスできない場合は、認識されていないパラメーターは Web ページで無視されますので、このオプション `?=value`  を使用できます。</span><span class="sxs-lookup"><span data-stu-id="49dc2-187">If you are rendering webpages on sites and you don't have access to the source code, you can use the `?=value` option, because webpages ignore unrecognized parameters.</span></span>   
    
    > [!IMPORTANT]
    > <span data-ttu-id="49dc2-188">URL で最初の一致が見つかったら、デバッガーは停止します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-188">After the first match is found in the URL, the debugger stops.</span></span>  <span data-ttu-id="49dc2-189">CDP ポートは、すべての WebView2 コントロールで共有され、1 つのポート番号を使用するので、2 つの WebView2 コントロールを同時にデバッグすることはできません。</span><span class="sxs-lookup"><span data-stu-id="49dc2-189">You cannot debug two WebView2 controls at the same time because the CDP port is shared by all WebView2 controls, and uses a single port number.</span></span>  
    
*   <span data-ttu-id="49dc2-190">実行中のプロセスのデバッグ</span><span class="sxs-lookup"><span data-stu-id="49dc2-190">Debug running processes</span></span>  
    
    <span data-ttu-id="49dc2-191">実行中の WebView2 プロセスにデバッガーを接続する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="49dc2-191">You may need to attach the debugger to running WebView2 processes.</span></span> <span data-ttu-id="49dc2-192">これを行うには、 `launch.json` にパラメーターを `request` 更新します `attach` 。</span><span class="sxs-lookup"><span data-stu-id="49dc2-192">To do that, in `launch.json`, update the `request` parameter to `attach`.</span></span>
    
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
    
    <span data-ttu-id="49dc2-193">WebView2 コントロールは、WebView2 コントロールのデバッグを許可するために CDP ポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="49dc2-193">Your WebView2 control must open the CDP port to allow debugging of the WebView2 control.</span></span>  <span data-ttu-id="49dc2-194">デバッガーを開始する前に、1 つの WebView2 コントロールだけが Chrome Developer Protocol (CDP) ポートを開いているか確認するために、コードをビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="49dc2-194">Your code must be built to ensure that only one WebView2 control has a Chrome Developer Protocol (CDP) port open, before starting the debugger.</span></span>  
    
*   <span data-ttu-id="49dc2-195">デバッグ トレース オプション</span><span class="sxs-lookup"><span data-stu-id="49dc2-195">Debug tracing options</span></span>  
    
    <span data-ttu-id="49dc2-196">デバッグ トレース `trace` を有効にするには、launch.jsにパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-196">Add the `trace` parameter to launch.json to enable debug tracing.</span></span>  
    
    1.  <span data-ttu-id="49dc2-197">パラメーターを `trace` 追加します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-197">Add `trace` parameter.</span></span>  
        
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
              
              :::image type="complex" source="./media/trace-log.png" alt-text=" デバッグ出力をログ ファイルに保存します。" lightbox="./media/trace-log.png":::
                 <span data-ttu-id="49dc2-199">デバッグ出力をログ ファイルに保存する</span><span class="sxs-lookup"><span data-stu-id="49dc2-199">Save debug output to a log file</span></span>  
              :::image-end:::  
           :::column-end:::
           :::column span="":::
              ```json
              ,"trace": "verbose"  // Turn on verbose tracing in the Debug Output pane.
              ```  
              
              :::image type="complex" source="./media/verbose.png" alt-text=" 詳細出力" lightbox="./media/verbose.png":::
                 <span data-ttu-id="49dc2-201">Visual Studioトレースを有効にしたコード デバッグ出力</span><span class="sxs-lookup"><span data-stu-id="49dc2-201">Visual Studio Code Debug Output with verbose tracing turned on</span></span>  
              :::image-end:::  
           :::column-end:::
        :::row-end:::  
        
*   <span data-ttu-id="49dc2-202">アドインOfficeデバッグします。</span><span class="sxs-lookup"><span data-stu-id="49dc2-202">Debug Office Add-ins.</span></span>  
    
    <span data-ttu-id="49dc2-203">アドインをデバッグする場合Officeコードの別のインスタンスでアドイン ソース コードをVisual Studioします。</span><span class="sxs-lookup"><span data-stu-id="49dc2-203">If you're debugging Office Add-ins, open the add-in source code in a separate instance of Visual Studio Code.</span></span>  <span data-ttu-id="49dc2-204">WebView2 launch.jsでアプリを開き、次のコード スニペットを追加して、デバッガーをアドインにOfficeします。</span><span class="sxs-lookup"><span data-stu-id="49dc2-204">Open launch.json in your WebView2 app and add the following code snippet to attach the debugger to the Office add-in.</span></span>
    
    ```json
    ,"debugServer": 4711
    ```  
    
*   <span data-ttu-id="49dc2-205">デバッガーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="49dc2-205">Troubleshooting the debugger</span></span>  
    
    <span data-ttu-id="49dc2-206">デバッガーを使用すると、次のシナリオが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="49dc2-206">You may encounter the following scenarios when using the debugger.</span></span>  
    
    *   <span data-ttu-id="49dc2-207">デバッガーはブレークポイントで停止しないし、デバッグ出力があります。</span><span class="sxs-lookup"><span data-stu-id="49dc2-207">The debugger doesn't stop at the breakpoint, and you have debug output.</span></span>  <span data-ttu-id="49dc2-208">この問題を解決するには、ブレークポイントを持つファイルが WebView2 コントロールで使用されるファイルと同じことを確認します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-208">To solve the issue, confirm that the file with the breakpoint is the same file that's used by the WebView2 control.</span></span>  <span data-ttu-id="49dc2-209">デバッガーはソース パスマッピングを実行しない。</span><span class="sxs-lookup"><span data-stu-id="49dc2-209">The debugger doesn't perform source path mapping.</span></span>  
    *   <span data-ttu-id="49dc2-210">実行中のプロセスに接続できないので、タイムアウト エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-210">You can't attach to a running process, and you get a timeout error.</span></span>  <span data-ttu-id="49dc2-211">この問題を解決するには、WebView2 コントロールが CDP ポートを開いているか確認します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-211">To solve the issue, confirm that the WebView2 control opened the CDP port.</span></span>  <span data-ttu-id="49dc2-212">レジストリ内  `additionalBrowserArguments`  の値が正しいか、オプションが正しいか確認します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-212">Ensure your `additionalBrowserArguments` value in the registry is correct, or the options are correct.</span></span>  <span data-ttu-id="49dc2-213">詳細については [、「additionalBrowserArguments for dotnet」][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments] および [「additionalBrowserArguments for Win32」に移動します][Webview2ReferenceWin32Webview2IdlParameters]。</span><span class="sxs-lookup"><span data-stu-id="49dc2-213">For more information, navigate to [additionalBrowserArguments for dotnet][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments] and [additionalBrowserArguments for Win32][Webview2ReferenceWin32Webview2IdlParameters].</span></span>  
        
* * *  

## <a name="see-also"></a><span data-ttu-id="49dc2-214">関連項目</span><span class="sxs-lookup"><span data-stu-id="49dc2-214">See also</span></span>  

*   <span data-ttu-id="49dc2-215">WebView2 の使用を開始するには [、[WebView2 スタートガイド] に移動します][Webview2MainGetStarted]。</span><span class="sxs-lookup"><span data-stu-id="49dc2-215">To get started using WebView2, navigate to [WebView2 Get Started Guides][Webview2MainGetStarted].</span></span>  
*   <span data-ttu-id="49dc2-216">WebView2 機能の包括的な例については [、GitHub の WebView2Samples][GithubMicrosoftedgeWebview2samples] リポジトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="49dc2-216">For a comprehensive example of WebView2 capabilities, navigate to the [WebView2Samples][GithubMicrosoftedgeWebview2samples] repo on GitHub.</span></span>
*   <span data-ttu-id="49dc2-217">WebView2 API の詳細については、「API リファレンス」 [に移動します][Webview2ApiReference]。</span><span class="sxs-lookup"><span data-stu-id="49dc2-217">For more detailed information about WebView2 APIs, navigate to [API reference][Webview2ApiReference].</span></span>
*   <span data-ttu-id="49dc2-218">WebView2 の詳細については [、「WebView2 Resources」に移動します][Webview2MainNextSteps]。</span><span class="sxs-lookup"><span data-stu-id="49dc2-218">For more information about WebView2, navigate to [WebView2 Resources][Webview2MainNextSteps].</span></span>
    
## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a><span data-ttu-id="49dc2-219">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="49dc2-219">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments]: /dotnet/api/microsoft.web.webview2.core.corewebview2environmentoptions.additionalbrowserarguments "CoreWebView2EnvironmentOptions.AdditionalBrowserArguments プロパティ (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[Webview2ReferenceWin32Webview2IdlParameters]: /microsoft-edge/webview2/reference/win32/webview2-idl#createcorewebview2environmentwithoptions  "CreateCoreWebView2Environment - Globals |Microsoft Docs"  
[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API リファレンス |Microsoft Docs"  
[Webview2MainNextSteps]: ../index.md#next-steps "次の手順 - Microsoft Edge WebView2 (プレビュー) の概要|Microsoft Docs"  
[Webview2MainGetStarted]: ../index.md#get-started "はじめに - Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  
