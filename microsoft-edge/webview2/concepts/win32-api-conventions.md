---
description: Win32 C++ WebView2 API の規則
title: Win32 C++ WebView2 API の規則
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/24/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、edge html
ms.openlocfilehash: b47e53a4846d4bb662ae108c6445a6c2a615722a
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11470859"
---
# <a name="win32-c-webview2-api-conventions"></a><span data-ttu-id="02a05-104">Win32 C++ WebView2 API の規則</span><span class="sxs-lookup"><span data-stu-id="02a05-104">Win32 C++ WebView2 API conventions</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="02a05-105">サポートされているプラットフォーム:</span><span class="sxs-lookup"><span data-stu-id="02a05-105">Supported platforms:</span></span>
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="02a05-106">Win32</span><span class="sxs-lookup"><span data-stu-id="02a05-106">Win32</span></span>
   :::column-end:::
:::row-end:::  

## <a name="prerequisites"></a><span data-ttu-id="02a05-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="02a05-107">Prerequisites</span></span>  

*   <span data-ttu-id="02a05-108">Win32 API の使用経験</span><span class="sxs-lookup"><span data-stu-id="02a05-108">Experience using Win32 API</span></span>  

## <a name="async-methods"></a><span data-ttu-id="02a05-109">非同期メソッド</span><span class="sxs-lookup"><span data-stu-id="02a05-109">Async methods</span></span>  

<span data-ttu-id="02a05-110">WebView2 Win32 C++ API の非同期メソッドは、デリゲート インターフェイスを使用して、次の理由で連絡します。</span><span class="sxs-lookup"><span data-stu-id="02a05-110">Asynchronous methods in the WebView2 Win32 C++ API use a delegate interface to contact you for the following reasons.</span></span>  

*   <span data-ttu-id="02a05-111">非同期メソッドが完了しました。</span><span class="sxs-lookup"><span data-stu-id="02a05-111">The async method has completed.</span></span>  
*   <span data-ttu-id="02a05-112">成功または失敗のコード。</span><span class="sxs-lookup"><span data-stu-id="02a05-112">The success or failure code.</span></span>  
*   <span data-ttu-id="02a05-113">非同期メソッドの結果。</span><span class="sxs-lookup"><span data-stu-id="02a05-113">The result of the asynchronous method.</span></span>  

<span data-ttu-id="02a05-114">すべての非同期メソッドの最終的なパラメーターは、実装を提供するデリゲート インターフェイスへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="02a05-114">The final parameter for all asynchronous methods is a pointer to a delegate interface of which you provide an implementation.</span></span>  

<span data-ttu-id="02a05-115">デリゲート インターフェイスには、成功または失敗のコードの最初のパラメーター a を受け取る `Invoke` `HRESULT` 1 つのメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="02a05-115">The delegate interface has a single `Invoke` method that takes as a first parameter an `HRESULT` of the success or failure code.</span></span>  <span data-ttu-id="02a05-116">さらに、メソッドに結果がある場合は、メソッドの結果である 2 番目のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="02a05-116">Additionally, there may be a second parameter that is the result of the method if the method has a result.</span></span>  <span data-ttu-id="02a05-117">たとえば [、ICoreWebView2::CapturePreview][Webview2ReferenceWin32Icorewebview2CapturePreview] メソッドは、最終的なパラメーターとしてポインターを受け取 `ICoreWebView2CapturePreviewCompletedHandler` ります。</span><span class="sxs-lookup"><span data-stu-id="02a05-117">For example, the [ICoreWebView2::CapturePreview][Webview2ReferenceWin32Icorewebview2CapturePreview] method takes as the final parameter an `ICoreWebView2CapturePreviewCompletedHandler` pointer.</span></span>  <span data-ttu-id="02a05-118">メソッド要求 `CapturePreview` を送信するには、実装するポインターの `ICoreWebView2CapturePreviewCompletedHandler` インスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="02a05-118">To send a `CapturePreview` method request, you provide an instance of the `ICoreWebView2CapturePreviewCompletedHandler` pointer that you implement.</span></span>  <span data-ttu-id="02a05-119">次のコード スニペットでは、1 つのメソッドを使用して実装します。</span><span class="sxs-lookup"><span data-stu-id="02a05-119">The following code snippet uses one method to implement.</span></span>  

