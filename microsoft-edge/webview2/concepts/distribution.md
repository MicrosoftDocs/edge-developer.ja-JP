---
description: Microsoft Edge WebView2 を使用してアプリをリリースするときの配布オプション
title: Microsoft Edge WebView2 アプリの配布
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 14f252b0155beb6bfce0b01dc080900f2d3e57ee
ms.sourcegitcommit: e79503c6c53ea9b7de58f8cf1532b5c82116a6eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "11195167"
---
# WebView2 を使用したアプリの配布  

WebView2 アプリを配布するときには、アプリが起動される前に、バッキング web プラットフォーム ( [WebView2 Runtime][Webview2Installer]) が存在することを確認します。  この記事では、WebView2 ランタイムをインストールする方法について説明し、WebView2 アプリ用の2つの配布モード (  [Evergreen](#evergreen-distribution-mode) と [Fixed のバージョン](#fixed-version-distribution-mode)) を使用します。  

## Evergreen 配布モード  

> [!NOTE]
> ほとんどの開発者は、Evergreen 配布モードをお勧めします。  

Evergreen 配布モードでは、アプリが最新の機能とセキュリティ更新プログラムを利用していることが保証されます。  次のような特徴があります。  

*   基になる web プラットフォーム \ (WebView2 Runtime) は、追加の作業を行わなくても自動的に更新されます。  
*   Evergreen 配布モードを使うすべてのアプリは、Evergreen WebView2 ランタイムの共有コピーを使用します。これにより、ディスク領域を節約できます。  
    
### WebView2 ランタイムについて  

WebView2 ランタイムは再配布可能なランタイムであり、WebView2 アプリのバッキング web プラットフォームとして機能します。  この概念は、Visual C++ や C++/.NET アプリの .NET ランタイムに似ています。  ランタイムには変更された Microsoft Edge \ (Chromium \) バイナリが含まれています。これは、アプリに対して適切に調整され、テストされています。  ランタイムは、インストール時にユーザーに表示されるブラウザーとしては表示されません。  たとえば、ユーザーがブラウザーのデスクトップショートカットまたはスタートメニューエントリを持っていない場合などです。  

開発およびテスト中には、いずれかの方法でバッキング web プラットフォームとして使うことができます。  

*   WebView2 ランタイム  
*   任意の Insider \ (永続的でない) Microsoft Edge \ (Chromium) ブラウザチャネル  
    
運用環境では、アプリが起動される前に、ランタイムがユーザーデバイスに存在することを確認する必要があります。  Microsoft Edge の厩舎チャネルは、WebView2 の使用には使用できません。  この決定により、アプリは、アプリが運用環境のブラウザーに依存しないようにします。

次の理由により、ブラウザーに依存しないようにします。  

*   Microsoft Edge \ (Chromium \) は、すべてのユーザーデバイスに存在するとは限りません。  たとえば、Windows Update から切断された、または Microsoft によって直接管理されていないデバイス (Enterprise と EDU market の大部分) に、ブラウザーが表示されない場合があります。  WebView2 ランタイムの配布を許可することで、アプリの前提条件として、ブラウザーに依存することを避けることができます。  
*   ブラウザーやアプリにはさまざまなユースケースがあるため、ブラウザーで依存関係を取得すると、アプリに意図しない副次的な影響が生じる可能性があります。  たとえば、IT 管理者は、内部の web サイトとの互換性を維持するためにブラウザーをバージョン管理することができます。  WebView2 ランタイムを使うと、ブラウザーの更新がアクティブに管理されている間も、アプリは evergreen を維持できます。  
*   ブラウザーとは異なり、アプリのシナリオに対してランタイムは開発およびテストされていますが、場合によっては、ブラウザーでまだ使用できないバグ修正が含まれていることがあります。  
    
今後、Evergreen WebView2 Runtime は、Windows の将来のリリースと共に出荷される予定です。  ランタイムがより汎用的に使用できるようになるまで、実行中のアプリでランタイムを展開します。  

### Evergreen WebView2 ランタイムの展開  

デバイス上のすべての Evergreen アプリには、1つの Evergreen WebView2 ランタイムのインストールのみが必要です。  [WebView2 Runtime ダウンロードページ][Webview2Installer]には、多数のツールが用意されています。  Evergreen ランタイムの展開に役立つツールを次に示します。  

*   WebView2 Runtime ブートストラップは、ごくわずかな \ (約 2 MB \ 2 MB) インストーラーです。  WebView2 Runtime ブートストラップは、ユーザーのデバイスアーキテクチャと一致する Microsoft サーバーから Evergreen ランタイムをダウンロードしてインストールします。  
*   ブートストラップをプログラムでダウンロードするためのリンクを使用します。  
*   WebView2 Runtime Standalone Installer は、オフライン環境に Evergreen WebView2 ランタイムをインストールする完全なインストーラーです。  
    
現時点では、ブートストラップとスタンドアロンインストーラーは両方ともコンピューターごとにインストールをサポートします。昇格が必要です。  昇格せずにインストーラーを実行すると、ユーザーにアクセス許可の昇格を促すメッセージが表示されます。  

次のワークフローを使用して、アプリを起動する前にランタイムが既にインストールされていることを確認します。  シナリオによっては、ワークフローを調整できます。  サンプルの [リポジトリ][GitHubMicrosoftedgeWebView2samplesWebview2Deployment]にはサンプルコードが用意されています。  

#### オンラインのみの展開  

ユーザーがインターネットにアクセスできると見なされるオンラインのみの展開シナリオがある場合は、次の手順を実行します。  

1.  アプリのセットアップ中に、ランタイムが既にインストールされていることを確認します。  確認するには、次のいずれかの操作を実行します。  
    *   レジストリが存在するかどうか、または空でないかどうかを調べ `pv (REG_SZ)` `null` ます。  `pv (REG_SZ)`次の場所で検索します。  
        
        64ビット版の Windows の場合  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
        32ビット版の Windows の場合  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
    *   [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring]を実行し、がになっていることを確認し `versionInfo` `NULL` ます。  
1.  ランタイムがインストールされていない場合は、リンクを使用してブートストラップをプログラムでダウンロードします。  
1.  昇格したプロセスまたはコマンドプロンプトから、 `MicrosoftEdgeWebview2Setup.exe /silent /install` サイレントインストールのためにブートストラップを呼び出します。  
    
前のワークフローには、次の利点があります。  

*   必要な場合、またはインストーラーをパッケージ化する必要がない場合にのみ、ランタイムをインストールします。  
*   ブートストラップは、デバイスアーキテクチャを自動的に検出し、対応するランタイムをインストールします。  
*   実行時にサイレントモードでインストールします。  
    
必要に応じてブートストラップをプログラムでダウンロードする代わりに、アプリと共にパッケージ化することもできます。  

#### オフライン展開  

アプリの展開がオフラインで動作する場合は、次の手順を実行します。  

1.  [スタンドアロンインストーラー][Webview2Installer]をダウンロードします。  
1.  アプリのインストーラーまたはアップデーターにインストーラーを含めます。  
1.  アプリのセットアップ中に、ランタイムが既にインストールされていることを確認します。  確認するには、次のいずれかの操作を実行します。  
    *   レジストリが存在するかどうか、または空でないかどうかを調べ `pv (REG_SZ)` `null` ます。  `pv (REG_SZ)`次の場所で検索します。  
        
        64ビット版の Windows の場合  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
        32ビット版の Windows の場合  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
    *   [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring]を実行し、がになっていることを確認し `versionInfo` `NULL` ます。  
1.  ランタイムがインストールされていない場合は、スタンドアロンインストーラーを実行します。  サイレントインストールを実行する場合は、昇格したプロセスからインストーラーを実行するか、または [コピー] をクリックして、次のコマンドを実行します。  
    
    ```shell
    MicrosoftEdgeWebView2RuntimeInstaller{X64/X86/ARM64}.exe /silent /install
    ```  
    
### Evergreen モードでの互換性を維持する  

Web は絶えず進化しています。  Evergreen WebView2 Runtime は最新の機能とセキュリティ修正プログラムを提供するために最新の状態に維持されます。  アプリの web との互換性を維持するために、テストインフラストラクチャを設定する必要があります。  

未安定の Microsoft Edge チャネル (ベータ/開発/カナリア) では、WebView2 Runtime の次の機能についてのヒントを見ることができます。  Microsoft Edge 用の web サイトを開発する場合と同様に、WebView2 アプリを定期的にテストする必要があります。  WebView2 アプリを、非永続的なチャネルのいずれかに対してテストし、問題が発生した場合にアプリを更新したり、 [問題を報告][GithubMicrosoftedgeWebviewfeedback] したりします。 通常、開発者とベータ版が推奨されるチャネルです。  適切なチャネルを判断するには、「 [Microsoft Edge チャネルの概要」][DeployEdgeMicrosoftEdgeChannels]に移動します。  テスト環境では、安定してい [ない Microsoft Edge チャネル][DownloadNonstableEdge] をダウンロードでき `regkey` ます。また、または環境変数を使用して、テストアプリのチャネルの優先順位を指定します。  詳細については、 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions]に移動してください。  また、 [Webdriver][HowtoWebdriver] を使って WebView2 のテストを自動化することもできます。

## 固定バージョンの配布モード   

厳密な互換性要件を持つ制約のある環境では、固定バージョンの配布モードの使用を検討してください。  WebView2 ランタイムの特定のバージョンを、固定バージョンの配布モードで選択してパッケージ化します。  アプリのランタイム更新のタイミングを指定できます。  修正済みのバージョン配布モードでは、自動更新は取得されません。 アプリとランタイムの更新を計画します。  

> [!NOTE] 
> 修正されたバージョンの配布モードは、以前は "自分で作成" と呼ばれていました。  

修正済みバージョンモードを使用するには、次の操作を実行します。

1.  修正済みバージョンパッケージを[ダウンロード][Webview2Installer]します。 
1.  コマンドライン `expand {path to the package} -F:* {path to the destination folder}` または WinRAR などのツールを使用してパッケージを展開します。 適切なフォルダー構造が生成されない可能性があるため、エクスプローラーを使用して伸長しないようにします。  
1.  プロジェクトに解凍された修正バージョンバイナリを含めます。  
1.  WebView2 環境の作成時に、修正されたバージョンのバイナリへのパスを指定します。  
    *   Win32 C/c + + の場合は、 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions] 関数を使って環境を作成することができます。  パラメーターを使用して、が `browserExecutableFolder` 含まれているフォルダーへのパスを指定し `msedgewebview2.exe` ます。  
    *   .NET の場合は、次のいずれかのオプションを使用して環境を指定できます。  
        
        > [!NOTE]
        > WebView2 プロパティを有効にするには、環境を指定する必要があり `Source` ます。  
        
        *   `CreationProperties`WebView2 要素で \ ([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties] / [WinForms][ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]\) プロパティを設定します。  `BrowserExecutableFolder` `CoreWebView2CreationProperties` \ ([WPF][ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties] / [WinForms][ReferenceWinFormsMicrosoftWebWebview2WinForms]\) クラスのメンバーを使って、修正されたバージョンのバイナリへのパスを指定します。  
        *   `EnsureCoreWebView2Async`[WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async] / 環境を指定するには、\ (WPF[WinForms][ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]\) を使用します。  CoreWebView2Environment のパラメーターを使って、修正された `browserExecutableFolder` バージョンのバイナリへのパスを指定します[CoreWebView2Environment.CreateAsync][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync] 。  
