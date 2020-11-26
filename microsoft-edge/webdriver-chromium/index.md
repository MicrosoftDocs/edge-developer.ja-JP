---
description: Microsoft Edge で web サイトまたはアプリをテストする方法、または WebDriver でブラウザーを自動化する方法について説明します。
title: WebDriver (Chromium)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/25/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 開発、html、css、javascript、開発者、webdriver、selenium、テスト、ツール、オートメーション、テスト
ms.openlocfilehash: 3c197a83dbf16c68102ff6e9a4ee6f33b0573af2
ms.sourcegitcommit: 2e14ff82350f700d7eabc8d33b3ec3e5fc8c61fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "11192255"
---
# <span data-ttu-id="a674b-104">テストオートメーションに WebDriver (Chromium) を使用する</span><span class="sxs-lookup"><span data-stu-id="a674b-104">Use WebDriver (Chromium) for test automation</span></span>  

<span data-ttu-id="a674b-105">WebDriver を使うと、ユーザーの操作をシミュレートする自動テストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a674b-105">WebDriver enables you \(developers\) to create automated tests that simulate user interaction.</span></span>  <span data-ttu-id="a674b-106">WebDriver のテストとシミュレーションは、次の理由から、JavaScript 単体テストとは異なります。</span><span class="sxs-lookup"><span data-stu-id="a674b-106">WebDriver tests and simulations differ from JavaScript unit tests because of the following reasons.</span></span>  

*   <span data-ttu-id="a674b-107">ブラウザーで実行されている JavaScript では利用できない機能と情報にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a674b-107">Accesses functionality and information not available to JavaScript running in browsers.</span></span>  
*   <span data-ttu-id="a674b-108">ユーザーイベントや OS レベルのイベントをより正確にシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="a674b-108">Simulates user events or OS-level events more accurately.</span></span>  
*   <span data-ttu-id="a674b-109">1回のテストセッションで、複数のウィンドウ、タブ、web ページを管理します。</span><span class="sxs-lookup"><span data-stu-id="a674b-109">Manages multiple windows, tabs, and webpages in a single test session.</span></span>  
*   <span data-ttu-id="a674b-110">特定のコンピューターで Microsoft Edge の複数のセッションを実行します。</span><span class="sxs-lookup"><span data-stu-id="a674b-110">Runs multiple sessions of Microsoft Edge on a specific machine.</span></span>  
    
<span data-ttu-id="a674b-111">次のセクションでは、Microsoft Edge \ (Chromium \) の WebDriver の使用を開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a674b-111">The following section describes how to get started with WebDriver for Microsoft Edge \(Chromium\).</span></span>  

## <span data-ttu-id="a674b-112">Microsoft Edge をインストールする (Chromium)</span><span class="sxs-lookup"><span data-stu-id="a674b-112">Install Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="a674b-113">[Microsoft Edge (Chromium)][MicrosoftEdge]をインストールしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a674b-113">Ensure you install [Microsoft Edge (Chromium)][MicrosoftEdge].</span></span>  <span data-ttu-id="a674b-114">Microsoft Edge \ (Chromium \) がインストールされていることを確認するには、に移動して `edge://settings/help` 、バージョン番号がバージョン75以降であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a674b-114">To confirm that you have Microsoft Edge \(Chromium\) installed, navigate to `edge://settings/help`, and verify the version number is Version 75 or later.</span></span>  

## <span data-ttu-id="a674b-115">Microsoft Edge ドライバーをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="a674b-115">Download Microsoft Edge Driver</span></span>  

<span data-ttu-id="a674b-116">テストの自動化を開始するには、次の手順を使用して、インストールした WebDriver のバージョンがお使いのブラウザーのバージョンと一致していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a674b-116">To begin automating tests, use the following steps to ensure that the WebDriver version you install matches your browser version.</span></span>  