```cpp
HRESULT Invoke(HRESULT result)
```  

<span data-ttu-id="02a05-120">メソッドを実装 `Invoke` し、 `CoreWebView2` 要求が完了 `Invoke` したらメソッド `CapturePreview` を要求します。</span><span class="sxs-lookup"><span data-stu-id="02a05-120">You implement the `Invoke` method and `CoreWebView2` requests your `Invoke` method when `CapturePreview` request completes.</span></span>  <span data-ttu-id="02a05-121">1 つのパラメーターは `HRESULT` 、要求の成功または失敗のコードを記述 `CapturePreview` します。</span><span class="sxs-lookup"><span data-stu-id="02a05-121">The single parameter is the `HRESULT` describing the success or failure code of the `CapturePreview` request.</span></span>  

<span data-ttu-id="02a05-122">または、たとえば、要求の成功または失敗コードを提供するメソッドを持つ `ICoreWebView2::ExecuteScript` `Invoke` インスタンスを指定 `ExecuteScript` します。</span><span class="sxs-lookup"><span data-stu-id="02a05-122">Alternately, for `ICoreWebView2::ExecuteScript`, you provide an instance that has an `Invoke` method that provides you with the success or failure code of the `ExecuteScript` request.</span></span>  <span data-ttu-id="02a05-123">また、スクリプトの実行結果の JSON である 2 番目のパラメーターも指定します。</span><span class="sxs-lookup"><span data-stu-id="02a05-123">Also provide the second parameter that is the JSON of the result of running the script.</span></span>  

<span data-ttu-id="02a05-124">デリゲート インターフェイスを手動で `CompleteHandler` 実装することもできますし、Callback 関数 [(WRL) を使用することもできます][CppCxWrlCallbackFunction]。</span><span class="sxs-lookup"><span data-stu-id="02a05-124">You may manually implement the `CompleteHandler` delegate interfaces, or you may use the [Callback function (WRL)][CppCxWrlCallbackFunction].</span></span>  <span data-ttu-id="02a05-125">[Callback 関数 (WRL) は][CppCxWrlCallbackFunction]、次の WebView2 コード スニペット全体で使用されます。</span><span class="sxs-lookup"><span data-stu-id="02a05-125">The [Callback function (WRL)][CppCxWrlCallbackFunction] is used throughout the following WebView2 code snippet.</span></span>  

```cpp
void ScriptComponent::InjectScript()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Inject Script",
        L"Enter script code:",
        L"Enter the JavaScript code to run in the webview.",
        L"window.getComputedStyle(document.body).backgroundColor");
    if (dialog.confirmed)
    {
        m_webView->ExecuteScript(dialog.input.c_str(),
            Callback<ICoreWebView2ExecuteScriptCompletedHandler>(
                [](HRESULT error, PCWSTR result) -> HRESULT
        {
            if (error != S_OK) {
                ShowFailure(error, L"ExecuteScript failed");
            }
            MessageBox(nullptr, result, L"ExecuteScript Result", MB_OK);
            return S_OK;
        }).Get());
    }
}
```  

## <a name="events"></a><span data-ttu-id="02a05-126">イベント</span><span class="sxs-lookup"><span data-stu-id="02a05-126">Events</span></span>  

