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
ms.openlocfilehash: 0314c796865d3d745b831d050498f59868e38e8f
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654502"
---
# インターフェイス IWebView2NewVersionAvailableEventArgs 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface IWebView2NewVersionAvailableEventArgs
  : public IUnknown
```

NewVersionAvailable イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_NewVersion](#get_newversion) | 現在の[IWebView2Environment](IWebView2Environment.md)のブラウザーのバージョン情報です。

## Members

#### get_NewVersion 

現在の[IWebView2Environment](IWebView2Environment.md)のブラウザーのバージョン情報です。

> パブリック HRESULT [get_NewVersion](#get_newversion)(LPWSTR * NewVersion)

