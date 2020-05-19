---
description: Microsoft Edge で web サイトまたはアプリをテストする方法、または WebDriver でブラウザーを自動化する方法について説明します。
title: WebDriver (Chromium)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/18/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 開発、html、css、javascript、開発者、webdriver、selenium、テスト、ツール、オートメーション、テスト
ms.openlocfilehash: 810c45e1e8d7fb5a6dbefee1c4ae6eccbe573326
ms.sourcegitcommit: f5dc9d3f1e6629120e036c4298f66de636688cb7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2020
ms.locfileid: "10659383"
---
# <span data-ttu-id="6d6be-104">WebDriver (Chromium)</span><span class="sxs-lookup"><span data-stu-id="6d6be-104">WebDriver (Chromium)</span></span>  

<span data-ttu-id="6d6be-105">W3C [Webdriver][W3CWebdriver] API は、プラットフォームと言語に依存しないインターフェイスとワイヤプロトコルであり、Microsoft Edge \ (Chromium \) などの web ブラウザーの動作をプログラムまたはスクリプトで制御できます。</span><span class="sxs-lookup"><span data-stu-id="6d6be-105">The W3C [WebDriver][W3CWebdriver] API is a platform and language-neutral interface and wire protocol allowing programs or scripts to control the behavior of a web browser, like Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="6d6be-106">WebDriver を使うと、開発者は、ユーザーの操作をシミュレートする自動テストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6d6be-106">WebDriver enables developers to create automated tests that simulate user interaction.</span></span>  <span data-ttu-id="6d6be-107">Webdriver のテストとシミュレーションは JavaScript 単体テストとは異なります。 WebDriver はブラウザーで実行されている JavaScript の機能と情報にアクセスできないため、Webdriver はユーザーイベントや OS レベルのイベントをより正確にシミュレートすることができます。</span><span class="sxs-lookup"><span data-stu-id="6d6be-107">WebDriver tests and simulations differ from JavaScript unit tests because WebDriver has access to functionality and information that JavaScript running in the browser does not, and WebDrive is able to more accurately simulate user events or OS-level events.</span></span>  <span data-ttu-id="6d6be-108">WebDriver は、1つのテストセッションで複数のウィンドウ、タブ、web ページにわたるテストを管理できます。</span><span class="sxs-lookup"><span data-stu-id="6d6be-108">WebDriver is able to manage testing across multiple windows, tabs and webpages in a single test session.</span></span>  

<span data-ttu-id="6d6be-109">ここでは、Microsoft Edge \ (Chromium) の WebDriver の使用を開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d6be-109">Here is how to get started with WebDriver for Microsoft Edge \(Chromium\).</span></span>  

## <span data-ttu-id="6d6be-110">Microsoft Edge をインストールする (Chromium)</span><span class="sxs-lookup"><span data-stu-id="6d6be-110">Install Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="6d6be-111">まだインストールしていない場合は、 [Microsoft Edge (Chromium) をインストール][MicrosoftEdge]してください。</span><span class="sxs-lookup"><span data-stu-id="6d6be-111">If you have not already, [install Microsoft Edge (Chromium)][MicrosoftEdge].</span></span>  <span data-ttu-id="6d6be-112">コンピューターにプレインストールされているバージョンの Microsoft Edge を使用している場合は、microsoft edge \ (Chromium \) と Microsoft Edge \ (EdgeHTML \) がインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6d6be-112">If you are using a pre-installed version of Microsoft Edge on your machine, verify that you have Microsoft Edge \(Chromium\) and not Microsoft Edge \(EdgeHTML\).</span></span>  <span data-ttu-id="6d6be-113">簡単に確認するには、 `edge://settings/help` ブラウザーに読み込み、バージョン番号が v75 以降であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6d6be-113">A quick way to check is to load `edge://settings/help` in the browser and confirm that the version number is v75 or later.</span></span>  

## <span data-ttu-id="6d6be-114">Microsoft Edge ドライバーをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="6d6be-114">Download Microsoft Edge Driver</span></span>  

