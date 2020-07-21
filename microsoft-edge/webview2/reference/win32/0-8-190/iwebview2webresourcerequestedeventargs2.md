---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2WebResourceRequestedEventArgs2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 7f710b4da71a4a4e61869f06e5d2a4a95a2d0891
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885710"
---
# 0.8.355-インターフェイス IWebView2WebResourceRequestedEventArgs2 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2WebResourceRequestedEventArgs2
  : public IWebView2WebResourceRequestedEventArgs
```

WebResourceRequested イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_ResourceContext](#get_resourcecontext) | Web リソース要求のコンテキスト。

## Members

#### get_ResourceContext 

Web リソース要求のコンテキスト。

> パブリック HRESULT [get_ResourceContext](#get_resourcecontext)(WEBVIEW2_WEB_RESOURCE_CONTEXT * コンテキスト)

