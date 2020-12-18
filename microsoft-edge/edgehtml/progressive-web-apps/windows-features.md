---
description: ネイティブ アプリ機能を使用して Windows 用 PWA を段階的に強化する
title: Windows 用に PWA (EdgeHTML) を調整する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: 段階的な Web アプリ、PWA、Edge、Windows、WinRT、UWP、EdgeHTML
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 59612d8292d4c4d4d7073b843386364d1ac55c5d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11234766"
---
# Windows 用に PWA (EdgeHTML) を調整する  

Windows 10 にインストールされている[][PwaIndexWindows10]PAS には、ユニバーサル[Windows プラットフォーム \(UWP\)][WindowsUWPGetStartedGuide]アプリとして実行する利点があります。たとえば、Windows アプリのサンドボックス セキュリティによる保護や[、Windows ランタイム \(WinRT\))][UwpApiIndex] API へのフル アクセスなど、次の機能を含むすべての利点があります。  

*   デバイス機能の制御 \(カメラ、マイク、GPS\)  
*   ユーザー リソース \(予定表、連絡先、ドキュメント、音楽など) へのアクセス  
*   Cortana 音声コマンドによるアプリの起動/ナビゲーション  
*   Windows OS との統合 \(Windows アクション センター、デスクトップ タスク バー、コンテキスト メニュー\)  
    
これらは、Windows 上の PWA \(EdgeHTML\) 用に追加された可能性の一部に限定されます。  

この記事では、クロスブラウザーとクロスプラットフォームの互換性を維持しながら、Windows 10 アプリとして PWA \(EdgeHTML\) をインストール、実行、拡張する方法について説明します。  

> [!IMPORTANT]
> この記事の例と手順では、2017 Visual Studio必要です。 Visual Studio 2019 には、この記事で使用されるテンプレートは含めではありません。 2017 Visual Studioダウンロードするには、「Visual Studio [Downloads - 2017, 2015 & Previous Versions」を参照してください][PreviousVSDownloads]。  


## 前提条件  

*   既存の PWA \(またはホストされた Web アプリ\)、ライブ サイトまたは localhost サイト。  このガイドでは、段階的な Web アプリの使用を開始するサンプル PWA [を使用します][PwaGetStarted]。  
*   コミュニティ [2017][MicrosoftVisualStudio|::ref1::|]の \(free\) Visual Studioダウンロードします。  Professional エディション、Enterprise エディション、または Preview エディション [を使用][MicrosoftVisualStudioPreview] できます。  新しいVisual Studioから、次のワークロードを選択します。  
    *   **ユニバーサル Windows プラットフォーム開発**  
        
## ユニバーサル Windows アプリをセットアップして実行する  

Windows 10 アプリとしてインストールされた PWA \(EdgeHTML\) は、ブラウザーとは別に、スタンドアロン \( `WWAHost.exe` プロセス\) ウィンドウで実行されます。  これを有効にする場合は、ホストされた Web アプリを含む軽量なアプリ ラッパーが必要です。このラッパーを使用すると、プロジェクト テンプレートを使用してすばやくVisual Studio `Progressive Web App (Universal Windows)` できます。  \(ネイティブの Windows ランタイム API 要求の送信を含むすべてのアプリ ロジックは、元の Web アプリ コードで引き続き実行されます。\)  

Windows アプリの開発環境を Visual Studio。  

1.  Windows の設定で、開発者モードを [有効にします][WindowsUWPGetStartedEnable]。  \(Windows `developer mode` 検索バーを入力して検索します。\)  
1.  新しいVisual Studioを起動し、[ **新しいプロジェクトの作成] を選択します**。  
1.  **Javascript Windows ユニバーサル**  >  **を選択し**、Visual Studio 2017 のプロジェクトの種類の一覧から [段階的な Web アプリ (ユニバーサル**Windows)** ] を選択します。  
1.  既定の Windows 10 `Target version` \(最新リリース\) と `Minimum version` \(ビルド 10586 以上\) を選択し **、[OK]** を選択します。  
    
    ![Visual Studio UWP プロジェクト ターゲット ビルドの選択ダイアログ](media/vs-target-min-version.png)  
    
    新しいプロジェクトが読み込まれると、package.appxmanifest デザイナーが開きます。  ここで、パッケージ ID、パッケージの依存関係、必要な機能、ビジュアル要素、拡張性ポイントなど、アプリの詳細を構成します。  これは、アプリ開発時に使用されるアプリ パッケージ マニフェストの簡単に構成可能な一時的なバージョンです。  
    アプリ プロジェクトをビルドすると、Visual Studioこのメタデータから [AppxManifest.xml][UwpSchemasAppxpackageUapmanifestschemaGeneratePackageManifest] ファイルが生成されます。このファイルは、アプリのインストールと実行に使用されます。  ファイルを更新する場合は常に、プロジェクトをリビルドして、実行時に両方 `package.appxmanifest` が反映されます `AppxManifest.xml` 。  
    
