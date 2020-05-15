---
description: Microsoft Edge WebView 2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32、WPF、および WinForms の Microsoft Edge WebView2 のリリースノート
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/14/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 14030d3dde8c4e68c0790073dc38e5c856e2a091
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654562"
---
# WebView2 SDK のリリースノート  

[WEBVIEW2 SDK][WebView2NuGetGallery]のリリースノート。  

## 0.9.515-プレリリース

[NuGet パッケージ][WebView2NuGetGallery0.9.515-prerelease]|Microsoft Edge の最小バージョン84.0.515.0。

**NuGet パッケージの更新後に、アプリを再コンパイルします。**

* **お知らせ:** WebView2 では、.NET Framework 4.6.2 以降および .NET Core 3.0 以降の Windows フォームと WPF が**プレリリースパッケージ**でサポートされるようになりました
* Wpf の概要[ガイド](./gettingstarted/wpf.md)をチェックアウトして、wpf アプリケーションの構築を開始する (wpf 固有の api 向けの[wpf リファレンス](./reference/wpf/0-9-515-reference-webview2.md))
* Windows フォームの概要[ガイド](./gettingstarted/winforms.md)を使用して windows フォームアプリケーションの構築を開始する、windows フォーム固有の api 用の[windows フォームリファレンス](./reference/winforms/0-9-515-reference-webview2.md)
* CoreWebView2 Api の[.Net 参照](./reference/dotnet/0-9-515-reference-webview2.md)のチェックアウト
* **既知の問題:** 今後のリリースで解決されるこのプレリリースの問題については、以下をご覧ください。
  * **DPI 認識:** 現時点では、WebView2 は DPI に対応していません。 高 DPI モニターで WebView2 を初期化すると、ウィンドウのサイズが変更されるまで、WebView が最初にウィンドウの一部として初期化される既知の問題が発生します。
  * **WPF デザイナー:** このリリースでは、現在、WPF designer はサポートされていません。 テキストエディターで適切な XAML を直接変更することによって、アプリに WebView2 コントロールを配置します。

## 0.9.488

[NuGet パッケージ][WebView2NuGetGallery0.9.488]|Microsoft Edge の最小バージョン84.0.488.0。

**NuGet パッケージの更新後に、アプリを再コンパイルします。**

