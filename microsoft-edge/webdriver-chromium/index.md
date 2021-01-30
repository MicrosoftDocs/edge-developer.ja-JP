---
description: Microsoft Edge で Web サイトまたはアプリをテストする方法、または WebDriver でブラウザーを自動化する方法について説明します。
title: テスト オートメーションに WebDriver (Chromium) を使用する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/29/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge, web 開発, html, css, javascript, 開発者, webdriver, selenium,テストする, ツール, 自動化, テスト
ms.openlocfilehash: 295985734d93c5912922be22c0af0c0e33e00a54
ms.sourcegitcommit: 070a60f634908eea0e29e260331f9fc0aa85ee78
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2021
ms.locfileid: "11306249"
---
# テスト オートメーションに WebDriver (Chromium) を使用する  

WebDriver を使用すると、開発者はユーザーの操作をシミュレートする自動テストを作成できます。  WebDriver のテストとシミュレーションは、WebDriver が次の理由で JavaScript 単体テストとは異なります。  

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

[選択した WebDriver 言語バインドをダウンロードします][SeleniumDownloads]。  Microsoft Edge チームは、Microsoft Edge \(Chromium\) をサポートしている [Selenium 4.00-alpha07][NugetPackagesSeleniumWebdriver400alpha07] 以降を推奨しています。  ただし、現在の安定した Selenium 3 リリースを含む、Selenium のすべての旧バージョンで Microsoft Edge \ (Chromium \) を制御することができます。  

> [!IMPORTANT]
> 以前に `ChromeDriver` と `ChromeOptions`を使って Microsoft Edge \ (Chromium \) の自動化またはテストを行ったことがある場合、WebDriver コードは Microsoft Edge バージョン 80 以降では実行されません。  この問題を解決するには、クラスを使ってテストを更新し `EdgeOptions` [、Microsoft Edge ドライバーをダウンロードします][MicrosoftDeveloperEdgeToolsWebdriver]。  

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

#### [Java](#tab/java/)  

<a id="selenium-tools-install"></a>  

プロジェクトJava Maven を使用している場合は、次の依存関係をファイルに対処して [msedge-selenium-tools-java][SonatypeMavenRepositorySearch] を追加 `pom.xml` します。  

```xml
<dependency>
    <groupId>com.microsoft.edge</groupId>
    <artifactId>msedge-selenium-tools-java</artifactId>
    <version>[3.141.0,)</version>
</dependency>
```  

The Java package is also available to download directly on the [Selenium Tools for Microsoft Edge Releases page][GithubMicrosoftEdgeSeleniumToolsReleases].  

#### [JavaScript](#tab/javascript/)  

<a id="selenium-tools-install"></a>  

[npm][JavaScript|::ref4::|] を使用して、[edge-selenium-tools][JavaScriptSeleniumTools] および [selenium-webdriver][JavaScriptSelenium] パッケージをインストールします。  

```javascript
npm install @microsoft/edge-selenium-tools selenium-webdriver
```  

* * *  

## WebDriver を使用して Microsoft Edge (Chromium) を自動化する  

WebDriver を使用してブラウザーを自動化するには、優先する WebDriver 言語バインドを使用して WebDriver セッションを最初に開始する必要があります。  セッションは、WebDriver コマンドを使用して制御できるブラウザーの単一の実行中インスタンスです。  WebDriver セッションを開始すると、新しいブラウザー インスタンスが起動します。  WebDriver セッションを閉じるまで、起動されたブラウザーは開いたままです。  

次のコンテンツでは、Selenium を使用して Microsoft Edge \(Chromium\) との WebDriver セッションを開始する方法について説明します。  これらの例は、Selenium 3 または 4 を使用して実行できます。  Selenium 3 で使用するには、[Microsoft Edge用 Selenium Tools][GithubMicrosoftEdgeSeleniumTools] をインストールする必要があります。  

### Microsoft Edge (Chromium) の自動化  

Selenium は、クラス `EdgeDriver` を使用して Microsoft Edge \(Chromium\) セッションを管理します。 セッションを開始し、Microsoft Edge \(Chromium\) を自動化するには、新しいオブジェクトを作成し、プロパティを設定したオブジェクト `EdgeDriver` `EdgeOptions` `UseChromium` を渡します `true` 。  

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

