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
ms.openlocfilehash: 87855fad02243a9d86053e43b5523013644f7e35
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398834"
---
# <a name="use-webdriver-chromium-for-test-automation"></a><span data-ttu-id="e143e-104">テスト オートメーションに WebDriver (Chromium) を使用する</span><span class="sxs-lookup"><span data-stu-id="e143e-104">Use WebDriver (Chromium) for test automation</span></span>  

<span data-ttu-id="e143e-105">WebDriver を使用すると、開発者はユーザーの操作をシミュレートする自動テストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e143e-105">WebDriver allows developers to create automated tests that simulate user interaction.</span></span>  <span data-ttu-id="e143e-106">WebDriver のテストとシミュレーションは、次の方法で JavaScript 単体テストとは異なります。</span><span class="sxs-lookup"><span data-stu-id="e143e-106">WebDriver tests and simulations differ from JavaScript unit tests in the following ways.</span></span>  

*   <span data-ttu-id="e143e-107">ブラウザーで実行されている JavaScript では利用できない機能と情報にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e143e-107">Accesses functionality and information not available to JavaScript running in browsers.</span></span>  
*   <span data-ttu-id="e143e-108">ユーザー イベントや OS レベルのイベントをより正確にシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="e143e-108">Simulates user events or OS-level events more accurately.</span></span>  
*   <span data-ttu-id="e143e-109">1 回のテスト セッションで、複数のウィンドウ、タブ、Web ページを管理します。</span><span class="sxs-lookup"><span data-stu-id="e143e-109">Manages multiple windows, tabs, and webpages in a single test session.</span></span>  
*   <span data-ttu-id="e143e-110">特定のコンピューターで Microsoft Edge の複数のセッションを実行します。</span><span class="sxs-lookup"><span data-stu-id="e143e-110">Runs multiple sessions of Microsoft Edge on a specific machine.</span></span>  
    
<span data-ttu-id="e143e-111">次のセクションでは、Microsoft Edge \(Chromium \) の WebDriver の使用を開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e143e-111">The following section describes how to get started with WebDriver for Microsoft Edge \(Chromium\).</span></span>  

## <a name="install-microsoft-edge-chromium"></a><span data-ttu-id="e143e-112">Microsoft Edge (Chromium) をインストールする</span><span class="sxs-lookup"><span data-stu-id="e143e-112">Install Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="e143e-113">[Microsoft Edge (Chromium)][MicrosoftEdge] を確実にインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="e143e-113">Ensure you install [Microsoft Edge (Chromium)][MicrosoftEdge].</span></span>  <span data-ttu-id="e143e-114">Microsoft Edge \(Chromium\) がインストールされていることを確認するには、に移動し、バージョン番号が `edge://settings/help` バージョン 75 以降である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e143e-114">To confirm that you have Microsoft Edge \(Chromium\) installed, navigate to `edge://settings/help`, and verify the version number is version 75 or later.</span></span>  

## <a name="download-microsoft-edge-driver"></a><span data-ttu-id="e143e-115">Microsoft Edge ドライバーをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="e143e-115">Download Microsoft Edge Driver</span></span>  

<span data-ttu-id="e143e-116">テストの自動化を開始するには、次の手順を使用して、インストールする WebDriver のバージョンがお使いのブラウザーのバージョンと一致していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e143e-116">To begin automating tests, use the following steps to ensure that the WebDriver version you install matches your browser version.</span></span>  

