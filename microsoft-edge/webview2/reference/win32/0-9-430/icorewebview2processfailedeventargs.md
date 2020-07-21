---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2ProcessFailedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: a19f8c445d7ff1f6bee24cdd8871c28d41eedebe
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886412"
---
# 0.9.430-インターフェイス ICoreWebView2ProcessFailedEventArgs 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ProcessFailedEventArgs
  : public IUnknown
```

ProcessFailed イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_ProcessFailedKind](#get_processfailedkind) | 発生したプロセスエラーの種類。

## Members

#### get_ProcessFailedKind 

発生したプロセスエラーの種類。

> パブリック HRESULT [get_ProcessFailedKind](#get_processfailedkind)(CORE_WEBVIEW2_PROCESS_FAILED_KIND * Processの KIND)

