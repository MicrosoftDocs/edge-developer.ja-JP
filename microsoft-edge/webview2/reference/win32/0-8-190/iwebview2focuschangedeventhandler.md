---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2FocusChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 8b7a588122b93cf56f7ce4473db87a0df16522b7
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885997"
---
# 0.8.355-インターフェイス IWebView2FocusChangedEventHandler 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2FocusChangedEventHandler
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

> パブリック HRESULT[呼び出し](#invoke)([IWebView2WebView](IWebView2WebView.md) * webview、IUnknown * args)

イベント引数はなく、args パラメーターは null になります。