1.  <span data-ttu-id="e143e-117">Microsoft Edge のバージョンを表示するには、に移動します `edge://settings/help` 。</span><span class="sxs-lookup"><span data-stu-id="e143e-117">To display the version of Microsoft Edge, navigate to `edge://settings/help`.</span></span>  
    
    :::image type="complex" source="./media/microsoft-edge-version.msft.png" alt-text="2021 年 2 月 10 日の Microsoft Edge Canary のビルド番号" lightbox="./media/microsoft-edge-version.msft.png":::
       <span data-ttu-id="e143e-119">2021 年 2 月 10 日の Microsoft Edge Canary のビルド番号</span><span class="sxs-lookup"><span data-stu-id="e143e-119">The build number for Microsoft Edge Canary on February 10, 2021</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="e143e-120">[ダウンロード[] セクションの [Microsoft Edge Driver]][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]に移動し、Microsoft Edge のバージョン番号に一致する WebDriver をダウンロードします。 </span><span class="sxs-lookup"><span data-stu-id="e143e-120">Navigate to [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver], under the **Downloads** section, and download the WebDriver that matches the version number of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="./media/microsoft-edge-driver-install.msft.png" alt-text="Microsoft Edge Driver の [ダウンロード] セクション" lightbox="./media/microsoft-edge-driver-install.msft.png":::
       <span data-ttu-id="e143e-122">Microsoft Edge Driver**の** [[ダウンロード][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]] セクション</span><span class="sxs-lookup"><span data-stu-id="e143e-122">The **Downloads** section on [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]</span></span>  
    :::image-end:::  
    
    <!--  
    > [!NOTE] 
    > For more information about test automation using Microsoft Edge \(EdgeHTML\), navigate to [Microsoft Edge Driver for Microsoft Edge \(EdgeHTML\)][Webdriver].  
    -->  
    
## <a name="choose-a-webdriver-language-binding"></a><span data-ttu-id="e143e-123">WebDriver 言語バインドの選択</span><span class="sxs-lookup"><span data-stu-id="e143e-123">Choose a WebDriver language binding</span></span>  

<span data-ttu-id="e143e-124">ダウンロードする必要がある最後のコンポーネントは、コード \(Python、 Java、 C\#, Ruby、 JavaScript\) を、Microsoft Edge \(Chromium\)でMicrosoft Edge ドライバーが実行するコマンドに変換するための言語固有のクライアント ドライバーです。</span><span class="sxs-lookup"><span data-stu-id="e143e-124">The last component you must download is a language-specific client driver to translate your code \(Python, Java, C\#, Ruby, JavaScript\) into commands the Microsoft Edge Driver runs in Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="e143e-125">[選択した WebDriver 言語バインドをダウンロードします][SeleniumDownloads]。</span><span class="sxs-lookup"><span data-stu-id="e143e-125">[Download the WebDriver language binding of your choice][SeleniumDownloads].</span></span>  <span data-ttu-id="e143e-126">Microsoft Edge チームは、Microsoft Edge \(Chromium\) をサポートしていますので [、Selenium 4.00-alpha07][NugetPackagesSeleniumWebdriver400alpha07] 以降をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e143e-126">The Microsoft Edge team recommends [Selenium 4.00-alpha07][NugetPackagesSeleniumWebdriver400alpha07] or later, because it supports Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="e143e-127">ただし、現在の安定した Selenium 3 リリースを含む、Selenium のすべての旧バージョンで Microsoft Edge \(Chromium \) を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="e143e-127">However, you may control Microsoft Edge \(Chromium\) in all older versions of Selenium, including the current stable Selenium 3 release.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="e143e-128">以前に Microsoft Edge \(Chromium\) を使用してクラスを自動化またはテストした場合 `ChromeDriver` `ChromeOptions` 、WebDriver コードは Microsoft Edge バージョン 80 以降では実行されません。</span><span class="sxs-lookup"><span data-stu-id="e143e-128">If you previously automated or tested Microsoft Edge \(Chromium\) using `ChromeDriver` and `ChromeOptions` classes, your WebDriver code does not run on Microsoft Edge Version 80 or later.</span></span>  <span data-ttu-id="e143e-129">この問題を解決するには、テストを更新してクラスを使用し `EdgeOptions` [、Microsoft Edge Driver をダウンロードします][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]。</span><span class="sxs-lookup"><span data-stu-id="e143e-129">To solve the problem, update your tests to use the `EdgeOptions` class and download [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver].</span></span>  

### <a name="use-selenium-3"></a><span data-ttu-id="e143e-130">Selenium 3 を使用する</span><span class="sxs-lookup"><span data-stu-id="e143e-130">Use Selenium 3</span></span>  

<span data-ttu-id="e143e-131">既に [Selenium 3][|::ref1::|] を使用している場合は、既存のブラウザーのテストがあり、Selenium のバージョンを変更せずに Microsoft Edge \(Chromium \) のカバレッジを追加することを希望するかもしれません。</span><span class="sxs-lookup"><span data-stu-id="e143e-131">If you already use [Selenium 3][|::ref1::|], you may have existing browser tests and want to add coverage for Microsoft Edge \(Chromium\) without changing your version of Selenium.</span></span>  <span data-ttu-id="e143e-132">[Selenium 3][|::ref2::|] を使用して Microsoft Edge  \(EdgeHTML \) と Microsoft Edge \(Chromium \) の自動テストを作成するには更新されたドライバーを使用するために、[Microsoft Edge 用 Selenium ツール][GithubMicrosoftEdgeSeleniumTools] のパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e143e-132">To use [Selenium 3][|::ref2::|] to write automated tests for both Microsoft Edge \(EdgeHTML\) and Microsoft Edge \(Chromium\), install the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package to use the updated driver.</span></span>  <span data-ttu-id="e143e-133">ツールに含まれている`EdgeDriver` と `EdgeDriverService` のクラスは、Selenium 4 の組み込みの対応物と完全互な換性があります。</span><span class="sxs-lookup"><span data-stu-id="e143e-133">The `EdgeDriver` and `EdgeDriverService` classes included in the tools are fully compatible with the built-in equivalents in Selenium 4.</span></span>  

<span data-ttu-id="e143e-134">次の手順を使用して、[Microsoft Edge 用Selenium ツール][GithubMicrosoftEdgeSeleniumTools] と [Selenium 3][|::ref3::|] をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="e143e-134">Use the following steps to add the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] and [Selenium 3][|::ref3::|] to your project.</span></span>  

