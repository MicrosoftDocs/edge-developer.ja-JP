---
description: Microsoft Edge で web サイトまたはアプリをテストする方法、または WebDriver でブラウザーを自動化する方法について説明します。
title: WebDriver (Chromium)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/08/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 開発、html、css、javascript、開発者、webdriver、selenium、テスト、ツール、オートメーション、テスト
ms.openlocfilehash: c60095373be337307225f28d320cae19174531a7
ms.sourcegitcommit: 1b5dfc5a2c7130b3abc6b4545fcaaae0b0897148
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "10757581"
---
# テストオートメーションに WebDriver (Chromium) を使用する  

WebDriver を使うと、開発者は、ユーザーの操作をシミュレートする自動テストを作成できます。  WebDriver のテストとシミュレーションは、次の理由から、JavaScript 単体テストとは異なります。 
*   ブラウザーで実行されている JavaScript では利用できない機能と情報にアクセスします。  
*   ユーザーイベントや OS レベルのイベントをより正確にシミュレートします。  
*   単一のテストセッションで複数のウィンドウ、タブ、web ページ間のテストを管理します。  
*   特定のコンピューターで Microsoft Edge の複数のセッションを実行します。  

次のセクションでは、Microsoft Edge \ (Chromium \) の WebDriver の使用を開始する方法について説明します。  

## Microsoft Edge をインストールする (Chromium)  

[Microsoft Edge (Chromium)][MicrosoftEdge]をインストールしていることを確認します。  Microsoft Edge (Chromium) がインストールされていることを確認するには、ブラウザーでに移動して、 `edge://settings/help` バージョン番号がバージョン75以降であることを確認します。  

## Microsoft Edge ドライバーをダウンロードする  

テストの自動化を開始するには、次の手順を使用して、インストールした WebDriver のバージョンがお使いのブラウザーのバージョンと一致していることを確認します。  

1.  「 `edge://settings/help` Edge のバージョンを取得する」に移動します。  
    
    :::image type="complex" source="./media/webdriver-chromium/edge-version.png" alt-text="2020年1月14日の Microsoft Edge カナリアのビルド番号":::
       図 1.   2020年1月14日の Microsoft Edge カナリアのビルド番号
    :::image-end:::  
    
1.  [Microsoft Edge ドライバーのダウンロード][MicrosoftDeveloperEdgeToolsWebdriverDownloads]ページに移動して、Edge のバージョン番号と一致するドライバーをダウンロードします。  
    
    :::image type="complex" source="./media/webdriver-chromium/edge-driver-install.png" alt-text="Microsoft Edge ドライバーページのダウンロードセクション":::
       図 2.   [Microsoft Edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriver]ページのダウンロードセクション
    :::image-end:::  
    
    > [!NOTE] 
    > Microsoft Edge (EdgeHTML) を使用したテストオートメーションの詳細については、「microsoft [edge 用 Microsoft WebDriver (EdgeHTML)][Webdriver]」を参照してください。  

## WebDriver 言語バインドの選択  

