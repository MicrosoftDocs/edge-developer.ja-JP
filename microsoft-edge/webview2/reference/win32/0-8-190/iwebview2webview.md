---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2WebView
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 7ef58d19bc5284a3e71dc8be16f3865239047a10
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878121"
---
# 0.8.355-インターフェイス IWebView2WebView 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface IWebView2WebView
  : public IUnknown
```

WebView2 では、最新の Edge web ブラウザー技術を使用して、web コンテンツをホストすることができます。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Settings](#get_settings) | [IWebView2Settings](IWebView2Settings.md)オブジェクトには、実行中の WebView のさまざまな変更可能な設定が含まれています。
[get_Source](#get_source) | 現在の最上位レベルのドキュメントの URI。
[検索](#navigate) | 最上位レベルのドキュメントを指定した URI に移動します。
[MoveFocus](#movefocus) | WebView にフォーカスを移動します。
[NavigateToString](#navigatetostring) | 新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。
[add_NavigationStarting](#add_navigationstarting) | NavigationStarting イベントのイベントハンドラーを追加します。
[remove_NavigationStarting](#remove_navigationstarting) | Add_NavigationStarting で以前に追加されたイベントハンドラーを削除します。
[add_DocumentStateChanged](#add_documentstatechanged) | DocumentStateChanged イベントのイベントハンドラーを追加します。
[remove_DocumentStateChanged](#remove_documentstatechanged) | Add_DocumentStateChanged で以前に追加されたイベントハンドラーを削除します。
[add_NavigationCompleted](#add_navigationcompleted) | NavigationCompleted イベントのイベントハンドラーを追加します。
[remove_NavigationCompleted](#remove_navigationcompleted) | Add_NavigationCompleted で以前に追加されたイベントハンドラーを削除します。
[add_FrameNavigationStarting](#add_framenavigationstarting) | FrameNavigationStarting イベントのイベントハンドラーを追加します。
[remove_FrameNavigationStarting](#remove_framenavigationstarting) | Add_FrameNavigationStarting で以前に追加されたイベントハンドラーを削除します。
[add_MoveFocusRequested](#add_movefocusrequested) | MoveFocusRequested されたイベントのイベントハンドラーを追加します。
[remove_MoveFocusRequested](#remove_movefocusrequested) | Add_MoveFocusRequested で以前に追加されたイベントハンドラーを削除します。
[add_GotFocus](#add_gotfocus) | GotFocus イベントのイベントハンドラーを追加します。
[remove_GotFocus](#remove_gotfocus) | Add_GotFocus で以前に追加されたイベントハンドラーを削除します。
[add_LostFocus](#add_lostfocus) | LostFocus イベントのイベントハンドラーを追加します。
[remove_LostFocus](#remove_lostfocus) | Add_LostFocus で以前に追加されたイベントハンドラーを削除します。
[add_WebResourceRequested_deprecated](#add_webresourcerequested_deprecated) | この API は廃止されます。新しい add_WebResourceRequested API を使用してください。
[remove_WebResourceRequested](#remove_webresourcerequested) | Add_WebResourceRequested で以前に追加されたイベントハンドラーを削除します。
[add_ScriptDialogOpening](#add_scriptdialogopening) | Scriptの開始イベントのイベントハンドラーを追加します。
[remove_ScriptDialogOpening](#remove_scriptdialogopening) | Add_ScriptDialogOpening で以前に追加されたイベントハンドラーを削除します。
[add_ZoomFactorChanged](#add_zoomfactorchanged) | ZoomFactorChanged イベントのイベントハンドラーを追加します。
[remove_ZoomFactorChanged](#remove_zoomfactorchanged) | Add_ZoomFactorChanged で以前に追加されたイベントハンドラーを削除します。
[add_PermissionRequested](#add_permissionrequested) | PermissionRequested されたイベントのイベントハンドラーを追加します。
[remove_PermissionRequested](#remove_permissionrequested) | Add_PermissionRequested で以前に追加されたイベントハンドラーを削除します。
[add_ProcessFailed](#add_processfailed) | ProcessFailed イベントのイベントハンドラーを追加します。
[remove_ProcessFailed](#remove_processfailed) | Add_ProcessFailed で以前に追加されたイベントハンドラーを削除します。
[AddScriptToExecuteOnDocumentCreated](#addscripttoexecuteondocumentcreated) | グローバルオブジェクトの作成後、HTML ドキュメントが解析されてから、HTML ドキュメントに含まれている他のスクリプトが実行される前に、指定された JavaScript を実行する必要があるスクリプトのリストに追加します。
[RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated) | AddScriptToExecuteOnDocumentCreated によって追加された、対応する JavaScript を削除します。
[Execuスクリプト](#executescript) | WebView でレンダリングされた現在のトップレベルドキュメントの javascript パラメーターから JavaScript コードを実行します。
[CapturePreview](#capturepreview) | WebView が表示されている画像をキャプチャします。
[再](#reload) | 現在のページを再読み込みします。
[get_Bounds](#get_bounds) | Webview の境界。
[put_Bounds](#put_bounds) | 境界プロパティを設定します。
[get_ZoomFactor](#get_zoomfactor) | WebView の現在のページのズームファクター。
[put_ZoomFactor](#put_zoomfactor) | ZoomFactor プロパティを設定します。
[get_IsVisible](#get_isvisible) | IsVisible プロパティは、webview の表示と非表示を切り替えるかどうかを決定します。
[put_IsVisible](#put_isvisible) | IsVisible プロパティを設定します。
[PostWebMessageAsJson](#postwebmessageasjson) | 指定した webMessage をこの[IWebView2WebView]()のトップレベルのドキュメントに投稿します。
[PostWebMessageAsString](#postwebmessageasstring) | これは、JavaScript オブジェクトの JSON 文字列表現ではなく、単純な文字列のメッセージを投稿するためのヘルパーです。
[add_WebMessageReceived](#add_webmessagereceived) | このイベントは、IsWebMessageEnabled 設定が設定され、webview 呼び出しの最上位のドキュメントになったときに発生 `window.chrome.webview.postMessage` します。
[remove_WebMessageReceived](#remove_webmessagereceived) | Add_WebMessageReceived で以前に追加されたイベントハンドラーを削除します。
[Close](#close) | Webview を閉じ、基になるブラウザーインスタンスをクリーンアップします。
[Calldevon Protocolメソッド](#calldevtoolsprotocolmethod) | 非同期の Devて Protocol メソッドを呼び出します。
[add_DevToolsProtocolEventReceived](#add_devtoolsprotocoleventreceived) | Devツールプロトコルイベントをサブスクライブします。
[remove_DevToolsProtocolEventReceived](#remove_devtoolsprotocoleventreceived) | Add_DevToolsProtocolEventReceived で以前に追加されたイベントハンドラーを削除します。
[get_BrowserProcessId](#get_browserprocessid) | WebView をホストしているブラウザープロセスのプロセス id。
[get_CanGoBack](#get_cangoback) | Webview をナビゲーション履歴の前のページに移動できます。
[get_CanGoForward](#get_cangoforward) | Webview をナビゲーション履歴の次のページに移動できます。
[GoBack](#goback) | ナビゲーション履歴で、webview を前のページに移動します。
[GoForward](#goforward) | Webview をナビゲーション履歴の次のページに移動します。
[WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#webview2_capture_preview_image_format) | [IWebView2WebView:: CapturePreview](#capturepreview)メソッドで使用されている画像形式。
[WEBVIEW2_SCRIPT_DIALOG_KIND](#webview2_script_dialog_kind) | [IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md)インターフェイスで使用される JavaScript ダイアログの種類。
[WEBVIEW2_PROCESS_FAILED_KIND](#webview2_process_failed_kind) | [IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md)インターフェイスで使用されているプロセスエラーの種類。
[WEBVIEW2_PERMISSION_TYPE](#webview2_permission_type) | アクセス許可要求の種類。
[WEBVIEW2_PERMISSION_STATE](#webview2_permission_state) | アクセス許可要求に対する応答。
[WEBVIEW2_MOVE_FOCUS_REASON](#webview2_move_focus_reason) | フォーカスを移動する理由。
[WEBVIEW2_WEB_ERROR_STATUS](#webview2_web_error_status) | Web ナビゲーションのエラー状態の値。
[WEBVIEW2_WEB_RESOURCE_CONTEXT](#webview2_web_resource_context) | Web リソース要求コンテキストの列挙。

## ナビゲーションイベント

ナビゲーションイベントの通常のシーケンスは、NavigationStarting、DocumentStateChanged、Navigationstarting です。

![dot-inline-dotgraph-1.png](media/dot-inline-dotgraph-1.png)

これは、同じ NavigationId イベント arg を持つナビゲーションイベント用であることに注意してください。 異なる NavigationId イベント引数を持つナビゲーションイベントは、重複する可能性があります。 たとえば、ナビゲーションを開始したときに NavigationStarting イベントが発生してから別のナビゲーションを開始した場合は、最初のナビで開始される navigationstarting 後に、2番目のナビゲーションのナビゲートが続いて、2番目のナビゲーションについて、該当するすべてのナビゲーションイベントが表示されます。 エラーが発生した場合は、ナビゲーションがエラーページに続いているかどうかによって、DocumentStateChanged イベントが発生していない可能性があります。 HTTP リダイレクトの場合、1つの行に複数の NavigationStarting イベントが存在します。最初の列の後には、IsRedirect フラグが設定されています。

WebView 内のサブフレームの場合、唯一のナビゲーションイベントは NavigationStarting イベントです。これは、ホストがサブフレームナビゲーションをブロックする機能を提供します。

## プロセスモデル

WebView2 は、Edge web ブラウザーと同じプロセスモデルを使用します。 ユーザーデータディレクトリを指定する WebView2 の呼び出しプロセスを提供するユーザーセッションの指定したユーザーデータディレクトリごとに、1つの Edge ブラウザープロセスが存在します。 つまり、1つの Edge ブラウザープロセスが複数の通話プロセスを処理している可能性があり、1つの呼び出しプロセスが複数の Edge ブラウザープロセスを使用している可能性があります。

![dot-inline-dotgraph-2.png](media/dot-inline-dotgraph-2.png)

ブラウザープロセスが表示されない場合は、いくつかのレンダラープロセスが存在します。 これらは、さまざまな WebViews で複数のフレームを処理するために必要に応じて作成されます。 レンダラープロセスの数は、サイト分離ブラウザー機能と、関連付けられている WebViews でレンダリングされた個別の切断元の数によって異なります。

![dot-inline-dotgraph-3.png](media/dot-inline-dotgraph-3.png)

クラッシュとハングに対処するには、これらのブラウザーと ProcessFailure イベントを使ってプロセスをレンダリングします。

Close メソッドを使用して、関連するブラウザーとレンダラープロセスを安全にシャットダウンできます。

## スレッドモデル

WebView2 は、UI スレッドで作成する必要があります。 特にメッセージポンプを持つスレッド。 すべてのコールバックがそのスレッドで発生し、WebView への呼び出しはそのスレッドで実行する必要があります。 他のスレッドから WebView を使うことは安全ではありません。

イベントハンドラーと完了ハンドラーを含むコールバックは逐次実行されます。 つまり、イベントハンドラーを実行していて、メッセージループを開始した場合、他のイベントハンドラーまたは完了コールバックによって reentrantly の実行が開始されません。

## セキュリティ

実行前に、必ず WebView の Source プロパティを確認してください。 Executesscript、PostWebMessageAsJson、Postwebmessageasjson などのメソッドを使って、WebView に情報を送信します。 ナビゲーションを引き起こしているページのページまたはスクリプトをエンドユーザーが操作している場合、WebView が別のページに移動している可能性があります。 同様に、AddScriptToExecuteOnDocumentCreated には細心の注意を払ってください。 今後のすべてのナビゲーションでは、このスクリプトが実行され、特定の元にのみ意図した情報へのアクセスを提供している場合、HTML ドキュメントはすべて、アクセス権を持つ可能性があります。

ExecuteScript の呼び出しの結果を調べるとき、WebMessageReceived イベントが発生した場合、または WebView の HTML ドキュメントから情報を受信するその他のメカニズムを確認する場合は、HTML ドキュメントの URI が予期したとおりであることを確認します。

WebView に送信するメッセージを構築する場合は、PostWebMessageAsJson の使用をお勧めし、JSON ライブラリを使って JSON 文字列パラメーターを構築します。 これにより、JSON 文字列またはスクリプトへのエンコード情報の発生を回避することができます。また、攻撃者によって制御される入力によって、残りの JSON メッセージを変更したり、任意のスクリプトを実行したりすることはできません。

## 文字列型

文字列 out パラメーターは、LPWSTR null で終了された文字列です。 呼び出し先は、、Cotaskmemalloc を使って文字列を割り当てます。 所有権は、呼び出し元に転送され、CoTaskMemFree を使ってメモリを解放することができます。

パラメーター内の文字列は、LPCWSTR null で終了する文字列です。 呼び出し元は、同期関数呼び出しの間、文字列が有効であることを保証します。 呼び出し先がその値を関数呼び出しが完了した後のある時点まで保持する必要がある場合、呼び出し元は、その値の文字列値のコピーを割り当てる必要があります。

## URI と JSON の解析

さまざまなメソッドで Uri と JSON を文字列として指定または受け入れます。 これらの文字列の解析と生成には、独自の好みのライブラリを使用してください。

アプリで WinRT が利用できる場合は `RuntimeClass_Windows_Data_Json_JsonObject` 、 `IJsonObjectStatics` JSON 文字列の解析または生成、 `RuntimeClass_Windows_Foundation_Uri` および uri の解析と生成を行うことができ `IUriRuntimeClassFactory` ます。 これらはどちらも Win32 アプリで動作します。

IUri と CreateUri を使って Uri を解析する場合は、次の URI の作成フラグを使って、WebView の URI 解析とより厳密に一致するようにします。 `Uri_CREATE_ALLOW_IMPLICIT_FILE_SCHEME | Uri_CREATE_NO_DECODE_EXTRA_INFO`

## デバッグ

標準のショートカット (または) で DevTools を開く。 `F12` `Ctrl+Shift+I` `--auto-open-devtools-for-tabs`コマンド引数スイッチを使うと、WebView を最初に作成したときに、DevTools ウィンドウをすぐに開くことができます。 ブラウザープロセスに追加のコマンドライン引数を指定する方法については、CreateWebView のドキュメントを参照してください。 WebView2 のさまざまなビルドを実行する場合は、CreateWebView ドキュメントでアプリケーションを変更せずに、LoaderOverride レジストリキーを確認してください。

## バージョン

特定のバージョンの SDK を使ってアプリをビルドすると、アプリは、インストールされているブラウザーバイナリの以前のバージョンまたは新しいバージョンで終了する可能性があります。 WebView2 のバージョン1.0.0.0 以降では、更新中に、SDK がインストールされているブラウザーバイナリのさまざまなバージョンで動作しなくなる可能性があります。 バージョン1.0.0.0 以降の SDK では、次のベストプラクティスに従って、インストールされているブラウザーのさまざまなバージョンを使用できます。

API への変更を考慮するために、DLL エクスポート CreateWebView2Environment を呼び出すときや、いずれかの WebView2 オブジェクトで QueryInterface を呼び出す場合は、エラーかどうかを確認してください。 E_NOINTERFACE の戻り値は、SDK が Edge ブラウザーのバイナリと互換性がないことを示します。

QueryInterface からのエラーのチェックは、SDK が Edge ブラウザーのバージョンよりも新しい場合や、アプリが Edge ブラウザーに認識されないインターフェイスを使用しようとした場合にも考慮されます。

インターフェイスが利用できない場合は、可能であれば関連する機能を無効にするか、ブラウザーを更新する必要があることをエンドユーザーに知らせることができます。

## Members

#### get_Settings 

[IWebView2Settings](IWebView2Settings.md)オブジェクトには、実行中の WebView のさまざまな変更可能な設定が含まれています。

> パブリック HRESULT [get_Settings](#get_settings)([IWebView2Settings](IWebView2Settings.md) * * 設定)

#### get_Source 

現在の最上位レベルのドキュメントの URI。

> パブリック HRESULT [get_Source](#get_source)(LPWSTR * uri)

この値は、別のサイトやフラグメントナビゲーションへの移動など、一部の状況では、DocumentStateChanged イベントの発生の一部として変更される可能性があります。 ページの再読み込みや、現在のページと同じ URL を持つ、他の種類のナビゲーションにも同じように表示されます。

```cpp
    // Register a handler for the DocumentStateChanged event.
    // This handler will read the webview's source URI and update
    // the app's address bar.
    CHECK_FAILURE(m_webView->add_DocumentStateChanged(
        Callback<IWebView2DocumentStateChangedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2DocumentStateChangedEventArgs* args)
                -> HRESULT {
                wil::unique_cotaskmem_string uri;
                sender->get_Source(&uri);
                if (wcscmp(uri.get(), L"about:blank") == 0)
                {
                    uri = wil::make_cotaskmem_string(L"");
                }
                SetWindowText(m_toolbar->addressBarWindow, uri.get());

                return S_OK;
            })
            .Get(),
        &m_documentStateChangedToken));
