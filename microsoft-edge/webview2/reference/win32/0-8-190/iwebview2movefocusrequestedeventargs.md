---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 2e3afec26b0e09a80182118f74b6f50733b0c71a
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654355"
---
# インターフェイス IWebView2MoveFocusRequestedEventArgs 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface IWebView2MoveFocusRequestedEventArgs
  : public IUnknown
```

MoveFocusRequested されたイベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Reason](#get_reason) | MoveFocus 要求されたイベントを WebView が発生させる理由。
[get_Handled](#get_handled) | イベントがアプリによって処理されたかどうかを示します。
[put_Handled](#put_handled) | Handled プロパティを設定します。

## Members

#### get_Reason 

MoveFocus 要求されたイベントを WebView が発生させる理由。

> パブリック HRESULT [get_Reason](#get_reason)(WEBVIEW2_MOVE_FOCUS_REASON * 値)

#### get_Handled 

イベントがアプリによって処理されたかどうかを示します。

> パブリック HRESULT [get_Handled](#get_handled)(ブール * 値)

アプリがフォーカスを目的の場所に移動した場合は、Handled プロパティを TRUE に設定する必要があります。 イベントハンドラーから制御が返された後、Handled プロパティが false の場合は、既定のアクションが実行されます。 既定のアクションでは、アプリで次のタブ位置の子ウィンドウを検索し、フォーカスをそのウィンドウに移動しようとします。 フォーカスを移動できるその他のウィンドウがない場合は、WebView の web コンテンツ内でフォーカスが変更されます。

#### put_Handled 

Handled プロパティを設定します。

> パブリック HRESULT [put_Handled](#put_handled)(BOOL 値)

