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
ms.openlocfilehash: b7d738628d6627232780e003f126b45c0421d6f0
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698948"
---
# WebView2 クラス (EdgeNotFoundException クラス) 

名前空間: WebView2 () \
"WebView2" アセンブリを実行します。

```
class Microsoft.Web.WebView2.Core.EdgeNotFoundException
  : public Exception
```

エッジのインストールが見つからない場合にスローされる例外。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[EdgeNotFoundException](#edgenotfoundexception) | EdgeNotFoundException クラスの新しいインスタンスを初期化します。
[EdgeNotFoundException](#edgenotfoundexception) | この例外の原因である内部例外への参照を使って、EdgeNotFoundException クラスの新しいインスタンスを初期化します。
[EdgeNotFoundException](#edgenotfoundexception) | 指定したエラーメッセージを使用して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。
[EdgeNotFoundException](#edgenotfoundexception) | 指定したエラーメッセージと、この例外の原因である内部例外への参照を指定して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。

## Members

#### EdgeNotFoundException 

EdgeNotFoundException クラスの新しいインスタンスを初期化します。

> パブリック[EdgeNotFoundException](#edgenotfoundexception)()

#### EdgeNotFoundException 

この例外の原因である内部例外への参照を使って、EdgeNotFoundException クラスの新しいインスタンスを初期化します。

> パブリック[EdgeNotFoundException](#edgenotfoundexception)(例外の内部)

##### パラメーター
* `inner` 現在の例外の原因である例外。

#### EdgeNotFoundException 

指定したエラーメッセージを使用して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。

> パブリック[EdgeNotFoundException](#edgenotfoundexception)(文字列メッセージ)

##### パラメーター
* `message` 例外の理由を説明するエラーメッセージ。

#### EdgeNotFoundException 

指定したエラーメッセージと、この例外の原因である内部例外への参照を指定して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。

> パブリック[EdgeNotFoundException](#edgenotfoundexception)(文字列メッセージ、例外の内部)

##### パラメーター
* `message` 例外の理由を説明するエラーメッセージ。 

* `inner` 現在の例外の原因である例外。

