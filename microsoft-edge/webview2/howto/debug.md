---
description: WebView2 コントロールをデバッグする方法について説明します。
title: WebView2 アプリケーションのデバッグを開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/21/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 78c0fb982de8ccce71a8df2b59447b55f64fdc2f
ms.sourcegitcommit: 24151cc65bad92d751a8e7a868c102e1121456e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "11052154"
---
# <span data-ttu-id="fac50-104">WebView2 アプリケーションのデバッグを開始する</span><span class="sxs-lookup"><span data-stu-id="fac50-104">Get started debugging WebView2 applications</span></span>  

<span data-ttu-id="fac50-105">Microsoft Edge WebView2 コントロールの目標は、web とネイティブアプリケーションの両方の開発機能とツールの両方を組み合わせることです。</span><span class="sxs-lookup"><span data-stu-id="fac50-105">The goal of the Microsoft Edge WebView2 control is to combine the best of both the web and native application development features and tools.</span></span>  <span data-ttu-id="fac50-106">WebView2 アプリケーションを開発するときは、アプリケーションをデバッグする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fac50-106">When you develop your WebView2 application, you should debug your application.</span></span>  <span data-ttu-id="fac50-107">この記事では、WebView2 アプリケーションで web とネイティブコードの両方をデバッグするために使用するさまざまなツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fac50-107">This article outlines the different tools to use to debug both your web and native code in your WebView2 application.</span></span>  

## [<span data-ttu-id="fac50-108">Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="fac50-108">Microsoft Edge DevTools</span></span>](#tab/devtools)  

<span data-ttu-id="fac50-109">Microsoft edge [(Chromium) 開発者ツール][DevtoolsGuideChromiumMain] を使用して、microsoft edge に表示されている別の web ページをデバッグする場合と同じ方法で、WebView2 コントロールに表示される web コンテンツをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="fac50-109">Use [Microsoft Edge (Chromium) Developer Tools][DevtoolsGuideChromiumMain] to debug web content displayed in WebView2 controls, in the same way that you may debug for another webpage displayed in Microsoft Edge.</span></span>  <span data-ttu-id="fac50-110">DevTools を開くには、WebView コントロールにフォーカスを設定し、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="fac50-110">To open the DevTools, set focus on the WebView control and then use one of the following actions.</span></span>  

*   <span data-ttu-id="fac50-111">を選択し `F12` ます。</span><span class="sxs-lookup"><span data-stu-id="fac50-111">Select `F12`.</span></span>  
*   <span data-ttu-id="fac50-112">を選択し `Ctrl` + `Shift` + `I` ます。</span><span class="sxs-lookup"><span data-stu-id="fac50-112">Select `Ctrl`+`Shift`+`I`.</span></span>  
*   <span data-ttu-id="fac50-113">コンテキストメニューを開き (\ を右クリックし)、[] を選び `Inspect` ます。</span><span class="sxs-lookup"><span data-stu-id="fac50-113">Open the context menu \(right-click\) and choose `Inspect`.</span></span>  

<span data-ttu-id="fac50-114">詳細については、「 [Devtools の概要][DevtoolsGuideChromiumMain]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fac50-114">For more information, see [DevTools overview][DevtoolsGuideChromiumMain].</span></span>  

:::image type="complex" source="./media/f12.png" alt-text="DevTools のデバッグ" lightbox="./media/f12.png":::
   <span data-ttu-id="fac50-116">DevTools のデバッグ</span><span class="sxs-lookup"><span data-stu-id="fac50-116">DevTools debugging</span></span>  
:::image-end:::  

## [<span data-ttu-id="fac50-117">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fac50-117">Visual Studio</span></span>](#tab/visualstudio)  

