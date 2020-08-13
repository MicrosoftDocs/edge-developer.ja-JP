---
description: WebView2 コントロールをデバッグする方法について説明します。
title: デバッグ WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/10/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 6b2cc65e5cb368c29efec2eb3638f0c1772000d9
ms.sourcegitcommit: 4bc904c5d54347185f275bd76441975be471c320
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2020
ms.locfileid: "10926478"
---
# <span data-ttu-id="7a059-104">WebView2 を使用してデバッグする方法</span><span class="sxs-lookup"><span data-stu-id="7a059-104">How to Debug with WebView2</span></span>  

<span data-ttu-id="7a059-105">Microsoft Edge WebView2 コントロールの目標は、web とネイティブアプリケーションの開発機能と開発者ツールの両方の最良の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="7a059-105">The goal of the Microsoft Edge WebView2 control is combining the best of both the web and native application development features and developer tools.</span></span>  <span data-ttu-id="7a059-106">次のページでは、WebView2 コントロールを使用して開発するときに使用するさまざまなツールについて、その概要を示します。</span><span class="sxs-lookup"><span data-stu-id="7a059-106">The following page outlines the different tools to use when developing with WebView2 controls.</span></span>  

## <span data-ttu-id="7a059-107">Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="7a059-107">Microsoft Edge DevTools</span></span>  

<span data-ttu-id="7a059-108">Microsoft edge [(Chromium) 開発者ツール][DevtoolsGuideChromiumMain]を使用して、microsoft edge と同じ方法で、WebView2 コントロールに表示される web コンテンツをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="7a059-108">Use [Microsoft Edge (Chromium) Developer Tools][DevtoolsGuideChromiumMain] to debug web content displayed in WebView2 controls, in the same way that you use Microsoft Edge.</span></span>  <span data-ttu-id="7a059-109">DevTools を開くには、[WebView] ウィンドウにフォーカスを設定し、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="7a059-109">To open the DevTools, set focus on the WebView window and then use any of the following actions.</span></span>  
*   <span data-ttu-id="7a059-110">を選択し `F12` ます。</span><span class="sxs-lookup"><span data-stu-id="7a059-110">Select `F12`.</span></span>  
*   <span data-ttu-id="7a059-111">を選択し `Ctrl` + `Shift` + `I` ます。</span><span class="sxs-lookup"><span data-stu-id="7a059-111">Select `Ctrl`+`Shift`+`I`.</span></span>  
*   <span data-ttu-id="7a059-112">コンテキストメニューを開く (\ 右クリック \) > 選択] をクリック `Inspect` します。</span><span class="sxs-lookup"><span data-stu-id="7a059-112">Open the context menu \(right-click\) > select `Inspect`.</span></span>  

:::image type="complex" source="../media/f12.png" alt-text="Microsoft Edge DevTools" lightbox="../media/f12.png":::
   <span data-ttu-id="7a059-114">Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="7a059-114">Microsoft Edge DevTools</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="7a059-115">ネイティブデバッガーがアタッチされている Visual Studio でアプリケーションをデバッグするときに、を押すと、 `F12` 開発者ツールではなくネイティブデバッガーがトリガーされることがあります。</span><span class="sxs-lookup"><span data-stu-id="7a059-115">When you debug your application in Visual Studio with the native debugger attached, pressing `F12` may trigger the native debugger instead of Developer Tools.</span></span>  <span data-ttu-id="7a059-116">`Ctrl` + `Shift` + `I` または、コンテキストメニュー \ (右クリック \) を使用して、この問題を回避します。</span><span class="sxs-lookup"><span data-stu-id="7a059-116">Press `Ctrl`+`Shift`+`I`, or use the context menu \(right-click\) to avoid the situation.</span></span>  

> [!NOTE]
> <span data-ttu-id="7a059-117">WebView を初めて `--auto-open-devtools-for-tabs` 作成するときに、コマンドライン引数を使って新しい DevTools ウィンドウを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="7a059-117">You may use the `--auto-open-devtools-for-tabs` command-line argument to open a new DevTools window when you first create a WebView.</span></span>  <!--See `CreateCoreWebView2Controller` documentation for how to provide additional command-line arguments to the browser process.  See `LoaderOverride` registry key to examine different builds of WebView2 without modifying your application in the `CreateCoreWebView2Controller` documentation.  -->  

## <span data-ttu-id="7a059-118">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7a059-118">Visual Studio</span></span>  

<span data-ttu-id="7a059-119">Visual studio 2019 バージョン 16.4 Preview 2 以降のスクリプトデバッガーを使って、Visual Studio でスクリプトをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="7a059-119">Use the script debugger in Visual Studio 2019 version 16.4 Preview 2 or later to debug your script in Visual Studio.</span></span>  <span data-ttu-id="7a059-120">C++ のワークロードを使用して、**デスクトップ開発**の**JavaScript 診断**コンポーネントを確認します。</span><span class="sxs-lookup"><span data-stu-id="7a059-120">Verify the **JavaScript diagnostics** component in **Desktop development with C++** workload is installed.</span></span>  

:::image type="complex" source="../media/vs-js-diagnostics.jpg" alt-text="Visual Studio JavaScript 診断ツール":::
   <span data-ttu-id="7a059-122">Visual Studio JavaScript 診断ツール</span><span class="sxs-lookup"><span data-stu-id="7a059-122">Visual Studio JavaScript diagnostics</span></span>  
