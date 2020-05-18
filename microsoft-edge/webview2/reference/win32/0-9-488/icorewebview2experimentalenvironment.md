---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 4adfa6fa899ce5079f9a1dc2cad78673d2cc899d
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654467"
---
# <span data-ttu-id="9ec42-104">インターフェイス ICoreWebView2ExperimentalEnvironment</span><span class="sxs-lookup"><span data-stu-id="9ec42-104">interface ICoreWebView2ExperimentalEnvironment</span></span> 

> [!NOTE]
> <span data-ttu-id="9ec42-105">これは、プレリリース SDK バージョン0.9.488 に同梱されている実験的な API です。</span><span class="sxs-lookup"><span data-stu-id="9ec42-105">This an experimental API that is shipped with our prerelease SDK version 0.9.488.</span></span>

```
interface ICoreWebView2ExperimentalEnvironment
  : public IUnknown
```

<span data-ttu-id="9ec42-106">このインターフェイスは、 [ICoreWebView2Environment](icorewebview2environment.md)の拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="9ec42-106">This interface is an extension of the [ICoreWebView2Environment](icorewebview2environment.md).</span></span>

## <span data-ttu-id="9ec42-107">まとめ</span><span class="sxs-lookup"><span data-stu-id="9ec42-107">Summary</span></span>

 <span data-ttu-id="9ec42-108">Members</span><span class="sxs-lookup"><span data-stu-id="9ec42-108">Members</span></span>                        | <span data-ttu-id="9ec42-109">説明</span><span class="sxs-lookup"><span data-stu-id="9ec42-109">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9ec42-110">CreateCoreWebView2CompositionController</span><span class="sxs-lookup"><span data-stu-id="9ec42-110">CreateCoreWebView2CompositionController</span></span>](#createcorewebview2compositioncontroller) | <span data-ttu-id="9ec42-111">ビジュアルホスティングで使用する新しい WebView を非同期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="9ec42-111">Asynchronously create a new WebView for use with visual hosting.</span></span>