<span data-ttu-id="fac50-118">Visual Studio には、WebView2 アプリケーションの web とネイティブコード向けのさまざまなデバッグツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="fac50-118">Visual Studio provides various debugging tools for web and native code in WebView2 applications.</span></span>  <span data-ttu-id="fac50-119">Visual Studio セクションでは、主にフォーカスが WebView コントロールのデバッグを行っていますが、Visual Studio でのデバッグ方法は通常どおり利用できます。</span><span class="sxs-lookup"><span data-stu-id="fac50-119">In the Visual Studio section, the primary focus is debugging WebView controls, however the other methods of debugging in Visual Studio are available as usual.</span></span>  <span data-ttu-id="fac50-120">Win32 アプリケーションまたは Office アドインでのみ、web とネイティブコードをデバッグするには、次のプロセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="fac50-120">Use the following process to debug web and native code in Win32 applications or Office Add-ins only.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="fac50-121">ネイティブデバッガーがアタッチされている Visual Studio でアプリケーションをデバッグする場合、を選択すると、 `F12` 開発者ツールではなくネイティブデバッガーがトリガーされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fac50-121">When you debug your application in Visual Studio with the native debugger attached, selecting `F12` may trigger the native debugger instead of Developer Tools.</span></span>  <span data-ttu-id="fac50-122">`Ctrl` + `Shift` + `I` または、コンテキストメニュー \ (右クリック \) を使用して、この状況を回避します。</span><span class="sxs-lookup"><span data-stu-id="fac50-122">Select `Ctrl`+`Shift`+`I`, or use the context menu \(right-click\) to avoid the situation.</span></span>  

<span data-ttu-id="fac50-123">作業を始める前に、次の要件が満たされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fac50-123">Before you begin, ensure the following requirements are met.</span></span>  

*   <span data-ttu-id="fac50-124">スクリプトをデバッグするには、Visual Studio 内からアプリを起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fac50-124">To debug scripts, the app must be launched from within Visual Studio.</span></span>  
*   <span data-ttu-id="fac50-125">実行中の WebView2 プロセスにデバッガーをアタッチすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fac50-125">You cannot attach a debugger to a running WebView2 process.</span></span>  
*   <span data-ttu-id="fac50-126">Visual Studio 2019 バージョン 16.4 Preview 2 以降をインストールします。</span><span class="sxs-lookup"><span data-stu-id="fac50-126">Install Visual Studio 2019 version 16.4 Preview 2 or later.</span></span>  

<span data-ttu-id="fac50-127">Visual Studio でスクリプトデバッガーツールをインストールしてセットアップします。</span><span class="sxs-lookup"><span data-stu-id="fac50-127">Install and set up the script debugger tools in Visual Studio.</span></span>  