:::image-end:::  

<!--todo: Please update the image to use a red rectangle to outline the portion of the screen to highlight  -->  

<span data-ttu-id="7a059-123">WebView2 スクリプトのデバッグを有効にするには、プロジェクトのコンテキストメニュー \ (右クリック \) を開いて、[**プロパティ**] > 選びます。</span><span class="sxs-lookup"><span data-stu-id="7a059-123">To enable WebView2 script debugging, open the context menu \(right-click\) on your project > select **Properties**.</span></span>  

*   <span data-ttu-id="7a059-124">[**構成プロパティ**] で、[**デバッグ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7a059-124">On **Configuration Properties**, select **Debugging**.</span></span>  
*   <span data-ttu-id="7a059-125">[**デバッガーの種類**] プロパティで、オプションの一覧から [ **JavaScript (WebView2)** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="7a059-125">On the **Debugger Type** property, select **JavaScript (WebView2)** from the list of options.</span></span> 

:::image type="complex" source="../media/vs-script-debugger.jpg" alt-text="Visual Studio JavaScript デバッガー":::
   <span data-ttu-id="7a059-127">Visual Studio JavaScript デバッガー</span><span class="sxs-lookup"><span data-stu-id="7a059-127">Visual Studio JavaScript Debugger</span></span>  
:::image-end:::  

<!--todo: Please update the image to use a red rectangle to outline the portion of the screen to highlight  -->  

<span data-ttu-id="7a059-128">すべての設定が完了し、デバッグする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="7a059-128">You are all set up and ready to debug.</span></span>  

<span data-ttu-id="7a059-129">デバッグするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="7a059-129">To Debug, complete the following actions.</span></span>  

1.  <span data-ttu-id="7a059-130">ブレークポイントを設定する</span><span class="sxs-lookup"><span data-stu-id="7a059-130">Set Breakpoints</span></span>  
    *   <span data-ttu-id="7a059-131">スクリプトファイルを開き、目的の場所にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="7a059-131">Open the script file and set the breakpoint where you want it.</span></span>  
        
        > [!NOTE]
        > <span data-ttu-id="7a059-132">JS/TS デバッグアダプターはソースパスマッピングを行っていません。</span><span class="sxs-lookup"><span data-stu-id="7a059-132">The JS/TS debug adapter does not do source path mapping.</span></span><span data-ttu-id="7a059-133">WebView2 に関連付けられているのとまったく同じパスを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a059-133">  You must open the exact same path associated with your WebView2.</span></span>  
        
1.  <span data-ttu-id="7a059-134">コードを実行する</span><span class="sxs-lookup"><span data-stu-id="7a059-134">Run Code</span></span>  
    *   <span data-ttu-id="7a059-135">適切なビルドのフレーバーとランタイム環境を選び、ローカル windows デバッガーを起動します。</span><span class="sxs-lookup"><span data-stu-id="7a059-135">Select your appropriate build flavor and runtime environment and then start the local windows debugger.</span></span>  
1.  <span data-ttu-id="7a059-136">デバッグコンソールの表示</span><span class="sxs-lookup"><span data-stu-id="7a059-136">View Debug Console</span></span>  
    *   <span data-ttu-id="7a059-137">アプリケーションが実行され、最初の webview2 を作成した後でデバッガーが接続されます。</span><span class="sxs-lookup"><span data-stu-id="7a059-137">You application runs and the debugger connects after the first webview2 is created.</span></span><span data-ttu-id="7a059-138">保留中のデバッグ出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a059-138">  Any pending debug output is displayed.</span></span>  
        
        > [!NOTE]
        > <span data-ttu-id="7a059-139">このデバッグ方法は、現在、Win32 アプリケーションと Office アドインに制限されています。</span><span class="sxs-lookup"><span data-stu-id="7a059-139">This method of debugging is currently restricted to Win32 applications and Office add-ins.</span></span>  
        
## <span data-ttu-id="7a059-140">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="7a059-140">Visual Studio Code</span></span>  

<span data-ttu-id="7a059-141">Visual Studio コードを使って、WebView2 コントロールで実行されるスクリプトをデバッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="7a059-141">You may use Visual Studio Code to debug scripts that run in WebView2 controls.</span></span>  <span data-ttu-id="7a059-142">詳細については、「 [Microsoft Edge (Chromium) WebView アプリケーション][GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a059-142">For more information, see [Microsoft Edge (Chromium) WebView Applications][GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications].</span></span>  

<!--todo:  add See also heading  -->  

## <span data-ttu-id="7a059-143">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="7a059-143">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!--## Debugging  

Open DevTools with the normal shortcuts: `F12` or `Ctrl+Shift+I`. You can use the `--auto-open-devtools-for-tabs` command argument switch to have the DevTools window open immediately when first creating a WebView. See CreateCoreWebView2Controller documentation for how to provide additional command line arguments to the browser process. Check out the LoaderOverride registry key for trying out different builds of WebView2 without modifying your application in the CreateCoreWebView2Controller documentation.  -->  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) WebView アプリケーション-VS コード-Microsoft Edge 用デバッガー-microsoft/vscode-edge-debug2 |GitHub"  
