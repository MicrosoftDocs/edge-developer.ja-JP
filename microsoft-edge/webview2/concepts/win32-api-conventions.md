---
description: Win32 C++ WebView2 API の規則
title: Win32 C++ WebView2 API の規則
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 6c596b038e871caa5a364991351636f51ef7d685
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010685"
---
# <span data-ttu-id="f506b-104">Win32 C++ WebView2 API の規則</span><span class="sxs-lookup"><span data-stu-id="f506b-104">Win32 C++ WebView2 API conventions</span></span>  

## <span data-ttu-id="f506b-105">Async メソッド</span><span class="sxs-lookup"><span data-stu-id="f506b-105">Async Methods</span></span>  

<span data-ttu-id="f506b-106">WebView2 Win32 C++ API の非同期メソッドでは、デリゲートインターフェイスを使って、async メソッドが完了したとき、成功または失敗コード、非同期メソッドの結果などを示します。</span><span class="sxs-lookup"><span data-stu-id="f506b-106">Asynchronous methods in the WebView2 Win32 C++ API use a delegate interface to callback to you to indicate when the async method has completed, the success or failure code, and for some, the result of the asynchronous method.</span></span>  <span data-ttu-id="f506b-107">すべての非同期メソッドの final パラメーターは、実装を提供するデリゲートインターフェイスへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="f506b-107">The final parameter for all asynchronous methods is a pointer to a delegate interface of which you provide an implementation.</span></span>  

<span data-ttu-id="f506b-108">Delegate インターフェイスには、 `Invoke` `HRESULT` 成功または失敗コードの最初のパラメーターとして受け取る1つのメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="f506b-108">The delegate interface has a single `Invoke` method that takes as a first parameter an `HRESULT` of the success or failure code.</span></span>  <span data-ttu-id="f506b-109">また、メソッドに結果が含まれている場合は、メソッドの結果として2番目のパラメーターが必要になることもあります。</span><span class="sxs-lookup"><span data-stu-id="f506b-109">Additionally there may be a second parameter that is the result of the method if the method has a result.</span></span>  <span data-ttu-id="f506b-110">たとえば、[ICoreWebView2:: CapturePreview] [Webview2ReferenceWin3209538Icorewebview2CapturePreview] メソッドは、最後のパラメーターとして `ICoreWebView2CapturePreviewCompletedHandler` ポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f506b-110">For example, the [ICoreWebView2::CapturePreview][Webview2ReferenceWin3209538Icorewebview2CapturePreview] method takes as the final parameter an `ICoreWebView2CapturePreviewCompletedHandler` pointer.</span></span>  <span data-ttu-id="f506b-111">メソッド要求を送信するには `CapturePreview` 、実装するポインターのインスタンスを指定し `ICoreWebView2CapturePreviewCompletedHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="f506b-111">To send a `CapturePreview` method request, you provide an instance of the `ICoreWebView2CapturePreviewCompletedHandler` pointer that you implement.</span></span>  <span data-ttu-id="f506b-112">次のコードスニペットでは、1つのメソッドを使って実装します。</span><span class="sxs-lookup"><span data-stu-id="f506b-112">The following code snippet uses one method to implement.</span></span>  

```cpp
HRESULT Invoke(HRESULT result)
```  

<span data-ttu-id="f506b-113">`Invoke` `CoreWebView2` `Invoke` 要求が完了したときにメソッドを実装し、メソッドを要求し `CapturePreview` ます。</span><span class="sxs-lookup"><span data-stu-id="f506b-113">You implement the `Invoke` method and `CoreWebView2` requests your `Invoke` method when `CapturePreview` request completes.</span></span>  <span data-ttu-id="f506b-114">Single パラメーターは、 `HRESULT` 要求の成功または失敗コードを記述することです `CapturePreview` 。</span><span class="sxs-lookup"><span data-stu-id="f506b-114">The single parameter is the `HRESULT` describing the success or failure code of the `CapturePreview` request.</span></span>  

<span data-ttu-id="f506b-115">または `ICoreWebView2::ExecuteScript` 、 `ICoreWebView2ExecuteScriptCompletedHandler` `Invoke` 要求の成功コードまたは失敗コードを提供するメソッド `ExecuteScript` と、スクリプトの実行結果の JSON である2番目のパラメーターを提供するインスタンスを指定し `resultObjectAsJson` ます。</span><span class="sxs-lookup"><span data-stu-id="f506b-115">Or for `ICoreWebView2::ExecuteScript`, you provide an instance of `ICoreWebView2ExecuteScriptCompletedHandler` which has an `Invoke` method that provides you with the success or failure code of the `ExecuteScript` request as well as the second parameter `resultObjectAsJson` which is the JSON of the result of running the script.</span></span>  