#### [<a name="c"></a><span data-ttu-id="e143e-135">C#</span><span class="sxs-lookup"><span data-stu-id="e143e-135">C#</span></span>](#tab/c-sharp/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="e143e-136">[NUGET CLI][NugetCLI] または [Visual Studio][VisualStudio] を使用して、 [Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools] と[Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410] の各パッケージを .NET projectに追加します。</span><span class="sxs-lookup"><span data-stu-id="e143e-136">Add the [Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools] and [Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410] packages to your .NET project using the [NuGet CLI][NugetCLI] or [Visual Studio][VisualStudio].</span></span>  

#### [<a name="python"></a><span data-ttu-id="e143e-137">Python</span><span class="sxs-lookup"><span data-stu-id="e143e-137">Python</span></span>](#tab/python/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="e143e-138">[pip][PythonPip] を使用して[msedge-selenium-tools][PythonSeleniumTools] および [selenium][PythonSelenium] パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e143e-138">Use [pip][PythonPip] to install the [msedge-selenium-tools][PythonSeleniumTools] and [selenium][PythonSelenium] packages.</span></span>  

```python
pip install msedge-selenium-tools selenium==3.141
```  

#### [<a name="java"></a><span data-ttu-id="e143e-139">Java</span><span class="sxs-lookup"><span data-stu-id="e143e-139">Java</span></span>](#tab/java/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="e143e-140">このプロジェクトJava Maven を使用している場合は、次の依存関係をファイルにコピーして貼り付け `pom.xml` [、msedge-selenium-tools-java を追加します][SonatypeMavenRepositorySearch]。</span><span class="sxs-lookup"><span data-stu-id="e143e-140">If your Java project uses Maven, copy and paste the following dependency to your `pom.xml` file to add [msedge-selenium-tools-java][SonatypeMavenRepositorySearch].</span></span>  

```xml
<dependency>
    <groupId>com.microsoft.edge</groupId>
    <artifactId>msedge-selenium-tools-java</artifactId>
    <version>[3.141.0,)</version>
</dependency>
```  

<span data-ttu-id="e143e-141">このJavaは [、[Selenium Tools for Microsoft Edge Releases]][GithubMicrosoftEdgeSeleniumToolsReleases]ページから直接ダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e143e-141">The Java package is also available to download directly on the [Selenium Tools for Microsoft Edge Releases page][GithubMicrosoftEdgeSeleniumToolsReleases].</span></span>  

