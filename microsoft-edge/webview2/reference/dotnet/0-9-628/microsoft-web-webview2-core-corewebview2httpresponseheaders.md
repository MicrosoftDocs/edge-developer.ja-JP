---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2HttpResponseHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2HttpResponseHeaders。
ms.openlocfilehash: 51218283460975421859c65da8a43553767ad216
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012282"
---
# WebView2 クラス (CoreWebView2HttpResponseHeaders クラス) 

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

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

> パブリック void [Appendheader](#appendheader)(文字列名、文字列値)

#### Contains 

ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。

> public bool [Contains](#contains)(文字列 name)

#### GetHeader 

名前に一致するコレクションの最初のヘッダー値を取得します。

> パブリック文字列 [GetHeader](#getheader)(文字列名)

#### GetHeaders 

名前に一致するヘッダー値を取得します。

> パブリック CoreWebView2HttpHeadersCollectionIterator [GetHeaders](#getheaders)(文字列名)

#### GetIterator 

応答ヘッダー全体のコレクションに対する反復子を取得します。

> パブリック CoreWebView2HttpHeadersCollectionIterator [Getiterator](#getiterator)()