<span data-ttu-id="02a05-127">WebView2 Win32 C++ API のイベントでは、and メソッドペアを使用してイベントの `add_EventName` `remove_EventName` サブスクライブとサブスクライブ解除を行います。</span><span class="sxs-lookup"><span data-stu-id="02a05-127">Events in the WebView2 Win32 C++ API use the `add_EventName` and `remove_EventName` method pair to subscribe and unsubscribe from events.</span></span>  <span data-ttu-id="02a05-128">この `add_EventName` メソッドは、イベント ハンドラーのデリゲート インターフェイスを受け取り、出力 `EventRegistrationToken` パラメーターとしてトークンを返します。</span><span class="sxs-lookup"><span data-stu-id="02a05-128">The `add_EventName` method takes an event handler delegate interface and gives back an `EventRegistrationToken` token as an output parameter.</span></span>  <span data-ttu-id="02a05-129">メソッド `remove_EventName` はトークンを受 `EventRegistrationToken` け取り、対応するイベント サブスクリプションを購読解除します。</span><span class="sxs-lookup"><span data-stu-id="02a05-129">The `remove_EventName` method takes an `EventRegistrationToken` token and unsubscribes the corresponding event subscription.</span></span>  

<span data-ttu-id="02a05-130">イベント ハンドラーデリゲート インターフェイスは、非同期メソッドの完了したハンドラー デリゲート インターフェイスと同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="02a05-130">Event handler delegate interfaces work similarly to the async method completed handler delegate interfaces.</span></span>  <span data-ttu-id="02a05-131">イベント ハンドラーのデリゲート インターフェイスを実装し、 `CoreWebView2` イベントが実行されるたびにコールバックを送信します。</span><span class="sxs-lookup"><span data-stu-id="02a05-131">You implement the event handler delegate interface and `CoreWebView2` sends a callback whenever the event runs.</span></span>  <span data-ttu-id="02a05-132">すべてのイベント ハンドラーデリゲート インターフェイスには、sender パラメーターの後にイベント args パラメーターが続く `Invoke` 1 つのメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="02a05-132">Every event handler delegate interface has a single `Invoke` method that has a sender parameter followed by an event args parameter.</span></span>  <span data-ttu-id="02a05-133">送信者は、イベントをサブスクライブしたオブジェクトのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="02a05-133">The sender is the instance of the object on which you subscribed for events.</span></span>  <span data-ttu-id="02a05-134">イベント args パラメーターは、現在発生しているイベントに関する情報を含むインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="02a05-134">The event args parameter is an interface that contains information about the currently firing event.</span></span>  

<span data-ttu-id="02a05-135">たとえば、イベント `NavigationCompleted` on には and `ICoreWebView2` メソッド `ICoreWebView2::add_NavigationCompleted` のペア `ICoreWebView2::remove_NavigationCompleted` があります。</span><span class="sxs-lookup"><span data-stu-id="02a05-135">For instance, the `NavigationCompleted` event on `ICoreWebView2` has the `ICoreWebView2::add_NavigationCompleted` and `ICoreWebView2::remove_NavigationCompleted` method pair.</span></span>  <span data-ttu-id="02a05-136">要求を送信するときに、以前に実装したメソッド `ICoreWebView2NavigationCompletedEventHandler` のインスタンスを指定 `Invoke` します。</span><span class="sxs-lookup"><span data-stu-id="02a05-136">When you send a request, you provide an instance of `ICoreWebView2NavigationCompletedEventHandler` in which you previously implemented `Invoke` method.</span></span>  <span data-ttu-id="02a05-137">イベントが `NavigationCompleted` 実行されると、メソッド `Invoke` が要求されます。</span><span class="sxs-lookup"><span data-stu-id="02a05-137">When the `NavigationCompleted` event runs, your `Invoke` method is requested.</span></span>  <span data-ttu-id="02a05-138">最初のパラメーターは、イベントを実行 `NavigationCompleted` します。</span><span class="sxs-lookup"><span data-stu-id="02a05-138">The first parameter runs the `NavigationCompleted` event.</span></span>  <span data-ttu-id="02a05-139">2 番目のパラメーターには、ナビゲーションが正常に完了した場合などについての情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="02a05-139">The second parameter contains information about if the navigation completed successfully and so on.</span></span>  

