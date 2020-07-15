---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2Environment
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 759c4a57e5ab099310c5f6d38f6777abcfc9fefa
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878534"
---
# <span data-ttu-id="d53ed-104">0.8.355-インターフェイス IWebView2Environment</span><span class="sxs-lookup"><span data-stu-id="d53ed-104">0.8.355 - interface IWebView2Environment</span></span> 

> [!NOTE]
> <span data-ttu-id="d53ed-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d53ed-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="d53ed-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d53ed-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2Environment
  : public IUnknown
```

<span data-ttu-id="d53ed-107">これは、WebView2 環境を表します。</span><span class="sxs-lookup"><span data-stu-id="d53ed-107">This represents the WebView2 Environment.</span></span>

## <span data-ttu-id="d53ed-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="d53ed-108">Summary</span></span>

 <span data-ttu-id="d53ed-109">Members</span><span class="sxs-lookup"><span data-stu-id="d53ed-109">Members</span></span>                        | <span data-ttu-id="d53ed-110">説明</span><span class="sxs-lookup"><span data-stu-id="d53ed-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d53ed-111">CreateWebView</span><span class="sxs-lookup"><span data-stu-id="d53ed-111">CreateWebView</span></span>](#createwebview) | <span data-ttu-id="d53ed-112">新しい[IWebView2WebView](IWebView2WebView.md)を非同期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="d53ed-112">Asynchronously create a new [IWebView2WebView](IWebView2WebView.md).</span></span>
[<span data-ttu-id="d53ed-113">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="d53ed-113">CreateWebResourceResponse</span></span>](#createwebresourceresponse) | <span data-ttu-id="d53ed-114">新しい web リソース応答オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d53ed-114">Create a new web resource response object.</span></span>

<span data-ttu-id="d53ed-115">WebViews は、環境パラメーターと共に指定したブラウザープロセスで実行され、環境から作成されたオブジェクトを同じ環境で使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d53ed-115">WebViews created from an environment run on the Browser process specified with environment parameters and objects created from an environment should be used in the same environment.</span></span> <span data-ttu-id="d53ed-116">異なる環境での使用は、互換性が保証されるとは限りません。また、失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d53ed-116">Using it in different environments are not guaranteed to be compatible and may fail.</span></span>

## <span data-ttu-id="d53ed-117">Members</span><span class="sxs-lookup"><span data-stu-id="d53ed-117">Members</span></span>

#### <span data-ttu-id="d53ed-118">CreateWebView</span><span class="sxs-lookup"><span data-stu-id="d53ed-118">CreateWebView</span></span> 

<span data-ttu-id="d53ed-119">新しい[IWebView2WebView](IWebView2WebView.md)を非同期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="d53ed-119">Asynchronously create a new [IWebView2WebView](IWebView2WebView.md).</span></span>

> <span data-ttu-id="d53ed-120">パブリック HRESULT [Createwebview](#createwebview)(HWND parentwindow、[IWebView2CreateWebViewCompletedHandler](IWebView2CreateWebViewCompletedHandler.md) \* handler)</span><span class="sxs-lookup"><span data-stu-id="d53ed-120">public HRESULT [CreateWebView](#createwebview)(HWND parentWindow,[IWebView2CreateWebViewCompletedHandler](IWebView2CreateWebViewCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="d53ed-121">parentWindow は、WebView を表示して入力を受け取る HWND です。</span><span class="sxs-lookup"><span data-stu-id="d53ed-121">parentWindow is the HWND in which the WebView should be displayed and from which receive input.</span></span> <span data-ttu-id="d53ed-122">WebView は、WebView の作成中に、指定されたウィンドウに子ウィンドウを追加します。</span><span class="sxs-lookup"><span data-stu-id="d53ed-122">The WebView will add a child window to the provided window during WebView creation.</span></span> <span data-ttu-id="d53ed-123">兄弟ウィンドウの順序によって影響を受ける Z オーダーやその他の項目にも影響します。</span><span class="sxs-lookup"><span data-stu-id="d53ed-123">Z-order and other things impacted by sibling window order will be affected accordingly.</span></span>

<span data-ttu-id="d53ed-124">アプリケーションは、プロセスまたはアプリケーションウィンドウのアプリケーションユーザーモデル ID を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d53ed-124">It is recommended that the application set Application User Model ID for the process or the application window.</span></span> <span data-ttu-id="d53ed-125">何も設定されていない場合は、WebView の作成中に、生成されたアプリケーションユーザーモデル ID が parentWindow のルートウィンドウに設定されます。</span><span class="sxs-lookup"><span data-stu-id="d53ed-125">If none is set, during WebView creation a generated Application User Model ID is set to root window of parentWindow.</span></span> 

```cpp
// Create or recreate the WebView and its environment.
void AppWindow::InitializeWebView(InitializeWebViewFlags webviewInitFlags)
{
    m_lastUsedInitFlags = webviewInitFlags;
    // To ensure browser switches get applied correctly, we need to close
    // the existing WebView. This will result in a new browser process
    // getting created which will apply the browser switches.
    CloseWebView();

    LPCWSTR subFolder = nullptr;
    LPCWSTR additionalBrowserSwitches = nullptr;
    HRESULT hr = CreateWebView2EnvironmentWithDetails(
        subFolder, nullptr, additionalBrowserSwitches,
        Callback<IWebView2CreateWebView2EnvironmentCompletedHandler>(
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
    HRESULT result, IWebView2Environment* environment)
{
    CHECK_FAILURE(result);

    CHECK_FAILURE(environment->QueryInterface(IID_PPV_ARGS(&m_webViewEnvironment)));
        CHECK_FAILURE(m_webViewEnvironment->CreateWebView(
            m_mainWindow, Callback<IWebView2CreateWebViewCompletedHandler>(
                              this, &AppWindow::OnCreateWebViewCompleted)
                              .Get()));
    return S_OK;
}
```

 <span data-ttu-id="d53ed-126">アプリが特定のインストールから webview のエッジを使用していて、インストールがアンインストールされている場合に、アプリが再起動マネージャーのメッセージを処理して、アプリが、適切に再起動できるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d53ed-126">It is recommended that the application handles restart manager messages so that it can be restarted gracefully in the case when the app is using Edge for webview from a certain installation and that installation is being uninstalled.</span></span> <span data-ttu-id="d53ed-127">たとえば、ユーザーが Dev channel から Edge をインストールし、そのチャネルの端を使ってアプリをテストしている場合は、アプリを終了せずにそのチャネルから edge をアンインストールすると、アプリは再起動され、開発者チャネルのアンインストールが成功します。</span><span class="sxs-lookup"><span data-stu-id="d53ed-127">For example, if a user installs Edge from Dev channel and opts to use Edge from that channel for testing the app, and then uninstalls Edge from that channel without closing the app, the app will be restarted to allow uninstallation of the dev channel to succeed.</span></span> 

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

#### <span data-ttu-id="d53ed-128">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="d53ed-128">CreateWebResourceResponse</span></span> 

<span data-ttu-id="d53ed-129">新しい web リソース応答オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d53ed-129">Create a new web resource response object.</span></span>

> <span data-ttu-id="d53ed-130">パブリック HRESULT [CreateWebResourceResponse](#createwebresourceresponse)(IStream \* content、int STATUSCODE、LPCWSTR の理由語句、LPCWSTR のヘッダー、[IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) \* \* 応答)</span><span class="sxs-lookup"><span data-stu-id="d53ed-130">public HRESULT [CreateWebResourceResponse](#createwebresourceresponse)(IStream \* content,int statusCode,LPCWSTR reasonPhrase,LPCWSTR headers,[IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) \*\* response)</span></span>

<span data-ttu-id="d53ed-131">ヘッダーは、改行で区切られた直接応答ヘッダー文字列です。</span><span class="sxs-lookup"><span data-stu-id="d53ed-131">The headers is the raw response header string delimited by newline.</span></span> <span data-ttu-id="d53ed-132">空のヘッダー文字列を使ってこのオブジェクトを作成し、 [IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md)を使用してヘッダー行を1行ずつ作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d53ed-132">It's also possible to create this object with empty headers string and then use the [IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md) to construct the headers line by line.</span></span> <span data-ttu-id="d53ed-133">その他のパラメーターについては、「 [IWebView2WebResourceResponse](IWebView2WebResourceResponse.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d53ed-133">For information on other parameters see [IWebView2WebResourceResponse](IWebView2WebResourceResponse.md).</span></span>

```cpp
        if (m_blockImages)
        {
            m_webView->AddWebResourceRequestedFilter(L"*", WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE);
            CHECK_FAILURE(m_webView->add_WebResourceRequested(
                Callback<IWebView2WebResourceRequestedEventHandler>(
                    [this](
                        IWebView2WebView* sender,
                        IWebView2WebResourceRequestedEventArgs* args) {
                        wil::com_ptr<IWebView2WebResourceRequestedEventArgs2>
                            webResourceEventArgs2;
                        args->QueryInterface(IID_PPV_ARGS(&webResourceEventArgs2));
                        WEBVIEW2_WEB_RESOURCE_CONTEXT resourceContext;
                        CHECK_FAILURE(
                            webResourceEventArgs2->get_ResourceContext(&resourceContext));
                        // Ensure that the type is image
                        if (resourceContext != WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE)
                        {
                            return E_INVALIDARG;
                        }
                        // Override the response with an empty one to block the image.
                        // If put_Response is not called, the request will continue as normal.
                        wil::com_ptr<IWebView2WebResourceResponse> response;
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

