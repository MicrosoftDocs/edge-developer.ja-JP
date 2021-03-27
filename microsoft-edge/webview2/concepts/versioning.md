---
description: Microsoft Edge WebView2 で使用されるバージョン モデル
title: WebView2 SDK バージョンの概要
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/17/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、edge html
ms.openlocfilehash: b292f59e264293a958eb619d04b751203cb517ac
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461179"
---
# <a name="understand-webview2-sdk-versions"></a><span data-ttu-id="44eea-104">WebView2 SDK バージョンの概要</span><span class="sxs-lookup"><span data-stu-id="44eea-104">Understand WebView2 SDK versions</span></span>  

<span data-ttu-id="44eea-105">WebView2 SDK の新しいバージョンは、Microsoft Edge \(Chromium\) ブラウザーと同じ一般的なケイデンスで出荷されます。これは約 6 週間ごとに行います。</span><span class="sxs-lookup"><span data-stu-id="44eea-105">New versions of the WebView2 SDK are shipped at the same general cadence as the Microsoft Edge \(Chromium\) browser, which is approximately every six weeks.</span></span>  

## <a name="release-and-prerelease-package"></a><span data-ttu-id="44eea-106">リリースおよびプレリリース パッケージ</span><span class="sxs-lookup"><span data-stu-id="44eea-106">Release and prerelease package</span></span>  

<span data-ttu-id="44eea-107">WebView2 NuGet パッケージには、リリース パッケージとプレリリース パッケージの両方が含まれています。</span><span class="sxs-lookup"><span data-stu-id="44eea-107">The WebView2 NuGet package contains both a release and pre-release package.</span></span>  

<span data-ttu-id="44eea-108">リリース **パッケージは前方** 互換性があり、次のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="44eea-108">The **release package** is forward compatible and contains the following components.</span></span>  

*   [<span data-ttu-id="44eea-109">Win32 C/C++ API</span><span class="sxs-lookup"><span data-stu-id="44eea-109">Win32 C/C++ APIs</span></span>][ReferenceWin32]
*   <span data-ttu-id="44eea-110">.NET API:  [WPF][DotnetMicrosoftWebWebview2WpfNamespace] [、WinForms、][DotnetMicrosoftWebWebview2WinformsNamespace]および [Core][DotnetMicrosoftWebWebview2CoreNamespace]。</span><span class="sxs-lookup"><span data-stu-id="44eea-110">.NET APIs:  [WPF][DotnetMicrosoftWebWebview2WpfNamespace], [WinForms][DotnetMicrosoftWebWebview2WinformsNamespace], and [Core][DotnetMicrosoftWebWebview2CoreNamespace].</span></span>  
    
<span data-ttu-id="44eea-111">SDK の API は完全にサポートされています。</span><span class="sxs-lookup"><span data-stu-id="44eea-111">APIs in the SDK are fully supported.</span></span>  

