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
ms.openlocfilehash: ef2eb16f6ba0186494400e6190d316ea503f9f16
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654489"
---
# WebView2 クラス (CoreWebView2AcceleratorKeyPressedEventArgs クラス) 

名前空間: WebView2 () \
"WebView2" アセンブリを実行します。

AcceleratorKeyPressed イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[Handled](#handled) | AcceleratorKeyPressedEvent ハンドラーの呼び出し中に、WebView は、ホストによってアクセスされるかどうかを決定するためにブロックされます。
[KeyEventKind](#keyeventkind) | イベントを発生させる原因となったキーイベントの種類。
[KeyEventLParam](#keyeventlparam) | ウィンドウメッセージと共に送信された LPARAM の値。
[PhysicalKeyStatus](#physicalkeystatus) | ウィンドウメッセージの LPARAM で渡された情報を表す構造体。
[VirtualKey](#virtualkey) | 押されたキーまたは離されたキーの Win32 仮想キーコード。

## Members

#### Handled 

AcceleratorKeyPressedEvent ハンドラーの呼び出し中に、WebView は、ホストによってアクセスされるかどうかを決定するためにブロックされます。

> パブリックブール[処理](#handled)

Handled プロパティが TRUE に設定されている場合、この操作によって WebView はこのアクセラレータキーの既定のアクションを実行できなくなります。 それ以外の場合、WebView は、ショートカットキーの既定のアクションを実行します。

#### KeyEventKind 

イベントを発生させる原因となったキーイベントの種類。

> パブリック[CoreWebView2KeyEventKind](./namespace-microsoft-web-webview2-core.md) [keyeventkind](#keyeventkind)

#### KeyEventLParam 

ウィンドウメッセージと共に送信された LPARAM の値。

> パブリック int [Keyeventlparam](#keyeventlparam)

WM_KEYDOWN と WM_KEYUP メッセージのドキュメントを参照してください。

#### PhysicalKeyStatus 

ウィンドウメッセージの LPARAM で渡された情報を表す構造体。

> パブリック[CoreWebView2PhysicalKeyStatus](microsoft-web-webview2-core-corewebview2physicalkeystatus.md) [physicalkeystatus](#physicalkeystatus)

#### VirtualKey 

押されたキーまたは離されたキーの Win32 仮想キーコード。

> パブリック uint の[Virtualkey](#virtualkey)

これは、VK_RETURN や "A" などの ASCII 値 (大文字) など、Win32 仮想キー定数のいずれかになります。 Ctrl キーまたは Alt キーを押しているかどうかを確認するには、GetKeyState (VK_CONTROL) または GetKeyState (VK_MENU) を呼び出します。

