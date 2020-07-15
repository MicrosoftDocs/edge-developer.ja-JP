---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2NavigationStartingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2NavigationStartingEventArgs。
ms.openlocfilehash: cd692de6aaa3dc694fb2fe149411e5fd64de1ee2
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878870"
---
# WebView2 クラス (CoreWebView2NavigationStartingEventArgs クラス) 

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

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

