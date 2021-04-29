---
description: Win32 アプリ用 WebView2 の使い始めガイド
title: WebView2 for Win32 アプリの使用を開始する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/29/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、Webview2、Webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、ブラウザー コントロール、エッジ html
ms.openlocfilehash: 47f24b160797ce0ab7a7cb6a656c4f6b4e5696ac
ms.sourcegitcommit: b51df5036642060525e03cd744b7d35726326abe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2021
ms.locfileid: "11526067"
---
# <a name="getting-started-with-webview2"></a><span data-ttu-id="dfa74-104">WebView2 の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="dfa74-104">Getting started with WebView2</span></span>  

<span data-ttu-id="dfa74-105">この記事では、[WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2]の主な機能について説明して、初めて WebView2 アプリの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="dfa74-105">In this article, get started creating your first WebView2 app and learn about the main features of [WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2].</span></span>  <span data-ttu-id="dfa74-106">個々の WebView2 API の詳細については、「API リファレンス」 [に移動します][Webview2ReferenceWin32]。</span><span class="sxs-lookup"><span data-stu-id="dfa74-106">For more information about individual WebView2 APIs, navigate to [API reference][Webview2ReferenceWin32].</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="dfa74-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="dfa74-107">Prerequisites</span></span>  

<span data-ttu-id="dfa74-108">先に進む前に、次の前提条件の一覧をインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="dfa74-108">Ensure you install the following list of pre-requisites before proceeding.</span></span>  

