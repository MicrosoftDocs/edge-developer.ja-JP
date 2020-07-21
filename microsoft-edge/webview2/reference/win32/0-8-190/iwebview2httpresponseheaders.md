---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2HttpResponseHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 077c85b2458c2cf843c4d2f0548d17ec01ba4751
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885962"
---
# 0.8.355-インターフェイス IWebView2HttpResponseHeaders 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2HttpResponseHeaders
  : public IUnknown
```

HTTP 応答ヘッダー。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[AppendHeader](#appendheader) | 名前と値が含まれるヘッダー行を追加します。
[Contains](#contains) | ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。
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

#### GetHeaders 

名前に一致するヘッダー値を取得します。

> パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name,[IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) * * iterator)

#### GetIterator 

応答ヘッダー全体のコレクションに対する反復子を取得します。

> パブリック HRESULT [Getiterator](#getiterator)([IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) * * iterator)

