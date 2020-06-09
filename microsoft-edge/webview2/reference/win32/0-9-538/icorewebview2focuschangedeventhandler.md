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
ms.openlocfilehash: 6fc29b620df5bcd265a7576e4b7ca1c7ebd73e6f
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699055"
---
# インターフェイス ICoreWebView2FocusChangedEventHandler 

```
interface ICoreWebView2FocusChangedEventHandler
  : public IUnknown
```

呼び出し元は、このメソッドを実装して GotFocus イベントと LostFocus イベントを受け取ります。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[Invoke](#invoke) | 対応するイベントのイベント引数を実装側に提供するために呼び出されます。

このイベントのイベント引数はありません。

## Members

#### Invoke 

対応するイベントのイベント引数を実装側に提供するために呼び出されます。

> パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) * sender、IUnknown * args)

イベント引数はなく、args パラメーターは null になります。

