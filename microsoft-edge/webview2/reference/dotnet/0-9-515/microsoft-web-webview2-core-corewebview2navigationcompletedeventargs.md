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
ms.openlocfilehash: 2a18fe9f8f79a109047d029affab8d84a6ef845c
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654180"
---
# WebView2 クラス (CoreWebView2NavigationCompletedEventArgs クラス) 

名前空間: WebView2 () \
"WebView2" アセンブリを実行します。

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

> 公開ブール[値](#issuccess)

これは、エラーページ内で終了するナビゲーション (ネットワークがない、DNS 参照エラー、HTTP server が4xx で応答する) でも、また、移動ページで呼び出された window. stop () などの追加機能については、false になります。

#### NavigationId 

ナビゲーションの ID です。

> パブリック ulong [Navigationid](#navigationid)

#### WebErrorStatus 

ナビゲーションに失敗した場合のエラーコード。

> パブリック CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)

