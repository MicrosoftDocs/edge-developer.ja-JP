---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2WebResourceResponse
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2WebResourceResponse
ms.openlocfilehash: f94aa86f589f49930de9186cdca4a6ae943d286f
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011385"
---
# 0.9.579-インターフェイス ICoreWebView2WebResourceResponse 

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

