---
description: WebDriver で Web サイトまたはアプリをテストMicrosoft Edgeブラウザーを自動化する方法について説明します。
title: テスト オートメーションに WebDriver (Chromium) を使用する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/24/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge, web 開発, html, css, javascript, 開発者, webdriver, selenium,テストする, ツール, 自動化, テスト
ms.openlocfilehash: a1ec308fc1412ead27c4776ce0ccc2e873376652
ms.sourcegitcommit: e150d798161277fd3fc610838ef2611dc08f5cf6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2021
ms.locfileid: "11624676"
---
# <a name="use-webdriver-chromium-for-test-automation"></a>テスト オートメーションに WebDriver (Chromium) を使用する  

WebDriver を使用すると、開発者はユーザーの操作をシミュレートする自動テストを作成できます。  WebDriver のテストとシミュレーションは、次の方法で JavaScript 単体テストとは異なります。  

*   ブラウザーで実行されている JavaScript では利用できない機能と情報にアクセスします。  
*   ユーザー イベントや OS レベルのイベントをより正確にシミュレートします。  
*   1 回のテスト セッションで、複数のウィンドウ、タブ、Web ページを管理します。  
*   特定のコンピューターで Microsoft Edge の複数のセッションを実行します。  


## <a name="relationship-between-webdriver-and-other-software"></a>WebDriver と他のソフトウェアの関係

WebDriver Microsoft Edgeを自動化してユーザーの操作をシミュレートするには、次の 3 つのコンポーネントが必要です。

*  Microsoft Edge
*  Microsoft Edge ドライバー
*  WebDriver テスト フレームワーク

これらのコンポーネント間の機能関係は次のとおりです。

| テクノロジ | ロール |
|---|---|
| WebDriver | プラットフォームおよび言語に依存しないワイヤー プロトコルの W3C 標準。  このプロトコルにより、アウトプロセス プログラムは Web ブラウザーの動作をリモートで指示できます。 |
| Microsoft Edge ドライバー | Microsoft が WebDriver プロトコルを実装する場合は、このプロトコルを使用Microsoft Edge。  テスト作成者は、ドライバーが受け取る WebDriver コマンドを使用Microsoft Edge記述します。  Microsoft Edgeドライバーは、そのコマンドをブラウザーに通信する責任があります。 |
| WebDriver テスト フレームワーク | テスト作成者は、テスト フレームワークを使用してエンドツーエンドのテストを記述し、ブラウザーを自動化します。  言語固有のインターフェイスを提供し、コードをコマンドに変換し、ドライバー Microsoft Edge \(Chromium\) でMicrosoft Edge実行します。  WebDriver テスト フレームワークは、すべての主要なプラットフォームと言語に対して存在します。  そのようなフレームワークの 1 つは Selenium です。 |
| Internet Explorer ドライバー | WebDriver プロトコルの実装は、webDriver プロトコルのInternet Explorer。  従来のエンド to エンド テストを実行するには、Internet Explorerドライバーを使用Internet Explorer勧めします。 |

次のセクションでは、WebDriver for Microsoft Edge \(Chromium\) について説明します。  


## <a name="install-microsoft-edge-chromium"></a>Microsoft Edge (Chromium) をインストールする  

[Microsoft Edge (Chromium)][MicrosoftEdge] を確実にインストールしてください。  \(Chromium\) がインストールされていることをMicrosoft Edge、に移動し、バージョン番号が `edge://settings/help` 75 以降である必要があります。


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
   
    
## <a name="choose-a-webdriver-testing-framework"></a>WebDriver テスト フレームワークの選択

