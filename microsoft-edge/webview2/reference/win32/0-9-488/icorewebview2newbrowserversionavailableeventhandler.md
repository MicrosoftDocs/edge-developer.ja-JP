---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2NewBrowserVersionAvailableEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: aa59efbb0b47977b41236950c47a01d6d95ee123
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886293"
---
# 0.9.515-インターフェイス ICoreWebView2NewBrowserVersionAvailableEventHandler 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2NewBrowserVersionAvailableEventHandler
  : public IUnknown
```

呼び出し元は、このインターフェイスを実装して、新しい参照サーバーの使用可能なイベントを受け取ります。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[Invoke](#invoke) | 対応するイベントのイベント引数を実装側に提供するために呼び出されます。

## Members

#### Invoke 

対応するイベントのイベント引数を実装側に提供するために呼び出されます。

> パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Environment](icorewebview2environment.md) * Webviewenvironment、IUnknown * args)

