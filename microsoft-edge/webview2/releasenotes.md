---
description: Microsoft Edge WebView2 SDK のリリースノート
title: Win32、WPF、および WinForms の Microsoft Edge WebView2 のリリースノート
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/15/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 96ceb12dc5cdf51a1ca254f52e967fd78b9dc15d
ms.sourcegitcommit: 442de63da52d00c6dc27fa08ccdb736534127566
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "11120096"
---
# WebView2 SDK のリリースノート  

WebView2 チームは、6週間のリズムで [WEBVIEW2 SDK][NuGetGallery] の更新プログラムを提供しています。  製品のお知らせ、API サーフェスの追加と変更、および変更の互換性に関する最新情報については、次の内容を確認してください。  

> [!NOTE]
> NuGet パッケージの更新後に、アプリを再コンパイルします。  

> [!IMPORTANT]
> WebView2 はプレビューであり、.NET Api はに `prerelease package` あります。  

## 0.9.628-プレリリース  

リリース日: 2020 年9月10日  

[NuGet パッケージ][NuGetGallery0.9.628-prerelease] \ |Microsoft Edge の最小バージョン87.0.628.0。  

> [!IMPORTANT]
> **お知らせ**: このプレリリースは、Microsoft Edge 87 ブランチに基づいてリリースされ続けます。  今後、プレリリース SDK のリリースが Microsoft edge のバージョンと一致しています。通常のリリースは Microsoft Edge の厩舎と同期されています。  

#### 全般的な情報  

*   > [!IMPORTANT]
    > **お知らせ**: ビジュアルホスティング api が [プレビュー] の下に表示されます。  WebView2 は、HWNDs に対してではなく、Visual のホスティングを使って WinComp/DComp のビジュアルと共に実行します。  インターフェイスは実験的なものです。  詳細については、 [ICoreWebView2ExperimentalEnvironment][ReferenceWin3209622Icorewebview2experimentalenvironment]に移動してください。  

#### .NET  

