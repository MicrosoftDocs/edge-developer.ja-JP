---
description: Microsoft Edge Driver を使用して WebView2 コントロールを自動化してテストする
title: Microsoft Edge ドライバーを使用した WebView2 の自動化とテスト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、Webview2、Webview、edge、ICoreWebView2、ICoreWebView2Controller、Selenium、Microsoft Edge Driver
ms.openlocfilehash: c23d639582d4ce550406cf955c96171167bde7c8
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11470831"
---
# <a name="automating-and-testing-webview2-with-microsoft-edge-driver"></a>Microsoft Edge Driverを使用した WebView2 の自動化とテスト  

WebView2 は Microsoft Edge \(Chromium\) Web プラットフォームを使用しますので、WebView2 開発者 \(you\) は、デバッグと自動化のための標準的な Web ツールを利用する場合があります。  Selenium はそのようなツールの 1 つです。  W3C [WebDriver][W3cWebdriver2] API を実装します。  Selenium を使用して、ユーザーの操作をシミュレートする自動テストを作成できます。  

次の手順を開始します。  

## <a name="step-1--download-webview2api-sample"></a>手順 1: WebView2API サンプルをダウンロードする  

既存の WebView2 プロジェクトをお持ちではない場合は、 [最新の WebView2][GithubMicrosoftedgewebview2samplesSampleappsWebview2apisample]SDK の包括的なサンプルである WebView2API サンプル アプリをダウンロードしてください。  [WebView2API サンプル アプリの前提条件を満たしていることを確認します][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisamplePrerequisites]。  

リポジトリを複製したら、プロジェクトをビルドして、Visual Studio。  次の図のようになります。  

:::image type="complex" source="../media/webdriver/sample-app.png" alt-text="WebView2API サンプル アプリ" lightbox="../media/webdriver/sample-app.png":::
   WebView2API サンプル アプリ  
:::image-end:::  

## <a name="step-2--install-microsoft-edge-driver"></a>手順 2: Microsoft Edge Driver をインストールする  

手順に従って Microsoft Edge Driver をインストールし [、WebView2][WebdriverChromiumDownloadMicrosoftEdgeDriver] を自動化およびテストするために Selenium で必要なブラウザー固有のドライバーをインストールします。  

Microsoft Edge Driver のバージョンが、アプリで使用する WebView2 ランタイムのバージョンと一致する必要があります。  WebView2API サンプルが動作するには、WebView2 ランタイムのバージョンが、サポートされている最新の WebView2 SDK リリースのバージョン以上である必要があります。  最新の WebView2 SDK リリースを見つけるには [、WebView2 リリース ノートに移動します][Webview2Releasenotes]。  現在使用している WebView2 ランタイムのバージョンを確認するには、に移動します `edge://settings/help` 。  

## <a name="step-3--add-selenium-to-the-webview2api-sample"></a>手順 3: WebView2API サンプルに Selenium を追加する  

この時点で、WebView2 ランタイムをインストールし、WebView2 プロジェクトをビルドし、Microsoft Edge Driver をインストールする必要があります。  次に、Selenium の使用を開始します。  

> [!NOTE]
> Selenium は C\#、Java、Python、Javascript、および Ruby をサポートします。  ただし、次のガイドは C\#を使用して記述されています。  

1.  まず、新しいプロジェクト**をC# .NET Framework****を作成**Visual Studio。  次に **進** むには、右下隅の [次へ] を選択します。  
    
    :::image type="complex" source="../media/webdriver/new-project.png" alt-text="新しいプロジェクトの作成" lightbox="../media/webdriver/new-project.png":::
       新しいプロジェクトの作成  
    :::image-end:::  
    
1.  プロジェクトに名前を付 **け**、好みの場所に **保存し**、[作成] を **選択します**。  
    
    :::image type="complex" source="../media/webdriver/app-create.png" alt-text="新しいプロジェクトを構成する" lightbox="../media/webdriver/app-create.png":::
       新しいプロジェクトを構成する  
    :::image-end:::  
    