<span data-ttu-id="6d6be-115">WebDriver では、ブラウザー固有のドライバーを各ブラウザーで自動化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d6be-115">WebDriver requires a browser-specific driver to automate each browser.</span></span>  <span data-ttu-id="6d6be-116">Microsoft Edge \ (Chromium \) については、WebDriver には、テストまたは自動化する Microsoft Edge のビルド用の適切な[Microsoft Edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriver]が必要です。</span><span class="sxs-lookup"><span data-stu-id="6d6be-116">For Microsoft Edge \(Chromium\), WebDriver requires the appropriate [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver] for the build of Microsoft Edge you want to test or automate.</span></span>  

<span data-ttu-id="6d6be-117">適切なビルド番号を確認するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="6d6be-117">To find your correct build number, use the following steps.</span></span>  

1.  <span data-ttu-id="6d6be-118">Microsoft Edge を起動する</span><span class="sxs-lookup"><span data-stu-id="6d6be-118">Launch Microsoft Edge</span></span> 
1.  <span data-ttu-id="6d6be-119">Microsoft Edge \ (Chromium \) バージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="6d6be-119">View the Microsoft Edge \(Chromium\) version.</span></span>  
    *   <span data-ttu-id="6d6be-120">次に移動します: </span><span class="sxs-lookup"><span data-stu-id="6d6be-120">Navigate to</span></span> `edge://settings/help`  
    *   <span data-ttu-id="6d6be-121">`...`  >  **Settings**  >   **Microsoft Edge に関する**設定を選択する</span><span class="sxs-lookup"><span data-stu-id="6d6be-121">Select `...` > **Settings** >  **About Microsoft Edge**</span></span>  
1.  <span data-ttu-id="6d6be-122">ビルドの適切なバージョンの WebDriver を確認して、適切に動作するようにします。</span><span class="sxs-lookup"><span data-stu-id="6d6be-122">Verify the correct version of WebDriver for your build ensures, so it runs correctly.</span></span>  

:::image type="complex" source="./media/webdriver-chromium/edge-version.png" alt-text="2020年1月14日の Microsoft Edge カナリアのビルド番号":::
   <span data-ttu-id="6d6be-124">図 1.</span><span class="sxs-lookup"><span data-stu-id="6d6be-124">Figure 1.</span></span>  <span data-ttu-id="6d6be-125">2020年1月14日の Microsoft Edge カナリアのビルド番号</span><span class="sxs-lookup"><span data-stu-id="6d6be-125">The build number for Microsoft Edge Canary on January 14, 2020</span></span>  
:::image-end:::  

<span data-ttu-id="6d6be-126">次に、[対応するバージョンの Microsoft Edge ドライバーをダウンロード][MicrosoftDeveloperEdgeToolsWebdriverDownloads]します。</span><span class="sxs-lookup"><span data-stu-id="6d6be-126">Now, [download the matching version of Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriverDownloads].</span></span>  

:::image type="complex" source="./media/webdriver-chromium/edge-driver-install.png" alt-text="Microsoft Edge ドライバーページのダウンロードセクション":::
   <span data-ttu-id="6d6be-128">図 2. </span><span class="sxs-lookup"><span data-stu-id="6d6be-128">Figure 2.</span></span>  <span data-ttu-id="6d6be-129">[Microsoft Edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriverDownloads]ページのダウンロードセクション</span><span class="sxs-lookup"><span data-stu-id="6d6be-129">The Downloads section of the [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriverDownloads] page</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="6d6be-130">Microsoft edge \ (EdgeHTML \) は[Microsoft Edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriverDownloads]では動作しません。</span><span class="sxs-lookup"><span data-stu-id="6d6be-130">Microsoft Edge \(EdgeHTML\) does not work with [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriverDownloads].</span></span>  <span data-ttu-id="6d6be-131">Microsoft Edge \ (EdgeHTML \) を自動化するには、microsoft [WebDriver For Microsoft edge \ (EdgeHTML \)][Webdriver]をダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d6be-131">To automate Microsoft Edge \(EdgeHTML\), you must download [Microsoft WebDriver for Microsoft Edge \(EdgeHTML\)][Webdriver].</span></span>  

