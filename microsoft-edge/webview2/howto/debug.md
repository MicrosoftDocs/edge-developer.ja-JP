---
description: WebView2 コントロールをデバッグする方法について説明します。
title: WebView2 アプリケーションのデバッグを開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/02/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、エッジ html
ms.openlocfilehash: 4f94fe880f66f8aeb387d2db4a8bfaab20699466
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230699"
---
# <span data-ttu-id="dcf80-104">WebView2 アプリケーションのデバッグを開始する</span><span class="sxs-lookup"><span data-stu-id="dcf80-104">Get started debugging WebView2 applications</span></span>  

<span data-ttu-id="dcf80-105">Microsoft Edge WebView2 コントロールの目標は、Web とネイティブの両方のアプリケーション開発機能とツールを組み合わせることです。</span><span class="sxs-lookup"><span data-stu-id="dcf80-105">The goal of the Microsoft Edge WebView2 control is to combine the best of both the web and native application development features and tools.</span></span>  <span data-ttu-id="dcf80-106">WebView2 アプリケーションを開発する場合は、アプリケーションをデバッグする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcf80-106">When you develop your WebView2 application, you should debug your application.</span></span>  <span data-ttu-id="dcf80-107">この記事では、WebView2 アプリケーションで Web とネイティブ コードの両方をデバッグするために使用するさまざまなツールの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-107">This article outlines the different tools to use to debug both your web and native code in your WebView2 application.</span></span>  

## [<span data-ttu-id="dcf80-108">Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="dcf80-108">Microsoft Edge DevTools</span></span>](#tab/devtools)  

<span data-ttu-id="dcf80-109">[Microsoft Edge (Chromium) 開発者][DevtoolsGuideChromiumMain]ツールを使用して、Microsoft Edge に表示される別の Web ページをデバッグするのと同じ方法で、WebView2 コントロールに表示される Web コンテンツをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="dcf80-109">Use [Microsoft Edge (Chromium) Developer Tools][DevtoolsGuideChromiumMain] to debug web content displayed in WebView2 controls, in the same way that you may debug for another webpage displayed in Microsoft Edge.</span></span>  <span data-ttu-id="dcf80-110">DevTools を開く場合は、WebView コントロールにフォーカスを設定し、次のいずれかのアクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-110">To open the DevTools, set focus on the WebView control and then use one of the following actions.</span></span>  

*   <span data-ttu-id="dcf80-111">`F12` を選択します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-111">Select `F12`.</span></span>  
*   <span data-ttu-id="dcf80-112">選択 `Ctrl` + `Shift` + `I` します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-112">Select `Ctrl`+`Shift`+`I`.</span></span>  
*   <span data-ttu-id="dcf80-113">コンテキスト メニュー \(右クリック\) を開き、選択します `Inspect` 。</span><span class="sxs-lookup"><span data-stu-id="dcf80-113">Open the context menu \(right-click\) and choose `Inspect`.</span></span>  
    
<span data-ttu-id="dcf80-114">詳しくは [、DevTools の概要に関するページをご覧ください][DevtoolsGuideChromiumMain]。</span><span class="sxs-lookup"><span data-stu-id="dcf80-114">For more information, see [DevTools overview][DevtoolsGuideChromiumMain].</span></span>  

:::image type="complex" source="./media/f12.png" alt-text="DevTools のデバッグ" lightbox="./media/f12.png":::
   <span data-ttu-id="dcf80-116">DevTools のデバッグ</span><span class="sxs-lookup"><span data-stu-id="dcf80-116">DevTools debugging</span></span>  
:::image-end:::  

## [<span data-ttu-id="dcf80-117">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="dcf80-117">Visual Studio</span></span>](#tab/visualstudio)  

