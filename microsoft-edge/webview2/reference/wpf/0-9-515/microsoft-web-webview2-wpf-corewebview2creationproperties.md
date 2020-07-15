---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 を CoreWebView2CreationProperties します。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft のように指定します。
ms.openlocfilehash: 72c85df7d2d58d74cf27e04eb7128fdfa14ca2d9
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880256"
---
# WebView2 クラスを CoreWebView2CreationProperties します。 

名前空間: Microsoft WebView2 \
アセンブリ: Microsoft.Web.WebView2.Wpf.dll

```
class Microsoft.Web.WebView2.Wpf.CoreWebView2CreationProperties
  : public DependencyObject
```

このクラスは、CoreWebView2Environment を作成するために使用される最も一般的なパラメーターのバンドルです。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[BrowserExecutableFolder](#browserexecutablefolder) | このインスタンスで環境を作成するときに、CoreWebView2Environment の browserExecutableFolder パラメーターとして渡す値を取得または設定します。
[言語](#language) | このインスタンスで環境を作成するときに、CoreWebView2Environment に渡される CoreWebView2EnvironmentOptions パラメーターの Language プロパティに使用する値を取得または設定します。
[UserDataFolder](#userdatafolder) | このインスタンスで環境を作成するときに、CoreWebView2Environment の userDataFolder パラメーターとして渡す値を取得または設定します。
[CoreWebView2CreationProperties](#corewebview2creationproperties) | すべてのプロパティの既定のデータを使用して、CoreWebView2CreationProperties の新しいインスタンスを作成します。

この主な目的は、 [WebView2](microsoft-web-webview2-wpf-webview2.md)で暗黙的な初期化中に使用される環境をカスタマイズするために、 [WebView2 プロパティ](microsoft-web-webview2-wpf-webview2.md)に設定することです。 また、一般的に使用される環境パラメーターを依存関係プロパティとして作成し、マークアップで使うことができる優れた WPF 統合ユーティリティです。

このクラスは、可能なすべての環境のカスタマイズオプションを含めることを意図していません。 WebView2 コントロールによって使用されている環境を完全に制御する必要がある場合[は、CoreWebView2Environment](microsoft-web-webview2-wpf-webview2.md)を使用して独自の環境を作成してから[WebView2](microsoft-web-webview2-wpf-webview2.md)に渡す*ことによっ*て、そのコントロールを明示的に初期化する必要があります。 初期化の概要については、 [WebView2](microsoft-web-webview2-wpf-webview2.md)クラスのドキュメントを参照してください。

## Members

#### BrowserExecutableFolder 

このインスタンスで環境を作成するときに、CoreWebView2Environment の browserExecutableFolder パラメーターとして渡す値を取得または設定します。

> パブリック文字列[ブラウザーの Executablefolder](#browserexecutablefolder)

#### 言語 

このインスタンスで環境を作成するときに、CoreWebView2Environment に渡される CoreWebView2EnvironmentOptions パラメーターの Language プロパティに使用する値を取得または設定します。

> 公開文字列の[言語](#language)

#### UserDataFolder 

このインスタンスで環境を作成するときに、CoreWebView2Environment の userDataFolder パラメーターとして渡す値を取得または設定します。

> パブリック文字列[Userdatafolder](#userdatafolder)

#### CoreWebView2CreationProperties 

すべてのプロパティの既定のデータを使用して、CoreWebView2CreationProperties の新しいインスタンスを作成します。

> パブリック[CoreWebView2CreationProperties](#corewebview2creationproperties)()

