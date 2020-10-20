---
description: Win32 アプリ用 WebView2 の概要ガイド
title: Win32 アプリの WebView2 の概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 20d830e2c8b95213b223da46f9afd9f69a137946
ms.sourcegitcommit: af91bfc3e6d8afc51f0fbbc0fe392262f424225c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2020
ms.locfileid: "11120383"
---
# <span data-ttu-id="a06e1-104">WebView2 の概要</span><span class="sxs-lookup"><span data-stu-id="a06e1-104">Getting started with WebView2</span></span>  

<span data-ttu-id="a06e1-105">次のコンテンツでは、 [WebView2][Webview2Index] の一般的に使われる機能について説明し、最初の WebView2 アプリを作成するための開始点を提供します。</span><span class="sxs-lookup"><span data-stu-id="a06e1-105">The following content walks you through the commonly used functionalities of [WebView2][Webview2Index] and provides a starting point for creating your first WebView2 app.</span></span>  <span data-ttu-id="a06e1-106">個々の WebView2 Api について詳しくは、 [api リファレンス][Webview2ReferenceWin32]をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a06e1-106">For more information about individual WebView2 APIs, see [API reference][Webview2ReferenceWin32].</span></span>  

## <span data-ttu-id="a06e1-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="a06e1-107">Prerequisites</span></span>  

*   <span data-ttu-id="a06e1-108">サポートされている OS \ (現在 Windows 10、Windows 8.1、Windows 7 \) にインストールされている[WebView2 Runtime][Webview2Installer]または[Microsoft Edge (Chromium) 非永続的なチャネル][MicrosoftedgeinsiderDownload]。</span><span class="sxs-lookup"><span data-stu-id="a06e1-108">[WebView2 Runtime][Webview2Installer] or any [Microsoft Edge (Chromium) non-stable channel][MicrosoftedgeinsiderDownload] installed on supported OS \(currently Windows 10, Windows 8.1, and Windows 7\).</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="a06e1-109">WebView チームは、カナリアチャネルの使用を推奨し、最低限必要なバージョンは82.0.488.0 です。</span><span class="sxs-lookup"><span data-stu-id="a06e1-109">The WebView team recommends using the Canary channel and the minimum required version is 82.0.488.0.</span></span>  
    
*   <span data-ttu-id="a06e1-110">[Visual Studio][MicrosoftVisualstudioMain] 2015 以降、C++ サポートがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="a06e1-110">[Visual Studio][MicrosoftVisualstudioMain] 2015 or later with C++ support installed.</span></span>  

## <span data-ttu-id="a06e1-111">手順 1-単一ウィンドウの win32 アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="a06e1-111">Step 1 - Create a single-window win32 app</span></span>  

<span data-ttu-id="a06e1-112">1つのメインウィンドウを含む基本的なデスクトッププロジェクトから始めます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-112">Start with a basic desktop project that contains a single main window.</span></span>  <span data-ttu-id="a06e1-113">チュートリアルに焦点を合わせるために、サンプルアプリ用の [従来の Windows デスクトップアプリケーション (C++) を作成][CppWindowsWalkthroughCreatingDesktopApplication] して、チュートリアルから変更されたサンプルコードを使用しています。</span><span class="sxs-lookup"><span data-stu-id="a06e1-113">To better focus the walkthrough, you are using modified sample code from [Walkthrough: Create a traditional Windows Desktop application (C++)][CppWindowsWalkthroughCreatingDesktopApplication] for your sample app.</span></span>  <span data-ttu-id="a06e1-114">更新されたサンプルをダウンロードして始めるには、 [WebView2 サンプル][GithubMicrosoftedgeWebview2samplesGettingStartedGuide]に移動します。</span><span class="sxs-lookup"><span data-stu-id="a06e1-114">To download the modified sample and get started, navigate to [WebView2 Samples][GithubMicrosoftedgeWebview2samplesGettingStartedGuide].</span></span>  

