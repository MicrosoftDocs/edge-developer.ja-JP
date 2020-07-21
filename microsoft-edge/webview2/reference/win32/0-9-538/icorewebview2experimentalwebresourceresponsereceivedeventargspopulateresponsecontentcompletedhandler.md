---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler
ms.openlocfilehash: c021cfa866e55bfdf30185eeaf6015db1b523271
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886542"
---
# インターフェイス ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler
  : public IUnknown
```

PopulateResponseContent async メソッドの完了ハンドラー。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[Invoke](#invoke) | 対応する非同期メソッド呼び出しの完了状態を実装側に提供するために呼び出されます。

WebResourceResponseReceieved イベントの応答のコンテンツストリームを利用できる場合に呼び出されます。

## Members

#### Invoke 

対応する非同期メソッド呼び出しの完了状態を実装側に提供するために呼び出されます。

> パブリック HRESULT[呼び出し](#invoke)(hresult 結果)

