---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 2ea3500c5e230b543f75241c47c58163276942da
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654401"
---
# インターフェイス ICoreWebView2NewWindowRequestedEventArgs 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface ICoreWebView2NewWindowRequestedEventArgs
  : public IUnknown
```

NewWindowRequested イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Uri](#get_uri) | NewWindowRequest のターゲット uri。
[put_NewWindow](#put_newwindow) | NewWindowRequest の結果として WebView を設定します。
[get_NewWindow](#get_newwindow) | 新しいウィンドウを取得します。
[put_Handled](#put_handled) | NewWindowRequestedEvent がホストによって処理されるかどうかを設定します。
[get_Handled](#get_handled) | NewWindowRequestedEvent がホストによって処理されるかどうかを取得します。
[get_IsUserInitiated](#get_isuserinitiated) | IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。
[GetDeferral](#getdeferral) | [ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを取得し、イベントを遅延状態にします。

このイベントは、webview 内のコンテンツが新しいウィンドウ (open () など) に要求されたときに発生します。

## Members

#### get_Uri 

NewWindowRequest のターゲット uri。

> パブリック HRESULT [get_Uri](#get_uri)(LPWSTR * Uri)

#### put_NewWindow 

NewWindowRequest の結果として WebView を設定します。

> パブリック HRESULT [put_NewWindow](#put_newwindow)([ICoreWebView2](ICoreWebView2.md) * NewWindow)

ターゲット webview に移動しないようにします。 NewWindow が設定されている場合は、トップレベルのウィンドウが開いている WindowProxy として返されます。

#### get_NewWindow 

新しいウィンドウを取得します。

> パブリック HRESULT [get_NewWindow](#get_newwindow)([ICoreWebView2](ICoreWebView2.md) * * NewWindow)

#### put_Handled 

NewWindowRequestedEvent がホストによって処理されるかどうかを設定します。

> パブリック HRESULT [put_Handled](#put_handled)(ブール値で処理される)

この値が false で、NewWindow が設定されていない場合は、WebView にポップアップウィンドウが表示され、開いている WindowProxy として返されます。 Window に対して NewWindow が設定されていない場合は true に設定します。 [呼び出し] を開くと、開いている WindowProxy は dummy ウィンドウオブジェクトになり、ウィンドウは読み込まれません。 Default は false です。

#### get_Handled 

NewWindowRequestedEvent がホストによって処理されるかどうかを取得します。

> パブリック HRESULT [get_Handled](#get_handled)(ブール * Handled)

#### get_IsUserInitiated 

IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。

> パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール * isUserInitiated)

#### GetDeferral 

[ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを取得し、イベントを遅延状態にします。

> パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) * * 延期)

[ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを使って、後でウィンドウを開く要求を完了することができます。 このイベントが延期されている間、opener window は、ウィンドウから切り離されたウィンドウに WindowProxy を返します。これは、延期が完了すると移動します。

