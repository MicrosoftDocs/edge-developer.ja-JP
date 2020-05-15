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
ms.openlocfilehash: aea00f37f28034e1b7a33d4fd11c5ed78f779d00
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654454"
---
# インターフェイス IWebView2HttpRequestHeaders 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface IWebView2HttpRequestHeaders
  : public IUnknown
```

HTTP 要求ヘッダー。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[GetHeader](#getheader) | 名前に一致するヘッダー値を取得します。
[Contains](#contains) | ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。
[SetHeader](#setheader) | 名前に一致するヘッダーを追加または更新します。
[RemoveHeader](#removeheader) | 名前に一致するヘッダーを削除します。
[GetIterator](#getiterator) | 要求ヘッダーのコレクションに対する反復子を取得します。

WebResourceRequested イベントと NavigationStarting イベントの HTTP 要求を検査するために使われます。 ただし、WebResourceRequested イベントから HTTP 要求ヘッダーを変更することはできますが、NavigationStarting イベントからは変更できません。

## Members

#### GetHeader 

名前に一致するヘッダー値を取得します。

> パブリック HRESULT [GetHeader](#getheader)(LPCWSTR NAME, LPWSTR * value)

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

> パブリック HRESULT [Getiterator](#getiterator)([IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) * * iterator)

