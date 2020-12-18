---
description: Microsoft Edge で Web サイトまたはアプリをテストする方法、または WebDriver でブラウザーを自動化する方法について説明します。
title: WebDriver (Chromium)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/02/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge, web 開発, html, css, javascript, 開発者, webdriver, selenium,テストする, ツール, 自動化, テスト
ms.openlocfilehash: 5e881eec59c966fd4fa6d35118032a3a51e7b9e5
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231134"
---
# WebDriver (Chromium) を使用したテスト自動化の概要  

WebDriver を使うと、\(developers\) は、ユーザーの操作をシミュレートする自動テストを作成できます。  WebDriver のテストとシミュレーションは、次の理由から、JavaScript 単体テストとは異なります。  

*   ブラウザーで実行されている JavaScript では利用できない機能と情報にアクセスします。  
*   ユーザー イベントや OS レベルのイベントをより正確にシミュレートします。  
*   1 回のテスト セッションで、複数のウィンドウ、タブ、Web ページを管理します。  
*   特定のコンピューターで Microsoft Edge の複数のセッションを実行します。  
    
次のセクションでは、Microsoft Edge \ (Chromium \) の WebDriver の使用を開始する方法について説明します。  

## Microsoft Edge (Chromium) をインストールする  

[Microsoft Edge (Chromium)][MicrosoftEdge] を確実にインストールしてください。  Microsoft Edge\ (Chromium \) がインストールされていることを確認するには、`edge://settings/help` に移動して  、バージョン番号がバージョン 75 以降であることを確認します。  

## Microsoft Edge ドライバーをダウンロードする  

テストの自動化を開始するには、次の手順を使用して、インストールする WebDriver のバージョンがお使いのブラウザーのバージョンと一致していることを確認します。  

1.  `edge://settings/help` に移動して、Microsoft Edge のバージョンを取得します。  
    
    :::image type="complex" source="./media/edge-version.png" alt-text="2020 年 1 月 14 日の Microsoft Edge カナリアのビルド番号":::
       2020 年 1 月 14 日の Microsoft Edge カナリアのビルド番号
    :::image-end:::  
    
1.  [Microsoft Edge ドライバーのダウンロード][MicrosoftDeveloperEdgeToolsWebdriverDownloads]ページに移動して、Microsoft edge のバージョン番号と一致するドライバーをダウンロードします。  
    
    :::image type="complex" source="./media/edge-driver-install.png" alt-text="Microsoft Edge ドライバー ページのダウンロード セクション":::
       [Microsoft Edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriver]ページのダウンロードセクション
    :::image-end:::  
    
    <!--  
    > [!NOTE] 
    > For more information about test automation using Microsoft Edge (EdgeHTML), see [Microsoft WebDriver for Microsoft Edge (EdgeHTML)][Webdriver].  
    -->  

## WebDriver 言語バインドの選択  

