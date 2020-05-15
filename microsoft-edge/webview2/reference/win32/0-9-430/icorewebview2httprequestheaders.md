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
ms.openlocfilehash: e12809d1db7e8c7764ad75e9a10f44ac3f445fa4
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654319"
---
# インターフェイス ICoreWebView2HttpRequestHeaders 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface ICoreWebView2HttpRequestHeaders
  : public IUnknown
```

HTTP 要求ヘッダー。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[GetHeader](#getheader) | 名前に一致するヘッダー値を取得します。
[GetHeaders](#getheaders) | 名前に一致するヘッダー値をイテレータを使って取得します。
[Contains](#contains) | ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。
[SetHeader](#setheader) | 名前に一致するヘッダーを追加または更新します。
[RemoveHeader](#removeheader) | 名前に一致するヘッダーを削除します。
[GetIterator](#getiterator) | 要求ヘッダーのコレクションに対する反復子を取得します。

WebResourceRequested イベントと NavigationStarting イベントの HTTP 要求を検査するために使われます。 ただし、WebResourceRequested イベントから HTTP 要求ヘッダーを変更することはできますが、NavigationStarting イベントからは変更できません。

## Members

#### GetHeader 

名前に一致するヘッダー値を取得します。

> パブリック HRESULT [GetHeader](#getheader)(LPCWSTR NAME, LPWSTR * value)

#### GetHeaders 

名前に一致するヘッダー値をイテレータを使って取得します。

> パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name,[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) * * iterator)

#### Contains 

ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。

> パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL * contains)

#### SetHeader 

名前に一致するヘッダーを追加または更新します。

> パブリック HRESULT [SetHeader](#setheader)(LPCWSTR NAME, LPCWSTR value)

#### RemoveHeader 

名前に一致するヘッダーを削除します。

> パブリック HRESULT [Removeheader](#removeheader)(LPCWSTR name)

#### GetIterator 

要求ヘッダーのコレクションに対する反復子を取得します。

> パブリック HRESULT [Getiterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) * * iterator)

