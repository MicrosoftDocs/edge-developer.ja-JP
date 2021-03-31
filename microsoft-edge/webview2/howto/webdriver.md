---
description: Microsoft Edge ドライバーを使用して WebView2 コントロールを自動化およびテストする
title: Microsoft Edge ドライバーを使用した WebView2 の自動化とテスト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/25/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、edge、ICoreWebView2、ICoreWebView2Controller、Selenium、Microsoft Edge Driver
ms.openlocfilehash: 2af1ce222abb1dc7a279afc05e87e7e42a45fe9e
ms.sourcegitcommit: 2e14ff82350f700d7eabc8d33b3ec3e5fc8c61fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "11191618"
---
# <span data-ttu-id="8cb5d-104">Microsoft Edge ドライバーを使用した WebView2 の自動化とテスト</span><span class="sxs-lookup"><span data-stu-id="8cb5d-104">Automating and testing WebView2 with Microsoft Edge Driver</span></span>  

<span data-ttu-id="8cb5d-105">WebView2 は Microsoft Edge \(Chromium \) web platform を使っているため、WebView2 の開発者 \(お客様 \) は、デバッグとオートメーション用の標準的な web ツールを利用することができます。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-105">Because WebView2 uses the Microsoft Edge \(Chromium\) web platform, WebView2 developers \(you\) may take advantage of standard web tooling for debugging and automation.</span></span>  <span data-ttu-id="8cb5d-106">Selenium は、このようなツールの1つです。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-106">Selenium is one such tool.</span></span>  <span data-ttu-id="8cb5d-107">W3C [Webdriver][W3cWebdriver2] API を実装します。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-107">It implements the W3C [WebDriver][W3cWebdriver2] API.</span></span>  <span data-ttu-id="8cb5d-108">Selenium を使って、自動テストを作成し、ユーザーの操作をシミュレートすることができます。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-108">You may use Selenium to create automated tests to simulate user interactions.</span></span>  

<span data-ttu-id="8cb5d-109">次の手順で作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-109">Get started with the following steps.</span></span>  

## <span data-ttu-id="8cb5d-110">手順 1: WebView2API のサンプルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="8cb5d-110">Step 1:  Download WebView2API Sample</span></span>  

<span data-ttu-id="8cb5d-111">既存の WebView2 プロジェクトがない場合は、最新の WebView2 SDK の包括的なサンプルである [WebView2API サンプルアプリ][GithubMicrosoftedgewebview2samplesSampleappsWebview2apisample]をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-111">If you do not have an existing WebView2 project, download the [WebView2API Sample app][GithubMicrosoftedgewebview2samplesSampleappsWebview2apisample], a comprehensive sample of the latest WebView2 SDK.</span></span>  <span data-ttu-id="8cb5d-112">[WebView2API サンプルアプリの前提条件][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisamplePrerequisites]を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-112">Ensure you have satisfied the [prerequisites for the WebView2API Sample app][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisamplePrerequisites].</span></span>  

<span data-ttu-id="8cb5d-113">リポジトリを複製したら、Visual Studio でプロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-113">Once you have cloned the repo, build the project in Visual Studio.</span></span>  <span data-ttu-id="8cb5d-114">次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-114">It should look like the following figure.</span></span>  

:::image type="complex" source="../media/webdriver/sample-app.png" alt-text="WebView2API サンプルアプリ" lightbox="../media/webdriver/sample-app.png":::
   <span data-ttu-id="8cb5d-116">WebView2API サンプルアプリ</span><span class="sxs-lookup"><span data-stu-id="8cb5d-116">WebView2API Sample app</span></span>  
:::image-end:::  

## <span data-ttu-id="8cb5d-117">手順 2: Microsoft Edge ドライバーをインストールする</span><span class="sxs-lookup"><span data-stu-id="8cb5d-117">Step 2:  Install Microsoft Edge Driver</span></span>  

