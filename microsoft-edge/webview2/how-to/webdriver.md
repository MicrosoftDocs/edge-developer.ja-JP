---
description: Microsoft Edge Driver を使用して WebView2 コントロールを自動化してテストする
title: Microsoft Edge ドライバーを使用した WebView2 の自動化とテスト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、Webview2、Webview、edge、ICoreWebView2、ICoreWebView2Controller、Selenium、Microsoft Edge Driver
ms.openlocfilehash: 37c0e41e11693c8a21b7240bf9370fd658834cff
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "11536029"
---
# <a name="automate-and-test-webview2-with-microsoft-edge-driver"></a><span data-ttu-id="81f4c-104">Microsoft Edge Driver を使用して WebView2 を自動化してテストする</span><span class="sxs-lookup"><span data-stu-id="81f4c-104">Automate and test WebView2 with Microsoft Edge Driver</span></span>  

<span data-ttu-id="81f4c-105">WebView2 は Microsoft Edge \(Chromium\) Web プラットフォームを使用しますので、WebView2 開発者 \(you\) は、デバッグと自動化のための標準的な Web ツールを利用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="81f4c-105">Because WebView2 uses the Microsoft Edge \(Chromium\) web platform, WebView2 developers \(you\) may take advantage of standard web tooling for debugging and automation.</span></span>  <span data-ttu-id="81f4c-106">Selenium はそのようなツールの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="81f4c-106">Selenium is one such tool.</span></span>  <span data-ttu-id="81f4c-107">W3C [WebDriver][W3cWebdriver2] API を実装します。</span><span class="sxs-lookup"><span data-stu-id="81f4c-107">It implements the W3C [WebDriver][W3cWebdriver2] API.</span></span>  <span data-ttu-id="81f4c-108">Selenium を使用して、ユーザーの操作をシミュレートする自動テストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="81f4c-108">You may use Selenium to create automated tests to simulate user interactions.</span></span>  

<span data-ttu-id="81f4c-109">次の手順を開始します。</span><span class="sxs-lookup"><span data-stu-id="81f4c-109">Get started with the following steps.</span></span>  

## <a name="step-1--download-webview2api-sample"></a><span data-ttu-id="81f4c-110">手順 1: WebView2API サンプルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="81f4c-110">Step 1:  Download WebView2API Sample</span></span>  

<span data-ttu-id="81f4c-111">既存の WebView2 プロジェクトをお持ちではない場合は、 [最新の WebView2][GithubMicrosoftedgewebview2samplesSampleappsWebview2apisample]SDK の包括的なサンプルである WebView2API サンプル アプリをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="81f4c-111">If you do not have an existing WebView2 project, download the [WebView2API Sample app][GithubMicrosoftedgewebview2samplesSampleappsWebview2apisample], a comprehensive sample of the latest WebView2 SDK.</span></span>  <span data-ttu-id="81f4c-112">[WebView2API サンプル アプリの前提条件を満たしていることを確認します][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisamplePrerequisites]。</span><span class="sxs-lookup"><span data-stu-id="81f4c-112">Ensure you have satisfied the [prerequisites for the WebView2API Sample app][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisamplePrerequisites].</span></span>  

<span data-ttu-id="81f4c-113">リポジトリを複製したら、プロジェクトをビルドして、Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="81f4c-113">Once you have cloned the repo, build the project in Visual Studio.</span></span>  <span data-ttu-id="81f4c-114">次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="81f4c-114">It should look like the following figure.</span></span>  

:::image type="complex" source="../media/webdriver/sample-app.png" alt-text="WebView2API サンプル アプリ" lightbox="../media/webdriver/sample-app.png":::
   <span data-ttu-id="81f4c-116">WebView2API サンプル アプリ</span><span class="sxs-lookup"><span data-stu-id="81f4c-116">WebView2API Sample app</span></span>  
:::image-end:::    

## <a name="step-2--install-microsoft-edge-driver"></a><span data-ttu-id="81f4c-117">手順 2: Microsoft Edge Driver をインストールする</span><span class="sxs-lookup"><span data-stu-id="81f4c-117">Step 2:  Install Microsoft Edge Driver</span></span>  

<span data-ttu-id="81f4c-118">手順に従って Microsoft Edge Driver をインストールし [、WebView2][WebdriverChromiumDownloadMicrosoftEdgeDriver] を自動化およびテストするために Selenium で必要なブラウザー固有のドライバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="81f4c-118">Follow the instructions to install [Microsoft Edge Driver][WebdriverChromiumDownloadMicrosoftEdgeDriver] the browser-specific driver required by Selenium to automate and test WebView2.</span></span>  

