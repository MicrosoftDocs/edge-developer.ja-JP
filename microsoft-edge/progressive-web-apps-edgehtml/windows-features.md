---
description: ネイティブアプリ機能により、Windows 版の PWA を段階的に強化
title: Windows の PWA (EdgeHTML) をカスタマイズする
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: プログレッシブ web アプリ、PWA、Edge、Windows、WinRT、UWP、EdgeHTML
ms.openlocfilehash: 70a675b1a4057326463fb63c6a93abf8f428c677
ms.sourcegitcommit: 8510fdaa72c8940440133e4c5b36349997d94127
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "10905574"
---
# Windows の PWA (EdgeHTML) をカスタマイズする  

Windows 10 にインストールされた microsoft は、[ユニバーサル Windows プラットフォーム \ (UWP \)][WindowsUWPGetStartedGuide]アプリとして実行することにより、次のようなものも含め、windows アプリのサンドボックスセキュリティと[windows ランタイム \ (WinRT \)][UwpApiIndex] api へのフルアクセスを含む[すべてのメリット][PwaIndexWindows10]を享受できます。  

*   デバイスの機能を制御する (カメラ、マイク、GPS など)  
*   ユーザーリソースにアクセスする (予定表、連絡先、ドキュメント、音楽など)  
*   Cortana の音声コマンドによるアプリの起動と移動  
*   Windows OS との統合 (Windows アクションセンター、デスクトップタスクバー、およびコンテキストメニューを介して)  

これらは、Windows の PWA \ (EdgeHTML \) で追加される可能性のほんの一部にすぎません。  

この記事では、Windows 10 アプリとして PWA \ (EdgeHTML) をインストール、実行、強化する方法について説明します。ただし、クロスブラウザーとクロスプラットフォームの互換性を確保します。  

> [!IMPORTANT]
> この記事の例と手順では、Visual Studio 2017 が必要です。 Visual Studio 2019 には、この記事で使用されているテンプレートは含まれていません。 Visual Studio 2017 をダウンロードするには、「 [Visual studio のダウンロード-2017、2015 & 以前のバージョン][PreviousVSDownloads]」を参照してください。  


## 前提条件  

*   Live または localhost サイトのいずれかである既存の PWA \ (またはホストされた web アプリ)。  このガイドでは、 [「プログレッシブ Web アプリの使用を開始][PwaGetStarted]する」のサンプルの PWA について説明します。  
*   \ (無料版) の[Visual Studio コミュニティ 2017][MicrosoftVisualStudio|::ref1::|]をダウンロードします。  プロフェッショナル、エンタープライズ、または[プレビュー][MicrosoftVisualStudioPreview]の各エディションを使用することもできます。  Visual Studio インストーラーで、次のワークロードを選択します。  
    *   **ユニバーサル Windows プラットフォーム開発**  

## ユニバーサル Windows アプリをセットアップして実行する  

Windows 10 アプリとしてインストールされた PWA \ (EdgeHTML \) は、ブラウザーとは独立して \ ( `WWAHost.exe` プロセス \) ウィンドウで実行されます。  これを有効にするには、ホストされた web アプリを含む軽量のアプリラッパーが必要です。これは、Visual Studio プロジェクトテンプレートを使用してすばやく設定することができ `Progressive Web App (Universal Windows)` ます。  \ (ネイティブの Windows ランタイム API 要求の送信を含むすべてのアプリロジックは、元の web アプリコードでも引き続き発生します)。  

Visual Studio で Windows アプリ開発環境をセットアップします。  

1.  Windows の [設定] で、[開発者モード][WindowsUWPGetStartedEnable]を有効にします。  \ ( `developer mode` Windows searchbar に入力して検索します。 \)  
1.  Visual Studio を起動し、[**新しいプロジェクトの作成**] を選択します。  
1.  [ **Javascript**  >  **Windows universal** ] を選択し、Visual Studio 2017 のプロジェクトの種類の一覧から [**プログレッシブ Web アプリ (ユニバーサル Windows)** ] を選択します。  
1.  既定の Windows 10 `Target version` \ (最新のリリース) と `Minimum version` \ (ビルド10586以降) を選択して、[ **OK]** を選択します。  

    ![UWP プロジェクトターゲットビルドの Visual Studio 選択ダイアログ](media/vs-target-min-version.png)  

    新しいプロジェクトが package.appxmanifest デザイナーを開き、読み込まれます。  ここでは、パッケージ id、パッケージの依存関係、必要な機能、ビジュアル要素、拡張性ポイントなど、アプリの詳細を構成します。  これは、アプリの開発中に使用される、簡単に構成可能な一時バージョンのアプリパッケージマニフェストです。  
    アプリプロジェクトをビルドすると、 [Visual Studio][UwpSchemasAppxpackageUapmanifestschemaGeneratePackageManifest]によって、このメタデータから AppxManifest.xmlファイルが生成されます。これは、アプリをインストールして実行するために使われます。  ファイルを更新するたびに、 `package.appxmanifest` 必ずプロジェクトを再ビルドして、実行時に両方が反映されるようにしてください `AppxManifest.xml` 。  

