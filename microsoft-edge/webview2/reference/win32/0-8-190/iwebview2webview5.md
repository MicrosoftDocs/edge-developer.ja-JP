---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2WebView5
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: bc48c5d495c2182ba39b867fdb46ce7af503f5ba
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884688"
---
# 0.8.355-インターフェイス IWebView2WebView5 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2WebView5
  : public IWebView2WebView4
```

プライマリ WebView オブジェクトによって実装されるその他の機能。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[add_ContainsFullScreenElementChanged](#add_containsfullscreenelementchanged) | "の場合、要素のプロパティが変更されたときに通知します。
[remove_ContainsFullScreenElementChanged](#remove_containsfullscreenelementchanged) | 対応する add_ イベントメソッドを使用して、前に追加したイベントハンドラーを削除します。
[get_ContainsFullScreenElement](#get_containsfullscreenelement) | WebView にフルスクリーン HTML 要素が含まれているかどうかを示します。
[add_WebResourceRequested](#add_webresourcerequested) | WebResourceRequested イベントのイベントハンドラーを追加します。
[AddWebResourceRequestedFilter](#addwebresourcerequestedfilter) | URI とリソースのコンテキストフィルターを WebResourceRequested イベントに追加します。
[RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter) | 以前に WebResourceRequested イベントに追加された、一致する WebResource フィルターを削除します。

このインターフェイスの QueryInterface は、 [IWebView2WebView](IWebView2WebView.md)を実装するオブジェクトから行うことができます。 詳細については、 [IWebView2WebView](IWebView2WebView.md)インターフェイスを参照してください。

## Members

#### add_ContainsFullScreenElementChanged 

"の場合、要素のプロパティが変更されたときに通知します。

> パブリック HRESULT [add_ContainsFullScreenElementChanged](#add_containsfullscreenelementchanged)([IWebView2ContainsFullScreenElementChangedEventHandler](IWebView2ContainsFullScreenElementChangedEventHandler.md) * eventHandler、EventRegistrationToken * token)

これは、WebView 内の HTML 要素が、WebView のサイズまたはフルスクリーンのままであることを意味します。 このイベントは、たとえば、ビデオ要素が全画面表示になっている要求の場合に便利です。 次に、Fullfullscreenelementelementのリスナーが、応答で WebView のサイズを変更できます。

```cpp
    // Register a handler for the ContainsFullScreenChanged event.
    CHECK_FAILURE(m_webView->add_ContainsFullScreenElementChanged(
        Callback<IWebView2ContainsFullScreenElementChangedEventHandler>(
            [this](IWebView2WebView5* sender, IUnknown* args) -> HRESULT {
                if (m_fullScreenAllowed)
                {
                    CHECK_FAILURE(sender->get_ContainsFullScreenElement(&m_containsFullscreenElement));
                    if (m_containsFullscreenElement)
                    {
                        EnterFullScreen();
                    }
                    else
                    {
                        ExitFullScreen();
                    }
                }
                return S_OK;
            })
            .Get(),
        nullptr));
```

#### remove_ContainsFullScreenElementChanged 

対応する add_ イベントメソッドを使用して、前に追加したイベントハンドラーを削除します。

> パブリック HRESULT [remove_ContainsFullScreenElementChanged](#remove_containsfullscreenelementchanged)(EventRegistrationToken token)

#### get_ContainsFullScreenElement 

WebView にフルスクリーン HTML 要素が含まれているかどうかを示します。

> パブリック HRESULT [get_ContainsFullScreenElement](#get_containsfullscreenelement)(BOOL * Fullfullscreenelement)

#### add_WebResourceRequested 

WebResourceRequested イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_WebResourceRequested](#add_webresourcerequested)([IWebView2WebResourceRequestedEventHandler](IWebView2WebResourceRequestedEventHandler.md) * eventHandler、EventRegistrationToken * token)

AddWebResourceRequestedFilter で追加された一致する URL とリソースコンテキストフィルターへの HTTP 要求を WebView が実行しているときに発生します。 イベントを発生させるには、少なくとも1つのフィルターを追加する必要があります。

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

#### AddWebResourceRequestedFilter 

URI とリソースのコンテキストフィルターを WebResourceRequested イベントに追加します。

> パブリック HRESULT [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)(LPCWSTR const uri、[WEBVIEW2_WEB_RESOURCE_CONTEXT](IWebView2WebView.md#webview2_web_resource_context) const resourcecontext)

URI パラメーターは、ワイルドカード文字列 (0 以上、"?": 完全に1つ) にすることができます。 nullptr は、L "" と同じです。 リソースコンテキストフィルターの説明については、「enum の WEBVIEW2_WEB_RESOURCE_CONTEXT」を参照してください。

#### RemoveWebResourceRequestedFilter 

以前に WebResourceRequested イベントに追加された、一致する WebResource フィルターを削除します。

> パブリック HRESULT [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)(LPCWSTR const uri、[WEBVIEW2_WEB_RESOURCE_CONTEXT](IWebView2WebView.md#webview2_web_resource_context) const resourcecontext)

同じフィルターが複数回追加された場合は、削除が有効になるまで何度も削除する必要があります。 追加されていないフィルターの E_INVALIDARG を返します。

