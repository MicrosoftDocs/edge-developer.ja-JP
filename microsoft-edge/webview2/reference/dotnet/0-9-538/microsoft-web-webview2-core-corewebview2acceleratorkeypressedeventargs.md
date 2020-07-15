---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2AcceleratorKeyPressedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2AcceleratorKeyPressedEventArgs。
ms.openlocfilehash: ef1ca9707bba15fdaf8f37a306b56fdfc2c34588
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878982"
---
# WebView2 クラス (CoreWebView2AcceleratorKeyPressedEventArgs クラス) 

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

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

