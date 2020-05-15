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
ms.openlocfilehash: 5b15d6205306e558d1d8709cceed8b7a68a77bce
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654369"
---
# インターフェイス IWebView2AcceleratorKeyPressedEventArgs 

> [!NOTE]
> このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。 最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。

```
interface IWebView2AcceleratorKeyPressedEventArgs
  : public IUnknown
```

AcceleratorKeyPressed イベントのイベント引数。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_KeyEventType](#get_keyeventtype) | イベントを発生させる原因となったキーイベントの種類。
[get_VirtualKey](#get_virtualkey) | 押されたキーまたは離されたキーの Win32 仮想キーコード。
[get_KeyEventLParam](#get_keyeventlparam) | ウィンドウメッセージと共に送信された LPARAM の値。
[get_PhysicalKeyStatus](#get_physicalkeystatus) | ウィンドウメッセージの LPARAM で渡された情報を表す構造体。
[ハンドル](#handle) | これにより、ブラウザプロセスが続行されます。

## Members

#### get_KeyEventType 

イベントを発生させる原因となったキーイベントの種類。

> パブリック HRESULT [get_KeyEventType](#get_keyeventtype)(WEBVIEW2_KEY_EVENT_TYPE * keyeventtype)

これは、WEBVIEW2_KEY_EVENT_TYPE_KEY_DOWN、WEBVIEW2_KEY_EVENT_TYPE_KEY_UP、WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_DOWN、または WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_UP のいずれかです。

#### get_VirtualKey 

押されたキーまたは離されたキーの Win32 仮想キーコード。

> パブリック HRESULT [get_VirtualKey](#get_virtualkey)(UINT * virtualkey)

これは、VK_RETURN や "A" などの ASCII 値 (大文字) など、Win32 仮想キー定数のいずれかになります。 Ctrl キーまたは Alt キーを押しているかどうかを確認するには、GetKeyState (VK_CONTROL) または GetKeyState (VK_MENU) を呼び出します。

#### get_KeyEventLParam 

ウィンドウメッセージと共に送信された LPARAM の値。

> パブリック HRESULT [get_KeyEventLParam](#get_keyeventlparam)(INT * lParam)

WM_KEYDOWN と WM_KEYUP メッセージのドキュメントを参照してください。

#### get_PhysicalKeyStatus 

ウィンドウメッセージの LPARAM で渡された情報を表す構造体。

> パブリック HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)(WEBVIEW2_PHYSICAL_KEY_STATUS * physicalKeyStatus)

#### ハンドル 

これにより、ブラウザプロセスが続行されます。

> パブリック HRESULT[ハンドル](#handle)(BOOL handled)

TRUE を渡すと、ブラウザーはこのショートカットキーの既定の操作を実行できなくなります。 イベントハンドラーが呼び出し[ハンドル ()](#handle)を使わずに返された場合は、ハンドル (FALSE) の呼び出しと同じです。 呼び出し[ハンドル ()](#handle)は、既に呼び出されているか、イベントハンドラーから返された場合は何もしません。