ダウンロードする必要がある最後のコンポーネントは、コード \ (Python、Java、C \ #、ルビ、JavaScript \ #、ルビ、JavaScript \ #、ルビ、JavaScript \) をコマンドに変換するための言語固有のクライアントドライバーです。 microsoft edge ドライバーは Microsoft Edge \ (Chromium \) で実行されます。  

[選択した WebDriver 言語バインドをダウンロード][SeleniumDownloads]します。  Microsoft edge チームは、Microsoft Edge \ (Chromium \) をサポートしているため、 [Selenium 4.00 alpha05][NugetPackagesSeleniumWebdriver400alpha05]以降をお勧めします。  ただし、現在の厩舎 Selenium 3 リリースを含む、Selenium のすべての旧バージョンで Microsoft Edge \ (Chromium \) を制御することができます。  

> [!IMPORTANT]
> 以前に Microsoft Edge \ (Chromium \) とクラスを使って自動化またはテストしている場合 `ChromeDriver` `ChromeOptions` 、webdriver コードは Microsoft Edge バージョン80以降では実行されません。  この問題を解決するには、クラスを使用するようにテストを更新 `EdgeOptions` し、 [Microsoft Edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriver]をインストールします。  

### Selenium 3 を使用する  

既に[Selenium 3][|::ref1::|]を使用している場合は、既存のブラウザーのテストが完了している可能性があります。また、Selenium のバージョンを変更せずに Microsoft Edge \ (Chromium \) のカバレッジを追加することもできます。  [Selenium 3][|::ref2::|]を使用して microsoft edge \ (EdgeHTML \) と microsoft edge \ (Chromium \) の自動テストを作成するには、更新されたドライバーを使用するために、 [microsoft Edge パッケージの Selenium Tools][GithubMicrosoftEdgeSeleniumTools]をインストールします。  `EdgeDriver` `EdgeDriverService` ツールに含まれているクラスとクラスは、Selenium 4 の組み込みの対応物と完全に互換性があります。  

次の手順を使用して、Microsoft Edge と[Selenium 3][|::ref3::|] [用の Selenium Tools][GithubMicrosoftEdgeSeleniumTools]をプロジェクトに追加します。

#### [C#](#tab/c-sharp/)  

<a id="selenium-tools-install"></a>  

[NUGET CLI][NugetCLI]または[Visual Studio][VisualStudio]を使用して、 [SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools]と[Selenium][NugetPackagesSeleniumWebdriver31410]の各パッケージを .net プロジェクトに追加します。

#### [Python](#tab/python/)  

<a id="selenium-tools-install"></a>  

[Pip][PythonPip]を使用して[msedge-selenium ツール][PythonSeleniumTools]と[selenium][PythonSelenium]パッケージをインストールします。

```python
pip install msedge-selenium-tools selenium==3.141
```  

#### [JavaScript](#tab/javascript/)  

<a id="selenium-tools-install"></a>  

[Npm][JavaScript|::ref4::|]を使用して、[エッジ-selenium ツール][JavaScriptSeleniumTools]と[selenium ドライバー][JavaScriptSelenium]パッケージをインストールします。

```javascript
npm install @microsoft/edge-selenium-tools selenium-webdriver
```  

* * *  

## WebDriver で Microsoft Edge (Chromium) を使用する

Selenium 3 または4のいずれかを使用して、次の例を実行できます。  Selenium 3 で使用するには、 [Microsoft Edge パッケージの Selenium ツール][GithubMicrosoftEdgeSeleniumTools]をインストールする必要があります。  

### 基本的な使用方法  

Microsoft Edge \ (EdgeHTML \) で使用するには、クラスの既定のインスタンスを作成するだけです `EdgeDriver` 。

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

### Microsoft Edge の推進 (Chromium)  

Microsoft Edge \ (Chromium \) で使用するには、新しい `EdgeDriver` クラスを作成し、 `EdgeOptions` プロパティが set に設定されたオブジェクトを渡し `UseChromium` `true` ます。  

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
> [DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability]ポリシーがに設定されている場合 `2` 、ドライバーは[microsoft edge devtools][DevToolsMain]を使用しているため、Microsoft edge[ドライバー][MicrosoftDeveloperEdgeToolsWebdriver]は[microsoft edge (Chromium)][MicrosoftEdge]を実行できません。  [DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability] `0` `1` [Microsoft Edge (Chromium)][MicrosoftEdge]に DeveloperToolsAvailability ポリシーを設定していることを確認します。  

### 特定のブラウザーのバイナリを選択する (Chromium のみ)  

このクラスは、 `EdgeOptions` Microsoft Edge (Chromium) の特定のバイナリで使うことができます。  たとえば、microsoft Edge ベータ版などの[Microsoft edge preview チャネル][MicrosoftedgeinsiderDownload]を使用してテストを実行できます。  

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

### Microsoft Edge Driver サービスをカスタマイズする  

#### [C#](#tab/c-sharp/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

クラス `EdgeDriver` インスタンスがクラスを使用して作成されると `EdgeOptions` 、 `EdgeDriverService` microsoft Edge \ (EdgeHTML \) または microsoft Edge \ (Chromium \) のいずれかに適切なクラスが作成されて起動します。  

を作成する場合は `EdgeDriverService` 、メソッドを使用して Microsoft Edge \ (Chromium \) 用に構成されたものを作成し `CreateChromiumService()` ます。  以下のコードでは、冗長ログ出力を有効にするなど、追加のカスタマイズに役立つ場合があります。  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE] 
>`EdgeOptions`インスタンスに渡すときに、オブジェクトを指定する必要はありません `EdgeDriverService` `EdgeDriver` 。 この `EdgeDriver` クラスは、提供するサービスに応じて、Microsoft edge \ (EdgeHTML \) または Microsoft edge \ (Chromium) のいずれかの既定のオプションを使用します。  
> ただし、両方のクラスを提供する場合は、 `EdgeDriverService` `EdgeOptions` 両方が同じバージョンの Microsoft Edge に対して構成されていることを確認します。  たとえば、既定の Microsoft Edge (EdgeHTML) `EdgeDriverService` クラスと Chromium プロパティをクラスで使うことはできません `EdgeOptions` 。  この `EdgeDriver` クラスは、異なるバージョンの使用を防ぐためにエラーをスローします。  

