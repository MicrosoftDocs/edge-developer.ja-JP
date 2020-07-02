---
description: Microsoft Edge WebView 2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32、WPF、および WinForms の Microsoft Edge WebView2 のリリースノート
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 1f229474d4de416f9f6516ce62ab88097f2bc1aa
ms.sourcegitcommit: 288bd2a1bec418a84d1f0bda013c1913886bd269
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "10844419"
---
# WebView2 SDK のリリースノート  

WebView2 チームは、6週間のリズムで[WEBVIEW2 SDK][NuGetGallery]の更新プログラムを提供しています。  製品のお知らせ、API サーフェスの追加と変更、および変更の互換性に関する最新情報については、次の内容を確認してください。  

> [!NOTE]
> NuGet パッケージの更新後に、アプリを再コンパイルします。  

> [!IMPORTANT]
> WebView2 はプレビューであり、.NET Api はに `pre-release package` あります。  

## 0.9.538  

[NuGet パッケージ][NuGetGallery0.9.538]\ |Microsoft Edge の最小バージョン85.0.538.0。  

#### 全般  

*   WebView2 SDK バージョン[0.8.149](#08149)のサポートを削除しています。  WebView チームでは、最新バージョンの WebView2 を使用して最新の状態を維持することをお勧めします。  
*   Microsoft Edge ブラウザーのプロファイルパスが変更された場合 ([#179][GithubMicrosoftedgeWebviewfeedbackIssue179])、グループポリシーが更新されました。  

#### Win32 C/c + +  

*   [ICoreWebView2ExperimentalNewWindowRequestedEventArgs::][ReferenceWin3209538Icorewebview2experimentalnewwindowrequestedeventargsGetWindowfeatures]が呼び出されたときに発生 `window.open()` し、 [ICoreWebView2ExperimentalWindowFeatures][ReferenceWin3209538Icorewebview2experimentalwindowfeatures] \ ([#70][GithubMicrosoftedgeWebviewfeedbackIssue70]\) に関連付けられた場合に発生する、: get_WindowFeatures: を追加しました。  
*   > [!IMPORTANT]
    > **変更の中断**: [CreateCoreWebView2EnvironmentWithDetails][ReferenceWin3209488Webview2IdlCreatecorewebview2environmentwithdetails]は廃止され、 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin3209538Webview2IdlCreatecorewebview2environmentwithoptions]に置き換えられます。  
*   > [!IMPORTANT]
    > **変更の中断**: WebView2 API が Windows api の名前付け規則に合わせて配置されるようにするために、WebView チームは次の名前を更新しました。  
    > *   [AreRemoteObjectsAllowed][ReferenceWin3209488Icorewebview2settingsGetAreremoteobjectsallowed]は、次のように[使用でき][ReferenceWin3209538Icorewebview2settingsGetArehostobjectsallowed]ます。  
*   [Addhostobjecttoscript][ReferenceWin3209538Icorewebview2Addhostobjecttoscript]が更新され、元のホストオブジェクトシリアライザーのマーカーがプロキシオブジェクトに設定され、JavaScript コールバックのパラメーターとしてシリアル化された ([#148][GithubMicrosoftedgeWebviewfeedbackIssue148]\)  

#### .NET (0.9.538 プレリリース版)  

*   WinForms と WPF WebView2API のサンプルをリリースしました。これは WebView2 SDK の包括的なガイドです。  詳細については、「[サンプルリポジトリ][GithubMicrosoftedgeWebview2samplesMain]」を参照してください。  
*   ビジュアルホスト機能と window 機能の[実験的な api][ConceptsVersioningExperimentalApis]のサポートが追加されました。  
*   > [!IMPORTANT]
    > **変更の中断**: 次の保留は IDisposable: [scriptWebResourceRequested 始値][ReferenceDotnet09538MicrosoftWebWebview2CoreCorewebview2Scriptdialogopening]、 [newwindowrequested][ReferenceDotnet09538MicrosoftWebWebview2CoreCorewebview2Newwindowrequested]、 [WebResourceRequested][ReferenceDotnet09538MicrosoftWebWebview2CoreCorewebview2Webresourcerequested]、および[permissionrequested][ReferenceDotnet09538MicrosoftWebWebview2CoreCorewebview2Permissionrequested]実装するようになりました。  
*   [GetCompareBrowserVersions の文字列][ReferenceDotnet09538MicrosoftWebWebview2CoreCorewebview2environmentGetavailablebrowserversionstring]と[CompareBrowserVersions][ReferenceDotnet09538MicrosoftWebWebview2CoreCorewebview2environmentComparebrowserversions]を[CoreWebView2Environment][ReferenceDotnet09538MicrosoftWebWebview2CoreCorewebview2environment]の静的として追加しました。  

## 0.9.515-プレリリース  

[NuGet パッケージ][NuGetGallery0.9.515-prerelease]\ |Microsoft Edge の最小バージョン84.0.515.0。  

*   > [!IMPORTANT]
    > **アナウンスメント**: WebView2 では、.net Framework 4.6.2 以降および .net Core 3.0 以降の Windows フォームと WPF が**プレリリースパッケージ**でサポートされるようになりました。  
*   Wpf アプリケーションの構築および WPF 固有の Api 用の WebView2 [Wpf 参照][ReferenceWpf09515Reference]について詳しくは、「 [wpf の概要][GettingstartedWpf]」をご覧ください。  
*   Windows フォームアプリケーションの構築および windows フォーム固有の Api 用の WebView2 [Windows フォームリファレンス][ReferenceWinforms09515Reference]の詳細については、「 [Windows フォームの概要][GettingstartedWinforms]」を参照してください。  
*   CoreWebView2 Api の詳細については、「 [.Net リファレンス][ReferenceDotnet09515Reference]」を参照してください。  
*   > [!CAUTION]
    > **既知の問題**: WebView チームは、今後のリリースで解決されるプレリリースの一部の問題を認識しています。  
    > *   **Dpi 認識**: WPF の WebView2 は現在 DPI に対応していません。  高 DPI モニターで WebView2 を初期化すると、ウィンドウのサイズが変更されるまで、WebView が最初にウィンドウの一部として初期化される既知の問題が発生します。  
    > *   **Wpf デザイナー**: wpf デザイナーは現在サポートされていません。  テキストエディターで適切な XAML を直接変更することによって、アプリに WebView2 コントロールを追加します。  

## 0.9.488  

[NuGet パッケージ][NuGetGallery0.9.488]\ |Microsoft Edge の最小バージョン84.0.488.0。  

*   > [!IMPORTANT]
    > **お知らせ**: 予定されている Microsoft Edge バージョン83以降、evergreen WebView は、安定したブラウザーチャネルをターゲットとしていません。  代わりに、別のバイナリセットのブランド[Evergreen WebView2 ランタイム][ConceptsDistributionEvergreenMode]をターゲットにします。これは、WebView チームが現在開発しているインストーラーを使ってインストールすることができます。  詳しくは、「[アプリの配布][ConceptsDistribution]」をご覧ください。  
*   > [!IMPORTANT]
    > **お知らせ**: 前進すると、WebView チームは2つのパッケージをリリースします。プレリリースパッケージ (\) と、安定した api を含む安定したリリースパッケージ (お客様の信頼できる)。  相違点については、「[ブラウザーのバージョンと WebView2 につい][ConceptsVersioning]て」を参照してください。  
*   > [!IMPORTANT]
    > **変更の中断**: WebView2 API が Windows api の名前付け規則に合わせて配置されるようにするために、WebView チームは次のインターフェイスの名前を更新しました。  
    > *   `CORE_WEBVIEW2_*` プレフィックスは現在 `COREWEBVIEW2_*` です。  
    > *   [GetCoreWebView2BrowserVersionInfo][ReferenceWin3209430Webview2IdlGetcorewebview2browserversioninfo]は[GetAvailableCoreWebView2BrowserVersionString][ReferenceWin3209488Webview2IdlGetavailablecorewebview2browserversionstring]になりました。  
    > *   [get_BrowserVersionInfo][ReferenceWin3209430Icorewebview2environmentGetBrowserversioninfo]が[get_BrowserVersionString][ReferenceWin3209488Icorewebview2environmentGetBrowserversionstring]ました。  
    > *   [Addremoteobject][ReferenceWin3209430Icorewebview2Addremoteobject]は[Addhostobjecttoscript][ReferenceWin3209488Icorewebview2Addhostobjecttoscript]になりました。  
    > *   [RemoveRemoteObject][ReferenceWin3209430Icorewebview2Removeremoteobject]が[Removehostobjectfromscript][ReferenceWin3209488Icorewebview2Removehostobjectfromscript]になりました。  
    > *   `chrome.webview.remoteObjects` は現在 `chrome.webview.hostObjects` です。  
*   > [!IMPORTANT]
    > **変更の中断**: `AddRemoteObject` JS プロキシメソッドも名前が変更されます。  
    > *   `getLocal` は現在 `getLocalProperty` です。  
    > *   `setLocal` は現在 `setLocalProperty` です。  
    > *   `getRemote` は現在 `getHostProperty` です。  
    > *   `setRemote` は現在 `setHostProperty` です。  
    > *   `applyRemote` は現在 `applyHostFunction` です。  
*   > [!IMPORTANT]
    > **変更の中断**: [CreateCoreWebView2EnvironmentWithDetails][ReferenceWin3209488Webview2IdlCreatecorewebview2environmentwithdetails]は廃止され、 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin3209488Webview2IdlCreatecorewebview2environmentwithoptions]に置き換えられます。  
*   [FrameNavigationCompleted][ReferenceWin3209488Icorewebview2AddFramenavigationcompleted]イベントが追加されました。  これで、iframe がナビゲーションを完了するときに、イベントが発生し、ナビゲーションとナビゲーション id の成功が返されます。  
*   アプリケーションがターゲットとする WebView2 ランタイムのバージョンを判断するために使用される[ICoreWebView2EnvironmentOptions][ReferenceWin3209488Icorewebview2environmentoptions]インターフェイスが追加されました。  
*   [IsBuiltInErrorPageEnabled][ReferenceWin3209488Icorewebview2settingsGetIsbuiltinerrorpageenabled]設定が追加されました。  これで、ナビゲーションエラーとレンダープロセスエラーについて、組み込みのエラーページを有効または無効にすることができます。  
*   .NET IDispatch の実装をサポートするために、リモートオブジェクトの挿入が更新されました \ ([#113][GithubMicrosoftedgeWebviewfeedbackIssue113]\)。  
*   コンテキストメニュー \ ([#108][GithubMicrosoftedgeWebviewfeedbackIssue108]\) からの要求を処理するために、 [newwindowrequested][ReferenceWin3209488Icorewebview2AddNewwindowrequested]イベントが更新されました。  
*   Visual ホスティング Api にアクセスできる、最初の個別の WebView2 プレリリースパッケージがリリースされました。  WebView チーム[が更新され、][GithubMicrosoftedgeWebview2samplesMain]新しい実験的な api が追加されました。  
    *   コンポジションツリーに接続し、WebView 用の入力を提供するために使用される[ICoreWebView2ExperimentalCompositionController][ReferenceWin3209488Icorewebview2experimentalcompositioncontroller]インターフェイスが追加されました。  
    *   からすべての情報を含む[ICoreWebView2ExperimentalPointerInfo][ReferenceWin3209488Icorewebview2experimentalpointerinfo]が追加されました `POINTER_INFO` 。  この値は、Sendpointer 入力に渡され、WebView にポインター入力を挿入します。  
    *   WebView にマウスカーソルを合わせたときにアプリに通知する[ICoreWebView2ExperimentalCursorChangedEventHandler][ReferenceWin3209488Icorewebview2experimentalcursorchangedeventhandler]が追加されました。  WebView のテキストボックス上にマウスを移動すると、カーソルが矢印からセレクターに変わります。  上の cursor プロパティは、 `CompositionController` 現在、WebView のマウスカーソルがどのようなものであるかをアプリに通知します。  

## 0.9.430  

[NuGet パッケージ][NuGetGallery0.9.430]\ |Microsoft Edge の最小バージョン82.0.430.0。  

WebView2 SDK は、フィードバックからいくつかの機能要求を取り入れた、Win32 の公式バージョンである Win32 C++ ベータバージョンです。  WebView チームは、変更によってリリースの数を制限しようとしていますが、一般的な可用性が考慮されています。ベータ版は、いくつかの重要な変更を1つの go で取り入れています。  

*   > [!IMPORTANT]
    > **変更の中断**: 最終リリースでは、WebView2 Api が Windows api の名前付け規則に合わせて配置されるように、WebView チームはプレフィックス*IWebView2WebView*を*ICoreWebView2*に変更します。  さらに、WebView2 SDK を UI フレームワークから利用するために、WebView チームは `ICoreWebView2` [ICoreWebView2][ReferenceWin3209430Icorewebview2]と[ICoreWebView2Host][ReferenceWin3209430Icorewebview2host]に分かれています。  `ICoreWebView2Host` ウィンドウのサイズ変更、表示/非表示、フォーカスなど、ウィンドウとコンポジションに関連する機能をサポートします。  ICoreWebView2 は、その他のすべての WebView2 機能をサポートしています。  変更の反映の詳細については、「WebView2 [Apisample][GithubMicrosoftedgeWebview2samplesMain]プロジェクトの[pull 要求][GithubMicrosoftedgeWebview2samplesPr17]」を参照してください。  
*   > [!IMPORTANT]
    > **変更の中断**: [sourcechanged][ReferenceWin3209430Icorewebview2AddSourcechanged]、 [Contentloading][ReferenceWin3209430Icorewebview2AddContentloading]、[履歴が変更された][ReferenceWin3209430Icorewebview2AddHistorychanged] [DocumentStateChanged][ReferenceWin3208190Iwebview2webviewAddDocumentstatechanged]を3つのコンポーネントに分割します。  これで、ソースの URL が変更されたときに、 `SourceChanged` イベントが発生します。  履歴の状態が変更されると、履歴変更イベントが発生します。  `ContentLoading`新しいドキュメントを読み込むときに、最初のスクリプトの前にイベントが発生します。  
*   ARM64 アーキテクチャのサポートが追加されました。  
*   タッチスクリーンデバイスのソフト入力パネル \ (SIP) サポートを追加しました。  
*   Windows server 2008 R2、Windows Server 2012、Windows Server 2012 R2、Windows Server 2016 のサポートが追加されました。  
*   [NotifyParentWindowPositionChanged][ReferenceWin3209430Icorewebview2hostNotifyparentwindowpositionchanged]が追加されました。これにより、ウィンドウモードのウィンドウがステータスバーに表示されます。  アクセシビリティ機能が動作するためには、変更をウィンドウなしモードでも実装する必要があります。  
*   任意のリモートオブジェクトからページにアクセスできるかどうかをグローバル制御するための[AreRemoteObjectsAllowed][ReferenceWin3209430Icorewebview2settingsGetAreremoteobjectsallowed]設定が追加されました。  既定で `AreRemoteObjectsAllowed` は、有効になります。 [Addremoteobject][ReferenceWin3209430Icorewebview2Addremoteobject]によって追加されたリモートオブジェクトは、ページからアクセスできます。  無効にすると `AreRemoteObjectsAllowed` 、そのオブジェクトはページからアクセスできません。  変更は次のナビゲーションイベントに適用されます。  
*   [IsZoomControlEnabled][ReferenceWin3209430Icorewebview2settingsGetIszoomcontrolenabled]設定を追加して、ユーザーが WebView `ctrl` + `+` と `ctrl` + `-` \ (または `ctrl` + マウスホイール \) のズームに影響しないようにします。  設定を無効にすると、 [put_ZoomFactor][ReferenceWin3209430Icorewebview2hostPutZoomfactor]を使用してズームを設定することができます。  
*   現在の WebView にのみ適用されるように変更された ZoomFactor。  現在の WebView のズームの変更は、元のサイトに移動した他の WebViews には影響しません。  詳細については、「 [get_ZoomFactor][ReferenceWin3209430Icorewebview2hostGetZoomfactor]」を参照してください。  
*   WebView \ ([#95][GithubMicrosoftedgeWebviewfeedbackIssue95]\) の HID ZoomView UI。  
*   [SetBoundsAndZoomFactor][ReferenceWin3209430Icorewebview2hostSetboundsandzoomfactor]が追加されました。  この時点で、WebView のズーム率と境界を同時に設定できます。  
*   [WindowCloseRequested][ReferenceWin3209430Icorewebview2AddWindowcloserequested]イベントが追加されました。  詳細については[add_WindowCloseRequested][ReferenceWin3209430Icorewebview2AddWindowcloserequested]を参照してください ([#119][GithubMicrosoftedgeWebviewfeedbackIssue119])。  
*   Javascript ダイアログイベント用の beforeunload ダイアログ型のサポートが追加され、列挙型エントリ[CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_BEFOREUNLOAD][ReferenceWin3209430Icorewebview2CoreWebview2ScriptDialogKind]追加されました。  
*   HttpRequestHeaders、 [GetHeader][ReferenceWin3209430Icorewebview2httpresponseheadersGetheader] 、HttpResponseHeaders、 [Get_HasCurrentHeader][ReferenceWin3209430Icorewebview2httpheaderscollectioniteratorGetHascurrentheader]プロパティに[GetHeaders][ReferenceWin3209430Icorewebview2httprequestheadersGetheaders]を httpheaderscollectioniterator に追加しました。  
*   > [!IMPORTANT]
    > **変更の中断**: DevToolsProtocolEventReceived の動作が変更されました。  次に、 [add_DevToolsProtocolEventReceived][ReferenceWin3209430Icorewebview2devtoolsprotocoleventreceiverAddDevtoolsprotocoleventreceived]remove_DevToolsProtocolEventReceived を使用して、特定の devtools プロトコルイベント用の[DevToolsProtocolEventReceiver][ReferenceWin3209430Icorewebview2devtoolsprotocoleventreceiver]を作成し、そのイベントをサブスクライブまたはサブスクライブ解除することができ / [remove_DevToolsProtocolEventReceived][ReferenceWin3209430Icorewebview2devtoolsprotocoleventreceiverRemoveDevtoolsprotocoleventreceived]ます。
*   > [!IMPORTANT]
    > **変更の中断**: WebMessageReceivedEventArgs ' [Get_WebMessageAsString][ReferenceWin3208190Iwebview2webmessagereceivedeventargsGetWebmessageasstring]プロパティが[Trygetwebmessageasstring][ReferenceWin3209430Icorewebview2webmessagereceivedeventargsTrygetwebmessageasstring]メソッドに変更されました。  
*   > [!IMPORTANT]
    > **変更の中断**: AcceleratorKeyPressedEventArgs ' [Handle][ReferenceWin3208190Iwebview2acceleratorkeypressedeventargsHandle]メソッドを[get_Handled][ReferenceWin3209430Icorewebview2acceleratorkeypressedeventargsGetHandled]プロパティに変更しました。  

## 0.8.355

[NuGet パッケージ][NuGetGallery0.8.355]\ |Microsoft Edge の最小バージョン80.0.355.0。

*   WebView2 SDK の包括的なガイドである WebView2API サンプルをリリースしました。  詳細については、「 [Apisample][GithubMicrosoftedgeWebview2samplesApisample]を参照してください。  
*   英語 \ ([#30][GithubMicrosoftedgeWebviewfeedbackIssue30]\) 以外のすべての言語で IME のサポートが追加されました。  
*   バグレポートに対応して WebResourceRequested イベントの API サーフェスを更新しました。  作成時にフィルターとイベントを同時に指定することは推奨されなくなりました。  Web リソース要求イベントを作成するには、 [add_WebResourceRequested][ReferenceWin3208190Iwebview2webview5AddWebresourcerequested]を使ってイベントと[AddWebResourceRequestedFilter][ReferenceWin3208190Iwebview2webview5Addwebresourcerequestedfilter]を追加し、フィルターを追加します。  [RemoveWebResourceRequestedFilter][ReferenceWin3208190Iwebview2webview5Removewebresourcerequestedfilter]はフィルター \ ([#36][GithubMicrosoftedgeWebviewfeedbackIssue36]\) \ ([#74][GithubMicrosoftedgeWebviewfeedbackIssue74]\) を削除します。  
*   > [!IMPORTANT]
    > **変更の中断**: 全画面の動作が変更されました。  廃止[された Isfullscreenallowed 許可さ][ReferenceWin3208190Iwebview2settingsGetIsfullscreenallowedDeprecated]れました。  既定では、WebView \ (ビデオなど) の要素が全画面表示に設定されている場合、WebView の境界がいっぱいになります。  要素が全画面モードに入る場合に、アプリで WebView のサイズを変更する方法を指定するには、 [Fullfullscreenelementchanged][ReferenceWin3208190Iwebview2containsfullscreenelementchangedeventhandler]イベントと[get_ContainsFullScreenElement][ReferenceWin3208190Iwebview2webview5GetContainsfullscreenelement]を使います。  

## 0.8.314  

[NuGet パッケージ][NuGetGallery0.8.314]\ |Microsoft Edge の最小バージョン80.0.314.0。  

*   Windows 7、Windows 8、Windows 8.1 のサポートが追加されました。  
*   Visual Studio と Visual Studio のコードデバッグサポートを WebView2 に追加しました。  次に、IDE から直接 WebView2 のスクリプトをデバッグします。  詳細については、「 [WebView2 コントロールを使用して開発するときにデバッグする方法][HowtoDebug]」を参照してください。  
*   追加されました `Native Object Injection` 。これにより、WebView2 内で実行されるスクリプトは、アプリケーションの Win32 コンポーネントから idispatch オブジェクトにアクセスし、idispatch オブジェクトのプロパティにアクセスすることができます。  詳細については、「 [Addremoteobject][ReferenceWin3208190Iwebview2webview4Addremoteobject] \ ([#17][GithubMicrosoftedgeWebviewfeedbackIssue17]\)」を参照してください。  
*   追加された `AcceleratorKeyPressed` イベント。  詳細については、「 [add_AcceleratorKeyPressed][ReferenceWin3208190Iwebview2webview4AddAcceleratorkeypressed] \ ([#57][GithubMicrosoftedgeWebviewfeedbackIssue57]\)」を参照してください。  
*   無効 `Context Menus` 。  詳細については、「 [put_AreDefaultContextMenusEnabled][ReferenceWin3208190Iwebview2settings2PutAredefaultcontextmenusenabled] \ ([#57][GithubMicrosoftedgeWebviewfeedbackIssue57]\)」を参照してください。  
*   更新されました `DPI Awareness` 。  これで、WebView の DPI 認識は、ホストアプリケーションの DPI 認識と同じになります。  
    
    > [!NOTE] 
    > 別のハイブリッドアプリケーションを起動したときに、元の WebView と異なる DPI 認識が適用されている場合は、ユーザーデータディレクトリが同じ ([#1][GithubMicrosoftedgeWebviewfeedbackIssue1]) である場合、新しい WebView は起動されません。  
    
*   更新された `Notification Change Behavior` ため、WebView2 は、WebView 内でホストされている web コンテンツによって求められる通知アクセス許可要求を自動的に拒否します  

## 0.8.270  

[NuGet パッケージ][NuGetGallery0.8.270]\ |Microsoft Edge の最小バージョン78.0.270.0。  

*   `DocumentTitleChanged`ドキュメントタイトルの変更 \ ([\ #27][GithubMicrosoftedgeWebviewfeedbackIssue27]\) を示すイベントが追加されました。  
*   `GetWebView2BrowserVersionInfo`API \ ([\ #18][GithubMicrosoftedgeWebviewfeedbackIssue18]\) を追加しました。  
*   追加された `NewWindowRequested` イベント。  
*   `CreateWebView2EnvironmentWithDetails`削除する関数が更新されました `releaseChannelPreference` 。  詳細については、「 [CreateWebView2EnvironmentWithDetails][ReferenceWin3208190WebView2IdlCreatewebview2environmentwithdetails]関数」を参照してください。  レジストリと環境変数の上書きは引き続きサポートされます。  既定のチャネルの設定が使用されます。上書きされていない場合。  
    チャネルの検索時に、WebView チームは、WebView2 SDK と互換性のない古いチャネルバージョンをスキップします。  
    WebView チームは、より安定したチャネルを選択して、エンドユーザーに対して最も一貫性のある動作を実現します。  最新のカナリアビルドを使ってテストする場合は、アプリを起動する `WEBVIEW2_RELEASE_CHANNEL_PREFERENCE` 前に環境変数を設定するスクリプトを作成する必要があり `1` ます。  
*   `CreateWebView2EnvironmentWithDetails` `userDataFolder` 指定されていない場合に選択するためのロジックで関数が更新されました。  詳細については、「 [CreateWebView2EnvironmentWithDetails][ReferenceWin3208190WebView2IdlCreatewebview2environmentwithdetails]関数」を参照してください。  以前に既定の場所を使用していた場合 `userDataFolder` 、新しい SDK に切り替えると、既定値 `userDataFolder` が reset (ホストコードディレクトリ内の新しい場所に設定されます) になり、状態もリセットされます。  
    指定したディレクトリに書き込むためのアクセス許可がホストプロセスにない場合、この `CreateWebView2EnvironmentWithDetails` 関数は失敗することがあります。  古いユーザーデータディレクトリから新しいディレクトリにデータをコピーすることができます。  

## 0.8.230  

[NuGet パッケージ][NuGetGallery0.8.230]\ |Microsoft Edge の最小バージョン77.0.230.0。  

*   `Stop`すべてのナビゲーションおよび保留中のリソースフェッチを停止するための API を追加しました \ ([\ #28][GithubMicrosoftedgeWebviewfeedbackIssue28]\)。  
*   Nuget パッケージ \ ([\ #22][GithubMicrosoftedgeWebviewfeedbackIssue22]\) に .tlb ファイルが追加されました。  
*   NuGet パッケージ \ ([\ #32][GithubMicrosoftedgeWebviewfeedbackIssue32]\) のインストーラリストに .net プロジェクトが追加されました。  

## 0.8.190  

[NuGet パッケージ][NuGetGallery0.8.190]\ |Microsoft Edge の最小バージョン77.0.190.0。  

*   `get_AreDevToolsEnabled` / `put_AreDevToolsEnabled` ユーザーが devtools \ ([\ #16][GithubMicrosoftedgeWebviewfeedbackIssue16]\) を開くことができる場合は、コントロールに追加されます。  
*   `get_IsStatusBarEnabled` / `put_IsStatusBarEnabled` ステータスバーが表示されている場合は、コントロールに追加されます (\[#19][GithubMicrosoftedgeWebviewfeedbackIssue19]\)。  
*   `get_CanGoBack` / `GoBack` / `get_CanGoForward` / `GoForward` ナビゲーション履歴を前後に移動するために追加されました。  
*   `IWebView2HttpHeadersCollectionIterator` / `IWebView2HttpRequestHeaders` / `IWebView2HttpRequestHeaders` WebView の http ヘッダーを表示および変更するための http ヘッダーの種類 () が追加されました。  
*   64ビットコンピューター \ ([\ #13][GithubMicrosoftedgeWebviewfeedbackIssue13]\) に32ビット WebView サポートが追加されました。  
*   SDK \ ([\ #14][GithubMicrosoftedgeWebviewfeedbackIssue14]\) に WebView IDL が追加されました。  
*   Iid¥ \ * interface id オブジェクト \ ([\ #12][GithubMicrosoftedgeWebviewfeedbackIssue12]\) をサポートするように lib を追加しました。  
*   追加されるのは、DLL ファイルのパス、リンク、自動コピーを SDK の NuGet ターゲットファイルに追加することです。  
*   `window.open`スクリプトでの要求を有効にしました。  

## 0.8.149  

[NuGet パッケージ][NuGetGallery0.8.149]\ |Microsoft Edge の最小バージョン76.0.149.0。  

最初の開発者プレビューリリース。  

<!-- Links -->  

[ConceptsDistribution]: ./concepts/distribution.md "WebView2 を使用したアプリケーションの配布 |Microsoft ドキュメント"  
[ConceptsDistributionEvergreenMode]: ./concepts/distribution.md#evergreen-distribution-mode "Evergreen 配布モード-WebView2 を使用したアプリケーションの配布 |Microsoft ドキュメント"  
[ConceptsVersioning]: ./concepts/versioning.md "ブラウザーのバージョンと WebView2 についてMicrosoft ドキュメント"  
[ConceptsVersioningExperimentalApis]: ./concepts/versioning.md#experimental-apis "実験的 Api-ブラウザーのバージョンと WebView2 についてMicrosoft ドキュメント"  
[GettingstartedWinforms]: ./gettingstarted/winforms.md "Windows Forms アプリでの WebView2 の概要 |Microsoft ドキュメント"  
[GettingstartedWpf]: ./gettingstarted/wpf.md "WPF での WebView2 の概要 |Microsoft ドキュメント"  
[HowtoDebug]: ./howto/debug.md "WebView2 コントロールを使用して開発を行うときのデバッグ方法 |Microsoft ドキュメント"  

[ReferenceWin3208190Iwebview2acceleratorkeypressedeventargsHandle]: ./reference/win32/0-8-190/iwebview2acceleratorkeypressedeventargs.md#handle "ハンドル-インターフェイスの IWebView2AcceleratorKeyPressedEventArgs |Microsoft ドキュメント"  
[ReferenceWin3208190Iwebview2containsfullscreenelementchangedeventhandler]: ./reference/win32/0-8-190/iwebview2containsfullscreenelementchangedeventhandler.md "インターフェイス IWebView2ContainsFullScreenElementChangedEventHandler |Microsoft ドキュメント"  
[ReferenceWin3208190Iwebview2settings2PutAredefaultcontextmenusenabled]: ./reference/win32/0-8-190/iwebview2settings2.md#put_aredefaultcontextmenusenabled "put_AreDefaultContextMenusEnabled インターフェイス IWebView2Settings2 |Microsoft ドキュメント"  
[ReferenceWin3208190Iwebview2settingsGetIsfullscreenallowedDeprecated]: ./reference/win32/0-8-190/iwebview2settings.md#get_isfullscreenallowed_deprecated "get_IsFullscreenAllowed_deprecated インターフェイス IWebView2Settings |Microsoft ドキュメント"  
[ReferenceWin3208190Iwebview2webmessagereceivedeventargsGetWebmessageasstring]: ./reference/win32/0-8-190/iwebview2webmessagereceivedeventargs.md#get_webmessageasstring "get_WebMessageAsString インターフェイス IWebView2WebMessageReceivedEventArgs |Microsoft ドキュメント"  
[ReferenceWin3208190Iwebview2webview4AddAcceleratorkeypressed]: ./reference/win32/0-8-190/iwebview2webview4.md#add_acceleratorkeypressed "add_AcceleratorKeyPressed インターフェイス IWebView2WebView4 |Microsoft ドキュメント"  
[ReferenceWin3208190Iwebview2webviewAddDocumentstatechanged]: ./reference/win32/0-8-190/iwebview2webview.md#add_documentstatechanged "add_DocumentStateChanged インターフェイス IWebView2WebView |Microsoft ドキュメント"  
[ReferenceWin3208190Iwebview2webview4Addremoteobject]: ./reference/win32/0-8-190/iwebview2webview4.md#addremoteobject "AddRemoteObject-interface IWebView2WebView4 |Microsoft ドキュメント"  
[ReferenceWin3208190Iwebview2webview5AddWebresourcerequested]: ./reference/win32/0-8-190/iwebview2webview5.md#add_webresourcerequested "add_WebResourceRequested インターフェイス IWebView2WebView5 |Microsoft ドキュメント"  
[ReferenceWin3208190Iwebview2webview5Addwebresourcerequestedfilter]: ./reference/win32/0-8-190/iwebview2webview5.md#addwebresourcerequestedfilter "AddWebResourceRequestedFilter-インターフェイス IWebView2WebView5 |Microsoft ドキュメント"  
[ReferenceWin3208190Iwebview2webview5GetContainsfullscreenelement]: ./reference/win32/0-8-190/iwebview2webview5.md#get_containsfullscreenelement "get_ContainsFullScreenElement インターフェイス IWebView2WebView5 |Microsoft ドキュメント"  
[ReferenceWin3208190Iwebview2webview5Removewebresourcerequestedfilter]: ./reference/win32/0-8-190/iwebview2webview5.md#removewebresourcerequestedfilter "RemoveWebResourceRequestedFilter-インターフェイス IWebView2WebView5 |Microsoft ドキュメント"  
[ReferenceWin3208190WebView2IdlCreatewebview2environmentwithdetails]:  ./reference/win32/0-8-190/webview2-idl.md#createwebview2environmentwithdetails "CreateWebView2EnvironmentWithDetails-Globals |Microsoft ドキュメント"  

[ReferenceWin3209430Icorewebview2]: ./reference/win32/0-9-430/icorewebview2.md "インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2acceleratorkeypressedeventargsGetHandled]: ./reference/win32/0-9-430/icorewebview2acceleratorkeypressedeventargs.md#get_handled "get_Handled インターフェイス ICoreWebView2AcceleratorKeyPressedEventArgs |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2AddContentloading]: ./reference/win32/0-9-430/icorewebview2.md#add_contentloading "add_ContentLoading インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2AddHistorychanged]: ./reference/win32/0-9-430/icorewebview2.md#add_historychanged "add_HistoryChanged インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2Addremoteobject]: ./reference/win32/0-9-430/icorewebview2.md#addremoteobject "AddRemoteObject-interface ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2AddSourcechanged]: ./reference/win32/0-9-430/icorewebview2.md#add_sourcechanged "add_SourceChanged インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2AddWindowcloserequested]: ./reference/win32/0-9-430/icorewebview2.md#add_windowcloserequested "add_WindowCloseRequested インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2CoreWebview2ScriptDialogKind]: ./reference/win32/0-9-430/icorewebview2.md#core_webview2_script_dialog_kind "CORE_WEBVIEW2_SCRIPT_DIALOG_KIND インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2devtoolsprotocoleventreceiver]: ./reference/win32/0-9-430/icorewebview2devtoolsprotocoleventreceiver.md "インターフェイス ICoreWebView2DevToolsProtocolEventReceiver |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2devtoolsprotocoleventreceiverAddDevtoolsprotocoleventreceived]: ./reference/win32/0-9-430/icorewebview2devtoolsprotocoleventreceiver.md#add_devtoolsprotocoleventreceived "add_DevToolsProtocolEventReceived インターフェイス ICoreWebView2DevToolsProtocolEventReceiver |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2devtoolsprotocoleventreceiverRemoveDevtoolsprotocoleventreceived]: ./reference/win32/0-9-430/icorewebview2devtoolsprotocoleventreceiver.md#remove_devtoolsprotocoleventreceived "remove_DevToolsProtocolEventReceived インターフェイス ICoreWebView2DevToolsProtocolEventReceiver |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2environmentGetBrowserversioninfo]: ./reference/win32/0-9-430/icorewebview2environment.md#get_browserversioninfo "get_BrowserVersionInfo インターフェイス ICoreWebView2Environment |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2host]: ./reference/win32/0-9-430/icorewebview2host.md "インターフェイス ICoreWebView2Host |Microsoft ドキュメント"  
[ReferenceWin3209430Webview2IdlGetcorewebview2browserversioninfo]: ./reference/win32/0-9-430/webview2-idl.md#getcorewebview2browserversioninfo "GetCoreWebView2BrowserVersionInfo-Globals |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2hostGetZoomfactor]: ./reference/win32/0-9-430/icorewebview2host.md#get_zoomfactor "get_ZoomFactor インターフェイス ICoreWebView2Host |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2hostNotifyparentwindowpositionchanged]: ./reference/win32/0-9-430/icorewebview2host.md#notifyparentwindowpositionchanged "NotifyParentWindowPositionChanged-インターフェイス ICoreWebView2Host |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2hostPutZoomfactor]: ./reference/win32/0-9-430/icorewebview2host.md#put_zoomfactor "put_ZoomFactor インターフェイス ICoreWebView2Host |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2hostSetboundsandzoomfactor]: ./reference/win32/0-9-430/icorewebview2host.md#setboundsandzoomfactor "SetBoundsAndZoomFactor-インターフェイス ICoreWebView2Host |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2httpheaderscollectioniteratorGetHascurrentheader]: ./reference/win32/0-9-430/icorewebview2httpheaderscollectioniterator.md#get_hascurrentheader "get_HasCurrentHeader インターフェイス ICoreWebView2HttpHeadersCollectionIterator |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2httprequestheadersGetheaders]: ./reference/win32/0-9-430/icorewebview2httprequestheaders.md#getheaders "GetHeaders-インターフェイス ICoreWebView2HttpRequestHeaders |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2httpresponseheadersGetheader]: ./reference/win32/0-9-430/icorewebview2httpresponseheaders.md#getheader "GetHeader-インターフェイス ICoreWebView2HttpResponseHeaders |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2Removeremoteobject]: ./reference/win32/0-9-430/icorewebview2.md#removeremoteobject "RemoveRemoteObject-インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2settingsGetAreremoteobjectsallowed]: ./reference/win32/0-9-430/icorewebview2settings.md#get_areremoteobjectsallowed "get_AreRemoteObjectsAllowed インターフェイス ICoreWebView2Settings |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2settingsGetIszoomcontrolenabled]: ./reference/win32/0-9-430/icorewebview2settings.md#get_iszoomcontrolenabled "get_IsZoomControlEnabled インターフェイス ICoreWebView2Settings |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2webmessagereceivedeventargsTrygetwebmessageasstring]: ./reference/win32/0-9-430/icorewebview2webmessagereceivedeventargs.md#trygetwebmessageasstring "TryGetWebMessageAsString-interface ICoreWebView2WebMessageReceivedEventArgs |Microsoft ドキュメント"  

[ReferenceWin3209488Icorewebview2AddFramenavigationcompleted]: ./reference/win32/0-9-488/icorewebview2.md#add_framenavigationcompleted "add_FrameNavigationCompleted インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209488Icorewebview2Addhostobjecttoscript]: ./reference/win32/0-9-488/icorewebview2.md#addhostobjecttoscript "AddHostObjectToScript-interface ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209488Icorewebview2AddNewwindowrequested]: ./reference/win32/0-9-488/icorewebview2.md#add_newwindowrequested "add_NewWindowRequested インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209488Icorewebview2environmentGetBrowserversionstring]: ./reference/win32/0-9-488/icorewebview2environment.md#get_browserversionstring "|Microsoft ドキュメント"  
[ReferenceWin3209488Icorewebview2environmentoptions]: ./reference/win32/0-9-488/icorewebview2environmentoptions.md "インターフェイス ICoreWebView2EnvironmentOptions |Microsoft ドキュメント"  
[ReferenceWin3209488Icorewebview2experimentalcompositioncontroller]: ./reference/win32/0-9-488/icorewebview2experimentalcompositioncontroller.md "インターフェイス ICoreWebView2ExperimentalCompositionController |Microsoft ドキュメント"  
[ReferenceWin3209488Icorewebview2experimentalcursorchangedeventhandler]: ./reference/win32/0-9-488/icorewebview2experimentalcursorchangedeventhandler.md "インターフェイス ICoreWebView2ExperimentalCursorChangedEventHandler |Microsoft ドキュメント"  
[ReferenceWin3209488Icorewebview2experimentalpointerinfo]: ./reference/win32/0-9-488/icorewebview2experimentalpointerinfo.md "インターフェイス ICoreWebView2ExperimentalPointerInfo |Microsoft ドキュメント"  
[ReferenceWin3209488Icorewebview2Removehostobjectfromscript]: ./reference/win32/0-9-488/icorewebview2.md#removehostobjectfromscript "RemoveHostObjectFromScript-interface ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209488Icorewebview2settingsGetAreremoteobjectsallowed]: ./reference/win32/0-9-488/icorewebview2settings.md#get_areremoteobjectsallowed "get_AreRemoteObjectsAllowed インターフェイス ICoreWebView2Settings |Microsoft ドキュメント"  
[ReferenceWin3209488Icorewebview2settingsGetIsbuiltinerrorpageenabled]: ./reference/win32/0-9-488/icorewebview2settings.md#get_isbuiltinerrorpageenabled "|Microsoft ドキュメント"  
[ReferenceWin3209488Webview2IdlCreatecorewebview2environmentwithdetails]: ./reference/win32/0-9-488/webview2-idl.md#createcorewebview2environmentwithdetails "CreateCoreWebView2EnvironmentWithDetails-Globals |Microsoft ドキュメント"  
[ReferenceWin3209488Webview2IdlCreatecorewebview2environmentwithoptions]: ./reference/win32/0-9-488/webview2-idl.md#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions-Globals |Microsoft ドキュメント"  
[ReferenceWin3209488Webview2IdlGetavailablecorewebview2browserversionstring]: ./reference/win32/0-9-488/webview2-idl.md#getavailablecorewebview2browserversionstring "GetAvailableCoreWebView2BrowserVersionString-Globals |Microsoft ドキュメント"  

[ReferenceDotnet09515Reference]: ./reference/dotnet/0-9-515-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[ReferenceWinforms09515Reference]: ./reference/winforms/0-9-515-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[ReferenceWpf09515Reference]: ./reference/wpf/0-9-515-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  

[ReferenceDotnet09538MicrosoftWebWebview2CoreCorewebview2environment]: ./reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2environment.md "WebView2 クラス | CoreWebView2Environment クラスを |Microsoft ドキュメント"  
[ReferenceDotnet09538MicrosoftWebWebview2CoreCorewebview2environmentComparebrowserversions]: ./reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2environment.md#comparebrowserversions "CompareBrowserVersions クラス | WebView2 クラスをお選びください。 CoreWebView2EnvironmentMicrosoft ドキュメント"
[ReferenceDotnet09538MicrosoftWebWebview2CoreCorewebview2environmentGetavailablebrowserversionstring]: ./reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2environment.md#getavailablebrowserversionstring "GetserverWebView2 クラスに CoreWebView2Environment を指定してください。 |Microsoft ドキュメント"  
[ReferenceDotnet09538MicrosoftWebWebview2CoreCorewebview2Newwindowrequested]: ./reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2.md#newwindowrequested "NewWindowRequested-CoreWebView2 クラス | WebView2 クラス |Microsoft ドキュメント"  
[ReferenceDotnet09538MicrosoftWebWebview2CoreCorewebview2Permissionrequested]: ./reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2.md#permissionrequested "要求された PermissionRequested クラス WebView2 |Microsoft ドキュメント"  
[ReferenceDotnet09538MicrosoftWebWebview2CoreCorewebview2Scriptdialogopening]: ./reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2.md#scriptdialogopening "WebView2 クラスの CoreWebView2 クラスのスクリプトの開始 |Microsoft ドキュメント"  
[ReferenceDotnet09538MicrosoftWebWebview2CoreCorewebview2Webresourcerequested]: ./reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2.md#webresourcerequested "WebResourceRequested クラス | WebView2 クラスをお選びください。 CoreWebView2Microsoft ドキュメント"  
[ReferenceWin3209538Icorewebview2Addhostobjecttoscript]: ./reference/win32/0-9-538/icorewebview2.md#addhostobjecttoscript "AddHostObjectToScript-interface ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209538Icorewebview2experimentalnewwindowrequestedeventargsGetWindowfeatures]: ./reference/win32/0-9-538/icorewebview2experimentalnewwindowrequestedeventargs.md#get_windowfeatures "get_WindowFeatures インターフェイス ICoreWebView2ExperimentalNewWindowRequestedEventArgs |Microsoft ドキュメント"  
[ReferenceWin3209538Icorewebview2experimentalwindowfeatures]: ./reference/win32/0-9-538/icorewebview2experimentalwindowfeatures.md "インターフェイス ICoreWebView2ExperimentalWindowFeatures |Microsoft ドキュメント"  
[ReferenceWin3209538Icorewebview2settingsGetArehostobjectsallowed]: ./reference/win32/0-9-538/icorewebview2settings.md#get_arehostobjectsallowed "get_AreHostObjectsAllowed インターフェイス ICoreWebView2Settings |Microsoft ドキュメント"  
[ReferenceWin3209538Webview2IdlCreatecorewebview2environmentwithoptions]: ./reference/win32/0-9-538/webview2-idl.md#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions-Globals |Microsoft ドキュメント"  

[GithubMicrosoftedgeWebviewfeedbackIssue1]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/1 "MicrosoftEdge/WebViewFeedback の問題1のフィードバックリポジトリ"  
[GithubMicrosoftedgeWebviewfeedbackIssue12]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/12 "MicrosoftEdge/WebViewFeedback の問題に関するフィードバックリポジトリ"  
[GithubMicrosoftedgeWebviewfeedbackIssue13]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/13 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ13"  
[GithubMicrosoftedgeWebviewfeedbackIssue14]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/14 "MicrosoftEdge/WebViewFeedback の問題に関するフィードバックリポジトリ"  
[GithubMicrosoftedgeWebviewfeedbackIssue16]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/16 "MicrosoftEdge/WebViewFeedback 問題のフィードバックリポジトリ"  
[GithubMicrosoftedgeWebviewfeedbackIssue17]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/17 "MicrosoftEdge/WebViewFeedback の問題に関するフィードバックリポジトリ"  
[GithubMicrosoftedgeWebviewfeedbackIssue18]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/18 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ18"  
[GithubMicrosoftedgeWebviewfeedbackIssue19]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/19 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ19"  
[GithubMicrosoftedgeWebviewfeedbackIssue22]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/22 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ22"  
[GithubMicrosoftedgeWebviewfeedbackIssue27]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/27 "MicrosoftEdge/WebViewFeedback の問題に関するフィードバックリポジトリ27"  
[GithubMicrosoftedgeWebviewfeedbackIssue28]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/28 "MicrosoftEdge/WebViewFeedback の問題に関するフィードバックリポジトリ"  
[GithubMicrosoftedgeWebviewfeedbackIssue30]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/30 "MicrosoftEdge/WebViewFeedback の問題を解決するためのフィードバックリポジトリ"  
[GithubMicrosoftedgeWebviewfeedbackIssue32]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/32 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ32"  
[GithubMicrosoftedgeWebviewfeedbackIssue36]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/36 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ36"  
[GithubMicrosoftedgeWebviewfeedbackIssue57]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/57 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ57"  
[GithubMicrosoftedgeWebviewfeedbackIssue70]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/70 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ70"  
[GithubMicrosoftedgeWebviewfeedbackIssue74]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/74 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ74"  
[GithubMicrosoftedgeWebviewfeedbackIssue95]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/95 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ95"  
[GithubMicrosoftedgeWebviewfeedbackIssue108]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/108 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ108"  
[GithubMicrosoftedgeWebviewfeedbackIssue113]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/113 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ113"  
[GithubMicrosoftedgeWebviewfeedbackIssue119]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/119 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ119" 
[GithubMicrosoftedgeWebviewfeedbackIssue148]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/148 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ148"  
[GithubMicrosoftedgeWebviewfeedbackIssue179]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/179 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ179"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesPr17]: https://github.com/MicrosoftEdge/WebView2Samples/pull/17 "最新の WebView2 SDK 0.9.430-MicrosoftEdge/WebView2Samples | を使用するようにプロジェクトを移動するGitHub"  
[GithubMicrosoftedgeWebview2samplesApisample]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/WebView2APISample "WebView2 API のサンプル-MicrosoftEdge/WebView2Samples |GitHub"  

[NuGetGallery]:  https://www.nuget.org/packages/Microsoft.Web.WebView2 "NuGet ギャラリー |WebView2"  
[NuGetGallery0.8.149]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.149 "NuGet ギャラリー |WebView2 v 0.8.149"  
[NuGetGallery0.8.190]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.190 "NuGet ギャラリー |WebView2 v 0.8.190"  
[NuGetGallery0.8.230]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.230 "NuGet ギャラリー |WebView2 v 0.8.230"  
[NuGetGallery0.8.270]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.270 "NuGet ギャラリー |WebView2 v 0.8.270"  
[NuGetGallery0.8.314]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.314 "NuGet ギャラリー |WebView2 v 0.8.314"  
[NuGetGallery0.8.355]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.355 "NuGet ギャラリー |WebView2 v 0.8.355"  
[NuGetGallery0.9.430]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.430 "NuGet ギャラリー |WebView2 v 0.9.430"  
[NuGetGallery0.9.488]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.488 "NuGet ギャラリー |WebView2 v 0.9.488"  
[NuGetGallery0.9.515-prerelease]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.515-prerelease "NuGet ギャラリー |WebView2 v 0.9.515 プレリリース"  
[NuGetGallery0.9.538]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.538 "NuGet ギャラリー |WebView2 v 0.9.538"  
