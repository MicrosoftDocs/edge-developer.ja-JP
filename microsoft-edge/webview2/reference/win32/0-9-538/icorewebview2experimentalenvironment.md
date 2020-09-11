---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2ExperimentalEnvironment
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExperimentalEnvironment
ms.openlocfilehash: e7ccb108c137e54635c6e5b69f9bc615ff8ff018
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011137"
---
# <span data-ttu-id="aa5f4-104">0.9.579-インターフェイス ICoreWebView2ExperimentalEnvironment</span><span class="sxs-lookup"><span data-stu-id="aa5f4-104">0.9.579 - interface ICoreWebView2ExperimentalEnvironment</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalEnvironment
  : public IUnknown
```

<span data-ttu-id="aa5f4-105">このインターフェイスは、 [ICoreWebView2Environment](icorewebview2environment.md)の拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="aa5f4-105">This interface is an extension of the [ICoreWebView2Environment](icorewebview2environment.md).</span></span>

## <span data-ttu-id="aa5f4-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="aa5f4-106">Summary</span></span>

 <span data-ttu-id="aa5f4-107">Members</span><span class="sxs-lookup"><span data-stu-id="aa5f4-107">Members</span></span>                        | <span data-ttu-id="aa5f4-108">説明</span><span class="sxs-lookup"><span data-stu-id="aa5f4-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="aa5f4-109">CreateCoreWebView2CompositionController</span><span class="sxs-lookup"><span data-stu-id="aa5f4-109">CreateCoreWebView2CompositionController</span></span>](#createcorewebview2compositioncontroller) | <span data-ttu-id="aa5f4-110">ビジュアルホスティングで使用する新しい WebView を非同期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="aa5f4-110">Asynchronously create a new WebView for use with visual hosting.</span></span>
[<span data-ttu-id="aa5f4-111">CreateCoreWebView2PointerInfo</span><span class="sxs-lookup"><span data-stu-id="aa5f4-111">CreateCoreWebView2PointerInfo</span></span>](#createcorewebview2pointerinfo) | <span data-ttu-id="aa5f4-112">空の [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)を作成します。</span><span class="sxs-lookup"><span data-stu-id="aa5f4-112">Create an empty [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md).</span></span>
[<span data-ttu-id="aa5f4-113">GetProviderForHwnd</span><span class="sxs-lookup"><span data-stu-id="aa5f4-113">GetProviderForHwnd</span></span>](#getproviderforhwnd) | <span data-ttu-id="aa5f4-114">指定された HWND に対応する ICoreWebView2CompositionController の UI オートメーションプロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="aa5f4-114">Returns the UI Automation Provider for the ICoreWebView2CompositionController that corresponds with the given HWND.</span></span>

<span data-ttu-id="aa5f4-115">[ICoreWebView2ExperimentalEnvironment]()インターフェイスを実装するオブジェクトも[ICoreWebView2Environment](icorewebview2environment.md)を実装します。</span><span class="sxs-lookup"><span data-stu-id="aa5f4-115">An object implementing the [ICoreWebView2ExperimentalEnvironment]() interface will also implement [ICoreWebView2Environment](icorewebview2environment.md).</span></span>

## <span data-ttu-id="aa5f4-116">Members</span><span class="sxs-lookup"><span data-stu-id="aa5f4-116">Members</span></span>

#### <span data-ttu-id="aa5f4-117">CreateCoreWebView2CompositionController</span><span class="sxs-lookup"><span data-stu-id="aa5f4-117">CreateCoreWebView2CompositionController</span></span> 

<span data-ttu-id="aa5f4-118">ビジュアルホスティングで使用する新しい WebView を非同期的に作成します。</span><span class="sxs-lookup"><span data-stu-id="aa5f4-118">Asynchronously create a new WebView for use with visual hosting.</span></span>

> <span data-ttu-id="aa5f4-119">パブリック HRESULT [CreateCoreWebView2CompositionController](#createcorewebview2compositioncontroller)(HWND parentwindow、 [ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler](icorewebview2experimentalcreatecorewebview2compositioncontrollercompletedhandler.md) \* handler)</span><span class="sxs-lookup"><span data-stu-id="aa5f4-119">public HRESULT [CreateCoreWebView2CompositionController](#createcorewebview2compositioncontroller)(HWND parentWindow, [ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler](icorewebview2experimentalcreatecorewebview2compositioncontrollercompletedhandler.md) \* handler)</span></span>

<span data-ttu-id="aa5f4-120">parentWindow は、アプリが WebView のビジュアルツリーを接続する HWND です。</span><span class="sxs-lookup"><span data-stu-id="aa5f4-120">parentWindow is the HWND in which the app will connect the visual tree of the WebView.</span></span> <span data-ttu-id="aa5f4-121">これは、WebView に対応するポインターまたはマウスの入力をアプリが受け取るようにする HWND です (そして、SendMouseInput/Sendpointer 入力を使って転送する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="aa5f4-121">This will be the HWND that the app will receive pointer/ mouse input meant for the WebView (and will need to use SendMouseInput/ SendPointerInput to forward).</span></span> <span data-ttu-id="aa5f4-122">アプリが WebView ビジュアルツリーを別のウィンドウの下に移動する場合、ビジュアルツリーの新しい親 HWND を更新するために put_ParentWindow を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa5f4-122">If the app moves the WebView visual tree to underneath a different window, then it needs to call put_ParentWindow to update the new parent HWND of the visual tree.</span></span>

<span data-ttu-id="aa5f4-123">作成した CoreWebView2CompositionController の put_RootVisualTarget を使って、ブラウザーのビジュアルツリーをホストするためのビジュアルを提供します。</span><span class="sxs-lookup"><span data-stu-id="aa5f4-123">Use put_RootVisualTarget on the created CoreWebView2CompositionController to provide a visual to host the browser's visual tree.</span></span>

<span data-ttu-id="aa5f4-124">アプリケーションは、プロセスまたはアプリケーションウィンドウのアプリケーションユーザーモデル ID を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="aa5f4-124">It is recommended that the application set Application User Model ID for the process or the application window.</span></span> <span data-ttu-id="aa5f4-125">何も設定されていない場合は、WebView の作成中に、生成されたアプリケーションユーザーモデル ID が parentWindow のルートウィンドウに設定されます。</span><span class="sxs-lookup"><span data-stu-id="aa5f4-125">If none is set, during WebView creation a generated Application User Model ID is set to root window of parentWindow.</span></span> 
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
    auto options = Microsoft::WRL::Make<CoreWebView2ExperimentalEnvironmentOptions>();
    CHECK_FAILURE(options->put_IsSingleSignOnUsingOSPrimaryAccountEnabled(
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
 <span data-ttu-id="aa5f4-126">アプリが特定のインストールから webview のエッジを使用していて、インストールがアンインストールされている場合に、アプリが再起動マネージャーのメッセージを処理して、アプリが、適切に再起動できるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="aa5f4-126">It is recommended that the application handles restart manager messages so that it can be restarted gracefully in the case when the app is using Edge for webview from a certain installation and that installation is being uninstalled.</span></span> <span data-ttu-id="aa5f4-127">たとえば、ユーザーが Dev channel から Edge をインストールし、そのチャネルの端を使ってアプリをテストしている場合は、アプリを終了せずにそのチャネルから edge をアンインストールすると、アプリは再起動され、開発者チャネルのアンインストールが成功します。</span><span class="sxs-lookup"><span data-stu-id="aa5f4-127">For example, if a user installs Edge from Dev channel and opts to use Edge from that channel for testing the app, and then uninstalls Edge from that channel without closing the app, the app will be restarted to allow uninstallation of the dev channel to succeed.</span></span> 
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

#### <span data-ttu-id="aa5f4-128">CreateCoreWebView2PointerInfo</span><span class="sxs-lookup"><span data-stu-id="aa5f4-128">CreateCoreWebView2PointerInfo</span></span> 

<span data-ttu-id="aa5f4-129">空の [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)を作成します。</span><span class="sxs-lookup"><span data-stu-id="aa5f4-129">Create an empty [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md).</span></span>

> <span data-ttu-id="aa5f4-130">パブリック HRESULT [CreateCoreWebView2PointerInfo](#createcorewebview2pointerinfo)([ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \* \* ポインター情報)</span><span class="sxs-lookup"><span data-stu-id="aa5f4-130">public HRESULT [CreateCoreWebView2PointerInfo](#createcorewebview2pointerinfo)([ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \*\* pointerInfo)</span></span>

<span data-ttu-id="aa5f4-131">返された [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) には、Sendポインタ入力を呼び出す前に、関連するすべての情報を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa5f4-131">The returned [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) needs to be populated with all of the relevant info before calling SendPointerInput.</span></span>

#### <span data-ttu-id="aa5f4-132">GetProviderForHwnd</span><span class="sxs-lookup"><span data-stu-id="aa5f4-132">GetProviderForHwnd</span></span> 

<span data-ttu-id="aa5f4-133">指定された HWND に対応する ICoreWebView2CompositionController の UI オートメーションプロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="aa5f4-133">Returns the UI Automation Provider for the ICoreWebView2CompositionController that corresponds with the given HWND.</span></span>

> <span data-ttu-id="aa5f4-134">パブリック HRESULT [Getproviderforhwnd](#getproviderforhwnd)(hwnd Hwnd、IUnknown \* \* provider)</span><span class="sxs-lookup"><span data-stu-id="aa5f4-134">public HRESULT [GetProviderForHwnd](#getproviderforhwnd)(HWND hwnd, IUnknown \*\* provider)</span></span>