<span data-ttu-id="f506b-116">デリゲートインターフェイスを手動で実装することも、 `CompleteHandler` [Wrl コールバック関数][CppCxWrlCallbackFunction]を使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="f506b-116">You may manually implement the `CompleteHandler` delegate interfaces, or you may use the [WRL Callback function][CppCxWrlCallbackFunction].</span></span>  <span data-ttu-id="f506b-117">Callback 関数は、次の WebView2 コードスニペット全体で使用されます。</span><span class="sxs-lookup"><span data-stu-id="f506b-117">The Callback function is used throughout the following WebView2 code snippet.</span></span>  

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

## <span data-ttu-id="f506b-118">イベント</span><span class="sxs-lookup"><span data-stu-id="f506b-118">Events</span></span>  

<span data-ttu-id="f506b-119">WebView2 Win32 C++ API のイベントでは、 `add_EventName` and `remove_EventName` メソッドのペアを使ってイベントをサブスクライブおよびサブスクライブ解除します。</span><span class="sxs-lookup"><span data-stu-id="f506b-119">Events in the WebView2 Win32 C++ API use the `add_EventName` and `remove_EventName` method pair to subscribe and unsubscribe from events.</span></span>  <span data-ttu-id="f506b-120">この `add_EventName` メソッドは、イベントハンドラーデリゲートインターフェイスを受け取り、 `EventRegistrationToken` out パラメーターとして戻ります。</span><span class="sxs-lookup"><span data-stu-id="f506b-120">The `add_EventName` method takes an event handler delegate interface and gives back an `EventRegistrationToken` as an out parameter.</span></span>  <span data-ttu-id="f506b-121">この `remove_EventName` メソッドは、 `EventRegistrationToken` 対応するイベントサブスクリプションを unsubscribes し、それを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f506b-121">The `remove_EventName` method takes an `EventRegistrationToken` and unsubscribes the corresponding event subscription.</span></span>  

<span data-ttu-id="f506b-122">イベントハンドラーのデリゲートインターフェイスは、async メソッドの完了したハンドラーデリゲートインターフェイスと同様に機能します。</span><span class="sxs-lookup"><span data-stu-id="f506b-122">Event handler delegate interfaces work very similarly to the async method completed handler delegate interfaces.</span></span>  <span data-ttu-id="f506b-123">イベントハンドラーのデリゲートインターフェイスを実装し、 `CoreWebView2` イベントが発生するたびにコールバックを送信します。</span><span class="sxs-lookup"><span data-stu-id="f506b-123">You implement the event handler delegate interface and `CoreWebView2` sends a callback whenever the event fires.</span></span>  <span data-ttu-id="f506b-124">各イベントハンドラーデリゲートインターフェイスには、 `Invoke` sender パラメーターとイベント引数パラメーターを持つ1つのメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="f506b-124">Every event handler delegate interface has a single `Invoke` method that has a sender parameter followed by an event args parameter.</span></span>  <span data-ttu-id="f506b-125">送信者は、イベントをサブスクライブしたオブジェクトのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="f506b-125">The sender is the instance of the object on which you subscribed for events.</span></span>  <span data-ttu-id="f506b-126">イベント引数パラメーターは、現在発生しているイベントに関する情報を含むインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="f506b-126">The event args parameter is an interface that contains information about the currently firing event.</span></span>  

<span data-ttu-id="f506b-127">たとえば、 `NavigationCompleted` on イベントには `ICoreWebView2` `ICoreWebView2::add_NavigationCompleted` and メソッドのペアがあり `ICoreWebView2::remove_NavigationCompleted` ます。</span><span class="sxs-lookup"><span data-stu-id="f506b-127">For instance the `NavigationCompleted` event on `ICoreWebView2` has the `ICoreWebView2::add_NavigationCompleted` and `ICoreWebView2::remove_NavigationCompleted` method pair.</span></span>  <span data-ttu-id="f506b-128">Add を要求するときに、 `ICoreWebView2NavigationCompletedEventHandler` 以前にメソッドを実装したインスタンスを指定し `Invoke` ます。</span><span class="sxs-lookup"><span data-stu-id="f506b-128">When you request add you provide an instance of `ICoreWebView2NavigationCompletedEventHandler` in which you previously implemented `Invoke` method.</span></span>  <span data-ttu-id="f506b-129">イベントが `NavigationCompleted` 発生すると、 `Invoke` メソッドが要求されます。</span><span class="sxs-lookup"><span data-stu-id="f506b-129">When the `NavigationCompleted` event fires, your `Invoke` method is requested.</span></span>  <span data-ttu-id="f506b-130">最初のパラメーターは、 `ICoreWebView2` イベントを発生させるものです `NavigationCompleted` 。</span><span class="sxs-lookup"><span data-stu-id="f506b-130">The first parameter is the `ICoreWebView2` which is firing the `NavigationCompleted` event.</span></span>  <span data-ttu-id="f506b-131">2番目のパラメーターは、 `ICoreWebView2NavigationCompletedEventArgs` ナビゲーションが正常に完了したかどうかに関する情報を含む、です。</span><span class="sxs-lookup"><span data-stu-id="f506b-131">The second parameter is the `ICoreWebView2NavigationCompletedEventArgs` which contains information about if the navigation completed successfully and so on.</span></span>  