#### [Python](#tab/python/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

Python を使っている場合、オブジェクトはを `Edge` 作成して管理し `EdgeService` ます。  を構成するには `EdgeService` 、 `Edge` 次のコードで示されているように、追加の引数をオブジェクトに渡します。  

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### [JavaScript](#tab/javascript/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

JavaScript を使っている場合は、クラスでを作成して構成し `Service` `ServiceBuilder` ます。  必要に応じて、 `Service` `Driver` サービスを開始して停止するオブジェクトにオブジェクトを渡すことができます。  
を構成するには `Service` 、 `ServiceBuilder` メソッドを使用する前に、クラスの追加のメソッドを実行し `build()` ます。  次に、 `service` メソッドのパラメーターとしてを渡し `Driver.createSession()` ます。  

```javascript
let service = new edge.ServiceBuilder().enableVerboseLogging().build();
let driver = edge.Driver.createSession(options, service);
```  

* * * 

### Chromium 固有のオプションを使用する  

`UseChromium`プロパティをに設定すると `true` 、 `EdgeOptions` 他の Chromium ブラウザーを自動化したときと同じ[Chromium 固有のプロパティやメソッド][SeleniumWebDriverChromeoptionsClass]に、このクラスを使ってアクセスできます。  

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
> `UseChromium`プロパティがに設定されている場合 `true` は、Microsoft Edge \ (EdgeHTML \) のプロパティとメソッドは使用できません。  

## その他の WebDriver のインストールオプション  

### Chocolatey  

パッケージマネージャーとして[Chocolatey][Chocolatey]を使用している場合は、次のコマンドを実行して Microsoft Edge ドライバーをインストールします。  

```console
choco install selenium-chromium-edge-driver
```  

詳細については、「 [Chocolatey の Selenium Chromium Edge ドライバー][ChocolateyPackagesSeleniumChromiumEdgeDriver]」を参照してください。  

### Docker  

[Docker][DockerHub]を使用している場合は、次のコマンドを実行して、microsoft edge \ (Chromium \) と[microsoft edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriver]がプレインストールされている事前構成済みイメージをダウンロードします。  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

詳細については、「 [Docker Hub のコンテナー][DockerHubMsedgedriver]」を参照してください。  

## Microsoft Edge DevTools チームと連絡を取り合う  

Microsoft Edge チームは、WebDriver、Selenium、Microsoft Edge の使用に関するフィードバックをお寄せください。  Microsoft Edge DevTools またはツイート[@EdgeDevTools][TwitterTweetEdgeDevTools]の**フィードバック**アイコンを使用して、チームに自分の意見を伝えます。  


