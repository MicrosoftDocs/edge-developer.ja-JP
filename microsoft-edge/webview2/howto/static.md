---
description: WebView2 ローダー ライブラリを静的にリンクする方法について説明します。
title: WebView2 ローダー ライブラリを静的にリンクする方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/02/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、Webview2、Webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、エッジ html
ms.openlocfilehash: 397c226eb958d1e656fb0ecb6dd8f1e2fe300746
ms.sourcegitcommit: e3cd336c9448277e0dde3b9da1521b5cbc7c44d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "11536548"
---
# <a name="statically-link-the-webview2-loader-library"></a><span data-ttu-id="1c698-104">WebView2 ローダー ライブラリを静的にリンクする</span><span class="sxs-lookup"><span data-stu-id="1c698-104">Statically link the WebView2 loader library</span></span>  

<span data-ttu-id="1c698-105">多くのファイルのパッケージではなく、1 つの実行可能ファイルでアプリケーションを配布できます。</span><span class="sxs-lookup"><span data-stu-id="1c698-105">You may want to distribute your application with a single executable file, instead of a package of many files.</span></span> <span data-ttu-id="1c698-106">単一の実行可能ファイルを作成したり、パッケージのサイズを小さくしたりするには、WebView2Loader ファイルを静的にリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c698-106">To create a single executable file, or to reduce the size of your package, you should statically link the WebView2Loader files.</span></span> <span data-ttu-id="1c698-107">WebView2 SDK には、ヘッダー ファイル、および `WebView2Loader.dll` ファイルが含 `IDL` まれています。</span><span class="sxs-lookup"><span data-stu-id="1c698-107">The WebView2 SDK contains a header file, `WebView2Loader.dll`, and the `IDL` file.</span></span> `WebView2Loader.dll` <span data-ttu-id="1c698-108">は、アプリが WebView2 ランタイム、またはデバイス上の WebView2 ランタイムの安定Microsoft Edgeを見つけるのに役立つ小さなコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="1c698-108">is a small component that helps apps locate the WebView2 Runtime, or non-stable channels of Microsoft Edge, on the device.</span></span>  

<span data-ttu-id="1c698-109">出荷しないアプリの場合は、 `WebView2Loader.dll` 次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1c698-109">For apps that don't want to ship a `WebView2Loader.dll`, complete the following steps.</span></span>  

1.  <span data-ttu-id="1c698-110">アプリの `.vcxproj` プロジェクト ファイルをテキスト エディター (テキスト エディターなど) で開Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="1c698-110">Open the `.vcxproj` project file for your app in a text editor, such as Visual Studio Code.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="1c698-111">プロジェクト `.vcproj` ファイルは非表示のファイルである可能性があります。つまり、プロジェクト ファイルは非表示Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="1c698-111">The `.vcproj` project file may be a hidden file, meaning it does not display in Visual Studio.</span></span>  <span data-ttu-id="1c698-112">コマンド ラインを使用して、隠しファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="1c698-112">Use the command-line to find hidden files.</span></span>  
    
1.  <span data-ttu-id="1c698-113">パッケージ ターゲット ファイルに WebView2 ファイルを含めるコードNuGet探します。</span><span class="sxs-lookup"><span data-stu-id="1c698-113">Locate the section in the code where you include the WebView2 NuGet package target files.</span></span>  <span data-ttu-id="1c698-114">コード内の場所は、次の図で強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="1c698-114">The location in the code is highlighted in the following figure.</span></span>  

    :::image type="complex" source="./media/inserthere.png" alt-text="Projectファイル コード スニペット" lightbox="./media/inserthere.png":::
       <span data-ttu-id="1c698-116">Projectファイル コード スニペット</span><span class="sxs-lookup"><span data-stu-id="1c698-116">Project Files code snippet</span></span>   
    :::image-end:::  
  