1.  <span data-ttu-id="a674b-117">に移動し `edge://settings/help` て、Microsoft Edge のバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="a674b-117">Navigate to `edge://settings/help` to get the version of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="../media/webdriver-chromium/edge-version.png" alt-text="2020年1月14日の Microsoft Edge カナリアのビルド番号" lightbox="../media/webdriver-chromium/edge-version.png":::
       <span data-ttu-id="a674b-119">2020年1月14日の Microsoft Edge カナリアのビルド番号</span><span class="sxs-lookup"><span data-stu-id="a674b-119">The build number for Microsoft Edge Canary on January 14, 2020</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="a674b-120">[Microsoft Edge ドライバーのダウンロード][MicrosoftDeveloperEdgeToolsWebdriverDownloads]ページに移動して、microsoft edge のバージョン番号と一致するドライバーをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a674b-120">Navigate to the [Microsoft Edge Driver downloads][MicrosoftDeveloperEdgeToolsWebdriverDownloads] page and download the driver that matches the version number of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="../media/webdriver-chromium/edge-driver-install.png" alt-text="Microsoft Edge ドライバーページのダウンロードセクション" lightbox="../media/webdriver-chromium/edge-driver-install.png":::
       <span data-ttu-id="a674b-122">[Microsoft Edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriver]ページのダウンロードセクション</span><span class="sxs-lookup"><span data-stu-id="a674b-122">The Downloads section of the [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver] page</span></span>  
    :::image-end:::  
    
    > [!NOTE] 
    > <span data-ttu-id="a674b-123">Microsoft Edge \ (EdgeHTML \) を使用したテストオートメーションの詳細については、microsoft office [WebDriver For Microsoft edge (EdgeHTML)][Webdriver]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a674b-123">For more information about test automation using Microsoft Edge \(EdgeHTML\), see [Microsoft WebDriver for Microsoft Edge (EdgeHTML)][Webdriver].</span></span>  
    
## <span data-ttu-id="a674b-124">WebDriver 言語バインドの選択</span><span class="sxs-lookup"><span data-stu-id="a674b-124">Choose a WebDriver language binding</span></span>  

<span data-ttu-id="a674b-125">ダウンロードする必要がある最後のコンポーネントは、コード \ (Python、Java、C \ #、ルビ、JavaScript \ #、ルビ、JavaScript \ #、ルビ、JavaScript \) をコマンドに変換するための言語固有のクライアントドライバーです。 microsoft edge ドライバーは Microsoft Edge \ (Chromium \) で実行されます。</span><span class="sxs-lookup"><span data-stu-id="a674b-125">The last component you must download is a language-specific client driver to translate your code \(Python, Java, C\#, Ruby, JavaScript\) into commands the Microsoft Edge Driver runs in Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="a674b-126">[選択した WebDriver 言語バインドをダウンロード][SeleniumDownloads]します。</span><span class="sxs-lookup"><span data-stu-id="a674b-126">[Download the WebDriver language binding of your choice][SeleniumDownloads].</span></span>  <span data-ttu-id="a674b-127">Microsoft edge チームは、Microsoft Edge \ (Chromium \) をサポートしているため、 [Selenium 4.00 alpha05][NugetPackagesSeleniumWebdriver400alpha05] 以降をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a674b-127">The Microsoft Edge team recommends [Selenium 4.00-alpha05][NugetPackagesSeleniumWebdriver400alpha05] or later, because it supports Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="a674b-128">ただし、現在の厩舎 Selenium 3 リリースを含む、Selenium のすべての旧バージョンで Microsoft Edge \ (Chromium \) を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="a674b-128">However, you may control Microsoft Edge \(Chromium\) in all older versions of Selenium, including the current stable Selenium 3 release.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="a674b-129">以前に Microsoft Edge \ (Chromium \) とクラスを使って自動化またはテストしている場合 `ChromeDriver` `ChromeOptions` 、webdriver コードは Microsoft Edge バージョン80以降では実行されません。</span><span class="sxs-lookup"><span data-stu-id="a674b-129">If you were previously automating or testing Microsoft Edge \(Chromium\) using `ChromeDriver` and `ChromeOptions` classes, your WebDriver code does not run on Microsoft Edge Version 80 or later.</span></span>  <span data-ttu-id="a674b-130">この問題を解決するには、クラスを使用するようにテストを更新 `EdgeOptions` し、 [Microsoft Edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriver]をインストールします。</span><span class="sxs-lookup"><span data-stu-id="a674b-130">To solve this problem, update your tests to use the `EdgeOptions` class and install [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver].</span></span>  

### <span data-ttu-id="a674b-131">Selenium 3 を使用する</span><span class="sxs-lookup"><span data-stu-id="a674b-131">Use Selenium 3</span></span>  

<span data-ttu-id="a674b-132">既に [Selenium 3][|::ref1::|]を使用している場合は、既存のブラウザーのテストが完了している可能性があります。また、Selenium のバージョンを変更せずに Microsoft Edge \ (Chromium \) のカバレッジを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="a674b-132">If you already use [Selenium 3][|::ref1::|], you may have existing browser tests and want to add coverage for Microsoft Edge \(Chromium\) without changing your version of Selenium.</span></span>  <span data-ttu-id="a674b-133">[Selenium 3][|::ref2::|]を使用して microsoft edge \ (EdgeHTML \) と microsoft edge \ (Chromium \) の自動テストを作成するには、更新されたドライバーを使用するために、 [microsoft Edge パッケージの Selenium Tools][GithubMicrosoftEdgeSeleniumTools]をインストールします。</span><span class="sxs-lookup"><span data-stu-id="a674b-133">To use [Selenium 3][|::ref2::|] to write automated tests for both Microsoft Edge \(EdgeHTML\) and Microsoft Edge \(Chromium\), install the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package to use the updated driver.</span></span>  <span data-ttu-id="a674b-134">`EdgeDriver` `EdgeDriverService` ツールに含まれているクラスとクラスは、Selenium 4 の組み込みの対応物と完全に互換性があります。</span><span class="sxs-lookup"><span data-stu-id="a674b-134">The `EdgeDriver` and `EdgeDriverService` classes included in the tools are fully compatible with the built-in equivalents in Selenium 4.</span></span>  

<span data-ttu-id="a674b-135">次の手順を使用して、Microsoft Edge と[Selenium 3][|::ref3::|] [用の Selenium Tools][GithubMicrosoftEdgeSeleniumTools]をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="a674b-135">Use the following steps to add the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] and [Selenium 3][|::ref3::|] to your project.</span></span>