```

#### 検索 

最上位レベルのドキュメントを指定した URI に移動します。

> パブリック HRESULT[移動](#navigate)(LPCWSTR uri)

詳細については、ナビゲーションイベントを参照してください。 これによってナビゲーションが開始されることに注意してください。この操作が完了すると、対応する NavigationStarting イベントが発生します。

```cpp
void ControlComponent::NavigateToAddressBar()
{
    WCHAR uri[2048] = L"";
    GetWindowText(m_toolbar->addressBarWindow, uri, ARRAYSIZE(uri));
    CHECK_FAILURE(m_webView->Navigate(uri));
}
```

#### MoveFocus 

WebView にフォーカスを移動します。

> パブリック HRESULT [MoveFocus](#movefocus)([WEBVIEW2_MOVE_FOCUS_REASON](#webview2_move_focus_reason)の理由)

WebView はフォーカスを取得し、WebView でホストされているページ内の対応する要素にフォーカスが設定されます。 プログラム的な理由により、フォーカスは前にフォーカスされた要素、または、前にフォーカスされている要素がない場合は既定の要素に設定されます。 次の理由から、フォーカスは最初の要素に設定されます。 前の理由から、フォーカスは最後の要素に設定されます。 また、WebView または Tab キーをクリックするなど、ユーザーの操作によってフォーカスを取得することもできます。 Tab キーを押した場合は、次のタブと shift キーを押しながら tab キーを押すと、[次へ] または [前のページ] を使用して MoveFocus を呼び出すことができます。 または、アプリがメッセージループの一部として IsDialogMessage を呼び出して、プラットフォームがタブを自動処理できるようにすることができます。 プラットフォームは、すべてのウィンドウを通じて WS_TABSTOP で回転します。 WebView が IsDialogMessage からフォーカスを取得すると、tab と shift + tab の最初または最後の要素にフォーカスが内部的に配置されます。

```cpp
    while (GetMessage(&msg, nullptr, 0, 0))
    {
        if (!TranslateAccelerator(msg.hwnd, hAccelTable, &msg))
        {
            // Calling IsDialogMessage handles Tab traversal automatically. If the
            // app wants the platform to auto handle tab, then call IsDialogMessage
            // before calling TranslateMessage/DispatchMessage. If the app wants to
            // handle tabbing itself, then skip calling IsDialogMessage and call
            // TranslateMessage/DispatchMessage directly.
            if (!g_autoTabHandle || !IsDialogMessage(GetAncestor(msg.hwnd, GA_ROOT), &msg))
            {
                TranslateMessage(&msg);
                DispatchMessage(&msg);
            }
        }
    }
