---
description: Microsoft Edge WebView 2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリの Microsoft Edge WebView 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 0ab152e52b5e5d89cf493ff525ce53d9ab174e6d
ms.sourcegitcommit: 799fe63d961a37ada455bb36ef3ef0d8076e70bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2020
ms.locfileid: "10685681"
---
# <span data-ttu-id="e2412-104">WebView2 の概要 (開発者用プレビュー)</span><span class="sxs-lookup"><span data-stu-id="e2412-104">Getting Started with WebView2 (developer preview)</span></span>

<span data-ttu-id="e2412-105">このチュートリアルでは、 [WebView2](https://aka.ms/webview)のよく使われる機能について説明します。ここでは、最初の WebView2 アプリの作成について説明します。</span><span class="sxs-lookup"><span data-stu-id="e2412-105">This walkthrough goes over the commonly used functionalities of [WebView2 (developer preview)](https://aka.ms/webview) and gets you started on creating your first WebView2 app.</span></span> <span data-ttu-id="e2412-106">個々の Api について詳しくは、 [api リファレンス](../reference/win32/0-9-488-reference-webview2.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e2412-106">Visit [API reference](../reference/win32/0-9-488-reference-webview2.md) to learn more about individual APIs.</span></span>  

## <span data-ttu-id="e2412-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="e2412-107">Prerequisites</span></span>

* <span data-ttu-id="e2412-108">サポートされている OS (現在 Windows 10、Windows 8.1、Windows 7) には、 [Microsoft Edge (Chromium)](https://www.microsoftedgeinsider.com/download/)がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="e2412-108">[Microsoft Edge (Chromium)](https://www.microsoftedgeinsider.com/download/) installed on supported OS (currently Windows 10, Windows 8.1, and Windows 7).</span></span> <span data-ttu-id="e2412-109">**カナリアチャネルを使うことをお勧めします。最低限必要なバージョンは 82.0.488.0**です。</span><span class="sxs-lookup"><span data-stu-id="e2412-109">**We recommend using the Canary channel and the minimum required version is 82.0.488.0**.</span></span>
* <span data-ttu-id="e2412-110">[Visual Studio](https://visualstudio.microsoft.com/) 2015 以降、C++ サポートがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="e2412-110">[Visual Studio](https://visualstudio.microsoft.com/) 2015 or later with C++ support installed.</span></span>

## <span data-ttu-id="e2412-111">手順 1-単一ウィンドウの win32 アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="e2412-111">Step 1 - Create a single window win32 app</span></span>

<span data-ttu-id="e2412-112">最初に、1つのメインウィンドウを含む基本的なデスクトッププロジェクトを開始します。</span><span class="sxs-lookup"><span data-stu-id="e2412-112">We will start with a basic desktop project containing a single main window.</span></span> <span data-ttu-id="e2412-113">これは、このチュートリアルの主な焦点ではないため、 [「チュートリアル: 従来の Windows デスクトップアプリケーションを作成する (C++)](/cpp/windows/walkthrough-creating-windows-desktop-applications-cpp?view=vs-2019)」で説明した変更されたサンプルコードを使います。</span><span class="sxs-lookup"><span data-stu-id="e2412-113">As this is not the main focus of this walkthrough, we will simply use modified sample code from [Walkthrough: Create a traditional Windows Desktop application (C++)](/cpp/windows/walkthrough-creating-windows-desktop-applications-cpp?view=vs-2019).</span></span> <span data-ttu-id="e2412-114">更新されたサンプルを[ダウンロード](https://aka.ms/HelloWebView)して使い始めることができます。</span><span class="sxs-lookup"><span data-stu-id="e2412-114">[Download](https://aka.ms/HelloWebView) the modified sample to get started.</span></span>

<span data-ttu-id="e2412-115">Visual Studio で**WebView2GettingStarted**を開きます。</span><span class="sxs-lookup"><span data-stu-id="e2412-115">Open **WebView2GettingStarted.sln** in Visual Studio.</span></span> <span data-ttu-id="e2412-116">以前のバージョンの Visual Studio を使っている場合は、 **WebView2GettingStarted**プロジェクトを右クリックして、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2412-116">If you are using an older version of Visual Studio, right click on the **WebView2GettingStarted** project and click **Properties**.</span></span> <span data-ttu-id="e2412-117">[**構成プロパティ**  >  の**全般**] で、 **Windows sdk のバージョン**とプラットフォームの**ツールセット**を変更して、Win10 SDK と VS ツールセットを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e2412-117">Under **Configuration Properties** > **General**, modify **Windows SDK Version** and **Platform Toolset** to use the Win10 SDK and VS toolset available to you.</span></span>

![ツールバージョン](../media/tool-version.png)

<span data-ttu-id="e2412-119">Visual Studio では、WebView2 header ファイルが見つからないことが原因でいくつかのエラーが表示されることがあります。これは、ステップ2が完了した後に発生します。</span><span class="sxs-lookup"><span data-stu-id="e2412-119">Visual Studio may show some errors due to missing WebView2 header file, which should go away once Step 2 is completed.</span></span>

## <span data-ttu-id="e2412-120">手順 2-WebView2 SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="e2412-120">Step 2 - Install WebView2 SDK</span></span>

<span data-ttu-id="e2412-121">次に、WebView2 SDK をプロジェクトに追加してみましょう。</span><span class="sxs-lookup"><span data-stu-id="e2412-121">Now let's add the WebView2 SDK into the project.</span></span> <span data-ttu-id="e2412-122">開発者向けプレビューでは、Nuget を使って Win32 SDK をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="e2412-122">For the developer preview, you can install the Win32 SDK via Nuget.</span></span>

1. <span data-ttu-id="e2412-123">プロジェクトを右クリックし、[ **Nuget パッケージの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2412-123">Right click the project and click **Manage Nuget Packages**.</span></span>

    ![管理-nuget-パッケージ](../media/manage-nuget-packages.png)

2. <span data-ttu-id="e2412-125">検索バーに「 **ImplementationLibrary** 」と入力し、結果から**ImplementationLibrary**をクリックし、右側のウィンドウで [**インストール**] をクリックして、最新の SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e2412-125">Enter **Microsoft.Windows.ImplementationLibrary** in the search bar, click **Microsoft.Windows.ImplementationLibrary** from the results, and click **Install** inthe right hand side window and install the latest SDK.</span></span> <span data-ttu-id="e2412-126">Nuget は、お使いのコンピューターに SDK をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e2412-126">Nuget will download the SDK to your machine.</span></span> <span data-ttu-id="e2412-127">このチュートリアルでは、 [Windows 実装ライブラリ](https://github.com/Microsoft/wil)と[Windows ランタイム C++ テンプレートライブラリ](/cpp/cppcx/wrl/windows-runtime-cpp-template-library-wrl?view=vs-2019)を使って COM を簡単に操作できるようになっていますが、これらは完全にオプションです。</span><span class="sxs-lookup"><span data-stu-id="e2412-127">While we use [Windows Implementation Library](https://github.com/Microsoft/wil) and [Windows Runtime C++ Template Library](/cpp/cppcx/wrl/windows-runtime-cpp-template-library-wrl?view=vs-2019) to make working with COM easier in this walkthrough, they are completely optional.</span></span>

    ![wil](../media/wil.png)

3. <span data-ttu-id="e2412-129">検索バーに「 **WebView2** 」と入力し、結果から**WebView2**をクリックし、右側のウィンドウで [**インストール**] をクリックして、最新の SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e2412-129">Enter **Microsoft.Web.WebView2** in the search bar, click **Microsoft.Web.WebView2** from the results, and click **Install** in the right hand side window and install the latest SDK.</span></span> <span data-ttu-id="e2412-130">Nuget は、お使いのコンピューターに SDK をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e2412-130">Nuget will download the SDK to your machine.</span></span>

    ![nuget.exe](../media/nuget.png)

4. <span data-ttu-id="e2412-132">WebView2 ヘッダーを含めます。</span><span class="sxs-lookup"><span data-stu-id="e2412-132">Include the WebView2 header.</span></span> <span data-ttu-id="e2412-133">「**形式**」の .cpp で、s 行の下に追加し `#include "WebView2.h"` `#include` ます。</span><span class="sxs-lookup"><span data-stu-id="e2412-133">In **HelloWebView.cpp**, add `#include "WebView2.h"` below the lines of `#include`s.</span></span>

    ```cpp
    ...
    #include <wrl.h>
    #include <wil/com.h>
    // include WebView2 header
    #include "WebView2.h"
    ```

<span data-ttu-id="e2412-134">WebView2 API に対して使用およびビルドするように設定されています。</span><span class="sxs-lookup"><span data-stu-id="e2412-134">You are all set to use and build against the WebView2 API.</span></span> <span data-ttu-id="e2412-135">F5 キーを押して、サンプルアプリをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="e2412-135">Press F5 to build and run the sample app.</span></span> <span data-ttu-id="e2412-136">空のウィンドウが表示されたアプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2412-136">You should see an app displaying an empty window.</span></span>

![空-アプリ](../media/empty-app.png)

## <span data-ttu-id="e2412-138">手順 3-親ウィンドウ内に1つの WebView を作成する</span><span class="sxs-lookup"><span data-stu-id="e2412-138">Step 3 - Create a single WebView within the parent window</span></span>

<span data-ttu-id="e2412-139">次に、メインウィンドウに WebView を追加してみましょう。</span><span class="sxs-lookup"><span data-stu-id="e2412-139">Now let's add a WebView to the main window.</span></span> <span data-ttu-id="e2412-140">ここでは、環境を設定して、コントロールを電源投入している `CreateCoreWebView2Environment` Microsoft Edge (Chromium) ブラウザーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e2412-140">We'll use `CreateCoreWebView2Environment` to set up the environment and locate the Microsoft Edge (Chromium) browser powering the control.</span></span> <span data-ttu-id="e2412-141">`CreateCoreWebView2EnvironmentWithOptions`既定の設定を使用する代わりに、ブラウザーの場所、ユーザーフォルダー、ブラウザーのフラグなどを指定する場合にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2412-141">You can also use `CreateCoreWebView2EnvironmentWithOptions` if you want to specify browser location, user folder, browser flags, etc., instead of using the default setting.</span></span> <span data-ttu-id="e2412-142">が完了する `CreateCoreWebView2Environment` `ICoreWebView2Environment::CreateCoreWebView2Controller` と、コールバックと呼び出しの内部で呼び出し `ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler` て、 `ICoreWebView2Controller::get_CoreWebView2` 関連付けられた WebView を取得できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e2412-142">Upon the completion of `CreateCoreWebView2Environment`, you'll be able to call `ICoreWebView2Environment::CreateCoreWebView2Controller` inside the `ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler` callback and call `ICoreWebView2Controller::get_CoreWebView2` to get the associated WebView.</span></span>

<span data-ttu-id="e2412-143">コールバックでは、いくつかの設定も設定して、WebView のサイズを変更して親ウィンドウの100% を取得し、Bing に移動します。</span><span class="sxs-lookup"><span data-stu-id="e2412-143">In the callback, let's also set a few settings, resize the WebView to take 100% of the parent window, and navigate to Bing.</span></span>

<span data-ttu-id="e2412-144">以下のコードをとの間にある**形式の .cpp**にコピーし `// <-- WebView2 sample code starts here -->` `// <-- WebView2 sample code ends here -->` ます。</span><span class="sxs-lookup"><span data-stu-id="e2412-144">Copy the following code to **HelloWebView.cpp** between `// <-- WebView2 sample code starts here -->` and `// <-- WebView2 sample code ends here -->`.</span></span>

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
                // this is a redundant demo step as they are the default settings values
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

<span data-ttu-id="e2412-145">F5 キーを押して、アプリをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="e2412-145">Press F5 to build and run the app.</span></span> <span data-ttu-id="e2412-146">これで、Bing と表示された WebView ウィンドウができます。</span><span class="sxs-lookup"><span data-stu-id="e2412-146">Now you have a WebView window displaying Bing.</span></span>

![bing-ウィンドウ](../media/bing-window.png)

## <span data-ttu-id="e2412-148">ステップ 4-ナビゲーションイベント</span><span class="sxs-lookup"><span data-stu-id="e2412-148">Step 4 - Navigation events</span></span>

<span data-ttu-id="e2412-149">最後の手順では、URL への移動について説明しまし `ICoreWebView2::Navigate` た。</span><span class="sxs-lookup"><span data-stu-id="e2412-149">We already covered navigating to URL using `ICoreWebView2::Navigate` in the last step.</span></span> <span data-ttu-id="e2412-150">ナビゲーション中に、WebView は、、、、、の順にホストがリッスンできる一連のイベントを起動し `NavigationStarting` `SourceChanged` `ContentLoading` `HistoryChanged` `NavigationCompleted` ます。</span><span class="sxs-lookup"><span data-stu-id="e2412-150">During navigation, WebView fires a sequence of events that the host can listen to - `NavigationStarting`, `SourceChanged`, `ContentLoading`, `HistoryChanged`, and then `NavigationCompleted`.</span></span> <span data-ttu-id="e2412-151">詳細について[は、ここ](../reference/win32/0-9-488/ICoreWebView2.md#navigation-events)をクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="e2412-151">Click [here](../reference/win32/0-9-488/ICoreWebView2.md#navigation-events) to learn more.</span></span>

![ナビゲーション-イベント](../media/navigation-events.png)

<span data-ttu-id="e2412-153">エラーが発生した場合は、 `SourceChanged` `ContentLoading` `HistoryChanged` ナビゲーションがエラーページに続いているかどうかによって、、またはイベントが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e2412-153">In error cases there may or may not be `SourceChanged`, `ContentLoading`, or `HistoryChanged` event(s) depending on whether the navigation is continued to an error page.</span></span> <span data-ttu-id="e2412-154">HTTP リダイレクトの場合、 `NavigationStarting` 1 つの行に複数のイベントが存在します。</span><span class="sxs-lookup"><span data-stu-id="e2412-154">In case of an HTTP redirect, there will be multiple `NavigationStarting` events in a row.</span></span>

<span data-ttu-id="e2412-155">これらのイベントを利用する例として、 `NavigationStarting` https 以外の要求をキャンセルするためのハンドラーを登録してください。</span><span class="sxs-lookup"><span data-stu-id="e2412-155">As an example of utilizing those events, let's register a handler for `NavigationStarting` to cancel any non-https requests.</span></span> <span data-ttu-id="e2412-156">以下のコードを次の**形式**でコピーします。 `// Step 4 - Navigation events`</span><span class="sxs-lookup"><span data-stu-id="e2412-156">Copy the following code to **HelloWebView.cpp** below `// Step 4 - Navigation events`.</span></span>

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

<span data-ttu-id="e2412-157">これで、アプリは https 以外のサイトに移動しません。</span><span class="sxs-lookup"><span data-stu-id="e2412-157">Now the app will not navigate to any non-https sites.</span></span> <span data-ttu-id="e2412-158">同様のメカニズムを使って、独自のドメイン内でのナビゲーションの制限など、他のタスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="e2412-158">You can use similar mechanism to accomplish other tasks, such as restricting navigation to within your own domain.</span></span>

## <span data-ttu-id="e2412-159">手順 5-スクリプト</span><span class="sxs-lookup"><span data-stu-id="e2412-159">Step 5 - Scripting</span></span>

<span data-ttu-id="e2412-160">ホストアプリでは、JavaScript を WebView に挿入することもできます。</span><span class="sxs-lookup"><span data-stu-id="e2412-160">The hosting app can also inject JavaScript into WebView.</span></span> <span data-ttu-id="e2412-161">タスク WebView は、任意の JavaScript の実行や初期化スクリプトの追加を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e2412-161">You can task WebView to execute arbitrary JavaScript or add initialization scripts.</span></span> <span data-ttu-id="e2412-162">追加された初期化スクリプトは、削除されるまでのすべての上位レベルのドキュメントと子フレームのナビゲーションに適用され、グローバルオブジェクトが作成された後で、その HTML ドキュメントに含まれている他のスクリプトが実行される前に実行されます。</span><span class="sxs-lookup"><span data-stu-id="e2412-162">Added initialization scripts apply to all future top level document and child frame navigation until removed, and run after the global object has been created and before any other script included by the HTML document is executed.</span></span>

<span data-ttu-id="e2412-163">以下のコードをコピー `// Step 5 - Scripting` します。</span><span class="sxs-lookup"><span data-stu-id="e2412-163">Copy the following code below `// Step 5 - Scripting`.</span></span>

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

<span data-ttu-id="e2412-164">これで、WebView は常にオブジェクトオブジェクトを固定し、ページドキュメントを1回返します。</span><span class="sxs-lookup"><span data-stu-id="e2412-164">Now WebView will always freeze the Object object and return the page document once.</span></span>

**<span data-ttu-id="e2412-165">これらのスクリプトインジェクション Api (およびその他のいくつかの WebView2 Api) は非同期であることに注意してください。特定の順序でコードを実行する場合は、コールバックを使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2412-165">Note that these script injection APIs (and some other WebView2 APIs) are asynchronous, you should use callbacks if code is to be executed in a particular order.</span></span>**

## <span data-ttu-id="e2412-166">ステップ 6-ホストと web コンテンツ間の通信</span><span class="sxs-lookup"><span data-stu-id="e2412-166">Step 6 - Communication between host and web content</span></span>

<span data-ttu-id="e2412-167">ホストと web コンテンツも相互に通信でき `postMessage` ます。</span><span class="sxs-lookup"><span data-stu-id="e2412-167">The host and the web content can also communicate with each other through `postMessage`.</span></span> <span data-ttu-id="e2412-168">WebView 内で実行されている web コンテンツは、ホストに送信でき `window.chrome.webview.postMessage` ます。また、メッセージはホストに登録されているすべてのメッセージによって処理され `ICoreWebView2WebMessageReceivedEventHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="e2412-168">The web content running within a WebView can post to the host through `window.chrome.webview.postMessage`, and the message would be handled by any registered `ICoreWebView2WebMessageReceivedEventHandler` on the host.</span></span> <span data-ttu-id="e2412-169">同様に、またはを通じて web コンテンツにメッセージを送信することもでき `ICoreWebView2::PostWebMessageAsString` `ICoreWebView2::PostWebMessageAsJSON` ます。これは、から追加されたハンドラーによって検出され `window.chrome.webview.addEventListener` ます。</span><span class="sxs-lookup"><span data-stu-id="e2412-169">Likewise, the host can message the web content through `ICoreWebView2::PostWebMessageAsString` or `ICoreWebView2::PostWebMessageAsJSON`, which would be caught by handlers added from `window.chrome.webview.addEventListener`.</span></span> <span data-ttu-id="e2412-170">通信メカニズムにより、web コンテンツは、ネイティブ Api を呼び出すように指示するメッセージを渡すことによってネイティブ機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="e2412-170">The communication mechanism allows the web content to utilize native capabilities by passing messages to ask the host to call native APIs.</span></span>

<span data-ttu-id="e2412-171">このメカニズムを理解するための例として、WebView でドキュメントの URL を少し detour で印刷してみましょう。</span><span class="sxs-lookup"><span data-stu-id="e2412-171">As an example to understand the mechanism, let's try printing out the document URL in WebView with a little detour,</span></span>

1. <span data-ttu-id="e2412-172">ホストは、受信したメッセージを web コンテンツに戻すためのハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="e2412-172">the host registers a handler to return received message back to the web content</span></span>
2. <span data-ttu-id="e2412-173">ホストは、ホストからメッセージを印刷するためのハンドラーを登録する web コンテンツにスクリプトを挿入します。</span><span class="sxs-lookup"><span data-stu-id="e2412-173">the host injects a script to the web content that registers a handler to print message from the host</span></span>
3. <span data-ttu-id="e2412-174">ホストは、URL をホストにポストする web コンテンツにスクリプトを挿入します。</span><span class="sxs-lookup"><span data-stu-id="e2412-174">the host injects a script to the web content that posts the URL to the host</span></span>
4. <span data-ttu-id="e2412-175">ホストのハンドラーがトリガーされ、web コンテンツへのメッセージ (URL) が返されます。</span><span class="sxs-lookup"><span data-stu-id="e2412-175">the host's handler is triggered and returns the message (the URL) to the web content</span></span>
5. <span data-ttu-id="e2412-176">web コンテンツのハンドラーがトリガーされ、ホストのメッセージ (URL) が出力されます。</span><span class="sxs-lookup"><span data-stu-id="e2412-176">the web content's handler is triggered and prints the host's message (the URL)</span></span>

<span data-ttu-id="e2412-177">以下のコードをコピーします。 `// Step 6 - Communication between host and web content`</span><span class="sxs-lookup"><span data-stu-id="e2412-177">Copy the following code below `// Step 6 - Communication between host and web content`,</span></span>

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

<span data-ttu-id="e2412-178">F5 キーを押して、アプリをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="e2412-178">Press F5 to build and run the app.</span></span> <span data-ttu-id="e2412-179">これで、ページに移動する前に Url が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e2412-179">It will now show URLs before navigating to pages.</span></span>

![表示-url](../media/show-url.png)

<span data-ttu-id="e2412-181">おめでとうございます。最初の WebView2 アプリを作成しました。</span><span class="sxs-lookup"><span data-stu-id="e2412-181">Congratulations, you've just built your first WebView2 app!</span></span>

## <span data-ttu-id="e2412-182">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e2412-182">Next Steps</span></span>

<span data-ttu-id="e2412-183">このチュートリアルではカバーされていない WebView2 の機能が多数あります。</span><span class="sxs-lookup"><span data-stu-id="e2412-183">There are plenty of WebView2 functionalities that are not covered in this walkthrough.</span></span>

<span data-ttu-id="e2412-184">詳細は次のページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e2412-184">To learn more:</span></span>

* <span data-ttu-id="e2412-185">WebView2's 機能の包括的な例については、「チェックアウト[WEBVIEW2 API のサンプル](https://github.com/MicrosoftEdge/WebView2Samples/tree/master/WebView2APISample)」をお探しください。</span><span class="sxs-lookup"><span data-stu-id="e2412-185">Checkout [WebView2 API Sample](https://github.com/MicrosoftEdge/WebView2Samples/tree/master/WebView2APISample) for a comprehensive example of WebView2's capabilities.</span></span>
* <span data-ttu-id="e2412-186">WebView2 を使って構築されたアプリケーションをチェックアウト[WebView2Browser](https://github.com/MicrosoftEdge/WebView2Browser)します。</span><span class="sxs-lookup"><span data-stu-id="e2412-186">Checkout [WebView2Browser](https://github.com/MicrosoftEdge/WebView2Browser) an application built using WebView2.</span></span>
* <span data-ttu-id="e2412-187">Api に関する詳細については、api[リファレンスを参照](../reference/win32/0-9-488-reference-webview2.md)してください。</span><span class="sxs-lookup"><span data-stu-id="e2412-187">Please explore [API reference](../reference/win32/0-9-488-reference-webview2.md) for detailed information about our API.</span></span>  

## <span data-ttu-id="e2412-188">WebView2 チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="e2412-188">Getting in touch with the WebView2 team</span></span>  

<span data-ttu-id="e2412-189">フィードバックを共有することで、より充実した WebView2 エクスペリエンスを構築できます。</span><span class="sxs-lookup"><span data-stu-id="e2412-189">Help us build a richer WebView2 experience by sharing your feedback!</span></span> <span data-ttu-id="e2412-190">[フィードバックリポジトリ](https://aka.ms/webviewfeedback)にアクセスして、機能要求またはバグレポートを送信するか、既知の問題を検索します。</span><span class="sxs-lookup"><span data-stu-id="e2412-190">Visit our [feedback repo](https://aka.ms/webviewfeedback) to submit feature requests or bug reports or search for known issues.</span></span>
