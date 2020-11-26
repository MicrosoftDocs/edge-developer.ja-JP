---
description: Microsoft Edge ドライバーを使用して WebView2 コントロールを自動化およびテストする
title: Microsoft Edge ドライバーを使用した WebView2 の自動化とテスト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/25/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、edge、ICoreWebView2、ICoreWebView2Controller、Selenium、Microsoft Edge Driver
ms.openlocfilehash: 2af1ce222abb1dc7a279afc05e87e7e42a45fe9e
ms.sourcegitcommit: 2e14ff82350f700d7eabc8d33b3ec3e5fc8c61fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "11191618"
---
# Microsoft Edge ドライバーを使用した WebView2 の自動化とテスト  

WebView2 は Microsoft Edge \ (Chromium \) web platform を使っているため、WebView2 の開発者 \ (お客様 \) は、デバッグとオートメーション用の標準的な web ツールを利用することができます。  Selenium は、このようなツールの1つです。  W3C [Webdriver][W3cWebdriver2] API を実装します。  Selenium を使って、自動テストを作成し、ユーザーの操作をシミュレートすることができます。  

次の手順で作業を開始します。  

## 手順 1: WebView2API のサンプルをダウンロードする  

既存の WebView2 プロジェクトがない場合は、最新の WebView2 SDK の包括的なサンプルである [WebView2API サンプルアプリ][GithubMicrosoftedgewebview2samplesSampleappsWebview2apisample]をダウンロードしてください。  [WebView2API サンプルアプリの前提条件][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisamplePrerequisites]を満たしていることを確認します。  

リポジトリを複製したら、Visual Studio でプロジェクトをビルドします。  次の図のようになります。  

:::image type="complex" source="../media/webdriver/sample-app.png" alt-text="WebView2API サンプルアプリ" lightbox="../media/webdriver/sample-app.png":::
   WebView2API サンプルアプリ  
:::image-end:::  

## 手順 2: Microsoft Edge ドライバーをインストールする  

指示に従って、 [Microsoft Edge driver][WebdriverChromiumDownloadMicrosoftEdgeDriver] をインストールします。 Selenium では、WebView2 を自動化してテストするために必要なブラウザー固有のドライバーです。  

Microsoft Edge ドライバーのバージョンが、アプリで使用する WebView2 ランタイムのバージョンと一致していることを確認します。  WebView2API サンプルを動作させるには、WebView2 Runtime のバージョンが、最新の WebView2 SDK リリースのサポートされているバージョン以上であることを確認してください。  最新の WebView2 SDK リリースを見つけるには、 [WebView2 リリースノート][Webview2Releasenotes]に移動します。  現在使用している WebView2 ランタイムのバージョンを確認するには、に移動 `edge://settings/help` します。  

## 手順 3: Selenium を WebView2API サンプルに追加する  

この時点で、WebView2 Runtime がインストールされていて、WebView2 プロジェクトと Microsoft Edge ドライバーがインストールされている必要があります。  それでは、Selenium を使い始めましょう。  

> [!NOTE]
> Selenium は、C \ #、Java、Python、Javascript、ルビをサポートしています。  ただし、次のガイドは C \ # を使って作成されています。  

1.  まず、 **Visual Studio**で新しい**C# .net Framework**プロジェクトを作成します。  右下隅にある [ **次へ** ] を選んで続行します。  
    
    :::image type="complex" source="../media/webdriver/new-project.png" alt-text="新しいプロジェクトの作成" lightbox="../media/webdriver/new-project.png":::
       新しいプロジェクトの作成  
    :::image-end:::  
    
1.  プロジェクトに **名前**を付け、希望の **場所**に保存して、[ **作成**] を選びます。  
    
    :::image type="complex" source="../media/webdriver/app-create.png" alt-text="新しいプロジェクトを構成する" lightbox="../media/webdriver/app-create.png":::
       新しいプロジェクトを構成する  
    :::image-end:::  
    
1.  新しいプロジェクトが作成されます。  このガイドでは、すべてのコードがファイルに書き込まれ `Program.cs` ます。  
    
    :::image type="complex" source="../media/webdriver/start-app.png" alt-text="新しいプロジェクト" lightbox="../media/webdriver/start-app.png":::
       新しいプロジェクト  
    :::image-end:::  
    
1.  次に、プロジェクトに **Selenium** を追加します。  **Selenium**をインストールするには、Selenium を使用します。  
    
    **Selenium ドライバーの nuget パッケージ**をダウンロードするには、 **Visual Studio**で**プロジェクト**をポイントして、[ **NuGet パッケージの管理**] を選びます。  次の画面が表示されます。  
    
    :::image type="complex" source="../media/webdriver/download-nuget.png" alt-text="NuGet パッケージをダウンロードする" lightbox="../media/webdriver/download-nuget.png":::
       NuGet パッケージをダウンロードする  
    :::image-end:::  
    
1.  `Selenium.WebDriver`検索バーに入力し、結果から [ **Selenium ドライバー** ] を選び、[**プレリリースを含める**] の横にあるチェックボックスをオンにします。  右側のウィンドウで、 **バージョン** が **4.0.0 をインストール** するように設定されていることを確認し、[ **インストール**] を選択します。  NuGet をコンピューターにダウンロード Selenium します。  
    
    Selenium ドライバーの NuGet パッケージの詳細については、 [Selenium][NugetSeleniumWebdriver400Alpha04]にアクセスしてください。  
    
    :::image type="complex" source="../media/webdriver/nuget.png" alt-text="NuGet パッケージの管理" lightbox="../media/webdriver/nuget.png":::
       NuGet パッケージの管理  
    :::image-end:::  
    