* **お知らせ:** 今後の Microsoft Edge バージョン83では、evergreen WebView は安定したブラウザーチャネルをターゲットとしていません。 代わりに、現在開発中のインストーラーを使用してチェーンインストールできる、別の一連のバイナリ (ブランドの[Microsoft Edge WebView2 Runtime](./index.md#microsoft-edge-webview2-runtime)) をターゲットとします。 詳細については[、「アプリの配布](./index.md#app-distribution)」をご覧ください。
* **お知らせ:** 次に、2つのパッケージをリリースします。プレリリースパッケージ (試用版) と、安定性の高い Api を備えた安定したリリースパッケージ (使用可能)。 [Microsoft Edge WEBVIEW2 SDK](./index.md#microsoft-edge-webview2-sdk)をチェックアウトして、相違点について確認してください。
* **変更の中断:** API が Windows API の名前付け規則に合わせて調整されるようにするために、次のインターフェイスの名前を更新しました。
  * CORE_WEBVIEW2_ * 接頭文字が * COREWEBVIEW2_ ました。
  * [GetCoreWebView2BrowserVersionInfo](reference/win32/0-9-430/webview2-idl.md#getcorewebview2browserversioninfo)は[GetAvailableCoreWebView2BrowserVersionString](reference/win32/0-9-488/webview2-idl.md#getavailablecorewebview2browserversionstring)になりました
  * [get_BrowserVersionInfo](reference/win32/0-9-430/icorewebview2environment.md#get_browserversioninfo)が[get_BrowserVersionString](reference/win32/0-9-488/icorewebview2environment.md#get_browserversionstring)されました
  * [Addremoteobject](reference/win32/0-9-430/icorewebview2.md#addremoteobject)は[Addhostobjecttoscript](reference/win32/0-9-488/icorewebview2.md#addhostobjecttoscript)になりました
  * [RemoveRemoteObject](reference/win32/0-9-430/icorewebview2.md#removeremoteobject)が[Removehostobjectfromscript](reference/win32/0-9-488/icorewebview2.md#removehostobjectfromscript)になりました
  * chrome. remoteObjects が chrome オブジェクトになります。
* **変更の中断:** AddRemoteObject JS プロキシメソッドも名前が変更されています。
  * getLocal が getLocalProperty に変わりました
  * setLocal が Localproperty になりました
  * getRemote が getHostProperty になりました
  * setRemote は現在は setHostProperty になっています
  * applyRemote が Applyhost関数になりました
* **変更の中断:** [CreateCoreWebView2EnvironmentWithDetails](reference/win32/0-9-488/webview2-idl.md#createcorewebview2environmentwithdetails)は廃止され、 [CreateCoreWebView2EnvironmentWithOptions](reference/win32/0-9-488/webview2-idl.md#createcorewebview2environmentwithoptions)に置き換えられました。  
* [FrameNavigationCompleted](reference/win32/0-9-488/icorewebview2.md#add_framenavigationcompleted)イベントが追加されました。 これで、iframe がナビゲーションを完了するときに、イベントが発生し、ナビゲーションとナビゲーション id の成功が返されます。
* アプリケーションがターゲットとする WebView2 ランタイムのバージョンを判断するために使用できる[ICoreWebView2EnvironmentOptions](reference/win32/0-9-488/ICoreWebView2EnvironmentOptions.md)インターフェイスが追加されました。
* [IsBuiltInErrorPageEnabled](reference/win32/0-9-488/ICoreWebView2Settings.md#get_isbuiltinerrorpageenabled)設定が追加されました。 これで、ナビゲーションエラーとレンダープロセスエラーについて、組み込みのエラーページを有効または無効にすることができます。
* .NET IDispatch の実装をサポートするために、リモートオブジェクトの挿入が更新されました。 ([#113](https://github.com/MicrosoftEdge/WebViewFeedback/issues/113))
* コンテキストメニューからの要求を処理するために、 [Newwindowrequested](reference/win32/0-9-488/icorewebview2.md#add_newwindowrequested)イベントが更新されました。 ([#108](https://github.com/MicrosoftEdge/WebViewFeedback/issues/108))
* Visual ホスティング Api にアクセスできる最初の個別のプレリリースパッケージをリリースしました。 [WebView2APISample](https://github.com/MicrosoftEdge/WebView2Samples)を更新して、新しい実験的な api を追加しました。
  * コンポジションツリーに接続し、WebView 用の入力を提供するために使用される[ICoreWebView2ExperimentalCompositionController](reference/win32/0-9-488/ICoreWebView2ExperimentalCompositionController.md)インターフェイスが追加されました。
  * POINTER_INFO からすべての情報を含む[ICoreWebView2ExperimentalPointerInfo](reference/win32/0-9-488/ICoreWebView2ExperimentalPointerInfo.md)が追加されました。 この値は、Sendpointer 入力に渡され、WebView にポインター入力を挿入します。
  * WebView にマウスカーソルを合わせたときにアプリに通知する[ICoreWebView2ExperimentalCursorChangedEventHandler](reference/win32/0-9-488/ICoreWebView2ExperimentalCursorChangedEventHandler.md)が追加されました。 WebView のテキストボックス上にマウスを移動すると、カーソルが矢印からセレクターに変わります。 CompositionController の cursor プロパティは、WebView のマウスカーソルが現在どのようなものであるかをアプリに通知します。

## 0.9.430

[NuGet パッケージ][WebView2NuGetGallery0.9.430]|Microsoft Edge の最小バージョン82.0.430.0。

**NuGet パッケージの更新後に、アプリを再コンパイルします。**

この SDK は、受け取ったいくつかの機能要求が組み込まれた、Win32 の公式バージョンのベータ版です。 変更によってリリースの数を制限しようとしましたが、一般的な利用可能状況については、ベータ版を使用して、いくつかの重要な変更を1つの方法でまとめています。

* **変更の中断:** 今回のリリースでは、API が Windows API の名前付け規則に合わせて調整されるように、プレフィックス*IWebView2WebView*を*ICoreWebView2*に変更します。 さらに、SDK を UI フレームワークによって使用できるようにするために、ICoreWebView2 を[ICoreWebView2](reference/win32/0-9-430/icorewebview2.md)と[ICoreWebView2Host](reference/win32/0-9-430/icorewebview2host.md)に分割しました。 ICoreWebView2Host は、ウィンドウ化やコンポジションに関連する、サイズ変更、表示、非表示、焦点などの機能をサポートしています。 ICoreWebView2 は、その他のすべての WebView2 機能をサポートしています。 これらの変更の反映の詳細については、 [WebView2APISample](https://github.com/MicrosoftEdge/WebView2Samples)プロジェクトで自分の[プル要求](https://github.com/MicrosoftEdge/WebView2Samples/pull/17)をチェックアウトしてください。
* **変更の中断:**[DocumentStateChanged](reference/win32/0-8-190/iwebview2webview.md#add_documentstatechanged)を3つのコンポーネントに分割します。これには、 [sourcechanged](reference/win32/0-9-430/icorewebview2.md#add_sourcechanged)、 [Contentloading](reference/win32/0-9-430/icorewebview2.md#add_contentloading)、[履歴の変更](reference/win32/0-9-430/icorewebview2.md#add_historychanged)があります。 これで、ソースの URL が変更されると、SourceChanged イベントが発生します。 履歴の状態が変更されると、履歴変更イベントが発生します。 ContentLoading イベントは、新しいドキュメントを読み込むときに、初期スクリプトの前に発生します。
* ARM64 アーキテクチャのサポートが追加されました
* タッチスクリーンデバイスのソフト入力パネル (SIP) サポートを追加しました
* 、、およびのサポートが追加されました。 `Windows Server 2008 R2` `Windows Server 2012/2012 R2` `Windows Server 2016`
* [NotifyParentWindowPositionChanged](reference/win32/0-9-430/icorewebview2host.md#notifyparentwindowpositionchanged)が追加されました。これにより、ウィンドウモードのウィンドウがステータスバーに表示されます。 また、アクセシビリティ機能が動作するためには、ウィンドウなしモードでも実装する必要があります。
* 任意のリモートオブジェクトからページにアクセスできるかどうかをグローバルに制御する[AreRemoteObjectsAllowed](reference/win32/0-9-430/icorewebview2settings.md#get_areremoteobjectsallowed)設定が追加されました。 既定では、AreRemoteObjectsAllowed が有効になっています。 [Addremoteobject](reference/win32/0-9-430/icorewebview2.md#addremoteobject)によって追加されたリモートオブジェクトは、ページからアクセスできます。 AreRemoteObjectsAllowed が無効になっている場合、そのページからオブジェクトにアクセスすることはできません。 変更は次のナビゲーションイベントに適用されます。
* ユーザー [IsZoomControlEnabled](reference/win32/0-9-430/icorewebview2settings.md#get_iszoomcontrolenabled)が、 `ctrl`  +  `+` / `-` または `ctrl` マウスホイールを使用した WebView のズームに影響しないようにするために、IsZoomControlEnabled 設定を追加しました。 この設定が無効になっている場合は、 [put_ZoomFactor](reference/win32/0-9-430/icorewebview2host.md#put_zoomfactor)でズームを設定することもできます。  
* 現在の WebView にのみ適用されるように変更された ZoomFactor。 現在の WebView に対する変更は、同じ元のサイトで発生した他の WebViews には影響しません。 詳細については、 [get_ZoomFactor](reference/win32/0-9-430/icorewebview2host.md#get_zoomfactor)を参照してください。
* WebView 用の Hid ZoomView UI。 ([#95](https://github.com/MicrosoftEdge/WebViewFeedback/issues/95))
* [SetBoundsAndZoomFactor](reference/win32/0-9-430/icorewebview2host.md#setboundsandzoomfactor)が追加されました。 これで、WebView のズーム倍率と境界を同時に設定することができます。
* [WindowCloseRequested](reference/win32/0-9-430/icorewebview2.md#add_windowcloserequested)イベントが追加されました。 詳細については、 [add_WindowCloseRequested](reference/win32/0-9-430/icorewebview2.md#add_windowcloserequested)を参照してください。 ([#119](https://github.com/MicrosoftEdge/WebViewFeedback/issues/119))
* Javascript ダイアログイベント用の beforeunload ダイアログ型のサポートが追加され、列挙型エントリ[CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_BEFOREUNLOAD](reference/win32/0-9-430/icorewebview2.md#core_webview2_script_dialog_kind)追加されました。
* HttpRequestHeaders、 [GetHeader](reference/win32/0-9-430/icorewebview2httpresponseheaders.md#getheader) 、HttpResponseHeaders、 [Get_HasCurrentHeader](reference/win32/0-9-430/icorewebview2httpheaderscollectioniterator.md#get_hascurrentheader)プロパティに[GetHeaders](reference/win32/0-9-430/icorewebview2httprequestheaders.md#getheaders)を httpheaderscollectioniterator に追加しました。
* **変更の中断:** DevToolsProtocolEventReceived の動作が変更されました。 これで、特定の devtools プロトコルイベント用の[DevToolsProtocolEventReceiver](reference/win32/0-9-430/icorewebview2devtoolsprotocoleventreceiver.md)を作成し、remove_DevToolsProtocolEventReceived [add_DevToolsProtocolEventReceived](reference/win32/0-9-430/icorewebview2devtoolsprotocoleventreceiver.md#add_devtoolsprotocoleventreceived)を使って、そのイベントをサブスクライブまたはサブスクライブ解除することができ / [remove_DevToolsProtocolEventReceived](reference/win32/0-9-430/icorewebview2devtoolsprotocoleventreceiver.md#remove_devtoolsprotocoleventreceived)ます。
* **変更の中断:** WebMessageReceivedEventArgs ' [get_WebMessageAsString](reference/win32/0-8-190/iwebview2webmessagereceivedeventargs.md#get_webmessageasstring)プロパティが[Trygetwebmessageasstring](reference/win32/0-9-430/icorewebview2webmessagereceivedeventargs.md#trygetwebmessageasstring)メソッドに変更されました。
* **変更の中断:** AcceleratorKeyPressedEventArgs の[ハンドル](reference/win32/0-8-190/iwebview2acceleratorkeypressedeventargs.md#handle)メソッドが[get_Handled](reference/win32/0-9-430/icorewebview2acceleratorkeypressedeventargs.md#get_handled)プロパティに変更されました。

## 0.8.355

[NuGet パッケージ][WebView2NuGetGallery0.8.355]|Microsoft Edge の最小バージョン80.0.355.0。

**NuGet パッケージの更新後に、アプリを再コンパイルします。**

* WebView2API のリリースのサンプル-SDK の包括的なガイドです。 [ここで](https://github.com/MicrosoftEdge/WebView2Samples/tree/master/WebView2APISample)確認してください。
* 英語以外のすべての言語で IME のサポートが追加されました。 ([#30](https://github.com/MicrosoftEdge/WebViewFeedback/issues/30))
* バグレポートに対応して WebResourceRequested イベントの API サーフェスを更新しました。  作成時にフィルターとイベントを同時に指定することは推奨されなくなりました。  Web リソース要求イベントを作成するには、 [add_WebResourceRequested](reference/win32/0-8-190/iwebview2webview5.md#add_webresourcerequested)を使ってイベントと[AddWebResourceRequestedFilter](reference/win32/0-8-190/iwebview2webview5.md#addwebresourcerequestedfilter)を追加し、フィルターを追加します。  [RemoveWebResourceRequestedFilter](reference/win32/0-8-190/iwebview2webview5.md#removewebresourcerequestedfilter)がフィルターを削除します。  ([#36](https://github.com/MicrosoftEdge/WebViewFeedback/issues/36))([#74](https://github.com/MicrosoftEdge/WebViewFeedback/issues/74))  
* **変更の中断:** フルスクリーン動作が変更されました。 廃止[された Isfullscreenallowed 許可さ](reference/win32/0-8-190/IWebView2Settings.md#get_isfullscreenallowed_deprecated)れました。  既定では、WebView 内の要素 (ビデオなど) が全画面表示に設定されている場合、WebView の境界がいっぱいになります。  要素が全画面モードに入る場合に、アプリで WebView のサイズを変更する方法を指定するには、 [Fullfullscreenelementchanged](reference/win32/0-8-190/IWebView2ContainsFullScreenElementChangedEventHandler.md#interface-iwebview2containsfullscreenelementchangedeventhandler)イベントと[get_ContainsFullScreenElement](reference/win32/0-8-190/iwebview2webview5.md#get_containsfullscreenelement)を使います。  

## 0.8.314

[NuGet パッケージ][WebView2NuGetGallery0.8.314]|Microsoft Edge の最小バージョン80.0.314.0。

**NuGet パッケージの更新後に、アプリを再コンパイルします。**

* Windows 7、Windows 8/8.1 のサポートが追加されました。
* Visual Studio と Visual Studio のコードデバッグサポートを WebView2 に追加しました。 これで、IDE から直接 WebView2 のスクリプトをデバッグできます。 詳細について[は、ここ](/microsoft-edge/hosting/webview2#debugging-webview2)をクリックしてください。  
* 追加さ `Native Object Injection` れると、WebView2 内で実行されているスクリプトは、アプリケーションの Win32 コンポーネントから idispatch オブジェクトを渡し、idispatch オブジェクトのプロパティにアクセスすることができます。  詳細については、 [Addremoteobject](reference/win32/0-8-190/iwebview2webview4.md#addremoteobject)を参照してください。  ([#17](https://github.com/MicrosoftEdge/WebViewFeedback/issues/17))。  
* 追加された `AcceleratorKeyPressed` イベント。  詳細については、 [add_AcceleratorKeyPressed](reference/win32/0-8-190/iwebview2webview4.md#add_acceleratorkeypressed)を参照してください。  ([#57](https://github.com/MicrosoftEdge/WebViewFeedback/issues/57))。  
* 無効 `Context Menus` 。  詳細については[put_AreDefaultContextMenusEnabled](reference/win32/0-8-190/iwebview2settings2.md#put_aredefaultcontextmenusenabled)を参照してください ([#57](https://github.com/MicrosoftEdge/WebViewFeedback/issues/57))。  
* 更新されました `DPI Awareness` 。 これで、WebView の DPI 認識はホストアプリケーションの DPI 認識と同じになります。 注: 元の WebView とは異なる DPI 認識で別のハイブリッドアプリケーションを起動すると、ユーザーデータディレクトリが同じ ([#1](https://github.com/MicrosoftEdge/WebViewFeedback/issues/1)) である場合、新しい WebView は起動されません。
* 更新された `Notification Change Behavior` ため、WebView2 は、WebView 内でホストされている web コンテンツによって求められる通知アクセス許可要求を自動的に拒否します

## 0.8.270  

[NuGet パッケージ][WebView2NuGetGallery0.8.270]|Microsoft Edge の最小バージョン78.0.270.0。  

**NuGet パッケージの更新後に、アプリを再コンパイルします。**

* `DocumentTitleChanged`ドキュメントタイトルの変更 \ ([\ #27][MicrosoftEdgeWebViewFeedbackIssue27]\) を示すイベントが追加されました。  
* `GetWebView2BrowserVersionInfo`API \ ([\ #18][MicrosoftEdgeWebViewFeedbackIssue18]\) を追加しました。  
* 追加された `NewWindowRequested` イベント。  
* `CreateWebView2EnvironmentWithDetails`削除する関数が更新されました `releaseChannelPreference` 。  詳細については、「 [CreateWebView2EnvironmentWithDetails][WebViewsGlobalsCreateWebView2EnvironmentWithDetails]関数」を参照してください。  レジストリと環境変数の上書きは引き続きサポートされます。  既定のチャネルの設定が使用されます。上書きされていない場合。  
    チャネルの検索時に、WebView2 SDK と互換性のない古いチャネルバージョンはスキップします。  
    さらに安定したチャネルを選択して、エンドユーザーに対して最も一貫性のある動作を実現します。  最新のカナリアビルドを使ってテストする場合は、アプリを起動する前に、環境変数を設定するスクリプトを作成する必要があり `WEBVIEW2_RELEASE_CHANNEL_PREFERENCE` `1` ます。  
* Updated `CreateWebView2EnvironmentWithDetails` 関数が指定されていない場合に選択するためのロジックを使用 `userDataFolder` します。  詳細については、「 [CreateWebView2EnvironmentWithDetails][WebViewsGlobalsCreateWebView2EnvironmentWithDetails]関数」を参照してください。  以前に既定の場所を使用していた場合 `userDataFolder` 、新しい SDK に切り替えると、既定値 `userDataFolder` が reset (ホストコードディレクトリ内の新しい場所に設定されます) になり、状態もリセットされます。  
    指定したディレクトリに書き込むためのアクセス許可がホストプロセスにない場合は、 `CreateWebView2EnvironmentWithDetails` 失敗することがあります。  古いユーザーデータディレクトリから新しいディレクトリにデータをコピーすることができます。  

## 0.8.230  

[NuGet パッケージ][WebView2NuGetGallery0.8.230]|Microsoft Edge の最小バージョン77.0.230.0。  

**NuGet パッケージの更新後に、アプリを再コンパイルします。**

* `Stop`すべてのナビゲーションおよび保留中のリソースフェッチを停止するための API を追加しました \ ([\ #28][MicrosoftEdgeWebViewFeedbackIssue28]\)。  
* Nuget パッケージ \ ([\ #22][MicrosoftEdgeWebViewFeedbackIssue22]\) に .tlb ファイルが追加されました。  
* NuGet パッケージ \ ([\ #32][MicrosoftEdgeWebViewFeedbackIssue32]\) のインストーラリストに .net プロジェクトが追加されました。  

## 0.8.190  

[NuGet パッケージ][WebView2NuGetGallery0.8.190]|Microsoft Edge の最小バージョン77.0.190.0。  

**NuGet パッケージの更新後に、アプリを再コンパイルします。**

* `get_AreDevToolsEnabled` / `put_AreDevToolsEnabled` ユーザーが devtools \ ([\ #16][MicrosoftEdgeWebViewFeedbackIssue16]\) を開くことができる場合は、コントロールに追加されます。  
* `get_IsStatusBarEnabled` / `put_IsStatusBarEnabled` ステータスバーが表示されている場合は、コントロールに追加されます (\[#19][MicrosoftEdgeWebViewFeedbackIssue19]\)。  
* `get_CanGoBack` / `GoBack` / `get_CanGoForward` / `GoForward` ナビゲーション履歴を前後に移動するために追加されました。  
* `IWebView2HttpHeadersCollectionIterator` / `IWebView2HttpRequestHeaders` / `IWebView2HttpRequestHeaders` WebView の http ヘッダーを表示および変更するための http ヘッダーの種類 () が追加されました。  
* 64ビットコンピューター \ ([\ #13][MicrosoftEdgeWebViewFeedbackIssue13]\) に32ビット WebView サポートが追加されました。  
* SDK \ ([\ #14][MicrosoftEdgeWebViewFeedbackIssue14]\) に WebView IDL が追加されました。  
* Iid¥ \ * interface id オブジェクト \ ([\ #12][MicrosoftEdgeWebViewFeedbackIssue12]\) をサポートするように lib を追加しました。  
* 追加されるのは、DLL ファイルのパス、リンク、自動コピーを SDK の NuGet ターゲットファイルに追加することです。  
* `window.open`スクリプトでの要求を有効にしました。  

## 0.8.149  

[NuGet パッケージ][WebView2NuGetGallery0.8.149]|Microsoft Edge の最小バージョン76.0.149.0。  

最初の開発者プレビューリリース。  

<!-- image links -->

<!-- Links -->
[MicrosoftEdgeWebViewFeedbackIssue12]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/12 "MicrosoftEdge/WebViewFeedback の問題に関するフィードバックリポジトリ"  
[MicrosoftEdgeWebViewFeedbackIssue13]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/13 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ13"  
[MicrosoftEdgeWebViewFeedbackIssue14]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/14 "MicrosoftEdge/WebViewFeedback の問題に関するフィードバックリポジトリ"  
[MicrosoftEdgeWebViewFeedbackIssue16]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/16 "MicrosoftEdge/WebViewFeedback 問題のフィードバックリポジトリ"  
[MicrosoftEdgeWebViewFeedbackIssue18]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/18 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ18"  
[MicrosoftEdgeWebViewFeedbackIssue19]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/19 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ19"  
[MicrosoftEdgeWebViewFeedbackIssue22]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/22 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ22"  
[MicrosoftEdgeWebViewFeedbackIssue27]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/27 "MicrosoftEdge/WebViewFeedback の問題に関するフィードバックリポジトリ27"  
[MicrosoftEdgeWebViewFeedbackIssue28]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/28 "MicrosoftEdge/WebViewFeedback の問題に関するフィードバックリポジトリ"  
[MicrosoftEdgeWebViewFeedbackIssue32]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/32 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ32"  

[WebView2NuGetGallery]: https://aka.ms/webviewnuget "NuGet ギャラリー |WebView2"  
[WebView2NuGetGallery0.8.149]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.149 "NuGet ギャラリー |WebView2 v 0.8.149"  
[WebView2NuGetGallery0.8.190]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.190 "NuGet ギャラリー |WebView2 v 0.8.190"  
[WebView2NuGetGallery0.8.230]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.230 "NuGet ギャラリー |WebView2 v 0.8.230"  
[WebView2NuGetGallery0.8.270]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.270 "NuGet ギャラリー |WebView2 v 0.8.270"  
[WebView2NuGetGallery0.8.314]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.314 "NuGet ギャラリー |WebView2 v 0.8.314"  
[WebView2NuGetGallery0.8.355]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.355 "NuGet ギャラリー |WebView2 v 0.8.355"  
[WebView2NuGetGallery0.9.430]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.430 "NuGet ギャラリー |WebView2 v 0.9.430"
[WebView2NuGetGallery0.9.488]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.488 "NuGet ギャラリー |WebView2 v 0.9.488"
[WebView2NuGetGallery0.9.515-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.515-prerelease "NuGet ギャラリー |WebView2 v 0.9.515 プレリリース"

[WebViewsGlobalsCreateWebView2EnvironmentWithDetails]: reference/win32/0-8-190/webview2-idl.md#createwebview2environmentwithdetails "WebView Globals-CreateWebView2EnvironmentWithDetails 関数"  
