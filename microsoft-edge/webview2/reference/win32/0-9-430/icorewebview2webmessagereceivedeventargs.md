---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/24/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: f3002c6e7941cea1f632e1df4ee42a8f38a468b6
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654549"
---
# インターフェイス ICoreWebView2WebMessageReceivedEventArgs 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface ICoreWebView2WebMessageReceivedEventArgs
  : public IUnknown
```

WebMessageReceived イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Source](#get_source) | この web メッセージを送信したドキュメントの URI です。
[get_WebMessageAsJson](#get_webmessageasjson) | このメッセージは、webview コンテンツから、JSON 文字列に変換されたホストに送信されます。
[TryGetWebMessageAsString](#trygetwebmessageasstring) | Webview コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。

## Members

#### get_Source 

この web メッセージを送信したドキュメントの URI です。

> パブリック HRESULT [get_Source](#get_source)(LPWSTR * Source)

#### get_WebMessageAsJson 

このメッセージは、webview コンテンツから、JSON 文字列に変換されたホストに送信されます。

> パブリック HRESULT [get_WebMessageAsJson](#get_webmessageasjson)(LPWSTR * webMessageAsJson)

JavaScript オブジェクトを使って通信する場合に使用します。

たとえば、次の postMessage 呼び出しは、次の WebMessageAsJson 値になります。

```cpp
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### TryGetWebMessageAsString 

Webview コンテンツからホストに投稿されたメッセージが文字列型の場合、このメソッドはその文字列の値を返します。

> パブリック HRESULT [Trygetwebmessageasstring](#trygetwebmessageasstring)(LPWSTR * webmessageasstring)

投稿されたメッセージが他の種類の JavaScript 型の場合は、このメソッドは E_INVALIDARG に失敗します。 これは、単純な文字列を使って通信する場合に使用します。

たとえば、次の postMessage の呼び出しは、次の WebMessageAsString 値になります。

```cpp
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