## <span data-ttu-id="6d6be-132">WebDriver 言語バインドの選択</span><span class="sxs-lookup"><span data-stu-id="6d6be-132">Choose a WebDriver language binding</span></span>  

<span data-ttu-id="6d6be-133">ダウンロードする必要がある最後のコンポーネントは、言語固有のクライアントドライバーです。</span><span class="sxs-lookup"><span data-stu-id="6d6be-133">The last component you must download is a language-specific client driver.</span></span>  <span data-ttu-id="6d6be-134">言語バインディングは、Python、Java、C \ #、ルビ、JavaScript で記述したコードを、[前のセクションでダウンロード](#download-microsoft-edge-driver)した Microsoft edge ドライバーが microsoft edge \ (Chromium \) で実行できるように変換します。</span><span class="sxs-lookup"><span data-stu-id="6d6be-134">The language binding translates the code you write in Python, Java, C\#, Ruby, and JavaScript into commands that the Microsoft Edge Driver you [downloaded in the previous section](#download-microsoft-edge-driver) is able to run in Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="6d6be-135">[選択した WebDriver 言語バインドをダウンロード][SeleniumDownloads]します。</span><span class="sxs-lookup"><span data-stu-id="6d6be-135">[Download the WebDriver language binding of your choice][SeleniumDownloads].</span></span>  <span data-ttu-id="6d6be-136">Microsoft Edge チームでは、Microsoft Edge \ (Chromium \) の組み込みサポートが[4.00 Selenium][NugetPackagesSeleniumWebdriver400alpha05]れているため、alpha05 以降を強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6d6be-136">The Microsoft Edge team highly recommends [Selenium 4.00-alpha05][NugetPackagesSeleniumWebdriver400alpha05] or later, since it has built-in support for Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="6d6be-137">ただし、現在の厩舎 Selenium 3 リリースを含む、Selenium のすべての旧バージョンで Microsoft Edge \ (Chromium \) を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6d6be-137">However, you are able to drive Microsoft Edge \(Chromium\) in all older versions of Selenium, including the current stable Selenium 3 release.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="6d6be-138">を使用して Microsoft Edge \ (Chromium \) を以前に自動化またはテストしている場合 `ChromeDriver` `ChromeOptions` 、webdriver コードは Microsoft Edge v80 以降で正常に動作しません。</span><span class="sxs-lookup"><span data-stu-id="6d6be-138">If you were previously automating or testing Microsoft Edge \(Chromium\) by using `ChromeDriver` and `ChromeOptions`, your WebDriver code does not run successfully against Microsoft Edge v80 or later.</span></span>  <span data-ttu-id="6d6be-139">この変更は中断されています。 Microsoft Edge \ (Chromium \) では、このコマンドは受け入れられなくなりました。</span><span class="sxs-lookup"><span data-stu-id="6d6be-139">This is a breaking change and Microsoft Edge \(Chromium\) no longer accepts the commands.</span></span>  <span data-ttu-id="6d6be-140">`EdgeOptions`クラスと[Microsoft Edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriver]を使うようにテストを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d6be-140">You must change your tests to use the `EdgeOptions` class and [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver].</span></span>  

### <span data-ttu-id="6d6be-141">Selenium 3 の使用</span><span class="sxs-lookup"><span data-stu-id="6d6be-141">Using Selenium 3</span></span>  

