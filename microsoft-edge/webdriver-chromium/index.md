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
# <a name="use-webdriver-chromium-for-test-automation"></a><span data-ttu-id="88619-104">テスト オートメーションに WebDriver (Chromium) を使用する</span><span class="sxs-lookup"><span data-stu-id="88619-104">Use WebDriver (Chromium) for test automation</span></span>  

<span data-ttu-id="88619-105">WebDriver を使用すると、開発者はユーザーの操作をシミュレートする自動テストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="88619-105">WebDriver allows developers to create automated tests that simulate user interaction.</span></span>  <span data-ttu-id="88619-106">WebDriver のテストとシミュレーションは、次の方法で JavaScript 単体テストとは異なります。</span><span class="sxs-lookup"><span data-stu-id="88619-106">WebDriver tests and simulations differ from JavaScript unit tests in the following ways.</span></span>  

*   <span data-ttu-id="88619-107">ブラウザーで実行されている JavaScript では利用できない機能と情報にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="88619-107">Accesses functionality and information not available to JavaScript running in browsers.</span></span>  
*   <span data-ttu-id="88619-108">ユーザー イベントや OS レベルのイベントをより正確にシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="88619-108">Simulates user events or OS-level events more accurately.</span></span>  
*   <span data-ttu-id="88619-109">1 回のテスト セッションで、複数のウィンドウ、タブ、Web ページを管理します。</span><span class="sxs-lookup"><span data-stu-id="88619-109">Manages multiple windows, tabs, and webpages in a single test session.</span></span>  
*   <span data-ttu-id="88619-110">特定のコンピューターで Microsoft Edge の複数のセッションを実行します。</span><span class="sxs-lookup"><span data-stu-id="88619-110">Runs multiple sessions of Microsoft Edge on a specific machine.</span></span>  


## <a name="relationship-between-webdriver-and-other-software"></a><span data-ttu-id="88619-111">WebDriver と他のソフトウェアの関係</span><span class="sxs-lookup"><span data-stu-id="88619-111">Relationship between WebDriver and other software</span></span>

<span data-ttu-id="88619-112">WebDriver Microsoft Edgeを自動化してユーザーの操作をシミュレートするには、次の 3 つのコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="88619-112">To automate Microsoft Edge with WebDriver to simulate user interaction, you need three components:</span></span>

*  <span data-ttu-id="88619-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="88619-113">Microsoft Edge</span></span>
*  <span data-ttu-id="88619-114">Microsoft Edge ドライバー</span><span class="sxs-lookup"><span data-stu-id="88619-114">Microsoft Edge Driver</span></span>
*  <span data-ttu-id="88619-115">WebDriver テスト フレームワーク</span><span class="sxs-lookup"><span data-stu-id="88619-115">A WebDriver testing framework</span></span>

<span data-ttu-id="88619-116">これらのコンポーネント間の機能関係は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="88619-116">The functional relationship between these components is as follows.</span></span>

| <span data-ttu-id="88619-117">テクノロジ</span><span class="sxs-lookup"><span data-stu-id="88619-117">Technology</span></span> | <span data-ttu-id="88619-118">ロール</span><span class="sxs-lookup"><span data-stu-id="88619-118">Role</span></span> |
|---|---|
| <span data-ttu-id="88619-119">WebDriver</span><span class="sxs-lookup"><span data-stu-id="88619-119">WebDriver</span></span> | <span data-ttu-id="88619-120">プラットフォームおよび言語に依存しないワイヤー プロトコルの W3C 標準。</span><span class="sxs-lookup"><span data-stu-id="88619-120">A W3C standard for a platform- and language-neutral wire protocol.</span></span>  <span data-ttu-id="88619-121">このプロトコルにより、アウトプロセス プログラムは Web ブラウザーの動作をリモートで指示できます。</span><span class="sxs-lookup"><span data-stu-id="88619-121">This protocol allows out-of-process programs to remotely instruct the behavior of web browsers.</span></span> |
| <span data-ttu-id="88619-122">Microsoft Edge ドライバー</span><span class="sxs-lookup"><span data-stu-id="88619-122">Microsoft Edge Driver</span></span> | <span data-ttu-id="88619-123">Microsoft が WebDriver プロトコルを実装する場合は、このプロトコルを使用Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="88619-123">Microsoft's implementation of the WebDriver protocol specifically for Microsoft Edge.</span></span>  <span data-ttu-id="88619-124">テスト作成者は、ドライバーが受け取る WebDriver コマンドを使用Microsoft Edge記述します。</span><span class="sxs-lookup"><span data-stu-id="88619-124">Test authors write tests that use WebDriver commands that Microsoft Edge Driver receives.</span></span>  <span data-ttu-id="88619-125">Microsoft Edgeドライバーは、そのコマンドをブラウザーに通信する責任があります。</span><span class="sxs-lookup"><span data-stu-id="88619-125">Microsoft Edge Driver is then responsible for communicating that command to the browser.</span></span> |
| <span data-ttu-id="88619-126">WebDriver テスト フレームワーク</span><span class="sxs-lookup"><span data-stu-id="88619-126">A WebDriver testing framework</span></span> | <span data-ttu-id="88619-127">テスト作成者は、テスト フレームワークを使用してエンドツーエンドのテストを記述し、ブラウザーを自動化します。</span><span class="sxs-lookup"><span data-stu-id="88619-127">Test authors use a testing framework to write end-to-end tests and automate browsers.</span></span>  <span data-ttu-id="88619-128">言語固有のインターフェイスを提供し、コードをコマンドに変換し、ドライバー Microsoft Edge \(Chromium\) でMicrosoft Edge実行します。</span><span class="sxs-lookup"><span data-stu-id="88619-128">Provides a language-specific interface that translates your code into commands that Microsoft Edge Driver runs in Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="88619-129">WebDriver テスト フレームワークは、すべての主要なプラットフォームと言語に対して存在します。</span><span class="sxs-lookup"><span data-stu-id="88619-129">WebDriver testing frameworks exist for all major platforms and languages.</span></span>  <span data-ttu-id="88619-130">そのようなフレームワークの 1 つは Selenium です。</span><span class="sxs-lookup"><span data-stu-id="88619-130">One such framework is Selenium.</span></span> |
| <span data-ttu-id="88619-131">Internet Explorer ドライバー</span><span class="sxs-lookup"><span data-stu-id="88619-131">Internet Explorer Driver</span></span> | <span data-ttu-id="88619-132">WebDriver プロトコルの実装は、webDriver プロトコルのInternet Explorer。</span><span class="sxs-lookup"><span data-stu-id="88619-132">An implementation of the WebDriver protocol specifically for Internet Explorer.</span></span>  <span data-ttu-id="88619-133">従来のエンド to エンド テストを実行するには、Internet Explorerドライバーを使用Internet Explorer勧めします。</span><span class="sxs-lookup"><span data-stu-id="88619-133">To run legacy end-to-end tests for Internet Explorer, we recommend using Internet Explorer Driver.</span></span> |