ダウンロードする必要がある最後のコンポーネントは、コード \(Python、 Java、 C\#, Ruby、 JavaScript\) を、Microsoft Edge \(Chromium\)でMicrosoft Edge ドライバーが実行するコマンドに変換するための言語固有のクライアント ドライバーです。  

[選択した WebDriver 言語バインドをダウンロードします][SeleniumDownloads]。  Microsoft Edge チームは、Microsoft Edge \ (Chromium \) をサポートしているため、 [Selenium 4.00-alpha05][NugetPackagesSeleniumWebdriver400alpha05] 以降をお勧めします。  ただし、現在の安定した Selenium 3 リリースを含む、Selenium のすべての旧バージョンで Microsoft Edge \ (Chromium \) を制御することができます。  

> [!IMPORTANT]
> 以前に `ChromeDriver` と `ChromeOptions`を使って Microsoft Edge \ (Chromium \) の自動化またはテストを行ったことがある場合、WebDriver コードは Microsoft Edge バージョン 80 以降では実行されません。  この問題を解決するには、テストを更新して`EdgeOptions`クラスを使用して、 [Microsoft Edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriver]をインストールします。  

### Selenium 3 を使用する  

既に [Selenium 3][|::ref1::|] を使用している場合は、既存のブラウザーのテストがあり、Selenium のバージョンを変更せずに Microsoft Edge \ (Chromium \) のカバレッジを追加することを希望するかもしれません。  [Selenium 3][|::ref2::|] を使用して Microsoft Edge  \ (EdgeHTML \) と Microsoft Edge \ (Chromium \) の自動テストを作成するには更新されたドライバーを使用するために、[Microsoft Edge 用 Selenium ツール][GithubMicrosoftEdgeSeleniumTools] のパッケージをインストールします。  ツールに含まれている`EdgeDriver` と `EdgeDriverService` のクラスは、Selenium 4 の組み込みの対応物と完全互な換性があります。  

次の手順を使用して、[Microsoft Edge 用Selenium ツール][GithubMicrosoftEdgeSeleniumTools] と [Selenium 3][|::ref3::|] をプロジェクトに追加します。

#### [C#](#tab/c-sharp/)  

<a id="selenium-tools-install"></a>  

[NUGET CLI][NugetCLI] または [Visual Studio][VisualStudio] を使用して、 [Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools] と[Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410] の各パッケージを .NET projectに追加します。  

#### [Python](#tab/python/)  

<a id="selenium-tools-install"></a>  

[pip][PythonPip] を使用して[msedge-selenium-tools][PythonSeleniumTools] および [selenium][PythonSelenium] パッケージをインストールします。  

```python
pip install msedge-selenium-tools selenium==3.141
```  

#### [JavaScript](#tab/javascript/)  

<a id="selenium-tools-install"></a>  

[npm][JavaScript|::ref4::|] を使用して、[edge-selenium-tools][JavaScriptSeleniumTools] および [selenium-webdriver][JavaScriptSelenium] パッケージをインストールします。  

```javascript
npm install @microsoft/edge-selenium-tools selenium-webdriver
```  

* * *  

## WebDriver で Microsoft Edge (Chromium) を使用する

Selenium 3 または 4 のいずれかを使用して、次の例を実行できます。  Selenium 3 で使用するには、[Microsoft Edge用 Selenium Tools][GithubMicrosoftEdgeSeleniumTools] をインストールする必要があります。  

### 基本的な使用方法  

Microsoft Edge \ (EdgeHTML \) を使用するには、`EdgeDriver` クラスの既定のインスタンスを作成 します。  

#### [C#](#tab/c-sharp/)  

<a id="basic-usage-code"></a>  

```csharp
var driver = new EdgeDriver();
```  

#### [Python](#tab/python/)  

<a id="basic-usage-code"></a>  

```python
driver = Edge()
```  

#### [JavaScript](#tab/javascript/)  

<a id="basic-usage-code"></a>  

```javascript
let driver = edge.Driver.createSession();
```  

* * *  

### Microsoft Edge のドライブ (Chromium)  

Microsoft Edge \ (Chromium \) を使用するには、新しい `EdgeDriver` クラスを作成し、 それを`UseChromium` プロパティが`true` にセットされた`EdgeOptions` オブジェクトに渡します。  

#### [C#](#tab/c-sharp/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### [Python](#tab/python/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options)
```  

#### [JavaScript](#tab/javascript/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);

let driver = edge.Driver.createSession(options);
```  

* * *  

> [!NOTE]
> IT 管理者が [DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability] ポリシーを `2` に設定している場合、[Microsoft Edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriver] は[Microsoft Edge (Chromium)][MicrosoftEdge] をドライブできません。なぜなら、ドライバーは[Microsoft Edge DevTools][DevToolsMain]を使用しているからです。  [Microsoft Edge (Chromium)][MicrosoftEdge] を自動化するために、[DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability] ポリシーが`0` または `1` に設定されていることを確認します。  

### 特定のブラウザーのバイナリを選択する (Chromium のみ)  

`EdgeOptions` クラスを Microsoft Edge \ (Chromium \) の特定のバイナリで使うことができます。  たとえば、Microsoft Edge ベータ版などの [Microsoft Edge preview チャネル][MicrosoftedgeinsiderDownload] を使用してテストを実行できます。  

#### [C#](#tab/c-sharp/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### [Python](#tab/python/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options)
```  

#### [JavaScript](#tab/javascript/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.setBinaryPath("C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe");

let driver = edge.Driver.createSession(options);
```  

* * *  

### Microsoft Edge ドライバー サービスをカスタマイズする  

#### [C#](#tab/c-sharp/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

`EdgeDriver` クラス インスタンスが`EdgeOptions` クラスを使用して作成されると、Microsoft Edge \ (EdgeHTML \) または Microsoft Edge \ (Chromium \) のいずれかのために、適切な`EdgeDriverService` クラスが作成されて起動します。  

`EdgeDriverService` を作成する場合は`CreateChromiumService()`メソッドを使用して Microsoft Edge \ (Chromium \) 用に構成されたものを作成します。  以下のコードで、冗長ログ出力を有効にするなど、追加のカスタマイズに役立つ場合があります。  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE] 
>`EdgeDriver`インスタンスに `EdgeDriverService` を渡すときに、`EdgeOptions`オブジェクトを指定する必要はありません。 この `EdgeDriver` クラスは、提供するサービスに応じて、Microsoft Edge \ (EdgeHTML \) または MicrosoftEdge \ (Chromium) のいずれかの既定のオプションを使用します。  
> ただし、`EdgeDriverService` と `EdgeOptions` 両方のクラスを提供する場合は、 両方が同じバージョンの Microsoft Edge に対して構成されていることを確認します。  たとえば、既定の Microsoft Edge \ (EdgeHTML \)`EdgeDriverService` クラスと `EdgeOptions` のクラスのChromium プロパティを使うことはできません  。  この `EdgeDriver` クラスは、異なるバージョンの使用を防ぐためにエラーをスローします。  