<span data-ttu-id="a06e1-115">Visual Studio で、を開き `WebView2GettingStarted.sln` ます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-115">In Visual Studio, open `WebView2GettingStarted.sln`.</span></span>  <span data-ttu-id="a06e1-116">以前のバージョンの Visual Studio を使っている場合は、 **WebView2GettingStarted** プロジェクトにカーソルを置いて、コンテキストメニュー \ (右クリック \) を開き、[ **プロパティ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-116">If you are using an older version of Visual Studio, hover on the **WebView2GettingStarted** project, open the contextual menu \(right-click\), and select **Properties**.</span></span>  <span data-ttu-id="a06e1-117">[**構成プロパティ**の  >  **全般**] で、 **Windows sdk のバージョン**と**プラットフォームのツールセット**を変更して、Win10 SDK と Visual Studio のツールセット (VS ツールセット \) を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a06e1-117">Under **Configuration Properties** > **General**, modify **Windows SDK Version** and **Platform Toolset** to use the Win10 SDK and Visual Studio toolset \(VS toolset\) available to you.</span></span>  

:::image type="complex" source="../media/tool-version.png" alt-text="ツールバージョン" lightbox="../media/tool-version.png":::
   <span data-ttu-id="a06e1-119">ツールバージョン</span><span class="sxs-lookup"><span data-stu-id="a06e1-119">Tool version</span></span>  
:::image-end:::  

<span data-ttu-id="a06e1-120">WebView2 ヘッダーファイルが存在しないため、Visual Studio でいくつかのエラーが表示されることがあります。これは、手順2が完了した後に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a06e1-120">Visual Studio may show some errors because of the missing WebView2 header file, which should go away after Step 2 is completed.</span></span>  

## <span data-ttu-id="a06e1-121">手順 2-WebView2 SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="a06e1-121">Step 2 - Install WebView2 SDK</span></span>  

<span data-ttu-id="a06e1-122">プロジェクトに WebView2 SDK を追加します。</span><span class="sxs-lookup"><span data-stu-id="a06e1-122">Add the WebView2 SDK into the project.</span></span>  <span data-ttu-id="a06e1-123">NuGet を使って Win32 SDK をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-123">You may install the Win32 SDK using NuGet.</span></span>  