<span data-ttu-id="6d6be-142">[Selenium 3][|::ref1::|]は最新の安定した Selenium リリースです。</span><span class="sxs-lookup"><span data-stu-id="6d6be-142">[Selenium 3][|::ref1::|] is the latest stable Selenium release.</span></span>  <span data-ttu-id="6d6be-143">既定では、Selenium 3 は古い Microsoft Edge \ (EdgeHTML \) を駆動しており、Microsoft Edge \ (Chromium \) の組み込みサポートはありません。</span><span class="sxs-lookup"><span data-stu-id="6d6be-143">By default, Selenium 3 drives the old Microsoft Edge \(EdgeHTML\), and does not have built-in support for Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="6d6be-144">Selenium 3 を Microsoft Edge \ (Chromium \) で使用するには、 [Microsoft edge パッケージ用の Selenium Tools][GithubMicrosoftEdgeSeleniumTools]をインストールします。</span><span class="sxs-lookup"><span data-stu-id="6d6be-144">To use Selenium 3 with Microsoft Edge \(Chromium\), install the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package.</span></span>  <span data-ttu-id="6d6be-145">Microsoft Edge 用 Selenium Tools は、更新されたドライバーを使用して Selenium 3 を拡張し、Microsoft Edge \ (EdgeHTML \) と新しい Microsoft Edge \ (Chromium \) のブラウザーの両方の自動テストを作成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6d6be-145">The Selenium Tools for Microsoft Edge extend Selenium 3 with an updated driver to help you write automated tests for both the Microsoft Edge \(EdgeHTML\) and new Microsoft Edge \(Chromium\) browsers.</span></span>  

<span data-ttu-id="6d6be-146">Microsoft Edge 用 Selenium Tools は、Selenium 3 と、既存のブラウザーテストを行っていて、Selenium バージョンを変更せずに新しい Microsoft Edge \ (Chromium \) ブラウザーを追加する必要がある開発者向けのソリューションです。</span><span class="sxs-lookup"><span data-stu-id="6d6be-146">Selenium Tools for Microsoft Edge is a solution for developers who prefer to remain on Selenium 3 and developers who have existing browser tests and want to add coverage for the new Microsoft Edge \(Chromium\) browser without changing Selenium versions.</span></span>  <span data-ttu-id="6d6be-147">`EdgeDriver` `EdgeDriverService` ツールに含まれているクラスとクラスは、Selenium の組み込みの同等の機能と完全に互換性があり、Microsoft Edge \ (EdgeHTML \) を既定で実行できます。このため、ツールは Selenium 内の既存の Edge クラスに対してシームレスなドロップイン置換として使うことができます。</span><span class="sxs-lookup"><span data-stu-id="6d6be-147">The `EdgeDriver` and `EdgeDriverService` classes included in the tools are fully compatible with the built-in equivalents in Selenium, and run Microsoft Edge \(EdgeHTML\) by default so the tools may be used as a seamless drop-in replacement for the existing Edge classes in Selenium.</span></span>  

<span data-ttu-id="6d6be-148">[Microsoft edge の Selenium ツールをインストール][GithubMicrosoftEdgeSeleniumTools]して、Selenium 3 プロジェクトで microsoft edge \ (Chromium) を使い始めることができます。</span><span class="sxs-lookup"><span data-stu-id="6d6be-148">[Install Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] to begin using Microsoft Edge \(Chromium\) with your Selenium 3 project.</span></span>  

## <span data-ttu-id="6d6be-149">WebDriver で Microsoft Edge (Chromium) を使用する</span><span class="sxs-lookup"><span data-stu-id="6d6be-149">Use Microsoft Edge (Chromium) with WebDriver</span></span>

<span data-ttu-id="6d6be-150">次の例は、Selenium 3 または4のいずれかを使って実行できます。</span><span class="sxs-lookup"><span data-stu-id="6d6be-150">The following examples are runnable using either Selenium 3 or 4.</span></span>  <span data-ttu-id="6d6be-151">Selenium 3 で使用するには、 [Microsoft Edge 用の Selenium Tools][GithubMicrosoftEdgeSeleniumTools]がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d6be-151">To use with Selenium 3, the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] must be installed.</span></span>  

### <span data-ttu-id="6d6be-152">基本的な使用方法</span><span class="sxs-lookup"><span data-stu-id="6d6be-152">Basic Usage</span></span>  

<span data-ttu-id="6d6be-153">Microsoft Edge \ (EdgeHTML \) で使用するには、クラスの既定のインスタンスを作成するだけです `EdgeDriver` 。</span><span class="sxs-lookup"><span data-stu-id="6d6be-153">To use with Microsoft Edge \(EdgeHTML\), simply create a default instance of the `EdgeDriver` class.</span></span>

