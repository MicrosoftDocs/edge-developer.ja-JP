---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2WebResourceRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2WebResourceRequestedEventArgs。
ms.openlocfilehash: 53cc31bc714417ab902fa8fdef9fd83f80871f10
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879668"
---
# WebView2 クラス (CoreWebView2WebResourceRequestedEventArgs クラス) 

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

WebResourceRequested イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[要求](#request) | HTTP 要求。
[ResourceContext](#resourcecontext) | Web リソース要求のコンテキスト。
[応答](#response) | HTTP 応答。
[GetDeferral](#getdeferral) | CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。

## Members

#### 要求 

HTTP 要求。

> パブリック HttpRequestMessage[要求](#request)

#### ResourceContext 

Web リソース要求のコンテキスト。

> パブリック[CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [resourcecontext](#resourcecontext)

#### 応答 

HTTP 応答。

> パブリック HttpResponseMessage[応答](#response)

#### GetDeferral 

CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。

> パブリック[CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [getdeferral](#getdeferral)()

CoreWebView2Deferral オブジェクトを使って、後でネットワーク要求を完了することができます。