#### [<span data-ttu-id="a674b-136">C#</span><span class="sxs-lookup"><span data-stu-id="a674b-136">C#</span></span>](#tab/c-sharp/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="a674b-137">[NUGET CLI][NugetCLI]または[Visual Studio][VisualStudio]を使用して、 [SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools]と[Selenium][NugetPackagesSeleniumWebdriver31410]の各パッケージを .net プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="a674b-137">Add the [Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools] and [Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410] packages to your .NET project using the [NuGet CLI][NugetCLI] or [Visual Studio][VisualStudio].</span></span>  

#### [<span data-ttu-id="a674b-138">Python</span><span class="sxs-lookup"><span data-stu-id="a674b-138">Python</span></span>](#tab/python/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="a674b-139">[Pip][PythonPip]を使用して[msedge-selenium ツール][PythonSeleniumTools]と[selenium][PythonSelenium]パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a674b-139">Use [pip][PythonPip] to install the [msedge-selenium-tools][PythonSeleniumTools] and [selenium][PythonSelenium] packages.</span></span>  

```python
pip install msedge-selenium-tools selenium==3.141
```  

#### [<span data-ttu-id="a674b-140">JavaScript</span><span class="sxs-lookup"><span data-stu-id="a674b-140">JavaScript</span></span>](#tab/javascript/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="a674b-141">[Npm][JavaScript|::ref4::|]を使用して、[エッジ selenium-ツール][JavaScriptSeleniumTools]と[selenium ドライバー][JavaScriptSelenium]パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a674b-141">Use [npm][JavaScript|::ref4::|] to install the [edge-selenium-tools][JavaScriptSeleniumTools] and [selenium-webdriver][JavaScriptSelenium] packages.</span></span>  

```javascript
npm install @microsoft/edge-selenium-tools selenium-webdriver
```  

* * *  

## <span data-ttu-id="a674b-142">WebDriver で Microsoft Edge (Chromium) を使用する</span><span class="sxs-lookup"><span data-stu-id="a674b-142">Use Microsoft Edge (Chromium) with WebDriver</span></span>

