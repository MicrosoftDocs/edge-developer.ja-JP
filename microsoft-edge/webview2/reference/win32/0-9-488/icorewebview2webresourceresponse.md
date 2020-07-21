---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2WebResourceResponse
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: e17e12759bef051a33e99999f0e938da5bd16939
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883785"
---
# 0.9.515-インターフェイス ICoreWebView2WebResourceResponse 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebResourceResponse
  : public IUnknown
```

WebResourceRequested イベントと共に使用される HTTP 応答。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Content](#get_content) | ストリームとしての HTTP 応答のコンテンツ。
[get_Headers](#get_headers) | 上書きされた HTTP 応答ヘッダー。
[get_ReasonPhrase](#get_reasonphrase) | HTTP 応答の理由の語句。
[get_StatusCode](#get_statuscode) | HTTP 応答状態コード。
[put_Content](#put_content) | Content プロパティを設定します。
[put_ReasonPhrase](#put_reasonphrase) | "理由" プロパティを設定します。
[put_StatusCode](#put_statuscode) | StatusCode プロパティを設定します。

## Members

#### get_Content 

ストリームとしての HTTP 応答のコンテンツ。

> パブリック HRESULT [get_Content](#get_content)(IStream * * コンテンツ)

この応答の WebResourceRequested イベントの遅延が完了するまで、ストリームにはすべてのコンテンツデータが利用可能である必要があります。 UI スレッドに対するパフォーマンスへの影響を防ぐには、ストリームをアジャイルにするか、バックグラウンドスレッドから作成する必要があります。 Null はコンテンツデータがないことを意味します。 IStream セマンティクスが適用されます (すべてのデータが使い果たされるまで、S_OK は読み取り呼び出しに戻ります)

#### get_Headers 

上書きされた HTTP 応答ヘッダー。

> パブリック HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) * * ヘッダー)

#### get_ReasonPhrase 

HTTP 応答の理由の語句。

> パブリック HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR * 理由語句)

#### get_StatusCode 

HTTP 応答状態コード。

> パブリック HRESULT [get_StatusCode](#get_statuscode)(Int * StatusCode)

#### put_Content 

Content プロパティを設定します。

> パブリック HRESULT [put_Content](#put_content)(IStream * コンテンツ)

#### put_ReasonPhrase 

"理由" プロパティを設定します。

> パブリック HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR 理由語句)

#### put_StatusCode 

StatusCode プロパティを設定します。

> パブリック HRESULT [put_StatusCode](#put_statuscode)(int StatusCode)