*   .NET バイナリには [、厳密な名前が付け][DotnetStandardAssemblyStrongNamed]られています。  \ ([\ #181][GithubMicrosoftedgeWebviewfeedbackIssue181]\)  
*   対象となる NuGet ターゲットが更新されました `WebViewLoader2.dll` 。  \ ([\ #228][GithubMicrosoftedgeWebviewfeedbackIssue228]\) と \ ([\ #183][GithubMicrosoftedgeWebviewfeedbackIssue183]\)  
*   `WebResourceRequested`.Net で[HttpRequestHeaders][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2httprequestheaders]と[HttpResponseHeaders][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2httpresponseheaders]の api を公開するように更新されました。  \ ([\ #131][GithubMicrosoftedgeWebviewfeedbackIssue131]\)  

## 0.9.622.11  

リリース日: 2020 年9月10日  

[NuGet パッケージ][NuGetGallery0.9.622.11] \ |WebView2 の最小ランタイムバージョン86.0.622.11。  

#### 全般的な情報  

*   > [!IMPORTANT]
    > **アナウンスメント**: この SDK は、WebView2 Win32 C/c + + GA のリリース候補です。  GA バージョンでは、同じ API インターフェイスと機能を使用する必要があります。  

*   切断された [ブラウザーポリシー][DeployedgeMicrosoftEdgePolicies]。  
*   WebView2 環境オプションの [AllowSingleSignOnUsingOSPrimaryAccount][ReferenceWin3209622Icorewebview2environmentoptionsGetAllowsinglesignonusingosprimaryaccount] プロパティを追加して、WebView の条件付きアクセスを有効にします。  
*   `ICoreWebView2NewWindowRequestedEventArgs` [Windowfeatures][ReferenceWin3209622Icorewebview2newwindowrequestedeventargsGetWindowfeatures]プロパティと関連付けられた[ICoreWebView2WindowFeatures][ReferenceWin3209622Icorewebview2windowfeatures]を含むように更新されました。  \ ([\ #293][GithubMicrosoftedgeWebviewfeedbackIssue293]\)  
*   `System.Windows.Rect` `System.Drawing.Rectangle` `System.Windows.Rect` \ ([\ #235][GithubMicrosoftedgeWebviewfeedbackIssue235]\) の代わりにを使用するように更新されました。  
*   パラメーターのない要求を処理するために、NewWindowRequested イベントが更新されました `window.open()` 。  \ ([\ #293][GithubMicrosoftedgeWebviewfeedbackIssue293]\)  
*   を使用する[Additionalbrowserarguments][ReferenceWin3209622Icorewebview2environmentoptionsPutAdditionalbrowserarguments] `ICoreWebView2EnvironmentOptions` は、環境変数でもレジストリ値でも上書きされません。  詳細については、 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin3209622IdlCreatecorewebview2environmentwithoptions]に移動してください。  

## 0.9.579  

リリース日: 2020 年7月20日  

[NuGet パッケージ][NuGetGallery0.9.579] \ |Microsoft Edge の最小バージョン86.0.579.0。  

#### 全般的な情報  

*   > [!IMPORTANT]
    > **お知らせ**: Evergreen WebView2 Runtime と installer がプレビュー用にリリースされました。  詳細については、「 [WebView2 の配布][Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview]に移動する」を参照してください。  
*   > [!IMPORTANT]
    > **お知らせ**: 次の sdk リリース以降、WebView2 SDK の次のバージョンはサポートされなくなりました。  
    > 
    > *   [0.8.190](#08190)  
    > *   [0.8.230](#08230)  
    > *   [0.8.270](#08270)  
    > *   [0.8.314](#08314)  
    > *   [0.8.355](#08355)  
    > 
    > WebView2 SDK バージョンは、nuget.org で廃止とマークされています。 WebView2 では、最新バージョンの WebView2 を使用して最新の状態を維持することをお勧めします。  

*   WebView worker のスレッドの改良が追加されました。  \ ([\ #318][GithubMicrosoftedgeWebviewfeedbackIssue318]\)  
*   WebView でポップアップブロックが無効になりました。  詳細については、イベントの [Isuserinitiated][ReferenceWin3209538Icorewebview2newwindowrequestedeventargsGetIsuserinitiated] プロパティに移動し `NewWindowRequested` ます。  
*   WebView ナビゲーションの開始イベントが発生することを確認 `about:blank` します。  この時点で、 `NavigationStarting` イベントはすべてのナビゲーションに対して発生しますが、キャンセル `about:blank` または iframe srcdoc はサポートされず、無視されます。  
*   `edge:// URI`WebView でブロックされたスキーム。  
*   WebView2 環境オプションに、WebView の条件付きアクセスを有効にする実験的な [IsSingleSignOnUsingOSPrimaryAccountEnabled][ReferenceWin3209538Icorewebview2experimentaloptionsGetIssinglesignonusingosprimaryaccountenabled] プロパティが追加されました。  
*   WebView が WebResource 要求に対する応答を受信して処理した後に発生する実験的な [WebResourceResponseReceived][ReferenceWin3209538Icorewebview2experimentalAddWebresourceresponsereceived] イベントが追加されました。  応答オブジェクトに認証ヘッダーが含まれている場合は、そのヘッダーが含まれます。  

#### .NET  

*   WPF フォーカス処理が改善されました。  \ ([\ #185][GithubMicrosoftedgeWebviewfeedbackIssue185]\)  
*   WPF Webview2 コントローラーのプロパティが追加されました `ZoomFactor` 。  

## 0.9.538  

[NuGet パッケージ][NuGetGallery0.9.538] \ |Microsoft Edge の最小バージョン85.0.538.0。  

#### 全般的な情報  

*   WebView2 SDK バージョン [0.8.149](#08149)のサポートを削除しています。  WebView2 では、最新バージョンの WebView2 を使用して最新の状態を維持することをお勧めします。  
*   Microsoft Edge ブラウザーのプロファイルパスが変更されたときにアカウントに対してグループポリシーが更新されました。 \ ([#179][GithubMicrosoftedgeWebviewfeedbackIssue179]\)。  

#### Win32 C/c + +  

*   [ICoreWebView2ExperimentalNewWindowRequestedEventArgs:: get_WindowFeatures][ReferenceWin3209538Icorewebview2experimentalnewwindowrequestedeventargsGetWindowfeatures]が追加されました `window.open()` 。実行され、 [ICoreWebView2ExperimentalWindowFeatures][ReferenceWin3209538Icorewebview2experimentalwindowfeatures] \ ([#70][GithubMicrosoftedgeWebviewfeedbackIssue70]\) に関連付けられたときに発生します。  
*   > [!IMPORTANT]
    > **変更の中断**:  [CreateCoreWebView2EnvironmentWithDetails][ReferenceWin3209488Webview2IdlCreatecorewebview2environmentwithdetails] は廃止され、[CreateCoreWebView2EnvironmentWithOptions] [[ReferenceWin3209538IdlCreatecorewebview2environmentwithoptions]] に置き換えられます。  
*   > [!IMPORTANT]
    > **変更の中断**: WebView2 API が Windows api の名前付け規則に合わせて配置されるようにするために、WebView チームは次の名前を更新しました。  
    > *   [AreRemoteObjectsAllowed][ReferenceWin3209488Icorewebview2settingsGetAreremoteobjectsallowed] は、次のように [使用でき][ReferenceWin3209538Icorewebview2settingsGetArehostobjectsallowed]ます。  
*   [Addhostobjecttoscript][ReferenceWin3209538Icorewebview2Addhostobjecttoscript]が更新され、元のホストオブジェクトシリアライザーのマーカーがプロキシオブジェクトに設定され、JavaScript コールバックのパラメーターとしてシリアル化された ([#148][GithubMicrosoftedgeWebviewfeedbackIssue148]\)  

#### .NET (0.9.538 プレリリース版)  

*   WinForms と WPF WebView2API のサンプルをリリースしました。これは WebView2 SDK の包括的なガイドです。  詳細については、「 [サンプルリポジトリ][GithubMicrosoftedgeWebview2samplesMain]」を参照してください。  
*   ビジュアルホスト機能と window 機能の [実験的な api][ConceptsVersioningExperimentalApis]のサポートが追加されました。  
*   > [!IMPORTANT]
    > **変更の中断**: 次の保留は IDisposable: [scriptWebResourceRequested 始値][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2Scriptdialogopening]、 [newwindowrequested][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2Newwindowrequested]、 [WebResourceRequested][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2Webresourcerequested]、および[permissionrequested][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2Permissionrequested]実装するようになりました。  
*   [GetCompareBrowserVersions の文字列][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentGetavailablebrowserversionstring]と[CompareBrowserVersions][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentComparebrowserversions]を[CoreWebView2Environment][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environment]の静的として追加しました。  

## 0.9.515-プレリリース  

[NuGet パッケージ][NuGetGallery0.9.515-prerelease] \ |Microsoft Edge の最小バージョン84.0.515.0。  

*   > [!IMPORTANT]
    > **アナウンスメント**: WebView2 では、.net Framework 4.6.2 以降および .net Core 3.0 以降の Windows フォームと WPF が **プレリリースパッケージ**でサポートされるようになりました。  
*   Wpf アプリケーションの構築および WPF 固有の Api 用の WebView2 [Wpf 参照][ReferenceWpfReference] について詳しくは、「 [Wpf の概要」][GettingstartedWpf]をご覧ください。  
*   Windows フォームアプリケーションの構築および windows フォーム固有の Api 用の WebView2 [Windows フォームリファレンス][ReferenceWinformsReference] の詳細については、「 [Windows フォームのクイックスタートガイド」][GettingstartedWinforms]を参照してください。  
*   CoreWebView2 Api の詳細については、「 [.Net リファレンス][ReferenceDotnetReference]」を参照してください。  
*   > [!CAUTION]
    > **既知の問題**: WebView チームは、今後のリリースで解決されるプレリリースの一部の問題を認識しています。  
    > *   **Dpi 認識**: WPF の WebView2 は現在 DPI に対応していません。  高 DPI モニターで WebView2 を初期化すると、ウィンドウのサイズが変更されるまで、WebView が最初にウィンドウの一部として初期化される既知の問題が発生します。  
    > *   **Wpf デザイナー**: wpf デザイナーは現在サポートされていません。  テキストエディターで適切な XAML を直接変更することによって、アプリに WebView2 コントロールを追加します。  

## 0.9.488  

[NuGet パッケージ][NuGetGallery0.9.488] \ |Microsoft Edge の最小バージョン84.0.488.0。  

*   > [!IMPORTANT]
    > **お知らせ**: 予定されている Microsoft Edge バージョン83以降、evergreen WebView は、安定したブラウザーチャネルをターゲットとしていません。  代わりに、別のバイナリセットのブランド [Evergreen WebView2 ランタイム][ConceptsDistributionEvergreenMode]をターゲットにします。これは、WebView チームが現在開発しているインストーラーを使ってインストールすることができます。  詳細については、「 [アプリの配布][ConceptsDistribution]」を参照してください。  
*   > [!IMPORTANT]
    > **お知らせ**: 前進すると、WebView チームは2つのパッケージをリリースします。プレリリースパッケージ (\) と、安定した api を含む安定したリリースパッケージ (お客様の信頼できる)。  相違点については、「 [ブラウザーのバージョンと WebView2 につい][ConceptsVersioning]て」を参照してください。  
*   > [!IMPORTANT]
    > **変更の中断**: WebView2 API が Windows api の名前付け規則に合わせて配置されるようにするために、WebView チームは次のインターフェイスの名前を更新しました。  
    > *   `CORE_WEBVIEW2_*` プレフィックスは現在 `COREWEBVIEW2_*` です。  
    > *   [GetCoreWebView2BrowserVersionInfo][ReferenceWin3209430Webview2IdlGetcorewebview2browserversioninfo] は [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin3209488Webview2IdlGetavailablecorewebview2browserversionstring]になりました。  
    > *   [get_BrowserVersionInfo][ReferenceWin3209430Icorewebview2environmentGetBrowserversioninfo] が [get_BrowserVersionString][ReferenceWin3209488Icorewebview2environmentGetBrowserversionstring]ました。  
    > *   [Addremoteobject][ReferenceWin3209430Icorewebview2Addremoteobject] は [Addhostobjecttoscript][ReferenceWin3209488Icorewebview2Addhostobjecttoscript]になりました。  
    > *   [RemoveRemoteObject][ReferenceWin3209430Icorewebview2Removeremoteobject] が [Removehostobjectfromscript][ReferenceWin3209488Icorewebview2Removehostobjectfromscript]になりました。  
    > *   `chrome.webview.remoteObjects` は現在 `chrome.webview.hostObjects` です。  
*   > [!IMPORTANT]
    > **変更の中断**: `AddRemoteObject` JS プロキシメソッドも名前が変更されます。  
    > *   `getLocal` は現在 `getLocalProperty` です。  
    > *   `setLocal` は現在 `setLocalProperty` です。  
    > *   `getRemote` は現在 `getHostProperty` です。  
    > *   `setRemote` は現在 `setHostProperty` です。  
    > *   `applyRemote` は現在 `applyHostFunction` です。  
*   > [!IMPORTANT]
    > **変更の中断**:  [CreateCoreWebView2EnvironmentWithDetails][ReferenceWin3209488Webview2IdlCreatecorewebview2environmentwithdetails] は廃止され、 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin3209488Webview2IdlCreatecorewebview2environmentwithoptions]に置き換えられます。  
*   [FrameNavigationCompleted][ReferenceWin3209488Icorewebview2AddFramenavigationcompleted]イベントが追加されました。  これで、iframe がナビゲーションを完了するときに、イベントが発生し、ナビゲーションとナビゲーション id の成功が返されます。  
*   アプリケーションがターゲットとする WebView2 ランタイムのバージョンを判断するために使用される [ICoreWebView2EnvironmentOptions][ReferenceWin3209488Icorewebview2environmentoptions] インターフェイスが追加されました。  
*   [IsBuiltInErrorPageEnabled][ReferenceWin3209488Icorewebview2settingsGetIsbuiltinerrorpageenabled]設定が追加されました。  これで、ナビゲーションエラーとレンダープロセスエラーについて、組み込みのエラーページを有効または無効にすることができます。  
*   .NET IDispatch の実装をサポートするために、リモートオブジェクトの挿入が更新されました \ ([#113][GithubMicrosoftedgeWebviewfeedbackIssue113]\)。  
*   コンテキストメニュー \ ([#108][GithubMicrosoftedgeWebviewfeedbackIssue108]\) からの要求を処理するために、 [newwindowrequested][ReferenceWin3209488Icorewebview2AddNewwindowrequested]イベントが更新されました。  
*   Visual ホスティング Api にアクセスできる、最初の個別の WebView2 プレリリースパッケージがリリースされました。  WebView チーム [が更新され、][GithubMicrosoftedgeWebview2samplesMain] 新しい実験的な api が追加されました。  
    *   [ICoreWebView2ExperimentalCompositionController][ReferenceWin3209488Icorewebview2experimentalcompositioncontroller]インターフェイスを追加して、コンポジションツリーに接続し、WebView の入力を指定します。  
    *   からのすべての情報が含まれている [ICoreWebView2ExperimentalPointerInfo][ReferenceWin3209488Icorewebview2experimentalpointerinfo]が追加されました `POINTER_INFO` 。  このオブジェクトは、WebView にポインター入力を挿入するために、Sendpointer 入力に渡されます。  
    *   [ICoreWebView2ExperimentalCursorChangedEventHandler][ReferenceWin3209488Icorewebview2experimentalcursorchangedeventhandler]を追加しました。 WebView にマウスカーソルを合わせたときに、アプリに通知されます。  WebView のテキストボックス上にマウスを移動すると、カーソルが矢印からセレクターに変わります。  上のプロパティは、 `cursor` `CompositionController` WebView のマウスカーソルが現在どのようなものであるかをアプリに通知します。  

## 0.9.430  

[NuGet パッケージ][NuGetGallery0.9.430] \ |Microsoft Edge の最小バージョン82.0.430.0。  

WebView2 SDK は、フィードバックからいくつかの機能要求を取り入れた、Win32 の公式バージョンである Win32 C++ ベータバージョンです。  WebView チームは、変更によってリリースの数を制限しようとしていますが、一般的な可用性が考慮されています。ベータ版は、いくつかの重要な変更を1つの go で取り入れています。  

*   > [!IMPORTANT]
    > **変更の中断**: 最終リリースでは、WebView2 Api が Windows api の名前付け規則に合わせて配置されるように、WebView チームはプレフィックス *IWebView2WebView*   を *ICoreWebView2*   に変更します。  さらに、WebView2 SDK を UI フレームワークから利用するために、WebView チームは `ICoreWebView2` [ICoreWebView2][ReferenceWin3209430Icorewebview2] と [ICoreWebView2Host][ReferenceWin3209430Icorewebview2host]に分かれています。  `ICoreWebView2Host` ウィンドウのサイズ変更、表示/非表示、フォーカスなど、ウィンドウとコンポジションに関連する機能をサポートします。  ICoreWebView2 は、その他のすべての WebView2 機能をサポートしています。  変更の反映の詳細については、WebView2 [Apisample][GithubMicrosoftedgeWebview2samplesMain]プロジェクトの[pull 要求][GithubMicrosoftedgeWebview2samplesPr17]に移動してください。  
*   > [!IMPORTANT]
    > **変更の中断**: [sourcechanged][ReferenceWin3209430Icorewebview2AddSourcechanged]、 [Contentloading][ReferenceWin3209430Icorewebview2AddContentloading]、[履歴が変更された][ReferenceWin3209430Icorewebview2AddHistorychanged] [DocumentStateChanged][ReferenceWin3208190Iwebview2webviewAddDocumentstatechanged]を3つのコンポーネントに分割します。  これで、ソースの URL が変更されたときに、 `SourceChanged` イベントが発生します。  履歴の状態が変更されると、 `HistoryChanged` イベントが発生します。  `ContentLoading`新しいドキュメントを読み込むときに、最初のスクリプトの前にイベントが発生します。  
*   ARM64 アーキテクチャのサポートが追加されました。  
*   タッチスクリーンデバイスのソフト入力パネル \ (SIP) サポートを追加しました。  
*   Windows server 2008 R2、Windows Server 2012、Windows Server 2012 R2、Windows Server 2016 のサポートが追加されました。  
*   [NotifyParentWindowPositionChanged][ReferenceWin3209430Icorewebview2hostNotifyparentwindowpositionchanged]が追加されました。これにより、ウィンドウモードのウィンドウがステータスバーに表示されます。  アクセシビリティ機能が動作するためには、変更をウィンドウなしモードでも実装する必要があります。  
*   任意のリモートオブジェクトからページにアクセスできるかどうかをグローバル制御するための [AreRemoteObjectsAllowed][ReferenceWin3209430Icorewebview2settingsGetAreremoteobjectsallowed] 設定が追加されました。  既定で `AreRemoteObjectsAllowed` は、有効になります。 [Addremoteobject][ReferenceWin3209430Icorewebview2Addremoteobject] によって追加されたリモートオブジェクトは、ページからアクセスできます。  無効にすると `AreRemoteObjectsAllowed` 、そのオブジェクトはページからアクセスできません。  変更は次のナビゲーションイベントに適用されます。  
*   [IsZoomControlEnabled][ReferenceWin3209430Icorewebview2settingsGetIszoomcontrolenabled]設定を追加して、ユーザーが WebView `ctrl` + `+` と `ctrl` + `-` \ (または `ctrl` + マウスホイール \) のズームに影響しないようにします。  設定を無効にすると、 [put_ZoomFactor][ReferenceWin3209430Icorewebview2hostPutZoomfactor] を使用してズームを設定することができます。  
*   現在の WebView にのみ適用されるように変更された ZoomFactor。  現在の WebView のズームの変更は、元のサイトに移動した他の WebViews には影響しません。  詳細については、 [get_ZoomFactor][ReferenceWin3209430Icorewebview2hostGetZoomfactor]に移動してください。  
*   WebView \ ([#95][GithubMicrosoftedgeWebviewfeedbackIssue95]\) の HID ZoomView UI。  
*   [SetBoundsAndZoomFactor][ReferenceWin3209430Icorewebview2hostSetboundsandzoomfactor]が追加されました。  この時点で、WebView のズーム率と境界を同時に設定できます。  
*   [WindowCloseRequested][ReferenceWin3209430Icorewebview2AddWindowcloserequested]イベントが追加されました。  詳細については、 [add_WindowCloseRequested][ReferenceWin3209430Icorewebview2AddWindowcloserequested] \ ([#119][GithubMicrosoftedgeWebviewfeedbackIssue119]\) に移動してください。  
*   Javascript ダイアログイベントのダイアログ型のサポートが追加され、 `beforeunload` 列挙型エントリ [CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_BEFOREUNLOAD][ReferenceWin3209430Icorewebview2CoreWebview2ScriptDialogKind] 追加されました。  
*   HttpRequestHeaders、 [GetHeader][ReferenceWin3209430Icorewebview2httpresponseheadersGetheader] 、HttpResponseHeaders、 [Get_HasCurrentHeader][ReferenceWin3209430Icorewebview2httpheaderscollectioniteratorGetHascurrentheader]プロパティに[GetHeaders][ReferenceWin3209430Icorewebview2httprequestheadersGetheaders]を httpheaderscollectioniterator に追加しました。  
*   > [!IMPORTANT]
    > **変更の中断**: 動作が変更されました `DevToolsProtocolEventReceived` 。  次に、 [add_DevToolsProtocolEventReceived][ReferenceWin3209430Icorewebview2devtoolsprotocoleventreceiverAddDevtoolsprotocoleventreceived]remove_DevToolsProtocolEventReceived を使用して、特定の devtools プロトコルイベント用の[DevToolsProtocolEventReceiver][ReferenceWin3209430Icorewebview2devtoolsprotocoleventreceiver]を作成し、そのイベントをサブスクライブまたはサブスクライブ解除することができ / [remove_DevToolsProtocolEventReceived][ReferenceWin3209430Icorewebview2devtoolsprotocoleventreceiverRemoveDevtoolsprotocoleventreceived]ます。
*   > [!IMPORTANT]
    > **変更の中断**: WebMessageReceivedEventArgs ' [Get_WebMessageAsString][ReferenceWin3208190Iwebview2webmessagereceivedeventargsGetWebmessageasstring] プロパティが [Trygetwebmessageasstring][ReferenceWin3209430Icorewebview2webmessagereceivedeventargsTrygetwebmessageasstring] メソッドに変更されました。  
*   > [!IMPORTANT]
    > **変更の中断**: `AcceleratorKeyPressedEventArgs` [get_Handled][ReferenceWin3209430Icorewebview2acceleratorkeypressedeventargsGetHandled]プロパティに[ハンドル][ReferenceWin3208190Iwebview2acceleratorkeypressedeventargsHandle]メソッドを変更しました。  

## 0.8.355

[NuGet パッケージ][NuGetGallery0.8.355] \ |Microsoft Edge の最小バージョン80.0.355.0。

*   WebView2 SDK の包括的なガイドである WebView2API サンプルをリリースしました。  詳細については、「 [Apisample][GithubMicrosoftedgeWebview2samplesApisample]」」を参照してください。  
*   英語 \ ([#30][GithubMicrosoftedgeWebviewfeedbackIssue30]\) 以外のすべての言語で IME のサポートが追加されました。  
*   バグレポートに対応してイベントの API サーフェスが更新されました `WebResourceRequested` 。  作成時にフィルターとイベントを同時に指定することは推奨されなくなりました。  Web リソース要求イベントを作成するには、 [add_WebResourceRequested][ReferenceWin3208190Iwebview2webview5AddWebresourcerequested] を使ってイベントと [AddWebResourceRequestedFilter][ReferenceWin3208190Iwebview2webview5Addwebresourcerequestedfilter] を追加し、フィルターを追加します。  [RemoveWebResourceRequestedFilter][ReferenceWin3208190Iwebview2webview5Removewebresourcerequestedfilter] はフィルター \ ([#36][GithubMicrosoftedgeWebviewfeedbackIssue36]\) \ ([#74][GithubMicrosoftedgeWebviewfeedbackIssue74]\) を削除します。  
*   > [!IMPORTANT]
    > **変更の中断**: 全画面の動作が変更されました。  廃止 [された Isfullscreenallowed 許可さ][ReferenceWin3208190Iwebview2settingsGetIsfullscreenallowedDeprecated]れました。  既定では、WebView \ (ビデオなど) の要素が全画面表示に設定されている場合、WebView の境界がいっぱいになります。  要素が全画面モードに入る場合に、アプリで WebView のサイズを変更する方法を指定するには、 [Fullfullscreenelementchanged][ReferenceWin3208190Iwebview2containsfullscreenelementchangedeventhandler] イベントと [get_ContainsFullScreenElement][ReferenceWin3208190Iwebview2webview5GetContainsfullscreenelement] を使います。  

## 0.8.314  

[NuGet パッケージ][NuGetGallery0.8.314] \ |Microsoft Edge の最小バージョン80.0.314.0。  

*   Windows 7、Windows 8、Windows 8.1 のサポートが追加されました。  
*   Visual Studio と Visual Studio のコードデバッグサポートを WebView2 に追加しました。  次に、IDE から直接 WebView2 のスクリプトをデバッグします。  詳細については、「 [WebView2 コントロールを使用して開発するときにデバッグする方法][HowtoDebug]」を参照してください。  
*   追加されました `Native Object Injection` 。これにより、WebView2 内で実行されるスクリプトは、アプリケーションの Win32 コンポーネントから idispatch オブジェクトにアクセスし、idispatch オブジェクトのプロパティにアクセスすることができます。  詳細については、 [Addremoteobject][ReferenceWin3208190Iwebview2webview4Addremoteobject] \ ([#17][GithubMicrosoftedgeWebviewfeedbackIssue17]\) に移動します。  
*   追加された `AcceleratorKeyPressed` イベント。  詳細については、 [add_AcceleratorKeyPressed][ReferenceWin3208190Iwebview2webview4AddAcceleratorkeypressed] \ ([#57][GithubMicrosoftedgeWebviewfeedbackIssue57]\) に移動してください。  
*   無効 `Context Menus` 。  詳細については、 [put_AreDefaultContextMenusEnabled][ReferenceWin3208190Iwebview2settings2PutAredefaultcontextmenusenabled] \ ([#57][GithubMicrosoftedgeWebviewfeedbackIssue57]\) に移動してください。  
*   更新されました `DPI Awareness` 。  これで、WebView の DPI 認識は、ホストアプリケーションの DPI 認識と同じになります。  
    
    > [!NOTE]
    > 別のハイブリッドアプリケーションを起動したときに、元の WebView と異なる DPI 認識が適用されている場合は、ユーザーデータディレクトリが同じ \ ([#1][GithubMicrosoftedgeWebviewfeedbackIssue1]\) である場合、新しい WebView は起動されません。  
    
*   更新された `Notification Change Behavior` ため、WebView2 は、WebView 内でホストされている web コンテンツによって求められる通知アクセス許可要求を自動的に拒否します  

## 0.8.270  

[NuGet パッケージ][NuGetGallery0.8.270] \ |Microsoft Edge の最小バージョン78.0.270.0。  

*   `DocumentTitleChanged`ドキュメントタイトルの変更 \ ([\ #27][GithubMicrosoftedgeWebviewfeedbackIssue27]\) を示すイベントが追加されました。  
*   `GetWebView2BrowserVersionInfo`API \ ([\ #18][GithubMicrosoftedgeWebviewfeedbackIssue18]\) を追加しました。  
*   追加された `NewWindowRequested` イベント。  
*   `CreateWebView2EnvironmentWithDetails`削除する関数が更新されました `releaseChannelPreference` 。  関数の詳細については `CreateWebView2EnvironmentWithDetails` 、 [CreateWebView2EnvironmentWithDetails][ReferenceWin3208190WebView2IdlCreatewebview2environmentwithdetails]に移動してください。  レジストリと環境変数の上書きは引き続きサポートされます。  既定のチャネルの設定が使用されます。上書きされていない場合。  
    チャネルの検索時に、WebView チームは、WebView2 SDK と互換性のない古いチャネルバージョンをスキップします。  
    WebView チームは、より安定したチャネルを選択して、エンドユーザーに対して最も一貫性のある動作を実現します。  最新のカナリアビルドを使ってテストする場合は、アプリを起動する `WEBVIEW2_RELEASE_CHANNEL_PREFERENCE` 前に環境変数を設定するスクリプトを作成する必要があり `1` ます。  
*   `CreateWebView2EnvironmentWithDetails` `userDataFolder` 指定されていない場合に選択するためのロジックで関数が更新されました。  関数の詳細については `CreateWebView2EnvironmentWithDetails` 、 [CreateWebView2EnvironmentWithDetails][ReferenceWin3208190WebView2IdlCreatewebview2environmentwithdetails]に移動してください。  以前に既定の場所を使用していた場合は、 `userDataFolder` 新しい SDK に切り替えると既定値 `userDataFolder` (host code ディレクトリ内の新しい場所に設定) がリセットされ、状態もリセットされます。  
    指定したディレクトリに書き込むためのアクセス許可がホストプロセスにない場合、この `CreateWebView2EnvironmentWithDetails` 関数は失敗することがあります。  古いユーザーデータディレクトリから新しいディレクトリにデータをコピーすることができます。  

## 0.8.230  

[NuGet パッケージ][NuGetGallery0.8.230] \ |Microsoft Edge の最小バージョン77.0.230.0。  

*   `Stop`すべてのナビゲーションおよび保留中のリソースフェッチを停止するための API を追加しました \ ([\ #28][GithubMicrosoftedgeWebviewfeedbackIssue28]\)。  
*   `.tlb`ファイルが NuGet パッケージ \ ([\ #22][GithubMicrosoftedgeWebviewfeedbackIssue22]\) に追加されました。  
*   NuGet パッケージ \ ([\ #32][GithubMicrosoftedgeWebviewfeedbackIssue32]\) のインストーラリストに .net プロジェクトが追加されました。  

## 0.8.190  

[NuGet パッケージ][NuGetGallery0.8.190] \ |Microsoft Edge の最小バージョン77.0.190.0。  

*   `get_AreDevToolsEnabled` / `put_AreDevToolsEnabled` ユーザーが devtools \ ([\ #16][GithubMicrosoftedgeWebviewfeedbackIssue16]\) を開くことができる場合は、コントロールに追加されます。  
*   `get_IsStatusBarEnabled` / `put_IsStatusBarEnabled` ステータスバーが表示されている場合は、コントロールに追加されます (\[#19][GithubMicrosoftedgeWebviewfeedbackIssue19]\)。  
*   `get_CanGoBack` / `GoBack` / `get_CanGoForward` / `GoForward` ナビゲーション履歴を前後に移動するために追加されました。  
*   `IWebView2HttpHeadersCollectionIterator` / `IWebView2HttpRequestHeaders` / `IWebView2HttpRequestHeaders` WebView の http ヘッダーを表示し、変更するための http ヘッダーの種類 \ (\) を追加しました。  
*   64ビットコンピューター \ ([\ #13][GithubMicrosoftedgeWebviewfeedbackIssue13]\) に32ビット WebView サポートが追加されました。  
*   SDK \ ([\ #14][GithubMicrosoftedgeWebviewfeedbackIssue14]\) に WebView IDL が追加されました。  
*   `IID\_\*`インターフェイス id オブジェクト \ ([\ #12][GithubMicrosoftedgeWebviewfeedbackIssue12]\) をサポートするために lib が追加されました。  
*   追加された DLL ファイルのパス、リンク、自動コピーを SDK の NuGet ファイルに追加し `TARGET` ます。  
*   `window.open()`スクリプトでの要求を有効にしました。  

## 0.8.149  

[NuGet パッケージ][NuGetGallery0.8.149] \ |Microsoft Edge の最小バージョン76.0.149.0。  

最初の開発者プレビューリリース。  

<!-- Links -->  

[ConceptsDistribution]: ./concepts/distribution.md "WebView2 を使用したアプリケーションの配布 |Microsoft ドキュメント"  
[ConceptsDistributionEvergreenMode]: ./concepts/distribution.md#evergreen-distribution-mode "Evergreen 配布モード-WebView2 を使用したアプリケーションの配布 |Microsoft ドキュメント"  
[Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview]: ./concepts/distribution.md#understanding-the-webview2-runtime "WebView2 Runtime と installer (Preview) を使ったアプリケーションの配布について WebView2 |Microsoft ドキュメント"  
[ConceptsVersioning]: ./concepts/versioning.md "ブラウザーのバージョンと WebView2 についてMicrosoft ドキュメント"  
[ConceptsVersioningExperimentalApis]: ./concepts/versioning.md#experimental-apis "実験的 Api-ブラウザーのバージョンと WebView2 についてMicrosoft ドキュメント"  
[GettingstartedWinforms]: ./gettingstarted/winforms.md "Windows Forms アプリでの WebView2 の概要 |Microsoft ドキュメント"  
[GettingstartedWpf]: ./gettingstarted/wpf.md "WPF での WebView2 の概要 |Microsoft ドキュメント"  
[HowtoDebug]: ./howto/debug.md "WebView2 コントロールを使用して開発を行うときのデバッグ方法 |Microsoft ドキュメント"  

[ReferenceWin3208190Iwebview2acceleratorkeypressedeventargsHandle]: /microsoft-edge/webview2/reference/win32/iwebview2acceleratorkeypressedeventargs?view=webview2-0.8.355&preserve-view=true#handle "ハンドル-インターフェイスの IWebView2AcceleratorKeyPressedEventArgs |Microsoft ドキュメント"  
[ReferenceWin3208190Iwebview2containsfullscreenelementchangedeventhandler]: /microsoft-edge/webview2/reference/win32/iwebview2containsfullscreenelementchangedeventhandler?view=webview2-0.8.355&preserve-view=true "インターフェイス IWebView2ContainsFullScreenElementChangedEventHandler |Microsoft ドキュメント"  
[ReferenceWin3208190Iwebview2settings2PutAredefaultcontextmenusenabled]: /microsoft-edge/webview2/reference/win32/iwebview2settings2?view=webview2-0.8.355&preserve-view=true#put_aredefaultcontextmenusenabled "put_AreDefaultContextMenusEnabled インターフェイス IWebView2Settings2 |Microsoft ドキュメント"  
[ReferenceWin3208190Iwebview2settingsGetIsfullscreenallowedDeprecated]: /microsoft-edge/webview2/reference/win32/iwebview2settings?view=webview2-0.8.355&preserve-view=true#get_isfullscreenallowed_deprecated "get_IsFullscreenAllowed_deprecated インターフェイス IWebView2Settings |Microsoft ドキュメント"  
[ReferenceWin3208190Iwebview2webmessagereceivedeventargsGetWebmessageasstring]: /microsoft-edge/webview2/reference/win32/iwebview2webmessagereceivedeventargs?view=webview2-0.8.355&preserve-view=true#get_webmessageasstring "get_WebMessageAsString インターフェイス IWebView2WebMessageReceivedEventArgs |Microsoft ドキュメント"  
[ReferenceWin3208190Iwebview2webview4AddAcceleratorkeypressed]: /microsoft-edge/webview2/reference/win32/iwebview2webview4?view=webview2-0.8.355&preserve-view=true#add_acceleratorkeypressed "add_AcceleratorKeyPressed インターフェイス IWebView2WebView4 |Microsoft ドキュメント"  
[ReferenceWin3208190Iwebview2webviewAddDocumentstatechanged]: /microsoft-edge/webview2/reference/win32/iwebview2webview?view=webview2-0.8.355&preserve-view=true#add_documentstatechanged "add_DocumentStateChanged インターフェイス IWebView2WebView |Microsoft ドキュメント"  
[ReferenceWin3208190Iwebview2webview4Addremoteobject]: /microsoft-edge/webview2/reference/win32/iwebview2webview4?view=webview2-0.8.355&preserve-view=true#addremoteobject "AddRemoteObject-interface IWebView2WebView4 |Microsoft ドキュメント"  
[ReferenceWin3208190Iwebview2webview5AddWebresourcerequested]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#add_webresourcerequested "add_WebResourceRequested インターフェイス IWebView2WebView5 |Microsoft ドキュメント"  
[ReferenceWin3208190Iwebview2webview5Addwebresourcerequestedfilter]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#addwebresourcerequestedfilter "AddWebResourceRequestedFilter-インターフェイス IWebView2WebView5 |Microsoft ドキュメント"  
[ReferenceWin3208190Iwebview2webview5GetContainsfullscreenelement]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#get_containsfullscreenelement "get_ContainsFullScreenElement インターフェイス IWebView2WebView5 |Microsoft ドキュメント"  
[ReferenceWin3208190Iwebview2webview5Removewebresourcerequestedfilter]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#removewebresourcerequestedfilter "RemoveWebResourceRequestedFilter-インターフェイス IWebView2WebView5 |Microsoft ドキュメント"  
[ReferenceWin3208190WebView2IdlCreatewebview2environmentwithdetails]:  /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.8.355&preserve-view=true#createwebview2environmentwithdetails "CreateWebView2EnvironmentWithDetails-Globals |Microsoft ドキュメント"  

[ReferenceWin3209430Icorewebview2]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true "インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2acceleratorkeypressedeventargsGetHandled]: /microsoft-edge/webview2/reference/win32/icorewebview2acceleratorkeypressedeventargs?view=webview2-0.9.430&preserve-view=true#get_handled "get_Handled インターフェイス ICoreWebView2AcceleratorKeyPressedEventArgs |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2AddContentloading]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_contentloading "add_ContentLoading インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2AddHistorychanged]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_historychanged "add_HistoryChanged インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2Addremoteobject]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#addremoteobject "AddRemoteObject-interface ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2AddSourcechanged]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_sourcechanged "add_SourceChanged インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2AddWindowcloserequested]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_windowcloserequested "add_WindowCloseRequested インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2CoreWebview2ScriptDialogKind]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#core_webview2_script_dialog_kind "CORE_WEBVIEW2_SCRIPT_DIALOG_KIND インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2devtoolsprotocoleventreceiver]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-0.9.430&preserve-view=true "インターフェイス ICoreWebView2DevToolsProtocolEventReceiver |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2devtoolsprotocoleventreceiverAddDevtoolsprotocoleventreceived]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-0.9.430&preserve-view=true#add_devtoolsprotocoleventreceived "add_DevToolsProtocolEventReceived インターフェイス ICoreWebView2DevToolsProtocolEventReceiver |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2devtoolsprotocoleventreceiverRemoveDevtoolsprotocoleventreceived]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-0.9.430&preserve-view=true#remove_devtoolsprotocoleventreceived "remove_DevToolsProtocolEventReceived インターフェイス ICoreWebView2DevToolsProtocolEventReceiver |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2environmentGetBrowserversioninfo]: /microsoft-edge/webview2/reference/win32/icorewebview2environment?view=webview2-0.9.430&preserve-view=true#get_browserversioninfo "get_BrowserVersionInfo インターフェイス ICoreWebView2Environment |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2host]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true "インターフェイス ICoreWebView2Host |Microsoft ドキュメント"  
[ReferenceWin3209430Webview2IdlGetcorewebview2browserversioninfo]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.430&preserve-view=true#getcorewebview2browserversioninfo "GetCoreWebView2BrowserVersionInfo-Globals |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2hostGetZoomfactor]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#get_zoomfactor "get_ZoomFactor インターフェイス ICoreWebView2Host |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2hostNotifyparentwindowpositionchanged]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#notifyparentwindowpositionchanged "NotifyParentWindowPositionChanged-インターフェイス ICoreWebView2Host |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2hostPutZoomfactor]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#put_zoomfactor "put_ZoomFactor インターフェイス ICoreWebView2Host |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2hostSetboundsandzoomfactor]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#setboundsandzoomfactor "SetBoundsAndZoomFactor-インターフェイス ICoreWebView2Host |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2httpheaderscollectioniteratorGetHascurrentheader]: /microsoft-edge/webview2/reference/win32/icorewebview2httpheaderscollectioniterator?view=webview2-0.9.430&preserve-view=true#get_hascurrentheader "get_HasCurrentHeader インターフェイス ICoreWebView2HttpHeadersCollectionIterator |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2httprequestheadersGetheaders]: /microsoft-edge/webview2/reference/win32/icorewebview2httprequestheaders?view=webview2-0.9.430&preserve-view=true#getheaders "GetHeaders-インターフェイス ICoreWebView2HttpRequestHeaders |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2httpresponseheadersGetheader]: /microsoft-edge/webview2/reference/win32/icorewebview2httpresponseheaders?view=webview2-0.9.430&preserve-view=true#getheader "GetHeader-インターフェイス ICoreWebView2HttpResponseHeaders |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2Removeremoteobject]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#removeremoteobject "RemoveRemoteObject-インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2settingsGetAreremoteobjectsallowed]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.430&preserve-view=true#get_areremoteobjectsallowed "get_AreRemoteObjectsAllowed インターフェイス ICoreWebView2Settings |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2settingsGetIszoomcontrolenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.430&preserve-view=true#get_iszoomcontrolenabled "get_IsZoomControlEnabled インターフェイス ICoreWebView2Settings |Microsoft ドキュメント"  
[ReferenceWin3209430Icorewebview2webmessagereceivedeventargsTrygetwebmessageasstring]: /microsoft-edge/webview2/reference/win32/icorewebview2webmessagereceivedeventargs?view=webview2-0.9.430&preserve-view=true#trygetwebmessageasstring "TryGetWebMessageAsString-interface ICoreWebView2WebMessageReceivedEventArgs |Microsoft ドキュメント"  

[ReferenceWin3209488Icorewebview2AddFramenavigationcompleted]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#add_framenavigationcompleted "add_FrameNavigationCompleted インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209488Icorewebview2Addhostobjecttoscript]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#addhostobjecttoscript "AddHostObjectToScript-interface ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209488Icorewebview2AddNewwindowrequested]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#add_newwindowrequested "add_NewWindowRequested インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209488Icorewebview2environmentGetBrowserversionstring]: /microsoft-edge/webview2/reference/win32/icorewebview2environment?view=webview2-0.9.488&preserve-view=true#get_browserversionstring " |Microsoft ドキュメント"  
[ReferenceWin3209488Icorewebview2environmentoptions]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions?view=webview2-0.9.488&preserve-view=true "インターフェイス ICoreWebView2EnvironmentOptions |Microsoft ドキュメント"  
[ReferenceWin3209488Icorewebview2experimentalcompositioncontroller]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller?view=webview2-0.9.488-prerelease&preserve-view=true "インターフェイス ICoreWebView2ExperimentalCompositionController |Microsoft ドキュメント"  
[ReferenceWin3209488Icorewebview2experimentalcursorchangedeventhandler]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcursorchangedeventhandler?view=webview2-0.9.488-prerelease&preserve-view=true "インターフェイス ICoreWebView2ExperimentalCursorChangedEventHandler |Microsoft ドキュメント"  
[ReferenceWin3209488Icorewebview2experimentalpointerinfo]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalpointerinfo?view=webview2-0.9.488-prerelease&preserve-view=true "インターフェイス ICoreWebView2ExperimentalPointerInfo |Microsoft ドキュメント"  
[ReferenceWin3209488Icorewebview2Removehostobjectfromscript]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#removehostobjectfromscript "RemoveHostObjectFromScript-interface ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209488Icorewebview2settingsGetAreremoteobjectsallowed]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.488&preserve-view=true#get_areremoteobjectsallowed "get_AreRemoteObjectsAllowed インターフェイス ICoreWebView2Settings |Microsoft ドキュメント"  
[ReferenceWin3209488Icorewebview2settingsGetIsbuiltinerrorpageenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.488&preserve-view=true#get_isbuiltinerrorpageenabled " |Microsoft ドキュメント"  
[ReferenceWin3209488Webview2IdlCreatecorewebview2environmentwithdetails]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.488&preserve-view=true#createcorewebview2environmentwithdetails "CreateCoreWebView2EnvironmentWithDetails-Globals |Microsoft ドキュメント"  
[ReferenceWin3209488Webview2IdlCreatecorewebview2environmentwithoptions]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.488&preserve-view=true#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions-Globals |Microsoft ドキュメント"  
[ReferenceWin3209488Webview2IdlGetavailablecorewebview2browserversionstring]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.488&preserve-view=true#getavailablecorewebview2browserversionstring "GetAvailableCoreWebView2BrowserVersionString-Globals |Microsoft ドキュメント"  

[ReferenceDotnetReference]: /dotnet/api/microsoft.web.webview2.core "WebView2 の名前空間 |Microsoft ドキュメント"  
[ReferenceWpfReference]: /dotnet/api/microsoft.web.webview2.wpf "WebView2 の名前空間 |Microsoft ドキュメント"  
[ReferenceWinformsReference]: /dotnet/api/microsoft.web.webview2.winforms "WinForms 名前空間 WebView2 |Microsoft ドキュメント"  

[ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environment]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment "CoreWebView2Environment クラス (WebView2 の場合) |Microsoft ドキュメント"  
[ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentComparebrowserversions]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.comparebrowserversions "CoreWebView2Environment (文字列, 文字列) メソッド (CompareBrowserVersions () |) |Microsoft ドキュメント"
[ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentGetavailablebrowserversionstring]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.getavailablebrowserversionstring "CoreWebView2Environment: この文字列 (文字列) メソッド (WebView2) を指定します (String) |Microsoft ドキュメント"  
[ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2Newwindowrequested]: /dotnet/api/microsoft.web.webview2.core.corewebview2.newwindowrequested "CoreWebView2 | 要求されたイベント (WebView2) |Microsoft ドキュメント"  
[ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2Permissionrequested]: /dotnet/api/microsoft.web.webview2.core.corewebview2.permissionrequested "CoreWebView2 によって要求されたイベント (WebView2) |Microsoft ドキュメント"  
[ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2Scriptdialogopening]: /dotnet/api/microsoft.web.webview2.core.corewebview2.scriptdialogopening "CoreWebView2: WebView2 イベントを開きます () |Microsoft ドキュメント"  
[ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2Webresourcerequested]: /dotnet/api/microsoft.web.webview2.core.corewebview2.webresourcerequested "CoreWebView2 WebResourceRequested イベント (WebView2 () |Microsoft ドキュメント"  
[ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2httprequestheaders]: /dotnet/api/microsoft.web.webview2.core.corewebview2httprequestheaders "CoreWebView2HttpRequestHeaders クラス (WebView2 の場合) |Microsoft ドキュメント"  
[ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2httpresponseheaders]: /dotnet/api/microsoft.web.webview2.core.corewebview2httpresponseheaders "CoreWebView2HttpResponseHeaders クラス (WebView2 の場合) |Microsoft ドキュメント"  

[ReferenceWin3209538Icorewebview2Addhostobjecttoscript]: /microsoft-edge/webview2/reference/win32/icorewebview2#addhostobjecttoscript?view=webview2-0.9.538&preserve-view=true "AddHostObjectToScript-interface ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin3209538Icorewebview2experimentalAddWebresourceresponsereceived]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-0.9.538-prerelease&preserve-view=true#add_webresourceresponsereceived "add_WebResourceResponseReceived インターフェイス ICoreWebView2Experimental |Microsoft ドキュメント"  
[ReferenceWin3209538Icorewebview2experimentaloptionsGetIssinglesignonusingosprimaryaccountenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalenvironmentoptions?view=webview2-0.9.538-prerelease&preserve-view=true#get_issinglesignonusingosprimaryaccountenabled "get_IsSingleSignOnUsingOSPrimaryAccountEnabled インターフェイス ICoreWebView2ExperimentalEnvironmentOptions |Microsoft ドキュメント"  
[ReferenceWin3209538Icorewebview2experimentalnewwindowrequestedeventargsGetWindowfeatures]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalnewwindowrequestedeventargs?view=webview2-0.9.538-prerelease&preserve-view=true#get_windowfeatures "get_WindowFeatures インターフェイス ICoreWebView2ExperimentalNewWindowRequestedEventArgs |Microsoft ドキュメント"  
[ReferenceWin3209538Icorewebview2experimentalwindowfeatures]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwindowfeatures?view=webview2-0.9.538-prerelease&preserve-view=true "インターフェイス ICoreWebView2ExperimentalWindowFeatures |Microsoft ドキュメント"  
[ReferenceWin3209538Icorewebview2newwindowrequestedeventargsGetIsuserinitiated]: /microsoft-edge/webview2/reference/win32/icorewebview2newwindowrequestedeventargs?view=webview2-0.9.538&preserve-view=true#get_isuserinitiated "get_IsUserInitiated インターフェイス ICoreWebView2NewWindowRequestedEventArgs |Microsoft ドキュメント"  
[ReferenceWin3209538Icorewebview2settingsGetArehostobjectsallowed]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.538&preserve-view=true#get_arehostobjectsallowed "get_AreHostObjectsAllowed インターフェイス ICoreWebView2Settings |Microsoft ドキュメント"  
[ReferenceWin3209538IdlCreatecorewebview2environmentwithoptions]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.538&preserve-view=true#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions-Globals |Microsoft ドキュメント"  

[ReferenceWin3209622Icorewebview2environmentoptionsGetAllowsinglesignonusingosprimaryaccount]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions?view=webview2-0.9.622&preserve-view=true#get_allowsinglesignonusingosprimaryaccount "get_AllowSingleSignOnUsingOSPrimaryAccount インターフェイス ICoreWebView2EnvironmentOptions |Microsoft ドキュメント"  
[ReferenceWin3209622Icorewebview2environmentoptionsPutAdditionalbrowserarguments]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions?view=webview2-0.9.622&preserve-view=true#put_additionalbrowserarguments "put_AdditionalBrowserArguments インターフェイス ICoreWebView2EnvironmentOptions |Microsoft ドキュメント"  
[ReferenceWin3209622Icorewebview2experimentalenvironment]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalenvironment?view=webview2-0.9.622-prerelease&preserve-view=true "インターフェイス ICoreWebView2ExperimentalEnvironment |Microsoft ドキュメント"  
[ReferenceWin3209622Icorewebview2newwindowrequestedeventargsGetWindowfeatures]: /microsoft-edge/webview2/reference/win32/icorewebview2newwindowrequestedeventargs?view=webview2-0.9.622&preserve-view=true#get_windowfeatures "get_WindowFeatures インターフェイス ICoreWebView2NewWindowRequestedEventArgs |Microsoft ドキュメント"  
[ReferenceWin3209622Icorewebview2windowfeatures]: /microsoft-edge/webview2/reference/win32/icorewebview2windowfeatures?view=webview2-0.9.622&preserve-view=true "インターフェイス ICoreWebView2WindowFeatures |Microsoft ドキュメント"  
[ReferenceWin3209622IdlCreatecorewebview2environmentwithoptions]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.622&preserve-view=true#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions-Globals |Microsoft Edge"  

[DeployedgeMicrosoftEdgePolicies]: /deployedge/microsoft-edge-policies "Microsoft Edge-ポリシー |Microsoft ドキュメント"  

[DotnetStandardAssemblyStrongNamed]: /dotnet/standard/assembly/strong-named "厳密な名前付きアセンブリ |Microsoft ドキュメント"  

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
[GithubMicrosoftedgeWebviewfeedbackIssue131]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/131 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ131"
[GithubMicrosoftedgeWebviewfeedbackIssue148]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/148 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ148"  
[GithubMicrosoftedgeWebviewfeedbackIssue179]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/179 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ179"
[GithubMicrosoftedgeWebviewfeedbackIssue181]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/181 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ181"
[GithubMicrosoftedgeWebviewfeedbackIssue183]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/183 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ183"
[GithubMicrosoftedgeWebviewfeedbackIssue185]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/185 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ185"
[GithubMicrosoftedgeWebviewfeedbackIssue228]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/228 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ228"
[GithubMicrosoftedgeWebviewfeedbackIssue235]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/235 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ235"
[GithubMicrosoftedgeWebviewfeedbackIssue293]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/293 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ293"
[GithubMicrosoftedgeWebviewfeedbackIssue318]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/318 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ318"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesPr17]: https://github.com/MicrosoftEdge/WebView2Samples/pull/17 "最新の WebView2 SDK 0.9.430-MicrosoftEdge/WebView2Samples | を使用するようにプロジェクトを移動するGitHub"  
[GithubMicrosoftedgeWebview2samplesApisample]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2APISample "WebView2 API のサンプル-MicrosoftEdge/WebView2Samples |GitHub"  

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
[NuGetGallery0.9.579]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.579 "NuGet ギャラリー |WebView2 v 0.9.579"
[NuGetGallery0.9.622.11]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.622.11 "NuGet ギャラリー |WebView2 v 0.9.622.11"
[NuGetGallery0.9.628-prerelease]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.628-prerelease "NuGet ギャラリー |WebView2 v 0.9.628 プレリリース"  
