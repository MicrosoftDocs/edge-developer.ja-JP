---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2PhysicalKeyStatus
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2PhysicalKeyStatus。
ms.openlocfilehash: adecd3b23369935b1dc5729e894eaf1c295a06d3
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012250"
---
# CoreWebView2PhysicalKeyStatus 構造体 (WebView2) 

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