<span data-ttu-id="88619-134">次のセクションでは、WebDriver for Microsoft Edge \(Chromium\) について説明します。</span><span class="sxs-lookup"><span data-stu-id="88619-134">The following sections describe how to get started with WebDriver for Microsoft Edge \(Chromium\).</span></span>  


## <a name="install-microsoft-edge-chromium"></a><span data-ttu-id="88619-135">Microsoft Edge (Chromium) をインストールする</span><span class="sxs-lookup"><span data-stu-id="88619-135">Install Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="88619-136">[Microsoft Edge (Chromium)][MicrosoftEdge] を確実にインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="88619-136">Ensure you install [Microsoft Edge (Chromium)][MicrosoftEdge].</span></span>  <span data-ttu-id="88619-137">\(Chromium\) がインストールされていることをMicrosoft Edge、に移動し、バージョン番号が `edge://settings/help` 75 以降である必要があります。</span><span class="sxs-lookup"><span data-stu-id="88619-137">To confirm that you have Microsoft Edge \(Chromium\) installed, navigate to `edge://settings/help`, and verify that the version number is 75 or later.</span></span>


## <a name="download-microsoft-edge-driver"></a><span data-ttu-id="88619-138">Microsoft Edge ドライバーをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="88619-138">Download Microsoft Edge Driver</span></span>

<span data-ttu-id="88619-139">テストの自動化を開始するには、次の手順を使用して、インストールする WebDriver のバージョンがお使いのブラウザーのバージョンと一致していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="88619-139">To begin automating tests, use the following steps to ensure that the WebDriver version you install matches your browser version.</span></span>  

1.  <span data-ttu-id="88619-140">バージョンのファイルをMicrosoft Edge。</span><span class="sxs-lookup"><span data-stu-id="88619-140">Find your version of Microsoft Edge.</span></span>  
    1.  <span data-ttu-id="88619-141">`edge://settings/help` に移動します。</span><span class="sxs-lookup"><span data-stu-id="88619-141">Navigate to `edge://settings/help`.</span></span>  
        
        :::image type="complex" source="./media/microsoft-edge-version.msft.png" alt-text="2021 年 4 月 15 日Microsoft Edgeのビルド番号" lightbox="./media/microsoft-edge-version.msft.png":::
           <span data-ttu-id="88619-143">2021 年 4 月 15 日Microsoft Edgeのビルド番号</span><span class="sxs-lookup"><span data-stu-id="88619-143">The build number for Microsoft Edge on April 15, 2021</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="88619-144">[ドライバー] [Microsoft Edge移動します][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]。</span><span class="sxs-lookup"><span data-stu-id="88619-144">Navigate to [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver].</span></span>  
1.  <span data-ttu-id="88619-145">[最新バージョン **を取得する] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="88619-145">Navigate to **Get the latest version**.</span></span>  
1.  <span data-ttu-id="88619-146">バージョン番号と一致するチャネルのビルドを選択Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="88619-146">Choose the build of channel that matches your version number of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="./media/microsoft-edge-driver-install.msft.png" alt-text="[ドライバー] Web ページの [最新バージョンを取得Microsoft Edge] セクション" lightbox="./media/microsoft-edge-driver-install.msft.png":::
       <span data-ttu-id="88619-148">[**ドライバー] Web ページの**[最新バージョンを取得[Microsoft Edge] セクション][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]</span><span class="sxs-lookup"><span data-stu-id="88619-148">The **Get the latest version** section on the [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] webpage</span></span>  
    :::image-end:::  
   
    
## <a name="choose-a-webdriver-testing-framework"></a><span data-ttu-id="88619-149">WebDriver テスト フレームワークの選択</span><span class="sxs-lookup"><span data-stu-id="88619-149">Choose a WebDriver testing framework</span></span>

