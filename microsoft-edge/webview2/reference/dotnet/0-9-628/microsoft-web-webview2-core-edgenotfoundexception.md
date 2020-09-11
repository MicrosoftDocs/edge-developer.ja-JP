---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について EdgeNotFoundException
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 EdgeNotFoundException。
ms.openlocfilehash: f74e28eb206458525b0043023e80aea3ac368674
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012232"
---
# WebView2 クラス (EdgeNotFoundException クラス) 

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

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

> パブリック [EdgeNotFoundException](#edgenotfoundexception)()

#### EdgeNotFoundException 

この例外の原因である内部例外への参照を使って、EdgeNotFoundException クラスの新しいインスタンスを初期化します。

> パブリック [EdgeNotFoundException](#edgenotfoundexception)(例外の内部)

##### パラメーター
* `inner` 現在の例外の原因である例外。

#### EdgeNotFoundException 

指定したエラーメッセージを使用して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。

> パブリック [EdgeNotFoundException](#edgenotfoundexception)(文字列メッセージ)

##### パラメーター
* `message` 例外の理由を説明するエラーメッセージ。

#### EdgeNotFoundException 

指定したエラーメッセージと、この例外の原因である内部例外への参照を指定して、EdgeNotFoundException クラスの新しいインスタンスを初期化します。

> パブリック [EdgeNotFoundException](#edgenotfoundexception)(文字列メッセージ、例外の内部)

##### パラメーター
* `message` 例外の理由を説明するエラーメッセージ。 

* `inner` 現在の例外の原因である例外。

