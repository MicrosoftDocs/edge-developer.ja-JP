---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: b496c37949e934fadf0af736059566edcab9f5c3
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885934"
---
# 0.8.355-インターフェイス IWebView2NavigationCompletedEventArgs 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2NavigationCompletedEventArgs
  : public IUnknown
```

NavigationCompleted イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_IsSuccess](#get_issuccess) | ナビゲーションが成功した場合は True です。
[get_WebErrorStatus](#get_weberrorstatus) | ナビゲーションに失敗した場合のエラーコード。

## Members

#### get_IsSuccess 

ナビゲーションが成功した場合は True です。

> パブリック HRESULT [get_IsSuccess](#get_issuccess)(ブール * の場合)

これは、エラーページ内で終了するナビゲーション (ネットワークがない、DNS 参照エラー、HTTP server が4xx で応答する) でも、また、移動ページで呼び出された window. stop () などの追加機能については、false になります。

#### get_WebErrorStatus 

ナビゲーションに失敗した場合のエラーコード。

> パブリック HRESULT [get_WebErrorStatus](#get_weberrorstatus)(WEBVIEW2_WEB_ERROR_STATUS * WEBVIEW2_WEB_ERROR_STATUS)