<span data-ttu-id="81f4c-119">Microsoft Edge Driver のバージョンが、アプリで使用する WebView2 ランタイムのバージョンと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81f4c-119">Ensure that the version of Microsoft Edge Driver matches the version of WebView2 Runtime that you app uses.</span></span>  <span data-ttu-id="81f4c-120">WebView2API サンプルが動作するには、WebView2 ランタイムのバージョンが、サポートされている最新の WebView2 SDK リリースのバージョン以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="81f4c-120">For the WebView2API Sample to work, make sure that your version of WebView2 Runtime is greater than or equal than the supported version of the latest WebView2 SDK release.</span></span>  <span data-ttu-id="81f4c-121">最新の WebView2 SDK リリースを見つけるには [、WebView2 リリース ノートに移動します][Webview2ReleaseNotes]。</span><span class="sxs-lookup"><span data-stu-id="81f4c-121">To locate the latest WebView2 SDK release, navigate to [WebView2 release notes][Webview2ReleaseNotes].</span></span>  <span data-ttu-id="81f4c-122">現在使用している WebView2 ランタイムのバージョンを確認するには、に移動します `edge://settings/help` 。</span><span class="sxs-lookup"><span data-stu-id="81f4c-122">To find out what version of WebView2 Runtime you currently have, navigate to `edge://settings/help`.</span></span>  

## <a name="step-3--add-selenium-to-the-webview2api-sample"></a><span data-ttu-id="81f4c-123">手順 3: WebView2API サンプルに Selenium を追加する</span><span class="sxs-lookup"><span data-stu-id="81f4c-123">Step 3:  Add Selenium to the WebView2API Sample</span></span>  

<span data-ttu-id="81f4c-124">この時点で、WebView2 ランタイムをインストールし、WebView2 プロジェクトをビルドし、Microsoft Edge Driver をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="81f4c-124">At this point you should have WebView2 Runtime installed, built a WebView2 project, and installed Microsoft Edge Driver.</span></span>  <span data-ttu-id="81f4c-125">次に、Selenium の使用を開始します。</span><span class="sxs-lookup"><span data-stu-id="81f4c-125">Now, get started using Selenium.</span></span>  

> [!NOTE]
> <span data-ttu-id="81f4c-126">Selenium は C\#、Java、Python、Javascript、および Ruby をサポートします。</span><span class="sxs-lookup"><span data-stu-id="81f4c-126">Selenium supports C\#, Java, Python, Javascript, and Ruby.</span></span>  <span data-ttu-id="81f4c-127">ただし、次のガイドは C\#を使用して記述されています。</span><span class="sxs-lookup"><span data-stu-id="81f4c-127">However, the following guide is written using C\#.</span></span>  