1.  マニフェストデザイナーの [**アプリケーション**] パネルで、PWA の URL をとして入力し `Start page` ます。

    > [!NOTE]
    > サービスワーカーは、として指定されているすべての https \ (セキュリティで保護されたリモート \) url でサポートされてい `StartPage` ます。  ローカルのスタートページを指定する web アプリでは、サービスワーカーは既定でサポートされていません。  このような場合に service worker のサポートを有効にするには、次のように明示的な[Applicationcontenturirules](#set-application-content-uri-rules-acurs)エントリをマニフェストに追加します。 `<uap:Rule Match="http://web-platform.test/" Type="include" uap5:ServiceWorker="true"/>`  
    
    ![Package.appxmanifest designer のアプリケーションパネル](media/vs-manifest-application.png)  
    
    必要に応じて、を変更することもでき `Display name` `Description` ます。  
1.  このファイルをデスクトップに保存します (または、選択したコンピューターの別の512x512 画像を保存します)。  
    次に、マニフェストデザイナーの**ビジュアルアセット**パネルで、[ `Source` フィールド **...** ] ボタンをクリックし、ソースファイルとして選択し、[**生成**] をクリックします。  \ ([ **OK]** をクリックして、既定のプレースホルダー画像を上書きします)。  
    
    ![Package.appxmanifest designer のビジュアルアセットパネル](media/vs-manifest-visual-assets.png)  
    
    これにより、アプリをインストール、実行、起動、配布するための基本的なビジュアルアセットがストアに生成されます。  
    欠けている `X` 画像を示す赤い \ (\) エラーが表示される場合は、[.. **.** ] ボタンをクリックして、生成された画像からファイルを手動で選ぶことができます。  
1.  マニフェストデザイナーの**コンテンツ uri**パネルで、 `http://example.com` PWA の場所 ( `Rule`  =  `include` と \ など) に置き換え `WinRT Access`  =  `All` ます。  
    これにより、PWA は、Windows 10 アプリとして実行されている場合に、ネイティブ Windows ランタイム \ (WinRT \) API 要求を送信する権限を付与することになります。これは、後で説明します。   実際の PWA が WinRT アクセスを必要としない場合は、値をに切り替えることができ `WinRT Access` `None` ます。  どちらの場合も、既定の文字列を PWA の URI に必ず指定してください `http://example.com` 。または、実行時にアプリが適切に読み込まれないようにしてください。  
    Windows 10 アプリとして PWA を実行してデバッグする準備ができました。  このガイドの手順に localhost サイトを使用している場合は、実行されていることを確認します。  そうしたら  
1.  ビルド \ ( `Ctrl` + `Shift` + `F5` \) を実行し、 `F5` 自分の PWA プロジェクトを \ (\) 実行します。  これで web サイトがスタンドアロンアプリウィンドウで起動します。  ホストされた web アプリだけでなく、Windows 10 にインストールされているプログレッシブ Web アプリとして実行されています。  

    ![WWAHost.exe ウィンドウで実行されている PWA](media/wwahost.png)  

## Windows アプリとして PWA \ (EdgeHTML \) をデバッグする  

PWA \ (EdgeHTML \) は、段階的に強化されたホステッド web アプリであるため、通常の IDE とワークフローを使って、web アプリと同じようにサーバー側のコードをデバッグできます。  展開された変更は、次に起動したときに、インストールされている PWA に反映されます (ユニバーサル Windows アプリパッケージを再展開する必要はありません)。

Windows 10 アプリでクライアント側のデバッグを行うには、アプリが必要 `Microsoft Edge DevTools Preview` です。  このスタンドアロンアプリには、ブラウザーの元の[Microsoft Edge devtools][DevToolsGuide] ( [PWA ツール][DevToolsGuideServiceWorkers]を含む)、基本的な[リモートデバッグ][DevToolsProtocol01ClientsEdgePreview]サポート、および EdgeHTML エンジンの実行中のインスタンスに接続するための[デバッグターゲットのセレクター][DevToolsGuideMicrosoftStoreApp] (Office のアドイン、Cortana、アプリ webviews など) のすべての機能が含まれています。  

ここでは、PWA \ (EdgeHTML) のデバッグをセットアップする方法について説明します。  

1.  まだインストールしていない場合は、microsoft Store から[Microsoft Edge DevTools プレビュー][MicrosoftStoreEdgeDevtoolsPreview]アプリをインストールします。  
1.  PWA サイトを起動して実行している状態で、DevTools アプリを起動します。  
1.  Visual Studio で、() コマンドを使用して Windows 10 アプリを起動し `Start Without Debugging` `Ctrl` + `F5` ます。  \ (Visual Studio デバッガーがアクティブな場合は、DevTools アプリが適切にアタッチされません)。  
1.  DevTools アプリで、ローカルデバッグターゲットの選択の [**更新**] ボタンをクリックします。  これで、PWA \ (EdgeHTML) サイトが一覧表示されます。  \ (ブラウザーウィンドウでも実行されている場合は、リスト内でそのサイトの最後のインスタンスになります)。  
1.  PWA の [\ (EdgeHTML \)] サイトの一覧をクリックして、新しい DevTools インスタンスタブを開き、デバッグを開始します。  
    
    ![Microsoft Edge DevTools アプリでのローカルデバッグターゲットの選択](media/devtools-local.png)  
    
1.  DevTools が Windows アプリの PWA として実行されていることを確認できます。  DevTools**コンソール**で、次のように入力します。  
    
    ```shell
    window.Windows
    ```  
    
    `Windows Runtime`すべての[トップレベルの WinRT 名前空間](#find-windows-runtime-winrt-apis)を含むグローバルオブジェクトを返します。  これは、PWA \ (EdgeHTML \) のエントリポイントであり、[ユニバーサル Windows プラットフォーム][WindowsUWPIndex]を対象としており、windows 10 アプリとして実行される (ブラウザーの外部で実行されている) web アプリにのみ公開され `WWAHost.exe` ます。  
    
## Windows ランタイム (WinRT) Api を見つける  

インストール済みの Windows アプリとして、 [PWA \ (EdgeHTML \) には、ネイティブの Windows ランタイム api へのフルアクセスがあり][WindowsRuntime]ます。使用する必要があるものを特定し、必要なアクセス許可を取得し、機能検出を利用して、サポートされている環境でその API 要求を送信します。  このプロセスに従って、PWA の Windows デスクトップユーザーにプログレッシブエンハンスメントを追加します。  

Windows PWA に必要なユニバーサル Windows プラットフォーム Api を特定する方法はいくつかあります。これには、windows デベロッパーセンターでの包括的な [UWP ドキュメント] の検索、Visual Studio を使った[uwp コードサンプル](#uwp-code-samples)のダウンロードと実行、windows での一般的なタスクのコードスニペットの参照が含まれます。

Windows の PWA に必要なユニバーサル Windows プラットフォーム Api を特定するには、さまざまな方法があります。これには、windows デベロッパーセンターでの包括的な [UWP ドキュメント] の検索、Visual Studio による[uwp コードサンプル](#uwp-code-samples)のダウンロードと実行、一般的なタスクのコードスニペットの参照[(EdgeHTML)][PwaIndexWindows10]が含まれます。  

全体的に、WinRT Api は C# と同じように動作するため、一般的な[ユニバーサル Windows プラットフォームのドキュメント][WindowsUWPIndex]と[API リファレンス][UwpApiIndex]に従って使用できます。  ただし、次の点にご注意ください。  

*   JavaScript の WinRT 機能では、[さまざまな大文字と小文字の規則][ScriptingJsinrtUsingWinRTCasingConventions]が使用される  
*   イベントは、クラスメソッドに渡される[文字列識別子として表され][ScriptingJsinrtHandlingWinRTEvents]ます。 `addEventListener` / `removeEventListener`  
*   [非同期メソッド][ScriptingJsinrtUsingWinRT]は JavaScript Promise モデルを使用します。  
*   `Windows.UI.Xaml`名前空間の api は JavaScript アプリではサポートされません。これは、代わりに[EdgeHTML][DevGuideWhatsNew] engine web レンダリングスタック (HTML, CSS) を使用します。  

詳しくは、「 [JavaScript での Windows ランタイムの使用][WindowRuntimeUsingJavascript]」をご覧ください。  

### UWP コードサンプル  

一般的な Windows 10 アプリのシナリオの JavaScript の例を参照するには、 [「ユニバーサル Windows プラットフォーム \ (UWP \) コードサンプル][MicrosoftDeveloperWindowsSamples]」をご覧ください。  このサンプルの JS バージョンでは、 [WinJS][GithubWinjsWinjs]ライブラリを使ってサンプルテンプレートを構成していますが、このサンプルで示されている WinRT API 要求を送信するために WinJS は必要ありません。  

> [!NOTE]
> アプリのイベントをリッスンする必要がある場合 [`activated`][UwpApiWindowsUiWebuiWebapplicationActivated] は、次のネイティブ WINRT API を使ってこれを行うことができます。  
> 
> **使用するもの**  
> 
> ```javascript
> Windows.UI.WebUI.WebUIApplication.addEventListener("activated", function (activatedEventArgs) {
>     // Check activatedEventArgs.kind and respond as needed
> });
> ```  
> 
> ...この種類の WinJS 要求は、次のように使用されます。  
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

## PWA から WinRT API 要求を送信する (EdgeHTML)  

この時点で、windows ユーザーの PWA 用のカスタムコンテキストメニュー (EdgeHTML \) を追加して、必要な Api を[windows のポップアップ][UwpApiWindowsUiPopups]名前空間で指定します。  

Microsoft の PWA \ (EdgeHTML \) から WinRT Api 要求を送信するには、最初に Windows アプリパッケージマニフェスト \ (\) ファイルに必要な権限 (またはアプリケーションコンテンツ URI 規則) を[設定](#set-application-content-uri-rules-acurs)する必要があり `.appxmanifest` ます。  

これらの API 要求のいずれかで、画像や音楽などのユーザーリソース、またはカメラやマイクなどのデバイス機能へのアクセスが必要な場合は、Windows がユーザーにアクセス許可を求めるために、アプリパッケージマニフェストに[アプリ機能の宣言](#app-capability-declarations)を追加する必要もあります。  後で PWA \ (EdgeHTML \) を Microsoft Store に公開した場合、これらの必要な[アプリのアクセス許可][MicrosoftSupportWindowsAppPermissions]についても、ストア登録情報に記載されています。  

#### アプリケーションコンテンツ URI 規則 (Acur) を設定する  

Acur、つまり URL 許可リストと呼ばれている場合は、PWA \ (EdgeHTML \) の Url を Windows ランタイム Api に直接アクセスできます。  Windows OS レベルでは、web サーバーでホストされているコードがプラットフォーム API 要求を直接送信することを許可するように、適切なポリシーの境界が設定されています。  PWA Url をとして指定するときに、アプリパッケージマニフェストファイルでこれらの境界を定義し `ApplicationContentUriRules` ます。  

ルールには、アプリのスタートページと、アプリページとして含めるその他のページを含める必要があります。  ユーザーが自分のルールに含まれていない URL に移動した場合、Windows は、スタンドアロンの PWA \ (EdgeHTML \) ウィンドウ (プロセス \) ではなく、Microsoft Edge ブラウザーでターゲット URL を開き `WWAHost.exe` ます。  特定の Url を除外することもできます。  

ルールに URL を指定するには、いくつかの方法があり `Match` ます。  

*   完全なホスト名  
*   任意のサブドメインを指定した URI を含むホスト名、またはサブドメインを指定した URI を除外したホスト名  
*   完全な URI  
*   クエリプロパティを含む正確な URI  
*   対象に含めるルールの場合は、部分的なパスと、特定のファイル拡張子を示すワイルドカード  
*   対象から除外する規則の場合は、相対パス  

次に、ファイル内の Acur の例をいくつか示し `.appxmanifest` ます。  

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

アプリの Acur 内で定義されている Url には、属性を通じて Windows ランタイムへのアクセス許可を付与することができ `WindowsRuntimeAccess` ます。この属性は、次の値を受け取ります。  

*   `all`: リモート JavaScript コードは、すべての WinRT Api とローカルのパッケージ化されたコンポーネントにアクセスできます。  [Windows \ (WinRT \))][UwpApiIndex]名前空間が挿入され、スクリプトエンジンに存在します。  
*   `allowForWeb`: リモート JavaScript コードアクセスは、カスタム C++/C # コンポーネントなど、ローカルのパッケージ化されたコンポーネントに制限されています。  
*   `none`設定.  指定された URL はプラットフォームにアクセスできません。  

このチュートリアルでは、1ページのアプリで、必要な ACUR のみを既に設定しています (前のセットアップの手順6と、アプリセクション \[を実行し](#set-up-and-run-your-universal-windows-app)ます)。  これは、Visual Studio designer の**コンテンツ uri**パネルで確認でき `package.appxmanifest` ます。  

![Visual Studio package.appxmanifest designer のコンテンツ URI パネル](media/vs-appxmanifest-editor-acurs.png)  

`package.appxmanifest`Visual Studio ソリューションエクスプローラーでファイルを右クリックして [**コードの表示**] (\) を選択することにより、マニフェストの生の XML を表示することもでき `F7` ます。  デザイナービューに戻るには、[**ビューデザイナー** \ (\)] を選択し `Shift` + `F7` ます。  

#### アプリ機能の宣言  

アプリが、画像や音楽などのユーザーリソース、またはカメラやマイクなどのデバイスにプログラムでアクセスする必要がある場合は、対応する[アプリ機能の宣言][WindowsUwpPackagingAppCapabilities]をアプリパッケージマニフェストファイルに含める必要があります。  アプリ機能の宣言には次の 3 つのカテゴリがあります。  

*   ストア アプリのほとんどのシナリオに適用される[一般的な用途の機能][WindowsUwpPackagingAppCapabilitiesGeneralUse]。  
*   アプリが周辺機器と内部デバイスにアクセスできるようにする[デバイス機能][WindowsUwpPackagingAppCapabilitiesDevice]。  
*   エンタープライズシナリオをサポートし、Microsoft ストア会社のアカウントを必要とする[特殊な用途の機能][WindowsUwpPackagingAppCapabilitiesSpecialRestricted]。  会社のアカウントについて詳しくは、「[アカウントの種類、場所、料金][WindowsUwpPublishAccountTypesLocationsFees]」をご覧ください。

Microsoft ストアアプリのページには、アプリパッケージマニフェストで宣言するすべての機能が一覧表示されているため、アプリで実際に使用する機能のみを指定するようにしてください。

一部の機能では、アプリが機密性の高いリソースにアクセスできます。  これらのリソースは、ユーザーの個人データにアクセスしたり、ユーザーに課金したりできるため、機密性の高いリソースと見なされます。  Windows 10[設定][BingResultsWindows10Settings]アプリで管理されるプライバシー設定により、ユーザーは機密性の高いリソースへのアクセスを動的に制御することができます。  したがって、機密性の高いリソースが常に利用できるとアプリでは想定していないことが重要です。  機密性の高いリソースへのアクセスについて詳しくは、「[個人データにアクセスするアプリのガイドライン][WindowsUwp|::ref2::|Index]」をご覧ください。  

アクセスを要求するには、アプリのパッケージマニフェストで機能を宣言します。  Visual Studio では、package.appxmanifest designer の [**機能**] パネルで行うことができます。  

![Visual Studio package.appxmanifest designer の [機能] パネル](media/vs-appxmanifest-editor-capabilities.png)  

このチュートリアルでは、既定のインターネット \ (クライアント \) 機能のみを使う必要があるため、これ以上の操作は必要ありません。  

### 機能検出を使って WinRT を呼び出す  

すべてのプラットフォームで PWA のユーザーエクスペリエンスの品質を向上させるために、WinRT 機能検出を使って、Windows での PWA の操作性を段階的に向上させることができます。  こうすることで、Windows 固有のコードが、WinRT Api が利用可能で適用可能なコンテキストでのみ実行されることを確認できます。  

機能検出は、次のように、 `Windows` オブジェクト \ ( [WinRT 名前空間][UwpApiIndex]へのエントリポイント) を簡単に探している場合があります。  

```javascript
if(window.Windows){
    /*Run code that sends Windows API requests */
}
```  

ただし、すべての windows [10 デバイスの種類][UwpExtensionSdkDeviceFamiliesOverview]ですべての windows api を使用できるわけではありませんが、一般的に、送信する API 要求の名前空間をさらに限定するために、より具体的な機能検出を使うと便利です。  

```javascript
if(window.Windows && Windows.Media.SpeechRecognition){
    /*Run code that sends Windows API requests */
}
```  

この背景を使って、カスタムコンテキストメニューを実装するための WinRT コードを追加する準備ができました。  サンプル PWA を使って[プログレッシブ Web アプリ][PwaGetStarted]を使い始める場合は、次の手順に従います。

1.  Visual Studio を PWA サイトプロジェクトで開きます。

1.  ソリューションエクスプローラーで、ファイルを開き、 `views\layout.pug` 次の行をサービスワーカーの参照のすぐ下に追加し `script` ます。
    
    ```xml
    script(src='/javascripts/site.js')
    ```  

1.  ソリューションエクスプローラーで、フォルダーを右クリックし、[ `javascripts` **Add**  >  **新しいファイル**の追加] をクリックします。

1.  ファイルに名前 `site.js` を付けて、次のコードをコピーします。
    
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

1.  ブラウザーで PWA を実行するときのコンテキストメニューの動作 ( `F5` pwa サイトプロジェクトから) と、windows アプリウィンドウの内部 ( `F5` ユニバーサル Windows アプリプロジェクトなど) を比較します。  ブラウザーで右クリックすると、Microsoft Edge の既定のコンテキストメニューが `WWAHost.exe` 表示されます。プロセスでは、カスタムメニューが表示されるようになりました。  

    | Microsoft Edge | Windows 10 アプリ |  
    |:--- |:---- |  
    | ![ブラウザーの既定のコンテキストメニュー](media/browser-context-menu.png) | ![アプリのカスタムコンテキストメニュー](media/app-context-menu.png) |  

この時点では、Windows で PWAs を段階的に強化するための堅固な基盤が用意されています。  質問がある場合や、何か不明確な点がある場合は、コメントを送信してください。  

## 追加情報

[Windows デベロッパーセンター][MicrosoftDeveloperWindowsApps]は、windows アプリ構築のすべての段階 ([[はじめ][MicrosoftDeveloperWindowsAppsGetStarted]に] から [設計]、[[設計][MicrosoftDeveloperWindowsAppsDesign]]、[[開発][MicrosoftDeveloperWindowsAppsDevelop]]、[Microsoft Store への[発行][MicrosoftDeveloperStorePublishApps]] まで) を網羅した包括的なリファレンスです。  

ユニバーサル Windows プラットフォーム \ (UWP) の一般的な概要と、さまざまな Windows 10 デバイスファミリのターゲットを設定する方法については、「[ユニバーサル Windows プラットフォームの概要][WindowsUWPGetStartedGuide]」を参照してください。  

準備ができたら、次のようにして、 [Microsoft ストアに PWA を提出](./microsoft-store.md)する方法について説明します。  

<!-- image links -->  

<!-- links -->  

[PwaGetStarted]: ./get-started.md "プログレッシブ Web アプリの使用を開始する"  
[PwaIndexWindows10]: ./index.md#pwas-on-windows-10-edgehtml "PWAs は Windows 10 (EdgeHTML) にあります。 Windows のプログレッシブ Web アプリ"  
[DevToolsGuide]: ../devtools-guide.md "Microsoft Edge (EdgeHTML) 開発者ツール"  
[DevToolsGuideMicrosoftStoreApp]: ../devtools-guide.md#microsoft-store-app "Microsoft ストアアプリ-Microsoft Edge (EdgeHTML) 開発者ツール"  
[DevToolsGuideServiceWorkers]: ../devtools-guide/service-workers.md "サービス ワーカー"  
[DevToolsProtocol01ClientsEdgePreview]: ../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge の DevTools プレビュー - DevTools プロトコル クライアント"  
[DevGuideWhatsNew]: ../dev-guide/whats-new.md "EdgeHTML の新機能"  
[WindowsRuntime]: ../windows-runtime/index.md "JavaScript の Windows ランタイム (WinRT)"  
[WindowRuntimeUsingJavascript]: ../windows-runtime/using-the-windows-runtime-in-javascript.md "JavaScript での Windows ランタイムの使用"  

[ScriptingJsinrtHandlingWinRTEvents]: /scripting/jswinrt/handling-windows-runtime-events-in-javascript "JavaScript での Windows ランタイムイベントの処理"  
[ScriptingJsinrtUsingWinRT]: /scripting/jswinrt/using-windows-runtime-asynchronous-methods "Windows ランタイム非同期メソッドの使用"  
[ScriptingJsinrtUsingWinRTCasingConventions]:  /scripting/jswinrt/using-the-windows-runtime-in-javascript#casing-conventions-with-windows-runtime-features "Windows ランタイム機能を使用した大文字と小文字の規則-JavaScript での Windows ランタイムの使用"  
[UwpApiIndex]: /uwp/api/index "Windows UWP の名前空間"  
[UwpApiWindowsUiPopups]: /uwp/api/windows.ui.popups "Windows UI のポップアップ名前空間"  
[UwpApiWindowsUiWebuiWebapplicationActivated]: /uwp/api/windows.ui.webui.webuiapplication.activated "WebUIApplication イベント"  
[UwpExtensionSdkDeviceFamiliesOverview]: /uwp/extension-sdks/device-families-overview "デバイスファミリの概要"  
[UwpSchemasAppxpackageUapmanifestschemaGeneratePackageManifest]: /uwp/schemas/appxpackage/uapmanifestschema/generate-package-manifest "Visual Studio でアプリパッケージマニフェストが生成される方法"  
[WindowsUWPIndex]: /windows/uwp/index "ユニバーサル Windows プラットフォームのドキュメント"  
[WindowsUWPGetStartedGuide]: /windows/uwp/get-started/universal-application-platform-guide "ユニバーサル Windows プラットフォーム (UWP) アプリとは何ですか?"  
[WindowsUWPGetStartedEnable]: /windows/uwp/get-started/enable-your-device-for-development "デバイスを開発用に有効にする"  
[WindowsUwpSecurityIndex]: /windows/uwp/security/index "証券"  
[WindowsUwpPublishAccountTypesLocationsFees]: /windows/uwp/publish/account-types-locations-and-fees "アカウントの種類、場所、料金"  
[WindowsUwpPackagingAppCapabilitiesSpecialRestricted]: /windows/uwp/packaging/app-capability-declarations#special-and-restricted-capabilities "制限された機能"  
[WindowsUwpPackagingAppCapabilitiesDevice]: /windows/uwp/packaging/app-capability-declarations#device-capabilities "デバイスの機能"  
[WindowsUwpPackagingAppCapabilitiesGeneralUse]: /windows/uwp/packaging/app-capability-declarations#general-use-capabilities "一般的な用途の機能"  
[WindowsUwpPackagingAppCapabilities]: /windows/uwp/packaging/app-capability-declarations "アプリ機能の宣言"  

[BingResultsWindows10Settings]: https://binged.it/2lOGSH0 "windows 10 の設定-Bing"  
[GithubWinjsWinjs]: https://github.com/winjs/winjs "winjs/winjs |GitHub"  
[MicrosoftDeveloperStorePublishApps]: https://developer.microsoft.com/store/publish-apps/index "Windows アプリとゲームを公開する"  
[MicrosoftDeveloperWindowsApps]: https://developer.microsoft.com/windows/apps/index "ユニバーサル Windows プラットフォームのドキュメント"  
[MicrosoftDeveloperWindowsAppsDesign]: https://developer.microsoft.com/windows/apps/design/index "Windows アプリの設計とコードの作成"  
[MicrosoftDeveloperWindowsAppsDevelop]: https://developer.microsoft.com/windows/apps/develop/index "UWP アプリの開発"  
[MicrosoftDeveloperWindowsAppsGetStarted]: https://developer.microsoft.com/windows/apps/getstarted/index "Windows 10 アプリの使用を開始する"  
[MicrosoftDeveloperWindowsSamples]: https://developer.microsoft.com/windows/samples "コードサンプル"  
[MicrosoftStoreEdgeDevtoolsPreview]: https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj "Microsoft Edge DevTools プレビュー"  
[MicrosoftSupportWindowsAppPermissions]: https://support.microsoft.com/help/10557/windows-10-app-permissions "アプリのアクセス許可"  
[MicrosoftVisualStudioDownloads]: https://visualstudio.microsoft.com/downloads "入手"  
[MicrosoftVisualStudioPreview]: https://visualstudio.microsoft.com/vs/preview "Visual Studio Preview"  
[PreviousVSDownloads]: https://visualstudio.microsoft.com/vs/older-downloads/ "Visual Studio のダウンロード"