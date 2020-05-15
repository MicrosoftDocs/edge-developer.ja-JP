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
ms.openlocfilehash: 9c8cd627275a98382f079bc4f64dd7f565d46630
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654547"
---
# インターフェイス ICoreWebView2ExperimentalCursorChangedEventHandler 

> [!NOTE]
> これは、プレリリース SDK バージョン0.9.488 に同梱されている実験的な API です。

```
interface ICoreWebView2ExperimentalCursorChangedEventHandler
  : public IUnknown
```

呼び出し元は、このインターフェイスを実装して、カーソル変更イベントを受け取ります。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[Invoke](#invoke) | 対応するイベントのイベント引数を実装側に提供するために呼び出されます。

新しいカーソルを取得するには、Cursor プロパティを使います。

## Members

#### Invoke 

対応するイベントのイベント引数を実装側に提供するために呼び出されます。

> パブリック HRESULT[呼び出し](#invoke)([ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) * sender、IUnknown * args)

イベント引数はなく、args パラメーターは null になります。

