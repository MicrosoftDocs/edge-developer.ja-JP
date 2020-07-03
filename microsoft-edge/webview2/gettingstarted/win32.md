---
description: Microsoft Edge WebView 2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリの WebView2 の概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/15/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: e184eaeb28a1e6e7aacf2917094149092d2fb6ee
ms.sourcegitcommit: ae0257f8fb9832296ee6a196ded7bad2aacd3208
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "10846550"
---
# <span data-ttu-id="f9a29-104">WebView2 の概要 (開発者用プレビュー)</span><span class="sxs-lookup"><span data-stu-id="f9a29-104">Getting started with WebView2 (developer preview)</span></span>  

<span data-ttu-id="f9a29-105">次のコンテンツでは、 [WebView2 (開発者向けプレビュー)][Webview2Index]の一般的な使用方法について説明し、最初の WebView2 アプリを作成するための開始点を示しています。</span><span class="sxs-lookup"><span data-stu-id="f9a29-105">The following content walks you through the commonly used functionalities of [WebView2 (developer preview)][Webview2Index] and provides a starting  point for creating your first WebView2 app.</span></span>  <span data-ttu-id="f9a29-106">個々の WebView2 Api について詳しくは、 [api リファレンス][Webview2ReferenceWin3209538]をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f9a29-106">For more information about individual WebView2 APIs, see [API reference][Webview2ReferenceWin3209538].</span></span>  

## <span data-ttu-id="f9a29-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="f9a29-107">Prerequisites</span></span>  

*   <span data-ttu-id="f9a29-108">[Microsoft Edge (Chromium)][MicrosoftedgeinsiderDownload]は、サポートされている OS \ (現在 windows 10、windows 8.1、windows 7 \) にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="f9a29-108">[Microsoft Edge (Chromium)][MicrosoftedgeinsiderDownload] installed on supported OS \(currently Windows 10, Windows 8.1, and Windows 7\).</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="f9a29-109">WebView チームは、カナリアチャネルの使用を推奨し、最低限必要なバージョンは82.0.488.0 です。</span><span class="sxs-lookup"><span data-stu-id="f9a29-109">The WebView team recommends using the Canary channel and the minimum required version is 82.0.488.0.</span></span>  
    
*   <span data-ttu-id="f9a29-110">[Visual Studio][MicrosoftVisualstudioMain] 2015 以降、C++ サポートがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="f9a29-110">[Visual Studio][MicrosoftVisualstudioMain] 2015 or later with C++ support installed.</span></span>  

## <span data-ttu-id="f9a29-111">手順 1-単一ウィンドウの win32 アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="f9a29-111">Step 1 - Create a single window win32 app</span></span>  

<span data-ttu-id="f9a29-112">1つのメインウィンドウを含む基本的なデスクトッププロジェクトから始めます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-112">Start with a basic desktop project containing a single main window.</span></span>  <span data-ttu-id="f9a29-113">チュートリアルに焦点を合わせるために、サンプルアプリ用の[従来の Windows デスクトップアプリケーション (C++) を作成][CppWindowsWalkthroughCreatingDesktopApplication]して、チュートリアルから変更されたサンプルコードを使用しています。</span><span class="sxs-lookup"><span data-stu-id="f9a29-113">To better focus the walkthrough, you are using modified sample code from [Walkthrough: Create a traditional Windows Desktop application (C++)][CppWindowsWalkthroughCreatingDesktopApplication] for your sample app.</span></span>  <span data-ttu-id="f9a29-114">更新されたサンプルをダウンロードして始めるには、「 [WebView2 のサンプル][GithubMicrosoftedgeWebview2samplesGettingStartedGuide]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f9a29-114">To download the modified sample and get started, see [WebView2 Samples][GithubMicrosoftedgeWebview2samplesGettingStartedGuide].</span></span>  

