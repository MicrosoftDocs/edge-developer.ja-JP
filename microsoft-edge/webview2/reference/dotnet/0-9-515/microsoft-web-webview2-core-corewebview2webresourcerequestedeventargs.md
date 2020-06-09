---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 072ce10e7ac1f34238278366c3e8799a3268cb0b
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697533"
---
# WebView2 クラス (CoreWebView2WebResourceRequestedEventArgs クラス) 

> [!NOTE]
> この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。 最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。

名前空間: WebView2 () \
"WebView2" アセンブリを実行します。

WebResourceRequested イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[要求](#request) | HTTP 要求。
[ResourceContext](#resourcecontext) | Web リソース要求のコンテキスト。
[応答](#response) | HTTP 応答。
[GetDeferral](#getdeferral) | CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。

## Members

#### 要求 

HTTP 要求。

> パブリック HttpRequestMessage[要求](#request)

#### ResourceContext 

Web リソース要求のコンテキスト。

> パブリック[CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [resourcecontext](#resourcecontext)

#### 応答 

HTTP 応答。

> パブリック HttpResponseMessage[応答](#response)

#### GetDeferral 

CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。

> パブリック[CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [getdeferral](#getdeferral)()

CoreWebView2Deferral オブジェクトを使って、後でネットワーク要求を完了することができます。