<span data-ttu-id="f506b-132">非同期メソッドの completed ハンドラーのデリゲートインターフェイスと同様に、直接実装することもできます。また、次の WebView2 コードスニペットで使用される WRL コールバック関数を使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="f506b-132">Similarly to the async method completed handler delegate interface you are able to implement it yourself directly, or you may use the WRL Callback function that is used in the following WebView2 code snippet.</span></span>  

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

## <span data-ttu-id="f506b-133">文字列</span><span class="sxs-lookup"><span data-stu-id="f506b-133">Strings</span></span>  

<span data-ttu-id="f506b-134">文字列 out パラメーターは `LPWSTR` 、null で終了する文字列です。</span><span class="sxs-lookup"><span data-stu-id="f506b-134">String out parameters are `LPWSTR` null-terminated strings.</span></span>  <span data-ttu-id="f506b-135">要求者は、を使用して文字列を割り当て `CoTaskMemAlloc` ます。</span><span class="sxs-lookup"><span data-stu-id="f506b-135">The requester allocates the string using `CoTaskMemAlloc`.</span></span>  <span data-ttu-id="f506b-136">所有権は要求者に転送されます。また、要求者は、を使ってメモリを解放する必要が `CoTaskMemFree` あります。</span><span class="sxs-lookup"><span data-stu-id="f506b-136">Ownership is transferred to the requester and it is up to the requester to free the memory using `CoTaskMemFree`.</span></span>  

<span data-ttu-id="f506b-137">パラメーター内の文字列は `LPCWSTR` 、null で終了する文字列です。</span><span class="sxs-lookup"><span data-stu-id="f506b-137">String in parameters are `LPCWSTR` null-terminated strings.</span></span>  <span data-ttu-id="f506b-138">リクエスターは、同期関数要求の間、文字列が有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f506b-138">The requester ensures the string is valid for the duration of the synchronous function request.</span></span>  <span data-ttu-id="f506b-139">この値を、レシーバーでその値をそのまま保持する必要がある場合は、受信者は、文字列値の関連コピーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f506b-139">If the receiver must retain that value to some point after the function request completes, the receiver must allocate an associated copy of the string value.</span></span>  

## <span data-ttu-id="f506b-140">URI と JSON の解析</span><span class="sxs-lookup"><span data-stu-id="f506b-140">URI and JSON parsing</span></span>  

<span data-ttu-id="f506b-141">さまざまなメソッドで Uri と JSON を文字列として指定または受け入れます。</span><span class="sxs-lookup"><span data-stu-id="f506b-141">Various methods provide or accept URIs and JSON as strings.</span></span>  <span data-ttu-id="f506b-142">文字列の解析と生成には、独自の好みのライブラリを使用してください。</span><span class="sxs-lookup"><span data-stu-id="f506b-142">Please use your own preferred library for parsing and generating the strings.</span></span>  

<span data-ttu-id="f506b-143">アプリで WinRT が利用できる場合は、 `RuntimeClass_Windows_Data_Json_JsonObject` and `IJsonObjectStatics` メソッドを使って JSON 文字列または uri の解析 `RuntimeClass_Windows_Foundation_Uri` と生成を行うことができ `IUriRuntimeClassFactory` ます。</span><span class="sxs-lookup"><span data-stu-id="f506b-143">If WinRT is available for your app, you may use the `RuntimeClass_Windows_Data_Json_JsonObject` and `IJsonObjectStatics` methods to parse or produce JSON strings or `RuntimeClass_Windows_Foundation_Uri` and `IUriRuntimeClassFactory` methods to parse and produce URIs.</span></span>  <span data-ttu-id="f506b-144">どちらの方法も Win32 アプリで動作します。</span><span class="sxs-lookup"><span data-stu-id="f506b-144">Both of methods work in Win32 apps.</span></span>  

<span data-ttu-id="f506b-145">Uri `IUri` を解析するために and を使っている場合は、 `CreateUri` 次の uri 作成フラグを使用して、 `CreateUri` WEBVIEW での uri 解析とより適切な動作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f506b-145">If you use `IUri` and `CreateUri` to parse URIs, you may want to use the following URI creation flags to have `CreateUri` behavior more closely match the URI parsing in the WebView.</span></span>  

```json
Uri_CREATE_ALLOW_IMPLICIT_FILE_SCHEME | Uri_CREATE_NO_DECODE_EXTRA_INFO
```  

<!-- links -->  

[Webview2ReferenceWin3209622Icorewebview2CapturePreview]: ../reference/win32/0-9-622/icorewebview2.md#capturepreview "CapturePreview-インターフェイス ICoreWebView2 |Microsoft ドキュメント"  

[CppCxWrlCallbackFunction]: /cpp/cppcx/wrl/callback-function-wrl "コールバック関数 (WRL) |Microsoft ドキュメント"  
