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
ms.openlocfilehash: 25d11995dd305a1958d6252c2ddf3afdb313fad1
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697183"
---
# インターフェイス ICoreWebView2AcceleratorKeyPressedEventArgs 

> [!NOTE]
> この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。 最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。

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