<span data-ttu-id="a674b-143">Selenium 3 または4のいずれかを使用して、次の例を実行できます。</span><span class="sxs-lookup"><span data-stu-id="a674b-143">You may run the following examples using either Selenium 3 or 4.</span></span>  <span data-ttu-id="a674b-144">Selenium 3 で使用するには、 [Microsoft Edge パッケージの Selenium ツール][GithubMicrosoftEdgeSeleniumTools] をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a674b-144">To use with Selenium 3, the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package must be installed.</span></span>  

### <span data-ttu-id="a674b-145">基本的な使用方法</span><span class="sxs-lookup"><span data-stu-id="a674b-145">Basic Usage</span></span>  

<span data-ttu-id="a674b-146">Microsoft Edge \ (EdgeHTML \) で使用するには、クラスの既定のインスタンスを作成 `EdgeDriver` します。</span><span class="sxs-lookup"><span data-stu-id="a674b-146">To use with Microsoft Edge \(EdgeHTML\), create a default instance of the `EdgeDriver` class.</span></span>  

#### [<span data-ttu-id="a674b-147">C#</span><span class="sxs-lookup"><span data-stu-id="a674b-147">C#</span></span>](#tab/c-sharp/)  

<a id="basic-usage-code"></a>  

```csharp
var driver = new EdgeDriver();
```  

#### [<span data-ttu-id="a674b-148">Python</span><span class="sxs-lookup"><span data-stu-id="a674b-148">Python</span></span>](#tab/python/)  

<a id="basic-usage-code"></a>  

```python
driver = Edge()
```  

#### [<span data-ttu-id="a674b-149">JavaScript</span><span class="sxs-lookup"><span data-stu-id="a674b-149">JavaScript</span></span>](#tab/javascript/)  

<a id="basic-usage-code"></a>  

```javascript
let driver = edge.Driver.createSession();
```  

* * *  

### <span data-ttu-id="a674b-150">Microsoft Edge の推進 (Chromium)</span><span class="sxs-lookup"><span data-stu-id="a674b-150">Driving Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="a674b-151">Microsoft Edge \ (Chromium \) で使用するには、新しい `EdgeDriver` クラスを作成し、 `EdgeOptions` プロパティが set に設定されたオブジェクトを渡し `UseChromium` `true` ます。</span><span class="sxs-lookup"><span data-stu-id="a674b-151">To use with Microsoft Edge \(Chromium\), create a new `EdgeDriver` class and pass it the `EdgeOptions` object with the `UseChromium` property set to `true`.</span></span>  

#### [<span data-ttu-id="a674b-152">C#</span><span class="sxs-lookup"><span data-stu-id="a674b-152">C#</span></span>](#tab/c-sharp/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### [<span data-ttu-id="a674b-153">Python</span><span class="sxs-lookup"><span data-stu-id="a674b-153">Python</span></span>](#tab/python/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options)
```  

#### [<span data-ttu-id="a674b-154">JavaScript</span><span class="sxs-lookup"><span data-stu-id="a674b-154">JavaScript</span></span>](#tab/javascript/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);

let driver = edge.Driver.createSession(options);
```  

* * *  

> [!NOTE]
> <span data-ttu-id="a674b-155">IT 管理者が[DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability]ポリシーを設定している場合 `2` 、ドライバーは[microsoft edge devtools][DevToolsMain]を使用しているため、Microsoft edge[ドライバー][MicrosoftDeveloperEdgeToolsWebdriver]は[microsoft edge (Chromium)][MicrosoftEdge]を実行できません。</span><span class="sxs-lookup"><span data-stu-id="a674b-155">If your IT admin has set the [DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability] policy to `2`, [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver] is not be able to drive [Microsoft Edge (Chromium)][MicrosoftEdge] because the driver uses the [Microsoft Edge DevTools][DevToolsMain].</span></span>  <span data-ttu-id="a674b-156">[DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability]ポリシーが `0` `1` [Microsoft Edge (Chromium)][MicrosoftEdge]に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a674b-156">Ensure the [DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability] policy is set to `0` or `1` to automate [Microsoft Edge (Chromium)][MicrosoftEdge].</span></span>  

