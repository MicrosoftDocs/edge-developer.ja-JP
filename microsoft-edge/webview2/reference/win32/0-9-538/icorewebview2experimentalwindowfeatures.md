---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ExperimentalWindowFeatures
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExperimentalWindowFeatures
ms.openlocfilehash: 2672f2aac842fd475f6148c439dbecdacd7793ee
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885404"
---
# インターフェイス ICoreWebView2ExperimentalWindowFeatures 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalWindowFeatures
  : public IUnknown
```

WebView ポップアップウィンドウのウィンドウ機能。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[get_Height](#get_height) | ウィンドウの高さ。
[get_Left](#get_left) | ウィンドウの左端。 HasPosition が false の場合は、エラーになります。
[get_MenuBar](#get_menubar) | メニューバーを表示するかどうか。
[get_ScrollBars](#get_scrollbars) | スクロールバーを表示するかどうか。
[get_Status](#get_status) | ステータスバーを追加するかどうか。
[get_Toolbar](#get_toolbar) | ブラウザーのツールバーを表示するかどうか。
[get_Top](#get_top) | ウィンドウの一番上の位置。 HasPosition が false の場合は、エラーになります。
[get_Width](#get_width) | ウィンドウの幅。
[HasPosition](#hasposition) | は左と上の値を指定しています。
[HasSize](#hassize) | 高さと幅の値を指定しました。

これらのフィールドは、次のように指定されているときに、window に渡された "windowFeatures" と一致します。[https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features](https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features)

## Members

#### get_Height 

ウィンドウの高さ。

> パブリック HRESULT [get_Height](#get_height)(UINT32 * Height)

最小値は100です。 HasSize が false の場合は、エラーになります。

#### get_Left 

ウィンドウの左端。 HasPosition が false の場合は、エラーになります。

> パブリック HRESULT [get_Left](#get_left)(UINT32 * Left)

#### get_MenuBar 

メニューバーを表示するかどうか。

> パブリック HRESULT [get_MenuBar](#get_menubar)(ブール * MenuBar)

#### get_ScrollBars 

スクロールバーを表示するかどうか。

> パブリック HRESULT [get_ScrollBars](#get_scrollbars)(ブール * ScrollBars)

#### get_Status 

ステータスバーを追加するかどうか。

> パブリック HRESULT [get_Status](#get_status)(ブール * 状態)

#### get_Toolbar 

ブラウザーのツールバーを表示するかどうか。

> パブリック HRESULT [get_Toolbar](#get_toolbar)(ブール * ツールバー)

#### get_Top 

ウィンドウの一番上の位置。 HasPosition が false の場合は、エラーになります。

> パブリック HRESULT [get_Top](#get_top)(UINT32 * Top)

#### get_Width 

ウィンドウの幅。

> パブリック HRESULT [get_Width](#get_width)(UINT32 * Width)

最小値は100です。 HasSize が false の場合は、エラーになります。

#### HasPosition 

は左と上の値を指定しています。

> パブリック HRESULT [hasposition](#hasposition)(ブール * hasposition)

#### HasSize 

高さと幅の値を指定しました。

> パブリック HRESULT [hassize](#hassize)(ブール * hassize)

