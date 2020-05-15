---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/13/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: f2c3bcb5334abc907a838971ebc1773b6485194f
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654241"
---
# WebView2 クラスを WebView2 します。 

名前空間: Microsoft WebView2 \
"WebView2" というアセンブリ。

```
class Microsoft.Web.WebView2.Wpf.WebView2
  : public HwndHost
```

WPF アプリケーションに web コンテンツを埋め込むためのコントロールです。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[ContentLoading](#contentloading) | CoreWebView2 の CoreWebView2 読み込みイベントを囲むラッパー。
[CoreWebView2Ready](#corewebview2ready) | このイベントは、コントロールの CoreWebView2 が (初期化のトリガーに関係なく) 初期化が完了したときにトリガーされ、何でも使用される前に発生します。
[NavigationCompleted](#navigationcompleted) | CoreWebView2 の CoreWebView2 イベントを囲むラッパー。
[NavigationStarting](#navigationstarting) | CoreWebView2 の CoreWebView2 開始イベントを囲むラッパー。
[SourceChanged](#sourcechanged) | CoreWebView2 の CoreWebView2 Echanged イベントを囲むラッパー。
[WebMessageReceived](#webmessagereceived) | CoreWebView2 の WebMessageReceived イベントを囲むラッパー。
[CanGoBack](#cangoback) | ナビゲーション履歴で前のページに移動できる場合は true を返します。
[CanGoForward](#cangoforward) | ナビゲーション履歴の次のページに移動できる場合は true を返します。
[CoreWebView2](#corewebview2) | CoreWebView2 の基になるコア COM API の完全な機能にアクセスします。
[プロパティのプロパティ](#creationproperties) | コントロールの CoreWebView2 の初期化時に使用されるオプションのバッグを取得または設定します。
[Source](#source) | WebView が現在表示されているトップレベルの Uri (または、CoreWebView2 の初期化が完了した後に表示されます)。
[EnsureCoreWebView2Async](#ensurecorewebview2async) | コントロールの CoreWebView2 の初期化を明示的にトリガーします。
[すべてのユーティリティ](#executescriptasync) | WebView でレンダリングされた現在のトップレベルドキュメントの javaScript パラメーターから JavaScript コードを実行します。
[GoBack](#goback) | ナビゲーション履歴で、WebView を前のページに移動します。
[GoForward](#goforward) | WebView をナビゲーション履歴の次のページに移動します。
[NavigateToString](#navigatetostring) | 新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。
[再](#reload) | 現在のページを再読み込みします。
[Stop](#stop) | すべてのナビゲーションと保留中のリソースフェッチを停止します。
[WebView2](#webview2) | WebView2 コントロールの新しいインスタンスを作成します。
[BuildWindowCore](#buildwindowcore) | これは HwndHost からオーバーライドされ、HWND の作成を指示するために呼び出されます。
[DestroyWindowCore](#destroywindowcore) | これは HwndHost からオーバーライドされ、HWND の破棄を指示するために呼び出されます。
[破棄](#dispose) | これは、IDispose パターンの一般的な実装に従って、基本クラスによって呼び出されます。
[HasFocusWithinCore](#hasfocuswithincore) | これは、HwndHost からオーバーライドされ、フォーカスがコントロールとウィンドウのどちらにあるかを WPF が認識する必要があるときに呼び出されます。
[OnKeyDown](#onkeydown) | これは UIElement から呼び出され、キー入力の入力を処理できるようにするために呼び出されます。
[OnKeyUp](#onkeyup) | 「Control.onkeydown」をご覧ください。
[Onpreview Keydown](#onpreviewkeydown) | これは "プレビュー" です (例:
[Onpreview Keyup](#onpreviewkeyup) | 詳しくは、「Onpreview Keydown」をご覧ください。
[OnWindowPositionChanged](#onwindowpositionchanged) | これは、コントロールの位置が変わったときに HwndHost によってオーバーライドされて呼び出されます。
[タブの基本](#tabintocore) | これは、HwndHost によって上書きされ、tab キーを使ってコントロール/ウィンドウにフォーカスが移動したことを通知します。

このコントロールは、実質的には WebView2 COM API を囲むラッパーであり、次のようなドキュメントを見つけることができます。 [https://aka.ms/webview2](https://aka.ms/webview2) CoreWebView2 プロパティにアクセスすると、基になる ICoreWebView2 インターフェイスとそのすべての機能に直接アクセスできます。 最も一般的な COM 機能の一部は、ラッパーメソッド、コントロールのプロパティ、イベントを使って直接アクセスすることもできます。

作成時には、コントロールの CoreWebView2 プロパティは null になります。 これは、CoreWebView2 を作成することが、エッジブラウザープロセスの起動などの負荷の高い操作であるためです。 CoreWebView2 を作成するには2つの方法があります。 1) EnsureCoreWebView2Async メソッドを呼び出します。 これは、明示的な初期化と呼ばれます。 2) Source プロパティを設定します (たとえば、マークアップから行うことができます)。 これは暗黙的な初期化と呼ばれます。 どちらのオプションを選択しても、バックグラウンドで初期化が開始され、終了するのを待たずに呼び出し元に戻ります。 初期化プロセスに関するオプションを指定するには、独自の CoreWebView2Environment を EnsureCoreWebView2Async に渡すか、または初期化の前にコントロールの "作成用プロパティ" プロパティを設定します。

(トリガーされた方法に関係なく) 初期化が完了すると、次の処理が行われます。 1) コントロールの CoreWebView2Ready イベントが呼び出されます。 CoreWebView2 を使用する前に1回限りのセットアップ操作を実行する必要がある場合は、そのイベントのハンドラーで操作を行う必要があります。 2) ソースプロパティに Uri が設定されている場合、コントロールはバックグラウンドでその Uri への移動を開始します (つまり、ナビゲーションが完了するのを待たずに、これらの手順は続行します)。 3) EnsureCoreWebView2Async から返されたタスクが完了します。

初期化プロセスに関係するメソッド、プロパティ、イベントの詳細については、その固有のドキュメントを参照してください。

コントロールの CoreWebView2 は非常に重いオブジェクトであるため (実行されている複数のプロセスとディスク領域を使用する可能性があります)、コントロールは IDisposable を実装して、解放する明示的な手段を提供します。 Dispose を呼び出すと、CoreWebView2 とその基になっているリソース (他の WebViews でも使用されているものを除く) が解放され、CoreWebView2 が null にリセットされます。 Dispose が呼び出された後は、CoreWebView2 を再初期化することはできません。必要な機能を使おうとすると、ObjectDisposedException がスローされます。

このコントロールは、WPF エコシステムの外部に存在するウィンドウを埋め込むために、HwndHost を拡張します。 これには、コントロールの入出力動作、および UIElement と FrameworkElement から "継承" する機能について、いくつかの意味があります。 詳しい情報については、HwndHost と WPF/Win32 の相互運用機能に関するドキュメントを参照してください。

* [https://docs.microsoft.com/dotnet/api/system.windows.interop.hwndhost](https://docs.microsoft.com/dotnet/api/system.windows.interop.hwndhost)

* [https://docs.microsoft.com/dotnet/framework/wpf/advanced/wpf-and-win32-interoperation#hwnds-inside-wpf](https://docs.microsoft.com/dotnet/framework/wpf/advanced/wpf-and-win32-interoperation#hwnds-inside-wpf)

## Members

#### ContentLoading 

CoreWebView2 の CoreWebView2 読み込みイベントを囲むラッパー。

> パブリックイベント EventHandler< CoreWebView2ContentLoadingEventArgs > [Contentloading](#contentloading)

このイベントと CoreWebView2 読み込みの唯一の違いは、ハンドラーに渡される最初のパラメーターです。 このイベントのハンドラーは WebView2 コントロールを受け取りますが、CoreWebView2 のハンドラーは CoreWebView2 インスタンスを受け取ります。

#### CoreWebView2Ready 

このイベントは、コントロールの CoreWebView2 が (初期化のトリガーに関係なく) 初期化が完了したときにトリガーされ、何でも使用される前に発生します。

> パブリックイベント EventHandler< EventArgs > [CoreWebView2Ready](#corewebview2ready)

このイベントを処理する必要があるのは、CoreWebView2 に対して1回限りのセットアップ操作を実行する必要がある場合です (たとえば、イベントハンドラーの追加、設定の構成、ドキュメント作成スクリプトのインストール、ホストオブジェクトの追加など)。 初期化の概要については、WebView2 クラスのドキュメントを参照してください。

このイベントには引数はありません。送信者は、CoreWebView2 プロパティが有効 (つまり null ではない) WebView2 コントロールになります。

#### NavigationCompleted 

CoreWebView2 の CoreWebView2 イベントを囲むラッパー。

> パブリックイベントイベントハンドラー< CoreWebView2NavigationCompletedEventArgs > [Navigationcompleted](#navigationcompleted)

このイベントと CoreWebView2 が完了する唯一の違いは、ハンドラーに渡される最初のパラメーターです。 このイベントのハンドラーは WebView2 コントロールを受け取りますが、CoreWebView2 のハンドラーは CoreWebView2 インスタンスを受け取ります。

#### NavigationStarting 

CoreWebView2 の CoreWebView2 開始イベントを囲むラッパー。

> パブリックイベントイベントハンドラー< CoreWebView2NavigationStartingEventArgs > [Navigationstarting](#navigationstarting)

このイベントと CoreWebView2 の唯一の違いは、ハンドラーに渡される最初のパラメーターです。 このイベントのハンドラーは WebView2 コントロールを受け取りますが、CoreWebView2 のハンドラーは CoreWebView2 インスタンスを受け取ります。

#### SourceChanged 

CoreWebView2 の CoreWebView2 Echanged イベントを囲むラッパー。

> パブリックイベント EventHandler< CoreWebView2SourceChangedEventArgs > [Sourcechanged](#sourcechanged)

このイベントと CoreWebView2 Echanged の唯一の違いは、ハンドラーに渡される最初のパラメーターです。 このイベントのハンドラーは WebView2 コントロールを受け取りますが、CoreWebView2 のハンドラーは CoreWebView2 インスタンスを受け取ります。

#### WebMessageReceived 

CoreWebView2 の WebMessageReceived イベントを囲むラッパー。

> パブリックイベント EventHandler< CoreWebView2WebMessageReceivedEventArgs > [WebMessageReceived](#webmessagereceived)

このイベントと CoreWebView2 の唯一の違いは、ハンドラーに渡される最初のパラメーターです。 このイベントのハンドラーは WebView2 コントロールを受け取りますが、CoreWebView2 のハンドラーは CoreWebView2 インスタンスを受け取ります。

#### CanGoBack 

ナビゲーション履歴で前のページに移動できる場合は true を返します。

> public bool [CanGoBack](#cangoback)

CoreWebView2 の CanGoBack プロパティを囲むラッパー。 CoreWebView2 CoreWebView2 がまだ初期化されていない場合は、false を返します。

#### CanGoForward 

ナビゲーション履歴の次のページに移動できる場合は true を返します。

> public bool [CanGoForward](#cangoforward)

CoreWebView2 の CanGoForward プロパティを囲むラッパー。 CoreWebView2 CoreWebView2 がまだ初期化されていない場合は、false を返します。

#### CoreWebView2 

CoreWebView2 の基になるコア COM API の完全な機能にアクセスします。

> パブリック CoreWebView2 [CoreWebView2](#corewebview2)

初期化が完了するまで null を返します。 初期化の概要については、WebView2 クラスのドキュメントを参照してください。

##### 例外
* `InvalidOperationException` 呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。 詳細については、「DispatcherObject アクセス」を参照してください。

* `ObjectDisposedException` コントロールで Dispose が既に呼び出されている場合にスローされます。

#### プロパティのプロパティ 

コントロールの CoreWebView2 の初期化時に使用されるオプションのバッグを取得または設定します。

> パブリック CoreWebView2CreationProperties の[プロパティ](#creationproperties)

このプロパティを設定しても、コントロールの CoreWebView2 の初期化が開始された後は機能しません (古い値は保持されます)。 初期化の概要については、WebView2 クラスのドキュメントを参照してください。

#### Source 

WebView が現在表示されているトップレベルの Uri (または、CoreWebView2 の初期化が完了した後に表示されます)。

> パブリック Uri[ソース](#source)

一般的に、このプロパティを取得することは、CoreWebView2 の CoreWebView2 プロパティを取得して、このプロパティを設定することと同じです。 CoreWebView2 で CoreWebView2 を呼び出すことと同じです。 CoreWebView2 が初期化される前にこのプロパティを取得すると、それに設定された最後の Uri が取得されます。 CoreWebView2 を初期化する前にこのプロパティを設定すると、初期化はバックグラウンドで開始されます (まだ進行中ではない場合)。その後、WebView2 は指定した Uri に移動します。 初期化の概要については、WebView2 クラスのドキュメントを参照してください。

##### 例外
* `ObjectDisposedException` コントロールで Dispose が既に呼び出されている場合にスローされます。

#### EnsureCoreWebView2Async 

コントロールの CoreWebView2 の初期化を明示的にトリガーします。

> public Task [EnsureCoreWebView2Async](#ensurecorewebview2async)(CoreWebView2Environment environment)

初期化の概要については、WebView2 クラスのドキュメントを参照してください。

##### パラメーター
* `environment` CoreWebView2 の作成に使用する事前に作成された CoreWebView2Environment。 独自の環境を作成することにより、CoreWebView2 の初期化方法に影響するいくつかのオプションを制御できます。 このメソッドに環境を渡すと、"メッセージの送信" プロパティで指定した設定が上書きされます。 Null (既定値) を渡すと、"作成中" プロパティに値が設定されていない場合は、既定の環境が自動的に作成されて使用されます。 

##### 返し
バックグラウンドの初期化プロセスを表すタスク。 タスクが完了したら、CoreWebView2 プロパティを使用できるようになります (つまり、null 以外)。 コントロールの CoreWebView2Ready イベントは、タスクが完了する前に呼び出されます。 

このメソッドを追加すると、何度も呼び出されることはありません (指定した環境は無視されます)。最初の呼び出しと同じタスクを返します。 初期化後にこのメソッドを呼び出す場合は、Source プロパティを設定しても効果はありません (指定された環境は無視されます)。単に、既に進行中の初期化を示すタスクを返します。 このメソッドは非同期であり、タスクを返すため、ほとんどの UI コントロールのほとんどのパブリック機能と同様に、UI スレッドでも呼び出す必要があります。 

##### 例外
* `InvalidOperationException` 呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。 詳細については、「DispatcherObject アクセス」を参照してください。

* `ObjectDisposedException` コントロールで Dispose が既に呼び出されている場合にスローされます。

#### すべてのユーティリティ 

WebView でレンダリングされた現在のトップレベルドキュメントの javaScript パラメーターから JavaScript コードを実行します。

> パブリック async タスク< 文字列 > [Executesの](#executescriptasync)テキスト (文字列 javaScript)

CoreWebView2 で CoreWebView2 を呼び出す場合と同じです。

##### 例外
* `InvalidOperationException` CoreWebView2 がまだ初期化されていない場合にスローされます。

* `InvalidOperationException` 呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。 詳細については、「DispatcherObject アクセス」を参照してください。

* `ObjectDisposedException` コントロールで Dispose が既に呼び出されている場合にスローされます。

#### GoBack 

ナビゲーション履歴で、WebView を前のページに移動します。

> パブリック void [GoBack](#goback)()

CoreWebView2 で CoreWebView2 が初期化されていない場合は、CoreWebView2 を呼び出しても、何も起こりません。

##### 例外
* `InvalidOperationException` 呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。 詳細については、「DispatcherObject アクセス」を参照してください。

* `ObjectDisposedException` コントロールで Dispose が既に呼び出されている場合にスローされます。

#### GoForward 

WebView をナビゲーション履歴の次のページに移動します。

> パブリック void [Goforward](#goforward)()

CoreWebView2 で CoreWebView2 が初期化されていない場合は、CoreWebView2 を呼び出す場合と同等です。

##### 例外
* `InvalidOperationException` 呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。 詳細については、「DispatcherObject アクセス」を参照してください。

* `ObjectDisposedException` コントロールで Dispose が既に呼び出されている場合にスローされます。

#### NavigateToString 

新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。

> パブリック void [NavigateToString](#navigatetostring)(文字列 htmlcontent)

CoreWebView2 で CoreWebView2 を呼び出すのと同じ NavigateToString

##### 例外
* `InvalidOperationException` CoreWebView2 がまだ初期化されていない場合にスローされます。

" <exception cref="InvalidOperationException"> 呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。  詳細については、「DispatcherObject アクセス」を参照してください。 </exception>
<exception cref="ObjectDisposedException">コントロールで Dispose が既に呼び出されている場合にスローされます。

#### 再 

現在のページを再読み込みします。

> パブリックの void[再読み込み](#reload)()

CoreWebView2 で CoreWebView2 を呼び出すのと同じです。

##### 例外
* `InvalidOperationException` CoreWebView2 がまだ初期化されていない場合にスローされます。

" <exception cref="InvalidOperationException"> 呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。  詳細については、「DispatcherObject アクセス」を参照してください。 </exception>
<exception cref="ObjectDisposedException">コントロールで Dispose が既に呼び出されている場合にスローされます。

#### Stop 

すべてのナビゲーションと保留中のリソースフェッチを停止します。

> パブリック void [Stop](#stop)()

CoreWebView2 で CoreWebView2 を呼び出すのと同じです。

##### 例外
* `InvalidOperationException` CoreWebView2 がまだ初期化されていない場合にスローされます。

" <exception cref="InvalidOperationException"> 呼び出しスレッドがこのオブジェクトを作成したスレッド (通常は UI スレッド) ではない場合にスローされます。  詳細については、「DispatcherObject アクセス」を参照してください。 </exception>
<exception cref="ObjectDisposedException">コントロールで Dispose が既に呼び出されている場合にスローされます。

#### WebView2 

WebView2 コントロールの新しいインスタンスを作成します。

> パブリック[WebView2](#webview2)()

コントロールの CoreWebView2 は、初期化されるまで null になります。 初期化の概要については、WebView2 クラスのドキュメントを参照してください。

#### BuildWindowCore 

これは HwndHost からオーバーライドされ、HWND の作成を指示するために呼び出されます。

> protected override HandleRef [Buildwindowcore](#buildwindowcore)(HandleRef hwndParent)

##### パラメーター
* `hwndParent` 作成したものの親として使用する HWND。

##### 返し
作成した HWND。

#### DestroyWindowCore 

これは HwndHost からオーバーライドされ、HWND の破棄を指示するために呼び出されます。

> protected override void [Destroywindowcore](#destroywindowcore)(HandleRef hwnd)

##### パラメーター
* `hwnd` 破棄する必要がある HWND。

#### 破棄 

これは、IDispose パターンの一般的な実装に従って、基本クラスによって呼び出されます。

> protected override void [Dispose](#dispose)(bool disposing)

これは、CoreWebView2 を含む、基盤となるすべての COM リソースを解放することで実装されています。

##### パラメーター
* `disposing` 呼び出し元が明示的に Dispose を呼び出している場合は True、完了している場合は false。

#### HasFocusWithinCore 

これは、HwndHost からオーバーライドされ、フォーカスがコントロールとウィンドウのどちらにあるかを WPF が認識する必要があるときに呼び出されます。

> protected override bool [HasFocusWithinCore](#hasfocuswithincore)()

Wpf は非 WPF ウィンドウをホストしているため、WPF がそれ自体を認識することはできません。そのため、代わりにこれを呼び出すように求められます。 応答するには、CoreWebView2 イベントに基づいて状態を追跡します。これにより、フォーカスが獲得または切断されたときに発生します。

##### 返し
フォーカスがコントロール/ウィンドウにある場合は True、そうでない場合は false。

#### OnKeyDown 

これは UIElement から呼び出され、キー入力の入力を処理できるようにするために呼び出されます。

> protected override void [control.onkeydown](#onkeydown)(KeyEventArgs e)

Wpf では、WPF 以外のウィンドウをホストしているため、キーボードイベントに対して実際に呼び出すことはできません。 ウィンドウにフォーカスがある場合、入力は、WPF の最上位ウィンドウと入力システムではなく、Windows に直接送信されます。 このオーバーライドは、CoreWebView2 から WPF へのアクセラレータキー入力の明示的な転送 (CoreWebView2Controller_AcceleratorKeyPressed) でのみ呼び出す必要があります。 その場合でも、この KeyDownEvent は、PreviewKeyDownEvent の実装によって明示的にトリガーされ、WPF の通常のシステムと一致するために発生します。 そのため、プロセスは次のようになります。 CoreWebView2Controller_AcceleratorKeyPressed-> は、PreviewKeyDownEvent > Onpreview Keydown-> KeyDownEvent > Control.onkeydown を発生させます。

#### OnKeyUp 

「Control.onkeydown」をご覧ください。

> protected override void [OnKeyUp](#onkeyup)(KeyEventArgs e)

#### Onpreview Keydown 

これは "プレビュー" です (例:

> protected override void [Onpreview keydown](#onpreviewkeydown)(KeyEventArgs e)

トンネリング) バージョンの Control.onkeydown では、実際に最初に発生します。 Control.onkeydown と同じように、CoreWebView2 から明示的にキーの押下を転送している場合にのみ呼び出されます。 WPF の標準の入力処理を模倣するために、これを受け取ったときに、標準のバブルの KeyDownEvent を回避して、発生させることができます。 これにより、WPF ツリー内の他のユーザーは、キー入力を処理している場合に WPF 自体がトリガーする同じ標準ペアの入力イベントを表示できます。

#### Onpreview Keyup 

詳しくは、「Onpreview Keydown」をご覧ください。

> protected override void [Onpreview keyup](#onpreviewkeyup)(KeyEventArgs e)

#### OnWindowPositionChanged 

これは、コントロールの位置が変わったときに HwndHost によってオーバーライドされて呼び出されます。

> protected override void [Onwindowpositionchanged](#onwindowpositionchanged)(Rect rcBoundingBox)

HwndHost は、作成した HWND の更新を行います。 必要な作業は、CoreWebView2 を新しい場所に合わせて移動することです。

#### タブの基本 

これは、HwndHost によって上書きされ、tab キーを使ってコントロール/ウィンドウにフォーカスが移動したことを通知します。

> protected [override ブール値](#tabintocore)のブール値 (TraversalRequest 要求)

WPF では、非 WPF HWND へのフォーカスの切り替えを管理することはできないため、ここに切り替えを委任します。 このため、私たちの仕事は、外部の HWND にフォーカスを置くだけです。

##### パラメーター
* `request` フォーカスの移動方法に関する情報。

##### 返し
ナビゲーションを処理したことを示す場合は True、そうしない場合は false を指定します。

