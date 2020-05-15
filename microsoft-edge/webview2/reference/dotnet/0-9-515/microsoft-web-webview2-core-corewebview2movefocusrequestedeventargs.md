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
ms.openlocfilehash: 3c88108f0e1df89c62c8713ff37f35d0c759cf6c
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654540"
---
# WebView2 クラス (CoreWebView2MoveFocusRequestedEventArgs クラス) 

名前空間: WebView2 () \
"WebView2" アセンブリを実行します。

MoveFocusRequested されたイベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[Handled](#handled) | イベントがアプリによって処理されたかどうかを示します。
[理由](#reason) | MoveFocus 要求されたイベントを WebView が発生させる理由。

## Members

#### Handled 

イベントがアプリによって処理されたかどうかを示します。

> パブリックブール[処理](#handled)

アプリがフォーカスを目的の場所に移動した場合は、Handled プロパティを TRUE に設定する必要があります。 イベントハンドラーから制御が返された後、Handled プロパティが false の場合は、既定のアクションが実行されます。 既定のアクションでは、アプリで次のタブ位置の子ウィンドウを検索し、フォーカスをそのウィンドウに移動しようとします。 フォーカスを移動できるその他のウィンドウがない場合は、WebView の web コンテンツ内でフォーカスが変更されます。

#### 理由 

MoveFocus 要求されたイベントを WebView が発生させる理由。

> パブリック CoreWebView2MoveFocusReason の[理由](#reason)

