---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2NewWindowRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: cbcac385546c44e776ed48b8ae4d3ab754b614e0
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885894"
---
# 0.8.355-インターフェイス IWebView2NewWindowRequestedEventArgs 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2NewWindowRequestedEventArgs
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
[GetDeferral](#getdeferral) | [IWebView2Deferral](IWebView2Deferral.md)オブジェクトを取得し、イベントを遅延状態にします。

このイベントは、webview 内のコンテンツが新しいウィンドウ (open () など) に要求されたときに発生します。

## Members

#### get_Uri 

NewWindowRequest のターゲット uri。

> パブリック HRESULT [get_Uri](#get_uri)(LPWSTR * Uri)

#### put_NewWindow 

NewWindowRequest の結果として WebView を設定します。

> パブリック HRESULT [put_NewWindow](#put_newwindow)([IWebView2WebView](IWebView2WebView.md) * NewWindow)

ターゲット webview に移動しないようにします。 NewWindow が設定されている場合は、トップレベルのウィンドウが開いている WindowProxy として返されます。

#### get_NewWindow 

新しいウィンドウを取得します。

> パブリック HRESULT [get_NewWindow](#get_newwindow)([IWebView2WebView](IWebView2WebView.md) * * NewWindow)

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

[IWebView2Deferral](IWebView2Deferral.md)オブジェクトを取得し、イベントを遅延状態にします。

> パブリック HRESULT [Getdeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) * * 延期)

[IWebView2Deferral](IWebView2Deferral.md)オブジェクトを使って、後でウィンドウを開く要求を完了することができます。 このイベントが延期されている間、opener window は、ウィンドウから切り離されたウィンドウに WindowProxy を返します。これは、延期が完了すると移動します。

