---
description: Microsoft Edge で Web サイトまたはアプリをテストする方法、または WebDriver を使用してブラウザーを自動化する方法について説明します。
title: テスト オートメーションに WebDriver (Chromium) を使用する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge, web 開発, html, css, javascript, 開発者, webdriver, selenium,テストする, ツール, 自動化, テスト
ms.openlocfilehash: b3b8a4ef2174c7f313fe9ee71bedbdf5e2f9b771
ms.sourcegitcommit: f95812c4e1b7277f67c6c4891be2779cc1b5bdf1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "11343795"
---
# テスト オートメーションに WebDriver (Chromium) を使用する  

WebDriver を使用すると、開発者はユーザーの操作をシミュレートする自動テストを作成できます。  WebDriver のテストとシミュレーションは、次の点で JavaScript 単体テストとは異なります。  

*   ブラウザーで実行されている JavaScript では利用できない機能と情報にアクセスします。  
*   ユーザー イベントや OS レベルのイベントをより正確にシミュレートします。  
*   1 回のテスト セッションで、複数のウィンドウ、タブ、Web ページを管理します。  
*   特定のコンピューターで Microsoft Edge の複数のセッションを実行します。  
    
次のセクションでは、Microsoft Edge \ (Chromium \) の WebDriver の使用を開始する方法について説明します。  

## Microsoft Edge (Chromium) をインストールする  

[Microsoft Edge (Chromium)][MicrosoftEdge] を確実にインストールしてください。  Microsoft Edge \(Chromium\) がインストールされていることを確認するには、バージョン番号がバージョン 75 以降に移動して `edge://settings/help` 確認します。  

## Microsoft Edge ドライバーをダウンロードする  

テストの自動化を開始するには、次の手順を使用して、インストールする WebDriver のバージョンがお使いのブラウザーのバージョンと一致していることを確認します。  

1.  Microsoft Edge のバージョンを表示するには、次に移動します `edge://settings/help` 。  
    
    :::image type="complex" source="./media/microsoft-edge-version.msft.png" alt-text="2021 年 2 月 10 日の Microsoft Edge Canary のビルド番号" lightbox="./media/microsoft-edge-version.msft.png":::
       2021 年 2 月 10 日の Microsoft Edge Canary のビルド番号  
    :::image-end:::  
    
1.  [[ダウンロード] セクションの][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]Microsoft **** Edge ドライバーに移動し、Microsoft Edge のバージョン番号と一致する WebDriver をダウンロードします。  
    
    :::image type="complex" source="./media/microsoft-edge-driver-install.msft.png" alt-text="Microsoft Edge ドライバーの [ダウンロード] セクション" lightbox="./media/microsoft-edge-driver-install.msft.png":::
       Microsoft Edge **ドライバー** の [[ダウンロード] セクション][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]  
    :::image-end:::  
    
    <!--  
    > [!NOTE] 
    > For more information about test automation using Microsoft Edge \(EdgeHTML\), navigate to [Microsoft Edge Driver for Microsoft Edge \(EdgeHTML\)][Webdriver].  
    -->  

## WebDriver 言語バインドの選択  

