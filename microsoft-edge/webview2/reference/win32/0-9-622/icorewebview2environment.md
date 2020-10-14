---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2Environment
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2Environment
ms.openlocfilehash: edf573bc7c4c83c7882005937db29a068ab7b015
ms.sourcegitcommit: 2d57b515d6ccbbe24cb3a8c8f44f9c3a26fc17a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "11115786"
---
# <span data-ttu-id="14d82-104">インターフェイス ICoreWebView2Environment</span><span class="sxs-lookup"><span data-stu-id="14d82-104">interface ICoreWebView2Environment</span></span> 

```
interface ICoreWebView2Environment
  : public IUnknown
```

<span data-ttu-id="14d82-105">これは、WebView2 環境を表します。</span><span class="sxs-lookup"><span data-stu-id="14d82-105">This represents the WebView2 Environment.</span></span>

## <span data-ttu-id="14d82-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="14d82-106">Summary</span></span>

 <span data-ttu-id="14d82-107">Members</span><span class="sxs-lookup"><span data-stu-id="14d82-107">Members</span></span>                        | <span data-ttu-id="14d82-108">説明</span><span class="sxs-lookup"><span data-stu-id="14d82-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="14d82-109">add_NewBrowserVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="14d82-109">add_NewBrowserVersionAvailable</span></span>](#add_newbrowserversionavailable) | <span data-ttu-id="14d82-110">新しい参照サーバーの使用可能なイベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="14d82-110">Add an event handler for the NewBrowserVersionAvailable event.</span></span>
