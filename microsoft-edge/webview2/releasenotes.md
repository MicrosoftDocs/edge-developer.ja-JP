---
description: Microsoft Edge WebView2 SDK のリリースノート
title: Win32、WPF、および WinForms の Microsoft Edge WebView2 のリリースノート
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: f0be7602bd5fe5cf8ede5158b12cb0b957247c20
ms.sourcegitcommit: 2d2cef9046f85ae731f8aa80b565546fcfe72e90
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2020
ms.locfileid: "11182843"
---
# WebView2 SDK のリリースノート  

WebView2 チームは、6週間のリズムで [WEBVIEW2 SDK][NuGetGallery] を更新します。  製品のお知らせ、追加、変更、Api の変更に関する最新情報については、次の内容を確認してください。  

> [!NOTE]
> NuGet パッケージの更新後に、アプリを再コンパイルします。  

## 1.0.707-プレリリース  

リリース日: 2020 年11月23日  

[NuGet パッケージ][NuGetGallery1.0.707-prerelease] \ |Microsoft Edge の最小バージョン89.0.707.0。  

#### 全般的な情報  

###### 機能  

*   [WebView2 グループポリシー][DeployedgeMicrosoftEdgeWebviewPolicies]が追加されました。  推奨される手順の詳細については、「 [グループポリシーの WebView2][Webview2ConceptsEnterpriseGroupPoliciesForWebview2]」を参照してください。  
*   > [!IMPORTANT]
    > **変更の中断**: 古いレジストリの場所が廃止されました。  
    > 
    > ```text
    > {Root}\Software\Policies\Microsoft\EmbeddedBrowserWebView\LoaderOverride\{AppId}
    > ```  
     
*   WebView2 内の [ドラッグ & ドロップ][ReferenceWin32Icorewebview2experimentalcompositioncontroller3] のサポートが追加されました。  
*   DPI サポートを処理するための Api を追加しました。  
    *   WebView のコンテンツと UI のポップアップ、および関連付けられた[RasterizationScaleChanged][ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210707PrereleaseAddRasterizationscalechanged]イベントの DPI スケールを変更する[RasterizationScale][ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210707PrereleaseGetRasterizationscale]プロパティが追加されました。  
    *   必要に応じて、自動的に [更新される][ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210707PrereleaseGetShouldDetectMonitorScaleChanges] ように、プロパティを設定し `RasterizationScale` ます。  
    *   境界がロジックピクセルであり、WebView で for WebView2 pixels ディスプレイを使用できることを指定して、 [BoundsMode プロパティ][ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210707PrereleaseGetBoundsMode] を追加して `RasterizationScale` `RasterizationScale` 物理サイズを取得するには、をに適用し `Bounds` ます。
