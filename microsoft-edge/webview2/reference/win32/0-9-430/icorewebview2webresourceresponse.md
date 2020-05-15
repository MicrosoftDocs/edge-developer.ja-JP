---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 6d28a5e0b08406cdf83b7e0a60428463e9647d45
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654359"
---
# インターフェイス ICoreWebView2WebResourceResponse 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface ICoreWebView2WebResourceResponse
  : public IUnknown
```

WebResourceRequested イベントと共に使用される HTTP 応答。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Content](#get_content) | ストリームとしての HTTP 応答のコンテンツ。
[put_Content](#put_content) | Content プロパティを設定します。
[get_Headers](#get_headers) | 上書きされた HTTP 応答ヘッダー。
[get_StatusCode](#get_statuscode) | HTTP 応答状態コード。
[put_StatusCode](#put_statuscode) | StatusCode プロパティを設定します。
[get_ReasonPhrase](#get_reasonphrase) | HTTP 応答の理由の語句。
[put_ReasonPhrase](#put_reasonphrase) | "理由" プロパティを設定します。

## Members

#### get_Content 

ストリームとしての HTTP 応答のコンテンツ。

> パブリック HRESULT [get_Content](#get_content)(IStream * * コンテンツ)

この応答の WebResourceRequested イベントの遅延が完了するまで、ストリームにはすべてのコンテンツデータが利用可能である必要があります。 UI スレッドに対するパフォーマンスへの影響を防ぐには、ストリームをアジャイルにするか、バックグラウンドスレッドから作成する必要があります。 Null はコンテンツデータがないことを意味します。 IStream セマンティクスが適用されます (すべてのデータが使い果たされるまで、S_OK は読み取り呼び出しに戻ります)

#### put_Content 

Content プロパティを設定します。

> パブリック HRESULT [put_Content](#put_content)(IStream * コンテンツ)

#### get_Headers 

上書きされた HTTP 応答ヘッダー。

> パブリック HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpResponseHeaders](ICoreWebView2HttpResponseHeaders.md) * * ヘッダー)

#### get_StatusCode 

HTTP 応答状態コード。

> パブリック HRESULT [get_StatusCode](#get_statuscode)(Int * StatusCode)

#### put_StatusCode 

StatusCode プロパティを設定します。

> パブリック HRESULT [put_StatusCode](#put_statuscode)(int StatusCode)

#### get_ReasonPhrase 

HTTP 応答の理由の語句。

> パブリック HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR * 理由語句)

#### put_ReasonPhrase 

"理由" プロパティを設定します。

> パブリック HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR 理由語句)

