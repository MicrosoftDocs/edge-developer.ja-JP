---
description: Microsoft Edge WebView2 で使用されるバージョン管理モデル
title: Microsoft Edge WebView2 のバージョン管理
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/18/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 132ccab0f9f378eedd8c83a7404c350161556f2e
ms.sourcegitcommit: fab44f7e183a3c4f12bf925512fc62d84a4d6edc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "11182396"
---
# <span data-ttu-id="48e9d-104">WebView2 SDK のバージョンについて</span><span class="sxs-lookup"><span data-stu-id="48e9d-104">Understand WebView2 SDK versions</span></span>

<span data-ttu-id="48e9d-105">WebView2 SDK の新しいバージョンは、Microsoft Edge \ (Chromium \) ブラウザーと同じ一般的なリズムで出荷されています。これは、約6週間です。</span><span class="sxs-lookup"><span data-stu-id="48e9d-105">New versions of the WebView2 SDK are shipped at the same general cadence as the Microsoft Edge \(Chromium\) browser, which is approximately every six weeks.</span></span>  

## <span data-ttu-id="48e9d-106">Release パッケージとプレリリースパッケージ</span><span class="sxs-lookup"><span data-stu-id="48e9d-106">Release and prerelease package</span></span>  

<span data-ttu-id="48e9d-107">WebView2 NuGet パッケージには、リリースとプレリリースの両方のパッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="48e9d-107">The WebView2 NuGet package contains both a release and pre-release package.</span></span>  

<span data-ttu-id="48e9d-108">リリースパッケージには上位互換性があり、 [Win32 C/c + + api][ReferenceWin32]が含まれています。</span><span class="sxs-lookup"><span data-stu-id="48e9d-108">The release package is forward compatible and contains the [Win32 C/C++ APIs][ReferenceWin32].</span></span>  <span data-ttu-id="48e9d-109">この SDK の Api は完全にサポートされています。</span><span class="sxs-lookup"><span data-stu-id="48e9d-109">APIs in this SDK are fully supported.</span></span>  

<span data-ttu-id="48e9d-110">プレリリースパッケージは、以下に示すような追加のコンポーネントを含むリリースパッケージのスーパーセットです。</span><span class="sxs-lookup"><span data-stu-id="48e9d-110">The prerelease package is a superset of the release package with the additional components listed below.</span></span>  

