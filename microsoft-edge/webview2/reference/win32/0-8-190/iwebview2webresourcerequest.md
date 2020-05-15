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
ms.openlocfilehash: 69bf9eeae4b6736ac6df6ddaa9594b7438cbf58c
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654232"
---
# インターフェイス IWebView2WebResourceRequest 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface IWebView2WebResourceRequest
  : public IUnknown
```

WebResourceRequested イベントと共に使用される HTTP 要求。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Uri](#get_uri) | 要求 URI。
[put_Uri](#put_uri) | Uri プロパティを設定します。
[get_Method](#get_method) | HTTP 要求メソッド。
[put_Method](#put_method) | Method プロパティを設定します。
[get_Content](#get_content) | HTTP 要求メッセージ本文をストリームとして送信します。
[put_Content](#put_content) | Content プロパティを設定します。
[get_Headers](#get_headers) | 変更可能な HTTP 要求ヘッダー。

## Members

#### get_Uri 

要求 URI。

> パブリック HRESULT [get_Uri](#get_uri)(LPWSTR * Uri)

#### put_Uri 

Uri プロパティを設定します。

> パブリック HRESULT [put_Uri](#put_uri)(LPCWSTR Uri)

#### get_Method 

HTTP 要求メソッド。

> パブリック HRESULT [get_Method](#get_method)(LPWSTR * メソッド)

#### put_Method 

Method プロパティを設定します。

> パブリック HRESULT [put_Method](#put_method)(LPCWSTR メソッド)

#### get_Content 

HTTP 要求メッセージ本文をストリームとして送信します。

> パブリック HRESULT [get_Content](#get_content)(IStream * * コンテンツ)

データの投稿はここにあります。 ストリームが設定されている場合は、メッセージ本文を上書きします。この応答の WebResourceRequested イベントの遅延が完了するまで、ストリームにはすべてのコンテンツデータが利用可能になっている必要があります。 UI スレッドへのパフォーマンスへの影響を防ぐために、Stream はバックグラウンド STA から作成したり、バックグラウンドで作成したりする必要があります。 Null はコンテンツデータがないことを意味します。 IStream セマンティクスが適用されます (すべてのデータが使い果たされるまで、S_OK は読み取り呼び出しに戻ります)

#### put_Content 

Content プロパティを設定します。

> パブリック HRESULT [put_Content](#put_content)(IStream * コンテンツ)

#### get_Headers 

変更可能な HTTP 要求ヘッダー。

> パブリック HRESULT [get_Headers](#get_headers)([IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md) * * ヘッダー)