#### [<a name="javascript"></a><span data-ttu-id="e143e-142">JavaScript</span><span class="sxs-lookup"><span data-stu-id="e143e-142">JavaScript</span></span>](#tab/javascript/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="e143e-143">[npm][JavaScript|::ref4::|] を使用して、[edge-selenium-tools][JavaScriptSeleniumTools] および [selenium-webdriver][JavaScriptSelenium] パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e143e-143">Use [npm][JavaScript|::ref4::|] to install the [edge-selenium-tools][JavaScriptSeleniumTools] and [selenium-webdriver][JavaScriptSelenium] packages.</span></span>  

```javascript
npm install @microsoft/edge-selenium-tools selenium-webdriver
```  

* * *  

## <a name="automate-microsoft-edge-chromium-with-webdriver"></a><span data-ttu-id="e143e-144">WebDriver を使用して Microsoft Edge (クロム) を自動化する</span><span class="sxs-lookup"><span data-stu-id="e143e-144">Automate Microsoft Edge (Chromium) with WebDriver</span></span>  

<span data-ttu-id="e143e-145">WebDriver を使用してブラウザーを自動化するには、まず優先 WebDriver 言語バインドを使用して WebDriver セッションを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e143e-145">To automate a browser using WebDriver, you must first start a WebDriver session using your preferred WebDriver language binding.</span></span>  <span data-ttu-id="e143e-146">セッションは、WebDriver コマンドを使用して制御されるブラウザーの 1 つの実行中のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="e143e-146">A session is a single running instance of a browser controlled using WebDriver commands.</span></span>  <span data-ttu-id="e143e-147">WebDriver セッションを開始して、新しいブラウザー インスタンスを起動します。</span><span class="sxs-lookup"><span data-stu-id="e143e-147">Start a WebDriver session to launch a new browser instance.</span></span>  <span data-ttu-id="e143e-148">WebDriver セッションを閉じるまで、起動されたブラウザー インスタンスは開いたままです。</span><span class="sxs-lookup"><span data-stu-id="e143e-148">The launched browser instance remains open until you close the WebDriver session.</span></span>  

<span data-ttu-id="e143e-149">次のコンテンツでは、Selenium を使用して Microsoft Edge \(Chromium\) で WebDriver セッションを開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e143e-149">The following content walks you through using Selenium to start a WebDriver session with Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="e143e-150">この例は、Selenium 3 または 4 のいずれかを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="e143e-150">You may run the examples using either Selenium 3 or 4.</span></span>  <span data-ttu-id="e143e-151">Selenium 3 で使用するには、[Microsoft Edge用 Selenium Tools][GithubMicrosoftEdgeSeleniumTools] をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e143e-151">To use with Selenium 3, the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package must be installed.</span></span>  

### <a name="automate-microsoft-edge-chromium"></a><span data-ttu-id="e143e-152">Microsoft Edge の自動化 (クロム)</span><span class="sxs-lookup"><span data-stu-id="e143e-152">Automate Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="e143e-153">Selenium は、クラス `EdgeDriver` を使用して Microsoft Edge \(Chromium\) セッションを管理します。</span><span class="sxs-lookup"><span data-stu-id="e143e-153">Selenium uses the `EdgeDriver` class to manage a Microsoft Edge \(Chromium\) session.</span></span>  <span data-ttu-id="e143e-154">セッションを開始し、Microsoft Edge \(Chromium\) を自動化するには、新しいオブジェクトを作成し、プロパティをに設定して `EdgeDriver` `EdgeOptions` `UseChromium` オブジェクトを渡します `true` 。</span><span class="sxs-lookup"><span data-stu-id="e143e-154">To start a session and automate Microsoft Edge \(Chromium\), create a new `EdgeDriver` object and pass it an `EdgeOptions` object with the `UseChromium` property set to `true`.</span></span>  

#### [<a name="c"></a><span data-ttu-id="e143e-155">C#</span><span class="sxs-lookup"><span data-stu-id="e143e-155">C#</span></span>](#tab/c-sharp/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### [<a name="python"></a><span data-ttu-id="e143e-156">Python</span><span class="sxs-lookup"><span data-stu-id="e143e-156">Python</span></span>](#tab/python/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options = options)
```  

#### [<a name="java"></a><span data-ttu-id="e143e-157">Java</span><span class="sxs-lookup"><span data-stu-id="e143e-157">Java</span></span>](#tab/java/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

<span data-ttu-id="e143e-158">この `EdgeDriver` クラスは Microsoft Edge \(Chromium\) のみをサポートし、Microsoft Edge \(EdgeHTML\) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e143e-158">The `EdgeDriver` class only supports Microsoft Edge \(Chromium\), and doesn't support Microsoft Edge \(EdgeHTML\).</span></span>  <span data-ttu-id="e143e-159">基本的な使い方については、 を指定せずに `EdgeDriver` 作成できます `EdgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="e143e-159">For basic usage, you may create an `EdgeDriver` without providing `EdgeOptions`.</span></span>  