#### [<span data-ttu-id="6d6be-154">C#</span><span class="sxs-lookup"><span data-stu-id="6d6be-154">C#</span></span>](#tab/c-sharp/)  

<a id="basic-usage-code" />  

```csharp
var driver = new EdgeDriver();
```  

#### [<span data-ttu-id="6d6be-155">Python</span><span class="sxs-lookup"><span data-stu-id="6d6be-155">Python</span></span>](#tab/python/)  

<a id="basic-usage-code" />  

```python
driver = Edge()
```  

* * *  

### <span data-ttu-id="6d6be-156">Microsoft Edge の推進 (Chromium)</span><span class="sxs-lookup"><span data-stu-id="6d6be-156">Driving Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="6d6be-157">代わりに Microsoft Edge \ (Chromium \) で使用するには、新しいクラスを作成し、プロパティがに設定された `EdgeDriver` `EdgeOptions` オブジェクトを渡し `UseChromium` `true` ます。</span><span class="sxs-lookup"><span data-stu-id="6d6be-157">To use with Microsoft Edge \(Chromium\) instead, create a new `EdgeDriver` class and pass it the `EdgeOptions` object with the `UseChromium` property set to `true`.</span></span>  

#### [<span data-ttu-id="6d6be-158">C#</span><span class="sxs-lookup"><span data-stu-id="6d6be-158">C#</span></span>](#tab/c-sharp/)  

<a id="diving-microsoft-edge-chromium-code" />  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### [<span data-ttu-id="6d6be-159">Python</span><span class="sxs-lookup"><span data-stu-id="6d6be-159">Python</span></span>](#tab/python/)  

<a id="diving-microsoft-edge-chromium-code" />  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options)
```  

* * *  

### <span data-ttu-id="6d6be-160">特定のブラウザーのバイナリを選択する (Chromium のみ)</span><span class="sxs-lookup"><span data-stu-id="6d6be-160">Choosing Specific Browser Binaries (Chromium-Only)</span></span>  

<span data-ttu-id="6d6be-161">特定の `EdgeOptions` バイナリを選択するには、クラスを使います。</span><span class="sxs-lookup"><span data-stu-id="6d6be-161">Use the `EdgeOptions` class to choose a specific binary.</span></span>  <span data-ttu-id="6d6be-162">Microsoft edge ベータ版などの[Microsoft edge preview チャネル][MicrosoftedgeinsiderDownload]をテストする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="6d6be-162">It is useful for testing [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.</span></span>  

#### [<span data-ttu-id="6d6be-163">C#</span><span class="sxs-lookup"><span data-stu-id="6d6be-163">C#</span></span>](#tab/c-sharp/)  

<a id="choosing-specific-browser-binaries-chrome-only-code" />  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### [<span data-ttu-id="6d6be-164">Python</span><span class="sxs-lookup"><span data-stu-id="6d6be-164">Python</span></span>](#tab/python/)  

<a id="choosing-specific-browser-binaries-chrome-only-code" />  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options)
```  

* * *  

### <span data-ttu-id="6d6be-165">Microsoft Edge Driver サービスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="6d6be-165">Customizing the Microsoft Edge Driver Service</span></span>  

#### [<span data-ttu-id="6d6be-166">C#</span><span class="sxs-lookup"><span data-stu-id="6d6be-166">C#</span></span>](#tab/c-sharp/)  

<a id="customizing-microsoft-edge-driver-services-code" />  

