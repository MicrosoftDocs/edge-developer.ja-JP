---
description: Microsoft Edge WebView2 で使用されるバージョン管理モデル
title: Microsoft Edge WebView2 のバージョン管理
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 3ce1f0653a14d92571f1365cbfebc8bb2215ecbe
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010678"
---
# <span data-ttu-id="10b49-104">WebView2 SDK のバージョンについて</span><span class="sxs-lookup"><span data-stu-id="10b49-104">Understand WebView2 SDK versions</span></span>  

<span data-ttu-id="10b49-105">WebView2 は Microsoft Edge によって異なります。</span><span class="sxs-lookup"><span data-stu-id="10b49-105">WebView2 depends on Microsoft Edge to function.</span></span>  <span data-ttu-id="10b49-106">各 WebView2 SDK では、最小ブラウザーバージョンがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="10b49-106">Each WebView2 SDK requires that a minimum browser version is installed.</span></span>  <span data-ttu-id="10b49-107">最小バージョンは、SDK のパッケージバージョンに反映されています。</span><span class="sxs-lookup"><span data-stu-id="10b49-107">The minimum version is reflected in the package version of the SDK.</span></span>  <span data-ttu-id="10b49-108">たとえば、を使用する場合は、 `SDK package version 0.9.488` 488 以降のビルド番号で Microsoft Edge をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="10b49-108">For example, if you use the `SDK package version 0.9.488`, then you must install Microsoft Edge with a build number of 488 or later.</span></span>  <span data-ttu-id="10b49-109">ブラウザーのバージョンも、WebView2 の [リリースノート][Releasenotes]で指定されています。</span><span class="sxs-lookup"><span data-stu-id="10b49-109">The browser version is also specified in the WebView2 [Release Notes][Releasenotes].</span></span>  <span data-ttu-id="10b49-110">Microsoft Edge ブラウザーの最新リリースの詳細については、「 [ブラウザーチャネル][DeployedgeChannels]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10b49-110">For more information about the latest release of the Microsoft Edge browser, navigate to [Browser Channels][DeployedgeChannels].</span></span>  

> [!NOTE]
> <span data-ttu-id="10b49-111">WebView2 は現在、プレビューに表示されています。</span><span class="sxs-lookup"><span data-stu-id="10b49-111">WebView2 is currently in preview.</span></span>  <span data-ttu-id="10b49-112">WebView チームは、ブラウザーのバージョンと Sdk の間の下位互換性を確保することを目的としていますが、新しいバージョンのブラウザーでは以前の SDK バージョンがサポートされていない可能性があるため、これは保証されません。</span><span class="sxs-lookup"><span data-stu-id="10b49-112">While the WebView team strives to ensure backward compatibility between browser versions and SDKs, it is not guaranteed because newer versions of the browser may not support previous SDK versions.</span></span>  <span data-ttu-id="10b49-113">ブラウザーのバージョンと Sdk の間に互換性のある変更があった場合、その変更は [リリースノート][Releasenotes]で指定されます。</span><span class="sxs-lookup"><span data-stu-id="10b49-113">If there are breaking changes between browser versions and SDKs, the changes are specified in the [Release Notes][Releasenotes].</span></span>  

<span data-ttu-id="10b49-114">今後、WebView チームは WebView2 アプリの配布モデルを変更することを計画しています。</span><span class="sxs-lookup"><span data-stu-id="10b49-114">In the future, the WebView team plans to change the distribution model for WebView2 apps.</span></span>  <span data-ttu-id="10b49-115">詳細については、「 [Evergreen 配布モード][DistributionEvergreenMode]に移動する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10b49-115">For more information, navigate to [Evergreen distribution mode][DistributionEvergreenMode].</span></span>  

## <span data-ttu-id="10b49-116">Release パッケージとプレリリースパッケージ</span><span class="sxs-lookup"><span data-stu-id="10b49-116">Release and prerelease package</span></span>  

<span data-ttu-id="10b49-117">[プレビュー] のリリースパッケージには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="10b49-117">In preview, the release package contains the following.</span></span>  

