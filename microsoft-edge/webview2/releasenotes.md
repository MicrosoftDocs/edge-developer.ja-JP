---
description: Microsoft Edge WebView2 SDK のリリース ノート
title: Win32、WPF、WinForms 向け Microsoft Edge WebView2 のリリース ノート
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/16/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、ブラウザー コントロール、エッジ html
ms.openlocfilehash: 58f96dda9c05cfc10790e3523a494e42cf33ec12
ms.sourcegitcommit: 988c9add287abd203acf1d5d51ef7146e6f0b351
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2021
ms.locfileid: "11339921"
---
# WebView2 SDK のリリース ノート  

WebView2 チームは [、WebView2 SDK][NuGetGallery] を 6 週間の更新で更新します。  API に対する製品のアナウンス、追加、変更、および変更の詳細については、次のコンテンツを確認してください。  

> [!NOTE]
> NuGet パッケージの更新後にアプリを再コンパイルしてください。  プレリリース パッケージを使用して開発する場合は Canary チャネルを使用し、リリース済みパッケージを使用する場合は常にランタイムを使用する方法をお勧めします。  詳細については、[バージョン管理] [に移動します][Webview2ConceptsVersioningMatchingWebview2RuntimeVersions]。  
 
## 1.0.790 プレリリース  

リリース日: 2021 年 2 月 10 日  

[NuGet パッケージ][NuGetGallery1.0.790-prerelease] \|Microsoft Edge バージョン 86.0.616.0 以降  

### 全般的な情報  

> [!IMPORTANT]
> **Breaking Change**: WebView2 pre-release package 1.0.781 is deprecated.  パッケージ 1.0.781 で開発を中止します。  

> [!IMPORTANT]
> WebView2 プレリリース パッケージ 0.9.430 は廃止され、今後のリリースから削除される予定です。  WebView アプリでパッケージを使う場合は、新しいパッケージに更新することをお勧めします。  

##### 機能  

