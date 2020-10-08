---
description: WebView2 loader ライブラリを静的にリンクする方法について説明します。
title: WebView2 loader ライブラリを静的にリンクする方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/01/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: b7e0ec70cb00f318d4eb67254f37fcec79a5fcf6
ms.sourcegitcommit: 903524ab85321ade278facd741d6487e8cabe33f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "11100312"
---
# <span data-ttu-id="5a95c-104">WebView2 loader ライブラリを静的にリンクする方法</span><span class="sxs-lookup"><span data-stu-id="5a95c-104">How to Statically link the WebView2 loader library</span></span>  

## <span data-ttu-id="5a95c-105">コンテキスト</span><span class="sxs-lookup"><span data-stu-id="5a95c-105">Context</span></span>  

<span data-ttu-id="5a95c-106">WebView2Loader.dll とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="5a95c-106">What is the WebView2Loader.dll?</span></span>  

*   <span data-ttu-id="5a95c-107">WebView2 SDK には、ヘッダーファイルとファイルが含まれてい `WebView2Loader.dll.` `IDL` ます。</span><span class="sxs-lookup"><span data-stu-id="5a95c-107">The WebView2 SDK contains a header file, `WebView2Loader.dll.`, and the `IDL` file.</span></span> `WebView2Loader.dll` <span data-ttu-id="5a95c-108">は、アプリがデバイス上の WebView2 Runtime (または非永続的な Microsoft Edge チャネル) を見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5a95c-108">is a small component that helps apps locate the WebView2 Runtime (or non-stable Microsoft Edge channels) on the device.</span></span>  

<span data-ttu-id="5a95c-109">1つのランタイムを備えたアプリについては、次の手順を `WebView2Loader.dll` 実行し**Procedure**ます。</span><span class="sxs-lookup"><span data-stu-id="5a95c-109">For apps that have a single runtime, and do not want to ship a `WebView2Loader.dll`, complete the following **Procedure** steps.</span></span>  

## <span data-ttu-id="5a95c-110">手順</span><span class="sxs-lookup"><span data-stu-id="5a95c-110">Procedure</span></span>  

1.  <span data-ttu-id="5a95c-111">`.vcxproj`Visual Studio コードなどのテキストエディターでアプリのプロジェクトファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5a95c-111">Open the `.vcxproj` project file for your app in a text editor, such as Visual Studio Code.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="5a95c-112">`.vcproj`プロジェクトファイルは非表示のファイルである可能性があります。これは Visual Studio では表示されません。</span><span class="sxs-lookup"><span data-stu-id="5a95c-112">The `.vcproj` project file may be a hidden file, meaning it does not display in Visual Studio.</span></span>  <span data-ttu-id="5a95c-113">コマンドラインを使用して、非表示のファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="5a95c-113">Use the command-line to find a hidden file.</span></span>  
    
1.  <span data-ttu-id="5a95c-114">WebView2 NuGet パッケージターゲットファイルが含まれているコードのセクションを見つけます。</span><span class="sxs-lookup"><span data-stu-id="5a95c-114">Locate the section in the code where you include the WebView2 NuGet package target files.</span></span>  <span data-ttu-id="5a95c-115">次の図では、コード内の場所が強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="5a95c-115">The location in the code is highlighted in the following figure.</span></span>  
    
    :::image type="complex" source="./media/inserthere.png" alt-text="プロジェクトファイルのコードスニペット" lightbox="./media/inserthere.png"::: 
       <span data-ttu-id="5a95c-117">プロジェクトファイルのコードスニペット</span><span class="sxs-lookup"><span data-stu-id="5a95c-117">Project Files code snippet</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="5a95c-118">次のコードスニペットをコピーして、が含まれている場所に貼り付け `Microsoft.Web.WebView2.targets` ます。</span><span class="sxs-lookup"><span data-stu-id="5a95c-118">Copy the following code snippet and paste it everywhere the `Microsoft.Web.WebView2.targets` is included.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="5a95c-119">たとえば、次のコードブロックの後に追加します。</span><span class="sxs-lookup"><span data-stu-id="5a95c-119">For example, include it after the following code block.</span></span>  
    > 
    > ```csharp
    > <Import Project="..\packages\Microsoft.Web.WebView2.0.9.579-prerelease\build\native\Microsoft.Web.WebView2.targets" Condition="Exists('..\packages\Microsoft.Web.WebView2.0.9.579-prerelease\build\native\Microsoft.Web.WebView2.targets')" />
    > ```  
    
    ```csharp
    <PropertyGroup> <WebView2LoaderPreference>Static</WebView2LoaderPreference> </PropertyGroup>
    ```
    
    :::image type="complex" source="./media/staticlib.png" alt-text="プロジェクトファイルのコードスニペット" lightbox="./media/staticlib.png"::: 
       <span data-ttu-id="5a95c-121">挿入されたコードスニペット</span><span class="sxs-lookup"><span data-stu-id="5a95c-121">Inserted code snippet</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="5a95c-122">アプリのビルド構成のその他の依存関係を編集します。</span><span class="sxs-lookup"><span data-stu-id="5a95c-122">Edit the additional dependencies of the build configuration for your app.</span></span>  <span data-ttu-id="5a95c-123">まず、すべてのタグを確認し `<AdditionalDependencies>` ます。</span><span class="sxs-lookup"><span data-stu-id="5a95c-123">To begin, find all of the `<AdditionalDependencies>` tags.</span></span>  