<span data-ttu-id="88619-150">ドライバーをダウンロードMicrosoft Edge、最後にダウンロードする必要があるコンポーネントは、WebDriver テスト フレームワークです。</span><span class="sxs-lookup"><span data-stu-id="88619-150">After downloading Microsoft Edge Driver, the last component you must download is a WebDriver testing framework.</span></span> <span data-ttu-id="88619-151">テスト作成者は、WebDriver テスト フレームワークを使用して、エンドツーエンドのテストを記述し、ブラウザーを自動化します。</span><span class="sxs-lookup"><span data-stu-id="88619-151">Test authors use WebDriver testing frameworks to write end-to-end tests and automate browsers.</span></span> <span data-ttu-id="88619-152">フレームワークは、コード (Python、Java、C#、Ruby、JavaScript など) を Microsoft Edge Driver が Microsoft Edge \(Chromium\) で実行するコマンドに変換する言語固有のインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="88619-152">The framework provides a language-specific interface that translates your code (such as Python, Java, C#, Ruby, or JavaScript) into commands that Microsoft Edge Driver runs in Microsoft Edge \(Chromium\).</span></span> <span data-ttu-id="88619-153">WebDriver テスト フレームワークは、すべての主要なプラットフォームと言語に対して存在します。</span><span class="sxs-lookup"><span data-stu-id="88619-153">WebDriver testing frameworks exist for all major platforms and languages.</span></span>


<span data-ttu-id="88619-154">この記事では、Selenium フレームワークを使用する手順を説明しますが、WebDriver をサポートする任意のライブラリ、フレームワーク、プログラミング言語を使用できます。</span><span class="sxs-lookup"><span data-stu-id="88619-154">This article provides instructions for using the Selenium framework, but you can use any library, framework, and programming language that supports WebDriver.</span></span>  <span data-ttu-id="88619-155">Selenium 以外の WebDriver テスト フレームワークを使用して同じタスクを実行するには、選択したフレームワークの公式ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="88619-155">To accomplish the same tasks using a WebDriver testing framework other than Selenium, consult the official documentation for your framework of choice.</span></span>

<span data-ttu-id="88619-156">Selenium を使用している場合、Microsoft Edge チームは、そのバージョンの Selenium が Microsoft Edge \(Chromium\) をサポートしていますので[、Selenium 4.0.0-beta2][NugetPackagesSeleniumWebdriver400beta02]以降をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="88619-156">If you are using Selenium, the Microsoft Edge team recommends [Selenium 4.0.0-beta2][NugetPackagesSeleniumWebdriver400beta02] or later, because that version of Selenium supports Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="88619-157">ただし、現在の安定した Selenium 3 リリースMicrosoft Edge含め、以前のすべてのバージョンの Selenium で \(Chromium\) を制御できます。</span><span class="sxs-lookup"><span data-stu-id="88619-157">However, you can control Microsoft Edge \(Chromium\) in all older versions of Selenium, including the current stable Selenium 3 release.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="88619-158">以前に Microsoft Edge \(Chromium\) を使用しておよびクラスを自動化またはテストした場合 `ChromeDriver` `ChromeOptions` 、WebDriver コードは Microsoft Edge バージョン 80 以降では実行されません。</span><span class="sxs-lookup"><span data-stu-id="88619-158">If you previously automated or tested Microsoft Edge \(Chromium\) using `ChromeDriver` and `ChromeOptions` classes, your WebDriver code does not run on Microsoft Edge Version 80 or later.</span></span>  <span data-ttu-id="88619-159">この問題を解決するには、テストを更新してクラスを使用し、Driver `EdgeOptions` [Microsoft Edgeダウンロードします][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]。</span><span class="sxs-lookup"><span data-stu-id="88619-159">To solve the problem, update your tests to use the `EdgeOptions` class and download [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver].</span></span>  

### <a name="using-selenium-4"></a><span data-ttu-id="88619-160">Selenium 4 の使用</span><span class="sxs-lookup"><span data-stu-id="88619-160">Using Selenium 4</span></span>

<span data-ttu-id="88619-161">Selenium WebDriver テスト フレームワークは、任意のプラットフォームで使用できます。Java、Python、C#、Ruby、JavaScript で使用できます。</span><span class="sxs-lookup"><span data-stu-id="88619-161">The Selenium WebDriver testing framework can be used on any platform, and is available for Java, Python, C#, Ruby, and JavaScript.</span></span>

<span data-ttu-id="88619-162">Selenium 4 には、Microsoft Edge (Chromium) が組み込Chromium。</span><span class="sxs-lookup"><span data-stu-id="88619-162">Selenium 4 has built-in support for Microsoft Edge (Chromium).</span></span>  <span data-ttu-id="88619-163">Selenium 4 をインストールするには [、[Selenium ライブラリのインストール] に移動します][SeleniumInstallingLibraries]。</span><span class="sxs-lookup"><span data-stu-id="88619-163">To install Selenium 4, navigate to [Installing Selenium libraries][SeleniumInstallingLibraries].</span></span>

<span data-ttu-id="88619-164">Selenium 4 を使用する場合は、Selenium Tools を使用する必要Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="88619-164">If you use Selenium 4, you don't need to use Selenium Tools for Microsoft Edge.</span></span>  <span data-ttu-id="88619-165">Selenium Tools for Microsoft Edgeセレン 3 のみ。</span><span class="sxs-lookup"><span data-stu-id="88619-165">Selenium Tools for Microsoft Edge are for Selenium 3 only.</span></span>  <span data-ttu-id="88619-166">Selenium 4 を Selenium Tools for Microsoft Edge で使用し、新しいインスタンスを作成しようとする場合は、次のエラー `EdgeDriver` メッセージが表示されます `System.MissingMethodException: 'Method not found: 'OpenQA.Selenium.Remote.DesiredCapabilities OpenQA.Selenium.DriverOptions.GenerateDesiredCapabilities(Boolean)'` 。</span><span class="sxs-lookup"><span data-stu-id="88619-166">If you try to use Selenium 4 with Selenium Tools for Microsoft Edge and try to create a new `EdgeDriver` instance, you get the following error: `System.MissingMethodException: 'Method not found: 'OpenQA.Selenium.Remote.DesiredCapabilities OpenQA.Selenium.DriverOptions.GenerateDesiredCapabilities(Boolean)'`.</span></span>  

<span data-ttu-id="88619-167">Selenium 4 を使用してこのエラーが発生する場合は、プロジェクトから削除し、名前空間の公式クラスとクラスを `Microsoft.Edge.SeleniumTools` `EdgeOptions` `EdgeDriver` 使用 `OpenQA.Selenium.Edge` してください。</span><span class="sxs-lookup"><span data-stu-id="88619-167">If you're using Selenium 4 and get this error, remove `Microsoft.Edge.SeleniumTools` from your project, and make sure you're using the official `EdgeOptions` and `EdgeDriver` classes from the `OpenQA.Selenium.Edge` namespace.</span></span>

### <a name="using-selenium-3"></a><span data-ttu-id="88619-168">Selenium 3 の使用</span><span class="sxs-lookup"><span data-stu-id="88619-168">Using Selenium 3</span></span>  

<span data-ttu-id="88619-169">既に [Selenium 3][|::ref1::|] を使用している場合は、既存のブラウザーのテストがあり、Selenium のバージョンを変更せずに Microsoft Edge \ (Chromium \) のカバレッジを追加することを希望するかもしれません。</span><span class="sxs-lookup"><span data-stu-id="88619-169">If you already use [Selenium 3][|::ref1::|], you may have existing browser tests and want to add coverage for Microsoft Edge \(Chromium\) without changing your version of Selenium.</span></span>  <span data-ttu-id="88619-170">[Selenium 3][|::ref2::|] を使用して Microsoft Edge  \ (EdgeHTML \) と Microsoft Edge \ (Chromium \) の自動テストを作成するには更新されたドライバーを使用するために、[Microsoft Edge 用 Selenium ツール][GithubMicrosoftEdgeSeleniumTools] のパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="88619-170">To use [Selenium 3][|::ref2::|] to write automated tests for both Microsoft Edge \(EdgeHTML\) and Microsoft Edge \(Chromium\), install the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package to use the updated driver.</span></span>  <span data-ttu-id="88619-171">ツールに含まれている`EdgeDriver` と `EdgeDriverService` のクラスは、Selenium 4 の組み込みの対応物と完全互な換性があります。</span><span class="sxs-lookup"><span data-stu-id="88619-171">The `EdgeDriver` and `EdgeDriverService` classes included in the tools are fully compatible with the built-in equivalents in Selenium 4.</span></span>  

<span data-ttu-id="88619-172">Selenium 3 を使用している場合は、次の手順を使用して、プロジェクトに Microsoft Edge および[Selenium 3 の Selenium][|::ref3::|] [Tools を][GithubMicrosoftEdgeSeleniumTools]追加します。</span><span class="sxs-lookup"><span data-stu-id="88619-172">If you are using Selenium 3, use the following steps to add the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] and [Selenium 3][|::ref3::|] to your project.</span></span>

