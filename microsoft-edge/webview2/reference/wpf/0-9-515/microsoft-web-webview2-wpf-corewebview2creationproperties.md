---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: d2c3b3ee179dec217418241031142549d170e440
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654157"
---
# WebView2 クラスを CoreWebView2CreationProperties します。 

名前空間: Microsoft WebView2 \
"WebView2" というアセンブリ。

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