1.  <span data-ttu-id="5a95c-124">`version.lib`アプリのファイル内のすべてのビルド構成に、追加の依存関係として追加し `.vcxproj` ます。</span><span class="sxs-lookup"><span data-stu-id="5a95c-124">Add `version.lib` as an additional dependency to every different build configuration in the `.vcxproj` file for your app.</span></span>  
    
    :::image type="complex" source="./media/versionlib.png" alt-text="プロジェクトファイルのコードスニペット" lightbox="./media/versionlib.png"::: 
       <span data-ttu-id="5a95c-126">追加 `version.lib` 先</span><span class="sxs-lookup"><span data-stu-id="5a95c-126">Adding `version.lib` to</span></span> `ItemDefinitionGroups`  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="5a95c-127">WebView2 チームは、今後のリリースで追加の依存関係の手順を自動化することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="5a95c-127">The WebView2 team aims to automate the additional dependency step in future releases.</span></span>  
    
<span data-ttu-id="5a95c-128">アプリをコンパイルして展開します。</span><span class="sxs-lookup"><span data-stu-id="5a95c-128">Compile and deploy your app.</span></span>  <span data-ttu-id="5a95c-129">正しい.</span><span class="sxs-lookup"><span data-stu-id="5a95c-129">Success.</span></span>  

## <span data-ttu-id="5a95c-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a95c-130">See also</span></span>  

*   <span data-ttu-id="5a95c-131">WebView2 の使用を開始するには、 [WebView2 の概要ガイド][Webview2MainGettingStarted]に移動します。</span><span class="sxs-lookup"><span data-stu-id="5a95c-131">To get started using WebView2, navigate to [WebView2 Getting Started Guides][Webview2MainGettingStarted].</span></span>  
*   <span data-ttu-id="5a95c-132">WebView2 機能の包括的な例については、GitHub on [WebView2Samples][GithubMicrosoftedgeWebview2samples] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a95c-132">For a comprehensive example of WebView2 capabilities, navigate to [WebView2Samples][GithubMicrosoftedgeWebview2samples] on GitHub.</span></span>
*   <span data-ttu-id="5a95c-133">WebView2 Api の詳細については、 [api リファレンス][Webview2ApiReference]に移動してください。</span><span class="sxs-lookup"><span data-stu-id="5a95c-133">For more detailed information about WebView2 APIs, navigate to [API reference][Webview2ApiReference].</span></span>
*   <span data-ttu-id="5a95c-134">WebView2 の詳細については、 [WebView2 リソース][Webview2MainNextSteps]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a95c-134">For more information about WebView2, navigate to [WebView2 Resources][Webview2MainNextSteps].</span></span>

## <span data-ttu-id="5a95c-135">WebView2 チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="5a95c-135">Getting in touch with the WebView2 team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"  

[Webview2ReferenceDotnet09628MicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments]: ../reference/dotnet/0-9-628/microsoft-web-webview2-core-corewebview2environmentoptions.md#additionalbrowserarguments "AdditionalBrowserArguments-0.9.515 クラス | WebView2 クラスの場合 |Microsoft ドキュメント"  
[Webview2ReferenceWin3209622Webview2IdlParameters]: ../reference/win32/0-9-622/webview2-idl.md#createcorewebview2environment  "CreateCoreWebView2Environment-Globals |Microsoft ドキュメント"  
[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API リファレンス |Microsoft ドキュメント"  
[Webview2MainNextSteps]: ../index.md#next-steps "次の手順-Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  
[Webview2MainGettingStarted]: ../index.md#getting-started "はじめに-Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftVscodeJSDebugWhatsNew]: https://github.com/microsoft/vscode-js-debug#whats-new "新機能-Visual Studio コードの JavaScript デバッガー-microsoft/vscode-js-debug |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) WebView アプリケーション-Visual Studio Code-Microsoft Edge 用デバッガー-microsoft/vscode-edge-debug2 |GitHub"  