1.  アプリで、修正されたバージョンのバイナリをパッケージ化して配布します。  必要に応じてバイナリを更新します。  
    
### 修正されたバージョンの既知の問題  

Evergreen ランタイムと比べると、修正されたバージョンにはインストールプロセスがないため、 [Microsoft PlayReady][MicrosoftPlayReady] は変更されずに機能しません。  次の操作を実行すると、問題を軽減できます。  

1.  次の場所など、ユーザーのデバイスに固定バージョンパッケージを展開するパスを見つけます。
    
    ```text
    D:\myapp\Microsoft.WebView2.FixedVersionRuntime.87.0.664.8.x64
    ```  
    
1.  ユーザーのデバイスで次のコマンドを実行します。

    ```shell
    icacls {Fixed Version path} /grant *S-1-15-2-2:(OI)(CI)(RX)
    icacls {Fixed Version path} /grant *S-1-15-2-1:(OI)(CI)(RX)
    ```  

1.  PlayReady は、ユーザーのデバイスで現在動作している必要があります。  [**修正済みバージョン**] フォルダーの [**セキュリティ**] タブに、との権限が含まれている必要があり `ALL APPLICATION PACKAGES` `ALL RESTRICTED APPLICATION PACKAGES` ます。  

    :::image type="complex" source="../media/play-ready-permission.png" alt-text="PlayReady のアクセス許可" lightbox="../media/play-ready-permission.png":::
        PlayReady のアクセス許可  
    :::image-end:::  

