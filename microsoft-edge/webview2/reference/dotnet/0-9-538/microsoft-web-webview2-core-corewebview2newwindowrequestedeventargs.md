---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 (CoreWebView2NewWindowRequestedEventArgs の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2NewWindowRequestedEventArgs。
ms.openlocfilehash: adeb4c0f223e8b38e3cefb93ae189a351d9828a5
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010909"
---
# 0.9.579 クラスの WebView2 クラス (CoreWebView2NewWindowRequestedEventArgs) 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

NewWindowRequested イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[Handled](#handled) | NewWindowRequestedEvent がホストによって処理されるかどうか。
[IsUserInitiated](#isuserinitiated) | IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。
[NewWindow](#newwindow) | 新しいウィンドウを取得します。
[URI](#uri) | NewWindowRequest のターゲット uri。
[WindowFeatures](#windowfeatures) | ウィンドウで指定されたウィンドウ機能。 [通話] を開きます。
[GetDeferral](#getdeferral) | CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。

このイベントは、webview 内のコンテンツが新しいウィンドウを開くように要求したときに発生します (ウィンドウを開く () など)。

## Members

#### Handled 

NewWindowRequestedEvent がホストによって処理されるかどうか。

> パブリックブール [処理](#handled)

この値が false で、NewWindow が設定されていない場合は、WebView にポップアップウィンドウが表示され、開いている WindowProxy として返されます。 Window に対して NewWindow が設定されていない場合は true に設定します。 [呼び出し] を開くと、開いている WindowProxy は dummy ウィンドウオブジェクトになり、ウィンドウは読み込まれません。 Default は false です。

#### IsUserInitiated 

IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。

> public bool [Isuserinitiated](#isuserinitiated)

#### NewWindow 

新しいウィンドウを取得します。

> パブリック CoreWebView2 [NewWindow](#newwindow)

#### URI 

NewWindowRequest のターゲット uri。

> パブリック文字列の [Uri](#uri)

ターゲット webview に移動しないようにします。 NewWindow が設定されている場合は、トップレベルのウィンドウが開いている WindowProxy として返されます。

#### WindowFeatures 

ウィンドウで指定されたウィンドウ機能。 [通話] を開きます。

> パブリック CoreWebView2WindowFeatures [Windowfeatures](#windowfeatures)

これらの機能は、新しい webview ウィンドウの配置とサイズ変更のために考慮することができます。

#### GetDeferral 

CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。

> パブリック CoreWebView2Deferral [Getdeferral](#getdeferral)()

CoreWebView2Deferral オブジェクトを使って、後でウィンドウを開く要求を完了することができます。 このイベントが延期されている間、opener window は、ウィンドウから切り離されたウィンドウに WindowProxy を返します。これは、延期が完了すると移動します。