1.  <span data-ttu-id="1c698-117">次のコード スニペットをコピーし、含まれる場所に `Microsoft.Web.WebView2.targets` 貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="1c698-117">Copy the following code snippet and paste it where the `Microsoft.Web.WebView2.targets` is included.</span></span>  

    ```xaml
    <PropertyGroup> 
        <WebView2LoaderPreference>Static</WebView2LoaderPreference> 
    </PropertyGroup>
    ```
      
    :::image type="complex" source="./media/staticlib.png" alt-text="挿入されたコード スニペット" lightbox="./media/staticlib.png":::
       <span data-ttu-id="1c698-119">挿入されたコード スニペット</span><span class="sxs-lookup"><span data-stu-id="1c698-119">Inserted code snippet</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1c698-120">アプリのビルド構成の追加の依存関係を編集します。</span><span class="sxs-lookup"><span data-stu-id="1c698-120">Edit the additional dependencies of the build configuration for your app.</span></span>  <span data-ttu-id="1c698-121">まず、すべてのタグを検索 `<AdditionalDependencies>` します。</span><span class="sxs-lookup"><span data-stu-id="1c698-121">To begin, find all of the `<AdditionalDependencies>` tags.</span></span> <span data-ttu-id="1c698-122">それぞれに対して、 `version.lib` ファイル内のすべての異なるビルド構成に追加の依存関係として追加 `.vcxproj` します。</span><span class="sxs-lookup"><span data-stu-id="1c698-122">For each, add `version.lib` as an additional dependency to every different build configuration in the `.vcxproj` file.</span></span>  
    
    :::image type="complex" source="./media/versionlib.png" alt-text="ItemDefinitionGroups への version.lib の追加" lightbox="./media/versionlib.png":::
       <span data-ttu-id="1c698-124">に追加 `version.lib` する</span><span class="sxs-lookup"><span data-stu-id="1c698-124">Adding `version.lib` to</span></span> `ItemDefinitionGroups`  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="1c698-125">WebView2 チームは、今後のリリースで追加の依存関係の追加を自動化します。</span><span class="sxs-lookup"><span data-stu-id="1c698-125">The WebView2 team aims to automate adding the additional dependency in future releases.</span></span>  
    
1. <span data-ttu-id="1c698-126">アプリをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="1c698-126">Compile and run your app.</span></span>

### <a name="getting-in-touch-with-the-webview2-team"></a><span data-ttu-id="1c698-127">WebView2 チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="1c698-127">Getting in touch with the WebView2 team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

### <a name="see-also"></a><span data-ttu-id="1c698-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c698-128">See also</span></span>  

*   <span data-ttu-id="1c698-129">WebView2 の使用を開始するには [、「WebView2 Getting Started Guides」に移動します][Webview2MainGettingStarted]。</span><span class="sxs-lookup"><span data-stu-id="1c698-129">To get started using WebView2, navigate to [WebView2 Getting Started Guides][Webview2MainGettingStarted].</span></span>  
*   <span data-ttu-id="1c698-130">WebView2 機能の包括的な例については[、WebView2Samples][GithubMicrosoftedgeWebview2samples]に移動GitHub。</span><span class="sxs-lookup"><span data-stu-id="1c698-130">For a comprehensive example of WebView2 capabilities, navigate to [WebView2Samples][GithubMicrosoftedgeWebview2samples] on GitHub.</span></span>
*   <span data-ttu-id="1c698-131">WebView2 API の詳細については、「API リファレンス」 [に移動します][Webview2ApiReference]。</span><span class="sxs-lookup"><span data-stu-id="1c698-131">For more detailed information about WebView2 APIs, navigate to [API reference][Webview2ApiReference].</span></span>
*   <span data-ttu-id="1c698-132">WebView2 の詳細については [、「WebView2 Resources」に移動します][Webview2MainNextSteps]。</span><span class="sxs-lookup"><span data-stu-id="1c698-132">For more information about WebView2, navigate to [WebView2 Resources][Webview2MainNextSteps].</span></span>

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft EdgeWebView2 API リファレンス |Microsoft Docs"  
[Webview2MainNextSteps]: ../index.md#next-steps "次の手順 - WebView2 (プレビュー) Microsoft Edgeの概要|Microsoft Docs"  
[Webview2MainGettingStarted]: ../index.md#getting-started "はじめに - WebView2 (プレビュー) Microsoft Edgeの概要|Microsoft Docs"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック - MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  

[GithubMicrosoftVscodeJSDebugWhatsNew]: https://github.com/microsoft/vscode-js-debug#whats-new "新機能- JavaScript デバッガー Visual Studio Code - microsoft/vscode-js-debug |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) WebView アプリケーション - Visual Studio Code - デバッガー for Microsoft Edge - microsoft/vscode-edge-debug2 |GitHub"  
