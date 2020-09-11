---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2HttpRequestHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2HttpRequestHeaders
ms.openlocfilehash: 8455db6adccf2d3d10e9934fee940d00bba7377c
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012273"
---
# インターフェイス ICoreWebView2HttpRequestHeaders 

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

