---
description: WebView2 loader ライブラリを静的にリンクする方法について説明します。
title: WebView2 loader ライブラリを静的にリンクする方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/15/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 880e9ed809dc268ee0b30b6ee3b5996711f54300
ms.sourcegitcommit: 0ded671914aae231493f418dd7645a04361dca1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "11120125"
---
# <span data-ttu-id="8913b-104">WebView2 loader ライブラリの静的なリンク</span><span class="sxs-lookup"><span data-stu-id="8913b-104">Statically link the WebView2 loader library</span></span>  

<span data-ttu-id="8913b-105">多数のファイルのパッケージではなく、1つの実行可能ファイルを使用してアプリケーションを配布することもできます。</span><span class="sxs-lookup"><span data-stu-id="8913b-105">You may want to distribute your application with a single executable file, instead of a package of many files.</span></span> <span data-ttu-id="8913b-106">1つの実行可能ファイルを作成するか、パッケージのサイズを小さくするには、WebView2Loader ファイルを静的にリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8913b-106">To create a single executable file, or to reduce the size of your package, you should statically link the WebView2Loader files.</span></span> <span data-ttu-id="8913b-107">WebView2 SDK には、ヘッダーファイルとファイルが含まれてい `WebView2Loader.dll` `IDL` ます。</span><span class="sxs-lookup"><span data-stu-id="8913b-107">The WebView2 SDK contains a header file, `WebView2Loader.dll`, and the `IDL` file.</span></span> `WebView2Loader.dll` <span data-ttu-id="8913b-108">は、デバイス上の WebView2 Runtime、または Microsoft Edge の非永続的なチャネルをアプリが見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8913b-108">is a small component that helps apps locate the WebView2 Runtime, or non-stable channels of Microsoft Edge, on the device.</span></span>  

<span data-ttu-id="8913b-109">を出荷したくないアプリの `WebView2Loader.dll` 場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8913b-109">For apps that don't want to ship a `WebView2Loader.dll`, complete the following steps.</span></span>  

1.  <span data-ttu-id="8913b-110">`.vcxproj`Visual Studio コードなどのテキストエディターでアプリのプロジェクトファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="8913b-110">Open the `.vcxproj` project file for your app in a text editor, such as Visual Studio Code.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="8913b-111">`.vcproj`プロジェクトファイルは非表示のファイルである可能性があります。これは Visual Studio では表示されません。</span><span class="sxs-lookup"><span data-stu-id="8913b-111">The `.vcproj` project file may be a hidden file, meaning it does not display in Visual Studio.</span></span>  <span data-ttu-id="8913b-112">コマンドラインを使用して、非表示のファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="8913b-112">Use the command-line to find hidden files.</span></span>  
    
1.  <span data-ttu-id="8913b-113">WebView2 NuGet パッケージターゲットファイルが含まれているコードのセクションを見つけます。</span><span class="sxs-lookup"><span data-stu-id="8913b-113">Locate the section in the code where you include the WebView2 NuGet package target files.</span></span>  <span data-ttu-id="8913b-114">次の図では、コード内の場所が強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="8913b-114">The location in the code is highlighted in the following figure.</span></span>  

    :::image type="complex" source="./media/inserthere.png" alt-text="プロジェクトファイルのコードスニペット" lightbox="./media/inserthere.png":::
       <span data-ttu-id="8913b-116">プロジェクトファイルのコードスニペット</span><span class="sxs-lookup"><span data-stu-id="8913b-116">Project Files code snippet</span></span>   
    :::image-end:::  
  
