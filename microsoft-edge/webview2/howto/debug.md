---
description: WebView2 コントロールをデバッグする方法について説明します。
title: WebView2 アプリケーションのデバッグを開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/13/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 15171147b847b1d41cd603efed1b8ee42185dc29
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010699"
---
# <span data-ttu-id="ba95b-104">WebView2 アプリケーションのデバッグを開始する</span><span class="sxs-lookup"><span data-stu-id="ba95b-104">Get started debugging WebView2 applications</span></span>  

<span data-ttu-id="ba95b-105">Microsoft Edge WebView2 コントロールの目標は、web とネイティブアプリケーションの両方の開発機能とツールの両方を組み合わせることです。</span><span class="sxs-lookup"><span data-stu-id="ba95b-105">The goal of the Microsoft Edge WebView2 control is to combine the best of both the web and native application development features and tools.</span></span>  <span data-ttu-id="ba95b-106">WebView2 アプリケーションを開発するときは、アプリケーションをデバッグする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba95b-106">When you develop your WebView2 application, you should debug your application.</span></span>  <span data-ttu-id="ba95b-107">この記事では、WebView2 アプリケーションで web とネイティブコードの両方をデバッグするために使用するさまざまなツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ba95b-107">This article outlines the different tools to use to debug both your web and native code in your WebView2 application.</span></span>  

## [<span data-ttu-id="ba95b-108">Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="ba95b-108">Microsoft Edge DevTools</span></span>](#tab/devtools)  

<span data-ttu-id="ba95b-109">Microsoft edge [(Chromium) 開発者ツール][DevtoolsGuideChromiumMain] を使用して、microsoft edge に表示されている別の web ページをデバッグする場合と同じ方法で、WebView2 コントロールに表示される web コンテンツをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="ba95b-109">Use [Microsoft Edge (Chromium) Developer Tools][DevtoolsGuideChromiumMain] to debug web content displayed in WebView2 controls, in the same way that you may debug for another webpage displayed in Microsoft Edge.</span></span>  <span data-ttu-id="ba95b-110">DevTools を開くには、WebView コントロールにフォーカスを設定し、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ba95b-110">To open the DevTools, set focus on the WebView control and then use one of the following actions.</span></span>  

*   <span data-ttu-id="ba95b-111">を選択し `F12` ます。</span><span class="sxs-lookup"><span data-stu-id="ba95b-111">Select `F12`.</span></span>  
*   <span data-ttu-id="ba95b-112">を選択し `Ctrl` + `Shift` + `I` ます。</span><span class="sxs-lookup"><span data-stu-id="ba95b-112">Select `Ctrl`+`Shift`+`I`.</span></span>  
*   <span data-ttu-id="ba95b-113">コンテキストメニューを開き (\ を右クリックし)、[] を選び `Inspect` ます。</span><span class="sxs-lookup"><span data-stu-id="ba95b-113">Open the context menu \(right-click\) and choose `Inspect`.</span></span>  

<span data-ttu-id="ba95b-114">詳細については、「 [Devtools の概要][DevtoolsGuideChromiumMain]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba95b-114">For more information, see [DevTools overview][DevtoolsGuideChromiumMain].</span></span>  

:::image type="complex" source="./media/f12.png" alt-text="DevTools のデバッグ" lightbox="./media/f12.png":::
   <span data-ttu-id="ba95b-116">DevTools のデバッグ</span><span class="sxs-lookup"><span data-stu-id="ba95b-116">DevTools debugging</span></span>  
:::image-end:::  

## [<span data-ttu-id="ba95b-117">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ba95b-117">Visual Studio</span></span>](#tab/visualstudio)  

<span data-ttu-id="ba95b-118">Visual Studio には、WebView2 アプリケーションの web とネイティブコード向けのさまざまなデバッグツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ba95b-118">Visual Studio provides various debugging tools for web and native code in WebView2 applications.</span></span>  <span data-ttu-id="ba95b-119">Visual Studio のセクションでは、主に WebView コントロールのデバッグがフォーカスされますが、Visual Studio でのデバッグの他の方法は通常どおり利用できます。</span><span class="sxs-lookup"><span data-stu-id="ba95b-119">In the Visual Studio section, the primarily focus is debugging WebView controls, however the other methods of debugging in Visual Studio are available as usual.</span></span>  <span data-ttu-id="ba95b-120">Win32 アプリケーションまたは Office アドインでのみ、web とネイティブコードをデバッグするには、次のプロセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="ba95b-120">Use the following process to debug web and native code in Win32 applications or Office add-ins only.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="ba95b-121">ネイティブデバッガーがアタッチされている Visual Studio でアプリケーションをデバッグする場合、を選択すると、 `F12` 開発者ツールではなくネイティブデバッガーがトリガーされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ba95b-121">When you debug your application in Visual Studio with the native debugger attached, selecting `F12` may trigger the native debugger instead of Developer Tools.</span></span>  <span data-ttu-id="ba95b-122">`Ctrl` + `Shift` + `I` または、コンテキストメニュー \ (右クリック \) を使用して、この状況を回避します。</span><span class="sxs-lookup"><span data-stu-id="ba95b-122">Select `Ctrl`+`Shift`+`I`, or use the context menu \(right-click\) to avoid the situation.</span></span>  

