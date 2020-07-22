---
description: WebView2 コントロールをデバッグする方法について説明します。
title: デバッグ WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 232104abc360cfa660d567ffb66535213fcb3ae0
ms.sourcegitcommit: a82aa5fc1ada35cd8274490fbff3c0a850785835
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "10888582"
---
# <span data-ttu-id="83624-104">WebView2 を使用してデバッグする方法</span><span class="sxs-lookup"><span data-stu-id="83624-104">How to Debug with WebView2</span></span>  

<span data-ttu-id="83624-105">Microsoft Edge WebView2 コントロールの目標は、web とネイティブアプリケーションの開発機能と開発者ツールの両方の最良の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="83624-105">The goal of the Microsoft Edge WebView2 control is combining the best of both the web and native application development features and developer tools.</span></span>  <span data-ttu-id="83624-106">次のページでは、WebView2 コントロールを使用して開発するときに使用するさまざまなツールについて、その概要を示します。</span><span class="sxs-lookup"><span data-stu-id="83624-106">The following page outlines the different tools to use when developing with WebView2 controls.</span></span>  

## <span data-ttu-id="83624-107">Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="83624-107">Microsoft Edge DevTools</span></span>  

<span data-ttu-id="83624-108">Microsoft edge [(Chromium) 開発者ツール][DevtoolsMain]を使用して、microsoft edge を使用している場合と同じように、WebView2 コントロールに表示される web コンテンツをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="83624-108">Use [Microsoft Edge (Chromium) Developer Tools][DevtoolsMain] to debug web content displayed in WebView2 controls, in the same way that you would if you were using Microsoft Edge.</span></span>  <span data-ttu-id="83624-109">DevTools を開くには、[WebView] ウィンドウにフォーカスを設定し、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="83624-109">To open the DevTools, set focus on the WebView window and then use any of the following actions.</span></span>  

*   <span data-ttu-id="83624-110">を選択し `F12` ます。</span><span class="sxs-lookup"><span data-stu-id="83624-110">Select `F12`.</span></span>  
*   <span data-ttu-id="83624-111">を選択し `Ctrl` + `Shift` + `I` ます。</span><span class="sxs-lookup"><span data-stu-id="83624-111">Select `Ctrl`+`Shift`+`I`.</span></span>  
*   <span data-ttu-id="83624-112">コンテキストメニューを開き (\ を右クリックし)、を選択し `Inspect` ます。</span><span class="sxs-lookup"><span data-stu-id="83624-112">Open the context menu \(right-click\) and select `Inspect`.</span></span>  

:::image type="complex" source="../media/f12.png" alt-text="Microsoft Edge DevTools" lightbox="../media/f12.png":::
   <span data-ttu-id="83624-114">Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="83624-114">Microsoft Edge DevTools</span></span>  
:::image-end:::  

> [!IMPORTANT]
> <span data-ttu-id="83624-115">ネイティブデバッガーがアタッチされている Visual Studio でアプリケーションをデバッグする場合、を選択すると、 `F12` 開発者ツールではなくネイティブデバッガーがトリガーされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="83624-115">When you debug your application in Visual Studio with the native debugger attached, selecting `F12` may trigger the native debugger instead of Developer Tools.</span></span>  <span data-ttu-id="83624-116">この `Ctrl` + `Shift` + `I` 問題を回避するには、コンテキストメニュー \ (右クリック \) を使用します。</span><span class="sxs-lookup"><span data-stu-id="83624-116">Use `Ctrl`+`Shift`+`I`, or use the context menu \(right-click\) to avoid the situation.</span></span>  

## <span data-ttu-id="83624-117">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="83624-117">Visual Studio</span></span>  

<span data-ttu-id="83624-118">Visual Studio を使って、アプリケーションコードを開発したり、スクリプトをデバッグしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="83624-118">You may use Visual Studio to develop application code and debug scripts at the same time.</span></span>  

<span data-ttu-id="83624-119">次の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="83624-119">Keep the following things in mind.</span></span>  

