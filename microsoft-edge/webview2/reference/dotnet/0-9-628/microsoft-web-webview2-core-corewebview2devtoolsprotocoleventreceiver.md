---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2DevToolsProtocolEventReceiver
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2DevToolsProtocolEventReceiver。
ms.openlocfilehash: 42ea3beb51dc315ed7ab3b7b0c04c7414adab2db
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012216"
---
# WebView2 クラス (CoreWebView2DevToolsProtocolEventReceiver クラス) 

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

特定の DevTools プロトコルイベント用に受信者が作成され、そのイベントのサブスクライブとサブスクライブ解除を行うことができます。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[DevToolsProtocolEventReceived](#devtoolsprotocoleventreceived) | Devツールプロトコルイベントをサブスクライブします。

GetDevToolsProtocolEventReceiver 経由で WebView オブジェクトから取得されます。

## Members

#### DevToolsProtocolEventReceived 

Devツールプロトコルイベントをサブスクライブします。

> パブリックイベント EventHandler< [CoreWebView2DevToolsProtocolEventReceivedEventArgs](microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md)  >  [DevToolsProtocolEventReceived](#devtoolsprotocoleventreceived)

ハンドラーの Invoke メソッドは、対応する Devて Protocol イベントが発生するたびに呼び出されます。 Invoke は、DevTools プロトコルイベントのパラメーターオブジェクトが JSON 文字列として含まれるイベント引数オブジェクトで呼び出されます。

