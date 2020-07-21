---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (CoreWebView2EnvironmentOptions の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 8378c6388f0bc7cda26ef4a34b8ef5e8d5c95f4d
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885045"
---
# 0.9.515 クラスの WebView2 クラス (CoreWebView2EnvironmentOptions) 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

WebView2 環境の作成に使用するオプション。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[AdditionalBrowserArguments](#additionalbrowserarguments) | WebView の動作を変更するには、AdditionalBrowserArguments を指定できます。
[言語](#language) | WebView が実行される既定の言語。
[Targetserversion](#targetcompatiblebrowserversion) | Edge WebView2 ランタイムバイナリのバージョンは、呼び出し元のアプリケーションと互換性がある必要があります。
[CoreWebView2EnvironmentOptions](#corewebview2environmentoptions) | CoreWebView2EnvironmentOptions クラスの新しいインスタンスを初期化します。

WebView2EnvironmentOptions には既定の実装が用意されています。

## Members

#### AdditionalBrowserArguments 

WebView の動作を変更するには、AdditionalBrowserArguments を指定できます。

> パブリック文字列の[Additionalbrowserarguments](#additionalbrowserarguments)

これらは、コマンドラインの一部としてブラウザープロセスに渡されます。 ブラウザプロセスへのコマンドラインスイッチの詳細については、「[フラグを使って Chromium を実行](https://aka.ms/RunChromiumWithFlags)する」を参照してください。 コマンドラインスイッチを使用してアプリを起動すると、 `--edge-webview-switches=xxx` そのスイッチの値 (上の例では xxx) もブラウザープロセスのコマンドラインに追加されます。 次のような一部 `--user-data-dir` のスイッチは、WebView として内部的で重要です。 これらのスイッチは、指定した場合でも無視されます。 同じスイッチが複数回指定されている場合は、最後のスイッチが優先されます。 無効および有効な機能を除き、同じスイッチの異なる値をマージしようとすることはありません。 およびで指定された機能は、 `--enable-features` `--disable-features` 単純なロジックにマージされます。これらの機能は、指定された機能と組み込み機能の和集合であり、機能が無効になっている場合は、[有効な機能] の一覧から削除されます。 アプリプロセスのコマンドライン `--edge-webview-switches` 値は、additionalBrowserArguments パラメーターが処理された後に処理されます。 一部の機能は内部で無効にされているため、有効にすることはできません。 指定したスイッチの解析に失敗した場合、それらは無視されます。 既定では、追加のフラグなしでブラウザープロセスを実行します。

#### 言語 

WebView が実行される既定の言語。

> 公開文字列の[言語](#language)

これは、コンテキストメニューやダイアログなどのブラウザー Ui に適用されます。 また、WebView が web サイトに送信する受け入れ言語の HTTP ヘッダーにも適用されます。 この形式は、 `language[-country]` `language` iso 639 の2文字コードであり、 `country` iso 3166 の2文字のコードです。

#### Targetserversion 

Edge WebView2 ランタイムバイナリのバージョンは、呼び出し元のアプリケーションと互換性がある必要があります。

> パブリック文字列[ターゲット](#targetcompatiblebrowserversion)/セルの sion

これは、アプリケーションで使用されている SDK のバージョンと対応する Edge WebView2 ランタイムバージョンに既定値が設定されています。 この値の形式は、"この値" と "他の型 Serversion" の値の形式と同じです。 対象となるのは、のバージョン部分だけです。 チャネルのサフィックス (存在する場合) は無視されます。 実際に使用されている Edge WebView2 ランタイムバイナリのバージョンは、指定された Target互換のバージョンとは異なる場合があります。 互換性が保証されるだけであることが保証されます。 CoreWebView2Environment の参照サーバーの文字列プロパティで実際のバージョンを確認できます。

#### CoreWebView2EnvironmentOptions 

CoreWebView2EnvironmentOptions クラスの新しいインスタンスを初期化します。

> パブリック[CoreWebView2EnvironmentOptions](#corewebview2environmentoptions)(文字列 additionalBrowserArguments、文字列言語、文字列ターゲット)

##### パラメーター
* `additionalBrowserArguments` WebView の動作を変更するには、AdditionalBrowserArguments を指定できます。 

* `language` WebView が実行される既定の言語。 

* `targetCompatibleBrowserVersion` Edge WebView2 ランタイムバイナリのバージョンは、呼び出し元のアプリケーションと互換性がある必要があります。

