---
description: Microsoft Edge WebView2 で使用されるバージョン管理モデル
title: Microsoft Edge WebView2 のバージョン管理
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/25/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 54d62de00a89a3c433fd77e9ec20945adbfc19c3
ms.sourcegitcommit: 2e14ff82350f700d7eabc8d33b3ec3e5fc8c61fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "11191611"
---
# <span data-ttu-id="0e711-104">WebView2 SDK のバージョンについて</span><span class="sxs-lookup"><span data-stu-id="0e711-104">Understand WebView2 SDK versions</span></span>  

<span data-ttu-id="0e711-105">WebView2 SDK の新しいバージョンは、Microsoft Edge \ (Chromium \) ブラウザーと同じ一般的なリズムで出荷されています。これは、約6週間です。</span><span class="sxs-lookup"><span data-stu-id="0e711-105">New versions of the WebView2 SDK are shipped at the same general cadence as the Microsoft Edge \(Chromium\) browser, which is approximately every six weeks.</span></span>  

## <span data-ttu-id="0e711-106">Release パッケージとプレリリースパッケージ</span><span class="sxs-lookup"><span data-stu-id="0e711-106">Release and prerelease package</span></span>  

<span data-ttu-id="0e711-107">WebView2 NuGet パッケージには、リリースとプレリリースの両方のパッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e711-107">The WebView2 NuGet package contains both a release and pre-release package.</span></span>  

<span data-ttu-id="0e711-108">**リリースパッケージ**には上位互換性があり、次のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e711-108">The **release package** is forward compatible and contains the following components.</span></span>  

*   [<span data-ttu-id="0e711-109">Win32 C/c + + Api</span><span class="sxs-lookup"><span data-stu-id="0e711-109">Win32 C/C++ APIs</span></span>][ReferenceWin32]
*   <span data-ttu-id="0e711-110">.NET Api:  [WPF][DotnetMicrosoftWebWebview2WpfNamespace]、 [WinForms][DotnetMicrosoftWebWebview2WinformsNamespace]、および [Core][DotnetMicrosoftWebWebview2CoreNamespace]。</span><span class="sxs-lookup"><span data-stu-id="0e711-110">.NET APIs:  [WPF][DotnetMicrosoftWebWebview2WpfNamespace], [WinForms][DotnetMicrosoftWebWebview2WinformsNamespace], and [Core][DotnetMicrosoftWebWebview2CoreNamespace].</span></span>  
    
<span data-ttu-id="0e711-111">SDK の Api は完全にサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0e711-111">APIs in the SDK are fully supported.</span></span>  