```

```cpp
        if (wParam == VK_TAB)
        {
            // Find out if the window is one we've customized for tab handling
            for (int i = 0; i < m_tabbableWindows.size(); i++)
            {
                if (m_tabbableWindows[i].first == hWnd)
                {
                    if (GetKeyState(VK_SHIFT) < 0)
                    {
                        TabBackwards(i);
                    }
                    else
                    {
                        TabForwards(i);
                    }
                    return true;
                }
            }
        }
```

```cpp
void ControlComponent::TabForwards(int currentIndex)
{
    // Find first enabled window after the active one
    for (int i = currentIndex + 1; i < m_tabbableWindows.size(); i++)
    {
        HWND hwnd = m_tabbableWindows.at(i).first;
        if (IsWindowEnabled(hwnd))
        {
            SetFocus(hwnd);
            return;
        }
    }
    // If this is the last enabled window, tab forwards into the WebView.
    m_webView->MoveFocus(WEBVIEW2_MOVE_FOCUS_REASON_NEXT);
}

void ControlComponent::TabBackwards(int currentIndex)
{
    // Find first enabled window before the active one
    for (int i = currentIndex - 1; i >= 0; i--)
    {
        HWND hwnd = m_tabbableWindows.at(i).first;
        if (IsWindowEnabled(hwnd))
        {
            SetFocus(hwnd);
            return;
        }
    }
    // If this is the last enabled window, tab forwards into the WebView.
    CHECK_FAILURE(m_webView->MoveFocus(WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS));
}
```

#### NavigateToString 

新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。

> パブリック HRESULT [NavigateToString](#navigatetostring)(LPCWSTR htmlcontent)

HtmlContent パラメーターの文字数は 2 MB 以下でなければなりません。 新しいページの起点は "空白" になります。

```cpp
                static const PCWSTR htmlContent =
                    L"<h1>Domain Blocked</h1>"
                    L"<p>You've attempted to navigate to a domain in the blocked "
                    L"sites list. Press back to return to the previous page.</p>";
                CHECK_FAILURE(sender->NavigateToString(htmlContent));
```

#### add_NavigationStarting 

NavigationStarting イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_NavigationStarting](#add_navigationstarting)([IWebView2NavigationStartingEventHandler](IWebView2NavigationStartingEventHandler.md) * eventHandler、EventRegistrationToken * token)

NavigationStarting は、WebView メインフレームが別の URI に移動するためのアクセス許可を要求しているときに発生します。 これは、リダイレクトの場合にも発生します。

```cpp
    // Register a handler for the NavigationStarting event.
    // This handler will check the domain being navigated to, and if the domain
    // matches a list of blocked sites, it will cancel the navigation and
    // possibly display a warning page.  It will also disable JavaScript on
    // selected websites.
    CHECK_FAILURE(m_webView->add_NavigationStarting(
        Callback<IWebView2NavigationStartingEventHandler>(
            [this](IWebView2WebView* sender,
                   IWebView2NavigationStartingEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Uri(&uri));

        if (ShouldBlockUri(uri.get()))
        {
            CHECK_FAILURE(args->put_Cancel(true));

            // If the user clicked a link to navigate, show a warning page.
            BOOL userInitiated;
            CHECK_FAILURE(args->get_IsUserInitiated(&userInitiated));
            if (userInitiated)
            {
                static const PCWSTR htmlContent =
                    L"<h1>Domain Blocked</h1>"
                    L"<p>You've attempted to navigate to a domain in the blocked "
                    L"sites list. Press back to return to the previous page.</p>";
                CHECK_FAILURE(sender->NavigateToString(htmlContent));
            }
        }
        // Changes to settings will apply at the next navigation, which includes the
        // navigation after a NavigationStarting event.  We can use this to change
        // settings according to what site we're visiting.
        if (ShouldBlockScriptForUri(uri.get()))
        {
            m_settings->put_IsScriptEnabled(FALSE);
        }
        else
        {
            m_settings->put_IsScriptEnabled(m_isScriptEnabled);
        }
        return S_OK;
    }).Get(), &m_navigationStartingToken));
```

#### remove_NavigationStarting 

Add_NavigationStarting で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_NavigationStarting](#remove_navigationstarting)(EventRegistrationToken token)

#### add_DocumentStateChanged 

DocumentStateChanged イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_DocumentStateChanged](#add_documentstatechanged)([IWebView2DocumentStateChangedEventHandler](IWebView2DocumentStateChangedEventHandler.md) * eventHandler、EventRegistrationToken * token)

DocumentStateChanged は、webview のメインフレームでの読み込みが開始されたとき、または同じページナビゲーション (フラグメントナビゲーションや履歴の推移など) が発生した場合に発生します。 これは、NavigationStarting イベントの後に、Navigationstarting イベントの前に続きます。

```cpp
    // Register a handler for the DocumentStateChanged event.
    // This handler will read the webview's source URI and update
    // the app's address bar.
    CHECK_FAILURE(m_webView->add_DocumentStateChanged(
        Callback<IWebView2DocumentStateChangedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2DocumentStateChangedEventArgs* args)
                -> HRESULT {
                wil::unique_cotaskmem_string uri;
                sender->get_Source(&uri);
                if (wcscmp(uri.get(), L"about:blank") == 0)
                {
                    uri = wil::make_cotaskmem_string(L"");
                }
                SetWindowText(m_toolbar->addressBarWindow, uri.get());

                return S_OK;
            })
            .Get(),
        &m_documentStateChangedToken));
```

#### remove_DocumentStateChanged 

Add_DocumentStateChanged で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_DocumentStateChanged](#remove_documentstatechanged)(EventRegistrationToken token)

#### add_NavigationCompleted 

NavigationCompleted イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_NavigationCompleted](#add_navigationcompleted)([IWebView2NavigationCompletedEventHandler](IWebView2NavigationCompletedEventHandler.md) * eventHandler、EventRegistrationToken * token)

NavigationCompleted イベントは、WebView が完全に読み込まれたとき (読み込みが開始された場合)、またはエラーが発生して読み込みを停止したときに発生します。

```cpp
    // Register a handler for the NavigationCompleted event.
    // Check whether the navigation succeeded, and if not, do something.
    // Also update the Back, Forward, and Cancel buttons.
    CHECK_FAILURE(m_webView->add_NavigationCompleted(
        Callback<IWebView2NavigationCompletedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2NavigationCompletedEventArgs* args)
                -> HRESULT {
                BOOL success;
                CHECK_FAILURE(args->get_IsSuccess(&success));
                if (!success)
                {
                    WEBVIEW2_WEB_ERROR_STATUS webErrorStatus;
                    CHECK_FAILURE(args->get_WebErrorStatus(&webErrorStatus));
                    if (webErrorStatus == WEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED)
                    {
                        // Do something here if you want to handle a specific error case.
                        // In most cases this isn't necessary, because the WebView will
                        // display its own error page automatically.
                    }
                }

                BOOL canGoBack;
                BOOL canGoForward;
                sender->get_CanGoBack(&canGoBack);
                sender->get_CanGoForward(&canGoForward);
                EnableWindow(m_toolbar->backWindow, canGoBack);
                EnableWindow(m_toolbar->forwardWindow, canGoForward);
                EnableWindow(m_toolbar->cancelWindow, FALSE);
                return S_OK;
            })
            .Get(),
        &m_navigationCompletedToken));
