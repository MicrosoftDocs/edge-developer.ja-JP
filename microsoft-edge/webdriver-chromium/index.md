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
# <span data-ttu-id="5faf1-104">テスト オートメーションに WebDriver (Chromium) を使用する</span><span class="sxs-lookup"><span data-stu-id="5faf1-104">Use WebDriver (Chromium) for test automation</span></span>  

<span data-ttu-id="5faf1-105">WebDriver を使用すると、開発者はユーザーの操作をシミュレートする自動テストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5faf1-105">WebDriver allows developers to create automated tests that simulate user interaction.</span></span>  <span data-ttu-id="5faf1-106">WebDriver のテストとシミュレーションは、WebDriver が次の理由で JavaScript 単体テストとは異なります。</span><span class="sxs-lookup"><span data-stu-id="5faf1-106">WebDriver tests and simulations differ from JavaScript unit tests because WebDriver:</span></span>  

*   <span data-ttu-id="5faf1-107">ブラウザーで実行されている JavaScript では利用できない機能と情報にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="5faf1-107">Accesses functionality and information not available to JavaScript running in browsers.</span></span>  
*   <span data-ttu-id="5faf1-108">ユーザー イベントや OS レベルのイベントをより正確にシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="5faf1-108">Simulates user events or OS-level events more accurately.</span></span>  
*   <span data-ttu-id="5faf1-109">1 回のテスト セッションで、複数のウィンドウ、タブ、Web ページを管理します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-109">Manages multiple windows, tabs, and webpages in a single test session.</span></span>  
*   <span data-ttu-id="5faf1-110">特定のコンピューターで Microsoft Edge の複数のセッションを実行します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-110">Runs multiple sessions of Microsoft Edge on a specific machine.</span></span>  
    
<span data-ttu-id="5faf1-111">次のセクションでは、Microsoft Edge \ (Chromium \) の WebDriver の使用を開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-111">The following section describes how to get started with WebDriver for Microsoft Edge \(Chromium\).</span></span>  

## <span data-ttu-id="5faf1-112">Microsoft Edge (Chromium) をインストールする</span><span class="sxs-lookup"><span data-stu-id="5faf1-112">Install Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="5faf1-113">[Microsoft Edge (Chromium)][MicrosoftEdge] を確実にインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="5faf1-113">Ensure you install [Microsoft Edge (Chromium)][MicrosoftEdge].</span></span>  <span data-ttu-id="5faf1-114">Microsoft Edge\ (Chromium \) がインストールされていることを確認するには、`edge://settings/help` に移動して  、バージョン番号がバージョン 75 以降であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-114">To confirm that you have Microsoft Edge \(Chromium\) installed, navigate to `edge://settings/help`, and verify the version number is Version 75 or later.</span></span>  

## <span data-ttu-id="5faf1-115">Microsoft Edge ドライバーをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="5faf1-115">Download Microsoft Edge Driver</span></span>  

<span data-ttu-id="5faf1-116">テストの自動化を開始するには、次の手順を使用して、インストールする WebDriver のバージョンがお使いのブラウザーのバージョンと一致していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-116">To begin automating tests, use the following steps to ensure that the WebDriver version you install matches your browser version.</span></span>  

1.  <span data-ttu-id="5faf1-117">`edge://settings/help` に移動して、Microsoft Edge のバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-117">Navigate to `edge://settings/help` to get the version of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="./media/edge-version.png" alt-text="2020 年 1 月 14 日の Microsoft Edge カナリアのビルド番号":::
       <span data-ttu-id="5faf1-119">2020 年 1 月 14 日の Microsoft Edge カナリアのビルド番号</span><span class="sxs-lookup"><span data-stu-id="5faf1-119">The build number for Microsoft Edge Canary on January 14, 2020</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="5faf1-120">[Microsoft Edge ドライバーのダウンロード][MicrosoftDeveloperEdgeToolsWebdriverDownloads]ページに移動して、Microsoft edge のバージョン番号と一致するドライバーをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="5faf1-120">Navigate to the [Microsoft Edge Driver downloads][MicrosoftDeveloperEdgeToolsWebdriverDownloads] page and download the driver that matches the version number of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="./media/edge-driver-install.png" alt-text="Microsoft Edge ドライバー ページのダウンロード セクション":::
       <span data-ttu-id="5faf1-122">[Microsoft Edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriver]ページのダウンロードセクション</span><span class="sxs-lookup"><span data-stu-id="5faf1-122">The Downloads section of the [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver] page</span></span>
    :::image-end:::  
    
    <!--  
    > [!NOTE] 
    > For more information about test automation using Microsoft Edge (EdgeHTML), see [Microsoft WebDriver for Microsoft Edge (EdgeHTML)][Webdriver].  
    -->  