<span data-ttu-id="dcf80-118">Visual Studioは、WebView2 アプリケーションで Web およびネイティブ コード用のさまざまなデバッグ ツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-118">Visual Studio provides various debugging tools for web and native code in WebView2 applications.</span></span>  <span data-ttu-id="dcf80-119">このセクションVisual Studio、主に WebView コントロールのデバッグに重点を置きますが、WebView コントロール内の他のデバッグ方法Visual Studio通常どおり使用できます。</span><span class="sxs-lookup"><span data-stu-id="dcf80-119">In the Visual Studio section, the primary focus is debugging WebView controls, however the other methods of debugging in Visual Studio are available as usual.</span></span>  <span data-ttu-id="dcf80-120">Win32 アプリケーションで Web とネイティブ コードをデバッグしたり、アドインのみをOfficeするには、次のプロセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-120">Use the following process to debug web and native code in Win32 applications or Office Add-ins only.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="dcf80-121">ネイティブ デバッガーがアタッチされた Visual Studio でアプリケーションをデバッグすると、選択すると、開発者ツールではなくネイティブ デバッガー `F12` がトリガーされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dcf80-121">When you debug your application in Visual Studio with the native debugger attached, selecting `F12` may trigger the native debugger instead of Developer Tools.</span></span>  <span data-ttu-id="dcf80-122">状況 `Ctrl` + `Shift` + `I` を回避するには、コンテキスト メニュー \(右クリック\) を選択するか、または使用します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-122">Select `Ctrl`+`Shift`+`I`, or use the context menu \(right-click\) to avoid the situation.</span></span>  

<span data-ttu-id="dcf80-123">開始する前に、次の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dcf80-123">Before you begin, ensure the following requirements are met.</span></span>  

*   <span data-ttu-id="dcf80-124">スクリプトをデバッグするには、アプリをアプリ内から起動するVisual Studio。</span><span class="sxs-lookup"><span data-stu-id="dcf80-124">To debug scripts, the app must be launched from within Visual Studio.</span></span>  
*   <span data-ttu-id="dcf80-125">実行中の WebView2 プロセスにデバッガーをアタッチすることはできません。</span><span class="sxs-lookup"><span data-stu-id="dcf80-125">You cannot attach a debugger to a running WebView2 process.</span></span>  
*   <span data-ttu-id="dcf80-126">2019 Visual Studio 16.4 Preview 2 以降をインストールします。</span><span class="sxs-lookup"><span data-stu-id="dcf80-126">Install Visual Studio 2019 version 16.4 Preview 2 or later.</span></span>  
    
<span data-ttu-id="dcf80-127">スクリプト デバッガー ツールをインストールしてセットアップVisual Studio。</span><span class="sxs-lookup"><span data-stu-id="dcf80-127">Install and set up the script debugger tools in Visual Studio.</span></span>  

