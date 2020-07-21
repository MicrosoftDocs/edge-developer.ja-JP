---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (CoreWebView2PhysicalKeyStatus の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: eecf4dd59d12c30667defd4e078e8624718bde26
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884590"
---
# WebView2 構造体 0.9.515-CoreWebView2PhysicalKeyStatus 構造体 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

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