<span data-ttu-id="6d6be-167">クラスを `EdgeDriver` 使ってクラスのインスタンスを作成すると `EdgeOptions` 、 `EdgeDriverService` microsoft Edge \ (EdgeHTML \) または microsoft Edge \ (Chromium \) の適切なクラスが自動的に作成され、起動されます。</span><span class="sxs-lookup"><span data-stu-id="6d6be-167">When an `EdgeDriver` class instance is created using `EdgeOptions` class, it automatically creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="6d6be-168">を作成する場合は `EdgeDriverService` 、メソッドを使用して Microsoft Edge \ (Chromium \) 用に構成されたものを作成し `CreateChromiumService()` ます。</span><span class="sxs-lookup"><span data-stu-id="6d6be-168">If you want to create an `EdgeDriverService`, create one configured for Microsoft Edge \(Chromium\) using the `CreateChromiumService()` method.</span></span>  <span data-ttu-id="6d6be-169">以下のコードでは、冗長ログ出力を有効にするなど、追加のカスタマイズに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="6d6be-169">You may find it useful for additional customizations like enabling verbose log output in the following code.</span></span>  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE]
> <span data-ttu-id="6d6be-170">クラスのインスタンスを渡すときに、オブジェクトを指定する必要はありません `EdgeOptions` `EdgeDriver` `EdgeDriverService` 。</span><span class="sxs-lookup"><span data-stu-id="6d6be-170">You do not need to provide the `EdgeOptions` object when passing the `EdgeDriver` class instance the `EdgeDriverService`.</span></span>  <span data-ttu-id="6d6be-171">この `EdgeDriver` クラスは、提供するサービスの種類に応じて、Microsoft edge \ (EdgeHTML \) または Microsoft edge \ (Chromium) のいずれかの既定のオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="6d6be-171">The `EdgeDriver` class uses the default options for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\) depending on what kind of service you provide.</span></span>  
> 
> <span data-ttu-id="6d6be-172">ただし、クラスとクラスの両方を提供する場合は、 `EdgeDriverService` `EdgeOptions` 両方が同じバージョンの Microsoft Edge で構成されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d6be-172">However, if you want to provide both an `EdgeDriverService` and `EdgeOptions` classes, you must ensure that both are configured for the same version of Microsoft Edge.</span></span>  <span data-ttu-id="6d6be-173">たとえば、既定の Microsoft Edge \ (EdgeHTML \) `EdgeDriverService` クラスと Chromium プロパティをクラスで使うことはできません `EdgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="6d6be-173">For example, it is not possible to use a default Microsoft Edge \(EdgeHTML\) `EdgeDriverService` class and Chromium properties in the `EdgeOptions` class.</span></span>  <span data-ttu-id="6d6be-174">この `EdgeDriver` クラスは、異なるバージョンの使用を防ぐためにエラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="6d6be-174">The `EdgeDriver` class throws an error to prevent using different versions.</span></span>  

#### [<span data-ttu-id="6d6be-175">Python</span><span class="sxs-lookup"><span data-stu-id="6d6be-175">Python</span></span>](#tab/python/)  

<a id="customizing-microsoft-edge-driver-services-code" />  

<span data-ttu-id="6d6be-176">Python を使っている場合、オブジェクトはを `Edge` 作成して管理し `EdgeService` ます。</span><span class="sxs-lookup"><span data-stu-id="6d6be-176">When using Python, the `Edge` object creates and manages the `EdgeService`.</span></span>  <span data-ttu-id="6d6be-177">を構成するには `EdgeService` 、オブジェクトに追加の引数を渡し `Edge` ます。</span><span class="sxs-lookup"><span data-stu-id="6d6be-177">To configure the `EdgeService`, pass additional arguments to the `Edge` object:</span></span>

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

* * *  

### <span data-ttu-id="6d6be-178">Chromium 固有のオプションを使用する</span><span class="sxs-lookup"><span data-stu-id="6d6be-178">Using Chromium-Specific Options</span></span>  

<span data-ttu-id="6d6be-179">プロパティとして設定されたクラスを使用 `EdgeOptions` `UseChromium` すると `true` 、Selenium の[ChromeOptions][SeleniumWebDriverChromeoptionsClass]クラスで利用できるものと同じすべてのメソッドとプロパティにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="6d6be-179">Using the `EdgeOptions` class with the `UseChromium` property set to `true` gives you access to all of the same methods and properties that are available in the [ChromeOptions][SeleniumWebDriverChromeoptionsClass] class in Selenium.</span></span>  <span data-ttu-id="6d6be-180">たとえば、他の Chromium ブラウザーの場合と同様に、メソッドを使用して、 `EdgeOptions.AddArguments()` 次のコードの[ヘッドレスモード][WikiHeadlessBrowser]で Microsoft Edge \ (Chromium) を実行します。</span><span class="sxs-lookup"><span data-stu-id="6d6be-180">For example, just like with other Chromium browsers, use the `EdgeOptions.AddArguments()` method to run Microsoft Edge \(Chromium\) in [headless mode][WikiHeadlessBrowser] in the following code.</span></span>  