[<span data-ttu-id="14d82-111">CreateCoreWebView2Controller</span><span class="sxs-lookup"><span data-stu-id="14d82-111">CreateCoreWebView2Controller</span></span>](#createcorewebview2controller) | <span data-ttu-id="14d82-112">新しい WebView を非同期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="14d82-112">Asynchronously create a new WebView.</span></span>
[<span data-ttu-id="14d82-113">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="14d82-113">CreateWebResourceResponse</span></span>](#createwebresourceresponse) | <span data-ttu-id="14d82-114">新しい web リソース応答オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="14d82-114">Create a new web resource response object.</span></span>
[<span data-ttu-id="14d82-115">get_BrowserVersionString</span><span class="sxs-lookup"><span data-stu-id="14d82-115">get_BrowserVersionString</span></span>](#get_browserversionstring) | <span data-ttu-id="14d82-116">ICoreWebView2Environment が安定していない場合は、チャネル名を含む現在の[ICoreWebView2Environment]()のブラウザーバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="14d82-116">The browser version info of the current [ICoreWebView2Environment](), including channel name if it is not the stable channel.</span></span>
[<span data-ttu-id="14d82-117">remove_NewBrowserVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="14d82-117">remove_NewBrowserVersionAvailable</span></span>](#remove_newbrowserversionavailable) | <span data-ttu-id="14d82-118">Add_NewBrowserVersionAvailable で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="14d82-118">Remove an event handler previously added with add_NewBrowserVersionAvailable.</span></span>

<span data-ttu-id="14d82-119">WebViews は、環境パラメーターと共に指定したブラウザープロセスで実行され、環境から作成されたオブジェクトを同じ環境で使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="14d82-119">WebViews created from an environment run on the browser process specified with environment parameters and objects created from an environment should be used in the same environment.</span></span> <span data-ttu-id="14d82-120">異なる環境での使用は、互換性が保証されるとは限りません。また、失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="14d82-120">Using it in different environments are not guaranteed to be compatible and may fail.</span></span>

## <span data-ttu-id="14d82-121">Members</span><span class="sxs-lookup"><span data-stu-id="14d82-121">Members</span></span>

#### <span data-ttu-id="14d82-122">add_NewBrowserVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="14d82-122">add_NewBrowserVersionAvailable</span></span> 

<span data-ttu-id="14d82-123">新しい参照サーバーの使用可能なイベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="14d82-123">Add an event handler for the NewBrowserVersionAvailable event.</span></span>

> <span data-ttu-id="14d82-124">パブリック HRESULT [add_NewBrowserVersionAvailable](#add_newbrowserversionavailable)([ICoreWebView2NewBrowserVersionAvailableEventHandler](icorewebview2newbrowserversionavailableeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="14d82-124">public HRESULT [add_NewBrowserVersionAvailable](#add_newbrowserversionavailable)([ICoreWebView2NewBrowserVersionAvailableEventHandler](icorewebview2newbrowserversionavailableeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="14d82-125">最新バージョンの Edge ブラウザーがインストールされていて、WebView2 で使用できるようになったときに呼び出される新機能。</span><span class="sxs-lookup"><span data-stu-id="14d82-125">NewBrowserVersionAvailable fires when a newer version of the Edge browser is installed and available for use via WebView2.</span></span> <span data-ttu-id="14d82-126">新しいバージョンのブラウザーを使用するには、新しい環境と WebView を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14d82-126">To use the newer version of the browser you must create a new environment and WebView.</span></span> <span data-ttu-id="14d82-127">このイベントは、コードが実行されているのと同じエッジチャネルから新しいバージョンの場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="14d82-127">This event will only be fired for new version from the same Edge channel that the code is running from.</span></span> <span data-ttu-id="14d82-128">インストールされている Edge で実行されていない場合、イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="14d82-128">When not running with installed Edge, no event will be fired.</span></span>

<span data-ttu-id="14d82-129">ユーザーデータフォルダーは一度に1つのブラウザープロセスでしか使用できないため、WebViews で新しいバージョンのブラウザーを使用して同じユーザーデータフォルダーを使用する場合は、最初に古いバージョンのブラウザーを使用している環境と WebViews を閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="14d82-129">Because a user data folder can only be used by one browser process at a time, if you want to use the same user data folder in the WebViews using the new version of the browser, you must close the environment and WebViews that are using the older version of the browser first.</span></span> <span data-ttu-id="14d82-130">または、単に、アプリを再起動するようにユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="14d82-130">Or simply prompt the user to restart the app.</span></span>

```cpp
    // After the environment is successfully created,
    // register a handler for the NewBrowserVersionAvailable event.
    // This handler tells when there is a new Edge version available on the machine.
    CHECK_FAILURE(m_webViewEnvironment->add_NewBrowserVersionAvailable(
        Callback<ICoreWebView2NewBrowserVersionAvailableEventHandler>(
            [this](ICoreWebView2Environment* sender, IUnknown* args) -> HRESULT {
                std::wstring message = L"We detected there is a new version for the browser.";
                if (m_webView)
                {
                    message += L"Do you want to restart the app? \n\n";
                    message += L"Click No if you only want to re-create the webviews. \n";
                    message += L"Click Cancel for no action. \n";
                }
                int response = MessageBox(
                    m_mainWindow, message.c_str(), L"New available version",
                    m_webView ? MB_YESNOCANCEL : MB_OK);

                if (response == IDYES)
                {
                    RestartApp();
                }
                else if (response == IDNO)
                {
                    ReinitializeWebViewWithNewBrowser();
                }
                else
                {
                    // do nothing
                }

                return S_OK;
            })
            .Get(),
        nullptr));
```

#### <span data-ttu-id="14d82-131">CreateCoreWebView2Controller</span><span class="sxs-lookup"><span data-stu-id="14d82-131">CreateCoreWebView2Controller</span></span> 

<span data-ttu-id="14d82-132">新しい WebView を非同期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="14d82-132">Asynchronously create a new WebView.</span></span>

> <span data-ttu-id="14d82-133">パブリック HRESULT [CreateCoreWebView2Controller](#createcorewebview2controller)(HWND parentwindow、 [ICoreWebView2CreateCoreWebView2ControllerCompletedHandler](icorewebview2createcorewebview2controllercompletedhandler.md) \* handler)</span><span class="sxs-lookup"><span data-stu-id="14d82-133">public HRESULT [CreateCoreWebView2Controller](#createcorewebview2controller)(HWND parentWindow, [ICoreWebView2CreateCoreWebView2ControllerCompletedHandler](icorewebview2createcorewebview2controllercompletedhandler.md) \* handler)</span></span>

<span data-ttu-id="14d82-134">parentWindow は、WebView を表示して入力を受け取る HWND です。</span><span class="sxs-lookup"><span data-stu-id="14d82-134">parentWindow is the HWND in which the WebView should be displayed and from which receive input.</span></span> <span data-ttu-id="14d82-135">WebView は、WebView の作成中に、指定されたウィンドウに子ウィンドウを追加します。</span><span class="sxs-lookup"><span data-stu-id="14d82-135">The WebView will add a child window to the provided window during WebView creation.</span></span> <span data-ttu-id="14d82-136">兄弟ウィンドウの順序によって影響を受ける Z オーダーやその他の項目にも影響します。</span><span class="sxs-lookup"><span data-stu-id="14d82-136">Z-order and other things impacted by sibling window order will be affected accordingly.</span></span>

<span data-ttu-id="14d82-137">アプリケーションは、プロセスまたはアプリケーションウィンドウのアプリケーションユーザーモデル ID を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="14d82-137">It is recommended that the application set Application User Model ID for the process or the application window.</span></span> <span data-ttu-id="14d82-138">何も設定されていない場合は、WebView の作成中に、生成されたアプリケーションユーザーモデル ID が parentWindow のルートウィンドウに設定されます。</span><span class="sxs-lookup"><span data-stu-id="14d82-138">If none is set, during WebView creation a generated Application User Model ID is set to root window of parentWindow.</span></span> 
```cpp
// Create or recreate the WebView and its environment.
void AppWindow::InitializeWebView()
{
    // To ensure browser switches get applied correctly, we need to close
    // the existing WebView. This will result in a new browser process
    // getting created which will apply the browser switches.
    CloseWebView();
    m_dcompDevice = nullptr;
    m_wincompCompositor = nullptr;
    LPCWSTR subFolder = nullptr;

    if (m_creationModeId == IDM_CREATION_MODE_VISUAL_DCOMP ||
        m_creationModeId == IDM_CREATION_MODE_TARGET_DCOMP)
    {
        HRESULT hr = DCompositionCreateDevice2(nullptr, IID_PPV_ARGS(&m_dcompDevice));
        if (!SUCCEEDED(hr))
        {
            MessageBox(
                m_mainWindow,
                L"Attempting to create WebView using DComp Visual is not supported.\r\n"
                "DComp device creation failed.\r\n"
                "Current OS may not support DComp.",
                L"Create with Windowless DComp Visual Failed", MB_OK);
            return;
        }
    }
    else if (m_creationModeId == IDM_CREATION_MODE_VISUAL_WINCOMP)
    {
        HRESULT hr = TryCreateDispatcherQueue();
        if (!SUCCEEDED(hr))
        {
            MessageBox(
                m_mainWindow,
                L"Attempting to create WebView using WinComp Visual is not supported.\r\n"
                "WinComp compositor creation failed.\r\n"
                "Current OS may not support WinComp.",
                L"Create with Windowless WinComp Visual Failed", MB_OK);
            return;
        }
        m_wincompCompositor = winrtComp::Compositor();
    }
    auto options = Microsoft::WRL::Make<CoreWebView2EnvironmentOptions>();
    CHECK_FAILURE(options->put_AllowSingleSignOnUsingOSPrimaryAccount(
        m_AADSSOEnabled ? TRUE : FALSE));
    if (!m_language.empty())
        CHECK_FAILURE(options->put_Language(m_language.c_str()));
    HRESULT hr = CreateCoreWebView2EnvironmentWithOptions(
        subFolder, nullptr, options.Get(),
        Callback<ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler>(
            this, &AppWindow::OnCreateEnvironmentCompleted)
            .Get());
    if (!SUCCEEDED(hr))
    {
        if (hr == HRESULT_FROM_WIN32(ERROR_FILE_NOT_FOUND))
        {
            MessageBox(
                m_mainWindow,
                L"Couldn't find Edge installation. "
                "Do you have a version installed that's compatible with this "
                "WebView2 SDK version?",
                nullptr, MB_OK);
        }
        else
        {
            ShowFailure(hr, L"Failed to create webview environment");
        }
    }
}
// This is the callback passed to CreateWebViewEnvironmentWithOptions.
// Here we simply create the WebView.
HRESULT AppWindow::OnCreateEnvironmentCompleted(
    HRESULT result, ICoreWebView2Environment* environment)
{
    CHECK_FAILURE(result);
    m_webViewEnvironment = environment;

    auto webViewExperimentalEnvironment =
        m_webViewEnvironment.try_query<ICoreWebView2ExperimentalEnvironment>();
    if (webViewExperimentalEnvironment && (m_dcompDevice || m_wincompCompositor))
    {
        CHECK_FAILURE(webViewExperimentalEnvironment->CreateCoreWebView2CompositionController(
            m_mainWindow,
            Callback<
                ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler>(
                [this](
                    HRESULT result,
                    ICoreWebView2ExperimentalCompositionController* compositionController) -> HRESULT {
                    auto controller =
                        wil::com_ptr<ICoreWebView2ExperimentalCompositionController>(compositionController)
                            .query<ICoreWebView2Controller>();
                    return OnCreateCoreWebView2ControllerCompleted(result, controller.get());
                })
                .Get()));
    }
    else
    {
        CHECK_FAILURE(m_webViewEnvironment->CreateCoreWebView2Controller(
            m_mainWindow, Callback<ICoreWebView2CreateCoreWebView2ControllerCompletedHandler>(
                              this, &AppWindow::OnCreateCoreWebView2ControllerCompleted)
                              .Get()));
    }

    return S_OK;
}
```
 <span data-ttu-id="14d82-139">アプリが特定のインストールから WebView のエッジを使用していて、インストールがアンインストールされている場合に、アプリが再起動マネージャーのメッセージを処理して、アプリが、適切に再起動できるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="14d82-139">It is recommended that the application handles restart manager messages so that it can be restarted gracefully in the case when the app is using Edge for WebView from a certain installation and that installation is being uninstalled.</span></span> <span data-ttu-id="14d82-140">たとえば、ユーザーが Dev channel から Edge をインストールし、そのチャネルの端を使ってアプリをテストしている場合は、アプリを終了せずにそのチャネルから edge をアンインストールすると、アプリは再起動され、開発者チャネルのアンインストールが成功します。</span><span class="sxs-lookup"><span data-stu-id="14d82-140">For example, if a user installs Edge from Dev channel and opts to use Edge from that channel for testing the app, and then uninstalls Edge from that channel without closing the app, the app will be restarted to allow uninstallation of the dev channel to succeed.</span></span> 
```cpp
    case WM_QUERYENDSESSION:
    {
        // yes, we can shut down
        // Register how we might be restarted
        RegisterApplicationRestart(L"--restore", RESTART_NO_CRASH | RESTART_NO_HANG);
        *result = TRUE;
        return true;
    }
    break;
    case WM_ENDSESSION:
    {
        if (wParam == TRUE)
        {
            // save app state and exit.
            PostQuitMessage(0);
            return true;
        }
    }
    break;
```
 <span data-ttu-id="14d82-141">アプリケーションで障害が発生したときに CreateCoreWebView2Controller が再試行される場合は、新しい WebView2 環境の作成からアプリケーションを再起動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="14d82-141">When the application retries CreateCoreWebView2Controller upon failure, it is recommended that the application restarts from creating a new WebView2 Environment.</span></span> <span data-ttu-id="14d82-142">エッジ更新が発生した場合は、WebView2 環境に関連付けられているバージョンが削除され、オブジェクトが機能しなくなっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="14d82-142">If an Edge update happens, the version associated with a WebView2 Environment could have been removed and causing the object to no longer work.</span></span> <span data-ttu-id="14d82-143">新しい WebView2 環境の作成は、最新バージョンを使用することで動作します。</span><span class="sxs-lookup"><span data-stu-id="14d82-143">Creating a new WebView2 Environment will work as it uses the latest version.</span></span>

<span data-ttu-id="14d82-144">同じユーザーデータフォルダーを使って既に実行中のインスタンスがあり、環境オブジェクトの EnvironmentOptions が異なる場合、または HWND の親ウィンドウにさまざまな DPI の認識がある場合は、WebView の作成に失敗します。</span><span class="sxs-lookup"><span data-stu-id="14d82-144">WebView creation will fail if there is already a running instance using the same user data folder, and the Environment objects have different EnvironmentOptions or the HWND parentWindows have different DPI awareness.</span></span> <span data-ttu-id="14d82-145">たとえば、1つの言語で既に WebView が作成されている場合、同じユーザーデータフォルダーを使って別の言語で WebView を作成しようとすると、失敗します。</span><span class="sxs-lookup"><span data-stu-id="14d82-145">For example, if there is already a WebView created with one language, trying to create a WebView with a different language using the same user data folder will fail.</span></span>

#### <span data-ttu-id="14d82-146">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="14d82-146">CreateWebResourceResponse</span></span> 

<span data-ttu-id="14d82-147">新しい web リソース応答オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="14d82-147">Create a new web resource response object.</span></span>

> <span data-ttu-id="14d82-148">パブリック HRESULT [CreateWebResourceResponse](#createwebresourceresponse)(IStream \* content、int STATUSCODE、LPCWSTR の理由語句、LPCWSTR のヘッダー、 [ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* \* 応答)</span><span class="sxs-lookup"><span data-stu-id="14d82-148">public HRESULT [CreateWebResourceResponse](#createwebresourceresponse)(IStream \* content, int statusCode, LPCWSTR reasonPhrase, LPCWSTR headers, [ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \*\* response)</span></span>

<span data-ttu-id="14d82-149">ヘッダーは、改行で区切られた直接応答ヘッダー文字列です。</span><span class="sxs-lookup"><span data-stu-id="14d82-149">The headers is the raw response header string delimited by newline.</span></span> <span data-ttu-id="14d82-150">空のヘッダー文字列を使ってこのオブジェクトを作成し、 [ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) を使用してヘッダー行を1行ずつ作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="14d82-150">It's also possible to create this object with empty headers string and then use the [ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) to construct the headers line by line.</span></span> <span data-ttu-id="14d82-151">その他のパラメーターについては、「 [ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14d82-151">For information on other parameters see [ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md).</span></span>

```cpp
        if (m_blockImages)
        {
            m_webView->AddWebResourceRequestedFilter(L"*", COREWEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE);
            CHECK_FAILURE(m_webView->add_WebResourceRequested(
                Callback<ICoreWebView2WebResourceRequestedEventHandler>(
                    [this](
                        ICoreWebView2* sender,
                        ICoreWebView2WebResourceRequestedEventArgs* args) {
                        COREWEBVIEW2_WEB_RESOURCE_CONTEXT resourceContext;
                        CHECK_FAILURE(
                            args->get_ResourceContext(&resourceContext));
                        // Ensure that the type is image
                        if (resourceContext != COREWEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE)
                        {
                            return E_INVALIDARG;
                        }
                        // Override the response with an empty one to block the image.
                        // If put_Response is not called, the request will continue as normal.
                        wil::com_ptr<ICoreWebView2WebResourceResponse> response;
                        CHECK_FAILURE(m_webViewEnvironment->CreateWebResourceResponse(
                            nullptr, 403 /*NoContent*/, L"Blocked", L"", &response));
                        CHECK_FAILURE(args->put_Response(response.get()));
                        return S_OK;
                    })
                    .Get(),
                &m_webResourceRequestedTokenForImageBlocking));
        }
        else
        {
            CHECK_FAILURE(m_webView->remove_WebResourceRequested(
                m_webResourceRequestedTokenForImageBlocking));
        }
```

#### <span data-ttu-id="14d82-152">get_BrowserVersionString</span><span class="sxs-lookup"><span data-stu-id="14d82-152">get_BrowserVersionString</span></span> 

<span data-ttu-id="14d82-153">ICoreWebView2Environment が安定していない場合は、チャネル名を含む現在の[ICoreWebView2Environment]()のブラウザーバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="14d82-153">The browser version info of the current [ICoreWebView2Environment](), including channel name if it is not the stable channel.</span></span>

> <span data-ttu-id="14d82-154">パブリック HRESULT [get_BrowserVersionString](#get_browserversionstring)(LPWSTR \* versionInfo)</span><span class="sxs-lookup"><span data-stu-id="14d82-154">public HRESULT [get_BrowserVersionString](#get_browserversionstring)(LPWSTR \* versionInfo)</span></span>

<span data-ttu-id="14d82-155">これは、GetAvailableCoreWebView2BrowserVersionString API の形式と一致します。</span><span class="sxs-lookup"><span data-stu-id="14d82-155">This matches the format of the GetAvailableCoreWebView2BrowserVersionString API.</span></span> <span data-ttu-id="14d82-156">チャネル名は、"ベータ"、"dev"、"カナリア" のようになります。</span><span class="sxs-lookup"><span data-stu-id="14d82-156">Channel names are 'beta', 'dev', and 'canary'.</span></span>

```cpp
        wil::unique_cotaskmem_string version_info;
        m_webViewEnvironment->get_BrowserVersionString(&version_info);
        MessageBox(
            m_mainWindow, version_info.get(), L"Browser Version Info After WebView Creation",
            MB_OK);
```

#### <span data-ttu-id="14d82-157">remove_NewBrowserVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="14d82-157">remove_NewBrowserVersionAvailable</span></span> 

<span data-ttu-id="14d82-158">Add_NewBrowserVersionAvailable で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="14d82-158">Remove an event handler previously added with add_NewBrowserVersionAvailable.</span></span>

> <span data-ttu-id="14d82-159">パブリック HRESULT [remove_NewBrowserVersionAvailable](#remove_newbrowserversionavailable)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="14d82-159">public HRESULT [remove_NewBrowserVersionAvailable](#remove_newbrowserversionavailable)(EventRegistrationToken token)</span></span>

