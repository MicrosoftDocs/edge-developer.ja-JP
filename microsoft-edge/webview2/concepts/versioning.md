---
description: Microsoft Edge WebView2 で使用されるバージョン管理モデル
title: Microsoft Edge WebView2 のバージョン管理
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: a47c7295e87cf4295f8cdf898b62aa3b550aa9a5
ms.sourcegitcommit: af91bfc3e6d8afc51f0fbbc0fe392262f424225c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2020
ms.locfileid: "11120340"
---
# <span data-ttu-id="b43c9-104">WebView2 SDK のバージョンについて</span><span class="sxs-lookup"><span data-stu-id="b43c9-104">Understand WebView2 SDK versions</span></span>  

<span data-ttu-id="b43c9-105">WebView2 アプリケーションを開発するには、 [WebView2 ランタイム][MicrosoftDeveloperEdgeWebview2] または [非安定した Microsoft Edge チャネル][MicrosoftedgeinsiderDownload]のいずれかをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b43c9-105">To develop a WebView2 application, you must install either the [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2] or a [non-stable Microsoft Edge channel][MicrosoftedgeinsiderDownload].</span></span>  <span data-ttu-id="b43c9-106">必要な最小バージョンは、SDK の NuGet パッケージバージョンに含まれています。</span><span class="sxs-lookup"><span data-stu-id="b43c9-106">The minimum version that's required is included in the NuGet package version of the SDK.</span></span>  <span data-ttu-id="b43c9-107">たとえば、を使っている場合は、 `SDK package version 0.9.488` [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2] 、またはビルド番号が488以降の [非安定した Microsoft Edge チャネル][MicrosoftedgeinsiderDownload] をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b43c9-107">For example, if you use the `SDK package version 0.9.488`, then you must install either the [WebView2 Runtime][MicrosoftDeveloperEdgeWebview2] or a [non-stable Microsoft Edge channel][MicrosoftedgeinsiderDownload] with a build number of 488 or later.</span></span>  <span data-ttu-id="b43c9-108">必要な最小バージョンは、WebView2 の [リリースノート][Releasenotes]にも指定されています。</span><span class="sxs-lookup"><span data-stu-id="b43c9-108">The minimum version required is also specified in the WebView2 [Release Notes][Releasenotes].</span></span>  <span data-ttu-id="b43c9-109">WebView2 SDK の新しいバージョンは、Microsoft Edge \ (Chromium \) ブラウザーと同じ一般的なリズムで出荷されています。これは、約6週間です。</span><span class="sxs-lookup"><span data-stu-id="b43c9-109">New versions of the WebView2 SDK are shipped at the same general cadence as the Microsoft Edge \(Chromium\) browser, which is approximately every six weeks.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="b43c9-110">Evergreen WebView2 アプリケーションを開発する際には、最新バージョンの WebView2 ランタイムと、安定していない Microsoft Edge ブラウザーを使用して、アプリケーションを定期的にテストします。</span><span class="sxs-lookup"><span data-stu-id="b43c9-110">When developing Evergreen WebView2 applications, regularly test your application against the latest versions of the WebView2 Runtime and non-stable Microsoft Edge browsers.</span></span>  <span data-ttu-id="b43c9-111">Web プラットフォームは絶えず進化しているため、アプリケーションが意図したとおりに動作するための最適な方法は、通常のテストです。</span><span class="sxs-lookup"><span data-stu-id="b43c9-111">Because the web platform is constantly evolving, regular testing is the best way to ensure your application performs as intended.</span></span>  

## <span data-ttu-id="b43c9-112">Release パッケージとプレリリースパッケージ</span><span class="sxs-lookup"><span data-stu-id="b43c9-112">Release and prerelease package</span></span>  

<span data-ttu-id="b43c9-113">WebView2 NuGet パッケージには、リリースとプレリリースの両方のパッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b43c9-113">The WebView2 NuGet package contains both a release and pre-release package.</span></span>  