```

#### remove_NavigationCompleted 

Add_NavigationCompleted で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_NavigationCompleted](#remove_navigationcompleted)(EventRegistrationToken token)

#### add_FrameNavigationStarting 

FrameNavigationStarting イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_FrameNavigationStarting](#add_framenavigationstarting)([IWebView2NavigationStartingEventHandler](IWebView2NavigationStartingEventHandler.md) * eventHandler、EventRegistrationToken * token)

FrameNavigationStarting は、WebView の子フレームが別の URI に移動するためのアクセス許可を要求しているときに発生します。 これは、リダイレクトの場合にも発生します。

```cpp
    // Register a handler for the FrameNavigationStarting event.
    // This handler will prevent a frame from navigating to a blocked domain.
    CHECK_FAILURE(m_webView->add_FrameNavigationStarting(
        Callback<IWebView2NavigationStartingEventHandler>(
            [this](IWebView2WebView* sender,
                   IWebView2NavigationStartingEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Uri(&uri));

        if (ShouldBlockUri(uri.get()))
        {
            CHECK_FAILURE(args->put_Cancel(true));
        }
        return S_OK;
    }).Get(), &m_frameNavigationStartingToken));
```

#### remove_FrameNavigationStarting 

Add_FrameNavigationStarting で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_FrameNavigationStarting](#remove_framenavigationstarting)(EventRegistrationToken token)

#### add_MoveFocusRequested 

MoveFocusRequested されたイベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_MoveFocusRequested](#add_movefocusrequested)([IWebView2MoveFocusRequestedEventHandler](IWebView2MoveFocusRequestedEventHandler.md) * eventHandler、EventRegistrationToken * token)

MoveFocusRequested は、ユーザーが WebView から tab キーを移動しようとしたときに発生します。 このイベントが発生すると、WebView のフォーカスが変更されません。

```cpp
    // Register a handler for the MoveFocusRequested event.
    // This event will be fired when the user tabs out of the webview.
    // The handler will focus another window in the app, depending on which
    // direction the focus is being shifted.
    CHECK_FAILURE(m_webView->add_MoveFocusRequested(
        Callback<IWebView2MoveFocusRequestedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2MoveFocusRequestedEventArgs* args)
                -> HRESULT {
                if (!g_autoTabHandle)
                {
                    WEBVIEW2_MOVE_FOCUS_REASON reason;
                    CHECK_FAILURE(args->get_Reason(&reason));

                    if (reason == WEBVIEW2_MOVE_FOCUS_REASON_NEXT)
                    {
                        TabForwards(-1);
                    }
                    else if (reason == WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS)
                    {
                        TabBackwards(int(m_tabbableWindows.size()));
                    }
                    CHECK_FAILURE(args->put_Handled(TRUE));
                }
                return S_OK;
            })
            .Get(),
        &m_moveFocusRequestedToken));
```

#### remove_MoveFocusRequested 

Add_MoveFocusRequested で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_MoveFocusRequested](#remove_movefocusrequested)(EventRegistrationToken token)

#### add_GotFocus 

GotFocus イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_GotFocus](#add_gotfocus)([IWebView2FocusChangedEventHandler](IWebView2FocusChangedEventHandler.md) * eventHandler、EventRegistrationToken * token)

GotFocus は、WebView がフォーカスを取得したときに発生します。

#### remove_GotFocus 

Add_GotFocus で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_GotFocus](#remove_gotfocus)(EventRegistrationToken token)

#### add_LostFocus 

LostFocus イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_LostFocus](#add_lostfocus)([IWebView2FocusChangedEventHandler](IWebView2FocusChangedEventHandler.md) * eventHandler、EventRegistrationToken * token)

このとき、WebView はフォーカスを失ったときに発生します。 MoveFocusRequested イベントが発生した場合は、MoveFocusRequested イベントが発生したときに、フォーカスはまだ WebView に残っています。 フォーカスが失われたのは、アプリのコードが、または MoveFocusRequested イベントを WebView から離した場合にのみ、後で発生します。

#### remove_LostFocus 

Add_LostFocus で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_LostFocus](#remove_lostfocus)(EventRegistrationToken token)

#### add_WebResourceRequested_deprecated 

この API は廃止されます。新しい add_WebResourceRequested API を使用してください。

> パブリック HRESULT [add_WebResourceRequested_deprecated](#add_webresourcerequested_deprecated)(LPCWSTR * Const urlfilter、[WEBVIEW2_WEB_RESOURCE_CONTEXT](#webview2_web_resource_context) * Const ResourceContextFilter、SIZE_T filterlength、[IWebView2WebResourceRequestedEventHandler](IWebView2WebResourceRequestedEventHandler.md) * eventHandler、EventRegistrationToken * token)

WebResourceRequested イベントのイベントハンドラーを追加します。 WebView が HTTP 要求を実行したときに発生します。 UrlFilter を使って、リッスンする url のサイズフィルターの長さを指定してリストを渡します。 各 url エントリでもワイルドカードをサポートしています。 ' * ' は0個以上の文字と一致し、"?" は1文字に一致します。 UrlFilter の各エントリについて、WebResourceRequested を起動する必要があるリソースの種類を表す、一致する resourceContextFilter を提供します。 FilterLength が0の場合、イベントはすべてのネットワーク要求に対して発生します。 サポートされているリソースコンテキストは、ドキュメント、スタイルシート、画像、メディア、フォント、スクリプト、XHR、取得です。

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

#### remove_WebResourceRequested 

Add_WebResourceRequested で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_WebResourceRequested](#remove_webresourcerequested)(EventRegistrationToken token)

#### add_ScriptDialogOpening 

Scriptの開始イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_ScriptDialogOpening](#add_scriptdialogopening)([IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md) * eventHandler、EventRegistrationToken * token)

イベントは、webview の JavaScript ダイアログ (警告、確認、またはプロンプト) が表示されたときに発生します。 このイベントは、IWebView2Settings:: Aredefaultscript プロパティが false に設定されている場合にのみ発生します。

```cpp
    // Register a handler for the ScriptDialogOpening event.
    // This handler will set up a custom prompt dialog for the user,
    // and may defer the event if the setting to defer dialogs is enabled.
    CHECK_FAILURE(m_webView->add_ScriptDialogOpening(
        Callback<IWebView2ScriptDialogOpeningEventHandler>(
            [this](
                IWebView2WebView* sender,
                IWebView2ScriptDialogOpeningEventArgs* args) -> HRESULT
    {
        wil::com_ptr<IWebView2ScriptDialogOpeningEventArgs> eventArgs = args;
        auto showDialog = [this, eventArgs]
        {
            wil::unique_cotaskmem_string uri;
            WEBVIEW2_SCRIPT_DIALOG_KIND type;
            wil::unique_cotaskmem_string message;
            wil::unique_cotaskmem_string defaultText;

            CHECK_FAILURE(eventArgs->get_Uri(&uri));
            CHECK_FAILURE(eventArgs->get_Kind(&type));
            CHECK_FAILURE(eventArgs->get_Message(&message));
            CHECK_FAILURE(eventArgs->get_DefaultText(&defaultText));

            std::wstring promptString = std::wstring(L"The page at '")
                + uri.get() + L"' says:";
            TextInputDialog dialog(
                m_appWindow->GetMainWindow(),
                L"Script Dialog",
                promptString.c_str(),
                message.get(),
                defaultText.get(),
                /* readonly */ type != WEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT);
            if (dialog.confirmed)
            {
                CHECK_FAILURE(eventArgs->put_ResultText(dialog.input.c_str()));
                CHECK_FAILURE(eventArgs->Accept());
            }
        };

        if (m_deferScriptDialogs)
        {
            wil::com_ptr<IWebView2Deferral> deferral;
            CHECK_FAILURE(args->GetDeferral(&deferral));
            m_completeDeferredDialog = [showDialog, deferral]
            {
                showDialog();
                CHECK_FAILURE(deferral->Complete());
            };
        }
        else
        {
            showDialog();
        }

        return S_OK;
    }).Get(), &m_scriptDialogOpeningToken));
```

#### remove_ScriptDialogOpening 

Add_ScriptDialogOpening で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_ScriptDialogOpening](#remove_scriptdialogopening)(EventRegistrationToken token)

#### add_ZoomFactorChanged 

ZoomFactorChanged イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)([IWebView2ZoomFactorChangedEventHandler](IWebView2ZoomFactorChangedEventHandler.md) * eventHandler、EventRegistrationToken * token)

WebView の ZoomFactor プロパティが変更されると、イベントが発生します。 呼び出し元が ZoomFactor プロパティを変更したか、ユーザーが手動でズームを変更したために、イベントが発生する可能性があります。 ZoomFactor プロパティを使用して呼び出し元によって変更された場合、内部のズームファクターはすぐに更新され、ZoomFactorChanged イベントは発生しません。 WebView は、各サイトで使用されている直前の拡大率を関連付けます。 そのため、別のページに移動するときにズーム倍率が変更される可能性があります。 このため、ズームファクターが変更された場合、ZoomFactorChanged イベントは DocumentStateChanged イベントの直後に発生します。

```cpp
    // Register a handler for the ZoomFactorChanged event.
    // This handler just announces the new level of zoom on the window's title bar.
    CHECK_FAILURE(m_webView->add_ZoomFactorChanged(
        Callback<IWebView2ZoomFactorChangedEventHandler>(
            [this](IWebView2WebView* sender, IUnknown* args) -> HRESULT {
                double zoomFactor;
                CHECK_FAILURE(sender->get_ZoomFactor(&zoomFactor));

                std::wstring message = L"WebView2APISample (Zoom: " +
                                       std::to_wstring(int(zoomFactor * 100)) + L"%)";
                SetWindowText(m_appWindow->GetMainWindow(), message.c_str());
                return S_OK;
            })
            .Get(),
        &m_zoomFactorChangedToken));