<span data-ttu-id="8cb5d-118">指示に従って、 [Microsoft Edge driver][WebdriverChromiumDownloadMicrosoftEdgeDriver] をインストールします。 Selenium では、WebView2 を自動化してテストするために必要なブラウザー固有のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-118">Follow the instructions to install [Microsoft Edge Driver][WebdriverChromiumDownloadMicrosoftEdgeDriver] the browser-specific driver required by Selenium to automate and test WebView2.</span></span>  

<span data-ttu-id="8cb5d-119">Microsoft Edge ドライバーのバージョンが、アプリで使用する WebView2 ランタイムのバージョンと一致していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-119">Ensure that the version of Microsoft Edge Driver matches the version of WebView2 Runtime that you app uses.</span></span>  <span data-ttu-id="8cb5d-120">WebView2API サンプルを動作させるには、WebView2 Runtime のバージョンが、最新の WebView2 SDK リリースのサポートされているバージョン以上であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-120">For the WebView2API Sample to work, make sure that your version of WebView2 Runtime is greater than or equal than the supported version of the latest WebView2 SDK release.</span></span>  <span data-ttu-id="8cb5d-121">最新の WebView2 SDK リリースを見つけるには、 [WebView2 リリースノート][Webview2Releasenotes]に移動します。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-121">To locate the latest WebView2 SDK release, navigate to [WebView2 release notes][Webview2Releasenotes].</span></span>  <span data-ttu-id="8cb5d-122">現在使用している WebView2 ランタイムのバージョンを確認するには、に移動 `edge://settings/help` します。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-122">To find out what version of WebView2 Runtime you currently have, navigate to `edge://settings/help`.</span></span>  

## <span data-ttu-id="8cb5d-123">手順 3: Selenium を WebView2API サンプルに追加する</span><span class="sxs-lookup"><span data-stu-id="8cb5d-123">Step 3:  Add Selenium to the WebView2API Sample</span></span>  

<span data-ttu-id="8cb5d-124">この時点で、WebView2 Runtime がインストールされていて、WebView2 プロジェクトと Microsoft Edge ドライバーがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-124">At this point you should have WebView2 Runtime installed, built a WebView2 project, and installed Microsoft Edge Driver.</span></span>  <span data-ttu-id="8cb5d-125">それでは、Selenium を使い始めましょう。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-125">Now, get started using Selenium.</span></span>  

> [!NOTE]
> <span data-ttu-id="8cb5d-126">Selenium は、C \ #、Java、Python、Javascript、ルビをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-126">Selenium supports C\#, Java, Python, Javascript, and Ruby.</span></span>  <span data-ttu-id="8cb5d-127">ただし、次のガイドは C \ # を使って作成されています。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-127">However, the following guide is written using C\#.</span></span>  

