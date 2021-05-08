---
description: Microsoft Edge WebView2 Chromium DevTools プロトコル パッケージを使用して WebView2 アプリで Chrome DevTools プロトコルをNuGetする方法
title: WebView2 で Chrome DevTools プロトコルを使用する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、edge、ICoreWebView2、ICoreWebView2Controller、Chrome DevTools プロトコル
ms.openlocfilehash: cd59bc0d177d17680222fcff8452c2cf8d56b195
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "11536056"
---
# <a name="use-chromium-devtools-protocol-in-webview2"></a><span data-ttu-id="41e2f-104">WebView2 で Chromium DevTools プロトコルを使用する</span><span class="sxs-lookup"><span data-stu-id="41e2f-104">Use Chromium DevTools Protocol in WebView2</span></span>  

<span data-ttu-id="41e2f-105">[DevTools プロトコルChromium Api][GitHubChromedevtoolsDevtoolsProtocol]は、ユーザー ベースのブラウザーをインストルメント、検査、デバッグ、およびプロファイルChromium提供します。</span><span class="sxs-lookup"><span data-stu-id="41e2f-105">The [Chromium DevTools Protocol][GitHubChromedevtoolsDevtoolsProtocol] provides APIs to instrument, inspect, debug, and profile Chromium-based browsers.</span></span>  <span data-ttu-id="41e2f-106">DevTools Chromiumは、\(Chromium\) DevTools のMicrosoft Edge基盤です。</span><span class="sxs-lookup"><span data-stu-id="41e2f-106">The Chromium DevTools Protocol is the foundation for the Microsoft Edge \(Chromium\) DevTools.</span></span>  <span data-ttu-id="41e2f-107">WebView2 Chromium実装されていない機能については、DevTools プロトコルの一覧を使用します。</span><span class="sxs-lookup"><span data-stu-id="41e2f-107">Use the Chromium DevTools Protocol for features that aren't implemented in the WebView2 platform.</span></span>  <span data-ttu-id="41e2f-108">DevTools プロトコルの機能Chromium詳細については[、「DevTools プロトコルChromium」に移動します][GitHubChromedevtoolsDevtoolsProtocol]。</span><span class="sxs-lookup"><span data-stu-id="41e2f-108">For more information about the Chromium DevTools Protocol functionality, navigate to [Chromium DevTools Protocol][GitHubChromedevtoolsDevtoolsProtocol].</span></span>  

> [!CAUTION]
> <span data-ttu-id="41e2f-109">WebView2 Microsoft Edgeは、DevTools プロトコルを維持またはChromiumサポートしていない。</span><span class="sxs-lookup"><span data-stu-id="41e2f-109">The Microsoft Edge WebView2 team does not maintain or support the Chromium DevTools Protocol.</span></span>  <span data-ttu-id="41e2f-110">DevTools Chromiumは、プロジェクトのオープン ソースによってChromiumされます。</span><span class="sxs-lookup"><span data-stu-id="41e2f-110">The Chromium DevTools Protocol is maintained by the open source Chromium project.</span></span>  
> 
> <span data-ttu-id="41e2f-111">将来の WebView2 プラットフォーム機能に関する提案を送信するには [、[WebView フィードバック][GithubMicrosoftedgeWebview2feedback] ] に移動して問題を提出します。</span><span class="sxs-lookup"><span data-stu-id="41e2f-111">To send your suggestions for future WebView2 platform features, navigate to [WebView Feedback][GithubMicrosoftedgeWebview2feedback] and submit an issue.</span></span>  

<span data-ttu-id="41e2f-112">WebView2 で Chromium DevTools プロトコル API を使用するには、次のいずれかのアクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="41e2f-112">To use the Chromium DevTools Protocol API in WebView2, use either of the following actions.</span></span>  