## <span data-ttu-id="5faf1-123">WebDriver 言語バインドの選択</span><span class="sxs-lookup"><span data-stu-id="5faf1-123">Choose a WebDriver language binding</span></span>  

<span data-ttu-id="5faf1-124">ダウンロードする必要がある最後のコンポーネントは、コード \(Python、 Java、 C\#, Ruby、 JavaScript\) を、Microsoft Edge \(Chromium\)でMicrosoft Edge ドライバーが実行するコマンドに変換するための言語固有のクライアント ドライバーです。</span><span class="sxs-lookup"><span data-stu-id="5faf1-124">The last component you must download is a language-specific client driver to translate your code \(Python, Java, C\#, Ruby, JavaScript\) into commands the Microsoft Edge Driver runs in Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="5faf1-125">[選択した WebDriver 言語バインドをダウンロードします][SeleniumDownloads]。</span><span class="sxs-lookup"><span data-stu-id="5faf1-125">[Download the WebDriver language binding of your choice][SeleniumDownloads].</span></span>  <span data-ttu-id="5faf1-126">Microsoft Edge チームは、Microsoft Edge \(Chromium\) をサポートしている [Selenium 4.00-alpha07][NugetPackagesSeleniumWebdriver400alpha07] 以降を推奨しています。</span><span class="sxs-lookup"><span data-stu-id="5faf1-126">The Microsoft Edge team recommends [Selenium 4.00-alpha07][NugetPackagesSeleniumWebdriver400alpha07] or later, because it supports Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="5faf1-127">ただし、現在の安定した Selenium 3 リリースを含む、Selenium のすべての旧バージョンで Microsoft Edge \ (Chromium \) を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="5faf1-127">However, you may control Microsoft Edge \(Chromium\) in all older versions of Selenium, including the current stable Selenium 3 release.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="5faf1-128">以前に `ChromeDriver` と `ChromeOptions`を使って Microsoft Edge \ (Chromium \) の自動化またはテストを行ったことがある場合、WebDriver コードは Microsoft Edge バージョン 80 以降では実行されません。</span><span class="sxs-lookup"><span data-stu-id="5faf1-128">If you were previously automating or testing Microsoft Edge \(Chromium\) using `ChromeDriver` and `ChromeOptions` classes, your WebDriver code does not run on Microsoft Edge Version 80 or later.</span></span>  <span data-ttu-id="5faf1-129">この問題を解決するには、クラスを使ってテストを更新し `EdgeOptions` [、Microsoft Edge ドライバーをダウンロードします][MicrosoftDeveloperEdgeToolsWebdriver]。</span><span class="sxs-lookup"><span data-stu-id="5faf1-129">To solve this problem, update your tests to use the `EdgeOptions` class and download [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver].</span></span>  

### <span data-ttu-id="5faf1-130">Selenium 3 を使用する</span><span class="sxs-lookup"><span data-stu-id="5faf1-130">Use Selenium 3</span></span>  

<span data-ttu-id="5faf1-131">既に [Selenium 3][|::ref1::|] を使用している場合は、既存のブラウザーのテストがあり、Selenium のバージョンを変更せずに Microsoft Edge \ (Chromium \) のカバレッジを追加することを希望するかもしれません。</span><span class="sxs-lookup"><span data-stu-id="5faf1-131">If you already use [Selenium 3][|::ref1::|], you may have existing browser tests and want to add coverage for Microsoft Edge \(Chromium\) without changing your version of Selenium.</span></span>  <span data-ttu-id="5faf1-132">[Selenium 3][|::ref2::|] を使用して Microsoft Edge  \ (EdgeHTML \) と Microsoft Edge \ (Chromium \) の自動テストを作成するには更新されたドライバーを使用するために、[Microsoft Edge 用 Selenium ツール][GithubMicrosoftEdgeSeleniumTools] のパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5faf1-132">To use [Selenium 3][|::ref2::|] to write automated tests for both Microsoft Edge \(EdgeHTML\) and Microsoft Edge \(Chromium\), install the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package to use the updated driver.</span></span>  <span data-ttu-id="5faf1-133">ツールに含まれている`EdgeDriver` と `EdgeDriverService` のクラスは、Selenium 4 の組み込みの対応物と完全互な換性があります。</span><span class="sxs-lookup"><span data-stu-id="5faf1-133">The `EdgeDriver` and `EdgeDriverService` classes included in the tools are fully compatible with the built-in equivalents in Selenium 4.</span></span>  

<span data-ttu-id="5faf1-134">次の手順を使用して、[Microsoft Edge 用Selenium ツール][GithubMicrosoftEdgeSeleniumTools] と [Selenium 3][|::ref3::|] をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-134">Use the following steps to add the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] and [Selenium 3][|::ref3::|] to your project.</span></span>  

#### [<span data-ttu-id="5faf1-135">C#</span><span class="sxs-lookup"><span data-stu-id="5faf1-135">C#</span></span>](#tab/c-sharp/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="5faf1-136">[NUGET CLI][NugetCLI] または [Visual Studio][VisualStudio] を使用して、 [Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools] と[Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410] の各パッケージを .NET projectに追加します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-136">Add the [Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools] and [Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410] packages to your .NET project using the [NuGet CLI][NugetCLI] or [Visual Studio][VisualStudio].</span></span>  

#### [<span data-ttu-id="5faf1-137">Python</span><span class="sxs-lookup"><span data-stu-id="5faf1-137">Python</span></span>](#tab/python/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="5faf1-138">[pip][PythonPip] を使用して[msedge-selenium-tools][PythonSeleniumTools] および [selenium][PythonSelenium] パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5faf1-138">Use [pip][PythonPip] to install the [msedge-selenium-tools][PythonSeleniumTools] and [selenium][PythonSelenium] packages.</span></span>  

```python
pip install msedge-selenium-tools selenium==3.141
```  

#### [<span data-ttu-id="5faf1-139">Java</span><span class="sxs-lookup"><span data-stu-id="5faf1-139">Java</span></span>](#tab/java/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="5faf1-140">プロジェクトJava Maven を使用している場合は、次の依存関係をファイルに対処して [msedge-selenium-tools-java][SonatypeMavenRepositorySearch] を追加 `pom.xml` します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-140">If your Java project uses Maven, add [msedge-selenium-tools-java][SonatypeMavenRepositorySearch] by coping the following dependency to your `pom.xml` file:</span></span>  

```xml
<dependency>
    <groupId>com.microsoft.edge</groupId>
    <artifactId>msedge-selenium-tools-java</artifactId>
    <version>[3.141.0,)</version>
</dependency>
```  

<span data-ttu-id="5faf1-141">The Java package is also available to download directly on the [Selenium Tools for Microsoft Edge Releases page][GithubMicrosoftEdgeSeleniumToolsReleases].</span><span class="sxs-lookup"><span data-stu-id="5faf1-141">The Java package is also available to download directly on the [Selenium Tools for Microsoft Edge Releases page][GithubMicrosoftEdgeSeleniumToolsReleases].</span></span>  

#### [<span data-ttu-id="5faf1-142">JavaScript</span><span class="sxs-lookup"><span data-stu-id="5faf1-142">JavaScript</span></span>](#tab/javascript/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="5faf1-143">[npm][JavaScript|::ref4::|] を使用して、[edge-selenium-tools][JavaScriptSeleniumTools] および [selenium-webdriver][JavaScriptSelenium] パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5faf1-143">Use [npm][JavaScript|::ref4::|] to install the [edge-selenium-tools][JavaScriptSeleniumTools] and [selenium-webdriver][JavaScriptSelenium] packages.</span></span>  

```javascript
npm install @microsoft/edge-selenium-tools selenium-webdriver
```  

* * *  

## <span data-ttu-id="5faf1-144">WebDriver を使用して Microsoft Edge (Chromium) を自動化する</span><span class="sxs-lookup"><span data-stu-id="5faf1-144">Automate Microsoft Edge (Chromium) with WebDriver</span></span>  

<span data-ttu-id="5faf1-145">WebDriver を使用してブラウザーを自動化するには、優先する WebDriver 言語バインドを使用して WebDriver セッションを最初に開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5faf1-145">To automate a browser using WebDriver, you must first start a WebDriver session using your preferred WebDriver language binding.</span></span>  <span data-ttu-id="5faf1-146">セッションは、WebDriver コマンドを使用して制御できるブラウザーの単一の実行中インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="5faf1-146">A session is a single running instance of a browser that can be controlled using WebDriver commands.</span></span>  <span data-ttu-id="5faf1-147">WebDriver セッションを開始すると、新しいブラウザー インスタンスが起動します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-147">Starting a WebDriver session launches a new browser instance.</span></span>  <span data-ttu-id="5faf1-148">WebDriver セッションを閉じるまで、起動されたブラウザーは開いたままです。</span><span class="sxs-lookup"><span data-stu-id="5faf1-148">The browser that is launched remains open until you close the WebDriver session.</span></span>  

<span data-ttu-id="5faf1-149">次のコンテンツでは、Selenium を使用して Microsoft Edge \(Chromium\) との WebDriver セッションを開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-149">The following content walks you through using Selenium to start a WebDriver session with Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="5faf1-150">これらの例は、Selenium 3 または 4 を使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="5faf1-150">You may run theses examples using either Selenium 3 or 4.</span></span>  <span data-ttu-id="5faf1-151">Selenium 3 で使用するには、[Microsoft Edge用 Selenium Tools][GithubMicrosoftEdgeSeleniumTools] をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5faf1-151">To use with Selenium 3, the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package must be installed.</span></span>  

### <span data-ttu-id="5faf1-152">Microsoft Edge (Chromium) の自動化</span><span class="sxs-lookup"><span data-stu-id="5faf1-152">Automating Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="5faf1-153">Selenium は、クラス `EdgeDriver` を使用して Microsoft Edge \(Chromium\) セッションを管理します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-153">Selenium uses the `EdgeDriver` class to manage a Microsoft Edge \(Chromium\) session.</span></span> <span data-ttu-id="5faf1-154">セッションを開始し、Microsoft Edge \(Chromium\) を自動化するには、新しいオブジェクトを作成し、プロパティを設定したオブジェクト `EdgeDriver` `EdgeOptions` `UseChromium` を渡します `true` 。</span><span class="sxs-lookup"><span data-stu-id="5faf1-154">To start a session and automate Microsoft Edge \(Chromium\), create a new `EdgeDriver` object and pass it an `EdgeOptions` object with the `UseChromium` property set to `true`.</span></span>  

#### [<span data-ttu-id="5faf1-155">C#</span><span class="sxs-lookup"><span data-stu-id="5faf1-155">C#</span></span>](#tab/c-sharp/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### [<span data-ttu-id="5faf1-156">Python</span><span class="sxs-lookup"><span data-stu-id="5faf1-156">Python</span></span>](#tab/python/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options)
```  

#### [<span data-ttu-id="5faf1-157">Java</span><span class="sxs-lookup"><span data-stu-id="5faf1-157">Java</span></span>](#tab/java/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

<span data-ttu-id="5faf1-158">この `EdgeDriver` クラスは Microsoft Edge (Chromium) のみをサポートし、Microsoft Edge (EdgeHTML) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5faf1-158">The `EdgeDriver` class supports Microsoft Edge (Chromium) only, and does not support Microsoft Edge (EdgeHTML).</span></span> <span data-ttu-id="5faf1-159">基本的な使用方法として、指定せずに作成 `EdgeDriver` できます `EdgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="5faf1-159">For basic usage, you may create an `EdgeDriver` without providing `EdgeOptions`.</span></span>  

```java
EdgeDriver driver = new EdgeDriver();
```  

#### [<span data-ttu-id="5faf1-160">JavaScript</span><span class="sxs-lookup"><span data-stu-id="5faf1-160">JavaScript</span></span>](#tab/javascript/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);

let driver = edge.Driver.createSession(options);
```  

* * *  

> [!NOTE]
> <span data-ttu-id="5faf1-161">IT 管理者が [DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability] ポリシーを `2` に設定している場合、[Microsoft Edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriver] はMicrosoft Edge (Chromium) をドライブできません。なぜなら、ドライバーは[Microsoft Edge DevTools][DevtoolsIndex]を使用しているからです。</span><span class="sxs-lookup"><span data-stu-id="5faf1-161">If your IT admin has set the [DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability] policy to `2`, [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver] is not be able to drive Microsoft Edge (Chromium) because the driver uses the [Microsoft Edge DevTools][DevtoolsIndex].</span></span>  <span data-ttu-id="5faf1-162">[DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]ポリシーが Microsoft `0` `1` Edge (Chromium) に設定または自動化されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5faf1-162">Ensure the [DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability] policy is set to `0` or `1` to automate Microsoft Edge (Chromium).</span></span>  

### <span data-ttu-id="5faf1-163">特定のブラウザーのバイナリを選択する (Chromium のみ)</span><span class="sxs-lookup"><span data-stu-id="5faf1-163">Choosing Specific Browser Binaries (Chromium-Only)</span></span>  

<span data-ttu-id="5faf1-164">特定の Microsoft Edge \(Chromium\) バイナリを使用して WebDriver セッションを開始できます。</span><span class="sxs-lookup"><span data-stu-id="5faf1-164">You may start a WebDriver session with specific Microsoft Edge \(Chromium\) binaries.</span></span>  <span data-ttu-id="5faf1-165">たとえば、Microsoft Edge ベータ版などの [Microsoft Edge preview チャネル][MicrosoftedgeinsiderDownload] を使用してテストを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5faf1-165">For example, you may run tests using the [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.</span></span>  

#### [<span data-ttu-id="5faf1-166">C#</span><span class="sxs-lookup"><span data-stu-id="5faf1-166">C#</span></span>](#tab/c-sharp/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### [<span data-ttu-id="5faf1-167">Python</span><span class="sxs-lookup"><span data-stu-id="5faf1-167">Python</span></span>](#tab/python/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options)
```  

#### [<span data-ttu-id="5faf1-168">Java</span><span class="sxs-lookup"><span data-stu-id="5faf1-168">Java</span></span>](#tab/java/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.setBinary("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

EdgeDriver driver = new EdgeDriver(options);
```  

#### [<span data-ttu-id="5faf1-169">JavaScript</span><span class="sxs-lookup"><span data-stu-id="5faf1-169">JavaScript</span></span>](#tab/javascript/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.setBinaryPath("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

let driver = edge.Driver.createSession(options);
```  

* * *  

### <span data-ttu-id="5faf1-170">Microsoft Edge ドライバー サービスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="5faf1-170">Customizing the Microsoft Edge Driver Service</span></span>  

#### [<span data-ttu-id="5faf1-171">C#</span><span class="sxs-lookup"><span data-stu-id="5faf1-171">C#</span></span>](#tab/c-sharp/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="5faf1-172">`EdgeDriver` クラス インスタンスが`EdgeOptions` クラスを使用して作成されると、Microsoft Edge \ (EdgeHTML \) または Microsoft Edge \ (Chromium \) のいずれかのために、適切な`EdgeDriverService` クラスが作成されて起動します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-172">When an `EdgeDriver` class instance is created using `EdgeOptions` class, it creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="5faf1-173">`EdgeDriverService` を作成する場合は`CreateChromiumService()`メソッドを使用して Microsoft Edge \ (Chromium \) 用に構成されたものを作成します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-173">If you want to create an `EdgeDriverService`, create one configured for Microsoft Edge \(Chromium\) using the `CreateChromiumService()` method.</span></span>  <span data-ttu-id="5faf1-174">カスタマイズを追加する必要がある場合に便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="5faf1-174">You may find it useful when you need to add customizations.</span></span> <span data-ttu-id="5faf1-175">たとえば、次のコードは詳細ログ出力を開始します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-175">For example, the following code starts verbose log output.</span></span>  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE] 
><span data-ttu-id="5faf1-176">`EdgeDriver`インスタンスに `EdgeDriverService` を渡すときに、`EdgeOptions`オブジェクトを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5faf1-176">You do not need to provide the `EdgeOptions` object when passing `EdgeDriverService` to the `EdgeDriver` instance.</span></span>  <span data-ttu-id="5faf1-177">この `EdgeDriver` クラスは、提供するサービスに基づいて、Microsoft Edge \(EdgeHTML\) または Microsoft Edge \(Chromium\) の既定のオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-177">The `EdgeDriver` class uses the default options for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\) based on the service you provide.</span></span>  
> <span data-ttu-id="5faf1-178">ただし、`EdgeDriverService` と `EdgeOptions` 両方のクラスを提供する場合は、 両方が同じバージョンの Microsoft Edge に対して構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-178">However, if you want to provide both `EdgeDriverService` and `EdgeOptions` classes, ensure that both are configured for the same version of Microsoft Edge.</span></span>  <span data-ttu-id="5faf1-179">たとえば、既定の Microsoft Edge \ (EdgeHTML \)`EdgeDriverService` クラスと `EdgeOptions` のクラスのChromium プロパティを使うことはできません  。</span><span class="sxs-lookup"><span data-stu-id="5faf1-179">For example, it is not possible to use a default Microsoft Edge \(EdgeHTML\) `EdgeDriverService` class and Chromium properties in the `EdgeOptions` class.</span></span>  <span data-ttu-id="5faf1-180">この `EdgeDriver` クラスは、異なるバージョンの使用を防ぐためにエラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="5faf1-180">The `EdgeDriver` class throws an error to prevent using different versions.</span></span>  

