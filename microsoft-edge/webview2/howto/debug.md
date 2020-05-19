---
description: WebView2 コントロールをデバッグする方法について説明します。
title: デバッグ WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/19/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 386bc237257be0ade8c48bc1c737b0151a882719
ms.sourcegitcommit: 5bdffe91a6594f77eeffa4e864fda90a02784771
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "10659708"
---
# <span data-ttu-id="57e4a-104">WebView2 コントロールを使用して開発を行うときのデバッグ方法</span><span class="sxs-lookup"><span data-stu-id="57e4a-104">How to Debug when developing with WebView2 controls</span></span>  

<span data-ttu-id="57e4a-105">Microsoft Edge WebView2 コントロールの目標は、web とネイティブアプリケーションの開発機能と開発者ツールの両方の最良の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="57e4a-105">The goal of the Microsoft Edge WebView2 control is combining the best of both the web and native application development features and developer tools.</span></span>  <span data-ttu-id="57e4a-106">この記事では、WebView2 コントロールを使用して開発するときに使用するさまざまなツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="57e4a-106">This article outlines the different tools to use when developing with WebView2 controls.</span></span>  

## <span data-ttu-id="57e4a-107">Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="57e4a-107">Microsoft Edge DevTools</span></span>  

<span data-ttu-id="57e4a-108">Microsoft edge [(Chromium) 開発者ツール](/microsoft-edge/devtools-guide-chromium)を使用して、microsoft edge を使用している場合と同じように、WebView2 コントロールに表示される web コンテンツをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="57e4a-108">Use [Microsoft Edge (Chromium) Developer Tools](/microsoft-edge/devtools-guide-chromium) to debug web content displayed in WebView2 controls, in the same way that you would if you were using Microsoft Edge.</span></span>  <span data-ttu-id="57e4a-109">DevTools を開くには、[WebView] ウィンドウにフォーカスを設定し、次のいずれかのオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="57e4a-109">To open the DevTools, set focus on the WebView window and then use any of the following options.</span></span>  
*   <span data-ttu-id="57e4a-110">を選択し `F12` ます。</span><span class="sxs-lookup"><span data-stu-id="57e4a-110">Select `F12`.</span></span>  
*   <span data-ttu-id="57e4a-111">を選択し `Ctrl` + `Shift` + `I` ます。</span><span class="sxs-lookup"><span data-stu-id="57e4a-111">Select `Ctrl`+`Shift`+`I`.</span></span>  
*   <span data-ttu-id="57e4a-112">コンテキストメニューを開く (\ 右クリック \) > 選択] をクリック `Inspect` します。</span><span class="sxs-lookup"><span data-stu-id="57e4a-112">Open the context menu \(right-click\) > select `Inspect`.</span></span>  

:::image type="complex" source="../media/f12.png" alt-text="Microsoft Edge DevTools":::
   <span data-ttu-id="57e4a-114">Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="57e4a-114">Microsoft Edge DevTools</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="57e4a-115">ネイティブデバッガーがアタッチされている Visual Studio でアプリケーションをデバッグする場合、を選択すると、 `F12` 開発者ツールではなくネイティブデバッガーがトリガーされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="57e4a-115">When you debug your application in Visual Studio with the native debugger attached, selecting `F12` may trigger the native debugger instead of Developer Tools.</span></span>  <span data-ttu-id="57e4a-116">`Ctrl` + `Shift` + `I` この問題を回避するには、コンテキストメニュー \ (右クリック \) を使用します。</span><span class="sxs-lookup"><span data-stu-id="57e4a-116">Use `Ctrl`+`Shift`+`I`, or use the context menu \(right-click\) to avoid this situation.</span></span>  

## <span data-ttu-id="57e4a-117">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="57e4a-117">Visual Studio</span></span>  

<span data-ttu-id="57e4a-118">Visual studio 2019 バージョン 16.4 Preview 2 以降のスクリプトデバッガーを使って、Visual Studio でスクリプトをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="57e4a-118">Use the script debugger in Visual Studio 2019 version 16.4 Preview 2 or later to debug your script in Visual Studio.</span></span>  <span data-ttu-id="57e4a-119">C++ のワークロードを使用して、**デスクトップ開発**の**JavaScript 診断**コンポーネントを確認します。</span><span class="sxs-lookup"><span data-stu-id="57e4a-119">Verify the **JavaScript diagnostics** component in **Desktop development with C++** workload is installed.</span></span>  

:::image type="complex" source="../media/vs-js-diagnostics.jpg" alt-text="Visual Studio JavaScript 診断ツール":::
   <span data-ttu-id="57e4a-121">Visual Studio JavaScript 診断ツール</span><span class="sxs-lookup"><span data-stu-id="57e4a-121">Visual Studio JavaScript diagnostics</span></span>  
:::image-end:::  

<!--todo: Please update the image to use a red rectangle to outline the portion of the screen to highlight  -->  

<span data-ttu-id="57e4a-122">WebView2 スクリプトのデバッグを有効にするには、プロジェクトのコンテキストメニュー \ (右クリック \) を開いて、[**プロパティ**] > 選びます。</span><span class="sxs-lookup"><span data-stu-id="57e4a-122">To enable WebView2 script debugging, open the context menu \(right-click\) on your project > select **Properties**.</span></span>  <span data-ttu-id="57e4a-123">[**構成プロパティ**] で、[**デバッグ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="57e4a-123">On **Configuration Properties**, select **Debugging**.</span></span>  <span data-ttu-id="57e4a-124">[**デバッガーの種類**] プロパティで、オプションの一覧から [ **JavaScript (WebView2)** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="57e4a-124">On the **Debugger Type** property, choose **JavaScript (WebView2)** from the list of options.</span></span> 

:::image type="complex" source="../media/vs-script-debugger.jpg" alt-text="Visual Studio JavaScript デバッガー":::
   <span data-ttu-id="57e4a-126">Visual Studio JavaScript デバッガー</span><span class="sxs-lookup"><span data-stu-id="57e4a-126">Visual Studio JavaScript Debugger</span></span>  
:::image-end:::  

<!--todo: Please update the image to use a red rectangle to outline the portion of the screen to highlight  -->  

## <span data-ttu-id="57e4a-127">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="57e4a-127">Visual Studio Code</span></span>  

<span data-ttu-id="57e4a-128">Visual Studio コードを使って、WebView2 コントロールで実行されるスクリプトをデバッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="57e4a-128">You may use Visual Studio Code to debug scripts that run in WebView2 controls.</span></span>  <span data-ttu-id="57e4a-129">詳細については、「 [Microsoft Edge (Chromium) WebView アプリケーション](https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57e4a-129">For more information, see [Microsoft Edge (Chromium) WebView Applications](https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications).</span></span>  

<!--todo:  add See also heading  -->  

## <span data-ttu-id="57e4a-130">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="57e4a-130">Getting in touch with the Microsoft Edge WebView team</span></span>  

<span data-ttu-id="57e4a-131">フィードバックを共有して、より充実した WebView2 エクスペリエンスを構築できます。</span><span class="sxs-lookup"><span data-stu-id="57e4a-131">Help build a richer WebView2 experience by sharing your feedback.</span></span>  <span data-ttu-id="57e4a-132">[フィードバックリポジトリ](https://aka.ms/webviewfeedback)にアクセスして、機能リクエストまたはバグレポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="57e4a-132">Visit the [feedback repo](https://aka.ms/webviewfeedback) to submit feature requests or bug reports.</span></span>  