#### [<span data-ttu-id="6d6be-181">C#</span><span class="sxs-lookup"><span data-stu-id="6d6be-181">C#</span></span>](#tab/c-sharp/)  

<a id="using-chromium-specific-options-code" />  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### [<span data-ttu-id="6d6be-182">Python</span><span class="sxs-lookup"><span data-stu-id="6d6be-182">Python</span></span>](#tab/python/)  

<a id="using-chromium-specific-options-code" />  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument('headless')
options.add_argument('disable-gpu')
```  

* * *  

> [!NOTE]
> <span data-ttu-id="6d6be-183">[Chromium 固有のプロパティとメソッド][SeleniumWebDriverChromeoptionsClass]は常に使用できますが、 `UseChromium` プロパティがに設定されていない場合は効果がありません `true` 。</span><span class="sxs-lookup"><span data-stu-id="6d6be-183">The [Chromium-specific properties and methods][SeleniumWebDriverChromeoptionsClass] are always available but have no effect if the `UseChromium` property is not set to `true`.</span></span>  <span data-ttu-id="6d6be-184">同様に、 `UseChromium` プロパティがに設定されている場合は、Microsoft Edge \ (EdgeHTML \) 用の既存のプロパティとメソッドは効果がありません `true` 。</span><span class="sxs-lookup"><span data-stu-id="6d6be-184">Similarly, existing properties and methods meant for Microsoft Edge \(EdgeHTML\) have no effect if `UseChromium` property is set to `true`.</span></span>  

## <span data-ttu-id="6d6be-185">Web ドライバーを設定するその他の方法</span><span class="sxs-lookup"><span data-stu-id="6d6be-185">Other ways to set up WebDriver</span></span>  

### <span data-ttu-id="6d6be-186">Chocolatey</span><span class="sxs-lookup"><span data-stu-id="6d6be-186">Chocolatey</span></span>  

<span data-ttu-id="6d6be-187">パッケージマネージャーとして[Chocolatey][Chocolatey]を使用している場合は、次のコマンドを実行して Microsoft Edge ドライバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6d6be-187">If you are using [Chocolatey][Chocolatey] as your package manager, install the Microsoft Edge Driver by running the following command.</span></span>  

```console
choco install selenium-chromium-edge-driver
```  

<span data-ttu-id="6d6be-188">詳細については、「 [Chocolatey の Selenium Chromium Edge ドライバー][ChocolateyPackagesSeleniumChromiumEdgeDriver]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d6be-188">For more information, see [Selenium Chromium Edge Driver on Chocolatey][ChocolateyPackagesSeleniumChromiumEdgeDriver].</span></span>  

### <span data-ttu-id="6d6be-189">Docker</span><span class="sxs-lookup"><span data-stu-id="6d6be-189">Docker</span></span>  

<span data-ttu-id="6d6be-190">[Docker][DockerHub]を使用している場合は、次のコマンドを実行して、microsoft edge \ (Chromium \) および[microsoft edge ドライバー][MicrosoftDeveloperEdgeToolsWebdriver]で事前に構成された画像をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="6d6be-190">If you are using [Docker][DockerHub], download a pre-configured image with Microsoft Edge \(Chromium\) and [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver] already installed by running the following command.</span></span>  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

<span data-ttu-id="6d6be-191">詳細については、「 [Docker Hub のコンテナー][DockerHubMsedgedriver]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d6be-191">For more information, see [container on Docker Hub][DockerHubMsedgedriver].</span></span>  

## <span data-ttu-id="6d6be-192">Microsoft Edge DevTools チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="6d6be-192">Getting in touch with the Microsoft Edge DevTools team</span></span>    

<span data-ttu-id="6d6be-193">Microsoft Edge チームは、WebDriver、Selenium、Microsoft Edge の使用に関するフィードバックをお寄せください。</span><span class="sxs-lookup"><span data-stu-id="6d6be-193">The Microsoft Edge team is eager to hear your feedback about using WebDriver, Selenium, and Microsoft Edge!</span></span>  <span data-ttu-id="6d6be-194">Microsoft Edge DevTools またはツイート[@EdgeDevTools][TwitterTweetEdgeDevTools]の**フィードバック**アイコンを使用して、チームに自分の意見を伝えます。</span><span class="sxs-lookup"><span data-stu-id="6d6be-194">Use the **Feedback** icon in the Microsoft Edge DevTools or tweet [@EdgeDevTools][TwitterTweetEdgeDevTools] to let the team know what you think.</span></span>  


:::image type="complex" source="./devtools-guide-chromium/media/devtools-feedback.png" alt-text="Microsoft Edge DevTools のフィードバックアイコン":::
   <span data-ttu-id="6d6be-196">Microsoft Edge DevTools の**フィードバック**アイコン</span><span class="sxs-lookup"><span data-stu-id="6d6be-196">The **Feedback** icon in the Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!-- image links -->  

<!-- links -->  

[Webdriver]: ./webdriver.md "WebDriver (EdgeHTML) |Microsoft ドキュメント"  

[Chocolatey]: https://chocolatey.org "Chocolatey |Chocolatey ソフトウェア"  
[ChocolateyPackagesSeleniumChromiumEdgeDriver]: https://chocolatey.org/packages/selenium-chromium-edge-driver "Selenium Chromium Edge Driver |Chocolatey"  

[DockerHub]: https://hub.docker.com "Docker Hub"  
[DockerHubMsedgedriver]: https://hub.docker.com/_/microsoft-msedge-msedgedriver?tab=description "msedgedriver |Docker hub"  

[GithubMicrosoftEdgeSeleniumTools]: https://github.com/microsoft/edge-selenium-tools "microsoft/edge-selenium-ツール |GitHub"  
[GithubSeleniumHq]: https://github.com/SeleniumHQ/selenium "SeleniumHQ/selenium |GitHub"  

[MicrosoftDeveloperEdgeToolsWebdriver]: https://developer.microsoft.com/microsoft-edge/tools/webdriver "WebDriver |Microsoft 開発者"
[MicrosoftDeveloperEdgeToolsWebdriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver/#downloads "ダウンロード-WebDriver |Microsoft 開発者"  

[MicrosoftEdge]: https://www.microsoft.com/edge "新しい Microsoft Edge ブラウザーをダウンロードする"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  

[NugetPackagesMicrosoftEdgeSeleniumtools]: https://www.nuget.org/packages/Microsoft.Edge.SeleniumTools "SeleniumTools |NuGet ギャラリー"  
[NugetPackagesSeleniumWebdriver31410]: https://www.nuget.org/packages/Selenium.WebDriver/3.141.0 "Selenium ドライバー 3.141.0 |NuGet ギャラリー"  
[NugetPackagesSeleniumWebdriver400alpha05]: https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-alpha05 "Selenium ドライバー 4.0.0-alpha05 |NuGet ギャラリー"  

[SeleniumHQ]: https://www.selenium.dev "SeleniumHQ"  
[SeleniumDownloads]: https://selenium.dev/downloads "ダウンロード |Selenium"  
[SeleniumWebDriverChromeoptionsClass]: https://www.selenium.dev/selenium/docs/api/dotnet/?topic=html/T_OpenQA_Selenium_Chrome_ChromeOptions.htm "ChromeOptions Class-WebDriver |Selenium"  

[TwitterTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |ツイートを投稿する"  

[W3CWebdriver]: https://w3.org/TR/webdriver2 "WebDriver"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "ヘッドレスブラウザー |Wikipedia"  
