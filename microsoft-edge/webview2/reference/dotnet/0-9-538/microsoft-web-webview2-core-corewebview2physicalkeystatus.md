---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 (CoreWebView2PhysicalKeyStatus の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2PhysicalKeyStatus。
ms.openlocfilehash: 17ed4a578234a056a7e6ff347829a12e39fa93bd
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010923"
---
# WebView2 構造体 0.9.579-CoreWebView2PhysicalKeyStatus 構造体 

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

> パブリック uint [スキャンコード](#scancode)

#### 通常の方法 

前のキーの状態。

> 公開 int [WasKeyDown](#waskeydown)

