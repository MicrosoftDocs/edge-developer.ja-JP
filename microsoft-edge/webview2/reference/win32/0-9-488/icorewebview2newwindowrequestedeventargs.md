---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: cc64e805b0d929d71340d5a012e7848860c35f5c
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654419"
---
# インターフェイス ICoreWebView2NewWindowRequestedEventArgs 

```
interface ICoreWebView2NewWindowRequestedEventArgs
  : public IUnknown
```

NewWindowRequested イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Handled](#get_handled) | NewWindowRequestedEvent がホストによって処理されるかどうかを取得します。
[get_IsUserInitiated](#get_isuserinitiated) | IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。
[get_NewWindow](#get_newwindow) | 新しいウィンドウを取得します。
[get_Uri](#get_uri) | NewWindowRequest のターゲット uri。
[GetDeferral](#getdeferral) | [ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを取得し、イベントを遅延状態にします。
[put_Handled](#put_handled) | NewWindowRequestedEvent がホストによって処理されるかどうかを設定します。
[put_NewWindow](#put_newwindow) | NewWindowRequest の結果として WebView を設定します。

このイベントは、webview 内のコンテンツが新しいウィンドウを開くように要求したときに発生します (ウィンドウを開く () など)。

## Members

#### get_Handled 

NewWindowRequestedEvent がホストによって処理されるかどうかを取得します。

> パブリック HRESULT [get_Handled](#get_handled)(ブール * Handled)

#### get_IsUserInitiated 

IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。

> パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール * isUserInitiated)

#### get_NewWindow 

新しいウィンドウを取得します。

> パブリック HRESULT [get_NewWindow](#get_newwindow)([ICoreWebView2](icorewebview2.md) * * NewWindow)

#### get_Uri 

NewWindowRequest のターゲット uri。

> パブリック HRESULT [get_Uri](#get_uri)(LPWSTR * Uri)

#### GetDeferral 

[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを取得し、イベントを遅延状態にします。

> パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) * * 延期)

[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを使って、後でウィンドウを開く要求を完了することができます。 このイベントが延期されている間、opener window は、ウィンドウから切り離されたウィンドウに WindowProxy を返します。これは、延期が完了すると移動します。

#### put_Handled 

NewWindowRequestedEvent がホストによって処理されるかどうかを設定します。

> パブリック HRESULT [put_Handled](#put_handled)(ブール値で処理される)

この値が false で、NewWindow が設定されていない場合は、WebView にポップアップウィンドウが表示され、開いている WindowProxy として返されます。 Window に対して NewWindow が設定されていない場合は true に設定します。 [呼び出し] を開くと、開いている WindowProxy は dummy ウィンドウオブジェクトになり、ウィンドウは読み込まれません。 Default は false です。

#### put_NewWindow 

NewWindowRequest の結果として WebView を設定します。

> パブリック HRESULT [put_NewWindow](#put_newwindow)([ICoreWebView2](icorewebview2.md) * NewWindow)

ターゲット webview に移動しないようにします。 NewWindow が設定されている場合は、トップレベルのウィンドウが開いている WindowProxy として返されます。