#### [<a name="c"></a><span data-ttu-id="88619-173">C#</span><span class="sxs-lookup"><span data-stu-id="88619-173">C#</span></span>](#tab/c-sharp/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="88619-174">[NUGET CLI][NugetCLI] または [Visual Studio][VisualStudio] を使用して、 [Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools] と[Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410] の各パッケージを .NET projectに追加します。</span><span class="sxs-lookup"><span data-stu-id="88619-174">Add the [Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools] and [Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410] packages to your .NET project using the [NuGet CLI][NugetCLI] or [Visual Studio][VisualStudio].</span></span>  

#### [<a name="python"></a><span data-ttu-id="88619-175">Python</span><span class="sxs-lookup"><span data-stu-id="88619-175">Python</span></span>](#tab/python/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="88619-176">[pip][PythonPip] を使用して[msedge-selenium-tools][PythonSeleniumTools] および [selenium][PythonSelenium] パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="88619-176">Use [pip][PythonPip] to install the [msedge-selenium-tools][PythonSeleniumTools] and [selenium][PythonSelenium] packages.</span></span>  

```python
pip install msedge-selenium-tools selenium==3.141
```  

#### [<a name="java"></a><span data-ttu-id="88619-177">Java</span><span class="sxs-lookup"><span data-stu-id="88619-177">Java</span></span>](#tab/java/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="88619-178">このプロジェクトJava Maven を使用している場合は、次の依存関係をファイルにコピーして貼り付け `pom.xml` [、msedge-selenium-tools-java を追加します][SonatypeMavenRepositorySearch]。</span><span class="sxs-lookup"><span data-stu-id="88619-178">If your Java project uses Maven, copy and paste the following dependency to your `pom.xml` file to add [msedge-selenium-tools-java][SonatypeMavenRepositorySearch].</span></span>  

```xml
<dependency>
    <groupId>com.microsoft.edge</groupId>
    <artifactId>msedge-selenium-tools-java</artifactId>
    <version>[3.141.0,)</version>
</dependency>
```  

<span data-ttu-id="88619-179">このJavaは、Selenium Tools for the [releases ページMicrosoft Edgeダウンロードすることもできます][GithubMicrosoftEdgeSeleniumToolsReleases]。</span><span class="sxs-lookup"><span data-stu-id="88619-179">The Java package is also available to download directly on the [Selenium Tools for Microsoft Edge Releases page][GithubMicrosoftEdgeSeleniumToolsReleases].</span></span>  

#### [<a name="javascript"></a><span data-ttu-id="88619-180">JavaScript</span><span class="sxs-lookup"><span data-stu-id="88619-180">JavaScript</span></span>](#tab/javascript/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="88619-181">[npm][JavaScript|::ref4::|] を使用して、[edge-selenium-tools][JavaScriptSeleniumTools] および [selenium-webdriver][JavaScriptSelenium] パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="88619-181">Use [npm][JavaScript|::ref4::|] to install the [edge-selenium-tools][JavaScriptSeleniumTools] and [selenium-webdriver][JavaScriptSelenium] packages.</span></span>  

```javascript
npm install @microsoft/edge-selenium-tools selenium-webdriver
```  

* * *  


## <a name="automate-microsoft-edge-chromium-with-webdriver"></a><span data-ttu-id="88619-182">WebDriver Microsoft Edge (Chromium) を自動化する</span><span class="sxs-lookup"><span data-stu-id="88619-182">Automate Microsoft Edge (Chromium) with WebDriver</span></span>  