1.  <span data-ttu-id="81f4c-128">まず、新しいプロジェクト**をC# .NET Framework\*\*\*\*を作成**Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="81f4c-128">Start by creating a new **C# .NET Framework** project in **Visual Studio**.</span></span>  <span data-ttu-id="81f4c-129">次に **進** むには、右下隅の [次へ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="81f4c-129">Choose **Next** on the bottom right-hand corner to continue.</span></span>  
    
    :::image type="complex" source="../media/webdriver/new-project.png" alt-text="新しいプロジェクトの作成" lightbox="../media/webdriver/new-project.png":::
       <span data-ttu-id="81f4c-131">新しいプロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="81f4c-131">Create a new project</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="81f4c-132">プロジェクトに名前を付 **け**、好みの場所に **保存し**、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="81f4c-132">Give your project a **name**, save it to your preferred **location**, and choose **Create**.</span></span>  
    
    :::image type="complex" source="../media/webdriver/app-create.png" alt-text="新しいプロジェクトを構成する" lightbox="../media/webdriver/app-create.png":::
       <span data-ttu-id="81f4c-134">新しいプロジェクトを構成する</span><span class="sxs-lookup"><span data-stu-id="81f4c-134">Configure your new project</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="81f4c-135">新しいプロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="81f4c-135">A new project is created.</span></span>  <span data-ttu-id="81f4c-136">このガイドでは、すべてのコードがファイルに書き込 `Program.cs` まれます。</span><span class="sxs-lookup"><span data-stu-id="81f4c-136">In this guide, all code is written to the `Program.cs` file.</span></span>  
    
    :::image type="complex" source="../media/webdriver/start-app.png" alt-text="新しいプロジェクト" lightbox="../media/webdriver/start-app.png":::
       <span data-ttu-id="81f4c-138">新しいプロジェクト</span><span class="sxs-lookup"><span data-stu-id="81f4c-138">New project</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="81f4c-139">次に **、Selenium を** プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="81f4c-139">Now add **Selenium** to the project.</span></span>  <span data-ttu-id="81f4c-140">**Selenium.WebDriver NuGet パッケージを使用して Selenium をインストールします**。</span><span class="sxs-lookup"><span data-stu-id="81f4c-140">Install Selenium using the **Selenium.WebDriver NuGet package**.</span></span>  
    
    <span data-ttu-id="81f4c-141">**Selenium.WebDriver NuGet**パッケージをダウンロードするには\*\*\*\*、Visual Studio で Project\*\*\*\* をポイントし、[NuGet パッケージの管理]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="81f4c-141">To download the **Selenium.WebDriver NuGet package**, in **Visual Studio**, hover on **Project**, and choose **Manage NuGet Package**.</span></span>  <span data-ttu-id="81f4c-142">次の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="81f4c-142">The following screen should appear.</span></span>  
    
    :::image type="complex" source="../media/webdriver/download-nuget.png" alt-text="NuGet パッケージのダウンロード" lightbox="../media/webdriver/download-nuget.png":::
       <span data-ttu-id="81f4c-144">NuGet パッケージのダウンロード</span><span class="sxs-lookup"><span data-stu-id="81f4c-144">Download NuGet package</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="81f4c-145">検索 `Selenium.WebDriver` バーに入力し、結果から **[Selenium.WebDriver]** を選択し、[プレリリースを含める] の横にあるチェック ボックスをオン **にします**。</span><span class="sxs-lookup"><span data-stu-id="81f4c-145">Type `Selenium.WebDriver` in the search bar, choose **Selenium.WebDriver** from the results, and make sure to checkmark the box next to **include pre-release**.</span></span>  <span data-ttu-id="81f4c-146">右側のウィンドウで、バージョンが**4.0.0-alpha04**以降のインストールに設定されているのを確認し、[インストール] を選択**します**。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="81f4c-146">On the right-hand side window, ensure the **Version** is set to **install 4.0.0-alpha04** or later and choose **Install**.</span></span>  <span data-ttu-id="81f4c-147">NuGet は、Selenium をコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="81f4c-147">NuGet downloads Selenium to your machine.</span></span>  
    
    <span data-ttu-id="81f4c-148">Selenium.WebDriver NuGet パッケージの詳細については [、「Selenium.WebDriver 4.0.0-alpha04」に移動します][NugetSeleniumWebdriver400Alpha04]。</span><span class="sxs-lookup"><span data-stu-id="81f4c-148">To learn more about the Selenium.WebDriver NuGet package, navigate to [Selenium.WebDriver 4.0.0-alpha04][NugetSeleniumWebdriver400Alpha04].</span></span>  
    
    :::image type="complex" source="../media/webdriver/nuget.png" alt-text="NuGet パッケージの管理" lightbox="../media/webdriver/nuget.png":::
       <span data-ttu-id="81f4c-150">NuGet パッケージの管理</span><span class="sxs-lookup"><span data-stu-id="81f4c-150">Manage NuGet package</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="81f4c-151">ファイル `OpenQA.Selenium.Edge` の先頭に次のステートメント  `using OpenQA.Selenium.Edge;` を追加して使用 `Program.cs` します。</span><span class="sxs-lookup"><span data-stu-id="81f4c-151">Use `OpenQA.Selenium.Edge` by adding the following statement:  `using OpenQA.Selenium.Edge;` at the beginning of `Program.cs` file.</span></span>  
    
    ```csharp
    using OpenQA.Selenium.Edge;
    
    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    ```  
    
## <a name="step-4-drive-webview2-with-selenium-and-microsoft-edge-driver"></a><span data-ttu-id="81f4c-152">手順 4: Selenium と Microsoft Edge ドライバーを使用して WebView2 を駆動する</span><span class="sxs-lookup"><span data-stu-id="81f4c-152">Step 4: Drive WebView2 with Selenium and Microsoft Edge Driver</span></span>  

