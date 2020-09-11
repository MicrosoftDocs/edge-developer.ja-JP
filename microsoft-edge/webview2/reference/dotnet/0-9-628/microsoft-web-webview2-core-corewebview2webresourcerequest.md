---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2WebResourceRequest
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2WebResourceRequest。
ms.openlocfilehash: 5c8d164b24995cc31070232dd9b1a2d88fc16cec
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012239"
---
# WebView2 クラス (CoreWebView2WebResourceRequest クラス) 

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

WebResourceRequested イベントと共に使用される HTTP 要求。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[コンテンツ](#content) | HTTP 要求メッセージ本文をストリームとして送信します。
[ヘッダー](#headers) | 変更可能な HTTP 要求ヘッダー。
[メソッド](#method) | HTTP 要求メソッド。
[URI](#uri) | 要求 URI。

## Members

#### コンテンツ 

HTTP 要求メッセージ本文をストリームとして送信します。

> パブリックストリーム [コンテンツ](#content)

データの投稿はここにあります。 ストリームが設定されている場合は、メッセージ本文を上書きします。この応答の WebResourceRequested イベントの遅延が完了するまで、ストリームにはすべてのコンテンツデータが利用可能になっている必要があります。 UI スレッドへのパフォーマンスへの影響を防ぐために、Stream はバックグラウンド STA から作成したり、バックグラウンドで作成したりする必要があります。 Null はコンテンツデータがないことを意味します。 IStream セマンティクスが適用されます (すべてのデータが使い果たされるまで、S_OK は読み取り呼び出しに戻ります)。

#### ヘッダー 

変更可能な HTTP 要求ヘッダー。

> パブリック [CoreWebView2HttpRequestHeaders](microsoft-web-webview2-core-corewebview2httprequestheaders.md) [ヘッダー](#headers)

#### メソッド 

HTTP 要求メソッド。

> パブリック文字列 [メソッド](#method)

#### URI 

要求 URI。

> パブリック文字列の [Uri](#uri)

