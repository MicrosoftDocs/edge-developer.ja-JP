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
ms.openlocfilehash: 2788a18898da1f878520f4c4eb072c1a8b43375b
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654181"
---
# インターフェイス IWebView2CreateWebViewCompletedHandler 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface IWebView2CreateWebViewCompletedHandler
  : public IUnknown
```

呼び出し元は、CreateWebView 経由で作成された WebView を受け取るために、このインターフェイスを実装します。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[Invoke](#invoke) | 呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。

## Members

#### Invoke 

呼び出し側に、対応する非同期メソッド呼び出しの完了状態と結果を提供するために呼び出されます。

> パブリック HRESULT[呼び出し](#invoke)(hresult Result、[IWebView2WebView](IWebView2WebView.md) * webView)

