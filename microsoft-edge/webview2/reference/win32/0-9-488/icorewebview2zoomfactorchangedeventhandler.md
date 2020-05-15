---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: e2469dd9a587735efcf88a48e0ce950cb4f85239
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654456"
---
# インターフェイス ICoreWebView2ZoomFactorChangedEventHandler 

```
interface ICoreWebView2ZoomFactorChangedEventHandler
  : public IUnknown
```

呼び出し元は、このインターフェイスを実装して ZoomFactorChanged イベントを受け取ります。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[Invoke](#invoke) | 対応するイベントのイベント引数を実装側に提供するために呼び出されます。

変更されたズームファクターを取得するには、ICoreWebView2Controller プロパティを使います。

## Members

#### Invoke 

対応するイベントのイベント引数を実装側に提供するために呼び出されます。

> パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) * sender、IUnknown * args)

イベント引数はなく、args パラメーターは null になります。