[<span data-ttu-id="9ec42-112">CreateCoreWebView2PointerInfo</span><span class="sxs-lookup"><span data-stu-id="9ec42-112">CreateCoreWebView2PointerInfo</span></span>](#createcorewebview2pointerinfo) | <span data-ttu-id="9ec42-113">空の[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)を作成します。</span><span class="sxs-lookup"><span data-stu-id="9ec42-113">Create an empty [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md).</span></span>
[<span data-ttu-id="9ec42-114">GetProviderForHwnd</span><span class="sxs-lookup"><span data-stu-id="9ec42-114">GetProviderForHwnd</span></span>](#getproviderforhwnd) | <span data-ttu-id="9ec42-115">指定された HWND に対応する ICoreWebView2CompositionController の UI オートメーションプロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="9ec42-115">Returns the UI Automation Provider for the ICoreWebView2CompositionController that corresponds with the given HWND.</span></span>

<span data-ttu-id="9ec42-116">[ICoreWebView2ExperimentalEnvironment]()インターフェイスを実装するオブジェクトも[ICoreWebView2Environment](icorewebview2environment.md)を実装します。</span><span class="sxs-lookup"><span data-stu-id="9ec42-116">An object implementing the [ICoreWebView2ExperimentalEnvironment]() interface will also implement [ICoreWebView2Environment](icorewebview2environment.md).</span></span>

## <span data-ttu-id="9ec42-117">Members</span><span class="sxs-lookup"><span data-stu-id="9ec42-117">Members</span></span>

#### <span data-ttu-id="9ec42-118">CreateCoreWebView2CompositionController</span><span class="sxs-lookup"><span data-stu-id="9ec42-118">CreateCoreWebView2CompositionController</span></span> 

<span data-ttu-id="9ec42-119">ビジュアルホスティングで使用する新しい WebView を非同期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="9ec42-119">Asynchronously create a new WebView for use with visual hosting.</span></span>

> <span data-ttu-id="9ec42-120">パブリック HRESULT [CreateCoreWebView2CompositionController](#createcorewebview2compositioncontroller)(HWND parentwindow、 [ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler](icorewebview2experimentalcreatecorewebview2compositioncontrollercompletedhandler.md) \* handler)</span><span class="sxs-lookup"><span data-stu-id="9ec42-120">public HRESULT [CreateCoreWebView2CompositionController](#createcorewebview2compositioncontroller)(HWND parentWindow, [ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler](icorewebview2experimentalcreatecorewebview2compositioncontrollercompletedhandler.md) \* handler)</span></span>

<span data-ttu-id="9ec42-121">parentWindow は、アプリが WebView のビジュアルツリーを接続する HWND です。</span><span class="sxs-lookup"><span data-stu-id="9ec42-121">parentWindow is the HWND in which the app will connect the visual tree of the WebView.</span></span> <span data-ttu-id="9ec42-122">これは、WebView に対応するポインターまたはマウスの入力をアプリが受け取るようにする HWND です (そして、SendMouseInput/Sendpointer 入力を使って転送する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="9ec42-122">This will be the HWND that the app will receive pointer/ mouse input meant for the WebView (and will need to use SendMouseInput/ SendPointerInput to forward).</span></span> <span data-ttu-id="9ec42-123">アプリが WebView ビジュアルツリーを別のウィンドウの下に移動する場合、ビジュアルツリーの新しい親 HWND を更新するために put_ParentWindow を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ec42-123">If the app moves the WebView visual tree to underneath a different window, then it needs to call put_ParentWindow to update the new parent HWND of the visual tree.</span></span>

<span data-ttu-id="9ec42-124">作成した CoreWebView2CompositionController の put_RootVisualTarget を使って、ブラウザーのビジュアルツリーをホストするためのビジュアルを提供します。</span><span class="sxs-lookup"><span data-stu-id="9ec42-124">Use put_RootVisualTarget on the created CoreWebView2CompositionController to provide a visual to host the browser's visual tree.</span></span>

<span data-ttu-id="9ec42-125">アプリケーションは、プロセスまたはアプリケーションウィンドウのアプリケーションユーザーモデル ID を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9ec42-125">It is recommended that the application set Application User Model ID for the process or the application window.</span></span> <span data-ttu-id="9ec42-126">何も設定されていない場合は、WebView の作成中に、生成されたアプリケーションユーザーモデル ID が parentWindow のルートウィンドウに設定されます。</span><span class="sxs-lookup"><span data-stu-id="9ec42-126">If none is set, during WebView creation a generated Application User Model ID is set to root window of parentWindow.</span></span> 
```cpp
// Create or recreate the WebView and its environment.
void AppWindow::InitializeWebView()
{
    // To ensure browser switches get applied correctly, we need to close
    // the existing WebView. This will result in a new browser process
    // getting created which will apply the browser switches.
    CloseWebView();
    m_dcompDevice = nullptr;
    m_wincompHelper = nullptr;

    LPCWSTR subFolder = nullptr;

    if (m_creationModeId == IDM_CREATION_MODE_VISUAL_DCOMP)
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
        HRESULT hr = CreateWinCompCompositor();
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
    }
    auto options = Microsoft::WRL::Make<CoreWebView2EnvironmentOptions>();
    if(!m_language.empty())
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
    if (webViewExperimentalEnvironment && (m_dcompDevice || m_wincompHelper))
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
 <span data-ttu-id="9ec42-127">アプリが特定のインストールから webview のエッジを使用していて、インストールがアンインストールされている場合に、アプリが再起動マネージャーのメッセージを処理して、アプリが、適切に再起動できるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9ec42-127">It is recommended that the application handles restart manager messages so that it can be restarted gracefully in the case when the app is using Edge for webview from a certain installation and that installation is being uninstalled.</span></span> <span data-ttu-id="9ec42-128">たとえば、ユーザーが Dev channel から Edge をインストールし、そのチャネルの端を使ってアプリをテストしている場合は、アプリを終了せずにそのチャネルから edge をアンインストールすると、アプリは再起動され、開発者チャネルのアンインストールが成功します。</span><span class="sxs-lookup"><span data-stu-id="9ec42-128">For example, if a user installs Edge from Dev channel and opts to use Edge from that channel for testing the app, and then uninstalls Edge from that channel without closing the app, the app will be restarted to allow uninstallation of the dev channel to succeed.</span></span> 
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

#### <span data-ttu-id="9ec42-129">CreateCoreWebView2PointerInfo</span><span class="sxs-lookup"><span data-stu-id="9ec42-129">CreateCoreWebView2PointerInfo</span></span> 

<span data-ttu-id="9ec42-130">空の[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)を作成します。</span><span class="sxs-lookup"><span data-stu-id="9ec42-130">Create an empty [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md).</span></span>

> <span data-ttu-id="9ec42-131">パブリック HRESULT [CreateCoreWebView2PointerInfo](#createcorewebview2pointerinfo)([ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \* \* ポインター情報)</span><span class="sxs-lookup"><span data-stu-id="9ec42-131">public HRESULT [CreateCoreWebView2PointerInfo](#createcorewebview2pointerinfo)([ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \*\* pointerInfo)</span></span>

<span data-ttu-id="9ec42-132">返された[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)には、Sendポインタ入力を呼び出す前に、関連するすべての情報を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ec42-132">The returned [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) needs to be populated with all of the relevant info before calling SendPointerInput.</span></span>

#### <span data-ttu-id="9ec42-133">GetProviderForHwnd</span><span class="sxs-lookup"><span data-stu-id="9ec42-133">GetProviderForHwnd</span></span> 

<span data-ttu-id="9ec42-134">指定された HWND に対応する ICoreWebView2CompositionController の UI オートメーションプロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="9ec42-134">Returns the UI Automation Provider for the ICoreWebView2CompositionController that corresponds with the given HWND.</span></span>

> <span data-ttu-id="9ec42-135">パブリック HRESULT [Getproviderforhwnd](#getproviderforhwnd)(hwnd Hwnd、IUnknown \* \* provider)</span><span class="sxs-lookup"><span data-stu-id="9ec42-135">public HRESULT [GetProviderForHwnd](#getproviderforhwnd)(HWND hwnd, IUnknown \*\* provider)</span></span>
