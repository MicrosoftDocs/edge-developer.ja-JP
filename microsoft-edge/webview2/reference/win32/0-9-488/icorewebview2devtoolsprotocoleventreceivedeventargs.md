---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 1397fb15963cadd508082e39a735a8f0f64a8e91
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698072"
---
# インターフェイス ICoreWebView2DevToolsProtocolEventReceivedEventArgs 

> [!NOTE]
> この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。 最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs
  : public IUnknown
```

DevToolsProtocolEventReceived イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_ParameterObjectAsJson](#get_parameterobjectasjson) | JSON 文字列として表される、対応する Devthe Protocol イベントのパラメーターオブジェクト。

## Members

#### get_ParameterObjectAsJson 

JSON 文字列として表される、対応する Devthe Protocol イベントのパラメーターオブジェクト。

> パブリック HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)(LPWSTR * ParameterObjectAsJson)

