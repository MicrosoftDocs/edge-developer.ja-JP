---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2WebResourceResponseReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2WebResourceResponseReceivedEventArgs。
ms.openlocfilehash: 44fc4f47aa10a7e409ac584cb75b750048056e47
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886528"
---
# WebView2 クラス (CoreWebView2WebResourceResponseReceivedEventArgs クラス) 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

WebResourceResponseReceived イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[要求](#request) | Web リソース要求オブジェクト。
[応答](#response) | Web リソース応答オブジェクト。
[PopulateResponseContentAsync](#populateresponsecontentasync) | 応答のコンテンツストリームを要求する Async メソッド。

## Members

#### 要求 

Web リソース要求オブジェクト。

> パブリック HttpRequestMessage[要求](#request)

このオブジェクトに加えた変更はすべて無視されます。

#### 応答 

Web リソース応答オブジェクト。

> パブリック HttpResponseMessage[応答](#response)

このオブジェクトに加えた変更はすべて無視されます。

#### PopulateResponseContentAsync 

応答のコンテンツストリームを要求する Async メソッド。

> パブリック async Task [PopulateResponseContentAsync](#populateresponsecontentasync)()

