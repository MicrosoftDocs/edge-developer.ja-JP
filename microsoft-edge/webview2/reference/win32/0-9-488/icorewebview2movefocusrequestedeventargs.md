---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2MoveFocusRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: dc6c904150605dc05b2fef00600785b9840f0eb8
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880529"
---
# 0.9.515-インターフェイス ICoreWebView2MoveFocusRequestedEventArgs 

> [!NOTE]
> この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。 最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface ICoreWebView2MoveFocusRequestedEventArgs
  : public IUnknown
```

MoveFocusRequested されたイベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Handled](#get_handled) | イベントがアプリによって処理されたかどうかを示します。
[get_Reason](#get_reason) | MoveFocus 要求されたイベントを WebView が発生させる理由。
[put_Handled](#put_handled) | Handled プロパティを設定します。

## Members

#### get_Handled 

イベントがアプリによって処理されたかどうかを示します。

> パブリック HRESULT [get_Handled](#get_handled)(ブール * 値)

アプリがフォーカスを目的の場所に移動した場合は、Handled プロパティを TRUE に設定する必要があります。 イベントハンドラーから制御が返された後、Handled プロパティが false の場合は、既定のアクションが実行されます。 既定のアクションでは、アプリで次のタブ位置の子ウィンドウを検索し、フォーカスをそのウィンドウに移動しようとします。 フォーカスを移動できるその他のウィンドウがない場合は、WebView の web コンテンツ内でフォーカスが変更されます。

#### get_Reason 

MoveFocus 要求されたイベントを WebView が発生させる理由。

> パブリック HRESULT [get_Reason](#get_reason)(COREWEBVIEW2_MOVE_FOCUS_REASON * 値)

#### put_Handled 

Handled プロパティを設定します。

> パブリック HRESULT [put_Handled](#put_handled)(BOOL 値)