1.  マニフェスト デザイナーの **アプリケーション パネル** で、PWA の URL を次のように入力します `Start page` 。
    
    > [!NOTE]
    > サービス ワーカーは、次のように指定された https \(secure, remote\) URL すべてでサポートされています `StartPage` 。  サービス ワーカーは、既定では、ローカルのスタート ページを指定する Web アプリではサポートされていません。  これらのケースでサービス ワーカー サポートを有効にするには、マニフェストに明示的な [ApplicationContentUriRules](#set-application-content-uri-rules-acurs) エントリを追加します。次に例を示します。 `<uap:Rule Match="http://web-platform.test/" Type="include" uap5:ServiceWorker="true"/>`  
    
    ![package.appxmanifest デザイナーのアプリケーション パネル](media/vs-manifest-application.png)  
    
    また、必要に応じて `Display name` `Description` 変更できます。  
1.  このファイル \(または選択した別の 512x512 イメージ\) をデスクトップに保存します。  
    次に、マニフェスト デザイナーの **[ビジュアル 資産**] パネルで、フィールド ... ボタンをクリックし、ソース ファイルとして選択し、[生成] `Source` をクリック**します**。 ****  **\([OK] をクリック**して既定のプレースホルダーイメージを上書きします\)。  
    
    ![package.appxmanifest デザイナーのビジュアル アセット パネル](media/vs-manifest-visual-assets.png)  
    
    これにより、ストアにアプリをインストール、実行、起動、配布するための基本的なビジュアル アセットが生成されます。  
    画像が見つからないことを示す赤い \( \) エラーが表示された場合は、... ボタンをクリックして、生成されたイメージからファイルを手動で選択 `X` できます。 ****  
1.  マニフェスト デザイナーの**コンテンツ URI パネル**で `http://example.com` 、PWA \(および \) の場所に `Rule`  =  `include` 置き `WinRT Access`  =  `All` 換えます。  
    これにより、Windows 10 アプリとして実行するときにネイティブの Windows ランタイム \(WinRT\) API 要求を送信するための PWA アクセス許可が付与されます。この API 要求については、少し後で説明します。   実際の PWA が WinRT アクセスを必要としない場合は、値を次の値に `WinRT Access` 切り替えます `None` 。  どちらの場合も、PWA の URI を使用して既定の文字列をサブアウトするか、アプリが実行時に適切に読み込 `http://example.com` めません。  
    PWA を Windows 10 アプリとして実行してデバッグする準備が整いました。  このガイドの手順を実行するために localhost サイトを使用している場合は、それが実行されている必要があります。  そうしたら  
1.  PWA プロジェクト `Ctrl` + `Shift` + `F5` を \( \) ビルド `F5` して \( \) 実行します。  これで、スタンドアロンのアプリ ウィンドウで Web サイトが起動する必要があります。  ホストされた Web アプリであるだけでなく、Windows 10 にインストールされている段階的な Web アプリとして実行されています。  
    
    ![新しいウィンドウで実行WWAHost.exe PWA](media/wwahost.png)  
    
## PWA \(EdgeHTML\) を Windows アプリとしてデバッグする  

PWA \(EdgeHTML\) は単純に段階的に拡張されたホストされた Web アプリなので、通常の IDE とワークフローを使用して、任意の Web アプリと同じサーバー側コードをデバッグできます。  ライブで展開した変更は、次回起動した PWA に反映されます (ユニバーサル Windows アプリ パッケージを再展開する必要はありません)。

Windows 10 アプリ内でのクライアント側デバッグには、アプリが必要 `Microsoft Edge DevTools Preview` です。  このスタンドアロン アプリには、元のブラウザー内の Microsoft [Edge DevTools][DevToolsGuide] [][DevToolsGuideMicrosoftStoreApp] [][DevToolsProtocol01ClientsEdgePreview] [\(PWA][DevToolsGuideServiceWorkers]ツール \ を含む) のすべての機能に加えて、基本的なリモート デバッグ サポートと、EdgeHTML エンジンの実行中のインスタンスにアタッチするためのデバッグ ターゲットの選択 (Office、Cortana、アプリ Web ビュー、Windows で実行される PWA など) が含まれています。  

PWA \(EdgeHTML\) のデバッグを設定する方法を次に示します。  

1.  Microsoft [Store から Microsoft Edge DevTools Preview][MicrosoftStoreEdgeDevtoolsPreview] アプリをまだインストールしていない場合はインストールします。  
1.  PWA サイトを起動して実行した状態で、DevTools アプリを起動します。  
1.  次Visual Studio、( ) コマンドを使って Windows 10 アプリ `Start Without Debugging` `Ctrl` + `F5` を起動します。  \(デバッガーがアクティブな場合、DevTools Visual Studioが正しくアタッチされません。\)  
1.  DevTools アプリで、[ローカル**** デバッグ ターゲットの選択] の [更新] ボタンをクリックします。  これで、PWA \(EdgeHTML\) サイトが一覧表示されます。  \(ブラウザー ウィンドウでも実行されている場合は、リスト内のそのサイトの最後のインスタンスです。\)  
1.  PWA \(EdgeHTML\) サイト一覧をクリックして、新しい DevTools インスタンス タブを開き、デバッグを開始します。  
    
    ![Microsoft Edge DevTools アプリのローカル デバッグ ターゲットの選択](media/devtools-local.png)  
    
1.  DevTools が PWA で実行されている Windows アプリとしてアタッチされているのを確認できます。  DevTools コンソールで **、次のコマンド**を入力します。  
    
    ```shell
    window.Windows
    ```  
    
    これにより、すべてのトップ レベル WinRT 名前空間を含む `Windows Runtime` [グローバル オブジェクトが返されます](#find-windows-runtime-winrt-apis)。  これは、ユニバーサル [Windows][WindowsUWPIndex]プラットフォームへの PWA \(EdgeHTML\) エントリポイントであり、Windows 10 アプリとして実行される Web アプリ (ブラウザーの外部で実行中のプロセス) にのみ公開されます `WWAHost.exe` 。  
    
## Windows ランタイム (WinRT) API の検索  

インストールされている Windows アプリとして [、PWA \(EdgeHTML\)][WindowsRuntime]はネイティブの Windows ランタイム API にフル アクセスできます。使用する必要のある情報を特定し、必要なアクセス許可を取得し、機能検出を使用して、サポートされている環境で API 要求を送信します。  このプロセスを実行して、PWA の Windows デスクトップ ユーザー向け段階的な拡張機能を追加します。  

Windows PWA に必要なユニバーサル Windows プラットフォーム API を特定するには、包括的な [Windows デベロッパー センターでの UWP ドキュメント][uwp/api/] の検索、Visual Studio を使った [UWP](#uwp-code-samples) コード サンプルのダウンロードと実行、Windows 上の PWA の一般的なタスクのコード スニペットの参照など、さまざまな方法があります。

Windows PWA に必要なユニバーサル Windows プラットフォーム API を特定する方法は多数あります。たとえば、包括的な [Windows デベロッパー センターでの UWP ドキュメント][uwp/api/] の検索、Visual Studio を使った [UWP](#uwp-code-samples) コード サンプルのダウンロードと実行 [、Windows 10 (EdgeHTML)][PwaIndexWindows10]での PWA の一般的なタスクのコード スニペットの参照などです。  

全体として、WinRT API は C# の場合と同じように JavaScript で動作します。そのため、一般的なユニバーサル [Windows][WindowsUWPIndex] プラットフォームのドキュメントと [API][UwpApiIndex] リファレンスに従って使用できます。  ただし、次の相違点に注意してください。  

*   JavaScript の WinRT 機能では、異  [なる大文字と小文字の規則が使用されます。][ScriptingJsinrtUsingWinRTCasingConventions]  
*   [イベントは、クラス メソッドに渡される][ScriptingJsinrtHandlingWinRTEvents]文字列識別子として `addEventListener` / `removeEventListener` 表されます。  
*   [非同期メソッドで][ScriptingJsinrtUsingWinRT] JavaScript Promise モデルを使用する  
*   名前空間内の API は、代わりに EdgeHTML エンジン Web レンダリング スタック `Windows.UI.Xaml` \(HTML, CSS\) を使用する JavaScript アプリではサポートされていません。 [][DevGuideWhatsNew]  
    
詳しくは [、JavaScript での Windows ランタイムの使用に関するページをご覧ください][WindowRuntimeUsingJavascript]。  

### UWP コード サンプル  

ユニバーサル [Windows プラットフォーム \(UWP\)][MicrosoftDeveloperWindowsSamples] コード サンプル のレポを参照して、Windows 10 アプリの一般的なシナリオの JavaScript の例を参照してください。  これらのサンプルの JS バージョンは [WinJS][GithubWinjsWinjs] ライブラリを使用してサンプル テンプレートを構造化しますが、これらのサンプルで示されている WinRT API 要求を送信するために WinJS は必要ありません。  

> [!NOTE]
> アプリのイベントをリッスンする必要がある場合は、次のネイティブ WinRT API を使用 [`activated`][UwpApiWindowsUiWebuiWebapplicationActivated] してこれを行います。  
> 
> **使用する**  
> 
> ```javascript
> Windows.UI.WebUI.WebUIApplication.addEventListener("activated", function (activatedEventArgs) {
>     // Check activatedEventArgs.kind and respond as needed
> });
> ```  
> 
> ...サンプルで使用される WinJS 要求とは対照的に、次の種類の WinJS 要求です。  
> 
> **不適切な例**  
> 
> ```javascript
>     var page = WinJS.UI.Pages.define("/html/scenario1-launched.html", {
>         ready: function (element, options) {
>             // Check options.activationKind and respond as needed
>         }
>     });
> ```  

## PWA (EdgeHTML) から WinRT API 要求を送信する  

この時点で、PWA \(EdgeHTML\) の Windows ユーザー向けカスタム コンテキスト メニューを追加し [、Windows.UI.Popups][UwpApiWindowsUiPopups] 名前空間で必要な API を特定したとします。  

PWA \(EdgeHTML\) から WinRT API 要求を送信するには、まず、Windows アプリ パッケージ マニフェスト \( \) ファイルに必要なアクセス許可[\(](#set-application-content-uri-rules-acurs)または、アプリケーション コンテンツ URI 規則\) を確立する必要があります。 `.appxmanifest`  

これらの API 要求の中に、画像や音楽のようなユーザー リソースへのアクセスや、カメラやマイクのようなデバイス機能へのアクセスが含まれる場合[](#app-capability-declarations)は、Windows がユーザーにアクセス許可を求めるメッセージを表示するために、アプリ機能の宣言をアプリ パッケージ マニフェストに追加する必要があります。  後で PWA \(EdgeHTML\) を Microsoft Store に[][MicrosoftSupportWindowsAppPermissions]公開する場合、必要なアプリのアクセス許可もストア登録情報に表示されます。  

#### アプリケーション コンテンツ URI ルール (ACURs) を設定する  

ACUR (URL 許可一覧とも呼ばれる) を使用すると、PWA \(EdgeHTML\) の URL を Windows ランタイム API に直接アクセスできます。  Windows OS レベルでは、Web サーバーでホストされているコードがプラットフォーム API 要求を直接送信できる適切なポリシー境界が設定されています。  PWA URL を次のように指定する場合は、アプリ パッケージ マニフェスト ファイルでこれらの境界を定義します `ApplicationContentUriRules` 。  

規則には、アプリの開始ページと、アプリ ページとして含めるその他のページを含める必要があります。  ユーザーがルールに含まれていない URL に移動すると、Windows はスタンドアロンの PWA \(EdgeHTML\) ウィンドウ \( process\) ではなく、Microsoft Edge ブラウザーでターゲット URL を開きます。 `WWAHost.exe`  特定の URL を除外する場合があります。  

ルールで URL を指定するには `Match` 、いくつかの方法があります。  

*   完全なホスト名  
*   任意のサブドメインを指定した URI を含むホスト名、またはサブドメインを指定した URI を除外したホスト名  
*   完全な URI  
*   クエリ プロパティを含む正確な URI  
*   対象に含めるルールの場合は、部分的なパスと、特定のファイル拡張子を示すワイルドカード  
*   対象から除外する規則の場合は、相対パス  
    
ファイル内の ACURs の例を次に示 `.appxmanifest` します。  

```xml
<Application
Id="App"
StartPage="https://contoso.com/home">
<uap:ApplicationContentUriRules>
    <uap:Rule Type="include" Match="https://contoso.com/" WindowsRuntimeAccess="all" />
    <uap:Rule Type="include" Match="https://*.contoso.com/" WindowsRuntimeAccess="all" />
    <uap:Rule Type="exclude" Match="https://contoso.com/excludethispage.aspx" />
</uap:ApplicationContentUriRules>
```  

アプリの ACUR 内で定義された URL は、次の値を受け入れる属性を通じて Windows ランタイムへのアクセス許可 `WindowsRuntimeAccess` を付与できます。  

*   `all`: リモート JavaScript コードは、すべての WinRT API と任意のローカル パッケージ コンポーネントにアクセスできます。  [Windows \(WinRT\))][UwpApiIndex]名前空間が挿入され、スクリプト エンジンに存在します。  
*   `allowForWeb`: リモート JavaScript コード アクセスは、カスタム C++/C# コンポーネントを含むローカル パッケージ コンポーネントに限定されます。  
*   `none`: 既定値です。  指定された URL はプラットフォームにアクセスできません。  
    
このチュートリアルでは、シングルページ アプリに必要な唯一の ACUR (前の[](#set-up-and-run-your-universal-windows-app)[アプリのセットアップと実行] セクションの手順 6)を既に設定しています。  この確認は、アプリケーション デザイナーの **[コンテンツ URI]** Visual Studio `package.appxmanifest` できます。  

![appxmanifest デザイナー Visual Studio URI パネル](media/vs-appxmanifest-editor-acurs.png)  

また、ソリューション エクスプローラーでファイルを右クリックし、[コードの表示] \( \) を選択Visual Studioマニフェストの生の XML を表示 `package.appxmanifest` **** `F7` することもできます。  デザイナー ビューに戻る場合は、ビュー**デザイナー** \( `Shift` + `F7` \) を選択します。  

#### アプリ機能の宣言  

アプリで、画像や音楽などのユーザー リソースや、カメラやマイクなどのデバイスへのプログラムによるアクセスが必要な場合は、対応するアプリ[][WindowsUwpPackagingAppCapabilities]機能の宣言をアプリ パッケージ マニフェスト ファイルに含める必要があります。  アプリ機能の宣言には次の 3 つのカテゴリがあります。  

*   ストア アプリのほとんどのシナリオに適用される[一般的な用途の機能][WindowsUwpPackagingAppCapabilitiesGeneralUse]。  
*   アプリが周辺機器と内部デバイスにアクセスできるようにする[デバイス機能][WindowsUwpPackagingAppCapabilitiesDevice]。  
*   [エンタープライズ シナリオをサポートし、Microsoft][WindowsUwpPackagingAppCapabilitiesSpecialRestricted] Store の会社アカウントを必要とする特殊な使用機能。  会社のアカウントについて詳しくは、「[アカウントの種類、場所、料金][WindowsUwpPublishAccountTypesLocationsFees]」をご覧ください。
    
Microsoft Store アプリ ページには、アプリ パッケージ マニフェストで宣言する機能すべてが一覧表示されます。そのため、アプリが実際に使用する機能のみを指定してください。

一部の機能は、機密性の高いリソースへのアクセスをアプリに提供します。  これらのリソースは、各リソースがユーザーの個人データにアクセスしたり、ユーザーにコストがかかるため、機密性の高いリソースと見なされます。  Windows 10 設定アプリによって管理される[][BingResultsWindows10Settings]プライバシー設定により、ユーザーは機密性の高いリソースへのアクセスを動的に制御できます。  したがって、機密性の高いリソースが常に利用可能とアプリで想定されていないことが重要です。  機密性の高いリソースへのアクセスについて詳しくは、「[個人データにアクセスするアプリのガイドライン][WindowsUwpSecurityIndex]」をご覧ください。  

アクセスを要求するには、アプリのパッケージ マニフェストで機能を宣言します。  このVisual Studio、package.appxmanifest デザイナーの **[** 機能] パネルから実行できます。  

![appxmanifest デザイナー Visual Studio機能パネル](media/vs-appxmanifest-editor-capabilities.png)  

このチュートリアルでは、既定の Internet \(Client\) 機能だけが必要なので、それ以上の操作は必要ありません。  

### 機能検出を使用して WinRT を呼び出す  

すべてのプラットフォームで PWA 対象ユーザーの品質基準エクスペリエンスを確保するには、WinRT 機能検出を使用して Windows での PWA エクスペリエンスを段階的に強化します。  これにより、Windows 固有のコードが WinRT API が利用可能で適用可能なコンテキストでのみ実行されるのを確認できます。  

機能の検出は、次のようにオブジェクト \(WinRT 名前空間 \へのエントリ ポイント) を探すのと同 `Windows` じほど簡単な場合があります。 [][UwpApiIndex]  

```javascript
if(window.Windows){
    /*Run code that sends Windows API requests */
}
```  

ただし、すべての [Windows 10][UwpExtensionSdkDeviceFamiliesOverview]デバイスの種類ですべての Windows API が利用できるわけではありませんが、通常は、送信する API 要求の名前空間をさらに修飾するために、より具体的な機能検出を使用すると便利です。  

```javascript
if(window.Windows && Windows.Media.SpeechRecognition){
    /*Run code that sends Windows API requests */
}
```  

このバックグラウンドで、カスタム コンテキスト メニューを実装するための WinRT コードを追加する準備が整いました。  [段階的な Web アプリの使用を開始する] のサンプル PWA [を使用している場合][PwaGetStarted]:

1.  PWA Visual Studioプロジェクトを開きます。  
1.  ソリューション エクスプローラーでファイルを開き、サービス ワーカーの参照の下に次 `views\layout.pug` `script` の行を追加します。
    
    ```xml
    script(src='/javascripts/site.js')
    ```  
    
1.  ソリューション エクスプローラーで、フォルダーを右クリックし、[ `javascripts` 新しいファイル**の**追加  >  **...] をクリックします**。
1.  ファイルに名前を `site.js` 付け、次のコードでコピーします。
    
    ```javascript
    if (window.Windows && Windows.UI.Popups) {
        document.addEventListener('contextmenu', function (e) {

            // Build the context menu
            var menu = new Windows.UI.Popups.PopupMenu();
            menu.commands.append(new Windows.UI.Popups.UICommand("Option 1", null, 1));
            menu.commands.append(new Windows.UI.Popups.UICommandSeparator);
            menu.commands.append(new Windows.UI.Popups.UICommand("Option 2", null, 2));

            // Convert from webpage to WinRT coordinates
            function pageToWinRT(pageX, pageY) {
                var zoomFactor = document.documentElement.msContentZoomFactor;
                return {
                    x: (pageX - window.pageXOffset) * zoomFactor,
                    y: (pageY - window.pageYOffset) * zoomFactor
                };
            }

            // When the menu is invoked, execute the requested command
            menu.showAsync(pageToWinRT(e.pageX, e.pageY)).done(function (invokedCommand) {
                if (invokedCommand !== null) {
                    switch (invokedCommand.id) {
                        case 1:
                            console.log('Option 1 selected');
                            // Invoke code for option 1
                            break;
                        case 2:
                            console.log('Option 2 selected');
                            // Invoke code for option 2
                            break;
                        default:
                            break;
                    }
                } else {
                    // The command is null if no command was invoked.
                    console.log("Context menu dismissed");
                }
            });
        }, false);
    }
    ```
    
1.  PWA をブラウザー \( PWA サイト プロジェクト\ から) で実行する場合と Windows アプリ ウィンドウ \( ユニバーサル Windows アプリ プロジェクト\) 内から実行した場合のコンテキスト メニューの動作を比較します `F5` `F5` 。  ブラウザーで右クリックすると Microsoft Edge の既定のコンテキスト メニューが表示され、プロセスではカスタム メニュー `WWAHost.exe` が表示されます。  
    
    | Microsoft Edge | Windows 10 アプリ |  
    |:--- |:---- |  
    | ![ブラウザーの既定のコンテキスト メニュー](media/browser-context-menu.png) | ![アプリのカスタム コンテキスト メニュー](media/app-context-menu.png) |  
    
Windows で PAS を段階的に強化する確固な基盤が提供されたと思います。  質問や不明な点が不明な場合は、コメントを送信してください。  

## 追加情報

[Windows デベロッパー][MicrosoftDeveloperWindowsApps]センターは、Windows アプリの構築のすべての段階 (使い始めから、Microsoft [][MicrosoftDeveloperWindowsAppsDesign]Store[][MicrosoftDeveloperWindowsAppsDevelop]の設計、[][MicrosoftDeveloperStorePublishApps]開発、公開まで) の完全なリファレンスです。 [][MicrosoftDeveloperWindowsAppsGetStarted]  

ユニバーサル Windows プラットフォーム \(UWP\) の概要と、さまざまな Windows 10 デバイス ファミリをターゲットとする方法については、「ユニバーサル Windows プラットフォームの概要」をご覧 [ください][WindowsUWPGetStartedGuide]。  

準備ができたら、Microsoft Store に PWA を提出する方法を次に [示します](./microsoft-store.md)。  

<!-- links -->  

[PwaGetStarted]: ./get-started.md "段階的な Web アプリの概要 |Microsoft Docs"  
[PwaIndexWindows10]: ./index.md#pwas-on-windows-10-edgehtml "Windows 10 の PAS (EdgeHTML) - Windows 上の段階的な Web アプリ |Microsoft Docs"  
[DevToolsGuide]: ../devtools-guide/index.md "Microsoft Edge (EdgeHTML) 開発者ツール |Microsoft Docs"  
[DevToolsGuideMicrosoftStoreApp]: ../devtools-guide/index.md#microsoft-store-app "Microsoft Store アプリ - Microsoft Edge (EdgeHTML) 開発者ツール |Microsoft Docs"  
[DevToolsGuideServiceWorkers]: ../devtools-guide/service-workers.md "サービス ワーカー |Microsoft Docs"  
[DevToolsProtocol01ClientsEdgePreview]: ../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge DevTools Preview - DevTools プロトコル クライアント |Microsoft Docs"  
[DevGuideWhatsNew]: ../dev-guide/whats-new.md "EdgeHTML の新機能 |Microsoft Docs"  
[WindowsRuntime]: ../windows-runtime/index.md "JavaScript 用 Windows ランタイム (WinRT) |Microsoft Docs"  
[WindowRuntimeUsingJavascript]: ../windows-runtime/using-the-windows-runtime-in-javascript.md "JavaScript での Windows ランタイムの使用 |Microsoft Docs"  

[ScriptingJsinrtHandlingWinRTEvents]: /scripting/jswinrt/handling-windows-runtime-events-in-javascript "JavaScript での Windows ランタイム イベントの処理 |Microsoft Docs"  
[ScriptingJsinrtUsingWinRT]: /scripting/jswinrt/using-windows-runtime-asynchronous-methods "Windows ランタイム非同期メソッドの使用 |Microsoft Docs"  
[ScriptingJsinrtUsingWinRTCasingConventions]:  /scripting/jswinrt/using-the-windows-runtime-in-javascript#casing-conventions-with-windows-runtime-features "Windows ランタイム機能での大文字と小文字の区別に関する規則 - JavaScript での Windows ランタイムの使用 |Microsoft Docs"  
[UwpApiIndex]: /uwp/api/index "Windows UWP 名前空間 |Microsoft Docs"  
[UwpApiWindowsUiPopups]: /uwp/api/windows.ui.popups "Windows.UI.Popups 名前空間 |Microsoft Docs"  
[UwpApiWindowsUiWebuiWebapplicationActivated]: /uwp/api/windows.ui.webui.webuiapplication.activated "WebUIApplication.Activated イベント |Microsoft Docs"  
[UwpExtensionSdkDeviceFamiliesOverview]: /uwp/extension-sdks/device-families-overview "デバイス ファミリの概要 |Microsoft Docs"  
[UwpSchemasAppxpackageUapmanifestschemaGeneratePackageManifest]: /uwp/schemas/appxpackage/uapmanifestschema/generate-package-manifest "アプリ Visual Studioマニフェストを生成する方法 |Microsoft Docs"  
[WindowsUWPIndex]: /windows/uwp/index "ユニバーサル Windows プラットフォームのドキュメント |Microsoft Docs"  
[WindowsUWPGetStartedGuide]: /windows/uwp/get-started/universal-application-platform-guide "ユニバーサル Windows プラットフォーム (UWP) アプリとは|Microsoft Docs"  
[WindowsUWPGetStartedEnable]: /windows/uwp/get-started/enable-your-device-for-development "デバイスを開発用に有効にする |Microsoft Docs"  
[WindowsUwpSecurityIndex]: /windows/uwp/security/index "セキュリティ |Microsoft Docs"  
[WindowsUwpPublishAccountTypesLocationsFees]: /windows/uwp/publish/account-types-locations-and-fees "アカウントの種類、場所、料金 |Microsoft Docs"  
[WindowsUwpPackagingAppCapabilitiesSpecialRestricted]: /windows/uwp/packaging/app-capability-declarations#special-and-restricted-capabilities "制限付き機能 |Microsoft Docs"  
[WindowsUwpPackagingAppCapabilitiesDevice]: /windows/uwp/packaging/app-capability-declarations#device-capabilities "デバイスの機能 |Microsoft Docs"  
[WindowsUwpPackagingAppCapabilitiesGeneralUse]: /windows/uwp/packaging/app-capability-declarations#general-use-capabilities "一般的な使用機能 |Microsoft Docs"  
[WindowsUwpPackagingAppCapabilities]: /windows/uwp/packaging/app-capability-declarations "アプリ機能の宣言 |Microsoft Docs"  

[BingResultsWindows10Settings]: https://binged.it/2lOGSH0 "Windows 10 の設定 - Bing"  
[GithubWinjsWinjs]: https://github.com/winjs/winjs "winjs/winjs |GitHub"  
[MicrosoftDeveloperStorePublishApps]: https://developer.microsoft.com/store/publish-apps/index "Windows アプリとゲームの公開"  
[MicrosoftDeveloperWindowsApps]: https://developer.microsoft.com/windows/apps/index "ユニバーサル Windows プラットフォームのドキュメント"  
[MicrosoftDeveloperWindowsAppsDesign]: https://developer.microsoft.com/windows/apps/design/index "Windows アプリの設計とコード作成"  
[MicrosoftDeveloperWindowsAppsDevelop]: https://developer.microsoft.com/windows/apps/develop/index "UWP アプリの開発"  
[MicrosoftDeveloperWindowsAppsGetStarted]: https://developer.microsoft.com/windows/apps/getstarted/index "Windows 10 アプリの使用を開始する"  
[MicrosoftDeveloperWindowsSamples]: https://developer.microsoft.com/windows/samples "コード サンプル"  
[MicrosoftStoreEdgeDevtoolsPreview]: https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj "Microsoft Edge DevTools Preview"  
[MicrosoftSupportWindowsAppPermissions]: https://support.microsoft.com/help/10557/windows-10-app-permissions "アプリのアクセス許可"  
[MicrosoftVisualStudioDownloads]: https://visualstudio.microsoft.com/downloads "ダウンロード"  
[MicrosoftVisualStudioPreview]: https://visualstudio.microsoft.com/vs/preview "Visual Studio プレビュー"  
[PreviousVSDownloads]: https://visualstudio.microsoft.com/vs/older-downloads/ "Visual Studioダウンロード"  