```java
EdgeDriver driver = new EdgeDriver();
```  

#### [<a name="javascript"></a><span data-ttu-id="e143e-160">JavaScript</span><span class="sxs-lookup"><span data-stu-id="e143e-160">JavaScript</span></span>](#tab/javascript/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);

let driver = edge.Driver.createSession(options);
```  

* * *  

> [!NOTE]
> <span data-ttu-id="e143e-161">IT 管理者が[DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]ポリシーをに設定している場合、Microsoft Edge Driver は `2` Microsoft Edge \(Chromium\) の駆動をブロックされます。ドライバーは[Microsoft Edge DevTools][DevtoolsIndex][][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]を使用します。</span><span class="sxs-lookup"><span data-stu-id="e143e-161">If your IT admin has set the [DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability] policy to `2`,  [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] is blocked from driving Microsoft Edge \(Chromium\), because the driver uses the [Microsoft Edge DevTools][DevtoolsIndex].</span></span>  <span data-ttu-id="e143e-162">[DeveloperToolsAvailability ポリシーが][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]Microsoft `0` `1` Edge (Chromium) に設定または自動化されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e143e-162">Ensure the [DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability] policy is set to `0` or `1` to automate Microsoft Edge (Chromium).</span></span>  

### <a name="choose-specific-browser-binaries-chromium-only"></a><span data-ttu-id="e143e-163">特定のブラウザー バイナリを選択する (クロムのみ)</span><span class="sxs-lookup"><span data-stu-id="e143e-163">Choose Specific Browser Binaries (Chromium-Only)</span></span>  

<span data-ttu-id="e143e-164">特定の Microsoft Edge \(Chromium\) バイナリを使用して WebDriver セッションを開始できます。</span><span class="sxs-lookup"><span data-stu-id="e143e-164">You may start a WebDriver session with specific Microsoft Edge \(Chromium\) binaries.</span></span>  <span data-ttu-id="e143e-165">たとえば、Microsoft Edge ベータ版などの [Microsoft Edge preview チャネル][MicrosoftedgeinsiderDownload] を使用してテストを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e143e-165">For example, you may run tests using the [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.</span></span>  

#### [<a name="c"></a><span data-ttu-id="e143e-166">C#</span><span class="sxs-lookup"><span data-stu-id="e143e-166">C#</span></span>](#tab/c-sharp/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### [<a name="python"></a><span data-ttu-id="e143e-167">Python</span><span class="sxs-lookup"><span data-stu-id="e143e-167">Python</span></span>](#tab/python/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options = options)
```  

#### [<a name="java"></a><span data-ttu-id="e143e-168">Java</span><span class="sxs-lookup"><span data-stu-id="e143e-168">Java</span></span>](#tab/java/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.setBinary("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

EdgeDriver driver = new EdgeDriver(options);
```  

#### [<a name="javascript"></a><span data-ttu-id="e143e-169">JavaScript</span><span class="sxs-lookup"><span data-stu-id="e143e-169">JavaScript</span></span>](#tab/javascript/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.setBinaryPath("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

let driver = edge.Driver.createSession(options);
```  

* * *  

### <a name="customize-the-microsoft-edge-driver-service"></a><span data-ttu-id="e143e-170">Microsoft Edge Driver Service のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="e143e-170">Customize the Microsoft Edge Driver Service</span></span>  

