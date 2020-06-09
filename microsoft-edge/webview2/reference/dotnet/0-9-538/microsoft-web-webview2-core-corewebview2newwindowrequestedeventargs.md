---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 54e2c06ef65f64560fbd5687148eace253352203
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698956"
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
[WindowFeatures](#windowfeatures) | ウィンドウで指定されたウィンドウ機能。 [通話] を開きます。
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

#### WindowFeatures 

> [!NOTE]
> これは、SDK バージョン[0.9.538-プレリリース](../../../releasenotes.md#09538)で出荷される[実験的な API](../../../concepts/versioning.md#experimental-apis)です。

ウィンドウで指定されたウィンドウ機能。 [通話] を開きます。

> パブリック CoreWebView2WindowFeatures [Windowfeatures](#windowfeatures)

これらの機能は、新しい webview ウィンドウの配置とサイズ変更のために考慮することができます。

#### GetDeferral 

CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。

> パブリック CoreWebView2Deferral [Getdeferral](#getdeferral)()

CoreWebView2Deferral オブジェクトを使って、後でウィンドウを開く要求を完了することができます。 このイベントが延期されている間、opener window は、ウィンドウから切り離されたウィンドウに WindowProxy を返します。これは、延期が完了すると移動します。