```

#### remove_ZoomFactorChanged 

Add_ZoomFactorChanged で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_ZoomFactorChanged](#remove_zoomfactorchanged)(EventRegistrationToken token)

#### add_PermissionRequested 

PermissionRequested されたイベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_PermissionRequested](#add_permissionrequested)([IWebView2PermissionRequestedEventHandler](IWebView2PermissionRequestedEventHandler.md) * eventHandler、EventRegistrationToken * token)

WebView のコンテンツが権限のある一部のリソースにアクセスするためのアクセス許可を要求したときに発生します。

```cpp
    // Register a handler for the PermissionRequested event.
    // This handler prompts the user to allow or deny the request.
    CHECK_FAILURE(m_webView->add_PermissionRequested(
        Callback<IWebView2PermissionRequestedEventHandler>(
            [this](
                IWebView2WebView* sender,
                IWebView2PermissionRequestedEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        WEBVIEW2_PERMISSION_TYPE type = WEBVIEW2_PERMISSION_TYPE_UNKNOWN_PERMISSION;
        BOOL userInitiated = FALSE;

        CHECK_FAILURE(args->get_Uri(&uri));
        CHECK_FAILURE(args->get_PermissionType(&type));
        CHECK_FAILURE(args->get_IsUserInitiated(&userInitiated));

        std::wstring message = L"Do you want to grant permission for ";
        message += NameOfPermissionType(type);
        message += L" to the website at ";
        message += uri.get();
        message += L"?\n\n";
        message += (userInitiated
            ? L"This request came from a user gesture."
            : L"This request did not come from a user gesture.");

        int response = MessageBox(nullptr, message.c_str(), L"Permission Request",
                                   MB_YESNOCANCEL | MB_ICONWARNING);

        WEBVIEW2_PERMISSION_STATE state =
              response == IDYES ? WEBVIEW2_PERMISSION_STATE_ALLOW
            : response == IDNO  ? WEBVIEW2_PERMISSION_STATE_DENY
            :                     WEBVIEW2_PERMISSION_STATE_DEFAULT;
        CHECK_FAILURE(args->put_State(state));

        return S_OK;
    }).Get(), &m_permissionRequestedToken));
```

#### remove_PermissionRequested 

Add_PermissionRequested で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_PermissionRequested](#remove_permissionrequested)(EventRegistrationToken token)

#### add_ProcessFailed 

ProcessFailed イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_ProcessFailed](#add_processfailed)([IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md) * eventHandler、EventRegistrationToken * token)

WebView プロセスが予期せず終了した場合、または応答不能になったときに発生します。

```cpp
    // Register a handler for the ProcessFailed event.
    // This handler checks if the browser process failed, and asks the user if
    // they want to recreate the webview.
    CHECK_FAILURE(m_webView->add_ProcessFailed(
        Callback<IWebView2ProcessFailedEventHandler>(
            [this](IWebView2WebView* sender,
                IWebView2ProcessFailedEventArgs* args) -> HRESULT
    {
        WEBVIEW2_PROCESS_FAILED_KIND failureType;
        CHECK_FAILURE(args->get_ProcessFailedKind(&failureType));
        if (failureType == WEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED)
        {
            int button = MessageBox(
                m_appWindow->GetMainWindow(),
                L"Browser process exited unexpectedly.  Recreate webview?",
                L"Browser process exited",
                MB_YESNO);
            if (button == IDYES)
            {
                m_appWindow->ReinitializeWebView();
            }
        }
        return S_OK;
    }).Get(), &m_processFailedToken));