1.  <span data-ttu-id="81f4c-153">まず、次の `EdgeOptions` コード スニペットをコピーして、オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="81f4c-153">First, create the `EdgeOptions` object, by copying the following code snippet.</span></span>  
    
    ```csharp
    static void Main(string[] args)
    {
        // EdgeOptions() requires using OpenQA.Selenium.Edge
        // Construct EdgeOptions with is_legacy = false and the string "webview2"
        EdgeOptions edgeOptions = new EdgeOptions(false, "webview2");
    ```  
    
    <span data-ttu-id="81f4c-154">オブジェクト `EdgeOptions` は、次の 2 つのパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="81f4c-154">The `EdgeOptions` object takes in the following two parameters.</span></span>  
    
    | <span data-ttu-id="81f4c-155">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81f4c-155">Parameter</span></span> | <span data-ttu-id="81f4c-156">詳細</span><span class="sxs-lookup"><span data-stu-id="81f4c-156">Details</span></span> |    
    |:--- |:--- |  
    | `is_legacy` | <span data-ttu-id="81f4c-157">に設定 `false` します。これは、新しいクロムベースの Microsoft Edge ブラウザーを駆動している Selenium に指示します。</span><span class="sxs-lookup"><span data-stu-id="81f4c-157">Set to `false`, which tells Selenium that you are driving the new Chromium-based Microsoft Edge browser.</span></span> |  
    | `"webview2"` | <span data-ttu-id="81f4c-158">WebView2 を駆動している Selenium を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="81f4c-158">A string that tells Selenium you are driving WebView2.</span></span> |  
    
1.  <span data-ttu-id="81f4c-159">次に、WebView2 プロジェクト ランタイムのファイル パスに設定し、Microsoft Edge Driver をインストールした場所へのファイル パスを指定する名前の文字列を作成し `edgeOptions.BinaryLocation` `msedgedriverDir` [、Microsoft][MicrosoftDeveloperMicrosoftEdgeWebDriverDownloads] `msedgedriverExe` Edge Driver ランタイムの名前を格納する名前の文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="81f4c-159">Next, set `edgeOptions.BinaryLocation` to the file path of your WebView2 project runtime, create a string named `msedgedriverDir` that provides the file path to where you installed [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeWebDriverDownloads], and create a string named `msedgedriverExe` to store the name of the Microsoft Edge Driver runtime.</span></span>  <span data-ttu-id="81f4c-160">既定では、ランタイムの名前は `msedgedriver.exe` .</span><span class="sxs-lookup"><span data-stu-id="81f4c-160">By default, the runtime is named `msedgedriver.exe`.</span></span> <span data-ttu-id="81f4c-161">次に示すように、これらの 2 つの文字列 `EdgeDriverService` を使用してオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="81f4c-161">Use these two strings to construct the `EdgeDriverService` object as shown below.</span></span>  <span data-ttu-id="81f4c-162">最後に、 を使用して `EdgeDriver` オブジェクトを `EdgeDriverService` 作成します `EdgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="81f4c-162">Finally, create the `EdgeDriver` object using `EdgeDriverService` and `EdgeOptions`.</span></span>  
    
    <span data-ttu-id="81f4c-163">下に次のコードをコピーして貼り付けます `edgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="81f4c-163">You may copy and paste the following code underneath `edgeOptions`.</span></span>  <span data-ttu-id="81f4c-164">プロジェクト ランタイムへの正しいファイル パスと、コンピューター上の Microsoft Edge Driver ランタイムを指定してください。</span><span class="sxs-lookup"><span data-stu-id="81f4c-164">Ensure you specify the correct file paths to your project runtime and the Microsoft Edge Driver runtime on your machine.</span></span>  
    
    ```csharp
    //Set the BinaryLocation to the filepath of the WebView2API Sample runtime
    edgeOptions.BinaryLocation = @"C:\path\to\your\webview2\project.exe";
    
    //Set msedgedriverDir to the filepath of the directory housing msedgedriver.exe
    string msedgedriverDir = @"C:\path\to\your\msededriver.exe's\directory";
    
    //Set msedgedriverExe to the name of the Edge Driver. By default it is:
    string msedgedriverExe = @"msedgedriver.exe";
    
    // Construct EdgeDriverService with is_legacy = false  
    EdgeDriverService service = EdgeDriverService.CreateDefaultService(msedgedriverDir, msedgedriverExe, false);
    
    EdgeDriver e = new EdgeDriver(service, edgeOptions);
    ```  
    