#### [Java](#tab/java/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

この `EdgeDriver` クラスは Microsoft Edge (Chromium) のみをサポートし、Microsoft Edge (EdgeHTML) はサポートされていません。 基本的な使用方法として、指定せずに作成 `EdgeDriver` できます `EdgeOptions` 。  

```java
EdgeDriver driver = new EdgeDriver();
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
> IT 管理者が [DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability] ポリシーを `2` に設定している場合、[Microsoft Edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriver] はMicrosoft Edge (Chromium) をドライブできません。なぜなら、ドライバーは[Microsoft Edge DevTools][DevtoolsIndex]を使用しているからです。  [DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]ポリシーが Microsoft `0` `1` Edge (Chromium) に設定または自動化されている必要があります。  

### 特定のブラウザーのバイナリを選択する (Chromium のみ)  

特定の Microsoft Edge \(Chromium\) バイナリを使用して WebDriver セッションを開始できます。  たとえば、Microsoft Edge ベータ版などの [Microsoft Edge preview チャネル][MicrosoftedgeinsiderDownload] を使用してテストを実行できます。  

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

#### [Java](#tab/java/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.setBinary("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

EdgeDriver driver = new EdgeDriver(options);
```  

#### [JavaScript](#tab/javascript/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.setBinaryPath("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