<span data-ttu-id="02a05-140">async メソッドが完了したハンドラー デリゲート インターフェイスと同様に、次のいずれかのアクションを使用してセットアップします。</span><span class="sxs-lookup"><span data-stu-id="02a05-140">Similar to the async method completed handler delegate interface, use one of the following actions to set it up.</span></span>  

*   <span data-ttu-id="02a05-141">直接実装します。</span><span class="sxs-lookup"><span data-stu-id="02a05-141">Implement it directly.</span></span>  
*   <span data-ttu-id="02a05-142">次の WebView2 コード スニペットで使用される Callback 関数 [(WRL)][CppCxWrlCallbackFunction] 関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="02a05-142">Use the [Callback function (WRL)][CppCxWrlCallbackFunction] function that is used in the following WebView2 code snippet.</span></span>  

<!-- todo:  what is async method completed handler delegate interface?  Is there a shorter name for it?  -->  

```cpp
// Register a handler for the NavigationCompleted event.
// Check whether the navigation succeeded, and if not, do something.
// Also update the Cancel buttons.
CHECK_FAILURE(m_webView->add_NavigationCompleted(
    Callback<ICoreWebView2NavigationCompletedEventHandler>(
        [this](ICoreWebView2* sender, ICoreWebView2NavigationCompletedEventArgs* args)
            -> HRESULT {
            BOOL success;
            CHECK_FAILURE(args->get_IsSuccess(&success));
            if (!success)
            {
                COREWEBVIEW2_WEB_ERROR_STATUS webErrorStatus;
                CHECK_FAILURE(args->get_WebErrorStatus(&webErrorStatus));
                if (webErrorStatus == COREWEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED)
                {
                    // Do something here if you want to handle a specific error case.
                    // In most cases it is not necessary, because the WebView
                    // displays an error page automatically.
                }
            }
            m_toolbar->SetItemEnabled(Toolbar::Item_CancelButton, false);
            m_toolbar->SetItemEnabled(Toolbar::Item_ReloadButton, true);
            return S_OK;
        })
        .Get(),
    &m_navigationCompletedToken));
```  

## <a name="strings"></a><span data-ttu-id="02a05-143">文字列</span><span class="sxs-lookup"><span data-stu-id="02a05-143">Strings</span></span>  

<span data-ttu-id="02a05-144">文字列出力パラメーターは `LPWSTR` 、null 終端文字列です。</span><span class="sxs-lookup"><span data-stu-id="02a05-144">String output parameters are `LPWSTR` null-terminated strings.</span></span>  <span data-ttu-id="02a05-145">要求者は、 を使用して文字列を提供します `CoTaskMemAlloc` 。</span><span class="sxs-lookup"><span data-stu-id="02a05-145">The requester provides the string using `CoTaskMemAlloc`.</span></span>  <span data-ttu-id="02a05-146">所有権は要求者に転送され、要求者が使用してメモリを解放する必要があります `CoTaskMemFree` 。</span><span class="sxs-lookup"><span data-stu-id="02a05-146">Ownership is transferred to the requester and it is up to the requester to free the memory using `CoTaskMemFree`.</span></span>  

<span data-ttu-id="02a05-147">文字列入力パラメーターは `LPCWSTR` null 終端文字列です。</span><span class="sxs-lookup"><span data-stu-id="02a05-147">String input parameters are `LPCWSTR` null-terminated strings.</span></span>  <span data-ttu-id="02a05-148">要求者は、同期関数要求の期間中、文字列が有効である必要があります。</span><span class="sxs-lookup"><span data-stu-id="02a05-148">The requester ensures the string is valid for the duration of the synchronous function request.</span></span>  <span data-ttu-id="02a05-149">関数要求が完了した後、レシーバーが値をある時点に格納する必要がある場合、レシーバーは文字列値の関連付けられたコピーを与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="02a05-149">If the receiver must store the value to some point after the function request completes, the receiver must give an associated copy of the string value.</span></span>  