<span data-ttu-id="0e711-112">**プレリリースパッケージ**は、[実験的 api](#experimental-apis)を使用したリリースパッケージのスーパーセットです。</span><span class="sxs-lookup"><span data-stu-id="0e711-112">The **prerelease package** is a superset of the release package with [Experimental APIs](#experimental-apis).</span></span>  

### <span data-ttu-id="0e711-113">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="0e711-113">Roadmap</span></span>  

<span data-ttu-id="0e711-114">リリースパッケージには、サポートされているすべての安定した Win32 C/c + + .NET Api が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e711-114">The release package contains all of the stable, supported Win32 C/C++ and .NET APIs.</span></span>  <span data-ttu-id="0e711-115">プレリリースパッケージには、フィードバックに基づいて変更される可能性がある実験的な Api が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e711-115">The prerelease package contains experimental APIs that are subject to change based on your feedback.</span></span>  

## <span data-ttu-id="0e711-116">試験的な API</span><span class="sxs-lookup"><span data-stu-id="0e711-116">Experimental APIs</span></span>  

<span data-ttu-id="0e711-117">WebView チームは、今後のリリースに含まれる可能性がある実験的な Api についてのフィードバックを求めています。</span><span class="sxs-lookup"><span data-stu-id="0e711-117">The WebView team is seeking feedback on experimental APIs that may be included in future releases.</span></span>  <span data-ttu-id="0e711-118">実験的な Api は、SDK で示されてい `experimental` ます。</span><span class="sxs-lookup"><span data-stu-id="0e711-118">The experimental APIs are marked as `experimental` in the SDK.</span></span>  <span data-ttu-id="0e711-119">実験的な Api を評価してフィードバックを共有できるように、 [WebView フィードバックリポジトリ][GithubMicrosoftedgeWebviewfeedback]に移動します。</span><span class="sxs-lookup"><span data-stu-id="0e711-119">To help you evaluate the Experimental APIs and share your feedback, navigate to the [WebView feedback repo][GithubMicrosoftedgeWebviewfeedback].</span></span>  

> [!CAUTION]
> <span data-ttu-id="0e711-120">実験的な Api は、SDK から SDK に導入、変更、削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0e711-120">Experimental APIs may be introduced, modified, and removed from SDK to SDK.</span></span>  <span data-ttu-id="0e711-121">プロダクションアプリで実験的な Api を使うことは避けてください。</span><span class="sxs-lookup"><span data-stu-id="0e711-121">Avoid using the experimental APIs in production apps.</span></span>  

> [!NOTE]
> <span data-ttu-id="0e711-122">実験的な Api は、インストールされているバージョンの WebView2 Runtime では使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0e711-122">Experimental APIs may not be available in your installed version of the WebView2 Runtime.</span></span>  

## <span data-ttu-id="0e711-123">WebView2 のランタイムバージョンの一致</span><span class="sxs-lookup"><span data-stu-id="0e711-123">Matching WebView2 Runtime versions</span></span>  
<span data-ttu-id="0e711-124">WebView2 アプリでは、ユーザーが [WebView2 ランタイム][MicrosoftDeveloperEdgeWebview2]をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e711-124">WebView2 apps require users to install a [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2].</span></span>  <span data-ttu-id="0e711-125">WebView2 ランタイムは、利用可能な最新バージョンに自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="0e711-125">The WebView2 Runtime automatically updates to the latest version available.</span></span>  <span data-ttu-id="0e711-126">一部のシナリオでは、ユーザーが自動 WebView2 ランタイム更新を停止する必要があります。これにより、アプリの互換性の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0e711-126">In some scenarios, users may want to stop automatic WebView2 Runtime updates, which may cause app compatibility issues.</span></span>  

<span data-ttu-id="0e711-127">WebView2 ランタイムの更新プログラムが停止している場合は、アプリで必要な最小バージョンの [WebView2 ランタイム][MicrosoftDeveloperEdgeWebview2] を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0e711-127">If WebView2 Runtime updates are stopped, ensure you understand the minimum version of the [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2] required by your app.</span></span>  <span data-ttu-id="0e711-128">次の2つの項目を検討してください。</span><span class="sxs-lookup"><span data-stu-id="0e711-128">Consider the following two items:</span></span>  

1.  <span data-ttu-id="0e711-129">SDK の最低限必要なバージョンは、WebView2 の [リリースノート][Webview2Releasenotes] の「 **最小 WebView2 ランタイムバージョン**」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="0e711-129">The minimum required version of the SDK, in found in the WebView2 [Release Notes][Webview2Releasenotes] under **minimum WebView2 Runtime version**.</span></span>  <span data-ttu-id="0e711-130">たとえば、SDK バージョン [1.0.622.22][Webview2Releasenotes1062222]の場合は、 [WebView2 ランタイム][MicrosoftDeveloperEdgeWebview2] 、またはビルド番号以降の [非安定した Microsoft Edge チャネル][MicrosoftedgeinsiderDownload] をインストールする必要があり `86.0.616.0` ます。</span><span class="sxs-lookup"><span data-stu-id="0e711-130">For example, for SDK version [1.0.622.22][Webview2Releasenotes1062222], you must install either the [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2] or a [non-stable Microsoft Edge channel][MicrosoftedgeinsiderDownload] with a build number of `86.0.616.0` or later.</span></span>  <span data-ttu-id="0e711-131">SDK で必要な最小バージョンは、web プラットフォームで変更が行われない場合にのみ変更されます。</span><span class="sxs-lookup"><span data-stu-id="0e711-131">The minimum version required by the SDK only changes when a breaking change occurs in the web platform.</span></span>  
1.  <span data-ttu-id="0e711-132">アプリで使うインターフェイスと Api をサポートするために必要な、最低限の必須バージョンの NuGet パッケージ。</span><span class="sxs-lookup"><span data-stu-id="0e711-132">The minimum required version of the NuGet package required to support the interfaces and APIs that you use in your app.</span></span>  <span data-ttu-id="0e711-133">WebView2 には、新しいインターフェイスと Api が定期的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="0e711-133">New interfaces and APIs are added periodically to WebView2.</span></span>  <span data-ttu-id="0e711-134">SDK にバンドルされている Api とインターフェイスは、異なるタイミングで SDK に Api とインターフェイスが追加されるため、異なるバージョンの WebView2 ランタイムを必要とします。</span><span class="sxs-lookup"><span data-stu-id="0e711-134">APIs and interfaces bundled in an SDK require different versions of the WebView2 Runtime, because APIs and interface are added to the SDK at different times.</span></span>  <span data-ttu-id="0e711-135">必須の WebView2 ランタイムバージョンは、API が最初に導入された SDK バージョンの3番目の番号のビルド番号と一致します。</span><span class="sxs-lookup"><span data-stu-id="0e711-135">The required WebView2 Runtime version matches the build number, the third number, of the SDK version the API was first introduced in.</span></span>  <span data-ttu-id="0e711-136">たとえば、SDK バージョン [1.0.622.22][Webview2Releasenotes1062222] で追加された新しい api またはインターフェイスには、WebView2 ランタイムバージョンが必要です。この  `86.0.622.0`  ような sdk リリースで追加された api やインターフェイスには、sdk と同じバージョン番号の WebView2 ランタイムが必要です。</span><span class="sxs-lookup"><span data-stu-id="0e711-136">For example, a new API or interface added in SDK version [1.0.622.22][Webview2Releasenotes1062222] requires the WebView2 Runtime version:  `86.0.622.0`  An API or interface added in a later SDK release requires the WebView2 Runtime that has the same version number as the SDK.</span></span>  <span data-ttu-id="0e711-137">WebView2 ランタイムバージョンがインターフェイスまたは API をサポートしているかどうかを判断するには、 [WebView2 ランタイム要件を決定](#determine-webview2-runtime-requirement)するに移動します。</span><span class="sxs-lookup"><span data-stu-id="0e711-137">To help you determine if the WebView2 Runtime version supports an interface or API, navigate to [Determine WebView2 Runtime requirement](#determine-webview2-runtime-requirement).</span></span>  
    
> [!IMPORTANT]
> <span data-ttu-id="0e711-138">[Evergreen WebView2 アプリ][Webview2ConceptsDistributionEvergreenDistributionMode]を開発する場合は、最新バージョンの WebView2 Runtime と、安定していない Microsoft Edge ブラウザーに対して、アプリを定期的にテストしてください。</span><span class="sxs-lookup"><span data-stu-id="0e711-138">When developing [Evergreen WebView2 apps][Webview2ConceptsDistributionEvergreenDistributionMode], regularly test your app against the latest versions of the WebView2 Runtime and non-stable Microsoft Edge browsers.</span></span>  <span data-ttu-id="0e711-139">Web プラットフォームは絶えず進化しているため、アプリが意図したとおりに動作するための最適な方法は、通常のテストです。</span><span class="sxs-lookup"><span data-stu-id="0e711-139">Because the web platform is constantly evolving, regular testing is the best way to ensure your app performs as intended.</span></span>  

### <span data-ttu-id="0e711-140">WebView2 のランタイム要件を決定する</span><span class="sxs-lookup"><span data-stu-id="0e711-140">Determine WebView2 Runtime requirement</span></span>  

<span data-ttu-id="0e711-141">使用する SDK に応じて、次の項目について検討します。</span><span class="sxs-lookup"><span data-stu-id="0e711-141">Depending on which SDK you use, consider the following items:</span></span>  

*   <span data-ttu-id="0e711-142">**Win32 C/c + +**。</span><span class="sxs-lookup"><span data-stu-id="0e711-142">**Win32 C/C++**.</span></span>  <span data-ttu-id="0e711-143">を使って新しいインターフェイスを取得するときは `QueryInterface` 、の戻り値を確認し `E_NOINTERFACE` ます。</span><span class="sxs-lookup"><span data-stu-id="0e711-143">When using `QueryInterface` to obtain a new interface, verify a return value of `E_NOINTERFACE`.</span></span>  <span data-ttu-id="0e711-144">この値は、WebView2 ランタイムが以前のバージョンであり、そのインターフェイスをサポートしていないことを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0e711-144">The value may indicate that the WebView2 Runtime is a previous version, and doesn't support that interface.</span></span>  <span data-ttu-id="0e711-145">このしくみの例については、「 [行 622-AppWindow .cpp」][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisampleAppwindowCppL622]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e711-145">For an example of how it works, navigate to [Line 622 - AppWindow.cpp][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisampleAppwindowCppL622].</span></span>  
*   <span data-ttu-id="0e711-146">**.Net と WinUI**。</span><span class="sxs-lookup"><span data-stu-id="0e711-146">**.NET and WinUI**.</span></span>  <span data-ttu-id="0e711-147">`No such interface supported`新しい sdk に追加されたメソッド、プロパティ、イベントを使用している場合は、例外を確認します。</span><span class="sxs-lookup"><span data-stu-id="0e711-147">Check for a `No such interface supported` exception when using methods, properties, and events that were added to more recent SDKs.</span></span>  <span data-ttu-id="0e711-148">この例外は、WebView2 ランタイムが以前のバージョンであり、Api をサポートしていない場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0e711-148">The exception may occur when the WebView2 Runtime is a previous version, and does not support the APIs.</span></span>  
    
<span data-ttu-id="0e711-149">API が利用できない場合は、関連する機能の削除を検討するか、WebView2 ランタイムの更新が必要であることをユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="0e711-149">If an API is unavailable, consider removing the associated feature, or inform your users that an update to the WebView2 Runtime is required.</span></span>  

<!--
## Versioning  

After you have used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.  Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that prevent your SDK from working with different versions of installed browser binaries.  After version 1.0.0.0, different versions of the SDK may work with different versions of the installed browser by using the following best practices.  

1.  To account for breaking changes to the API be sure to check for failure when requesting the DLL export `CreateCoreWebView2Environment` and when running `QueryInterface` on any `CoreWebView2` object.  A return value of `E_NOINTERFACE` indicates that the SDK is not compatible with the Microsoft Edge browser binaries.  
1.  Checking for failure from `QueryInterface` also accounts for cases where the SDK is newer than the version of the Microsoft Edge browser and your app attempts to use an interface of which the Microsoft Edge browser is unaware.  
1.  When an interface is unavailable, you may consider disabling the associated feature if possible, or otherwise informing your users to update their browsers.  
    -->  

<!--links -->  

[Webview2ConceptsDistributionEvergreenDistributionMode]: ./distribution.md#evergreen-distribution-mode "Evergreen 配布モード-WebView2 を使用したアプリの配布 |Microsoft ドキュメント"  
[Webview2Releasenotes]: ../releasenotes.md "WebView2 SDK のリリースノート |Microsoft ドキュメント"  
[Webview2Releasenotes1062222]: ../releasenotes.md#1062222 "1.0.622.22-WebView2 SDK のリリースノート |Microsoft ドキュメント"   

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge チャネルの概要 |Microsoft ドキュメント"  

[DotnetMicrosoftWebWebview2CoreNamespace]: /dotnet/api/microsoft.web.webview2.core "WebView2 の名前空間 |Microsoft ドキュメント"  
[DotnetMicrosoftWebWebview2WpfNamespace]: /dotnet/api/microsoft.web.webview2.wpf "WebView2 の名前空間 |Microsoft ドキュメント"  
[DotnetMicrosoftWebWebview2WinformsNamespace]: /dotnet/api/microsoft.web.webview2.winforms "WinForms 名前空間 WebView2 |Microsoft ドキュメント"  
[ReferenceWin32]: /microsoft-edge/webview2/reference/win32 "WebView2 Win32 C++ リファレンス |Microsoft ドキュメント"  

[MicrosoftDeveloperEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2/ "Microsoft Edge WebView2 |Microsoft 開発者"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisampleAppwindowCppL622]: https://github.com/MicrosoftEdge/WebView2Samples/blob/8ec7de9d3e80a942bc7025cffad98eee75e11e64/SampleApps/WebView2APISample/AppWindow.cpp#L622 "Line 622-AppWindow .cpp-MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  
