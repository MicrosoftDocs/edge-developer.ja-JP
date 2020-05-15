---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 62daeaab702b431f787bc800ab79664fc183c4ce
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654160"
---
# インターフェイス IWebView2WebView2 

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