1.  新しいプロジェクトが作成されます。  このガイドでは、すべてのコードがファイルに書き込 `Program.cs` まれます。  
    
    :::image type="complex" source="../media/webdriver/start-app.png" alt-text="新しいプロジェクト" lightbox="../media/webdriver/start-app.png":::
       新しいプロジェクト  
    :::image-end:::  
    
1.  次に **、Selenium を** プロジェクトに追加します。  **Selenium.WebDriver NuGet パッケージを使用して Selenium をインストールします**。  
    
    **Selenium.WebDriver NuGet**パッケージをダウンロードするには****、Visual Studio で Project**** をポイントし、[NuGet パッケージの管理]**を選択します**。  次の画面が表示されます。  
    
    :::image type="complex" source="../media/webdriver/download-nuget.png" alt-text="NuGet パッケージのダウンロード" lightbox="../media/webdriver/download-nuget.png":::
       NuGet パッケージのダウンロード  
    :::image-end:::  
    
1.  検索 `Selenium.WebDriver` バーに入力し、結果から **[Selenium.WebDriver]** を選択し、[プレリリースを含める] の横にあるチェック ボックスをオン **にします**。  右側のウィンドウで、バージョンが**4.0.0-alpha04**以降のインストールに設定されているのを確認し、[インストール] を選択**します**。 ****  NuGet は、Selenium をコンピューターにダウンロードします。  
    
    Selenium.WebDriver NuGet パッケージの詳細については [、「Selenium.WebDriver 4.0.0-alpha04」に移動します][NugetSeleniumWebdriver400Alpha04]。  
    
    :::image type="complex" source="../media/webdriver/nuget.png" alt-text="NuGet パッケージの管理" lightbox="../media/webdriver/nuget.png":::
       NuGet パッケージの管理  
    :::image-end:::  
    
1.  ファイル `OpenQA.Selenium.Edge` の先頭に次のステートメント  `using OpenQA.Selenium.Edge;` を追加して使用 `Program.cs` します。  
    
    ```csharp
    using OpenQA.Selenium.Edge;
    
    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    ```  
    
## <a name="step-4-drive-webview2-with-selenium-and-microsoft-edge-driver"></a>手順 4: Selenium と Microsoft Edge ドライバーを使用して WebView2 を駆動する  

1.  まず、次の `EdgeOptions` コード スニペットをコピーして、オブジェクトを作成します。  
    
    ```csharp
    static void Main(string[] args)
    {
        // EdgeOptions() requires using OpenQA.Selenium.Edge
        // Construct EdgeOptions with is_legacy = false and the string "webview2"
        EdgeOptions edgeOptions = new EdgeOptions(false, "webview2");
    ```  
    
    オブジェクト `EdgeOptions` は、次の 2 つのパラメーターを受け取ります。  
    
    | パラメーター | 詳細 |    
    |:--- |:--- |  
    | `is_legacy` | に設定 `false` します。これは、新しいクロムベースの Microsoft Edge ブラウザーを駆動している Selenium に指示します。 |  
    | `"webview2"` | WebView2 を駆動している Selenium を示す文字列。 |  
    
1.  次に、WebView2 プロジェクト ランタイムのファイル パスに設定し、Microsoft Edge Driver をインストールした場所へのファイル パスを指定する名前の文字列を作成し `edgeOptions.BinaryLocation` `msedgedriverDir` [、Microsoft][MicrosoftDeveloperMicrosoftEdgeWebDriverDownloads] `msedgedriverExe` Edge Driver ランタイムの名前を格納する名前の文字列を作成します。  既定では、ランタイムの名前は `msedgedriver.exe` . 次に示すように、これらの 2 つの文字列 `EdgeDriverService` を使用してオブジェクトを作成します。  最後に、 を使用して `EdgeDriver` オブジェクトを `EdgeDriverService` 作成します `EdgeOptions` 。  
    
    下に次のコードをコピーして貼り付けます `edgeOptions` 。  プロジェクト ランタイムへの正しいファイル パスと、コンピューター上の Microsoft Edge Driver ランタイムを指定してください。  
    
    ```csharp
    //Set the BinaryLocation to the filepath of the WebView2API Sample runtime
    edgeOptions.BinaryLocation = @"C:\path\to\your\webview2\project.exe";
    
    //Set msedgedriverDir to the filepath of the directory housing msedgedriver.exe
    string msedgedriverDir = @"C:\path\to\your\msededriver.exe's\directory";
    
    //Set msedgedriverExe to the name of the Edge Driver. By default it is:
    string msedgedriverExe = @"msedgedriver.exe";
    
    // Construct EdgeDriverService with is_legacy = false  
    EdgeDriverService service = EdgeDriverService.CreateDefaultService(msedgedriverDir, msedgedriverExe, false);
    
    EdgeDriver e = new EdgeDriver(service, edgeOptions);
    ```
    