#### [<a name="c"></a><span data-ttu-id="e143e-171">C#</span><span class="sxs-lookup"><span data-stu-id="e143e-171">C#</span></span>](#tab/c-sharp/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="e143e-172">クラス を使用してクラス インスタンスを作成すると `EdgeOptions` `EdgeDriver` `EdgeDriverService` 、Microsoft Edge \(EdgeHTML\) または Microsoft Edge \(Chromium\) の適切なクラスを作成して起動します。</span><span class="sxs-lookup"><span data-stu-id="e143e-172">When you use the `EdgeOptions` class to create an `EdgeDriver` class instance, it creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="e143e-173">を作成する場合は `EdgeDriverService` 、 `CreateChromiumService()` メソッドを使用して Microsoft Edge \(Chromium\) 用に構成されたメソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="e143e-173">If you want to create an `EdgeDriverService`, use the `CreateChromiumService()` method to create one configured for Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="e143e-174">この `CreateChromiumService()` メソッドは、カスタマイズを追加する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="e143e-174">The `CreateChromiumService()` method is useful when you need to add customizations.</span></span>  <span data-ttu-id="e143e-175">たとえば、次のコードは詳細ログ出力を開始します。</span><span class="sxs-lookup"><span data-stu-id="e143e-175">For example, the following code starts verbose log output.</span></span>  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE] 
><span data-ttu-id="e143e-176">インスタンスに渡す場合は `EdgeOptions` 、オブジェクトを指定 `EdgeDriverService` する必要 `EdgeDriver` があります。</span><span class="sxs-lookup"><span data-stu-id="e143e-176">You do not need to provide the `EdgeOptions` object when you pass `EdgeDriverService` to the `EdgeDriver` instance.</span></span>  <span data-ttu-id="e143e-177">この `EdgeDriver` クラスは、指定したサービスに基づいて、Microsoft Edge \(EdgeHTML\) または Microsoft Edge \(Chromium\) のいずれかの既定のオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="e143e-177">The `EdgeDriver` class uses the default options for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\) based on the service you provide.</span></span>  
> <span data-ttu-id="e143e-178">ただし、`EdgeDriverService` と `EdgeOptions` 両方のクラスを提供する場合は、 両方が同じバージョンの Microsoft Edge に対して構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e143e-178">However, if you want to provide both `EdgeDriverService` and `EdgeOptions` classes, ensure that both are configured for the same version of Microsoft Edge.</span></span>  <span data-ttu-id="e143e-179">たとえば、クラスで既定の Microsoft Edge \(EdgeHTML\) クラスと `EdgeDriverService` クロム プロパティを使用 `EdgeOptions` できます。</span><span class="sxs-lookup"><span data-stu-id="e143e-179">For example, you may use a default Microsoft Edge \(EdgeHTML\) `EdgeDriverService` class and Chromium properties in the `EdgeOptions` class.</span></span>  <span data-ttu-id="e143e-180">この `EdgeDriver` クラスは、異なるバージョンの使用を防ぐためにエラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="e143e-180">The `EdgeDriver` class throws an error to prevent using different versions.</span></span>  

#### [<a name="python"></a><span data-ttu-id="e143e-181">Python</span><span class="sxs-lookup"><span data-stu-id="e143e-181">Python</span></span>](#tab/python/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="e143e-182">Python を使用すると、 `Edge` オブジェクトによって作成および管理されます `EdgeService` 。</span><span class="sxs-lookup"><span data-stu-id="e143e-182">When you use Python, the `Edge` object creates and manages the `EdgeService`.</span></span>  <span data-ttu-id="e143e-183">を構成するには `EdgeService` 、次のコードに示す追加 `Edge` の引数をオブジェクトに渡します。</span><span class="sxs-lookup"><span data-stu-id="e143e-183">To configure the `EdgeService`, pass extra arguments to the `Edge` object as indicated in the following code.</span></span>  

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### [<a name="java"></a><span data-ttu-id="e143e-184">Java</span><span class="sxs-lookup"><span data-stu-id="e143e-184">Java</span></span>](#tab/java/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="e143e-185">メソッドを `createDefaultService()` 使用して `EdgeDriverService` 、Microsoft Edge \(Chromium\) 用に構成された構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="e143e-185">Use the `createDefaultService()` method to create an `EdgeDriverService` configured for Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="e143e-186">システムJavaを使用して、ドライバー サービスをカスタマイズJava。</span><span class="sxs-lookup"><span data-stu-id="e143e-186">Use Java system properties to customize driver services in Java.</span></span>  <span data-ttu-id="e143e-187">たとえば、次のコードでは、プロパティを `"webdriver.edge.verboseLogging"` 使用して詳細ログ出力を有効にします。</span><span class="sxs-lookup"><span data-stu-id="e143e-187">For example, the following code uses the `"webdriver.edge.verboseLogging"` property to turn on verbose log output.</span></span>  

