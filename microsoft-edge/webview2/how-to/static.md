---
description: WebView2 ローダー ライブラリを静的にリンクする方法について説明します。
title: WebView2 ローダー ライブラリを静的にリンクする方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、Webview2、Webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、エッジ html
ms.openlocfilehash: 8f48a4fde9e2960de6156fc14db8c84f87a49868
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "11536031"
---
# <a name="statically-link-the-webview2-loader-library"></a><span data-ttu-id="1935e-104">WebView2 ローダー ライブラリを静的にリンクする</span><span class="sxs-lookup"><span data-stu-id="1935e-104">Statically link the WebView2 loader library</span></span>  

<span data-ttu-id="1935e-105">多くのファイルのパッケージではなく、1 つの実行可能ファイルでアプリケーションを配布できます。</span><span class="sxs-lookup"><span data-stu-id="1935e-105">You may want to distribute your application with a single executable file, instead of a package of many files.</span></span> <span data-ttu-id="1935e-106">単一の実行可能ファイルを作成したり、パッケージのサイズを小さくしたりするには、WebView2Loader ファイルを静的にリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1935e-106">To create a single executable file, or to reduce the size of your package, you should statically link the WebView2Loader files.</span></span> <span data-ttu-id="1935e-107">WebView2 SDK には、ヘッダー ファイル、および `WebView2Loader.dll` ファイルが含 `IDL` まれています。</span><span class="sxs-lookup"><span data-stu-id="1935e-107">The WebView2 SDK contains a header file, `WebView2Loader.dll`, and the `IDL` file.</span></span> `WebView2Loader.dll` <span data-ttu-id="1935e-108">は、アプリがデバイス上の WebView2 ランタイム(または Microsoft Edge の安定しないチャネル)を見つけるのに役立つ小さなコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="1935e-108">is a small component that helps apps locate the WebView2 Runtime, or non-stable channels of Microsoft Edge, on the device.</span></span>  

<span data-ttu-id="1935e-109">出荷しないアプリの場合は、 `WebView2Loader.dll` 次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1935e-109">For apps that don't want to ship a `WebView2Loader.dll`, complete the following steps.</span></span>  

1.  <span data-ttu-id="1935e-110">アプリの `.vcxproj` プロジェクト ファイルをテキスト エディター (コードなど) でVisual Studioします。</span><span class="sxs-lookup"><span data-stu-id="1935e-110">Open the `.vcxproj` project file for your app in a text editor, such as Visual Studio Code.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="1935e-111">プロジェクト `.vcproj` ファイルは非表示のファイルである可能性があります。つまり、プロジェクト ファイルは非表示のファイルVisual Studio。</span><span class="sxs-lookup"><span data-stu-id="1935e-111">The `.vcproj` project file may be a hidden file, meaning it does not display in Visual Studio.</span></span>  <span data-ttu-id="1935e-112">コマンド ラインを使用して、隠しファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="1935e-112">Use the command-line to find hidden files.</span></span>  
    
1.  <span data-ttu-id="1935e-113">WebView2 NuGet パッケージ ターゲット ファイルを含めるコード内のセクションを探します。</span><span class="sxs-lookup"><span data-stu-id="1935e-113">Locate the section in the code where you include the WebView2 NuGet package target files.</span></span>  <span data-ttu-id="1935e-114">コード内の場所は、次の図で強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="1935e-114">The location in the code is highlighted in the following figure.</span></span>  
    
    :::image type="complex" source="./media/insert-here.png" alt-text="Project Files コード スニペット" lightbox="./media/insert-here.png":::
       <span data-ttu-id="1935e-116">Project Files コード スニペット</span><span class="sxs-lookup"><span data-stu-id="1935e-116">Project Files code snippet</span></span>   
    :::image-end:::  
    