<span data-ttu-id="88619-183">WebDriver を使用してブラウザーを自動化するには、まず優先 WebDriver テスト フレームワークを使用して WebDriver セッションを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88619-183">To automate a browser using WebDriver, you must first start a WebDriver session using your preferred WebDriver testing framework.</span></span>  <span data-ttu-id="88619-184">セッションは、WebDriver コマンドを使用して制御されるブラウザーの 1 つの実行中のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="88619-184">A session is a single running instance of a browser controlled using WebDriver commands.</span></span>  <span data-ttu-id="88619-185">WebDriver セッションを開始して、新しいブラウザー インスタンスを起動します。</span><span class="sxs-lookup"><span data-stu-id="88619-185">Start a WebDriver session to launch a new browser instance.</span></span>  <span data-ttu-id="88619-186">WebDriver セッションを閉じるまで、起動されたブラウザー インスタンスは開いたままです。</span><span class="sxs-lookup"><span data-stu-id="88619-186">The launched browser instance remains open until you close the WebDriver session.</span></span>  

<span data-ttu-id="88619-187">次のコンテンツでは、Selenium を使用して WebDriver セッションを開始し、\(Microsoft Edge\) Chromiumします。</span><span class="sxs-lookup"><span data-stu-id="88619-187">The following content walks you through using Selenium to start a WebDriver session with Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="88619-188">これらの例は、Selenium 3 または 4 を使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="88619-188">You can run these examples using either Selenium 3 or 4.</span></span>  <span data-ttu-id="88619-189">WebDriver を Selenium 3 で使用するには[、Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools]インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="88619-189">To use WebDriver with Selenium 3, the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package must be installed.</span></span>  

> [!NOTE]
> <span data-ttu-id="88619-190">この記事では、Selenium フレームワークを使用する手順を説明しますが、WebDriver をサポートする任意のライブラリ、フレームワーク、プログラミング言語を使用できます。</span><span class="sxs-lookup"><span data-stu-id="88619-190">This article provides instructions for using the Selenium framework, but you can use any library, framework, and programming language that supports WebDriver.</span></span>  <span data-ttu-id="88619-191">別のフレームワークを使用して同じタスクを実行するには、選択したフレームワークの公式ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="88619-191">To accomplish the same tasks using another framework, consult the official documentation for your framework of choice.</span></span>

### <a name="automate-microsoft-edge-chromium"></a><span data-ttu-id="88619-192">自動Microsoft Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="88619-192">Automate Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="88619-193">Selenium はクラス `EdgeDriver` を使用して、\(Microsoft Edge\) セッションChromium管理します。</span><span class="sxs-lookup"><span data-stu-id="88619-193">Selenium uses the `EdgeDriver` class to manage a Microsoft Edge \(Chromium\) session.</span></span>  <span data-ttu-id="88619-194">セッションを開始し、\(Chromium\) をMicrosoft Edgeするには、新しいオブジェクトを作成し、プロパティをに設定したオブジェクト `EdgeDriver` `EdgeOptions` `UseChromium` を渡します `true` 。</span><span class="sxs-lookup"><span data-stu-id="88619-194">To start a session and automate Microsoft Edge \(Chromium\), create a new `EdgeDriver` object and pass it an `EdgeOptions` object with the `UseChromium` property set to `true`.</span></span>  

#### [<a name="c"></a><span data-ttu-id="88619-195">C#</span><span class="sxs-lookup"><span data-stu-id="88619-195">C#</span></span>](#tab/c-sharp/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### [<a name="python"></a><span data-ttu-id="88619-196">Python</span><span class="sxs-lookup"><span data-stu-id="88619-196">Python</span></span>](#tab/python/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options = options)
```  

#### [<a name="java"></a><span data-ttu-id="88619-197">Java</span><span class="sxs-lookup"><span data-stu-id="88619-197">Java</span></span>](#tab/java/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

<span data-ttu-id="88619-198">この `EdgeDriver` クラスは Microsoft Edge\(Chromium\) のみをサポートし、\(EdgeHTML\) のMicrosoft Edgeサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="88619-198">The `EdgeDriver` class only supports Microsoft Edge \(Chromium\), and doesn't support Microsoft Edge \(EdgeHTML\).</span></span>  <span data-ttu-id="88619-199">基本的な使用方法については、指定せずに作成 `EdgeDriver` できます `EdgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="88619-199">For basic usage, you can create an `EdgeDriver` without providing `EdgeOptions`.</span></span>  

```java
EdgeDriver driver = new EdgeDriver();
```  

#### [<a name="javascript"></a><span data-ttu-id="88619-200">JavaScript</span><span class="sxs-lookup"><span data-stu-id="88619-200">JavaScript</span></span>](#tab/javascript/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);

let driver = edge.Driver.createSession(options);
```  

* * *  

> [!NOTE]
> <span data-ttu-id="88619-201">IT 管理者が[DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]ポリシーをに設定している場合 `2` [、Microsoft Edge ドライバー][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]は Microsoft Edge \(Chromium\) の駆動をブロックされます。ドライバーは Microsoft Edge [DevTools][DevtoolsIndex]を使用します。</span><span class="sxs-lookup"><span data-stu-id="88619-201">If your IT admin has set the [DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability] policy to `2`,  [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] is blocked from driving Microsoft Edge \(Chromium\), because the driver uses the [Microsoft Edge DevTools][DevtoolsIndex].</span></span>  <span data-ttu-id="88619-202">[DeveloperToolsAvailability ポリシーに設定][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]されている、または自動化するポリシー `0` `1` (Microsoft Edge) をChromium。</span><span class="sxs-lookup"><span data-stu-id="88619-202">Ensure the [DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability] policy is set to `0` or `1` to automate Microsoft Edge (Chromium).</span></span>  

### <a name="choose-specific-browser-binaries-chromium-only"></a><span data-ttu-id="88619-203">特定のブラウザー バイナリを選択する (Chromiumのみ)</span><span class="sxs-lookup"><span data-stu-id="88619-203">Choose Specific Browser Binaries (Chromium-Only)</span></span>  

<span data-ttu-id="88619-204">\(Chromium\) バイナリの特定のMicrosoft Edge WebDriver セッションを開始できます。</span><span class="sxs-lookup"><span data-stu-id="88619-204">You can start a WebDriver session with specific Microsoft Edge \(Chromium\) binaries.</span></span>  <span data-ttu-id="88619-205">たとえば、テストを実行するには、Microsoft Edge[などの][MicrosoftedgeinsiderDownload]プレビュー チャネルをMicrosoft Edge Beta。</span><span class="sxs-lookup"><span data-stu-id="88619-205">For example, you can run tests using the [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.</span></span>  

#### [<a name="c"></a><span data-ttu-id="88619-206">C#</span><span class="sxs-lookup"><span data-stu-id="88619-206">C#</span></span>](#tab/c-sharp/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### [<a name="python"></a><span data-ttu-id="88619-207">Python</span><span class="sxs-lookup"><span data-stu-id="88619-207">Python</span></span>](#tab/python/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options = options)
```  

