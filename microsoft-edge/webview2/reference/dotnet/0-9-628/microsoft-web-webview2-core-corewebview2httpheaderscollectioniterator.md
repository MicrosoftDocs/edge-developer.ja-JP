---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2HttpHeadersCollectionIterator
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2HttpHeadersCollectionIterator。
ms.openlocfilehash: e7aad408372acbbd19ecab9d04312f21e2396e88
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012285"
---
# WebView2 クラス (CoreWebView2HttpHeadersCollectionIterator クラス) 

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

HTTP ヘッダーのコレクションの Iterator。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[HasCurrentHeader](#hascurrentheader) | 反復子でヘッダーが不足していない場合は True です。
[MoveNext](#movenext) | 反復子をコレクション内の次の HTTP ヘッダーに移動します。

CoreWebView2HttpRequestHeaders と CoreWebView2HttpResponseHeaders を参照してください。

## Members

#### HasCurrentHeader 

反復子でヘッダーが不足していない場合は True です。

> public bool [HasCurrentHeader](#hascurrentheader)

反復子が反復処理を行っているコレクションが空である場合、または反復子がコレクションの末尾を超えている場合、この値は false になります。

#### MoveNext 

反復子をコレクション内の次の HTTP ヘッダーに移動します。

> パブリックブール [MoveNext](#movenext)()

他の HTTP ヘッダーがない場合は、hasNext パラメーターが FALSE に設定されます。 この処理を実行すると、GetCurrentHeader メソッドは呼び出されたときに失敗します。

