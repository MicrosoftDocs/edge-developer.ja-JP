---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2NavigationStartingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2NavigationStartingEventArgs
ms.openlocfilehash: ebfb4aaf3f0c2b5531aaab3783572cf550bebf83
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012343"
---
# インターフェイス ICoreWebView2NavigationStartingEventArgs 

```
interface ICoreWebView2NavigationStartingEventArgs
  : public IUnknown
```

NavigationStarting イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Cancel](#get_cancel) | ホストでは、このフラグを設定して移動を取り消すことができます。
[get_IsRedirected](#get_isredirected) | ナビゲーションがリダイレクトされた場合は True です。
[get_IsUserInitiated](#get_isuserinitiated) | プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。
[get_NavigationId](#get_navigationid) | ナビゲーションの ID です。
[get_RequestHeaders](#get_requestheaders) | ナビゲーションの HTTP 要求ヘッダー。
[get_Uri](#get_uri) | 要求されたナビゲーションの uri。
[put_Cancel](#put_cancel) | "キャンセル" プロパティを設定します。

## Members

#### get_Cancel 

ホストでは、このフラグを設定して移動を取り消すことができます。

> パブリック HRESULT [get_Cancel](#get_cancel)(ブール * キャンセル)

設定されている場合は、ナビゲーションが行われないか、現在のページのコンテンツがそのまま保持されます。 パフォーマンス上の理由から、GET HTTP 要求は、ホストの応答中に発生する可能性があります。 つまり、ナビゲーションの要求の一部を cookie に設定して使うことができます。 "About" に移動するための取り消し: srcdoc への空白またはフレームのナビゲーションはサポートされていません。 このような試みは無視されます。

#### get_IsRedirected 

ナビゲーションがリダイレクトされた場合は True です。

> パブリック HRESULT [get_IsRedirected](#get_isredirected)(ブール * isredirected)

#### get_IsUserInitiated 

プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。

> パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール * isUserInitiated)

#### get_NavigationId 

ナビゲーションの ID です。

> パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 * navigationid)

#### get_RequestHeaders 

ナビゲーションの HTTP 要求ヘッダー。

> パブリック HRESULT [get_RequestHeaders](#get_requestheaders)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) * * RequestHeaders)

ただし、NavigationStarting イベントの HTTP 要求ヘッダーを変更することはできません。

#### get_Uri 

要求されたナビゲーションの uri。

> パブリック HRESULT [get_Uri](#get_uri)(LPWSTR * Uri)

#### put_Cancel 

"キャンセル" プロパティを設定します。

> パブリック HRESULT [put_Cancel](#put_cancel)(ブール値のキャンセル)

