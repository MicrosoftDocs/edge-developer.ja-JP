---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2NavigationCompletedEventArgs。
ms.openlocfilehash: dfa6aedb10e60a2af15c7b098c479f8537d6c747
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012212"
---
# WebView2 クラス (CoreWebView2NavigationCompletedEventArgs クラス) 

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

NavigationCompleted イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[IsSuccess](#issuccess) | ナビゲーションが成功した場合は True です。
[NavigationId](#navigationid) | ナビゲーションの ID です。
[WebErrorStatus](#weberrorstatus) | ナビゲーションに失敗した場合のエラーコード。

## Members

#### IsSuccess 

ナビゲーションが成功した場合は True です。

> 公開ブール [値](#issuccess)

これは、エラーページ内で終了するナビゲーション (ネットワークがない、DNS 参照エラー、HTTP server が4xx で応答する) でも、その他のシナリオ (たとえば、移動中のページで呼び出された window. stop () など) では、false になります。

#### NavigationId 

ナビゲーションの ID です。

> パブリック ulong [Navigationid](#navigationid)

#### WebErrorStatus 

ナビゲーションに失敗した場合のエラーコード。

> パブリック CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)

