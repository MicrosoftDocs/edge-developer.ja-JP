---
description: Win32 C++ WebView2 API の規則
title: Win32 C++ WebView2 API の規則
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: c8792133da2b858cfaa456df5a7dce26c3c65154
ms.sourcegitcommit: 553957c101f83681b363103cb6af56bf20173f23
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "10895567"
---
# Win32 C++ WebView2 API の規則  

## Async メソッド  

WebView2 Win32 C++ API の非同期メソッドでは、デリゲートインターフェイスを使って、async メソッドが完了したとき、成功または失敗コード、非同期メソッドの結果などを示します。  すべての非同期メソッドの final パラメーターは、実装を提供するデリゲートインターフェイスへのポインターです。  

Delegate インターフェイスには、 `Invoke` `HRESULT` 成功または失敗コードの最初のパラメーターとして受け取る1つのメソッドがあります。  また、メソッドに結果が含まれている場合は、メソッドの結果として2番目のパラメーターが必要になることもあります。  たとえば、 [ICoreWebView2:: CapturePreview][Webview2ReferenceWin3209538Icorewebview2CapturePreview]メソッドは、最後のパラメーターとして `ICoreWebView2CapturePreviewCompletedHandler` ポインターを受け取ります。  メソッド要求を送信するには `CapturePreview` 、実装するポインターのインスタンスを指定し `ICoreWebView2CapturePreviewCompletedHandler` ます。  次のコードスニペットでは、1つのメソッドを使って実装します。  

```cpp
HRESULT Invoke(HRESULT result)
```  

`Invoke` `CoreWebView2` `Invoke` 要求が完了したときにメソッドを実装し、メソッドを要求し `CapturePreview` ます。  Single パラメーターは、 `HRESULT` 要求の成功または失敗コードを記述することです `CapturePreview` 。  

または `ICoreWebView2::ExecuteScript` 、 `ICoreWebView2ExecuteScriptCompletedHandler` `Invoke` 要求の成功コードまたは失敗コードを提供するメソッド `ExecuteScript` と、スクリプトの実行結果の JSON である2番目のパラメーターを提供するインスタンスを指定し `resultObjectAsJson` ます。  

デリゲートインターフェイスを手動で実装することも、 `CompleteHandler` [Wrl コールバック関数][CppCxWrlCallbackFunction]を使うこともできます。  Callback 関数は、次の WebView2 コードスニペット全体で使用されます。  

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

## イベント  

WebView2 Win32 C++ API のイベントでは、 `add_EventName` and `remove_EventName` メソッドのペアを使ってイベントをサブスクライブおよびサブスクライブ解除します。  この `add_EventName` メソッドは、イベントハンドラーデリゲートインターフェイスを受け取り、 `EventRegistrationToken` out パラメーターとして戻ります。  この `remove_EventName` メソッドは、 `EventRegistrationToken` 対応するイベントサブスクリプションを unsubscribes し、それを受け取ります。  

イベントハンドラーのデリゲートインターフェイスは、async メソッドの完了したハンドラーデリゲートインターフェイスと同様に機能します。  イベントハンドラーのデリゲートインターフェイスを実装し、 `CoreWebView2` イベントが発生するたびにコールバックを送信します。  各イベントハンドラーデリゲートインターフェイスには、 `Invoke` sender パラメーターとイベント引数パラメーターを持つ1つのメソッドがあります。  送信者は、イベントをサブスクライブしたオブジェクトのインスタンスです。  イベント引数パラメーターは、現在発生しているイベントに関する情報を含むインターフェイスです。  

たとえば、 `NavigationCompleted` on イベントには `ICoreWebView2` `ICoreWebView2::add_NavigationCompleted` and メソッドのペアがあり `ICoreWebView2::remove_NavigationCompleted` ます。  Add を要求するときに、 `ICoreWebView2NavigationCompletedEventHandler` 以前にメソッドを実装したインスタンスを指定し `Invoke` ます。  イベントが `NavigationCompleted` 発生すると、 `Invoke` メソッドが要求されます。  最初のパラメーターは、 `ICoreWebView2` イベントを発生させるものです `NavigationCompleted` 。  2番目のパラメーターは、 `ICoreWebView2NavigationCompletedEventArgs` ナビゲーションが正常に完了したかどうかに関する情報を含む、です。  

非同期メソッドの completed ハンドラーのデリゲートインターフェイスと同様に、直接実装することもできます。また、次の WebView2 コードスニペットで使用される WRL コールバック関数を使うこともできます。  

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

## 文字列  

文字列 out パラメーターは `LPWSTR` 、null で終了する文字列です。  要求者は、を使用して文字列を割り当て `CoTaskMemAlloc` ます。  所有権は要求者に転送されます。また、要求者は、を使ってメモリを解放する必要が `CoTaskMemFree` あります。  

パラメーター内の文字列は `LPCWSTR` 、null で終了する文字列です。  リクエスターは、同期関数要求の間、文字列が有効であることを確認します。  この値を、レシーバーでその値をそのまま保持する必要がある場合は、受信者は、文字列値の関連コピーを割り当てる必要があります。  

## URI と JSON の解析  

さまざまなメソッドで Uri と JSON を文字列として指定または受け入れます。  文字列の解析と生成には、独自の好みのライブラリを使用してください。  

アプリで WinRT が利用できる場合は、 `RuntimeClass_Windows_Data_Json_JsonObject` and `IJsonObjectStatics` メソッドを使って JSON 文字列または uri の解析 `RuntimeClass_Windows_Foundation_Uri` と生成を行うことができ `IUriRuntimeClassFactory` ます。  どちらの方法も Win32 アプリで動作します。  

Uri `IUri` を解析するために and を使っている場合は、 `CreateUri` 次の uri 作成フラグを使用して、 `CreateUri` WEBVIEW での uri 解析とより適切な動作を行うことができます。  

```json
Uri_CREATE_ALLOW_IMPLICIT_FILE_SCHEME | Uri_CREATE_NO_DECODE_EXTRA_INFO
```  

<!-- links -->  

[Webview2ReferenceWin3209538Icorewebview2CapturePreview]: ../reference/win32/0-9-538/icorewebview2.md#capturepreview "CapturePreview-インターフェイス ICoreWebView2 |Microsoft ドキュメント"  

[CppCxWrlCallbackFunction]: /cpp/cppcx/wrl/callback-function-wrl "コールバック関数 (WRL) |Microsoft ドキュメント"  
