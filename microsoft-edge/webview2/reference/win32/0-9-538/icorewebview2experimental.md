---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2Experimental
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2Experimental
ms.openlocfilehash: 98f13193e73781f9f7371db05ed3ca99ca93c128
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886545"
---
# インターフェイス ICoreWebView2Experimental 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2Experimental
  : public IUnknown
```

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[add_WebResourceResponseReceived](#add_webresourceresponsereceived) | WebResourceResponseReceived イベントのイベントハンドラーを追加します。
[remove_WebResourceResponseReceived](#remove_webresourceresponsereceived) | Add_WebResourceResponseReceived で以前に追加された WebResourceResponseReceived イベントハンドラーを削除します。

## Members

#### add_WebResourceResponseReceived 

WebResourceResponseReceived イベントのイベントハンドラーを追加します。

> パブリック HRESULT [add_WebResourceResponseReceived](#add_webresourceresponsereceived)([ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler](icorewebview2experimentalwebresourceresponsereceivedeventhandler.md) * eventHandler、EventRegistrationToken * token)

WebResourceResponseReceived イベントは、WebView が WebResource 要求に対する応答を受信して処理した後に発生します。 イベント引数には、WebResourceResponse によって送信された WebResourceRequest が含まれています。これには、認証ヘッダーなど、関連付けられた WebResourceRequested イベントの一部として含まれていないネットワークスタックによって追加されたヘッダーも含まれています。 
```cpp
    wil::com_ptr<ICoreWebView2Experimental> webviewExperimental;
    CHECK_FAILURE(m_appWindow->GetWebView()->QueryInterface(IID_PPV_ARGS(&webviewExperimental)));
    CHECK_FAILURE(webviewExperimental->add_WebResourceResponseReceived(
        Callback<ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler>(
            [this](
                ICoreWebView2Experimental* sender,
                ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs* args) {           
                wil::com_ptr<ICoreWebView2WebResourceRequest> request;
                CHECK_FAILURE(args->get_Request(&request));
                wil::unique_cotaskmem_string uri;
                CHECK_FAILURE(request->get_Uri(&uri));
                if (wcscmp(uri.get(), L"https://authenticationtest.com/HTTPAuth/") == 0)
                {
                    wil::com_ptr<ICoreWebView2HttpRequestHeaders> requestHeaders;
                    CHECK_FAILURE(request->get_Headers(&requestHeaders));

                    wil::unique_cotaskmem_string authHeaderValue;
                    if (requestHeaders->GetHeader(L"Authorization", &authHeaderValue) == S_OK)
                    {
                        std::wstring message(L"Authorization: ");
                        message += authHeaderValue.get();
                        MessageBox(nullptr, message.c_str(), nullptr, MB_OK);
                        m_appWindow->DeleteComponent(this);
                    }
                }
                
                return S_OK;
            })
            .Get(),
        &m_webResourceResponseReceivedToken));
```

#### remove_WebResourceResponseReceived 

Add_WebResourceResponseReceived で以前に追加された WebResourceResponseReceived イベントハンドラーを削除します。

> パブリック HRESULT [remove_WebResourceResponseReceived](#remove_webresourceresponsereceived)(EventRegistrationToken token)

