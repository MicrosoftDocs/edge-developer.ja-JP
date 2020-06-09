---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: d99349ec763796bd6b1ea242abbe5c2219c221c2
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698965"
---
# WebView2 クラス (CoreWebView2DevToolsProtocolEventReceiver クラス) 

名前空間: WebView2 () \
"WebView2" アセンブリを実行します。

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

ハンドラーの Invoke メソッドは、対応する Devて Protocol イベントが発生するたびに呼び出されます。 Invoke は、DevTools プロトコルイベントのパラメーターオブジェクトを JSON 文字列として含むイベント引数オブジェクトで呼び出されます。

