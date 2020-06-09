---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: e0fb3f9ff7114b0c4f2a42893adabfd72e9616de
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698954"
---
# CoreWebView2PhysicalKeyStatus 構造体 (WebView2) 

名前空間: WebView2 () \
"WebView2" アセンブリを実行します。

Win32 キーイベントに指定された LPARAM にパックされた情報を表す構造体。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[IsExtendedKey](#isextendedkey) | キーが拡張キーかどうかを示します。
[IsKeyReleased](#iskeyreleased) | 切り替えの状態。
[IsMenuKeyDown](#ismenukeydown) | コンテキストコード。
[RepeatCount](#repeatcount) | 現在のメッセージの繰り返し回数。
[ScanCode](#scancode) | スキャンコード。
[通常の方法](#waskeydown) | 前のキーの状態。

詳細については、WM_KEYDOWN のドキュメントを参照してください [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown) 。

## Members

#### IsExtendedKey 

キーが拡張キーかどうかを示します。

> パブリック int [IsExtendedKey](#isextendedkey)

#### IsKeyReleased 

切り替えの状態。

> 公開 int [Iskeyreleased](#iskeyreleased)

#### IsMenuKeyDown 

コンテキストコード。

> パブリック int [Ismenukeydown](#ismenukeydown)

#### RepeatCount 

現在のメッセージの繰り返し回数。

> パブリック uint [Repeatcount](#repeatcount)

#### ScanCode 

スキャンコード。

> パブリック uint[スキャンコード](#scancode)

#### 通常の方法 

前のキーの状態。

> 公開 int [WasKeyDown](#waskeydown)