### <span data-ttu-id="a674b-157">特定のブラウザーのバイナリを選択する (Chromium のみ)</span><span class="sxs-lookup"><span data-stu-id="a674b-157">Choosing Specific Browser Binaries (Chromium-Only)</span></span>  

<span data-ttu-id="a674b-158">このクラスは、 `EdgeOptions` Microsoft Edge \ (Chromium \) の特定のバイナリで使うことができます。</span><span class="sxs-lookup"><span data-stu-id="a674b-158">You may use the `EdgeOptions` class with specific binaries of Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="a674b-159">たとえば、microsoft Edge ベータ版などの [Microsoft edge preview チャネル][MicrosoftedgeinsiderDownload] を使用してテストを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a674b-159">For example, you may run tests using the [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.</span></span>  

#### [<span data-ttu-id="a674b-160">C#</span><span class="sxs-lookup"><span data-stu-id="a674b-160">C#</span></span>](#tab/c-sharp/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### [<span data-ttu-id="a674b-161">Python</span><span class="sxs-lookup"><span data-stu-id="a674b-161">Python</span></span>](#tab/python/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options)
```  

#### [<span data-ttu-id="a674b-162">JavaScript</span><span class="sxs-lookup"><span data-stu-id="a674b-162">JavaScript</span></span>](#tab/javascript/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.setBinaryPath("C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe");

let driver = edge.Driver.createSession(options);
```  

* * *  

### <span data-ttu-id="a674b-163">Microsoft Edge Driver サービスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="a674b-163">Customizing the Microsoft Edge Driver Service</span></span>  

#### [<span data-ttu-id="a674b-164">C#</span><span class="sxs-lookup"><span data-stu-id="a674b-164">C#</span></span>](#tab/c-sharp/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="a674b-165">クラス `EdgeDriver` インスタンスがクラスを使用して作成されると `EdgeOptions` 、 `EdgeDriverService` microsoft Edge \ (EdgeHTML \) または microsoft Edge \ (Chromium \) のいずれかに適切なクラスが作成されて起動します。</span><span class="sxs-lookup"><span data-stu-id="a674b-165">When an `EdgeDriver` class instance is created using `EdgeOptions` class, it creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="a674b-166">を作成する場合は `EdgeDriverService` 、メソッドを使用して Microsoft Edge \ (Chromium \) 用に構成されたものを作成し `CreateChromiumService()` ます。</span><span class="sxs-lookup"><span data-stu-id="a674b-166">If you want to create an `EdgeDriverService`, create one configured for Microsoft Edge \(Chromium\) using the `CreateChromiumService()` method.</span></span>  <span data-ttu-id="a674b-167">以下のコードでは、冗長ログ出力を有効にするなど、追加のカスタマイズに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="a674b-167">You may find it useful for additional customizations like enabling verbose log output in the following code.</span></span>  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE] 
><span data-ttu-id="a674b-168">`EdgeOptions`インスタンスに渡すときに、オブジェクトを指定する必要はありません `EdgeDriverService` `EdgeDriver` 。</span><span class="sxs-lookup"><span data-stu-id="a674b-168">You do not need to provide the `EdgeOptions` object when passing `EdgeDriverService` to the `EdgeDriver` instance.</span></span> <span data-ttu-id="a674b-169">この `EdgeDriver` クラスは、提供するサービスに応じて、Microsoft edge \ (EdgeHTML \) または Microsoft edge \ (Chromium) のいずれかの既定のオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="a674b-169">The `EdgeDriver` class uses the default options for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\) depending on the service you provide.</span></span>  
> <span data-ttu-id="a674b-170">ただし、両方のクラスを提供する場合は、 `EdgeDriverService` `EdgeOptions` 両方が同じバージョンの Microsoft Edge に対して構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a674b-170">However, if you want to provide both `EdgeDriverService` and `EdgeOptions` classes, ensure that both are configured for the same version of Microsoft Edge.</span></span>  <span data-ttu-id="a674b-171">たとえば、既定の Microsoft Edge \ (EdgeHTML \) `EdgeDriverService` クラスと Chromium プロパティをクラスで使うことはできません `EdgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="a674b-171">For example, it is not possible to use a default Microsoft Edge \(EdgeHTML\) `EdgeDriverService` class and Chromium properties in the `EdgeOptions` class.</span></span>  <span data-ttu-id="a674b-172">この `EdgeDriver` クラスは、異なるバージョンの使用を防ぐためにエラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="a674b-172">The `EdgeDriver` class throws an error to prevent using different versions.</span></span>  

