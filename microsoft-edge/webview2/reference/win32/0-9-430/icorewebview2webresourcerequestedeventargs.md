---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2WebResourceRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 00aaddcc732076e4f7aa808b04132641fe7fe969
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886445"
---
# 0.9.430-インターフェイス ICoreWebView2WebResourceRequestedEventArgs 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

WebResourceRequested イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Request](#get_request) | HTTP 要求。
[get_Response](#get_response) | HTTP 応答。
[put_Response](#put_response) | Response プロパティを設定します。
[GetDeferral](#getdeferral) | [ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを取得し、イベントを遅延状態にします。
[get_ResourceContext](#get_resourcecontext) | Web リソース要求のコンテキスト。

## Members

#### get_Request 

HTTP 要求。

> パブリック HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](ICoreWebView2WebResourceRequest.md) * * Request)

#### get_Response 

HTTP 応答。

> パブリック HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) * * 応答)

#### put_Response 

Response プロパティを設定します。

> パブリック HRESULT [put_Response](#put_response)([ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) * Response)

#### GetDeferral 

[ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを取得し、イベントを遅延状態にします。

> パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) * * 延期)

[ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを使って、後でネットワーク要求を完了することができます。

#### get_ResourceContext 

Web リソース要求のコンテキスト。

> パブリック HRESULT [get_ResourceContext](#get_resourcecontext)(CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT * コンテキスト)

