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
ms.openlocfilehash: 9ee85620ece653a2312076f7b6f4fe9f6ca3da92
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699094"
---
# WebView2 クラス (CoreWebView2WindowFeatures クラス) 

> [!NOTE]
> これは、SDK バージョン[0.9.538-プレリリース](../../../releasenotes.md#09538)で出荷される[実験的な API](../../../concepts/versioning.md#experimental-apis)です。

名前空間: WebView2 () \
"WebView2" アセンブリを実行します。

WebView ポップアップウィンドウのウィンドウ機能。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[サイズ](#height) | ウィンドウの高さ。
[Left](#left) | ウィンドウの左端。
[メニューバー](#menubar) | メニューバーを表示するかどうか。
[スクロールバー](#scrollbars) | スクロールバーを表示するかどうか。
[ステータス](#status) | ステータスバーを追加するかどうか。
[ツール バー](#toolbar) | ブラウザーのツールバーを表示するかどうか。
[先頭](#top) | ウィンドウの一番上の位置。
[幅](#width) | ウィンドウの幅。
[HasPosition](#hasposition) | は左と上の値を指定しています。
[HasSize](#hassize) | 高さと幅の値を指定しました。

## Members

#### サイズ 

ウィンドウの高さ。

> パブリック uint の[高さ](#height)

#### Left 

ウィンドウの左端。

> 公開 uint の[左](#left)

HasPosition が false の場合は、エラーになります。

#### メニューバー 

メニューバーを表示するかどうか。

> パブリック int[メニューバー](#menubar)

#### スクロールバー 

スクロールバーを表示するかどうか。

> パブリック int[スクロールバー](#scrollbars)

#### ステータス 

ステータスバーを追加するかどうか。

> パブリック整数の[状態](#status)

#### ツール バー 

ブラウザーのツールバーを表示するかどうか。

> パブリックの int[ツールバー](#toolbar)

#### 先頭 

ウィンドウの一番上の位置。

> 公開 uint の[最上位](#top)

HasPosition が false の場合は、エラーになります。

#### 幅 

ウィンドウの幅。

> パブリック uint の[幅](#width)

#### HasPosition 

は左と上の値を指定しています。

> 公開 int [Hasposition](#hasposition)()

#### HasSize 

高さと幅の値を指定しました。

> 公開 int [Hassize](#hassize)()

