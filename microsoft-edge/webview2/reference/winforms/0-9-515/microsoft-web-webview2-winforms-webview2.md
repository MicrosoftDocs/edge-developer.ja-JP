---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WinForms の WebView2 を WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft WebView2。 winforms。 WebView2
ms.openlocfilehash: 7d707c2a6ecb8127074735f06ba6d4f1f28eea0c
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879451"
---
# WebView2 クラス WinForms クラスの WebView2 

名前空間: WebView2 WinForms \
アセンブリ: Microsoft.Web.WebView2.WinForms.dll

```
class Microsoft.Web.WebView2.WinForms.WebView2
  : public Control
```

WebView2 を WinForms に埋め込むためのコントロールです。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[ContentLoading](#contentloading) | ナビゲーションが新しい URI で開始され、その URI のコンテンツがレンダリングを開始した後のコンテンツ読み込みディスパッチ。
[CoreWebView2Ready](#corewebview2ready) | このイベントは、コントロールの[CoreWebView2](#corewebview2)が (初期化のトリガーに関係なく) 初期化が完了したときにトリガーされ、何でも使用される前に発生します。
[NavigationCompleted](#navigationcompleted) | NavigationCompleted はトップレベルドキュメントの移動によって、レンダリングが正常に完了するかどうかによって、発行が完了します。
[NavigationStarting](#navigationstarting) | NavigationStarting のトップレベルのドキュメントについて新しい移動が開始される前にディスパッチを開始します。
[SourceChanged](#sourcechanged) | ソースプロパティが変更された後の SourceChanged ディスパッチ。
[WebMessageReceived](#webmessagereceived) | WebMessageReceived は、web コンテンツによってアプリホストにメッセージが送信された後でディスパッチさ `chrome.webview.postMessage` れます。
[CoreWebView2](#corewebview2) | 基になる CoreWebView2。
[Source](#source) | Source プロパティは、WebView2 のトップレベルのドキュメントの URI です。
[ZoomFactor](#zoomfactor) | WebView のズームファクター。
[CanGoBack](#cangoback) | Webview が GoBack メソッドによってナビゲーション履歴内の前のページに移動できる場合は、true を返します。
[CanGoForward](#cangoforward) | | Forward メソッドを使用して、ナビゲーション履歴内の次のページに移動できる場合は true を返します。
[EnsureCoreWebView2Async](#ensurecorewebview2async) | コントロールの[CoreWebView2](#corewebview2)の初期化を明示的にトリガーします。
[すべてのユーティリティ](#executescriptasync) | WebView2 のトップレベルのドキュメントで、指定されたスクリプトを実行します。
[GoBack](#goback) | ナビゲーション履歴で前のページに移動します。
[GoForward](#goforward) | ナビゲーション履歴の次のページに移動します。
[NavigateToString](#navigatetostring) | WebView2 のトップレベルのドキュメントとして、指定された HTML をレンダリングします。
[再](#reload) | WebView2 のトップレベルの文書を再度読み込みます。
[Stop](#stop) | WebView2 で進行中のナビゲーションを停止します。
[WebView2](#webview2) | 新しい WebView2 WinForms コントロールを作成します。

## Members

#### ContentLoading 

ナビゲーションが新しい URI で開始され、その URI のコンテンツがレンダリングを開始した後のコンテンツ読み込みディスパッチ。

> パブリックイベント EventHandler< CoreWebView2ContentLoadingEventArgs > [Contentloading](#contentloading)

これは、CoreWebView2 の ContentLoading イベントと同じです。 詳細については、「CoreWebView2 の読み込みドキュメント」を参照してください。

#### CoreWebView2Ready 

このイベントは、コントロールの[CoreWebView2](#corewebview2)が (初期化のトリガーに関係なく) 初期化が完了したときにトリガーされ、何でも使用される前に発生します。

> パブリックイベント EventHandler< EventArgs > [CoreWebView2Ready](#corewebview2ready)

このイベントを処理する必要があるのは、CoreWebView2 に対して1回限りのセットアップ操作を実行する必要がある場合です (たとえば、イベントハンドラーの追加、設定の構成、ドキュメント作成スクリプトのインストール、ホストオブジェクトの追加など)。

このイベントには引数はありません。送信者は、CoreWebView2 プロパティが有効 (つまり null ではない) WebView2 コントロールになります。

#### NavigationCompleted 

NavigationCompleted はトップレベルドキュメントの移動によって、レンダリングが正常に完了するかどうかによって、発行が完了します。

> パブリックイベントイベントハンドラー< CoreWebView2NavigationCompletedEventArgs > [Navigationcompleted](#navigationcompleted)

これは、CoreWebView2 の NavigationCompleted イベントと同じです。 詳細については、「CoreWebView2 のドキュメント」を参照してください。

#### NavigationStarting 

NavigationStarting のトップレベルのドキュメントについて新しい移動が開始される前にディスパッチを開始します。

> パブリックイベントイベントハンドラー< CoreWebView2NavigationStartingEventArgs > [Navigationstarting](#navigationstarting)

これは、CoreWebView2 の NavigationStarting イベントと同じです。 詳細については、「CoreWebView2」を参照してください。

#### SourceChanged 

ソースプロパティが変更された後の SourceChanged ディスパッチ。

> パブリックイベント EventHandler< CoreWebView2SourceChangedEventArgs > [Sourcechanged](#sourcechanged)

これは、ナビゲーション中に発生する可能性があります。それ以外の場合は、ページのスクリプトによってドキュメントの URI が変更されます。 これは、CoreWebView2 の SourceChanged イベントと同じです。 詳細については、CoreWebView2 を参照してください。

#### WebMessageReceived 

WebMessageReceived は、web コンテンツによってアプリホストにメッセージが送信された後でディスパッチさ `chrome.webview.postMessage` れます。

> パブリックイベント EventHandler< CoreWebView2WebMessageReceivedEventArgs > [WebMessageReceived](#webmessagereceived)

これは、CoreWebView2 の WebMessageReceived イベントと同じです。 詳細については、WebMessageReceived のドキュメント CoreWebView2 を参照してください。

#### CoreWebView2 

基になる CoreWebView2。

> パブリック CoreWebView2 [CoreWebView2](#corewebview2)

このプロパティを使って、WebView2 で公開されているよりも多くの操作を WebView2 コンテンツで実行します。 この値は、初期化されるまで null です。 Initializeasync 呼び出しメソッドを使用して、基になる CoreWebView2 を強制的に初期化することができます。

#### Source 

Source プロパティは、WebView2 のトップレベルのドキュメントの URI です。

> パブリック Uri[ソース](#source)

ソースの設定は、CoreWebView2 の呼び出しと同じです。 基になる CoreWebView2 がまだ初期化されていない場合、このプロパティは "about: blank" となります。 プロパティが絶対 URI 以外の URI または null に設定されている場合、プロパティは変わりません。 詳細については、CoreWebView2 のドキュメントを参照してください。

#### ZoomFactor 

WebView のズームファクター。

> パブリックダブル[ZoomFactor](#zoomfactor)

#### CanGoBack 

Webview が GoBack メソッドによってナビゲーション履歴内の前のページに移動できる場合は、true を返します。

> public bool [CanGoBack](#cangoback)

これは、CoreWebView2 の CanGoBack プロパティと同じです。 基になる CoreWebView2 がまだ初期化されていない場合、このプロパティは false になります。 詳細については、CanGoBack のドキュメント CoreWebView2 を参照してください。

#### CanGoForward 

| Forward メソッドを使用して、ナビゲーション履歴内の次のページに移動できる場合は true を返します。

> public bool [CanGoForward](#cangoforward)

これは、CoreWebView2 の CanGoForward プロパティと同じです。 基になる CoreWebView2 がまだ初期化されていない場合、このプロパティは false になります。 詳細については、CanGoForward のドキュメント CoreWebView2 を参照してください。

#### EnsureCoreWebView2Async 

コントロールの[CoreWebView2](#corewebview2)の初期化を明示的にトリガーします。

> public Task [EnsureCoreWebView2Async](#ensurecorewebview2async)(CoreWebView2Environment environment)

##### パラメーター
* `environment` CoreWebView2 の作成に使用する事前に作成された CoreWebView2Environment。 独自の環境を作成することにより、CoreWebView2 の初期化方法に影響するいくつかのオプションを制御できます。 Null (既定値) を渡すと、既定の環境が自動的に作成されて使用されます。 

##### 返し
バックグラウンドの初期化プロセスを表すタスク。 タスクが完了したら、CoreWebView2 プロパティを使用できるようになります (つまり、null 以外)。 コントロールの[CoreWebView2Ready](#corewebview2ready)イベントは、タスクが完了する前に呼び出されます。 

このメソッドを追加すると、何度も呼び出されることはありません (指定した環境は無視されます)。最初の呼び出しと同じタスクを返します。 初期化後にこのメソッドを呼び出す場合は、 [Source](#source)プロパティを設定しても効果はありません (指定された環境は無視されます)。単に、既に進行中の初期化を示すタスクを返します。 

##### 例外
* `System.InvalidOperationException` UI 以外のスレッドから呼び出された場合にスローされます。

#### すべてのユーティリティ 

WebView2 のトップレベルのドキュメントで、指定されたスクリプトを実行します。

> パブリック async タスク< 文字列 > [Executesの](#executescriptasync)テキスト (文字列スクリプト)

これは、CoreWebView2 の Executesメソッドと同じです。 基になる CoreWebView2 がまだ初期化されていない場合、このメソッドは InvalidOperationException をスローします。 詳細については CoreWebView2.ExecuteScriptAsync のドキュメントを参照してください。

#### GoBack 

ナビゲーション履歴で前のページに移動します。

> パブリック void [GoBack](#goback)()

これは、CoreWebView2 の GoBack メソッドと同じです。 基になる CoreWebView2 がまだ初期化されていない場合、このメソッドは何も行いません。 詳細については、CoreWebView2 のドキュメントを参照してください。

#### GoForward 

ナビゲーション履歴の次のページに移動します。

> パブリック void [Goforward](#goforward)()

これは、CoreWebView2 の GoForward メソッドと同じです。 基になる CoreWebView2 がまだ初期化されていない場合、このメソッドは何も行いません。 詳細については、「CoreWebView2 フォワードドキュメント」を参照してください。

#### NavigateToString 

WebView2 のトップレベルのドキュメントとして、指定された HTML をレンダリングします。

> パブリック void [NavigateToString](#navigatetostring)(文字列 htmlcontent)

これは、CoreWebView2 の NavigateToString メソッドと同じです。 基になる CoreWebView2 がまだ初期化されていない場合、このメソッドは InvalidOperationException をスローします。 詳細については、NavigateToString のドキュメント CoreWebView2 を参照してください。

#### 再 

WebView2 のトップレベルの文書を再度読み込みます。

> パブリックの void[再読み込み](#reload)()

これは、CoreWebView2 の Reload メソッドと同じです。 基になる CoreWebView2 がまだ初期化されていない場合、このメソッドは InvalidOperationException をスローします。 詳細については、CoreWebView2 のドキュメントを参照してください。

#### Stop 

WebView2 で進行中のナビゲーションを停止します。

> パブリック void [Stop](#stop)()

これは、CoreWebView2 の Stop メソッドと同じです。 基になる CoreWebView2 がまだ初期化されていない場合、このメソッドは何も行いません。 詳細については、CoreWebView2 のドキュメントを参照してください。

#### WebView2 

新しい WebView2 WinForms コントロールを作成します。

> パブリック[WebView2](#webview2)()

構築後、CoreWebView2 プロパティは null になります。 [EnsureCoreWebView2Async](#ensurecorewebview2async)を呼び出して、基になる CoreWebView2 を初期化します。