*   <span data-ttu-id="dfa74-109">サポートされている OS \(現在は Windows 10、Windows 8.1、および Windows 7\ にインストールされている、[WebView2 ランタイム][Webview2Installer]または [Microsoft Edge (Chromium) 非安定チャネル][MicrosoftedgeinsiderDownload]。</span><span class="sxs-lookup"><span data-stu-id="dfa74-109">[WebView2 Runtime][Webview2Installer] or any [Microsoft Edge (Chromium) non-stable channel][MicrosoftedgeinsiderDownload] installed on supported OS \(currently Windows 10, Windows 8.1, and Windows 7\).</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="dfa74-110">WebView チームは Canary チャネルの使用を推奨し、最小必須バージョンは 82.0.488.0 です。</span><span class="sxs-lookup"><span data-stu-id="dfa74-110">The WebView team recommends using the Canary channel and the minimum required version is 82.0.488.0.</span></span>  
    
*   <span data-ttu-id="dfa74-111">[Visual Studio][MicrosoftVisualstudioMain] C++ サポートがインストールされている 2015 以降。</span><span class="sxs-lookup"><span data-stu-id="dfa74-111">[Visual Studio][MicrosoftVisualstudioMain] 2015 or later with C++ support installed.</span></span>  
    
## <a name="step-1---create-a-single-window-app"></a><span data-ttu-id="dfa74-112">手順 1 - シングル ウィンドウ アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="dfa74-112">Step 1 - Create a single-window app</span></span>  

<span data-ttu-id="dfa74-113">1 つのメイン ウィンドウを含む基本的なデスクトップ プロジェクトから開始します。</span><span class="sxs-lookup"><span data-stu-id="dfa74-113">Start with a basic desktop project that contains a single main window.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="dfa74-114">チュートリアルに焦点を当てるには、「ウォークスルー: 従来の Windows デスクトップ アプリケーション [(C++)][CppWindowsWalkthroughCreatingDesktopApplication] を作成する」の変更されたサンプル コードを使用します。</span><span class="sxs-lookup"><span data-stu-id="dfa74-114">To better focus the walkthrough, use modified sample code from [Walkthrough: Create a traditional Windows Desktop application (C++)][CppWindowsWalkthroughCreatingDesktopApplication] for your sample app.</span></span>  <span data-ttu-id="dfa74-115">変更したサンプルをダウンロードして開始するには [、[WebView2 サンプル] に移動します][GithubMicrosoftedgeWebview2samplesGettingStartedGuide]。</span><span class="sxs-lookup"><span data-stu-id="dfa74-115">To download the modified sample and get started, navigate to [WebView2 Samples][GithubMicrosoftedgeWebview2samplesGettingStartedGuide].</span></span>  

1.  <span data-ttu-id="dfa74-116">[Visual Studio] を開きます `WebView2GettingStarted.sln` 。</span><span class="sxs-lookup"><span data-stu-id="dfa74-116">In Visual Studio, open `WebView2GettingStarted.sln`.</span></span>  
    <span data-ttu-id="dfa74-117">以前のバージョンの Visual Studio を使用する場合は **、WebView2GettingStarted** プロジェクトにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き、[プロパティ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="dfa74-117">If you use an older version of Visual Studio, hover on the **WebView2GettingStarted** project, open the contextual menu \(right-click\), and choose **Properties**.</span></span>  <span data-ttu-id="dfa74-118">[**構成プロパティ全般**  >  **] で\*\*\*\*、Windows** \*\*\*\* SDK バージョンとプラットフォーム ツールセットを変更して、Win10 SDK を使用し、使用可能Visual Studioツールセットを使用します。</span><span class="sxs-lookup"><span data-stu-id="dfa74-118">Under **Configuration Properties** > **General**, modify **Windows SDK Version** and **Platform Toolset** to use the Win10 SDK and Visual Studio toolset available to you.</span></span>  

:::image type="complex" source="../media/tool-version.png" alt-text="ツールのバージョン" lightbox="../media/tool-version.png":::
   <span data-ttu-id="dfa74-120">ツールのバージョン</span><span class="sxs-lookup"><span data-stu-id="dfa74-120">Tool version</span></span>  
:::image-end:::  

<span data-ttu-id="dfa74-121">Visual Studio WebView2 ヘッダー ファイルが存在しないので、エラーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="dfa74-121">Visual Studio may display errors, because your project is missing the WebView2 header file.</span></span>  <span data-ttu-id="dfa74-122">エラーは、手順 2 の後 [に修正する必要があります](#step-2---install-webview2-sdk)。</span><span class="sxs-lookup"><span data-stu-id="dfa74-122">The errors should be fixed after [Step 2](#step-2---install-webview2-sdk).</span></span>  

## <a name="step-2---install-webview2-sdk"></a><span data-ttu-id="dfa74-123">手順 2-WebView2 SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="dfa74-123">Step 2 - Install WebView2 SDK</span></span>  

<span data-ttu-id="dfa74-124">WebView2 SDK をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="dfa74-124">Add the WebView2 SDK into the project.</span></span>  <span data-ttu-id="dfa74-125">NuGet を使用して Win32 SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="dfa74-125">Use NuGet to install the Win32 SDK.</span></span>  

1.  <span data-ttu-id="dfa74-126">プロジェクトにマウス ポインターを置き、コンテキスト メニュー \(右クリック\) を開き **、[NuGet パッケージの管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dfa74-126">Hover on the project, open the contextual menu \(right-click\), and choose **Manage NuGet Packages**.</span></span>  
    
    :::image type="complex" source="../media/manage-nuget-packages.png" alt-text="NuGet パッケージの管理" lightbox="../media/manage-nuget-packages.png":::
       <span data-ttu-id="dfa74-128">NuGet パッケージの管理</span><span class="sxs-lookup"><span data-stu-id="dfa74-128">Manage NuGet packages</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="dfa74-129">Windows 実装ライブラリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="dfa74-129">Install the Windows Implementation Library.</span></span>  
    1.  <span data-ttu-id="dfa74-130">検索バーに `Microsoft.Windows.ImplementationLibrary` **「Microsoft.Windows.implementationLibrary >」と入力します**。</span><span class="sxs-lookup"><span data-stu-id="dfa74-130">In the search bar, type `Microsoft.Windows.ImplementationLibrary` > choose **Microsoft.Windows.ImplementationLibrary**.</span></span>  
    1.  <span data-ttu-id="dfa74-131">右側のウィンドウで、[インストール] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="dfa74-131">In the right-hand side window, choose **Install**.</span></span>  <span data-ttu-id="dfa74-132">NuGet は、ライブラリをコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="dfa74-132">NuGet downloads the library to your machine.</span></span>  
        
        > [!NOTE]
        > <span data-ttu-id="dfa74-133">[Windows 実装ライブラリと][GithubMicrosoftWilMain] [Windows ランタイム C++ テンプレート ライブラリ][CppCxWrlTemplateLibraryVS2019]はオプションであり、例では COM の操作を容易にします。</span><span class="sxs-lookup"><span data-stu-id="dfa74-133">The [Windows Implementation Library][GithubMicrosoftWilMain] and [Windows Runtime C++ Template Library][CppCxWrlTemplateLibraryVS2019] are optional and make working with COM easier for the example.</span></span>  
        
        :::image type="complex" source="../media/wil.png" alt-text="Windows 実装ライブラリ" lightbox="../media/wil.png":::
           <span data-ttu-id="dfa74-135">Windows 実装ライブラリ</span><span class="sxs-lookup"><span data-stu-id="dfa74-135">Windows Implementation Library</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="dfa74-136">WebView2 SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="dfa74-136">Install the WebView2 SDK.</span></span>  
    1.  <span data-ttu-id="dfa74-137">検索バーに `Microsoft.Web.WebView2` と入力し、**[microsoft.Web.WebView2]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfa74-137">In the search bar, type `Microsoft.Web.WebView2` > choose **Microsoft.Web.WebView2**.</span></span>  
    1.  <span data-ttu-id="dfa74-138">右側のウィンドウで、[インストール] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="dfa74-138">In the right-hand side window, choose **Install**.</span></span>  <span data-ttu-id="dfa74-139">NuGet は SDK をコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="dfa74-139">NuGet downloads the SDK to your machine.</span></span>  
        
        :::image type="complex" source="../media/nuget.png" alt-text="NuGet パッケージ マネージャー" lightbox="../media/nuget.png":::
           <span data-ttu-id="dfa74-141">NuGet パッケージ マネージャー</span><span class="sxs-lookup"><span data-stu-id="dfa74-141">NuGet Package Manager</span></span>
        :::image-end:::  
        
1.  <span data-ttu-id="dfa74-142">WebView2 ヘッダーをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="dfa74-142">Add WebView2 header to your project.</span></span>  
    :::row:::
       :::column span="1":::
          <span data-ttu-id="dfa74-143">ファイルで `HelloWebView.cpp` 、次のコード スニペットをコピーし、最後の行の後に貼り付 `#include` けます。</span><span class="sxs-lookup"><span data-stu-id="dfa74-143">In the `HelloWebView.cpp` file, copy the following code snippet and paste it after the last `#include` line.</span></span>  
          
          ```cpp
          // include WebView2 header
          #include "WebView2.h"
          ```  
       :::column-end:::
       :::column span="1":::
          <span data-ttu-id="dfa74-144">include セクションは、次のコード スニペットのようになります。</span><span class="sxs-lookup"><span data-stu-id="dfa74-144">The include section should look similar to the following code snippet.</span></span>  
          
          ```cpp
          ...
          #include <wrl.h>
          #include <wil/com.h>
          // include WebView2 header
          #include "WebView2.h"
          ```  
       :::column-end:::
    :::row-end:::
    
<span data-ttu-id="dfa74-145">WebView2 API に対して使用してビルドする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="dfa74-145">Ready to use and build against the WebView2 API.</span></span>  

### <a name="build-your-empty-sample-app"></a><span data-ttu-id="dfa74-146">空のサンプル アプリをビルドする</span><span class="sxs-lookup"><span data-stu-id="dfa74-146">Build your empty sample app</span></span>  

<span data-ttu-id="dfa74-147">サンプル アプリをビルドして実行するには、 を選択します `F5` 。</span><span class="sxs-lookup"><span data-stu-id="dfa74-147">To build and run the sample app, select `F5`.</span></span>  <span data-ttu-id="dfa74-148">アプリに空のウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dfa74-148">Your app displays an empty window.</span></span>  

:::image type="complex" source="../media/empty-app.png" alt-text="空のアプリ" lightbox="../media/empty-app.png":::
   <span data-ttu-id="dfa74-150">空のアプリ</span><span class="sxs-lookup"><span data-stu-id="dfa74-150">Empty app</span></span>  
:::image-end:::  

## <a name="step-3---create-a-single-webview-within-the-parent-window"></a><span data-ttu-id="dfa74-151">手順 3 - 親ウィンドウ内に 1 つの WebView を作成する</span><span class="sxs-lookup"><span data-stu-id="dfa74-151">Step 3 - Create a single WebView within the parent window</span></span>  

<span data-ttu-id="dfa74-152">メイン ウィンドウに WebView を追加します。</span><span class="sxs-lookup"><span data-stu-id="dfa74-152">Add a WebView to the main window.</span></span>  

 <span data-ttu-id="dfa74-153">このメソッド `CreateCoreWebView2Environment` を使用して、環境をセットアップし、コントロールに電力を供給する Microsoft Edge \(Chromium\) ブラウザーを探します。</span><span class="sxs-lookup"><span data-stu-id="dfa74-153">Use the `CreateCoreWebView2Environment` method to set up the environment and locate the Microsoft Edge \(Chromium\) browser powering the control.</span></span>  <span data-ttu-id="dfa74-154">既定の設定を使用する代わりに、ブラウザーの場所、ユーザー フォルダー、ブラウザー フラグを指定する場合にも、このメソッド `CreateCoreWebView2EnvironmentWithOptions` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dfa74-154">You may also use the `CreateCoreWebView2EnvironmentWithOptions` method if you want to specify browser location, user folder, browser flags, and so on, instead of using the default setting.</span></span>  <span data-ttu-id="dfa74-155">メソッドが完了すると、コールバック内でメソッドを実行し、関連付けられた WebView を取得する `CreateCoreWebView2Environment` `ICoreWebView2Environment::CreateCoreWebView2Controller` `ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler` `ICoreWebView2Controller::get_CoreWebView2` メソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfa74-155">Upon the completion of the `CreateCoreWebView2Environment` method, run the `ICoreWebView2Environment::CreateCoreWebView2Controller` method inside the `ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler` callback and run the `ICoreWebView2Controller::get_CoreWebView2` method to get the associated WebView.</span></span>  

<span data-ttu-id="dfa74-156">コールバックで、もう少し設定を設定し、WebView のサイズを変更して親ウィンドウの 100% を占め、Bing に移動します。</span><span class="sxs-lookup"><span data-stu-id="dfa74-156">In the callback, set a few more settings, resize the WebView to take 100% of the parent window, and navigate to Bing.</span></span>  

<span data-ttu-id="dfa74-157">次のコード スニペットをコピーし、コメント `HelloWebView.cpp` の後とコメントの前 `// <-- WebView2 sample code starts here -->` に貼り付 `// <-- WebView2 sample code ends here -->` けます。</span><span class="sxs-lookup"><span data-stu-id="dfa74-157">Copy the following code snippet and paste into `HelloWebView.cpp` after the `// <-- WebView2 sample code starts here -->` comment and before the `// <-- WebView2 sample code ends here -->` comment.</span></span>  

```cpp
// Step 3 - Create a single WebView within the parent window
// Locate the browser and set up the environment for WebView
CreateCoreWebView2EnvironmentWithOptions(nullptr, nullptr, nullptr,
    Callback<ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler>(
        [hWnd](HRESULT result, ICoreWebView2Environment* env) -> HRESULT {
        
            // Create a CoreWebView2Controller and get the associated CoreWebView2 whose parent is the main window hWnd
            env->CreateCoreWebView2Controller(hWnd, Callback<ICoreWebView2CreateCoreWebView2ControllerCompletedHandler>(
                [hWnd](HRESULT result, ICoreWebView2Controller* controller) -> HRESULT {
                if (controller != nullptr) {
                    webviewController = controller;
                    webviewController->get_CoreWebView2(&webviewWindow);
                }
                
                // Add a few settings for the webview
                // The demo step is redundant since the values are the default settings
                ICoreWebView2Settings* Settings;
                webviewWindow->get_Settings(&Settings);
                Settings->put_IsScriptEnabled(TRUE);
                Settings->put_AreDefaultScriptDialogsEnabled(TRUE);
                Settings->put_IsWebMessageEnabled(TRUE);
                
                // Resize WebView to fit the bounds of the parent window
                RECT bounds;
                GetClientRect(hWnd, &bounds);
                webviewController->put_Bounds(bounds);
                
                // Schedule an async task to navigate to Bing
                webviewWindow->Navigate(L"https://www.bing.com/");
                
                // Step 4 - Navigation events
                
                // Step 5 - Scripting
                
                // Step 6 - Communication between host and web content
                
                return S_OK;
            }).Get());
        return S_OK;
    }).Get());
```  

### <a name="build-your-bing-sample-app"></a><span data-ttu-id="dfa74-158">Bing サンプル アプリをビルドする</span><span class="sxs-lookup"><span data-stu-id="dfa74-158">Build your Bing sample app</span></span>  

<span data-ttu-id="dfa74-159">アプリをビルドして実行するには、`F5` を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfa74-159">To build and run the app, select `F5`.</span></span>  <span data-ttu-id="dfa74-160">これで、WebView ウィンドウに Bing ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dfa74-160">Now you have a WebView window displaying the Bing page.</span></span>  

:::image type="complex" source="../media/bing-window.png" alt-text="Bing ウィンドウ" lightbox="../media/bing-window.png":::
   <span data-ttu-id="dfa74-162">Bing ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="dfa74-162">Bing window</span></span>  
:::image-end:::  

## <a name="step-4---navigation-events"></a><span data-ttu-id="dfa74-163">手順 4 - ナビゲーション イベント</span><span class="sxs-lookup"><span data-stu-id="dfa74-163">Step 4 - Navigation events</span></span>  

<span data-ttu-id="dfa74-164">WebView チームは、最後の手順でメソッドを使用して URL への移動 `ICoreWebView2::Navigate` について既に説明しました。</span><span class="sxs-lookup"><span data-stu-id="dfa74-164">The WebView team already covered navigating to URL using the `ICoreWebView2::Navigate` method in the last step.</span></span>  <span data-ttu-id="dfa74-165">ナビゲーション中に、WebView はホストがリッスンできる一連のイベントを発生します。</span><span class="sxs-lookup"><span data-stu-id="dfa74-165">During navigation, WebView fires a sequence of events to which the host may listen.</span></span>  

1.  `NavigationStarting`  
1.  `SourceChanged`  
1.  `ContentLoading`  
1.  `HistoryChanged`   
1.  `NavigationCompleted`   

<span data-ttu-id="dfa74-166">詳細については、「ナビゲーション イベント」 [に移動します][Webview2ConceptsNavigationEvents]。</span><span class="sxs-lookup"><span data-stu-id="dfa74-166">For more information, navigate to [Navigation events][Webview2ConceptsNavigationEvents].</span></span>  

:::image type="complex" source="../media/navigation-events.png" alt-text="ナビゲーション イベント" lightbox="../media/navigation-events.png":::
   <span data-ttu-id="dfa74-168">ナビゲーション イベント</span><span class="sxs-lookup"><span data-stu-id="dfa74-168">Navigation events</span></span>  
:::image-end:::  

<span data-ttu-id="dfa74-169">エラーの場合、ナビゲーションがエラー Web ページに続いているかどうかに応じて、次の 1 つ以上のイベントが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="dfa74-169">In error cases, one or more of the following events may occur depending on whether the navigation is continued to an error webpage.</span></span>  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`

> [!NOTE]
> <span data-ttu-id="dfa74-170">HTTP リダイレクトが発生した場合、1 行に複数の `NavigationStarting` イベントがあります。</span><span class="sxs-lookup"><span data-stu-id="dfa74-170">If an HTTP redirect occurs, there are multiple `NavigationStarting` events in a row.</span></span>  

<span data-ttu-id="dfa74-171">イベントを使用する例として、イベントのハンドラーを登録して、https 以外の要求 `NavigationStarting` をキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="dfa74-171">As an example of using the events, register a handler for the `NavigationStarting` event to cancel any non-https requests.</span></span>  <span data-ttu-id="dfa74-172">次のコード スニペットをコピーし、に貼り付けます `HelloWebView.cpp` 。</span><span class="sxs-lookup"><span data-stu-id="dfa74-172">Copy the following code snippet and paste into `HelloWebView.cpp`.</span></span>  

```cpp
// register an ICoreWebView2NavigationStartingEventHandler to cancel any non-https navigation
EventRegistrationToken token;
webviewWindow->add_NavigationStarting(Callback<ICoreWebView2NavigationStartingEventHandler>(
    [](ICoreWebView2* webview, ICoreWebView2NavigationStartingEventArgs * args) -> HRESULT {
        PWSTR uri;
        args->get_Uri(&uri);
        std::wstring source(uri);
        if (source.substr(0, 5) != L"https") {
            args->put_Cancel(true);
        }
        CoTaskMemFree(uri);
        return S_OK;
    }).Get(), &token);
```  

<span data-ttu-id="dfa74-173">これで、アプリは https 以外のサイトには移動されません。</span><span class="sxs-lookup"><span data-stu-id="dfa74-173">Now the app does not navigate to any non-https sites.</span></span>  <span data-ttu-id="dfa74-174">同様のメカニズムを使用して、独自のドメイン内へのナビゲーションの制限など、他のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="dfa74-174">You may use similar mechanism to accomplish other tasks, such as restricting navigation to within your own domain.</span></span>  

## <a name="step-5---scripting"></a><span data-ttu-id="dfa74-175">手順 5 - スクリプト</span><span class="sxs-lookup"><span data-stu-id="dfa74-175">Step 5 - Scripting</span></span>  

<span data-ttu-id="dfa74-176">ホスト アプリを使用して、実行時に JavaScript コードを WebView2 コントロールに挿入できます。</span><span class="sxs-lookup"><span data-stu-id="dfa74-176">You may use host apps to inject JavaScript code into WebView2 controls at runtime.</span></span>  <span data-ttu-id="dfa74-177">任意の JavaScript を実行したり、初期化スクリプトを追加したりするために、WebView をタスクすることができます。</span><span class="sxs-lookup"><span data-stu-id="dfa74-177">You may task WebView to run arbitrary JavaScript or add initialization scripts.</span></span>  <span data-ttu-id="dfa74-178">挿入された JavaScript は、JavaScript が削除されるまで、すべての新しいトップ レベル ドキュメントとすべての子フレームに適用されます。</span><span class="sxs-lookup"><span data-stu-id="dfa74-178">The injected JavaScript applies to all new top-level documents and any child frames until the JavaScript is removed.</span></span>  <span data-ttu-id="dfa74-179">挿入された JavaScript は、特定のタイミングで実行されます。</span><span class="sxs-lookup"><span data-stu-id="dfa74-179">The injected JavaScript is run with specific timing.</span></span>  

*   <span data-ttu-id="dfa74-180">グローバル オブジェクトの作成後に実行します。</span><span class="sxs-lookup"><span data-stu-id="dfa74-180">Run it after the creation of the global object.</span></span>  
*   <span data-ttu-id="dfa74-181">HTML ドキュメントに含まれる他のスクリプトを実行する前に実行してください。</span><span class="sxs-lookup"><span data-stu-id="dfa74-181">Run it before any other script included in the HTML document is run.</span></span>  

<span data-ttu-id="dfa74-182">次のコード スニペットをコピーし、に貼り付けます `HelloWebView.cpp` 。</span><span class="sxs-lookup"><span data-stu-id="dfa74-182">Copy the following code snippet and paste into `HelloWebView.cpp`.</span></span>  

```cpp
// Schedule an async task to add initialization script that freezes the Object object
webviewWindow->AddScriptToExecuteOnDocumentCreated(L"Object.freeze(Object);", nullptr);
// Schedule an async task to get the document URL
webviewWindow->ExecuteScript(L"window.document.URL;", Callback<ICoreWebView2ExecuteScriptCompletedHandler>(
    [](HRESULT errorCode, LPCWSTR resultObjectAsJson) -> HRESULT {
        LPCWSTR URL = resultObjectAsJson;
        //doSomethingWithURL(URL);
        return S_OK;
    }).Get());
```  

<span data-ttu-id="dfa74-183">これで、WebView は常にオブジェクトを `Object` フリーズし、ページ ドキュメントを 1 回返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfa74-183">Now, WebView should always freeze the `Object` object and returns the page document once.</span></span>  

> [!NOTE] 
> <span data-ttu-id="dfa74-184">スクリプトインジェクション API \(および他の WebView2 API\) は非同期です。コードを特定の順序で実行する必要がある場合は、コールバックを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfa74-184">The script injection APIs \(and some other WebView2 APIs\) are asynchronous, you should use callbacks if code is must be run in a specific order.</span></span>  

## <a name="step-6---communication-between-host-and-web-content"></a><span data-ttu-id="dfa74-185">手順 6 - ホストコンテンツと Web コンテンツ間の通信</span><span class="sxs-lookup"><span data-stu-id="dfa74-185">Step 6 - Communication between host and web content</span></span>  

<span data-ttu-id="dfa74-186">ホストと Web コンテンツは、メソッドを介して相互に通信 `postMessage` する場合があります。</span><span class="sxs-lookup"><span data-stu-id="dfa74-186">The host and the web content may also communicate with each other through the `postMessage` method.</span></span>  <span data-ttu-id="dfa74-187">WebView 内で実行されている Web コンテンツは、メソッドを介してホストに投稿され、メッセージはホストに登録されたイベント ハンドラー `window.chrome.webview.postMessage` `ICoreWebView2WebMessageReceivedEventHandler` によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="dfa74-187">The web content running within a WebView may post to the host through the `window.chrome.webview.postMessage` method, and the message is handled by any registered the `ICoreWebView2WebMessageReceivedEventHandler` event handler on the host.</span></span>  <span data-ttu-id="dfa74-188">同様に、ホストは、リスナーから追加されたハンドラーによってキャッチされる Web コンテンツまたはメソッドを通じて `ICoreWebView2::PostWebMessageAsString` `ICoreWebView2::PostWebMessageAsJSON` メッセージを送信 `window.chrome.webview.addEventListener` できます。</span><span class="sxs-lookup"><span data-stu-id="dfa74-188">Likewise, the host may message the web content through `ICoreWebView2::PostWebMessageAsString` or `ICoreWebView2::PostWebMessageAsJSON` method, which is caught by handlers added from `window.chrome.webview.addEventListener` listener.</span></span>  <span data-ttu-id="dfa74-189">通信メカニズムにより、Web コンテンツはメッセージを渡してホストにネイティブ API の実行を求め、ネイティブ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dfa74-189">The communication mechanism allows the web content to use native capabilities by passing messages to ask the host to run native APIs.</span></span>  

<span data-ttu-id="dfa74-190">メカニズムを理解する例として、WebView でドキュメント URL を出力しようとするときに、次の手順が実行されます。</span><span class="sxs-lookup"><span data-stu-id="dfa74-190">As an example to understand the mechanism, the following steps occur when you try to output the document URL in WebView.</span></span>  

1.  <span data-ttu-id="dfa74-191">ホストは、受信したメッセージを Web コンテンツに戻すハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="dfa74-191">The host registers a handler to return received message back to the web content</span></span>  
1.  <span data-ttu-id="dfa74-192">ホストは、ホストからのメッセージを印刷するためのハンドラーを登録するスクリプトを Web コンテンツに挿入します。</span><span class="sxs-lookup"><span data-stu-id="dfa74-192">The host injects a script to the web content that registers a handler to print message from the host</span></span>  
1.  <span data-ttu-id="dfa74-193">ホストは、URL をホストに投稿する Web コンテンツにスクリプトを挿入します。</span><span class="sxs-lookup"><span data-stu-id="dfa74-193">The host injects a script to the web content that posts the URL to the host</span></span>  
1.  <span data-ttu-id="dfa74-194">ホストのハンドラーがトリガーされ、メッセージ \(the URL\) を Web コンテンツに返します。</span><span class="sxs-lookup"><span data-stu-id="dfa74-194">The handler of the host is triggered and returns the message \(the URL\) to the web content</span></span>  
1.  <span data-ttu-id="dfa74-195">Web コンテンツのハンドラーがトリガーされ、ホスト \(the URL\) からメッセージが出力されます。</span><span class="sxs-lookup"><span data-stu-id="dfa74-195">The handler of the web content is triggered and prints message from the host \(the URL\)</span></span>  

<span data-ttu-id="dfa74-196">次のコード スニペットをコピーし、に貼り付けます `HelloWebView.cpp` 。</span><span class="sxs-lookup"><span data-stu-id="dfa74-196">Copy the following code snippet and paste into `HelloWebView.cpp`.</span></span>  

```cpp
// Set an event handler for the host to return received message back to the web content
webviewWindow->add_WebMessageReceived(Callback<ICoreWebView2WebMessageReceivedEventHandler>(
    [](ICoreWebView2* webview, ICoreWebView2WebMessageReceivedEventArgs * args) -> HRESULT {
        PWSTR message;
        args->TryGetWebMessageAsString(&message);
        // processMessage(&message);
        webview->PostWebMessageAsString(message);
        CoTaskMemFree(message);
        return S_OK;
    }).Get(), &token);

// Schedule an async task to add initialization script that
// 1) Add an listener to print message from the host
// 2) Post document URL to the host
webviewWindow->AddScriptToExecuteOnDocumentCreated(
    L"window.chrome.webview.addEventListener(\'message\', event => alert(event.data));" \
    L"window.chrome.webview.postMessage(window.document.URL);",
nullptr);
```  

### <a name="build-your-display-url-sample-app"></a><span data-ttu-id="dfa74-197">表示 URL サンプル アプリをビルドする</span><span class="sxs-lookup"><span data-stu-id="dfa74-197">Build your display URL sample app</span></span>  

<span data-ttu-id="dfa74-198">アプリをビルドして実行するには、`F5` を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfa74-198">To build and run the app, select `F5`.</span></span>  <span data-ttu-id="dfa74-199">WEB ページに移動する前に、URL がポップアップ ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dfa74-199">The URL appears in a pop-up window before navigating to a webpage.</span></span>  

:::image type="complex" source="../media/show-url.png" alt-text="表示 URL" lightbox="../media/show-url.png":::
   <span data-ttu-id="dfa74-201">表示 URL</span><span class="sxs-lookup"><span data-stu-id="dfa74-201">Display url</span></span>  
:::image-end:::  

<span data-ttu-id="dfa74-202">これで、最初の WebView2 アプリがビルドされました。</span><span class="sxs-lookup"><span data-stu-id="dfa74-202">Congratulations, you built your first WebView2 app.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="dfa74-203">次の手順</span><span class="sxs-lookup"><span data-stu-id="dfa74-203">Next steps</span></span>  

<span data-ttu-id="dfa74-204">この記事で説明されていない追加の WebView2 機能については、次のリソースを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dfa74-204">For additional WebView2 functionality that isn't covered in this article, review the following resources.</span></span>  

*   <span data-ttu-id="dfa74-205">WebView2 アプリケーションの構築の詳細については [、「WebView2 開発のベスト プラクティス」に移動します][WV2BestPractices]。</span><span class="sxs-lookup"><span data-stu-id="dfa74-205">To learn more about building WebView2 applications, navigate to [WebView2 development best practices][WV2BestPractices].</span></span>  
*   <span data-ttu-id="dfa74-206">WebView2 機能の包括的な例については [、「WebView2 API サンプル」に移動します][GithubMicrosoftedgeWebview2samplesApisample]。</span><span class="sxs-lookup"><span data-stu-id="dfa74-206">For a comprehensive example of WebView2 capabilities, navigate to [WebView2 API Sample][GithubMicrosoftedgeWebview2samplesApisample].</span></span>  
*   <span data-ttu-id="dfa74-207">WebView2 を使用してビルドされたサンプル アプリの場合は [、WebView2Browser に移動します][GithubMicrosoftedgeWebview2browser]。</span><span class="sxs-lookup"><span data-stu-id="dfa74-207">For a sample app built using WebView2, navigate to [WebView2Browser][GithubMicrosoftedgeWebview2browser].</span></span>  
*   <span data-ttu-id="dfa74-208">WebView2 API の詳細については、「API リファレンス」 [に移動します][Webview2ReferenceWin32]。</span><span class="sxs-lookup"><span data-stu-id="dfa74-208">For detailed information about the WebView2 API, navigate to [API reference][Webview2ReferenceWin32].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a><span data-ttu-id="dfa74-209">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="dfa74-209">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[WV2BestPractices]: ../concepts/developer-guide.md "WebView2 の開発のベスト プラクティス|Microsoft Docs"  
[MicrosoftDeveloperMicrosoftEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2 " WebView2 | Microsoft Edge 開発者"  

[Webview2ReferenceWin32]: /microsoft-edge/webview2/reference/win32 "WebView2 Win32 C++ リファレンス |Microsoft Docs"  
[Webview2ConceptsNavigationEvents]: ../concepts/navigation-events.md "ナビゲーション イベント | Microsoft Docs"  

[CppCxWrlTemplateLibraryVS2019]: /cpp/cppcx/wrl/windows-runtime-cpp-template-library-wrl?view=vs-2019&preserve-view=true "Windows ランタイム C++ テンプレート ライブラリ (WRL) |Microsoft Docs"  
[CppWindowsWalkthroughCreatingDesktopApplication]: /cpp/windows/walkthrough-creating-windows-desktop-applications-cpp?view=vs-2019&preserve-view=true "チュートリアル: 従来の Windows デスクトップ アプリケーション (C++) アプリケーションを作成|Microsoft Docs"  

[GithubMicrosoftedgeWebview2browser]: https://github.com/MicrosoftEdge/WebView2Browser "WebView2Browser - MicrosoftEdge/WebView2Browser |GitHub"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック - MicrosoftEdge/WebViewFeedback | GitHub"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  

[GithubMicrosoftedgeWebview2samplesApisample]: https://github.com/MicrosoftEdge/WebView2Samples/blob/master/SampleApps/WebView2APISample/README.md "WebView2 API サンプル - MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesGettingStartedGuide]: https://github.com/MicrosoftEdge/WebView2Samples#1-getting-started-guide "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  

[GithubMicrosoftWilMain]: https://github.com/Microsoft/wil "Windows 実装ライブラリ (WIL) - microsoft/wil |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channels をダウンロードする"  

[MicrosoftVisualstudioMain]: https://visualstudio.microsoft.com "Visual Studio"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 インストーラー"  