ダウンロードする必要がある最後のコンポーネントは、コード \(Python、 Java、 C\#, Ruby、 JavaScript\) を、Microsoft Edge \(Chromium\)でMicrosoft Edge ドライバーが実行するコマンドに変換するための言語固有のクライアント ドライバーです。  

[選択した WebDriver 言語バインドをダウンロードします][SeleniumDownloads]。  Microsoft Edge チームは、Microsoft Edge \(Chromium\) をサポートしている [Selenium 4.00-alpha07][NugetPackagesSeleniumWebdriver400alpha07] 以降を推奨しています。  ただし、現在の安定した Selenium 3 リリースを含む、Selenium のすべての旧バージョンで Microsoft Edge \ (Chromium \) を制御することができます。  

> [!IMPORTANT]
> 以前に Microsoft Edge \(Chromium\) の使用とクラスを自動化またはテストした場合 `ChromeDriver` `ChromeOptions` 、WebDriver コードは Microsoft Edge Version 80 以降では実行されません。  この問題を解決するには、クラスを使ってテストを更新し `EdgeOptions` [、Microsoft Edge ドライバーをダウンロードします][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]。  

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

If your Java project uses Maven, copy and paste the following dependency to your `pom.xml` file to add [msedge-selenium-tools-java][SonatypeMavenRepositorySearch].  

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

WebDriver を使用してブラウザーを自動化するには、優先する WebDriver 言語バインドを使用して WebDriver セッションを最初に開始する必要があります。  セッションは、WebDriver コマンドを使用して制御されるブラウザーの単一の実行中インスタンスです。  WebDriver セッションを開始して、新しいブラウザー インスタンスを起動します。  起動されたブラウザー インスタンスは、WebDriver セッションを閉じるまで開いたままです。  

次のコンテンツでは、Selenium を使用して Microsoft Edge \(Chromium\) との WebDriver セッションを開始する方法について説明します。  この例は、Selenium 3 または 4 を使用して実行できます。  Selenium 3 で使用するには、[Microsoft Edge用 Selenium Tools][GithubMicrosoftEdgeSeleniumTools] をインストールする必要があります。  

### Microsoft Edge (Chromium) を自動化する  

Selenium は、クラス `EdgeDriver` を使用して Microsoft Edge \(Chromium\) セッションを管理します。  セッションを開始し、Microsoft Edge \(Chromium\) を自動化するには、新しいオブジェクトを作成し、プロパティを設定したオブジェクト `EdgeDriver` `EdgeOptions` `UseChromium` を渡します `true` 。  

#### [C#](#tab/c-sharp/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### [Python](#tab/python/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options)
```  

#### [Java](#tab/java/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

この `EdgeDriver` クラスは Microsoft Edge \(Chromium\) のみをサポートし、Microsoft Edge \(EdgeHTML\) をサポートします。  基本的な使用方法として、指定せずに作成 `EdgeDriver` できます `EdgeOptions` 。  

```java
EdgeDriver driver = new EdgeDriver();
```  

#### [JavaScript](#tab/javascript/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);

let driver = edge.Driver.createSession(options);
```  

* * *  

> [!NOTE]
> IT 管理者が [DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability] ポリシーを設定している場合、ドライバーは Microsoft Edge DevTools を使うので `2`  [、Microsoft Edge][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] ドライバーは Microsoft [Edge][DevtoolsIndex]\(Chromium\) の駆動をブロックされます。  [DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]ポリシーが Microsoft `0` `1` Edge (Chromium) に設定または自動化されている必要があります。  

### 特定のブラウザー バイナリを選択する (Chromium のみ)  

特定の Microsoft Edge \(Chromium\) バイナリを使用して WebDriver セッションを開始できます。  たとえば、Microsoft Edge ベータ版などの [Microsoft Edge preview チャネル][MicrosoftedgeinsiderDownload] を使用してテストを実行できます。  

#### [C#](#tab/c-sharp/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### [Python](#tab/python/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options)
```  

#### [Java](#tab/java/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.setBinary("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

EdgeDriver driver = new EdgeDriver(options);
```  

#### [JavaScript](#tab/javascript/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.setBinaryPath("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

let driver = edge.Driver.createSession(options);
```  

* * *  

### Microsoft Edge Driver Service をカスタマイズする  

#### [C#](#tab/c-sharp/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

クラスを使用してクラス インスタンスを作成すると `EdgeOptions` `EdgeDriver` `EdgeDriverService` 、Microsoft Edge \(EdgeHTML\) または Microsoft Edge \(Chromium\) の適切なクラスが作成され、起動されます。  

作成する場合は、このメソッドを使用して `EdgeDriverService` `CreateChromiumService()` 、Microsoft Edge \(Chromium\) 用に構成されたメソッドを作成します。  この `CreateChromiumService()` メソッドは、カスタマイズを追加する必要がある場合に便利です。  たとえば、次のコードは詳細ログ出力を開始します。  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE] 
>インスタンスに渡す際に `EdgeOptions` オブジェクトを指定する `EdgeDriverService` 必要 `EdgeDriver` はない。  この `EdgeDriver` クラスは、提供するサービスに基づいて、Microsoft Edge \(EdgeHTML\) または Microsoft Edge \(Chromium\) の既定のオプションを使用します。  
> ただし、`EdgeDriverService` と `EdgeOptions` 両方のクラスを提供する場合は、 両方が同じバージョンの Microsoft Edge に対して構成されていることを確認します。  たとえば、既定の Microsoft Edge \(EdgeHTML\) クラスと Chromium プロパティをクラス `EdgeDriverService` で使用 `EdgeOptions` できます。  この `EdgeDriver` クラスは、異なるバージョンの使用を防ぐためにエラーをスローします。  

#### [Python](#tab/python/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

Python を使用すると、オブジェクト `Edge` によって作成および管理されます `EdgeService` 。  構成するには `EdgeService` 、次のコードに示す追加の引数をオブジェクト `Edge` に渡します。  

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### [Java](#tab/java/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

このメソッド `createDefaultService()` を使用して `EdgeDriverService` 、Microsoft Edge \(Chromium\) 用に構成された構成を作成します。  システム Javaを使って、ドライバー サービスをカスタマイズJava。  たとえば、次のコードはプロパティを使用 `"webdriver.edge.verboseLogging"` して詳細ログ出力を有効にします。  

```java
System.setProperty("webdriver.edge.verboseLogging", "true");
EdgeDriverService service = EdgeDriverService.createDefaultService();
EdgeOptions options = new EdgeOptions();
EdgeDriver driver = new EdgeDriver(service, options);
```  

#### [JavaScript](#tab/javascript/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

JavaScript を使用する場合は、クラスを使用して作成 `Service` および構成 `ServiceBuilder` します。  任意で、`Service` オブジェクトを`Driver` オブジェクトに渡すことができます。それによって、サービスが開始\(および 停止\) します。  
構成するには、 `Service` メソッドを使用する前にクラスで `ServiceBuilder` 別のメソッドを実行 `build()` します。  次に、`Driver.createSession()` メソッドのパラメーターとして`service` を渡し ます。  

```javascript
let service = new edge.ServiceBuilder().enableVerboseLogging().build();
let driver = edge.Driver.createSession(options, service);
```  

* * *  

### Chromium-固有 のオプションを使用する  

プロパティを設定した場合は、他の Chromium ブラウザーを自動化するときに使用されるのと同じ Chromium 固有のプロパティとメソッドにクラスを `UseChromium` `true` `EdgeOptions` 使用してアクセスできます。 [][WebdriverCapabilitiesEdgeOptions]  

#### [C#](#tab/c-sharp/)  

<a id="use-chromium-specific-options-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### [Python](#tab/python/)  

<a id="use-chromium-specific-options-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument("headless")
options.add_argument("disable-gpu")
```  

#### [Java](#tab/java/)  

<a id="use-chromium-specific-options-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.addArguments("headless");
options.addArguments("disable-gpu");
```  

#### [JavaScript](#tab/javascript/)  

<a id="use-chromium-specific-options-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.addArguments("headless");
options.addArguments("disable-gpu");
```  

* * *  

> [!NOTE]
> `UseChromium`プロパティが`true` に設定されている場合は、Microsoft Edge \ (EdgeHTML \) のプロパティとメソッドは使用できません。  

## その他の WebDriver インストール オプション  

### Chocolatey  

パッケージ マネージャーとして [大日][Chocolatey] を使う場合は、次のコマンドを実行して Microsoft Edge ドライバーをインストールします。  

```console
choco install selenium-chromium-edge-driver
```  

詳しくは、「セレンティの [Selenium Chromium Edge Driver」に移動してください][ChocolateyPackagesSeleniumChromiumEdgeDriver]。  

### Docker  

Docker を使用 [する][DockerHub]場合は、次のコマンドを実行して、Microsoft Edge \(Chromium\) と Microsoft [Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] がプレインストールされた事前構成済みのイメージをダウンロードします。  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

詳細については、Docker Hub の [msedgedriver コンテナーに移動します][DockerHubMsedgedriver]。  

## 次の手順  

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

[MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]: https://developer.microsoft.com/microsoft-edge/tools/webdriver "WebDriver |Microsoft 開発者"  

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
[SeleniumDocumentation]: https://www.selenium.dev/documentation "Selenium Browser Automation Project |Selenium のドキュメント"  
[SeleniumDownloads]: https://selenium.dev/downloads "ダウンロード |Selenium"  

[SonatypeMavenRepositorySearch]: https://search.maven.org/artifact/com.microsoft.edge/msedge-selenium-tools-java/3.141.0/jar "sonatype Maven Central Repository Search |com.microsoft.edge:msedge-selenium-tools-java"

[TwitterTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |ツイートを投稿する"  

[VisualStudio]: https://visualstudio.microsoft.com/ "Visual Studio"  

[W3CWebdriver]: https://w3.org/TR/webdriver2 "WebDriver |W3C"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "ヘッドレス ブラウザー |Wikipedia"  