1.  <span data-ttu-id="1935e-117">次のコード スニペットをコピーし、含まれる場所に `Microsoft.Web.WebView2.targets` 貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="1935e-117">Copy the following code snippet and paste it where the `Microsoft.Web.WebView2.targets` is included.</span></span>  
    
    ```xaml
    <PropertyGroup> 
        <WebView2LoaderPreference>Static</WebView2LoaderPreference> 
    </PropertyGroup>
    ```  
    
    :::image type="complex" source="./media/static-lib.png" alt-text="挿入されたコード スニペット" lightbox="./media/static-lib.png":::
       <span data-ttu-id="1935e-119">挿入されたコード スニペット</span><span class="sxs-lookup"><span data-stu-id="1935e-119">Inserted code snippet</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1935e-120">アプリのビルド構成の追加の依存関係を編集します。</span><span class="sxs-lookup"><span data-stu-id="1935e-120">Edit the additional dependencies of the build configuration for your app.</span></span>  <span data-ttu-id="1935e-121">まず、すべてのタグを検索 `<AdditionalDependencies>` します。</span><span class="sxs-lookup"><span data-stu-id="1935e-121">To begin, find all of the `<AdditionalDependencies>` tags.</span></span> <span data-ttu-id="1935e-122">それぞれに対して、 `version.lib` ファイル内のすべての異なるビルド構成に追加の依存関係として追加 `.vcxproj` します。</span><span class="sxs-lookup"><span data-stu-id="1935e-122">For each, add `version.lib` as an additional dependency to every different build configuration in the `.vcxproj` file.</span></span>  
    
    :::image type="complex" source="./media/version-lib.png" alt-text="ItemDefinitionGroups への version.lib の追加" lightbox="./media/version-lib.png":::
       <span data-ttu-id="1935e-124">に追加 `version.lib` する</span><span class="sxs-lookup"><span data-stu-id="1935e-124">Adding `version.lib` to</span></span> `ItemDefinitionGroups`  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="1935e-125">WebView2 チームは、今後のリリースで追加の依存関係の追加を自動化します。</span><span class="sxs-lookup"><span data-stu-id="1935e-125">The WebView2 team aims to automate adding the additional dependency in future releases.</span></span>  
    
1.  <span data-ttu-id="1935e-126">アプリをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="1935e-126">Compile and run your app.</span></span>  
    
## <a name="getting-in-touch-with-the-webview2-team"></a><span data-ttu-id="1935e-127">WebView2 チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="1935e-127">Getting in touch with the WebView2 team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

## <a name="see-also"></a><span data-ttu-id="1935e-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="1935e-128">See also</span></span>  

*   <span data-ttu-id="1935e-129">WebView2 の使用を開始するには [、[WebView2 スタートガイド] に移動します][Webview2MainGetStarted]。</span><span class="sxs-lookup"><span data-stu-id="1935e-129">To get started using WebView2, navigate to [WebView2 Get Started Guides][Webview2MainGetStarted].</span></span>  
*   <span data-ttu-id="1935e-130">WebView2 機能の包括的な例については [、GitHub の WebView2Samples][GithubMicrosoftedgeWebview2samples] に移動します。</span><span class="sxs-lookup"><span data-stu-id="1935e-130">For a comprehensive example of WebView2 capabilities, navigate to [WebView2Samples][GithubMicrosoftedgeWebview2samples] on GitHub.</span></span>
*   <span data-ttu-id="1935e-131">WebView2 API の詳細については、「API リファレンス」 [に移動します][Webview2ApiReference]。</span><span class="sxs-lookup"><span data-stu-id="1935e-131">For more detailed information about WebView2 APIs, navigate to [API reference][Webview2ApiReference].</span></span>
*   <span data-ttu-id="1935e-132">WebView2 の詳細については [、「WebView2 Resources」に移動します][Webview2MainNextSteps]。</span><span class="sxs-lookup"><span data-stu-id="1935e-132">For more information about WebView2, navigate to [WebView2 Resources][Webview2MainNextSteps].</span></span>
    
<!-- links -->  

[DevtoolsGuideChromiumMain]: ../index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API リファレンス |Microsoft Docs"  
[Webview2MainNextSteps]: ../index.md#next-steps "次の手順 - Microsoft Edge WebView2 (プレビュー) の概要|Microsoft Docs"  
[Webview2MainGetStarted]: ../index.md#get-started "はじめに - Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft Docs"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック - MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  

[GithubMicrosoftVscodeJSDebugWhatsNew]: https://github.com/microsoft/vscode-js-debug#whats-new "新機能- JavaScript デバッガー Visual Studioコード - microsoft/vscode-js-debug |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (クロム) WebView アプリケーション - Visual Studio コード - デバッガー for Microsoft Edge - microsoft/vscode-edge-debug2 |GitHub"  