1.  <span data-ttu-id="8913b-117">次のコードスニペットをコピーして、が含まれている場所に貼り付け `Microsoft.Web.WebView2.targets` ます。</span><span class="sxs-lookup"><span data-stu-id="8913b-117">Copy the following code snippet and paste it where the `Microsoft.Web.WebView2.targets` is included.</span></span>  

    ```xaml
    <PropertyGroup> 
        <WebView2LoaderPreference>Static</WebView2LoaderPreference> 
    </PropertyGroup>
    ```
      
    :::image type="complex" source="./media/staticlib.png" alt-text="プロジェクトファイルのコードスニペット" lightbox="./media/staticlib.png":::
       <span data-ttu-id="8913b-119">挿入されたコードスニペット</span><span class="sxs-lookup"><span data-stu-id="8913b-119">Inserted code snippet</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8913b-120">アプリのビルド構成のその他の依存関係を編集します。</span><span class="sxs-lookup"><span data-stu-id="8913b-120">Edit the additional dependencies of the build configuration for your app.</span></span>  <span data-ttu-id="8913b-121">まず、すべてのタグを確認し `<AdditionalDependencies>` ます。</span><span class="sxs-lookup"><span data-stu-id="8913b-121">To begin, find all of the `<AdditionalDependencies>` tags.</span></span> <span data-ttu-id="8913b-122">それぞれについて、 `version.lib` ファイル内のすべての異なるビルド構成に対して、追加の依存関係として追加し `.vcxproj` ます。</span><span class="sxs-lookup"><span data-stu-id="8913b-122">For each, add `version.lib` as an additional dependency to every different build configuration in the `.vcxproj` file.</span></span>  
    
    :::image type="complex" source="./media/versionlib.png" alt-text="プロジェクトファイルのコードスニペット" lightbox="./media/versionlib.png":::
       <span data-ttu-id="8913b-124">追加 `version.lib` 先</span><span class="sxs-lookup"><span data-stu-id="8913b-124">Adding `version.lib` to</span></span> `ItemDefinitionGroups`  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="8913b-125">WebView2 チームは、今後のリリースで追加の依存関係を自動的に追加することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="8913b-125">The WebView2 team aims to automate adding the additional dependency in future releases.</span></span>  
    
1. <span data-ttu-id="8913b-126">アプリをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="8913b-126">Compile and run your app.</span></span>

### <span data-ttu-id="8913b-127">WebView2 チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="8913b-127">Getting in touch with the WebView2 team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

### <span data-ttu-id="8913b-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="8913b-128">See also</span></span>  

*   <span data-ttu-id="8913b-129">WebView2 の使用を開始するには、 [WebView2 の概要ガイド][Webview2MainGettingStarted]に移動します。</span><span class="sxs-lookup"><span data-stu-id="8913b-129">To get started using WebView2, navigate to [WebView2 Getting Started Guides][Webview2MainGettingStarted].</span></span>  
*   <span data-ttu-id="8913b-130">WebView2 機能の包括的な例については、GitHub on [WebView2Samples][GithubMicrosoftedgeWebview2samples] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8913b-130">For a comprehensive example of WebView2 capabilities, navigate to [WebView2Samples][GithubMicrosoftedgeWebview2samples] on GitHub.</span></span>
*   <span data-ttu-id="8913b-131">WebView2 Api の詳細については、 [api リファレンス][Webview2ApiReference]に移動してください。</span><span class="sxs-lookup"><span data-stu-id="8913b-131">For more detailed information about WebView2 APIs, navigate to [API reference][Webview2ApiReference].</span></span>
*   <span data-ttu-id="8913b-132">WebView2 の詳細については、 [WebView2 リソース][Webview2MainNextSteps]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8913b-132">For more information about WebView2, navigate to [WebView2 Resources][Webview2MainNextSteps].</span></span>

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API リファレンス |Microsoft ドキュメント"  
[Webview2MainNextSteps]: ../index.md#next-steps "次の手順-Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  
[Webview2MainGettingStarted]: ../index.md#getting-started "はじめに-Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftVscodeJSDebugWhatsNew]: https://github.com/microsoft/vscode-js-debug#whats-new "新機能-Visual Studio コードの JavaScript デバッガー-microsoft/vscode-js-debug |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) WebView アプリケーション-Visual Studio Code-Microsoft Edge 用デバッガー-microsoft/vscode-edge-debug2 |GitHub"  