#### [<a name="java"></a><span data-ttu-id="88619-208">Java</span><span class="sxs-lookup"><span data-stu-id="88619-208">Java</span></span>](#tab/java/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.setBinary("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

EdgeDriver driver = new EdgeDriver(options);
```  

#### [<a name="javascript"></a><span data-ttu-id="88619-209">JavaScript</span><span class="sxs-lookup"><span data-stu-id="88619-209">JavaScript</span></span>](#tab/javascript/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.setBinaryPath("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

let driver = edge.Driver.createSession(options);
```  

* * *  

### <a name="customize-the-microsoft-edge-driver-service"></a><span data-ttu-id="88619-210">ドライバー サービスMicrosoft Edgeカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="88619-210">Customize the Microsoft Edge Driver Service</span></span>  

#### [<a name="c"></a><span data-ttu-id="88619-211">C#</span><span class="sxs-lookup"><span data-stu-id="88619-211">C#</span></span>](#tab/c-sharp/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="88619-212">クラス を使用してクラス インスタンスを作成すると `EdgeOptions` `EdgeDriver` `EdgeDriverService` 、Microsoft Edge \(EdgeHTML\) または Microsoft Edge \(Chromium\) のいずれかの適切なクラスを作成して起動します。</span><span class="sxs-lookup"><span data-stu-id="88619-212">When you use the `EdgeOptions` class to create an `EdgeDriver` class instance, it creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="88619-213">を作成する場合は、メソッドを使用して `EdgeDriverService` 、\(Chromium\) 用に `CreateChromiumService()` 構成Microsoft Edge作成します。</span><span class="sxs-lookup"><span data-stu-id="88619-213">If you want to create an `EdgeDriverService`, use the `CreateChromiumService()` method to create one configured for Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="88619-214">この `CreateChromiumService()` メソッドは、カスタマイズを追加する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="88619-214">The `CreateChromiumService()` method is useful when you need to add customizations.</span></span>  <span data-ttu-id="88619-215">たとえば、次のコードは詳細ログ出力を開始します。</span><span class="sxs-lookup"><span data-stu-id="88619-215">For example, the following code starts verbose log output.</span></span>  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE] 
><span data-ttu-id="88619-216">インスタンスに渡す場合は `EdgeOptions` 、オブジェクトを指定 `EdgeDriverService` する必要 `EdgeDriver` があります。</span><span class="sxs-lookup"><span data-stu-id="88619-216">You do not need to provide the `EdgeOptions` object when you pass `EdgeDriverService` to the `EdgeDriver` instance.</span></span>  <span data-ttu-id="88619-217">このクラスは、指定したサービスに基Microsoft Edge `EdgeDriver` \(EdgeHTML\) または Microsoft Edge \(Chromium\) の既定のオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="88619-217">The `EdgeDriver` class uses the default options for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\) based on the service you provide.</span></span>  
> <span data-ttu-id="88619-218">ただし、`EdgeDriverService` と `EdgeOptions` 両方のクラスを提供する場合は、 両方が同じバージョンの Microsoft Edge に対して構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="88619-218">However, if you want to provide both `EdgeDriverService` and `EdgeOptions` classes, ensure that both are configured for the same version of Microsoft Edge.</span></span>  <span data-ttu-id="88619-219">たとえば、\(EdgeHTML\) クラスの既定Microsoft Edgeを使用し、 `EdgeDriverService` クラスChromiumプロパティを使用 `EdgeOptions` できます。</span><span class="sxs-lookup"><span data-stu-id="88619-219">For example, you may use a default Microsoft Edge \(EdgeHTML\) `EdgeDriverService` class and Chromium properties in the `EdgeOptions` class.</span></span>  <span data-ttu-id="88619-220">この `EdgeDriver` クラスは、異なるバージョンの使用を防ぐためにエラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="88619-220">The `EdgeDriver` class throws an error to prevent using different versions.</span></span>  

#### [<a name="python"></a><span data-ttu-id="88619-221">Python</span><span class="sxs-lookup"><span data-stu-id="88619-221">Python</span></span>](#tab/python/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="88619-222">Python を使用すると、 `Edge` オブジェクトによって作成および管理されます `EdgeService` 。</span><span class="sxs-lookup"><span data-stu-id="88619-222">When you use Python, the `Edge` object creates and manages the `EdgeService`.</span></span>  <span data-ttu-id="88619-223">を構成するには `EdgeService` 、次のコードに示す追加 `Edge` の引数をオブジェクトに渡します。</span><span class="sxs-lookup"><span data-stu-id="88619-223">To configure the `EdgeService`, pass extra arguments to the `Edge` object as indicated in the following code.</span></span>  

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### [<a name="java"></a><span data-ttu-id="88619-224">Java</span><span class="sxs-lookup"><span data-stu-id="88619-224">Java</span></span>](#tab/java/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="88619-225">このメソッド `createDefaultService()` を使用して `EdgeDriverService` 、\(Microsoft Edge\) 用に構成Chromiumします。</span><span class="sxs-lookup"><span data-stu-id="88619-225">Use the `createDefaultService()` method to create an `EdgeDriverService` configured for Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="88619-226">システムJavaを使用して、ドライバー サービスをカスタマイズJava。</span><span class="sxs-lookup"><span data-stu-id="88619-226">Use Java system properties to customize driver services in Java.</span></span>  <span data-ttu-id="88619-227">たとえば、次のコードでは、プロパティを `"webdriver.edge.verboseLogging"` 使用して詳細ログ出力を有効にします。</span><span class="sxs-lookup"><span data-stu-id="88619-227">For example, the following code uses the `"webdriver.edge.verboseLogging"` property to turn on verbose log output.</span></span>  