## <a name="uri-and-json-parsing"></a><span data-ttu-id="02a05-150">URI と JSON の解析</span><span class="sxs-lookup"><span data-stu-id="02a05-150">URI and JSON parsing</span></span>  

<span data-ttu-id="02a05-151">さまざまなメソッドが URI と JSON を文字列として提供または受け入れる。</span><span class="sxs-lookup"><span data-stu-id="02a05-151">Various methods provide or accept URIs and JSON as strings.</span></span>  <span data-ttu-id="02a05-152">文字列の解析と生成には、優先ライブラリを使用します。</span><span class="sxs-lookup"><span data-stu-id="02a05-152">Use your preferred library for parsing and generating the strings.</span></span>  

<span data-ttu-id="02a05-153">アプリで WinRT を使用できる場合は、and メソッドを使用して JSON 文字列またはメソッドを解析または生成し `RuntimeClass_Windows_Data_Json_JsonObject` `IJsonObjectStatics` 、URI を解析および `RuntimeClass_Windows_Foundation_Uri` `IUriRuntimeClassFactory` 生成できます。</span><span class="sxs-lookup"><span data-stu-id="02a05-153">If WinRT is available for your app, you may use the `RuntimeClass_Windows_Data_Json_JsonObject` and `IJsonObjectStatics` methods to parse or produce JSON strings or `RuntimeClass_Windows_Foundation_Uri` and `IUriRuntimeClassFactory` methods to parse and produce URIs.</span></span>  <span data-ttu-id="02a05-154">どちらのメソッドも Win32 アプリで動作します。</span><span class="sxs-lookup"><span data-stu-id="02a05-154">Both of methods work in Win32 apps.</span></span>  

<span data-ttu-id="02a05-155">URI を使用して解析する場合は、次の URI 作成フラグを使用して、WebView での URI 解析とより密接に一致する動作を実行 `IUri` `CreateUri` `CreateUri` できます。</span><span class="sxs-lookup"><span data-stu-id="02a05-155">If you use `IUri` and `CreateUri` to parse URIs, you may want to use the following URI creation flags to have `CreateUri` behavior more closely match the URI parsing in the WebView.</span></span>  

```json
Uri_CREATE_ALLOW_IMPLICIT_FILE_SCHEME | Uri_CREATE_NO_DECODE_EXTRA_INFO
```  

## <a name="see-also"></a><span data-ttu-id="02a05-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="02a05-156">See also</span></span>  

*   <span data-ttu-id="02a05-157">WebView2 Win32 C/C++ の使用を開始するには、[WebView2 の使用を開始する][Webview2IndexGettingStarted] ガイドに移動します。</span><span class="sxs-lookup"><span data-stu-id="02a05-157">To get started using WebView2 Win32 C/C++, navigate to [Getting started with WebView2][Webview2IndexGettingStarted] guides.</span></span>  
*   <span data-ttu-id="02a05-158">WebView2 API の詳細については、「API リファレンス」 [に移動します][DotnetApiMicrosoftWebWebview2WpfWebview2]。</span><span class="sxs-lookup"><span data-stu-id="02a05-158">For more detailed information about WebView2 APIs, navigate to [API reference][DotnetApiMicrosoftWebWebview2WpfWebview2].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a><span data-ttu-id="02a05-159">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="02a05-159">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2GettingstartedWin32]: ../gettingstarted/win32.md "WebView2 の概要 |Microsoft Docs"  

[Webview2ReferenceWin32Icorewebview2CapturePreview]: /microsoft-edge/webview2/reference/win32/icorewebview2#capturepreview "CapturePreview - インターフェイス ICoreWebView2 |Microsoft Docs"  

[CppCxWrlCallbackFunction]: /cpp/cppcx/wrl/callback-function-wrl "コールバック関数 (WRL) |Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2WpfWebview2]: /dotnet/api/microsoft.web.webview2.wpf.webview2 "WebView2 クラス | Microsoft Docs"  