#### [<span data-ttu-id="5faf1-181">Python</span><span class="sxs-lookup"><span data-stu-id="5faf1-181">Python</span></span>](#tab/python/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="5faf1-182">Python を使っている場合、`Edge` オブジェクトは`EdgeService` を作成して管理します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-182">When using Python, the `Edge` object creates and manages the `EdgeService`.</span></span>  <span data-ttu-id="5faf1-183">`EdgeService` を構成するには、次のコードで示されているように、`Edge` のオブジェクトに追加の引数を渡します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-183">To configure the `EdgeService`, pass additional arguments to the `Edge` object as indicated in the following code.</span></span>  

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### [<span data-ttu-id="5faf1-184">Java</span><span class="sxs-lookup"><span data-stu-id="5faf1-184">Java</span></span>](#tab/java/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="5faf1-185">このメソッド `createDefaultService()` を使用して `EdgeDriverService` 、Microsoft Edge \(Chromium\) 用に構成された構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-185">Use the `createDefaultService()` method to create an `EdgeDriverService` configured for Microsoft Edge \(Chromium\).</span></span> <span data-ttu-id="5faf1-186">ドライバー サービスは、Javaプロパティを使用してJavaカスタマイズされます。</span><span class="sxs-lookup"><span data-stu-id="5faf1-186">Driver services in Java are customized using Java system properties.</span></span> <span data-ttu-id="5faf1-187">たとえば、次のコードはプロパティを使用 `"webdriver.edge.verboseLogging"` して詳細ログ出力を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5faf1-187">For example, the following code uses the `"webdriver.edge.verboseLogging"` property to enable verbose log output.</span></span>  