*   <span data-ttu-id="10b49-118">[Win32 C/c + + api][ReferenceWin3209622]: SDK の api であり、GA 時には同じままであると想定されています。</span><span class="sxs-lookup"><span data-stu-id="10b49-118">[Win32 C/C++ APIs][ReferenceWin3209622]: APIs in the SDK that are expected to remain the same at GA.</span></span>  

<span data-ttu-id="10b49-119">プレビューでは、プレリリースパッケージには次のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="10b49-119">In preview, the prerelease package contains the following components.</span></span>  

*   <span data-ttu-id="10b49-120">.NET Api: [WPF][ReferenceWpf09515]、 [WinForms][ReferenceWinforms09515]、および [Core][ReferenceDotnet09628]</span><span class="sxs-lookup"><span data-stu-id="10b49-120">.NET APIs: [WPF][ReferenceWpf09515], [WinForms][ReferenceWinforms09515], and [Core][ReferenceDotnet09628]</span></span>  
*   <span data-ttu-id="10b49-121">実験的な Api。</span><span class="sxs-lookup"><span data-stu-id="10b49-121">Experimental APIs.</span></span>  <span data-ttu-id="10b49-122">詳細については、「 [実験的 api](#experimental-apis) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="10b49-122">For more information, see the [Experimental APIs](#experimental-apis) section.</span></span>  

## <span data-ttu-id="10b49-123">試験的な API</span><span class="sxs-lookup"><span data-stu-id="10b49-123">Experimental APIs</span></span>  

<span data-ttu-id="10b49-124">WebView チームは、将来の機能を示す実験的な Api をテストしています。</span><span class="sxs-lookup"><span data-stu-id="10b49-124">The WebView team is testing experimental APIs that may represent future functionality.</span></span>  <span data-ttu-id="10b49-125">実験的な Api は、SDK で示されてい `experimental` ます。</span><span class="sxs-lookup"><span data-stu-id="10b49-125">The experimental APIs are marked as `experimental` in the SDK.</span></span>  <span data-ttu-id="10b49-126">実験的な Api は、リリースパッケージで完全に安定した Api として出荷される場合があります。</span><span class="sxs-lookup"><span data-stu-id="10b49-126">Experimental APIs may ship as fully stable APIs in the release package.</span></span>  <span data-ttu-id="10b49-127">すべての実験的な Api は、リリース前に変更することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="10b49-127">You should expect all experimental APIs to change before release.</span></span>  <span data-ttu-id="10b49-128">[WebView フィードバックリポジトリ][GithubMicrosoftedgeWebviewfeedback]を使って、実験的な api を評価し、フィードバックを共有してください。</span><span class="sxs-lookup"><span data-stu-id="10b49-128">Please evaluate the Experimental APIs and share feedback using the [WebView feedback repo][GithubMicrosoftedgeWebviewfeedback].</span></span>  

> [!CAUTION]
> <span data-ttu-id="10b49-129">プロダクションアプリで実験的な Api を使うことは避けてください。</span><span class="sxs-lookup"><span data-stu-id="10b49-129">Avoid using the experimental APIs in production apps.</span></span>  

## <span data-ttu-id="10b49-130">WebView2 のランタイムバージョンの一致</span><span class="sxs-lookup"><span data-stu-id="10b49-130">Matching WebView2 Runtime versions</span></span>  

<span data-ttu-id="10b49-131">特定の SDK バージョンを使って WebView2 アプリを作成する場合、ユーザーのアプリのユーザーは、互換性のあるさまざまなバージョンの WebView2 ランタイムでアプリを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="10b49-131">When writing a WebView2 app using a particular SDK version, the users fo you app may run your it with various compatible versions of the WebView2 Runtime.</span></span>  <span data-ttu-id="10b49-132">今後の互換性のある WebView2 ランタイムバージョンには、以前の互換性のある WebView2 ランタイムバージョンと、新しい非実験的な Api 以外の、すべての非実験的な Api が含まれています。</span><span class="sxs-lookup"><span data-stu-id="10b49-132">In the future, a newer compatible WebView2 Runtime version contains all the non-experimental APIs from an older compatible WebView2 Runtime version plus additional new non-experimental APIs.</span></span>  

*   <span data-ttu-id="10b49-133">**Win32 C/c + +** の開発者は、 `QueryInterface` 新しいインターフェイスを取得するためにを使う場合、の戻り値を確認する必要があります `E_NOINTERFACE` 。これは、WebView2 ランタイムが古いため、その特定のインターフェイスがサポートされていないことを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="10b49-133">**Win32 C/C++** developers, when using `QueryInterface` to obtain a new interface, should check for a return value of `E_NOINTERFACE`, which may indicate that the WebView2 Runtime is older and does not support that particular interface.</span></span>  
*   <span data-ttu-id="10b49-134">**.Net と WinUI** の開発者は、 `No such interface supported` WebView2 ランタイムが古い場合や特定の api がサポートされていない場合に発生する可能性がある、後日の sdk で追加されたメソッド、プロパティ、イベントを使用する場合に例外を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10b49-134">**.NET and WinUI** developers should check for a `No such interface supported` exception when using methods, properties, and events added in later SDKs which may occur when the WebView2 Runtime is older and does not support those particular APIs.</span></span>  

<span data-ttu-id="10b49-135">API が利用できない場合は、可能であれば関連する機能を無効にするか、またはエンドユーザーに WebView2 ランタイムバージョンを更新する必要があることを通知することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="10b49-135">If an API is unavailable, consider disabling the associated feature, if possible, or otherwise informing the end user they need to update their WebView2 Runtime version.</span></span>  

<span data-ttu-id="10b49-136">実験的な Api は、SDK から SDK に導入、変更、削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="10b49-136">Experimental APIs may be introduced, modified, and removed from SDK to SDK.</span></span>  <span data-ttu-id="10b49-137">WebView2 ランタイムで利用できない実験的な API を使用しようとすると、先ほど説明したのと同じ動作が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="10b49-137">When attempting to use an experimental API that is not available in the WebView2 Runtime you may observe the same previously described behavior.</span></span>  

## <span data-ttu-id="10b49-138">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="10b49-138">Roadmap</span></span>  

<span data-ttu-id="10b49-139">WebView2 が安定した一般的な状態に達すると、リリースパッケージには、サポートされているすべての安定した Win32 C/c + + + .NET Api が含まれます。</span><span class="sxs-lookup"><span data-stu-id="10b49-139">After WebView2 reaches a stable general available state, the release package contains all of the stable, supported Win32 C/C++ and .NET APIs.</span></span>  <span data-ttu-id="10b49-140">プレリリースパッケージには、フィードバックに基づいて変更される可能性のある実験的な Api が含まれています。</span><span class="sxs-lookup"><span data-stu-id="10b49-140">The prerelease package contains experimental APIs that are subject to change based upon your feedback and shared insights.</span></span>  

<!--## Versioning  

After you have used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.  Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that prevent your SDK from working with different versions of installed browser binaries.  After version 1.0.0.0, different versions of the SDK may work with different versions of the installed browser by using the following best practices.  

1.  To account for breaking changes to the API be sure to check for failure when requesting the DLL export `CreateCoreWebView2Environment` and when running `QueryInterface` on any `CoreWebView2` object.  A return value of `E_NOINTERFACE` indicates that the SDK is not compatible with the Microsoft Edge browser binaries.  
1.  Checking for failure from `QueryInterface` also accounts for cases where the SDK is newer than the version of the Microsoft Edge browser and your app attempts to use an interface of which the Microsoft Edge browser is unaware.  

1.  When an interface is unavailable, you may consider disabling the associated feature if possible, or otherwise informing your users to update their browsers.  -->  

<!--links -->

[DistributionEvergreenMode]: ./distribution.md#evergreen-distribution-mode "Evergreen 配布モード-WebView2 を使用したアプリケーションの配布 |Microsoft ドキュメント"  
[ReferenceDotnet09628]: ../reference/dotnet/0-9-628-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[ReferenceWinforms09515]: ../reference/winforms/0-9-515-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[ReferenceWin3209622]: ../reference/win32/0-9-622-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[ReferenceWpf09515]: ../reference/wpf/0-9-515-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[Releasenotes]: ../releasenotes.md "WebView2 SDK のリリースノート |Microsoft ドキュメント"  

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge チャネルの概要 |Microsoft ドキュメント"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  