```java
System.setProperty("webdriver.edge.verboseLogging", "true");
EdgeDriverService service = EdgeDriverService.createDefaultService();
EdgeOptions options = new EdgeOptions();
EdgeDriver driver = new EdgeDriver(service, options);
```  

#### [<a name="javascript"></a><span data-ttu-id="e143e-188">JavaScript</span><span class="sxs-lookup"><span data-stu-id="e143e-188">JavaScript</span></span>](#tab/javascript/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="e143e-189">JavaScript を使用する場合は、クラスを使用して a `Service` を作成して構成 `ServiceBuilder` します。</span><span class="sxs-lookup"><span data-stu-id="e143e-189">When you use JavaScript, create and configure a `Service` with the `ServiceBuilder` class.</span></span>  <span data-ttu-id="e143e-190">任意で、`Service` オブジェクトを`Driver` オブジェクトに渡すことができます。それによって、サービスが開始\(および 停止\) します。</span><span class="sxs-lookup"><span data-stu-id="e143e-190">Optionally, you may pass the `Service` object to the `Driver` object, which starts \(and stops\) the service for you.</span></span>  
<span data-ttu-id="e143e-191">を構成するには `Service` 、メソッドを使用する前にクラス `ServiceBuilder` で別のメソッドを実行 `build()` します。</span><span class="sxs-lookup"><span data-stu-id="e143e-191">To configure the `Service`, run another method in the `ServiceBuilder` class before you use the `build()` method.</span></span>  <span data-ttu-id="e143e-192">次に、`Driver.createSession()` メソッドのパラメーターとして`service` を渡し ます。</span><span class="sxs-lookup"><span data-stu-id="e143e-192">Then pass the `service` as a parameter in the `Driver.createSession()` method.</span></span>  

```javascript
let service = new edge.ServiceBuilder().enableVerboseLogging().build();
let driver = edge.Driver.createSession(options, service);
```  

* * *  

### <a name="use-chromium-specific-options"></a><span data-ttu-id="e143e-193">Chromium-固有 のオプションを使用する</span><span class="sxs-lookup"><span data-stu-id="e143e-193">Use Chromium-Specific Options</span></span>  

<span data-ttu-id="e143e-194">プロパティをに設定すると、他のクロム ブラウザーを自動化するときに使用されるのと同じクロム固有のプロパティとメソッドにアクセスするためにクラスを `UseChromium` `true` `EdgeOptions` 使用できます。 [][WebdriverCapabilitiesEdgeOptions]</span><span class="sxs-lookup"><span data-stu-id="e143e-194">If you set the `UseChromium` property to `true`, you may use the `EdgeOptions` class to access the same [Chromium-specific properties and methods][WebdriverCapabilitiesEdgeOptions] that are used when you automate other Chromium browsers.</span></span>  

#### [<a name="c"></a><span data-ttu-id="e143e-195">C#</span><span class="sxs-lookup"><span data-stu-id="e143e-195">C#</span></span>](#tab/c-sharp/)  

<a id="use-chromium-specific-options-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### [<a name="python"></a><span data-ttu-id="e143e-196">Python</span><span class="sxs-lookup"><span data-stu-id="e143e-196">Python</span></span>](#tab/python/)  

<a id="use-chromium-specific-options-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument("headless")
options.add_argument("disable-gpu")
```  

#### [<a name="java"></a><span data-ttu-id="e143e-197">Java</span><span class="sxs-lookup"><span data-stu-id="e143e-197">Java</span></span>](#tab/java/)  

<a id="use-chromium-specific-options-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.addArguments("headless");
options.addArguments("disable-gpu");
```  

#### [<a name="javascript"></a><span data-ttu-id="e143e-198">JavaScript</span><span class="sxs-lookup"><span data-stu-id="e143e-198">JavaScript</span></span>](#tab/javascript/)  