*   <span data-ttu-id="48e9d-111">.NET Api: [WPF][DotnetMicrosoftWebWebview2WpfNamespace]、 [WinForms][DotnetMicrosoftWebWebview2WinformsNamespace]、および [Core][DotnetMicrosoftWebWebview2CoreNamespace]</span><span class="sxs-lookup"><span data-stu-id="48e9d-111">.NET APIs: [WPF][DotnetMicrosoftWebWebview2WpfNamespace], [WinForms][DotnetMicrosoftWebWebview2WinformsNamespace], and [Core][DotnetMicrosoftWebWebview2CoreNamespace]</span></span>  
*   <span data-ttu-id="48e9d-112">実験的な Api: 詳細については、「 [実験的 api](#experimental-apis) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="48e9d-112">Experimental APIs:  For more information, navigate to the [Experimental APIs](#experimental-apis) section.</span></span>  

### <span data-ttu-id="48e9d-113">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="48e9d-113">Roadmap</span></span>  

<span data-ttu-id="48e9d-114">リリースパッケージには、サポートされているすべての安定した Win32 C/C + + C++ Api が含まれています。</span><span class="sxs-lookup"><span data-stu-id="48e9d-114">The release package contains all of the stable, supported Win32 C/C++ APIs.</span></span>  <span data-ttu-id="48e9d-115">今後、リリースパッケージには、一般に公開されるときに、サポートされているすべての安定した .NET Api が含まれます。</span><span class="sxs-lookup"><span data-stu-id="48e9d-115">In the future, the release package will contain all stable, supported .NET APIs when they're made generally available.</span></span>  <span data-ttu-id="48e9d-116">プレリリースパッケージには、フィードバックに基づいて変更される可能性がある実験的な Api が含まれています。</span><span class="sxs-lookup"><span data-stu-id="48e9d-116">The prerelease package contains experimental APIs that are subject to change based on your feedback.</span></span> 

## <span data-ttu-id="48e9d-117">試験的な API</span><span class="sxs-lookup"><span data-stu-id="48e9d-117">Experimental APIs</span></span>  

<span data-ttu-id="48e9d-118">WebView チームは、今後のリリースに含まれる可能性がある実験的な Api についてのフィードバックを求めています。</span><span class="sxs-lookup"><span data-stu-id="48e9d-118">The WebView team is seeking feedback on experimental APIs that may be included in future releases.</span></span>  <span data-ttu-id="48e9d-119">実験的な Api は、SDK で示されてい `experimental` ます。</span><span class="sxs-lookup"><span data-stu-id="48e9d-119">The experimental APIs are marked as `experimental` in the SDK.</span></span>  <span data-ttu-id="48e9d-120">[WebView フィードバックリポジトリ][GithubMicrosoftedgeWebviewfeedback]を使って、実験的な api を評価し、フィードバックを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="48e9d-120">You can evaluate the Experimental APIs and share feedback using the [WebView feedback repo][GithubMicrosoftedgeWebviewfeedback].</span></span>  

> [!CAUTION]
> <span data-ttu-id="48e9d-121">実験的な Api は、SDK から SDK に導入、変更、削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="48e9d-121">Experimental APIs may be introduced, modified, and removed from SDK to SDK.</span></span>  <span data-ttu-id="48e9d-122">プロダクションアプリで実験的な Api を使うことは避けてください。</span><span class="sxs-lookup"><span data-stu-id="48e9d-122">Avoid using the experimental APIs in production apps.</span></span>  

> [!NOTE]
> <span data-ttu-id="48e9d-123">実験的な Api は、インストールされているバージョンの WebView2 Runtime では使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="48e9d-123">Experimental APIs may not be available in your installed version of the WebView2 Runtime.</span></span>  

## <span data-ttu-id="48e9d-124">WebView2 のランタイムバージョンの一致</span><span class="sxs-lookup"><span data-stu-id="48e9d-124">Matching WebView2 Runtime versions</span></span>  
<span data-ttu-id="48e9d-125">WebView2 アプリケーションでは、ユーザーが [WebView2 ランタイム][MicrosoftDeveloperEdgeWebview2]をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="48e9d-125">WebView2 applications require users to install a [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2].</span></span> <span data-ttu-id="48e9d-126">WebView2 ランタイムは、使用できる最新バージョンに自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="48e9d-126">The WebView2 Runtime updates automatically to the latest version that's available.</span></span> <span data-ttu-id="48e9d-127">一部のシナリオでは、ユーザーが自動 WebView2 ランタイム更新を停止する必要があります。これにより、アプリケーションの互換性の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="48e9d-127">In some scenarios, users may need to stop automatic WebView2 Runtime updates, which can cause application compatibility issues.</span></span>

<span data-ttu-id="48e9d-128">WebView2 ランタイムの更新プログラムが停止している場合は、アプリケーションで必要な最小バージョンの [WebView2 ランタイム][MicrosoftDeveloperEdgeWebview2] を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="48e9d-128">If WebView2 Runtime updates are stopped, ensure you understand the minimum version of the [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2] that's required by your application.</span></span> <span data-ttu-id="48e9d-129">次の2つの項目を検討してください。</span><span class="sxs-lookup"><span data-stu-id="48e9d-129">Consider the following two items:</span></span>  

1. <span data-ttu-id="48e9d-130">SDK の必須バージョンのうち、最小の**WebView2 ランタイムバージョン**の WebView2[リリースノート][Releasenotes]に記載されているものを参照してください。</span><span class="sxs-lookup"><span data-stu-id="48e9d-130">The minimum required version of the SDK, which can be found in the WebView2 [Release Notes][Releasenotes] under **minimum WebView2 Runtime version**.</span></span> <span data-ttu-id="48e9d-131">たとえば、SDK バージョン[1.0.622.22](https://docs.microsoft.com/microsoft-edge/webview2/releasenotes#1062222)の場合は、 [WebView2 ランタイム][MicrosoftDeveloperEdgeWebview2]、または**86.0.616.0**以降のビルド番号を持つ[非安定した Microsoft Edge チャネル][MicrosoftedgeinsiderDownload]をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="48e9d-131">For example, for SDK version [1.0.622.22](https://docs.microsoft.com/microsoft-edge/webview2/releasenotes#1062222), you must install either the [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2] or a [non-stable Microsoft Edge channel][MicrosoftedgeinsiderDownload] with a build number of **86.0.616.0** or later.</span></span> <span data-ttu-id="48e9d-132">SDK で必要な最小バージョンは、web プラットフォームで変更が行われた場合にのみ変更されます。</span><span class="sxs-lookup"><span data-stu-id="48e9d-132">The minimum version required by the SDK will only change when there's a breaking change in the web platform.</span></span>

2. <span data-ttu-id="48e9d-133">アプリで使用されるインターフェイスと Api をサポートするために必要な、最低限必要なバージョンの NuGet パッケージ。</span><span class="sxs-lookup"><span data-stu-id="48e9d-133">The minimum required version of the NuGet package that's required to support the interfaces and APIs used in your app.</span></span> <span data-ttu-id="48e9d-134">WebView2 には、新しいインターフェイスと Api が定期的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="48e9d-134">New interfaces and APIs are added periodically to WebView2.</span></span> <span data-ttu-id="48e9d-135">SDK にバンドルされている Api とインターフェイスは、異なるタイミングで SDK に追加されたため、異なるバージョンの WebView2 ランタイムを必要とします。</span><span class="sxs-lookup"><span data-stu-id="48e9d-135">APIs and interfaces bundled in an SDK will require different versions of the WebView2 Runtime because they were added to the SDK at different times.</span></span>  <span data-ttu-id="48e9d-136">必須の WebView2 ランタイムバージョンは、API が最初に導入された SDK バージョンの3番目の番号のビルド番号と一致します。</span><span class="sxs-lookup"><span data-stu-id="48e9d-136">The required WebView2 Runtime version matches the build number, the third number, of the SDK version the API was first introduced in.</span></span> <span data-ttu-id="48e9d-137">たとえば、SDK バージョン [1.0.622.22](https://docs.microsoft.com/microsoft-edge/webview2/releasenotes#1062222) に追加された新しい API またはインターフェイスには、WebView2 ランタイムバージョン86.0 が必要です。**622**. 0。</span><span class="sxs-lookup"><span data-stu-id="48e9d-137">For example, a new API or interface added in SDK version [1.0.622.22](https://docs.microsoft.com/microsoft-edge/webview2/releasenotes#1062222) will need the WebView2 Runtime version: 86.0.**622**.0.</span></span> <span data-ttu-id="48e9d-138">後続の SDK リリースで追加された API またはインターフェイスでは、SDK と同じバージョン番号の WebView2 ランタイムが必要です。</span><span class="sxs-lookup"><span data-stu-id="48e9d-138">An API or interface added in a subsequent SDK release requires the WebView2 Runtime that has the same version number as the SDK.</span></span> <span data-ttu-id="48e9d-139">WebView2 ランタイムバージョンが、インターフェイスまたは API を [プログラム](#determine-webview2-runtime-requirement)でサポートしているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="48e9d-139">You can determine if the WebView2 Runtime version supports an interface or API [programmatically](#determine-webview2-runtime-requirement).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="48e9d-140">[Evergreen WebView2 アプリケーション](distribution.md#evergreen-distribution-mode)を開発する際には、最新バージョンの WebView2 ランタイムと、安定していない Microsoft Edge ブラウザーを使用して、アプリケーションを定期的にテストします。</span><span class="sxs-lookup"><span data-stu-id="48e9d-140">When developing [Evergreen WebView2 applications](distribution.md#evergreen-distribution-mode), regularly test your application against the latest versions of the WebView2 Runtime and non-stable Microsoft Edge browsers.</span></span>  <span data-ttu-id="48e9d-141">Web プラットフォームは絶えず進化しているため、アプリケーションが意図したとおりに動作するための最適な方法は、通常のテストです。</span><span class="sxs-lookup"><span data-stu-id="48e9d-141">Because the web platform is constantly evolving, regular testing is the best way to ensure your application performs as intended.</span></span>  

### <span data-ttu-id="48e9d-142">WebView2 のランタイム要件を決定する</span><span class="sxs-lookup"><span data-stu-id="48e9d-142">Determine WebView2 Runtime requirement</span></span>

<span data-ttu-id="48e9d-143">使用する SDK に応じて、次の項目について検討します。</span><span class="sxs-lookup"><span data-stu-id="48e9d-143">Depending on which SDK you use, consider the following items:</span></span> 

*   <span data-ttu-id="48e9d-144">**Win32 C/c + +**。</span><span class="sxs-lookup"><span data-stu-id="48e9d-144">**Win32 C/C++**.</span></span>  <span data-ttu-id="48e9d-145">を使って `QueryInterface` 新しいインターフェイスを取得するときは、の戻り値を確認し `E_NOINTERFACE` ます。</span><span class="sxs-lookup"><span data-stu-id="48e9d-145">When using `QueryInterface` to obtain a new interface, check for a return value of `E_NOINTERFACE`.</span></span>  <span data-ttu-id="48e9d-146">この値は、WebView2 ランタイムが以前のバージョンであり、そのインターフェイスをサポートしていないことを示す場合があります。</span><span class="sxs-lookup"><span data-stu-id="48e9d-146">This value may indicate that the WebView2 Runtime is a previous version, and doesn't support that interface.</span></span> <span data-ttu-id="48e9d-147">このしくみの [例](https://github.com/MicrosoftEdge/WebView2Samples/blob/8ec7de9d3e80a942bc7025cffad98eee75e11e64/SampleApps/WebView2APISample/AppWindow.cpp#L622) については、WebView2API のサンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="48e9d-147">Navigate to the WebView2API Sample for an [example](https://github.com/MicrosoftEdge/WebView2Samples/blob/8ec7de9d3e80a942bc7025cffad98eee75e11e64/SampleApps/WebView2APISample/AppWindow.cpp#L622) of how this works.</span></span>
*   <span data-ttu-id="48e9d-148">**.Net と WinUI**。</span><span class="sxs-lookup"><span data-stu-id="48e9d-148">**.NET and WinUI**.</span></span>  <span data-ttu-id="48e9d-149">`No such interface supported`新しい sdk に追加されたメソッド、プロパティ、イベントを使用している場合は、例外を確認します。</span><span class="sxs-lookup"><span data-stu-id="48e9d-149">Check for a `No such interface supported` exception when using methods, properties, and events that were added to more recent SDKs.</span></span>  <span data-ttu-id="48e9d-150">この例外は、WebView2 ランタイムが以前のバージョンであり、その Api をサポートしていない場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="48e9d-150">This exception may occur when the WebView2 Runtime is a previous version, and doesn't support those APIs.</span></span>  

<span data-ttu-id="48e9d-151">API が利用できない場合は、関連する機能を削除するか、WebView2 ランタイムのバージョンを更新する必要があることをユーザーに知らせてください。</span><span class="sxs-lookup"><span data-stu-id="48e9d-151">If an API is unavailable, consider removing the associated feature, or inform your users that they need to update their version of the WebView2 Runtime.</span></span>  



 

<!--## Versioning  

After you have used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.  Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that prevent your SDK from working with different versions of installed browser binaries.  After version 1.0.0.0, different versions of the SDK may work with different versions of the installed browser by using the following best practices.  

1.  To account for breaking changes to the API be sure to check for failure when requesting the DLL export `CreateCoreWebView2Environment` and when running `QueryInterface` on any `CoreWebView2` object.  A return value of `E_NOINTERFACE` indicates that the SDK is not compatible with the Microsoft Edge browser binaries.  
1.  Checking for failure from `QueryInterface` also accounts for cases where the SDK is newer than the version of the Microsoft Edge browser and your app attempts to use an interface of which the Microsoft Edge browser is unaware.  

1.  When an interface is unavailable, you may consider disabling the associated feature if possible, or otherwise informing your users to update their browsers.  -->  

<!--links -->  

[Releasenotes]: ../releasenotes.md "WebView2 SDK のリリースノート |Microsoft ドキュメント"  

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge チャネルの概要 |Microsoft ドキュメント"  

[DotnetMicrosoftWebWebview2CoreNamespace]: /dotnet/api/microsoft.web.webview2.core "WebView2 の名前空間 |Microsoft ドキュメント"  
[DotnetMicrosoftWebWebview2WpfNamespace]: /dotnet/api/microsoft.web.webview2.wpf "WebView2 の名前空間 |Microsoft ドキュメント"  
[DotnetMicrosoftWebWebview2WinformsNamespace]: /dotnet/api/microsoft.web.webview2.winforms "WinForms 名前空間 WebView2 |Microsoft ドキュメント"  
[ReferenceWin32]: /microsoft-edge/webview2/reference/win32 "WebView2 Win32 C++ リファレンス |Microsoft ドキュメント"  

[MicrosoftDeveloperEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2/ "Microsoft Edge WebView2 |Microsoft 開発者"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Insider チャネルをダウンロードする"  