<span data-ttu-id="ba95b-123">作業を始める前に、次の要件が満たされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ba95b-123">Before you begin, ensure the following requirements are met.</span></span>  

*   <span data-ttu-id="ba95b-124">スクリプトをデバッグするには、Visual Studio 内からアプリを起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba95b-124">To debug scripts, the app must be launched from within Visual Studio.</span></span>  
*   <span data-ttu-id="ba95b-125">実行中の WebView2 プロセスにデバッガーをアタッチすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ba95b-125">You cannot attach a debugger to a running WebView2 process.</span></span>  
*   <span data-ttu-id="ba95b-126">Visual Studio 2019 バージョン 16.4 Preview 2 以降をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ba95b-126">Install Visual Studio 2019 version 16.4 Preview 2 or later.</span></span>  

<span data-ttu-id="ba95b-127">Visual Studio でスクリプトデバッガーツールをインストールしてセットアップします。</span><span class="sxs-lookup"><span data-stu-id="ba95b-127">Install and set up the script debugger tools in Visual Studio.</span></span>  

1.  <span data-ttu-id="ba95b-128">**C++ でデスクトップ開発**に**JavaScript 診断**コンポーネントをインストールするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ba95b-128">Complete the following actions to install the **JavaScript diagnostics** component in **Desktop development with C++**.</span></span>  

    1. <span data-ttu-id="ba95b-129">Windows エクスプローラーバーに「」と入力 `Visual Studio Installer` します。</span><span class="sxs-lookup"><span data-stu-id="ba95b-129">In the Windows Explorer bar, type `Visual Studio Installer`.</span></span>  
    1. <span data-ttu-id="ba95b-130">[ **Visual Studio インストーラー** ] を選択して開きます。</span><span class="sxs-lookup"><span data-stu-id="ba95b-130">Choose **Visual Studio Installer** to open it.</span></span>  
    1. <span data-ttu-id="ba95b-131">Visual Studio インストーラーのインストールされているバージョンで、[ **その他** ] ボタンを選択し、[ **変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ba95b-131">In the Visual Studio Installer, on the installed version, choose the **More** button, and then choose **Modify**.</span></span>  
    1. <span data-ttu-id="ba95b-132">Visual Studio の [ **ワークロード**] で、[ **デスクトップ開発** ] の [C++] の設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="ba95b-132">In Visual Studio, under **Workloads**, choose the **Desktop Development in C++** setting.</span></span>  
        
        :::image type="complex" source="./media/workloads.png" alt-text="Visual Studio のワークロードの変更画面" lightbox="./media/workloads.png":::
            <span data-ttu-id="ba95b-134">Visual Studio のワークロードの変更画面</span><span class="sxs-lookup"><span data-stu-id="ba95b-134">Visual Studio Modifying Workloads Screen</span></span> :::image-end:::  
        
    1.  <span data-ttu-id="ba95b-135">**個々のコンポーネント**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ba95b-135">Choose **Individual components**.</span></span>  
    1.  <span data-ttu-id="ba95b-136">検索ボックスに「」と入力し `JavaScript diagnostics` ます。</span><span class="sxs-lookup"><span data-stu-id="ba95b-136">In the search box, enter `JavaScript diagnostics`.</span></span>  
    1.  <span data-ttu-id="ba95b-137">**JavaScript 診断**設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="ba95b-137">Choose the **JavaScript diagnostics** setting.</span></span>  
    1.  <span data-ttu-id="ba95b-138">[ **Modify**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ba95b-138">Choose **Modify**.</span></span> 
        
        :::image type="complex" source="./media/indivcomp.png" alt-text="Visual Studio による個々のコンポーネントの変更のタブ" lightbox="./media/indivcomp.png":::
           <span data-ttu-id="ba95b-140">Visual Studio による個々のコンポーネントの変更のタブ</span><span class="sxs-lookup"><span data-stu-id="ba95b-140">Visual Studio Modifying Individual Components Tab</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="ba95b-141">WebView2 アプリケーションのスクリプトのデバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ba95b-141">Enable script debugging for WebView2 applications.</span></span>  
    1.  <span data-ttu-id="ba95b-142">WebView2 プロジェクトで、コンテキストメニュー \ を右クリックし、[ **プロパティ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ba95b-142">In your WebView2 project, open the context menu \(right-click\), and choose **Properties**.</span></span>  
    1.  <span data-ttu-id="ba95b-143">[ **構成プロパティ**] で、[ **デバッグ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ba95b-143">Under the **Configuration Properties**, choose **Debugging**.</span></span>  
    1.  <span data-ttu-id="ba95b-144">[ **デバッガーの種類**] で、[ **JavaScript (WebView2)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ba95b-144">Under the **Debugger Type**, choose **JavaScript (WebView2)**.</span></span>  
        
        :::image type="complex" source="./media/enbjs.png" alt-text="Visual Studio のデバッグ構成プロパティ" lightbox="./media/enbjs.png":::
           <span data-ttu-id="ba95b-146">Visual Studio の **デバッグ** 構成プロパティ</span><span class="sxs-lookup"><span data-stu-id="ba95b-146">Visual Studio **Debugging** Configuration Property</span></span>  
        :::image-end:::  
        
<span data-ttu-id="ba95b-147">WebView2 アプリケーションをデバッグするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ba95b-147">Complete the following actions to debug your WebView2 application.</span></span>  

1.  <span data-ttu-id="ba95b-148">ソースコードにブレークポイントを設定するには、行番号の左側にカーソルを置いて、[ブレークポイントの設定] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ba95b-148">To set a breakpoint in your source code, hover to the left of the line number, and choose to set a breakpoint.</span></span>  <span data-ttu-id="ba95b-149">JS/TS デバッグアダプターはソースパスマッピングを実行しません。</span><span class="sxs-lookup"><span data-stu-id="ba95b-149">The JS/TS debug adapter does not perform source path mapping.</span></span>  <span data-ttu-id="ba95b-150">WebView2 に関連付けられているのとまったく同じパスを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba95b-150">You must open the exact same path associated with your WebView2.</span></span>  
    
    :::image type="complex" source="./media/breakpoint.png" alt-text="Visual Studio のブレークポイントの追加" lightbox="./media/breakpoint.png"::: 
       <span data-ttu-id="ba95b-152">Visual Studio のブレークポイントの追加</span><span class="sxs-lookup"><span data-stu-id="ba95b-152">Visual Studio add breakpoint</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ba95b-153">デバッガーを実行するには、プラットフォームのビットサイズを選択し、[ **ローカル Windows デバッガー**] の横にある緑色の [再生] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="ba95b-153">To run the debugger, choose the bit size of the platform, and then choose the green play button next to **Local Windows Debugger**.</span></span>  <span data-ttu-id="ba95b-154">アプリケーションが実行され、作成された最初の WebView2 プロセスにデバッガーが接続されます。</span><span class="sxs-lookup"><span data-stu-id="ba95b-154">The application runs and the debugger connects to the first WebView2 process that is created.</span></span>  
    
    :::image type="complex" source="./media/run.png" alt-text=" Visual Studio のローカル Windows デバッガー" lightbox="./media/run.png"::: 
       <span data-ttu-id="ba95b-156">Visual Studio の **ローカル Windows デバッガー**</span><span class="sxs-lookup"><span data-stu-id="ba95b-156">Visual Studio **Local Windows Debugger**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ba95b-157">**デバッグコンソール**でデバッガーからの出力を見つけます。</span><span class="sxs-lookup"><span data-stu-id="ba95b-157">In the **Debug Console**, find the output from the debugger.</span></span>  
    
    :::image type="complex" source="./media/console.png" alt-text=" Visual Studio のデバッグコンソール" lightbox="./media/console.png"::: 
       <span data-ttu-id="ba95b-159">Visual Studio の **デバッグコンソール**</span><span class="sxs-lookup"><span data-stu-id="ba95b-159">Visual Studio **Debug Console**</span></span>  
    :::image-end:::  
    
* * *  

## <span data-ttu-id="ba95b-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba95b-160">See also</span></span>  

*   <span data-ttu-id="ba95b-161">WebView2 の使用を開始するには、 [WebView2 の概要ガイド][Webview2MainGettingStarted]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba95b-161">To get started using WebView2, see [WebView2 Getting Started Guides][Webview2MainGettingStarted].</span></span>  
*   <span data-ttu-id="ba95b-162">WebView2 機能の包括的な例については、GitHub の [WebView2Samples][GithubMicrosoftedgeWebview2samples] リポジトリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba95b-162">For a comprehensive example of WebView2 capabilities, see the [WebView2Samples][GithubMicrosoftedgeWebview2samples] repo on GitHub.</span></span>
*   <span data-ttu-id="ba95b-163">WebView2 Api について詳しくは、 [api リファレンス][Webview2ApiReference]をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ba95b-163">For more detailed information about WebView2 APIs, see [API reference][Webview2ApiReference].</span></span>
*   <span data-ttu-id="ba95b-164">WebView2 の詳細については、「 [WebView2 のリソース][Webview2MainNextSteps]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba95b-164">For more information about WebView2, see [WebView2 Resources][Webview2MainNextSteps].</span></span>

## <span data-ttu-id="ba95b-165">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="ba95b-165">Getting in touch with the Microsoft Edge WebView team</span></span>  

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