<!-- links -->  

[ConceptsVersioning]: ./versioning.md "ブラウザーのバージョンと WebView2 についてMicrosoft ドキュメント"  
[HowtoWebdriver]: ../howto/webdriver.md "Microsoft Edge Driver での WebView2 の自動化とテスト |Microsoft ドキュメント"  

[ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions]: /microsoft-edge/webview2/reference/win32/webview2-idl#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions-Globals |Microsoft ドキュメント"  
[ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring]: /microsoft-edge/webview2/reference/win32/webview2-idl#getavailablecorewebview2browserversionstring "GetAvailableCoreWebView2BrowserVersionString-Globals |Microsoft ドキュメント"  

[DeployEdgeMicrosoftEdgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge チャネルの概要 |Microsoft ドキュメント"  

[ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.createasync "WebView2 クラスの CreateAsync-CoreWebView2Environment クラス |Microsoft ドキュメント"  
[ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async "EnsureCoreWebView2Async クラス | WebView2 クラスをお選びください。 |Microsoft ドキュメント"  
[ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.winforms.webview2.ensurecorewebview2async "EnsureCoreWebView2Async-WebView2 クラス | WebView2 クラス |Microsoft ドキュメント"  
[ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties]: /dotnet/api/microsoft.web.webview2.wpf.corewebview2creationproperties "CoreWebView2CreationProperties クラス | WebView2 クラスをお選びください。 |Microsoft ドキュメント"  
[ReferenceWinFormsMicrosoftWebWebview2WinForms]: /dotnet/api/microsoft.web.webview2.winforms "WebView2 クラス | WinForms クラス |Microsoft ドキュメント"  
[ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties]: /dotnet/api/microsoft.web.webview2.wpf.webview2.creationproperties "WebView2 クラスのプロパティの自動 WebView2 のプロパティ |Microsoft ドキュメント"  
[ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]: /dotnet/api/microsoft.web.webview2.winforms.webview2 "WebView2 クラス WebView2 | WinForms クラス |Microsoft ドキュメント"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 インストーラ |Microsoft 開発者"  

[DownloadNonstableEdge]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView のフィードバック |GitHub"  

[GitHubMicrosoftEdgeWebView2SamplesWebview2Deployment]: https://github.com/MicrosoftEdge/WebView2Samples#webview2-deployment "WebView2 展開-MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftPlayReady]: https://www.microsoft.com/playready "Microsoft PlayReady"  