3.  これで、 `EdgeDriver` プロジェクトで WebView2 を駆動するように構成されています。  たとえば **、WebView2API**サンプルを使用している場合は、コマンドを実行 `https://microsoft.com` して移動 `e.Url = @"https://www.microsoft.com";` できます。  行にブレークポイントを設定し、プロジェクトを実行して、Selenium ドライブ WebView2 を確認します。  
    
    ```csharp
        //The following navigates the WebView2API Sample from bing.com to microsoft.com
        e.Url = @"https://www.microsoft.com";
        
        //This exits the edge driver
        e.Quit();
    }
    ```  
    
    :::image type="complex" source="../media/webdriver/microsoft.png" alt-text="WebView2 を実行するセレン" lightbox="../media/webdriver/microsoft.png":::
       WebView2 を実行するセレン  
    :::image-end:::

お疲れさまでした。  Selenium と Microsoft Edge Driver を使用して WebView2 プロジェクトと駆動型 WebView2 を正常に自動化しました。  

## <a name="see-also"></a>関連項目  

*   API Selenium が WebView2 または Microsoft Edge \(Chromium\) を駆動する方法の詳細については、Selenium のドキュメントの [WebDriver に移動します。][SeleniumWebdriver]   
*   WebView2 コントロールの詳細と、ネイティブ アプリに Web コンテンツを埋め込む際に使用する方法については [、「Microsoft Edge WebView2][WebViewIndex]の概要」に移動します。  
*   Microsoft Edge \(Chromium\) の自動化の詳細については、「テストオートメーションに[WebDriver (Chromium)][WebdriverChromium]を使用する」に移動します。   
    
## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a>Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[WebdriverChromium]: ../../webdriver-chromium/index.md "WebDriver (Chromium) を使用してテストオートメーションを|Microsoft Docs"  
[WebdriverChromiumDownloadMicrosoftEdgeDriver]: ../../webdriver-chromium/index.md#download-microsoft-edge-driver "Microsoft Edge Driver をダウンロードする - テストオートメーションに WebDriver (Chromium) を使用|Microsoft Docs"  
[WebViewIndex]: ../index.md "Microsoft Edge WebView2 の概要 - Microsoft Docs"  
[Webview2Releasenotes]: ../releasenotes.md "WebView2 SDK のリリースノート |Microsoft Docs"  

[MicrosoftDeveloperMicrosoftEdgeWebDriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver#downloads "WebDriver ファイルをダウンロード|Microsoft Edge 開発者"  

[GithubMicrosoftedgewebview2samplesSampleappsWebview2apisample]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2APISample "WebView2 API サンプル - MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisamplePrerequisites]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2APISample#prerequisites "前提条件 - WebView2 API のサンプル |GitHub"  

[NugetSeleniumWebdriver400Alpha04]: https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-alpha04 "Selenium.WebDriver 4.0.0-alpha04 |NuGet ギャラリー"  

[SeleniumWebdriver]: https://www.selenium.dev/documentation/en/webdriver "WebDriver |Selenium"  

[W3cWebdriver2]: https://www.w3.org/TR/webdriver2 "WebDriver |W3C"  