<span data-ttu-id="f9a29-115">Visual Studio で、を開き `WebView2GettingStarted.sln` ます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-115">In Visual Studio, open `WebView2GettingStarted.sln`.</span></span>  <span data-ttu-id="f9a29-116">以前のバージョンの Visual Studio を使っている場合は、 **WebView2GettingStarted**プロジェクトにカーソルを置いて、コンテキストメニュー \ (右クリック \) を開き、[**プロパティ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-116">If you are using an older version of Visual Studio, hover on the **WebView2GettingStarted** project, open the contextual menu \(right-click\), and select **Properties**.</span></span>  <span data-ttu-id="f9a29-117">[**構成プロパティ**の  >  **全般**] で、 **Windows sdk のバージョン**と**プラットフォームのツールセット**を変更して、Win10 SDK と Visual Studio のツールセット (VS ツールセット \) を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f9a29-117">Under **Configuration Properties** > **General**, modify **Windows SDK Version** and **Platform Toolset** to use the Win10 SDK and Visual Studio toolset \(VS toolset\) available to you.</span></span>  

:::image type="complex" source="../media/tool-version.png" alt-text="ツールバージョン":::
   <span data-ttu-id="f9a29-119">ツールバージョン</span><span class="sxs-lookup"><span data-stu-id="f9a29-119">Tool version</span></span>  
:::image-end:::  

<span data-ttu-id="f9a29-120">Visual Studio では、WebView2 ヘッダーファイルが見つからないことが原因でいくつかのエラーが表示されることがあります。これは、手順2が完了した後に発生します。</span><span class="sxs-lookup"><span data-stu-id="f9a29-120">Visual Studio may show some errors due to missing WebView2 header file, which should go away after Step 2 is completed.</span></span>  

## <span data-ttu-id="f9a29-121">手順 2-WebView2 SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="f9a29-121">Step 2 - Install WebView2 SDK</span></span>  

<span data-ttu-id="f9a29-122">プロジェクトに WebView2 SDK を追加します。</span><span class="sxs-lookup"><span data-stu-id="f9a29-122">Add the WebView2 SDK into the project.</span></span>  <span data-ttu-id="f9a29-123">開発者用プレビューでは、Nuget を使って Win32 SDK をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-123">For the developer preview, you may install the Win32 SDK using Nuget.</span></span>  