*   [WebView を中断して再開する TrySuspend][Webview2ReferenceWin32Icorewebview23ViewWebview210790PrereleaseTrysuspend]メソッドと Resume メソッドが追加されました。  
*   仮想ホスト [名をディレクトリ パスにマップする SetVirtualHostNameToFolderMapping][Webview2ReferenceWin32Icorewebview23ViewWebview210790PrereleaseSetvirtualhostnametofoldermapping] メソッドが追加されました。  \([\#37][GithubMicrosoftedgeWebviewfeedbackIssue37], [\#161][GithubMicrosoftedgeWebviewfeedbackIssue161], and [\#212][GithubMicrosoftedgeWebviewfeedbackIssue212]\).  
*   背景の色とアルファ チャネルを設定する [DefaultBackgroundColor][Webview2ReferenceWin32Icorewebview2controller2ViewWebview210790PrereleaseGetDefaultbackgroundcolor] プロパティを追加しました。  \([\#414][GithubMicrosoftedgeWebviewfeedbackIssue414]\)。  
*   User Agent を取得または設定する [UserAgent][Webview2ReferenceWin32Icorewebview2experimentalsettingsViewWebview210790PrereleaseGetUseragent] プロパティを追加しました。  \([\#122][GithubMicrosoftedgeWebviewfeedbackIssue122]\)。  
*   メソッドを `CreateCookieWithCookie` メソッドに置き換 `CopyCookie` えました。  
*   [ICoreWebView2CompositionController][Webview2ReferenceWin32Icorewebview2compositioncontrollerViewWebview210790Prerelease]インターフェイスを使用してビジュアル ホスティングのサポートを追加しました。このインターフェイスは、次の新しいメソッドを `CreateCoreWebView2CompositionController` 使用して作成されます `ICoreWebView2Environment3` 。  

    
##### バグ修正  

*   WebView2 で Microsoft Edge のショッピング機能を無効にしました。  
*   オンになっている場合は、PDF ビューアーでコンテキスト メニューを `AreDefaultContextMenusEnabled` オフにします `false` 。  \([\#605][GithubMicrosoftedgeWebviewfeedbackIssue605]\)。  
*   クエリを実行するときに返 `E_NOINTERFACE` されるバグを修正 `ICoreWebView2` しました `ICoreWebView2Experimental` 。  \([\#691][GithubMicrosoftedgeWebviewfeedbackIssue691]\)。  
*   URI の形式が正しく設定されているときにナビゲーションが許可されるバグ `CoreWebView2NavigationStartingEventArgs.Cancel` を修正しました `false` 。  \([\#400][GithubMicrosoftedgeWebviewfeedbackIssue400]\)。  
*   イベントハンドラーがイベントに `window.print()` 関連付けられているポップアップ ウィンドウでブロックされるバグを修正 `NewWindowRequested` しました。  \([\#409][GithubMicrosoftedgeWebviewfeedbackIssue409]\)。  
*   異なるモニター間でアプリを移動する場合の動的 DPI の問題を修正しました。  \([\#58][GithubMicrosoftedgeWebviewfeedbackIssue58]\)  
*   `HRESULT` [ICoreWebView2WebResourceResponseViewGetContentCompletedHandler::Invoke][Webview2ReferenceWin32Icorewebview2webresourceresponseviewgetcontentcompletedhandlerViewWebview210790PrereleaseInvoke]によって渡されるインスタンスが改善されました。  
*   [オートフィル管理] ボタンをオフにします。  \([\#585][GithubMicrosoftedgeWebviewfeedbackIssue585]\)。  
*   複数Visual Studioでホストされている場合の実行中に `WebView2.Dispose` クラッシュする問題を修正しました。  \([\#816][GithubMicrosoftedgeWebviewfeedbackIssue816]\ and [\#442][GithubMicrosoftedgeWebviewfeedbackIssue442]\).  
*   新しいツールボックスに WebView2 コントロールを表示Visual Studio修正しました。  \([\#210][GithubMicrosoftedgeWebviewfeedbackIssue210]\)。  
*   CPU 使用率の高い問題の削減。  \([\#878][GithubMicrosoftedgeWebviewfeedbackIssue878]\)。  
*   非推奨の 1.0.781 プレリリース パッケージの問題を修正しました。 [\#875][GithubMicrosoftedgeWebviewfeedbackIssue875] [\#878][GithubMicrosoftedgeWebviewfeedbackIssue878]\)。  
    
##### プロモーション  

*   次の試験的な API が Stable に昇格されました。  
    *   ビジュアル ホスティング API。  
    *   [SetVirtualHostNameToFolderMapping][Webview2ReferenceWin32Icorewebview23ViewWebview210790PrereleaseSetvirtualhostnametofoldermapping]  
    *   [TrySuspend と Resume][Webview2ReferenceWin32Icorewebview23ViewWebview210790PrereleaseTrysuspend]  
    *   [DefaultBackgroundColor][Webview2ReferenceWin32Icorewebview2controller2ViewWebview210790PrereleaseGetDefaultbackgroundcolor]  
    
#### .NET  

##### バグ修正  

*   WPF SDK を使用する WebView アプリがクラッシュするバグを修正しました。  クラッシュは、ウィンドウが F4 キーを使って閉じらたときに発生しました。  \([\#399][GithubMicrosoftedgeWebviewfeedbackIssue399]\)。  
*   WebView2 の初期化画面が灰色ではなく透明になります。  \([\#196][GithubMicrosoftedgeWebviewfeedbackIssue196]\)。  
    
## 1.0.705.50  

リリース日: 2021 年 1 月 25 日  

[NuGet パッケージ][NuGetGallery1.0.705.50] \|WebView2 ランタイム バージョン 86.0.616.0 以降  

##### プロモーション  

*   次の試験的な API が Stable に昇格されました。  
    *   [WebResourceResponseReceived API][Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseAddWebresourceresponsereceived]  
    *   [NavigateWithWebResourceRequest API][Webview2ReferenceWin32Icorewebview2environment2ViewWebview210721PrereleaseCreatewebresourcerequest]  
    *   [Cookie 管理 API][Webview2ReferenceWin32Icorewebview2cookiemanagerViewWebview210721Prerelease]  
    *   [DOMContentLoaded API][Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseAddDomcontentloaded]  
    *   [WebView Environment プロパティ][Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseGetEnvironment]  

## 1.0.721-プレリリース  

リリース日: 2020 年 12 月 8 日  

[NuGet パッケージ][NuGetGallery1.0.721-prerelease] \|Microsoft Edge バージョン 86.0.616.0 以降  

#### 全般的な情報  

> [!IMPORTANT]
> **Breaking Change**: WebView2 pre-release package 1.0.707 and package 0.9.628 are deprecated.  パッケージ 1.0.707 と package0.9.628 の開発を中止します。  

###### 機能  

*   [WebView2 グループ ポリシーを追加しました][DeployedgeMicrosoftEdgeWebviewPolicies]。  推奨される方法の詳細については [、WebView2 のグループ ポリシーに移動してください][Webview2ConceptsEnterpriseGroupPoliciesForWebview2]。  
*   > [!IMPORTANT]
    > **Breaking Change**: 古いレジストリの場所を廃止しました。  
    > 
    > ```text
    > {Root}\Software\Policies\Microsoft\EmbeddedBrowserWebView\LoaderOverride\{AppId}
    > ```  
    
*   WebView2 での [ドラッグ アンド ドロップの][Webview2ReferenceWin32Icorewebview2experimentalcompositioncontroller3ViewWebview210721Prerelease] サポートが追加されました。  
*   DPI サポートを処理する API が追加されました。  
    *   [WebView コンテンツと][Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetRasterizationscale]UI ポップアップの DPI スケールを変更する RasterizationScale プロパティ、および[関連付けられた RasterizationScaleChanged イベントが追加][Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseAddRasterizationscalechanged]されました。  
    *   [ShouldDetectMonitorScaleChanges][Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetShoulddetectmonitorscalechanges]プロパティが追加され、必要に応じてプロパティ `RasterizationScale` が自動的に更新されます。  
    *   [BoundsMode プロパティ][Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetBoundsmode]が追加され、境界がロジック ピクセルであり、WebView が WebView2 ピクセル表示に使用され、WebView は物理サイズを取得するために With を使用できます `RasterizationScale` `RasterizationScale` `Bounds` 。  
*   イベントを `NewWindowRequested` 処理および `Ctrl` + `click` 更新しました `Shift` + `click` 。  \([\#168][GithubMicrosoftedgeWebviewfeedbackIssue168] and [\#371][GithubMicrosoftedgeWebviewfeedbackIssue371]\).  
*   次の試験的な API が Stable に昇格されました。  
    *   [WebResourceResponseReceived API][Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseAddWebresourceresponsereceived]  
    *   [NavigateWithWebResourceRequest API][Webview2ReferenceWin32Icorewebview2environment2ViewWebview210721PrereleaseCreatewebresourcerequest]  
    *   [Cookie 管理 API][Webview2ReferenceWin32Icorewebview2cookiemanagerViewWebview210721Prerelease]  
    *   [DOMContentLoaded API][Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseAddDomcontentloaded]  
    *   [WebView Environment プロパティ][Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseGetEnvironment]  
        
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
    
## 1.0.674-プレリリース  

リリース日: 2020 年 10 月 19 日  

[NuGet パッケージ][NuGetGallery1.0.674-prerelease] \|WebView2 ランタイム バージョン 86.0.616.0 以降。  

#### 全般的な情報  

*   ナビゲーション中にポスト データまたは他の要求ヘッダーを提供する [NavigateWithWebResourceRequest][Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseNavigatewithwebresourcerequest] メソッドが追加されました。  
*   初期 HTML ドキュメントが読み込まれ、解析されると実行される [DOMContentLoaded][Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseAddDomcontentloaded] イベントが追加されました。  
*   WebView2 [に Environment][Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseGetEnvironment] プロパティを追加しました。  このプロパティは、WebView2 のインスタンスが作成された WebView2 環境を公開します。  
*   開発者が [WebView2][Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseGetCookiemanager] セッションを認証したり、WebView から Cookie を取得して他のツールを認証したりできる Cookie 管理 API が追加されました。  Webview チームは、言語またはフレームワーク固有の改善を計画しています。  詳細については、「API レビュー [: Cookie の管理」に移動します][GithubMicrosoftedgeWebview2AnnouncementIssue2]。  
*   [WebResourceResponseReceived][Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseAddWebresourceresponsereceived]イベントを更新し、不変[の WebResourceResponseView][Webview2ReferenceWin32Icorewebview2experimentalwebresourceresponseviewViewWebview210674Prerelease]と[WebResourceResponseReceivedEventArgs::P opulateResponseContent][Webview2ReferenceWin32Icorewebview2experimentalwebresourceresponsereceivedeventargsViewWebview209628PrereleasePopulateresponsecontent] to [WebResourceResponseView::GetContent][Webview2ReferenceWin32Icorewebview2experimentalwebresourceresponseviewViewWebview210674PrereleaseGetcontent]を追加しました。  
*   WebView2 [で Microsoft Defender Application Guard (WDAG)][WindowsSecurityThreatProtectionMicrosoftDefenderApplicationGuardWindows10] をオフにします。  
*   ビジュアル ホスティング [用の SystemCursorId][Webview2ReferenceWin32Icorewebview2experimentalcompositioncontroller2ViewWebview210674PrereleaseGetSystemcursorid] が追加されました。  
*   ビジュアル ホスティングの入力メソッドに修正されたバグが追加されました。  
*   WebView2 静的ライブラリを `version.lib` 使用する場合の要件が削除されました。  
    
#### .NET  

*   変数を [公開するために CoreWebView2][DotnetApiMicrosoftWebWebview2CoreCorewebview2] クラスを更新 `CoreWebView2Environment` しました。  
*   名前空間内のカスタム EventArgs クラスの実装を `Microsoft.Web.WebView2.Core` [System.EventArgs][DotnetApiSystemEventargs] または [System.ComponentModel.CancelEventArgs][DotnetApiSystemComponentmodelCancelEventargs]のサブクラスに変更しました。  \([\#250][GithubMicrosoftedgeWebviewfeedbackIssue250]\)  
*   WinForms の [CoreWebView2CreationProperties][DotnetApiMicrosoftWebWebview2Winforms] のサポートが追加されました。  \([\#204][GithubMicrosoftedgeWebviewfeedbackIssue204]\)。  
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
*   [固定バージョン モードは][Webview2ConceptsDistributionFixedVersionDistributionMode] 、開発者向けプレビューで利用できます。  
    
## 0.9.622.11  

リリース日: 2020 年 9 月 10 日  

[NuGet パッケージ][NuGetGallery0.9.622.11] \|WebView2 ランタイム バージョン 86.0.616.0 以降。  

#### 全般的な情報  

*   > [!IMPORTANT]
    > **アナウンス**: この SDK は、WebView2 Win32 C/C++ GA の Release Candidate です。  GA バージョンでは、同じ API インターフェイスと機能を使用する必要があります。  
    
*   切断 [されたブラウザー ポリシー][DeployedgeMicrosoftEdgePolicies]。  
*   [WebView2 環境オプションに AllowSingleSignOnUsingOSPrimaryAccount][Webview2ReferenceWin32Icorewebview2environmentoptionsViewWebview209622GetAllowsinglesignonusingosprimaryaccount]プロパティを追加し、WebView の条件付きアクセスを有効にしました。  
*   `ICoreWebView2NewWindowRequestedEventArgs` [WindowFeatures プロパティと][Webview2ReferenceWin32Icorewebview2newwindowrequestedeventargsViewWebview209622GetWindowfeatures]、関連付けられた[ICoreWebView2WindowFeatures][Webview2ReferenceWin32Icorewebview2windowfeaturesViewWebview209622]を含む更新を行いました。  \([\#293][GithubMicrosoftedgeWebviewfeedbackIssue293]\)。  
*   `System.Windows.Rect` `System.Drawing.Rectangle` `System.Windows.Rect` \([\#235][GithubMicrosoftedgeWebviewfeedbackIssue235]\) の代わりに使用#235しました。  
*   パラメーターを指定せずに要求を処理する NewWindowRequested `window.open()` イベントを更新しました。  \([\#293][GithubMicrosoftedgeWebviewfeedbackIssue293]\)。  
*   [指定された AdditionalBrowserArguments][Webview2ReferenceWin32Icorewebview2environmentoptionsViewWebview209622PutAdditionalbrowserarguments] は、環境変数やレジストリ値 `ICoreWebView2EnvironmentOptions` で上書きされるのではない。  詳細については、「[CreateCoreWebView2EnvironmentWithOptions][Webview2ReferenceWin32Webview2IdlViewWebview209622Createcorewebview2environmentwithoptions]」を参照してください。  
    
## 0.9.579  

リリース日: 2020 年 7 月 20 日  

[NuGet パッケージ][NuGetGallery0.9.579] \|Microsoft Edge バージョン 86.0.579.0。  

#### 全般的な情報  

*   > [!IMPORTANT]
    > **Announcement**: Evergreen WebView2 Runtime and installer is released for preview.  詳細については [、WebView2 の配布に移動します][Webview2ConceptsDistributionUnderstandRuntimeInstaller]。  
    
*   > [!IMPORTANT]
    > **アナウンス**: 次の WebView2 SDK バージョンは、次の SDK リリース以降サポートされなくなりました。  
    > 
    > *   [0.8.190](#08190)  
    > *   [0.8.230](#08230)  
    > *   [0.8.270](#08270)  
    > *   [0.8.314](#08314)  
    > *   [0.8.355](#08355)  
    > 
    > また、WebView2 SDK のバージョンは、次のバージョンでも非推奨nuget.org。 WebView2 では、WebView2 の最新バージョンを最新の情報に更新してください。  
    
*   WebView ワーカー スレッドの機能強化が追加されました。  \([\#318][GithubMicrosoftedgeWebviewfeedbackIssue318]\)。  
*   WebView でポップアップ ブロックをオフにします。  詳細については、イベントの [IsUserInitiated][Webview2ReferenceWin32Icorewebview2newwindowrequestedeventargsViewWebview209538GetIsuserinitiated] プロパティに移動 `NewWindowRequested` します。  
*   WebView ナビゲーション開始イベントが実行されます `about:blank` 。  現在では、すべてのナビゲーションに対してイベントが実行されますが、iframe に対する取り消しは `NavigationStarting` `about:blank` サポートされ `srcdoc` 、無視されません。  
*   `edge://`WebView で一部の URI スキームをブロックしました。  
*   WebView2 環境 [オプションに実験的な IsSingleSignOnUsingOSPrimaryAccountEnabled][Webview2ReferenceWin32Icorewebview2experimentalenvironmentoptionsViewWebview209538PrereleaseGetIssinglesignonusingosprimaryaccountenabled] プロパティを追加し、WebView の条件付きアクセスを有効にしました。  
*   WebView が WebResource 要求からの応答を受信して処理した後に実行される試験的な [WebResourceResponseReceived][Webview2ReferenceWin32Icorewebview2experimentalViewWebview209538PrereleaseAddWebresourceresponsereceived] イベントが追加されました。  認証ヘッダーがある場合は、応答オブジェクトに含まれます。  
    
#### .NET  

*   WPF フォーカス処理が改善されました。  \([\#185][GithubMicrosoftedgeWebviewfeedbackIssue185]\)。  
*   WPF `ZoomFactor` Webview2 コントローラーにプロパティを追加しました。  
    
## 0.9.538  

[NuGet パッケージ][NuGetGallery0.9.538] \|Microsoft Edge バージョン 85.0.538.0。  

#### 全般的な情報  

*   WebView2 SDK バージョン [0.8.149 のサポートを削除しました](#08149)。  WebView2 では、WebView2 の最新バージョンを最新の情報に更新してください。  
*   Microsoft Edge ブラウザーのプロファイル パスが変更された日時を考慮に入れるグループ ポリシーを更新しました \([#179][GithubMicrosoftedgeWebviewfeedbackIssue179]\)。  
    
#### Win32 C/C++  

*   [ICoreWebView2ExperimentalNewWindowRequestedEventArgs::get_WindowFeatures][Webview2ReferenceWin32Icorewebview2experimentalnewwindowrequestedeventargsViewWebview209538PrereleaseGetWindowfeatures]が追加されました。このイベントは、実行時に発生し `window.open()` [、ICoreWebView2ExperimentalWindowFeatures][Webview2ReferenceWin32Icorewebview2experimentalwindowfeaturesViewWebview209538Prerelease] \([#70][GithubMicrosoftedgeWebviewfeedbackIssue70]\) に関連付けます。  
*   > [!IMPORTANT]
    > **Breaking Change**: Deprecated [CreateCoreWebView2EnvironmentWithDetails][Webview2ReferenceWin32Webview2IdlViewWebview209488Createcorewebview2environmentwithdetails] and replaced with [CreateCoreWebView2EnvironmentWithOptions][Webview2ReferenceWin32Webview2IdlViewWebview209538Createcorewebview2environmentwithoptions].  
    
*   > [!IMPORTANT]
    > **Breaking Change**: WebView2 API が Windows API の名前付け規則に準拠するために、WebView チームは次の名前を更新しました。  
    > 
    > *   [AreRemoteObjectsAllowed][Webview2ReferenceWin32Icorewebview2settingsViewWebview209488GetAreremoteobjectsallowed] は [AreHostObjectsAllowed に変更されました][Webview2ReferenceWin32Icorewebview2settingsViewWebview209538GetArehostobjectsallowed]。  
    
*   [AddHostObjectToScript を更新しました][Webview2ReferenceWin32Icorewebview2ViewWebview209538ddhostobjecttoscript]。  元のホスト オブジェクト シリアライザー マーカーがプロキシ オブジェクトに設定されます。  次に、JavaScript コールバック \( #148 \) でパラメーターとして渡された場合、ホスト オブジェクトのシリアライザー マーカーがホスト[オブジェクトとしてシリアル化されます][GithubMicrosoftedgeWebviewfeedbackIssue148]。  
    
#### .NET (0.9.538 プレリリース)  

*   リリースされた WinForms と WPF WebView2API サンプルは、WebView2 SDK の包括的なガイドです。  詳細については、Samples [Repo に移動します][GithubMicrosoftedgeWebview2samplesMain]。  
*   視覚的なホスティングとウィンドウ機能の試験的な API [のサポートが追加されました][Webview2ConceptsVersioningExperimentalApis]。  
*   > [!IMPORTANT]
    > **Breaking Change**: The following deferrals now implement IDisposable:  [ScriptDialogOpening,][DotnetApiMicrosoftWebWebview2CoreCorewebview2Scriptdialogopening] [NewWindowRequested][DotnetApiMicrosoftWebWebview2CoreCorewebview2Newwindowrequested], [WebResourceRequested][DotnetApiMicrosoftWebWebview2CoreCorewebview2Webresourcerequested], and [PermissionRequested][DotnetApiMicrosoftWebWebview2CoreCorewebview2Permissionrequested].  
    
*   [GetAvailableBrowserVersionString][DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentGetavailablebrowserversionstring]と[CompareBrowserVersions][DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentComparebrowserversions]が[CoreWebView2Environment][DotnetApiMicrosoftWebWebview2CoreCorewebview2environment]静的として追加されました。  
    
## 0.9.515-プレリリース  

[NuGet パッケージ][NuGetGallery0.9.515-prerelease] \|Microsoft Edge バージョン 84.0.515.0。  

*   > [!IMPORTANT]
    > **お**知らせ : WebView2 では、プレリリース パッケージの .NET Framework 4.6.2 以降および .NET Core 3.0 以降で Windows フォームと WPF **が**サポートされます。  
    
*   WPF アプリの作成の詳細については [、「WPF Getting Started Guide」][Webview2GettingstartedWpf] および「WebView2 WPF Reference for [WPF-specific][DotnetApiMicrosoftWebWebview2Wpf] APIs」を参照してください。  
*   Windows フォーム アプリの構築の詳細については [、「Windows フォーム][Webview2GettingstartedWinforms] の概要ガイド」および「Windows フォーム固有 API 用 WebView2 [Windows][DotnetApiMicrosoftWebWebview2Winforms] フォーム リファレンス」に移動してください。  
*   CoreWebView2 API の詳細については、「.NET [リファレンス」に移動してください][DotnetApiMicrosoftWebWebview2Core]。  
*   > [!CAUTION]
    > **既知の問題**: WebView チームは、今後のリリースで解決されるプレリリースのいくつかの問題を認識しています。  
    > 
    > *   **DPI 対応**: WPF の WebView2 は、現在 DPI 対応ではありません。  高 DPI モニターで WebView2 を初期化する場合、ウィンドウのサイズが変更されるまで、最初に WebView がウィンドウの小数部として初期化されるという既知の問題があります。  
    > *   **WPF デザイナー**: WPF デザイナーは現在サポートされていません。  テキスト エディターで適切な XAML を直接変更して、アプリに WebView2 コントロールを追加します。  
    
## 0.9.488  

[NuGet パッケージ][NuGetGallery0.9.488] \|Microsoft Edge バージョン 84.0.488.0。  

*   > [!IMPORTANT]
    > **アナウンス**: 今後の Microsoft Edge バージョン 83 から、Evergreen WebView は Stable ブラウザー チャネルを対象としなくなりました。  代わりに、WebView チームが現在開発しているインストーラーを介してチェーン インストールできる [、Evergreen WebView2 ランタイム][Webview2ConceptsDistributionEvergreenDistributionMode]というブランド化された別のバイナリセットをターゲットにします。  詳細については [、App-Distribution に移動します][Webview2ConceptsDistribution]。  
    
*   > [!IMPORTANT]
    > **お**知らせ : 今後、WebView チームは 2 つのパッケージをリリースします。試験的な API を含むプレリリース パッケージ \(試用用\) と安定した API を含む安定したリリース パッケージ \(自分の信頼のために\)。  違いについては、「ブラウザーのバージョンと [WebView2][Webview2ConceptsVersioning]について」に移動してください。  
    
*   > [!IMPORTANT]
    > **変更の**ブレーク: WebView2 API が Windows API の名前付け規則に準拠するために、WebView チームは次のインターフェイスの名前を更新しました。  
    > 
    > *   `CORE_WEBVIEW2_*` プレフィックスは次の値です `COREWEBVIEW2_*` 。  
    > *   [GetCoreWebView2BrowserVersionInfo][Webview2ReferenceWin32Webview2IdlViewWebview209430Getcorewebview2browserversioninfo] は現在 [、GetAvailableCoreWebView2BrowserVersionString です][Webview2ReferenceWin32Webview2IdlViewWebview209488Getavailablecorewebview2browserversionstring]。  
    > *   [get_BrowserVersionInfo][Webview2ReferenceWin32Icorewebview2environmentViewWebview209430GetBrowserversioninfo]が表示[get_BrowserVersionString。][Webview2ReferenceWin32Icorewebview2environmentViewWebview209488GetBrowserversionstring]  
    > *   [AddRemoteObject][Webview2ReferenceWin32Icorewebview2ViewWebview209430Addremoteobject] は [AddHostObjectToScript です][Webview2ReferenceWin32Icorewebview2ViewWebview209488Addhostobjecttoscript]。  
    > *   [RemoveRemoteObject][Webview2ReferenceWin32Icorewebview2ViewWebview209430Removeremoteobject] は [RemoveHostObjectFromScript に変更しました][Webview2ReferenceWin32Icorewebview2ViewWebview209488Removehostobjectfromscript]。  
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
    > **Breaking Change**: Deprecated [CreateCoreWebView2EnvironmentWithDetails][Webview2ReferenceWin32Webview2IdlViewWebview209488Createcorewebview2environmentwithdetails] and replaced with [CreateCoreWebView2EnvironmentWithOptions][Webview2ReferenceWin32Webview2IdlViewWebview209488Createcorewebview2environmentwithoptions].  
    
*   [FrameNavigationCompleted イベントが追加][Webview2ReferenceWin32Icorewebview2ViewWebview209488AddFramenavigationcompleted]されました。  これで、iframe がナビゲーションを完了すると、イベントが実行され、ナビゲーションの成功とナビゲーション ID が返されます。  
*   [ICoreWebView2EnvironmentOptions][Webview2ReferenceWin32Icorewebview2environmentoptionsViewWebview209488]インターフェイスが追加されました。このインターフェイスは、アプリの対象となる WebView2 ランタイムのバージョンを判断するために使用できます。  
*   [IsBuiltInErrorPageEnabled 設定を追加][Webview2ReferenceWin32Icorewebview2settingsViewWebview209488GetIsbuiltinerrorpageenabled]しました。  ナビゲーションエラーとレンダリング プロセスの失敗に関して、組み込みのエラー Web ページをオンまたはオフに切り替えます。  
*   .NET 実装 \( #113 `IDispatch` \)[をサポートするためにリモート オブジェクト インジェクションを][GithubMicrosoftedgeWebviewfeedbackIssue113]更新しました。  
*   コンテキスト メニュー \( #108 \) からの要求を処理する [NewWindowRequested][Webview2ReferenceWin32Icorewebview2ViewWebview209488AddNewwindowrequested] [イベントを更新][GithubMicrosoftedgeWebviewfeedbackIssue108]しました。  
*   ビジュアル ホスティング API にアクセスできる最初の独立した WebView2 プレリリース パッケージをリリースしました。  WebView チームは、 [新しい試験的な API を含む APISample][GithubMicrosoftedgeWebview2samplesMain] を更新しました。  
    
    *   コンポジション ツリーに接続し、WebView の入力を提供するための [ICoreWebView2ExperimentalCompositionController][Webview2ReferenceWin32Icorewebview2experimentalcompositioncontrollerViewWebview209488Prerelease] インターフェイスが追加されました。  
    *   [ICoreWebView2ExperimentalPointerInfo][Webview2ReferenceWin32Icorewebview2experimentalpointerinfoViewWebview209488Prerelease]が追加されました。この情報には、 `POINTER_INFO`  このオブジェクトは、ポインター入力を WebView に挿入するために SendPointerInput に渡されます。  
    *   [ICoreWebView2ExperimentalCursorChangedEventHandler][Webview2ReferenceWin32Icorewebview2experimentalcursorchangedeventhandlerViewWebview209488Prerelease]が追加されました。このイベントは、WebView 上のマウス カーソルを変更する必要がある場合にアプリに指示します。  WebView のテキスト ボックスの上にマウスポインターを置く場合、カーソルは矢印からセレクターに変わります。  アプリ上のプロパティは、マウス カーソルが WebView に対して現在何をする必要かを `cursor` `CompositionController` 示します。  
    
## 0.9.430  

[NuGet パッケージ][NuGetGallery0.9.430] \|Microsoft Edge バージョン 82.0.430.0。  

WebView2 SDK は正式な Win32 C++ ベータ版で、フィードバックからのいくつかの機能要求が組み込まれています。  WebView チームは、変更が大きかったリリースの数を制限しようとする。  一般提供のアプローチとして、いくつかの重要な変更がベータリリースに組み込まれる。  

*   > [!IMPORTANT]
    > **Breaking Change**: 最終リリースが近づくにつれて、WebView2 API が Windows API の名前付け規則に準拠するために、プレフィックス *IWebView2WebView*   の名前が *ICoreWebView2*   に変更されました。  さらに、UI フレームワークから WebView2 SDK を活用するために `ICoreWebView2` [、ICoreWebView2 と ICoreWebView2Host][Webview2ReferenceWin32Icorewebview2ViewWebview209430] に分かれた WebView チームを [使用][Webview2ReferenceWin32Icorewebview2hostViewWebview209430]します。  `ICoreWebView2Host` ウィンドウとコンポジションに関連するサイズ変更、表示と非表示、フォーカス、その他の機能をサポートします。  ICoreWebView2 は、他のすべての WebView2 機能をサポートしています。  変更の組み込みについて詳しくは、WebView2 [][GithubMicrosoftedgeWebview2samplesPr17] [APISample][GithubMicrosoftedgeWebview2samplesMain]プロジェクトの WebView2 プル要求に移動してください。  
    
*   > [!IMPORTANT]
    > **Breaking Change**: Split [DocumentStateChanged][Webview2ReferenceWin32Iwebview2webviewViewWebview208355AddDocumentstatechanged] into three components:  [SourceChanged,][Webview2ReferenceWin32Icorewebview2ViewWebview209430AddSourcechanged] [ContentLoading][Webview2ReferenceWin32Icorewebview2ViewWebview209430AddContentloading], and [HistoryChanged][Webview2ReferenceWin32Icorewebview2ViewWebview209430AddHistorychanged].  ソース URL が変更された場合、 `SourceChanged` イベントが実行されます。  履歴の状態が変更された場合、 `HistoryChanged` イベントが実行されます。  この `ContentLoading` イベントは、新しいドキュメントが読み込まれるときに、最初のスクリプトの前に実行されます。  
    
*   ARM64 アーキテクチャのサポートが追加されました。  
*   タッチ スクリーン デバイスのソフト入力パネル \(SIP\) のサポートが追加されました。  
*   Windows Server 2016 のWindows Server 2008 R2、Windows Server 2012、Windows Server 2012 R2、および Windows Server 2016 のサポートが追加されました。  
*   ウィンドウ モードでウィンドウに従うステータス バーの [NotifyParentWindowPositionChanged][Webview2ReferenceWin32Icorewebview2hostViewWebview209430Notifyparentwindowpositionchanged] が追加されました。  また、アクセシビリティ機能を機能するために、ウィンドウレス モードで変更を実装します。  
*   リモート オブジェクトから Web ページにアクセスできるかどうかをグローバルに制御する [AreRemoteObjectsAllowed][Webview2ReferenceWin32Icorewebview2settingsViewWebview209430GetAreremoteobjectsallowed] 設定が追加されました。  既定ではオン `AreRemoteObjectsAllowed` になっているので [、AddRemoteObject][Webview2ReferenceWin32Icorewebview2ViewWebview209430Addremoteobject] によって追加されたリモート オブジェクトには Web ページからアクセスできます。  オフ `AreRemoteObjectsAllowed` にすると、Web ページからオブジェクトにアクセスできない。  変更は、次のナビゲーション イベントに適用されます。  
*   [IsZoomControlEnabled][Webview2ReferenceWin32Icorewebview2settingsViewWebview209430GetIszoomcontrolenabled]設定が追加され、ユーザーが \(または + マウス ホイール\) を使用して WebView のズームに影響を与えるのを `ctrl` + `+` `ctrl` + `-` `ctrl` 防ぐ機能が追加されました。  設定をオフにした場合でも [、put_ZoomFactorを][Webview2ReferenceWin32Icorewebview2hostViewWebview209430PutZoomfactor] 使ってズームを設定できます。  
*   ZoomFactor が現在の WebView にのみ適用されるに変更されました。  現在の WebView に対するズームの変更は、同じ原点のサイトを使用して移動した他の WebView には影響を与えいません。  詳細については、次 [のリンク][Webview2ReferenceWin32Icorewebview2hostViewWebview209430GetZoomfactor]get_ZoomFactor。  
*   WebView の ZoomView UI を非表示に \([#95][GithubMicrosoftedgeWebviewfeedbackIssue95]\)。  
*   [SetBoundsAndZoomFactor を追加しました][Webview2ReferenceWin32Icorewebview2hostViewWebview209430Setboundsandzoomfactor]。  これで、WebView のズーム倍率と範囲を同時に設定できます。  
*   [WindowCloseRequested イベントが追加][Webview2ReferenceWin32Icorewebview2ViewWebview209430AddWindowcloserequested]されました。  詳細については、\( [add_WindowCloseRequested][Webview2ReferenceWin32Icorewebview2ViewWebview209430AddWindowcloserequested] \)[に#119][GithubMicrosoftedgeWebviewfeedbackIssue119]してください。  
*   JavaScript ダイアログ イベントの `beforeunload` ダイアログの種類のサポートが追加され、列挙 [CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_BEFOREUNLOAD][Webview2ReferenceWin32Icorewebview2ViewWebview209430CoreWebview2ScriptDialogKind] が追加されました。  
*   [GetHeaders][Webview2ReferenceWin32Icorewebview2httprequestheadersViewWebview209430Getheaders]を HttpRequestHeaders、GetHeader を HttpResponseHeaders、および httpHeadersCollectionIterator [get_HasCurrentHeaderプロパティに][Webview2ReferenceWin32Icorewebview2httpheaderscollectioniteratorViewWebview209430GetHascurrentheader]追加しました。 [][Webview2ReferenceWin32Icorewebview2httpresponseheadersViewWebview209430Getheader]  
*   > [!IMPORTANT]
    > **Breaking Change**: 変更 `DevToolsProtocolEventReceived` された動作。  ここで、特定の DevTools Protocol イベントに対して[DevToolsProtocolEventReceiver][Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview209430]を作成し、次のコマンドを使用してそのようなイベントをサブスクライブ/[サブスクライブ解除][Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview209430AddDevtoolsprotocoleventreceived] / [add_DevToolsProtocolEventReceived remove_DevToolsProtocolEventReceived。][Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview209430RemoveDevtoolsprotocoleventreceived]  
    
*   > [!IMPORTANT]
    > **Breaking Change**: Get_WebMessageAsString `WebMessageReceivedEventArgs` [][Webview2ReferenceWin32Iwebview2webmessagereceivedeventargsViewWebview208355GetWebmessageasstring] [TryGetWebMessageAsString メソッドに変更][Webview2ReferenceWin32Icorewebview2webmessagereceivedeventargsViewWebview209430Trygetwebmessageasstring]されました。  
    
*   > [!IMPORTANT]
    > **Breaking Change**: Changed `AcceleratorKeyPressedEventArgs` [Handle][Webview2ReferenceWin32Iwebview2acceleratorkeypressedeventargsViewWebview208355Handle] メソッドを get_Handledプロパティ [に][Webview2ReferenceWin32Icorewebview2acceleratorkeypressedeventargsViewWebview209430GetHandled] 変更しました。  
    
## 0.8.355  

[NuGet パッケージ][NuGetGallery0.8.355] \|Microsoft Edge バージョン 80.0.355.0。  

*   リリースされた WebView2API サンプルは、WebView2 SDK の包括的なガイドです。  詳細については、API サンプルに [移動してください][GithubMicrosoftedgeWebview2samplesApisample]。  
*   英語 \( \ ([\][GithubMicrosoftedgeWebviewfeedbackIssue30]) 以外のすべての言語に IME #30しました。  
*   バグ 報告に応じてイベントの API `WebResourceRequested` サーフェスを更新しました。  同時にフィルターを指定し、作成時にイベントを指定する機能は廃止されました。  Web リソース要求イベントを作成するには、add_WebResourceRequested を使用してイベントを追加し[、AddWebResourceRequestedFilter][Webview2ReferenceWin32Iwebview2webview5ViewWebview208355Addwebresourcerequestedfilter]を使用してフィルターを追加します。 [][Webview2ReferenceWin32Iwebview2webview5ViewWebview208355AddWebresourcerequested]  [RemoveWebResourceRequestedFilter][Webview2ReferenceWin32Iwebview2webview5ViewWebview208355Removewebresourcerequestedfilter] はフィルター \([#36][GithubMicrosoftedgeWebviewfeedbackIssue36]\) \( #74 \)[を削除][GithubMicrosoftedgeWebviewfeedbackIssue74]します。  
*   > [!IMPORTANT]
    > **Breaking Change**: 全画面の動作を変更しました。  非推奨 [の IsFullScreenAllowed][Webview2ReferenceWin32Iwebview2settingsViewWebview208355GetIsfullscreenallowedDeprecated]。  既定では、WebView \(video\など) の要素が全画面に設定されている場合、WebView の境界が埋め込みます。  [ContainsFullScreenElementChanged][Webview2ReferenceWin32Iwebview2containsfullscreenelementchangedeventhandlerViewWebview208355]イベントと[][Webview2ReferenceWin32Iwebview2webview5ViewWebview208355GetContainsfullscreenelement]get_ContainsFullScreenElement を使って、要素が全画面表示モードに入る場合に、アプリで WebView のサイズを変更する方法を指定します。  
    
## 0.8.314  

[NuGet パッケージ][NuGetGallery0.8.314] \|Microsoft Edge バージョン 80.0.314.0。  

*   Windows 7、Windows 8、Windows 8.1 のサポートが追加されました。  
*   WebView2 Visual StudioサポートVisual Studioコードのデバッグ サポートを追加しました。  次に、IDE から直接 WebView2 でスクリプトをデバッグします。  詳細については [、WebView2 コントロールを使用して開発するときにデバッグする方法に移動します][Webview2HowtoDebug]。  
*   WebView2 の実行中のスクリプトが、アプリの Win32 コンポーネントから IDispatch オブジェクトにアクセスし、IDispatch オブジェクトのプロパティにアクセスするために追加 `Native Object Injection` されました。  詳細については [、AddRemoteObject][Webview2ReferenceWin32Iwebview2webview4ViewWebview208355Addremoteobject] \( #17 \)[に移動][GithubMicrosoftedgeWebviewfeedbackIssue17]します。  
*   イベントが `AcceleratorKeyPressed` 追加されました。  詳細については、\( [add_AcceleratorKeyPressed][Webview2ReferenceWin32Iwebview2webview4ViewWebview208355AddAcceleratorkeypressed] \)[に#57][GithubMicrosoftedgeWebviewfeedbackIssue57]してください。  
*   オフ `Context Menus` にしました。  詳細については、\( [put_AreDefaultContextMenusEnabled][Webview2ReferenceWin32Iwebview2settings2ViewWebview208355PutAredefaultcontextmenusenabled] \)[に][GithubMicrosoftedgeWebviewfeedbackIssue57]#57してください。  
*   更新されました `DPI Awareness` 。  現在、WebView の DPI 対応は、ホスト アプリの DPI 対応と同じです。  
    
    > [!NOTE]
    > 別のハイブリッド アプリが元の WebView とは異なる DPI 対応で起動された場合、同じ \( #1 \) の場合、新しい WebView `user data folder` [は起動][GithubMicrosoftedgeWebviewfeedbackIssue1]されません。  
    
*   WebView でホストされている Web コンテンツによって要求される通知アクセス許可要求を `Notification Change Behavior` WebView2 が自動的に拒否するように更新されました。  
    
## 0.8.270  

[NuGet パッケージ][NuGetGallery0.8.270] \|Microsoft Edge バージョン 78.0.270.0。  

*   ドキュメント タイトル `DocumentTitleChanged` の変更 \( \#27 \)[を示すイベントが追加][GithubMicrosoftedgeWebviewfeedbackIssue27]されました。  
*   API `GetWebView2BrowserVersionInfo` \([\#18][GithubMicrosoftedgeWebviewfeedbackIssue18]\) が追加されました。  
*   イベントが `NewWindowRequested` 追加されました。  
*   削除する `CreateWebView2EnvironmentWithDetails` 関数を更新しました `releaseChannelPreference` 。  関数の詳細については `CreateWebView2EnvironmentWithDetails` [、CreateWebView2EnvironmentWithDetails に移動します][Webview2ReferenceWin32Webview2IdlViewWebview208355Createwebview2environmentwithdetails]。  レジストリと環境変数のオーバーライドは引き続きサポートされています。  オーバーライドされない限り、既定のチャネル設定が使用されます。  
    チャネル検索中、WebView チームは、WebView2 SDK と互換性がない以前のチャネル バージョンをスキップします。  
    WebView チームは、より安定したチャネルを選択して、エンド ユーザーにとって最も一貫した動作を保証します。  最新の Canary ビルドでテストする場合は、アプリを起動する前に環境変数を設定する `WEBVIEW2_RELEASE_CHANNEL_PREFERENCE` `1` スクリプトを作成する必要があります。  
*   指定しない場合 `CreateWebView2EnvironmentWithDetails` に選択するロジックを使用して関数 `userDataFolder` を更新しました。  関数の詳細については `CreateWebView2EnvironmentWithDetails` [、CreateWebView2EnvironmentWithDetails に移動します][Webview2ReferenceWin32Webview2IdlViewWebview208355Createwebview2environmentwithdetails]。  以前に既定の場所を使用した場合、新しい SDK に切り替える場合、既定はリセット \(ホスト コード ディレクトリの新しい場所に設定\) され、状態もリセット `userDataFolder` `userDataFolder` されます。  指定されたディレクトリに書き込むアクセス許可がホスト プロセスに付与されていない場合、関数 `CreateWebView2EnvironmentWithDetails` は失敗する可能性があります。  古いディレクトリから新しいディレクトリに `user data folder` データをコピーできます。  
    
## 0.8.230  

[NuGet パッケージ][NuGetGallery0.8.230] \|Microsoft Edge バージョン 77.0.230.0。  

*   すべてのナビゲーション `Stop` と保留中のリソース フェッチ \([\#28][GithubMicrosoftedgeWebviewfeedbackIssue28]\) を停止する API が追加されました。  
*   `.tlb`NuGet パッケージ \( \#22 \)[にファイルを追加][GithubMicrosoftedgeWebviewfeedbackIssue22]しました。  
*   NuGet パッケージ \( \#32 \) のインストーラーリストに .NET[プロジェクトを追加][GithubMicrosoftedgeWebviewfeedbackIssue32]しました。  
    
## 0.8.190  

[NuGet パッケージ][NuGetGallery0.8.190] \|Microsoft Edge バージョン 77.0.190.0。  

*   ユーザーが `get_AreDevToolsEnabled` / `put_AreDevToolsEnabled` DevTools \( \#16 \) を開くことができるか制御[するために追加][GithubMicrosoftedgeWebviewfeedbackIssue16]されました。  
*   ステータス バー `get_IsStatusBarEnabled` / `put_IsStatusBarEnabled` が表示される \( \#19 \)[を制御するために追加][GithubMicrosoftedgeWebviewfeedbackIssue19]されます。  
*   ナビゲーション履歴 `get_CanGoBack` / `GoBack` / `get_CanGoForward` / `GoForward` を行き来する場合に追加されました。  
*   WebView で HTTP ヘッダーを表示および変更する HTTP ヘッダー型 `IWebView2HttpHeadersCollectionIterator` / `IWebView2HttpRequestHeaders` / `IWebView2HttpRequestHeaders` \( \) が追加されました。  
*   64 ビット コンピューター \( \#13 \) に 32 ビットの WebView[サポートが追加][GithubMicrosoftedgeWebviewfeedbackIssue13]されました。  
*   WEBView IDL を SDK \([\#14][GithubMicrosoftedgeWebviewfeedbackIssue14]\) に追加しました。  
*   インターフェイス ID オブジェクト `IID\_\*` \( \#12 \)[をサポートするライブラリが追加][GithubMicrosoftedgeWebviewfeedbackIssue12]されました。  
*   SDK の NuGet ファイルへの DLL ファイルのパス、リンク、および自動 `TARGET` コピーが追加されました。  
*   スクリプトで要求 `window.open()` を有効にしました。  
    
## 0.8.149  

[NuGet パッケージ][NuGetGallery0.8.149] \|Microsoft Edge バージョン 76.0.149.0。  

開発者向けプレビューの最初のリリース。  

<!-- Links -->  

[Webview2ConceptsDistribution]: ./concepts/distribution.md "WebView2 を使用したアプリケーションの配布 |Microsoft Docs"  
[Webview2ConceptsDistributionEvergreenDistributionMode]: ./concepts/distribution.md#evergreen-distribution-mode "常用配布モード - WebView2 を使用したアプリケーションの|Microsoft Docs"  
[Webview2ConceptsDistributionFixedVersionDistributionMode]: ./concepts/distribution.md#fixed-version-distribution-mode "固定バージョン配布モード - WebView2 を使用したアプリケーションの|Microsoft Docs"  
[Webview2ConceptsDistributionUnderstandRuntimeInstaller]: ./concepts/distribution.md#understanding-the-webview2-runtime "WebView2 ランタイムとインストーラーについて - WebView2 を使用したアプリケーションの配布|Microsoft Docs"  
[Webview2ConceptsEnterpriseGroupPoliciesForWebview2]: ./concepts/enterprise.md#group-policies-for-webview2 "WebView2 のグループ ポリシー - WebView2 アプリケーションの管理|Microsoft Docs"  
[Webview2ConceptsVersioning]: ./concepts/versioning.md "ブラウザーのバージョンと WebView2 について | Microsoft Docs"  
[Webview2ConceptsVersioningExperimentalApis]: ./concepts/versioning.md#experimental-apis "試験的な API - ブラウザーのバージョンと WebView2 |Microsoft Docs"  
[Webview2ConceptsVersioningMatchingWebview2RuntimeVersions]: ./concepts/versioning.md#matching-webview2-runtime-versions "一致する WebView2 ランタイム バージョン - WebView2 SDK のバージョンとバージョン|Microsoft Docs"  
[Webview2GettingstartedWinforms]: ./gettingstarted/winforms.md "Windows Forms アプリの WebView2 の使用を開始する|Microsoft Docs"  
[Webview2GettingstartedWpf]: ./gettingstarted/wpf.md "WPF アプリケーションでの WebView2 の|Microsoft Docs"  
[Webview2HowtoDebug]: ./howto/debug.md "WebView2 コントロールを使用して開発するときにデバッグする|Microsoft Docs"  

[Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseAddDomcontentloaded]: /microsoft-edge/webview2/reference/win32/icorewebview2_2?view=webview2-1.0.721-prerelease&preserve-view=true#add_domcontentloaded "add_DOMContentLoaded - インターフェイスICoreWebView2_2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseAddWebresourceresponsereceived]: /microsoft-edge/webview2/reference/win32/icorewebview2_2?view=webview2-1.0.721-prerelease&preserve-view=true#add_webresourceresponsereceived "add_WebResourceResponseReceived - インターフェイス ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseGetEnvironment]: /microsoft-edge/webview2/reference/win32/icorewebview2_2?view=webview2-1.0.721-prerelease&preserve-view=true#get_environment "ICoreWebView2CookieManager |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview23ViewWebview210790PrereleaseSetvirtualhostnametofoldermapping]: /microsoft-edge/webview2/reference/win32/icorewebview2_3?view=webview2-1.0.790-prerelease&preserve-view=true#setvirtualhostnametofoldermapping "SetVirtualHostNameToFolderMapping - インターフェイス ICoreWebView2_3 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview23ViewWebview210790PrereleaseTrysuspend]: /microsoft-edge/webview2/reference/win32/icorewebview2_3?view=webview2-1.0.790-prerelease&preserve-view=true#trysuspend "TrySuspend - インターフェイス ICoreWebview2_3 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2acceleratorkeypressedeventargsViewWebview209430GetHandled]: /microsoft-edge/webview2/reference/win32/icorewebview2acceleratorkeypressedeventargs?view=webview2-0.9.430&preserve-view=true#get_handled "get_Handled - インターフェイス ICoreWebView2AcceleratorKeyPressedEventArgs |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2compositioncontrollerViewWebview210790Prerelease]: /microsoft-edge/webview2/reference/win32/icorewebview2compositioncontroller?view=webview2-1.0.790-prerelease&preserve-view=true "インターフェイス ICoreWebView2CompositionController |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2controller2ViewWebview210790PrereleaseGetDefaultbackgroundcolor]: /microsoft-edge/webview2/reference/win32/icorewebview2controller2?view=webview2-1.0.790-prerelease&preserve-view=true#get_defaultbackgroundcolor "get_DefaultBackgroundColor - インターフェイス ICoreWebView2Controller2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2cookiemanagerViewWebview210721Prerelease]: /microsoft-edge/webview2/reference/win32/icorewebview2cookiemanager?view=webview2-1.0.721-prerelease&preserve-view=true "ICoreWebView2CookieManager |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview209430]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-0.9.430&preserve-view=true "interface ICoreWebView2DevToolsProtocolEventReceiver |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview209430AddDevtoolsprotocoleventreceived]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-0.9.430&preserve-view=true#add_devtoolsprotocoleventreceived "add_DevToolsProtocolEventReceived - インターフェイス ICoreWebView2DevToolsProtocolEventReceiver |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview209430RemoveDevtoolsprotocoleventreceived]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-0.9.430&preserve-view=true#remove_devtoolsprotocoleventreceived "remove_DevToolsProtocolEventReceived - インターフェイス ICoreWebView2DevToolsProtocolEventReceiver |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2environment2ViewWebview210721PrereleaseCreatewebresourcerequest]: /microsoft-edge/webview2/reference/win32/icorewebview2environment2?view=webview2-1.0.721-prerelease&preserve-view=true#createwebresourcerequest "CreateWebResourceRequest - インターフェイス ICoreWebView2Environment |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2environmentoptionsViewWebview209488]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions?view=webview2-0.9.488&preserve-view=true "interface ICoreWebView2EnvironmentOptions |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2environmentoptionsViewWebview209622GetAllowsinglesignonusingosprimaryaccount]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions?view=webview2-0.9.622&preserve-view=true#get_allowsinglesignonusingosprimaryaccount "get_AllowSingleSignOnUsingOSPrimaryAccount - インターフェイス ICoreWebView2EnvironmentOptions |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2environmentoptionsViewWebview209622PutAdditionalbrowserarguments]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions?view=webview2-0.9.622&preserve-view=true#put_additionalbrowserarguments "put_AdditionalBrowserArguments - インターフェイス ICoreWebView2EnvironmentOptions |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2environmentViewWebview209430GetBrowserversioninfo]: /microsoft-edge/webview2/reference/win32/icorewebview2environment?view=webview2-0.9.430&preserve-view=true#get_browserversioninfo "get_BrowserVersionInfo - インターフェイス ICoreWebView2Environment |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2environmentViewWebview209488GetBrowserversionstring]: /microsoft-edge/webview2/reference/win32/icorewebview2environment?view=webview2-0.9.488&preserve-view=true#get_browserversionstring "get_BrowserVersionString - インターフェイス ICoreWebView2Environment |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalcompositioncontroller2ViewWebview210674PrereleaseGetSystemcursorid]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller2?view=webview2-1.0.674-prerelease&preserve-view=true#get_systemcursorid "interface ICoreWebView2ExperimentalWebResourceResponseView |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalcompositioncontroller3ViewWebview210721Prerelease]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller3?view=webview2-1.0.721-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalCompositionController3 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalcompositioncontrollerViewWebview209488Prerelease]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller?view=webview2-0.9.488-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalCompositionController |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseAddRasterizationscalechanged]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.721-prerelease&preserve-view=true#add_rasterizationscalechanged "add_RasterizationScaleChanged - インターフェイス ICoreWebView2ExperimentalController |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetBoundsmode]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.721-prerelease&preserve-view=true#get_boundsmode "get_BoundsMode - インターフェイス ICoreWebView2ExperimentalController |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetRasterizationscale]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.721-prerelease&preserve-view=true#get_rasterizationscale "get_RasterizationScale - インターフェイス ICoreWebView2ExperimentalController |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetShoulddetectmonitorscalechanges]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.721-prerelease&preserve-view=true#get_shoulddetectmonitorscalechanges "get_ShouldDetectMonitorScaleChanges - インターフェイス ICoreWebView2ExperimentalController |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalcursorchangedeventhandlerViewWebview209488Prerelease]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcursorchangedeventhandler?view=webview2-0.9.488-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalCursorChangedEventHandler |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalenvironmentoptionsViewWebview209538PrereleaseGetIssinglesignonusingosprimaryaccountenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalenvironmentoptions?view=webview2-0.9.538-prerelease&preserve-view=true#get_issinglesignonusingosprimaryaccountenabled "get_IsSingleSignOnUsingOSPrimaryAccountEnabled - インターフェイス ICoreWebView2ExperimentalEnvironmentOptions |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalnewwindowrequestedeventargsViewWebview209538PrereleaseGetWindowfeatures]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalnewwindowrequestedeventargs?view=webview2-0.9.538-prerelease&preserve-view=true#get_windowfeatures "get_WindowFeatures - インターフェイス ICoreWebView2ExperimentalNewWindowRequestedEventArgs |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalpointerinfoViewWebview209488Prerelease]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalpointerinfo?view=webview2-0.9.488-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalPointerInfo |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalsettingsViewWebview210790PrereleaseGetUseragent]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalsettings?view=webview2-1.0.790-prerelease&preserve-view=true#get_useragent "get_UserAgent - インターフェイス ICoreWebView2ExperimentalSettings |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalViewWebview209538PrereleaseAddWebresourceresponsereceived]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-0.9.538-prerelease&preserve-view=true#add_webresourceresponsereceived "add_WebResourceResponseReceived - インターフェイス ICoreWebView2Experimental |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseAddDomcontentloaded]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#add_domcontentloaded "add_DOMContentLoaded - インターフェイス ICoreWebView2Experimental |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseAddWebresourceresponsereceived]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#add_webresourceresponsereceived "add_WebResourceResponseReceived - インターフェイス ICoreWebView2Experimental |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseGetCookiemanager]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#get_cookiemanager "get_CookieManager - インターフェイス ICoreWebView2Experimental |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseGetEnvironment]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#get_environment "get_Environment - インターフェイス ICoreWebView2Experimental |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseNavigatewithwebresourcerequest]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#navigatewithwebresourcerequest "NavigateWithWebResourceRequest - インターフェイス ICoreWebView2Experimental |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalwebresourceresponsereceivedeventargsViewWebview209628PrereleasePopulateresponsecontent]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwebresourceresponsereceivedeventargs?view=webview2-0.9.628-prerelease&preserve-view=true#populateresponsecontent "PopulateResponseContent - interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalwebresourceresponseviewViewWebview210674Prerelease]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwebresourceresponseview?view=webview2-1.0.674-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalWebResourceResponseView |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalwebresourceresponseviewViewWebview210674PrereleaseGetcontent]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwebresourceresponseview?view=webview2-1.0.674-prerelease&preserve-view=true#getcontent "GetContent - interface ICoreWebView2ExperimentalWebResourceResponseView |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalwindowfeaturesViewWebview209538Prerelease]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwindowfeatures?view=webview2-0.9.538-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalWindowFeatures |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2hostViewWebview209430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true "interface ICoreWebView2Host |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2hostViewWebview209430GetZoomfactor]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#get_zoomfactor "get_ZoomFactor - インターフェイス ICoreWebView2Host |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2hostViewWebview209430Notifyparentwindowpositionchanged]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#notifyparentwindowpositionchanged "NotifyParentWindowPositionChanged - インターフェイス ICoreWebView2Host |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2hostViewWebview209430PutZoomfactor]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#put_zoomfactor "put_ZoomFactor - インターフェイス ICoreWebView2Host |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2hostViewWebview209430Setboundsandzoomfactor]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#setboundsandzoomfactor "SetBoundsAndZoomFactor - インターフェイス ICoreWebView2Host |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2httpheaderscollectioniteratorViewWebview209430GetHascurrentheader]: /microsoft-edge/webview2/reference/win32/icorewebview2httpheaderscollectioniterator?view=webview2-0.9.430&preserve-view=true#get_hascurrentheader "get_HasCurrentHeader - インターフェイス ICoreWebView2HttpHeadersCollectionIterator |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2httprequestheadersViewWebview209430Getheaders]: /microsoft-edge/webview2/reference/win32/icorewebview2httprequestheaders?view=webview2-0.9.430&preserve-view=true#getheaders "GetHeaders - インターフェイス ICoreWebView2HttpRequestHeaders |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2httpresponseheadersViewWebview209430Getheader]: /microsoft-edge/webview2/reference/win32/icorewebview2httpresponseheaders?view=webview2-0.9.430&preserve-view=true#getheader "GetHeader - インターフェイス ICoreWebView2HttpResponseHeaders |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2newwindowrequestedeventargsViewWebview209538GetIsuserinitiated]: /microsoft-edge/webview2/reference/win32/icorewebview2newwindowrequestedeventargs?view=webview2-0.9.538&preserve-view=true#get_isuserinitiated "get_IsUserInitiated インターフェイス ICoreWebView2NewWindowRequestedEventArgs |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2newwindowrequestedeventargsViewWebview209622GetWindowfeatures]: /microsoft-edge/webview2/reference/win32/icorewebview2newwindowrequestedeventargs?view=webview2-0.9.622&preserve-view=true#get_windowfeatures "get_WindowFeatures - インターフェイス ICoreWebView2NewWindowRequestedEventArgs |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2settingsViewWebview209430GetAreremoteobjectsallowed]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.430&preserve-view=true#get_areremoteobjectsallowed "get_AreRemoteObjectsAllowed - インターフェイス ICoreWebView2Settings |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2settingsViewWebview209430GetIszoomcontrolenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.430&preserve-view=true#get_iszoomcontrolenabled "get_IsZoomControlEnabled - インターフェイス ICoreWebView2Settings |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2settingsViewWebview209488GetAreremoteobjectsallowed]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.488&preserve-view=true#get_areremoteobjectsallowed "get_AreRemoteObjectsAllowed - インターフェイス ICoreWebView2Settings |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2settingsViewWebview209488GetIsbuiltinerrorpageenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.488&preserve-view=true#get_isbuiltinerrorpageenabled " |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2settingsViewWebview209538GetArehostobjectsallowed]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.538&preserve-view=true#get_arehostobjectsallowed "get_AreHostObjectsAllowed - インターフェイス ICoreWebView2Settings |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true "interface ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209430AddContentloading]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_contentloading "add_ContentLoading - インターフェイス ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209430AddHistorychanged]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_historychanged "add_HistoryChanged - インターフェイス ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209430Addremoteobject]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#addremoteobject "AddRemoteObject - インターフェイス ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209430AddSourcechanged]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_sourcechanged "add_SourceChanged - インターフェイス ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209430AddWindowcloserequested]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_windowcloserequested "add_WindowCloseRequested - インターフェイス ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209430CoreWebview2ScriptDialogKind]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#core_webview2_script_dialog_kind "CORE_WEBVIEW2_SCRIPT_DIALOG_KIND - インターフェイス ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209430Removeremoteobject]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#removeremoteobject "RemoveRemoteObject - インターフェイス ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209488AddFramenavigationcompleted]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#add_framenavigationcompleted "add_FrameNavigationCompleted - インターフェイス ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209488Addhostobjecttoscript]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#addhostobjecttoscript "AddHostObjectToScript - インターフェイス ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209488AddNewwindowrequested]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#add_newwindowrequested "add_NewWindowRequested - インターフェイス ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209488Removehostobjectfromscript]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#removehostobjectfromscript "RemoveHostObjectFromScript - インターフェイス ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209538ddhostobjecttoscript]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.538&preserve-view=true#addhostobjecttoscript "AddHostObjectToScript - インターフェイス ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2webmessagereceivedeventargsViewWebview209430Trygetwebmessageasstring]: /microsoft-edge/webview2/reference/win32/icorewebview2webmessagereceivedeventargs?view=webview2-0.9.430&preserve-view=true#trygetwebmessageasstring "TryGetWebMessageAsString - インターフェイス ICoreWebView2WebMessageReceivedEventArgs |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2webresourceresponseviewgetcontentcompletedhandlerViewWebview210790PrereleaseInvoke]: /microsoft-edge/webview2/reference/win32/icorewebview2webresourceresponseviewgetcontentcompletedhandler?view=webview2-1.0.790-prerelease&preserve-view=true#invoke "Invoke - interface ICoreWebView2WebResourceResponseViewGetContentCompletedHandler |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2windowfeaturesViewWebview209622]: /microsoft-edge/webview2/reference/win32/icorewebview2windowfeatures?view=webview2-0.9.622&preserve-view=true "interface ICoreWebView2WindowFeatures |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2acceleratorkeypressedeventargsViewWebview208355Handle]: /microsoft-edge/webview2/reference/win32/iwebview2acceleratorkeypressedeventargs?view=webview2-0.8.355&preserve-view=true#handle "Handle - インターフェイス IWebView2AcceleratorKeyPressedEventArgs |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2containsfullscreenelementchangedeventhandlerViewWebview208355]: /microsoft-edge/webview2/reference/win32/iwebview2containsfullscreenelementchangedeventhandler?view=webview2-0.8.355&preserve-view=true "interface IWebView2ContainsFullScreenElementChangedEventHandler |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2settings2ViewWebview208355PutAredefaultcontextmenusenabled]: /microsoft-edge/webview2/reference/win32/iwebview2settings2?view=webview2-0.8.355&preserve-view=true#put_aredefaultcontextmenusenabled "put_AreDefaultContextMenusEnabled - インターフェイス IWebView2Settings2 |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2settingsViewWebview208355GetIsfullscreenallowedDeprecated]: /microsoft-edge/webview2/reference/win32/iwebview2settings?view=webview2-0.8.355&preserve-view=true#get_isfullscreenallowed_deprecated "get_IsFullscreenAllowed_deprecated - インターフェイス IWebView2Settings |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2webmessagereceivedeventargsViewWebview208355GetWebmessageasstring]: /microsoft-edge/webview2/reference/win32/iwebview2webmessagereceivedeventargs?view=webview2-0.8.355&preserve-view=true#get_webmessageasstring "get_WebMessageAsString - インターフェイス IWebView2WebMessageReceivedEventArgs |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2webview4ViewWebview208355AddAcceleratorkeypressed]: /microsoft-edge/webview2/reference/win32/iwebview2webview4?view=webview2-0.8.355&preserve-view=true#add_acceleratorkeypressed "add_AcceleratorKeyPressed - インターフェイス IWebView2WebView4 |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2webview4ViewWebview208355Addremoteobject]: /microsoft-edge/webview2/reference/win32/iwebview2webview4?view=webview2-0.8.355&preserve-view=true#addremoteobject "AddRemoteObject - インターフェイス IWebView2WebView4 |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2webview5ViewWebview208355AddWebresourcerequested]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#add_webresourcerequested "add_WebResourceRequested - インターフェイス IWebView2WebView5 |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2webview5ViewWebview208355Addwebresourcerequestedfilter]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#addwebresourcerequestedfilter "AddWebResourceRequestedFilter - インターフェイス IWebView2WebView5 |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2webview5ViewWebview208355GetContainsfullscreenelement]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#get_containsfullscreenelement "get_ContainsFullScreenElement - インターフェイス IWebView2WebView5 |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2webview5ViewWebview208355Removewebresourcerequestedfilter]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#removewebresourcerequestedfilter "RemoveWebResourceRequestedFilter - インターフェイス IWebView2WebView5 |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2webviewViewWebview208355AddDocumentstatechanged]: /microsoft-edge/webview2/reference/win32/iwebview2webview?view=webview2-0.8.355&preserve-view=true#add_documentstatechanged "add_DocumentStateChanged - インターフェイス IWebView2WebView |Microsoft Docs" 
[Webview2ReferenceWin32Webview2IdlViewWebview208355Createwebview2environmentwithdetails]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.8.355&preserve-view=true#createwebview2environmentwithdetails "CreateWebView2EnvironmentWithDetails - Globals |Microsoft Docs" 
[Webview2ReferenceWin32Webview2IdlViewWebview209430Getcorewebview2browserversioninfo]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.430&preserve-view=true#getcorewebview2browserversioninfo "GetCoreWebView2BrowserVersionInfo - Globals |Microsoft Docs" 
[Webview2ReferenceWin32Webview2IdlViewWebview209488Createcorewebview2environmentwithdetails]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.488&preserve-view=true#createcorewebview2environmentwithdetails "CreateCoreWebView2EnvironmentWithDetails - Globals |Microsoft Docs" 
[Webview2ReferenceWin32Webview2IdlViewWebview209488Createcorewebview2environmentwithoptions]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.488&preserve-view=true#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions - Globals | Microsoft Docs" 
[Webview2ReferenceWin32Webview2IdlViewWebview209488Getavailablecorewebview2browserversionstring]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.488&preserve-view=true#getavailablecorewebview2browserversionstring "GetAvailableCoreWebView2BrowserVersionString - Globals |Microsoft Docs" 
[Webview2ReferenceWin32Webview2IdlViewWebview209538Createcorewebview2environmentwithoptions]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.538&preserve-view=true#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions - Globals | Microsoft Docs" 
[Webview2ReferenceWin32Webview2IdlViewWebview209622Createcorewebview2environmentwithoptions]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.622&preserve-view=true#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions - Globals |Microsoft Edge" 

[DeployedgeMicrosoftEdgePolicies]: /deployedge/microsoft-edge-policies "Microsoft Edge - ポリシー|Microsoft Docs"  
[DeployedgeMicrosoftEdgeWebviewPolicies]: /deployedge/microsoft-edge-webview-policies "Microsoft Edge WebView2 - ポリシー|Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2Core]: /dotnet/api/microsoft.web.webview2.core "Microsoft.Web.WebView2.Core 名前空間 |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2]: /dotnet/api/microsoft.web.webview2.core.corewebview2 "CoreWebView2 クラス (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2environment]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment "CoreWebView2Environment クラス (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentComparebrowserversions]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.comparebrowserversions "CoreWebView2Environment.CompareBrowserVersions(String, String) メソッド (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentGetavailablebrowserversionstring]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.getavailablebrowserversionstring "CoreWebView2Environment.GetAvailableBrowserVersionString(String) メソッド (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2httprequestheaders]: /dotnet/api/microsoft.web.webview2.core.corewebview2httprequestheaders "CoreWebView2HttpRequestHeaders クラス (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2httpresponseheaders]: /dotnet/api/microsoft.web.webview2.core.corewebview2httpresponseheaders "CoreWebView2HttpResponseHeaders クラス (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Newwindowrequested]: /dotnet/api/microsoft.web.webview2.core.corewebview2.newwindowrequested "CoreWebView2.NewWindowRequested イベント (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Permissionrequested]: /dotnet/api/microsoft.web.webview2.core.corewebview2.permissionrequested "CoreWebView2.PermissionRequested イベント (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Scriptdialogopening]: /dotnet/api/microsoft.web.webview2.core.corewebview2.scriptdialogopening "CoreWebView2.ScriptDialogOpening イベント (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Webresourcerequested]: /dotnet/api/microsoft.web.webview2.core.corewebview2.webresourcerequested "CoreWebView2.WebResourceRequested イベント (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2Corewebview2initializationcompletedeventargs]: /dotnet/api/microsoft.web.webview2.core.corewebview2initializationcompletedeventargs "CoreWebView2InitializationCompletedEventArgs クラス |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreWebview2runtimenotfoundexception]: /dotnet/api/microsoft.web.webview2.core.webview2runtimenotfoundexception "CoreWebView2.WebView2RuntimeNotFound (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2Winforms]: /dotnet/api/microsoft.web.webview2.winforms "Microsoft.Web.WebView2.WinForms 名前空間 |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsCorewebview2creationproperties]: /dotnet/api/microsoft.web.webview2.winforms.corewebview2creationproperties "CoreWebView2CreationProperties クラス (Microsoft.Web.WebView2.Winforms) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2Source]: /dotnet/api/microsoft.web.webview2.winforms.webview2.source "Webview2.Source クラス (Microsoft.Web.WebView2.Winforms) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2Wpf]: /dotnet/api/microsoft.web.webview2.wpf "Microsoft.Web.WebView2.Wpf 名前空間 | Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2Acceleratorkeypressed]: /dotnet/api/microsoft.web.webview2.wpf.webview2.acceleratorkeypressed "microsoft.web.webview2.wpf.webview2.acceleratorkeypressed |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2Buildwindowcore]: /dotnet/api/microsoft.web.webview2.wpf.webview2.buildwindowcore "WebView2.BuildWindowCore(HandleRef) メソッド (Microsoft.Web.WebView2.Wpf) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2Destroywindowcore]: /dotnet/api/microsoft.web.webview2.wpf.webview2.destroywindowcore "WebView2.DestroyWindowCore(HandleRef) メソッド (Microsoft.Web.WebView2.Wpf) |Microsoft Docs"  
[DotnetApiSystemComponentmodelCancelEventargs]: /dotnet/api/system.componentmodel.canceleventargs "CancelEventArgs クラス (System.ComponentModel) |Microsoft Docs"  
[DotnetApiSystemEventargs]: /dotnet/api/system.eventargs "EventArgs クラス (System) |Microsoft Docs"  

[DotnetStandardAssemblyStrongNamed]: /dotnet/standard/assembly/strong-named "強力な名前のアセンブリ|Microsoft Docs"  

[WindowsSecurityThreatProtectionMicrosoftDefenderApplicationGuardWindows10]: /windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview "Microsoft Defender Application Guard (Windows 10) - Windows セキュリティ |Microsoft Docs"  

[GithubMicrosoftedgeWebview2AnnouncementIssue2]: https://github.com/MicrosoftEdge/WebView2Announcement/issues/2 "MicrosoftEdge/WebViewAnnouncement 問題 2 のアナウンス 情報"  

[GithubMicrosoftedgeWebview2samplesApisample]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2APISample "WebView2 API サンプル - MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  
[GithubMicrosoftedgeWebview2samplesPr17]: https://github.com/MicrosoftEdge/WebView2Samples/pull/17 "最新の WebView2 SDK 0.9.430 を使用するプロジェクトを移動する - MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftedgeWebviewfeedbackIssue1]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1 "MicrosoftEdge/WebViewFeedback 問題 1 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue12]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/12 "MicrosoftEdge/WebViewFeedback 問題 12 のフィードバック情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue13]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/13 "MicrosoftEdge/WebViewFeedback 問題 13 のフィードバック情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue14]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/14 "MicrosoftEdge/WebViewFeedback 問題 14 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue16]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/16 "MicrosoftEdge/WebViewFeedback 問題 16 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue17]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/17 "MicrosoftEdge/WebViewFeedback 問題 17 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue18]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/18 "MicrosoftEdge/WebViewFeedback 問題 18 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue19]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/19 "MicrosoftEdge/WebViewFeedback 問題 19 のフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue22]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/22 "MicrosoftEdge/WebViewFeedback 問題 22 のフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue27]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/27 "MicrosoftEdge/WebViewFeedback 問題 27 のフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue28]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/28 "MicrosoftEdge/WebViewFeedback 問題 28 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue30]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/30 "MicrosoftEdge/WebViewFeedback 問題 30 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue32]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/32 "MicrosoftEdge/WebViewFeedback 問題 32 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue36]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/36 "MicrosoftEdge/WebViewFeedback 問題 36 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue37]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/37 "MicrosoftEdge/WebViewFeedback 問題 37 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue57]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/57 "MicrosoftEdge/WebViewFeedback 問題 57 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue58]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/58 "MicrosoftEdge/WebViewFeedback 問題 58 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue70]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/70 "MicrosoftEdge/WebViewFeedback 問題 70 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue74]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/74 "MicrosoftEdge/WebViewFeedback 問題 74 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue95]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/95 "MicrosoftEdge/WebViewFeedback 問題 95 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue108]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/108 "MicrosoftEdge/WebViewFeedback の問題 108 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue113]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/113 "MicrosoftEdge/WebViewFeedback 問題 113 のフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue119]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/119 "MicrosoftEdge/WebViewFeedback 問題 119 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue122]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/122 "MicrosoftEdge/WebViewFeedback 問題 122 のフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue131]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/131 "MicrosoftEdge/WebViewFeedback 問題 131 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue148]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/148 "MicrosoftEdge/WebViewFeedback 問題 148 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue161]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/161 "MicrosoftEdge/WebViewFeedback 問題 161 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue168]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/168 "MicrosoftEdge/WebViewFeedback 問題 168 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue177]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/177 "MicrosoftEdge/WebViewFeedback 問題 177 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue179]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/179 "MicrosoftEdge/WebViewFeedback 問題 179 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue181]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/181 "MicrosoftEdge/WebViewFeedback 問題 181 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue183]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/183 "MicrosoftEdge/WebViewFeedback 問題 183 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue185]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/185 "MicrosoftEdge/WebViewFeedback 問題 185 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue196]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/196 "MicrosoftEdge/WebViewFeedback 問題 196 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue204]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/204 "MicrosoftEdge/WebViewFeedback 問題 204 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue205]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/205 "MicrosoftEdge/WebViewFeedback 問題 205 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue210]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/210 "MicrosoftEdge/WebViewFeedback 問題 210 のフィードバック情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue212]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/212 "MicrosoftEdge/WebViewFeedback 問題 212 のフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue219]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/219 "MicrosoftEdge/WebViewFeedback 問題 219 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue228]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/228 "MicrosoftEdge/WebViewFeedback の問題 228 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue235]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/235 "MicrosoftEdge/WebViewFeedback 問題 235 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue250]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/250 "MicrosoftEdge/WebViewFeedback 問題 250 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue275]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/275 "MicrosoftEdge/WebViewFeedback 問題 275 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue288]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/288 "MicrosoftEdge/WebViewFeedback 問題 288 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue293]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/293 "MicrosoftEdge/WebViewFeedback 問題 293 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue318]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/318 "MicrosoftEdge/WebViewFeedback 問題 318 のフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue335]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/335 "MicrosoftEdge/WebViewFeedback の問題 335 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue371]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/371 "MicrosoftEdge/WebViewFeedback の問題 371 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue382]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/382 "MicrosoftEdge/WebViewFeedback 問題 382 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue399]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/399 "MicrosoftEdge/WebViewFeedback の問題 399 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue400]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/400 "MicrosoftEdge/WebViewFeedback 問題 400 のフィードバック 情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue409]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/409 "MicrosoftEdge/WebViewFeedback の問題 409 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue414]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/414 "MicrosoftEdge/WebViewFeedback 問題 414 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue431]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/431 "MicrosoftEdge/WebViewFeedback 問題 431 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue432]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/432 "MicrosoftEdge/WebViewFeedback 問題 432 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue442]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/442 "MicrosoftEdge/WebViewFeedback 問題 442 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue461]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/461 "MicrosoftEdge/WebViewFeedback 問題 461 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue525]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/525 "MicrosoftEdge/WebViewFeedback 問題 525 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue549]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/549 "MicrosoftEdge/WebViewFeedback 問題 549 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue560]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/560 "MicrosoftEdge/WebViewFeedback 問題 560 のフィードバック情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue585]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/585 "MicrosoftEdge/WebViewFeedback の問題 585 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue605]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/605 "MicrosoftEdge/WebViewFeedback 問題 605 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue611]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/611 "MicrosoftEdge/WebViewFeedback 問題 611 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue691]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/691 "MicrosoftEdge/WebViewFeedback 問題 691 に関するフィードバックの情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue816]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/816 "MicrosoftEdge/WebViewFeedback 問題 816 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue875]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/875 "MicrosoftEdge/WebViewFeedback 問題 875 のフィードバック の情報"  
[GithubMicrosoftedgeWebviewfeedbackIssue878]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/878 "MicrosoftEdge/WebViewFeedback 問題 878 のフィードバック の情報"  

[MicrosoftDevblogDotnetAnnouncingGeneralAvailabilityForMicrosoftEdgeWebview2ForNetFixedDistributionMethod]: https://devblogs.microsoft.com/dotnet/announcing-general-availability-for-microsoft-edge-webview2-for-net-and-fixed-distribution-method ".NET および固定配布方法に関する Microsoft Edge WebView2 の一般提供| .NET ブログ"  

[MicrosoftDeveloperMicrosoftEdgeWebView2]: https://developer.microsoft.com/microsoft-edge/webview2/ "Microsoft Edge WebView2 |Microsoft Edge 開発者"  

[NuGetGallery]: https://www.nuget.org/packages/Microsoft.Web.WebView2 "NuGet ギャラリー |Microsoft.Web.WebView2"  
[NuGetGallery0.8.149]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.149 "NuGet ギャラリー |Microsoft.Web.WebView2 v0.8.149"  
[NuGetGallery0.8.190]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.190 "NuGet ギャラリー |Microsoft.Web.WebView2 v0.8.190"  
[NuGetGallery0.8.230]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.230 "NuGet ギャラリー |Microsoft.Web.WebView2 v0.8.230"  
[NuGetGallery0.8.270]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.270 "NuGet ギャラリー |Microsoft.Web.WebView2 v0.8.270"  
[NuGetGallery0.8.314]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.314 "NuGet ギャラリー |Microsoft.Web.WebView2 v0.8.314"  
[NuGetGallery0.8.355]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.355 "NuGet ギャラリー |Microsoft.Web.WebView2 v0.8.355"  
[NuGetGallery0.9.430]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.430 "NuGet ギャラリー |Microsoft.Web.WebView2 v0.9.430"  
[NuGetGallery0.9.488]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.488 "NuGet ギャラリー |Microsoft.Web.WebView2 v0.9.488"  
[NuGetGallery0.9.515-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.515-prerelease "NuGet ギャラリー |Microsoft.Web.WebView2 v0.9.515 プレリリース"  
[NuGetGallery0.9.538]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.538 "NuGet ギャラリー |Microsoft.Web.WebView2 v0.9.538"  
[NuGetGallery0.9.579]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.579 "NuGet ギャラリー |Microsoft.Web.WebView2 v0.9.579"  
[NuGetGallery0.9.622.11]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.622.11 "NuGet ギャラリー |Microsoft.Web.WebView2 v0.9.622.11"  
[NuGetGallery0.9.628-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.628-prerelease "NuGet ギャラリー |Microsoft.Web.WebView2 v0.9.628 プレリリース"  
[NuGetGallery1.0.622.22]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.622.22 "NuGet ギャラリー |Microsoft.Web.WebView2 v1.0.622.22"  
[NuGetGallery1.0.664.34]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.664.34 "NuGet ギャラリー |Microsoft.Web.WebView2 v1.0.664.34"  
[NuGetGallery1.0.664.37]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.664.37 "NuGet ギャラリー |Microsoft.Web.WebView2 v1.0.664.37"  
[NuGetGallery1.0.674-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.674-prerelease "NuGet ギャラリー |Microsoft.Web.WebView2 v1.0.674 プレリリース"  
[NuGetGallery1.0.705.50]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.705.50 "NuGet ギャラリー |Microsoft.Web.WebView2 v1.0.705.50"  
[NuGetGallery1.0.721-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.721-prerelease "NuGet ギャラリー |Microsoft.Web.WebView2 v1.0.721 プレリリース"  
[NuGetGallery1.0.790-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.790-prerelease "NuGet ギャラリー |Microsoft.Web.WebView2 v1.0.790 プレリリース"  

[WindowsBlogsMsedgedevEdgeWebview2GeneralAvailability]: https://blogs.windows.com/msedgedev/edge-webview2-general-availability "Microsoft Edge WebView2 の一般提供の|Microsoft Edge ブログ"  