*   `NewWindowRequested`処理するイベントが更新されました `Ctrl` + `click` `Shift` + `click` 。  \ ([\ #168][GithubMicrosoftedgeWebviewfeedbackIssue168] と [\ #371][GithubMicrosoftedgeWebviewfeedbackIssue371]\)。  

#### .NET  

###### 機能  

* .NET Core 3.1 + および .NET 5 の WinForms designer を有効にしました。  
* .NET cookie 管理が改善されました。  \ ([\ #611][GithubMicrosoftedgeWebviewfeedbackIssue611]\)  

###### バグ修正

*   WebView2 で Automationproperties.acceleratorkey をサポートする [AcceleratorKeyPressed][DotnetApiMicrosoftWebWebview2WpfWebview2Acceleratorkeypressed] イベントが追加されました。  \ ([\ #288][GithubMicrosoftedgeWebviewfeedbackIssue288]\)  
*   WebView2 フォルダーへの出力から不要なファイルが削除されました。  \ ([\ #461][GithubMicrosoftedgeWebviewfeedbackIssue461]\)  
*   改善されたホストオブジェクト API。  \ ([\ #335][GithubMicrosoftedgeWebviewfeedbackIssue335] と [\ #525][GithubMicrosoftedgeWebviewfeedbackIssue525]\)。  

## 1.0.664.37  

リリース日: 2020 年11月20日  

[NuGet パッケージ][NuGetGallery1.0.664.37] \ |WebView2 の最小ランタイムバージョン86.0.664.37。  

#### 全般的な情報  

> [!IMPORTANT]
> **お知らせ**: .net WPF/WinForms WebView2 は、一般に \ (GA) で利用できるようになりました。  このリリース以降、リリース Sdk は上位互換性があります。  詳細については、「 [GA お知らせブログの投稿][MicrosoftDevblogDotnetAnnouncingGeneralAvailabilityForMicrosoftEdgeWebview2ForNetFixedDistributionMethod]」を参照してください。  

###### 機能  

*   .NET WPF/WinForms WebView2 は、一般に \ (GA) で利用できるようになりました。  
*   固定配布 \ (所有権の取り込み) モードが GA になりました。  

#### .NET  

###### バグ修正  

*   `CoreWebView2NewWindowRequestedEventArgs.Handled` 新しいウィンドウを開くことができないようにします \ ([\ #549][GithubMicrosoftedgeWebviewfeedbackIssue549]\) と \ ([\ #560][GithubMicrosoftedgeWebviewfeedbackIssue560]\)  


## 1.0.674-プレリリース  

リリース日: 2020 年10月19日  

[NuGet パッケージ][NuGetGallery1.0.674-prerelease] \ |WebView2 の最小ランタイムバージョン86.0.616.0。  

#### 全般的な情報  

*   ナビゲーション中に投稿データまたは追加の要求ヘッダーを提供できる [NavigateWithWebResourceRequest][ReferenceWin32Icorewebview2experimentalNavigatewithwebresourcerequest10674] メソッドが追加されました。
*   初期 HTML ドキュメントが読み込まれて解析されるときに実行される [Domcontentloaded][ReferenceWin32Icorewebview2experimentalAddDomcontentloaded10674] イベントが追加されました。
*   WebView2 の [環境][ReferenceWin32Icorewebview2experimentalGetEnvironment10674] プロパティが追加されました。  このプロパティは、WebView2 のインスタンスが作成された WebView2 環境を公開します。
*   開発者が WebView2 セッションを認証したり、WebView からの cookie を取得して他のツールを認証したりできる [cookie 管理][ReferenceWin32Icorewebview2experimentalGetCookiemanager10674] api が追加されました。  言語/フレームワーク固有の改善を計画しています。  詳細については、「 [API レビュー: Cookie 管理][GithubMicrosoftedgeWebview2AnnouncementIssue2]」を参照してください。
*   [WebResourceResponseReceived][ReferenceWin32Icorewebview2experimentalAddWebresourceresponsereceived10674]イベントが更新され、不変の[WebResourceResponseView][ReferenceWin32Icorewebview2experimentalwebresourceresponseview10674]と WebResourceResponseReceivedEventArgs が追加されました[:P。 Opulaterの OnGetContent][ReferenceWin32Icorewebview2experimentalwebresourceresponsereceivedeventargsPopulateresponsecontent09628]は[WebResourceResponseView::][ReferenceWin32Icorewebview2experimentalwebresourceresponseviewGetcontent10674]になります。
*   WebView2 の [Microsoft Defender Application Guard (WDAG)][WindowsSecurityThreatProtectionMicrosoftDefenderApplicationGuardWindows10] をオフにします。
*   ビジュアルホスティング用の [systemの id][ReferenceWin32Icorewebview2experimentalcompositioncontroller2GetSystemcursorid10674] が追加されました。
*   ビジュアルホスティングで入力方式に修正されたバグを追加しました。
*   WebView2 スタティックライブラリを使用する場合、開発者はバージョン .lib を含める必要がなくなりました。

#### .NET  

*   CoreWebView2Environment 変数を公開するために [CoreWebView2][DotnetApiMicrosoftWebWebview2CoreCorewebview2] クラスが更新されました。  
*   名前空間のカスタム EventArgs クラスの実装 `Microsoft.Web.WebView2.Core` が、system.componentmodel.annotations また[System.EventArgs][DotnetApiSystemEventargs]は[CancelEventArgs][DotnetApiSystemComponentmodelCancelEventargs]のサブクラスとして変更されました。  \ ([\ #250][GithubMicrosoftedgeWebviewfeedbackIssue250]\)  
*   WinForms での [CoreWebView2CreationProperties][DotnetApiMicrosoftWebWebview2Winforms] のサポートが追加されました。  \ ([\ #204][GithubMicrosoftedgeWebviewfeedbackIssue204]\)
*   .NET [WebResourceRequested][DotnetApiMicrosoftWebWebview2CoreCorewebview2Webresourcerequested] api が追加されました。  \ ([\ #219][GithubMicrosoftedgeWebviewfeedbackIssue219]\)  
*   WinForms Designer [Source][DotnetApiMicrosoftWebWebview2WinformsWebview2Source] プロパティが default に更新されたか、null にリセットされました。  \ ([\ #177][GithubMicrosoftedgeWebviewfeedbackIssue177]\)  
*   100% 未満の DPI モードをサポートするために WebView2.Init () の WebView2 境界が更新されました。  \ ([\ #432][GithubMicrosoftedgeWebviewfeedbackIssue432]\)  
*   強化された [buildwindowcore][DotnetApiMicrosoftWebWebview2WpfWebview2Buildwindowcore] と [destroywindowcore][DotnetApiMicrosoftWebWebview2WpfWebview2Destroywindowcore] の信頼性が向上しました。  \ ([\ #382][GithubMicrosoftedgeWebviewfeedbackIssue382]\)  
*   オペレーティングシステムアーキテクチャの代わりにプロセスビットに読み込むように .NET ローダーベースを更新しました。  \ ([\ #431][GithubMicrosoftedgeWebviewfeedbackIssue431]\)  
*   `EdgeNotFoundExpection` [WebView2RuntimeNotFoundException][DotnetApiMicrosoftWebWebview2CoreWebview2runtimenotfoundexception]に名前が変更されます。
 
## 1.0.622.22  

リリース日: 2020 年10月19日  

[NuGet パッケージ][NuGetGallery1.0.622.22] \ |WebView2 の最小ランタイムバージョン86.0.616.0。  

#### 全般的な情報  

> [!IMPORTANT]
> **お知らせ**: Win32 C/c + + WebView2 は、一般に \ (GA) で利用できるようになりました。  このリリース以降、リリース Sdk は上位互換性があります。  詳細については、「 [GA お知らせブログの投稿][WindowsBlogsMsedgedevEdgeWebview2GeneralAvailability]」を参照してください。  

*  [Evergreen WebView2 Runtime と installer][Webview2ConceptsDistributionUnderstandRuntimeInstaller] は GA です。  ブートストラップ、ブートストラップのダウンリンク、Evergreen ランタイムのスタンドアロンインストーラーは、 [Microsoft Edge WebView2][MicrosoftDeveloperMicrosoftEdgeWebView2]で利用できます。  インストールワークフローのサンプルコードは、 [WebView2Samples リポジトリ][GithubMicrosoftedgeWebview2samplesMain]でも利用できます。  
*  [修正バージョンモード][Webview2ConceptsDistributionFixedVersionMode] は、開発者向けプレビューで利用できます。  

## 0.9.628-プレリリース  

リリース日: 2020 年9月10日  

[NuGet パッケージ][NuGetGallery0.9.628-prerelease] \ |Microsoft Edge の最小バージョン86.0.616.0。  

> [!IMPORTANT]
> **お知らせ**: このプレリリースは、Microsoft Edge 87 ブランチに基づいてリリースされ続けます。  今後、プレリリース SDK のリリースが Microsoft edge のバージョンと一致しています。通常のリリースは Microsoft Edge の厩舎と同期されています。  

#### 全般的な情報  

*   > [!IMPORTANT]
    > **お知らせ**: ビジュアルホスティング api が [プレビュー] の下に表示されます。  WebView2 は、HWNDs に対してではなく、Visual のホスティングを使って WinComp/DComp のビジュアルと共に実行します。  インターフェイスは実験的なものです。  詳細については、 [ICoreWebView2ExperimentalEnvironment][ReferenceWin32Icorewebview2experimentalenvironment09628]に移動してください。  

#### .NET  

*   .NET バイナリには [、厳密な名前が付け][DotnetStandardAssemblyStrongNamed]られています。  \ ([\ #181][GithubMicrosoftedgeWebviewfeedbackIssue181]\)  
*   対象となる NuGet ターゲットが更新されました `WebViewLoader2.dll` 。  \ ([\ #228][GithubMicrosoftedgeWebviewfeedbackIssue228]\) と \ ([\ #183][GithubMicrosoftedgeWebviewfeedbackIssue183]\)  
*   `WebResourceRequested`.Net で[HttpRequestHeaders][DotnetApiMicrosoftWebWebview2CoreCorewebview2httprequestheaders]と[HttpResponseHeaders][DotnetApiMicrosoftWebWebview2CoreCorewebview2httpresponseheaders]の api を公開するように更新されました。  \ ([\ #131][GithubMicrosoftedgeWebviewfeedbackIssue131]\)  

## 0.9.622.11  

リリース日: 2020 年9月10日  

[NuGet パッケージ][NuGetGallery0.9.622.11] \ |WebView2 の最小ランタイムバージョン86.0.616.0。  

#### 全般的な情報  

*   > [!IMPORTANT]
    > **アナウンスメント**: この SDK は、WebView2 Win32 C/c + + GA のリリース候補です。  GA バージョンでは、同じ API インターフェイスと機能を使用する必要があります。  

*   切断された [ブラウザーポリシー][DeployedgeMicrosoftEdgePolicies]。  
*   WebView2 環境オプションの [AllowSingleSignOnUsingOSPrimaryAccount][ReferenceWin32Icorewebview2environmentoptionsGetAllowsinglesignonusingosprimaryaccount09622] プロパティを追加して、WebView の条件付きアクセスを有効にします。  
*   `ICoreWebView2NewWindowRequestedEventArgs` [Windowfeatures][ReferenceWin32Icorewebview2newwindowrequestedeventargsGetWindowfeatures09622]プロパティと関連付けられた[ICoreWebView2WindowFeatures][ReferenceWin32Icorewebview2windowfeatures09622]を含むように更新されました。  \ ([\ #293][GithubMicrosoftedgeWebviewfeedbackIssue293]\)  
*   `System.Windows.Rect` `System.Drawing.Rectangle` `System.Windows.Rect` \ ([\ #235][GithubMicrosoftedgeWebviewfeedbackIssue235]\) の代わりにを使用するように更新されました。  
*   パラメーターのない要求を処理するために、NewWindowRequested イベントが更新されました `window.open()` 。  \ ([\ #293][GithubMicrosoftedgeWebviewfeedbackIssue293]\)  
*   を使用して設定した[Additionalbrowserarguments 引数][ReferenceWin32Icorewebview2environmentoptionsPutAdditionalbrowserarguments09622] `ICoreWebView2EnvironmentOptions` は、環境変数またはレジストリ値で上書きされません。  詳細については、 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32IdlCreatecorewebview2environmentwithoptions09622]に移動してください。  

## 0.9.579  

リリース日: 2020 年7月20日  

[NuGet パッケージ][NuGetGallery0.9.579] \ |Microsoft Edge の最小バージョン86.0.579.0。  

#### 全般的な情報  

*   > [!IMPORTANT]
    > **お知らせ**: Evergreen WebView2 Runtime と installer がプレビュー用にリリースされました。  詳細については、[WebView2 の配布] [Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview] に移動します。  
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
*   WebView でポップアップブロックが無効になりました。  詳細については、イベントの [Isuserinitiated][ReferenceWin32Icorewebview2newwindowrequestedeventargsGetIsuserinitiated09538] プロパティに移動し `NewWindowRequested` ます。  
*   WebView ナビゲーションの開始イベントが発生することを確認 `about:blank` します。  ここでは、 `NavigationStarting` すべてのナビゲーションについてイベントが発生しますが、 `about:blank` または iframe の取り消しまたは iframe のキャンセルはサポートされません。  
*   `edge:// URI`WebView でブロックされたスキーム。  
*   WebView2 環境オプションに、WebView の条件付きアクセスを有効にする実験的な [IsSingleSignOnUsingOSPrimaryAccountEnabled][ReferenceWin32Icorewebview2experimentaloptionsGetIssinglesignonusingosprimaryaccountenabled09538] プロパティが追加されました。  
*   WebView が WebResource 要求に対する応答を受信して処理した後に発生する実験的な [WebResourceResponseReceived][ReferenceWin32Icorewebview2experimentalAddWebresourceresponsereceived09538] イベントが追加されました。  応答オブジェクトに認証ヘッダーが含まれている場合は、そのヘッダーが含まれます。  

#### .NET  

*   WPF フォーカス処理が改善されました。  \ ([\ #185][GithubMicrosoftedgeWebviewfeedbackIssue185]\)  
*   WPF Webview2 コントローラーのプロパティが追加されました `ZoomFactor` 。  

## 0.9.538  

[NuGet パッケージ][NuGetGallery0.9.538] \ |Microsoft Edge の最小バージョン85.0.538.0。  

#### 全般的な情報  

*   WebView2 SDK バージョン [0.8.149](#08149)のサポートを削除しています。  WebView2 では、最新バージョンの WebView2 を使用して最新の状態を維持することをお勧めします。  
*   Microsoft Edge ブラウザーのプロファイルパスが変更されたときにアカウントに対してグループポリシーが更新されました。 \ ([#179][GithubMicrosoftedgeWebviewfeedbackIssue179]\)。  

#### Win32 C/c + +  

*   [ICoreWebView2ExperimentalNewWindowRequestedEventArgs:: get_WindowFeatures][ReferenceWin32Icorewebview2experimentalnewwindowrequestedeventargsGetWindowfeatures09538]が追加されました `window.open()` 。実行され、 [ICoreWebView2ExperimentalWindowFeatures][ReferenceWin32Icorewebview2experimentalwindowfeatures09538] \ ([#70][GithubMicrosoftedgeWebviewfeedbackIssue70]\) に関連付けられたときに発生します。  
*   > [!IMPORTANT]
    > **変更の中断**: 廃止された [CreateCoreWebView2EnvironmentWithDetails][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithdetails09488] 、[CreateCoreWebView2EnvironmentWithOptions] [[ReferenceWin32IdlCreatecorewebview2environmentwithoptions09538]] に置き換えます。  
*   > [!IMPORTANT]
    > **変更の中断**: WebView2 API が Windows api の名前付け規則に合わせて配置されるようにするために、WebView チームは次の名前を更新しました。  
    > *   [AreRemoteObjectsAllowed][ReferenceWin32Icorewebview2settingsGetAreremoteobjectsallowed09488] は、次のように [使用でき][ReferenceWin32Icorewebview2settingsGetArehostobjectsallowed09538]ます。  
*   [Addhostobjecttoscript][ReferenceWin32Icorewebview2Addhostobjecttoscript09538]が更新され、元のホストオブジェクトシリアライザーのマーカーがプロキシオブジェクトに設定され、JavaScript コールバックのパラメーターとしてシリアル化された ([#148][GithubMicrosoftedgeWebviewfeedbackIssue148]\)  

#### .NET (0.9.538 プレリリース版)  

*   WinForms と WPF WebView2API のサンプルをリリースしました。これは WebView2 SDK の包括的なガイドです。  詳細については、「 [サンプルリポジトリ][GithubMicrosoftedgeWebview2samplesMain]」を参照してください。  
*   ビジュアルホスト機能と window 機能の [実験的な api][ConceptsVersioningExperimentalApis]のサポートが追加されました。  
*   > [!IMPORTANT]
    > **変更の中断**: 次の保留は IDisposable: [scriptWebResourceRequested 始値][DotnetApiMicrosoftWebWebview2CoreCorewebview2Scriptdialogopening]、 [newwindowrequested][DotnetApiMicrosoftWebWebview2CoreCorewebview2Newwindowrequested]、 [WebResourceRequested][DotnetApiMicrosoftWebWebview2CoreCorewebview2Webresourcerequested]、および[permissionrequested][DotnetApiMicrosoftWebWebview2CoreCorewebview2Permissionrequested]実装するようになりました。  
*   [GetCompareBrowserVersions の文字列][DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentGetavailablebrowserversionstring]と[CompareBrowserVersions][DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentComparebrowserversions]を[CoreWebView2Environment][DotnetApiMicrosoftWebWebview2CoreCorewebview2environment]の静的として追加しました。  

## 0.9.515-プレリリース  

[NuGet パッケージ][NuGetGallery0.9.515-prerelease] \ |Microsoft Edge の最小バージョン84.0.515.0。  

*   > [!IMPORTANT]
    > **アナウンスメント**: WebView2 では、.net Framework 4.6.2 以降および .net Core 3.0 以降の Windows フォームと WPF が **プレリリースパッケージ**でサポートされるようになりました。  
*   WPF アプリケーションの構築の詳細については、「 [Wpf 入門ガイド」][GettingstartedWpf] と「wpf 固有の Api の WebView2 [wpf リファレンス][DotnetApiMicrosoftWebWebview2Wpf] 」を参照してください。  
*   Windows フォームアプリケーションの構築の詳細については、windows forms の「 [ファーストステップガイド」][GettingstartedWinforms] と「windows フォーム固有の api 用の WebView2 [Windows フォームリファレンス][DotnetApiMicrosoftWebWebview2Winforms] 」を参照してください。  
*   CoreWebView2 Api の詳細については、「 [.Net リファレンス][DotnetApiMicrosoftWebWebview2Core]」を参照してください。  
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
    > *   [GetCoreWebView2BrowserVersionInfo][ReferenceWin32Webview2IdlGetcorewebview2browserversioninfo09430] は [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring09488]になりました。  
    > *   [get_BrowserVersionInfo][ReferenceWin32Icorewebview2environmentGetBrowserversioninfo09430] が [get_BrowserVersionString][ReferenceWin32Icorewebview2environmentGetBrowserversionstring09488]ました。  
    > *   [Addremoteobject][ReferenceWin32Icorewebview2Addremoteobject09430] は [Addhostobjecttoscript][ReferenceWin32Icorewebview2Addhostobjecttoscript09488]になりました。  
    > *   [RemoveRemoteObject][ReferenceWin32Icorewebview2Removeremoteobject09430] が [Removehostobjectfromscript][ReferenceWin32Icorewebview2Removehostobjectfromscript09488]になりました。  
    > *   `chrome.webview.remoteObjects` は現在 `chrome.webview.hostObjects` です。  
*   > [!IMPORTANT]
    > **変更の中断**: `AddRemoteObject` JS プロキシメソッドも名前が変更されます。  
    > *   `getLocal` は現在 `getLocalProperty` です。  
    > *   `setLocal` は現在 `setLocalProperty` です。  
    > *   `getRemote` は現在 `getHostProperty` です。  
    > *   `setRemote` は現在 `setHostProperty` です。  
    > *   `applyRemote` は現在 `applyHostFunction` です。  
*   > [!IMPORTANT]
    > **変更の中断**: 廃止された [CreateCoreWebView2EnvironmentWithDetails][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithdetails09488] 。 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions09488]に置き換えられます。  
*   [FrameNavigationCompleted][ReferenceWin32Icorewebview2AddFramenavigationcompleted09488]イベントが追加されました。  これで、iframe がナビゲーションを完了するときに、イベントが発生し、ナビゲーションとナビゲーション ID の成功が返されます。  
*   アプリケーションがターゲットとする WebView2 ランタイムのバージョンを判断するために使用される [ICoreWebView2EnvironmentOptions][ReferenceWin32Icorewebview2environmentoptions09488] インターフェイスが追加されました。  
*   [IsBuiltInErrorPageEnabled][ReferenceWin32Icorewebview2settingsGetIsbuiltinerrorpageenabled09488]設定が追加されました。  これで、ナビゲーションエラーとレンダープロセスエラーについて、組み込みのエラーページを有効または無効にすることができます。  
*   .NET の実装をサポートするためにリモートオブジェクトの挿入が更新されました `IDispatch` \ ([#113][GithubMicrosoftedgeWebviewfeedbackIssue113]\)。  
*   コンテキストメニュー \ ([#108][GithubMicrosoftedgeWebviewfeedbackIssue108]\) からの要求を処理するために、 [newwindowrequested][ReferenceWin32Icorewebview2AddNewwindowrequested09488]イベントが更新されました。  
*   Visual ホスティング Api にアクセスできる、最初の個別の WebView2 プレリリースパッケージがリリースされました。  WebView チーム [が更新され、][GithubMicrosoftedgeWebview2samplesMain] 新しい実験的な api が追加されました。  
    *   [ICoreWebView2ExperimentalCompositionController][ReferenceWin32Icorewebview2experimentalcompositioncontroller09488]インターフェイスを追加して、コンポジションツリーに接続し、WebView の入力を指定します。  
    *   からのすべての情報が含まれている [ICoreWebView2ExperimentalPointerInfo][ReferenceWin32Icorewebview2experimentalpointerinfo09488]が追加されました `POINTER_INFO` 。  このオブジェクトは、WebView にポインター入力を挿入するために、Sendpointer 入力に渡されます。  
    *   [ICoreWebView2ExperimentalCursorChangedEventHandler][ReferenceWin32Icorewebview2experimentalcursorchangedeventhandler09488]を追加しました。 WebView にマウスカーソルを合わせたときに、アプリに通知されます。  WebView のテキストボックス上にマウスを移動すると、カーソルが矢印からセレクターに変わります。  上のプロパティは、 `cursor` `CompositionController` WebView のマウスカーソルが現在どのようなものであるかをアプリに通知します。  

## 0.9.430  

[NuGet パッケージ][NuGetGallery0.9.430] \ |Microsoft Edge の最小バージョン82.0.430.0。  

WebView2 SDK は、フィードバックからいくつかの機能要求を取り入れた、Win32 の公式バージョンである Win32 C++ ベータバージョンです。  WebView チームは、変更を反映させるリリースの数を制限しようとします。  一般的な可用性については、いくつかの重要な変更がベータ版に組み込まれています。  

*   > [!IMPORTANT]
    > **変更の中断**: 最終リリースでは、WebView2 Api が Windows api の名前付け規則に合わせて配置されるように、WebView チームはプレフィックス *IWebView2WebView*   を *ICoreWebView2*   に変更します。  さらに、WebView2 SDK を UI フレームワークから利用するために、WebView チームは `ICoreWebView2` [ICoreWebView2][ReferenceWin32Icorewebview209430] と [ICoreWebView2Host][ReferenceWin32Icorewebview2host09430]に分かれています。  `ICoreWebView2Host` ウィンドウのサイズ変更、表示/非表示、フォーカスなど、ウィンドウとコンポジションに関連する機能をサポートします。  ICoreWebView2 は、その他のすべての WebView2 機能をサポートしています。  変更の反映の詳細については、WebView2 [Apisample][GithubMicrosoftedgeWebview2samplesMain]プロジェクトの[pull 要求][GithubMicrosoftedgeWebview2samplesPr17]に移動してください。  
*   > [!IMPORTANT]
    > **変更の中断**: [sourcechanged][ReferenceWin32Icorewebview2AddSourcechanged09430]、 [Contentloading][ReferenceWin32Icorewebview2AddContentloading09430]、[履歴が変更された][ReferenceWin32Icorewebview2AddHistorychanged09430] [DocumentStateChanged][ReferenceWin32Iwebview2webviewAddDocumentstatechanged08190]を3つのコンポーネントに分割します。  これで、ソースの URL が変更されたときに、 `SourceChanged` イベントが発生します。  履歴の状態が変更されると、 `HistoryChanged` イベントが発生します。  `ContentLoading`新しいドキュメントを読み込むときに、最初のスクリプトの前にイベントが発生します。  
*   ARM64 アーキテクチャのサポートが追加されました。  
*   タッチスクリーンデバイスのソフト入力パネル \ (SIP) サポートを追加しました。  
*   Windows server 2008 R2、Windows Server 2012、Windows Server 2012 R2、Windows Server 2016 のサポートが追加されました。  
*   [NotifyParentWindowPositionChanged][ReferenceWin32Icorewebview2hostNotifyparentwindowpositionchanged09430]が追加されました。これにより、ウィンドウモードでステータスバーをウィンドウに表示することができます。  また、アクセシビリティ機能を使用するために、この変更をウィンドウレスモードで実装します。  
*   任意のリモートオブジェクトからページにアクセスできるかどうかをグローバル制御するための [AreRemoteObjectsAllowed][ReferenceWin32Icorewebview2settingsGetAreremoteobjectsallowed09430] 設定が追加されました。  既定で `AreRemoteObjectsAllowed` は、有効になります。 [Addremoteobject][ReferenceWin32Icorewebview2Addremoteobject09430] によって追加されたリモートオブジェクトは、ページからアクセスできます。  無効にすると、 `AreRemoteObjectsAllowed` ページからオブジェクトにアクセスできなくなります。  変更は次のナビゲーションイベントに適用されます。  
*   [IsZoomControlEnabled][ReferenceWin32Icorewebview2settingsGetIszoomcontrolenabled09430]設定を追加して、ユーザーが WebView `ctrl` + `+` と `ctrl` + `-` \ (または `ctrl` + マウスホイール \) のズームに影響しないようにします。  設定を無効にすると、 [put_ZoomFactor][ReferenceWin32Icorewebview2hostPutZoomfactor09430] を使用してズームを設定することができます。  
*   現在の WebView にのみ適用されるように変更された ZoomFactor。  現在の WebView のズームの変更は、元のサイトに移動した他の WebViews には影響しません。  詳細については、 [get_ZoomFactor][ReferenceWin32Icorewebview2hostGetZoomfactor09430]に移動してください。  
*   WebView \ ([#95][GithubMicrosoftedgeWebviewfeedbackIssue95]\) の HID ZoomView UI。  
*   [SetBoundsAndZoomFactor][ReferenceWin32Icorewebview2hostSetboundsandzoomfactor09430]が追加されました。  この時点で、WebView のズーム率と境界を同時に設定できます。  
*   [WindowCloseRequested][ReferenceWin32Icorewebview2AddWindowcloserequested09430]イベントが追加されました。  詳細については、 [add_WindowCloseRequested][ReferenceWin32Icorewebview2AddWindowcloserequested09430] \ ([#119][GithubMicrosoftedgeWebviewfeedbackIssue119]\) に移動してください。  
*   JavaScript ダイアログイベントのダイアログ型のサポートが追加され、 `beforeunload` 列挙型エントリ [CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_BEFOREUNLOAD][ReferenceWin32Icorewebview2CoreWebview2ScriptDialogKind09430] 追加されました。  
*   HttpRequestHeaders、 [GetHeader][ReferenceWin32Icorewebview2httpresponseheadersGetheader09430] 、HttpResponseHeaders、 [Get_HasCurrentHeader][ReferenceWin32Icorewebview2httpheaderscollectioniteratorGetHascurrentheader09430]プロパティに[GetHeaders][ReferenceWin32Icorewebview2httprequestheadersGetheaders09430]を httpheaderscollectioniterator に追加しました。  
*   > [!IMPORTANT]
    > **変更の中断**: 動作が変更されました `DevToolsProtocolEventReceived` 。  次に、 [add_DevToolsProtocolEventReceived][ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverAddDevtoolsprotocoleventreceived09430]remove_DevToolsProtocolEventReceived を使用して、特定の devtools プロトコルイベント用の[DevToolsProtocolEventReceiver][ReferenceWin32Icorewebview2devtoolsprotocoleventreceiver09430]を作成し、そのイベントをサブスクライブまたはサブスクライブ解除することができ / [remove_DevToolsProtocolEventReceived][ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverRemoveDevtoolsprotocoleventreceived09430]ます。
*   > [!IMPORTANT]
    > **変更の中断**: `WebMessageReceivedEventArgs` [Get_WebMessageAsString][ReferenceWin32Iwebview2webmessagereceivedeventargsGetWebmessageasstring08190] プロパティが [trygetwebmessageasstring][ReferenceWin32Icorewebview2webmessagereceivedeventargsTrygetwebmessageasstring09430] メソッドに変更されました。  
*   > [!IMPORTANT]
    > **変更の中断**: `AcceleratorKeyPressedEventArgs` [get_Handled][ReferenceWin32Icorewebview2acceleratorkeypressedeventargsGetHandled09430]プロパティに[ハンドル][ReferenceWin32Iwebview2acceleratorkeypressedeventargsHandle08190]メソッドを変更しました。  

## 0.8.355

[NuGet パッケージ][NuGetGallery0.8.355] \ |Microsoft Edge の最小バージョン80.0.355.0。

*   WebView2 SDK の包括的なガイドである WebView2API サンプルをリリースしました。  詳細については、「 [Apisample][GithubMicrosoftedgeWebview2samplesApisample]」」を参照してください。  
*   英語 \ ([#30][GithubMicrosoftedgeWebviewfeedbackIssue30]\) 以外のすべての言語で IME のサポートが追加されました。  
*   バグレポートに対応してイベントの API サーフェスが更新されました `WebResourceRequested` 。  作成時にフィルターとイベントを同時に指定することは推奨されなくなりました。  Web リソース要求イベントを作成するには、 [add_WebResourceRequested][ReferenceWin32Iwebview2webview5AddWebresourcerequested08190] を使ってイベントと [AddWebResourceRequestedFilter][ReferenceWin32Iwebview2webview5Addwebresourcerequestedfilter08190] を追加し、フィルターを追加します。  [RemoveWebResourceRequestedFilter][ReferenceWin32Iwebview2webview5Removewebresourcerequestedfilter08190] はフィルター \ ([#36][GithubMicrosoftedgeWebviewfeedbackIssue36]\) \ ([#74][GithubMicrosoftedgeWebviewfeedbackIssue74]\) を削除します。  
*   > [!IMPORTANT]
    > **変更の中断**: 全画面の動作が変更されました。  廃止 [された Isfullscreenallowed 許可さ][ReferenceWin32Iwebview2settingsGetIsfullscreenallowedDeprecated08190]れました。  既定では、WebView \ (ビデオなど) の要素が全画面表示に設定されている場合、WebView の境界がいっぱいになります。  要素が全画面モードに入る場合に、アプリで WebView のサイズを変更する方法を指定するには、 [Fullfullscreenelementchanged][ReferenceWin32Iwebview2containsfullscreenelementchangedeventhandler08190] イベントと [get_ContainsFullScreenElement][ReferenceWin32Iwebview2webview5GetContainsfullscreenelement08190] を使います。  

## 0.8.314  

[NuGet パッケージ][NuGetGallery0.8.314] \ |Microsoft Edge の最小バージョン80.0.314.0。  

*   Windows 7、Windows 8、Windows 8.1 のサポートが追加されました。  
*   Visual Studio と Visual Studio のコードデバッグサポートを WebView2 に追加しました。  次に、IDE から直接 WebView2 のスクリプトをデバッグします。  詳細については、「 [WebView2 コントロールを使用して開発するときにデバッグする方法][HowtoDebug]」を参照してください。  
*   追加されました `Native Object Injection` 。これにより、WebView2 内で実行されるスクリプトは、アプリケーションの Win32 コンポーネントから idispatch オブジェクトにアクセスし、idispatch オブジェクトのプロパティにアクセスすることができます。  詳細については、 [Addremoteobject][ReferenceWin32Iwebview2webview4Addremoteobject08190] \ ([#17][GithubMicrosoftedgeWebviewfeedbackIssue17]\) に移動します。  
*   追加された `AcceleratorKeyPressed` イベント。  詳細については、 [add_AcceleratorKeyPressed][ReferenceWin32Iwebview2webview4AddAcceleratorkeypressed08190] \ ([#57][GithubMicrosoftedgeWebviewfeedbackIssue57]\) に移動してください。  
*   無効 `Context Menus` 。  詳細については、 [put_AreDefaultContextMenusEnabled][ReferenceWin32Iwebview2settings2PutAredefaultcontextmenusenabled08190] \ ([#57][GithubMicrosoftedgeWebviewfeedbackIssue57]\) に移動してください。  
*   更新されました `DPI Awareness` 。  これで、WebView の DPI 認識は、ホストアプリケーションの DPI 認識と同じになります。  
    
    > [!NOTE]
    > 別のハイブリッドアプリケーションを起動したときに、元の WebView と異なる DPI 認識が適用されている場合は、ユーザーデータディレクトリが同じ \ ([#1][GithubMicrosoftedgeWebviewfeedbackIssue1]\) である場合、新しい WebView は起動されません。  
    
*   更新された `Notification Change Behavior` ため、WebView2 は、WebView 内でホストされている web コンテンツによって求められる通知アクセス許可要求を自動的に拒否します  

## 0.8.270  

[NuGet パッケージ][NuGetGallery0.8.270] \ |Microsoft Edge の最小バージョン78.0.270.0。  

*   `DocumentTitleChanged`ドキュメントタイトルの変更 \ ([\ #27][GithubMicrosoftedgeWebviewfeedbackIssue27]\) を示すイベントが追加されました。  
*   `GetWebView2BrowserVersionInfo`API \ ([\ #18][GithubMicrosoftedgeWebviewfeedbackIssue18]\) を追加しました。  
*   追加された `NewWindowRequested` イベント。  
*   `CreateWebView2EnvironmentWithDetails`削除する関数が更新されました `releaseChannelPreference` 。  関数の詳細については `CreateWebView2EnvironmentWithDetails` 、 [CreateWebView2EnvironmentWithDetails][ReferenceWin32WebView2IdlCreatewebview2environmentwithdetails08190]に移動してください。  レジストリと環境変数の上書きは引き続きサポートされます。  既定のチャネルの設定が使用されます。上書きされていない場合。  
    チャネルの検索時に、WebView チームは、WebView2 SDK と互換性のない以前のチャネルバージョンをスキップします。  
    WebView チームは、より安定したチャネルを選択して、エンドユーザーに対して最も一貫性のある動作を実現します。  最新のカナリアビルドを使ってテストする場合は、アプリを起動する `WEBVIEW2_RELEASE_CHANNEL_PREFERENCE` 前に環境変数を設定するスクリプトを作成する必要があり `1` ます。  
*   `CreateWebView2EnvironmentWithDetails` `userDataFolder` 指定されていない場合に選択するためのロジックで関数が更新されました。  関数の詳細については `CreateWebView2EnvironmentWithDetails` 、 [CreateWebView2EnvironmentWithDetails][ReferenceWin32WebView2IdlCreatewebview2environmentwithdetails08190]に移動してください。  以前に既定の場所を使用していた場合は、 `userDataFolder` 新しい SDK に切り替えると既定値 `userDataFolder` (host code ディレクトリ内の新しい場所に設定) がリセットされ、状態もリセットされます。  
    指定したディレクトリに書き込むためのアクセス許可がホストプロセスにない場合、この `CreateWebView2EnvironmentWithDetails` 関数は失敗することがあります。  古いユーザーデータディレクトリから新しいディレクトリにデータをコピーすることができます。  

## 0.8.230  

[NuGet パッケージ][NuGetGallery0.8.230] \ |Microsoft Edge の最小バージョン77.0.230.0。  

*   `Stop`すべてのナビゲーションおよび保留中のリソースフェッチを停止するための API を追加しました \ ([\ #28][GithubMicrosoftedgeWebviewfeedbackIssue28]\)。  
*   `.tlb`ファイルが NuGet パッケージ \ ([\ #22][GithubMicrosoftedgeWebviewfeedbackIssue22]\) に追加されました。  
*   NuGet パッケージ \ ([\ #32][GithubMicrosoftedgeWebviewfeedbackIssue32]\) のインストーラリストに .net プロジェクトが追加されました。  

## 0.8.190  

[NuGet パッケージ][NuGetGallery0.8.190] \ |Microsoft Edge の最小バージョン77.0.190.0。  

*   `get_AreDevToolsEnabled` / `put_AreDevToolsEnabled` ユーザーが devtools \ ([\ #16][GithubMicrosoftedgeWebviewfeedbackIssue16]\) を開くことができるかどうかを制御するために追加されました。  
*   `get_IsStatusBarEnabled` / `put_IsStatusBarEnabled` ステータスバーが表示されている場合は、コントロールに追加されます (\[#19][GithubMicrosoftedgeWebviewfeedbackIssue19]\)。  
*   `get_CanGoBack` / `GoBack` / `get_CanGoForward` / `GoForward` ナビゲーション履歴を前後に移動するために追加されました。  
*   `IWebView2HttpHeadersCollectionIterator` / `IWebView2HttpRequestHeaders` / `IWebView2HttpRequestHeaders` WebView の http ヘッダーを表示し、変更するための http ヘッダーの種類 \ (\) を追加しました。  
*   64ビットコンピューター \ ([\ #13][GithubMicrosoftedgeWebviewfeedbackIssue13]\) に32ビット WebView サポートが追加されました。  
*   SDK \ ([\ #14][GithubMicrosoftedgeWebviewfeedbackIssue14]\) に WebView IDL が追加されました。  
*   `IID\_\*`インターフェイス ID オブジェクト \ ([\ #12][GithubMicrosoftedgeWebviewfeedbackIssue12]\) をサポートするために lib が追加されました。  
*   SDK では、DLL ファイルのパス、リンク、自動コピーなどのファイルを NuGet ファイルに追加し `TARGET` ます。  
*   `window.open()`スクリプトでの要求を有効にしました。  

## 0.8.149  

[NuGet パッケージ][NuGetGallery0.8.149] \ |Microsoft Edge の最小バージョン76.0.149.0。  

最初の開発者プレビューリリース。  

<!-- Links -->  

[ConceptsDistribution]: ./concepts/distribution.md "WebView2 を使用したアプリケーションの配布 |Microsoft ドキュメント"  
[ConceptsDistributionEvergreenMode]: ./concepts/distribution.md#evergreen-distribution-mode "Evergreen 配布モード-WebView2 を使用したアプリケーションの配布 |Microsoft ドキュメント"  
[Webview2ConceptsDistributionFixedVersionMode]: ./concepts/distribution.md#fixed-version-distribution-mode "固定バージョン配布モード-WebView2 を使用したアプリケーションの配布 |Microsoft ドキュメント"  
[Webview2ConceptsDistributionUnderstandRuntimeInstaller]: ./concepts/distribution.md#understanding-the-webview2-runtime "WebView2 を使用したアプリケーションの WebView2 ランタイムとインストーラーの配布について理解するMicrosoft ドキュメント"  
[Webview2ConceptsEnterpriseGroupPoliciesForWebview2]: ./concepts/enterprise.md#group-policies-for-webview2 "WebView2 のグループポリシー-WebView2 アプリケーションを管理するMicrosoft ドキュメント"  
[ConceptsVersioning]: ./concepts/versioning.md "ブラウザーのバージョンと WebView2 についてMicrosoft ドキュメント"  
[ConceptsVersioningExperimentalApis]: ./concepts/versioning.md#experimental-apis "実験的 Api-ブラウザーのバージョンと WebView2 についてMicrosoft ドキュメント"  
[GettingstartedWinforms]: ./gettingstarted/winforms.md "Windows Forms アプリでの WebView2 の概要 |Microsoft ドキュメント"  
[GettingstartedWpf]: ./gettingstarted/wpf.md "WPF での WebView2 の概要 |Microsoft ドキュメント"  
[HowtoDebug]: ./howto/debug.md "WebView2 コントロールを使用して開発を行うときのデバッグ方法 |Microsoft ドキュメント"  

[ReferenceWin32Iwebview2acceleratorkeypressedeventargsHandle08190]: /microsoft-edge/webview2/reference/win32/iwebview2acceleratorkeypressedeventargs?view=webview2-0.8.355&preserve-view=true#handle "ハンドル-インターフェイスの IWebView2AcceleratorKeyPressedEventArgs |Microsoft ドキュメント"  
[ReferenceWin32Iwebview2containsfullscreenelementchangedeventhandler08190]: /microsoft-edge/webview2/reference/win32/iwebview2containsfullscreenelementchangedeventhandler?view=webview2-0.8.355&preserve-view=true "インターフェイス IWebView2ContainsFullScreenElementChangedEventHandler |Microsoft ドキュメント"  
[ReferenceWin32Iwebview2settings2PutAredefaultcontextmenusenabled08190]: /microsoft-edge/webview2/reference/win32/iwebview2settings2?view=webview2-0.8.355&preserve-view=true#put_aredefaultcontextmenusenabled "put_AreDefaultContextMenusEnabled インターフェイス IWebView2Settings2 |Microsoft ドキュメント"  
[ReferenceWin32Iwebview2settingsGetIsfullscreenallowedDeprecated08190]: /microsoft-edge/webview2/reference/win32/iwebview2settings?view=webview2-0.8.355&preserve-view=true#get_isfullscreenallowed_deprecated "get_IsFullscreenAllowed_deprecated インターフェイス IWebView2Settings |Microsoft ドキュメント"  
[ReferenceWin32Iwebview2webmessagereceivedeventargsGetWebmessageasstring08190]: /microsoft-edge/webview2/reference/win32/iwebview2webmessagereceivedeventargs?view=webview2-0.8.355&preserve-view=true#get_webmessageasstring "get_WebMessageAsString インターフェイス IWebView2WebMessageReceivedEventArgs |Microsoft ドキュメント"  
[ReferenceWin32Iwebview2webview4AddAcceleratorkeypressed08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview4?view=webview2-0.8.355&preserve-view=true#add_acceleratorkeypressed "add_AcceleratorKeyPressed インターフェイス IWebView2WebView4 |Microsoft ドキュメント"  
[ReferenceWin32Iwebview2webviewAddDocumentstatechanged08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview?view=webview2-0.8.355&preserve-view=true#add_documentstatechanged "add_DocumentStateChanged インターフェイス IWebView2WebView |Microsoft ドキュメント"  
[ReferenceWin32Iwebview2webview4Addremoteobject08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview4?view=webview2-0.8.355&preserve-view=true#addremoteobject "AddRemoteObject-interface IWebView2WebView4 |Microsoft ドキュメント"  
[ReferenceWin32Iwebview2webview5AddWebresourcerequested08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#add_webresourcerequested "add_WebResourceRequested インターフェイス IWebView2WebView5 |Microsoft ドキュメント"  
[ReferenceWin32Iwebview2webview5Addwebresourcerequestedfilter08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#addwebresourcerequestedfilter "AddWebResourceRequestedFilter-インターフェイス IWebView2WebView5 |Microsoft ドキュメント"  
[ReferenceWin32Iwebview2webview5GetContainsfullscreenelement08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#get_containsfullscreenelement "get_ContainsFullScreenElement インターフェイス IWebView2WebView5 |Microsoft ドキュメント"  
[ReferenceWin32Iwebview2webview5Removewebresourcerequestedfilter08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#removewebresourcerequestedfilter "RemoveWebResourceRequestedFilter-インターフェイス IWebView2WebView5 |Microsoft ドキュメント"  
[ReferenceWin32WebView2IdlCreatewebview2environmentwithdetails08190]:  /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.8.355&preserve-view=true#createwebview2environmentwithdetails "CreateWebView2EnvironmentWithDetails-Globals |Microsoft ドキュメント"  

[ReferenceWin32Icorewebview209430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true "インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2acceleratorkeypressedeventargsGetHandled09430]: /microsoft-edge/webview2/reference/win32/icorewebview2acceleratorkeypressedeventargs?view=webview2-0.9.430&preserve-view=true#get_handled "get_Handled インターフェイス ICoreWebView2AcceleratorKeyPressedEventArgs |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2AddContentloading09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_contentloading "add_ContentLoading インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2AddHistorychanged09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_historychanged "add_HistoryChanged インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2Addremoteobject09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#addremoteobject "AddRemoteObject-interface ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2AddSourcechanged09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_sourcechanged "add_SourceChanged インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2AddWindowcloserequested09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_windowcloserequested "add_WindowCloseRequested インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2CoreWebview2ScriptDialogKind09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#core_webview2_script_dialog_kind "CORE_WEBVIEW2_SCRIPT_DIALOG_KIND インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2devtoolsprotocoleventreceiver09430]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-0.9.430&preserve-view=true "インターフェイス ICoreWebView2DevToolsProtocolEventReceiver |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverAddDevtoolsprotocoleventreceived09430]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-0.9.430&preserve-view=true#add_devtoolsprotocoleventreceived "add_DevToolsProtocolEventReceived インターフェイス ICoreWebView2DevToolsProtocolEventReceiver |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverRemoveDevtoolsprotocoleventreceived09430]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-0.9.430&preserve-view=true#remove_devtoolsprotocoleventreceived "remove_DevToolsProtocolEventReceived インターフェイス ICoreWebView2DevToolsProtocolEventReceiver |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2environmentGetBrowserversioninfo09430]: /microsoft-edge/webview2/reference/win32/icorewebview2environment?view=webview2-0.9.430&preserve-view=true#get_browserversioninfo "get_BrowserVersionInfo インターフェイス ICoreWebView2Environment |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2host09430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true "インターフェイス ICoreWebView2Host |Microsoft ドキュメント"  
[ReferenceWin32Webview2IdlGetcorewebview2browserversioninfo09430]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.430&preserve-view=true#getcorewebview2browserversioninfo "GetCoreWebView2BrowserVersionInfo-Globals |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2hostGetZoomfactor09430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#get_zoomfactor "get_ZoomFactor インターフェイス ICoreWebView2Host |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2hostNotifyparentwindowpositionchanged09430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#notifyparentwindowpositionchanged "NotifyParentWindowPositionChanged-インターフェイス ICoreWebView2Host |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2hostPutZoomfactor09430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#put_zoomfactor "put_ZoomFactor インターフェイス ICoreWebView2Host |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2hostSetboundsandzoomfactor09430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#setboundsandzoomfactor "SetBoundsAndZoomFactor-インターフェイス ICoreWebView2Host |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2httpheaderscollectioniteratorGetHascurrentheader09430]: /microsoft-edge/webview2/reference/win32/icorewebview2httpheaderscollectioniterator?view=webview2-0.9.430&preserve-view=true#get_hascurrentheader "get_HasCurrentHeader インターフェイス ICoreWebView2HttpHeadersCollectionIterator |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2httprequestheadersGetheaders09430]: /microsoft-edge/webview2/reference/win32/icorewebview2httprequestheaders?view=webview2-0.9.430&preserve-view=true#getheaders "GetHeaders-インターフェイス ICoreWebView2HttpRequestHeaders |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2httpresponseheadersGetheader09430]: /microsoft-edge/webview2/reference/win32/icorewebview2httpresponseheaders?view=webview2-0.9.430&preserve-view=true#getheader "GetHeader-インターフェイス ICoreWebView2HttpResponseHeaders |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2Removeremoteobject09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#removeremoteobject "RemoveRemoteObject-インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2settingsGetAreremoteobjectsallowed09430]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.430&preserve-view=true#get_areremoteobjectsallowed "get_AreRemoteObjectsAllowed インターフェイス ICoreWebView2Settings |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2settingsGetIszoomcontrolenabled09430]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.430&preserve-view=true#get_iszoomcontrolenabled "get_IsZoomControlEnabled インターフェイス ICoreWebView2Settings |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2webmessagereceivedeventargsTrygetwebmessageasstring09430]: /microsoft-edge/webview2/reference/win32/icorewebview2webmessagereceivedeventargs?view=webview2-0.9.430&preserve-view=true#trygetwebmessageasstring "TryGetWebMessageAsString-interface ICoreWebView2WebMessageReceivedEventArgs |Microsoft ドキュメント"  

[ReferenceWin32Icorewebview2AddFramenavigationcompleted09488]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#add_framenavigationcompleted "add_FrameNavigationCompleted インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2Addhostobjecttoscript09488]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#addhostobjecttoscript "AddHostObjectToScript-interface ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2AddNewwindowrequested09488]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#add_newwindowrequested "add_NewWindowRequested インターフェイス ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2environmentGetBrowserversionstring09488]: /microsoft-edge/webview2/reference/win32/icorewebview2environment?view=webview2-0.9.488&preserve-view=true#get_browserversionstring " |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2environmentoptions09488]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions?view=webview2-0.9.488&preserve-view=true "インターフェイス ICoreWebView2EnvironmentOptions |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2experimentalcompositioncontroller09488]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller?view=webview2-0.9.488-prerelease&preserve-view=true "インターフェイス ICoreWebView2ExperimentalCompositionController |Microsoft ドキュメント"
[ReferenceWin32Icorewebview2experimentalcompositioncontroller09488]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller?view=webview2-0.9.488-prerelease&preserve-view=true "インターフェイス ICoreWebView2ExperimentalCompositionController |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2experimentalcursorchangedeventhandler09488]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcursorchangedeventhandler?view=webview2-0.9.488-prerelease&preserve-view=true "インターフェイス ICoreWebView2ExperimentalCursorChangedEventHandler |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2experimentalpointerinfo09488]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalpointerinfo?view=webview2-0.9.488-prerelease&preserve-view=true "インターフェイス ICoreWebView2ExperimentalPointerInfo |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2Removehostobjectfromscript09488]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#removehostobjectfromscript "RemoveHostObjectFromScript-interface ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2settingsGetAreremoteobjectsallowed09488]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.488&preserve-view=true#get_areremoteobjectsallowed "get_AreRemoteObjectsAllowed インターフェイス ICoreWebView2Settings |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2settingsGetIsbuiltinerrorpageenabled09488]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.488&preserve-view=true#get_isbuiltinerrorpageenabled " |Microsoft ドキュメント"  
[ReferenceWin32Webview2IdlCreatecorewebview2environmentwithdetails09488]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.488&preserve-view=true#createcorewebview2environmentwithdetails "CreateCoreWebView2EnvironmentWithDetails-Globals |Microsoft ドキュメント"  
[ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions09488]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.488&preserve-view=true#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions-Globals |Microsoft ドキュメント"  
[ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring09488]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.488&preserve-view=true#getavailablecorewebview2browserversionstring "GetAvailableCoreWebView2BrowserVersionString-Globals |Microsoft ドキュメント"  

[ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210707PrereleaseAddRasterizationscalechanged]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.707-prerelease&preserve-view=true#add_rasterizationscalechanged "add_RasterizationScaleChanged インターフェイス ICoreWebView2ExperimentalController |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210707PrereleaseGetBoundsMode]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.707-prerelease&preserve-view=true#get_boundsmode "get_BoundsMode インターフェイス ICoreWebView2ExperimentalController |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210707PrereleaseGetRasterizationscale]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.707-prerelease&preserve-view=true#get_rasterizationscale "get_RasterizationScale インターフェイス ICoreWebView2ExperimentalController |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210707PrereleaseGetShouldDetectMonitorScaleChanges]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.707-prerelease&preserve-view=true#get_shoulddetectmonitorscalechanges "get_ShouldDetectMonitorScaleChanges インターフェイス ICoreWebView2ExperimentalController |Microsoft ドキュメント"  

[DotnetApiMicrosoftWebWebview2Core]: /dotnet/api/microsoft.web.webview2.core "WebView2 の名前空間 |Microsoft ドキュメント"  
[DotnetApiMicrosoftWebWebview2Wpf]: /dotnet/api/microsoft.web.webview2.wpf "WebView2 の名前空間 |Microsoft ドキュメント"  
[DotnetApiMicrosoftWebWebview2Winforms]: /dotnet/api/microsoft.web.webview2.winforms "WinForms 名前空間 WebView2 |Microsoft ドキュメント"  

[DotnetApiMicrosoftWebWebview2CoreWebview2runtimenotfoundexception]: /dotnet/api/microsoft.web.webview2.core.webview2runtimenotfoundexception "WebView2RuntimeNotFound (WebView2) | CoreWebView2) |Microsoft ドキュメント"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2]: /dotnet/api/microsoft.web.webview2.core.corewebview2 "CoreWebView2 クラス (WebView2 の場合) |Microsoft ドキュメント"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2environment]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment "CoreWebView2Environment クラス (WebView2 の場合) |Microsoft ドキュメント"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentComparebrowserversions]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.comparebrowserversions "CoreWebView2Environment (文字列, 文字列) メソッド (CompareBrowserVersions () |) |Microsoft ドキュメント"
[DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentGetavailablebrowserversionstring]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.getavailablebrowserversionstring "CoreWebView2Environment: この文字列 (文字列) メソッド (WebView2) を指定します (String) |Microsoft ドキュメント"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Newwindowrequested]: /dotnet/api/microsoft.web.webview2.core.corewebview2.newwindowrequested "CoreWebView2 | 要求されたイベント (WebView2) |Microsoft ドキュメント"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Permissionrequested]: /dotnet/api/microsoft.web.webview2.core.corewebview2.permissionrequested "CoreWebView2 によって要求されたイベント (WebView2) |Microsoft ドキュメント"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Scriptdialogopening]: /dotnet/api/microsoft.web.webview2.core.corewebview2.scriptdialogopening "CoreWebView2: WebView2 イベントを開きます () |Microsoft ドキュメント"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Webresourcerequested]: /dotnet/api/microsoft.web.webview2.core.corewebview2.webresourcerequested "CoreWebView2 WebResourceRequested イベント (WebView2 () |Microsoft ドキュメント"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2httprequestheaders]: /dotnet/api/microsoft.web.webview2.core.corewebview2httprequestheaders "CoreWebView2HttpRequestHeaders クラス (WebView2 の場合) |Microsoft ドキュメント"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2httpresponseheaders]: /dotnet/api/microsoft.web.webview2.core.corewebview2httpresponseheaders "CoreWebView2HttpResponseHeaders クラス (WebView2 の場合) |Microsoft ドキュメント"  

[DotnetApiMicrosoftWebWebview2WinformsCorewebview2creationproperties]: /dotnet/api/microsoft.web.webview2.winforms.corewebview2creationproperties "CoreWebView2CreationProperties クラス (WebView2) | Winforms) |Microsoft ドキュメント"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2Source]: /dotnet/api/microsoft.web.webview2.winforms.webview2.source "Webview2 クラス (Winforms) | WebView2) |Microsoft ドキュメント"  

[DotnetApiMicrosoftWebWebview2WpfWebview2Buildwindowcore]: /dotnet/api/microsoft.web.webview2.wpf.webview2.buildwindowcore "WebView2: HandleRef () メソッド () | (WebView2) |Microsoft ドキュメント"  
[DotnetApiMicrosoftWebWebview2WpfWebview2Destroywindowcore]: /dotnet/api/microsoft.web.webview2.wpf.webview2.destroywindowcore "WebView2: HandleRef () メソッド (WebView2 ()] |Microsoft ドキュメント"  

[DotnetApiMicrosoftWebWebview2WpfWebview2Acceleratorkeypressed]: /dotnet/api/microsoft.web.webview2.wpf.webview2.acceleratorkeypressed "webview2 | acceleratorkeypressed |) | webview2 |Microsoft ドキュメント"  

[ReferenceWin32Icorewebview2Addhostobjecttoscript09538]: /microsoft-edge/webview2/reference/win32/icorewebview2#addhostobjecttoscript?view=webview2-0.9.538&preserve-view=true "AddHostObjectToScript-interface ICoreWebView2 |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2experimentalAddWebresourceresponsereceived09538]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-0.9.538-prerelease&preserve-view=true#add_webresourceresponsereceived "add_WebResourceResponseReceived インターフェイス ICoreWebView2Experimental |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2experimentaloptionsGetIssinglesignonusingosprimaryaccountenabled09538]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalenvironmentoptions?view=webview2-0.9.538-prerelease&preserve-view=true#get_issinglesignonusingosprimaryaccountenabled "get_IsSingleSignOnUsingOSPrimaryAccountEnabled インターフェイス ICoreWebView2ExperimentalEnvironmentOptions |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2experimentalnewwindowrequestedeventargsGetWindowfeatures09538]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalnewwindowrequestedeventargs?view=webview2-0.9.538-prerelease&preserve-view=true#get_windowfeatures "get_WindowFeatures インターフェイス ICoreWebView2ExperimentalNewWindowRequestedEventArgs |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2experimentalwindowfeatures09538]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwindowfeatures?view=webview2-0.9.538-prerelease&preserve-view=true "インターフェイス ICoreWebView2ExperimentalWindowFeatures |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2newwindowrequestedeventargsGetIsuserinitiated09538]: /microsoft-edge/webview2/reference/win32/icorewebview2newwindowrequestedeventargs?view=webview2-0.9.538&preserve-view=true#get_isuserinitiated "get_IsUserInitiated インターフェイス ICoreWebView2NewWindowRequestedEventArgs |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2settingsGetArehostobjectsallowed09538]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.538&preserve-view=true#get_arehostobjectsallowed "get_AreHostObjectsAllowed インターフェイス ICoreWebView2Settings |Microsoft ドキュメント"  
[ReferenceWin32IdlCreatecorewebview2environmentwithoptions09538]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.538&preserve-view=true#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions-Globals |Microsoft ドキュメント"  

[ReferenceWin32Icorewebview2environmentoptionsGetAllowsinglesignonusingosprimaryaccount09622]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions?view=webview2-0.9.622&preserve-view=true#get_allowsinglesignonusingosprimaryaccount "get_AllowSingleSignOnUsingOSPrimaryAccount インターフェイス ICoreWebView2EnvironmentOptions |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2environmentoptionsPutAdditionalbrowserarguments09622]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions?view=webview2-0.9.622&preserve-view=true#put_additionalbrowserarguments "put_AdditionalBrowserArguments インターフェイス ICoreWebView2EnvironmentOptions |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2newwindowrequestedeventargsGetWindowfeatures09622]: /microsoft-edge/webview2/reference/win32/icorewebview2newwindowrequestedeventargs?view=webview2-0.9.622&preserve-view=true#get_windowfeatures "get_WindowFeatures インターフェイス ICoreWebView2NewWindowRequestedEventArgs |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2windowfeatures09622]: /microsoft-edge/webview2/reference/win32/icorewebview2windowfeatures?view=webview2-0.9.622&preserve-view=true "インターフェイス ICoreWebView2WindowFeatures |Microsoft ドキュメント"  
[ReferenceWin32IdlCreatecorewebview2environmentwithoptions09622]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.622&preserve-view=true#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions-Globals |Microsoft Edge"  
[ReferenceWin32Icorewebview2experimentalenvironment09628]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalenvironment?view=webview2-0.9.628-prerelease&preserve-view=true "インターフェイス ICoreWebView2ExperimentalEnvironment |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2experimentalwebresourceresponsereceivedeventargsPopulateresponsecontent09628]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwebresourceresponsereceivedeventargs?view=webview2-0.9.628-prerelease&preserve-view=true#populateresponsecontent "PopulateResponseContent-インターフェイス ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs |Microsoft ドキュメント"  

[ReferenceWin32Icorewebview2experimentalAddDomcontentloaded10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#add_domcontentloaded "add_DOMContentLoaded インターフェイス ICoreWebView2Experimental |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2experimentalAddWebresourceresponsereceived10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#add_webresourceresponsereceived "add_WebResourceResponseReceived インターフェイス ICoreWebView2Experimental |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2experimentalGetCookiemanager10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#get_cookiemanager "get_CookieManager インターフェイス ICoreWebView2Experimental |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2experimentalGetEnvironment10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#get_environment "get_Environment インターフェイス ICoreWebView2Experimental |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2experimentalNavigatewithwebresourcerequest10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#navigatewithwebresourcerequest "NavigateWithWebResourceRequest-インターフェイス ICoreWebView2Experimental |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2experimentalcompositioncontroller2GetSystemcursorid10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller2#get_systemcursorid?view=webview2-1.0.674-prerelease&preserve-view=true "インターフェイス ICoreWebView2ExperimentalWebResourceResponseView |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2experimentalwebresourceresponseview10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwebresourceresponseview?view=webview2-1.0.674-prerelease&preserve-view=true "インターフェイス ICoreWebView2ExperimentalWebResourceResponseView |Microsoft ドキュメント"  
[ReferenceWin32Icorewebview2experimentalwebresourceresponseviewGetcontent10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwebresourceresponseview?view=webview2-1.0.674-prerelease&preserve-view=true#getcontent "GetContent-インターフェイス ICoreWebView2ExperimentalWebResourceResponseView |Microsoft ドキュメント"  

[ReferenceWin32Icorewebview2experimentalcompositioncontroller3]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller3?view=webview2-1.0.707-prerelease&preserve-view=true "インターフェイス ICoreWebView2ExperimentalCompositionController3 |Microsoft ドキュメント"  

[DeployedgeMicrosoftEdgePolicies]: /deployedge/microsoft-edge-policies "Microsoft Edge-ポリシー |Microsoft ドキュメント"  
[DeployedgeMicrosoftEdgeWebviewPolicies]: /deployedge/microsoft-edge-webview-policies "Microsoft Edge WebView2-ポリシー |Microsoft ドキュメント"  

[WindowsSecurityThreatProtectionMicrosoftDefenderApplicationGuardWindows10]: /windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview "Microsoft Defender Application Guard (Windows 10)-Windows セキュリティ |Microsoft ドキュメント"

[DotnetApiSystemComponentmodelCancelEventargs]: /dotnet/api/system.componentmodel.canceleventargs "CancelEventArgs クラス (System.componentmodel.annotations) |Microsoft ドキュメント"  
[DotnetApiSystemEventargs]: /dotnet/api/system.eventargs "EventArgs クラス (システム) |Microsoft ドキュメント"  
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
[GithubMicrosoftedgeWebviewfeedbackIssue168]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/168 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ168"  
[GithubMicrosoftedgeWebviewfeedbackIssue177]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/177 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ177"
[GithubMicrosoftedgeWebviewfeedbackIssue179]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/179 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ179"
[GithubMicrosoftedgeWebviewfeedbackIssue181]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/181 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ181"
[GithubMicrosoftedgeWebviewfeedbackIssue183]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/183 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ183"
[GithubMicrosoftedgeWebviewfeedbackIssue185]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/185 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ185"
[GithubMicrosoftedgeWebviewfeedbackIssue204]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/204 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ204"
[GithubMicrosoftedgeWebviewfeedbackIssue219]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/219 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ219"
[GithubMicrosoftedgeWebviewfeedbackIssue228]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/228 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ228"
[GithubMicrosoftedgeWebviewfeedbackIssue235]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/235 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ235"
[GithubMicrosoftedgeWebviewfeedbackIssue250]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/250 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ250"
[GithubMicrosoftedgeWebviewfeedbackIssue288]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/288 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ288"
[GithubMicrosoftedgeWebviewfeedbackIssue293]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/293 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ293"
[GithubMicrosoftedgeWebviewfeedbackIssue318]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/318 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ318"  
[GithubMicrosoftedgeWebviewfeedbackIssue335]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/335 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ335"  
[GithubMicrosoftedgeWebviewfeedbackIssue371]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/371 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ371"  
[GithubMicrosoftedgeWebviewfeedbackIssue382]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/382 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ382"  
[GithubMicrosoftedgeWebviewfeedbackIssue431]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/431 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ431"  
[GithubMicrosoftedgeWebviewfeedbackIssue432]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/432 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ432"  
[GithubMicrosoftedgeWebviewfeedbackIssue461]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/461 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ461"  
[GithubMicrosoftedgeWebviewfeedbackIssue525]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/525 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ525"  
[GithubMicrosoftedgeWebviewfeedbackIssue549]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/549 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ549"  
[GithubMicrosoftedgeWebviewfeedbackIssue560]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/560 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ560"  
[GithubMicrosoftedgeWebviewfeedbackIssue611]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/611 "MicrosoftEdge/WebViewFeedback の問題のフィードバックリポジトリ611"  

[GithubMicrosoftedgeWebview2AnnouncementIssue2]:  https://github.com/MicrosoftEdge/WebView2Announcement/issues/2 "MicrosoftEdge/WebViewAnnouncement の問題2のお知らせリポジトリ"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesPr17]: https://github.com/MicrosoftEdge/WebView2Samples/pull/17 "最新の WebView2 SDK 0.9.430-MicrosoftEdge/WebView2Samples | を使用するようにプロジェクトを移動するGitHub"  
[GithubMicrosoftedgeWebview2samplesApisample]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2APISample "WebView2 API のサンプル-MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftDevblogDotnetAnnouncingGeneralAvailabilityForMicrosoftEdgeWebview2ForNetFixedDistributionMethod]: https://devblogs.microsoft.com/dotnet/announcing-general-availability-for-microsoft-edge-webview2-for-net-and-fixed-distribution-method "Microsoft Edge WebView2 for .NET および固定配布メソッドの一般的な利用可能性の発表 | .NET ブログ"  

[MicrosoftDeveloperMicrosoftEdgeWebView2]: https://developer.microsoft.com/microsoft-edge/webview2/ "Microsoft Edge WebView2 |Microsoft Edge 開発者"  

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
[NuGetGallery1.0.622.22]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.622.22 "NuGet ギャラリー |WebView2 v 1.0.622.22"
[NuGetGallery1.0.664.34]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.664.34 "NuGet ギャラリー |WebView2 v 1.0.664.34"
[NuGetGallery1.0.664.37]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.664.37 "NuGet ギャラリー |WebView2 v 1.0.664.37"
[NuGetGallery0.9.628-prerelease]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.628-prerelease "NuGet ギャラリー |WebView2 v 0.9.628 プレリリース"  
[NuGetGallery1.0.674-prerelease]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.674-prerelease "NuGet ギャラリー |WebView2 v 1.0.674 プレリリース"  
[NuGetGallery1.0.707-prerelease]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.707-prerelease "NuGet ギャラリー |WebView2 v 1.0.707 プレリリース"  

[WindowsBlogsMsedgedevEdgeWebview2GeneralAvailability]: https://blogs.windows.com/msedgedev/edge-webview2-general-availability "Microsoft Edge WebView2 の一般的な利用可能性についてのアナウンス |Microsoft Edge ブログ"  
