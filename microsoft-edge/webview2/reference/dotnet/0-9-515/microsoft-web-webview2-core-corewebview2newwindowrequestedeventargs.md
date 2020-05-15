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
ms.openlocfilehash: cca15ccc5292f5eaf6f317ffb657f46fcd84b4a9
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654538"
---
# WebView2 クラス (CoreWebView2NewWindowRequestedEventArgs クラス) 

名前空間: WebView2 () \
"WebView2" アセンブリを実行します。

NewWindowRequested イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[Handled](#handled) | NewWindowRequestedEvent がホストによって処理されるかどうか。
[IsUserInitiated](#isuserinitiated) | IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。
[NewWindow](#newwindow) | 新しいウィンドウを取得します。
[URI](#uri) | NewWindowRequest のターゲット uri。
[GetDeferral](#getdeferral) | CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。

このイベントは、webview 内のコンテンツが新しいウィンドウを開くように要求したときに発生します (ウィンドウを開く () など)。

## Members

#### Handled 

NewWindowRequestedEvent がホストによって処理されるかどうか。

> パブリックブール[処理](#handled)

この値が false で、NewWindow が設定されていない場合は、WebView にポップアップウィンドウが表示され、開いている WindowProxy として返されます。 Window に対して NewWindow が設定されていない場合は true に設定します。 [呼び出し] を開くと、開いている WindowProxy は dummy ウィンドウオブジェクトになり、ウィンドウは読み込まれません。 Default は false です。

#### IsUserInitiated 

IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。

> public bool [Isuserinitiated](#isuserinitiated)

#### NewWindow 

新しいウィンドウを取得します。

> パブリック CoreWebView2 [NewWindow](#newwindow)

#### URI 

NewWindowRequest のターゲット uri。

> パブリック文字列の[Uri](#uri)

ターゲット webview に移動しないようにします。 NewWindow が設定されている場合は、トップレベルのウィンドウが開いている WindowProxy として返されます。

#### GetDeferral 

CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。

> パブリック CoreWebView2Deferral [Getdeferral](#getdeferral)()

CoreWebView2Deferral オブジェクトを使って、後でウィンドウを開く要求を完了することができます。 このイベントが延期されている間、opener window は、ウィンドウから切り離されたウィンドウに WindowProxy を返します。これは、延期が完了すると移動します。

