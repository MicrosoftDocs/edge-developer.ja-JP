---
description: Microsoft Edge WebView2 を使用してアプリをリリースする場合の配布オプション
title: Microsoft Edge WebView2 アプリの配布
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、edge html
ms.openlocfilehash: 97ede968e066c572bb1b22e10ed7e758e38e3ca4
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "11535700"
---
# <a name="distribution-of-apps-using-webview2"></a>WebView2 を使用したアプリの配布  

WebView2 アプリを配布する場合は、アプリを起動する前に、バッキング Web プラットフォームである [WebView2 ランタイム][Webview2Installer]が存在することを確認してください。  この記事では、ユーザー \(開発者\) が WebView2 ランタイムをインストールし、WebView2 アプリの 2 つの配布モードである[エバーグリーン](#evergreen-distribution-mode)と[固定バージョン](#fixed-version-distribution-mode)を使用する方法について説明します。  

## <a name="evergreen-distribution-mode"></a>エバーグリーンの配布モード  

> [!NOTE]
> ほとんどの開発者には、エバーグリーンの配布モードをお勧めします。  

エバーグリーンの配布モードでは、アプリで最新の機能とセキュリティ更新プログラムを利用できます。  次の特徴があります。  

*   基礎となる Web プラットフォーム \(WebView2 Runtime\) は、追加の作業を行わずに自動的に更新されます。  
*   エバーグリーン配布モードを使用するすべてのアプリは、ディスク領域を節約するエバーグリーン WebView2 ランタイムの共有コピーを使用します。  
    
### <a name="understanding-the-webview2-runtime"></a>WebView2 ランタイムについて  

WebView2 ランタイムは再頒布可能なランタイムであり、WebView2 アプリのバッキング Web プラットフォームとして機能します。  概念は、Visual C++ または C++/.NET アプリ用の .NET ランタイムに似ています。  ランタイムには、アプリ用に微調整されテストされた、変更された Microsoft Edge \(Chromium\) バイナリが含まれています。  ランタイムは、インストール時にユーザーに表示されるブラウザーとして表示されません。  たとえば、ユーザーにはブラウザーのデスクトップ ショートカットやスタート メニューのエントリがありません。  

開発およびテスト中は、どちらかをバッキング Web プラットフォームとして使用できます。  

*   WebView2 ランタイム  
*   任意の Insider \(非安定版\) Microsoft Edge \(Chromium\) ブラウザー チャネル  
    
運用環境では、アプリを起動する前に、ユーザー のデバイスにランタイムが存在することを確認する必要があります。  Microsoft Edge Stable チャネルは、WebView2 の使用には利用できません。  この決定により、アプリが運用環境でブラウザーに依存することを防ぎます。

次の理由により、ブラウザーに依存しないようにしてください。  

*   Microsoft Edge \(Chromium\) は、すべてのユーザー デバイスに存在することが保証されているわけではありません。  たとえば、Windows Update から切断されたデバイスや、Microsoft によって直接管理されていないデバイス \(Enterprise および EDU 市場の大部分\) にはブラウザーが存在しない場合があります。  WebView2 ランタイムを配布できるようにすることで、アプリの前提条件としてブラウザーに依存することを回避できます。  
*   ブラウザーとアプリの使用例は異なっています。そのため、ブラウザーに依存すると、アプリに意図しない副作用が発生する可能性があります。  たとえば、IT 管理者は、内部 Web サイトの互換性を確保するためにブラウザーのバージョン管理を行う場合があります。  WebView2 ランタイムを使うと、ブラウザーの更新プログラムがアクティブに管理されている間、アプリを常にエバーグリーンに保つことができます。  
*   ブラウザーとは対照的に、ランタイムはアプリのシナリオ用に開発およびテストされ、場合によっては、ブラウザーでまだ利用できないバグ修正が含まれる場合があります。  
    
今後、エバーグリーン WebView2 ランタイムは Windows の将来のリリースとともに配付される予定です。  ランタイムがより一般に利用可能になるまで、運用アプリでランタイムを展開します。  

### <a name="deploying-the-evergreen-webview2-runtime"></a>エバーグリーン WebView2 ランタイムの展開  

デバイス上のすべてのエバーグリーン アプリに必要なエバーグリーン WebView2 ランタイムのインストールは 1 つだけです。  [ WebView2 ランタイムのダウンロード ページ][Webview2Installer]には、多数のツールが用意されています。  次のツールは、エバーグリーン ランタイムの展開に役立ちます。  

*   WebView2 ランタイム ブートストラップは、小さな \(約 2 MB\) インストーラーです。  WebView2 ランタイム ブートストラップは、ユーザーのデバイス アーキテクチャに一致する Microsoft サーバーからエバーグリーン ランタイムをダウンロードしてインストールします。  
*   リンクを使用して、プログラムでブートストラップをダウンロードします。  
*   WebView2 ランタイム スタンドアロン インストーラーは、オフライン環境にエバーグリーン WebView2 ランタイムをインストールする完全なインストーラーです。  
    
現在、ブートストラップとスタンドアロンの両方のインストーラーは、昇格が必要なコンピューターごとのインストールのみをサポートしています。  昇格せずにインストーラーを実行すると、アクセス許可を昇格するように求めるメッセージが表示されます。  

アプリを起動する前にランタイムが既にインストールされていることを確認するには、次のワークフローを使用します。  自分のシナリオに応じてワークフローを調整できます。  サンプル コードは、[サンプルのリポジトリ][GitHubMicrosoftedgeWebView2samplesWebview2Deployment]で利用可能です。  

#### <a name="online-only-deployment"></a>オンラインのみの展開  

ユーザーがインターネットにアクセスできると想定されるオンラインのみの展開シナリオがある場合は、次の手順を実行します。  

1.  アプリのセットアップ中に、ランタイムが既にインストールされていることを確認します。  確認するには、次のいずれかの操作を実行します。  
    *   `pv (REG_SZ)` レジストリ キーが存在し、`null` または空でないことを確認します。  次の場所で、`pv (REG_SZ)` を探します。  
        
        64 ビット Windows の場合  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
        32 ビット Windows の場合  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
    *   [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring]を実行し、`versionInfo` が `NULL` であることを確認します。  
1.  ランタイムがインストールされていない場合は、リンクを使用してプログラムでブートストラップをダウンロードします。  
1.  サイレント インストールの場合は、昇格したプロセスまたはコマンドプロンプトから `MicrosoftEdgeWebview2Setup.exe /silent /install` を使用してブートストラップを呼び出します。  
    
前のワークフローには、次の利点があります。  

*   必要な場合、またはインストーラーをパッケージ化する必要がない場合にのみ、ランタイムをインストールします。  
*   ブートストラップは自動的にデバイス アーキテクチャを検出し、一致するランタイムをインストールします。  
*   ランタイムをサイレント インストールします。  
    
プログラムでオンデマンドでダウンロードする代わりに、ブートストラップをアプリにパッケージ化することもできます。  

#### <a name="offline-deployment"></a>オフラインの展開  

アプリの展開を完全にオフラインで行う必要があるオフライン展開シナリオがある場合は、次の手順を実行します。  

1.  [スタンドアロン インストーラー][Webview2Installer]をダウンロードします。  
1.  インストーラーをアプリ インストーラーまたはアップデーターに含めます。  
1.  アプリのセットアップ中に、ランタイムが既にインストールされていることを確認します。  確認するには、次のいずれかの操作を実行します。  
    *   `pv (REG_SZ)` レジストリ キーが存在し、`null` または空でないことを確認します。  次の場所で、`pv (REG_SZ)` を探します。  
        
        64 ビット Windows の場合  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
        32 ビット Windows の場合  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
    *   [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring]を実行し、`versionInfo` が `NULL` であることを確認します。  
1.  ランタイムがインストールされていない場合は、スタンドアロン インストーラーを実行します。  サイレント インストールを実行する場合は、昇格されたプロセスからインストーラーを実行するか、次のコマンドをコピーして実行します。  
    
    ```shell
    MicrosoftEdgeWebView2RuntimeInstaller{X64/X86/ARM64}.exe /silent /install
    ```  
    
### <a name="stay-compatible-in-evergreen-mode"></a>エバーグリーン モードで互換性を保つ  

Web は常に進化しています。  エバーグリーン WebView2 ランタイムは最新の状態に保たれ、最新の機能とセキュリティ修正プログラムが提供されます。  アプリが Web との互換性を維持できるようにするには、テスト インフラストラクチャを設定する必要があります。  

不安定な Microsoft Edge チャネル \(Beta/Dev/Canary\) では、WebView2 ランタイムで次に予定されている機能のヒントを確認できます。  Microsoft Edge 用の Web サイトを開発する場合と同様に、WebView2 アプリを定期的にテストする必要があります。  不安定なチャネルの 1 つに対して WebView2 アプリをテストし、問題が発生した場合はアプリを更新するか、[問題を報告します][GithubMicrosoftedgeWebviewfeedback]。 通常、推奨されるチャネルは Dev と Beta です。  適切なチャネルを判断するには、「[Microsoft Edge チャネルの概要][DeployEdgeMicrosoftEdgeChannels]」を参照してください。  安定していない [Microsoft Edge チャネル][DownloadNonstableEdge]をテスト環境にダウンロードし、`regkey` または環境変数を使用してテスト アプリのチャネルの設定を指定することができます。  詳細については、「[CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions]」を参照してください。  [WebDriver ][HowToWebdriver] を使用して WebView2 のテストを自動化することもできます。

## <a name="fixed-version-distribution-mode"></a>固定バージョンの配布モード   

厳密な互換性要件がある制約のある環境では、固定バージョンの配布モードの使用を検討してください。  固定バージョンの配布モードを使用して、特定のバージョンの WebView2 ランタイムを選択してパッケージ化します。  アプリのランタイム更新のタイミングを指定できます。  固定バージョンの配布モードは自動更新を受け取りません。 アプリとランタイムの更新を計画します。  

> [!NOTE] 
> 固定バージョンの配布モードは、以前は bring-your-own (持ち込み) と呼ばれていました。  

固定バージョン モードを使用するには、次の操作を実行します。

1.  固定バージョン パッケージを[ダウンロードします][Webview2Installer]。 
1.  コマンド ライン `expand {path to the package} -F:* {path to the destination folder}` または WinRAR などのツールを使用してパッケージを展開します。 フォルダー構造が正しく生成されない可能性があるため、エクスプローラーで展開するのは避けてください。  
1.  展開された固定バージョンのバイナリをプロジェクトに含めます。  
1.  WebView2 環境を作成するときに、固定バージョンのバイナリへのパスを指定します。  
    *   Win32 C/C++ の場合は、[、CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions] 関数を使用して環境を作成できます。  `browserExecutableFolder` パラメーターを使用して、`msedgewebview2.exe` が含まれているフォルダーへのパスを指定します。  
    *   .NET の場合は、次のいずれかのオプションを使用して環境を指定できます。  
        
        > [!NOTE]
        > WebView2 の `Source` プロパティを有効にするには、環境を指定する必要があります。  
        
        *   `CreationProperties`WebView2 要素の \([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties]/[WinForms][ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]\) プロパティを設定します。  `CoreWebView2CreationProperties` \([WPF][ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties]/[WinForms][ReferenceWinFormsMicrosoftWebWebview2WinForms]\) クラスの `BrowserExecutableFolder` メンバーを使用して、固定バージョンのバイナリへのパスを指定します。  
        *   `EnsureCoreWebView2Async` \([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async]/[WinForms][ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]\) を使用して環境を指定します。  [CoreWebView2Environment.CreateAsync][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync] の `browserExecutableFolder` パラメーターを使用して、固定バージョンのバイナリへのパスを指定します。  
1.  固定バージョンのバイナリをアプリにパッケージ化して配付します。  必要に応じてバイナリを更新します。  
    
### <a name="known-issues-for-fixed-version"></a>固定バージョンの既知の問題  

エバーグリーン ランタイムと比較すると、固定バージョンにはインストール プロセスが含まれていないため、[Microsoft PlayReady][MicrosoftPlayReady] は変更をしないと動作しません。  以下の操作を実行すると、問題を軽減できる可能性があります。  

1.  次の場所など、ユーザーのデバイスに固定バージョン パッケージを展開するパスを指定ます。
    
    ```text
    D:\myapp\Microsoft.WebView2.FixedVersionRuntime.87.0.664.8.x64
    ```  
    
1.  ユーザーのデバイスで次のコマンドを実行します。

    ```shell
    icacls {Fixed Version path} /grant *S-1-15-2-2:(OI)(CI)(RX)
    icacls {Fixed Version path} /grant *S-1-15-2-1:(OI)(CI)(RX)
    ```  

1.  これで PlayReady はユーザーのデバイスで動作しているはずです。  **[固定バージョン]** フォルダーの **[セキュリティ]** タブには、`ALL APPLICATION PACKAGES` と `ALL RESTRICTED APPLICATION PACKAGES` のアクセス許可が含まれている必要があります。  

    :::image type="complex" source="../media/play-ready-permission.png" alt-text="PlayReady のアクセス許可" lightbox="../media/play-ready-permission.png":::
        PlayReady のアクセス許可  
    :::image-end:::  

<!-- links -->  

[ConceptsVersioning]: ./versioning.md "ブラウザーのバージョンと WebView2 について | Microsoft Docs"  
[HowToWebdriver]: ../how-to/webdriver.md "Microsoft Edge Driver での WebView2 の自動化とテスト | Microsoft Docs"  

[ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions]: /microsoft-edge/webview2/reference/win32/webview2-idl#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions - Globals | Microsoft Docs"  
[ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring]: /microsoft-edge/webview2/reference/win32/webview2-idl#getavailablecorewebview2browserversionstring "GetAvailableCoreWebView2BrowserVersionString - グローバル | Microsoft Docs"  

[DeployEdgeMicrosoftEdgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge チャネルの概要 | Microsoft Docs"  

[ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.createasync "CreateAsync - Microsoft.Web.WebView2.Core.CoreWebView2Environment クラス | Microsoft Docs"  
[ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async "EnsureCoreWebView2Async -Microsoft.Web.WebView2.Wpf.WebView2 クラス | Microsoft Docs"  
[ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.winforms.webview2.ensurecorewebview2async "EnsureCoreWebView2Async - Microsoft.Web.WebView2.WinForms.WebView2 クラス | Microsoft Docs"  
[ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties]: /dotnet/api/microsoft.web.webview2.wpf.corewebview2creationproperties "CoreWebView2CreationProperties - Microsoft.Web.WebView2.Wpf.CoreWebView2CreationProperties クラス | Microsoft Docs"  
[ReferenceWinFormsMicrosoftWebWebview2WinForms]: /dotnet/api/microsoft.web.webview2.winforms "Microsoft.Web.WebView2.WinForms クラス | Microsoft Docs"  
[ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties]: /dotnet/api/microsoft.web.webview2.wpf.webview2.creationproperties "CreationProperties - Microsoft.Web.WebView2.Wpf.WebView2 クラス | Microsoft Docs"  
[ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]: /dotnet/api/microsoft.web.webview2.winforms.webview2 "Microsoft.Web.WebView2.WinForms.WebView2 クラス | Microsoft Docs"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 インストーラー | Microsoft デベロッパー"  

[DownloadNonstableEdge]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック |GitHub"  

[GitHubMicrosoftEdgeWebView2SamplesWebview2Deployment]: https://github.com/MicrosoftEdge/WebView2Samples#webview2-deployment "WebView2 の展開 - MicrosoftEdge/WebView2Samples | GitHub"  

[MicrosoftPlayReady]: https://www.microsoft.com/playready "Microsoft PlayReady"  