#### [Python](#tab/python/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

Python を使っている場合、`Edge` オブジェクトは`EdgeService` を作成して管理します。  `EdgeService` を構成するには、次のコードで示されているように、`Edge` のオブジェクトに追加の引数を渡します。  

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### [JavaScript](#tab/javascript/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

JavaScript を使っている場合は、`Service` を`ServiceBuilder` クラスで作成して構成します。  任意で、`Service` オブジェクトを`Driver` オブジェクトに渡すことができます。それによって、サービスが開始\(および 停止\) します。  
`Service` を構成するには、`build()`メソッドを使用する前に、`ServiceBuilder` クラスの追加のメソッドを実行します。  次に、`Driver.createSession()` メソッドのパラメーターとして`service` を渡し ます。  

```javascript
let service = new edge.ServiceBuilder().enableVerboseLogging().build();
let driver = edge.Driver.createSession(options, service);
```  

* * *  

### Chromium-固有 のオプションを使用する  

`UseChromium`プロパティを `true` に設定した場合は、他の Chromium ブラウザーを自動化するときのように`EdgeOptions` クラスを使用して、同じ[Chromium 固有のプロパティやメソッド][SeleniumWebDriverChromeoptionsClass]にアクセスできます。  

#### [C#](#tab/c-sharp/)  

<a id="using-chromium-specific-options-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### [Python](#tab/python/)  

<a id="using-chromium-specific-options-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument("headless")
options.add_argument("disable-gpu")
```  

#### [JavaScript](#tab/javascript/)  

<a id="using-chromium-specific-options-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.addArguments("headless");
options.addArguments("disable-gpu");
```

* * *  

> [!NOTE]
> `UseChromium`プロパティが`true` に設定されている場合は、Microsoft Edge \ (EdgeHTML \) のプロパティとメソッドは使用できません。  

## その他の WebDriver のインストール オプション  

### Chocolatey  

パッケージ マネージャーとして [Chocolatey][Chocolatey] を使用している場合は、次のコマンドを実行して Microsoft Edge ドライバーをインストールします。  

```console
choco install selenium-chromium-edge-driver
```  

詳細については、「[Chocolatey の Selenium Chromium Edge ドライバー][ChocolateyPackagesSeleniumChromiumEdgeDriver]」を参照してください。  

### Docker  

[Docker][DockerHub] を使用している場合は、次のコマンドを実行して、Microsoft Edge\ (Chromium \) と[Microsoft Edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriver] が事前インストールされている事前構成済みイメージをダウンロードします。  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

詳細については、「[Docker Hub のコンテナー][DockerHubMsedgedriver]」を参照してください。  

## Microsoft Edge DevTools チームと連絡を取る  