1.  <span data-ttu-id="fac50-128">**C++ でデスクトップ開発**に**JavaScript 診断**コンポーネントをインストールするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="fac50-128">Complete the following actions to install the **JavaScript diagnostics** component in **Desktop development with C++**.</span></span>  

    1. <span data-ttu-id="fac50-129">Windows エクスプローラーバーに「」と入力 `Visual Studio Installer` します。</span><span class="sxs-lookup"><span data-stu-id="fac50-129">In the Windows Explorer bar, type `Visual Studio Installer`.</span></span>  
    1. <span data-ttu-id="fac50-130">[ **Visual Studio インストーラー** ] を選択して開きます。</span><span class="sxs-lookup"><span data-stu-id="fac50-130">Choose **Visual Studio Installer** to open it.</span></span>  
    1. <span data-ttu-id="fac50-131">Visual Studio インストーラーのインストールされているバージョンで、[ **その他** ] ボタンを選択し、[ **変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fac50-131">In the Visual Studio Installer, on the installed version, choose the **More** button, and then choose **Modify**.</span></span>  
    1. <span data-ttu-id="fac50-132">Visual Studio の [ **ワークロード**] で、[ **デスクトップ開発** ] の [C++] の設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="fac50-132">In Visual Studio, under **Workloads**, choose the **Desktop Development in C++** setting.</span></span>  
        
        :::image type="complex" source="./media/workloads.png" alt-text="Visual Studio のワークロードの変更画面" lightbox="./media/workloads.png":::
            <span data-ttu-id="fac50-134">Visual Studio のワークロードの変更画面</span><span class="sxs-lookup"><span data-stu-id="fac50-134">Visual Studio Modifying Workloads Screen</span></span> :::image-end:::  
        
    1.  <span data-ttu-id="fac50-135">**個々のコンポーネント**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fac50-135">Choose **Individual components**.</span></span>  
    1.  <span data-ttu-id="fac50-136">検索ボックスに「」と入力し `JavaScript diagnostics` ます。</span><span class="sxs-lookup"><span data-stu-id="fac50-136">In the search box, enter `JavaScript diagnostics`.</span></span>  
    1.  <span data-ttu-id="fac50-137">**JavaScript 診断**設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="fac50-137">Choose the **JavaScript diagnostics** setting.</span></span>  
    1.  <span data-ttu-id="fac50-138">[ **Modify**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fac50-138">Choose **Modify**.</span></span> 
        
        :::image type="complex" source="./media/indivcomp.png" alt-text="Visual Studio による個々のコンポーネントの変更のタブ" lightbox="./media/indivcomp.png":::
           <span data-ttu-id="fac50-140">Visual Studio による個々のコンポーネントの変更のタブ</span><span class="sxs-lookup"><span data-stu-id="fac50-140">Visual Studio Modifying Individual Components Tab</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="fac50-141">WebView2 アプリケーションのスクリプトのデバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fac50-141">Enable script debugging for WebView2 applications.</span></span>  
    1.  <span data-ttu-id="fac50-142">WebView2 プロジェクトで、コンテキストメニュー \ を右クリックし、[ **プロパティ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fac50-142">In your WebView2 project, open the context menu \(right-click\), and choose **Properties**.</span></span>  
    1.  <span data-ttu-id="fac50-143">[ **構成プロパティ**] で、[ **デバッグ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fac50-143">Under the **Configuration Properties**, choose **Debugging**.</span></span>  
    1.  <span data-ttu-id="fac50-144">[ **デバッガーの種類**] で、[ **JavaScript (WebView2)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fac50-144">Under the **Debugger Type**, choose **JavaScript (WebView2)**.</span></span>  
        
        :::image type="complex" source="./media/enbjs.png" alt-text="Visual Studio のデバッグ構成プロパティ" lightbox="./media/enbjs.png":::
           <span data-ttu-id="fac50-146">Visual Studio の **デバッグ** 構成プロパティ</span><span class="sxs-lookup"><span data-stu-id="fac50-146">Visual Studio **Debugging** Configuration Property</span></span>  
        :::image-end:::  
        
<span data-ttu-id="fac50-147">WebView2 アプリケーションをデバッグするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="fac50-147">Complete the following actions to debug your WebView2 application.</span></span>  

1.  <span data-ttu-id="fac50-148">ソースコードにブレークポイントを設定するには、行番号の左側にカーソルを置いて、[ブレークポイントの設定] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fac50-148">To set a breakpoint in your source code, hover to the left of the line number, and choose to set a breakpoint.</span></span>  <span data-ttu-id="fac50-149">JS/TS デバッグアダプターはソースパスマッピングを実行しません。</span><span class="sxs-lookup"><span data-stu-id="fac50-149">The JS/TS debug adapter does not perform source path mapping.</span></span>  <span data-ttu-id="fac50-150">WebView2 に関連付けられているのとまったく同じパスを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="fac50-150">You must open the exact same path associated with your WebView2.</span></span>  
    
    :::image type="complex" source="./media/breakpoint.png" alt-text="Visual Studio のブレークポイントの追加" lightbox="./media/breakpoint.png"::: 
       <span data-ttu-id="fac50-152">Visual Studio のブレークポイントの追加</span><span class="sxs-lookup"><span data-stu-id="fac50-152">Visual Studio add breakpoint</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="fac50-153">デバッガーを実行するには、プラットフォームのビットサイズを選択し、[ **ローカル Windows デバッガー**] の横にある緑色の [再生] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="fac50-153">To run the debugger, choose the bit size of the platform, and then choose the green play button next to **Local Windows Debugger**.</span></span>  <span data-ttu-id="fac50-154">アプリケーションが実行され、作成された最初の WebView2 プロセスにデバッガーが接続されます。</span><span class="sxs-lookup"><span data-stu-id="fac50-154">The application runs and the debugger connects to the first WebView2 process that is created.</span></span>  
    
    :::image type="complex" source="./media/run.png" alt-text=" Visual Studio のローカル Windows デバッガー" lightbox="./media/run.png"::: 
       <span data-ttu-id="fac50-156">Visual Studio の **ローカル Windows デバッガー**</span><span class="sxs-lookup"><span data-stu-id="fac50-156">Visual Studio **Local Windows Debugger**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="fac50-157">**デバッグコンソール**でデバッガーからの出力を見つけます。</span><span class="sxs-lookup"><span data-stu-id="fac50-157">In the **Debug Console**, find the output from the debugger.</span></span>  
    
    :::image type="complex" source="./media/console.png" alt-text=" Visual Studio のデバッグコンソール" lightbox="./media/console.png"::: 
       <span data-ttu-id="fac50-159">Visual Studio の **デバッグコンソール**</span><span class="sxs-lookup"><span data-stu-id="fac50-159">Visual Studio **Debug Console**</span></span>  
    :::image-end:::  
    
## [<span data-ttu-id="fac50-160">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="fac50-160">Visual Studio Code</span></span>](#tab/visualstudiocode)  

<span data-ttu-id="fac50-161">Microsoft Visual Studio コードを使って、WebView2 コントロールで実行されるスクリプトをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="fac50-161">Use Microsoft Visual Studio Code to debug scripts that run in WebView2 controls.</span></span>  <!--Ensure that you're using Visual Studio Code version [insert build here] or later.  -->  

<span data-ttu-id="fac50-162">Visual Studio コードで、次の操作を実行してコードをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="fac50-162">In Visual Studio Code, complete the following actions to debug your code.</span></span> 

1.  <span data-ttu-id="fac50-163">プロジェクトにファイルが必要です `launch.json` 。</span><span class="sxs-lookup"><span data-stu-id="fac50-163">Your project is required to have a `launch.json` file.</span></span>  <span data-ttu-id="fac50-164">プロジェクトにファイルが含まれていない場合は `launch.json` 、次のコードスニペットをコピーして、新しいファイルを作成し `launch.json` ます。</span><span class="sxs-lookup"><span data-stu-id="fac50-164">If your project doesn't have a `launch.json` file, copy the following code snippet and create a new `launch.json` file.</span></span>  
        
    ```json
        "name": "Hello debug world",
        "type": "pwa-msedge",
        "port": 9222, // The port value is optional, and the default value is 9222.
        "request": "launch",
        "runtimeExecutable": "C:/path/to/your/webview2/application.exe",
        "env": {
            // Customize for your application location if needed
            "Path": "%path%;e:/path/to/your/application/location; "
        },
        "useWebView": true,
    ```  
        
1.  <span data-ttu-id="fac50-165">ソースコードにブレークポイントを設定するには、その行にカーソルを合わせて、</span><span class="sxs-lookup"><span data-stu-id="fac50-165">To set a breakpoint in your source code, hover on the line, and select</span></span> `F9`
    
    :::image type="complex" source="./media/breakpointvs.png" alt-text="Visual Studio コードでブレークポイントが設定されている" lightbox="./media/breakpointvs.png":::
       <span data-ttu-id="fac50-167">Visual Studio コードでブレークポイントが設定されている</span><span class="sxs-lookup"><span data-stu-id="fac50-167">Breakpoint is set in Visual Studio Code</span></span>  
    :::image-end:::
    
    > [!NOTE]
    > <span data-ttu-id="fac50-168">Visual Studio コードではソースマッピングが実行されないため、WebView2 で使用するのと同じファイルにブレークポイントを設定してください。</span><span class="sxs-lookup"><span data-stu-id="fac50-168">Because Visual Studio Code does not perform source mapping, ensure you set breakpoints in the same file that WebView2 uses.</span></span>  <span data-ttu-id="fac50-169">パスが一致しない場合、Visual Studio コードはブレークポイントで実行中のコードを一時停止しません。</span><span class="sxs-lookup"><span data-stu-id="fac50-169">If the paths do not match, Visual Studio Code does not pause the running code at the breakpoint.</span></span>  
    
1.  <span data-ttu-id="fac50-170">コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="fac50-170">Run the code.</span></span>  
    1.  <span data-ttu-id="fac50-171">[ **実行** ] タブで、ドロップダウンメニューから [起動構成] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fac50-171">On the **Run** tab, choose the launch configuration from the dropdown menu.</span></span>  
    1.  <span data-ttu-id="fac50-172">アプリケーションのデバッグを開始するには、[デバッグの開始] を選びます。これは、[起動構成] ドロップダウンの隣にある緑色の三角形です。</span><span class="sxs-lookup"><span data-stu-id="fac50-172">To start debugging your application, choose Start Debugging, which is the green triangle next to the launch configuration drop down.</span></span>  
        
        :::image type="complex" source="./media/runvs.png" alt-text=" Visual Studio コードの [実行] タブ" lightbox="./media/runvs.png":::
           <span data-ttu-id="fac50-174">Visual Studio コードの [実行] タブ</span><span class="sxs-lookup"><span data-stu-id="fac50-174">Visual Studio Code Run tab</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="fac50-175">デバッグ **コンソール** を開いて、デバッグ出力とエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="fac50-175">Open **Debug Console** to view the debug output and errors.</span></span>  
    
    :::image type="complex" source="./media/resultsvs.png" alt-text=" Visual Studio コードデバッグコンソール" lightbox="./media/resultsvs.png":::
       <span data-ttu-id="fac50-177">Visual Studio コードデバッグコンソール</span><span class="sxs-lookup"><span data-stu-id="fac50-177">Visual Studio Code Debug Console</span></span>  
    :::image-end:::  
    
<span data-ttu-id="fac50-178">**詳細設定**:</span><span class="sxs-lookup"><span data-stu-id="fac50-178">**Advanced Settings**:</span></span>  

*   <span data-ttu-id="fac50-179">ターゲット Webview のデバッグ。</span><span class="sxs-lookup"><span data-stu-id="fac50-179">Targeted Webview debugging.</span></span> 

    <span data-ttu-id="fac50-180">一部の WebView2 アプリケーションでは、複数の WebView2 コントロールを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="fac50-180">In some WebView2 applications, you may use more than one WebView2 control.</span></span> <span data-ttu-id="fac50-181">この状況でデバッグする WebView2 コントロールを選ぶには、ターゲット指定された WebView2 デバッグを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fac50-181">To pick the WebView2 control to debug in this situation you can use targeted webview2 debugging</span></span> 
    
    <span data-ttu-id="fac50-182">`launch.json`ターゲット Webview のデバッグを使用するには、次の操作を開いて実行します。</span><span class="sxs-lookup"><span data-stu-id="fac50-182">Open `launch.json` and complete the following actions to use targeted Webview debugging.</span></span>  
    
    1.  <span data-ttu-id="fac50-183">パラメーターがに設定されていることを確認 `useWebview` `true` します。</span><span class="sxs-lookup"><span data-stu-id="fac50-183">Confirm that the `useWebview` parameter is set to `true`.</span></span>  
    1.  <span data-ttu-id="fac50-184">パラメーターを追加 `urlFilter` します。</span><span class="sxs-lookup"><span data-stu-id="fac50-184">Add the `urlFilter` parameter.</span></span>  <span data-ttu-id="fac50-185">WebView2 コントロールが URL に移動すると、 `urlFilter` パラメーター値が使用され、url に表示される文字列が比較されます。</span><span class="sxs-lookup"><span data-stu-id="fac50-185">When the WebView2 control navigates to a URL, the `urlFilter` parameter value is used to compare strings that appear in the URL.</span></span>  
    
    ```json
    "useWebview": "true",
    "urlFilter": "*index.ts",
    
    // Other urlFilter options.
    
    urlFilter="*index.ts"    // Match any url that ends with index.ts, and ignore all leading characters. 
    urlFilter="*index*"      // Match any url that contains the string index anywhere in the URL.  
    urlFilter="file://C:/path/to/my/index.ts," // To match explicit file called index.ts.  
    ```  
    
    <span data-ttu-id="fac50-186">アプリケーションをデバッグするときに、レンダリング処理の最初からコードをステップ実行しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="fac50-186">When debugging your application, you may need to step through the code from the beginning of the rendering process.</span></span> <span data-ttu-id="fac50-187">Web ページをサイトにレンダリングしていて、ソースコードにアクセスできない場合、web ページでは認識されないパラメーターが無視されるため、このオプションを使うことができ `?=value`  ます。</span><span class="sxs-lookup"><span data-stu-id="fac50-187">If you are rendering webpages on sites and you don't have access to the source code, you can use the `?=value` option, because webpages ignore unrecognized parameters.</span></span>   
    
    > [!IMPORTANT]
    > <span data-ttu-id="fac50-188">URL で最初の一致が見つかった後、デバッガーは停止します。</span><span class="sxs-lookup"><span data-stu-id="fac50-188">After the first match is found in the URL, the debugger stops.</span></span>  <span data-ttu-id="fac50-189">CDP ポートはすべての WebView2 コントロールで共有され、1つのポート番号を使用するため、2つの WebView2 コントロールを同時にデバッグすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fac50-189">You cannot debug two WebView2 controls at the same time because the CDP port is shared by all WebView2 controls, and uses a single port number.</span></span>  
    
*   <span data-ttu-id="fac50-190">実行中のプロセスをデバッグする</span><span class="sxs-lookup"><span data-stu-id="fac50-190">Debug running processes</span></span>  
    
    <span data-ttu-id="fac50-191">WebView2 プロセスを実行するためにデバッガーをアタッチすることが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="fac50-191">You may need to attach the debugger to running WebView2 processes.</span></span> <span data-ttu-id="fac50-192">そのためには、で `launch.json` `request` パラメーターをに更新 `attach` します。</span><span class="sxs-lookup"><span data-stu-id="fac50-192">To do that, in `launch.json`, update the `request` parameter to `attach`.</span></span>
        
    ```json
        "name": "Hello debugging world",
        "type": "pwa-msedge",
        "port": 9222, 
        "request": "attach",
        "runtimeExecutable": "C:/path/to/your/webview2/application.exe",  
        "env": {
            "Path": "%path%;e:/path/to/your/build/location; "  
        },
        "useWebView": true
    ```  
        
    <span data-ttu-id="fac50-193">WebView2 コントロールは、WebView2 コントロールのデバッグを許可するために、CDP ポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="fac50-193">Your WebView2 control must open the CDP port to allow debugging of the WebView2 control.</span></span>  <span data-ttu-id="fac50-194">デバッガーを開始する前に、コードをビルドして、1つの WebView2 コントロールのみに Chrome (Chrome) ポートを開いていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fac50-194">Your code must be built to ensure that only one WebView2 control has a Chrome Developer Protocol (CDP) port open, before starting the debugger.</span></span>  
    
*   <span data-ttu-id="fac50-195">デバッグトレースオプション</span><span class="sxs-lookup"><span data-stu-id="fac50-195">Debug tracing options</span></span>  
    
    <span data-ttu-id="fac50-196">`trace`launch.jsのパラメーターを追加して、デバッグトレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fac50-196">Add the `trace` parameter to launch.json to enable debug tracing.</span></span>  
    
    1.  <span data-ttu-id="fac50-197">`trace`パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="fac50-197">Add `trace` parameter.</span></span>  
        
 
        
        :::row:::
           :::column span="":::
              ```json
                "name": "Hello debugging world",
                "type": "pwa-msedge",
                "port": 9222, 
                "request": "attach",
                "runtimeExecutable": "C:/path/to/your/webview2/application.exe",  
                "env": {
                "Path": "%path%;e:/path/to/your/build/location; "  
                },
                "useWebView": true
                ,"trace": true  // Turn on  debug tracing, and save the output to a log file.
              ```  
              
              :::image type="complex" source="./media/tracelog.png" alt-text=" デバッグ出力をログファイルに保存します。" lightbox="./media/tracelog.png":::
                 <span data-ttu-id="fac50-199">ログファイルへのデバッグ出力の保存</span><span class="sxs-lookup"><span data-stu-id="fac50-199">Save debug output to a log file</span></span>  
              :::image-end:::  
           :::column-end:::
           :::column span="":::
              ```json
              ,"trace": "verbose"  // Turn on verbose tracing in the Debug Output pane.
              ```  
              
              :::image type="complex" source="./media/verbose.png" alt-text=" 詳細な出力" lightbox="./media/verbose.png":::
                 <span data-ttu-id="fac50-201">冗長トレースが有効になっている Visual Studio コードデバッグの出力</span><span class="sxs-lookup"><span data-stu-id="fac50-201">Visual Studio Code Debug Output with verbose tracing turned on</span></span>  
              :::image-end:::  
           :::column-end:::
        :::row-end:::  
        
*   <span data-ttu-id="fac50-202">Office アドインをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="fac50-202">Debug Office Add-ins.</span></span>
    
    <span data-ttu-id="fac50-203">Office アドインをデバッグする場合は、アドインのソースコードを Visual Studio コードの別のインスタンスで開きます。</span><span class="sxs-lookup"><span data-stu-id="fac50-203">If you're debugging Office Add-ins, open the add-in source code in a separate instance of Visual Studio Code.</span></span>  <span data-ttu-id="fac50-204">WebView2 アプリケーションで launch.jsを開き、次のコードスニペットを追加して、デバッガーを Office アドインにアタッチします。</span><span class="sxs-lookup"><span data-stu-id="fac50-204">Open launch.json in your WebView2 application and add the following code snippet to attach the debugger to the Office add-in.</span></span>
    
    ```json
    ,"debugServer": 4711
    ```  
    
*   <span data-ttu-id="fac50-205">デバッガーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="fac50-205">Troubleshooting the debugger</span></span>  
    
    <span data-ttu-id="fac50-206">デバッガーの使用時には、次のシナリオが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fac50-206">You may encounter the following scenarios when using the debugger.</span></span>  

    *   <span data-ttu-id="fac50-207">デバッガーはブレークポイントで停止せず、デバッグ出力があります。</span><span class="sxs-lookup"><span data-stu-id="fac50-207">The debugger doesn't stop at the breakpoint, and you have debug output.</span></span>  <span data-ttu-id="fac50-208">この問題を解決するには、ブレークポイントを設定したファイルが WebView2 コントロールで使用されているファイルと同じであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fac50-208">To solve the issue, confirm that the file with the breakpoint is the same file that's used by the WebView2 control.</span></span>  <span data-ttu-id="fac50-209">デバッガーはソースパスマッピングを実行しません。</span><span class="sxs-lookup"><span data-stu-id="fac50-209">The debugger doesn't perform source path mapping.</span></span>  
    *   <span data-ttu-id="fac50-210">実行中のプロセスにアタッチできないため、タイムアウトエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="fac50-210">You can't attach to a running process, and you get a timeout error.</span></span>  <span data-ttu-id="fac50-211">この問題を解決するには、WebView2 コントロールが CDP ポートを開いていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fac50-211">To solve the issue, confirm that the WebView2 control opened the CDP port.</span></span>  <span data-ttu-id="fac50-212">レジストリの  `additionalBrowserArguments`  値が正しいこと、またはオプションが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="fac50-212">Ensure your `additionalBrowserArguments` value in the registry is correct, or the options are correct.</span></span>  <span data-ttu-id="fac50-213">詳細については、「[.net] [Webview2ReferenceDotnet09515MicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments] と [additionalBrowserArguments for Win32] [Webview2ReferenceWin3209538Webview2IdlParameters]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fac50-213">For more information, see [additionalBrowserArguments for dotnet][Webview2ReferenceDotnet09515MicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments] and [additionalBrowserArguments for Win32][Webview2ReferenceWin3209538Webview2IdlParameters].</span></span>  
    
* * *  


* * *  

## <span data-ttu-id="fac50-214">関連項目</span><span class="sxs-lookup"><span data-stu-id="fac50-214">See also</span></span>  

*   <span data-ttu-id="fac50-215">WebView2 の使用を開始するには、 [WebView2 の概要ガイド][Webview2MainGettingStarted]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fac50-215">To get started using WebView2, see [WebView2 Getting Started Guides][Webview2MainGettingStarted].</span></span>  
*   <span data-ttu-id="fac50-216">WebView2 機能の包括的な例については、GitHub の [WebView2Samples][GithubMicrosoftedgeWebview2samples] リポジトリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fac50-216">For a comprehensive example of WebView2 capabilities, see the [WebView2Samples][GithubMicrosoftedgeWebview2samples] repo on GitHub.</span></span>
*   <span data-ttu-id="fac50-217">WebView2 Api について詳しくは、 [api リファレンス][Webview2ApiReference]をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fac50-217">For more detailed information about WebView2 APIs, see [API reference][Webview2ApiReference].</span></span>
*   <span data-ttu-id="fac50-218">WebView2 の詳細については、「 [WebView2 のリソース][Webview2MainNextSteps]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fac50-218">For more information about WebView2, see [WebView2 Resources][Webview2MainNextSteps].</span></span>

## <span data-ttu-id="fac50-219">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="fac50-219">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール"  

[Webview2ReferenceDotnet09628MicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments]: ../reference/dotnet/0-9-628/microsoft-web-webview2-core-corewebview2environmentoptions.md#additionalbrowserarguments "AdditionalBrowserArguments-0.9.515 クラス | WebView2 クラスの場合 |Microsoft ドキュメント"  
[Webview2ReferenceWin3209622Webview2IdlParameters]: ../reference/win32/0-9-622/webview2-idl.md#createcorewebview2environment  "CreateCoreWebView2Environment-Globals |Microsoft ドキュメント"  
[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API リファレンス |Microsoft ドキュメント"  
[Webview2MainNextSteps]: ../index.md#next-steps "次の手順-Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  
[Webview2MainGettingStarted]: ../index.md#getting-started "はじめに-Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftVscodeJSDebugWhatsNew]: https://github.com/microsoft/vscode-js-debug#whats-new "新機能-Visual Studio コードの JavaScript デバッガー-microsoft/vscode-js-debug |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) WebView アプリケーション-Visual Studio Code-Microsoft Edge 用デバッガー-microsoft/vscode-edge-debug2 |GitHub"  
