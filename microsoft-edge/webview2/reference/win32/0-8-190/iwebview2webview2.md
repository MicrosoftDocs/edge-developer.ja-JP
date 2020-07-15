---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 52218ddcbecdaf3bdb736af877493c85d4460c10
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878044"
---
# 0.8.355-インターフェイス IWebView2WebView2 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface IWebView2WebView2
  : public IUnknown
```

プライマリ WebView オブジェクトによって実装されるその他の機能。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[Stop](#stop) | すべてのナビゲーションと保留中のリソースフェッチを停止します。

このインターフェイスの QueryInterface は、 [IWebView2WebView](IWebView2WebView.md)を実装するオブジェクトから行うことができます。 詳細については、 [IWebView2WebView](IWebView2WebView.md)インターフェイスを参照してください。

## Members

#### Stop 

すべてのナビゲーションと保留中のリソースフェッチを停止します。

> パブリック HRESULT [Stop](#stop)()