:::image type="complex" source="./devtools-guide-chromium/media/devtools-feedback.png" alt-text="Microsoft Edge DevTools のフィードバックアイコン":::
   Microsoft Edge DevTools の**フィードバック**アイコン  
:::image-end:::  

<!-- image links -->  

<!-- links -->  

[DevToolsMain]: ./devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"
[Webdriver]: ./webdriver.md "WebDriver (EdgeHTML) |Microsoft ドキュメント"  

[DeployedgePoliciesDevelopertoolsavailability]: /deployedge/microsoft-edge-policies#developertoolsavailability "DeveloperToolsAvailability-Microsoft Edge-ポリシー |Microsoft ドキュメント"  

[Chocolatey]: https://chocolatey.org "Chocolatey |Chocolatey ソフトウェア"  
[ChocolateyPackagesSeleniumChromiumEdgeDriver]: https://chocolatey.org/packages/selenium-chromium-edge-driver "Selenium Chromium Edge Driver |Chocolatey"  

[DockerHub]: https://hub.docker.com "Docker Hub"  
[DockerHubMsedgedriver]: https://hub.docker.com/_/microsoft-msedge-msedgedriver?tab=description "msedgedriver |Docker hub"  

[GithubMicrosoftEdgeSeleniumTools]: https://github.com/microsoft/edge-selenium-tools "microsoft/edge-selenium-ツール |GitHub"  
[GithubSeleniumHq]: https://github.com/SeleniumHQ/selenium "SeleniumHQ/selenium |GitHub"  

[JavaScriptnpm]: https://www.npmjs.com/ "npm"
[JavaScriptSeleniumTools]: https://www.npmjs.com/package/@microsoft/edge-selenium-tools "@microsoft/edge-selenium-tools |npm"
[JavaScriptSelenium]: https://www.npmjs.com/package/selenium-webdriver "selenium-webdriver |npm"

[MicrosoftDeveloperEdgeToolsWebdriver]: https://developer.microsoft.com/microsoft-edge/tools/webdriver "WebDriver |Microsoft 開発者"
[MicrosoftDeveloperEdgeToolsWebdriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver/#downloads "ダウンロード-WebDriver |Microsoft 開発者"  

[MicrosoftEdge]: https://www.microsoft.com/edge "新しい Microsoft Edge ブラウザーをダウンロードする"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  

[NugetCLI]:https://www.nuget.org/packages/NuGet.CommandLine/ "Nuget.exe: CommandLine |NuGet ギャラリー"
[NugetPackagesMicrosoftEdgeSeleniumtools]: https://www.nuget.org/packages/Microsoft.Edge.SeleniumTools "SeleniumTools |NuGet ギャラリー"  
[NugetPackagesSeleniumWebdriver31410]: https://www.nuget.org/packages/Selenium.WebDriver/3.141.0 "Selenium ドライバー 3.141.0 |NuGet ギャラリー"  
[NugetPackagesSeleniumWebdriver400alpha05]: https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-alpha05 "Selenium ドライバー 4.0.0-alpha05 |NuGet ギャラリー"  

[PythonPip]: https://pypi.org/project/pip/ "pip |PyPI"
[PythonSeleniumTools]: https://pypi.org/project/msedge-selenium-tools/ "msedge-selenium-ツール |PyPI"
[PythonSelenium]: https://pypi.org/project/selenium/ "selenium |PyPI"

[SeleniumHQ]: https://www.selenium.dev "SeleniumHQ"  
[SeleniumDownloads]: https://selenium.dev/downloads "ダウンロード |Selenium"  
[SeleniumWebDriverChromeoptionsClass]: https://www.selenium.dev/selenium/docs/api/dotnet/?topic=html/T_OpenQA_Selenium_Chrome_ChromeOptions.htm "ChromeOptions Class-WebDriver |Selenium"  

[TwitterTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |ツイートを投稿する"  

[VisualStudio]: https://visualstudio.microsoft.com/ "Visual Studio"

[W3CWebdriver]: https://w3.org/TR/webdriver2 "WebDriver"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "ヘッドレスブラウザー |Wikipedia"  