#### [<span data-ttu-id="a674b-173">Python</span><span class="sxs-lookup"><span data-stu-id="a674b-173">Python</span></span>](#tab/python/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="a674b-174">Python を使っている場合、オブジェクトはを `Edge` 作成して管理し `EdgeService` ます。</span><span class="sxs-lookup"><span data-stu-id="a674b-174">When using Python, the `Edge` object creates and manages the `EdgeService`.</span></span>  <span data-ttu-id="a674b-175">を構成するには `EdgeService` 、 `Edge` 次のコードで示されているように、追加の引数をオブジェクトに渡します。</span><span class="sxs-lookup"><span data-stu-id="a674b-175">To configure the `EdgeService`, pass additional arguments to the `Edge` object as indicated in the following code.</span></span>  

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### [<span data-ttu-id="a674b-176">JavaScript</span><span class="sxs-lookup"><span data-stu-id="a674b-176">JavaScript</span></span>](#tab/javascript/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="a674b-177">JavaScript を使っている場合は、クラスでを作成して構成し `Service` `ServiceBuilder` ます。</span><span class="sxs-lookup"><span data-stu-id="a674b-177">When using JavaScript, create and configure a `Service` with the `ServiceBuilder` class.</span></span>  <span data-ttu-id="a674b-178">必要に応じて、オブジェクトをオブジェクトに渡すことができます。このオブジェクトは、 `Service` `Driver` サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="a674b-178">Optionally, you may pass the `Service` object to the `Driver` object, which starts \(and stops\) the service for you.</span></span>  
<span data-ttu-id="a674b-179">を構成するには `Service` 、 `ServiceBuilder` メソッドを使用する前に、クラスの追加のメソッドを実行し `build()` ます。</span><span class="sxs-lookup"><span data-stu-id="a674b-179">To configure the `Service`, run additional methods in the `ServiceBuilder` class before using the `build()` method.</span></span>  <span data-ttu-id="a674b-180">次に、 `service` メソッドのパラメーターとしてを渡し `Driver.createSession()` ます。</span><span class="sxs-lookup"><span data-stu-id="a674b-180">Then pass the `service` as a parameter in the `Driver.createSession()` method.</span></span>  

```javascript
let service = new edge.ServiceBuilder().enableVerboseLogging().build();
let driver = edge.Driver.createSession(options, service);
```  

* * *  

### <span data-ttu-id="a674b-181">Chromium-Specific のオプションを使用する</span><span class="sxs-lookup"><span data-stu-id="a674b-181">Use Chromium-Specific Options</span></span>  

<span data-ttu-id="a674b-182">プロパティをに設定した場合は `UseChromium` `true` 、 `EdgeOptions` 他の Chromium ブラウザーを自動化するときと同じ [Chromium 固有のプロパティやメソッド][SeleniumWebDriverChromeoptionsClass] にアクセスするために、クラスを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="a674b-182">If you set the `UseChromium` property to `true`, you may use the `EdgeOptions` class to access the same [Chromium-specific properties and methods][SeleniumWebDriverChromeoptionsClass] as when you automate other Chromium browsers.</span></span>  

#### [<span data-ttu-id="a674b-183">C#</span><span class="sxs-lookup"><span data-stu-id="a674b-183">C#</span></span>](#tab/c-sharp/)  

<a id="using-chromium-specific-options-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### [<span data-ttu-id="a674b-184">Python</span><span class="sxs-lookup"><span data-stu-id="a674b-184">Python</span></span>](#tab/python/)  

<a id="using-chromium-specific-options-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument("headless")
options.add_argument("disable-gpu")
```  

#### [<span data-ttu-id="a674b-185">JavaScript</span><span class="sxs-lookup"><span data-stu-id="a674b-185">JavaScript</span></span>](#tab/javascript/)  

<a id="using-chromium-specific-options-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.addArguments("headless");
options.addArguments("disable-gpu");
```