ドライバーをダウンロードMicrosoft Edge、最後にダウンロードする必要があるコンポーネントは、WebDriver テスト フレームワークです。 テスト作成者は、WebDriver テスト フレームワークを使用して、エンドツーエンドのテストを記述し、ブラウザーを自動化します。 フレームワークは、コード (Python、Java、C#、Ruby、JavaScript など) を Microsoft Edge Driver が Microsoft Edge \(Chromium\) で実行するコマンドに変換する言語固有のインターフェイスを提供します。 WebDriver テスト フレームワークは、すべての主要なプラットフォームと言語に対して存在します。


この記事では、Selenium フレームワークを使用する手順を説明しますが、WebDriver をサポートする任意のライブラリ、フレームワーク、プログラミング言語を使用できます。  Selenium 以外の WebDriver テスト フレームワークを使用して同じタスクを実行するには、選択したフレームワークの公式ドキュメントを参照してください。

Selenium を使用している場合、Microsoft Edge チームは、そのバージョンの Selenium が Microsoft Edge \(Chromium\) をサポートしていますので[、Selenium 4.0.0-beta2][NugetPackagesSeleniumWebdriver400beta02]以降をお勧めします。  ただし、現在の安定した Selenium 3 リリースMicrosoft Edge含め、以前のすべてのバージョンの Selenium で \(Chromium\) を制御できます。  

> [!IMPORTANT]
> 以前に Microsoft Edge \(Chromium\) を使用しておよびクラスを自動化またはテストした場合 `ChromeDriver` `ChromeOptions` 、WebDriver コードは Microsoft Edge バージョン 80 以降では実行されません。  この問題を解決するには、テストを更新してクラスを使用し、Driver `EdgeOptions` [Microsoft Edgeダウンロードします][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]。  

### <a name="using-selenium-4"></a>Selenium 4 の使用

Selenium WebDriver テスト フレームワークは、任意のプラットフォームで使用できます。Java、Python、C#、Ruby、JavaScript で使用できます。

Selenium 4 には、Microsoft Edge (Chromium) が組み込Chromium。  Selenium 4 をインストールするには [、[Selenium ライブラリのインストール] に移動します][SeleniumInstallingLibraries]。

Selenium 4 を使用する場合は、Selenium Tools を使用する必要Microsoft Edge。  Selenium Tools for Microsoft Edgeセレン 3 のみ。  Selenium 4 を Selenium Tools for Microsoft Edge で使用し、新しいインスタンスを作成しようとする場合は、次のエラー `EdgeDriver` メッセージが表示されます `System.MissingMethodException: 'Method not found: 'OpenQA.Selenium.Remote.DesiredCapabilities OpenQA.Selenium.DriverOptions.GenerateDesiredCapabilities(Boolean)'` 。  

Selenium 4 を使用してこのエラーが発生する場合は、プロジェクトから削除し、名前空間の公式クラスとクラスを `Microsoft.Edge.SeleniumTools` `EdgeOptions` `EdgeDriver` 使用 `OpenQA.Selenium.Edge` してください。

### <a name="using-selenium-3"></a>Selenium 3 の使用  

既に [Selenium 3][|::ref1::|] を使用している場合は、既存のブラウザーのテストがあり、Selenium のバージョンを変更せずに Microsoft Edge \ (Chromium \) のカバレッジを追加することを希望するかもしれません。  [Selenium 3][|::ref2::|] を使用して Microsoft Edge  \ (EdgeHTML \) と Microsoft Edge \ (Chromium \) の自動テストを作成するには更新されたドライバーを使用するために、[Microsoft Edge 用 Selenium ツール][GithubMicrosoftEdgeSeleniumTools] のパッケージをインストールします。  ツールに含まれている`EdgeDriver` と `EdgeDriverService` のクラスは、Selenium 4 の組み込みの対応物と完全互な換性があります。  

Selenium 3 を使用している場合は、次の手順を使用して、プロジェクトに Microsoft Edge および[Selenium 3 の Selenium][|::ref3::|] [Tools を][GithubMicrosoftEdgeSeleniumTools]追加します。

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

WebDriver を使用してブラウザーを自動化するには、まず優先 WebDriver テスト フレームワークを使用して WebDriver セッションを開始する必要があります。  セッションは、WebDriver コマンドを使用して制御されるブラウザーの 1 つの実行中のインスタンスです。  WebDriver セッションを開始して、新しいブラウザー インスタンスを起動します。  WebDriver セッションを閉じるまで、起動されたブラウザー インスタンスは開いたままです。  

次のコンテンツでは、Selenium を使用して WebDriver セッションを開始し、\(Microsoft Edge\) Chromiumします。  これらの例は、Selenium 3 または 4 を使用して実行できます。  WebDriver を Selenium 3 で使用するには[、Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools]インストールする必要があります。  

> [!NOTE]
> この記事では、Selenium フレームワークを使用する手順を説明しますが、WebDriver をサポートする任意のライブラリ、フレームワーク、プログラミング言語を使用できます。  別のフレームワークを使用して同じタスクを実行するには、選択したフレームワークの公式ドキュメントを参照してください。

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


## <a name="testing-internet-explorer"></a>テストInternet Explorer

必要なサイトをテストするには、Internet Explorerドライバー Internet Explorer [を使用][GithubSeleniumHqWikiIEDriver] Internet Explorer。  Internet Explorerドライバーは、Selenium プロジェクトによって維持されます。  IE モードMicrosoft Edgeサポートされている場合でも、IE モードでサイトMicrosoft EdgeテストMicrosoft Edgeドライバーを使用することはできません。


## <a name="application-guard"></a>Application Guard

アプリケーション (Application Guard) をMicrosoft Defender Application Guard信頼できるサイトは、ドライバーを使用Microsoft Edgeできます。

Application Guard を使用する信頼されていないサイトは、ドライバーを使用して自動化またはMicrosoft Edgeできません。  Application Guard はコンテナー内の信頼されていないサイトを起動します。このコンテナーは、ドライバーがサイトと通信するために必要Microsoft Edgeリモート デバッグ ポートを公開します。

エンタープライズ管理者は、クラウド リソースや内部ネットワークなど、信頼できるサイトを定義します。  信頼できるサイトの一覧に含されていないサイトは、信頼されていないと見なされます。  Microsoft Edgeドライバーは、InPrivate ウィンドウと信頼できるサイトリスト内のサイトの両方を自動化できます。

Application Guard の詳細については、次の場所に移動します。 

*  [Microsoft Edge での Microsoft Defender Application Guard のサポート][DeployedgeMicrosoftEdgeSecurityWindowsDefenderApplicationGuard]
*  [Microsoft Defender Application Guard概要][WindowsSecurityThreatProtectionMicrosoftDefenderApplicationGuardWindows10]


## <a name="see-also"></a>関連項目

*  [Selenium のドキュメント][SeleniumDocumentation] - Selenium のコンテキストでの WebDriver に関する情報と、Selenium を使用して自動 WebDriver テストを記述する方法について説明します。


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>Microsoft Edge DevTools チームと連絡を取る  

このMicrosoft Edgeチームは、WebDriver、WebDriver テスト フレームワーク (Selenium など)、およびテスト フレームワークの使用に関するフィードバックを熱心にMicrosoft Edge。  チームに質問とコメントを送信するには、DevTools の [フィードバックの送信] Microsoft Edgeを選択するか、ツイートを送信[@EdgeDevTools。][TwitterTweetEdgeDevTools] ****  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン  
:::image-end:::  


<!-- links -->  
[DevtoolsIndex]: ../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 開発者ツール | Microsoft Docs"  
[WebdriverCapabilitiesEdgeOptions]: ./capabilities-edge-options.md "機能と EdgeOptions |Microsoft Docs"  
<!-- external links -->
[DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]: /deployedge/microsoft-edge-policies#developertoolsavailability "DeveloperToolsAvailability - Microsoft Edge - ポリシー |Microsoft Docs"  
[DeployedgeMicrosoftEdgeSecurityWindowsDefenderApplicationGuard]: /deployedge/microsoft-edge-security-windows-defender-application-guard "Microsoft EdgeのサポートMicrosoft Defender Application Guard |Microsoft Docs"

[WindowsSecurityThreatProtectionMicrosoftDefenderApplicationGuardWindows10]: /windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview "Microsoft Defender Application Guard (Windows 10) - Windows セキュリティ |Microsoft Docs"  

[DockerHub]: https://hub.docker.com "Docker Hub"  
[DockerHubMsedgedriver]: https://hub.docker.com/_/microsoft-msedge-msedgedriver?tab=description "msedgedriver |Docker hub"  

[GithubMicrosoftEdgeSeleniumTools]: https://github.com/microsoft/edge-selenium-tools "microsoft/edge-selenium-tools |GitHub"  
[GithubMicrosoftEdgeSeleniumToolsReleases]: https://github.com/microsoft/edge-selenium-tools/releases "microsoft/edge-selenium-tools |GitHub"  
[GithubSeleniumHq]: https://github.com/SeleniumHQ/selenium "SeleniumHQ/selenium |GitHub"  
[GithubSeleniumHqWikiIEDriver]: https://github.com/SeleniumHQ/selenium/wiki/InternetExplorerDriver "Internet Explorer ドライバー - Selenium |GitHub"

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
[SeleniumInstallingLibraries]: https://www.selenium.dev/documentation/en/selenium_installation/installing_selenium_libraries "Selenium ライブラリのインストール|Selenium"

[SonatypeMavenRepositorySearch]: https://search.maven.org/artifact/com.microsoft.edge/msedge-selenium-tools-java/3.141.0/jar "Sonatype Maven Central Repository Search |com.microsoft.edge:msedge-selenium-tools-java"

[TwitterTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |ツイートを投稿する"  

[VisualStudio]: https://visualstudio.microsoft.com/ "Visual Studio"  

[W3CWebdriver]: https://w3.org/TR/webdriver2 "WebDriver |W3C"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "ヘッドレス ブラウザー |Wikipedia"  