1.  <span data-ttu-id="8cb5d-128">まず、 **Visual Studio**で新しい**C# .net Framework**プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-128">Start by creating a new **C# .NET Framework** project in **Visual Studio**.</span></span>  <span data-ttu-id="8cb5d-129">右下隅にある [ **次へ** ] を選んで続行します。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-129">Choose **Next** on the bottom right-hand corner to continue.</span></span>  
    
    :::image type="complex" source="../media/webdriver/new-project.png" alt-text="新しいプロジェクトの作成" lightbox="../media/webdriver/new-project.png":::
       <span data-ttu-id="8cb5d-131">新しいプロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="8cb5d-131">Create a new project</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8cb5d-132">プロジェクトに **名前**を付け、希望の **場所**に保存して、[ **作成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-132">Give your project a **name**, save it to your preferred **location**, and choose **Create**.</span></span>  
    
    :::image type="complex" source="../media/webdriver/app-create.png" alt-text="新しいプロジェクトを構成する" lightbox="../media/webdriver/app-create.png":::
       <span data-ttu-id="8cb5d-134">新しいプロジェクトを構成する</span><span class="sxs-lookup"><span data-stu-id="8cb5d-134">Configure your new project</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8cb5d-135">新しいプロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-135">A new project is created.</span></span>  <span data-ttu-id="8cb5d-136">このガイドでは、すべてのコードがファイルに書き込まれ `Program.cs` ます。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-136">In this guide, all code is written to the `Program.cs` file.</span></span>  
    
    :::image type="complex" source="../media/webdriver/start-app.png" alt-text="新しいプロジェクト" lightbox="../media/webdriver/start-app.png":::
       <span data-ttu-id="8cb5d-138">新しいプロジェクト</span><span class="sxs-lookup"><span data-stu-id="8cb5d-138">New project</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8cb5d-139">次に、プロジェクトに **Selenium** を追加します。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-139">Now add **Selenium** to the project.</span></span>  <span data-ttu-id="8cb5d-140">**Selenium**をインストールするには、Selenium を使用します。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-140">Install Selenium using the **Selenium.WebDriver NuGet package**.</span></span>  
    
    <span data-ttu-id="8cb5d-141">**Selenium ドライバーの nuget パッケージ**をダウンロードするには、 **Visual Studio**で**プロジェクト**をポイントして、[ **NuGet パッケージの管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-141">To download the **Selenium.WebDriver NuGet package**, in **Visual Studio**, hover over **Project**, and choose **Manage NuGet Package**.</span></span>  <span data-ttu-id="8cb5d-142">次の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-142">The following screen should appear.</span></span>  
    
    :::image type="complex" source="../media/webdriver/download-nuget.png" alt-text="NuGet パッケージをダウンロードする" lightbox="../media/webdriver/download-nuget.png":::
       <span data-ttu-id="8cb5d-144">NuGet パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="8cb5d-144">Download NuGet package</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8cb5d-145">`Selenium.WebDriver`検索バーに入力し、結果から [ **Selenium ドライバー** ] を選び、[**プレリリースを含める**] の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-145">Enter `Selenium.WebDriver` in the search bar, choose **Selenium.WebDriver** from the results, and make sure to checkmark the box next to **include pre-release**.</span></span>  <span data-ttu-id="8cb5d-146">右側のウィンドウで、 **バージョン** が **4.0.0 をインストール** するように設定されていることを確認し、[ **インストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-146">On the right-hand side window, ensure the **Version** is set to **install 4.0.0-alpha04** or later and choose **Install**.</span></span>  <span data-ttu-id="8cb5d-147">NuGet をコンピューターにダウンロード Selenium します。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-147">NuGet downloads Selenium to your machine.</span></span>  
    
    <span data-ttu-id="8cb5d-148">Selenium ドライバーの NuGet パッケージの詳細については、 [Selenium][NugetSeleniumWebdriver400Alpha04]にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-148">To learn more about the Selenium.WebDriver NuGet package, navigate to [Selenium.WebDriver 4.0.0-alpha04][NugetSeleniumWebdriver400Alpha04].</span></span>  
    
    :::image type="complex" source="../media/webdriver/nuget.png" alt-text="NuGet パッケージの管理" lightbox="../media/webdriver/nuget.png":::
       <span data-ttu-id="8cb5d-150">NuGet パッケージの管理</span><span class="sxs-lookup"><span data-stu-id="8cb5d-150">Manage NuGet package</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8cb5d-151">`OpenQA.Selenium.Edge` `using OpenQA.Selenium.Edge;` ファイルの先頭に次のステートメントを追加して使用し `Program.cs` ます。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-151">Use `OpenQA.Selenium.Edge` by adding the following statement:  `using OpenQA.Selenium.Edge;` at the beginning of `Program.cs` file.</span></span>  
    
    ```csharp
    using OpenQA.Selenium.Edge;
    
    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    ```  
    
## <span data-ttu-id="8cb5d-152">手順 4: Selenium と Microsoft Edge ドライバーを使用して WebView2 ドライブを使用する</span><span class="sxs-lookup"><span data-stu-id="8cb5d-152">Step 4: Drive WebView2 with Selenium and Microsoft Edge Driver</span></span>  

1.  <span data-ttu-id="8cb5d-153">まず、 `EdgeOptions` 次のコードスニペットをコピーして、オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-153">First, create the `EdgeOptions` object, by copying the following code snippet.</span></span>  
    
    ```csharp
    static void Main(string[] args)
    {
        // EdgeOptions() requires using OpenQA.Selenium.Edge
        // Construct EdgeOptions with is_legacy = false and the string "webview2"
        EdgeOptions edgeOptions = new EdgeOptions(false, "webview2");
    ```  
    
    <span data-ttu-id="8cb5d-154">このオブジェクトには、 `EdgeOptions` 次の2つのパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-154">The `EdgeOptions` object takes in the following two parameters.</span></span>  
    
    | <span data-ttu-id="8cb5d-155">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8cb5d-155">Parameter</span></span> | <span data-ttu-id="8cb5d-156">詳細</span><span class="sxs-lookup"><span data-stu-id="8cb5d-156">Details</span></span> |    
    |:--- |:--- |  
    | `is_legacy` | <span data-ttu-id="8cb5d-157">Selenium を設定すると `false` 、新しい Chromium ベースの Microsoft Edge ブラウザーを運転していることが通知されます。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-157">Set to `false`, which tells Selenium that you are driving the new Chromium-based Microsoft Edge browser.</span></span> |  
    | `"webview2"` | <span data-ttu-id="8cb5d-158">WebView2 を運転している Selenium を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-158">A string that tells Selenium you are driving WebView2.</span></span> |  
    
1.  <span data-ttu-id="8cb5d-159">次に、 `edgeOptions.BinaryLocation` WebView2 project ランタイムのファイルパスを設定し、 `msedgedriverDir` [microsoft edge ドライバー][MicrosoftDeveloperMicrosoftEdgeWebDriverDownloads]をインストールした場所へのファイルパスを提供するという名前の文字列を作成して、 `msedgedriverExe` microsoft edge ドライバーランタイムの名前を格納するための名前の付いた文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-159">Next, set `edgeOptions.BinaryLocation` to the file path of your WebView2 project runtime, create a string named `msedgedriverDir` that provides the file path to where you installed [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeWebDriverDownloads], and create a string named `msedgedriverExe` to store the name of the Microsoft Edge Driver runtime.</span></span>  <span data-ttu-id="8cb5d-160">既定では、ランタイムにはという名前が付けられ `msedgedriver.exe` ます。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-160">By default, the runtime is named `msedgedriver.exe`.</span></span> <span data-ttu-id="8cb5d-161">次に示すように、これら2つの文字列を使っ `EdgeDriverService` てオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-161">Use these two strings to construct the `EdgeDriverService` object as shown below.</span></span>  <span data-ttu-id="8cb5d-162">最後に、and を使用してオブジェクトを作成し `EdgeDriver` `EdgeDriverService` `EdgeOptions` ます。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-162">Finally, create the `EdgeDriver` object using `EdgeDriverService` and `EdgeOptions`.</span></span>  
    
    <span data-ttu-id="8cb5d-163">以下のコードをコピーして貼り付けることができ `edgeOptions` ます。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-163">You may copy and paste the following code underneath `edgeOptions`.</span></span>  <span data-ttu-id="8cb5d-164">コンピューターのプロジェクトランタイムと Microsoft Edge ドライバーランタイムへの適切なファイルパスを指定していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-164">Ensure you specify the correct file paths to your project runtime and the Microsoft Edge Driver runtime on your machine.</span></span>  
    
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
    
3.  <span data-ttu-id="8cb5d-165">これで、 `EdgeDriver` プロジェクトで WebView2 を実行するように構成されました。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-165">Now, `EdgeDriver` is configured to drive the WebView2 in your project.</span></span>  <span data-ttu-id="8cb5d-166">たとえば、 **WebView2API サンプル**を使っている場合は、コマンドを実行して移動することができ `https://microsoft.com` `e.Url = @"https://www.microsoft.com";` ます。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-166">For example, if you are using the **WebView2API Sample**, you may navigate to `https://microsoft.com` by running the `e.Url = @"https://www.microsoft.com";` command.</span></span>  <span data-ttu-id="8cb5d-167">行にブレークポイントを設定し、プロジェクトを実行して、Selenium drive WebView2 を確認します。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-167">Verify the Selenium drive WebView2 by setting a breakpoint on the line and running the project.</span></span>  
    
    ```csharp
        //The following navigates the WebView2API Sample from bing.com to microsoft.com
        e.Url = @"https://www.microsoft.com";
        
        //This exits the edge driver
        e.Quit();
    }
    ```  
    
    :::image type="complex" source="../media/webdriver/microsoft.png" alt-text="Selenium WebView2" lightbox="../media/webdriver/microsoft.png":::
       <span data-ttu-id="8cb5d-169">Selenium WebView2</span><span class="sxs-lookup"><span data-stu-id="8cb5d-169">Selenium running WebView2</span></span>  
    :::image-end:::

<span data-ttu-id="8cb5d-170">お疲れさまでした。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-170">Congratulations.</span></span>  <span data-ttu-id="8cb5d-171">Selenium および Microsoft Edge ドライバーを使用して、WebView2 プロジェクトとドリブン WebView2 を正常に自動化しました。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-171">You have successfully automated a WebView2 project and driven WebView2 using Selenium and Microsoft Edge Driver.</span></span>  

## <span data-ttu-id="8cb5d-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="8cb5d-172">See also</span></span>  

*   <span data-ttu-id="8cb5d-173">Api Selenium が WebView2 または Microsoft Edge \(Chromium \) を操作する方法の概要については、 [Selenium のドキュメントの Webdriver][SeleniumWebdriver]に移動してください。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-173">For a comprehensive look at how the APIs Selenium drives WebView2 or Microsoft Edge \(Chromium\), navigate to [WebDriver on Selenium documentation][SeleniumWebdriver]</span></span>   
*   <span data-ttu-id="8cb5d-174">WebView2 control の詳細と、ネイティブアプリに web コンテンツを埋め込むときの使用方法については、「 [Microsoft Edge WebView2 の概要][WebViewIndex]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-174">To learn more about WebView2 control and how to use it when embedding web content in your native app, navigate to [Introduction to Microsoft Edge WebView2][WebViewIndex].</span></span>  
*   <span data-ttu-id="8cb5d-175">Microsoft Edge \(Chromium) の自動化の詳細については、「 [WebDriver (Chromium) を使ってテストオートメーションを使用][WebdriverChromium]する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cb5d-175">To learn more about automating Microsoft Edge \(Chromium\), navigate to [Use WebDriver (Chromium) for test automation][WebdriverChromium]</span></span>   
    
## <span data-ttu-id="8cb5d-176">Microsoft Edge WebView チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="8cb5d-176">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[WebdriverChromium]: ../../webdriver-chromium/index.md "テストオートメーションに WebDriver (Chromium) を使います。Microsoft ドキュメント"  
[WebdriverChromiumDownloadMicrosoftEdgeDriver]: ../../webdriver-chromium/index.md#download-microsoft-edge-driver "Microsoft Edge ドライバーをダウンロードする-テストオートメーション用に WebDriver (Chromium) を使います。Microsoft ドキュメント"  
[WebViewIndex]: ../index.md "Microsoft Edge WebView2 の概要-Microsoft ドキュメント"  
[Webview2Releasenotes]: ../releasenotes.md "WebView2 SDK のリリースノート |Microsoft ドキュメント"  

[MicrosoftDeveloperMicrosoftEdgeWebDriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver#downloads "WebDriver をダウンロード |Microsoft Edge 開発者"  

[GithubMicrosoftedgewebview2samplesSampleappsWebview2apisample]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2APISample "WebView2 API のサンプル-MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisamplePrerequisites]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2APISample#prerequisites "前提条件-WebView2 API のサンプル |GitHub"  

[NugetSeleniumWebdriver400Alpha04]: https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-alpha04 "Selenium ドライバー 4.0.0-alpha04 |NuGet ギャラリー"  

[SeleniumWebdriver]: https://www.selenium.dev/documentation/en/webdriver "WebDriver |Selenium"  

[W3cWebdriver2]: https://www.w3.org/TR/webdriver2 "WebDriver |勧告"  