*   <span data-ttu-id="41e2f-113">[Microsoft.Web.WebView2.DevToolsProtocolExtension (Preview)][NugetPackagesMicrosoftWebWebView2DevToolsprotocolextension]パッケージ \(.NET\) をインストールNuGet使用します。</span><span class="sxs-lookup"><span data-stu-id="41e2f-113">Install and use the [Microsoft.Web.WebView2.DevToolsProtocolExtension (Preview)][NugetPackagesMicrosoftWebWebView2DevToolsprotocolextension] NuGet package \(.NET\).</span></span>  
*   <span data-ttu-id="41e2f-114">次のいずれかの方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="41e2f-114">Run one of the following methods.</span></span>  
    *   <span data-ttu-id="41e2f-115">.NET:  [CallDevToolsProtocolAsync][DotnetApiMicrosoftWebWebview2CoreCorewebview2CalldevtoolsprotocolmethodasyncViewWebview2Dotnet1077444MicrosoftWebWebView2CoreCorewebview2CalldevtoolsprotocolmethodsyncSystemStringSystemString], [GetDevToolsProtocolEventReceiver][DotnetApiMicrosoftWebWebview2CoreCorewebview2GetdevtoolsprotocoleventreceiverViewWebview2Dotnet1077444]</span><span class="sxs-lookup"><span data-stu-id="41e2f-115">.NET:  [CallDevToolsProtocolAsync][DotnetApiMicrosoftWebWebview2CoreCorewebview2CalldevtoolsprotocolmethodasyncViewWebview2Dotnet1077444MicrosoftWebWebView2CoreCorewebview2CalldevtoolsprotocolmethodsyncSystemStringSystemString], [GetDevToolsProtocolEventReceiver][DotnetApiMicrosoftWebWebview2CoreCorewebview2GetdevtoolsprotocoleventreceiverViewWebview2Dotnet1077444]</span></span>  
    *   <span data-ttu-id="41e2f-116">Win32 C/C++:  [CallDevToolsProtocolMethod][Webview2ReferenceWin32Icorewebview2ViewWebview21077444Calldevtoolsprotocolmethod], [ICoreWebView2DevToolsProtocolEventReceiver][Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview21077444]</span><span class="sxs-lookup"><span data-stu-id="41e2f-116">Win32 C/C++:  [CallDevToolsProtocolMethod][Webview2ReferenceWin32Icorewebview2ViewWebview21077444Calldevtoolsprotocolmethod], [ICoreWebView2DevToolsProtocolEventReceiver][Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview21077444]</span></span>  
    
## <a name="use-devtoolsprotocolhelper-preview"></a><span data-ttu-id="41e2f-117">Use DevToolsProtocolHelper (Preview)</span><span class="sxs-lookup"><span data-stu-id="41e2f-117">Use DevToolsProtocolHelper (Preview)</span></span>

> [!NOTE]
> <span data-ttu-id="41e2f-118">[Microsoft.Web.WebView2.DevToolsProtocolExtension][NugetPackagesMicrosoftWebWebView2DevToolsprotocolextension] NuGet現在テクニカル プレビュー中です。</span><span class="sxs-lookup"><span data-stu-id="41e2f-118">The [Microsoft.Web.WebView2.DevToolsProtocolExtension][NugetPackagesMicrosoftWebWebView2DevToolsprotocolextension] NuGet package is currently in technical preview.</span></span>  <span data-ttu-id="41e2f-119">プレビュー中は、実稼働アプリでのパッケージの使用を控える必要があります。</span><span class="sxs-lookup"><span data-stu-id="41e2f-119">While in preview, refrain from using the package in production apps.</span></span>

<span data-ttu-id="41e2f-120">[Microsoft.Web.WebView2.DevToolsProtocolExtension (Preview)][NugetPackagesMicrosoftWebWebView2DevToolsprotocolextension]は、Chromium DevTools プロトコル機能に簡単にアクセスできる WebView2 チームによって作成された NuGet パッケージです。</span><span class="sxs-lookup"><span data-stu-id="41e2f-120">[Microsoft.Web.WebView2.DevToolsProtocolExtension (Preview)][NugetPackagesMicrosoftWebWebView2DevToolsprotocolextension] is a NuGet package created by the WebView2 team that provides easy access to Chromium DevTools Protocol features.</span></span>  <span data-ttu-id="41e2f-121">次の例では、WebView2 コントロールの DevTools プロトコルChromium位置情報機能を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="41e2f-121">The following examples describe how to use the geolocation functionality in Chromium DevTools Protocol in your WebView2 control.</span></span>  <span data-ttu-id="41e2f-122">同様のパターンに従って、他の DevTools プロトコル機能Chromium使用できます。</span><span class="sxs-lookup"><span data-stu-id="41e2f-122">You may follow a similar pattern to use other Chromium DevTools Protocol features.</span></span>  

