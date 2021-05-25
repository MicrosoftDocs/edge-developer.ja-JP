---
description: WebDriver で Web サイトまたはアプリをテストMicrosoft Edgeブラウザーを自動化する方法について説明します。
title: テスト オートメーションに WebDriver (Chromium) を使用する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/20/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge, web 開発, html, css, javascript, 開発者, webdriver, selenium,テストする, ツール, 自動化, テスト
ms.openlocfilehash: 5d30fe14051ac8857c6ea4d64b8c8f1f8e8049ac
ms.sourcegitcommit: a7609b75a94755ed983111af7083a0d3bf64eeac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "11583588"
---
# <a name="use-webdriver-chromium-for-test-automation"></a>テスト オートメーションに WebDriver (Chromium) を使用する  

WebDriver を使用すると、開発者はユーザーの操作をシミュレートする自動テストを作成できます。  WebDriver のテストとシミュレーションは、次の方法で JavaScript 単体テストとは異なります。  

*   ブラウザーで実行されている JavaScript では利用できない機能と情報にアクセスします。  
*   ユーザー イベントや OS レベルのイベントをより正確にシミュレートします。  
*   1 回のテスト セッションで、複数のウィンドウ、タブ、Web ページを管理します。  
*   特定のコンピューターで Microsoft Edge の複数のセッションを実行します。  
    
次のセクションでは、Microsoft Edge \ (Chromium \) の WebDriver の使用を開始する方法について説明します。  

## <a name="install-microsoft-edge-chromium"></a>Microsoft Edge (Chromium) をインストールする  

[Microsoft Edge (Chromium)][MicrosoftEdge] を確実にインストールしてください。  \(Chromium\) がインストールされていることをMicrosoft Edge、に移動し、バージョン番号が `edge://settings/help` バージョン 75 以降である必要があります。  

## <a name="download-microsoft-edge-driver"></a>Microsoft Edge ドライバーをダウンロードする  

テストの自動化を開始するには、次の手順を使用して、インストールする WebDriver のバージョンがお使いのブラウザーのバージョンと一致していることを確認します。  

1.  バージョンのファイルをMicrosoft Edge。  
    1.  `edge://settings/help` に移動します。  
        
        :::image type="complex" source="./media/microsoft-edge-version.msft.png" alt-text="2021 年 4 月 15 日Microsoft Edgeのビルド番号" lightbox="./media/microsoft-edge-version.msft.png":::
           2021 年 4 月 15 日Microsoft Edgeのビルド番号  
        :::image-end:::  
        
1.  [ドライバー] [Microsoft Edge移動します][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]。  
1.  [最新バージョン **を取得する] に移動します**。  
1.  バージョン番号と一致するチャネルのビルドを選択Microsoft Edge。  
    
    :::image type="complex" source="./media/microsoft-edge-driver-install.msft.png" alt-text="[ドライバー] Web ページの [最新バージョンを取得Microsoft Edge] セクション" lightbox="./media/microsoft-edge-driver-install.msft.png":::
       [**ドライバー] Web ページの**[最新バージョンを取得[Microsoft Edge] セクション][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]  
    :::image-end:::  
    
    <!--  
    > [!NOTE] 
    > For more information about test automation using Microsoft Edge \(EdgeHTML\), navigate to [Microsoft Edge Driver for Microsoft Edge (EdgeHTML)][Webdriver].  
    -->  
    
## <a name="choose-a-webdriver-language-binding"></a>WebDriver 言語バインドの選択  