1.  <span data-ttu-id="f9a29-124">プロジェクトにマウスポインターを合わせて、コンテキストメニュー \ (右クリック \) を開き、[ **Nuget パッケージの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f9a29-124">Hover on the project, open the contextual menu \(right-click\), and select **Manage Nuget Packages**.</span></span>  
    
    :::image type="complex" source="../media/manage-nuget-packages.png" alt-text="Nuget パッケージを管理する":::
       <span data-ttu-id="f9a29-126">Nuget パッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="f9a29-126">Manage Nuget packages</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f9a29-127">Windows 実装ライブラリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f9a29-127">Install the Windows Implementation Library.</span></span>  
    1.  <span data-ttu-id="f9a29-128">`Microsoft.Windows.ImplementationLibrary`検索バーに入力し、結果から [ **ImplementationLibrary** ] を選択して、右側のウィンドウで [**インストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f9a29-128">Enter `Microsoft.Windows.ImplementationLibrary` in the search bar, select **Microsoft.Windows.ImplementationLibrary** from the results, and select **Install** in the right-hand side window.</span></span>  <span data-ttu-id="f9a29-129">Nuget によって SDK がコンピューターにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-129">Nuget downloads the SDK to your machine.</span></span>  
        
        > [!NOTE] 
        > <span data-ttu-id="f9a29-130">[Windows 実装ライブラリ][GithubMicrosoftWilMain]と[Windows ランタイム C++ テンプレートライブラリ][CppCxWrlTemplateLibraryVS2019]は省略可能であり、この例で COM を簡単に操作できるように追加されています。</span><span class="sxs-lookup"><span data-stu-id="f9a29-130">The [Windows Implementation Library][GithubMicrosoftWilMain] and [Windows Runtime C++ Template Library][CppCxWrlTemplateLibraryVS2019] are optional and were added to make working with COM easier for the example.</span></span>  
        
        :::image type="complex" source="../media/wil.png" alt-text="Windows 実装ライブラリ":::
           <span data-ttu-id="f9a29-132">Windows 実装ライブラリ</span><span class="sxs-lookup"><span data-stu-id="f9a29-132">Windows Implementation Library</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="f9a29-133">WebView2 SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f9a29-133">Install the WebView2 SDK.</span></span>  
    1.  <span data-ttu-id="f9a29-134">`Microsoft.Web.WebView2`検索バーに入力し、結果から [ **WebView2** ] を選択して、右側のウィンドウで [**インストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f9a29-134">Enter `Microsoft.Web.WebView2` in the search bar, select **Microsoft.Web.WebView2** from the results, and select **Install** in the right-hand side window.</span></span>  <span data-ttu-id="f9a29-135">Nuget によって SDK がコンピューターにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-135">Nuget downloads the SDK to your machine.</span></span>  
        
        :::image type="complex" source="../media/nuget.png" alt-text="Nuget.exe":::
           <span data-ttu-id="f9a29-137">Nuget.exe</span><span class="sxs-lookup"><span data-stu-id="f9a29-137">Nuget</span></span>
        :::image-end:::  
        
1.  <span data-ttu-id="f9a29-138">プロジェクトに WebView2 ヘッダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="f9a29-138">Add WebView2 header to your project.</span></span>  
    :::row:::
       :::column span="1":::
          <span data-ttu-id="f9a29-139">`HelloWebView.cpp`を開き、次のコードスニペットをコピーして、最後の行の後ろに貼り付け `HelloWebView.cpp` `#include` ます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-139">Open `HelloWebView.cpp`, copy the following code snippet and paste into `HelloWebView.cpp` after last `#include` line.</span></span>  
          
          ```cpp
          // include WebView2 header
          #include "WebView2.h"
          ```  
       :::column-end:::
       :::column span="1":::
          <span data-ttu-id="f9a29-140">Include セクションは、次のコードスニペットのようになります。</span><span class="sxs-lookup"><span data-stu-id="f9a29-140">The include section should look similar to the following code snippet.</span></span>  
          
          ```cpp
          ...
          #include <wrl.h>
          #include <wil/com.h>
          // include WebView2 header
          #include "WebView2.h"
          ```  
       :::column-end:::
    :::row-end:::
    
<span data-ttu-id="f9a29-141">WebView2 API に対して使用およびビルドするように設定されています。</span><span class="sxs-lookup"><span data-stu-id="f9a29-141">You are all set to use and build against the WebView2 API.</span></span>  

### <span data-ttu-id="f9a29-142">空のサンプルアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="f9a29-142">Build your empty sample app</span></span>  

<span data-ttu-id="f9a29-143">を押して `F5` 、サンプルアプリをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="f9a29-143">Press `F5` to build and run the sample app.</span></span>  <span data-ttu-id="f9a29-144">空のウィンドウが表示されたアプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-144">You should see an app displaying an empty window.</span></span>  

:::image type="complex" source="../media/empty-app.png" alt-text="空のアプリ":::
   <span data-ttu-id="f9a29-146">空のアプリ</span><span class="sxs-lookup"><span data-stu-id="f9a29-146">Empty app</span></span>  
:::image-end:::  

## <span data-ttu-id="f9a29-147">手順 3-親ウィンドウ内に1つの WebView を作成する</span><span class="sxs-lookup"><span data-stu-id="f9a29-147">Step 3 - Create a single WebView within the parent window</span></span>  

<span data-ttu-id="f9a29-148">メインウィンドウに WebView を追加します。</span><span class="sxs-lookup"><span data-stu-id="f9a29-148">Add a WebView to the main window.</span></span>  <span data-ttu-id="f9a29-149">メソッドを使用して `CreateCoreWebView2Environment` 環境を設定し、コントロールの電源を入れて Microsoft Edge \ (Chromium) ブラウザーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-149">Use the `CreateCoreWebView2Environment` method to set up the environment and locate the Microsoft Edge \(Chromium\) browser powering the control.</span></span>  <span data-ttu-id="f9a29-150">また、 `CreateCoreWebView2EnvironmentWithOptions` 既定の設定を使用する代わりに、ブラウザーの場所、ユーザーフォルダー、ブラウザーのフラグなどを指定する場合にも、このメソッドを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-150">You may also use the `CreateCoreWebView2EnvironmentWithOptions` method if you want to specify browser location, user folder, browser flags, and so on, instead of using the default setting.</span></span>  <span data-ttu-id="f9a29-151">メソッドが完了する `CreateCoreWebView2Environment` `ICoreWebView2Environment::CreateCoreWebView2Controller` と、コールバック内でメソッドを実行 `ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler` し、メソッドを実行して、 `ICoreWebView2Controller::get_CoreWebView2` 関連付けられている WebView を取得できます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-151">Upon the completion of the `CreateCoreWebView2Environment` method, you are able to run the `ICoreWebView2Environment::CreateCoreWebView2Controller` method inside the `ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler` callback and run the `ICoreWebView2Controller::get_CoreWebView2` method to get the associated WebView.</span></span>  

<span data-ttu-id="f9a29-152">コールバックでいくつかの追加設定を行い、WebView のサイズを変更して親ウィンドウの100% を取得し、Bing に移動します。</span><span class="sxs-lookup"><span data-stu-id="f9a29-152">In the callback, set a few additional settings, resize the WebView to take 100% of the parent window, and navigate to Bing.</span></span>  

<span data-ttu-id="f9a29-153">次のコードスニペットをコピーし、 `HelloWebView.cpp` メモの後 `// <-- WebView2 sample code starts here -->` とメモの前に貼り付け `// <-- WebView2 sample code ends here -->` ます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-153">Copy the following code snippet and paste into `HelloWebView.cpp` after the `// <-- WebView2 sample code starts here -->` note and before the `// <-- WebView2 sample code ends here -->` note.</span></span>  

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
                // this is a redundant demo step as the values are the default settings
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


### <span data-ttu-id="f9a29-154">Bing サンプルアプリを構築する</span><span class="sxs-lookup"><span data-stu-id="f9a29-154">Build your Bing sample app</span></span>  

<span data-ttu-id="f9a29-155">を押して `F5` アプリをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="f9a29-155">Press `F5` to build and run the app.</span></span>  <span data-ttu-id="f9a29-156">これで、[WebView] ウィンドウに Bing ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-156">Now you have a WebView window displaying the Bing page.</span></span>  

:::image type="complex" source="../media/bing-window.png" alt-text="Bing ウィンドウ":::
   <span data-ttu-id="f9a29-158">Bing ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="f9a29-158">Bing window</span></span>  
:::image-end:::  

## <span data-ttu-id="f9a29-159">ステップ 4-ナビゲーションイベント</span><span class="sxs-lookup"><span data-stu-id="f9a29-159">Step 4 - Navigation events</span></span>  

<span data-ttu-id="f9a29-160">既に紹介している WebView チームについては、最後の手順のメソッドを使用して URL に移動し `ICoreWebView2::Navigate` ます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-160">The WebView team already covered navigating to URL using the `ICoreWebView2::Navigate` method in the last step.</span></span>  <span data-ttu-id="f9a29-161">ナビゲーション中に、WebView は、ホストがリッスンできる一連のイベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-161">During navigation, WebView fires a sequence of events to which the host may listen.</span></span>  

1.  `NavigationStarting`  
1.  `SourceChanged`  
1.  `ContentLoading`  
1.  `HistoryChanged`   
1.  `NavigationCompleted`   

<span data-ttu-id="f9a29-162">詳細については、「[ナビゲーションイベント][Webview2ReferenceWin3209538Icorewebview2NavigationEvents]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9a29-162">For more information, see [Navigation events][Webview2ReferenceWin3209538Icorewebview2NavigationEvents].</span></span>  

:::image type="complex" source="../media/navigation-events.png" alt-text="ナビゲーションイベント":::
   <span data-ttu-id="f9a29-164">ナビゲーションイベント</span><span class="sxs-lookup"><span data-stu-id="f9a29-164">Navigation events</span></span>  
:::image-end:::  

<span data-ttu-id="f9a29-165">エラーが発生した場合は、ナビゲーションがエラーページに続いているかどうかによって、次のいずれかのイベントが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="f9a29-165">In error cases, one or more of the following events may occur depending on whether the navigation is continued to an error page.</span></span>  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`

<span data-ttu-id="f9a29-166">HTTP リダイレクトの場合、 `NavigationStarting` 1 つの行に複数のイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="f9a29-166">In case of an HTTP redirect, there are multiple `NavigationStarting` events in a row.</span></span>  

<span data-ttu-id="f9a29-167">イベントを利用する例として、イベントのハンドラーを登録して `NavigationStarting` https 以外の要求をキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="f9a29-167">As an example of utilizing the events, register a handler for the `NavigationStarting` event to cancel any non-https requests.</span></span>  <span data-ttu-id="f9a29-168">次のコードスニペットをコピーして貼り付け `HelloWebView.cpp` ます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-168">Copy the following code snippet and paste into `HelloWebView.cpp`.</span></span>  

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

<span data-ttu-id="f9a29-169">これで、アプリは https 以外のサイトに移動しません。</span><span class="sxs-lookup"><span data-stu-id="f9a29-169">Now the app is not navigating to any non-https sites.</span></span>  <span data-ttu-id="f9a29-170">同様のメカニズムを使って、独自のドメイン内でのナビゲーションの制限など、他のタスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-170">You may use similar mechanism to accomplish other tasks, such as restricting navigation to within your own domain.</span></span>  

## <span data-ttu-id="f9a29-171">手順 5-スクリプト</span><span class="sxs-lookup"><span data-stu-id="f9a29-171">Step 5 - Scripting</span></span>  

<span data-ttu-id="f9a29-172">ホストアプリでは、JavaScript を WebView に挿入することもできます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-172">The hosting app may also inject JavaScript into WebView.</span></span>  <span data-ttu-id="f9a29-173">タスク WebView で任意の JavaScript を実行したり、初期化スクリプトを追加したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-173">You may task WebView to execute arbitrary JavaScript or add initialization scripts.</span></span>  <span data-ttu-id="f9a29-174">追加された初期化スクリプトは、削除されるまでのすべての上位レベルのドキュメントと子フレームのナビゲーションに適用され、グローバルオブジェクトが作成された後で、その HTML ドキュメントに含まれている他のスクリプトが実行される前に実行されます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-174">Added initialization scripts apply to all future top level document and child frame navigation until removed, and run after the global object has been created and before any other script included by the HTML document is executed.</span></span>  

<span data-ttu-id="f9a29-175">次のコードスニペットをコピーして貼り付け `HelloWebView.cpp` ます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-175">Copy the following code snippet and paste into `HelloWebView.cpp`.</span></span>  

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

<span data-ttu-id="f9a29-176">WebView では常にオブジェクトがフリーズされ、 `Object` ページドキュメントが1回返されます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-176">Now WebView should always freezes the `Object` object and returns the page document once.</span></span>  

> [!NOTE] 
> <span data-ttu-id="f9a29-177">スクリプトインジェクション Api \ (および他のいくつかの WebView2 Api \) は非同期です。特定の順序でコードを実行する必要がある場合は、コールバックを使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9a29-177">The script injection APIs \(and some other WebView2 APIs\) are asynchronous, you should use callbacks if code is must be run in a specific order.</span></span>  

## <span data-ttu-id="f9a29-178">ステップ 6-ホストと web コンテンツ間の通信</span><span class="sxs-lookup"><span data-stu-id="f9a29-178">Step 6 - Communication between host and web content</span></span>  

<span data-ttu-id="f9a29-179">この方法では、ホストと web コンテンツもメソッドを通じて相互に通信することができ `postMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-179">The host and the web content may also communicate with each other through the `postMessage` method.</span></span>  <span data-ttu-id="f9a29-180">WebView 内で実行されている web コンテンツは、メソッドによってホストに投稿される可能性があり `window.chrome.webview.postMessage` ます。メッセージは、 `ICoreWebView2WebMessageReceivedEventHandler` ホスト上のイベントハンドラーによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-180">The web content running within a WebView may post to the host through the `window.chrome.webview.postMessage` method, and the message is handled by any registered the `ICoreWebView2WebMessageReceivedEventHandler` event handler on the host.</span></span>  <span data-ttu-id="f9a29-181">同様に、ホストで `ICoreWebView2::PostWebMessageAsString` は、 `ICoreWebView2::PostWebMessageAsJSON` リスナーから追加されたハンドラーによって検出された web コンテンツを経由して、またはメソッドでメッセージを送信することがあり `window.chrome.webview.addEventListener` ます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-181">Likewise, the host may message the web content through `ICoreWebView2::PostWebMessageAsString` or `ICoreWebView2::PostWebMessageAsJSON` method, which is caught by handlers added from `window.chrome.webview.addEventListener` listener.</span></span>  <span data-ttu-id="f9a29-182">通信メカニズムにより、web コンテンツは、ネイティブ Api を呼び出すように指示するメッセージを渡すことによってネイティブ機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-182">The communication mechanism allows the web content to utilize native capabilities by passing messages to ask the host to call native APIs.</span></span>  

<span data-ttu-id="f9a29-183">このメカニズムを理解するための例として、WebView でドキュメントの URL を印刷しようとすると、次の手順が発生します。</span><span class="sxs-lookup"><span data-stu-id="f9a29-183">As an example to understand the mechanism, the following steps occur when you try printing out the document URL in WebView.</span></span>  

1.  <span data-ttu-id="f9a29-184">ホストは、受信したメッセージを web コンテンツに戻すためのハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="f9a29-184">The host registers a handler to return received message back to the web content</span></span>  
1.  <span data-ttu-id="f9a29-185">ホストは、ホストからメッセージを印刷するためのハンドラーを登録する web コンテンツにスクリプトを挿入します。</span><span class="sxs-lookup"><span data-stu-id="f9a29-185">The host injects a script to the web content that registers a handler to print message from the host</span></span>  
1.  <span data-ttu-id="f9a29-186">ホストは、URL をホストにポストする web コンテンツにスクリプトを挿入します。</span><span class="sxs-lookup"><span data-stu-id="f9a29-186">The host injects a script to the web content that posts the URL to the host</span></span>  
1.  <span data-ttu-id="f9a29-187">ホストのハンドラーがトリガーされ、web コンテンツへのメッセージ \ (URL) が返されます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-187">The handler of the host is triggered and returns the message \(the URL\) to the web content</span></span>  
1.  <span data-ttu-id="f9a29-188">Web コンテンツのハンドラーがトリガーされ、ホスト \ (URL \) からメッセージが出力されます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-188">The handler of the web content is triggered and prints message from the host \(the URL\)</span></span>  

<span data-ttu-id="f9a29-189">次のコードスニペットをコピーして貼り付け `HelloWebView.cpp` ます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-189">Copy the following code snippet and paste into `HelloWebView.cpp`.</span></span>    

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

### <span data-ttu-id="f9a29-190">Show URL サンプルアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="f9a29-190">Build your show URL sample app</span></span>  

<span data-ttu-id="f9a29-191">を押して `F5` アプリをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="f9a29-191">Press `F5` to build and run the app.</span></span>  <span data-ttu-id="f9a29-192">ページに移動する前に、ポップアップウィンドウに URL が表示されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9a29-192">You should see the URL in a pop-up window prior to navigating to a page.</span></span>  

:::image type="complex" source="../media/show-url.png" alt-text="Url の表示":::
   <span data-ttu-id="f9a29-194">Url の表示</span><span class="sxs-lookup"><span data-stu-id="f9a29-194">Show url</span></span>  
:::image-end:::  

<span data-ttu-id="f9a29-195">おめでとうございます。最初の WebView2 アプリを作成しました。</span><span class="sxs-lookup"><span data-stu-id="f9a29-195">Congratulations, you just built your first WebView2 app!</span></span>  

## <span data-ttu-id="f9a29-196">次のステップ</span><span class="sxs-lookup"><span data-stu-id="f9a29-196">Next steps</span></span>  

<span data-ttu-id="f9a29-197">このページで取り上げていない WebView2 の機能の多くは、次のセクションで追加のリソースを提供しています。</span><span class="sxs-lookup"><span data-stu-id="f9a29-197">Many of the WebView2 functionalities that are not covered on this page, the following section provided additional resources.</span></span>  

### <span data-ttu-id="f9a29-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9a29-198">See also</span></span>  

*   <span data-ttu-id="f9a29-199">WebView2 機能の包括的な例については、「 [WEBVIEW2 API のサンプル][GithubMicrosoftedgeWebview2samplesApisample]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f9a29-199">For a comprehensive example of WebView2 capabilities, see [WebView2 API Sample][GithubMicrosoftedgeWebview2samplesApisample].</span></span>  
*   <span data-ttu-id="f9a29-200">WebView2 を使って構築されたサンプルアプリケーションについては、「 [WebView2Browser][GithubMicrosoftedgeWebview2browser]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9a29-200">For a sample application built using WebView2, see [WebView2Browser][GithubMicrosoftedgeWebview2browser].</span></span>  
*   <span data-ttu-id="f9a29-201">WebView2 API の詳細については、 [api リファレンス][Webview2ReferenceWin3209538]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9a29-201">For detailed information about the WebView2 API, see [API reference][Webview2ReferenceWin3209538].</span></span>  

## <span data-ttu-id="f9a29-202">WebView2 チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="f9a29-202">Getting in touch with the WebView2 team</span></span>  

<span data-ttu-id="f9a29-203">フィードバックを共有して、より充実した WebView2 エクスペリエンスを構築できます。</span><span class="sxs-lookup"><span data-stu-id="f9a29-203">Help build a richer WebView2 experience by sharing your feedback!</span></span>  <span data-ttu-id="f9a29-204">GitHub の[フィードバックリポジトリ][GithubMicrosoftedgeWebviewfeedback]にアクセスして、機能要求またはバグレポートを送信するか、既知の問題を検索します。</span><span class="sxs-lookup"><span data-stu-id="f9a29-204">Visit the [feedback repo][GithubMicrosoftedgeWebviewfeedback] on GitHub to submit feature requests or bug reports or search for known issues.</span></span>  

<!-- links -->  

[Webview2Index]: ../index.md "Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  
[Webview2ReferenceWin3209538]: ../reference/win32/0-9-538-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[Webview2ReferenceWin3209538Icorewebview2NavigationEvents]: ../reference/win32/0-9-538/ICoreWebView2.md#navigation-events "ナビゲーションイベント-インターフェイス ICoreWebView2 |Microsoft ドキュメント"  

[CppCxWrlTemplateLibraryVS2019]: /cpp/cppcx/wrl/windows-runtime-cpp-template-library-wrl?view=vs-2019 "Windows ランタイム C++ テンプレートライブラリ (WRL) |Microsoft ドキュメント"  
[CppWindowsWalkthroughCreatingDesktopApplication]: /cpp/windows/walkthrough-creating-windows-desktop-applications-cpp?view=vs-2019 "チュートリアル: 従来の Windows デスクトップアプリケーションの作成 (C++) |Microsoft ドキュメント"  

[GithubMicrosoftedgeWebview2browser]: https://github.com/MicrosoftEdge/WebView2Browser "WebView2Browser-MicrosoftEdge/WebView2Browser |GitHub"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  

[GithubMicrosoftedgeWebview2samplesApisample]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/WebView2APISample "WebView2 API のサンプル-MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesGettingStartedGuide]: https://github.com/MicrosoftEdge/WebView2Samples#1-getting-started-guide "WebView2 サンプル-MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftWilMain]: https://github.com/Microsoft/wil "Windows 実装ライブラリ (WIL)-microsoft/WIL |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  

[MicrosoftVisualstudioMain]: https://visualstudio.microsoft.com "Visual Studio"  
