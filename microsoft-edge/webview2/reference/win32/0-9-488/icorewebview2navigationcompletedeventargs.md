---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: c13d0625669d6303c115c3d415d12278cfbe8320
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880501"
---
# 0.9.515-インターフェイス ICoreWebView2NavigationCompletedEventArgs 

> [!NOTE]
> この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。 最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface ICoreWebView2NavigationCompletedEventArgs
  : public IUnknown
```

NavigationCompleted イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_IsSuccess](#get_issuccess) | ナビゲーションが成功した場合は True です。
[get_NavigationId](#get_navigationid) | ナビゲーションの ID です。
[get_WebErrorStatus](#get_weberrorstatus) | ナビゲーションに失敗した場合のエラーコード。

## Members

#### get_IsSuccess 

ナビゲーションが成功した場合は True です。

> パブリック HRESULT [get_IsSuccess](#get_issuccess)(ブール * の場合)

これは、エラーページ内で終了するナビゲーション (ネットワークがない、DNS 参照エラー、HTTP server が4xx で応答する) でも、また、移動ページで呼び出された window. stop () などの追加機能については、false になります。

#### get_NavigationId 

ナビゲーションの ID です。

> パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 * navigation_id)

#### get_WebErrorStatus 

ナビゲーションに失敗した場合のエラーコード。

> パブリック HRESULT [get_WebErrorStatus](#get_weberrorstatus)(COREWEBVIEW2_WEB_ERROR_STATUS * COREWEBVIEW2_WEB_ERROR_STATUS)

