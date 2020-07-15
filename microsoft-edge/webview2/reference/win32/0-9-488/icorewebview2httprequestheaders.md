---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2HttpRequestHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 2587a3e07869076be659e29d484a647b74c2bd7f
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880550"
---
# 0.9.515-インターフェイス ICoreWebView2HttpRequestHeaders 

> [!NOTE]
> この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。 最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface ICoreWebView2HttpRequestHeaders
  : public IUnknown
```

HTTP 要求ヘッダー。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[Contains](#contains) | ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。
[GetHeader](#getheader) | 名前に一致するヘッダー値を取得します。
[GetHeaders](#getheaders) | 名前に一致するヘッダー値をイテレータを使って取得します。
[GetIterator](#getiterator) | 要求ヘッダーのコレクションに対する反復子を取得します。
[RemoveHeader](#removeheader) | 名前に一致するヘッダーを削除します。
[SetHeader](#setheader) | 名前に一致するヘッダーを追加または更新します。

WebResourceRequested イベントと NavigationStarting イベントの HTTP 要求を検査するために使われます。 ただし、WebResourceRequested イベントから HTTP 要求ヘッダーを変更することはできますが、NavigationStarting イベントからは変更できません。

## Members

#### Contains 

ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。

> パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL * contains)

#### GetHeader 

名前に一致するヘッダー値を取得します。

> パブリック HRESULT [GetHeader](#getheader)(LPCWSTR NAME, LPWSTR * value)

#### GetHeaders 

名前に一致するヘッダー値をイテレータを使って取得します。

> パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) * * iterator)

#### GetIterator 

要求ヘッダーのコレクションに対する反復子を取得します。

> パブリック HRESULT [Getiterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) * * iterator)

#### RemoveHeader 

名前に一致するヘッダーを削除します。

> パブリック HRESULT [Removeheader](#removeheader)(LPCWSTR name)

#### SetHeader 

名前に一致するヘッダーを追加または更新します。

> パブリック HRESULT [SetHeader](#setheader)(LPCWSTR NAME, LPCWSTR value)

