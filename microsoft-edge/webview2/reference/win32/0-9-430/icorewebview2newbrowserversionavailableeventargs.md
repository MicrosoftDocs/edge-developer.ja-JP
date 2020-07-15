---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2NewBrowserVersionAvailableEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: f59b5acac510b66eae0e1ada51e28b6dd9363ca8
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877855"
---
# 0.9.430-インターフェイス ICoreWebView2NewBrowserVersionAvailableEventArgs 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface ICoreWebView2NewBrowserVersionAvailableEventArgs
  : public IUnknown
```

新しい参照サーバーの available イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_NewVersion](#get_newversion) | 現在の[ICoreWebView2Environment](ICoreWebView2Environment.md)のブラウザーのバージョン情報です。

## Members

#### get_NewVersion 

現在の[ICoreWebView2Environment](ICoreWebView2Environment.md)のブラウザーのバージョン情報です。

> パブリック HRESULT [get_NewVersion](#get_newversion)(LPWSTR * NewVersion)

