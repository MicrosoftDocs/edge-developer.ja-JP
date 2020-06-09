---
description: Microsoft Edge ドライバーを使用して WebView2 コントロールを自動化およびテストする
title: Microsoft Edge ドライバーを使用した WebView2 の自動化とテスト
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、edge、ICoreWebView2、ICoreWebView2Controller、Selenium、Microsoft Edge Driver
ms.openlocfilehash: 15e9a0957047569a0832fbb6ea6e8bf280905b8d
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697260"
---
# <span data-ttu-id="d96ff-104">Microsoft Edge ドライバーを使用した WebView2 の自動化とテスト</span><span class="sxs-lookup"><span data-stu-id="d96ff-104">Automating and testing WebView2 with Microsoft Edge Driver</span></span>

<span data-ttu-id="d96ff-105">WebView2 は Chromium web プラットフォームを利用しているため、WebView2 の開発者は、デバッグとオートメーション用の標準的な web ツールを利用できます。</span><span class="sxs-lookup"><span data-stu-id="d96ff-105">Because WebView2 utilizes the Chromium web platform, WebView2 developers can take advantage of standard web tooling for debugging and automation.</span></span> <span data-ttu-id="d96ff-106">このようなツールの1つは Selenium であり、W3C [Webdriver](https://www.w3.org/TR/webdriver2/) API を実装します。この API を使って、ユーザー操作をシミュレートする自動テストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d96ff-106">One such tool is Selenium, which implements the W3C [WebDriver](https://www.w3.org/TR/webdriver2/) API, which can be used to create automated tests that simulate user interactions.</span></span>

<span data-ttu-id="d96ff-107">手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d96ff-107">Here's how to get started:</span></span>

## <span data-ttu-id="d96ff-108">手順 1: WebView2API のサンプルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="d96ff-108">Step 1: Download WebView2API Sample</span></span>

<span data-ttu-id="d96ff-109">既存の WebView2 プロジェクトがない場合は、最新の WebView2 SDK の包括的なサンプルである、 [WebView2API サンプルアプリケーション](https://github.com/MicrosoftEdge/WebView2Samples/tree/master/WebView2APISample#webview2-api-sample)をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="d96ff-109">If you do not have an existing WebView2 project, download our [WebView2API Sample application](https://github.com/MicrosoftEdge/WebView2Samples/tree/master/WebView2APISample#webview2-api-sample), a comprehensive sample of the latest WebView2 SDK.</span></span> <span data-ttu-id="d96ff-110">これらの[前提条件](https://github.com/MicrosoftEdge/WebView2Samples/tree/master/WebView2APISample#prerequisites)を満たしていることをもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="d96ff-110">Please double check that you have satisfied these [prerequisites](https://github.com/MicrosoftEdge/WebView2Samples/tree/master/WebView2APISample#prerequisites).</span></span>

<span data-ttu-id="d96ff-111">リポジトリを複製したら、Visual Studio でプロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="d96ff-111">Once you have cloned the repo, build the project in Visual Studio.</span></span> <span data-ttu-id="d96ff-112">次のような表示になります。</span><span class="sxs-lookup"><span data-stu-id="d96ff-112">It should look like the following:</span></span>

![代替テキスト](../media/webdriver/sample-app.png)

## <span data-ttu-id="d96ff-114">手順 2: Microsoft Edge ドライバーをインストールする</span><span class="sxs-lookup"><span data-stu-id="d96ff-114">Step 2: Install Microsoft Edge Driver</span></span>

<span data-ttu-id="d96ff-115">指示に従って、 [Microsoft Edge driver](https://docs.microsoft.com/microsoft-edge/webdriver-chromium#download-microsoft-edge-driver)をインストールします。 Selenium では、WebView2 を自動化してテストするために必要なブラウザー固有のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="d96ff-115">Follow the instructions to install [Microsoft Edge Driver](https://docs.microsoft.com/microsoft-edge/webdriver-chromium#download-microsoft-edge-driver) the browser-specific driver required by Selenium to automate and test WebView2.</span></span>

<span data-ttu-id="d96ff-116">Microsoft Edge ドライバーのバージョンが、アプリケーションで使用されている Microsoft Edge のバージョンと一致していることを確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="d96ff-116">It is important to make sure that the version of Microsoft Edge Driver matches the version of Microsoft Edge that the application uses.</span></span> <span data-ttu-id="d96ff-117">WebView2API サンプルを使用するには、お使いの Microsoft Edge のバージョンが、サポートされている最新の SDK リリースの[リリースノートに含ま](https://docs.microsoft.com/microsoft-edge/hosting/webview2/releasenotes)れるバージョン以上であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d96ff-117">For the WebView2API Sample to work, make sure that your version of Microsoft Edge is greater than or equal to the supported version of our latest SDK release found [in our Release Notes](https://docs.microsoft.com/microsoft-edge/hosting/webview2/releasenotes).</span></span> <span data-ttu-id="d96ff-118">現在使用している Microsoft Edge のバージョンを確認するには、 `edge://settings/help` ブラウザーで読み込みます。</span><span class="sxs-lookup"><span data-stu-id="d96ff-118">To find out what version of Microsoft Edge you currently have, load `edge://settings/help` in the browser.</span></span>

## <span data-ttu-id="d96ff-119">手順 3: Selenium を WebView2API サンプルに追加する</span><span class="sxs-lookup"><span data-stu-id="d96ff-119">Step 3: Add Selenium to the WebView2API Sample</span></span>

<span data-ttu-id="d96ff-120">この時点で、Microsoft Edge をインストールして、WebView2 プロジェクトを構築し、Microsoft Edge ドライバーをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d96ff-120">At this point you should have Microsoft Edge installed, built a WebView2 project, and installed Microsoft Edge Driver.</span></span> <span data-ttu-id="d96ff-121">それでは、Selenium を使い始めましょう。</span><span class="sxs-lookup"><span data-stu-id="d96ff-121">Now, let's get started using Selenium.</span></span>

> [!NOTE]
> <span data-ttu-id="d96ff-122">Selenium は、C#、Java、Python、Javascript、および Ruby をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d96ff-122">Selenium supports C#, Java, Python, Javascript, and Ruby.</span></span> <span data-ttu-id="d96ff-123">ただし、このガイドは C# で説明されています。</span><span class="sxs-lookup"><span data-stu-id="d96ff-123">However, this guide will be in C#.</span></span>

1. <span data-ttu-id="d96ff-124">まず、 **Visual Studio**で新しい**C# .net Framework**プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d96ff-124">Start by creating a new **C# .NET Framework** project in **Visual Studio**.</span></span> <span data-ttu-id="d96ff-125">右下隅にある [**次へ**] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="d96ff-125">Click **Next** on the bottom right-hand corner to continue.</span></span>

![代替テキスト](../media/webdriver/new-project.png)

2. <span data-ttu-id="d96ff-127">プロジェクトに**名前**を付け、希望の**場所**に保存して、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d96ff-127">Give your project a **name**, save it to your preferred **location**, and click **Create**.</span></span>

![代替テキスト](../media/webdriver/app-create.png)

3. <span data-ttu-id="d96ff-129">新しいプロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d96ff-129">A new project will be created.</span></span> <span data-ttu-id="d96ff-130">このガイドでは、すべてのコードが**Program.cs**ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="d96ff-130">In this guide, all code will be written in the **Program.cs** file.</span></span>

![代替テキスト](../media/webdriver/start-app.png)

4. <span data-ttu-id="d96ff-132">それでは、プロジェクトに**Selenium**を追加しましょう。</span><span class="sxs-lookup"><span data-stu-id="d96ff-132">Now let's add **Selenium** to the project.</span></span> <span data-ttu-id="d96ff-133">Selenium は、 **Selenium ドライバー NuGet パッケージ**を使ってインストールできます。</span><span class="sxs-lookup"><span data-stu-id="d96ff-133">You can install Selenium via the **Selenium.WebDriver NuGet package**.</span></span>

<span data-ttu-id="d96ff-134">**Selenium ドライバーの nuget パッケージ**をダウンロードするには、 **Visual Studio**で**プロジェクト**をマウスでポイントし、[ **NuGet パッケージの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d96ff-134">To download the **Selenium.WebDriver NuGet package**, in **Visual Studio**, hover over **Project** and select **Manage NuGet Package**.</span></span> <span data-ttu-id="d96ff-135">次の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d96ff-135">The following screen should appear:</span></span>

![代替テキスト](../media/webdriver/download-nuget.png)

5. <span data-ttu-id="d96ff-137">検索バーに**Selenium ドライバー**を入力し、結果から [ **Selenium** ] をクリックして、[**プレリリースを含める**] の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d96ff-137">Enter **Selenium.WebDriver** in the search bar, click **Selenium.WebDriver** from the results, and make sure to checkmark the box next to **include pre-release**.</span></span> <span data-ttu-id="d96ff-138">右側のウィンドウで、**バージョン**が**4.0.0 をインストール**するように設定されていることを確認し、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d96ff-138">On the right-hand side window, ensure the **Version** is set to **install 4.0.0-alpha04** or later and click **Install**.</span></span> <span data-ttu-id="d96ff-139">Nuget は、Selenium をコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d96ff-139">Nuget will download Selenium to your machine.</span></span>

[<span data-ttu-id="d96ff-140">Selenium ドライバー NuGet パッケージの詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d96ff-140">Learn more about the Selenium.WebDriver NuGet package.</span></span>](https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-alpha04)

![代替テキスト](../media/webdriver/nuget.png)

6. <span data-ttu-id="d96ff-142">**OpenQA.Selenium.Edge** ```using OpenQA.Selenium.Edge;``` **Program.cs**の先頭に、次のステートメントを追加して Selenium を使います。</span><span class="sxs-lookup"><span data-stu-id="d96ff-142">Use **OpenQA.Selenium.Edge** by adding the following statement:```using OpenQA.Selenium.Edge;``` at the beginning of **Program.cs**</span></span>

```csharp
using OpenQA.Selenium.Edge;

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## <span data-ttu-id="d96ff-143">手順 4: Selenium と Microsoft EdgeDriver のドライブ WebView2</span><span class="sxs-lookup"><span data-stu-id="d96ff-143">Step 4: Drive WebView2 with Selenium and Microsoft EdgeDriver</span></span>

1. <span data-ttu-id="d96ff-144">まず、 `EdgeOptions` 次のコードをコピーしてオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d96ff-144">First, create the `EdgeOptions` object, by copying the code below:</span></span>

```csharp
static void Main(string[] args)
{
    // EdgeOptions() requires using OpenQA.Selenium.Edge
    // Construct EdgeOptions with is_legacy = false and the string "webview2"
    EdgeOptions edgeOptions = new EdgeOptions(false, "webview2");
```

<span data-ttu-id="d96ff-145">この `EdgeOptions` オブジェクトには、次の2つのパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="d96ff-145">The `EdgeOptions` object takes in two parameters:</span></span>
\
    **<span data-ttu-id="d96ff-146">引き</span><span class="sxs-lookup"><span data-stu-id="d96ff-146">Parameters:</span></span>**
    1. `is_legacy`<span data-ttu-id="d96ff-147">: を設定すると `false` 、新しい Chromium ベースの Microsoft Edge ブラウザーを運転していることが Selenium に指示されます。</span><span class="sxs-lookup"><span data-stu-id="d96ff-147">: set to `false`, which tells Selenium that you are driving the new Chromium-based Microsoft Edge browser.</span></span>
    2. `"webview2"`<span data-ttu-id="d96ff-148">: **WebView2**を運転している Selenium を示す文字列</span><span class="sxs-lookup"><span data-stu-id="d96ff-148">: a string that tell Selenium you are driving **WebView2**</span></span>

2. <span data-ttu-id="d96ff-149">次に、 `edgeOptions.BinaryLocation` WebView2 プロジェクトの実行可能ファイルのファイルパスを設定して、 `msedgedriverDir` [microsoft edge ドライバー](https://developer.microsoft.com/microsoft-edge/tools/webdriver/#downloads)をインストールした場所へのファイルパスを提供する文字列を作成し、 `msedgedriverExe` microsoft edge ドライバーの実行可能ファイルの名前を格納するために呼び出される文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="d96ff-149">Next, set `edgeOptions.BinaryLocation` to the file path of your WebView2 project's executable, create a string called `msedgedriverDir` that provides the file path to where you installed [Microsoft Edge Driver](https://developer.microsoft.com/microsoft-edge/tools/webdriver/#downloads), and create a string called `msedgedriverExe` to store the name of the Microsoft Edge Driver executable.</span></span> <span data-ttu-id="d96ff-150">既定では、実行可能ファイルが呼び出され `"msedgedriver.exe"` ます。</span><span class="sxs-lookup"><span data-stu-id="d96ff-150">By default, the executable is called `"msedgedriver.exe"`.</span></span> <span data-ttu-id="d96ff-151">次に示すように、これら2つの文字列を使っ `EdgeDriverService` てオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d96ff-151">Use these two strings to construct the `EdgeDriverService` object as shown below.</span></span> <span data-ttu-id="d96ff-152">最後に、and を使用してオブジェクトを作成し `EdgeDriver` `EdgeDriverService` `EdgeOptions` ます。</span><span class="sxs-lookup"><span data-stu-id="d96ff-152">Finally, create the `EdgeDriver` object using `EdgeDriverService` and `EdgeOptions`.</span></span>

<span data-ttu-id="d96ff-153">以下のコードをコピーして貼り付けることができ `edgeOptions` ます。</span><span class="sxs-lookup"><span data-stu-id="d96ff-153">You can copy and paste the following code underneath `edgeOptions`.</span></span> <span data-ttu-id="d96ff-154">使用しているコンピューターで、プロジェクトの実行可能ファイルと Microsoft Edge ドライバーの実行可能ファイルに適切なファイルパスを指定していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d96ff-154">Make sure to specify the correct file paths to your project's executable and the Microsoft Edge Driver's executable on your machine.</span></span>

```csharp
    //Set the BinaryLocation to the filepath of the WebView2API Sample's executable
    edgeOptions.BinaryLocation = @"C:\path\to\your\webview2\project.exe";

    //Set msedgedriverDir to the filepath of the directory housing msedgedriver.exe
    string msedgedriverDir = @"C:\path\to\your\msededriver.exe's\directory";

    //Set msedgedriverExe to the name of the Edge Driver. By default it is:
    string msedgedriverExe = @"msedgedriver.exe";

    // Construct EdgeDriverService with is_legacy = false  
    EdgeDriverService service = EdgeDriverService.CreateDefaultService(msedgedriverDir, msedgedriverExe, false);

    EdgeDriver e = new EdgeDriver(service, edgeOptions);
```

3. <span data-ttu-id="d96ff-155">これで、 **EdgeDriver**は、プロジェクトで**WebView2**を設定するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="d96ff-155">Now, **EdgeDriver** is configured to drive the **WebView2** in your project.</span></span> <span data-ttu-id="d96ff-156">たとえば、 **WebView2API サンプル**を使っている場合は、に**移動**でき <https://microsoft.com> ```e.Url = @"https://www.microsoft.com";``` ます。</span><span class="sxs-lookup"><span data-stu-id="d96ff-156">For example, if you are using the **WebView2API Sample**, you can **Navigate** to <https://microsoft.com> by calling ```e.Url = @"https://www.microsoft.com";```.</span></span> <span data-ttu-id="d96ff-157">この行にブレークポイントを設定し、プロジェクトを実行して、 **Selenium** drive **WebView2**を視聴することができます。</span><span class="sxs-lookup"><span data-stu-id="d96ff-157">You can watch **Selenium** drive **WebView2** by setting a breakpoint on this line and running the project.</span></span>

```csharp
    //The following will Navigate the WebView2API Sample from bing.com to microsoft.com
    e.Url = @"https://www.microsoft.com";

    //This exits the edge driver
    e.Quit();
}
```

![代替テキスト](../media/webdriver/microsoft.png)

<span data-ttu-id="d96ff-159">お疲れさまでした。</span><span class="sxs-lookup"><span data-stu-id="d96ff-159">Congratulations!</span></span> <span data-ttu-id="d96ff-160">Selenium および Microsoft Edge ドライバーを使用して、WebView2 プロジェクトとドリブン WebView2 を正常に自動化しました。</span><span class="sxs-lookup"><span data-stu-id="d96ff-160">You have successfully automated a WebView2 project and driven WebView2 using Selenium and Microsoft Edge Driver.</span></span>

## <span data-ttu-id="d96ff-161">次のステップ</span><span class="sxs-lookup"><span data-stu-id="d96ff-161">Next steps</span></span>

<span data-ttu-id="d96ff-162">詳細は次のページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d96ff-162">To learn more:</span></span>

- <span data-ttu-id="d96ff-163">[Selenium のドキュメント](https://www.selenium.dev/documentation/en/webdriver/)を参照して、WebView2 または Microsoft Edge (Chromium) で利用できる api Selenium の概要をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d96ff-163">Check out [Selenium's documentation](https://www.selenium.dev/documentation/en/webdriver/) for a comprehensive look at the APIs Selenium has available for driving WebView2 or Microsoft Edge (Chromium)</span></span>
- <span data-ttu-id="d96ff-164">[WebView2](https://docs.microsoft.com/microsoft-edge/hosting/webview2)コントロールの詳細と、ネイティブアプリに web コンテンツを埋め込むときの使い方について説明します。</span><span class="sxs-lookup"><span data-stu-id="d96ff-164">Learn more about [WebView2](https://docs.microsoft.com/microsoft-edge/hosting/webview2) control and how to use it when embedding web content in your native app</span></span>
- <span data-ttu-id="d96ff-165">Microsoft edge ドライバーの概要 (Chromium) の詳細については、 [Microsoft Edge ドライバーのドキュメント](https://docs.microsoft.com/microsoft-edge/webdriver-chromium)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d96ff-165">Check out [documentation for Microsoft Edge Driver](https://docs.microsoft.com/microsoft-edge/webdriver-chromium) to learn more about automating Microsoft Edge (Chromium)</span></span>

## <span data-ttu-id="d96ff-166">WebView2 チームと連絡を取り合う</span><span class="sxs-lookup"><span data-stu-id="d96ff-166">Getting in touch with the WebView2 team</span></span>  

<span data-ttu-id="d96ff-167">フィードバックを共有することで、より充実した WebView2 エクスペリエンスを構築できます。</span><span class="sxs-lookup"><span data-stu-id="d96ff-167">Help us build a richer WebView2 experience by sharing your feedback!</span></span> <span data-ttu-id="d96ff-168">[フィードバックリポジトリ](https://github.com/MicrosoftEdge/WebViewFeedback)にアクセスして、機能のリクエストやバグレポートを送信したり、既知の問題を検索したりします。</span><span class="sxs-lookup"><span data-stu-id="d96ff-168">Visit our [feedback repo](https://github.com/MicrosoftEdge/WebViewFeedback) to submit feature requests or bug reports or to search for known issues.</span></span>