1.  <span data-ttu-id="dcf80-128">C++ を使用したデスクトップ開発で **JavaScript 診断コンポーネント** をインストールするには、次 **の操作を実行します**。</span><span class="sxs-lookup"><span data-stu-id="dcf80-128">Complete the following actions to install the **JavaScript diagnostics** component in **Desktop development with C++**.</span></span>  
    
    1.  <span data-ttu-id="dcf80-129">エクスプローラー バーに「.」と入力します `Visual Studio Installer` 。</span><span class="sxs-lookup"><span data-stu-id="dcf80-129">In the Windows Explorer bar, type `Visual Studio Installer`.</span></span>  
    1.  <span data-ttu-id="dcf80-130">**[Visual Studioを選択して**開きます。</span><span class="sxs-lookup"><span data-stu-id="dcf80-130">Choose **Visual Studio Installer** to open it.</span></span>  
    1.  <span data-ttu-id="dcf80-131">新しいVisual Studioインストーラーのインストール済みバージョンで、[その他]\*\*\*\* ボタンを選択し、[変更] を**選択します**。</span><span class="sxs-lookup"><span data-stu-id="dcf80-131">In the Visual Studio Installer, on the installed version, choose the **More** button, and then choose **Modify**.</span></span>  
    1.  <span data-ttu-id="dcf80-132">[Visual Studioワークロード] で、[C++ でのデスクトップ開発]**設定を選択**します。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="dcf80-132">In Visual Studio, under **Workloads**, choose the **Desktop Development in C++** setting.</span></span>  
        
        :::image type="complex" source="./media/workloads.png" alt-text="Visual Studioの変更画面" lightbox="./media/workloads.png":::
            <span data-ttu-id="dcf80-134">Visual Studioの変更画面</span><span class="sxs-lookup"><span data-stu-id="dcf80-134">Visual Studio Modifying Workloads Screen</span></span>
        :::image-end:::  
        
    1.  <span data-ttu-id="dcf80-135">個別の **コンポーネントを選択します**。</span><span class="sxs-lookup"><span data-stu-id="dcf80-135">Choose **Individual components**.</span></span>  
    1.  <span data-ttu-id="dcf80-136">検索ボックスに「.」と入力します `JavaScript diagnostics` 。</span><span class="sxs-lookup"><span data-stu-id="dcf80-136">In the search box, enter `JavaScript diagnostics`.</span></span>  
    1.  <span data-ttu-id="dcf80-137">**JavaScript 診断設定を選択**します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-137">Choose the **JavaScript diagnostics** setting.</span></span>  
    1.  <span data-ttu-id="dcf80-138">Choose **Modify**.</span><span class="sxs-lookup"><span data-stu-id="dcf80-138">Choose **Modify**.</span></span> 
        
        :::image type="complex" source="./media/indivcomp.png" alt-text="Visual Studioの変更] タブ" lightbox="./media/indivcomp.png":::
           <span data-ttu-id="dcf80-140">Visual Studioの変更] タブ</span><span class="sxs-lookup"><span data-stu-id="dcf80-140">Visual Studio Modifying Individual Components Tab</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="dcf80-141">WebView2 アプリケーションのスクリプト デバッグを有効にする。</span><span class="sxs-lookup"><span data-stu-id="dcf80-141">Enable script debugging for WebView2 applications.</span></span>  
    1.  <span data-ttu-id="dcf80-142">WebView2 プロジェクトで、コンテキスト メニュー \(右クリック\) を開き、[プロパティ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="dcf80-142">In your WebView2 project, open the context menu \(right-click\), and choose **Properties**.</span></span>  
    1.  <span data-ttu-id="dcf80-143">[構成プロパティ **] で、[** デバッグ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dcf80-143">Under the **Configuration Properties**, choose **Debugging**.</span></span>  
    1.  <span data-ttu-id="dcf80-144">デバッガーの**種類で\*\*\*\*、JavaScript (WebView2) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dcf80-144">Under the **Debugger Type**, choose **JavaScript (WebView2)**.</span></span>  
        
        :::image type="complex" source="./media/enbjs.png" alt-text="Visual Studioデバッグ構成プロパティ" lightbox="./media/enbjs.png":::
           <span data-ttu-id="dcf80-146">Visual Studio **デバッグ構成** プロパティ</span><span class="sxs-lookup"><span data-stu-id="dcf80-146">Visual Studio **Debugging** Configuration Property</span></span>  
        :::image-end:::  
        
<span data-ttu-id="dcf80-147">WebView2 アプリケーションをデバッグするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-147">Complete the following actions to debug your WebView2 application.</span></span>  

1.  <span data-ttu-id="dcf80-148">ソース コードにブレークポイントを設定するには、行番号の左側にポイントし、ブレークポイントの設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-148">To set a breakpoint in your source code, hover to the left of the line number, and choose to set a breakpoint.</span></span>  <span data-ttu-id="dcf80-149">JS/TS デバッグ アダプターはソース パス マッピングを実行します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-149">The JS/TS debug adapter does not perform source path mapping.</span></span>  <span data-ttu-id="dcf80-150">WebView2 に関連付けられているパスとまったく同じパスを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcf80-150">You must open the exact same path associated with your WebView2.</span></span>  
    
    :::image type="complex" source="./media/breakpoint.png" alt-text="Visual Studioブレークポイントを追加する" lightbox="./media/breakpoint.png"::: 
       <span data-ttu-id="dcf80-152">Visual Studioブレークポイントを追加する</span><span class="sxs-lookup"><span data-stu-id="dcf80-152">Visual Studio add breakpoint</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="dcf80-153">デバッガーを実行するには、プラットフォームのビット サイズを選択し、ローカル Windows デバッガーの横にある緑色の再生ボタン **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dcf80-153">To run the debugger, choose the bit size of the platform, and then choose the green play button next to **Local Windows Debugger**.</span></span>  <span data-ttu-id="dcf80-154">アプリケーションが実行され、デバッガーは作成された最初の WebView2 プロセスに接続します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-154">The application runs and the debugger connects to the first WebView2 process that is created.</span></span>  
    
    :::image type="complex" source="./media/run.png" alt-text=" Visual Studio Windows デバッガーを使う" lightbox="./media/run.png"::: 
       <span data-ttu-id="dcf80-156">Visual Studio Windows **デバッガーのインストール**</span><span class="sxs-lookup"><span data-stu-id="dcf80-156">Visual Studio **Local Windows Debugger**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="dcf80-157">デバッグ コンソール **で、** デバッガーからの出力を見つける。</span><span class="sxs-lookup"><span data-stu-id="dcf80-157">In the **Debug Console**, find the output from the debugger.</span></span>  
    
    :::image type="complex" source="./media/console.png" alt-text=" Visual Studio デバッグ コンソール" lightbox="./media/console.png"::: 
       <span data-ttu-id="dcf80-159">Visual Studio **デバッグ コンソール**</span><span class="sxs-lookup"><span data-stu-id="dcf80-159">Visual Studio **Debug Console**</span></span>  
    :::image-end:::  
    
## [<span data-ttu-id="dcf80-160">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="dcf80-160">Visual Studio Code</span></span>](#tab/visualstudiocode)  

<span data-ttu-id="dcf80-161">Microsoft Visual Studio コードを使用して、WebView2 コントロールで実行されるスクリプトをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="dcf80-161">Use Microsoft Visual Studio Code to debug scripts that run in WebView2 controls.</span></span>  <!--Ensure that you're using Visual Studio Code version [insert build here] or later.  -->  

<span data-ttu-id="dcf80-162">コードVisual Studio、次のアクションを実行してコードをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="dcf80-162">In Visual Studio Code, complete the following actions to debug your code.</span></span> 

1.  <span data-ttu-id="dcf80-163">プロジェクトにはファイルが必要 `launch.json` です。</span><span class="sxs-lookup"><span data-stu-id="dcf80-163">Your project is required to have a `launch.json` file.</span></span>  <span data-ttu-id="dcf80-164">プロジェクトにファイルが存在しない場合は、次のコード スニペットをコピーして `launch.json` 、新しいファイルを作成 `launch.json` します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-164">If your project doesn't have a `launch.json` file, copy the following code snippet and create a new `launch.json` file.</span></span>  
    
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
    
1.  <span data-ttu-id="dcf80-165">ソース コードにブレークポイントを設定するには、行にカーソルを合わせると、</span><span class="sxs-lookup"><span data-stu-id="dcf80-165">To set a breakpoint in your source code, hover on the line, and select</span></span> `F9`
    
    :::image type="complex" source="./media/breakpointvs.png" alt-text="ブレークポイントがコードでVisual Studioされている" lightbox="./media/breakpointvs.png":::
       <span data-ttu-id="dcf80-167">ブレークポイントがコードでVisual Studioされている</span><span class="sxs-lookup"><span data-stu-id="dcf80-167">Breakpoint is set in Visual Studio Code</span></span>  
    :::image-end:::
    
    > [!NOTE]
    > <span data-ttu-id="dcf80-168">コードVisual Studioソース マッピングを実行しないので、WebView2 が使用するファイルと同じファイルにブレークポイントを設定してください。</span><span class="sxs-lookup"><span data-stu-id="dcf80-168">Because Visual Studio Code does not perform source mapping, ensure you set breakpoints in the same file that WebView2 uses.</span></span>  <span data-ttu-id="dcf80-169">パスが一致しない場合、Visual Studioコードは実行中のコードをブレークポイントで一時停止しません。</span><span class="sxs-lookup"><span data-stu-id="dcf80-169">If the paths do not match, Visual Studio Code does not pause the running code at the breakpoint.</span></span>  
    
1.  <span data-ttu-id="dcf80-170">コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-170">Run the code.</span></span>  
    1.  <span data-ttu-id="dcf80-171">[実行 **] タブ** で、ドロップダウン メニューから起動構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-171">On the **Run** tab, choose the launch configuration from the dropdown menu.</span></span>  
    1.  <span data-ttu-id="dcf80-172">アプリケーションのデバッグを開始するには、[デバッグの開始] を選択します。これは、起動構成ドロップダウンの横にある緑色の三角形です。</span><span class="sxs-lookup"><span data-stu-id="dcf80-172">To start debugging your application, choose Start Debugging, which is the green triangle next to the launch configuration drop down.</span></span>  
        
        :::image type="complex" source="./media/runvs.png" alt-text=" Visual Studioコードの実行] タブ" lightbox="./media/runvs.png":::
           <span data-ttu-id="dcf80-174">Visual Studioコードの実行] タブ</span><span class="sxs-lookup"><span data-stu-id="dcf80-174">Visual Studio Code Run tab</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="dcf80-175">デバッグ **コンソールを開** き、デバッグ出力とエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-175">Open **Debug Console** to view the debug output and errors.</span></span>  
    
    :::image type="complex" source="./media/resultsvs.png" alt-text=" Visual Studio コード デバッグ コンソール" lightbox="./media/resultsvs.png":::
       <span data-ttu-id="dcf80-177">Visual Studio コード デバッグ コンソール</span><span class="sxs-lookup"><span data-stu-id="dcf80-177">Visual Studio Code Debug Console</span></span>  
    :::image-end:::  
    
<span data-ttu-id="dcf80-178">**詳細設定**:</span><span class="sxs-lookup"><span data-stu-id="dcf80-178">**Advanced Settings**:</span></span>  

*   <span data-ttu-id="dcf80-179">対象となる Web ビューのデバッグ。</span><span class="sxs-lookup"><span data-stu-id="dcf80-179">Targeted Webview debugging.</span></span> 
    
    <span data-ttu-id="dcf80-180">一部の WebView2 アプリケーションでは、複数の WebView2 コントロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dcf80-180">In some WebView2 applications, you may use more than one WebView2 control.</span></span> <span data-ttu-id="dcf80-181">この状況でデバッグする WebView2 コントロールを選択するには、ターゲット Webview2 デバッグを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dcf80-181">To pick the WebView2 control to debug in this situation you can use targeted webview2 debugging</span></span> 
    
    <span data-ttu-id="dcf80-182">次 `launch.json` の操作を開いて完了し、対象の Webview デバッグを使用します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-182">Open `launch.json` and complete the following actions to use targeted Webview debugging.</span></span>  
    
    1.  <span data-ttu-id="dcf80-183">パラメーターが `useWebview` 次に設定されているのを確認します `true` 。</span><span class="sxs-lookup"><span data-stu-id="dcf80-183">Confirm that the `useWebview` parameter is set to `true`.</span></span>  
    1.  <span data-ttu-id="dcf80-184">パラメーターを追加 `urlFilter` します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-184">Add the `urlFilter` parameter.</span></span>  <span data-ttu-id="dcf80-185">WebView2 コントロールが URL に移動すると、URL に表示される文字列を比較するためにパラメーター値 `urlFilter` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="dcf80-185">When the WebView2 control navigates to a URL, the `urlFilter` parameter value is used to compare strings that appear in the URL.</span></span>  
    
    ```json
    "useWebview": "true",
    "urlFilter": "*index.ts",
    
    // Other urlFilter options.
    
    urlFilter="*index.ts"    // Match any url that ends with index.ts, and ignore all leading characters. 
    urlFilter="*index*"      // Match any url that contains the string index anywhere in the URL.  
    urlFilter="file://C:/path/to/my/index.ts," // To match explicit file called index.ts.  
    ```  
    
    <span data-ttu-id="dcf80-186">アプリケーションをデバッグするときに、レンダリング プロセスの最初からコードをステップ実行する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="dcf80-186">When debugging your application, you may need to step through the code from the beginning of the rendering process.</span></span> <span data-ttu-id="dcf80-187">サイトで Web ページをレンダリングする場合にソース コードにアクセスできない場合は、このオプションを使用できます。Web ページは認識できないパラメーターを `?=value`  無視します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-187">If you are rendering webpages on sites and you don't have access to the source code, you can use the `?=value` option, because webpages ignore unrecognized parameters.</span></span>   
    
    > [!IMPORTANT]
    > <span data-ttu-id="dcf80-188">URL で最初の一致が見つかると、デバッガーは停止します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-188">After the first match is found in the URL, the debugger stops.</span></span>  <span data-ttu-id="dcf80-189">CDP ポートは、すべての WebView2 コントロールで共有され、1 つのポート番号を使用するために、2 つの WebView2 コントロールを同時にデバッグすることはできません。</span><span class="sxs-lookup"><span data-stu-id="dcf80-189">You cannot debug two WebView2 controls at the same time because the CDP port is shared by all WebView2 controls, and uses a single port number.</span></span>  
    
*   <span data-ttu-id="dcf80-190">実行中のプロセスをデバッグする</span><span class="sxs-lookup"><span data-stu-id="dcf80-190">Debug running processes</span></span>  
    
    <span data-ttu-id="dcf80-191">実行中の WebView2 プロセスにデバッガーをアタッチする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="dcf80-191">You may need to attach the debugger to running WebView2 processes.</span></span> <span data-ttu-id="dcf80-192">これを行うには、in `launch.json` パラメーターを `request` 次の値に更新します `attach` 。</span><span class="sxs-lookup"><span data-stu-id="dcf80-192">To do that, in `launch.json`, update the `request` parameter to `attach`.</span></span>
    
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
    
    <span data-ttu-id="dcf80-193">WebView2 コントロールは、Cdp ポートを開き、WebView2 コントロールのデバッグを可能にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcf80-193">Your WebView2 control must open the CDP port to allow debugging of the WebView2 control.</span></span>  <span data-ttu-id="dcf80-194">デバッガーを起動する前に、Chrome Developer Protocol (CDP) ポートを開いている WebView2 コントロールが 1 つだけ確保するために、コードをビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcf80-194">Your code must be built to ensure that only one WebView2 control has a Chrome Developer Protocol (CDP) port open, before starting the debugger.</span></span>  
    
*   <span data-ttu-id="dcf80-195">デバッグ トレース オプション</span><span class="sxs-lookup"><span data-stu-id="dcf80-195">Debug tracing options</span></span>  
    
    <span data-ttu-id="dcf80-196">デバッグ トレース `trace` を有効にするにはlaunch.jsパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-196">Add the `trace` parameter to launch.json to enable debug tracing.</span></span>  
    
    1.  <span data-ttu-id="dcf80-197">パラメーターを `trace` 追加します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-197">Add `trace` parameter.</span></span>  
        
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
              
              :::image type="complex" source="./media/tracelog.png" alt-text=" デバッグ出力をログ ファイルに保存します。" lightbox="./media/tracelog.png":::
                 <span data-ttu-id="dcf80-199">デバッグ出力をログ ファイルに保存する</span><span class="sxs-lookup"><span data-stu-id="dcf80-199">Save debug output to a log file</span></span>  
              :::image-end:::  
           :::column-end:::
           :::column span="":::
              ```json
              ,"trace": "verbose"  // Turn on verbose tracing in the Debug Output pane.
              ```  
              
              :::image type="complex" source="./media/verbose.png" alt-text=" 詳細出力" lightbox="./media/verbose.png":::
                 <span data-ttu-id="dcf80-201">Visual Studioトレースを有効にしたコード デバッグ出力</span><span class="sxs-lookup"><span data-stu-id="dcf80-201">Visual Studio Code Debug Output with verbose tracing turned on</span></span>  
              :::image-end:::  
           :::column-end:::
        :::row-end:::  
        
*   <span data-ttu-id="dcf80-202">アドインOfficeデバッグします。</span><span class="sxs-lookup"><span data-stu-id="dcf80-202">Debug Office Add-ins.</span></span>
    
    <span data-ttu-id="dcf80-203">アドインをデバッグするOffice、アドイン ソース コードをアドイン コードの別のインスタンスVisual Studioします。</span><span class="sxs-lookup"><span data-stu-id="dcf80-203">If you're debugging Office Add-ins, open the add-in source code in a separate instance of Visual Studio Code.</span></span>  <span data-ttu-id="dcf80-204">WebView2 launch.jsでアプリケーションを開き、次のコード スニペットを追加して、デバッガーをアドインにアタッチOfficeします。</span><span class="sxs-lookup"><span data-stu-id="dcf80-204">Open launch.json in your WebView2 application and add the following code snippet to attach the debugger to the Office add-in.</span></span>
    
    ```json
    ,"debugServer": 4711
    ```  
    
*   <span data-ttu-id="dcf80-205">デバッガーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="dcf80-205">Troubleshooting the debugger</span></span>  
    
    <span data-ttu-id="dcf80-206">デバッガーを使用する場合、次のシナリオが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="dcf80-206">You may encounter the following scenarios when using the debugger.</span></span>  
    
    *   <span data-ttu-id="dcf80-207">デバッガーはブレークポイントで停止しないので、デバッグ出力があります。</span><span class="sxs-lookup"><span data-stu-id="dcf80-207">The debugger doesn't stop at the breakpoint, and you have debug output.</span></span>  <span data-ttu-id="dcf80-208">この問題を解決するには、ブレークポイントが設定されたファイルが、WebView2 コントロールで使用されているファイルと同じファイルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcf80-208">To solve the issue, confirm that the file with the breakpoint is the same file that's used by the WebView2 control.</span></span>  <span data-ttu-id="dcf80-209">デバッガーはソース パスマッピングを実行します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-209">The debugger doesn't perform source path mapping.</span></span>  
    *   <span data-ttu-id="dcf80-210">実行中のプロセスにアタッチできないので、タイムアウト エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-210">You can't attach to a running process, and you get a timeout error.</span></span>  <span data-ttu-id="dcf80-211">この問題を解決するには、WebView2 コントロールが CDP ポートを開いているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-211">To solve the issue, confirm that the WebView2 control opened the CDP port.</span></span>  <span data-ttu-id="dcf80-212">レジストリの  `additionalBrowserArguments`  値が正しいか、オプションが正しいか確認します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-212">Ensure your `additionalBrowserArguments` value in the registry is correct, or the options are correct.</span></span>  <span data-ttu-id="dcf80-213">詳細については [、dotnet 用の additionalBrowserArguments][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments] と [Win32 用の additionalBrowserArguments を参照してください][Webview2ReferenceWin32Webview2IdlParameters]。</span><span class="sxs-lookup"><span data-stu-id="dcf80-213">For more information, see [additionalBrowserArguments for dotnet][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments] and [additionalBrowserArguments for Win32][Webview2ReferenceWin32Webview2IdlParameters].</span></span>  
    
* * *  

## <span data-ttu-id="dcf80-214">関連項目</span><span class="sxs-lookup"><span data-stu-id="dcf80-214">See also</span></span>  

*   <span data-ttu-id="dcf80-215">WebView2 の使用を開始するには [、WebView2 の開始ガイドを参照してください][Webview2MainGettingStarted]。</span><span class="sxs-lookup"><span data-stu-id="dcf80-215">To get started using WebView2, see [WebView2 Getting Started Guides][Webview2MainGettingStarted].</span></span>  
*   <span data-ttu-id="dcf80-216">WebView2 機能の包括的な例については、GitHub の [WebView2Samples][GithubMicrosoftedgeWebview2samples] リポジトリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcf80-216">For a comprehensive example of WebView2 capabilities, see the [WebView2Samples][GithubMicrosoftedgeWebview2samples] repo on GitHub.</span></span>
*   <span data-ttu-id="dcf80-217">WebView2 API の詳細については、API リファレンスを [参照してください][Webview2ApiReference]。</span><span class="sxs-lookup"><span data-stu-id="dcf80-217">For more detailed information about WebView2 APIs, see [API reference][Webview2ApiReference].</span></span>
*   <span data-ttu-id="dcf80-218">WebView2 の詳細については [、「WebView2 リソース」を参照してください][Webview2MainNextSteps]。</span><span class="sxs-lookup"><span data-stu-id="dcf80-218">For more information about WebView2, see [WebView2 Resources][Webview2MainNextSteps].</span></span>
    
## <span data-ttu-id="dcf80-219">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="dcf80-219">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments]: /dotnet/api/microsoft.web.webview2.core.corewebview2environmentoptions.additionalbrowserarguments "CoreWebView2EnvironmentOptions.AdditionalBrowserArguments プロパティ (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[Webview2ReferenceWin32Webview2IdlParameters]: /microsoft-edge/webview2/reference/win32/webview2-idl#createcorewebview2environmentwithoptions  "CreateCoreWebView2Environment - Globals |Microsoft Docs"  
[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API リファレンス |Microsoft Docs"  
[Webview2MainNextSteps]: ../index.md#next-steps "次の手順 - Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft Docs"  
[Webview2MainGettingStarted]: ../index.md#getting-started "はじめに - Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft Docs"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック - MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  

[GithubMicrosoftVscodeJSDebugWhatsNew]: https://github.com/microsoft/vscode-js-debug#whats-new "新機能- Visual Studio コードの JavaScript デバッガー - microsoft/vscode-js-debug |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) WebView アプリケーション - Visual Studio コード - Microsoft Edge のデバッガー - microsoft/vscode-edge-debug2 |GitHub"  
