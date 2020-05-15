---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/28/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 10311cf26b66e824447461530f1ce0870ea01ceb
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654279"
---
# インターフェイス ICoreWebView2AcceleratorKeyPressedEventArgs 

```
interface ICoreWebView2AcceleratorKeyPressedEventArgs
  : public IUnknown
```

AcceleratorKeyPressed イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Handled](#get_handled) | AcceleratorKeyPressedEvent ハンドラーの呼び出し中に、WebView は、ホストによってアクセスされるかどうかを決定するためにブロックされます。
[get_KeyEventKind](#get_keyeventkind) | イベントを発生させる原因となったキーイベントの種類。
[get_KeyEventLParam](#get_keyeventlparam) | ウィンドウメッセージと共に送信された LPARAM の値。
[get_PhysicalKeyStatus](#get_physicalkeystatus) | ウィンドウメッセージの LPARAM で渡された情報を表す構造体。
[get_VirtualKey](#get_virtualkey) | 押されたキーまたは離されたキーの Win32 仮想キーコード。
[put_Handled](#put_handled) | Handled プロパティを設定します。

## Members

#### get_Handled 

AcceleratorKeyPressedEvent ハンドラーの呼び出し中に、WebView は、ホストによってアクセスされるかどうかを決定するためにブロックされます。

> パブリック HRESULT [get_Handled](#get_handled)(ブール * Handled)

Handled プロパティが TRUE に設定されている場合、この操作によって WebView はこのアクセラレータキーの既定のアクションを実行できなくなります。 それ以外の場合、WebView は、ショートカットキーの既定のアクションを実行します。

#### get_KeyEventKind 

イベントを発生させる原因となったキーイベントの種類。

> パブリック HRESULT [get_KeyEventKind](#get_keyeventkind)(COREWEBVIEW2_KEY_EVENT_KIND * keyEventKind)

#### get_KeyEventLParam 

ウィンドウメッセージと共に送信された LPARAM の値。

> パブリック HRESULT [get_KeyEventLParam](#get_keyeventlparam)(INT * lParam)

WM_KEYDOWN と WM_KEYUP メッセージのドキュメントを参照してください。

#### get_PhysicalKeyStatus 

ウィンドウメッセージの LPARAM で渡された情報を表す構造体。

> パブリック HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)(COREWEBVIEW2_PHYSICAL_KEY_STATUS * physicalKeyStatus)

#### get_VirtualKey 

押されたキーまたは離されたキーの Win32 仮想キーコード。

> パブリック HRESULT [get_VirtualKey](#get_virtualkey)(UINT * virtualkey)

これは、VK_RETURN や "A" などの ASCII 値 (大文字) など、Win32 仮想キー定数のいずれかになります。 Ctrl キーまたは Alt キーを押しているかどうかを確認するには、GetKeyState (VK_CONTROL) または GetKeyState (VK_MENU) を呼び出します。

#### put_Handled 

Handled プロパティを設定します。

> パブリック HRESULT [put_Handled](#put_handled)(ブール値で処理される)

