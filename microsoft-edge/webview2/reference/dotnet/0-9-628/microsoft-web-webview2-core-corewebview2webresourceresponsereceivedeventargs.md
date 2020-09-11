---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2WebResourceResponseReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2WebResourceResponseReceivedEventArgs。
ms.openlocfilehash: 2d0660616de0c234b1535b2af127843fea3a3a53
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012233"
---
# WebView2 クラス (CoreWebView2WebResourceResponseReceivedEventArgs クラス) 

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

> パブリック [CoreWebView2WebResourceRequest](microsoft-web-webview2-core-corewebview2webresourcerequest.md) [要求](#request)

このオブジェクトに加えた変更はすべて無視されます。

#### 応答 

Web リソース応答オブジェクト。

> パブリック [CoreWebView2WebResourceResponse](microsoft-web-webview2-core-corewebview2webresourceresponse.md) [応答](#response)

このオブジェクトに加えた変更はすべて無視されます。

#### PopulateResponseContentAsync 

応答のコンテンツストリームを要求する Async メソッド。

> パブリック async Task [PopulateResponseContentAsync](#populateresponsecontentasync)()

