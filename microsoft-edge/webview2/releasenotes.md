---
description: Microsoft Edge WebView2 SDK のリリース ノート
title: Win32、WPF、WinForms 向け Microsoft Edge WebView2 のリリース ノート
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/01/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、ブラウザー コントロール、エッジ html
ms.openlocfilehash: 199077b1922fd7249bd67133d55d85bc0f144926
ms.sourcegitcommit: ab4b555d30f3be05d8620e8deb3c74350b6696be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2021
ms.locfileid: "11306617"
---
# WebView2 SDK のリリース ノート  

WebView2 チームは [、WebView2 SDK][NuGetGallery] を 6 週間の更新で更新します。  API に対する製品のアナウンス、追加、変更、および変更の詳細については、次のコンテンツを確認してください。  

> [!NOTE]
> NuGet パッケージの更新後にアプリを再コンパイルしてください。  プレリリース パッケージを使用して開発する場合は Canary チャネルを使用し、リリース済みパッケージを使用する場合は常にランタイムを使用する方法をお勧めします。  詳細については、[バージョン管理] [に移動します][VersioningDoc]。  
 
## 1.0.781 プレリリース  

リリース日: 2021 年 1 月 29 日  

[NuGet パッケージ][NuGetGallery1.0.781-prerelease] \|Microsoft Edge バージョン 86.0.616.0 以降  

### 全般的な情報  

> [!IMPORTANT]
> WebView2 プレリリース パッケージ 0.9.430 は廃止され、今後のリリースから削除される予定です。  WebView アプリでパッケージを使う場合は、新しいパッケージに更新することをお勧めします。  

##### 機能  