ダウンロードする必要がある最後のコンポーネントは、コード \(Python、 Java、 C\#, Ruby、 JavaScript\) を、Microsoft Edge \(Chromium\)でMicrosoft Edge ドライバーが実行するコマンドに変換するための言語固有のクライアント ドライバーです。  

[選択した WebDriver 言語バインドをダウンロードします][SeleniumDownloads]。  このMicrosoft Edgeチームは[、Selenium 4.0.0-beta2][NugetPackagesSeleniumWebdriver400beta02]以降を推奨します。これは、Microsoft Edge \(Chromium\) をサポートしています。  ただし、現在の安定した Selenium 3 リリースMicrosoft Edge含め、以前のすべてのバージョンの Selenium で \(Chromium\) を制御できます。  

> [!IMPORTANT]
> 以前に Microsoft Edge \(Chromium\) を使用しておよびクラスを自動化またはテストした場合 `ChromeDriver` `ChromeOptions` 、WebDriver コードは Microsoft Edge バージョン 80 以降では実行されません。  この問題を解決するには、テストを更新してクラスを使用し、Driver `EdgeOptions` [Microsoft Edgeダウンロードします][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]。  

### <a name="using-selenium-4"></a>Selenium 4 の使用

Selenium 4 には、Microsoft Edge (Chromium) が組み込Chromium。  Selenium 4 をインストールするには [、[Selenium ライブラリのインストール] に移動します][SeleniumInstallingLibraries]。

Selenium 4 を使用する場合は、Selenium Tools を使用する必要Microsoft Edge。  Selenium Tools for Microsoft Edgeセレン 3 のみ。  Selenium Tools で Selenium 4 を使用して、Microsoft Edgeインスタンスを作成しようとする場合は、次のエラー `EdgeDriver` メッセージが表示されます `System.MissingMethodException: 'Method not found: 'OpenQA.Selenium.Remote.DesiredCapabilities OpenQA.Selenium.DriverOptions.GenerateDesiredCapabilities(Boolean)'` 。  

Selenium 4 を使用してこのエラーが発生する場合は、プロジェクトから削除し、名前空間の公式クラスとクラスを `Microsoft.Edge.SeleniumTools` `EdgeOptions` `EdgeDriver` 使用 `OpenQA.Selenium.Edge` してください。

### <a name="using-selenium-3"></a>Selenium 3 の使用  

既に [Selenium 3][|::ref1::|] を使用している場合は、既存のブラウザーのテストがあり、Selenium のバージョンを変更せずに Microsoft Edge \ (Chromium \) のカバレッジを追加することを希望するかもしれません。  [Selenium 3][|::ref2::|] を使用して Microsoft Edge  \ (EdgeHTML \) と Microsoft Edge \ (Chromium \) の自動テストを作成するには更新されたドライバーを使用するために、[Microsoft Edge 用 Selenium ツール][GithubMicrosoftEdgeSeleniumTools] のパッケージをインストールします。  ツールに含まれている`EdgeDriver` と `EdgeDriverService` のクラスは、Selenium 4 の組み込みの対応物と完全互な換性があります。  

次の手順を使用して、[Microsoft Edge 用Selenium ツール][GithubMicrosoftEdgeSeleniumTools] と [Selenium 3][|::ref3::|] をプロジェクトに追加します。  

#### [<a name="c"></a>C#](#tab/c-sharp/)  

<a id="selenium-tools-install"></a>  

[NUGET CLI][NugetCLI] または [Visual Studio][VisualStudio] を使用して、 [Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools] と[Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410] の各パッケージを .NET projectに追加します。  

#### [<a name="python"></a>Python](#tab/python/)  

<a id="selenium-tools-install"></a>  

[pip][PythonPip] を使用して[msedge-selenium-tools][PythonSeleniumTools] および [selenium][PythonSelenium] パッケージをインストールします。  

```python
pip install msedge-selenium-tools selenium==3.141
```  

#### [<a name="java"></a>Java](#tab/java/)  

<a id="selenium-tools-install"></a>  

このプロジェクトJava Maven を使用している場合は、次の依存関係をファイルにコピーして貼り付け `pom.xml` [、msedge-selenium-tools-java を追加します][SonatypeMavenRepositorySearch]。  

```xml
<dependency>
    <groupId>com.microsoft.edge</groupId>
    <artifactId>msedge-selenium-tools-java</artifactId>
    <version>[3.141.0,)</version>
</dependency>
```  

このJavaは、Selenium Tools for the [releases ページMicrosoft Edgeダウンロードすることもできます][GithubMicrosoftEdgeSeleniumToolsReleases]。  

#### [<a name="javascript"></a>JavaScript](#tab/javascript/)  

<a id="selenium-tools-install"></a>  

[npm][JavaScript|::ref4::|] を使用して、[edge-selenium-tools][JavaScriptSeleniumTools] および [selenium-webdriver][JavaScriptSelenium] パッケージをインストールします。  

```javascript
npm install @microsoft/edge-selenium-tools selenium-webdriver
```  

* * *  

## <a name="automate-microsoft-edge-chromium-with-webdriver"></a>WebDriver Microsoft Edge (Chromium) を自動化する  

WebDriver を使用してブラウザーを自動化するには、まず優先 WebDriver 言語バインドを使用して WebDriver セッションを開始する必要があります。  セッションは、WebDriver コマンドを使用して制御されるブラウザーの 1 つの実行中のインスタンスです。  WebDriver セッションを開始して、新しいブラウザー インスタンスを起動します。  WebDriver セッションを閉じるまで、起動されたブラウザー インスタンスは開いたままです。  

次のコンテンツでは、Selenium を使用して WebDriver セッションを開始し、\(Microsoft Edge\) Chromiumします。  この例は、Selenium 3 または 4 を使用して実行できます。  Selenium 3 で使用するには、[Microsoft Edge用 Selenium Tools][GithubMicrosoftEdgeSeleniumTools] をインストールする必要があります。  

### <a name="automate-microsoft-edge-chromium"></a>自動Microsoft Edge (Chromium)  

Selenium はクラス `EdgeDriver` を使用して、\(Microsoft Edge\) セッションChromium管理します。  セッションを開始し、\(Chromium\) をMicrosoft Edgeするには、新しいオブジェクトを作成し、プロパティをに設定したオブジェクト `EdgeDriver` `EdgeOptions` `UseChromium` を渡します `true` 。  

#### [<a name="c"></a>C#](#tab/c-sharp/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### [<a name="python"></a>Python](#tab/python/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options = options)
```  

#### [<a name="java"></a>Java](#tab/java/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

この `EdgeDriver` クラスは Microsoft Edge\(Chromium\) のみをサポートし、\(EdgeHTML\) のMicrosoft Edgeサポートされていません。  基本的な使用方法については、指定せずに作成 `EdgeDriver` できます `EdgeOptions` 。  

```java
EdgeDriver driver = new EdgeDriver();
```  

#### [<a name="javascript"></a>JavaScript](#tab/javascript/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);

let driver = edge.Driver.createSession(options);
```  

* * *  

> [!NOTE]
> IT 管理者が[DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]ポリシーをに設定している場合 `2` [、Microsoft Edge ドライバー][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]は Microsoft Edge \(Chromium\) の駆動をブロックされます。ドライバーは Microsoft Edge [DevTools][DevtoolsIndex]を使用します。  [DeveloperToolsAvailability ポリシーに設定][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]されている、または自動化するポリシー `0` `1` (Microsoft Edge) をChromium。  

### <a name="choose-specific-browser-binaries-chromium-only"></a>特定のブラウザー バイナリを選択する (Chromiumのみ)  

\(Chromium\) バイナリの特定のMicrosoft Edge WebDriver セッションを開始できます。  たとえば、テストを実行するには、Microsoft Edge[などの][MicrosoftedgeinsiderDownload]プレビュー チャネルをMicrosoft Edge Beta。  

#### [<a name="c"></a>C#](#tab/c-sharp/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### [<a name="python"></a>Python](#tab/python/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options = options)
```  

#### [<a name="java"></a>Java](#tab/java/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.setBinary("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

EdgeDriver driver = new EdgeDriver(options);
```  

#### [<a name="javascript"></a>JavaScript](#tab/javascript/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.setBinaryPath("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

let driver = edge.Driver.createSession(options);
```  

* * *  

### <a name="customize-the-microsoft-edge-driver-service"></a>ドライバー サービスMicrosoft Edgeカスタマイズする  

#### [<a name="c"></a>C#](#tab/c-sharp/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

クラス を使用してクラス インスタンスを作成すると `EdgeOptions` `EdgeDriver` `EdgeDriverService` 、Microsoft Edge \(EdgeHTML\) または Microsoft Edge \(Chromium\) のいずれかの適切なクラスを作成して起動します。  

を作成する場合は、メソッドを使用して `EdgeDriverService` 、\(Chromium\) 用に `CreateChromiumService()` 構成Microsoft Edge作成します。  この `CreateChromiumService()` メソッドは、カスタマイズを追加する必要がある場合に便利です。  たとえば、次のコードは詳細ログ出力を開始します。  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE] 
>インスタンスに渡す場合は `EdgeOptions` 、オブジェクトを指定 `EdgeDriverService` する必要 `EdgeDriver` があります。  このクラスは、指定したサービスに基Microsoft Edge `EdgeDriver` \(EdgeHTML\) または Microsoft Edge \(Chromium\) の既定のオプションを使用します。  
> ただし、`EdgeDriverService` と `EdgeOptions` 両方のクラスを提供する場合は、 両方が同じバージョンの Microsoft Edge に対して構成されていることを確認します。  たとえば、\(EdgeHTML\) クラスの既定Microsoft Edgeを使用し、 `EdgeDriverService` クラスChromiumプロパティを使用 `EdgeOptions` できます。  この `EdgeDriver` クラスは、異なるバージョンの使用を防ぐためにエラーをスローします。  

#### [<a name="python"></a>Python](#tab/python/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

Python を使用すると、 `Edge` オブジェクトによって作成および管理されます `EdgeService` 。  を構成するには `EdgeService` 、次のコードに示す追加 `Edge` の引数をオブジェクトに渡します。  

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### [<a name="java"></a>Java](#tab/java/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

このメソッド `createDefaultService()` を使用して `EdgeDriverService` 、\(Microsoft Edge\) 用に構成Chromiumします。  システムJavaを使用して、ドライバー サービスをカスタマイズJava。  たとえば、次のコードでは、プロパティを `"webdriver.edge.verboseLogging"` 使用して詳細ログ出力を有効にします。  

```java
System.setProperty("webdriver.edge.verboseLogging", "true");
EdgeDriverService service = EdgeDriverService.createDefaultService();
EdgeOptions options = new EdgeOptions();
EdgeDriver driver = new EdgeDriver(service, options);
```  

#### [<a name="javascript"></a>JavaScript](#tab/javascript/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

JavaScript を使用する場合は、クラスを使用して a `Service` を作成して構成 `ServiceBuilder` します。  必要に応じて、オブジェクトを `Service` オブジェクトに渡して、 `Driver` サービスを \(and stops\) で開始できます。  
を構成するには `Service` 、メソッドを使用する前にクラス `ServiceBuilder` で別のメソッドを実行 `build()` します。  次に、`Driver.createSession()` メソッドのパラメーターとして`service` を渡し ます。  

```javascript
let service = new edge.ServiceBuilder().enableVerboseLogging().build();
let driver = edge.Driver.createSession(options, service);
```  

* * *  

### <a name="use-chromium-specific-options"></a>Chromium-固有 のオプションを使用する  

プロパティをに設定した場合は、クラスを使用して、他のブラウザーを自動化するときに使用される Chromium 固有のプロパティとメソッドにアクセスChromium `UseChromium` `true` `EdgeOptions` できます。 [][WebdriverCapabilitiesEdgeOptions]  

#### [<a name="c"></a>C#](#tab/c-sharp/)  

<a id="use-chromium-specific-options-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### [<a name="python"></a>Python](#tab/python/)  

<a id="use-chromium-specific-options-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument("headless")
options.add_argument("disable-gpu")
```  

#### [<a name="java"></a>Java](#tab/java/)  

<a id="use-chromium-specific-options-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.addArguments("headless");
options.addArguments("disable-gpu");
```  

#### [<a name="javascript"></a>JavaScript](#tab/javascript/)  

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

## <a name="other-webdriver-installation-options"></a>その他の WebDriver インストール オプション  

### <a name="docker"></a>Docker  

Docker を使用[する場合][DockerHub]は、次のコマンドを実行して、Microsoft Edge \(Chromium\) および Microsoft Edge [Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]がプリインストールされた構成済みのイメージをダウンロードします。  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

詳細については、Docker Hub の [msedgedriver コンテナーに移動します][DockerHubMsedgedriver]。  

## <a name="next-steps"></a>次の手順  

WebDriver の詳細と、Selenium を使用して自動 WebDriver テストを記述する方法については [、Selenium のドキュメントに移動します][SeleniumDocumentation]。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

Microsoft Edge チームは、WebDriver、Selenium、Microsoft Edge の使用に関するフィードバックをお待ちしております。  チームに質問とコメントを送信するには、DevTools の [フィードバックの送信] Microsoft Edgeを選択するか、ツイートを送信[@EdgeDevTools。][TwitterTweetEdgeDevTools] ****  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン  
:::image-end:::  

<!-- links -->  

[DevtoolsIndex]: ../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[WebdriverCapabilitiesEdgeOptions]: ./capabilities-edge-options.md "機能と EdgeOptions |Microsoft Docs"  

<!--[Webdriver]: /archive/microsoft-edge/legacy/developer/webdriver/index "WebDriver (EdgeHTML) | Microsoft Docs"  -->  

[DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]: /deployedge/microsoft-edge-policies#developertoolsavailability "DeveloperToolsAvailability-Microsoft Edge-ポリシー |Microsoft ドキュメント"  

[DockerHub]: https://hub.docker.com "Docker Hub"  
[DockerHubMsedgedriver]: https://hub.docker.com/_/microsoft-msedge-msedgedriver?tab=description "msedgedriver |Docker hub"  

[GithubMicrosoftEdgeSeleniumTools]: https://github.com/microsoft/edge-selenium-tools "microsoft/edge-selenium-tools |GitHub"  
[GithubMicrosoftEdgeSeleniumToolsReleases]: https://github.com/microsoft/edge-selenium-tools/releases "microsoft/edge-selenium-tools |GitHub"  
[GithubSeleniumHq]: https://github.com/SeleniumHQ/selenium "SeleniumHQ/selenium |GitHub"  

[JavaScriptnpm]: https://www.npmjs.com/ "npm"  
[JavaScriptSeleniumTools]: https://www.npmjs.com/package/@microsoft/edge-selenium-tools "@microsoft/edge-selenium-tools |npm"  
[JavaScriptSelenium]: https://www.npmjs.com/package/selenium-webdriver "selenium-webdriver |npm"  

[MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]: https://developer.microsoft.com/microsoft-edge/tools/webdriver "Microsoft Edgeドライバー|Microsoft Edge開発者"  

[MicrosoftEdge]: https://www.microsoft.com/edge "新しい Microsoft Edge ブラウザーをダウンロードする"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  

[NugetCLI]:https://www.nuget.org/packages/NuGet.CommandLine/ "NuGet.CommandLine |NuGet ギャラリー"  
[NugetPackagesMicrosoftEdgeSeleniumtools]: https://www.nuget.org/packages/Microsoft.Edge.SeleniumTools "Microsoft.Edge.SeleniumTools |NuGet ギャラリー"  
[NugetPackagesSeleniumWebdriver31410]: https://www.nuget.org/packages/Selenium.WebDriver/3.141.0 "Selenium.WebDriver 3.141.0 |NuGet ギャラリー"  
[NugetPackagesSeleniumWebdriver400beta02]: https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-beta2 "Selenium.WebDriver 4.0.0-beta2 |NuGetギャラリー"  

[PythonPip]: https://pypi.org/project/pip/ "pip |PyPI"  
[PythonSeleniumTools]: https://pypi.org/project/msedge-selenium-tools/ "msedge-selenium-tools |PyPI"  
[PythonSelenium]: https://pypi.org/project/selenium/ "selenium |PyPI"

[SeleniumHQ]: https://www.selenium.dev "SeleniumHQ"  
[SeleniumDocumentation]: https://www.selenium.dev/documentation "Selenium Browser Automation Project |Selenium のドキュメント"  
[SeleniumDownloads]: https://selenium.dev/downloads "ダウンロード |Selenium"  
[SeleniumInstallingLibraries]: https://www.selenium.dev/documentation/en/selenium_installation/installing_selenium_libraries "Selenium ライブラリのインストール|Selenium"

[SonatypeMavenRepositorySearch]: https://search.maven.org/artifact/com.microsoft.edge/msedge-selenium-tools-java/3.141.0/jar "sonatype Maven Central Repository Search |com.microsoft.edge:msedge-selenium-tools-java"

[TwitterTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |ツイートを投稿する"  

[VisualStudio]: https://visualstudio.microsoft.com/ "Visual Studio"  

[W3CWebdriver]: https://w3.org/TR/webdriver2 "WebDriver |W3C"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "ヘッドレス ブラウザー |Wikipedia"  