```java
System.setProperty("webdriver.edge.verboseLogging", "true");
EdgeDriverService service = EdgeDriverService.createDefaultService();
EdgeOptions options = new EdgeOptions();
EdgeDriver driver = new EdgeDriver(service, options);
```  

#### [<span data-ttu-id="5faf1-188">JavaScript</span><span class="sxs-lookup"><span data-stu-id="5faf1-188">JavaScript</span></span>](#tab/javascript/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="5faf1-189">JavaScript を使っている場合は、`Service` を`ServiceBuilder` クラスで作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-189">When using JavaScript, create and configure a `Service` with the `ServiceBuilder` class.</span></span>  <span data-ttu-id="5faf1-190">任意で、`Service` オブジェクトを`Driver` オブジェクトに渡すことができます。それによって、サービスが開始\(および 停止\) します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-190">Optionally, you may pass the `Service` object to the `Driver` object, which starts \(and stops\) the service for you.</span></span>  
<span data-ttu-id="5faf1-191">構成するには、 `Service` メソッドを使用する前にクラスで `ServiceBuilder` 別のメソッドを実行 `build()` します。</span><span class="sxs-lookup"><span data-stu-id="5faf1-191">To configure the `Service`, run another method in the `ServiceBuilder` class before using the `build()` method.</span></span>  <span data-ttu-id="5faf1-192">次に、`Driver.createSession()` メソッドのパラメーターとして`service` を渡し ます。</span><span class="sxs-lookup"><span data-stu-id="5faf1-192">Then pass the `service` as a parameter in the `Driver.createSession()` method.</span></span>  