<span data-ttu-id="44eea-112">プレ **リリース パッケージは、** 実験的 API を使用したリリース パッケージ [のスーパーセットです](#experimental-apis)。</span><span class="sxs-lookup"><span data-stu-id="44eea-112">The **prerelease package** is a superset of the release package with [Experimental APIs](#experimental-apis).</span></span>  <span data-ttu-id="44eea-113">プレリリース SDK を使用して実稼働アプリをビルドしないようにします。</span><span class="sxs-lookup"><span data-stu-id="44eea-113">Avoid using the prerelease SDK to build production apps.</span></span>  

### <a name="roadmap"></a><span data-ttu-id="44eea-114">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="44eea-114">Roadmap</span></span>  

<span data-ttu-id="44eea-115">リリース パッケージには、サポートされている安定した Win32 C/C++ および .NET API すべてが含まれています。</span><span class="sxs-lookup"><span data-stu-id="44eea-115">The release package contains all of the stable, supported Win32 C/C++ and .NET APIs.</span></span>  <span data-ttu-id="44eea-116">prerelease パッケージには、フィードバックに基づいて変更される可能性がある実験的な API が含まれています。</span><span class="sxs-lookup"><span data-stu-id="44eea-116">The prerelease package contains experimental APIs that are subject to change based on your feedback.</span></span>  

## <a name="experimental-apis"></a><span data-ttu-id="44eea-117">試験的な API</span><span class="sxs-lookup"><span data-stu-id="44eea-117">Experimental APIs</span></span>  

<span data-ttu-id="44eea-118">WebView チームは、将来のリリースに含まれる可能性がある実験的な API に関するフィードバックを求めている。</span><span class="sxs-lookup"><span data-stu-id="44eea-118">The WebView team is seeking feedback on experimental APIs that may be included in future releases.</span></span>  <span data-ttu-id="44eea-119">実験的な API は SDK のように `experimental` マークされます。</span><span class="sxs-lookup"><span data-stu-id="44eea-119">The experimental APIs are marked as `experimental` in the SDK.</span></span>  <span data-ttu-id="44eea-120">実験 API を評価し、フィードバックを共有するには [、WebView フィードバック repo に移動します][GithubMicrosoftedgeWebviewfeedback]。</span><span class="sxs-lookup"><span data-stu-id="44eea-120">To help you evaluate the Experimental APIs and share your feedback, navigate to the [WebView feedback repo][GithubMicrosoftedgeWebviewfeedback].</span></span>  

> [!CAUTION]
> <span data-ttu-id="44eea-121">実験 API は、SDK から SDK に導入、変更、および削除される場合があります。</span><span class="sxs-lookup"><span data-stu-id="44eea-121">Experimental APIs may be introduced, modified, and removed from SDK to SDK.</span></span>  <span data-ttu-id="44eea-122">実稼働アプリで実験的な API を使用しないようにします。</span><span class="sxs-lookup"><span data-stu-id="44eea-122">Avoid using the experimental APIs in production apps.</span></span>  

> [!NOTE]
> <span data-ttu-id="44eea-123">実験的な API は、インストールされているバージョンの WebView2 ランタイムでは使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="44eea-123">Experimental APIs may not be available in your installed version of the WebView2 Runtime.</span></span>  

## <a name="matching-webview2-runtime-versions"></a><span data-ttu-id="44eea-124">一致する WebView2 ランタイム バージョン</span><span class="sxs-lookup"><span data-stu-id="44eea-124">Matching WebView2 Runtime versions</span></span>  
<span data-ttu-id="44eea-125">WebView2 アプリでは、ユーザーが [WebView2 ランタイムをインストールする必要があります][MicrosoftDeveloperEdgeWebview2]。</span><span class="sxs-lookup"><span data-stu-id="44eea-125">WebView2 apps require users to install a [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2].</span></span>  <span data-ttu-id="44eea-126">WebView2 ランタイムは、利用可能な最新バージョンに自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="44eea-126">The WebView2 Runtime automatically updates to the latest version available.</span></span>  <span data-ttu-id="44eea-127">一部のシナリオでは、ユーザーが WebView2 ランタイムの自動更新を停止する必要が生じ、アプリの互換性の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="44eea-127">In some scenarios, users may want to stop automatic WebView2 Runtime updates, which may cause app compatibility issues.</span></span>  

<span data-ttu-id="44eea-128">WebView2 ランタイム更新プログラムが停止している場合は、アプリに必要な [WebView2 ランタイム][MicrosoftDeveloperEdgeWebview2] の最小バージョンを理解してください。</span><span class="sxs-lookup"><span data-stu-id="44eea-128">If WebView2 Runtime updates are stopped, ensure you understand the minimum version of the [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2] required by your app.</span></span>  <span data-ttu-id="44eea-129">次の 2 つの項目を検討してください。</span><span class="sxs-lookup"><span data-stu-id="44eea-129">Consider the following two items:</span></span>  

1.  <span data-ttu-id="44eea-130">Webview2 インスタンスを正常に読み込むのに必要な最小バージョンの SDK は、読[][Webview2Releasenotes]み込む最小 Microsoft Edge バージョンの WebView2 リリース ノート**にあります**。</span><span class="sxs-lookup"><span data-stu-id="44eea-130">The minimum required version of the SDK in order to successfully load a webview2 instance is found in the WebView2 [Release Notes][Webview2Releasenotes] under **Minimum Microsoft Edge version to load**.</span></span>  <span data-ttu-id="44eea-131">SDK で必要な読み込み最小バージョンは、Web プラットフォームで変更が発生した場合にのみ変更されます。</span><span class="sxs-lookup"><span data-stu-id="44eea-131">The minimum version to load required by the SDK only changes when a breaking change occurs in the web platform.</span></span>  <span data-ttu-id="44eea-132">たとえば、SDK バージョン [1.0.622.22][Webview2Releasenotes1062222]の場合、ビルド番号が 1 つ以上の [WebView2 ランタイム][MicrosoftDeveloperEdgeWebview2] または安定しない [Microsoft Edge][MicrosoftedgeinsiderDownload] チャネルをインストール `86.0.616.0` する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44eea-132">For example, for SDK version [1.0.622.22][Webview2Releasenotes1062222], you must install either the [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2] or a [non-stable Microsoft Edge channel][MicrosoftedgeinsiderDownload] with a build number of `86.0.616.0` or newer.</span></span>   
1.  <span data-ttu-id="44eea-133">アプリ内のインターフェイスと API をサポートするために必要な NuGet パッケージの最小必要バージョンは、WebView2[][Webview2Releasenotes]リリース ノートの「完全な API の互換性」の下に**示されています**。</span><span class="sxs-lookup"><span data-stu-id="44eea-133">The minimum required version of the NuGet package required to support the interfaces and APIs in your app is found in the WebView2 [Release Notes][Webview2Releasenotes] under **Full API Compatibility**.</span></span>  <span data-ttu-id="44eea-134">新しいインターフェイスと API は WebView2 に定期的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="44eea-134">New interfaces and APIs are added periodically to WebView2.</span></span>  <span data-ttu-id="44eea-135">SDK にバンドルされている API とインターフェイスでは、API とインターフェイスが SDK に異なる時間に追加されるので、WebView2 ランタイムのバージョンが異なっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="44eea-135">APIs and interfaces bundled in an SDK require different versions of the WebView2 Runtime, because APIs and interface are added to the SDK at different times.</span></span>  <span data-ttu-id="44eea-136">必要な WebView2 ランタイム バージョンは、API が最初に導入された SDK バージョンのビルド番号 (3 番目の番号) と一致します。</span><span class="sxs-lookup"><span data-stu-id="44eea-136">The required WebView2 Runtime version matches the build number, the third number, of the SDK version the API was first introduced in.</span></span>  <span data-ttu-id="44eea-137">たとえば、SDK バージョン [1.0.622.22][Webview2Releasenotes1062222] で追加された新しい API またはインターフェイスには、WebView2 ランタイム バージョン以降が `86.0.622.0` 必要です。</span><span class="sxs-lookup"><span data-stu-id="44eea-137">For example, a new API or interface added in SDK version [1.0.622.22][Webview2Releasenotes1062222] requires the WebView2 Runtime version `86.0.622.0` or newer.</span></span>  <span data-ttu-id="44eea-138">後の SDK リリースで追加された API またはインターフェイスには、SDK と同じバージョン番号を持つ WebView2 ランタイムが必要です。</span><span class="sxs-lookup"><span data-stu-id="44eea-138">An API or interface added in a later SDK release requires a WebView2 Runtime that has the same version number as the SDK.</span></span>  <span data-ttu-id="44eea-139">WebView2 ランタイム バージョンがインターフェイスまたは API をサポートしているかどうかを判断するには [、[WebView2](#determine-webview2-runtime-requirement)ランタイム要件の決定] に移動します。</span><span class="sxs-lookup"><span data-stu-id="44eea-139">To help you determine if the WebView2 Runtime version supports an interface or API, navigate to [Determine WebView2 Runtime requirement](#determine-webview2-runtime-requirement).</span></span>  
    
> [!IMPORTANT]
> <span data-ttu-id="44eea-140">[Evergreen WebView2][Webview2ConceptsDistributionEvergreenDistributionMode]アプリを開発する場合は、WebView2 ランタイムと安定しない Microsoft Edge チャネルの最新バージョンに対してアプリを定期的にテストします。</span><span class="sxs-lookup"><span data-stu-id="44eea-140">When developing [Evergreen WebView2 apps][Webview2ConceptsDistributionEvergreenDistributionMode], regularly test your app against the latest versions of the WebView2 Runtime and non-stable Microsoft Edge channels.</span></span>  <span data-ttu-id="44eea-141">Web プラットフォームは常に進化し続けるので、アプリが意図した通り動作することを確認するには、定期的なテストが最適な方法です。</span><span class="sxs-lookup"><span data-stu-id="44eea-141">Because the web platform is constantly evolving, regular testing is the best way to ensure your app performs as intended.</span></span>  

### <a name="determine-webview2-runtime-requirement"></a><span data-ttu-id="44eea-142">WebView2 ランタイム要件の決定</span><span class="sxs-lookup"><span data-stu-id="44eea-142">Determine WebView2 Runtime requirement</span></span>  

<span data-ttu-id="44eea-143">使用する SDK に応じて、次の項目を検討してください。</span><span class="sxs-lookup"><span data-stu-id="44eea-143">Depending on which SDK you use, consider the following items:</span></span>  

*   <span data-ttu-id="44eea-144">**Win32 C/C++**。</span><span class="sxs-lookup"><span data-stu-id="44eea-144">**Win32 C/C++**.</span></span>  <span data-ttu-id="44eea-145">新しいインターフェイス `QueryInterface` を取得するために使用する場合は、 の戻り値を確認します `E_NOINTERFACE` 。</span><span class="sxs-lookup"><span data-stu-id="44eea-145">When using `QueryInterface` to obtain a new interface, verify a return value of `E_NOINTERFACE`.</span></span>  <span data-ttu-id="44eea-146">この値は、WebView2 ランタイムが以前のバージョンであり、そのインターフェイスをサポートしない場合があります。</span><span class="sxs-lookup"><span data-stu-id="44eea-146">The value may indicate that the WebView2 Runtime is a previous version, and doesn't support that interface.</span></span>  <span data-ttu-id="44eea-147">動作の例については [、Line 622 - AppWindow.cpp に移動します][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisampleAppwindowCppL622]。</span><span class="sxs-lookup"><span data-stu-id="44eea-147">For an example of how it works, navigate to [Line 622 - AppWindow.cpp][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisampleAppwindowCppL622].</span></span>  
*   <span data-ttu-id="44eea-148">**.NET と WinUI**。</span><span class="sxs-lookup"><span data-stu-id="44eea-148">**.NET and WinUI**.</span></span>  <span data-ttu-id="44eea-149">より新しい SDK に追加されたメソッド、プロパティ、およびイベントを使用する場合は、 `No such interface supported` 例外を確認します。</span><span class="sxs-lookup"><span data-stu-id="44eea-149">Check for a `No such interface supported` exception when using methods, properties, and events that were added to more recent SDKs.</span></span>  <span data-ttu-id="44eea-150">この例外は、WebView2 ランタイムが以前のバージョンであり、API をサポートしていない場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="44eea-150">The exception may occur when the WebView2 Runtime is a previous version, and does not support the APIs.</span></span>  
    
<span data-ttu-id="44eea-151">API が使用できない場合は、関連付けられた機能の削除を検討するか、WebView2 ランタイムの更新が必要です。</span><span class="sxs-lookup"><span data-stu-id="44eea-151">If an API is unavailable, consider removing the associated feature, or inform your users that an update to the WebView2 Runtime is required.</span></span>  

<!--
## Versioning  

After you have used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.  Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that prevent your SDK from working with different versions of installed browser binaries.  After version 1.0.0.0, different versions of the SDK may work with different versions of the installed browser by using the following best practices.  

1.  To account for breaking changes to the API be sure to check for failure when requesting the DLL export `CreateCoreWebView2Environment` and when running `QueryInterface` on any `CoreWebView2` object.  A return value of `E_NOINTERFACE` indicates that the SDK is not compatible with the Microsoft Edge browser binaries.  
1.  Checking for failure from `QueryInterface` also accounts for cases where the SDK is newer than the version of the Microsoft Edge browser and your app attempts to use an interface of which the Microsoft Edge browser is unaware.  
1.  When an interface is unavailable, you may consider disabling the associated feature if possible, or otherwise informing your users to update their browsers.  
    -->  

<!--links -->  

[Webview2ConceptsDistributionEvergreenDistributionMode]: ./distribution.md#evergreen-distribution-mode "Evergreen 配布モード - WebView2 アプリケーションを使用したアプリの|Microsoft Docs"  
[Webview2Releasenotes]: ../releasenotes.md "WebView2 SDK のリリース ノート|Microsoft Docs"  
[Webview2Releasenotes1062222]: ../releasenotes.md#1062222 "1.0.622.22 - WebView2 SDK のリリース |Microsoft Docs"   

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge チャネルの概要 | Microsoft Docs"  

[DotnetMicrosoftWebWebview2CoreNamespace]: /dotnet/api/microsoft.web.webview2.core "Microsoft.Web.WebView2.Core 名前空間|Microsoft Docs"  
[DotnetMicrosoftWebWebview2WpfNamespace]: /dotnet/api/microsoft.web.webview2.wpf "Microsoft.Web.WebView2.Wpf 名前空間 | Microsoft Docs"  
[DotnetMicrosoftWebWebview2WinformsNamespace]: /dotnet/api/microsoft.web.webview2.winforms "Microsoft.Web.WebView2.WinForms 名前空間|Microsoft Docs"  
[ReferenceWin32]: /microsoft-edge/webview2/reference/win32 "WebView2 Win32 C++ リファレンス |Microsoft Docs"  

[MicrosoftDeveloperEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2/ "Microsoft Edge WebView2 |Microsoft 開発者"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック - MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisampleAppwindowCppL622]: https://github.com/MicrosoftEdge/WebView2Samples/blob/8ec7de9d3e80a942bc7025cffad98eee75e11e64/SampleApps/WebView2APISample/AppWindow.cpp#L622 "Line 622 - AppWindow.cpp - MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider Channels をダウンロードする"  
