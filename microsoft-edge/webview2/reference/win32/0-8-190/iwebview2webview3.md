---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 436e0e33180c65afcce0487fffeff5f168dceab7
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654164"
---
# インターフェイス IWebView2WebView3 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface IWebView2WebView3
  : public IWebView2WebView
```

プライマリ WebView オブジェクトによって実装されるその他の機能。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[Stop](#stop) | すべてのナビゲーションと保留中のリソースフェッチを停止します。
[add_NewWindowRequested](#add_newwindowrequested) | NewWindowRequested イベントのイベントハンドラーを追加します。
[remove_NewWindowRequested](#remove_newwindowrequested) | Add_NewWindowRequested で以前に追加されたイベントハンドラーを削除します。
[add_DocumentTitleChanged](#add_documenttitlechanged) | Documentechanged Lechanged イベントのイベントハンドラーを追加します。
[remove_DocumentTitleChanged](#remove_documenttitlechanged) | Add_DocumentTitleChanged で以前に追加されたイベントハンドラーを削除します。
[get_DocumentTitle](#get_documenttitle) | 現在のトップレベルドキュメントのタイトル。

このインターフェイスの QueryInterface は、 [IWebView2WebView](IWebView2WebView.md)を実装するオブジェクトから行うことができます。 詳細については、 [IWebView2WebView](IWebView2WebView.md)インターフェイスを参照してください。

## Members

#### Stop 

すべてのナビゲーションと保留中のリソースフェッチを停止します。

> パブリック HRESULT [Stop](#stop)()

#### add_NewWindowRequested 

NewWindowRequested イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_NewWindowRequested](#add_newwindowrequested)([IWebView2NewWindowRequestedEventHandler](IWebView2NewWindowRequestedEventHandler.md) * eventHandler、EventRegistrationToken * token)

ウィンドウを開くなど、WebView 内のコンテンツが新しいウィンドウを開くように要求したときに発生します。 アプリは、開かれたウィンドウと見なされるターゲット webview を渡すことができます。

```cpp
    // Register a handler for the NewWindowRequested event.
    // This handler will defer the event, create a new app window, and then once the
    // new window is ready, it'll provide that new window's WebView as the response to
    // the request.
    CHECK_FAILURE(m_webView->add_NewWindowRequested(
        Callback<IWebView2NewWindowRequestedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2NewWindowRequestedEventArgs* args) {
                wil::com_ptr<IWebView2Deferral> deferral;
                CHECK_FAILURE(args->GetDeferral(&deferral));

                auto newAppWindow = new AppWindow(L"");
                newAppWindow->m_onWebViewFirstInitialized = [args, deferral, newAppWindow]() {
                    CHECK_FAILURE(args->put_NewWindow(newAppWindow->m_webView.get()));
                    CHECK_FAILURE(args->put_Handled(TRUE));
                    CHECK_FAILURE(deferral->Complete());
                };

                return S_OK;
            })
            .Get(),
        nullptr));
```

#### remove_NewWindowRequested 

Add_NewWindowRequested で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_NewWindowRequested](#remove_newwindowrequested)(EventRegistrationToken token)

#### add_DocumentTitleChanged 

Documentechanged Lechanged イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_DocumentTitleChanged](#add_documenttitlechanged)([IWebView2DocumentTitleChangedEventHandler](IWebView2DocumentTitleChangedEventHandler.md) * eventHandler、EventRegistrationToken * token)

イベントは、WebView の DocumentTitle プロパティが変更されたとき、または NavigationCompleted イベントの前または後に発生する可能性があるときに発生します。

```cpp
    // Register a handler for the DocumentTitleChanged event.
    // This handler just announces the new title on the window's title bar.
    CHECK_FAILURE(m_webView->add_DocumentTitleChanged(
        Callback<IWebView2DocumentTitleChangedEventHandler>(
            [this](IWebView2WebView3* sender, IUnknown* args) -> HRESULT {
                wil::unique_cotaskmem_string title;
                CHECK_FAILURE(sender->get_DocumentTitle(&title));
                SetWindowText(m_appWindow->GetMainWindow(), title.get());
                return S_OK;
            })
            .Get(),
        &m_documentTitleChangedToken));
```

#### remove_DocumentTitleChanged 

Add_DocumentTitleChanged で以前に追加されたイベントハンドラーを削除します。

> パブリック HRESULT [remove_DocumentTitleChanged](#remove_documenttitlechanged)(EventRegistrationToken token)

#### get_DocumentTitle 

現在のトップレベルドキュメントのタイトル。

> パブリック HRESULT [get_DocumentTitle](#get_documenttitle)(LPWSTR * title)

ドキュメントに明示的なタイトルが含まれていない場合、または空の場合は、ドキュメントの URI と一致しないかもしれない既定値が使用されます。

