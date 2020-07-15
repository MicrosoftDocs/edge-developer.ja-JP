---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2。
ms.openlocfilehash: f8e0ebae683e1e68d12ce541fbec922ec9c05ef4
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879010"
---
# WebView2 クラス (CoreWebView2 クラス) 

名前空間: WebView2 () \
アセンブリ: Microsoft.Web.WebView2.Core.dll

WebView2 では、最新の Edge web ブラウザー技術を使用して、web コンテンツをホストすることができます。

## まとめ

 Members                        | 説明
--------------------------------|---------------------------------------------
[BrowserProcessId](#browserprocessid) | WebView をホストしているブラウザープロセスのプロセス id。
[CanGoBack](#cangoback) | ナビゲーション履歴で前のページに移動できる場合は true を返します。
[CanGoForward](#cangoforward) | ナビゲーション履歴の次のページに移動できる場合は true を返します。
[ContainsFullScreenElement](#containsfullscreenelement) | WebView にフルスクリーン HTML 要素が含まれているかどうかを示します。
[ContainsFullScreenElementChanged](#containsfullscreenelementchanged) | "の場合、要素のプロパティが変更されたときに通知します。
[ContentLoading](#contentloading) | ContentLoading は、コンテンツが読み込まれる前に発生します。 AddScriptToExecuteOnDocumentCreated ContentLoading によって追加されたスクリプトは、同じページナビゲーション (フラグメントナビゲーションや履歴の推移など) が発生した場合には発生しません。
[DocumentTitle](#documenttitle) | 現在のトップレベルドキュメントのタイトル。
[ドキュメントの概要](#documenttitlechanged) | イベントは、WebView の DocumentTitle プロパティが変更されたとき、または NavigationCompleted イベントの前または後に発生する可能性があるときに発生します。
[FrameNavigationCompleted](#framenavigationcompleted) | FrameNavigationCompleted イベントが発生するのは、子フレームが完全に読み込まれた (読み込みが開始された) か、エラーが発生して読み込みを停止したときです。
[FrameNavigationStarting](#framenavigationstarting) | FrameNavigationStarting は、WebView の子フレームが別の URI に移動するためのアクセス許可を要求しているときに発生します。
[変更履歴](#historychanged) | 履歴は、トップレベルのドキュメントのナビゲーション履歴の変更をリッスンします。
[NavigationCompleted](#navigationcompleted) | NavigationCompleted イベントは、WebView が完全に読み込まれたとき (読み込みが開始された場合)、またはエラーが発生して読み込みを停止したときに発生します。
[NavigationStarting](#navigationstarting) | NavigationStarting は、WebView メインフレームが別の URI に移動するためのアクセス許可を要求しているときに発生します。
[NewWindowRequested](#newwindowrequested) | ウィンドウを開くなど、WebView 内のコンテンツが新しいウィンドウを開くように要求したときに発生します。
[PermissionRequested](#permissionrequested) | WebView のコンテンツが権限のある一部のリソースにアクセスするためのアクセス許可を要求したときに発生します。
[ProcessFailed](#processfailed) | WebView プロセスが予期せず終了した場合、または応答不能になったときに発生します。
[Scriptて開く](#scriptdialogopening) | イベントは、webview の JavaScript ダイアログ (警告、確認、またはプロンプト) が表示されたときに発生します。
[設定](#settings) | CoreWebView2Settings オブジェクトには、実行に関するさまざまな変更可能な設定が含まれています。
[Source](#source) | 現在の最上位レベルのドキュメントの URI。
[SourceChanged](#sourcechanged) | SourceChanged Source プロパティが変更されたときに発生します。
[WebMessageReceived](#webmessagereceived) | このイベントは、IsWebMessageEnabled 設定が設定され、webview 呼び出しの最上位のドキュメントになったときに発生 `window.chrome.webview.postMessage` します。
[WebResourceRequested](#webresourcerequested) | AddWebResourceRequestedFilter で追加された一致する URL とリソースコンテキストフィルターへの HTTP 要求を WebView が実行しているときに発生します。
[WindowCloseRequested](#windowcloserequested) | ウィンドウを閉じるために、WebView 内のコンテンツが要求されたときに発生します。たとえば、close の後に呼び出されます。
[AddHostObjectToScript](#addhostobjecttoscript) | 指定された名前を持つ WebView で実行されているスクリプトに、指定されたホストオブジェクトを追加します。
[AddScriptToExecuteOnDocumentCreatedAsync](#addscripttoexecuteondocumentcreatedasync) | グローバルオブジェクトの作成後、HTML ドキュメントが解析されてから、HTML ドキュメントに含まれている他のスクリプトが実行される前に、指定された JavaScript を実行する必要があるスクリプトのリストに追加します。
[AddWebResourceRequestedFilter](#addwebresourcerequestedfilter) | URI とリソースのコンテキストフィルターを WebResourceRequested イベントに追加します。
[Calldev| Protocolmethodasync](#calldevtoolsprotocolmethodasync) | 非同期の Devて Protocol メソッドを呼び出します。
[CapturePreviewAsync](#capturepreviewasync) | WebView が表示されている画像をキャプチャします。
[すべてのユーティリティ](#executescriptasync) | WebView でレンダリングされた現在のトップレベルドキュメントの javascript パラメーターから JavaScript コードを実行します。
[GetDevToolsProtocolEventReceiver](#getdevtoolsprotocoleventreceiver) | DevTools プロトコルイベントをサブスクライブできる DevTools プロトコルイベントレシーバーを入手します。
[GoBack](#goback) | ナビゲーション履歴で、WebView を前のページに移動します。
[GoForward](#goforward) | WebView をナビゲーション履歴の次のページに移動します。
[検索](#navigate) | 最上位レベルのドキュメントを指定した URI に移動します。
[NavigateToString](#navigatetostring) | 新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。
[Opendevツールウィンドウ](#opendevtoolswindow) | WebView で現在のドキュメントの [DevTools] ウィンドウを開きます。
[PostWebMessageAsJson](#postwebmessageasjson) | 指定した webMessage をこの WebView のトップレベルドキュメントに投稿します。
[PostWebMessageAsString](#postwebmessageasstring) | これは、JavaScript オブジェクトの JSON 文字列表現ではなく、単純な文字列のメッセージを投稿するためのヘルパーです。
[再](#reload) | 現在のページを再読み込みします。
[RemoveHostObjectFromScript](#removehostobjectfromscript) | 名前で指定されたホストオブジェクトを削除して、WebView の JavaScript コードからアクセスできなくなるようにします。
[RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated) | 指定したスクリプト id を使用して、AddScriptToExecuteOnDocumentCreated で追加された対応する JavaScript を削除します。
[RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter) | 以前に WebResourceRequested イベントに追加された、一致する WebResource フィルターを削除します。
[Stop](#stop) | すべてのナビゲーションと保留中のリソースフェッチを停止します。

## Members

#### BrowserProcessId 

WebView をホストしているブラウザープロセスのプロセス id。

> パブリック uint[ブラウザー processid](#browserprocessid)

#### CanGoBack 

ナビゲーション履歴で前のページに移動できる場合は true を返します。

> public bool [CanGoBack](#cangoback)

CanGoBack の値が変更されると、履歴変更イベントが発生します。

#### CanGoForward 

ナビゲーション履歴の次のページに移動できる場合は true を返します。

> public bool [CanGoForward](#cangoforward)

CanGoForward の値が変更されると、履歴変更イベントが発生します。

#### ContainsFullScreenElement 

WebView にフルスクリーン HTML 要素が含まれているかどうかを示します。

> パブリックブール型[Fullscreenelement](#containsfullscreenelement)

#### ContainsFullScreenElementChanged 

"の場合、要素のプロパティが変更されたときに通知します。

> パブリックイベント EventHandler< オブジェクト > [Fullfullscreenelementchanged](#containsfullscreenelementchanged)

これは、WebView 内の HTML 要素が、WebView のサイズまたはフルスクリーンのままであることを意味します。 このイベントは、たとえば、ビデオ要素が全画面表示になっている要求の場合に便利です。 次に、Fullfullscreenelementelementのリスナーが、応答で WebView のサイズを変更できます。

#### ContentLoading 

ContentLoading は、コンテンツが読み込まれる前に発生します。 AddScriptToExecuteOnDocumentCreated ContentLoading によって追加されたスクリプトは、同じページナビゲーション (フラグメントナビゲーションや履歴の推移など) が発生した場合には発生しません。

> パブリックイベントハンドラー< [CoreWebView2ContentLoadingEventArgs](microsoft-web-webview2-core-corewebview2contentloadingeventargs.md)  >  [contentloading](#contentloading)

これは、NavigationStarting イベントと SourceChanged イベントの後で、履歴の変更イベントと Navigationstarting イベントの前に発生します。

#### DocumentTitle 

現在のトップレベルドキュメントのタイトル。

> パブリック文字列[ドキュメントタイトル](#documenttitle)

ドキュメントに明示的なタイトルが含まれていない場合、または空の場合は、ドキュメントの URI と一致しないかもしれない既定値が使用されます。

#### ドキュメントの概要 

イベントは、WebView の DocumentTitle プロパティが変更されたとき、または NavigationCompleted イベントの前または後に発生する可能性があるときに発生します。

> パブリックイベントイベントハンドラー< オブジェクト >[ドキュメント](#documenttitlechanged)の概要

#### FrameNavigationCompleted 

FrameNavigationCompleted イベントが発生するのは、子フレームが完全に読み込まれた (読み込みが開始された) か、エラーが発生して読み込みを停止したときです。

> パブリックイベント EventHandler< [CoreWebView2NavigationCompletedEventArgs](microsoft-web-webview2-core-corewebview2navigationcompletedeventargs.md)  >  [FrameNavigationCompleted](#framenavigationcompleted)

#### FrameNavigationStarting 

FrameNavigationStarting は、WebView の子フレームが別の URI に移動するためのアクセス許可を要求しているときに発生します。

> パブリックイベント EventHandler< [CoreWebView2NavigationStartingEventArgs](microsoft-web-webview2-core-corewebview2navigationstartingeventargs.md)  >  [FrameNavigationStarting](#framenavigationstarting)

これは、リダイレクトの場合にも発生します。

#### 変更履歴 

履歴は、トップレベルのドキュメントのナビゲーション履歴の変更をリッスンします。

> パブリックイベント EventHandler< オブジェクト >[履歴の変更](#historychanged)

履歴の変更を使って、CanGoBack/CanGoForward の値が変更されたかどうかを確認します。 GoBack/GoForward を使用する場合にも変更履歴が発生します。 変更履歴は、SourceChanged と ContentLoading の後に発生します。 履歴変更イベントのイベントハンドラーを追加します。

#### NavigationCompleted 

NavigationCompleted イベントは、WebView が完全に読み込まれたとき (読み込みが開始された場合)、またはエラーが発生して読み込みを停止したときに発生します。

> パブリックイベント EventHandler< [CoreWebView2NavigationCompletedEventArgs](microsoft-web-webview2-core-corewebview2navigationcompletedeventargs.md)  >  [navigationcompleted](#navigationcompleted)

#### NavigationStarting 

NavigationStarting は、WebView メインフレームが別の URI に移動するためのアクセス許可を要求しているときに発生します。

> パブリックイベント EventHandler< [CoreWebView2NavigationStartingEventArgs](microsoft-web-webview2-core-corewebview2navigationstartingeventargs.md)  >  [navigationstarting](#navigationstarting)

これは、リダイレクトの場合にも発生します。

#### NewWindowRequested 

ウィンドウを開くなど、WebView 内のコンテンツが新しいウィンドウを開くように要求したときに発生します。

> パブリックイベント EventHandler< [CoreWebView2NewWindowRequestedEventArgs](microsoft-web-webview2-core-corewebview2newwindowrequestedeventargs.md)  >  [newwindowrequested](#newwindowrequested)

アプリは、開かれたウィンドウと見なされるターゲット webview を渡すことができます。

#### PermissionRequested 

WebView のコンテンツが権限のある一部のリソースにアクセスするためのアクセス許可を要求したときに発生します。

> パブリックイベント EventHandler< [CoreWebView2PermissionRequestedEventArgs](microsoft-web-webview2-core-corewebview2permissionrequestedeventargs.md)  >  [permissionrequested](#permissionrequested)

#### ProcessFailed 

WebView プロセスが予期せず終了した場合、または応答不能になったときに発生します。

> パブリックイベント EventHandler< [CoreWebView2ProcessFailedEventArgs](microsoft-web-webview2-core-corewebview2processfailedeventargs.md)  >  [processfailed](#processfailed)

#### Scriptて開く 

イベントは、webview の JavaScript ダイアログ (警告、確認、またはプロンプト) が表示されたときに発生します。

> パブリックイベント EventHandler< [CoreWebView2ScriptDialogOpeningEventArgs](microsoft-web-webview2-core-corewebview2scriptdialogopeningeventargs.md)  >  [script を開く](#scriptdialogopening)

このイベントは、CoreWebView2Settings Defaultscript Senabled プロパティが false に設定されている場合にのみ発生します。 Scriptdialogs 左中イベントを使うと、ダイアログを非表示にしたり、既定のダイアログをカスタムダイアログに置き換えたりすることができます。

#### 設定 

CoreWebView2Settings オブジェクトには、実行に関するさまざまな変更可能な設定が含まれています。

> パブリック[CoreWebView2Settings](microsoft-web-webview2-core-corewebview2settings.md)の[設定](#settings)

#### Source 

現在の最上位レベルのドキュメントの URI。

> パブリック文字列[ソース](#source)

この値は、別のサイトやフラグメントナビゲーションへの移動などの場合に、SourceChanged イベント発生の一部として変更される可能性があります。 ページの再読み込みや、現在のページと同じ URL を持つ、他の種類のナビゲーションにも同じように表示されます。

#### SourceChanged 

SourceChanged Source プロパティが変更されたときに発生します。

> パブリックイベント EventHandler< [CoreWebView2SourceChangedEventArgs](microsoft-web-webview2-core-corewebview2sourcechangedeventargs.md)  >  [sourcechanged](#sourcechanged)

SourceChanged のサイトまたはフラグメントナビゲーションに移動する場合に発生します。 ページの再読み込みや、現在のページと同じ URL を持つ、他の種類のナビゲーションについては、このような操作は発生しません。 SourceChanged ドキュメントへのナビゲーションのためにコンテンツを読み込む前に、SourceChanged が呼び出されます。 SourceChanged イベントのイベントハンドラーを追加します。

#### WebMessageReceived 

このイベントは、IsWebMessageEnabled 設定が設定され、webview 呼び出しの最上位のドキュメントになったときに発生 `window.chrome.webview.postMessage` します。

> パブリックイベント EventHandler< [CoreWebView2WebMessageReceivedEventArgs](microsoft-web-webview2-core-corewebview2webmessagereceivedeventargs.md)  >  [WebMessageReceived](#webmessagereceived)

PostMessage 関数は、 `void postMessage(object)` JSON 変換でサポートされているオブジェクトです。 PostMessage が呼び出されると、postMessage のオブジェクトパラメーターを JSON 文字列に変換して、CoreWebView2WebMessageReceivedEventHandler セットが呼び出されます。

#### WebResourceRequested 

AddWebResourceRequestedFilter で追加された一致する URL とリソースコンテキストフィルターへの HTTP 要求を WebView が実行しているときに発生します。

> パブリックイベント EventHandler< [CoreWebView2WebResourceRequestedEventArgs](microsoft-web-webview2-core-corewebview2webresourcerequestedeventargs.md)  >  [WebResourceRequested](#webresourcerequested)

イベントを発生させるには、少なくとも1つのフィルターを追加する必要があります。

#### WindowCloseRequested 

ウィンドウを閉じるために、WebView 内のコンテンツが要求されたときに発生します。たとえば、close の後に呼び出されます。

> public イベント EventHandler< object > [WindowCloseRequested](#windowcloserequested)

アプリが適切である場合は、アプリで WebView と関連するアプリのウィンドウを閉じる必要があります。

#### AddHostObjectToScript 

指定された名前を持つ WebView で実行されているスクリプトに、指定されたホストオブジェクトを追加します。

> public void [Addhostobjecttoscript](#addhostobjecttoscript)(文字列名、オブジェクト rawobject)

ホストオブジェクトは、でホストオブジェクトプロキシとして公開され `window.chrome.webview.hostObjects.{name}` ます。 ホストオブジェクトプロキシは保証され、ホストオブジェクトを表すオブジェクトに解決されます。 WebView の JavaScript コードは、appObject に次の方法でアクセスして、appObject の属性とメソッドにアクセスできます。 
```
let app_object = await window.chrome.webview.hostObjects.host_object;
let attr1 = await app_object.attr1;
let result = await app_object.method1(parameters);
```
 単純型、IDispatch、配列はサポートされていますが、ジェネリック IUnknown、VT_DECIMAL、または VT_RECORD variant はサポートされていないことに注意してください。 コールバック関数などのリモート JavaScript オブジェクトは、IDispatch を実装するオブジェクトと共に VT_DISPATCH VARIANT として表されます。 JavaScript のコールバックメソッドは、DISPID の DISPID_VALUE を使って呼び出すことができます。 入れ子になった配列は、最大3レベルまでサポートされます。 参照型での配列はサポートされていません。 VT_EMPTY と VT_NULL は JavaScript に NULL としてマッピングされます。 JavaScript は null で、undefined は VT_EMPTY にマップされます。

さらに、すべてのホストオブジェクトがとして公開され `window.chrome.webview.hostObjects.sync.{name}` ます。 ここでは、ホストオブジェクトが同期ホストオブジェクトプロキシとして公開されています。 これらは、ホストコードが実行されるためのクロスプロセスとの通信を待機している、実行中のスクリプトの実行を待機していて、機能やプロパティへのアクセスを同期することはできません。 これにより、信頼性の問題が発生する可能性があり、上記で説明した promise ベースの非同期 API を使うことをお勧めし `window.chrome.webview.hostObjects.{name}` ます。

同期ホストオブジェクトプロキシと非同期ホストオブジェクトプロキシは、どちらも同じホストオブジェクトをプロキシすることができます。 1つのプロキシによって加えられたリモートの変更は、他のプロキシと同期か非同期かにかかわらず、同じホストオブジェクトの他のプロキシにも反映されます。

JavaScript はネイティブコードへの同期呼び出しでブロックされますが、ネイティブコードは JavaScript にコールバックすることはできません。 これを実行しようとすると、HRESULT_FROM_WIN32 (ERROR_POSSIBLE_DEADLOCK) で失敗します。

ホストオブジェクトプロキシは、すべてのプロパティ get、プロパティセット、メソッド呼び出しを受け取る JavaScript プロキシオブジェクトです。 関数またはオブジェクトプロトタイプの一部であるプロパティまたはメソッドはローカルで実行されます。 さらに、配列内のすべてのプロパティまたはメソッド `chrome.webview.hostObjects.options.forceLocalProperties` もローカルで実行されます。 これは既定で、JavaScript のような、というようなオプションのメソッドが含まれてい `toJSON` `Symbol.toPrimitive` ます。 必要に応じて、この配列に追加することができます。

最善の手段と `chrome.webview.hostObjects.cleanupSome` して、ガベージコレクションのホストオブジェクトプロキシを収集する方法があります。

ホストオブジェクトプロキシには、ローカルで実行される次のメソッドがあります。

* applyHostFunction、getHostProperty、setHostProperty: ホストオブジェクトでメソッドの呼び出し、プロパティの取得、プロパティの設定を実行します。 これらのメソッドを使うと、競合するローカルメソッドまたはプロパティがある場合に、メソッドまたはプロパティを明示的に強制的に実行できます。 たとえば、 `proxy.toString()` はプロキシオブジェクトに対してローカル toString メソッドを実行します。 ただし `proxy.applyHostFunction('toString')` `toString` 、代わりに host プロキシオブジェクトで実行されます。

* getLocalProperty、setLocalProperty: プロパティ get、またはローカルにプロパティを設定します。 これらのメソッドを使うと、ホストオブジェクトプロキシ自体でプロパティを取得または設定することができます。 たとえば、 `proxy.unknownProperty` は、host プロキシオブジェクトから名前が付けられたプロパティを取得し `unknownProperty` ます。 ただし、この `proxy.getLocalProperty('unknownProperty')` プロパティの値は `unknownProperty` プロキシオブジェクト自体で取得されます。

* 同期: 非同期ホストオブジェクトプロキシは、同じホストオブジェクトの同期ホストオブジェクトプロキシの promise を返す同期メソッドを公開します。 たとえば、 `chrome.webview.hostObjects.sample.methodCall()` 非同期ホストオブジェクトプロキシを返します。 代わりに、メソッドを使用して `sync` 同期ホストオブジェクトプロキシを取得できます。 `const syncProxy = await chrome.webview.hostObjects.sample.methodCall().sync()`

* 非同期: 同期ホストオブジェクトプロキシは、同じホストオブジェクトの非同期ホストオブジェクトプロキシをブロックして返す async メソッドを公開します。 たとえば、 `chrome.webview.hostObjects.sync.sample.methodCall()` 同期ホストオブジェクトプロキシを返します。 このブロックに対してメソッドを呼び出す `async` と、同じホストオブジェクトの非同期ホストオブジェクトプロキシが返されます。 `const asyncProxy = chrome.webview.hostObjects.sync.sample.methodCall().async()`

* 次に、非同期ホストオブジェクトプロキシには then メソッドがあります。 これにより、awaitable を行うことができます。 `then` は、host オブジェクトの表現によって解決される promise を返します。 プロキシが JavaScript リテラルを表す場合は、そのリテラルのコピーがローカルに返されます。 プロキシが関数を表す場合は、awaitable 以外のプロキシが返されます。 プロキシがリテラルプロパティと関数プロパティが混在した JavaScript オブジェクトを表している場合、オブジェクトのコピーが、一部のプロパティをホストオブジェクトプロキシとして返します。

その他のすべてのプロパティとメソッドの呼び出し (上記のリモートオブジェクトプロキシメソッド、forceLocalProperties リスト、関数およびオブジェクトプロトタイプのプロパティ以外) は、リモートで実行されます。 非同期ホストオブジェクトプロキシは、メソッドのリモート呼び出しまたはプロパティの取得の非同期完了を表す promise を返します。 この保証は、リモート操作が完了した後に解決され、その約束が、演算の結果値に解決されます。 同期ホストオブジェクトプロキシは、同じように動作しますが、JavaScript の実行をブロックし、リモート操作が完了するまで待機します。

非同期ホストオブジェクトプロキシのプロパティの設定は、若干異なります。 Set はすぐに戻り値として設定されます。 これは JavaScript プロキシオブジェクトの要件です。 プロパティセットが完了するのを非同期的に待つ必要がある場合は、上記のように、setHostProperty メソッドを使って、promise を返します。 同期オブジェクトプロパティセットプロパティは、プロパティが設定されるまで同期的にブロックされます。

#### AddScriptToExecuteOnDocumentCreatedAsync 

グローバルオブジェクトの作成後、HTML ドキュメントが解析されてから、HTML ドキュメントに含まれている他のスクリプトが実行される前に、指定された JavaScript を実行する必要があるスクリプトのリストに追加します。

> パブリック async タスク< 文字列 > [AddScriptToExecuteOnDocumentCreatedAsync](#addscripttoexecuteondocumentcreatedasync)(文字列 javaScript)

##### 返し
[RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)を呼び出したときに渡すことができるスクリプト id を返します。 

挿入されたスクリプトは、RemoveScriptToExecuteOnDocumentCreated で削除されるまで、将来のすべての上位レベルのドキュメントと子フレームのナビゲーションに適用されます。 これは非同期的に適用されるため、今後のナビゲーションでスクリプトを実行する準備ができていることを確認する前に、完了ハンドラーが実行されるまで待機する必要があります。

[サンドボックス](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox)のプロパティまたは[コンテンツセキュリティポリシーの HTTP ヘッダー](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy)によって、HTML ドキュメントに何らかのサンドボックスが含まれている場合は、このスクリプトの実行に影響します。 たとえば、' allow als ' キーワードが設定されていない場合、関数への呼び出し `alert` は無視されます。

#### AddWebResourceRequestedFilter 

URI とリソースのコンテキストフィルターを WebResourceRequested イベントに追加します。

> パブリック void [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)(文字列 Uri、CoreWebView2WebResourceContext resourcecontext)

URI パラメーターは、ワイルドカード文字列 (0 以上、"?": 完全に1つ) にすることができます。 nullptr は、L "" と同じです。 リソースコンテキストフィルターの説明については、「CoreWebView2WebResourceContext enum」を参照してください。

#### Calldev| Protocolmethodasync 

非同期の Devて Protocol メソッドを呼び出します。

> パブリック async タスク< 文字列 > [CalldevparametersAsJson Protocolmethodasync](#calldevtoolsprotocolmethodasync)(文字列 methodName, string)

##### 返し
メソッドの戻りオブジェクトを表す JSON 文字列。

使用できるメソッドの一覧と説明については、「 [Devtools プロトコルビューアー](https://aka.ms/DevToolsProtocolDocs) 」をご覧ください。 MethodName パラメーターは、書式のメソッドの完全な名前です `{domain}.{method}` 。 ParametersAsJson パラメーターは、対応するメソッドのパラメーターを含む JSON 形式の文字列です。 メソッドが非同期的に完了すると、ハンドラーの Invoke メソッドが呼び出されます。 Invoke は、JSON 文字列としてメソッドの戻りオブジェクトを使って呼び出されます。

#### CapturePreviewAsync 

WebView が表示されている画像をキャプチャします。

> パブリック async タスク[CapturePreviewAsync](#capturepreviewasync)(CoreWebView2CapturePreviewImageFormat imageformat、ストリーム画像 estream)

ImageFormat パラメーターを使用して、画像の形式を指定します。 結果のイメージバイナリデータは、指定された imageStream パラメーターに書き込まれます。 CapturePreview がストリームへの書き込みを終了すると、指定された handler パラメーターの Invoke メソッドが呼び出されます。

#### すべてのユーティリティ 

WebView でレンダリングされた現在のトップレベルドキュメントの javascript パラメーターから JavaScript コードを実行します。

> パブリック async タスク< 文字列 > [Executesの](#executescriptasync)テキスト (文字列 javaScript)

##### 返し
指定された JavaScript を実行した結果を表す JSON エンコードされた文字列を返します。 

このメソッドは、指定された JavaScript を非同期的に実行し、指定された JavaScript の結果を返します。 提供された JavaScript の結果が `undefined` 、参照循環を含んでいる場合、または JSON にエンコードできない場合は、文字列 ' null ' が返されます。 指定した JavaScript で呼び出される関数に明示的な戻り値がない場合 `undefined` は、が返されます。 指定した JavaScript が処理されない例外をスローすると、' null ' が返されます。 イベント後にこのメソッドが呼び出された場合 `NavigationStarting` 、指定された JavaScript は、読み込み時に新しいドキュメントで実行され、トリガーされたときと同じタイミングで実行され `ContentLoading` ます。 `ExecuteScript` がに設定されていても動作 `IsScriptEnabled` `FALSE` します。

#### GetDevToolsProtocolEventReceiver 

DevTools プロトコルイベントをサブスクライブできる DevTools プロトコルイベントレシーバーを入手します。

> パブリック CoreWebView2DevToolsProtocolEventReceiver [GetDevToolsProtocolEventReceiver](#getdevtoolsprotocoleventreceiver)(文字列 eventName)

使用できるメソッドの一覧と説明については、「 [Devtools プロトコルビューアー](https://aka.ms/DevToolsProtocolDocs) 」をご覧ください。 MethodName パラメーターは、書式のメソッドの完全な名前です `{domain}.{method}` 。 ParametersAsJson パラメーターは、対応するメソッドのパラメーターを含む JSON 形式の文字列です。 メソッドが非同期的に完了すると、ハンドラーの Invoke メソッドが呼び出されます。 Invoke は、JSON 文字列としてメソッドの戻りオブジェクトを使って呼び出されます。

#### GoBack 

ナビゲーション履歴で、WebView を前のページに移動します。

> パブリック void [GoBack](#goback)()

#### GoForward 

WebView をナビゲーション履歴の次のページに移動します。

> パブリック void [Goforward](#goforward)()

#### 検索 

最上位レベルのドキュメントを指定した URI に移動します。

> パブリック void の[移動](#navigate)(文字列 uri)

詳細については、ナビゲーションイベントを参照してください。 これによってナビゲーションが開始されることに注意してください。この操作が完了すると、対応する NavigationStarting イベントが発生します。

#### NavigateToString 

新しい文書のソース HTML として、htmlContent へのナビゲーションを開始します。

> パブリック void [NavigateToString](#navigatetostring)(文字列 htmlcontent)

HtmlContent パラメーターの文字数は 2 MB 以下でなければなりません。 新しいページの起点は "空白" になります。

#### Opendevツールウィンドウ 

WebView で現在のドキュメントの [DevTools] ウィンドウを開きます。

> パブリック void [Opendevツールウィンドウ](#opendevtoolswindow)()

DevTools ウィンドウが既に開いているときに、何も呼び出されません。

#### PostWebMessageAsJson 

指定した webMessage をこの WebView のトップレベルドキュメントに投稿します。

> パブリック void [Postwebmessageasjson](#postwebmessageasjson)(String webmessageasjson)

最上位のドキュメントのウィンドウには、"." というメッセージイベントが発生します。 このドキュメントの JavaScript は、次のようにしてイベントをサブスクライブし、サブスクライブを取り消すことができます。

```
window.chrome.webview.addEventListener('message', handler)
window.chrome.webview.removeEventListener('message', handler)
```

イベント引数は、のインスタンス `MessageEvent` です。 CoreWebView2Settings の設定は true である必要があります。また、このメソッドは E_INVALIDARG で失敗する可能性があります。 イベント arg の data プロパティは、JSON 文字列として JavaScript オブジェクトに解析された webMessage 文字列のパラメーターです。 イベント arg の source プロパティは、オブジェクトへの参照です `window.chrome.webview` 。 Webview の HTML ドキュメントからホストにメッセージを送信する方法については、「SetWebMessageReceivedEventHandler」を参照してください。 このメッセージは非同期的に送信されます。 メッセージがページに投稿される前にナビゲーションが発生した場合、メッセージは送信されません。

#### PostWebMessageAsString 

これは、JavaScript オブジェクトの JSON 文字列表現ではなく、単純な文字列のメッセージを投稿するためのヘルパーです。

> パブリック void [Postwebmessageasstring](#postwebmessageasstring)(String webmessageasstring)

これは、PostWebMessageAsJson とまったく同じように動作し `window.chrome.webview` ますが、message イベント arg の data プロパティは、webMessageAsString と同じ値を持つ文字列になります。 JSON オブジェクトではなく単純な文字列を使って通信する場合は、PostWebMessageAsJson の代わりに、これを使います。

#### 再 

現在のページを再読み込みします。

> パブリックの void[再読み込み](#reload)()

これは、すべてのナビゲーションイベント (HTTP キャッシュ内のエントリを含む) を含む、現在のトップレベルドキュメントの URI に移動する操作と似ています。 ただし、戻る/forward 履歴は変更されません。

#### RemoveHostObjectFromScript 

名前で指定されたホストオブジェクトを削除して、WebView の JavaScript コードからアクセスできなくなるようにします。

> パブリック void [Removehostobjectfromscript](#removehostobjectfromscript)(文字列名)

新しいアクセスの試行は拒否されますが、そのオブジェクトが WebView の JavaScript コードによって既に取得されている場合は、JavaScript コードはそのオブジェクトに引き続きアクセスできます。 既に削除されているか追加されていない名前に対してこのメソッドを呼び出すと、エラーが発生します。

#### RemoveScriptToExecuteOnDocumentCreated 

指定したスクリプト id を使用して、AddScriptToExecuteOnDocumentCreated で追加された対応する JavaScript を削除します。

> パブリック void [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)(文字列 id)

#### RemoveWebResourceRequestedFilter 

以前に WebResourceRequested イベントに追加された、一致する WebResource フィルターを削除します。

> パブリック void [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)(文字列 Uri、 [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) resourcecontext)

同じフィルターが複数回追加された場合は、削除が有効になるまで何度も削除する必要があります。 追加されていないフィルターの E_INVALIDARG を返します。

#### Stop 

すべてのナビゲーションと保留中のリソースフェッチを停止します。

> パブリック void [Stop](#stop)()

スクリプトは停止されません。