3.  <span data-ttu-id="81f4c-165">これで、 `EdgeDriver` プロジェクトで WebView2 を駆動するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="81f4c-165">Now, `EdgeDriver` is configured to drive the WebView2 in your project.</span></span>  <span data-ttu-id="81f4c-166">たとえば **、WebView2API**サンプルを使用している場合は、コマンドを実行 `https://microsoft.com` して移動 `e.Url = @"https://www.microsoft.com";` できます。</span><span class="sxs-lookup"><span data-stu-id="81f4c-166">For example, if you are using the **WebView2API Sample**, you may navigate to `https://microsoft.com` by running the `e.Url = @"https://www.microsoft.com";` command.</span></span>  <span data-ttu-id="81f4c-167">行にブレークポイントを設定し、プロジェクトを実行して、Selenium ドライブ WebView2 を確認します。</span><span class="sxs-lookup"><span data-stu-id="81f4c-167">Verify the Selenium drive WebView2 by setting a breakpoint on the line and running the project.</span></span>  
    
    ```csharp
        //The following navigates the WebView2API Sample from bing.com to microsoft.com
        e.Url = @"https://www.microsoft.com";
        
        //This exits the edge driver
        e.Quit();
    }
    ```  
    
    :::image type="complex" source="../media/webdriver/microsoft.png" alt-text="WebView2 を実行するセレン" lightbox="../media/webdriver/microsoft.png":::
       <span data-ttu-id="81f4c-169">WebView2 を実行するセレン</span><span class="sxs-lookup"><span data-stu-id="81f4c-169">Selenium running WebView2</span></span>  
    :::image-end:::
    
<span data-ttu-id="81f4c-170">お疲れさまでした。</span><span class="sxs-lookup"><span data-stu-id="81f4c-170">Congratulations.</span></span>  <span data-ttu-id="81f4c-171">Selenium と Microsoft Edge Driver を使用して WebView2 プロジェクトと駆動型 WebView2 を正常に自動化しました。</span><span class="sxs-lookup"><span data-stu-id="81f4c-171">You have successfully automated a WebView2 project and driven WebView2 using Selenium and Microsoft Edge Driver.</span></span>  

## <a name="see-also"></a><span data-ttu-id="81f4c-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="81f4c-172">See also</span></span>  

*   <span data-ttu-id="81f4c-173">API Selenium が WebView2 または Microsoft Edge \(Chromium\) を駆動する方法の詳細については、Selenium のドキュメントの [WebDriver に移動します。][SeleniumWebdriver]</span><span class="sxs-lookup"><span data-stu-id="81f4c-173">For a comprehensive look at how the APIs Selenium drives WebView2 or Microsoft Edge \(Chromium\), navigate to [WebDriver on Selenium documentation][SeleniumWebdriver]</span></span>   
*   <span data-ttu-id="81f4c-174">WebView2 コントロールの詳細と、ネイティブ アプリに Web コンテンツを埋め込む際に使用する方法については [、「Microsoft Edge WebView2][WebViewIndex]の概要」に移動します。</span><span class="sxs-lookup"><span data-stu-id="81f4c-174">To learn more about WebView2 control and how to use it when embedding web content in your native app, navigate to [Introduction to Microsoft Edge WebView2][WebViewIndex].</span></span>  
*   <span data-ttu-id="81f4c-175">Microsoft Edge \(Chromium\) の自動化の詳細については、「テストオートメーションに[WebDriver (Chromium)][WebdriverChromium]を使用する」に移動します。</span><span class="sxs-lookup"><span data-stu-id="81f4c-175">To learn more about automating Microsoft Edge \(Chromium\), navigate to [Use WebDriver (Chromium) for test automation][WebdriverChromium]</span></span>   
    
## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a><span data-ttu-id="81f4c-176">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="81f4c-176">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[WebdriverChromium]: ../../webdriver-chromium/index.md "WebDriver (Chromium) を使用してテストオートメーションを|Microsoft Docs"  
[WebdriverChromiumDownloadMicrosoftEdgeDriver]: ../../webdriver-chromium/index.md#download-microsoft-edge-driver "Microsoft Edge Driver をダウンロードする - テストオートメーションに WebDriver (Chromium) を使用|Microsoft Docs"  
[WebViewIndex]: ../index.md "Microsoft Edge WebView2 の概要 - Microsoft Docs"  
[Webview2ReleaseNotes]: ../release-notes.md "WebView2 SDK のリリースノート |Microsoft Docs"  

[MicrosoftDeveloperMicrosoftEdgeWebDriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver#downloads "WebDriver ファイルをダウンロード|Microsoft Edge 開発者"  

[GithubMicrosoftedgewebview2samplesSampleappsWebview2apisample]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2APISample "WebView2 API サンプル - MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisamplePrerequisites]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2APISample#prerequisites "前提条件 - WebView2 API のサンプル |GitHub"  

[NugetSeleniumWebdriver400Alpha04]: https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-alpha04 "Selenium.WebDriver 4.0.0-alpha04 |NuGet ギャラリー"  

[SeleniumWebdriver]: https://www.selenium.dev/documentation/en/webdriver "WebDriver |Selenium"  

[W3cWebdriver2]: https://www.w3.org/TR/webdriver2 "WebDriver |W3C"  
