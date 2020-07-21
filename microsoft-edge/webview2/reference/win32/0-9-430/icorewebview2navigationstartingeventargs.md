---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2NavigationStartingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: bd9d10d5f281b2e8f0a5d0687235560c44edc170
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886438"
---
# 0.9.430-インターフェイス ICoreWebView2NavigationStartingEventArgs 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2NavigationStartingEventArgs
  : public IUnknown
```

NavigationStarting イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Uri](#get_uri) | 要求されたナビゲーションの uri。
[get_IsUserInitiated](#get_isuserinitiated) | プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。
[get_IsRedirected](#get_isredirected) | ナビゲーションがリダイレクトされた場合は True です。
[get_RequestHeaders](#get_requestheaders) | ナビゲーションの HTTP 要求ヘッダー。
[get_Cancel](#get_cancel) | ホストでは、このフラグを設定して移動を取り消すことができます。
[put_Cancel](#put_cancel) | "キャンセル" プロパティを設定します。
[get_NavigationId](#get_navigationid) | ナビゲーションの ID です。

## Members

#### get_Uri 

要求されたナビゲーションの uri。

> パブリック HRESULT [get_Uri](#get_uri)(LPWSTR * Uri)

#### get_IsUserInitiated 

プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。

> パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール * isUserInitiated)

#### get_IsRedirected 

ナビゲーションがリダイレクトされた場合は True です。

> パブリック HRESULT [get_IsRedirected](#get_isredirected)(ブール * isredirected)

#### get_RequestHeaders 

ナビゲーションの HTTP 要求ヘッダー。

> パブリック HRESULT [get_RequestHeaders](#get_requestheaders)([ICoreWebView2HttpRequestHeaders](ICoreWebView2HttpRequestHeaders.md) * * RequestHeaders)

ただし、NavigationStarting イベントの HTTP 要求ヘッダーを変更することはできません。

#### get_Cancel 

ホストでは、このフラグを設定して移動を取り消すことができます。

> パブリック HRESULT [get_Cancel](#get_cancel)(ブール * キャンセル)

設定されている場合は、ナビゲーションが行われないか、現在のページのコンテンツがそのまま保持されます。 パフォーマンス上の理由から、GET HTTP 要求は、ホストの応答中に発生する可能性があります。 つまり、ナビゲーションの要求の一部を cookie に設定して使うことができます。

#### put_Cancel 

"キャンセル" プロパティを設定します。

> パブリック HRESULT [put_Cancel](#put_cancel)(ブール値のキャンセル)

#### get_NavigationId 

ナビゲーションの ID です。

> パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 * navigation_id)

