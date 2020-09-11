---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2HttpRequestHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2HttpRequestHeaders。
ms.openlocfilehash: 1441d5a45caf4e8f561de2487438b66e067760f6
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012218"
---
# WebView2 クラス (CoreWebView2HttpRequestHeaders クラス) 

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

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

> public bool [Contains](#contains)(文字列 name)

#### GetHeader 

名前に一致するヘッダー値を取得します。

> パブリック文字列 [GetHeader](#getheader)(文字列名)

#### GetHeaders 

名前に一致するヘッダー値をイテレータを使って取得します。

> パブリック CoreWebView2HttpHeadersCollectionIterator [GetHeaders](#getheaders)(文字列名)

#### GetIterator 

要求ヘッダーのコレクションに対する反復子を取得します。

> パブリック CoreWebView2HttpHeadersCollectionIterator [Getiterator](#getiterator)()

#### RemoveHeader 

名前に一致するヘッダーを削除します。

> パブリック void [Removeheader](#removeheader)(文字列名)

#### SetHeader 

名前に一致するヘッダーを追加または更新します。

> パブリック void [SetHeader](#setheader)(文字列名、文字列値)