```

#### remove_ProcessFailed 

Add_ProcessFailed で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_ProcessFailed](#remove_processfailed)(EventRegistrationToken token)

#### AddScriptToExecuteOnDocumentCreated 

グローバルオブジェクトの作成後、HTML ドキュメントが解析されてから、HTML ドキュメントに含まれている他のスクリプトが実行される前に、指定された JavaScript を実行する必要があるスクリプトのリストに追加します。

> パブリック HRESULT [AddScriptToExecuteOnDocumentCreated](#addscripttoexecuteondocumentcreated)(LPCWSTR JavaScript、[IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler](IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler.md) * handler)

挿入されたスクリプトは、RemoveScriptToExecuteOnDocumentCreated で削除されるまで、将来のすべての上位レベルのドキュメントと子フレームのナビゲーションに適用されます。 これは非同期的に適用されるため、今後のナビゲーションでスクリプトを実行する準備ができていることを確認する前に、完了ハンドラーが実行されるまで待機する必要があります。

[サンドボックス](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox)のプロパティまたは[コンテンツセキュリティポリシーの HTTP ヘッダー](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy)によって、HTML ドキュメントに何らかのサンドボックスが含まれている場合は、このスクリプトの実行に影響します。 たとえば、' allow als ' キーワードが設定されていない場合、関数への呼び出し `alert` は無視されます。

```cpp
// Prompt the user for some script and register it to execute whenever a new page loads.
void ScriptComponent::AddInitializeScript()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Add Initialize Script",
        L"Initialization Script:",
        L"Enter the JavaScript code to run as the initialization script that "
            L"runs before any script in the HTML document.",
    // This example script stops child frames from opening new windows.  Because
    // the initialization script runs before any script in the HTML document, we
    // can trust the results of our checks on window.parent and window.top.
        L"if (window.parent !== window.top) {\r\n"
        L"    delete window.open;\r\n"
        L"}");
    if (dialog.confirmed)
    {
        m_webView->AddScriptToExecuteOnDocumentCreated(
            dialog.input.c_str(),
            Callback<IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler>(
                [this](HRESULT error, PCWSTR id) -> HRESULT
        {
            m_lastInitializeScriptId = id;
            MessageBox(nullptr, id, L"AddScriptToExecuteOnDocumentCreated Id", MB_OK);
            return S_OK;
        }).Get());

    }
}
```

#### RemoveScriptToExecuteOnDocumentCreated 

AddScriptToExecuteOnDocumentCreated によって追加された、対応する JavaScript を削除します。

> パブリック HRESULT [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)(LPCWSTR id)

#### Execuスクリプト 

WebView でレンダリングされた現在のトップレベルドキュメントの javascript パラメーターから JavaScript コードを実行します。

> パブリック HRESULT の[Executescript](#executescript)(LPCWSTR JavaScript、[IWebView2ExecuteScriptCompletedHandler](IWebView2ExecuteScriptCompletedHandler.md) * handler)

これは非同期的に実行されます。完了すると、ExecuteScriptCompletedHandler パラメーターでハンドラーが指定されると、指定された JavaScript を評価した結果を使って Invoke メソッドが呼び出されます。 結果値は、JSON でエンコードされた文字列です。 結果が定義されていない場合、参照循環が含まれている場合、または JSON にエンコードできない場合は、JSON null 値が文字列 ' null ' として返されます。 明示的な戻り値のない関数は undefined を返します。 実行されたスクリプトが未処理の例外をスローした場合、結果は ' null ' にもなります。 このメソッドは非同期的に適用されます。 1つのドキュメントに対して webview を実行しているときに、操作が行われたときに、その呼び出しが行われてから JavaScript が実行される前に、移動が行われると、スクリプトは実行されず、ハンドラーは errorCode パラメーターの E_FAIL で呼び出されます。 実行方法 IsScriptEnabled が FALSE に設定されている場合でも、スクリプトは機能します。

```cpp
// Prompt the user for some script and then execute it.
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
            Callback<IWebView2ExecuteScriptCompletedHandler>(
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

#### CapturePreview 

WebView が表示されている画像をキャプチャします。

> パブリック HRESULT [CapturePreview](#capturepreview)([WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#webview2_capture_preview_image_format) imageformat、IStream * imagestream、[IWebView2CapturePreviewCompletedHandler](IWebView2CapturePreviewCompletedHandler.md) * handler)

ImageFormat パラメーターを使用して、画像の形式を指定します。 結果のイメージバイナリデータは、指定された imageStream パラメーターに書き込まれます。 CapturePreview がストリームへの書き込みを終了すると、指定された handler パラメーターの Invoke メソッドが呼び出されます。

```cpp
// Show the user a file selection dialog, then save a screenshot of the WebView
// to the selected file.
void FileComponent::SaveScreenshot()
{
    OPENFILENAME openFileName = {};
    openFileName.lStructSize = sizeof(openFileName);
    openFileName.hwndOwner = nullptr;
    openFileName.hInstance = nullptr;
    WCHAR fileName[MAX_PATH] = L"WebView2_Screenshot.png";
    openFileName.lpstrFile = fileName;
    openFileName.lpstrFilter = L"PNG File\0*.png\0";
    openFileName.nMaxFile = ARRAYSIZE(fileName);
    openFileName.Flags = OFN_OVERWRITEPROMPT;

    if (GetSaveFileName(&openFileName))
    {
        wil::com_ptr<IStream> stream;
        CHECK_FAILURE(SHCreateStreamOnFileEx(
            fileName, STGM_READWRITE | STGM_CREATE, FILE_ATTRIBUTE_NORMAL, TRUE, nullptr,
            &stream));

        HWND mainWindow = m_appWindow->GetMainWindow();

        CHECK_FAILURE(m_webView->CapturePreview(
            WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG, stream.get(),
            Callback<IWebView2CapturePreviewCompletedHandler>(
                [mainWindow](HRESULT error_code) -> HRESULT {
                    CHECK_FAILURE(error_code);

                    MessageBox(mainWindow, L"Preview Captured", L"Preview Captured", MB_OK);
                    return S_OK;
                })
                .Get()));
    }
}
```

#### 再 

現在のページを再読み込みします。

> パブリック HRESULT [Reload](#reload)()

これは、すべてのナビゲーションイベント (HTTP キャッシュ内のエントリを含む) を含む、現在のトップレベルドキュメントの URI に移動する操作と似ています。 ただし、戻る/forward 履歴は変更されません。

#### get_Bounds 

Webview の境界。

> パブリック HRESULT [get_Bounds](#get_bounds)(RECT * 境界)

境界は親 HWND を基準としています。 アプリには、WebView を配置する2つの方法があります。

1. WebView 親 HWND である子 HWND を作成します。 WebView が必要な場所にこのウィンドウを配置します。 この場合、(0, 0) を使用して、WebView の Bound の左上隅 (offset) にします。

1. アプリの一番上のウィンドウは、WebView 親 HWND として使います。 Webview の左上隅を、アプリ内で適切に配置されるように設定します。 バインドされた値は、ホストの座標空間にあります。

#### put_Bounds 

境界プロパティを設定します。

> パブリック HRESULT [put_Bounds](#put_bounds)(四角形の境界)

```cpp
// Update the bounds of the WebView window to fit available space.
void ViewComponent::ResizeWebView()
{
    RECT desiredBounds = m_webViewBounds;
    desiredBounds.bottom = LONG(
        (m_webViewBounds.bottom - m_webViewBounds.top) * m_webViewRatio + m_webViewBounds.top);
    desiredBounds.right = LONG(
        (m_webViewBounds.right - m_webViewBounds.left) * m_webViewRatio + m_webViewBounds.left);

    m_webView->put_Bounds(desiredBounds);
}
```

#### get_ZoomFactor 

WebView の現在のページのズームファクター。

> パブリック HRESULT [get_ZoomFactor](#get_zoomfactor)(Double * ZoomFactor)

ズーム倍率はサイトごとに維持されます。 ズーム倍率を変更すると、ページレイアウトが変更される場合があることに注意して `window.innerWidth/innerHeight` ください。 WebView を別のサイトからページに移動すると、前のページに設定されているズーム倍率は適用されません。 アプリで特定のページの拡大率を設定する場合は、最初に DocumentStateChanged イベントハンドラーに配置する必要があります。 これにより、指定されたズームファクターの ZoomFactorChanged イベントを受け取る前に、永続化されたズームファクターの ZoomFactorChanged イベントを受け取ることに注意してください。 0以下の zoomFactor を指定することはできません。 WebView には、内部でサポートされているズームファクター範囲もあります。 指定したズームファクターがその範囲外の場合は、範囲内に収まるように正規化され、実際に適用されたズームファクターに対して ZoomFactorChanged イベントが発生します。 この範囲の正規化が行われると、ZoomFactor プロパティは、ZoomFactor プロパティの前の変更時に指定されたズーム率を報告します。これは、webview が正規化されたズームファクターを適用した後に ZoomFactorChanged イベントが受信されるまでです。

#### put_ZoomFactor 

ZoomFactor プロパティを設定します。

> パブリック HRESULT [put_ZoomFactor](#put_zoomfactor)(double ZoomFactor)

#### get_IsVisible 

IsVisible プロパティは、webview の表示と非表示を切り替えるかどうかを決定します。

> パブリック HRESULT [get_IsVisible](#get_isvisible)(BOOL * IsVisible)

IsVisible が false に設定されている場合、webview は透過的であり、表示されません。 ただし、この操作を行っても、webview (CreateWebView に渡された HWND パラメーター) が含まれているウィンドウには影響しません。 ウィンドウを非表示にする場合は、IsVisible プロパティを変更するだけでなく、直接 ShowWindow を呼び出します。 子ウィンドウとして WebView を実行しても、上のウィンドウを最小化または復元したときにウィンドウメッセージが表示されません。 パフォーマンスを向上させるために、アプリのウィンドウを最小化して、アプリウィンドウが復元されたときに true に戻す場合は、WebView の IsVisible プロパティを false に設定する必要があります。 アプリウィンドウでは、WM_SYSCOMMAND メッセージを受信したときに SC_MINIMIZE と SC_RESTORE コマンドを処理することができます。

```cpp
void ViewComponent::ToggleVisibility()
{
    BOOL visible;
    m_webView->get_IsVisible(&visible);
    m_isVisible = !visible;
    m_webView->put_IsVisible(m_isVisible);
}
```

#### put_IsVisible 

IsVisible プロパティを設定します。

> パブリック HRESULT [put_IsVisible](#put_isvisible)(BOOL IsVisible)

```cpp
    if (message == WM_SYSCOMMAND)
    {
        if (wParam == SC_MINIMIZE)
        {
            // Hide the webview when the app window is minimized.
            m_webView->put_IsVisible(FALSE);
        }
        else if (wParam == SC_RESTORE)
        {
            // When the app window is restored, show the webview
            // (unless the user has toggle visibility off).
            if (m_isVisible)
            {
                m_webView->put_IsVisible(TRUE);
            }
        }
    }
```

#### PostWebMessageAsJson 

指定した webMessage をこの[IWebView2WebView]()のトップレベルのドキュメントに投稿します。

> パブリック HRESULT [Postwebmessageasjson](#postwebmessageasjson)(LPCWSTR webmessageasjson)

最上位のドキュメントのウィンドウには、"." というメッセージイベントが発生します。 このドキュメントの JavaScript は、次のようにしてイベントをサブスクライブし、サブスクライブを取り消すことができます。 

```cpp
window.chrome.webview.addEventListener('message', handler)
window.chrome.webview.removeEventListener('message', handler)
```

 イベント引数は、のインスタンス `MessageEvent` です。 IWebView2Settings:: IsWebMessageEnabled の設定は true である必要があります。また、このメソッドは E_INVALIDARG で失敗します。 イベント arg の data プロパティは、JSON 文字列として JavaScript オブジェクトに解析された webMessage 文字列のパラメーターです。 イベント arg の source プロパティは、オブジェクトへの参照です `window.chrome.webview` 。 Webview の HTML ドキュメントからホストにメッセージを送信する方法については、「SetWebMessageReceivedEventHandler」を参照してください。 このメッセージは非同期的に送信されます。 メッセージがページに投稿される前にナビゲーションが発生した場合、メッセージは送信されません。

```cpp
    // Setup the web message received event handler before navigating to
    // ensure we don't miss any messages.
    CHECK_FAILURE(m_webView->add_WebMessageReceived(
        Microsoft::WRL::Callback<IWebView2WebMessageReceivedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2WebMessageReceivedEventArgs* args)
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Source(&uri));

        // Always validate that the origin of the message is what you expect.
        if (uri.get() != m_sampleUri)
        {
            return S_OK;
        }
        wil::unique_cotaskmem_string messageRaw;
        CHECK_FAILURE(args->get_WebMessageAsString(&messageRaw));
        std::wstring message = messageRaw.get();

        if (message.compare(0, 13, L"SetTitleText ") == 0)
        {
            m_appWindow->SetTitleText(message.substr(13).c_str());
        }
        else if (message.compare(L"GetWindowBounds") == 0)
        {
            RECT bounds = m_appWindow->GetWindowBounds();
            std::wstring reply =
                L"{\"WindowBounds\":\"Left:" + std::to_wstring(bounds.left)
                + L"\\nTop:" + std::to_wstring(bounds.top)
                + L"\\nRight:" + std::to_wstring(bounds.right)
                + L"\\nBottom:" + std::to_wstring(bounds.bottom)
                + L"\"}";
            CHECK_FAILURE(sender->PostWebMessageAsJson(reply.c_str()));
        }
        return S_OK;
    }).Get(), &m_webMessageReceivedToken));
```

#### PostWebMessageAsString 

これは、JavaScript オブジェクトの JSON 文字列表現ではなく、単純な文字列のメッセージを投稿するためのヘルパーです。

> パブリック HRESULT [Postwebmessageasstring](#postwebmessageasstring)(LPCWSTR webmessageasstring)

これは、PostWebMessageAsJson とまったく同じように動作し `window.chrome.webview` ますが、message イベント arg の data プロパティは、webMessageAsString と同じ値を持つ文字列になります。 JSON オブジェクトではなく単純な文字列を使って通信する場合は、PostWebMessageAsJson の代わりに、これを使います。

#### add_WebMessageReceived 

このイベントは、IsWebMessageEnabled 設定が設定され、webview 呼び出しの最上位のドキュメントになったときに発生 `window.chrome.webview.postMessage` します。

> パブリック HRESULT [add_WebMessageReceived](#add_webmessagereceived)([IWebView2WebMessageReceivedEventHandler](IWebView2WebMessageReceivedEventHandler.md) * handler、EventRegistrationToken * token)

PostMessage 関数は、 `void postMessage(object)` JSON 変換でサポートされているオブジェクトです。

```cpp
        window.chrome.webview.addEventListener('message', arg => {
            if ("SetColor" in arg.data) {
                document.getElementById("colorable").style.color = arg.data.SetColor;
            }
            if ("WindowBounds" in arg.data) {
                document.getElementById("window-bounds").value = arg.data.WindowBounds;
            }
        });

        function SetTitleText() {
            let titleText = document.getElementById("title-text");
            window.chrome.webview.postMessage(`SetTitleText ${titleText.value}`);
        }
        function GetWindowBounds() {
            window.chrome.webview.postMessage("GetWindowBounds");
        }
```

 PostMessage が呼び出されると、この SetWebMessageReceivedEventHandler メソッドによって設定された[IWebView2WebMessageReceivedEventHandler](IWebView2WebMessageReceivedEventHandler.md)が、postMessage のオブジェクトパラメーターを JSON 文字列に変換して呼び出されます。

```cpp
    // Setup the web message received event handler before navigating to
    // ensure we don't miss any messages.
    CHECK_FAILURE(m_webView->add_WebMessageReceived(
        Microsoft::WRL::Callback<IWebView2WebMessageReceivedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2WebMessageReceivedEventArgs* args)
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Source(&uri));

        // Always validate that the origin of the message is what you expect.
        if (uri.get() != m_sampleUri)
        {
            return S_OK;
        }
        wil::unique_cotaskmem_string messageRaw;
        CHECK_FAILURE(args->get_WebMessageAsString(&messageRaw));
        std::wstring message = messageRaw.get();

        if (message.compare(0, 13, L"SetTitleText ") == 0)
        {
            m_appWindow->SetTitleText(message.substr(13).c_str());
        }
        else if (message.compare(L"GetWindowBounds") == 0)
        {
            RECT bounds = m_appWindow->GetWindowBounds();
            std::wstring reply =
                L"{\"WindowBounds\":\"Left:" + std::to_wstring(bounds.left)
                + L"\\nTop:" + std::to_wstring(bounds.top)
                + L"\\nRight:" + std::to_wstring(bounds.right)
                + L"\\nBottom:" + std::to_wstring(bounds.bottom)
                + L"\"}";
            CHECK_FAILURE(sender->PostWebMessageAsJson(reply.c_str()));
        }
        return S_OK;
    }).Get(), &m_webMessageReceivedToken));
```

#### remove_WebMessageReceived 

Add_WebMessageReceived で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_WebMessageReceived](#remove_webmessagereceived)(EventRegistrationToken token)

#### Close 

Webview を閉じ、基になるブラウザーインスタンスをクリーンアップします。

> パブリック HRESULT [Close](#close)()

ブラウザーの instace をクリーンアップすると、webview に電源が入っているリソースが解放されます。 他の webviews が使用していない場合は、ブラウザーインスタンスがシャットダウンされます。

Close を呼び出した後、すべてのメソッド呼び出しは失敗し、イベントハンドラーは発生しなくなります。 具体的には、WebView が呼び出されたときに、WebView はそのイベントハンドラーへの参照を解放します。

"閉じる" は、WebView が最終的な参照を失い、destructed されたときに暗黙的に呼び出されます。 ただし、WebView とアプリコードの間の参照が誤って循環しないように、明示的に Close を呼び出すことをお勧めします。 具体的には、イベントハンドラーで WebView への参照をキャプチャすると、WebView とイベントハンドラーの間に参照サイクルが作成されます。 Close は、すべてのイベントハンドラーを解放することで、このサイクルを中断します。 ただし、このような状況を回避するには、webview で明示的に Close を呼び出し、webview を適切にクリーンアップするために、WebView への参照をキャプチャしないようにすることをお勧めします。

```cpp
// Close the WebView and deinitialize related state. This doesn't close the app window.
void AppWindow::CloseWebView()
{
    DeleteAllComponents();
    if (m_webView)
    {
        m_webView->Close();
        m_webView = nullptr;
    }
    m_webViewEnvironment = nullptr;
}
```

#### Calldevon Protocolメソッド 

非同期の Devて Protocol メソッドを呼び出します。

> パブリック HRESULT[呼び出し DevLPCWSTR Protocolmethod](#calldevtoolsprotocolmethod)(METHODNAME、LPCWSTR ParametersAsJson、[IWebView2CallDevToolsProtocolMethodCompletedHandler](IWebView2CallDevToolsProtocolMethodCompletedHandler.md) * handler)

使用できるメソッドの一覧と説明については、「 [Devtools プロトコルビューアー](https://aka.ms/DevToolsProtocolDocs) 」をご覧ください。 MethodName パラメーターは、書式のメソッドの完全な名前です `{domain}.{method}` 。 ParametersAsJson パラメーターは、対応するメソッドのパラメーターを含む JSON 形式の文字列です。 メソッドが非同期的に完了すると、ハンドラーの Invoke メソッドが呼び出されます。 Invoke は、JSON 文字列としてメソッドの戻りオブジェクトを使って呼び出されます。

```cpp
// Prompt the user for the name and parameters of a CDP method, then call it.
void ScriptComponent::CallCdpMethod()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Call CDP Method",
        L"CDP method name:",
        L"Enter the CDP method name to call, followed by a space,\r\n"
            L"followed by the parameters in JSON format.",
        L"Runtime.evaluate {\"expression\":\"alert(\\\"test\\\")\"}");
    if (dialog.confirmed)
    {
        size_t delimiterPos = dialog.input.find(L' ');
        std::wstring methodName = dialog.input.substr(0, delimiterPos);
        std::wstring methodParams =
            (delimiterPos < dialog.input.size()
                ? dialog.input.substr(delimiterPos + 1)
                : L"{}");

        m_webView->CallDevToolsProtocolMethod(
            methodName.c_str(),
            methodParams.c_str(),
            Callback<IWebView2CallDevToolsProtocolMethodCompletedHandler>(
                [](HRESULT error, PCWSTR resultJson) -> HRESULT
                {
                    MessageBox(nullptr, resultJson, L"CDP Method Result", MB_OK);
                    return S_OK;
                }).Get());
    }
}
```

#### add_DevToolsProtocolEventReceived 

Devツールプロトコルイベントをサブスクライブします。

> パブリック HRESULT [add_DevToolsProtocolEventReceived](#add_devtoolsprotocoleventreceived)(LPCWSTR EventName、[IWebView2DevToolsProtocolEventReceivedEventHandler](IWebView2DevToolsProtocolEventReceivedEventHandler.md) * handler、EventRegistrationToken * token)

使用できるイベントの一覧と説明については、「 [Devtools プロトコルビューアー](https://aka.ms/DevToolsProtocolDocs) 」をご覧ください。 EventName パラメーターは、形式におけるイベントの完全な名前です `{domain}.{event}` 。 ハンドラーの Invoke メソッドは、対応する Devて Protocol イベントが発生するたびに呼び出されます。 Invoke は、JSON 文字列として CDP イベントのパラメーターオブジェクトを含むイベント引数オブジェクトで呼び出されます。

```cpp
// Prompt the user to name a CDP event, and then subscribe to that event.
void ScriptComponent::SubscribeToCdpEvent()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Subscribe to CDP Event",
        L"CDP event name:",
        L"Enter the name of the CDP event to subscribe to.\r\n"
            L"You may also have to call the \"enable\" method of the\r\n"
            L"event's domain to receive events (for example \"Log.enable\").\r\n",
        L"Log.entryAdded");
    if (dialog.confirmed)
    {
        std::wstring eventName = dialog.input;
        // If we are already subscribed to this event, unsubscribe first.
        auto preexistingToken = m_devToolsProtocolEventReceivedTokenMap.find(eventName);
        if (preexistingToken != m_devToolsProtocolEventReceivedTokenMap.end())
        {
            CHECK_FAILURE(m_webView->remove_DevToolsProtocolEventReceived(
                eventName.c_str(),
                preexistingToken->second));
        }

        CHECK_FAILURE(m_webView->add_DevToolsProtocolEventReceived(
            eventName.c_str(),
            Callback<IWebView2DevToolsProtocolEventReceivedEventHandler>(
                [eventName](IWebView2WebView* sender,
                            IWebView2DevToolsProtocolEventReceivedEventArgs* args)
                -> HRESULT
        {
            wil::unique_cotaskmem_string parameterObjectAsJson;
            CHECK_FAILURE(args->get_ParameterObjectAsJson(&parameterObjectAsJson));
            MessageBox(nullptr, parameterObjectAsJson.get(),
                       (L"CDP Event Fired: " + eventName).c_str(), MB_OK);
            return S_OK;
        }).Get(), &m_devToolsProtocolEventReceivedTokenMap[eventName]));
    }
}
```

#### remove_DevToolsProtocolEventReceived 

Add_DevToolsProtocolEventReceived で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_DevToolsProtocolEventReceived](#remove_devtoolsprotocoleventreceived)(LPCWSTR EventName, EventRegistrationToken token)

#### get_BrowserProcessId 

WebView をホストしているブラウザープロセスのプロセス id。

> パブリック HRESULT [get_BrowserProcessId](#get_browserprocessid)(UINT32 * 値)

#### get_CanGoBack 

Webview をナビゲーション履歴の前のページに移動できます。

> パブリック HRESULT [get_CanGoBack](#get_cangoback)(BOOL * CanGoBack)

DocumentStateChanged イベントを使用して値を変更 get_CanGoBack ます。

#### get_CanGoForward 

Webview をナビゲーション履歴の次のページに移動できます。

> パブリック HRESULT [get_CanGoForward](#get_cangoforward)(BOOL * CanGoForward)

DocumentStateChanged イベントを使用して値を変更 get_CanGoForward ます。

#### GoBack 

ナビゲーション履歴で、webview を前のページに移動します。

> パブリック HRESULT [GoBack](#goback)()

#### GoForward 

Webview をナビゲーション履歴の次のページに移動します。

> パブリック HRESULT [Goforward](#goforward)()

#### WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT 

[IWebView2WebView:: CapturePreview](#capturepreview)メソッドで使用されている画像形式。

> 列挙型[WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#webview2_capture_preview_image_format)

 値                         | 説明
--------------------------------|---------------------------------------------
WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG            | PNG 画像形式。
WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_JPEG            | JPEG イメージ形式。

#### WEBVIEW2_SCRIPT_DIALOG_KIND 

[IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md)インターフェイスで使用される JavaScript ダイアログの種類。

> 列挙型[WEBVIEW2_SCRIPT_DIALOG_KIND](#webview2_script_dialog_kind)

 値                         | 説明
--------------------------------|---------------------------------------------
WEBVIEW2_SCRIPT_DIALOG_KIND_ALERT            | ウィンドウで呼び出されるダイアログ。警告 JavaScript 関数。
WEBVIEW2_SCRIPT_DIALOG_KIND_CONFIRM            | ウィンドウを通じて呼び出されるダイアログ。 JavaScript 関数を確認してください。
WEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT            | Window というプロンプトで呼び出されるダイアログ。

#### WEBVIEW2_PROCESS_FAILED_KIND 

[IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md)インターフェイスで使用されているプロセスエラーの種類。

> 列挙型[WEBVIEW2_PROCESS_FAILED_KIND](#webview2_process_failed_kind)

 値                         | 説明
--------------------------------|---------------------------------------------
WEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED            | ブラウザープロセスが予期せず終了したことを示します。
WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_EXITED            | レンダープロセスが予期せず終了したことを示します。
WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE            | レンダープロセスが応答しなくなったことを示します。

#### WEBVIEW2_PERMISSION_TYPE 

アクセス許可要求の種類。

> 列挙型[WEBVIEW2_PERMISSION_TYPE](#webview2_permission_type)

 値                         | 説明
--------------------------------|---------------------------------------------
WEBVIEW2_PERMISSION_TYPE_UNKNOWN_PERMISSION            | 不明な権限。
WEBVIEW2_PERMISSION_TYPE_MICROPHONE            | オーディオをキャプチャするためのアクセス許可。
WEBVIEW2_PERMISSION_TYPE_CAMERA            | ビデオをキャプチャするためのアクセス許可。
WEBVIEW2_PERMISSION_TYPE_GEOLOCATION            | 位置情報へのアクセス許可。
WEBVIEW2_PERMISSION_TYPE_NOTIFICATIONS            | Web 通知を送信するためのアクセス許可。
WEBVIEW2_PERMISSION_TYPE_OTHER_SENSORS            | 汎用センサーへのアクセス許可。
WEBVIEW2_PERMISSION_TYPE_CLIPBOARD_READ            | ユーザーのジェスチャを使わずにシステムクリップボードを読み取る権限。

#### WEBVIEW2_PERMISSION_STATE 

アクセス許可要求に対する応答。

> 列挙型[WEBVIEW2_PERMISSION_STATE](#webview2_permission_state)

 値                         | 説明
--------------------------------|---------------------------------------------
WEBVIEW2_PERMISSION_STATE_DEFAULT            | 既定のブラウザー動作を使用します。通常はユーザーに判断を求めます。
WEBVIEW2_PERMISSION_STATE_ALLOW            | 権限の要求を許可します。
WEBVIEW2_PERMISSION_STATE_DENY            | 権限の要求を拒否します。

#### WEBVIEW2_MOVE_FOCUS_REASON 

フォーカスを移動する理由。

> 列挙型[WEBVIEW2_MOVE_FOCUS_REASON](#webview2_move_focus_reason)

 値                         | 説明
--------------------------------|---------------------------------------------
WEBVIEW2_MOVE_FOCUS_REASON_PROGRAMMATIC            | コード設定による WebView へのフォーカス。
WEBVIEW2_MOVE_FOCUS_REASON_NEXT            | タブトラバーサルを前方に移動するためにフォーカスを移動する。
WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS            | タブトラバーサルに戻るためにフォーカスを移動する。

#### WEBVIEW2_WEB_ERROR_STATUS 

Web ナビゲーションのエラー状態の値。

> 列挙型[WEBVIEW2_WEB_ERROR_STATUS](#webview2_web_error_status)

 値                         | 説明
--------------------------------|---------------------------------------------
WEBVIEW2_WEB_ERROR_STATUS_UNKNOWN            | 不明なエラーが発生しました。
WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_COMMON_NAME_IS_INCORRECT            | SSL 証明書の共通名が web アドレスと一致しません。
WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_EXPIRED            | SSL 証明書の有効期限が切れています。
WEBVIEW2_WEB_ERROR_STATUS_CLIENT_CERTIFICATE_CONTAINS_ERRORS            | SSL クライアント証明書にエラーが含まれています。
WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_REVOKED            | SSL 証明書が失効しています。
WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_IS_INVALID            | SSL 証明書が無効です。
WEBVIEW2_WEB_ERROR_STATUS_SERVER_UNREACHABLE            | ホストに到達できません。
WEBVIEW2_WEB_ERROR_STATUS_TIMEOUT            | 接続がタイムアウトしました。
WEBVIEW2_WEB_ERROR_STATUS_ERROR_HTTP_INVALID_SERVER_RESPONSE            | サーバーが無効または認識不能な応答を返しました。
WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_ABORTED            | 接続が中止されました。
WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_RESET            | 接続がリセットされました。
WEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED            | インターネット接続が切断されました。
WEBVIEW2_WEB_ERROR_STATUS_CANNOT_CONNECT            | 宛先に接続できません。
WEBVIEW2_WEB_ERROR_STATUS_HOST_NAME_NOT_RESOLVED            | 指定されたホスト名を解決できませんでした。
WEBVIEW2_WEB_ERROR_STATUS_OPERATION_CANCELED            | 操作が取り消されました。
WEBVIEW2_WEB_ERROR_STATUS_REDIRECT_FAILED            | 要求のリダイレクトに失敗しました。
WEBVIEW2_WEB_ERROR_STATUS_UNEXPECTED_ERROR            | 予期しないエラーが発生しました。

#### WEBVIEW2_WEB_RESOURCE_CONTEXT 

Web リソース要求コンテキストの列挙。

> 列挙型[WEBVIEW2_WEB_RESOURCE_CONTEXT](#webview2_web_resource_context)

 値                         | 説明
--------------------------------|---------------------------------------------
WEBVIEW2_WEB_RESOURCE_CONTEXT_ALL            | すべてのリソース。
WEBVIEW2_WEB_RESOURCE_CONTEXT_DOCUMENT            | ドキュメントリソース。
WEBVIEW2_WEB_RESOURCE_CONTEXT_STYLESHEET            | CSS リソース。
WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE            | 画像リソース。
WEBVIEW2_WEB_RESOURCE_CONTEXT_MEDIA            | その他のメディアリソース (ビデオなど)。
WEBVIEW2_WEB_RESOURCE_CONTEXT_FONT            | フォントリソース。
WEBVIEW2_WEB_RESOURCE_CONTEXT_SCRIPT            | スクリプトリソース。
WEBVIEW2_WEB_RESOURCE_CONTEXT_XML_HTTP_REQUEST            | XML HTTP 要求。
WEBVIEW2_WEB_RESOURCE_CONTEXT_FETCH            | API 通信を取得します。
WEBVIEW2_WEB_RESOURCE_CONTEXT_TEXT_TRACK            | TextTrack のリソース。
WEBVIEW2_WEB_RESOURCE_CONTEXT_EVENT_SOURCE            | 
WEBVIEW2_WEB_RESOURCE_CONTEXT_WEBSOCKET            | 
WEBVIEW2_WEB_RESOURCE_CONTEXT_MANIFEST            | 
WEBVIEW2_WEB_RESOURCE_CONTEXT_SIGNED_EXCHANGE            | 
WEBVIEW2_WEB_RESOURCE_CONTEXT_PING            | 
WEBVIEW2_WEB_RESOURCE_CONTEXT_CSP_VIOLATION_REPORT            | 
WEBVIEW2_WEB_RESOURCE_CONTEXT_OTHER            | その他のリソース。
