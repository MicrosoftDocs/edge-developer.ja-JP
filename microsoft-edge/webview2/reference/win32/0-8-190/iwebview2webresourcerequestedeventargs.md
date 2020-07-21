---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2WebResourceRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: aa5206be13790fd7a783f2afb4471de90fc8f2ae
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885719"
---
# 0.8.355-インターフェイス IWebView2WebResourceRequestedEventArgs 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

WebResourceRequested イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Request](#get_request) | HTTP 要求。
[get_Response](#get_response) | HTTP 応答。
[put_Response](#put_response) | Response プロパティを設定します。
[GetDeferral](#getdeferral) | [IWebView2Deferral](IWebView2Deferral.md)オブジェクトを取得し、イベントを遅延状態にします。

## Members

#### get_Request 

HTTP 要求。

> パブリック HRESULT [get_Request](#get_request)([IWebView2WebResourceRequest](IWebView2WebResourceRequest.md) * * Request)

#### get_Response 

HTTP 応答。

> パブリック HRESULT [get_Response](#get_response)([IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) * * 応答)

#### put_Response 

Response プロパティを設定します。

> パブリック HRESULT [put_Response](#put_response)([IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) * Response)

#### GetDeferral 

[IWebView2Deferral](IWebView2Deferral.md)オブジェクトを取得し、イベントを遅延状態にします。

> パブリック HRESULT [Getdeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) * * 延期)

[IWebView2Deferral](IWebView2Deferral.md)オブジェクトを使って、後でネットワーク要求を完了することができます。

