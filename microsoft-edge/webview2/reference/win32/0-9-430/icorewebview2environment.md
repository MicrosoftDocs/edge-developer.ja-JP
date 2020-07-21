---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2Environment
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: ea9234bf666840e6b87dd9827747d11ef74eb4c7
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884205"
---
# <span data-ttu-id="580c8-104">0.9.430-インターフェイス ICoreWebView2Environment</span><span class="sxs-lookup"><span data-stu-id="580c8-104">0.9.430 - interface ICoreWebView2Environment</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2Environment
  : public IUnknown
```

<span data-ttu-id="580c8-105">これは、WebView2 環境を表します。</span><span class="sxs-lookup"><span data-stu-id="580c8-105">This represents the WebView2 Environment.</span></span>

## <span data-ttu-id="580c8-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="580c8-106">Summary</span></span>

 <span data-ttu-id="580c8-107">Members</span><span class="sxs-lookup"><span data-stu-id="580c8-107">Members</span></span>                        | <span data-ttu-id="580c8-108">説明</span><span class="sxs-lookup"><span data-stu-id="580c8-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="580c8-109">CreateCoreWebView2Host</span><span class="sxs-lookup"><span data-stu-id="580c8-109">CreateCoreWebView2Host</span></span>](#createcorewebview2host) | <span data-ttu-id="580c8-110">新しい WebView を非同期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="580c8-110">Asynchronously create a new WebView.</span></span>
[<span data-ttu-id="580c8-111">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="580c8-111">CreateWebResourceResponse</span></span>](#createwebresourceresponse) | <span data-ttu-id="580c8-112">新しい web リソース応答オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="580c8-112">Create a new web resource response object.</span></span>
[<span data-ttu-id="580c8-113">get_BrowserVersionInfo</span><span class="sxs-lookup"><span data-stu-id="580c8-113">get_BrowserVersionInfo</span></span>](#get_browserversioninfo) | <span data-ttu-id="580c8-114">ICoreWebView2Environment が安定していない場合は、チャネル名を含む現在の[ICoreWebView2Environment]()のブラウザーバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="580c8-114">The browser version info of the current [ICoreWebView2Environment](), including channel name if it is not the stable channel.</span></span>
[<span data-ttu-id="580c8-115">add_NewBrowserVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="580c8-115">add_NewBrowserVersionAvailable</span></span>](#add_newbrowserversionavailable) | <span data-ttu-id="580c8-116">新しいバージョンの Edge ブラウザーがインストールされていて、WebView2 経由で使用できるようになったときに、Newfactorserver Available イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="580c8-116">The NewBrowserVersionAvailable event fires when a newer version of the Edge browser is installed and available to use via WebView2.</span></span>
[<span data-ttu-id="580c8-117">remove_NewBrowserVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="580c8-117">remove_NewBrowserVersionAvailable</span></span>](#remove_newbrowserversionavailable) | <span data-ttu-id="580c8-118">Add_NewBrowserVersionAvailable で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="580c8-118">Remove an event handler previously added with add_NewBrowserVersionAvailable.</span></span>

<span data-ttu-id="580c8-119">WebViews は、環境パラメーターと共に指定したブラウザープロセスで実行され、環境から作成されたオブジェクトを同じ環境で使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="580c8-119">WebViews created from an environment run on the Browser process specified with environment parameters and objects created from an environment should be used in the same environment.</span></span> <span data-ttu-id="580c8-120">異なる環境での使用は、互換性が保証されるとは限りません。また、失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="580c8-120">Using it in different environments are not guaranteed to be compatible and may fail.</span></span>

## <span data-ttu-id="580c8-121">Members</span><span class="sxs-lookup"><span data-stu-id="580c8-121">Members</span></span>

#### <span data-ttu-id="580c8-122">CreateCoreWebView2Host</span><span class="sxs-lookup"><span data-stu-id="580c8-122">CreateCoreWebView2Host</span></span> 

<span data-ttu-id="580c8-123">新しい WebView を非同期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="580c8-123">Asynchronously create a new WebView.</span></span>

> <span data-ttu-id="580c8-124">パブリック HRESULT [CreateCoreWebView2Host](#createcorewebview2host)(HWND parentwindow、[ICoreWebView2CreateCoreWebView2HostCompletedHandler](ICoreWebView2CreateCoreWebView2HostCompletedHandler.md) \* handler)</span><span class="sxs-lookup"><span data-stu-id="580c8-124">public HRESULT [CreateCoreWebView2Host](#createcorewebview2host)(HWND parentWindow,[ICoreWebView2CreateCoreWebView2HostCompletedHandler](ICoreWebView2CreateCoreWebView2HostCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="580c8-125">parentWindow は、WebView を表示して入力を受け取る HWND です。</span><span class="sxs-lookup"><span data-stu-id="580c8-125">parentWindow is the HWND in which the WebView should be displayed and from which receive input.</span></span> <span data-ttu-id="580c8-126">WebView は、WebView の作成中に、指定されたウィンドウに子ウィンドウを追加します。</span><span class="sxs-lookup"><span data-stu-id="580c8-126">The WebView will add a child window to the provided window during WebView creation.</span></span> <span data-ttu-id="580c8-127">兄弟ウィンドウの順序によって影響を受ける Z オーダーやその他の項目にも影響します。</span><span class="sxs-lookup"><span data-stu-id="580c8-127">Z-order and other things impacted by sibling window order will be affected accordingly.</span></span>

<span data-ttu-id="580c8-128">アプリケーションは、プロセスまたはアプリケーションウィンドウのアプリケーションユーザーモデル ID を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="580c8-128">It is recommended that the application set Application User Model ID for the process or the application window.</span></span> <span data-ttu-id="580c8-129">何も設定されていない場合は、WebView の作成中に、生成されたアプリケーションユーザーモデル ID が parentWindow のルートウィンドウに設定されます。</span><span class="sxs-lookup"><span data-stu-id="580c8-129">If none is set, during WebView creation a generated Application User Model ID is set to root window of parentWindow.</span></span> 

```cpp
// Create or recreate the WebView and its environment.
void AppWindow::InitializeWebView()
{
    // To ensure browser switches get applied correctly, we need to close
    // the existing WebView. This will result in a new browser process
    // getting created which will apply the browser switches.
    CloseWebView();

    LPCWSTR subFolder = nullptr;
    LPCWSTR additionalBrowserSwitches = nullptr;
    HRESULT hr = CreateCoreWebView2EnvironmentWithDetails(
        subFolder, nullptr, additionalBrowserSwitches,
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

// This is the callback passed to CreateWebViewEnvironmnetWithDetails.
// Here we simply create the WebView.
HRESULT AppWindow::OnCreateEnvironmentCompleted(
    HRESULT result, ICoreWebView2Environment* environment)
{
    CHECK_FAILURE(result);

    CHECK_FAILURE(environment->QueryInterface(IID_PPV_ARGS(&m_webViewEnvironment)));
        CHECK_FAILURE(m_webViewEnvironment->CreateCoreWebView2Host(
            m_mainWindow, Callback<ICoreWebView2CreateCoreWebView2HostCompletedHandler>(
                              this, &AppWindow::OnCreateCoreWebView2HostCompleted)
                              .Get()));
    return S_OK;
}
```

 <span data-ttu-id="580c8-130">アプリが特定のインストールから webview のエッジを使用していて、インストールがアンインストールされている場合に、アプリが再起動マネージャーのメッセージを処理して、アプリが、適切に再起動できるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="580c8-130">It is recommended that the application handles restart manager messages so that it can be restarted gracefully in the case when the app is using Edge for webview from a certain installation and that installation is being uninstalled.</span></span> <span data-ttu-id="580c8-131">たとえば、ユーザーが Dev channel から Edge をインストールし、そのチャネルの端を使ってアプリをテストしている場合は、アプリを終了せずにそのチャネルから edge をアンインストールすると、アプリは再起動され、開発者チャネルのアンインストールが成功します。</span><span class="sxs-lookup"><span data-stu-id="580c8-131">For example, if a user installs Edge from Dev channel and opts to use Edge from that channel for testing the app, and then uninstalls Edge from that channel without closing the app, the app will be restarted to allow uninstallation of the dev channel to succeed.</span></span> 

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

#### <span data-ttu-id="580c8-132">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="580c8-132">CreateWebResourceResponse</span></span> 

<span data-ttu-id="580c8-133">新しい web リソース応答オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="580c8-133">Create a new web resource response object.</span></span>

> <span data-ttu-id="580c8-134">パブリック HRESULT [CreateWebResourceResponse](#createwebresourceresponse)(IStream \* content、int STATUSCODE、LPCWSTR の理由語句、LPCWSTR のヘッダー、[ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \* \* 応答)</span><span class="sxs-lookup"><span data-stu-id="580c8-134">public HRESULT [CreateWebResourceResponse](#createwebresourceresponse)(IStream \* content,int statusCode,LPCWSTR reasonPhrase,LPCWSTR headers,[ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \*\* response)</span></span>

<span data-ttu-id="580c8-135">ヘッダーは、改行で区切られた直接応答ヘッダー文字列です。</span><span class="sxs-lookup"><span data-stu-id="580c8-135">The headers is the raw response header string delimited by newline.</span></span> <span data-ttu-id="580c8-136">空のヘッダー文字列を使ってこのオブジェクトを作成し、 [ICoreWebView2HttpResponseHeaders](ICoreWebView2HttpResponseHeaders.md)を使用してヘッダー行を1行ずつ作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="580c8-136">It's also possible to create this object with empty headers string and then use the [ICoreWebView2HttpResponseHeaders](ICoreWebView2HttpResponseHeaders.md) to construct the headers line by line.</span></span> <span data-ttu-id="580c8-137">その他のパラメーターについては、「 [ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="580c8-137">For information on other parameters see [ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md).</span></span>

```cpp
        if (m_blockImages)
        {
            m_webView->AddWebResourceRequestedFilter(L"*", CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE);
            CHECK_FAILURE(m_webView->add_WebResourceRequested(
                Callback<ICoreWebView2WebResourceRequestedEventHandler>(
                    [this](
                        ICoreWebView2* sender,
                        ICoreWebView2WebResourceRequestedEventArgs* args) {
                        CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT resourceContext;
                        CHECK_FAILURE(
                            args->get_ResourceContext(&resourceContext));
                        // Ensure that the type is image
                        if (resourceContext != CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE)
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

#### <span data-ttu-id="580c8-138">get_BrowserVersionInfo</span><span class="sxs-lookup"><span data-stu-id="580c8-138">get_BrowserVersionInfo</span></span> 

<span data-ttu-id="580c8-139">ICoreWebView2Environment が安定していない場合は、チャネル名を含む現在の[ICoreWebView2Environment]()のブラウザーバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="580c8-139">The browser version info of the current [ICoreWebView2Environment](), including channel name if it is not the stable channel.</span></span>

> <span data-ttu-id="580c8-140">パブリック HRESULT [get_BrowserVersionInfo](#get_browserversioninfo)(LPWSTR \* versionInfo)</span><span class="sxs-lookup"><span data-stu-id="580c8-140">public HRESULT [get_BrowserVersionInfo](#get_browserversioninfo)(LPWSTR \* versionInfo)</span></span>

<span data-ttu-id="580c8-141">これは、GetCoreWebView2BrowserVersionInfo API の形式と一致します。</span><span class="sxs-lookup"><span data-stu-id="580c8-141">This matches the format of the GetCoreWebView2BrowserVersionInfo API.</span></span> <span data-ttu-id="580c8-142">チャネル名は、"ベータ"、"dev"、"カナリア" のようになります。</span><span class="sxs-lookup"><span data-stu-id="580c8-142">Channel names are 'beta', 'dev', and 'canary'.</span></span>

```cpp
        wil::unique_cotaskmem_string version_info;
        m_webViewEnvironment->get_BrowserVersionInfo(&version_info);
        MessageBox(
            m_mainWindow, version_info.get(), L"Browser Version Info After WebView Creation",
            MB_OK);
```

#### <span data-ttu-id="580c8-143">add_NewBrowserVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="580c8-143">add_NewBrowserVersionAvailable</span></span> 

<span data-ttu-id="580c8-144">新しいバージョンの Edge ブラウザーがインストールされていて、WebView2 経由で使用できるようになったときに、Newfactorserver Available イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="580c8-144">The NewBrowserVersionAvailable event fires when a newer version of the Edge browser is installed and available to use via WebView2.</span></span>

> <span data-ttu-id="580c8-145">パブリック HRESULT [add_NewBrowserVersionAvailable](#add_newbrowserversionavailable)([ICoreWebView2NewBrowserVersionAvailableEventHandler](ICoreWebView2NewBrowserVersionAvailableEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="580c8-145">public HRESULT [add_NewBrowserVersionAvailable](#add_newbrowserversionavailable)([ICoreWebView2NewBrowserVersionAvailableEventHandler](ICoreWebView2NewBrowserVersionAvailableEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="580c8-146">新しいバージョンのブラウザーを使用するには、新しい環境と WebView を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="580c8-146">To use the newer version of the browser you must create a new environment and WebView.</span></span> <span data-ttu-id="580c8-147">このイベントは、コードが実行されているのと同じエッジチャネルから新しいバージョンの場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="580c8-147">This event will only be fired for new version from the same Edge channel that the code is running from.</span></span> <span data-ttu-id="580c8-148">インストールされている Edge で実行されていない場合、イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="580c8-148">When not running with installed Edge, no event will be fired.</span></span>

<span data-ttu-id="580c8-149">ユーザーデータフォルダーは一度に1つのブラウザープロセスでしか使用できないため、WebViews で新しいバージョンのブラウザーを使用して同じユーザーデータフォルダーを使用する場合は、最初に古いバージョンのブラウザーを使用している環境と WebViews を閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="580c8-149">Because a user data folder can only be used by one browser process at a time, if you want to use the same user data folder in the WebViews using the new version of the browser, you must close the environment and WebViews that are using the older version of the browser first.</span></span> <span data-ttu-id="580c8-150">または、単に、アプリを再起動するようにユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="580c8-150">Or simply prompt the user to restart the app.</span></span>

```cpp
    // After the environment is successfully created,
    // register a handler for the NewBrowserVersionAvailable event.
    // This handler tells when there is a new Edge version available on the machine.
    CHECK_FAILURE(m_webViewEnvironment->add_NewBrowserVersionAvailable(
        Callback<ICoreWebView2NewBrowserVersionAvailableEventHandler>(
            [this](
                ICoreWebView2Environment* sender,
                ICoreWebView2NewBrowserVersionAvailableEventArgs* args) -> HRESULT {
                // Get the version value from args
                wil::unique_cotaskmem_string newVersion;
                CHECK_FAILURE(args->get_NewVersion(&newVersion));
                std::wstring message = L"We detected there is a new version for the browser.";
                message += L"\n\nVersion number: ";
                message += newVersion.get();
                message += L"\n\n";
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

#### <span data-ttu-id="580c8-151">remove_NewBrowserVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="580c8-151">remove_NewBrowserVersionAvailable</span></span> 

<span data-ttu-id="580c8-152">Add_NewBrowserVersionAvailable で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="580c8-152">Remove an event handler previously added with add_NewBrowserVersionAvailable.</span></span>

> <span data-ttu-id="580c8-153">パブリック HRESULT [remove_NewBrowserVersionAvailable](#remove_newbrowserversionavailable)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="580c8-153">public HRESULT [remove_NewBrowserVersionAvailable](#remove_newbrowserversionavailable)(EventRegistrationToken token)</span></span>

