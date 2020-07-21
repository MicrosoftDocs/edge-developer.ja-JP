---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2HttpResponseHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 1daa6c3cdf03ce160968d43715f12ffa7eb41e84
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885584"
---
# 0.9.515-インターフェイス ICoreWebView2HttpResponseHeaders 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2HttpResponseHeaders
  : public IUnknown
```

HTTP 応答ヘッダー。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[AppendHeader](#appendheader) | 名前と値が含まれるヘッダー行を追加します。
[Contains](#contains) | ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。
[GetHeader](#getheader) | 名前に一致するコレクションの最初のヘッダー値を取得します。
[GetHeaders](#getheaders) | 名前に一致するヘッダー値を取得します。
[GetIterator](#getiterator) | 応答ヘッダー全体のコレクションに対する反復子を取得します。

WebResourceRequested イベントの WebResourceResponse を作成するために使われます。

## Members

#### AppendHeader 

名前と値が含まれるヘッダー行を追加します。

> パブリック HRESULT [Appendheader](#appendheader)(LPCWSTR NAME, LPCWSTR value)

#### Contains 

ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。

> パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL * contains)

#### GetHeader 

名前に一致するコレクションの最初のヘッダー値を取得します。

> パブリック HRESULT [GetHeader](#getheader)(LPCWSTR NAME, LPWSTR * value)

#### GetHeaders 

名前に一致するヘッダー値を取得します。

> パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) * * iterator)

#### GetIterator 

応答ヘッダー全体のコレクションに対する反復子を取得します。

> パブリック HRESULT [Getiterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) * * iterator)

