---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (EdgeNotFoundException の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: fc65d857f11a77a1d3629d40266f0453acadaa7b
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886312"
---
# 0.9.515 クラスの WebView2 クラス (EdgeNotFoundException) 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

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