```javascript
let service = new edge.ServiceBuilder().enableVerboseLogging().build();
let driver = edge.Driver.createSession(options, service);
```  

* * *  

### <span data-ttu-id="5faf1-193">Chromium-固有 のオプションを使用する</span><span class="sxs-lookup"><span data-stu-id="5faf1-193">Use Chromium-Specific Options</span></span>  

<span data-ttu-id="5faf1-194">プロパティを設定した場合は、他の Chromium ブラウザーを自動化するときに使用されるのと同じ Chromium 固有のプロパティとメソッドにクラスを `UseChromium` `true` `EdgeOptions` 使用してアクセスできます。 [][WebdriverCapabilitiesEdgeOptions]</span><span class="sxs-lookup"><span data-stu-id="5faf1-194">If you set the `UseChromium` property to `true`, you may use the `EdgeOptions` class to access the same [Chromium-specific properties and methods][WebdriverCapabilitiesEdgeOptions] that are used when automating other Chromium browsers.</span></span>  

#### [<span data-ttu-id="5faf1-195">C#</span><span class="sxs-lookup"><span data-stu-id="5faf1-195">C#</span></span>](#tab/c-sharp/)  

<a id="using-chromium-specific-options-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### [<span data-ttu-id="5faf1-196">Python</span><span class="sxs-lookup"><span data-stu-id="5faf1-196">Python</span></span>](#tab/python/)  