## <a name="step-1-create-a-webpage-to-find-your-geolocation"></a><span data-ttu-id="41e2f-123">手順 1: Web ページを作成して位置情報を検索する</span><span class="sxs-lookup"><span data-stu-id="41e2f-123">Step 1: Create a webpage to find your geolocation</span></span>  

<span data-ttu-id="41e2f-124">位置情報を検索 `HTML file` するを作成するには、アクションに従って完了します。</span><span class="sxs-lookup"><span data-stu-id="41e2f-124">To create an `HTML file` to find your geolocation, complete following the actions.</span></span>  

1.  <span data-ttu-id="41e2f-125">\(Visual Studio Code IDE\) を開きます。</span><span class="sxs-lookup"><span data-stu-id="41e2f-125">Open Visual Studio Code \(or an IDE of your choice\).</span></span>  
1.  <span data-ttu-id="41e2f-126">新しいファイルを `.html` 作成します。</span><span class="sxs-lookup"><span data-stu-id="41e2f-126">Create a new `.html` file.</span></span>  
1.  <span data-ttu-id="41e2f-127">次のコード スニペットを新しいファイルにコピーして貼り付 `.html` けます。</span><span class="sxs-lookup"><span data-stu-id="41e2f-127">Copy and paste the following code snippet in your new `.html` file.</span></span>  
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <title>Geolocation Finder</title>
    </head>
    <body>
        <button id="display">Display Location</button>
        <div id="message"></div>
    </body>
    
    <script>
        const btn = document.getElementById('display');
        // Find the user location.
        btn.addEventListener('click', function () {
            navigator.geolocation.getCurrentPosition(onSuccess, onError);
        });
        
        // Update message to display the latitude and longitude coordinates.
        function onSuccess(position) {
            const {latitude, longitude} = position.coords;
            message.textContent = `Your location: (${latitude},${longitude})`;
        }
        
        function onError() {
            message.textContent = `Operation Failed`;
        }
    </script>
    </html>
    ```  
    
1.  <span data-ttu-id="41e2f-128">ファイル名を `.html` 使用してファイルを保存します `geolocation.html` 。</span><span class="sxs-lookup"><span data-stu-id="41e2f-128">Save the `.html` file with the filename `geolocation.html`.</span></span>  
1.  <span data-ttu-id="41e2f-129">Microsoft Edge を開きます。</span><span class="sxs-lookup"><span data-stu-id="41e2f-129">Open Microsoft Edge.</span></span>  
1.  <span data-ttu-id="41e2f-130">`geolocation.html` ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="41e2f-130">Open the `geolocation.html` file.</span></span>  
1.  <span data-ttu-id="41e2f-131">緯度と経度の座標を表示するには、[表示場所] **ボタンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="41e2f-131">To display your latitude and longitude coordinates, choose the **Display Location** button.</span></span>  <span data-ttu-id="41e2f-132">位置情報を確認して比較するには、座標をコピーして貼り付けます [https://www.bing.com/maps][BingMaps] 。</span><span class="sxs-lookup"><span data-stu-id="41e2f-132">To verify and compare your geolocation, copy and paste your coordinates in [https://www.bing.com/maps][BingMaps].</span></span>  
    
    :::image type="complex" source="./media/geolocater-browser.png" alt-text="ユーザーの位置情報座標を表示するMicrosoft Edge" lightbox="./media/geolocater-browser.png":::
       <span data-ttu-id="41e2f-134">ユーザーの位置情報座標を表示するMicrosoft Edge</span><span class="sxs-lookup"><span data-stu-id="41e2f-134">Display the geolocation coordinates of the user in Microsoft Edge</span></span>  
    :::image-end:::  
    
## <a name="step-2-display-geolocationhtml-in-a-webview2"></a><span data-ttu-id="41e2f-135">手順 2: WebView2 geolocation.html を表示する</span><span class="sxs-lookup"><span data-stu-id="41e2f-135">Step 2: Display geolocation.html in a WebView2</span></span>  

1.  <span data-ttu-id="41e2f-136">WebView2 アプリを作成するには、次の開始ガイドまたは WebView2 サンプルのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="41e2f-136">To create a WebView2 app, use either of the following get started guides or WebView2 samples.</span></span>  
    *   [<span data-ttu-id="41e2f-137">はじめにフォームで WebView2 を使用Windowsする</span><span class="sxs-lookup"><span data-stu-id="41e2f-137">Get Started with WebView2 in Windows Forms</span></span>][Webview2GetStartedWinforms]  
    *   [<span data-ttu-id="41e2f-138">はじめにWPF での WebView2 の使用</span><span class="sxs-lookup"><span data-stu-id="41e2f-138">Get Started with WebView2 in WPF</span></span>][Webview2GetStartedWpf]  
    *   [<span data-ttu-id="41e2f-139">WebView2 サンプル</span><span class="sxs-lookup"><span data-stu-id="41e2f-139">WebView2 samples</span></span>][GithubMicrosoftedgeWebview2samples]  
        
1.  <span data-ttu-id="41e2f-140">WebView2 コントロールの初期ナビゲーションをに設定します `geolocation.html` 。</span><span class="sxs-lookup"><span data-stu-id="41e2f-140">Set the initial navigation of the WebView2 control to `geolocation.html`.</span></span>  
    
    ```csharp
    webView.CoreWebView2.Navigate(@"C:\{path\to\file}\geolocation.html");
    ```  
    
1.  <span data-ttu-id="41e2f-141">ファイルが `geolocation.html` WebView2 コントロール アプリに表示されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="41e2f-141">Ensure the `geolocation.html` file displays in your WebView2 control app.</span></span>  
    
    :::image type="complex" source="./media/initial-geolocate.png" alt-text="WebView2 コントロール geolocater.html ファイルを表示する" lightbox="./media/initial-geolocate.png":::
       <span data-ttu-id="41e2f-143">`geolocation.html`WebView2 コントロール アプリにファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="41e2f-143">Display the `geolocation.html` file in your WebView2 control app</span></span>  
    :::image-end:::  
    
## <a name="step-3-install-the-devtoolsprotocolhelper-nuget-package"></a><span data-ttu-id="41e2f-144">手順 3: DevToolsProtocolHelper パッケージをインストールNuGetする</span><span class="sxs-lookup"><span data-stu-id="41e2f-144">Step 3: Install the DevToolsProtocolHelper NuGet package</span></span>  

<span data-ttu-id="41e2f-145">ダウンロードNuGetを使用します `Microsoft.Web.WebView2.DevToolsProtocolExtension` 。</span><span class="sxs-lookup"><span data-stu-id="41e2f-145">Use NuGet to download `Microsoft.Web.WebView2.DevToolsProtocolExtension`.</span></span>  <span data-ttu-id="41e2f-146">パッケージをインストールするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="41e2f-146">To install the package, complete the following actions.</span></span>  

1.  <span data-ttu-id="41e2f-147">[パッケージ**Project**  >  **参照NuGet管理する] を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="41e2f-147">Choose **Project** > **Manage NuGet Packages** > **Browse**.</span></span>  
1.  <span data-ttu-id="41e2f-148">`Microsoft.Web.WebView2.DevToolsProtocolExtension` **Microsoft.Web.WebView2.DevToolsProtocolExtension Install を入力して選択**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="41e2f-148">Type `Microsoft.Web.WebView2.DevToolsProtocolExtension` and choose **Microsoft.Web.WebView2.DevToolsProtocolExtension** > **Install**.</span></span>   
    
:::image type="complex" source="./media/cdp-nuget.png" alt-text="Microsoft.Web.WebView2.DevToolsProtocolExtension がページに表示Visual Studio NuGet パッケージ マネージャー" lightbox="./media/cdp-nuget.png":::
   <span data-ttu-id="41e2f-150">**Microsoft.Web.WebView2.DevToolsProtocolExtension**がページに表示Visual Studio NuGet パッケージ マネージャー</span><span class="sxs-lookup"><span data-stu-id="41e2f-150">Ensure **Microsoft.Web.WebView2.DevToolsProtocolExtension** displays in the Visual Studio NuGet Package Manager</span></span>  
:::image-end:::    

## <a name="step-4-use-devtools-protocol-helper"></a><span data-ttu-id="41e2f-151">手順 4: DevTools プロトコル ヘルパーを使用する</span><span class="sxs-lookup"><span data-stu-id="41e2f-151">Step 4: Use DevTools Protocol Helper</span></span>  

1.  <span data-ttu-id="41e2f-152">名前空間を `DevToolsProtocolExtension` プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="41e2f-152">Add the `DevToolsProtocolExtension` namespace to your project.</span></span>  
    
    ```csharp
    using Microsoft.Web.WebView2.Core;
    using Microsoft.Web.WebView2.Core.DevToolsProtocolExtension;
    ```  
    
1.  <span data-ttu-id="41e2f-153">オブジェクトをインスタンス `DevToolsProtocolHelper` 化し、に移動します `geolocation.html` 。</span><span class="sxs-lookup"><span data-stu-id="41e2f-153">Instantiate the `DevToolsProtocolHelper` object and navigate to `geolocation.html`.</span></span>  
    
    ```csharp
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
        DevToolsProtocolHelper helper = webView.CoreWebView2.GetDevToolsProtocolHelper(); 
        
        webView.CoreWebView2.Navigate(@"C:\{path\to\file}\geolocation.html");
    }
    ```  
    
1.  <span data-ttu-id="41e2f-154">[setGeoLocationOverrideAsync メソッドを実行][GithubChromedevtoolsDevtoolsProtocolTotEmulationMethodSetgeolocationoverride]します。</span><span class="sxs-lookup"><span data-stu-id="41e2f-154">Run the [setGeoLocationOverrideAsync][GithubChromedevtoolsDevtoolsProtocolTotEmulationMethodSetgeolocationoverride] method.</span></span>  <span data-ttu-id="41e2f-155">詳細については [、setGeolocationOverride に移動します][GithubChromedevtoolsDevtoolsProtocolTotEmulationMethodSetgeolocationoverride]。</span><span class="sxs-lookup"><span data-stu-id="41e2f-155">For more information, navigate to [setGeolocationOverride][GithubChromedevtoolsDevtoolsProtocolTotEmulationMethodSetgeolocationoverride].</span></span>  
    
    ```csharp
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
        DevToolsProtocolHelper helper = webview.CoreWebView2.GetDevToolsProtocolHelper();
        
        webView.CoreWebView2.Navigate(@"C:\{path\to\file}\geolocation.html");
        
        // Latitude and longitude for Paris, France.
        double latitude = 48.857024082572565;  
        double longitude = 2.3161581601457386;  
        double accuracy = 1;
        await helper.Emulation.setGeolocationOverrideAsync(latitude, longitude, accuracy);
        
    }
    ```  
    
1.  <span data-ttu-id="41e2f-156">アプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="41e2f-156">Run your app.</span></span>  
1.  <span data-ttu-id="41e2f-157">パリ、フランスの座標を表示するには、[表示場所] **ボタンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="41e2f-157">To display the coordinates of Paris, France, choose the **Display Location** button.</span></span>  
    
    :::image type="complex" source="./media/final-location-cdp.png" alt-text="パリの座標.html WebView2 コントロールにファイルを表示する" lightbox="./media/final-location-cdp.png":::
       <span data-ttu-id="41e2f-159">パリの `.html` 座標を使用して WebView2 コントロールにファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="41e2f-159">Display the `.html` file in a WebView2 control with the coordinates for Paris</span></span>  
    :::image-end:::  
    
## <a name="file-a-chromium-devtools-protocol-bug"></a><span data-ttu-id="41e2f-160">DevTools Chromiumのバグをファイルする</span><span class="sxs-lookup"><span data-stu-id="41e2f-160">File a Chromium DevTools Protocol bug</span></span>  

<span data-ttu-id="41e2f-161">WebView2 チームは、DevTools プロトコルChromium所有しています。</span><span class="sxs-lookup"><span data-stu-id="41e2f-161">The WebView2 team doesn't own the Chromium DevTools Protocol.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="41e2f-162">フィードバックとバグを問題Chromiumに直接送信します。</span><span class="sxs-lookup"><span data-stu-id="41e2f-162">Direct feedback and bugs to the Chromium Issues repo.</span></span>  

<span data-ttu-id="41e2f-163">DevTools プロトコルのChromiumまたは問題をファイルするには、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="41e2f-163">To file a Chromium DevTools Protocol bug or issue, complete the following actions.</span></span>  

1.  <span data-ttu-id="41e2f-164">バグ レポート [をファイルします][ChromiumBugsChromiumIssuesEntryComponentsPlatformDevtoolsPlatform]。</span><span class="sxs-lookup"><span data-stu-id="41e2f-164">File a [bug report][ChromiumBugsChromiumIssuesEntryComponentsPlatformDevtoolsPlatform].</span></span>  
1.  <span data-ttu-id="41e2f-165">[[WebView フィードバック] に移動し][GithubMicrosoftedgeWebview2feedback]、新しい問題を開きます。</span><span class="sxs-lookup"><span data-stu-id="41e2f-165">Navigate to [WebView Feedback][GithubMicrosoftedgeWebview2feedback] and open a new issue.</span></span>  
    
## <a name="see-also"></a><span data-ttu-id="41e2f-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="41e2f-166">See also</span></span>  

*   [<span data-ttu-id="41e2f-167">WebView2 サンプル</span><span class="sxs-lookup"><span data-stu-id="41e2f-167">WebView2 samples</span></span>][GithubMicrosoftedgeWebview2samples]  
    
 <!-- links -->  

[Webview2GetStartedWinforms]: /microsoft-edge/webview2/get-started/winforms "WebView2 の使用を開始するには、Windowsフォーム|Microsoft Docs"  
[Webview2GetStartedWpf]: /microsoft-edge/webview2/get-started/wpf "WPF サーバーでの WebView2 の|Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2CoreCorewebview2GetdevtoolsprotocoleventreceiverViewWebview2Dotnet1077444]: /dotnet/api/microsoft.web.webview2.core.corewebview2.getdevtoolsprotocoleventreceiver?view=webview2-dotnet-1.0.774.44&preserve-view=true "CoreWebView2.GetDevToolsProtocolEventReceiver(String) メソッドの|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2CalldevtoolsprotocolmethodasyncViewWebview2Dotnet1077444MicrosoftWebWebView2CoreCorewebview2CalldevtoolsprotocolmethodsyncSystemStringSystemString]: /dotnet/api/microsoft.web.webview2.core.corewebview2.calldevtoolsprotocolmethodasync?view=webview2-dotnet-1.0.774.44&preserve-view=true#Microsoft_Web_WebView2_Core_CoreWebView2_CallDevToolsProtocolMethodAsync_System_String_System_String_ "CoreWebView2.CallDevToolsProtocolMethodAsync(String, String) メソッドの|Microsoft Docs"  

[Webview2ReferenceWin32Icorewebview2ViewWebview21077444Calldevtoolsprotocolmethod]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-1.0.774.44&preserve-view=true#calldevtoolsprotocolmethod "CallDevToolsProtocolMethod - インターフェイス ICoreWebView2 |Microsoft Docs"  
[Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview21077444]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-1.0.774.44&preserve-view=true "インターフェイス ICoreWebView2DevToolsProtocolEventReceiver |Microsoft Docs"  

[BingMaps]: https://www.bing.com/maps "Bing地図"  

[GitHubChromedevtoolsDevtoolsProtocol]: https://chromedevtools.github.io/devtools-protocol "Chrome DevTools プロトコル |GitHub"  
[GithubChromedevtoolsDevtoolsProtocolTotEmulationMethodSetgeolocationoverride]: https://chromedevtools.github.io/devtools-protocol/tot/Emulation/#method-setGeolocationOverride "エミュレーション.setGeolocationOverride - Chrome DevTools プロトコル |GitHub"  

[GithubMicrosoftedgeWebview2feedback]: https://github.com/MicrosoftEdge/WebView2Feedback "WebView フィードバック |GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 のサンプル |GitHub"  

[ChromiumBugsChromiumIssuesEntryComponentsPlatformDevtoolsPlatform]: https://bugs.chromium.org/p/chromium/issues/entry?components=Platform%3EDevTools%3EPlatform "バグ レポート|Chromiumバグ"  

[NugetPackagesMicrosoftWebWebView2DevToolsprotocolextension]: https://www.nuget.org/packages/Microsoft.Web.WebView2.DevToolsProtocolExtension "Microsoft.Web.WebView2.DevToolsProtocolExtension |NuGetQA ギャラリー"  