Microsoft Edge チームは、WebDriver、Selenium、Microsoft Edge の使用に関するフィードバックをお待ちしております。  チームに自分の意見を伝えるには、Microsoft Edge DevTools で [**フィードバックの送信**] アイコンを選択するか、[@EdgeDevTools][TwitterTweetEdgeDevTools] にツイート を送信します。  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン  
:::image-end:::  

<!-- links -->  

[DevToolsMain]: ../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"
[Webdriver]: ../webdriver/index.md "WebDriver (EdgeHTML) |Microsoft ドキュメント"  

[DeployedgePoliciesDevelopertoolsavailability]: /deployedge/microsoft-edge-policies#developertoolsavailability "DeveloperToolsAvailability-Microsoft Edge-ポリシー |Microsoft ドキュメント"  

[Chocolatey]: https://chocolatey.org "Chocolatey |Chocolatey ソフトウェア"  
[ChocolateyPackagesSeleniumChromiumEdgeDriver]: https://chocolatey.org/packages/selenium-chromium-edge-driver "Selenium Chromium Edge ドライバー |Chocolatey"  

[DockerHub]: https://hub.docker.com "Docker Hub"  
[DockerHubMsedgedriver]: https://hub.docker.com/_/microsoft-msedge-msedgedriver?tab=description "msedgedriver |Docker hub"  

[GithubMicrosoftEdgeSeleniumTools]: https://github.com/microsoft/edge-selenium-tools "microsoft/edge-selenium-tools |GitHub"  
[GithubSeleniumHq]: https://github.com/SeleniumHQ/selenium "SeleniumHQ/selenium |GitHub"  

[JavaScriptnpm]: https://www.npmjs.com/ "npm"  
[JavaScriptSeleniumTools]: https://www.npmjs.com/package/@microsoft/edge-selenium-tools "@microsoft/edge-selenium-tools |npm"  
[JavaScriptSelenium]: https://www.npmjs.com/package/selenium-webdriver "selenium-webdriver |npm"  

[MicrosoftDeveloperEdgeToolsWebdriver]: https://developer.microsoft.com/microsoft-edge/tools/webdriver "WebDriver |Microsoft 開発者"  
[MicrosoftDeveloperEdgeToolsWebdriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver/#downloads "ダウンロード-WebDriver |Microsoft 開発者"  

[MicrosoftEdge]: https://www.microsoft.com/edge "新しい Microsoft Edge ブラウザーをダウンロードする"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  

[NugetCLI]:https://www.nuget.org/packages/NuGet.CommandLine/ "NuGet.CommandLine |NuGet ギャラリー"  
[NugetPackagesMicrosoftEdgeSeleniumtools]: https://www.nuget.org/packages/Microsoft.Edge.SeleniumTools "Microsoft.Edge.SeleniumTools |NuGet ギャラリー"  
[NugetPackagesSeleniumWebdriver31410]: https://www.nuget.org/packages/Selenium.WebDriver/3.141.0 "Selenium.WebDriver 3.141.0 |NuGet ギャラリー"  
[NugetPackagesSeleniumWebdriver400alpha05]: https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-alpha05 "Selenium.WebDriver 4.0.0-alpha05 |NuGet ギャラリー"  

[PythonPip]: https://pypi.org/project/pip/ "pip |PyPI"  
[PythonSeleniumTools]: https://pypi.org/project/msedge-selenium-tools/ "msedge-selenium-tools |PyPI"  
[PythonSelenium]: https://pypi.org/project/selenium/ "selenium |PyPI"

[SeleniumHQ]: https://www.selenium.dev "SeleniumHQ"  
[SeleniumDownloads]: https://selenium.dev/downloads "ダウンロード |Selenium"  
[SeleniumWebDriverChromeoptionsClass]: https://www.selenium.dev/selenium/docs/api/dotnet/?topic=html/T_OpenQA_Selenium_Chrome_ChromeOptions.htm "ChromeOptions Class-WebDriver |Selenium"  

[TwitterTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |ツイートを投稿する"  

[VisualStudio]: https://visualstudio.microsoft.com/ "Visual Studio"  

[W3CWebdriver]: https://w3.org/TR/webdriver2 "WebDriver |W3C"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "ヘッドレス ブラウザー |Wikipedia"  
