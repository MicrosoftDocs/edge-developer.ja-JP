---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: b917f309194316b26ee94aa94dc8289ef4430007
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697540"
---
# WebView2 クラス (CoreWebView2WebMessageReceivedEventArgs クラス) 

> [!NOTE]
> この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。 最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。

名前空間: WebView2 () \
"WebView2" アセンブリを実行します。

WebMessageReceived イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[Source](#source) | この web メッセージを送信したドキュメントの URI です。
[WebMessageAsJson](#webmessageasjson) | このメッセージは、webview コンテンツから、JSON 文字列に変換されたホストに送信されます。
[TryGetWebMessageAsString](#trygetwebmessageasstring) | Webview コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。

## Members

#### Source 

この web メッセージを送信したドキュメントの URI です。

> パブリック文字列[ソース](#source)

#### WebMessageAsJson 

このメッセージは、webview コンテンツから、JSON 文字列に変換されたホストに送信されます。

> パブリック文字列[Webmessageasjson](#webmessageasjson)

JavaScript オブジェクトを使って通信する場合に使用します。

たとえば、次の postMessage 呼び出しは、次の WebMessageAsJson 値になります。

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### TryGetWebMessageAsString 

Webview コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。

> パブリック文字列[Trygetwebmessageasstring](#trygetwebmessageasstring)()

投稿されたメッセージが他の種類の JavaScript 型の場合は、このメソッドは E_INVALIDARG に失敗します。 これは、単純な文字列を使って通信する場合に使用します。

たとえば、次の postMessage の呼び出しは、次の WebMessageAsString 値になります。

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