1.  <span data-ttu-id="a06e1-124">プロジェクトにマウスポインターを合わせて、コンテキストメニュー \ (右クリック \) を開き、[ **NuGet パッケージの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a06e1-124">Hover on the project, open the contextual menu \(right-click\), and select **Manage NuGet Packages**.</span></span>  
    
    :::image type="complex" source="../media/manage-nuget-packages.png" alt-text="ツールバージョン" lightbox="../media/manage-nuget-packages.png":::
       <span data-ttu-id="a06e1-126">NuGet パッケージの管理</span><span class="sxs-lookup"><span data-stu-id="a06e1-126">Manage NuGet packages</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="a06e1-127">Windows 実装ライブラリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a06e1-127">Install the Windows Implementation Library.</span></span>  
    1.  <span data-ttu-id="a06e1-128">`Microsoft.Windows.ImplementationLibrary`検索バーに入力し、結果から [ **ImplementationLibrary** ] を選択して、右側のウィンドウで [**インストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a06e1-128">Enter `Microsoft.Windows.ImplementationLibrary` in the search bar, select **Microsoft.Windows.ImplementationLibrary** from the results, and select **Install** in the right-hand side window.</span></span>  <span data-ttu-id="a06e1-129">NuGet によって SDK がコンピューターにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-129">NuGet downloads the SDK to your machine.</span></span>  
        
        > [!NOTE] 
        > <span data-ttu-id="a06e1-130">[Windows 実装ライブラリ][GithubMicrosoftWilMain]と[Windows ランタイム C++ テンプレートライブラリ][CppCxWrlTemplateLibraryVS2019]は省略可能であり、この例で COM を簡単に操作できるように追加されています。</span><span class="sxs-lookup"><span data-stu-id="a06e1-130">The [Windows Implementation Library][GithubMicrosoftWilMain] and [Windows Runtime C++ Template Library][CppCxWrlTemplateLibraryVS2019] are optional and were added to make working with COM easier for the example.</span></span>  
        
        :::image type="complex" source="../media/wil.png" alt-text="ツールバージョン" lightbox="../media/wil.png":::
           <span data-ttu-id="a06e1-132">Windows 実装ライブラリ</span><span class="sxs-lookup"><span data-stu-id="a06e1-132">Windows Implementation Library</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="a06e1-133">WebView2 SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="a06e1-133">Install the WebView2 SDK.</span></span>  
    1.  <span data-ttu-id="a06e1-134">`Microsoft.Web.WebView2`検索バーに入力し、結果から [ **WebView2** ] を選択して、右側のウィンドウで [**インストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a06e1-134">Enter `Microsoft.Web.WebView2` in the search bar, select **Microsoft.Web.WebView2** from the results, and select **Install** in the right-hand side window.</span></span>  <span data-ttu-id="a06e1-135">NuGet によって SDK がコンピューターにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-135">NuGet downloads the SDK to your machine.</span></span>  
        
        :::image type="complex" source="../media/nuget.png" alt-text="ツールバージョン" lightbox="../media/nuget.png":::
           <span data-ttu-id="a06e1-137">Nuget パッケージマネージャー</span><span class="sxs-lookup"><span data-stu-id="a06e1-137">Nuget Package Manager</span></span>
        :::image-end:::  
        
1.  <span data-ttu-id="a06e1-138">プロジェクトに WebView2 ヘッダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="a06e1-138">Add WebView2 header to your project.</span></span>  
    :::row:::
       :::column span="1":::
          <span data-ttu-id="a06e1-139">`HelloWebView.cpp`を開き、次のコードスニペットをコピーして、最後の行の後ろに貼り付け `HelloWebView.cpp` `#include` ます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-139">Open `HelloWebView.cpp`, copy the following code snippet and paste into `HelloWebView.cpp` after last `#include` line.</span></span>  
          
          ```cpp
          // include WebView2 header
          #include "WebView2.h"
          ```  
       :::column-end:::
       :::column span="1":::
          <span data-ttu-id="a06e1-140">Include セクションは、次のコードスニペットのようになります。</span><span class="sxs-lookup"><span data-stu-id="a06e1-140">The include section should look similar to the following code snippet.</span></span>  
          
          ```cpp
          ...
          #include <wrl.h>
          #include <wil/com.h>
          // include WebView2 header
          #include "WebView2.h"
          ```  
       :::column-end:::
    :::row-end:::
    
<span data-ttu-id="a06e1-141">WebView2 API に対して使用およびビルドするように設定されています。</span><span class="sxs-lookup"><span data-stu-id="a06e1-141">You are all set to use and build against the WebView2 API.</span></span>  

### <span data-ttu-id="a06e1-142">空のサンプルアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="a06e1-142">Build your empty sample app</span></span>  

<span data-ttu-id="a06e1-143">`F5`サンプルアプリをビルドして実行することを選択します。</span><span class="sxs-lookup"><span data-stu-id="a06e1-143">Select `F5` to build and run the sample app.</span></span>  <span data-ttu-id="a06e1-144">空のウィンドウを表示するアプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-144">An app displaying an empty window appears.</span></span>  

:::image type="complex" source="../media/empty-app.png" alt-text="ツールバージョン" lightbox="../media/empty-app.png":::
   <span data-ttu-id="a06e1-146">空のアプリ</span><span class="sxs-lookup"><span data-stu-id="a06e1-146">Empty app</span></span>  
:::image-end:::  

## <span data-ttu-id="a06e1-147">手順 3-親ウィンドウ内に1つの WebView を作成する</span><span class="sxs-lookup"><span data-stu-id="a06e1-147">Step 3 - Create a single WebView within the parent window</span></span>  

<span data-ttu-id="a06e1-148">メインウィンドウに WebView を追加します。</span><span class="sxs-lookup"><span data-stu-id="a06e1-148">Add a WebView to the main window.</span></span>  <span data-ttu-id="a06e1-149">メソッドを使用して `CreateCoreWebView2Environment` 環境を設定し、コントロールの電源を入れて Microsoft Edge \ (Chromium) ブラウザーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-149">Use the `CreateCoreWebView2Environment` method to set up the environment and locate the Microsoft Edge \(Chromium\) browser powering the control.</span></span>  <span data-ttu-id="a06e1-150">また、 `CreateCoreWebView2EnvironmentWithOptions` 既定の設定を使用する代わりに、ブラウザーの場所、ユーザーフォルダー、ブラウザーのフラグなどを指定する場合にも、このメソッドを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-150">You may also use the `CreateCoreWebView2EnvironmentWithOptions` method if you want to specify browser location, user folder, browser flags, and so on, instead of using the default setting.</span></span>  <span data-ttu-id="a06e1-151">メソッドが完了する `CreateCoreWebView2Environment` `ICoreWebView2Environment::CreateCoreWebView2Controller` と、コールバック内でメソッドを実行 `ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler` し、メソッドを実行して、 `ICoreWebView2Controller::get_CoreWebView2` 関連付けられている WebView を取得できます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-151">Upon the completion of the `CreateCoreWebView2Environment` method, you are able to run the `ICoreWebView2Environment::CreateCoreWebView2Controller` method inside the `ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler` callback and run the `ICoreWebView2Controller::get_CoreWebView2` method to get the associated WebView.</span></span>  

<span data-ttu-id="a06e1-152">コールバックでいくつかの追加設定を行い、WebView のサイズを変更して親ウィンドウの100% を取得し、Bing に移動します。</span><span class="sxs-lookup"><span data-stu-id="a06e1-152">In the callback, set a few additional settings, resize the WebView to take 100% of the parent window, and navigate to Bing.</span></span>  

<span data-ttu-id="a06e1-153">次のコードスニペットをコピーし、 `HelloWebView.cpp` メモの後 `// <-- WebView2 sample code starts here -->` とメモの前に貼り付け `// <-- WebView2 sample code ends here -->` ます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-153">Copy the following code snippet and paste into `HelloWebView.cpp` after the `// <-- WebView2 sample code starts here -->` note and before the `// <-- WebView2 sample code ends here -->` note.</span></span>  

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

### <span data-ttu-id="a06e1-154">Bing サンプルアプリを構築する</span><span class="sxs-lookup"><span data-stu-id="a06e1-154">Build your Bing sample app</span></span>  

<span data-ttu-id="a06e1-155">`F5`アプリをビルドして実行することを選択します。</span><span class="sxs-lookup"><span data-stu-id="a06e1-155">Select `F5` to build and run the app.</span></span>  <span data-ttu-id="a06e1-156">これで、[WebView] ウィンドウに Bing ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-156">Now you have a WebView window displaying the Bing page.</span></span>  

:::image type="complex" source="../media/bing-window.png" alt-text="ツールバージョン" lightbox="../media/bing-window.png":::
   <span data-ttu-id="a06e1-158">Bing ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="a06e1-158">Bing window</span></span>  
:::image-end:::  

## <span data-ttu-id="a06e1-159">ステップ 4-ナビゲーションイベント</span><span class="sxs-lookup"><span data-stu-id="a06e1-159">Step 4 - Navigation events</span></span>  

<span data-ttu-id="a06e1-160">既に紹介している WebView チームについては、最後の手順のメソッドを使用して URL に移動し `ICoreWebView2::Navigate` ます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-160">The WebView team already covered navigating to URL using the `ICoreWebView2::Navigate` method in the last step.</span></span>  <span data-ttu-id="a06e1-161">ナビゲーション中に、WebView は、ホストがリッスンできる一連のイベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-161">During navigation, WebView fires a sequence of events to which the host may listen.</span></span>  

1.  `NavigationStarting`  
1.  `SourceChanged`  
1.  `ContentLoading`  
1.  `HistoryChanged`   
1.  `NavigationCompleted`   

<span data-ttu-id="a06e1-162">詳細については、「 [ナビゲーションイベント][Webview2ConceptsNavigationEvents]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a06e1-162">For more information, navigate to [Navigation events][Webview2ConceptsNavigationEvents].</span></span>  

:::image type="complex" source="../media/navigation-events.png" alt-text="ツールバージョン" lightbox="../media/navigation-events.png":::
   <span data-ttu-id="a06e1-164">ナビゲーションイベント</span><span class="sxs-lookup"><span data-stu-id="a06e1-164">Navigation events</span></span>  
:::image-end:::  

<span data-ttu-id="a06e1-165">エラーが発生した場合は、ナビゲーションがエラーページに続いているかどうかによって、次のいずれかのイベントが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="a06e1-165">In error cases, one or more of the following events may occur depending on whether the navigation is continued to an error page.</span></span>  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`

<span data-ttu-id="a06e1-166">HTTP リダイレクトが発生する場合は、 `NavigationStarting` 1 つの行に複数のイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="a06e1-166">If an HTTP redirect occurs, there are multiple `NavigationStarting` events in a row.</span></span>  

<span data-ttu-id="a06e1-167">イベントを使用する例として、イベントのハンドラーを登録して `NavigationStarting` https 以外の要求をキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="a06e1-167">As an example of using the events, register a handler for the `NavigationStarting` event to cancel any non-https requests.</span></span>  <span data-ttu-id="a06e1-168">次のコードスニペットをコピーして貼り付け `HelloWebView.cpp` ます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-168">Copy the following code snippet and paste into `HelloWebView.cpp`.</span></span>  

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

<span data-ttu-id="a06e1-169">これで、アプリは https 以外のサイトに移動しません。</span><span class="sxs-lookup"><span data-stu-id="a06e1-169">Now the app is not navigating to any non-https sites.</span></span>  <span data-ttu-id="a06e1-170">同様のメカニズムを使って、独自のドメイン内でのナビゲーションの制限など、他のタスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-170">You may use similar mechanism to accomplish other tasks, such as restricting navigation to within your own domain.</span></span>  

## <span data-ttu-id="a06e1-171">手順 5-スクリプト</span><span class="sxs-lookup"><span data-stu-id="a06e1-171">Step 5 - Scripting</span></span>  

<span data-ttu-id="a06e1-172">ホストアプリでは、JavaScript を WebView に挿入することもできます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-172">The hosting app may also inject JavaScript into WebView.</span></span>  <span data-ttu-id="a06e1-173">タスク WebView で任意の JavaScript を実行したり、初期化スクリプトを追加したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-173">You may task WebView to run arbitrary JavaScript or add initialization scripts.</span></span>  <span data-ttu-id="a06e1-174">追加された初期化スクリプトは、削除されるまで、今後のすべてのトップレベルのドキュメントと子フレームのナビゲーションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-174">Added initialization scripts apply to all future top-level document and child frame navigation until removed.</span></span>  <span data-ttu-id="a06e1-175">初期化スクリプトは、グローバルオブジェクトを作成した後、および HTML ドキュメントに含まれている他のスクリプトを実行する前に実行されます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-175">The initialization scripts run after creating the global object and before running any other script included by the HTML document.</span></span>  

<span data-ttu-id="a06e1-176">次のコードスニペットをコピーして貼り付け `HelloWebView.cpp` ます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-176">Copy the following code snippet and paste into `HelloWebView.cpp`.</span></span>  

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

<span data-ttu-id="a06e1-177">この時点で、WebView は常にオブジェクトを固定 `Object` し、ページドキュメントを1回返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a06e1-177">Now, WebView should always freeze the `Object` object and returns the page document once.</span></span>  

> [!NOTE] 
> <span data-ttu-id="a06e1-178">スクリプトインジェクション Api \ (および他のいくつかの WebView2 Api \) は非同期です。特定の順序でコードを実行する必要がある場合は、コールバックを使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a06e1-178">The script injection APIs \(and some other WebView2 APIs\) are asynchronous, you should use callbacks if code is must be run in a specific order.</span></span>  

## <span data-ttu-id="a06e1-179">ステップ 6-ホストと web コンテンツ間の通信</span><span class="sxs-lookup"><span data-stu-id="a06e1-179">Step 6 - Communication between host and web content</span></span>  

<span data-ttu-id="a06e1-180">この方法では、ホストと web コンテンツもメソッドを通じて相互に通信することができ `postMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-180">The host and the web content may also communicate with each other through the `postMessage` method.</span></span>  <span data-ttu-id="a06e1-181">WebView 内で実行されている web コンテンツは、メソッドによってホストに投稿される可能性があり `window.chrome.webview.postMessage` ます。メッセージは、 `ICoreWebView2WebMessageReceivedEventHandler` ホスト上のイベントハンドラーによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-181">The web content running within a WebView may post to the host through the `window.chrome.webview.postMessage` method, and the message is handled by any registered the `ICoreWebView2WebMessageReceivedEventHandler` event handler on the host.</span></span>  <span data-ttu-id="a06e1-182">同様に、ホストで `ICoreWebView2::PostWebMessageAsString` は、 `ICoreWebView2::PostWebMessageAsJSON` リスナーから追加されたハンドラーによって検出された web コンテンツを経由して、またはメソッドでメッセージを送信することがあり `window.chrome.webview.addEventListener` ます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-182">Likewise, the host may message the web content through `ICoreWebView2::PostWebMessageAsString` or `ICoreWebView2::PostWebMessageAsJSON` method, which is caught by handlers added from `window.chrome.webview.addEventListener` listener.</span></span>  <span data-ttu-id="a06e1-183">通信メカニズムにより、web コンテンツは、ネイティブ Api を実行するようにホストにメッセージを送信することによってネイティブ機能を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-183">The communication mechanism allows the web content to use native capabilities by passing messages to ask the host to run native APIs.</span></span>  

<span data-ttu-id="a06e1-184">このメカニズムを理解するための例として、WebView でドキュメントの URL を印刷しようとすると、次の手順が発生します。</span><span class="sxs-lookup"><span data-stu-id="a06e1-184">As an example to understand the mechanism, the following steps occur when you try printing out the document URL in WebView.</span></span>  

1.  <span data-ttu-id="a06e1-185">ホストは、受信したメッセージを web コンテンツに戻すためのハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="a06e1-185">The host registers a handler to return received message back to the web content</span></span>  
1.  <span data-ttu-id="a06e1-186">ホストは、ホストからメッセージを印刷するためのハンドラーを登録する web コンテンツにスクリプトを挿入します。</span><span class="sxs-lookup"><span data-stu-id="a06e1-186">The host injects a script to the web content that registers a handler to print message from the host</span></span>  
1.  <span data-ttu-id="a06e1-187">ホストは、URL をホストにポストする web コンテンツにスクリプトを挿入します。</span><span class="sxs-lookup"><span data-stu-id="a06e1-187">The host injects a script to the web content that posts the URL to the host</span></span>  
1.  <span data-ttu-id="a06e1-188">ホストのハンドラーがトリガーされ、web コンテンツへのメッセージ \ (URL) が返されます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-188">The handler of the host is triggered and returns the message \(the URL\) to the web content</span></span>  
1.  <span data-ttu-id="a06e1-189">Web コンテンツのハンドラーがトリガーされ、ホスト \ (URL \) からメッセージが出力されます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-189">The handler of the web content is triggered and prints message from the host \(the URL\)</span></span>  

<span data-ttu-id="a06e1-190">次のコードスニペットをコピーして貼り付け `HelloWebView.cpp` ます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-190">Copy the following code snippet and paste into `HelloWebView.cpp`.</span></span>    

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

### <span data-ttu-id="a06e1-191">Show URL サンプルアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="a06e1-191">Build your show URL sample app</span></span>  

<span data-ttu-id="a06e1-192">`F5`アプリをビルドして実行することを選択します。</span><span class="sxs-lookup"><span data-stu-id="a06e1-192">Select `F5` to build and run the app.</span></span>  <span data-ttu-id="a06e1-193">URL は、ページに移動する前にポップアップウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a06e1-193">The URL appears in a pop-up window before navigating to a page.</span></span>  

:::image type="complex" source="../media/show-url.png" alt-text="ツールバージョン" lightbox="../media/show-url.png":::
   <span data-ttu-id="a06e1-195">Url の表示</span><span class="sxs-lookup"><span data-stu-id="a06e1-195">Show url</span></span>  
:::image-end:::  

<span data-ttu-id="a06e1-196">おめでとうございます。最初の WebView2 アプリを作成しました。</span><span class="sxs-lookup"><span data-stu-id="a06e1-196">Congratulations, you just built your first WebView2 app.</span></span>  

## <span data-ttu-id="a06e1-197">次のステップ</span><span class="sxs-lookup"><span data-stu-id="a06e1-197">Next steps</span></span>  

<span data-ttu-id="a06e1-198">このページで取り上げていない WebView2 の機能の多くは、次のセクションで追加のリソースを提供しています。</span><span class="sxs-lookup"><span data-stu-id="a06e1-198">Many of the WebView2 functionalities that are not covered on this page, the following section provided additional resources.</span></span>  

### <span data-ttu-id="a06e1-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="a06e1-199">See also</span></span>  

*   <span data-ttu-id="a06e1-200">WebView2 機能の包括的な例については、「 [WEBVIEW2 API のサンプル][GithubMicrosoftedgeWebview2samplesApisample]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a06e1-200">For a comprehensive example of WebView2 capabilities, navigate to [WebView2 API Sample][GithubMicrosoftedgeWebview2samplesApisample].</span></span>  
*   <span data-ttu-id="a06e1-201">WebView2 を使って構築されたサンプルアプリケーションの場合は、 [WebView2Browser][GithubMicrosoftedgeWebview2browser]に移動します。</span><span class="sxs-lookup"><span data-stu-id="a06e1-201">For a sample application built using WebView2, navigate to [WebView2Browser][GithubMicrosoftedgeWebview2browser].</span></span>  
*   <span data-ttu-id="a06e1-202">WebView2 API の詳細については、 [api リファレンス][Webview2ReferenceWin32]に移動してください。</span><span class="sxs-lookup"><span data-stu-id="a06e1-202">For detailed information about the WebView2 API, navigate to [API reference][Webview2ReferenceWin32].</span></span>  

## <span data-ttu-id="a06e1-203">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="a06e1-203">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2Index]: ../index.md "Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  
[Webview2ReferenceWin32]: /microsoft-edge/webview2/reference/win32 "WebView2 Win32 C++ リファレンス |Microsoft ドキュメント"  
[Webview2ConceptsNavigationEvents]: ../concepts/navigation-events.md "ナビゲーションイベント |Microsoft ドキュメント"  

[CppCxWrlTemplateLibraryVS2019]: /cpp/cppcx/wrl/windows-runtime-cpp-template-library-wrl?view=vs-2019&preserve-view=true "Windows ランタイム C++ テンプレートライブラリ (WRL) |Microsoft ドキュメント"  
[CppWindowsWalkthroughCreatingDesktopApplication]: /cpp/windows/walkthrough-creating-windows-desktop-applications-cpp?view=vs-2019&preserve-view=true "チュートリアル: 従来の Windows デスクトップアプリケーションの作成 (C++) |Microsoft ドキュメント"  

[GithubMicrosoftedgeWebview2browser]: https://github.com/MicrosoftEdge/WebView2Browser "WebView2Browser-MicrosoftEdge/WebView2Browser |GitHub"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  

[GithubMicrosoftedgeWebview2samplesApisample]: https://github.com/MicrosoftEdge/WebView2Samples/blob/master/SampleApps/WebView2APISample/README.md "WebView2 API のサンプル-MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesGettingStartedGuide]: https://github.com/MicrosoftEdge/WebView2Samples#1-getting-started-guide "WebView2 サンプル-MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftWilMain]: https://github.com/Microsoft/wil "Windows 実装ライブラリ (WIL)-microsoft/WIL |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  

[MicrosoftVisualstudioMain]: https://visualstudio.microsoft.com "Visual Studio"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 Installer"  