<span data-ttu-id="b43c9-114">リリースパッケージには上位互換性があり、 [Win32 C/c + + api][ReferenceWin32]が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b43c9-114">The release package is forward compatible and contains the [Win32 C/C++ APIs][ReferenceWin32].</span></span>  <span data-ttu-id="b43c9-115">この SDK の Api は完全にサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b43c9-115">APIs in this SDK are fully supported.</span></span>  

<span data-ttu-id="b43c9-116">プレリリースパッケージは、以下に示すような追加のコンポーネントを含むリリースパッケージのスーパーセットです。</span><span class="sxs-lookup"><span data-stu-id="b43c9-116">The prerelease package is a superset of the release package with the additional components listed below.</span></span>  

*   <span data-ttu-id="b43c9-117">.NET Api: [WPF][DotnetMicrosoftWebWebview2WpfNamespace]、 [WinForms][DotnetMicrosoftWebWebview2WinformsNamespace]、および [Core][DotnetMicrosoftWebWebview2CoreNamespace]</span><span class="sxs-lookup"><span data-stu-id="b43c9-117">.NET APIs: [WPF][DotnetMicrosoftWebWebview2WpfNamespace], [WinForms][DotnetMicrosoftWebWebview2WinformsNamespace], and [Core][DotnetMicrosoftWebWebview2CoreNamespace]</span></span>  
*   <span data-ttu-id="b43c9-118">実験的な Api: 詳細については、「 [実験的 api](#experimental-apis) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b43c9-118">Experimental APIs:  For more information, navigate to the [Experimental APIs](#experimental-apis) section.</span></span>  

## <span data-ttu-id="b43c9-119">試験的な API</span><span class="sxs-lookup"><span data-stu-id="b43c9-119">Experimental APIs</span></span>  

<span data-ttu-id="b43c9-120">WebView チームは、今後のリリースに含まれる可能性がある実験的な Api をテストしています。</span><span class="sxs-lookup"><span data-stu-id="b43c9-120">The WebView team is testing experimental APIs that may be included in future releases.</span></span>  <span data-ttu-id="b43c9-121">実験的な Api は、SDK で示されてい `experimental` ます。</span><span class="sxs-lookup"><span data-stu-id="b43c9-121">The experimental APIs are marked as `experimental` in the SDK.</span></span>  <span data-ttu-id="b43c9-122">実験的な Api は、リリースパッケージで完全に安定した Api として出荷される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b43c9-122">Experimental APIs may ship as fully stable APIs in the release package.</span></span>  <span data-ttu-id="b43c9-123">[WebView フィードバックリポジトリ][GithubMicrosoftedgeWebviewfeedback]を使って、実験的な api を評価し、フィードバックを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="b43c9-123">You can evaluate the Experimental APIs and share feedback using the [WebView feedback repo][GithubMicrosoftedgeWebviewfeedback].</span></span>  

> [!CAUTION]
> <span data-ttu-id="b43c9-124">プロダクションアプリで実験的な Api を使うことは避けてください。</span><span class="sxs-lookup"><span data-stu-id="b43c9-124">Avoid using the experimental APIs in production apps.</span></span>  

## <span data-ttu-id="b43c9-125">WebView2 のランタイムバージョンの一致</span><span class="sxs-lookup"><span data-stu-id="b43c9-125">Matching WebView2 Runtime versions</span></span>  

<span data-ttu-id="b43c9-126">特定の SDK バージョンを使って WebView2 アプリを作成する場合、アプリのユーザーは、互換性のあるいくつかの WebView2 ランタイムバージョンでアプリを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="b43c9-126">When writing a WebView2 app using a particular SDK version, users of your app may run it with several compatible versions of the WebView2 Runtime.</span></span>  <span data-ttu-id="b43c9-127">WebView チームは、以前のバージョンのランタイムと新しい非実験的な Api からの非実験的な Api を含む互換性のある WebView2 ランタイムバージョンで作業しています。</span><span class="sxs-lookup"><span data-stu-id="b43c9-127">The WebView team is working on a compatible WebView2 Runtime version that contains non-experimental APIs from previous versions of the Runtime and new non-experimental APIs.</span></span>  

<span data-ttu-id="b43c9-128">使用する SDK に応じて、次の項目について検討します。</span><span class="sxs-lookup"><span data-stu-id="b43c9-128">Depending on which SDK you use, consider the following items:</span></span> 

*   <span data-ttu-id="b43c9-129">**Win32 C/c + +**。</span><span class="sxs-lookup"><span data-stu-id="b43c9-129">**Win32 C/C++**.</span></span>  <span data-ttu-id="b43c9-130">を使って `QueryInterface` 新しいインターフェイスを取得するときは、の戻り値を確認し `E_NOINTERFACE` ます。</span><span class="sxs-lookup"><span data-stu-id="b43c9-130">When using `QueryInterface` to obtain a new interface, check for a return value of `E_NOINTERFACE`.</span></span>  <span data-ttu-id="b43c9-131">この値は、WebView2 ランタイムが以前のバージョンであり、そのインターフェイスをサポートしていないことを示す場合があります。</span><span class="sxs-lookup"><span data-stu-id="b43c9-131">This value may indicate that the WebView2 Runtime is a previous version, and doesn't support that interface.</span></span>  
*   <span data-ttu-id="b43c9-132">**.Net と WinUI**。</span><span class="sxs-lookup"><span data-stu-id="b43c9-132">**.NET and WinUI**.</span></span>  <span data-ttu-id="b43c9-133">`No such interface supported`新しい sdk に追加されたメソッド、プロパティ、イベントを使用している場合は、例外を確認します。</span><span class="sxs-lookup"><span data-stu-id="b43c9-133">Check for a `No such interface supported` exception when using methods, properties, and events that were added to more recent SDKs.</span></span>  <span data-ttu-id="b43c9-134">この例外は、WebView2 ランタイムが以前のバージョンであり、その Api をサポートしていない場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b43c9-134">This exception may occur when the WebView2 Runtime is a previous version, and doesn't support those APIs.</span></span>  

<span data-ttu-id="b43c9-135">API が利用できない場合は、関連する機能を削除するか、WebView2 ランタイムのバージョンを更新する必要があることをユーザーに知らせてください。</span><span class="sxs-lookup"><span data-stu-id="b43c9-135">If an API is unavailable, consider removing the associated feature, or inform your users that they need to update their version of the WebView2 Runtime.</span></span>  

<span data-ttu-id="b43c9-136">実験的な Api は、SDK から SDK に導入、変更、削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b43c9-136">Experimental APIs may be introduced, modified, and removed from SDK to SDK.</span></span>  <span data-ttu-id="b43c9-137">実験的な Api は、インストールされているバージョンの WebView2 Runtime では使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="b43c9-137">Experimental APIs may not be available in your installed version of the WebView2 Runtime.</span></span>  

## <span data-ttu-id="b43c9-138">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="b43c9-138">Roadmap</span></span>  

<span data-ttu-id="b43c9-139">リリースパッケージには、サポートされているすべての安定した Win32 C/C + + C++ Api が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b43c9-139">The release package contains all of the stable, supported Win32 C/C++ APIs.</span></span>  <span data-ttu-id="b43c9-140">今後、リリースパッケージには、一般公開されている限り、サポートされているすべての安定した .NET Api が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b43c9-140">In the future, the release package will contain all stable, supported .NET APIs when they are made generally available.</span></span>  <span data-ttu-id="b43c9-141">プレリリースパッケージには、フィードバックに基づいて変更される可能性のある実験的な Api が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b43c9-141">The prerelease package contains experimental APIs that are subject to change based upon your feedback and shared insights.</span></span>  

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
