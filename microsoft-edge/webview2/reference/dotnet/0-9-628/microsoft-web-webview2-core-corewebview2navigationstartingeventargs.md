---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2NavigationStartingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2NavigationStartingEventArgs。
ms.openlocfilehash: 1b80b42bc26316d1fcc8ac74656f24cb0db75bae
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012256"
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

> パブリックブール値の [キャンセル](#cancel)

設定されている場合は、ナビゲーションが行われないか、現在のページのコンテンツがそのまま保持されます。 パフォーマンス上の理由から、GET HTTP 要求は、ホストの応答中に発生する可能性があります。 つまり、ナビゲーションの要求の一部を cookie に設定して使うことができます。

#### IsRedirected 

ナビゲーションがリダイレクトされた場合は True です。

> パブリックブール値 [リダイレクト](#isredirected)

#### IsUserInitiated 

プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。

> public bool [Isuserinitiated](#isuserinitiated)

#### NavigationId 

ナビゲーションの ID です。

> パブリック ulong [Navigationid](#navigationid)

#### RequestHeaders 

ナビゲーションの HTTP 要求ヘッダー。

> パブリック CoreWebView2HttpRequestHeaders [RequestHeaders](#requestheaders)

ただし、NavigationStarting イベントの HTTP 要求ヘッダーを変更することはできません。

#### URI 

要求されたナビゲーションの uri。

> パブリック文字列の [Uri](#uri)