*   <span data-ttu-id="83624-120">Visual Studio では、アプリが Visual Studio 内から起動された場合にのみデバッグスクリプトをサポートします。</span><span class="sxs-lookup"><span data-stu-id="83624-120">Visual Studio only supports debugging scripts when the app is launched from within Visual Studio.</span></span>  <span data-ttu-id="83624-121">\ (デバッグの実行プロセスをアタッチすることはサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="83624-121">\(Attaching a running process for debugging is not supported.\)</span></span>  
*   <span data-ttu-id="83624-122">ターゲット WebView のデバッグシナリオはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="83624-122">The targeted WebView debugging scenario is not supported.</span></span>  

<span data-ttu-id="83624-123">Visual studio 2019 バージョン 16.4 Preview 2 以降のスクリプトデバッガーを使って、Visual Studio でスクリプトをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="83624-123">Use the script debugger in Visual Studio 2019 version 16.4 Preview 2 or later to debug your script in Visual Studio.</span></span>  

<span data-ttu-id="83624-124">デバッガーを設定します。</span><span class="sxs-lookup"><span data-stu-id="83624-124">Set up the debugger.</span></span>  

*   <span data-ttu-id="83624-125">C++ のワークロードを使用して、**デスクトップ開発**の**JavaScript 診断**コンポーネントを確認します。</span><span class="sxs-lookup"><span data-stu-id="83624-125">Verify the **JavaScript diagnostics** component in **Desktop development with C++** workload is installed.</span></span>  
    
    1.  <span data-ttu-id="83624-126">Windows の [**アプリ & 機能**の設定] に移動します。</span><span class="sxs-lookup"><span data-stu-id="83624-126">Navigate to **Apps & features** settings in Windows.</span></span>  <span data-ttu-id="83624-127">Windows タスクバーを使って検索します。</span><span class="sxs-lookup"><span data-stu-id="83624-127">Search for it using the Windows task bar.</span></span>  
    1.  <span data-ttu-id="83624-128">[ **Modify**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="83624-128">Choose **Modify**.</span></span>  
    1.  <span data-ttu-id="83624-129">[ **C++** ] チェックボックスがオンになっていることを**確認します**。</span><span class="sxs-lookup"><span data-stu-id="83624-129">Verify the **Javascript diagnostics** and **Desktop Development in C++** checkboxes are selected.</span></span>  
        
        :::image type="complex" source="../media/appsandfeatures.png" alt-text="アプリと機能" lightbox="../media/appsandfeatures.png":::
           <span data-ttu-id="83624-131">アプリと機能</span><span class="sxs-lookup"><span data-stu-id="83624-131">Apps & Features</span></span>  
        :::image-end:::  
        
*   <span data-ttu-id="83624-132">WebView2 スクリプトのデバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="83624-132">Enable WebView2 script debugging.</span></span>  
    1.  <span data-ttu-id="83624-133">プロジェクトにカーソルを置いて、コンテキストメニュー \ (右クリック \) を開き、[**プロパティ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="83624-133">Hover on your project, open the context menu \(right-click\), and select **Properties**.</span></span>  
    1.  <span data-ttu-id="83624-134">[**構成プロパティ**] で、[**デバッグ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="83624-134">On **Configuration Properties**, select **Debugging**.</span></span>  
    1.  <span data-ttu-id="83624-135">[**デバッガーの種類**] プロパティで、オプションの一覧を検索し、[ **JavaScript (WebView2)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="83624-135">On the **Debugger Type** property, search the the list of options, and select **JavaScript (WebView2)**.</span></span>  
        
        :::image type="complex" source="../media/enbjs.png" alt-text="Visual Studio JavaScript デバッガー" lightbox="../media/enbjs.png":::
           <span data-ttu-id="83624-137">Visual Studio JavaScript デバッガー</span><span class="sxs-lookup"><span data-stu-id="83624-137">Visual Studio JavaScript Debugger</span></span>  
        :::image-end:::  
        
<!--todo: Please update the image to use a red rectangle to outline the portion of the screen to highlight  -->  

<span data-ttu-id="83624-138">すべての設定が完了し、デバッグする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="83624-138">You are all set up and ready to debug.</span></span>  

<span data-ttu-id="83624-139">デバッグするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="83624-139">To Debug, complete the following actions.</span></span>  

1.  <span data-ttu-id="83624-140">ブレークポイントを設定する</span><span class="sxs-lookup"><span data-stu-id="83624-140">Set Breakpoints</span></span>  
    *   <span data-ttu-id="83624-141">スクリプトファイルを開き、目的の場所にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="83624-141">Open the script file and set the breakpoint where you want it.</span></span>  
        
        > [!NOTE]
        > <span data-ttu-id="83624-142">JS/TS デバッグアダプターはソースパスマッピングを行っていません。</span><span class="sxs-lookup"><span data-stu-id="83624-142">The JS/TS debug adapter does not do source path mapping.</span></span><span data-ttu-id="83624-143">WebView2 に関連付けられているのとまったく同じパスを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="83624-143">  You must open the exact same path associated with your WebView2.</span></span>  
        
1.  <span data-ttu-id="83624-144">コードを実行する</span><span class="sxs-lookup"><span data-stu-id="83624-144">Run Code</span></span>  
    *   <span data-ttu-id="83624-145">適切なビルドのフレーバーとランタイム環境を選び、ローカル windows デバッガーを起動します。</span><span class="sxs-lookup"><span data-stu-id="83624-145">Select your appropriate build flavor and runtime environment and then start the local windows debugger.</span></span>  
1.  <span data-ttu-id="83624-146">デバッグコンソールの表示</span><span class="sxs-lookup"><span data-stu-id="83624-146">View Debug Console</span></span>  
    *   <span data-ttu-id="83624-147">アプリケーションが実行され、最初の webview2 を作成した後でデバッガーが接続されます。</span><span class="sxs-lookup"><span data-stu-id="83624-147">You application runs and the debugger connects after the first webview2 is created.</span></span><span data-ttu-id="83624-148">保留中のデバッグ出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="83624-148">  Any pending debug output is displayed.</span></span>  
        
        > [!NOTE]
        > <span data-ttu-id="83624-149">このデバッグ方法は、現在、Win32 アプリケーションと Office アドインに制限されています。</span><span class="sxs-lookup"><span data-stu-id="83624-149">This method of debugging is currently restricted to Win32 applications and Office add-ins.</span></span>  
        
## <span data-ttu-id="83624-150">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="83624-150">Visual Studio Code</span></span>  

<span data-ttu-id="83624-151">Visual Studio コードを使って、WebView2 コントロールで実行されるスクリプトをデバッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="83624-151">You may use Visual Studio Code to debug scripts that run in WebView2 controls.</span></span>  <span data-ttu-id="83624-152">詳細については、「 [Microsoft Edge (Chromium) WebView アプリケーション][GithubMicrosoftVscodeEdgeDebug2MainChromiumWebviewApplications]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83624-152">For more information, see [Microsoft Edge (Chromium) WebView Applications][GithubMicrosoftVscodeEdgeDebug2MainChromiumWebviewApplications].</span></span>  

<!--todo:  add See also heading  -->  

## <span data-ttu-id="83624-153">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="83624-153">Getting in touch with the Microsoft Edge WebView team</span></span>  

<span data-ttu-id="83624-154">フィードバックを共有して、より充実した WebView2 エクスペリエンスを構築できます。</span><span class="sxs-lookup"><span data-stu-id="83624-154">Help build a richer WebView2 experience by sharing your feedback.</span></span>  <span data-ttu-id="83624-155">[フィードバックリポジトリ][GithubMicrosoftedgeWebviewfeedback]にアクセスして、機能リクエストまたはバグレポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="83624-155">Visit the [feedback repo][GithubMicrosoftedgeWebviewfeedback] to submit feature requests or bug reports.</span></span>  

<!-- links -->  

[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[GithubMicrosoftVscodeEdgeDebug2MainChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) WebView アプリケーション-VS コード-Microsoft Edge 用デバッガー |GitHub"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  