let driver = edge.Driver.createSession(options);
```  

* * *  

### Microsoft Edge ドライバー サービスをカスタマイズする  

#### [C#](#tab/c-sharp/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

`EdgeDriver` クラス インスタンスが`EdgeOptions` クラスを使用して作成されると、Microsoft Edge \ (EdgeHTML \) または Microsoft Edge \ (Chromium \) のいずれかのために、適切な`EdgeDriverService` クラスが作成されて起動します。  

`EdgeDriverService` を作成する場合は`CreateChromiumService()`メソッドを使用して Microsoft Edge \ (Chromium \) 用に構成されたものを作成します。  カスタマイズを追加する必要がある場合に便利な場合があります。 たとえば、次のコードは詳細ログ出力を開始します。  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE] 
>`EdgeDriver`インスタンスに `EdgeDriverService` を渡すときに、`EdgeOptions`オブジェクトを指定する必要はありません。  この `EdgeDriver` クラスは、提供するサービスに基づいて、Microsoft Edge \(EdgeHTML\) または Microsoft Edge \(Chromium\) の既定のオプションを使用します。  
> ただし、`EdgeDriverService` と `EdgeOptions` 両方のクラスを提供する場合は、 両方が同じバージョンの Microsoft Edge に対して構成されていることを確認します。  たとえば、既定の Microsoft Edge \ (EdgeHTML \)`EdgeDriverService` クラスと `EdgeOptions` のクラスのChromium プロパティを使うことはできません  。  この `EdgeDriver` クラスは、異なるバージョンの使用を防ぐためにエラーをスローします。  

#### [Python](#tab/python/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

Python を使っている場合、`Edge` オブジェクトは`EdgeService` を作成して管理します。  `EdgeService` を構成するには、次のコードで示されているように、`Edge` のオブジェクトに追加の引数を渡します。  

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### [Java](#tab/java/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

このメソッド `createDefaultService()` を使用して `EdgeDriverService` 、Microsoft Edge \(Chromium\) 用に構成された構成を作成します。 ドライバー サービスは、Javaプロパティを使用してJavaカスタマイズされます。 たとえば、次のコードはプロパティを使用 `"webdriver.edge.verboseLogging"` して詳細ログ出力を有効にします。  

```java
System.setProperty("webdriver.edge.verboseLogging", "true");
EdgeDriverService service = EdgeDriverService.createDefaultService();
EdgeOptions options = new EdgeOptions();
EdgeDriver driver = new EdgeDriver(service, options);
```  

#### [JavaScript](#tab/javascript/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

JavaScript を使っている場合は、`Service` を`ServiceBuilder` クラスで作成して構成します。  任意で、`Service` オブジェクトを`Driver` オブジェクトに渡すことができます。それによって、サービスが開始\(および 停止\) します。  
構成するには、 `Service` メソッドを使用する前にクラスで `ServiceBuilder` 別のメソッドを実行 `build()` します。  次に、`Driver.createSession()` メソッドのパラメーターとして`service` を渡し ます。  

```javascript
let service = new edge.ServiceBuilder().enableVerboseLogging().build();
let driver = edge.Driver.createSession(options, service);
```  

* * *  

### Chromium-固有 のオプションを使用する  

プロパティを設定した場合は、他の Chromium ブラウザーを自動化するときに使用されるのと同じ Chromium 固有のプロパティとメソッドにクラスを `UseChromium` `true` `EdgeOptions` 使用してアクセスできます。 [][WebdriverCapabilitiesEdgeOptions]  

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

#### [Java](#tab/java/)  

<a id="using-chromium-specific-options-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.addArguments("headless");
options.addArguments("disable-gpu");
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

詳細については、Docker Hub の [msedgedriver コンテナーに移動します][DockerHubMsedgedriver]。  

## 次のステップ

WebDriver の詳細と、Selenium を使用して自動化された WebDriver テストを作成する方法については [、Selenium のドキュメントに移動してください][SeleniumDocumentation]。  

## Microsoft Edge DevTools チームと連絡を取る  

Microsoft Edge チームは、WebDriver、Selenium、Microsoft Edge の使用に関するフィードバックをお待ちしております。  チームに質問やコメントを送信するには、Microsoft **** Edge DevTools の [フィードバックの送信] アイコンを選択するか、ツイートを送信[@EdgeDevTools。][TwitterTweetEdgeDevTools]  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン  
:::image-end:::  

<!-- links -->  

[DevtoolsIndex]: ../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[WebdriverCapabilitiesEdgeOptions]: ./capabilities-edge-options.md "機能と EdgeOptions |Microsoft Docs"  
<!--[Webdriver]: ../edgehtml/webdriver/index.md "WebDriver (EdgeHTML) | Microsoft Docs"  -->  

[DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]: /deployedge/microsoft-edge-policies#developertoolsavailability "DeveloperToolsAvailability-Microsoft Edge-ポリシー |Microsoft ドキュメント"  

[Chocolatey]: https://chocolatey.org "Chocolatey |Chocolatey ソフトウェア"  
[ChocolateyPackagesSeleniumChromiumEdgeDriver]: https://chocolatey.org/packages/selenium-chromium-edge-driver "Selenium Chromium Edge ドライバー |Chocolatey"  

[DockerHub]: https://hub.docker.com "Docker Hub"  
[DockerHubMsedgedriver]: https://hub.docker.com/_/microsoft-msedge-msedgedriver?tab=description "msedgedriver |Docker hub"  

[GithubMicrosoftEdgeSeleniumTools]: https://github.com/microsoft/edge-selenium-tools "microsoft/edge-selenium-tools |GitHub"  
[GithubMicrosoftEdgeSeleniumToolsReleases]: https://github.com/microsoft/edge-selenium-tools/releases "microsoft/edge-selenium-tools |GitHub"  
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
[NugetPackagesSeleniumWebdriver400alpha07]: https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-alpha07 "Selenium.WebDriver 4.0.0-alpha07 |NuGet ギャラリー"  

[PythonPip]: https://pypi.org/project/pip/ "pip |PyPI"  
[PythonSeleniumTools]: https://pypi.org/project/msedge-selenium-tools/ "msedge-selenium-tools |PyPI"  
[PythonSelenium]: https://pypi.org/project/selenium/ "selenium |PyPI"

[SeleniumHQ]: https://www.selenium.dev "SeleniumHQ"  
[SeleniumDocumentation]: https://www.selenium.dev/documentation "Selenium Browser Automation Project :: Selenium のドキュメント"  
[SeleniumDownloads]: https://selenium.dev/downloads "ダウンロード |Selenium"  

[SonatypeMavenRepositorySearch]: https://search.maven.org/artifact/com.microsoft.edge/msedge-selenium-tools-java/3.141.0/jar "sonatype Maven Central Repository Search |com.microsoft.edge:msedge-selenium-tools-java"

[TwitterTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |ツイートを投稿する"  

[VisualStudio]: https://visualstudio.microsoft.com/ "Visual Studio"  

[W3CWebdriver]: https://w3.org/TR/webdriver2 "WebDriver |W3C"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "ヘッドレス ブラウザー |Wikipedia"  
