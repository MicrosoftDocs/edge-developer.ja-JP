---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2WebResourceResponse
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2WebResourceResponse。
ms.openlocfilehash: 5359634d83717ce844d2c1604a2645ceffc477cc
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012235"
---
# WebView2 クラス (CoreWebView2WebResourceResponse クラス) 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

WebResourceRequested イベントと共に使用される HTTP 応答。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[コンテンツ](#content) | ストリームとしての HTTP 応答のコンテンツ。
[ヘッダー](#headers) | 上書きされた HTTP 応答ヘッダー。
[理由語句](#reasonphrase) | HTTP 応答の理由の語句。
[StatusCode](#statuscode) | HTTP 応答状態コード。

## Members

#### コンテンツ 

ストリームとしての HTTP 応答のコンテンツ。

> パブリックストリーム [コンテンツ](#content)

この応答の WebResourceRequested イベントの遅延が完了するまで、ストリームにはすべてのコンテンツデータが利用可能である必要があります。 UI スレッドに対するパフォーマンスへの影響を防ぐには、ストリームをアジャイルにするか、バックグラウンドスレッドから作成する必要があります。 Null はコンテンツデータがないことを意味します。 IStream セマンティクスが適用されます (すべてのデータが使い果たされるまで、S_OK は読み取り呼び出しに戻ります)。

#### ヘッダー 

上書きされた HTTP 応答ヘッダー。

> パブリック [CoreWebView2HttpResponseHeaders](microsoft-web-webview2-core-corewebview2httpresponseheaders.md) [ヘッダー](#headers)

#### 理由語句 

HTTP 応答の理由の語句。

> パブリック文字列の [理由語句](#reasonphrase)

#### StatusCode 

HTTP 応答状態コード。

> パブリック int の [StatusCode](#statuscode)