<a id="use-chromium-specific-options-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.addArguments("headless");
options.addArguments("disable-gpu");
```  

* * *  

> [!NOTE]
> <span data-ttu-id="e143e-199">`UseChromium`プロパティが`true` に設定されている場合は、Microsoft Edge \(EdgeHTML \) のプロパティとメソッドは使用できません。</span><span class="sxs-lookup"><span data-stu-id="e143e-199">If the `UseChromium` property is set to `true`, you are not able to use properties and methods for Microsoft Edge \(EdgeHTML\).</span></span>  

## <a name="other-webdriver-installation-options"></a><span data-ttu-id="e143e-200">その他の WebDriver インストール オプション</span><span class="sxs-lookup"><span data-stu-id="e143e-200">Other WebDriver installation options</span></span>  

### <a name="chocolatey"></a><span data-ttu-id="e143e-201">Chocolatey</span><span class="sxs-lookup"><span data-stu-id="e143e-201">Chocolatey</span></span>  

<span data-ttu-id="e143e-202">パッケージ マネージャーとして [Chocolatey][Chocolatey] を使用する場合は、次のコマンドを実行して Microsoft Edge Driver をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e143e-202">If you use [Chocolatey][Chocolatey] as your package manager, run the following command to install the Microsoft Edge Driver.</span></span>  

```console
choco install selenium-chromium-edge-driver
```  

<span data-ttu-id="e143e-203">詳細については、「チョコレートの [セレン クロム エッジ ドライバー」に移動します][ChocolateyPackagesSeleniumChromiumEdgeDriver]。</span><span class="sxs-lookup"><span data-stu-id="e143e-203">For more information, navigate to [Selenium Chromium Edge Driver on Chocolatey][ChocolateyPackagesSeleniumChromiumEdgeDriver].</span></span>  

### <a name="docker"></a><span data-ttu-id="e143e-204">Docker</span><span class="sxs-lookup"><span data-stu-id="e143e-204">Docker</span></span>  

<span data-ttu-id="e143e-205">Docker を使用 [する場合][DockerHub]は、次のコマンドを実行して、Microsoft Edge \(Chromium\) と [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] がプリインストールされた事前構成済みのイメージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e143e-205">If you use [Docker][DockerHub], run the following command to download a pre-configured image with Microsoft Edge \(Chromium\) and [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] pre-installed.</span></span>  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

<span data-ttu-id="e143e-206">詳細については、Docker Hub の [msedgedriver コンテナーに移動します][DockerHubMsedgedriver]。</span><span class="sxs-lookup"><span data-stu-id="e143e-206">For more information, navigate to the [msedgedriver container on Docker Hub][DockerHubMsedgedriver].</span></span>  

## <a name="next-steps"></a><span data-ttu-id="e143e-207">次の手順</span><span class="sxs-lookup"><span data-stu-id="e143e-207">Next steps</span></span>  

<span data-ttu-id="e143e-208">WebDriver の詳細と、Selenium を使用して自動 WebDriver テストを記述する方法については [、Selenium のドキュメントに移動します][SeleniumDocumentation]。</span><span class="sxs-lookup"><span data-stu-id="e143e-208">To learn more about WebDriver and how to write automated WebDriver tests using Selenium, navigate to the [Selenium documentation][SeleniumDocumentation].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="e143e-209">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="e143e-209">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="e143e-210">Microsoft Edge チームは、WebDriver、Selenium、Microsoft Edge の使用に関するフィードバックをお待ちしております。</span><span class="sxs-lookup"><span data-stu-id="e143e-210">The Microsoft Edge team is eager to hear your feedback about using WebDriver, Selenium, and Microsoft Edge.</span></span>  <span data-ttu-id="e143e-211">チームに質問やコメントを送信するには、Microsoft  Edge DevTools の [フィードバックの送信][アイコン][TwitterTweetEdgeDevTools]を選択するか、ツイートを送信@EdgeDevTools。</span><span class="sxs-lookup"><span data-stu-id="e143e-211">To send the team your questions and comments, choose the **Send Feedback** icon in the Microsoft Edge DevTools or send a tweet [@EdgeDevTools][TwitterTweetEdgeDevTools].</span></span>  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="e143e-213">Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン</span><span class="sxs-lookup"><span data-stu-id="e143e-213">The **Send Feedback** icon in the Microsoft Edge DevTools</span></span>  
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
