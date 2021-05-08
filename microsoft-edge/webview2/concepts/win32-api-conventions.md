---
description: Win32 C++ WebView2 API の規則
title: Win32 C++ WebView2 API の規則
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、edge html
ms.openlocfilehash: b5a86751bfe3386058812ca166fa7cf9e0e201dc
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "11535644"
---
# <a name="win32-c-webview2-api-conventions"></a>Win32 C++ WebView2 API の規則  

:::row:::
   :::column span="1":::
      サポートされているプラットフォーム:
   :::column-end:::
   :::column span="2":::
      Win32
   :::column-end:::
:::row-end:::  

## <a name="prerequisites"></a>前提条件  

*   Win32 API の使用経験  

## <a name="async-methods"></a>非同期メソッド  

WebView2 Win32 C++ API の非同期メソッドは、デリゲート インターフェイスを使用して、次の理由で連絡します。  

*   非同期メソッドが完了しました。  
*   成功または失敗のコード。  
*   非同期メソッドの結果。  

すべての非同期メソッドの最終的なパラメーターは、実装を提供するデリゲート インターフェイスへのポインターです。  

デリゲート インターフェイスには、成功または失敗のコードの最初のパラメーター a を受け取る `Invoke` `HRESULT` 1 つのメソッドがあります。  さらに、メソッドに結果がある場合は、メソッドの結果である 2 番目のパラメーターがあります。  たとえば [、ICoreWebView2::CapturePreview][Webview2ReferenceWin32Icorewebview2CapturePreview] メソッドは、最終的なパラメーターとしてポインターを受け取 `ICoreWebView2CapturePreviewCompletedHandler` ります。  メソッド要求 `CapturePreview` を送信するには、実装するポインターの `ICoreWebView2CapturePreviewCompletedHandler` インスタンスを指定します。  次のコード スニペットでは、1 つのメソッドを使用して実装します。  

```cpp
HRESULT Invoke(HRESULT result)
```  

メソッドを実装 `Invoke` し、 `CoreWebView2` 要求が完了 `Invoke` したらメソッド `CapturePreview` を要求します。  1 つのパラメーターは `HRESULT` 、要求の成功または失敗のコードを記述 `CapturePreview` します。  

または、たとえば、要求の成功または失敗コードを提供するメソッドを持つ `ICoreWebView2::ExecuteScript` `Invoke` インスタンスを指定 `ExecuteScript` します。  また、スクリプトの実行結果の JSON である 2 番目のパラメーターも指定します。  

デリゲート インターフェイスを手動で `CompleteHandler` 実装することもできますし、Callback 関数 [(WRL) を使用することもできます][CppCxWrlCallbackFunction]。  [Callback 関数 (WRL) は][CppCxWrlCallbackFunction]、次の WebView2 コード スニペット全体で使用されます。  

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

## <a name="events"></a>イベント  

WebView2 Win32 C++ API のイベントでは、and メソッドペアを使用してイベントの `add_EventName` `remove_EventName` サブスクライブとサブスクライブ解除を行います。  この `add_EventName` メソッドは、イベント ハンドラーのデリゲート インターフェイスを受け取り、出力 `EventRegistrationToken` パラメーターとしてトークンを返します。  メソッド `remove_EventName` はトークンを受 `EventRegistrationToken` け取り、対応するイベント サブスクリプションを購読解除します。  

イベント ハンドラーデリゲート インターフェイスは、非同期メソッドの完了したハンドラー デリゲート インターフェイスと同様に動作します。  イベント ハンドラーのデリゲート インターフェイスを実装し、 `CoreWebView2` イベントが実行されるたびにコールバックを送信します。  すべてのイベント ハンドラーデリゲート インターフェイスには、sender パラメーターの後にイベント args パラメーターが続く `Invoke` 1 つのメソッドがあります。  送信者は、イベントをサブスクライブしたオブジェクトのインスタンスです。  イベント args パラメーターは、現在発生しているイベントに関する情報を含むインターフェイスです。  

たとえば、イベント `NavigationCompleted` on には and `ICoreWebView2` メソッド `ICoreWebView2::add_NavigationCompleted` のペア `ICoreWebView2::remove_NavigationCompleted` があります。  要求を送信するときに、以前に実装したメソッド `ICoreWebView2NavigationCompletedEventHandler` のインスタンスを指定 `Invoke` します。  イベントが `NavigationCompleted` 実行されると、メソッド `Invoke` が要求されます。  最初のパラメーターは、イベントを実行 `NavigationCompleted` します。  2 番目のパラメーターには、ナビゲーションが正常に完了した場合などについての情報が含まれる。  

async メソッドが完了したハンドラー デリゲート インターフェイスと同様に、次のいずれかのアクションを使用してセットアップします。  

*   直接実装します。  
*   次の WebView2 コード スニペットで使用される Callback 関数 [(WRL)][CppCxWrlCallbackFunction] 関数を使用します。  

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

## <a name="strings"></a>文字列  

文字列出力パラメーターは `LPWSTR` 、null 終端文字列です。  要求者は、 を使用して文字列を提供します `CoTaskMemAlloc` 。  所有権は要求者に転送され、要求者が使用してメモリを解放する必要があります `CoTaskMemFree` 。  

文字列入力パラメーターは `LPCWSTR` null 終端文字列です。  要求者は、同期関数要求の期間中、文字列が有効である必要があります。  関数要求が完了した後、レシーバーが値をある時点に格納する必要がある場合、レシーバーは文字列値の関連付けられたコピーを与える必要があります。  

## <a name="uri-and-json-parsing"></a>URI と JSON の解析  

さまざまなメソッドが URI と JSON を文字列として提供または受け入れる。  文字列の解析と生成には、優先ライブラリを使用します。  

アプリで WinRT を使用できる場合は、and メソッドを使用して JSON 文字列またはメソッドを解析または生成し `RuntimeClass_Windows_Data_Json_JsonObject` `IJsonObjectStatics` 、URI を解析および `RuntimeClass_Windows_Foundation_Uri` `IUriRuntimeClassFactory` 生成できます。  どちらのメソッドも Win32 アプリで動作します。  

URI を使用して解析する場合は、次の URI 作成フラグを使用して、WebView での URI 解析とより密接に一致する動作を実行 `IUri` `CreateUri` `CreateUri` できます。  

```json
Uri_CREATE_ALLOW_IMPLICIT_FILE_SCHEME | Uri_CREATE_NO_DECODE_EXTRA_INFO
```  

## <a name="see-also"></a>関連項目  

*   WebView2 Win32 C/C++ の使用を開始するには、[WebView2 の使用を開始する][Webview2IndexGetStarted] ガイドに移動します。  
*   WebView2 API の詳細については、「API リファレンス」 [に移動します][DotnetApiMicrosoftWebWebview2WpfWebview2]。  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a>Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2GetStartedWin32]: ../get-started/win32.md "WebView2 の使用を|Microsoft Docs"  

[Webview2ReferenceWin32Icorewebview2CapturePreview]: /microsoft-edge/webview2/reference/win32/icorewebview2#capturepreview "CapturePreview - インターフェイス ICoreWebView2 |Microsoft Docs"  

[CppCxWrlCallbackFunction]: /cpp/cppcx/wrl/callback-function-wrl "コールバック関数 (WRL) |Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2WpfWebview2]: /dotnet/api/microsoft.web.webview2.wpf.webview2 "WebView2 クラス | Microsoft Docs"  
