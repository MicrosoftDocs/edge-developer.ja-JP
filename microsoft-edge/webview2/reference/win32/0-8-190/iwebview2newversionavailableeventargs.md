---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2NewVersionAvailableEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 4271cc1002de70db2803a5bd6d4be73748bf5bbb
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885871"
---
# 0.8.355-インターフェイス IWebView2NewVersionAvailableEventArgs 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

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