*   [WebView を中断して再開する TrySuspend][ReferenceWin32Icorewebview210781PreReleaseTrySuspendResume]メソッドと Resume メソッドが追加されました。  
*   仮想ホスト [名をディレクトリ パスにマップする SetVirtualHostNameToFolderMapping][ReferenceWin32Icorewebview210781PreReleaseSetVirtualHostNameToFolderMapping] メソッドが追加されました。  \([\#37][GithubMicrosoftedgeWebviewfeedbackIssue37], [\#161][GithubMicrosoftedgeWebviewfeedbackIssue161], and [\#212][GithubMicrosoftedgeWebviewfeedbackIssue212]\).  
*   背景の色とアルファ チャネルを設定する [DefaultBackgroundColor][ReferenceWin32Icorewebview2controllerViewWebview210781PreReleaseDefaultBackgroundColor] プロパティを追加しました。  \([\#414][GithubMicrosoftedgeWebviewfeedbackIssue414]\)。  
*   User [Agent を取得][ReferenceWin32Icorewebview2experimentalsettings10781PreReleaseGetUserAgent] または設定する UserAgent プロパティを追加しました。  \([\#122][GithubMicrosoftedgeWebviewfeedbackIssue122]\)。
*   メソッドを `CreateCookieWithCookie` メソッドに置き換 `CopyCookie` えました。  
*   [ICoreWebView2CompositionController][ReferenceWin32Icorewebview2controllerViewWebview210781CompositionController]インターフェイスを使用してビジュアル ホスティングのサポートを追加しました。このインターフェイスは、次の新しいメソッドを `CreateCoreWebView2CompositionController` 使用して作成されます `ICoreWebView2Environment3` 。  

    
##### バグ修正  

*   WebView2 で Microsoft Edge のショッピング機能を無効にします。  
*   オンになっている場合は、PDF ビューアーでコンテキスト メニューを `AreDefaultContextMenusEnabled` オフにします `false` 。  \([\#605][GithubMicrosoftedgeWebviewfeedbackIssue605]\)。  
*   クエリを実行するときに返 `E_NOINTERFACE` されるバグを修正 `ICoreWebView2` しました `ICoreWebView2Experimental` 。  \([\#691][GithubMicrosoftedgeWebviewfeedbackIssue691]\)。  
*   URI の形式が正しく設定されているときにナビゲーションが許可されるバグ `CoreWebView2NavigationStartingEventArgs.Cancel` を修正しました `false` 。  \([\#400][GithubMicrosoftedgeWebviewfeedbackIssue400]\)。  
*   イベントハンドラーがイベントに `window.print()` 関連付けられているポップアップ ウィンドウでブロックされるバグを修正 `NewWindowRequested` しました。  \([\#409][GithubMicrosoftedgeWebviewfeedbackIssue409]\)。  
*   異なるモニター間でアプリを移動する場合の動的 DPI の問題を修正しました。  \([\#58][GithubMicrosoftedgeWebviewfeedbackIssue58]\)  
*   `HRESULT` [ICoreWebView2WebResourceResponseViewGetContentCompletedHandler::Invoke][ReferenceWin32Icorewebview2webresourceresponseviewgetcontentcompletedhandlerInvoke10781]によって渡される処理が改善されました。  
    
##### プロモーション  

*   次の試験的な API が Stable に昇格されました。  
    *   ビジュアル ホスティング API。  
    *   [SetVirtualHostNameToFolderMapping][ReferenceWin32Icorewebview210781PreReleaseSetVirtualHostNameToFolderMapping]  
    *   [TrySuspend と Resume][ReferenceWin32Icorewebview210781PreReleaseTrySuspendResume]  
    *   [DefaultBackgroundColor][ReferenceWin32Icorewebview2controllerViewWebview210781PreReleaseDefaultBackgroundColor]  
    
#### .NET  

##### バグ修正  

*   WPF SDK を使用する WebView アプリがクラッシュするバグを修正しました。  クラッシュは、ウィンドウが F4 キーを使って閉じらたときに発生しました。  \([\#399][GithubMicrosoftedgeWebviewfeedbackIssue399]\)。  
*   WebView2 の初期化画面が灰色ではなく透明になります。  \([\#196][GithubMicrosoftedgeWebviewfeedbackIssue196]\)。  
    
## 1.0.705.50  

リリース日: 2021 年 1 月 25 日  

[NuGet パッケージ][NuGetGallery1.0.705.50] \|WebView2 ランタイム バージョン 86.0.616.0 以降  

##### プロモーション  

*   次の試験的な API が Stable に昇格されました。  
    *   [WebResourceResponseReceived API][WebResourceResponseReceivedAPI]  
    *   [NavigateWithWebResourceRequest API][NavigateWithWebResourceRequestAPI]  
    *   [Cookie 管理 API][CookiemanagementAPI]  
    *   [DOMContentLoaded API][DOMContentLoadedAPI]  
    *   [WebView Environment プロパティ][WebViewEnvironmentproperty]  

## 1.0.721-プレリリース  

リリース日: 2020 年 12 月 8 日  

[NuGet パッケージ][NuGetGallery1.0.721-prerelease] \|Microsoft Edge バージョン 86.0.616.0 以降  

#### 全般的な情報  

> [!IMPORTANT]
> **Breaking Change**: WebView2 pre-release packages 1.0.707 and 0.9.628 are deprecated.  これらのパッケージを使用して開発を中止してください。  

###### 機能  

*   [WebView2 グループ ポリシーを追加しました][DeployedgeMicrosoftEdgeWebviewPolicies]。  推奨される方法の詳細については [、WebView2 のグループ ポリシーに移動してください][Webview2ConceptsEnterpriseGroupPoliciesForWebview2]。  
*   > [!IMPORTANT]
    > **Breaking Change**: 古いレジストリの場所を廃止しました。  
    > 
    > ```text
    > {Root}\Software\Policies\Microsoft\EmbeddedBrowserWebView\LoaderOverride\{AppId}
    > ```  
    
*   WebView2 での [ドラッグ アンド ドロップの][ReferenceWin32Icorewebview2experimentalcompositioncontroller3] サポートが追加されました。  
*   DPI サポートを処理する API が追加されました。  
    *   [WebView コンテンツと][ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetRasterizationscale]UI ポップアップの DPI スケールを変更する RasterizationScale プロパティ、および[関連付けられた RasterizationScaleChanged イベントが追加][ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseAddRasterizationscalechanged]されました。  
    *   [ShouldDetectMonitorScaleChanges][ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetShouldDetectMonitorScaleChanges]プロパティが追加され、必要に応じてプロパティ `RasterizationScale` が自動的に更新されます。  
    *   [BoundsMode][ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetBoundsMode]プロパティが追加され、境界がロジック ピクセルであり、WebView が WebView2 ピクセル表示に使用できると指定され `RasterizationScale` 、WebView は物理サイズを取得するために With を使用します。 `RasterizationScale` `Bounds`  
*   イベントを `NewWindowRequested` 処理および `Ctrl` + `click` 更新しました `Shift` + `click` 。  \([\#168][GithubMicrosoftedgeWebviewfeedbackIssue168] and [\#371][GithubMicrosoftedgeWebviewfeedbackIssue371]\).  
*   次の試験的な API が Stable に昇格されました。  
    *   [WebResourceResponseReceived API][WebResourceResponseReceivedAPI]  
    *   [NavigateWithWebResourceRequest API][NavigateWithWebResourceRequestAPI]  
    *   [Cookie 管理 API][CookiemanagementAPI]  
    *   [DOMContentLoaded API][DOMContentLoadedAPI]  
    *   [WebView 環境プロパティ][WebViewEnvironmentproperty]  
        
#### .NET  

###### 機能  

*   .NET Core 3.1+ および .NET 5 で WinForms デザイナーを有効にしました。  
*   .NET Cookie の管理が改善されました。  \([\#611][GithubMicrosoftedgeWebviewfeedbackIssue611]\)。  
*   `CoreWebView2Ready` [CoreWebView2InitializationCompleted に置き換えました][DotnetApiMicrosoftWebWebview2Corewebview2initializationcompletedeventargs]。  

###### バグ修正

*   WebView2 [で AcceleratorKey の][DotnetApiMicrosoftWebWebview2WpfWebview2Acceleratorkeypressed] 押下をサポートする AcceleratorKeyPressed イベントが追加されました。  \([\#288][GithubMicrosoftedgeWebviewfeedbackIssue288]\)。  
*   不要なファイルが WebView2 フォルダーに出力されるのを削除しました。  \([\#461][GithubMicrosoftedgeWebviewfeedbackIssue461]\)。  
*   改善されたホスト オブジェクト API。  \([\#335][GithubMicrosoftedgeWebviewfeedbackIssue335] and [\#525][GithubMicrosoftedgeWebviewfeedbackIssue525]\).  
    
## 1.0.664.37  

リリース日: 2020 年 11 月 20 日  

[NuGet パッケージ][NuGetGallery1.0.664.37] \|WebView2 ランタイム バージョン 86.0.616.0 以降。  

#### 全般的な情報  

> [!IMPORTANT]
> **アナウンス**: .NET WPF/WinForms WebView2 SDK が一般公開 \(GA\) されました。  このリリースから、リリース SDK は前方互換性があります。  詳細については、GA のお知らせ [ブログの投稿に移動します][MicrosoftDevblogDotnetAnnouncingGeneralAvailabilityForMicrosoftEdgeWebview2ForNetFixedDistributionMethod]。  

###### 機能  

*   .NET WPF/WinForms WebView2 が一般公開 \(GA\) されました。  
*   固定配布 \(Bring-your-own\) モードが GA に到達しました。  
    
#### .NET  

###### バグ修正  

*   `CoreWebView2NewWindowRequestedEventArgs.Handled` をクリックすると、新しいウィンドウが開かれません。  \([\#549][GithubMicrosoftedgeWebviewfeedbackIssue549] and [\#560][GithubMicrosoftedgeWebviewfeedbackIssue560]\).  
    
## 1.0.674 プレリリース  

リリース日: 2020 年 10 月 19 日  

[NuGet パッケージ][NuGetGallery1.0.674-prerelease] \|WebView2 ランタイム バージョン 86.0.616.0 以降。  

#### 全般的な情報  

*   ナビゲーション中にポスト データまたは他の要求ヘッダーを提供する [NavigateWithWebResourceRequest][ReferenceWin32Icorewebview2experimentalNavigatewithwebresourcerequest10674] メソッドが追加されました。  
*   初期 HTML ドキュメントが読み込まれ、解析されると実行される [DOMContentLoaded][ReferenceWin32Icorewebview2experimentalAddDomcontentloaded10674] イベントが追加されました。  
*   WebView2 [に Environment][ReferenceWin32Icorewebview2experimentalGetEnvironment10674] プロパティを追加しました。  このプロパティは、WebView2 のインスタンスが作成された WebView2 環境を公開します。  
*   開発者が [WebView2][ReferenceWin32Icorewebview2experimentalGetCookiemanager10674] セッションを認証したり、WebView から Cookie を取得して他のツールを認証したりできる Cookie 管理 API が追加されました。  Webview チームは、言語またはフレームワーク固有の改善を計画しています。  詳細については、「API レビュー [: Cookie の管理」に移動します][GithubMicrosoftedgeWebview2AnnouncementIssue2]。  
*   [WebResourceResponseReceived][ReferenceWin32Icorewebview2experimentalAddWebresourceresponsereceived10674]イベントを更新し、不変[の WebResourceResponseView][ReferenceWin32Icorewebview2experimentalwebresourceresponseview10674]と[WebResourceResponseReceivedEventArgs::P opulateResponseContent][ReferenceWin32Icorewebview2experimentalwebresourceresponsereceivedeventargsPopulateresponsecontent09628] to [WebResourceResponseView::GetContent][ReferenceWin32Icorewebview2experimentalwebresourceresponseviewGetcontent10674]を追加しました。  
*   WebView2 [で Microsoft Defender Application Guard (WDAG)][WindowsSecurityThreatProtectionMicrosoftDefenderApplicationGuardWindows10] をオフにします。  
*   ビジュアル ホスティング [用の SystemCursorId][ReferenceWin32Icorewebview2experimentalcompositioncontroller2GetSystemcursorid10674] が追加されました。  
*   ビジュアル ホスティングの入力メソッドに修正されたバグが追加されました。  
*   WebView2 静的ライブラリを `version.lib` 使用する場合の要件が削除されました。  
    
#### .NET  

*   変数を [公開するために CoreWebView2][DotnetApiMicrosoftWebWebview2CoreCorewebview2] クラスを更新 `CoreWebView2Environment` しました。  
*   名前空間内のカスタム EventArgs クラスの実装を `Microsoft.Web.WebView2.Core` [System.EventArgs][DotnetApiSystemEventargs] または [System.ComponentModel.CancelEventArgs][DotnetApiSystemComponentmodelCancelEventargs]のサブクラスに変更しました。  \([\#250][GithubMicrosoftedgeWebviewfeedbackIssue250]\)  
*   WinForms の [CoreWebView2CreationProperties][DotnetApiMicrosoftWebWebview2Winforms] のサポートが追加されました。  \([\#204][GithubMicrosoftedgeWebviewfeedbackIssue204]\)
*   [WebResourceRequested][DotnetApiMicrosoftWebWebview2CoreCorewebview2Webresourcerequested] .NET API が追加されました。  \([\#219][GithubMicrosoftedgeWebviewfeedbackIssue219]\)。  
*   WinForms Designer [Source][DotnetApiMicrosoftWebWebview2WinformsWebview2Source] プロパティが既定に更新または null にリセットされました。  \([\#177][GithubMicrosoftedgeWebviewfeedbackIssue177]\)。  
*   100% 未満の DPI WebView2.Iniサポートするために、t() で WebView2 の境界を更新しました。  \([\#432][GithubMicrosoftedgeWebviewfeedbackIssue432]\)。  
*   [BuildWindowCore と][DotnetApiMicrosoftWebWebview2WpfWebview2Buildwindowcore] [DestroyWindowCore][DotnetApiMicrosoftWebWebview2WpfWebview2Destroywindowcore]が更新され、堅牢性が向上しました。  \([\#382][GithubMicrosoftedgeWebviewfeedbackIssue382]\)。  
*   オペレーティング システム アーキテクチャではなく、プロセス ビットで読み込む .NET ローダー ベースを更新しました。  \([\#431][GithubMicrosoftedgeWebviewfeedbackIssue431]\)。  
*   `EdgeNotFoundExpection` [WebView2RuntimeNotFoundException に名前が変更されました][DotnetApiMicrosoftWebWebview2CoreWebview2runtimenotfoundexception]。  
    
## 1.0.622.22  

リリース日: 2020 年 10 月 19 日  

[NuGet パッケージ][NuGetGallery1.0.622.22] \|WebView2 ランタイム バージョン 86.0.616.0 以降。  

#### 全般的な情報  

> [!IMPORTANT]
> **Announcement**: Win32 C/C++ WebView2 is now Generally Available \(GA\).  このリリースから、リリース SDK は前方互換性があります。  詳細については、GA のお知らせ [ブログの投稿に移動します][WindowsBlogsMsedgedevEdgeWebview2GeneralAvailability]。  

*   [Evergreen WebView2 ランタイムとインストーラーは][Webview2ConceptsDistributionUnderstandRuntimeInstaller] GA です。  Bootstrapper、Bootstrapper のダウンリンク リンク、および Evergreen WebView2 ランタイムのスタンドアロン インストーラーは [、Microsoft Edge WebView2 で利用できます][MicrosoftDeveloperMicrosoftEdgeWebView2]。  インストール ワークフローのサンプル コードは [、WebView2Samples レポでも使用できます][GithubMicrosoftedgeWebview2samplesMain]。  
*   [固定バージョン モードは][Webview2ConceptsDistributionFixedVersionMode] 、開発者向けプレビューで利用できます。  
    
## 0.9.622.11  

リリース日: 2020 年 9 月 10 日  

[NuGet パッケージ][NuGetGallery0.9.622.11] \|WebView2 ランタイム バージョン 86.0.616.0 以降。  

#### 全般的な情報  

*   > [!IMPORTANT]
    > **アナウンス**: この SDK は、WebView2 Win32 C/C++ GA の Release Candidate です。  GA バージョンでは、同じ API インターフェイスと機能を使用する必要があります。  
    
*   切断 [されたブラウザー ポリシー][DeployedgeMicrosoftEdgePolicies]。  
*   [WebView2 環境オプションに AllowSingleSignOnUsingOSPrimaryAccount][ReferenceWin32Icorewebview2environmentoptionsGetAllowsinglesignonusingosprimaryaccount09622]プロパティを追加し、WebView の条件付きアクセスを有効にしました。  
*   `ICoreWebView2NewWindowRequestedEventArgs` [WindowFeatures プロパティと][ReferenceWin32Icorewebview2newwindowrequestedeventargsGetWindowfeatures09622]、関連付けられた[ICoreWebView2WindowFeatures][ReferenceWin32Icorewebview2windowfeatures09622]を含む更新を行いました。  \([\#293][GithubMicrosoftedgeWebviewfeedbackIssue293]\)。  
*   `System.Windows.Rect` `System.Drawing.Rectangle` `System.Windows.Rect` \([\#235][GithubMicrosoftedgeWebviewfeedbackIssue235]\) の代わりに使用#235しました。  
*   パラメーターを指定せずに要求を処理する NewWindowRequested `window.open()` イベントを更新しました。  \([\#293][GithubMicrosoftedgeWebviewfeedbackIssue293]\)。  
*   [指定された AdditionalBrowserArguments][ReferenceWin32Icorewebview2environmentoptionsPutAdditionalbrowserarguments09622] は、環境変数やレジストリ値 `ICoreWebView2EnvironmentOptions` で上書きされるのではない。  詳細については、「[CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32IdlCreatecorewebview2environmentwithoptions09622]」を参照してください。  
    
## 0.9.579  

リリース日: 2020 年 7 月 20 日  

[NuGet パッケージ][NuGetGallery0.9.579] \|Microsoft Edge バージョン 86.0.579.0。  

#### 全般的な情報  

*   > [!IMPORTANT]
    > **アナウンス**: Evergreen WebView2 ランタイムとインストーラーがプレビュー用にリリースされます。  詳細については [、WebView2 の配布に移動します][Webview2ConceptsDistributionUnderstandRuntimeInstaller]。  
    
*   > [!IMPORTANT]
    > **アナウンス**: 次の WebView2 SDK バージョンは、次の SDK リリース以降サポートされなくなりました。  
    > 
    > *   [0.8.190](#08190)  
    > *   [0.8.230](#08230)  
    > *   [0.8.270](#08270)  
    > *   [0.8.314](#08314)  
    > *   [0.8.355](#08355)  
    > 
    > また、WebView2 SDK バージョンは、次のバージョンでも非推奨nuget.org。 WebView2 では、WebView2 の最新バージョンを最新の情報に更新してください。  
    
*   WebView ワーカー スレッドの機能強化が追加されました。  \([\#318][GithubMicrosoftedgeWebviewfeedbackIssue318]\)。  
*   WebView でポップアップ ブロックをオフにします。  詳細については、イベントの [IsUserInitiated][ReferenceWin32Icorewebview2newwindowrequestedeventargsGetIsuserinitiated09538] プロパティに移動 `NewWindowRequested` します。  
*   WebView ナビゲーション開始イベントが実行されます `about:blank` 。  現在では、すべてのナビゲーションに対してイベントが実行されますが、iframe または iframe の取り消しは `NavigationStarting` `about:blank` サポートされ `srcdoc` 、無視されません。  
*   `edge://`WebView で一部の URI スキームをブロックしました。  
*   WebView2 環境 [オプションに実験的な IsSingleSignOnUsingOSPrimaryAccountEnabled][ReferenceWin32Icorewebview2experimentaloptionsGetIssinglesignonusingosprimaryaccountenabled09538] プロパティを追加し、WebView の条件付きアクセスを有効にしました。  
*   WebView が WebResource 要求からの応答を受信して処理した後に実行される試験的な [WebResourceResponseReceived][ReferenceWin32Icorewebview2experimentalAddWebresourceresponsereceived09538] イベントが追加されました。  認証ヘッダーがある場合は、応答オブジェクトに含まれます。  
    
#### .NET  

*   WPF フォーカス処理が改善されました。  \([\#185][GithubMicrosoftedgeWebviewfeedbackIssue185]\)。  
*   WPF `ZoomFactor` Webview2 コントローラーにプロパティを追加しました。  
    
## 0.9.538  

[NuGet パッケージ][NuGetGallery0.9.538] \|Microsoft Edge バージョン 85.0.538.0。  

#### 全般的な情報  

*   WebView2 SDK バージョン [0.8.149 のサポートを削除しました](#08149)。  WebView2 では、WebView2 の最新バージョンを最新の情報に更新してください。  
*   Microsoft Edge ブラウザーのプロファイル パスが変更された日時を考慮するグループ ポリシーを更新しました \([#179][GithubMicrosoftedgeWebviewfeedbackIssue179]\)。  
    
#### Win32 C/C++  

*   [ICoreWebView2ExperimentalNewWindowRequestedEventArgs::get_WindowFeatures][ReferenceWin32Icorewebview2experimentalnewwindowrequestedeventargsGetWindowfeatures09538]が追加されました。このイベントは、実行時に発生し `window.open()` [、ICoreWebView2ExperimentalWindowFeatures][ReferenceWin32Icorewebview2experimentalwindowfeatures09538] \([#70][GithubMicrosoftedgeWebviewfeedbackIssue70]\) に関連付けます。  
*   > [!IMPORTANT]
    > **Breaking Change**: Deprecated [CreateCoreWebView2EnvironmentWithDetails][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithdetails09488] and replaced with [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32IdlCreatecorewebview2environmentwithoptions09538].  
    
*   > [!IMPORTANT]
    > **Breaking Change**: WebView2 API が Windows API の名前付け規則に準拠するために、WebView チームは次の名前を更新しました。  
    > 
    > *   [AreRemoteObjectsAllowed][ReferenceWin32Icorewebview2settingsGetAreremoteobjectsallowed09488] は [AreHostObjectsAllowed に変更されました][ReferenceWin32Icorewebview2settingsGetArehostobjectsallowed09538]。  
    
*   [AddHostObjectToScript を更新しました][ReferenceWin32Icorewebview2Addhostobjecttoscript09538]。  元のホスト オブジェクト シリアライザー マーカーがプロキシ オブジェクトに設定されます。  次に、JavaScript コールバック \( #148 \) でパラメーターとして渡された場合、ホスト オブジェクトのシリアライザー マーカーがホスト[オブジェクトとしてシリアル化されます][GithubMicrosoftedgeWebviewfeedbackIssue148]。  
    
#### .NET (0.9.538 プレリリース)  

*   リリースされた WinForms と WPF WebView2API サンプルは、WebView2 SDK の包括的なガイドです。  詳細については、Samples [Repo に移動します][GithubMicrosoftedgeWebview2samplesMain]。  
*   視覚的なホスティングとウィンドウ機能の試験的な API [のサポートが追加されました][ConceptsVersioningExperimentalApis]。  
*   > [!IMPORTANT]
    > **Breaking Change**: 次の保留が IDisposable を実装しました: ScriptDialogOpening、NewWindowRequested、WebResourceRequested、[][DotnetApiMicrosoftWebWebview2CoreCorewebview2Scriptdialogopening]および[PermissionRequested][DotnetApiMicrosoftWebWebview2CoreCorewebview2Permissionrequested]。 [][DotnetApiMicrosoftWebWebview2CoreCorewebview2Newwindowrequested] [][DotnetApiMicrosoftWebWebview2CoreCorewebview2Webresourcerequested]  
    
*   [GetAvailableBrowserVersionString][DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentGetavailablebrowserversionstring]と[CompareBrowserVersions][DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentComparebrowserversions]が[CoreWebView2Environment][DotnetApiMicrosoftWebWebview2CoreCorewebview2environment]静的として追加されました。  
    
## 0.9.515-プレリリース  

[NuGet パッケージ][NuGetGallery0.9.515-prerelease] \|Microsoft Edge バージョン 84.0.515.0。  

*   > [!IMPORTANT]
    > **お**知らせ : WebView2 では、.NET Framework 4.6.2 以降で Windows フォームと WPF がサポートされ、プレリリース パッケージの .NET Core 3.0 以降がサポート**されます。**  
    
*   WPF アプリの作成の詳細については [、「WPF Getting Started Guide」][GettingstartedWpf] および「WebView2 [WPF Reference][DotnetApiMicrosoftWebWebview2Wpf] for WPF-specific APIs」を参照してください。  
*   Windows フォーム アプリの構築の詳細については [、「Windows フォーム][GettingstartedWinforms] の概要ガイド」および「Windows フォーム固有 API 用 WebView2 [Windows][DotnetApiMicrosoftWebWebview2Winforms] フォーム リファレンス」に移動してください。  
*   CoreWebView2 API の詳細については、「.NET [リファレンス」に移動してください][DotnetApiMicrosoftWebWebview2Core]。  
*   > [!CAUTION]
    > **既知の問題**: WebView チームは、今後のリリースで解決されるプレリリースのいくつかの問題を認識しています。  
    > 
    > *   **DPI 対応**: WPF 用 WebView2 は、現在 DPI 対応ではありません。  高 DPI モニターで WebView2 を初期化する場合、ウィンドウのサイズが変更されるまで、最初に WebView がウィンドウの小数部として初期化されるという既知の問題があります。  
    > *   **WPF デザイナー**: WPF デザイナーは現在サポートされていません。  テキスト エディターで適切な XAML を直接変更して、アプリに WebView2 コントロールを追加します。  
    
## 0.9.488  

[NuGet パッケージ][NuGetGallery0.9.488] \|Microsoft Edge バージョン 84.0.488.0。  

*   > [!IMPORTANT]
    > **アナウンス**: 今後の Microsoft Edge バージョン 83 から、Evergreen WebView は Stable ブラウザー チャネルを対象としなくなりました。  代わりに、WebView チームが現在開発しているインストーラーを介してチェーン インストールできる [、Evergreen WebView2 ランタイム][ConceptsDistributionEvergreenMode]というブランド化された別のバイナリ セットをターゲットにします。  詳細については [、App-Distribution に移動します][ConceptsDistribution]。  
    
*   > [!IMPORTANT]
    > **お**知らせ : 今後、WebView チームは 2 つのパッケージをリリースします。試験的な API を含むプレリリース パッケージ \(試用用\) と安定した API を含む安定したリリース パッケージ \(自分の信頼のために\)。  違いについては、「ブラウザーのバージョンと [WebView2][ConceptsVersioning]について」に移動してください。  
    
*   > [!IMPORTANT]
    > **変更の**ブレーク: WebView2 API が Windows API の名前付け規則に準拠するために、WebView チームは次のインターフェイスの名前を更新しました。  
    > 
    > *   `CORE_WEBVIEW2_*` プレフィックスは次の値です `COREWEBVIEW2_*` 。  
    > *   [GetCoreWebView2BrowserVersionInfo][ReferenceWin32Webview2IdlGetcorewebview2browserversioninfo09430] は現在 [、GetAvailableCoreWebView2BrowserVersionString です][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring09488]。  
    > *   [get_BrowserVersionInfo][ReferenceWin32Icorewebview2environmentGetBrowserversioninfo09430]が表示[get_BrowserVersionString。][ReferenceWin32Icorewebview2environmentGetBrowserversionstring09488]  
    > *   [AddRemoteObject][ReferenceWin32Icorewebview2Addremoteobject09430] は [AddHostObjectToScript です][ReferenceWin32Icorewebview2Addhostobjecttoscript09488]。  
    > *   [RemoveRemoteObject][ReferenceWin32Icorewebview2Removeremoteobject09430] は [RemoveHostObjectFromScript に変更しました][ReferenceWin32Icorewebview2Removehostobjectfromscript09488]。  
    > *   `chrome.webview.remoteObjects` is now `chrome.webview.hostObjects` .  
    
*   > [!IMPORTANT]
    > **Breaking Change**: `AddRemoteObject` JS プロキシ メソッドの名前も変更されます。  
    > 
    > *   `getLocal` is now `getLocalProperty` .  
    > *   `setLocal` is now `setLocalProperty` .  
    > *   `getRemote` is now `getHostProperty` .  
    > *   `setRemote` is now `setHostProperty` .  
    > *   `applyRemote` is now `applyHostFunction` .  
    
*   > [!IMPORTANT]
    > **Breaking Change**: Deprecated [CreateCoreWebView2EnvironmentWithDetails][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithdetails09488] and replaced with [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions09488].  
    
*   [FrameNavigationCompleted イベントが追加][ReferenceWin32Icorewebview2AddFramenavigationcompleted09488]されました。  これで、iframe がナビゲーションを完了すると、イベントが実行され、ナビゲーションの成功とナビゲーション ID が返されます。  
*   [ICoreWebView2EnvironmentOptions][ReferenceWin32Icorewebview2environmentoptions09488]インターフェイスが追加されました。このインターフェイスは、アプリの対象となる WebView2 ランタイムのバージョンを判断するために使用できます。  
*   [IsBuiltInErrorPageEnabled 設定を追加][ReferenceWin32Icorewebview2settingsGetIsbuiltinerrorpageenabled09488]しました。  ナビゲーションエラーとレンダリング プロセスの失敗に関して、組み込みのエラー Web ページをオンまたはオフにできます。  
*   .NET 実装 \( #113 `IDispatch` \)[をサポートするためにリモート オブジェクト インジェクションを][GithubMicrosoftedgeWebviewfeedbackIssue113]更新しました。  
*   コンテキスト メニュー \( #108 \) からの要求を処理する [NewWindowRequested][ReferenceWin32Icorewebview2AddNewwindowrequested09488] [イベントを更新][GithubMicrosoftedgeWebviewfeedbackIssue108]しました。  
*   ビジュアル ホスティング API にアクセスできる最初の独立した WebView2 プレリリース パッケージをリリースしました。  WebView チームは、 [新しい試験的な API を含む APISample][GithubMicrosoftedgeWebview2samplesMain] を更新しました。  
    
    *   コンポジション ツリーに接続し、WebView の入力を提供するための [ICoreWebView2ExperimentalCompositionController][ReferenceWin32Icorewebview2experimentalcompositioncontroller09488] インターフェイスが追加されました。  
    *   [ICoreWebView2ExperimentalPointerInfo][ReferenceWin32Icorewebview2experimentalpointerinfo09488]が追加されました。この情報には、 `POINTER_INFO`  このオブジェクトは、ポインター入力を WebView に挿入するために SendPointerInput に渡されます。  
    *   [ICoreWebView2ExperimentalCursorChangedEventHandler][ReferenceWin32Icorewebview2experimentalcursorchangedeventhandler09488]が追加されました。このイベントは、WebView 上のマウス カーソルを変更する必要がある場合にアプリに指示します。  WebView のテキスト ボックスの上にマウスポインターを置く場合、カーソルは矢印からセレクターに変わります。  アプリ上のプロパティは、マウス カーソルが WebView に対して現在何をする必要かを `cursor` `CompositionController` 示します。  
    
## 0.9.430  

[NuGet パッケージ][NuGetGallery0.9.430] \|Microsoft Edge バージョン 82.0.430.0。  

WebView2 SDK は正式な Win32 C++ ベータ版で、フィードバックからのいくつかの機能要求が組み込まれています。  WebView チームは、変更が大きかったリリースの数を制限しようとする。  一般提供のアプローチとして、いくつかの重要な変更がベータリリースに組み込まれる。  

*   > [!IMPORTANT]
    > **Breaking Change**: 最終リリースが近づくにつれて、WebView2 API が Windows API の名前付け規則に準拠するために、プレフィックス *IWebView2WebView*   の名前が *ICoreWebView2*   に変更されました。  さらに、UI フレームワークから WebView2 SDK を活用するために `ICoreWebView2` [、ICoreWebView2 と ICoreWebView2Host][ReferenceWin32Icorewebview209430] に分かれた WebView チームを [使用][ReferenceWin32Icorewebview2host09430]します。  `ICoreWebView2Host` ウィンドウとコンポジションに関連するサイズ変更、表示と非表示、フォーカス、その他の機能をサポートします。  ICoreWebView2 は、他のすべての WebView2 機能をサポートしています。  変更の組み込みについて詳しくは、WebView2 [][GithubMicrosoftedgeWebview2samplesPr17] [APISample][GithubMicrosoftedgeWebview2samplesMain]プロジェクトの WebView2 プル要求に移動してください。  
    
*   > [!IMPORTANT]
    > **Breaking Change**: Split [DocumentStateChanged][ReferenceWin32Iwebview2webviewAddDocumentstatechanged08190] into three components:  [SourceChanged,][ReferenceWin32Icorewebview2AddSourcechanged09430] [ContentLoading][ReferenceWin32Icorewebview2AddContentloading09430], and [HistoryChanged][ReferenceWin32Icorewebview2AddHistorychanged09430].  ソース URL が変更された場合、 `SourceChanged` イベントが実行されます。  履歴の状態が変更された場合、 `HistoryChanged` イベントが実行されます。  この `ContentLoading` イベントは、新しいドキュメントが読み込まれるときに、最初のスクリプトの前に実行されます。  
    
*   ARM64 アーキテクチャのサポートが追加されました。  
*   タッチ スクリーン デバイス用のソフト入力パネル \(SIP\) のサポートが追加されました。  
*   Windows Server 2016 のWindows Server 2008 R2、Windows Server 2012、Windows Server 2012 R2、Windows Server 2016 のサポートが追加されました。  
*   ウィンドウ モードでウィンドウに従うステータス バーの [NotifyParentWindowPositionChanged][ReferenceWin32Icorewebview2hostNotifyparentwindowpositionchanged09430] が追加されました。  また、アクセシビリティ機能を機能するために、ウィンドウレス モードで変更を実装します。  
*   リモート オブジェクトから Web ページにアクセスできるかどうかをグローバルに制御する [AreRemoteObjectsAllowed][ReferenceWin32Icorewebview2settingsGetAreremoteobjectsallowed09430] 設定が追加されました。  既定ではオン `AreRemoteObjectsAllowed` になっているので [、AddRemoteObject][ReferenceWin32Icorewebview2Addremoteobject09430] によって追加されたリモート オブジェクトには Web ページからアクセスできます。  オフ `AreRemoteObjectsAllowed` にすると、Web ページからオブジェクトにアクセスできない。  変更は、次のナビゲーション イベントに適用されます。  
*   [IsZoomControlEnabled][ReferenceWin32Icorewebview2settingsGetIszoomcontrolenabled09430]設定が追加され、ユーザーが \(または + マウス ホイール\) を使用して WebView のズームに影響を与えるのを `ctrl` + `+` `ctrl` + `-` `ctrl` 防ぐ機能が追加されました。  設定をオフにした場合でも [、put_ZoomFactorを][ReferenceWin32Icorewebview2hostPutZoomfactor09430] 使ってズームを設定できます。  
*   ZoomFactor が現在の WebView にのみ適用されるに変更されました。  現在の WebView に対するズームの変更は、同じ原点のサイトを使用して移動した他の WebView には影響を与えいません。  詳細については、次 [のリンク][ReferenceWin32Icorewebview2hostGetZoomfactor09430]get_ZoomFactor。  
*   WebView の ZoomView UI を非表示に \([#95][GithubMicrosoftedgeWebviewfeedbackIssue95]\)。  
*   [SetBoundsAndZoomFactor を追加しました][ReferenceWin32Icorewebview2hostSetboundsandzoomfactor09430]。  これで、WebView のズーム倍率と範囲を同時に設定できます。  
*   [WindowCloseRequested イベントが追加][ReferenceWin32Icorewebview2AddWindowcloserequested09430]されました。  詳細については、\( [add_WindowCloseRequested][ReferenceWin32Icorewebview2AddWindowcloserequested09430] \)[に#119][GithubMicrosoftedgeWebviewfeedbackIssue119]してください。  
*   JavaScript ダイアログ イベントの `beforeunload` ダイアログの種類のサポートが追加され、列挙 [CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_BEFOREUNLOAD][ReferenceWin32Icorewebview2CoreWebview2ScriptDialogKind09430] が追加されました。  
*   [GetHeaders][ReferenceWin32Icorewebview2httprequestheadersGetheaders09430]を HttpRequestHeaders、GetHeader を HttpResponseHeaders、および httpHeadersCollectionIterator [get_HasCurrentHeaderプロパティに][ReferenceWin32Icorewebview2httpheaderscollectioniteratorGetHascurrentheader09430]追加しました。 [][ReferenceWin32Icorewebview2httpresponseheadersGetheader09430]  
*   > [!IMPORTANT]
    > **Breaking Change**: 変更 `DevToolsProtocolEventReceived` された動作。  ここで、特定の DevTools Protocol イベントに対して[DevToolsProtocolEventReceiver][ReferenceWin32Icorewebview2devtoolsprotocoleventreceiver09430]を作成し、次のコマンドを使用してそのようなイベントをサブスクライブ/[サブスクライブ解除][ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverAddDevtoolsprotocoleventreceived09430] / [add_DevToolsProtocolEventReceived remove_DevToolsProtocolEventReceived。][ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverRemoveDevtoolsprotocoleventreceived09430]  
    
*   > [!IMPORTANT]
    > **Breaking Change**: Get_WebMessageAsString `WebMessageReceivedEventArgs` [][ReferenceWin32Iwebview2webmessagereceivedeventargsGetWebmessageasstring08190] [TryGetWebMessageAsString メソッドに変更][ReferenceWin32Icorewebview2webmessagereceivedeventargsTrygetwebmessageasstring09430]されました。  
    
*   > [!IMPORTANT]
    > **Breaking Change**: Changed `AcceleratorKeyPressedEventArgs` [Handle][ReferenceWin32Iwebview2acceleratorkeypressedeventargsHandle08190]メソッドを get_Handledプロパティに変更しました。 [][ReferenceWin32Icorewebview2acceleratorkeypressedeventargsGetHandled09430]  
    
## 0.8.355  

[NuGet パッケージ][NuGetGallery0.8.355] \|Microsoft Edge バージョン 80.0.355.0。  

*   リリースされた WebView2API サンプルは、WebView2 SDK の包括的なガイドです。  詳細については、API サンプルに [移動してください][GithubMicrosoftedgeWebview2samplesApisample]。  
*   英語 \( \ ( \ ) 以外のすべての言語に IME[#30][GithubMicrosoftedgeWebviewfeedbackIssue30]しました。  
*   バグ 報告に応じてイベントの API `WebResourceRequested` サーフェスを更新しました。  同時にフィルターを指定し、作成時にイベントを指定する機能は廃止されました。  Web リソース要求イベントを作成するには、add_WebResourceRequested を使用してイベントを追加し[、AddWebResourceRequestedFilter][ReferenceWin32Iwebview2webview5Addwebresourcerequestedfilter08190]を使用してフィルターを追加します。 [][ReferenceWin32Iwebview2webview5AddWebresourcerequested08190]  [RemoveWebResourceRequestedFilter][ReferenceWin32Iwebview2webview5Removewebresourcerequestedfilter08190] はフィルター \([#36][GithubMicrosoftedgeWebviewfeedbackIssue36]\) \( #74 \)[を削除][GithubMicrosoftedgeWebviewfeedbackIssue74]します。  
*   > [!IMPORTANT]
    > **Breaking Change**: 全画面での動作が変更されました。  非推奨 [の IsFullScreenAllowed][ReferenceWin32Iwebview2settingsGetIsfullscreenallowedDeprecated08190]。  既定では、WebView \(video\など) の要素が全画面に設定されている場合、WebView の境界が埋め込みます。  [ContainsFullScreenElementChanged][ReferenceWin32Iwebview2containsfullscreenelementchangedeventhandler08190]イベントと[][ReferenceWin32Iwebview2webview5GetContainsfullscreenelement08190]get_ContainsFullScreenElement を使って、要素が全画面表示モードに入る場合に、アプリで WebView のサイズを変更する方法を指定します。  
    
## 0.8.314  

[NuGet パッケージ][NuGetGallery0.8.314] \|Microsoft Edge バージョン 80.0.314.0。  

*   Windows 7、Windows 8、Windows 8.1 のサポートが追加されました。  
*   WebView2 Visual Studioコード Visual Studioサポートを追加しました。  次に、IDE から直接 WebView2 でスクリプトをデバッグします。  詳細については [、WebView2 コントロールを使用して開発するときにデバッグする方法に移動します][HowtoDebug]。  
*   WebView2 の実行中のスクリプトが、アプリの Win32 コンポーネントから IDispatch オブジェクトにアクセスし、IDispatch オブジェクトのプロパティにアクセスするために追加 `Native Object Injection` されました。  詳細については [、AddRemoteObject][ReferenceWin32Iwebview2webview4Addremoteobject08190] \( #17 \)[に移動][GithubMicrosoftedgeWebviewfeedbackIssue17]します。  
*   イベントが `AcceleratorKeyPressed` 追加されました。  詳細については、\( [add_AcceleratorKeyPressed][ReferenceWin32Iwebview2webview4AddAcceleratorkeypressed08190] \)[に#57][GithubMicrosoftedgeWebviewfeedbackIssue57]してください。  
*   オフ `Context Menus` にしました。  詳細については、\( [put_AreDefaultContextMenusEnabled][ReferenceWin32Iwebview2settings2PutAredefaultcontextmenusenabled08190] \)[に][GithubMicrosoftedgeWebviewfeedbackIssue57]#57してください。  
*   更新されました `DPI Awareness` 。  現在、WebView の DPI 対応はホスト アプリの DPI 対応と同じです。  
    
    > [!NOTE]
    > 別のハイブリッド アプリが元の WebView とは異なる DPI 対応で起動された場合、同じ \( #1 \) の場合、新しい WebView `user data folder` [は起動][GithubMicrosoftedgeWebviewfeedbackIssue1]されません。  
    
*   WebView2 が、WebView でホストされている Web コンテンツによって要求される通知アクセス許可要求 `Notification Change Behavior` を自動的に拒否するように更新されました。  
    
## 0.8.270  

[NuGet パッケージ][NuGetGallery0.8.270] \|Microsoft Edge バージョン 78.0.270.0。  

*   ドキュメント タイトル `DocumentTitleChanged` の変更 \( \#27 \)[を示すイベントが][GithubMicrosoftedgeWebviewfeedbackIssue27]追加されました。  
*   API `GetWebView2BrowserVersionInfo` \([\#18][GithubMicrosoftedgeWebviewfeedbackIssue18]\) が追加されました。  
*   イベントが追加 `NewWindowRequested` されました。  
*   削除する `CreateWebView2EnvironmentWithDetails` 関数を更新しました `releaseChannelPreference` 。  関数の詳細については `CreateWebView2EnvironmentWithDetails` [、CreateWebView2EnvironmentWithDetails に移動します][ReferenceWin32WebView2IdlCreatewebview2environmentwithdetails08190]。  レジストリと環境変数のオーバーライドは引き続きサポートされています。  オーバーライドされない限り、既定のチャネル設定が使用されます。  
    チャネル検索中、WebView チームは、WebView2 SDK と互換性がない以前のチャネル バージョンをスキップします。  
    WebView チームは、より安定したチャネルを選択して、エンド ユーザーにとって最も一貫した動作を保証します。  最新の Canary ビルドでテストする場合は、アプリを起動する前に環境変数を設定する `WEBVIEW2_RELEASE_CHANNEL_PREFERENCE` `1` スクリプトを作成する必要があります。  
*   指定しない場合 `CreateWebView2EnvironmentWithDetails` に選択するロジックを使用して関数 `userDataFolder` を更新しました。  関数の詳細については `CreateWebView2EnvironmentWithDetails` [、CreateWebView2EnvironmentWithDetails に移動します][ReferenceWin32WebView2IdlCreatewebview2environmentwithdetails08190]。  以前に既定の場所を使用した場合、新しい SDK に切り替える場合、既定はリセット \(ホスト コード ディレクトリの新しい場所に設定\) され、状態もリセット `userDataFolder` `userDataFolder` されます。  指定されたディレクトリに書き込むアクセス許可がホスト プロセスに付与されていない場合、関数 `CreateWebView2EnvironmentWithDetails` は失敗する可能性があります。  古いディレクトリから新しいディレクトリに `user data folder` データをコピーできます。  
    
## 0.8.230  

[NuGet パッケージ][NuGetGallery0.8.230] \|Microsoft Edge バージョン 77.0.230.0。  

*   すべてのナビゲーション `Stop` と保留中のリソース フェッチ \([\#28][GithubMicrosoftedgeWebviewfeedbackIssue28]\) を停止する API が追加されました。  
*   `.tlb`NuGet パッケージ \( \#22 \)[にファイルを追加][GithubMicrosoftedgeWebviewfeedbackIssue22]しました。  
*   NuGet パッケージ \( \#32 \) のインストーラー一覧に .NET[プロジェクトを追加][GithubMicrosoftedgeWebviewfeedbackIssue32]しました。  
    
## 0.8.190  

[NuGet パッケージ][NuGetGallery0.8.190] \|Microsoft Edge バージョン 77.0.190.0。  

*   ユーザーが `get_AreDevToolsEnabled` / `put_AreDevToolsEnabled` DevTools \( \#16 \) を開くことができるか制御[するために追加][GithubMicrosoftedgeWebviewfeedbackIssue16]されました。  
*   ステータス バー `get_IsStatusBarEnabled` / `put_IsStatusBarEnabled` が表示される \( \#19 \)[を制御するために追加][GithubMicrosoftedgeWebviewfeedbackIssue19]されます。  
*   ナビゲーション履歴 `get_CanGoBack` / `GoBack` / `get_CanGoForward` / `GoForward` を行き来する場合に追加されました。  
*   WebView で HTTP ヘッダーを表示および変更する HTTP ヘッダーの種類 `IWebView2HttpHeadersCollectionIterator` / `IWebView2HttpRequestHeaders` / `IWebView2HttpRequestHeaders` \( \) が追加されました。  
*   64 ビット コンピューター \( \#13 \) に 32 ビット WebView[サポートが追加][GithubMicrosoftedgeWebviewfeedbackIssue13]されました。  
*   WEBView IDL を SDK \([\#14][GithubMicrosoftedgeWebviewfeedbackIssue14]\) に追加しました。  
*   インターフェイス ID オブジェクト `IID\_\*` \( \#12 \)[をサポートするライブラリが追加][GithubMicrosoftedgeWebviewfeedbackIssue12]されました。  
*   SDK の NuGet ファイルへの DLL ファイルのパス、リンク、および自動 `TARGET` コピーが追加されました。  
*   スクリプトで要求 `window.open()` を有効にしました。  
    
## 0.8.149  

[NuGet パッケージ][NuGetGallery0.8.149] \|Microsoft Edge バージョン 76.0.149.0。  

開発者向けの最初のプレビュー リリース。  

<!-- Links -->  

[VersioningDoc]: ./concepts/versioning.md#matching-webview2-runtime-versions
[ConceptsDistribution]: ./concepts/distribution.md "WebView2 を使用したアプリケーションの配布 |Microsoft Docs"  
[ConceptsDistributionEvergreenMode]: ./concepts/distribution.md#evergreen-distribution-mode "常用配布モード - WebView2 を使用したアプリケーションの|Microsoft Docs"  
[Webview2ConceptsDistributionFixedVersionMode]: ./concepts/distribution.md#fixed-version-distribution-mode "固定バージョン配布モード - WebView2 を使用したアプリケーションの|Microsoft Docs"  
[Webview2ConceptsDistributionUnderstandRuntimeInstaller]: ./concepts/distribution.md#understanding-the-webview2-runtime "WebView2 ランタイムとインストーラーについて - WebView2 を使用したアプリケーションの配布|Microsoft Docs"  
[Webview2ConceptsEnterpriseGroupPoliciesForWebview2]: ./concepts/enterprise.md#group-policies-for-webview2 "WebView2 のグループ ポリシー - WebView2 アプリケーションの管理|Microsoft Docs"  
[ConceptsVersioning]: ./concepts/versioning.md "ブラウザーのバージョンと WebView2 について | Microsoft Docs"  
[ConceptsVersioningExperimentalApis]: ./concepts/versioning.md#experimental-apis "試験的な API - ブラウザーのバージョンと WebView2 |Microsoft Docs"  
[GettingstartedWinforms]: ./gettingstarted/winforms.md "Windows Forms アプリの WebView2 の使用を開始する|Microsoft Docs"  
[GettingstartedWpf]: ./gettingstarted/wpf.md "WPF アプリケーションでの WebView2 の|Microsoft Docs"  
[HowtoDebug]: ./howto/debug.md "WebView2 コントロールを使用して開発するときにデバッグする|Microsoft Docs"  

[ReferenceWin32Iwebview2acceleratorkeypressedeventargsHandle08190]: /microsoft-edge/webview2/reference/win32/iwebview2acceleratorkeypressedeventargs?view=webview2-0.8.355&preserve-view=true#handle "Handle - インターフェイス IWebView2AcceleratorKeyPressedEventArgs |Microsoft Docs"  
[ReferenceWin32Iwebview2containsfullscreenelementchangedeventhandler08190]: /microsoft-edge/webview2/reference/win32/iwebview2containsfullscreenelementchangedeventhandler?view=webview2-0.8.355&preserve-view=true "interface IWebView2ContainsFullScreenElementChangedEventHandler |Microsoft Docs"  
[ReferenceWin32Iwebview2settings2PutAredefaultcontextmenusenabled08190]: /microsoft-edge/webview2/reference/win32/iwebview2settings2?view=webview2-0.8.355&preserve-view=true#put_aredefaultcontextmenusenabled "put_AreDefaultContextMenusEnabled - インターフェイス IWebView2Settings2 |Microsoft Docs"  
[ReferenceWin32Iwebview2settingsGetIsfullscreenallowedDeprecated08190]: /microsoft-edge/webview2/reference/win32/iwebview2settings?view=webview2-0.8.355&preserve-view=true#get_isfullscreenallowed_deprecated "get_IsFullscreenAllowed_deprecated - インターフェイス IWebView2Settings |Microsoft Docs"  
[ReferenceWin32Iwebview2webmessagereceivedeventargsGetWebmessageasstring08190]: /microsoft-edge/webview2/reference/win32/iwebview2webmessagereceivedeventargs?view=webview2-0.8.355&preserve-view=true#get_webmessageasstring "get_WebMessageAsString - インターフェイス IWebView2WebMessageReceivedEventArgs |Microsoft Docs"  
[ReferenceWin32Iwebview2webview4AddAcceleratorkeypressed08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview4?view=webview2-0.8.355&preserve-view=true#add_acceleratorkeypressed "add_AcceleratorKeyPressed - インターフェイス IWebView2WebView4 |Microsoft Docs"  
[ReferenceWin32Iwebview2webviewAddDocumentstatechanged08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview?view=webview2-0.8.355&preserve-view=true#add_documentstatechanged "add_DocumentStateChanged - インターフェイス IWebView2WebView |Microsoft Docs"  
[ReferenceWin32Iwebview2webview4Addremoteobject08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview4?view=webview2-0.8.355&preserve-view=true#addremoteobject "AddRemoteObject - インターフェイス IWebView2WebView4 |Microsoft Docs"  
[ReferenceWin32Iwebview2webview5AddWebresourcerequested08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#add_webresourcerequested "add_WebResourceRequested - インターフェイス IWebView2WebView5 |Microsoft Docs"  
[ReferenceWin32Iwebview2webview5Addwebresourcerequestedfilter08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#addwebresourcerequestedfilter "AddWebResourceRequestedFilter - インターフェイス IWebView2WebView5 |Microsoft Docs"  
[ReferenceWin32Iwebview2webview5GetContainsfullscreenelement08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#get_containsfullscreenelement "get_ContainsFullScreenElement - インターフェイス IWebView2WebView5 |Microsoft Docs"  
[ReferenceWin32Iwebview2webview5Removewebresourcerequestedfilter08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#removewebresourcerequestedfilter "RemoveWebResourceRequestedFilter - インターフェイス IWebView2WebView5 |Microsoft Docs"  
[ReferenceWin32WebView2IdlCreatewebview2environmentwithdetails08190]:  /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.8.355&preserve-view=true#createwebview2environmentwithdetails "CreateWebView2EnvironmentWithDetails - Globals |Microsoft Docs"  

[ReferenceWin32Icorewebview209430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true "interface ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2acceleratorkeypressedeventargsGetHandled09430]: /microsoft-edge/webview2/reference/win32/icorewebview2acceleratorkeypressedeventargs?view=webview2-0.9.430&preserve-view=true#get_handled "get_Handled - インターフェイス ICoreWebView2AcceleratorKeyPressedEventArgs |Microsoft Docs"  
[ReferenceWin32Icorewebview2AddContentloading09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_contentloading "add_ContentLoading - インターフェイス ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2AddHistorychanged09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_historychanged "add_HistoryChanged - インターフェイス ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2Addremoteobject09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#addremoteobject "AddRemoteObject - インターフェイス ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2AddSourcechanged09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_sourcechanged "add_SourceChanged - インターフェイス ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2AddWindowcloserequested09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_windowcloserequested "add_WindowCloseRequested - インターフェイス ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2CoreWebview2ScriptDialogKind09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#core_webview2_script_dialog_kind "CORE_WEBVIEW2_SCRIPT_DIALOG_KIND - インターフェイス ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2devtoolsprotocoleventreceiver09430]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-0.9.430&preserve-view=true "interface ICoreWebView2DevToolsProtocolEventReceiver |Microsoft Docs"  
[ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverAddDevtoolsprotocoleventreceived09430]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-0.9.430&preserve-view=true#add_devtoolsprotocoleventreceived "add_DevToolsProtocolEventReceived - インターフェイス ICoreWebView2DevToolsProtocolEventReceiver |Microsoft Docs"  
[ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverRemoveDevtoolsprotocoleventreceived09430]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-0.9.430&preserve-view=true#remove_devtoolsprotocoleventreceived "remove_DevToolsProtocolEventReceived - インターフェイス ICoreWebView2DevToolsProtocolEventReceiver |Microsoft Docs"  
[ReferenceWin32Icorewebview2environmentGetBrowserversioninfo09430]: /microsoft-edge/webview2/reference/win32/icorewebview2environment?view=webview2-0.9.430&preserve-view=true#get_browserversioninfo "get_BrowserVersionInfo - インターフェイス ICoreWebView2Environment |Microsoft Docs"  
[ReferenceWin32Icorewebview2host09430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true "interface ICoreWebView2Host |Microsoft Docs"  
[ReferenceWin32Webview2IdlGetcorewebview2browserversioninfo09430]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.430&preserve-view=true#getcorewebview2browserversioninfo "GetCoreWebView2BrowserVersionInfo - Globals |Microsoft Docs"  
[ReferenceWin32Icorewebview2hostGetZoomfactor09430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#get_zoomfactor "get_ZoomFactor - インターフェイス ICoreWebView2Host |Microsoft Docs"  
[ReferenceWin32Icorewebview2hostNotifyparentwindowpositionchanged09430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#notifyparentwindowpositionchanged "NotifyParentWindowPositionChanged - インターフェイス ICoreWebView2Host |Microsoft Docs"  
[ReferenceWin32Icorewebview2hostPutZoomfactor09430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#put_zoomfactor "put_ZoomFactor - インターフェイス ICoreWebView2Host |Microsoft Docs"  
[ReferenceWin32Icorewebview2hostSetboundsandzoomfactor09430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#setboundsandzoomfactor "SetBoundsAndZoomFactor - インターフェイス ICoreWebView2Host |Microsoft Docs"  
[ReferenceWin32Icorewebview2httpheaderscollectioniteratorGetHascurrentheader09430]: /microsoft-edge/webview2/reference/win32/icorewebview2httpheaderscollectioniterator?view=webview2-0.9.430&preserve-view=true#get_hascurrentheader "get_HasCurrentHeader - インターフェイス ICoreWebView2HttpHeadersCollectionIterator |Microsoft Docs"  
[ReferenceWin32Icorewebview2httprequestheadersGetheaders09430]: /microsoft-edge/webview2/reference/win32/icorewebview2httprequestheaders?view=webview2-0.9.430&preserve-view=true#getheaders "GetHeaders - インターフェイス ICoreWebView2HttpRequestHeaders |Microsoft Docs"  
[ReferenceWin32Icorewebview2httpresponseheadersGetheader09430]: /microsoft-edge/webview2/reference/win32/icorewebview2httpresponseheaders?view=webview2-0.9.430&preserve-view=true#getheader "GetHeader - インターフェイス ICoreWebView2HttpResponseHeaders |Microsoft Docs"  
[ReferenceWin32Icorewebview2Removeremoteobject09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#removeremoteobject "RemoveRemoteObject - インターフェイス ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2settingsGetAreremoteobjectsallowed09430]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.430&preserve-view=true#get_areremoteobjectsallowed "get_AreRemoteObjectsAllowed - インターフェイス ICoreWebView2Settings |Microsoft Docs"  
[ReferenceWin32Icorewebview2settingsGetIszoomcontrolenabled09430]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.430&preserve-view=true#get_iszoomcontrolenabled "get_IsZoomControlEnabled - インターフェイス ICoreWebView2Settings |Microsoft Docs"  
[ReferenceWin32Icorewebview2webmessagereceivedeventargsTrygetwebmessageasstring09430]: /microsoft-edge/webview2/reference/win32/icorewebview2webmessagereceivedeventargs?view=webview2-0.9.430&preserve-view=true#trygetwebmessageasstring "TryGetWebMessageAsString - インターフェイス ICoreWebView2WebMessageReceivedEventArgs |Microsoft Docs"  

[ReferenceWin32Icorewebview2AddFramenavigationcompleted09488]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#add_framenavigationcompleted "add_FrameNavigationCompleted - インターフェイス ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2Addhostobjecttoscript09488]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#addhostobjecttoscript "AddHostObjectToScript - インターフェイス ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2AddNewwindowrequested09488]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#add_newwindowrequested "add_NewWindowRequested - インターフェイス ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2environmentGetBrowserversionstring09488]: /microsoft-edge/webview2/reference/win32/icorewebview2environment?view=webview2-0.9.488&preserve-view=true#get_browserversionstring " |Microsoft Docs"  
[ReferenceWin32Icorewebview2environmentoptions09488]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions?view=webview2-0.9.488&preserve-view=true "interface ICoreWebView2EnvironmentOptions |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalcompositioncontroller09488]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller?view=webview2-0.9.488-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalCompositionController |Microsoft Docs"
[ReferenceWin32Icorewebview2experimentalcompositioncontroller09488]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller?view=webview2-0.9.488-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalCompositionController |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalcursorchangedeventhandler09488]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcursorchangedeventhandler?view=webview2-0.9.488-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalCursorChangedEventHandler |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalpointerinfo09488]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalpointerinfo?view=webview2-0.9.488-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalPointerInfo |Microsoft Docs"  
[ReferenceWin32Icorewebview2Removehostobjectfromscript09488]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#removehostobjectfromscript "RemoveHostObjectFromScript - インターフェイス ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2settingsGetAreremoteobjectsallowed09488]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.488&preserve-view=true#get_areremoteobjectsallowed "get_AreRemoteObjectsAllowed - インターフェイス ICoreWebView2Settings |Microsoft Docs"  
[ReferenceWin32Icorewebview2settingsGetIsbuiltinerrorpageenabled09488]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.488&preserve-view=true#get_isbuiltinerrorpageenabled " |Microsoft Docs"  
[ReferenceWin32Webview2IdlCreatecorewebview2environmentwithdetails09488]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.488&preserve-view=true#createcorewebview2environmentwithdetails "CreateCoreWebView2EnvironmentWithDetails - Globals |Microsoft Docs"  
[ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions09488]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.488&preserve-view=true#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions - Globals | Microsoft Docs"  
[ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring09488]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.488&preserve-view=true#getavailablecorewebview2browserversionstring "GetAvailableCoreWebView2BrowserVersionString - グローバル | Microsoft Docs"  

[ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseAddRasterizationscalechanged]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.721-prerelease&preserve-view=true#add_rasterizationscalechanged "add_RasterizationScaleChanged - インターフェイス ICoreWebView2ExperimentalController |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetBoundsMode]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.721-prerelease&preserve-view=true#get_boundsmode "get_BoundsMode - インターフェイス ICoreWebView2ExperimentalController |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetRasterizationscale]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.721-prerelease&preserve-view=true#get_rasterizationscale "get_RasterizationScale - インターフェイス ICoreWebView2ExperimentalController |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetShouldDetectMonitorScaleChanges]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.721-prerelease&preserve-view=true#get_shoulddetectmonitorscalechanges "get_ShouldDetectMonitorScaleChanges - インターフェイス ICoreWebView2ExperimentalController |Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2Core]: /dotnet/api/microsoft.web.webview2.core "Microsoft.Web.WebView2.Core 名前空間 |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2Wpf]: /dotnet/api/microsoft.web.webview2.wpf "Microsoft.Web.WebView2.Wpf 名前空間 |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2Winforms]: /dotnet/api/microsoft.web.webview2.winforms "Microsoft.Web.WebView2.WinForms 名前空間 |Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2CoreWebview2runtimenotfoundexception]: /dotnet/api/microsoft.web.webview2.core.webview2runtimenotfoundexception "CoreWebView2.WebView2RuntimeNotFound (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2]: /dotnet/api/microsoft.web.webview2.core.corewebview2 "CoreWebView2 クラス (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2environment]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment "CoreWebView2Environment クラス (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentComparebrowserversions]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.comparebrowserversions "CoreWebView2Environment.CompareBrowserVersions(String, String) メソッド (Microsoft.Web.WebView2.Core) |Microsoft Docs"
[DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentGetavailablebrowserversionstring]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.getavailablebrowserversionstring "CoreWebView2Environment.GetAvailableBrowserVersionString(String) メソッド (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Newwindowrequested]: /dotnet/api/microsoft.web.webview2.core.corewebview2.newwindowrequested "CoreWebView2.NewWindowRequested イベント (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Permissionrequested]: /dotnet/api/microsoft.web.webview2.core.corewebview2.permissionrequested "CoreWebView2.PermissionRequested イベント (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Scriptdialogopening]: /dotnet/api/microsoft.web.webview2.core.corewebview2.scriptdialogopening "CoreWebView2.ScriptDialogOpening イベント (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Webresourcerequested]: /dotnet/api/microsoft.web.webview2.core.corewebview2.webresourcerequested "CoreWebView2.WebResourceRequested イベント (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2httprequestheaders]: /dotnet/api/microsoft.web.webview2.core.corewebview2httprequestheaders "CoreWebView2HttpRequestHeaders クラス (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2httpresponseheaders]: /dotnet/api/microsoft.web.webview2.core.corewebview2httpresponseheaders "CoreWebView2HttpResponseHeaders クラス (Microsoft.Web.WebView2.Core) |Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2WinformsCorewebview2creationproperties]: /dotnet/api/microsoft.web.webview2.winforms.corewebview2creationproperties "CoreWebView2CreationProperties クラス (Microsoft.Web.WebView2.Winforms) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2Source]: /dotnet/api/microsoft.web.webview2.winforms.webview2.source "Webview2.Source クラス (Microsoft.Web.WebView2.Winforms) |Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2WpfWebview2Buildwindowcore]: /dotnet/api/microsoft.web.webview2.wpf.webview2.buildwindowcore "WebView2.BuildWindowCore(HandleRef) メソッド (Microsoft.Web.WebView2.Wpf) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2Destroywindowcore]: /dotnet/api/microsoft.web.webview2.wpf.webview2.destroywindowcore "WebView2.DestroyWindowCore(HandleRef) メソッド (Microsoft.Web.WebView2.Wpf) |Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2WpfWebview2Acceleratorkeypressed]: /dotnet/api/microsoft.web.webview2.wpf.webview2.acceleratorkeypressed "microsoft.web.webview2.wpf.webview2.acceleratorkeypressed |Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2Corewebview2initializationcompletedeventargs]: /dotnet/api/microsoft.web.webview2.core.corewebview2initializationcompletedeventargs "CoreWebView2InitializationCompletedEventArgs クラス |Microsoft Docs"  

[ReferenceWin32Icorewebview2Addhostobjecttoscript09538]: /microsoft-edge/webview2/reference/win32/icorewebview2#addhostobjecttoscript?view=webview2-0.9.538&preserve-view=true "AddHostObjectToScript - インターフェイス ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalAddWebresourceresponsereceived09538]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-0.9.538-prerelease&preserve-view=true#add_webresourceresponsereceived "add_WebResourceResponseReceived - インターフェイス ICoreWebView2Experimental |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentaloptionsGetIssinglesignonusingosprimaryaccountenabled09538]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalenvironmentoptions?view=webview2-0.9.538-prerelease&preserve-view=true#get_issinglesignonusingosprimaryaccountenabled "get_IsSingleSignOnUsingOSPrimaryAccountEnabled - インターフェイス ICoreWebView2ExperimentalEnvironmentOptions |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalnewwindowrequestedeventargsGetWindowfeatures09538]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalnewwindowrequestedeventargs?view=webview2-0.9.538-prerelease&preserve-view=true#get_windowfeatures "get_WindowFeatures - インターフェイス ICoreWebView2ExperimentalNewWindowRequestedEventArgs |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalwindowfeatures09538]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwindowfeatures?view=webview2-0.9.538-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalWindowFeatures |Microsoft Docs"  
[ReferenceWin32Icorewebview2newwindowrequestedeventargsGetIsuserinitiated09538]: /microsoft-edge/webview2/reference/win32/icorewebview2newwindowrequestedeventargs?view=webview2-0.9.538&preserve-view=true#get_isuserinitiated "get_IsUserInitiated インターフェイス ICoreWebView2NewWindowRequestedEventArgs |Microsoft Docs"  
[ReferenceWin32Icorewebview2settingsGetArehostobjectsallowed09538]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.538&preserve-view=true#get_arehostobjectsallowed "get_AreHostObjectsAllowed - インターフェイス ICoreWebView2Settings |Microsoft Docs"  
[ReferenceWin32IdlCreatecorewebview2environmentwithoptions09538]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.538&preserve-view=true#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions - Globals | Microsoft Docs"  

[ReferenceWin32Icorewebview2environmentoptionsGetAllowsinglesignonusingosprimaryaccount09622]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions?view=webview2-0.9.622&preserve-view=true#get_allowsinglesignonusingosprimaryaccount "get_AllowSingleSignOnUsingOSPrimaryAccount - インターフェイス ICoreWebView2EnvironmentOptions |Microsoft Docs"  
[ReferenceWin32Icorewebview2environmentoptionsPutAdditionalbrowserarguments09622]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions?view=webview2-0.9.622&preserve-view=true#put_additionalbrowserarguments "put_AdditionalBrowserArguments - インターフェイス ICoreWebView2EnvironmentOptions |Microsoft Docs"  
[ReferenceWin32Icorewebview2newwindowrequestedeventargsGetWindowfeatures09622]: /microsoft-edge/webview2/reference/win32/icorewebview2newwindowrequestedeventargs?view=webview2-0.9.622&preserve-view=true#get_windowfeatures "get_WindowFeatures - インターフェイス ICoreWebView2NewWindowRequestedEventArgs |Microsoft Docs"  
[ReferenceWin32Icorewebview2windowfeatures09622]: /microsoft-edge/webview2/reference/win32/icorewebview2windowfeatures?view=webview2-0.9.622&preserve-view=true "interface ICoreWebView2WindowFeatures |Microsoft Docs"  
[ReferenceWin32IdlCreatecorewebview2environmentwithoptions09622]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.622&preserve-view=true#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions - Globals |Microsoft Edge"  
[ReferenceWin32Icorewebview2experimentalenvironment09628]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalenvironment?view=webview2-0.9.628-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalEnvironment |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalwebresourceresponsereceivedeventargsPopulateresponsecontent09628]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwebresourceresponsereceivedeventargs?view=webview2-0.9.628-prerelease&preserve-view=true#populateresponsecontent "PopulateResponseContent - interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs |Microsoft Docs"  

[ReferenceWin32Icorewebview2experimentalAddDomcontentloaded10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#add_domcontentloaded "add_DOMContentLoaded - インターフェイス ICoreWebView2Experimental |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalAddWebresourceresponsereceived10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#add_webresourceresponsereceived "add_WebResourceResponseReceived - インターフェイス ICoreWebView2Experimental |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalGetCookiemanager10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#get_cookiemanager "get_CookieManager - インターフェイス ICoreWebView2Experimental |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalGetEnvironment10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#get_environment "get_Environment - インターフェイス ICoreWebView2Experimental |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalNavigatewithwebresourcerequest10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#navigatewithwebresourcerequest "NavigateWithWebResourceRequest - インターフェイス ICoreWebView2Experimental |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalcompositioncontroller2GetSystemcursorid10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller2#get_systemcursorid?view=webview2-1.0.674-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalWebResourceResponseView |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalwebresourceresponseview10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwebresourceresponseview?view=webview2-1.0.674-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalWebResourceResponseView |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalwebresourceresponseviewGetcontent10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwebresourceresponseview?view=webview2-1.0.674-prerelease&preserve-view=true#getcontent "GetContent - interface ICoreWebView2ExperimentalWebResourceResponseView |Microsoft Docs"  

[ReferenceWin32Icorewebview2experimentalcompositioncontroller3]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller3?view=webview2-1.0.721-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalCompositionController3 |Microsoft Docs"  

[DeployedgeMicrosoftEdgePolicies]: /deployedge/microsoft-edge-policies "Microsoft Edge - ポリシー|Microsoft Docs"  
[DeployedgeMicrosoftEdgeWebviewPolicies]: /deployedge/microsoft-edge-webview-policies "Microsoft Edge WebView2 - ポリシー|Microsoft Docs"  

[WindowsSecurityThreatProtectionMicrosoftDefenderApplicationGuardWindows10]: /windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview "Microsoft Defender Application Guard (Windows 10) - Windows セキュリティ |Microsoft Docs"

[DotnetApiSystemComponentmodelCancelEventargs]: /dotnet/api/system.componentmodel.canceleventargs "CancelEventArgs クラス (System.ComponentModel) |Microsoft Docs"  
[DotnetApiSystemEventargs]: /dotnet/api/system.eventargs "EventArgs クラス (System) |Microsoft Docs"  
[DotnetStandardAssemblyStrongNamed]: /dotnet/standard/assembly/strong-named "強力な名前のアセンブリ|Microsoft Docs"  

[GithubMicrosoftedgeWebviewfeedbackIssue1]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/1 "MicrosoftEdge/WebViewFeedback 問題 1 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue12]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/12 "MicrosoftEdge/WebViewFeedback 問題 12 のフィードバック情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue13]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/13 "MicrosoftEdge/WebViewFeedback 問題 13 のフィードバック情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue14]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/14 "MicrosoftEdge/WebViewFeedback 問題 14 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue16]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/16 "MicrosoftEdge/WebViewFeedback 問題 16 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue17]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/17 "MicrosoftEdge/WebViewFeedback 問題 17 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue18]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/18 "MicrosoftEdge/WebViewFeedback 問題 18 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue19]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/19 "MicrosoftEdge/WebViewFeedback 問題 19 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue22]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/22 "MicrosoftEdge/WebViewFeedback 問題 22 のフィードバック情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue27]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/27 "MicrosoftEdge/WebViewFeedback 問題 27 のフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue28]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/28 "MicrosoftEdge/WebViewFeedback 問題 28 のフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue30]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/30 "MicrosoftEdge/WebViewFeedback 問題 30 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue32]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/32 "MicrosoftEdge/WebViewFeedback 問題 32 のフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue36]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/36 "MicrosoftEdge/WebViewFeedback 問題 36 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue57]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/57 "MicrosoftEdge/WebViewFeedback 問題 57 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue70]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/70 "MicrosoftEdge/WebViewFeedback 問題 70 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue74]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/74 "MicrosoftEdge/WebViewFeedback 問題 74 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue95]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/95 "MicrosoftEdge/WebViewFeedback 問題 95 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue108]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/108 "MicrosoftEdge/WebViewFeedback の問題 108 に関するフィードバックの情報"
[GithubMicrosoftedgeWebviewfeedbackIssue113]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/113 "MicrosoftEdge/WebViewFeedback 問題 113 のフィードバック情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue119]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/119 "MicrosoftEdge/WebViewFeedback 問題 119 に関するフィードバックの情報"
[GithubMicrosoftedgeWebviewfeedbackIssue131]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/131 "MicrosoftEdge/WebViewFeedback 問題 131 に関するフィードバックの情報"
[GithubMicrosoftedgeWebviewfeedbackIssue148]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/148 "MicrosoftEdge/WebViewFeedback 問題 148 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue168]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/168 "MicrosoftEdge/WebViewFeedback 問題 168 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue177]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/177 "MicrosoftEdge/WebViewFeedback 問題 177 のフィードバック の情報"
[GithubMicrosoftedgeWebviewfeedbackIssue179]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/179 "MicrosoftEdge/WebViewFeedback 問題 179 に関するフィードバックの情報"
[GithubMicrosoftedgeWebviewfeedbackIssue181]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/181 "MicrosoftEdge/WebViewFeedback の問題 181 に関するフィードバックの情報"
[GithubMicrosoftedgeWebviewfeedbackIssue183]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/183 "MicrosoftEdge/WebViewFeedback 問題 183 に関するフィードバックの情報"
[GithubMicrosoftedgeWebviewfeedbackIssue185]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/185 "MicrosoftEdge/WebViewFeedback 問題 185 のフィードバック の情報"
[GithubMicrosoftedgeWebviewfeedbackIssue204]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/204 "MicrosoftEdge/WebViewFeedback 問題 204 に関するフィードバックの情報"
[GithubMicrosoftedgeWebviewfeedbackIssue219]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/219 "MicrosoftEdge/WebViewFeedback 問題 219 に関するフィードバックの情報"
[GithubMicrosoftedgeWebviewfeedbackIssue228]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/228 "MicrosoftEdge/WebViewFeedback 問題 228 に関するフィードバックの情報"
[GithubMicrosoftedgeWebviewfeedbackIssue235]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/235 "MicrosoftEdge/WebViewFeedback 問題 235 のフィードバック の情報"
[GithubMicrosoftedgeWebviewfeedbackIssue250]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/250 "MicrosoftEdge/WebViewFeedback 問題 250 のフィードバック 情報"
[GithubMicrosoftedgeWebviewfeedbackIssue288]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/288 "MicrosoftEdge/WebViewFeedback 問題 288 のフィードバック 情報"
[GithubMicrosoftedgeWebviewfeedbackIssue293]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/293 "MicrosoftEdge/WebViewFeedback 問題 293 のフィードバック の情報"
[GithubMicrosoftedgeWebviewfeedbackIssue318]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/318 "MicrosoftEdge/WebViewFeedback 問題 318 のフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue335]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/335 "MicrosoftEdge/WebViewFeedback 問題 335 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue371]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/371 "MicrosoftEdge/WebViewFeedback の問題 371 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue382]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/382 "MicrosoftEdge/WebViewFeedback 問題 382 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue431]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/431 "MicrosoftEdge/WebViewFeedback 問題 431 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue432]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/432 "MicrosoftEdge/WebViewFeedback 問題 432 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue461]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/461 "MicrosoftEdge/WebViewFeedback 問題 461 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue525]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/525 "MicrosoftEdge/WebViewFeedback 問題 525 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue549]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/549 "MicrosoftEdge/WebViewFeedback 問題 549 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue560]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/560 "MicrosoftEdge/WebViewFeedback 問題 560 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue611]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/611 "MicrosoftEdge/WebViewFeedback 問題 611 のフィードバック 情報"  

[GithubMicrosoftedgeWebview2AnnouncementIssue2]:  https://github.com/MicrosoftEdge/WebView2Announcement/issues/2 "MicrosoftEdge/WebViewAnnouncement 問題 2 のアナウンス 情報"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  
[GithubMicrosoftedgeWebview2samplesPr17]: https://github.com/MicrosoftEdge/WebView2Samples/pull/17 "最新の WebView2 SDK 0.9.430 を使用するプロジェクトを移動する - MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesApisample]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2APISample "WebView2 API サンプル - MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftDevblogDotnetAnnouncingGeneralAvailabilityForMicrosoftEdgeWebview2ForNetFixedDistributionMethod]: https://devblogs.microsoft.com/dotnet/announcing-general-availability-for-microsoft-edge-webview2-for-net-and-fixed-distribution-method ".NET および固定配布方法に関する Microsoft Edge WebView2 の一般提供| .NET ブログ"  

[MicrosoftDeveloperMicrosoftEdgeWebView2]: https://developer.microsoft.com/microsoft-edge/webview2/ "Microsoft Edge WebView2 |Microsoft Edge 開発者"  

[NuGetGallery]:  https://www.nuget.org/packages/Microsoft.Web.WebView2 "NuGet ギャラリー |Microsoft.Web.WebView2"  
[NuGetGallery0.8.149]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.149 "NuGet ギャラリー |Microsoft.Web.WebView2 v0.8.149"  
[NuGetGallery0.8.190]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.190 "NuGet ギャラリー |Microsoft.Web.WebView2 v0.8.190"  
[NuGetGallery0.8.230]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.230 "NuGet ギャラリー |Microsoft.Web.WebView2 v0.8.230"  
[NuGetGallery0.8.270]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.270 "NuGet ギャラリー |Microsoft.Web.WebView2 v0.8.270"  
[NuGetGallery0.8.314]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.314 "NuGet ギャラリー |Microsoft.Web.WebView2 v0.8.314"  
[NuGetGallery0.8.355]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.355 "NuGet ギャラリー |Microsoft.Web.WebView2 v0.8.355"  
[NuGetGallery0.9.430]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.430 "NuGet ギャラリー |Microsoft.Web.WebView2 v0.9.430"  
[NuGetGallery0.9.488]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.488 "NuGet ギャラリー |Microsoft.Web.WebView2 v0.9.488"  
[NuGetGallery0.9.515-prerelease]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.515-prerelease "NuGet ギャラリー |Microsoft.Web.WebView2 v0.9.515 プレリリース"  
[NuGetGallery0.9.538]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.538 "NuGet ギャラリー |Microsoft.Web.WebView2 v0.9.538"  
[NuGetGallery0.9.579]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.579 "NuGet ギャラリー |Microsoft.Web.WebView2 v0.9.579"
[NuGetGallery0.9.622.11]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.622.11 "NuGet ギャラリー |Microsoft.Web.WebView2 v0.9.622.11"
[NuGetGallery1.0.622.22]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.622.22 "NuGet ギャラリー |Microsoft.Web.WebView2 v1.0.622.22"
[NuGetGallery1.0.664.34]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.664.34 "NuGet ギャラリー |Microsoft.Web.WebView2 v1.0.664.34"
[NuGetGallery1.0.664.37]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.664.37 "NuGet ギャラリー |Microsoft.Web.WebView2 v1.0.664.37"
[NuGetGallery0.9.628-prerelease]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.628-prerelease "NuGet ギャラリー |Microsoft.Web.WebView2 v0.9.628 プレリリース"  
[NuGetGallery1.0.674-prerelease]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.674-prerelease "NuGet ギャラリー |Microsoft.Web.WebView2 v1.0.674 プレリリース"  
[NuGetGallery1.0.721-prerelease]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.721-prerelease "NuGet ギャラリー |Microsoft.Web.WebView2 v1.0.721 プレリリース"  
[WindowsBlogsMsedgedevEdgeWebview2GeneralAvailability]: https://blogs.windows.com/msedgedev/edge-webview2-general-availability "Microsoft Edge WebView2 の一般提供の|Microsoft Edge ブログ"  

[WebResourceResponseReceivedAPI]: /microsoft-edge/webview2/reference/win32/icorewebview2_2?view=webview2-1.0.721-prerelease#add_webresourceresponsereceived&preserve-view=true "add_WebResourceResponseReceived - インターフェイス ICoreWebView2 |Microsoft Docs"
[NavigateWithWebResourceRequestAPI]: /microsoft-edge/webview2/reference/win32/icorewebview2environment2?view=webview2-1.0.721-prerelease#createwebresourcerequest&preserve-view=true "CreateWebResourceRequest - インターフェイス ICoreWebView2Environment |Microsoft Docs"
[CookiemanagementAPI]: /microsoft-edge/webview2/reference/win32/icorewebview2cookiemanager?view=webview2-1.0.721-prerelease&preserve-view=true "ICoreWebView2CookieManager |Microsoft Docs"
[DOMContentLoadedAPI]: /microsoft-edge/webview2/reference/win32/icorewebview2_2?view=webview2-1.0.721-prerelease#add_domcontentloaded&preserve-view=true "add_DOMContentLoaded - インターフェイスICoreWebView2_2 |Microsoft Docs"
[WebViewEnvironmentproperty]: /microsoft-edge/webview2/reference/win32/icorewebview2_2?view=webview2-1.0.721-prerelease#get_environment&preserve-view=true "ICoreWebView2CookieManager |Microsoft Docs"

[GithubMicrosoftedgeWebviewfeedbackIssue37]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/37 "MicrosoftEdge/WebViewFeedback 問題 37 のフィードバック の情報" 
[GithubMicrosoftedgeWebviewfeedbackIssue58]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/58 "MicrosoftEdge/WebViewFeedback 問題 58 のフィードバック 情報" 
[GithubMicrosoftedgeWebviewfeedbackIssue122]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/122 "MicrosoftEdge/WebViewFeedback 問題 122 のフィードバックの情報" 
[GithubMicrosoftedgeWebviewfeedbackIssue161]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/161 "MicrosoftEdge/WebViewFeedback 問題 161 に関するフィードバックの情報" 
[GithubMicrosoftedgeWebviewfeedbackIssue196]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/196 "MicrosoftEdge/WebViewFeedback 問題 196 のフィードバック の情報" 
[GithubMicrosoftedgeWebviewfeedbackIssue205]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/205 "MicrosoftEdge/WebViewFeedback 問題 205 のフィードバック の情報" 
[GithubMicrosoftedgeWebviewfeedbackIssue212]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/212 "MicrosoftEdge/WebViewFeedback 問題 212 のフィードバックの情報" 
[GithubMicrosoftedgeWebviewfeedbackIssue399]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/399 "MicrosoftEdge/WebViewFeedback 問題 399 のフィードバック の情報" 
[GithubMicrosoftedgeWebviewfeedbackIssue400]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/400 "MicrosoftEdge/WebViewFeedback 問題 400 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue409]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/409 "MicrosoftEdge/WebViewFeedback 問題 409 に関するフィードバックの情報" 
[GithubMicrosoftedgeWebviewfeedbackIssue605]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/605 "MicrosoftEdge/WebViewFeedback 問題 605 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue691]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/691 "MicrosoftEdge/WebViewFeedback 問題 691 に関するフィードバックの情報" 
[GithubMicrosoftedgeWebviewfeedbackIssue414]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/414 "MicrosoftEdge/WebViewFeedback 問題 414 のフィードバックの情報" 
[NuGetGallery1.0.705.50]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.705.50 "NuGet ギャラリー |Microsoft.Web.WebView2 v1.0.705.50"
[NuGetGallery1.0.781-prerelease]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.781-prerelease "NuGet ギャラリー |Microsoft.Web.WebView2 v1.0.781 プレリリース"  
[ReferenceWin32Icorewebview210781PreReleaseTrySuspendResume]: /microsoft-edge/webview2/reference/win32/icorewebview2_3?view=webview2-1.0.781-prerelease&preserve-view=true#trysuspend "TrySuspend - インターフェイス ICoreWebview2_3 |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalsettings10781PreReleaseGetUserAgent]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalsettings?view=webview2-1.0.781-prerelease#get_useragent "get_UserAgent - インターフェイス ICoreWebView2ExperimentalSettings |Microsoft Docs"  
[ReferenceWin32Icorewebview210781PreReleaseSetVirtualHostNameToFolderMapping]: /microsoft-edge/webview2/reference/win32/icorewebview2_3?view=webview2-1.0.781-prerelease&preserve-view=true#setvirtualhostnametofoldermapping "SetVirtualHostNameToFolderMapping - インターフェイス ICoreWebView2_3 |Microsoft Docs"   
[ReferenceWin32Icorewebview2controllerViewWebview210781PreReleaseDefaultBackgroundColor]: /microsoft-edge/webview2/reference/win32/icorewebview2controller2?view=webview2-1.0.781-prerelease&preserve-view=true#get_defaultbackgroundcolor "get_DefaultBackgroundColor - インターフェイス ICoreWebView2Controller2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2controllerViewWebview210781CompositionController]:  /microsoft-edge/webview2/reference/win32/icorewebview2compositioncontroller?view=webview2-1.0.781-prerelease&preserve-view=true "インターフェイス ICoreWebView2CompositionController |Microsoft Docs"  
[ReferenceWin32Icorewebview2webresourceresponseviewgetcontentcompletedhandlerInvoke10781]: /microsoft-edge/webview2/reference/win32/icorewebview2webresourceresponseviewgetcontentcompletedhandler?view=webview2-1.0.781-prerelease&preserve-view=true#invoke "Invoke - インターフェイス ICoreWebView2WebResourceResponseViewGetContentCompletedHandler |Microsoft Docs"  
