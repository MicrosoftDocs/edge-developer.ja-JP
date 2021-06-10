---
description: WebView2 SDK Microsoft Edgeリリース ノート
title: Win32、WPF、および WinForms Microsoft Edge WebView2 のリリース ノート
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、Webview2、Webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、ブラウザー コントロール、エッジ html
ms.openlocfilehash: 0ba9e2b26e5ff5046b9d00d365b0052d42e5a9b1
ms.sourcegitcommit: afeeeea9fccc3c4c096d7d44c401f4fe87ea2cd7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "11599415"
---
# <a name="release-notes-for-webview2-sdk"></a>WebView2 SDK のリリース ノート  

WebView2 チームは、6 週間のケイデンスで [WebView2 SDK][NuGetGallery] を更新します。  製品のお知らせ、追加、変更、API の変更点に関する最新の情報については、次のコンテンツを確認してください。  

> [!NOTE]
> アプリ パッケージを更新した後でアプリを再コンパイルNuGetします。  WebView チームでは、プレリリース パッケージを使用して開発するときに Canary チャネルを使用し、リリース パッケージを使用する場合は Evergreen WebView2 ランタイムを使用してください。  詳細については、「一致する [WebView2 ランタイム バージョン」に移動します][Webview2ConceptsVersioningMatchingWebview2RuntimeVersions]。  

> [!NOTE]
> WebView2 のバグ修正プログラムは、ランタイムまたは SDK に固有です。  

## <a name="10902-prerelease"></a>1.0.902-prerelease

リリース日: 2021 年 6 月 1 日  

[NuGet \|][NuGetGallery1.0.902-prerelease]読Microsoft Edge最小バージョン: 86.0.616.0 以降 \|完全な API 互換性: 92.0.902.0 以降  

### <a name="general"></a>全般  

#### <a name="experimental-features"></a>実験的な機能  

*   [IsSwipeNavigationEnabled][Webview2ReferenceWin32Icorewebview2experimentalsettings5ViewWebview210902PrereleaseGetIsswipenavigationenabled]プロパティを追加し、エンド ユーザーがタッチ入力が有効なデバイスでスワイプ ジェスチャを使用して WebView2 内を移動する機能を有効または無効にします。
*   [BrowserProcessExited イベントを追加][Webview2ReferenceWin32Icorewebview2experimentalenvironment4ViewWebview210902PrereleaseAddBrowserprocessexited]しました。
*   API add_ClientCertificateRequested [追加しました][Webview2ReferenceWin32Icorewebview2experimental3ViewWebview210902PrereleaseAddClientcertificaterequested]。 必要に応じてクライアント証明書ダイアログ プロンプトを表示し、既定のクライアント証明書ダイアログ プロンプトを置き換える必要なメタデータへのアクセスを有効にできます。
*   AddHostObjectToScriptWithOrigins の iframe 要素のサポートが追加されました。
*   WebView2 の起動パフォーマンスとディスクのフットプリントが向上しました。

#### <a name="bug-fixes"></a>バグ修正  

