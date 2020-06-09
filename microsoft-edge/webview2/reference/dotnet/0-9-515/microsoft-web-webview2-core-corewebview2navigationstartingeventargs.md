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
ms.openlocfilehash: 98e242ace5eb0ae5958ddb1eb6cd380d194294be
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697631"
---
# WebView2 クラス (CoreWebView2NavigationStartingEventArgs クラス) 

> [!NOTE]
> この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。 最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。

名前空間: WebView2 () \
"WebView2" アセンブリを実行します。

NavigationStarting イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[Cancel](#cancel) | ホストでは、このフラグを設定して移動を取り消すことができます。
[IsRedirected](#isredirected) | ナビゲーションがリダイレクトされた場合は True です。
[IsUserInitiated](#isuserinitiated) | プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。
[NavigationId](#navigationid) | ナビゲーションの ID です。
[RequestHeaders](#requestheaders) | ナビゲーションの HTTP 要求ヘッダー。
[URI](#uri) | 要求されたナビゲーションの uri。

## Members

#### Cancel 

ホストでは、このフラグを設定して移動を取り消すことができます。

> パブリックブール値の[キャンセル](#cancel)

設定されている場合は、ナビゲーションが行われないか、現在のページのコンテンツがそのまま保持されます。 パフォーマンス上の理由から、GET HTTP 要求は、ホストの応答中に発生する可能性があります。 つまり、ナビゲーションの要求の一部を cookie に設定して使うことができます。

#### IsRedirected 

ナビゲーションがリダイレクトされた場合は True です。

> パブリックブール値[リダイレクト](#isredirected)

#### IsUserInitiated 

プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。

> public bool [Isuserinitiated](#isuserinitiated)

#### NavigationId 

ナビゲーションの ID です。

> パブリック ulong [Navigationid](#navigationid)

#### RequestHeaders 

ナビゲーションの HTTP 要求ヘッダー。

> パブリック HttpRequestHeaders [RequestHeaders](#requestheaders)

ただし、NavigationStarting イベントの HTTP 要求ヘッダーを変更することはできません。

#### URI 

要求されたナビゲーションの uri。

> パブリック文字列の[Uri](#uri)