1.  `OpenQA.Selenium.Edge` `using OpenQA.Selenium.Edge;` ファイルの先頭に次のステートメントを追加して使用し `Program.cs` ます。  
    
    ```csharp
    using OpenQA.Selenium.Edge;
    
    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    ```  
    
## 手順 4: Selenium と Microsoft Edge ドライバーを使用して WebView2 ドライブを使用する  

1.  まず、 `EdgeOptions` 次のコードスニペットをコピーして、オブジェクトを作成します。  
    
    ```csharp
    static void Main(string[] args)
    {
        // EdgeOptions() requires using OpenQA.Selenium.Edge
        // Construct EdgeOptions with is_legacy = false and the string "webview2"
        EdgeOptions edgeOptions = new EdgeOptions(false, "webview2");
    ```  
    
    このオブジェクトには、 `EdgeOptions` 次の2つのパラメーターがあります。  
    
    | パラメーター | 詳細 |    
    |:--- |:--- |  
    | `is_legacy` | Selenium を設定すると `false` 、新しい Chromium ベースの Microsoft Edge ブラウザーを運転していることが通知されます。 |  
    | `"webview2"` | WebView2 を運転している Selenium を示す文字列。 |  
    
1.  次に、 `edgeOptions.BinaryLocation` WebView2 project ランタイムのファイルパスを設定し、 `msedgedriverDir` [microsoft edge ドライバー][MicrosoftDeveloperMicrosoftEdgeWebDriverDownloads]をインストールした場所へのファイルパスを提供するという名前の文字列を作成して、 `msedgedriverExe` microsoft edge ドライバーランタイムの名前を格納するための名前の付いた文字列を作成します。  既定では、ランタイムにはという名前が付けられ `msedgedriver.exe` ます。 次に示すように、これら2つの文字列を使っ `EdgeDriverService` てオブジェクトを作成します。  最後に、and を使用してオブジェクトを作成し `EdgeDriver` `EdgeDriverService` `EdgeOptions` ます。  
    
    以下のコードをコピーして貼り付けることができ `edgeOptions` ます。  コンピューターのプロジェクトランタイムと Microsoft Edge ドライバーランタイムへの適切なファイルパスを指定していることを確認します。  
    
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
    
3.  これで、 `EdgeDriver` プロジェクトで WebView2 を実行するように構成されました。  たとえば、 **WebView2API サンプル**を使っている場合は、コマンドを実行して移動することができ `https://microsoft.com` `e.Url = @"https://www.microsoft.com";` ます。  行にブレークポイントを設定し、プロジェクトを実行して、Selenium drive WebView2 を確認します。  
    
    ```csharp
        //The following navigates the WebView2API Sample from bing.com to microsoft.com
        e.Url = @"https://www.microsoft.com";
        
        //This exits the edge driver
        e.Quit();
    }
    ```  
    
    :::image type="complex" source="../media/webdriver/microsoft.png" alt-text="Selenium WebView2" lightbox="../media/webdriver/microsoft.png":::
       Selenium WebView2  
    :::image-end:::

お疲れさまでした。  Selenium および Microsoft Edge ドライバーを使用して、WebView2 プロジェクトとドリブン WebView2 を正常に自動化しました。  

## 関連項目  

*   Api Selenium が WebView2 または Microsoft Edge \ (Chromium \) を操作する方法の概要については、 [Selenium のドキュメントの Webdriver][SeleniumWebdriver]に移動してください。   
*   WebView2 control の詳細と、ネイティブアプリに web コンテンツを埋め込むときの使用方法については、「 [Microsoft Edge WebView2 の概要][WebViewIndex]」を参照してください。  
*   Microsoft Edge \ (Chromium) の自動化の詳細については、「 [WebDriver (Chromium) を使ってテストオートメーションを使用][WebdriverChromium]する」を参照してください。   
    
## Microsoft Edge WebView チームと連絡を取り合う  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[WebdriverChromium]: ../../webdriver-chromium/index.md "テストオートメーションに WebDriver (Chromium) を使います。Microsoft ドキュメント"  
[WebdriverChromiumDownloadMicrosoftEdgeDriver]: ../../webdriver-chromium/index.md#download-microsoft-edge-driver "Microsoft Edge ドライバーをダウンロードする-テストオートメーション用に WebDriver (Chromium) を使います。Microsoft ドキュメント"  
[WebViewIndex]: ../index.md "Microsoft Edge WebView2 の概要-Microsoft ドキュメント"  
[Webview2Releasenotes]: ../releasenotes.md "WebView2 SDK のリリースノート |Microsoft ドキュメント"  

[MicrosoftDeveloperMicrosoftEdgeWebDriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver#downloads "WebDriver をダウンロード |Microsoft Edge 開発者"  

[GithubMicrosoftedgewebview2samplesSampleappsWebview2apisample]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2APISample "WebView2 API のサンプル-MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisamplePrerequisites]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2APISample#prerequisites "前提条件-WebView2 API のサンプル |GitHub"  

[NugetSeleniumWebdriver400Alpha04]: https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-alpha04 "Selenium ドライバー 4.0.0-alpha04 |NuGet ギャラリー"  

[SeleniumWebdriver]: https://www.selenium.dev/documentation/en/webdriver "WebDriver |Selenium"  

[W3cWebdriver2]: https://www.w3.org/TR/webdriver2 "WebDriver |勧告"  