*   マウスの左クリックでコンテキスト メニューが閉じないバグを修正します。 この変更はランタイム固有です。
*   同じユーザー データ フォルダーを共有するアプリの exe ファイルのバージョン情報が一貫性のない場合に WebView2 の作成が失敗するバグを修正しました。
*   AreBrowserAcceleratorKeysEnabled で、Refresh、Home、Back などの特別なブラウザー キーを無効にできないバグを修正しました。 この変更はランタイム固有です。
*   バックグラウンドで作成すると WebView2 ウィンドウが空白である WebView2 .NET コントロールのバグを修正しました。 \([\#1077][GithubMicrosoftedgeWebviewfeedbackIssue1077]\)。 
*   'enter' または 'esc' を押してファイルピッカー ダイアログを閉じ、WebView コントロールを使用して WPF アプリケーションがクラッシュしなくなりました。 \([\#1099][GithubMicrosoftedgeWebviewfeedbackIssue1099]\)。 
*   WebResourceRequested イベント ハンドラーが接続されている場合に [AllowSingleSignOnUsingOSPrimaryAccount][Webview2ReferenceWin32Icorewebview2environmentoptionsGetAllowsinglesignonusingosprimaryaccount] が WebView2 で正しく動作しないバグを修正しました。 この変更はランタイム固有です。 \([\#1183][GithubMicrosoftedgeWebviewfeedbackIssue1183]\)。  
*   ファイルをダウンロードすると、WebView2 DefaultBackgroundColor の透明度が壊れなくなりました。 この変更はランタイム固有です。 \([\#1108][GithubMicrosoftedgeWebviewfeedbackIssue1108]\)。 
*   Microsoft のブランド化を含む画面共有メディアピッカー メッセージが削除されました。 \([\#940][GithubMicrosoftedgeWebviewfeedbackIssue940]\)。 
*   親フォームを非表示にしても WebView2 コントロール \([\#828][GithubMicrosoftedgeWebviewfeedbackIssue828] および [\#1079 \)][GithubMicrosoftedgeWebviewfeedbackIssue1079]を非表示にしない WebView2 WinForm コントロールのバグを修正しました。
*   WebView2 の WPF WS_CLIPCHILDRENに静的なスタイルを追加しました。 \([\#1013][GithubMicrosoftedgeWebviewfeedbackIssue1013]\)。 
*   リンクを右クリックすると WebView2 ホスト アプリがクラッシュするバグを修正しました。 この変更はランタイム固有です。
*   新しい Edge WebView2 ランタイム バージョンに移行するときにホスト アプリ プロセスがクラッシュする可能性がある信頼性のバグを修正しました。
*   **DEPRECATION**: 7 用の正式に非推奨の DefaultBackgroundColor API Windowsしました。


#### <a name="promotions"></a>プロモーション

*   [ダウンロード API][Webview2ReferenceWin32Icorewebview24ViewWebview210902PrereleaseAddDownloadstarting] が安定版に昇格しました。
*   [ピンチズーム API][Webview2ReferenceWin32Icorewebview2setting5ViewWebview210902PrereleaseGetIspinchzoomenabled] が安定版に昇格しました。
*   [AddFrameCreated][Webview2ReferenceWin32Icorewebview24ViewWebview210902PrereleaseAddFramecreated] が stable に昇格しました。
*   [自動入力 API][Webview2ReferenceWin32Icorewebview2setting4ViewWebview210902PrereleaseGetIsgeneralautofillenabled] が安定した状態に昇格しました。
    > [!NOTE]
    > ローカルに保存されている一般的なオートフィルとパスワードの自動保存情報を削除する現在の API はありません。  ユーザー データ フォルダー全体を削除するデータを削除するコントロールを指定してください。 



### <a name="net"></a>.NET  
    
#### <a name="bug-fixes"></a>バグ修正  

*   親ウィンドウが破棄された後、WebView2 ウィンドウの表示が正しく更新されない WebView2 WinForm コントロールのバグを修正しました。 \([\#1282][GithubMicrosoftedgeWebviewfeedbackIssue1282] および [\#828][GithubMicrosoftedgeWebviewfeedbackIssue828]\)。
*   WPF OneWay バインド モードの Source プロパティ バインドが正しく動作しないという WebView2 WPF コントロールのバグを修正しました。 \([\#619][GithubMicrosoftedgeWebviewfeedbackIssue619] および [\#608][GithubMicrosoftedgeWebviewfeedbackIssue608]\)。

## <a name="1086435"></a>1.0.864.35

リリース日: 2021 年 5 月 31 日  

[NuGet \|][NuGetGallery1.0.864.35]読み込む最小ランタイム バージョン: 86.0.616.0 以降 \|完全な API 互換性: 91.0.864.35 以降  

### <a name="general"></a>全般  

#### <a name="bug-fixes"></a>バグ修正  

*   新しい Edge WebView2 ランタイム バージョンに移行するときにホスト アプリ プロセスがクラッシュする可能性がある信頼性のバグを修正しました。
*   一部の状況でメモリの削除を妨げるバグを修正しました。 この変更はランタイム固有です。
*   プロジェクトが WebView2.h ファイルを見つけられなかった 818 SDK リリース パッケージのエラーを修正しました。 \([\#1209][GithubMicrosoftedgeWebviewfeedbackIssue1209]\)。 
*   バイナリボディを含む一部の要求で WebResourceRequested イベントが削除されるバグを修正しました。
*   NewWindowRequested のドキュメントを改善します。 \([\#448][GithubMicrosoftedgeWebviewfeedbackIssue448]\)。 

#### <a name="promotions"></a>プロモーション
*   [UserAgent API が][Webview2ReferenceWin32Icorewebview2setting2ViewWebview21086435GetUseragent] 安定しました。
*   [AreBrowserkeysenabled は][Webview2ReferenceWin32Icorewebview2setting2ViewWebview21086435GetArebrowseracceleratorkeysenabled] 安定しています。

### <a name="net"></a>.NET  

#### <a name="bug-fixes"></a>バグ修正  
*   CoreWebView2WebResourceRequest ヘッダー コレクションを反復するときに最初のヘッダーが見つからないという WebView2 .NET コントロールのバグを修正しました。 \([\#1123][GithubMicrosoftedgeWebviewfeedbackIssue1123]\)。 

## <a name="10865-prerelease"></a>1.0.865-prerelease  

リリース日: 2021 年 4 月 26 日  

[NuGet \|][NuGetGallery1.0.865-prerelease]読Microsoft Edge最小バージョン: 86.0.616.0 以降 \|完全な API 互換性: 91.0.865.0 以降  

### <a name="general"></a>全般  

#### <a name="experimental-features"></a>実験的な機能  

*   [IsPinchZoomEnabled 設定を追加][Webview2ReferenceWin32Icorewebview2experimentalsettings4ViewWebview210865PrereleaseIspinchzoomenabled]しました。 これにより、設定でページスケールズームコントロールをオンまたはオフにできます。  
*   カスタム add_DownloadStarting API [を追加][Webview2ReferenceWin32Icorewebview2experimental2ViewWebview210865PrereleaseAddDownloadstarting] しました。  これにより、ダウンロードをブロックし、別のパスに保存し、必要なメタデータにアクセスしてカスタム ダウンロード UI を作成できます。  
*   `iframe` [AddHostObjectToScriptWithOrigins から要素のサポートが追加されました][Webview2ReferenceWin32Icorewebview2experimentalframeViewWebview210865PrereleaseAddhostobjecttoscriptwithorigins]。  
*   API を使用してブラウザーのファンクション キー [を][GithubMicrosoftedgeWebview2samplesWebview2wpfbrowser] オフにする WPF サンプル アプリのサンプル コードを追加しました。  
*   WebView2 ランタイムを簡単に更新する [UpdateRuntime][Webview2ReferenceWin32Icorewebview2experimentalenvironment3ViewWebview210865PrereleaseUpdateruntime] API を追加しました。  
    
#### <a name="bug-fixes"></a>バグ修正  

*   WebView2 のバイナリ `Chromium DevTools Protocol` データを含 `POST` むメッセージのハンドラーを修正しました。  
*   へのリンク `OpenSaveAsAwareness` が含まれているため、ダウンロード UI をオフにしました `edge://settings` 。  \([\#1120][GithubMicrosoftedgeWebviewfeedbackIssue1120]\)。  
*   画面共有ダイアログからブランド化を削除しました。  \([\#940][GithubMicrosoftedgeWebviewfeedbackIssue940]\)。  
*   [SetWindowDisplayAffinity][WindowsWin32ApiWinuserSetWindowDisplayAffinity]関数が WebView2 アプリで画面キャプチャを停止すると WebView2 が壊れたバグを修正しました。  \([\#841][GithubMicrosoftedgeWebviewfeedbackIssue841]\)。
*   ペン入力が WebView2 に送信された場合にマウス入力が機能しなくなったコンポジション ホスティングのバグを修正しました。  
*   ペン入力後にマウス入力が壊れたバグを修正しました。  この変更はランタイム固有です。  
    
### <a name="net"></a>.NET  

#### <a name="experimental-features"></a>実験的な機能  

*   WEBView2 デザイナー ツールを WPF ツールボックスに追加しました。  \([\#210][GithubMicrosoftedgeWebviewfeedbackIssue210]\)。  
*   .NET デザイナー モードで WebView2 UI 要素を追加しました。  
    
#### <a name="bug-fixes"></a>バグ修正  

*   より詳細な .NET 例外でそれぞれをラップすることで、COM 例外の説明が改善されました。  \([\#338][GithubMicrosoftedgeWebviewfeedbackIssue338]\)。  この変更はランタイム固有です。  
*   フォーカスをシフトする場合に発生するバグを修正し、WebView2 コントロールが Microsoft Visual Studio ツールでクラッシュ `tab` Office。  \([\#589\#933][GithubMicrosoftedgeWebviewfeedbackIssue589] [][GithubMicrosoftedgeWebviewfeedbackIssue933]\)。  この変更はランタイム固有です。  
*   .NET framework ローダーのダウン レベルが強化され、堅牢性が向上しました。  \([\#946][GithubMicrosoftedgeWebviewfeedbackIssue946]\)。
*   最初のナビゲーションが完了する前に更新しようとしてクラッシュするバグを修正しました。  \([\#1011][GithubMicrosoftedgeWebviewfeedbackIssue1011]\)。
*   初期化が修正され、ナビゲーションが実行されます `CoreWebView2InitializationCompleted` 。  \([\#1050][GithubMicrosoftedgeWebviewfeedbackIssue1050]\)。
*   .NET ブラウザー プロセスのクラッシュ エラー処理が改善されました。  クラッシュせずにイベントを処理した後で、 `ProcessFailed` コントロールを再作成できます。  \([\#996][GithubMicrosoftedgeWebviewfeedbackIssue996]\)。  
    
## <a name="1081841"></a>1.0.818.41  

リリース日: 2021 年 4 月 21 日  

[NuGet \|][NuGetGallery1.0.818.41]読み込む最小ランタイム バージョン: 86.0.616.0 以降 \|完全な API 互換性: 90.0.818.41 以降  

### <a name="general"></a>全般  

#### <a name="features"></a>機能  

*   イベントを拡張 `ProcessFailed` しました。  これで、レンダラー以外の子プロセスとフレーム レンダラーが発生します。  
*   に対 `iframe` する要素のサポートが追加されました `AddScriptToExecuteOnDocumentCreated` 。  
*   WebView2 コードが、形式が正しく設定されていないバージョン情報を持つアプリケーション ファイルに対する復元 `.exe` 性が向上しました。  \([\#850][GithubMicrosoftedgeWebviewfeedbackIssue850]\)。  
*   `--winhttp-proxy-resolver`WebView ブラウザー プロセスのコマンド ラインから削除され、WebView2 の他のプロキシ コマンド ライン オプションが有効になります。  
    
## <a name="10824-prerelease"></a>1.0.824-prerelease  

リリース日: 2021 年 3 月 8 日  

[NuGet \|][NuGetGallery1.0.824-prerelease]読Microsoft Edge最小バージョン: 86.0.616.0 以降 \|完全な API 互換性: 91.0.824.0 以降  

### <a name="general"></a>全般  

#### <a name="features"></a>機能  

*   イベントを拡張 `ProcessFailed` しました。  これで、レンダラー以外の子プロセスとフレーム レンダラーが発生します。  
*   実験的な [AreBrowserAcceleratorKeysEnabled 設定を追加][Webview2ReferenceWin32Icorewebview2experimentalsettingsViewWebview210824GetArebrowseracceleratorkeysenabled] しました。  ナビゲーション、印刷、保存、その他のブラウザー固有の機能に関連するキーボード ショートカットにブラウザーが応答しない場合があります。  
*   に対 `iframe` する要素のサポートが追加されました `AddScriptToExecuteOnDocumentCreated` 。  
    
#### <a name="promotion"></a>プロモーション  

*   [UserAgent][Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseAddWebresourceresponsereceived] API が Stable に昇格しました。  
*   Rasterization Scale API \([RasterizationScale][Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetRasterizationscale] プロパティ  [、RasterizationScaleChanged][Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseAddRasterizationscalechanged] イベント [、BoundsMode][Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetBoundsmode]プロパティ [、ShouldDetectMonitorScaleChanges][Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetShoulddetectmonitorscalechanges] プロパティ\) が Stable に昇格しました。  
    
#### <a name="bug-fixes"></a>バグ修正  

*   MFC や ATL などのサポートされている C++ および .NET プロジェクトの種類が展開されました。  \([\#506][GithubMicrosoftedgeWebviewfeedbackIssue506] [、\#669][GithubMicrosoftedgeWebviewfeedbackIssue669] [、\#851][GithubMicrosoftedgeWebviewfeedbackIssue851]\)。  
*   Evergreen WebView2 ランタイムが受信ファイアウォールエントリをリークするバグを修正しました。  
*   イベント中の応答の設定を `WebResourceRequested` 修正しました。  \([\#568][GithubMicrosoftedgeWebviewfeedbackIssue568]\)。  
*   ブラウザー プロセスが終了する原因 `edge://` となるナビゲーションのバグを修正しました。  \([\#604][GithubMicrosoftedgeWebviewfeedbackIssue604]\)。  
*   Visual Hosting モードで WebView2 の境界を画面のサイズに制限するバグを修正しました。  
    
## <a name="1077444"></a>1.0.774.44  

リリース日: 2021 年 3 月 8 日  

[NuGet \|][NuGetGallery1.0.774.44]読み込む最小ランタイム バージョン: 86.0.616.0 以降 \|完全な API 互換性: 89.0.774.44 以降  

### <a name="general"></a>全般  

#### <a name="features"></a>機能  

*   WebView2 でMicrosoft Edgeブラウザー サービスを無効にしました。  
*   Visual Hosting API が一般提供されています。  
    
#### <a name="promotions"></a>プロモーション  

*   次の実験的な API が Stable に昇格されました。  
    *   [DPI サポート][Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseAddWebresourceresponsereceived] 関連 API  
    *   ビジュアル ホスティング API  
    *   [SetVirtualHostNameToFolderMapping][Webview2ReferenceWin32Icorewebview23ViewWebview210790PrereleaseSetvirtualhostnametofoldermapping]  
    *   [TrySuspend と Resume][Webview2ReferenceWin32Icorewebview23ViewWebview210790PrereleaseTrysuspend]  
    *   [DefaultBackgroundColor][Webview2ReferenceWin32Icorewebview2controller2ViewWebview210790PrereleaseGetDefaultbackgroundcolor]  
        
#### <a name="bug-fixes"></a>バグ修正  

*   Visual Hosting モードで WebView2 の境界を画面のサイズに制限するバグを修正しました。  
    
## <a name="10790-prerelease"></a>1.0.790-prerelease  

リリース日: 2021 年 2 月 10 日  

[NuGet \|][NuGetGallery1.0.790-prerelease]Microsoft Edgeバージョン 86.0.616.0 以降  

### <a name="general"></a>全般  

> [!IMPORTANT]
> **Breaking Change**: WebView2 プレリリース パッケージ 1.0.781 は非推奨です。  パッケージ 1.0.781 での開発を中止します。  

> [!IMPORTANT]
> WebView2 プレリリース パッケージ 0.9.430 は廃止され、次のリリースでは削除されます。  WebView アプリでパッケージを使用する場合、WebView チームは新しいパッケージに移動するようにお勧めします。  

#### <a name="features"></a>機能  

*   [WebViews を中断および再開する TrySuspend][Webview2ReferenceWin32Icorewebview23ViewWebview210790PrereleaseTrysuspend]メソッドと Resume メソッドを追加しました。  
*   仮想ホスト [名をディレクトリ パスにマップする SetVirtualHostNameToFolderMapping][Webview2ReferenceWin32Icorewebview23ViewWebview210790PrereleaseSetvirtualhostnametofoldermapping] メソッドを追加しました。  \([\#37][GithubMicrosoftedgeWebviewfeedbackIssue37] [、\#161、\#212\)。][GithubMicrosoftedgeWebviewfeedbackIssue161] [][GithubMicrosoftedgeWebviewfeedbackIssue212]  
*   背景の色とアルファ チャネルを設定する [DefaultBackgroundColor][Webview2ReferenceWin32Icorewebview2controller2ViewWebview210790PrereleaseGetDefaultbackgroundcolor] プロパティを追加しました。  \([\#414][GithubMicrosoftedgeWebviewfeedbackIssue414]\)。  
*   User Agent を取得または設定する [UserAgent][Webview2ReferenceWin32Icorewebview2experimentalsettingsViewWebview210790PrereleaseGetUseragent] プロパティを追加しました。  \([\#122][GithubMicrosoftedgeWebviewfeedbackIssue122]\)。  
*   メソッドを `CreateCookieWithCookie` メソッドに置き換 `CopyCookie` えました。  
*   新しいメソッドを使用して作成された [ICoreWebView2CompositionController][Webview2ReferenceWin32Icorewebview2compositioncontrollerViewWebview210790Prerelease] インターフェイスを使用したビジュアル ホスティング `CreateCoreWebView2CompositionController` のサポートが追加されました `ICoreWebView2Environment3` 。  
    
#### <a name="bug-fixes"></a>バグ修正  

*   WebView2 でMicrosoft Edgeショッピング機能を無効にしました。  
*   PDF ビューアーのコンテキスト メニューをオフ `AreDefaultContextMenusEnabled` にした `false` 場合は、 です。  \([\#605][GithubMicrosoftedgeWebviewfeedbackIssue605]\)。  
*   クエリを実行するときに返 `E_NOINTERFACE` されるバグを `ICoreWebView2` 修正しました `ICoreWebView2Experimental` 。  \([\#691][GithubMicrosoftedgeWebviewfeedbackIssue691]\)。  
*   に設定されている場合に、不正な形式の URI を使用してナビゲーションを許可する `CoreWebView2NavigationStartingEventArgs.Cancel` バグを修正しました `false` 。  \([\#400][GithubMicrosoftedgeWebviewfeedbackIssue400]\)。  
*   イベントハンドラーがイベントに接続されたポップアップ ウィンドウでブロックされる `window.print()` バグを修正 `NewWindowRequested` しました。  \([\#409][GithubMicrosoftedgeWebviewfeedbackIssue409]\)。  
*   異なるモニター間でアプリを移動する際の動的 DPI の問題を修正しました。  \([\#58][GithubMicrosoftedgeWebviewfeedbackIssue58]\)  
*   `HRESULT` [ICoreWebView2WebResourceResponseViewGetContentCompletedHandler::Invoke][Webview2ReferenceWin32Icorewebview2webresourceresponseviewgetcontentcompletedhandlerViewWebview210790PrereleaseInvoke]によって渡されるインスタンスが改善されました。  
*   [自動入力管理] ボタンをオフにします。  \([\#585][GithubMicrosoftedgeWebviewfeedbackIssue585]\)。  
*   複数Visual Studioでホストされている場合に実行中に `WebView2.Dispose` クラッシュする問題を修正しました。  \([\#816][GithubMicrosoftedgeWebviewfeedbackIssue816]\) と [\#442][GithubMicrosoftedgeWebviewfeedbackIssue442]\)。  
*   WebView2 コントロールをツールボックスに表示Visual Studioしました。  \([\#210][GithubMicrosoftedgeWebviewfeedbackIssue210]\)。  
*   CPU 使用率の高い問題を減らしました。  \([\#878][GithubMicrosoftedgeWebviewfeedbackIssue878]\)。  
*   非推奨の 1.0.781-prerelease パッケージの問題を修正しました。  \([\#875][GithubMicrosoftedgeWebviewfeedbackIssue875] および [\#878][GithubMicrosoftedgeWebviewfeedbackIssue878]\)。  
    
#### <a name="promotions"></a>プロモーション  

*   次の実験的な API が Stable に昇格されました。  
    *   ビジュアル ホスティング API  
    *   [SetVirtualHostNameToFolderMapping][Webview2ReferenceWin32Icorewebview23ViewWebview210790PrereleaseSetvirtualhostnametofoldermapping]  
        
### <a name="net"></a>.NET  

#### <a name="bug-fixes"></a>バグ修正  

*   WPF SDK を使用する WebView アプリがクラッシュするバグを修正しました。  ウィンドウを閉じるを選択すると `F4` 、クラッシュが発生しました。  \([\#399][GithubMicrosoftedgeWebviewfeedbackIssue399]\)。  
*   WebView2 の初期化画面が灰色ではなく透明になります。  \([\#196][GithubMicrosoftedgeWebviewfeedbackIssue196]\)。  
    
## <a name="1070550"></a>1.0.705.50  

リリース日: 2021 年 1 月 25 日  

[NuGet \|][NuGetGallery1.0.705.50]WebView2 ランタイム バージョン 86.0.616.0 以降  

### <a name="general"></a>全般  

#### <a name="promotions"></a>プロモーション  

*   次の実験的な API が Stable に昇格されました。  
    *   [WebResourceResponseReceived API][Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseAddWebresourceresponsereceived]  
    *   [NavigateWithWebResourceRequest API][Webview2ReferenceWin32Icorewebview2environment2ViewWebview210721PrereleaseCreatewebresourcerequest]  
    *   [Cookie 管理 API][Webview2ReferenceWin32Icorewebview2cookiemanagerViewWebview210721Prerelease]  
    *   [DOMContentLoaded API][Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseAddDomcontentloaded]  
    *   [WebView Environment プロパティ][Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseGetEnvironment]  
        
## <a name="10721-prerelease"></a>1.0.721-prerelease  

リリース日: 2020 年 12 月 8 日  

[NuGet \|][NuGetGallery1.0.721-prerelease]Microsoft Edgeバージョン 86.0.616.0 以降  

### <a name="general"></a>全般  

> [!IMPORTANT]
> **Breaking Change**: WebView2 プレリリース パッケージ 1.0.707 およびパッケージ 0.9.628 は非推奨です。  パッケージ 1.0.707 および package0.9.628 での開発を中止します。  

#### <a name="features"></a>機能  

*   [WebView2 グループ ポリシーを追加しました][DeployedgeMicrosoftEdgeWebviewPolicies]。  推奨されるプラクティスの詳細については [、「WebView2 のグループ ポリシー」に移動します][Webview2ConceptsEnterpriseGroupPoliciesForWebview2]。  
*   > [!IMPORTANT]
    > **Breaking Change**: 古いレジストリの場所を非推奨にしました。  
    > 
    > ```text
    > {Root}\Software\Policies\Microsoft\EmbeddedBrowserWebView\LoaderOverride\{AppId}
    > ```  
    
*   WebView2 での [ドラッグ アンド ドロップの][Webview2ReferenceWin32Icorewebview2experimentalcompositioncontroller3ViewWebview210721Prerelease] サポートが追加されました。  
*   DPI サポートを処理する API が追加されました。  
    *   WebView コンテンツと UI ポップアップ、および関連付けられた[RasterizationScaleChanged][Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseAddRasterizationscalechanged]イベントの DPI スケールを変更する[RasterizationScale][Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetRasterizationscale]プロパティを追加しました。  
    *   [ShouldDetectMonitorScaleChanges][Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetShoulddetectmonitorscalechanges]プロパティを追加し、必要に応じてプロパティ `RasterizationScale` を自動的に更新しました。  
    *   [BoundsMode][Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetBoundsmode]プロパティを追加して、境界がロジック ピクセルであり、WebView が WebView2 ピクセル表示に使用できる値を指定し、WebView は、物理サイズを取得するために使用します `RasterizationScale` `RasterizationScale` `Bounds` 。  
*   処理する `NewWindowRequested` イベントを更新 `Ctrl` + `click` しました `Shift` + `click` 。  \([\#168][GithubMicrosoftedgeWebviewfeedbackIssue168] および [\#371][GithubMicrosoftedgeWebviewfeedbackIssue371]\)。  
*   次の実験的な API が Stable に昇格されました。  
    *   [WebResourceResponseReceived API][Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseAddWebresourceresponsereceived]  
    *   [NavigateWithWebResourceRequest API][Webview2ReferenceWin32Icorewebview2environment2ViewWebview210721PrereleaseCreatewebresourcerequest]  
    *   [Cookie 管理 API][Webview2ReferenceWin32Icorewebview2cookiemanagerViewWebview210721Prerelease]  
    *   [DOMContentLoaded API][Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseAddDomcontentloaded]  
    *   [WebView Environment プロパティ][Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseGetEnvironment]  
        
### <a name="net"></a>.NET  

#### <a name="features"></a>機能  

*   .NET Core 3.1+ および .NET 5 で WinForms デザイナーを有効にしました。  
*   .NET Cookie の管理が改善されました。  \([\#611][GithubMicrosoftedgeWebviewfeedbackIssue611]\)。  
*   `CoreWebView2Ready` [CoreWebView2InitializationCompleted に置き換えました][DotnetApiMicrosoftWebWebview2Corewebview2initializationcompletedeventargs]。  
    
#### <a name="bug-fixes"></a>バグ修正

*   WebView2 [で Select をサポートする AcceleratorKeyPressed][DotnetApiMicrosoftWebWebview2WpfWebview2Acceleratorkeypressed] `AcceleratorKey` イベントを追加しました。  \([\#288][GithubMicrosoftedgeWebviewfeedbackIssue288]\)。  
*   不要なファイルが WebView2 フォルダーに出力されるのを削除しました。  \([\#461][GithubMicrosoftedgeWebviewfeedbackIssue461]\)。  
*   ホスト オブジェクト API が改善されました。  \([\#335][GithubMicrosoftedgeWebviewfeedbackIssue335] および [\#525][GithubMicrosoftedgeWebviewfeedbackIssue525]\)。  
    
## <a name="1066437"></a>1.0.664.37  

リリース日: 2020 年 11 月 20 日  

[NuGet \|][NuGetGallery1.0.664.37]WebView2 ランタイム バージョン 86.0.616.0 以降  

### <a name="general"></a>全般  

> [!IMPORTANT]
> **お**知らせ : .NET WPF/WinForms WebView2 SDK が一般公開 \(GA\)されました。  このリリースから、リリース SDK は転送互換性があります。  詳細については、GA アナウンス [ブログの投稿に移動します][MicrosoftDevblogDotnetAnnouncingGeneralAvailabilityForMicrosoftEdgeWebview2ForNetFixedDistributionMethod]。  

#### <a name="features"></a>機能  

*   .NET WPF/WinForms WebView2 が一般公開 \(GA\) に変更されました。  
*   固定配布 \(Bring-your-own\) モードが GA に達しました。  
    
### <a name="net"></a>.NET  

#### <a name="bug-fixes"></a>バグ修正  

*   `CoreWebView2NewWindowRequestedEventArgs.Handled` 新しいウィンドウが開かれません。  \([\#549][GithubMicrosoftedgeWebviewfeedbackIssue549] および [\#560][GithubMicrosoftedgeWebviewfeedbackIssue560]\)。  
    
## <a name="10674-prerelease"></a>1.0.674-prerelease  

リリース日: 2020 年 10 月 19 日  

[NuGet \|][NuGetGallery1.0.674-prerelease]WebView2 ランタイム バージョン 86.0.616.0 以降  

### <a name="general"></a>全般  

*   ナビゲーション中に投稿データや他の要求ヘッダーを提供する [NavigateWithWebResourceRequest][Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseNavigatewithwebresourcerequest] メソッドを追加しました。  
*   最初の HTML ドキュメントが読み込まれ、解析されると実行される [DOMContentLoaded][Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseAddDomcontentloaded] イベントが追加されました。  
*   WebView2 [に Environment][Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseGetEnvironment] プロパティを追加しました。  このプロパティは、WebView2 のインスタンスが作成された WebView2 環境を公開します。  
*   開発者が [WebView2][Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseGetCookiemanager] セッションを認証したり、WebView から Cookie を取得して他のツールを認証したりできる Cookie 管理 API が追加されました。  Webview チームは、言語またはフレームワーク固有の改善を計画しています。  詳細については、「API レビュー: [Cookie 管理」に移動します][GithubMicrosoftedgeWebview2AnnouncementIssue2]。  
*   [WebResourceResponseReceived][Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseAddWebresourceresponsereceived]イベントを更新し、変更できない[WebResourceResponseView][Webview2ReferenceWin32Icorewebview2experimentalwebresourceresponseviewViewWebview210674Prerelease]と[WebResourceResponseReceivedEventArgs::P opulateResponseContent][Webview2ReferenceWin32Icorewebview2experimentalwebresourceresponsereceivedeventargsViewWebview209628PrereleasePopulateresponsecontent]を[WebResourceResponseView::GetContent][Webview2ReferenceWin32Icorewebview2experimentalwebresourceresponseviewViewWebview210674PrereleaseGetcontent]に追加しました。  
*   WebView2 [Microsoft Defender Application Guard (WDAG)][WindowsSecurityThreatProtectionMicrosoftDefenderApplicationGuardWindows10]を無効にします。  
*   Visual Hosting [用の SystemCursorId][Webview2ReferenceWin32Icorewebview2experimentalcompositioncontroller2ViewWebview210674PrereleaseGetSystemcursorid] が追加されました。  
*   Visual Hosting の Input メソッドで修正されたバグを追加しました。  
*   削除された `version.lib` WebView2 静的ライブラリを使用する場合の要件が含まれます。  
    
### <a name="net"></a>.NET  

*   変数を [公開するために CoreWebView2][DotnetApiMicrosoftWebWebview2CoreCorewebview2] クラスを更新 `CoreWebView2Environment` しました。  
*   名前空間内のカスタム EventArgs クラスの実装を `Microsoft.Web.WebView2.Core` [System.EventArgs][DotnetApiSystemEventargs] または [System.ComponentModel.CancelEventArgs][DotnetApiSystemComponentmodelCancelEventargs]のサブクラスに変更しました。  \([\#250][GithubMicrosoftedgeWebviewfeedbackIssue250]\)  
*   WinForms の [CoreWebView2CreationProperties の][DotnetApiMicrosoftWebWebview2Winforms] サポートが追加されました。  \([\#204][GithubMicrosoftedgeWebviewfeedbackIssue204]\)。  
*   [WebResourceRequested][DotnetApiMicrosoftWebWebview2CoreCorewebview2Webresourcerequested] .NET API を追加しました。  \([\#219][GithubMicrosoftedgeWebviewfeedbackIssue219]\)。  
*   WinForms Designer [Source プロパティを既定][DotnetApiMicrosoftWebWebview2WinformsWebview2Source] または null にリセットしました。  \([\#177][GithubMicrosoftedgeWebviewfeedbackIssue177]\)。  
*   100% 未満の DPI WebView2.Iniサポートするために、t() の WebView2 境界を更新しました。  \([\#432][GithubMicrosoftedgeWebviewfeedbackIssue432]\)。  
*   [BuildWindowCore と][DotnetApiMicrosoftWebWebview2WpfWebview2Buildwindowcore] [DestroyWindowCore][DotnetApiMicrosoftWebWebview2WpfWebview2Destroywindowcore]を更新し、堅牢性を向上しました。  \([\#382][GithubMicrosoftedgeWebviewfeedbackIssue382]\)。  
*   オペレーティング システム アーキテクチャではなく、プロセス ビットを読み込む .NET Loader ベースを更新しました。  \([\#431][GithubMicrosoftedgeWebviewfeedbackIssue431]\)。  
*   `EdgeNotFoundException` [WebView2RuntimeNotFoundException に名前を変更しました][DotnetApiMicrosoftWebWebview2CoreWebview2runtimenotfoundexception]。  
    
## <a name="1062222"></a>1.0.622.22  

リリース日: 2020 年 10 月 19 日  

[NuGet \|][NuGetGallery1.0.622.22]WebView2 ランタイム バージョン 86.0.616.0 以降  

### <a name="general"></a>全般  

> [!IMPORTANT]
> **お**知らせ : Win32 C/C++ WebView2 が一般公開 \(GA\)されました。  このリリースを開始すると、リリース SDK は転送互換性があります。  詳細については、「GA アナウンス ブログ [の投稿」に移動します][WindowsBlogsMsedgedevEdgeWebview2GeneralAvailability]。  

*   [Evergreen WebView2 ランタイムとインストーラーは][Webview2ConceptsDistributionUnderstandRuntimeInstaller] GA です。  ブートストラップ、ブートストラップ用のダウンリンク リンク、および Evergreen WebView2 ランタイム用のスタンドアロン インストーラーは[、WebView2][MicrosoftDeveloperMicrosoftEdgeWebView2]でMicrosoft Edgeできます。  インストール ワークフローのサンプル コードは [、WebView2Samples repo でも使用できます][GithubMicrosoftedgeWebview2samplesMain]。  
*   [開発者プレビューでは、][Webview2ConceptsDistributionFixedVersionDistributionMode] 固定バージョン モードを使用できます。  
    
## <a name="0962211"></a>0.9.622.11  

リリース日: 2020 年 9 月 10 日  

[NuGet \|][NuGetGallery0.9.622.11]WebView2 ランタイム バージョン 86.0.616.0 以降  

### <a name="general"></a>全般  

*   > [!IMPORTANT]
    > **お**知らせ : この SDK は、WebView2 Win32 C/C++ GA のリリース候補です。  GA バージョンでは、同じ API インターフェイスと機能を使用する必要があります。  
    
*   接続 [されていないブラウザー ポリシー][DeployedgeMicrosoftEdgePolicies]。  
*   WebView2 [環境オプションに AllowSingleSignOnUsingOSPrimaryAccount][Webview2ReferenceWin32Icorewebview2environmentoptionsViewWebview209622GetAllowsinglesignonusingosprimaryaccount] プロパティを追加し、WebView の条件付きアクセスを有効にします。  
*   `ICoreWebView2NewWindowRequestedEventArgs` [WindowFeatures プロパティ][Webview2ReferenceWin32Icorewebview2newwindowrequestedeventargsViewWebview209622GetWindowfeatures]と、関連付けられた[ICoreWebView2WindowFeatures を含む更新。][Webview2ReferenceWin32Icorewebview2windowfeaturesViewWebview209622]  \([\#293][GithubMicrosoftedgeWebviewfeedbackIssue293]\)。  
*   `System.Windows.Rect` `System.Drawing.Rectangle` `System.Windows.Rect` \( \#235 \) の代わりに[使用#235][GithubMicrosoftedgeWebviewfeedbackIssue235]しました。  
*   パラメーターなしで要求を処理する NewWindowRequested `window.open()` イベントを更新しました。  \([\#293][GithubMicrosoftedgeWebviewfeedbackIssue293]\)。  
*   [AdditionalBrowserArguments][Webview2ReferenceWin32Icorewebview2environmentoptionsViewWebview209622PutAdditionalbrowserarguments] を使用して指定した場合、環境変数やレジストリ値では `ICoreWebView2EnvironmentOptions` 上書きされていません。  詳細については、「[CreateCoreWebView2EnvironmentWithOptions][Webview2ReferenceWin32Webview2IdlViewWebview209622Createcorewebview2environmentwithoptions]」を参照してください。  
    
## <a name="09579"></a>0.9.579  

リリース日: 2020 年 7 月 20 日  

[NuGet \|][NuGetGallery0.9.579]Microsoft Edgeバージョン 86.0.579.0。  

### <a name="general"></a>全般  

*   > [!IMPORTANT]
    > **お**知らせ : Evergreen WebView2 ランタイムとインストーラーがプレビュー用にリリースされました。  詳細については [、「WebView2 の配布」に移動します][Webview2ConceptsDistributionUnderstandRuntimeInstaller]。  
    
*   > [!IMPORTANT]
    > **お**知らせ : 次の WebView2 SDK バージョンは、次の SDK リリース以降はサポートされなくなりました。  
    > 
    > *   [0.8.190](#08190)  
    > *   [0.8.230](#08230)  
    > *   [0.8.270](#08270)  
    > *   [0.8.314](#08314)  
    > *   [0.8.355](#08355)  
    > 
    > WebView2 SDK バージョンは、このバージョンでも非推奨 nuget.org。 WebView2 では、最新バージョンの WebView2 を使用して最新の情報を取得する必要があります。  
    
*   WebView ワーカー スレッドの機能強化が追加されました。  \([\#318][GithubMicrosoftedgeWebviewfeedbackIssue318]\)。  
*   WebView でポップアップ ブロッカーをオフにしました。  詳細については、イベントの [IsUserInitiated プロパティ][Webview2ReferenceWin32Icorewebview2newwindowrequestedeventargsViewWebview209538GetIsuserinitiated] に移動 `NewWindowRequested` します。  
*   確実な WebView ナビゲーション開始イベントが実行されます `about:blank` 。  これで、すべてのナビゲーションに対してイベントが実行されますが、要素または要素の取り消しは `NavigationStarting` `about:blank` サポートされ `srcdoc` `iframe` 、無視されません。  
*   `edge://`WebView で一部の URI スキームをブロックしました。  
*   WebView2 環境オプション [に実験的な IsSingleSignOnUsingOSPrimaryAccountEnabled][Webview2ReferenceWin32Icorewebview2experimentalenvironmentoptionsViewWebview209538PrereleaseGetIssinglesignonusingosprimaryaccountenabled] プロパティを追加し、WebView の条件付きアクセスを有効にします。  
*   WebResource 要求からの応答を WebView が受信して処理した後に実行される実験的な [WebResourceResponseReceived][Webview2ReferenceWin32Icorewebview2experimentalViewWebview209538PrereleaseAddWebresourceresponsereceived] イベントが追加されました。  認証ヘッダーがある場合は、応答オブジェクトに含まれます。  
    
### <a name="net"></a>.NET  

*   WPF フォーカスの処理が改善されました。  \([\#185][GithubMicrosoftedgeWebviewfeedbackIssue185]\)。  
*   WPF `ZoomFactor` Webview2 コントローラーにプロパティを追加しました。  
    
## <a name="09538"></a>0.9.538  

[NuGet \|][NuGetGallery0.9.538]Microsoft Edgeバージョン 85.0.538.0。  

### <a name="general"></a>全般  

*   WebView2 SDK バージョン [0.8.149 のサポートを削除します](#08149)。  WebView2 では、最新バージョンの WebView2 を使用して最新の情報を取得する必要があります。  
*   グループ ポリシーを更新し、ブラウザーのプロファイル パスが変更Microsoft Edge[\(][GithubMicrosoftedgeWebviewfeedbackIssue179]\) を#179しました。  
    
### <a name="win32-cc"></a>Win32 C/C++  

*   [ICoreWebView2ExperimentalNewWindowRequestedEventArgs::get_WindowFeatures][Webview2ReferenceWin32Icorewebview2experimentalnewwindowrequestedeventargsViewWebview209538PrereleaseGetWindowfeatures]を追加しました。これは `window.open()` [、ICoreWebView2ExperimentalWindowFeatures][Webview2ReferenceWin32Icorewebview2experimentalwindowfeaturesViewWebview209538Prerelease] \([#70][GithubMicrosoftedgeWebviewfeedbackIssue70]\) に関連付けられたときに発生します。  
*   > [!IMPORTANT]
    > **Breaking Change**: [非推奨の CreateCoreWebView2EnvironmentWithDetails を][Webview2ReferenceWin32Webview2IdlViewWebview209488Createcorewebview2environmentwithdetails] [CreateCoreWebView2EnvironmentWithOptions][Webview2ReferenceWin32Webview2IdlViewWebview209538Createcorewebview2environmentwithoptions]に置き換えました。  
    
*   > [!IMPORTANT]
    > **Breaking Change**: WebView2 API が Windows API の名前付け規則と一致するために、WebView チームは次の名前を更新しました。  
    > 
    > *   [AreRemoteObjectsAllowed は][Webview2ReferenceWin32Icorewebview2settingsViewWebview209488GetAreremoteobjectsallowed] [AreHostObjectsAllowed です][Webview2ReferenceWin32Icorewebview2settingsViewWebview209538GetArehostobjectsallowed]。  
    
*   [AddHostObjectToScript を更新][Webview2ReferenceWin32Icorewebview2ViewWebview209538ddhostobjecttoscript]しました。  元のホスト オブジェクト シリアライザー マーカーがプロキシ オブジェクトに設定されます。  次に、JavaScript コールバック \( #148 \) でパラメーターとして渡された場合、ホスト オブジェクト シリアライザー マーカーはホスト[オブジェクトとしてシリアル化][GithubMicrosoftedgeWebviewfeedbackIssue148]されます。  
    
### <a name="net-09538-pre-release"></a>.NET (0.9.538 プレリリース)  

*   WebView2 SDK の包括的なガイドである WinForms および WPF WebView2API サンプルをリリースしました。  詳細については、「Samples [Repo」に移動します][GithubMicrosoftedgeWebview2samplesMain]。  
*   視覚的なホスティングとウィンドウ機能の実験的な [API のサポートが追加されました][Webview2ConceptsVersioningExperimentalApis]。  
*   > [!IMPORTANT]
    > **Breaking Change**: 次の遅延が IDisposable を実装しました。  [ScriptDialogOpening][DotnetApiMicrosoftWebWebview2CoreCorewebview2Scriptdialogopening]、 [NewWindowRequested][DotnetApiMicrosoftWebWebview2CoreCorewebview2Newwindowrequested]、 [WebResourceRequested][DotnetApiMicrosoftWebWebview2CoreCorewebview2Webresourcerequested]、 [PermissionRequested][DotnetApiMicrosoftWebWebview2CoreCorewebview2Permissionrequested].  
    
*   [GetAvailableBrowserVersionString][DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentGetavailablebrowserversionstring]および[CompareBrowserVersions][DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentComparebrowserversions]を[CoreWebView2Environment][DotnetApiMicrosoftWebWebview2CoreCorewebview2environment]静的として追加しました。  
    
## <a name="09515-prerelease"></a>0.9.515-prerelease  

[NuGet \|][NuGetGallery0.9.515-prerelease]Microsoft Edgeバージョン 84.0.515.0。  

*   > [!IMPORTANT]
    > **お**知らせ : WebView2 は .NET Framework 4.6.2 以降の Windows フォームと WPF、プレリリース パッケージでは .NET Core 3.0 以降を**サポートしています**。  
    
*   WPF アプリの構築の詳細については[、「WPF はじめにガイド」および「WebView2][Webview2GetStartedWpf] [WPF Reference][DotnetApiMicrosoftWebWebview2Wpf] for WPF 固有の API」に移動します。  
*   Windows フォーム アプリの構築の詳細については[、「Windows フォーム はじめに ガイド][Webview2GetStartedWinforms]」および「webView2 Windows フォーム リファレンス[][DotnetApiMicrosoftWebWebview2Winforms]」に移動して、Windows フォーム固有の API を参照してください。  
*   CoreWebView2 API の詳細については [、「.NET リファレンス」に移動します][DotnetApiMicrosoftWebWebview2Core]。  
*   > [!CAUTION]
    > **既知の問題**: WebView チームは、今後のリリースで解決されるプレリリースのいくつかの問題を認識しています。  
    > 
    > *   **DPI の認識**: WPF 用 WebView2 は現在 DPI 対応ではありません。  高 DPI モニターで WebView2 を初期化する場合、ウィンドウのサイズが変更されるまで、最初に WebView がウィンドウの一部として初期化されるという既知の問題があります。  
    > *   **WPF デザイナー**: WPF デザイナーは現在サポートされていません。  テキスト エディターで適切な XAML を直接変更して、アプリに WebView2 コントロールを追加します。  
    
## <a name="09488"></a>0.9.488  

[NuGet \|][NuGetGallery0.9.488]Microsoft Edgeバージョン 84.0.488.0。  

*   > [!IMPORTANT]
    > **お**知らせ : 今後のバージョン 83 Microsoft Edge、Evergreen WebView は Stable ブラウザー チャネルをターゲットにしなくなりました。  代わりに、WebView チームが現在開発中のインストーラーを介してチェーン インストールできる [、Evergreen WebView2 ランタイム][Webview2ConceptsDistributionEvergreenDistributionMode]というブランド化された別のバイナリ セットを対象とします。  詳細については [、「App-Distribution」に移動します][Webview2ConceptsDistribution]。  
    
*   > [!IMPORTANT]
    > **お**知らせ : WebView チームは、実験的な API を含むプレリリース パッケージ \(試用\) と安定した API を持つ安定したリリース パッケージ \(信頼できる\) の 2 つのパッケージをリリースします。  違いについては、「ブラウザーのバージョンと [WebView2 について」に移動します][Webview2ConceptsVersioning]。  
    
*   > [!IMPORTANT]
    > **Breaking Change**: WebView2 API が Windows API の名前付け規則と一致するために、WebView チームは次のインターフェイスの名前を更新しました。  
    > 
    > *   `CORE_WEBVIEW2_*` プレフィックスは現在です `COREWEBVIEW2_*` 。  
    > *   [GetCoreWebView2BrowserVersionInfo][Webview2ReferenceWin32Webview2IdlViewWebview209430Getcorewebview2browserversioninfo] は [GetAvailableCoreWebView2BrowserVersionString です][Webview2ReferenceWin32Webview2IdlViewWebview209488Getavailablecorewebview2browserversionstring]。  
    > *   [get_BrowserVersionInfo][Webview2ReferenceWin32Icorewebview2environmentViewWebview209430GetBrowserversioninfo]が表示[get_BrowserVersionString。][Webview2ReferenceWin32Icorewebview2environmentViewWebview209488GetBrowserversionstring]  
    > *   [AddRemoteObject][Webview2ReferenceWin32Icorewebview2ViewWebview209430Addremoteobject] は [AddHostObjectToScript です][Webview2ReferenceWin32Icorewebview2ViewWebview209488Addhostobjecttoscript]。  
    > *   [RemoveRemoteObject は][Webview2ReferenceWin32Icorewebview2ViewWebview209430Removeremoteobject] [RemoveHostObjectFromScript です][Webview2ReferenceWin32Icorewebview2ViewWebview209488Removehostobjectfromscript]。  
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
    > **Breaking Change**: [非推奨の CreateCoreWebView2EnvironmentWithDetails を][Webview2ReferenceWin32Webview2IdlViewWebview209488Createcorewebview2environmentwithdetails] [CreateCoreWebView2EnvironmentWithOptions][Webview2ReferenceWin32Webview2IdlViewWebview209488Createcorewebview2environmentwithoptions]に置き換えました。  
    
*   [FrameNavigationCompleted イベントを追加][Webview2ReferenceWin32Icorewebview2ViewWebview209488AddFramenavigationcompleted]しました。  これで、要素がナビゲーションを完了すると、イベントが実行され、ナビゲーションとナビゲーション ID の成功 `iframe` が返されます。  
*   [ICoreWebView2EnvironmentOptions][Webview2ReferenceWin32Icorewebview2environmentoptionsViewWebview209488]インターフェイスが追加されました。これは、アプリが対象とする Evergreen WebView2 ランタイムのバージョンを決定するために使用できます。  
*   [IsBuiltInErrorPageEnabled 設定を追加][Webview2ReferenceWin32Icorewebview2settingsViewWebview209488GetIsbuiltinerrorpageenabled]しました。  これで、ナビゲーションエラーとレンダリング プロセスの失敗のために、組み込みのエラー Web ページのオンとオフを切り替えます。  
*   .NET 実装 \( #113 `IDispatch` \)[をサポートするために、リモート オブジェクトの挿入を更新][GithubMicrosoftedgeWebviewfeedbackIssue113]しました。  
*   コンテキスト メニュー \( \ ( \ ) からの要求を処理する [NewWindowRequested][Webview2ReferenceWin32Icorewebview2ViewWebview209488AddNewwindowrequested] [イベント#108][GithubMicrosoftedgeWebviewfeedbackIssue108]しました。  
*   ビジュアル ホスティング API にアクセスできる最初の独立した WebView2 プレリリース パッケージをリリースしました。  WebView チームは [APISample を更新して][GithubMicrosoftedgeWebview2samplesMain] 、新しい実験的 API を含む。  
    *   コンポジション ツリーに接続し、WebView に入力を提供する [ICoreWebView2ExperimentalCompositionController][Webview2ReferenceWin32Icorewebview2experimentalcompositioncontrollerViewWebview209488Prerelease] インターフェイスを追加しました。  
    *   [ICoreWebView2ExperimentalPointerInfo][Webview2ReferenceWin32Icorewebview2experimentalpointerinfoViewWebview209488Prerelease]を追加しました `POINTER_INFO` 。  このオブジェクトは SendPointerInput に渡され、ポインター入力を WebView に挿入します。  
    *   [ICoreWebView2ExperimentalCursorChangedEventHandler][Webview2ReferenceWin32Icorewebview2experimentalcursorchangedeventhandlerViewWebview209488Prerelease]を追加しました。これは、WebView 上のマウス カーソルを変更する必要があるときにアプリに指示します。  WebView のテキスト ボックスの上にマウスを置く場合、カーソルは矢印からセレクターに変わります。  このプロパティは、WebView のマウス カーソルの現在の位置 `cursor` `CompositionController` をアプリに指示します。  
        
## <a name="09430"></a>0.9.430  

[NuGet \|][NuGetGallery0.9.430]Microsoft Edgeバージョン 82.0.430.0。  

WebView2 SDK は公式の Win32 C++ Beta バージョンで、フィードバックからのいくつかの機能要求が組み込まれています。  WebView チームは、変更が大きかったリリースの数を制限します。  一般的な可用性のアプローチとして、いくつかの大きな変更点がベータ版リリースに組み込まれる。  

*   > [!IMPORTANT]
    > **Breaking Change**: 最終リリースが近づくにつれて `IWebView2WebView` 、WebView2 API が Windows API 名前付け規則と一致するためにプレフィックスの名前を変更しました `ICoreWebView2` 。  さらに、UI フレームワークから WebView2 SDK を活用するために、WebView チームは `ICoreWebView2` [ICoreWebView2 と ICoreWebView2Host][Webview2ReferenceWin32Icorewebview2ViewWebview209430] に [分かっています][Webview2ReferenceWin32Icorewebview2hostViewWebview209430]。  `ICoreWebView2Host` ウィンドウとコンポジションに関連するサイズ変更、表示と非表示、フォーカス、その他の機能をサポートします。  ICoreWebView2 は、他のすべての WebView2 機能をサポートします。  変更を組み込む方法の詳細については、WebView2 [][GithubMicrosoftedgeWebview2samplesPr17] [APISample][GithubMicrosoftedgeWebview2samplesMain]プロジェクトの WebView2 プル要求に移動します。  
    
*   > [!IMPORTANT]
    > **Breaking Change**: [DocumentStateChanged][Webview2ReferenceWin32Iwebview2webviewViewWebview208355AddDocumentstatechanged]を[SourceChanged、ContentLoading、HistoryChanged][Webview2ReferenceWin32Icorewebview2ViewWebview209430AddSourcechanged]の 3 つのコンポーネント[に分割します][Webview2ReferenceWin32Icorewebview2ViewWebview209430AddHistorychanged]。 [][Webview2ReferenceWin32Icorewebview2ViewWebview209430AddContentloading]  これで、ソース URL が変更された場合、 `SourceChanged` イベントが実行されます。  履歴の状態が変更された場合、 `HistoryChanged` イベントが実行されます。  イベント `ContentLoading` は、新しいドキュメントが読み込まれるときに、最初のスクリプトの前に実行されます。  
    
*   ARM64 アーキテクチャのサポートが追加されました。  
*   タッチ スクリーン デバイスのソフト入力パネル \(SIP\) のサポートが追加されました。  
*   サーバー 2008 R2、Windows R2、Windows Server 2012、Windows Server 2012、およびWindows Server 2016。  
*   ウィンドウ モード [でウィンドウに従うステータス バーに NotifyParentWindowPositionChanged][Webview2ReferenceWin32Icorewebview2hostViewWebview209430Notifyparentwindowpositionchanged] が追加されました。  また、アクセシビリティ機能を機能するために、ウィンドウレス モードで変更を実装します。  
*   リモート オブジェクトから Web ページにアクセスできるかどうかをグローバルに制御する [AreRemoteObjectsAllowed][Webview2ReferenceWin32Icorewebview2settingsViewWebview209430GetAreremoteobjectsallowed] 設定が追加されました。  既定ではオン `AreRemoteObjectsAllowed` になっているので [、AddRemoteObject][Webview2ReferenceWin32Icorewebview2ViewWebview209430Addremoteobject] によって追加されたリモート オブジェクトには Web ページからアクセスできます。  オフ `AreRemoteObjectsAllowed` にすると、Web ページからオブジェクトにアクセスできない。  変更は、次のナビゲーション イベントに適用されます。  
*   [IsZoomControlEnabled][Webview2ReferenceWin32Icorewebview2settingsViewWebview209430GetIszoomcontrolenabled]設定を追加し、ユーザーが \(または + マウス ホイール `ctrl` + `+` `ctrl` + `-` `ctrl` \) を使用して WebView のズームに影響を与えなけれな  設定をオフにした場合 [でも][Webview2ReferenceWin32Icorewebview2hostViewWebview209430PutZoomfactor] 、put_ZoomFactorを使用してズームを設定できます。  
*   現在の WebView にのみ適用される ZoomFactor を変更しました。  現在の WebView に対するズームの変更は、同じ原点のサイトを使用して移動した他の WebView には影響を与えいません。  詳細については、「get_ZoomFactor」 [に移動します][Webview2ReferenceWin32Icorewebview2hostViewWebview209430GetZoomfactor]。  
*   WebView[\(][GithubMicrosoftedgeWebviewfeedbackIssue95]の ZoomView UI を非表示#95 \)。  
*   [SetBoundsAndZoomFactor を追加][Webview2ReferenceWin32Icorewebview2hostViewWebview209430Setboundsandzoomfactor]しました。  これで、WebView のズーム倍率と範囲を同時に設定できます。  
*   [WindowCloseRequested イベントを追加][Webview2ReferenceWin32Icorewebview2ViewWebview209430AddWindowcloserequested]しました。  詳細については、\( \( [add_WindowCloseRequested][Webview2ReferenceWin32Icorewebview2ViewWebview209430AddWindowcloserequested] \)[#119][GithubMicrosoftedgeWebviewfeedbackIssue119]移動します。  
*   JavaScript ダイアログ イベントのダイアログの種類のサポートが `beforeunload` 追加され、列挙型 [CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_BEFOREUNLOAD][Webview2ReferenceWin32Icorewebview2ViewWebview209430CoreWebview2ScriptDialogKind] 追加されました。  
*   HttpRequestHeaders に GetHeaders、GetHeader を HttpResponseHeaders に、httpHeadersCollectionIterator に get_HasCurrentHeader[プロパティを][Webview2ReferenceWin32Icorewebview2httpheaderscollectioniteratorViewWebview209430GetHascurrentheader]追加しました。 [][Webview2ReferenceWin32Icorewebview2httprequestheadersViewWebview209430Getheaders] [][Webview2ReferenceWin32Icorewebview2httpresponseheadersViewWebview209430Getheader]  
*   > [!IMPORTANT]
    > **Breaking Change**: 変更 `DevToolsProtocolEventReceived` された動作。  ここで、特定の DevTools Protocol イベントに対して[DevToolsProtocolEventReceiver][Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview209430]を作成し、この[][Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview209430AddDevtoolsprotocoleventreceived]イベントをサブスクライブ/サブスクライブ解除するには、add_DevToolsProtocolEventReceived remove_DevToolsProtocolEventReceived。 / [][Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview209430RemoveDevtoolsprotocoleventreceived]  
    
*   > [!IMPORTANT]
    > **Breaking Change**: この `WebMessageReceivedEventArgs` [プロパティget_WebMessageAsString][Webview2ReferenceWin32Iwebview2webmessagereceivedeventargsViewWebview208355GetWebmessageasstring] [TryGetWebMessageAsString メソッドに変更][Webview2ReferenceWin32Icorewebview2webmessagereceivedeventargsViewWebview209430Trygetwebmessageasstring] しました。  
    
*   > [!IMPORTANT]
    > **Breaking Change**: Change `AcceleratorKeyPressedEventArgs` [Handle][Webview2ReferenceWin32Iwebview2acceleratorkeypressedeventargsViewWebview208355Handle] メソッドを get_Handledプロパティ [に][Webview2ReferenceWin32Icorewebview2acceleratorkeypressedeventargsViewWebview209430GetHandled] 変更しました。  
    
## <a name="08355"></a>0.8.355  

[NuGet \|][NuGetGallery0.8.355]Microsoft Edge 80.0.355.0 を使用します。  

*   リリースされた WebView2API サンプルは、WebView2 SDK の包括的なガイドです。  詳細については、「API サンプル」 [に移動します][GithubMicrosoftedgeWebview2samplesApisample]。  
*   英語 \( および \) 以外のすべての言語に IME[サポート#30][GithubMicrosoftedgeWebviewfeedbackIssue30]しました。  
*   バグ 報告に応じてイベントの API `WebResourceRequested` サーフェスを更新しました。  作成時にフィルターとイベントを同時に指定する機能は廃止されました。  Web リソース要求イベントを作成するには、add_WebResourceRequestedを使用してイベントを追加し[、AddWebResourceRequestedFilter][Webview2ReferenceWin32Iwebview2webview5ViewWebview208355Addwebresourcerequestedfilter]を使用してフィルターを追加します。 [][Webview2ReferenceWin32Iwebview2webview5ViewWebview208355AddWebresourcerequested]  [RemoveWebResourceRequestedFilter は][Webview2ReferenceWin32Iwebview2webview5ViewWebview208355Removewebresourcerequestedfilter] フィルター \( \( \)[\#36(][GithubMicrosoftedgeWebviewfeedbackIssue36]#74 \)[を削除][GithubMicrosoftedgeWebviewfeedbackIssue74]します。  
*   > [!IMPORTANT]
    > **Breaking Change**: フルスクリーンの動作を変更しました。  非推奨 [の IsFullScreenAllowed][Webview2ReferenceWin32Iwebview2settingsViewWebview208355GetIsfullscreenallowedDeprecated].  既定では、WebView \(video\など) の要素がフルスクリーンに設定されている場合、WebView の境界が埋め込みます。  [ContainsFullScreenElementChanged][Webview2ReferenceWin32Iwebview2containsfullscreenelementchangedeventhandlerViewWebview208355]イベントと[][Webview2ReferenceWin32Iwebview2webview5ViewWebview208355GetContainsfullscreenelement]get_ContainsFullScreenElement を使用して、要素が全画面表示モードに入る場合にアプリで WebView のサイズを変更する方法を指定します。  
    
## <a name="08314"></a>0.8.314  

[NuGet \|][NuGetGallery0.8.314]Microsoft Edgeバージョン 80.0.314.0。  

*   7、Windows、およびWindows 8のサポートがWindows 8.1。  
*   WebView2 Visual StudioおよびVisual Studio Codeサポートを追加しました。  次に、IDE から WebView2 でスクリプトをデバッグします。  詳細については [、「WebView2 コントロールを使用して開発するときにデバッグする方法」を参照してください][Webview2HowToDebug]。  
*   WebView2 の実行中のスクリプトで、アプリの Win32 コンポーネントから IDispatch オブジェクトにアクセスし、IDispatch オブジェクトのプロパティにアクセスするために追加 `Native Object Injection` されました。  詳細については [、AddRemoteObject][Webview2ReferenceWin32Iwebview2webview4ViewWebview208355Addremoteobject] \( #17 \)[に移動][GithubMicrosoftedgeWebviewfeedbackIssue17]します。  
*   イベントを `AcceleratorKeyPressed` 追加しました。  詳細については、「\( \( [add_AcceleratorKeyPressed][Webview2ReferenceWin32Iwebview2webview4ViewWebview208355AddAcceleratorkeypressed] \)[#57][GithubMicrosoftedgeWebviewfeedbackIssue57]移動します。  
*   をオフに `Context Menus` しました。  詳細については、\( \( [put_AreDefaultContextMenusEnabled][Webview2ReferenceWin32Iwebview2settings2ViewWebview208355PutAredefaultcontextmenusenabled] \)[#57][GithubMicrosoftedgeWebviewfeedbackIssue57]移動します。  
*   更新されました `DPI Awareness` 。  これで、WebView の DPI 認識は、ホスト アプリの DPI 認識と同じです。  
    
    > [!NOTE]
    > 別のハイブリッド アプリが元の WebView とは異なる DPI Awareness で起動された場合、同じ \( #1 \) の場合、新しい WebView `user data folder` [は起動されません][GithubMicrosoftedgeWebviewfeedbackIssue1]。  
    
*   WebView2 が WebView でホストされている Web コンテンツによって求める通知アクセス許可要求を自動的に拒否するように `Notification Change Behavior` 更新されました。  
    
## <a name="08270"></a>0.8.270  

[NuGet \|][NuGetGallery0.8.270]Microsoft Edgeバージョン 78.0.270.0。  

*   ドキュメントタイトル `DocumentTitleChanged` の変更 \( \#27 \)[を示すイベントを追加][GithubMicrosoftedgeWebviewfeedbackIssue27]しました。  
*   API `GetWebView2BrowserVersionInfo` \([\#18][GithubMicrosoftedgeWebviewfeedbackIssue18]\) を追加しました。  
*   イベントを `NewWindowRequested` 追加しました。  
*   削除する `CreateWebView2EnvironmentWithDetails` 関数を更新しました `releaseChannelPreference` 。  関数の詳細については `CreateWebView2EnvironmentWithDetails` [、CreateWebView2EnvironmentWithDetails に移動します][Webview2ReferenceWin32Webview2IdlViewWebview208355Createwebview2environmentwithdetails]。  レジストリと環境変数のオーバーライドは引き続きサポートされています。  既定のチャネル設定は、オーバーライドされない限り使用されます。  
    チャネル検索中、WebView チームは、WebView2 SDK と互換性がない以前のチャネル バージョンをスキップします。  
    WebView チームは、より安定したチャネルを選択して、エンド ユーザーにとって最も一貫性のある動作を保証します。  最新の Canary ビルドでテストする場合は、アプリを起動する前に環境変数を `WEBVIEW2_RELEASE_CHANNEL_PREFERENCE` 設定するスクリプト `1` を作成する必要があります。  
*   指定しない場合 `CreateWebView2EnvironmentWithDetails` に選択するロジックを使用して `userDataFolder` 関数を更新しました。  関数の詳細については `CreateWebView2EnvironmentWithDetails` [、CreateWebView2EnvironmentWithDetails に移動します][Webview2ReferenceWin32Webview2IdlViewWebview208355Createwebview2environmentwithdetails]。  以前に既定の場所を使用した場合、新しい SDK に切り替える場合、既定値は \(ホスト コード ディレクトリの新しい場所に設定\) にリセットされ、状態も `userDataFolder` `userDataFolder` リセットされます。  ホスト プロセスに指定したディレクトリへの書き込み権限が付与されていない場合、関数が `CreateWebView2EnvironmentWithDetails` 失敗する可能性があります。  古いディレクトリから新しいディレクトリに `user data folder` データをコピーできます。  
    
## <a name="08230"></a>0.8.230  

[NuGet \|][NuGetGallery0.8.230]Microsoft Edge 77.0.230.0 を使用します。  

*   すべてのナビゲーション `Stop` と保留中のリソースフェッチを停止する API が追加されました[\(][GithubMicrosoftedgeWebviewfeedbackIssue28]\#28\)。  
*   パッケージ `.tlb` \([\NuGet \) にファイルを#22][GithubMicrosoftedgeWebviewfeedbackIssue22]しました。  
*   パッケージ \([\NuGet \)][GithubMicrosoftedgeWebviewfeedbackIssue32]のインストーラー リストに .NET プロジェクト#32しました。  
    
## <a name="08190"></a>0.8.190  

[NuGet \|][NuGetGallery0.8.190]Microsoft Edge 77.0.190.0 を使用します。  

*   ユーザーが `get_AreDevToolsEnabled` / `put_AreDevToolsEnabled` DevTools \( \#16 \)[を開くことができる#16][GithubMicrosoftedgeWebviewfeedbackIssue16]追加されました。  
*   ステータス バー `get_IsStatusBarEnabled` / `put_IsStatusBarEnabled` が \([\( \#19][GithubMicrosoftedgeWebviewfeedbackIssue19]\) と表示される#19追加されました。  
*   ナビゲーション履歴 `get_CanGoBack` / `GoBack` / `get_CanGoForward` / `GoForward` を行き来する場合に追加されました。  
*   WebView で HTTP ヘッダーを表示および変更する HTTP ヘッダーの種類 `IWebView2HttpHeadersCollectionIterator` / `IWebView2HttpRequestHeaders` / `IWebView2HttpRequestHeaders` \( \) を追加しました。  
*   64 ビット コンピューター \( \#13 \) に 32 ビット[WebView サポートが追加][GithubMicrosoftedgeWebviewfeedbackIssue13]されました。  
*   SDK \( \#14 \) に WebView IDL[を追加][GithubMicrosoftedgeWebviewfeedbackIssue14]しました。  
*   インターフェイス ID オブジェクト `IID\_\*` \( \#12 \)[をサポートする lib を追加][GithubMicrosoftedgeWebviewfeedbackIssue12]しました。  
*   SDK で DLL ファイルのパス、リンク、および自動コピーをNuGet `TARGET` 追加しました。  
*   スクリプトで要求 `window.open()` を有効にしました。  
    
## <a name="08149"></a>0.8.149  

[NuGet \|][NuGetGallery0.8.149]Microsoft Edgeバージョン 76.0.149.0。  

開発者プレビューの最初のリリース。  

<!-- Links -->  

[Webview2ConceptsDistribution]: ./concepts/distribution.md "WebView2 を使用したアプリケーションの配布 |Microsoft Docs"  
[Webview2ConceptsDistributionEvergreenDistributionMode]: ./concepts/distribution.md#evergreen-distribution-mode "Evergreen 配布モード - WebView2 を使用したアプリケーションの|Microsoft Docs"  
[Webview2ConceptsDistributionFixedVersionDistributionMode]: ./concepts/distribution.md#fixed-version-distribution-mode "固定バージョン配布モード - WebView2 を使用したアプリケーションの|Microsoft Docs"  
[Webview2ConceptsDistributionUnderstandRuntimeInstaller]: ./concepts/distribution.md#understanding-the-webview2-runtime "WebView2 ランタイムとインストーラーについて理解する - WebView2 を使用したアプリケーションの配布 |Microsoft Docs"  
[Webview2ConceptsEnterpriseGroupPoliciesForWebview2]: ./concepts/enterprise.md#group-policies-for-webview2 "WebView2 のグループ ポリシー - WebView2 アプリケーションの管理 |Microsoft Docs"  
[Webview2ConceptsVersioning]: ./concepts/versioning.md "ブラウザーのバージョンと WebView2 について | Microsoft Docs"  
[Webview2ConceptsVersioningExperimentalApis]: ./concepts/versioning.md#experimental-apis "実験的 API - ブラウザーのバージョンと WebView2 の|Microsoft Docs"  
[Webview2ConceptsVersioningMatchingWebview2RuntimeVersions]: ./concepts/versioning.md#matching-webview2-runtime-versions "一致する WebView2 ランタイム バージョン - WebView2 SDK のバージョンの|Microsoft Docs"  
[Webview2GetStartedWinforms]: ./get-started/winforms.md "フォーム アプリの WebView2 のWindowsを開始|Microsoft Docs"  
[Webview2GetStartedWpf]: ./get-started/wpf.md "WPF サーバーでの WebView2 の|Microsoft Docs"  
[Webview2HowToDebug]: ./how-to/debug.md "WebView2 コントロールを使用して開発するときにデバッグする|Microsoft Docs"  

[Webview2ReferenceWin32Icorewebview2experimental2ViewWebview210865PrereleaseAddDownloadstarting]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental2?view=webview2-1.0.865-prerelease&preserve-view=true#add_downloadstarting  "add_DownloadStarting - インターフェイス ICoreWebView2Experimental2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalenvironment3ViewWebview210865PrereleaseUpdateruntime]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalenvironment3?view=webview2-1.0.865-prerelease&preserve-view=true#updateruntime  "UpdateRuntime - インターフェイス ICoreWebView2ExperimentalEnvironment3 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalframeViewWebview210865PrereleaseAddhostobjecttoscriptwithorigins]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalframe?view=webview2-1.0.865-prerelease&preserve-view=true#addhostobjecttoscriptwithorigins  "AddHostObjectToScriptWithOrigins - interface ICoreWebView2ExperimentalFrame |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalsettings4ViewWebview210865PrereleaseIspinchzoomenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalsettings4?view=webview2-1.0.865-prerelease&preserve-view=true#ispinchzoomenabled  "IsPinchZoomEnabled - インターフェイス ICoreWebView2ExperimentalSettings4 |Microsoft Docs" 

[Webview2ReferenceWin32Icorewebview2experimentalsettingsViewWebview210824GetArebrowseracceleratorkeysenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalsettings2?view=webview2-1.0.824&preserve-view=true#get_arebrowseracceleratorkeysenabled "get_AreBrowserAcceleratorKeyPressed - インターフェイス ICoreWebView2ExperimentalSettings |Microsoft Docs" 

[Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseAddDomcontentloaded]: /microsoft-edge/webview2/reference/win32/icorewebview2_2?view=webview2-1.0.721-prerelease&preserve-view=true#add_domcontentloaded "add_DOMContentLoaded - インターフェイス ICoreWebView2_2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseAddWebresourceresponsereceived]: /microsoft-edge/webview2/reference/win32/icorewebview2_2?view=webview2-1.0.721-prerelease&preserve-view=true#add_webresourceresponsereceived "add_WebResourceResponseReceived - インターフェイス ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseGetEnvironment]: /microsoft-edge/webview2/reference/win32/icorewebview2_2?view=webview2-1.0.721-prerelease&preserve-view=true#get_environment "ICoreWebView2CookieManager |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview23ViewWebview210790PrereleaseSetvirtualhostnametofoldermapping]: /microsoft-edge/webview2/reference/win32/icorewebview2_3?view=webview2-1.0.790-prerelease&preserve-view=true#setvirtualhostnametofoldermapping "SetVirtualHostNameToFolderMapping - インターフェイス ICoreWebView2_3 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview23ViewWebview210790PrereleaseTrysuspend]: /microsoft-edge/webview2/reference/win32/icorewebview2_3?view=webview2-1.0.790-prerelease&preserve-view=true#trysuspend "TrySuspend - インターフェイス ICoreWebview2_3 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2acceleratorkeypressedeventargsViewWebview209430GetHandled]: /microsoft-edge/webview2/reference/win32/icorewebview2acceleratorkeypressedeventargs?view=webview2-0.9.430&preserve-view=true#get_handled "get_Handled - インターフェイス ICoreWebView2AcceleratorKeyPressedEventArgs |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2compositioncontrollerViewWebview210790Prerelease]: /microsoft-edge/webview2/reference/win32/icorewebview2compositioncontroller?view=webview2-1.0.790-prerelease&preserve-view=true "インターフェイス ICoreWebView2CompositionController |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2controller2ViewWebview210790PrereleaseGetDefaultbackgroundcolor]: /microsoft-edge/webview2/reference/win32/icorewebview2controller2?view=webview2-1.0.790-prerelease&preserve-view=true#get_defaultbackgroundcolor "get_DefaultBackgroundColor - インターフェイス ICoreWebView2Controller2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2cookiemanagerViewWebview210721Prerelease]: /microsoft-edge/webview2/reference/win32/icorewebview2cookiemanager?view=webview2-1.0.721-prerelease&preserve-view=true "ICoreWebView2CookieManager |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview209430]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-0.9.430&preserve-view=true "インターフェイス ICoreWebView2DevToolsProtocolEventReceiver |Microsoft Docs" 
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
[Webview2ReferenceWin32Icorewebview2experimentalcompositioncontrollerViewWebview209488Prerelease]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller?view=webview2-0.9.488-prerelease&preserve-view=true "インターフェイス ICoreWebView2ExperimentalCompositionController |Microsoft Docs" 
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
[Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseNavigatewithwebresourcerequest]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#navigatewithwebresourcerequest "NavigateWithWebResourceRequest - interface ICoreWebView2Experimental |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalwebresourceresponsereceivedeventargsViewWebview209628PrereleasePopulateresponsecontent]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwebresourceresponsereceivedeventargs?view=webview2-0.9.628-prerelease&preserve-view=true#populateresponsecontent "PopulateResponseContent - インターフェイス ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalwebresourceresponseviewViewWebview210674Prerelease]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwebresourceresponseview?view=webview2-1.0.674-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalWebResourceResponseView |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalwebresourceresponseviewViewWebview210674PrereleaseGetcontent]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwebresourceresponseview?view=webview2-1.0.674-prerelease&preserve-view=true#getcontent "GetContent - インターフェイス ICoreWebView2ExperimentalWebResourceResponseView |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalwindowfeaturesViewWebview209538Prerelease]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwindowfeatures?view=webview2-0.9.538-prerelease&preserve-view=true "インターフェイス ICoreWebView2ExperimentalWindowFeatures |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2hostViewWebview209430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true "インターフェイス ICoreWebView2Host |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2hostViewWebview209430GetZoomfactor]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#get_zoomfactor "get_ZoomFactor - インターフェイス ICoreWebView2Host |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2hostViewWebview209430Notifyparentwindowpositionchanged]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#notifyparentwindowpositionchanged "NotifyParentWindowPositionChanged - インターフェイス ICoreWebView2Host |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2hostViewWebview209430PutZoomfactor]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#put_zoomfactor "put_ZoomFactor - インターフェイス ICoreWebView2Host |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2hostViewWebview209430Setboundsandzoomfactor]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#setboundsandzoomfactor "SetBoundsAndZoomFactor - インターフェイス ICoreWebView2Host |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2httpheaderscollectioniteratorViewWebview209430GetHascurrentheader]: /microsoft-edge/webview2/reference/win32/icorewebview2httpheaderscollectioniterator?view=webview2-0.9.430&preserve-view=true#get_hascurrentheader "get_HasCurrentHeader - インターフェイス ICoreWebView2HttpHeadersCollectionIterator |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2httprequestheadersViewWebview209430Getheaders]: /microsoft-edge/webview2/reference/win32/icorewebview2httprequestheaders?view=webview2-0.9.430&preserve-view=true#getheaders "GetHeaders - インターフェイス ICoreWebView2HttpRequestHeaders |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2httpresponseheadersViewWebview209430Getheader]: /microsoft-edge/webview2/reference/win32/icorewebview2httpresponseheaders?view=webview2-0.9.430&preserve-view=true#getheader "GetHeader - インターフェイス ICoreWebView2HttpResponseHeaders |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2newwindowrequestedeventargsViewWebview209538GetIsuserinitiated]: /microsoft-edge/webview2/reference/win32/icorewebview2newwindowrequestedeventargs?view=webview2-0.9.538&preserve-view=true#get_isuserinitiated "get_IsUserInitiated ICoreWebView2NewWindowRequestedEventArgs |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2newwindowrequestedeventargsViewWebview209622GetWindowfeatures]: /microsoft-edge/webview2/reference/win32/icorewebview2newwindowrequestedeventargs?view=webview2-0.9.622&preserve-view=true#get_windowfeatures "get_WindowFeatures - インターフェイス ICoreWebView2NewWindowRequestedEventArgs |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2settingsViewWebview209430GetAreremoteobjectsallowed]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.430&preserve-view=true#get_areremoteobjectsallowed "get_AreRemoteObjectsAllowed - インターフェイス ICoreWebView2Settings |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2settingsViewWebview209430GetIszoomcontrolenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.430&preserve-view=true#get_iszoomcontrolenabled "get_IsZoomControlEnabled - インターフェイス ICoreWebView2Settings |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2settingsViewWebview209488GetAreremoteobjectsallowed]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.488&preserve-view=true#get_areremoteobjectsallowed "get_AreRemoteObjectsAllowed - インターフェイス ICoreWebView2Settings |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2settingsViewWebview209488GetIsbuiltinerrorpageenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.488&preserve-view=true#get_isbuiltinerrorpageenabled "get_IsBuiltInErrorPageEnabled - インターフェイス ICoreWebView2Settings |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2settingsViewWebview209538GetArehostobjectsallowed]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.538&preserve-view=true#get_arehostobjectsallowed "get_AreHostObjectsAllowed - インターフェイス ICoreWebView2Settings |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true "インターフェイス ICoreWebView2 |Microsoft Docs" 
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
[Webview2ReferenceWin32Icorewebview2windowfeaturesViewWebview209622]: /microsoft-edge/webview2/reference/win32/icorewebview2windowfeatures?view=webview2-0.9.622&preserve-view=true "インターフェイス ICoreWebView2WindowFeatures |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2acceleratorkeypressedeventargsViewWebview208355Handle]: /microsoft-edge/webview2/reference/win32/iwebview2acceleratorkeypressedeventargs?view=webview2-0.8.355&preserve-view=true#handle "Handle - インターフェイス IWebView2AcceleratorKeyPressedEventArgs |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2containsfullscreenelementchangedeventhandlerViewWebview208355]: /microsoft-edge/webview2/reference/win32/iwebview2containsfullscreenelementchangedeventhandler?view=webview2-0.8.355&preserve-view=true "インターフェイス IWebView2ContainsFullScreenElementChangedEventHandler |Microsoft Docs" 
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

[DeployedgeMicrosoftEdgePolicies]: /deployedge/microsoft-edge-policies "Microsoft Edge - ポリシー |Microsoft Docs"  
[DeployedgeMicrosoftEdgeWebviewPolicies]: /deployedge/microsoft-edge-webview-policies "Microsoft EdgeWebView2 - ポリシー|Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2Core]: /dotnet/api/microsoft.web.webview2.core "Microsoft.Web.WebView2.Core 名前空間|Microsoft Docs"  
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
[DotnetApiMicrosoftWebWebview2Winforms]: /dotnet/api/microsoft.web.webview2.winforms "Microsoft.Web.WebView2.WinForms 名前空間|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsCorewebview2creationproperties]: /dotnet/api/microsoft.web.webview2.winforms.corewebview2creationproperties "CoreWebView2CreationProperties クラス (Microsoft.Web.WebView2.Winforms) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2Source]: /dotnet/api/microsoft.web.webview2.winforms.webview2.source "Webview2.Source クラス (Microsoft.Web.WebView2.Winforms) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2Wpf]: /dotnet/api/microsoft.web.webview2.wpf "Microsoft.Web.WebView2.Wpf 名前空間 | Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2Acceleratorkeypressed]: /dotnet/api/microsoft.web.webview2.wpf.webview2.acceleratorkeypressed "microsoft.web.webview2.wpf.webview2.acceleratorkeypressed |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2Buildwindowcore]: /dotnet/api/microsoft.web.webview2.wpf.webview2.buildwindowcore "WebView2.BuildWindowCore(HandleRef) メソッド (Microsoft.Web.WebView2.Wpf) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2Destroywindowcore]: /dotnet/api/microsoft.web.webview2.wpf.webview2.destroywindowcore "WebView2.DestroyWindowCore(HandleRef) メソッド (Microsoft.Web.WebView2.Wpf) |Microsoft Docs"  
[DotnetApiSystemComponentmodelCancelEventargs]: /dotnet/api/system.componentmodel.canceleventargs "CancelEventArgs クラス (System.ComponentModel) |Microsoft Docs"  
[DotnetApiSystemEventargs]: /dotnet/api/system.eventargs "EventArgs クラス (System) |Microsoft Docs"  

[DotnetStandardAssemblyStrongNamed]: /dotnet/standard/assembly/strong-named "名前の強いアセンブリ |Microsoft Docs"  

[WindowsSecurityThreatProtectionMicrosoftDefenderApplicationGuardWindows10]: /windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview "Microsoft Defender Application Guard (Windows 10) - Windows セキュリティ |Microsoft Docs"  
[WindowsWin32ApiWinuserSetWindowDisplayAffinity]: /windows/win32/api/winuser/nf-winuser-setwindowdisplayaffinity "SetWindowDisplayAffinity 関数 (winuser.h) - Win32 アプリの|Microsoft Docs"  

[GithubMicrosoftedgeWebview2AnnouncementIssue2]: https://github.com/MicrosoftEdge/WebView2Announcement/issues/2 "MicrosoftEdge/WebViewAnnouncement の問題 2 のアナウンス レポ"  

[GithubMicrosoftedgeWebview2samplesApisample]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2APISample "WebView2 API サンプル - MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 サンプル-MicrosoftEdge/WebView2Samples | GitHub"  
[GithubMicrosoftedgeWebview2samplesWebview2wpfbrowser]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2WpfBrowser "WebView2WpfBrowser - MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesPr17]: https://github.com/MicrosoftEdge/WebView2Samples/pull/17 "プロジェクトを移動して最新の WebView2 SDK 0.9.430 を使用する - MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftedgeWebviewfeedbackIssue1]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 1"  
[GithubMicrosoftedgeWebviewfeedbackIssue12]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/12 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 12"  
[GithubMicrosoftedgeWebviewfeedbackIssue13]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/13 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 13"  
[GithubMicrosoftedgeWebviewfeedbackIssue14]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/14 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 14"  
[GithubMicrosoftedgeWebviewfeedbackIssue16]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/16 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 16"  
[GithubMicrosoftedgeWebviewfeedbackIssue17]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/17 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 17"  
[GithubMicrosoftedgeWebviewfeedbackIssue18]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/18 "MicrosoftEdge/WebViewFeedback 問題 18 のフィードバック レポ"  
[GithubMicrosoftedgeWebviewfeedbackIssue19]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/19 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 19"  
[GithubMicrosoftedgeWebviewfeedbackIssue22]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/22 "MicrosoftEdge/WebViewFeedback 問題 22 のフィードバック repo"  
[GithubMicrosoftedgeWebviewfeedbackIssue27]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/27 "MicrosoftEdge/WebViewFeedback 問題 27 のフィードバック レポ"  
[GithubMicrosoftedgeWebviewfeedbackIssue28]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/28 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 28"  
[GithubMicrosoftedgeWebviewfeedbackIssue30]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/30 "MicrosoftEdge/WebViewFeedback 問題 30 のフィードバック レポ"  
[GithubMicrosoftedgeWebviewfeedbackIssue32]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/32 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 32"  
[GithubMicrosoftedgeWebviewfeedbackIssue36]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/36 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 36"  
[GithubMicrosoftedgeWebviewfeedbackIssue37]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/37 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 37"  
[GithubMicrosoftedgeWebviewfeedbackIssue57]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/57 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 57"  
[GithubMicrosoftedgeWebviewfeedbackIssue58]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/58 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 58"  
[GithubMicrosoftedgeWebviewfeedbackIssue70]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/70 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 70"  
[GithubMicrosoftedgeWebviewfeedbackIssue74]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/74 "MicrosoftEdge/WebViewFeedback 問題 74 のフィードバック レポ"  
[GithubMicrosoftedgeWebviewfeedbackIssue95]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/95 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 95"  
[GithubMicrosoftedgeWebviewfeedbackIssue108]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/108 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 108"  
[GithubMicrosoftedgeWebviewfeedbackIssue113]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/113 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 113"  
[GithubMicrosoftedgeWebviewfeedbackIssue119]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/119 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 119"  
[GithubMicrosoftedgeWebviewfeedbackIssue122]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/122 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 122"  
[GithubMicrosoftedgeWebviewfeedbackIssue131]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/131 "MicrosoftEdge/WebViewFeedback 問題 131 のフィードバック repo"  
[GithubMicrosoftedgeWebviewfeedbackIssue148]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/148 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 148"  
[GithubMicrosoftedgeWebviewfeedbackIssue161]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/161 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 161"  
[GithubMicrosoftedgeWebviewfeedbackIssue168]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/168 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 168"  
[GithubMicrosoftedgeWebviewfeedbackIssue177]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/177 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 177"  
[GithubMicrosoftedgeWebviewfeedbackIssue179]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/179 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 179"  
[GithubMicrosoftedgeWebviewfeedbackIssue181]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/181 "MicrosoftEdge/WebViewFeedback 問題 181 のフィードバック repo"  
[GithubMicrosoftedgeWebviewfeedbackIssue183]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/183 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 183"  
[GithubMicrosoftedgeWebviewfeedbackIssue185]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/185 "MicrosoftEdge/WebViewFeedback 問題 185 のフィードバック repo"  
[GithubMicrosoftedgeWebviewfeedbackIssue196]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/196 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 196"  
[GithubMicrosoftedgeWebviewfeedbackIssue204]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/204 "MicrosoftEdge/WebViewFeedback 問題 204 のフィードバック repo"  
[GithubMicrosoftedgeWebviewfeedbackIssue205]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/205 "MicrosoftEdge/WebViewFeedback 問題 205 のフィードバック レポ"  
[GithubMicrosoftedgeWebviewfeedbackIssue210]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/210 "MicrosoftEdge/WebViewFeedback 問題 210 のフィードバック repo"  
[GithubMicrosoftedgeWebviewfeedbackIssue212]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/212 "MicrosoftEdge/WebViewFeedback 問題 212 のフィードバック repo"  
[GithubMicrosoftedgeWebviewfeedbackIssue219]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/219 "MicrosoftEdge/WebViewFeedback 問題 219 のフィードバック repo"  
[GithubMicrosoftedgeWebviewfeedbackIssue228]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/228 "MicrosoftEdge/WebViewFeedback 問題 228 のフィードバック repo"  
[GithubMicrosoftedgeWebviewfeedbackIssue235]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/235 "MicrosoftEdge/WebViewFeedback 問題 235 のフィードバック repo"  
[GithubMicrosoftedgeWebviewfeedbackIssue250]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/250 "MicrosoftEdge/WebViewFeedback 問題 250 のフィードバック レポ"  
[GithubMicrosoftedgeWebviewfeedbackIssue275]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/275 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 275"  
[GithubMicrosoftedgeWebviewfeedbackIssue288]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/288 "MicrosoftEdge/WebViewFeedback 問題 288 のフィードバック repo"  
[GithubMicrosoftedgeWebviewfeedbackIssue293]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/293 "MicrosoftEdge/WebViewFeedback 問題 293 のフィードバック repo"  
[GithubMicrosoftedgeWebviewfeedbackIssue318]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/318 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 318"  
[GithubMicrosoftedgeWebviewfeedbackIssue335]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/335 "MicrosoftEdge/WebViewFeedback 問題 335 のフィードバック レポ"  
[GithubMicrosoftedgeWebviewfeedbackIssue371]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/371 "MicrosoftEdge/WebViewFeedback 問題 371 のフィードバック repo"  
[GithubMicrosoftedgeWebviewfeedbackIssue382]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/382 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 382"  
[GithubMicrosoftedgeWebviewfeedbackIssue399]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/399 "MicrosoftEdge/WebViewFeedback 問題 399 のフィードバック repo"  
[GithubMicrosoftedgeWebviewfeedbackIssue400]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/400 "MicrosoftEdge/WebViewFeedback 問題 400 のフィードバック レポ"  
[GithubMicrosoftedgeWebviewfeedbackIssue409]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/409 "MicrosoftEdge/WebViewFeedback 問題 409 のフィードバック レポ"  
[GithubMicrosoftedgeWebviewfeedbackIssue414]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/414 "MicrosoftEdge/WebViewFeedback 問題 414 のフィードバック レポ"  
[GithubMicrosoftedgeWebviewfeedbackIssue431]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/431 "MicrosoftEdge/WebViewFeedback 問題 431 のフィードバック レポ"  
[GithubMicrosoftedgeWebviewfeedbackIssue432]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/432 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 432"  
[GithubMicrosoftedgeWebviewfeedbackIssue442]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/442 "MicrosoftEdge/WebViewFeedback 問題 442 のフィードバック レポ"  
[GithubMicrosoftedgeWebviewfeedbackIssue461]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/461 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 461"  
[GithubMicrosoftedgeWebviewfeedbackIssue506]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/506 "MicrosoftEdge/WebViewFeedback 問題 506 のフィードバック repo"  
[GithubMicrosoftedgeWebviewfeedbackIssue525]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/525 "MicrosoftEdge/WebViewFeedback のフィードバック repo の問題 525"  
[GithubMicrosoftedgeWebviewfeedbackIssue549]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/549 "MicrosoftEdge/WebViewFeedback のフィードバック repo の問題 549"  
[GithubMicrosoftedgeWebviewfeedbackIssue560]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/560 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 560"  
[GithubMicrosoftedgeWebviewfeedbackIssue568]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/568 "MicrosoftEdge/WebViewFeedback のフィードバック repo の問題 568"  
[GithubMicrosoftedgeWebviewfeedbackIssue585]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/585 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 585"  
[GithubMicrosoftedgeWebviewfeedbackIssue604]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/604 "MicrosoftEdge/WebViewFeedback 問題 604 のフィードバック repo"  
[GithubMicrosoftedgeWebviewfeedbackIssue605]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/605 "MicrosoftEdge/WebViewFeedback 問題 605 のフィードバック repo"  
[GithubMicrosoftedgeWebviewfeedbackIssue611]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/611 "MicrosoftEdge/WebViewFeedback 問題 611 のフィードバック repo"  
[GithubMicrosoftedgeWebviewfeedbackIssue669]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/669 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 669"  
[GithubMicrosoftedgeWebviewfeedbackIssue691]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/691 "MicrosoftEdge/WebViewFeedback 問題 691 のフィードバック repo"  
[GithubMicrosoftedgeWebviewfeedbackIssue816]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/816 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 816"  
[GithubMicrosoftedgeWebviewfeedbackIssue851]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/851 "MicrosoftEdge/WebViewFeedback 問題 851 のフィードバック repo"  
[GithubMicrosoftedgeWebviewfeedbackIssue875]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/875 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 875"  
[GithubMicrosoftedgeWebviewfeedbackIssue878]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/878 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 878"  
[GithubMicrosoftedgeWebviewfeedbackIssue1120]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1120 "MicrosoftEdge/WebViewFeedback 問題 1120 のフィードバック repo"
[GithubMicrosoftedgeWebviewfeedbackIssue940]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/940 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 940"
[GithubMicrosoftedgeWebviewfeedbackIssue841]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/841 "MicrosoftEdge/WebViewFeedback 問題 841 のフィードバック レポ"
[GithubMicrosoftedgeWebviewfeedbackIssue210]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/210 "MicrosoftEdge/WebViewFeedback 問題 210 のフィードバック repo"
[GithubMicrosoftedgeWebviewfeedbackIssue338]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/338 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 338"
[GithubMicrosoftedgeWebviewfeedbackIssue589]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/589 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 589"
[GithubMicrosoftedgeWebviewfeedbackIssue933]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/933 "MicrosoftEdge/WebViewFeedback 問題 933 のフィードバック repo"
[GithubMicrosoftedgeWebviewfeedbackIssue946]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/946 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 946"
[GithubMicrosoftedgeWebviewfeedbackIssue1011]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1011 "MicrosoftEdge/WebViewFeedback 問題 1011 のフィードバック レポ"
[GithubMicrosoftedgeWebviewfeedbackIssue1050]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1050 "MicrosoftEdge/WebViewFeedback 問題 1050 のフィードバック レポ"
[GithubMicrosoftedgeWebviewfeedbackIssue996]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/996 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 996"
[GithubMicrosoftedgeWebviewfeedbackIssue850]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/850 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 850"
[GithubMicrosoftedgeWebviewfeedbackIssue1077]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1077 "MicrosoftEdge/WebViewFeedback 問題 1077 のフィードバック repo"
[GithubMicrosoftedgeWebviewfeedbackIssue1099]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1099 "MicrosoftEdge/WebViewFeedback 問題 1099 のフィードバック repo"
[GithubMicrosoftedgeWebviewfeedbackIssue1183]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1183 "MicrosoftEdge/WebViewFeedback 問題 1183 のフィードバック repo"
[GithubMicrosoftedgeWebviewfeedbackIssue1108]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1108 "MicrosoftEdge/WebViewFeedback 問題 1108 のフィードバック repo"
[GithubMicrosoftedgeWebviewfeedbackIssue940]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/940 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 850"
[GithubMicrosoftedgeWebviewfeedbackIssue1079]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1079 "MicrosoftEdge/WebViewFeedback 問題 1079 のフィードバック レポ"
[GithubMicrosoftedgeWebviewfeedbackIssue1013]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1013 "MicrosoftEdge/WebViewFeedback 問題 1013 のフィードバック repo"
[GithubMicrosoftedgeWebviewfeedbackIssue1282]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1282 "MicrosoftEdge/WebViewFeedback 問題 1282 のフィードバック repo"
[GithubMicrosoftedgeWebviewfeedbackIssue828]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/828 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 828"
[GithubMicrosoftedgeWebviewfeedbackIssue619]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/619 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 619"
[GithubMicrosoftedgeWebviewfeedbackIssue608]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/608 "MicrosoftEdge/WebViewFeedback 問題 608 のフィードバック レポ"
[GithubMicrosoftedgeWebviewfeedbackIssue1209]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1209 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 1209"
[GithubMicrosoftedgeWebviewfeedbackIssue448]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/448 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 448"
[GithubMicrosoftedgeWebviewfeedbackIssue1123]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1123 "MicrosoftEdge/WebViewFeedback のフィードバック repo 問題 1123"

[MicrosoftDevblogDotnetAnnouncingGeneralAvailabilityForMicrosoftEdgeWebview2ForNetFixedDistributionMethod]: https://devblogs.microsoft.com/dotnet/announcing-general-availability-for-microsoft-edge-webview2-for-net-and-fixed-distribution-method "WebView2 for .NET および固定配布Microsoft Edge .NET ブログの一般|発表"  

[MicrosoftDeveloperMicrosoftEdgeWebView2]: https://developer.microsoft.com/microsoft-edge/webview2/ "Microsoft EdgeWebView2 |Microsoft Edge開発者"  

[NuGetGallery]: https://www.nuget.org/packages/Microsoft.Web.WebView2 "NuGetギャラリー |Microsoft.Web.WebView2"  
[NuGetGallery0.8.149]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.149 "NuGetギャラリー |Microsoft.Web.WebView2 v0.8.149"  
[NuGetGallery0.8.190]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.190 "NuGetギャラリー |Microsoft.Web.WebView2 v0.8.190"  
[NuGetGallery0.8.230]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.230 "NuGetギャラリー |Microsoft.Web.WebView2 v0.8.230"  
[NuGetGallery0.8.270]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.270 "NuGetギャラリー |Microsoft.Web.WebView2 v0.8.270"  
[NuGetGallery0.8.314]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.314 "NuGetギャラリー |Microsoft.Web.WebView2 v0.8.314"  
[NuGetGallery0.8.355]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.355 "NuGetギャラリー |Microsoft.Web.WebView2 v0.8.355"  
[NuGetGallery0.9.430]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.430 "NuGetギャラリー |Microsoft.Web.WebView2 v0.9.430"  
[NuGetGallery0.9.488]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.488 "NuGetギャラリー |Microsoft.Web.WebView2 v0.9.488"  
[NuGetGallery0.9.515-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.515-prerelease "NuGetギャラリー |Microsoft.Web.WebView2 v0.9.515 プレリリース"  
[NuGetGallery0.9.538]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.538 "NuGetギャラリー |Microsoft.Web.WebView2 v0.9.538"  
[NuGetGallery0.9.579]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.579 "NuGetギャラリー |Microsoft.Web.WebView2 v0.9.579"  
[NuGetGallery0.9.622.11]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.622.11 "NuGetギャラリー |Microsoft.Web.WebView2 v0.9.622.11"  
[NuGetGallery0.9.628-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.628-prerelease "NuGetギャラリー |Microsoft.Web.WebView2 v0.9.628 プレリリース"  
[NuGetGallery1.0.622.22]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.622.22 "NuGetギャラリー |Microsoft.Web.WebView2 v1.0.622.22"  
[NuGetGallery1.0.664.34]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.664.34 "NuGetギャラリー |Microsoft.Web.WebView2 v1.0.664.34"  
[NuGetGallery1.0.664.37]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.664.37 "NuGetギャラリー |Microsoft.Web.WebView2 v1.0.664.37"  
[NuGetGallery1.0.674-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.674-prerelease "NuGetギャラリー |Microsoft.Web.WebView2 v1.0.674 プレリリース"  
[NuGetGallery1.0.705.50]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.705.50 "NuGetギャラリー |Microsoft.Web.WebView2 v1.0.705.50"  
[NuGetGallery1.0.721-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.721-prerelease "NuGetギャラリー |Microsoft.Web.WebView2 v1.0.721 プレリリース"  
[NuGetGallery1.0.774.44]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.774.44 "NuGetギャラリー |Microsoft.Web.WebView2 v1.0.774.44"  
[NuGetGallery1.0.790-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.790-prerelease "NuGetギャラリー |Microsoft.Web.WebView2 v1.0.790 プレリリース"  
[NuGetGallery1.0.818.41]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.818.41 "NuGetギャラリー |Microsoft.Web.WebView2 v1.0.818.41"  
[NuGetGallery1.0.864.35]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.864.35 "NuGetギャラリー |Microsoft.Web.WebView2 v1.0.864.35"  
[NuGetGallery1.0.824-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.824-prerelease "NuGetギャラリー |Microsoft.Web.WebView2 v1.0.824 プレリリース"  
[NuGetGallery1.0.865-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.865-prerelease "NuGetギャラリー |Microsoft.Web.WebView2 v1.0.865 プレリリース"  
[NuGetGallery1.0.902-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.902-prerelease "NuGetギャラリー |Microsoft.Web.WebView2 v1.0.902 プレリリース"  

[WindowsBlogsMsedgedevEdgeWebview2GeneralAvailability]: https://blogs.windows.com/msedgedev/edge-webview2-general-availability "WebView2 Microsoft Edge可用性に関する|Microsoft Edgeブログ"  
[Webview2ReferenceWin32Icorewebview2experimentalsettings5ViewWebview210902PrereleaseGetIsswipenavigationenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalsettings5?view=webview2-1.0.902-prerelease&preserve-view=true#get_isswipenavigationenabled "get_IsSwipeNavigationEnabled - インターフェイス ICoreWebView2ExperimentalSettings5 |Microsoft Docs"
[Webview2ReferenceWin32Icorewebview2experimentalenvironment4ViewWebview210902PrereleaseAddBrowserprocessexited]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalenvironment4?view=webview2-1.0.902-prerelease&preserve-view=true#add_browserprocessexited "add_BrowserProcessExited - インターフェイス ICoreWebView2ExperimentalEnvironment4 |Microsoft Docs"
[Webview2ReferenceWin32Icorewebview2experimental3ViewWebview210902PrereleaseAddClientcertificaterequested]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental3?view=webview2-1.0.902-prerelease&preserve-view=true#add_clientcertificaterequested "add_ClientCertificateRequested - インターフェイス ICoreWebView2Experimental3 |Microsoft Docs"


[Webview2ReferenceWin32Icorewebview24ViewWebview210902PrereleaseAddDownloadstarting]: /microsoft-edge/webview2/reference/win32/icorewebview2_4?view=webview2-1.0.902-prerelease&preserve-view=true#add_downloadstarting "add_DownloadStarting - インターフェイス ICoreWebView2_4 |Microsoft Docs"
[Webview2ReferenceWin32Icorewebview24ViewWebview210902PrereleaseAddFramecreated]: /microsoft-edge/webview2/reference/win32/icorewebview2_4?view=webview2-1.0.902-prerelease&preserve-view=true#add_framecreated "add_FrameCreated - インターフェイス ICoreWebView2_4 |Microsoft Docs"
[Webview2ReferenceWin32Icorewebview2setting4ViewWebview210902PrereleaseGetIsgeneralautofillenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2settings4?view=webview2-1.0.902-prerelease&preserve-view=true#get_isgeneralautofillenabled "get_IsGeneralAutofillEnabled - インターフェイス ICoreWebView2Settings4 |Microsoft Docs"
[Webview2ReferenceWin32Icorewebview2setting5ViewWebview210902PrereleaseGetIspinchzoomenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2settings5?view=webview2-1.0.902-prerelease&preserve-view=true#get_ispinchzoomenabled "get_IsPinchZoomEnabled - インターフェイス ICoreWebView2Settings5 |Microsoft Docs"

[Webview2ReferenceWin32Icorewebview2environmentoptionsGetAllowsinglesignonusingosprimaryaccount]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions#get_allowsinglesignonusingosprimaryaccount "get_AllowSingleSignOnUsingOSPrimaryAccount - インターフェイス ICoreWebView2EnvironmentOptions |Microsoft Docs"
[Webview2ReferenceWin32Icorewebview2setting2ViewWebview21086435GetUseragent]: /microsoft-edge/webview2/reference/win32/icorewebview2settings2?view=webview2-1.0.864.35&preserve-view=true#get_useragent 

/microsoft-edge/webview2/reference/win32/icorewebview2settings2?view=webview2-1.0.864.35&preserve-view=true#get_useragent 

"get_UserAgent - インターフェイス ICoreWebView2Setting2 |Microsoft Docs"
[Webview2ReferenceWin32Icorewebview2setting2ViewWebview21086435GetArebrowseracceleratorkeysenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2settings3?view=webview2-1.0.864.35&preserve-view=true#get_arebrowseracceleratorkeysenabled "get_AreBrowserAcceleratorKeysEnabled - インターフェイス ICoreWebView2Settings3 |Microsoft Docs"