```java
System.setProperty("webdriver.edge.verboseLogging", "true");
EdgeDriverService service = EdgeDriverService.createDefaultService();
EdgeOptions options = new EdgeOptions();
EdgeDriver driver = new EdgeDriver(service, options);
```  

#### [<a name="javascript"></a><span data-ttu-id="88619-228">JavaScript</span><span class="sxs-lookup"><span data-stu-id="88619-228">JavaScript</span></span>](#tab/javascript/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="88619-229">JavaScript を使用する場合は、クラスを使用して a `Service` を作成して構成 `ServiceBuilder` します。</span><span class="sxs-lookup"><span data-stu-id="88619-229">When you use JavaScript, create and configure a `Service` with the `ServiceBuilder` class.</span></span>  <span data-ttu-id="88619-230">必要に応じて、オブジェクトを `Service` オブジェクトに渡して、 `Driver` サービスを \(and stops\) で開始できます。</span><span class="sxs-lookup"><span data-stu-id="88619-230">Optionally, you can pass the `Service` object to the `Driver` object, which starts \(and stops\) the service for you.</span></span>  
<span data-ttu-id="88619-231">を構成するには `Service` 、メソッドを使用する前にクラス `ServiceBuilder` で別のメソッドを実行 `build()` します。</span><span class="sxs-lookup"><span data-stu-id="88619-231">To configure the `Service`, run another method in the `ServiceBuilder` class before you use the `build()` method.</span></span>  <span data-ttu-id="88619-232">次に、`Driver.createSession()` メソッドのパラメーターとして`service` を渡し ます。</span><span class="sxs-lookup"><span data-stu-id="88619-232">Then pass the `service` as a parameter in the `Driver.createSession()` method.</span></span>  

```javascript
let service = new edge.ServiceBuilder().enableVerboseLogging().build();
let driver = edge.Driver.createSession(options, service);
```  

* * *  

### <a name="use-chromium-specific-options"></a><span data-ttu-id="88619-233">Chromium-固有 のオプションを使用する</span><span class="sxs-lookup"><span data-stu-id="88619-233">Use Chromium-Specific Options</span></span>  

<span data-ttu-id="88619-234">プロパティをに設定した場合は、クラスを使用して、他のブラウザーを自動化するときに使用される Chromium 固有のプロパティとメソッドにアクセスChromium `UseChromium` `true` `EdgeOptions` できます。 [][WebdriverCapabilitiesEdgeOptions]</span><span class="sxs-lookup"><span data-stu-id="88619-234">If you set the `UseChromium` property to `true`, you can use the `EdgeOptions` class to access the same [Chromium-specific properties and methods][WebdriverCapabilitiesEdgeOptions] that are used when you automate other Chromium browsers.</span></span>  

#### [<a name="c"></a><span data-ttu-id="88619-235">C#</span><span class="sxs-lookup"><span data-stu-id="88619-235">C#</span></span>](#tab/c-sharp/)  

<a id="use-chromium-specific-options-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### [<a name="python"></a><span data-ttu-id="88619-236">Python</span><span class="sxs-lookup"><span data-stu-id="88619-236">Python</span></span>](#tab/python/)  

<a id="use-chromium-specific-options-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument("headless")
options.add_argument("disable-gpu")
```  

#### [<a name="java"></a><span data-ttu-id="88619-237">Java</span><span class="sxs-lookup"><span data-stu-id="88619-237">Java</span></span>](#tab/java/)  

<a id="use-chromium-specific-options-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.addArguments("headless");
options.addArguments("disable-gpu");
```  

#### [<a name="javascript"></a><span data-ttu-id="88619-238">JavaScript</span><span class="sxs-lookup"><span data-stu-id="88619-238">JavaScript</span></span>](#tab/javascript/)  