* * *  

> [!NOTE]
> <span data-ttu-id="a674b-186">`UseChromium`プロパティがに設定されている場合 `true` は、Microsoft Edge \ (EdgeHTML \) のプロパティとメソッドは使用できません。</span><span class="sxs-lookup"><span data-stu-id="a674b-186">If the `UseChromium` property is set to `true`, you are not able to use properties and methods for Microsoft Edge \(EdgeHTML\).</span></span>  

## <span data-ttu-id="a674b-187">その他の WebDriver のインストールオプション</span><span class="sxs-lookup"><span data-stu-id="a674b-187">Additional WebDriver installation options</span></span>  

### <span data-ttu-id="a674b-188">Chocolatey</span><span class="sxs-lookup"><span data-stu-id="a674b-188">Chocolatey</span></span>  

<span data-ttu-id="a674b-189">パッケージマネージャーとして [Chocolatey][Chocolatey] を使用している場合は、次のコマンドを実行して Microsoft Edge ドライバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a674b-189">If you use [Chocolatey][Chocolatey] as your package manager, install the Microsoft Edge Driver by running the following command.</span></span>  

```console
choco install selenium-chromium-edge-driver
```  

<span data-ttu-id="a674b-190">詳細については、「 [Chocolatey の Selenium Chromium Edge ドライバー][ChocolateyPackagesSeleniumChromiumEdgeDriver]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a674b-190">For more information, see [Selenium Chromium Edge Driver on Chocolatey][ChocolateyPackagesSeleniumChromiumEdgeDriver].</span></span>  

### <span data-ttu-id="a674b-191">Docker</span><span class="sxs-lookup"><span data-stu-id="a674b-191">Docker</span></span>  

<span data-ttu-id="a674b-192">[Docker][DockerHub]を使用している場合は、次のコマンドを実行して、microsoft edge \ (Chromium \) と[microsoft edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriver]がプレインストールされている事前構成済みイメージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a674b-192">If you use [Docker][DockerHub], download a pre-configured image with Microsoft Edge \(Chromium\) and [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver] pre-installed by running the following command.</span></span>  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

<span data-ttu-id="a674b-193">詳細については、「 [Docker Hub のコンテナー][DockerHubMsedgedriver]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a674b-193">For more information, see [container on Docker Hub][DockerHubMsedgedriver].</span></span>  

## <span data-ttu-id="a674b-194">Microsoft Edge DevTools チームと連絡を取る</span><span class="sxs-lookup"><span data-stu-id="a674b-194">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="a674b-195">Microsoft Edge チームは、WebDriver、Selenium、Microsoft Edge の使用に関するフィードバックをお寄せください。</span><span class="sxs-lookup"><span data-stu-id="a674b-195">The Microsoft Edge team is eager to hear your feedback about using WebDriver, Selenium, and Microsoft Edge.</span></span>  <span data-ttu-id="a674b-196">チームに自分の意見を知らせるには、Microsoft Edge DevTools で [ **フィードバックの送信** ] アイコンを選択するか、ツイート [@EdgeDevTools][TwitterTweetEdgeDevTools]を送信します。</span><span class="sxs-lookup"><span data-stu-id="a674b-196">To let the team know what you think, choose the **Send Feedback** icon in the Microsoft Edge DevTools or send a tweet [@EdgeDevTools][TwitterTweetEdgeDevTools].</span></span>  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools の [フィードバックの送信] アイコン" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="a674b-198">Microsoft Edge DevTools の [ **フィードバックの送信** ] アイコン</span><span class="sxs-lookup"><span data-stu-id="a674b-198">The **Send Feedback** icon in the Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!-- links -->  

[DevToolsMain]: ../devtools-guide-chromium.md "Microsoft Edge (Chromium) 開発者ツール |Microsoft ドキュメント"
[Webdriver]: ../webdriver.md "WebDriver (EdgeHTML) |Microsoft ドキュメント"  

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

[W3CWebdriver]: https://w3.org/TR/webdriver2 "WebDriver |勧告"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "ヘッドレスブラウザー |Wikipedia"  