<a id="using-chromium-specific-options-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument("headless")
options.add_argument("disable-gpu")
```  

#### [<span data-ttu-id="5faf1-197">Java</span><span class="sxs-lookup"><span data-stu-id="5faf1-197">Java</span></span>](#tab/java/)  

<a id="using-chromium-specific-options-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.addArguments("headless");
options.addArguments("disable-gpu");
```  

#### [<span data-ttu-id="5faf1-198">JavaScript</span><span class="sxs-lookup"><span data-stu-id="5faf1-198">JavaScript</span></span>](#tab/javascript/)  

<a id="using-chromium-specific-options-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.addArguments("headless");
options.addArguments("disable-gpu");
```  

* * *  

> [!NOTE]
> <span data-ttu-id="5faf1-199">`UseChromium`プロパティが`true` に設定されている場合は、Microsoft Edge \ (EdgeHTML \) のプロパティとメソッドは使用できません。</span><span class="sxs-lookup"><span data-stu-id="5faf1-199">If the `UseChromium` property is set to `true`, you are not able to use properties and methods for Microsoft Edge \(EdgeHTML\).</span></span>  

## <span data-ttu-id="5faf1-200">その他の WebDriver のインストール オプション</span><span class="sxs-lookup"><span data-stu-id="5faf1-200">Additional WebDriver installation options</span></span>  

### <span data-ttu-id="5faf1-201">Chocolatey</span><span class="sxs-lookup"><span data-stu-id="5faf1-201">Chocolatey</span></span>  

<span data-ttu-id="5faf1-202">パッケージ マネージャーとして [Chocolatey][Chocolatey] を使用している場合は、次のコマンドを実行して Microsoft Edge ドライバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5faf1-202">If you use [Chocolatey][Chocolatey] as your package manager, install the Microsoft Edge Driver by running the following command.</span></span>  

```console
choco install selenium-chromium-edge-driver
```  

<span data-ttu-id="5faf1-203">詳細については、「[Chocolatey の Selenium Chromium Edge ドライバー][ChocolateyPackagesSeleniumChromiumEdgeDriver]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5faf1-203">For more information, see [Selenium Chromium Edge Driver on Chocolatey][ChocolateyPackagesSeleniumChromiumEdgeDriver].</span></span>  

### <span data-ttu-id="5faf1-204">Docker</span><span class="sxs-lookup"><span data-stu-id="5faf1-204">Docker</span></span>  

<span data-ttu-id="5faf1-205">[Docker][DockerHub] を使用している場合は、次のコマンドを実行して、Microsoft Edge\ (Chromium \) と[Microsoft Edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriver] が事前インストールされている事前構成済みイメージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="5faf1-205">If you use [Docker][DockerHub], download a pre-configured image with Microsoft Edge \(Chromium\) and [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver] pre-installed by running the following command.</span></span>  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

<span data-ttu-id="5faf1-206">詳細については、Docker Hub の [msedgedriver コンテナーに移動します][DockerHubMsedgedriver]。</span><span class="sxs-lookup"><span data-stu-id="5faf1-206">For more information, navigate to the [msedgedriver container on Docker Hub][DockerHubMsedgedriver].</span></span>  

## <span data-ttu-id="5faf1-207">次のステップ</span><span class="sxs-lookup"><span data-stu-id="5faf1-207">Next steps</span></span>

<span data-ttu-id="5faf1-208">WebDriver の詳細と、Selenium を使用して自動化された WebDriver テストを作成する方法については [、Selenium のドキュメントに移動してください][SeleniumDocumentation]。</span><span class="sxs-lookup"><span data-stu-id="5faf1-208">To learn more about WebDriver and how to write automated WebDriver tests using Selenium, navigate to the [Selenium documentation][SeleniumDocumentation].</span></span>  

## <span data-ttu-id="5faf1-209">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="5faf1-209">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="5faf1-210">Microsoft Edge チームは、WebDriver、Selenium、Microsoft Edge の使用に関するフィードバックをお待ちしております。</span><span class="sxs-lookup"><span data-stu-id="5faf1-210">The Microsoft Edge team is eager to hear your feedback about using WebDriver, Selenium, and Microsoft Edge.</span></span>  <span data-ttu-id="5faf1-211">チームに質問やコメントを送信するには、Microsoft \*\*\*\* Edge DevTools の [フィードバックの送信] アイコンを選択するか、ツイートを送信[@EdgeDevTools。][TwitterTweetEdgeDevTools]</span><span class="sxs-lookup"><span data-stu-id="5faf1-211">To send the team your questions and comments, choose the **Send Feedback** icon in the Microsoft Edge DevTools or send a tweet [@EdgeDevTools][TwitterTweetEdgeDevTools].</span></span>  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="5faf1-213">Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン</span><span class="sxs-lookup"><span data-stu-id="5faf1-213">The **Send Feedback** icon in the Microsoft Edge DevTools</span></span>  
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