<a id="use-chromium-specific-options-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.addArguments("headless");
options.addArguments("disable-gpu");
```  

* * *  

> [!NOTE]
> <span data-ttu-id="88619-239">`UseChromium`プロパティが`true` に設定されている場合は、Microsoft Edge \ (EdgeHTML \) のプロパティとメソッドは使用できません。</span><span class="sxs-lookup"><span data-stu-id="88619-239">If the `UseChromium` property is set to `true`, you are not able to use properties and methods for Microsoft Edge \(EdgeHTML\).</span></span>  


## <a name="other-webdriver-installation-options"></a><span data-ttu-id="88619-240">その他の WebDriver インストール オプション</span><span class="sxs-lookup"><span data-stu-id="88619-240">Other WebDriver installation options</span></span>  

### <a name="docker"></a><span data-ttu-id="88619-241">Docker</span><span class="sxs-lookup"><span data-stu-id="88619-241">Docker</span></span>  

<span data-ttu-id="88619-242">Docker を使用[する場合][DockerHub]は、次のコマンドを実行して、Microsoft Edge \(Chromium\) および Microsoft Edge [Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]がプリインストールされた構成済みのイメージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="88619-242">If you use [Docker][DockerHub], run the following command to download a pre-configured image with Microsoft Edge \(Chromium\) and [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] pre-installed.</span></span>  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

<span data-ttu-id="88619-243">詳細については、Docker Hub の [msedgedriver コンテナーに移動します][DockerHubMsedgedriver]。</span><span class="sxs-lookup"><span data-stu-id="88619-243">For more information, navigate to the [msedgedriver container on Docker Hub][DockerHubMsedgedriver].</span></span>  


## <a name="testing-internet-explorer"></a><span data-ttu-id="88619-244">テストInternet Explorer</span><span class="sxs-lookup"><span data-stu-id="88619-244">Testing Internet Explorer</span></span>

<span data-ttu-id="88619-245">必要なサイトをテストするには、Internet Explorerドライバー Internet Explorer [を使用][GithubSeleniumHqWikiIEDriver] Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="88619-245">To test sites that require Internet Explorer, use [Internet Explorer Driver][GithubSeleniumHqWikiIEDriver] with Internet Explorer.</span></span>  <span data-ttu-id="88619-246">Internet Explorerドライバーは、Selenium プロジェクトによって維持されます。</span><span class="sxs-lookup"><span data-stu-id="88619-246">Internet Explorer Driver is maintained by the Selenium project.</span></span>  <span data-ttu-id="88619-247">IE モードMicrosoft Edgeサポートされている場合でも、IE モードでサイトMicrosoft EdgeテストMicrosoft Edgeドライバーを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="88619-247">Even though Microsoft Edge supports IE Mode, you can't use Microsoft Edge Driver with Microsoft Edge to test sites in IE Mode.</span></span>


## <a name="application-guard"></a><span data-ttu-id="88619-248">Application Guard</span><span class="sxs-lookup"><span data-stu-id="88619-248">Application Guard</span></span>

<span data-ttu-id="88619-249">アプリケーション (Application Guard) をMicrosoft Defender Application Guard信頼できるサイトは、ドライバーを使用Microsoft Edgeできます。</span><span class="sxs-lookup"><span data-stu-id="88619-249">Trusted sites that use Microsoft Defender Application Guard (Application Guard) can be automated using Microsoft Edge Driver.</span></span>

<span data-ttu-id="88619-250">Application Guard を使用する信頼されていないサイトは、ドライバーを使用して自動化またはMicrosoft Edgeできません。</span><span class="sxs-lookup"><span data-stu-id="88619-250">Untrusted sites that use Application Guard cannot be automated or manipulated using Microsoft Edge Driver.</span></span>  <span data-ttu-id="88619-251">Application Guard はコンテナー内の信頼されていないサイトを起動します。このコンテナーは、ドライバーがサイトと通信するために必要Microsoft Edgeリモート デバッグ ポートを公開します。</span><span class="sxs-lookup"><span data-stu-id="88619-251">Application Guard launches untrusted sites in a container, and this container doesn't expose the remote debugging port that Microsoft Edge Driver needs to communicate with the site.</span></span>

<span data-ttu-id="88619-252">エンタープライズ管理者は、クラウド リソースや内部ネットワークなど、信頼できるサイトを定義します。</span><span class="sxs-lookup"><span data-stu-id="88619-252">Your enterprise administrator defines what are trusted sites, including cloud resources and internal networks.</span></span>  <span data-ttu-id="88619-253">信頼できるサイトの一覧に含されていないサイトは、信頼されていないと見なされます。</span><span class="sxs-lookup"><span data-stu-id="88619-253">Sites that aren't in the trusted sites list are considered untrusted.</span></span>  <span data-ttu-id="88619-254">Microsoft Edgeドライバーは、InPrivate ウィンドウと信頼できるサイトリスト内のサイトの両方を自動化できます。</span><span class="sxs-lookup"><span data-stu-id="88619-254">Microsoft Edge Driver can automate both InPrivate windows, and sites in the trusted sites list.</span></span>

<span data-ttu-id="88619-255">Application Guard の詳細については、次の場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="88619-255">For more information about Application Guard, navigate to:</span></span> 

*  [<span data-ttu-id="88619-256">Microsoft Edge での Microsoft Defender Application Guard のサポート</span><span class="sxs-lookup"><span data-stu-id="88619-256">Microsoft Edge support for Microsoft Defender Application Guard</span></span>][DeployedgeMicrosoftEdgeSecurityWindowsDefenderApplicationGuard]
*  [<span data-ttu-id="88619-257">Microsoft Defender Application Guard概要</span><span class="sxs-lookup"><span data-stu-id="88619-257">Microsoft Defender Application Guard overview</span></span>][WindowsSecurityThreatProtectionMicrosoftDefenderApplicationGuardWindows10]


## <a name="see-also"></a><span data-ttu-id="88619-258">関連項目</span><span class="sxs-lookup"><span data-stu-id="88619-258">See also</span></span>

*  <span data-ttu-id="88619-259">[Selenium のドキュメント][SeleniumDocumentation] - Selenium のコンテキストでの WebDriver に関する情報と、Selenium を使用して自動 WebDriver テストを記述する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="88619-259">[Selenium documentation][SeleniumDocumentation] - Information about WebDriver in the context of Selenium, and how to write automated WebDriver tests using Selenium.</span></span>


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="88619-260">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="88619-260">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="88619-261">このMicrosoft Edgeチームは、WebDriver、WebDriver テスト フレームワーク (Selenium など)、およびテスト フレームワークの使用に関するフィードバックを熱心にMicrosoft Edge。</span><span class="sxs-lookup"><span data-stu-id="88619-261">The Microsoft Edge team is eager to hear your feedback about using WebDriver, WebDriver testing frameworks (such as Selenium), and Microsoft Edge.</span></span>  <span data-ttu-id="88619-262">チームに質問とコメントを送信するには、DevTools の [フィードバックの送信] Microsoft Edgeを選択するか、ツイートを送信[@EdgeDevTools。][TwitterTweetEdgeDevTools] \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="88619-262">To send the team your questions and comments, choose the **Send Feedback** icon in the Microsoft Edge DevTools or send a tweet [@EdgeDevTools][TwitterTweetEdgeDevTools].</span></span>  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="88619-264">Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン</span><span class="sxs-lookup"><span data-stu-id="88619-264">The **Send Feedback** icon in the Microsoft Edge DevTools</span></span>  
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
