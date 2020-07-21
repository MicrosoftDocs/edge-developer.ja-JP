---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 64dac6c56576b618cbdc84da2c8fcbcd0e41028f
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884737"
---
# 0.8.355-インターフェイス IWebView2WebView2 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

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

