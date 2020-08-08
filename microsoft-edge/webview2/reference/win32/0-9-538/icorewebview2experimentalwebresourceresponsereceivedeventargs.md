---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs
ms.openlocfilehash: 056667b4ee1995763fee81c8d7a9be31496f7f3e
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886534"
---
# インターフェイス ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs
  : public IUnknown
```

WebResourceResponseReceived イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Request](#get_request) | Web リソース要求オブジェクト。 このオブジェクトに加えた変更はすべて無視されます。
[get_Response](#get_response) | Web リソース応答オブジェクト。
[PopulateResponseContent](#populateresponsecontent) | 応答のコンテンツストリームを要求する Async メソッド。

送信された要求と受信した返信が含まれます。 注: 応答コンテンツストリームを取得するには、最初に PopulateResponseContent を呼び出し、非同期呼び出しが完了するまで待ちます。そうでない場合、返されるコンテンツストリームオブジェクトは null になります。

## Members

#### get_Request 

Web リソース要求オブジェクト。 このオブジェクトに加えた変更はすべて無視されます。

> パブリック HRESULT [get_Request](#get_request)(ICoreWebView2WebResourceRequest * * Request)

#### get_Response 

Web リソース応答オブジェクト。

> パブリック HRESULT [get_Response](#get_response)(ICoreWebView2WebResourceResponse * * 応答)

このオブジェクトに加えた変更はすべて無視されます。

#### PopulateResponseContent 

応答のコンテンツストリームを要求する Async メソッド。

> パブリック HRESULT [PopulateResponseContent](#populateresponsecontent)([ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler](icorewebview2experimentalwebresourceresponsereceivedeventargspopulateresponsecontentcompletedhandler.md) * handler)

```cpp
                    args->PopulateResponseContent(
                        Callback<
                            ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler>(
                            [this, webResourceRequest, webResourceResponse](HRESULT result) {
                                std::wstring message =
                                    L"{ \"kind\": \"event\", \"name\": "
                                    L"\"WebResourceResponseReceived\", \"args\": {"
                                    L"\"request\": " +
                                    RequestToJsonString(webResourceRequest.get()) +
                                    L", "
                                    L"\"response\": " +
                                    ResponseToJsonString(webResourceResponse.get()) + L"}";

                                message +=
                                    WebViewPropertiesToJsonString(m_webviewEventSource.get());
                                message += L"}";
                                PostEventMessage(message);
                                return S_OK;
                            })
                            .Get());
```
