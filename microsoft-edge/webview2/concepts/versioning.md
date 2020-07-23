---
description: Microsoft Edge WebView2 で使用されるバージョン管理モデル
title: Microsoft Edge WebView2 のバージョン管理
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/22/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: acf3103f39d33586ee0614aeb0f10de0ab71c89a
ms.sourcegitcommit: b3555043e9d5aefa5a9e36ba4d73934d41559f49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "10894313"
---
# <span data-ttu-id="dd826-104">WebView2 SDK のバージョンについて</span><span class="sxs-lookup"><span data-stu-id="dd826-104">Understand WebView2 SDK versions</span></span>  

<span data-ttu-id="dd826-105">WebView2 は Microsoft Edge によって異なります。</span><span class="sxs-lookup"><span data-stu-id="dd826-105">WebView2 depends on Microsoft Edge to function.</span></span>  <span data-ttu-id="dd826-106">各 WebView2 SDK では、最小ブラウザーバージョンがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd826-106">Each WebView2 SDK requires that a minimum browser version is installed.</span></span>  <span data-ttu-id="dd826-107">最小バージョンは、SDK のパッケージバージョンに反映されています。</span><span class="sxs-lookup"><span data-stu-id="dd826-107">The minimum version is reflected in the package version of the SDK.</span></span>  <span data-ttu-id="dd826-108">たとえば、を使用する場合は、 `SDK package version 0.9.488` 488 以降のビルド番号で Microsoft Edge をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd826-108">For example, if you use the `SDK package version 0.9.488`, then you must install Microsoft Edge with a build number of 488 or later.</span></span>  <span data-ttu-id="dd826-109">ブラウザーのバージョンも、WebView2 の[リリースノート][Releasenotes]で指定されています。</span><span class="sxs-lookup"><span data-stu-id="dd826-109">The browser version is also specified in the WebView2 [Release Notes][Releasenotes].</span></span>  <span data-ttu-id="dd826-110">ブラウザーの最新リリースの詳細については、「[ブラウザーチャネル][DeployedgeChannels]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd826-110">For more information on the latest releases of the browser, see [Browser Channels][DeployedgeChannels].</span></span>  

> [!NOTE]
> <span data-ttu-id="dd826-111">WebView2 は現在、プレビューに表示されています。</span><span class="sxs-lookup"><span data-stu-id="dd826-111">WebView2 is currently in preview.</span></span>  <span data-ttu-id="dd826-112">WebView チームは、ブラウザーのバージョンと Sdk の間の下位互換性を確保することを目的としていますが、新しいバージョンのブラウザーでは以前の SDK バージョンがサポートされていない可能性があるため、これは保証されません。</span><span class="sxs-lookup"><span data-stu-id="dd826-112">While the WebView team strives to ensure backward compatibility between browser versions and SDKs, it is not guaranteed because newer versions of the browser may not support previous SDK versions.</span></span>  <span data-ttu-id="dd826-113">ブラウザーのバージョンと Sdk の間に互換性のある変更がある場合は、[リリースノート][Releasenotes]で変更を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd826-113">If there are breaking changes between browser versions and SDKs, we specify the changes in the [Release Notes][Releasenotes].</span></span>  

<span data-ttu-id="dd826-114">今後、WebView2 アプリケーションの配布モデルを変更する予定です。</span><span class="sxs-lookup"><span data-stu-id="dd826-114">In the future, we plan to change the distribution model for WebView2 applications.</span></span>  <span data-ttu-id="dd826-115">詳細については、「 [Evergreen 配布モード][DistributionEvergreenMode]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd826-115">For more information, see [Evergreen distribution mode][DistributionEvergreenMode].</span></span>  
 
## <span data-ttu-id="dd826-116">リリースとプレリリース版のパッケージ</span><span class="sxs-lookup"><span data-stu-id="dd826-116">Release and pre-release package</span></span>  

<span data-ttu-id="dd826-117">[プレビュー] のリリースパッケージには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dd826-117">In preview, the release package contains the following.</span></span>  

*   <span data-ttu-id="dd826-118">[Win32 C/c + + api][ReferenceWin3209538]: SDK の api であり、GA 時には同じままであると想定されています。</span><span class="sxs-lookup"><span data-stu-id="dd826-118">[Win32 C/C++ APIs][ReferenceWin3209538]: APIs in the SDK that are expected to remain the same at GA.</span></span>  

<span data-ttu-id="dd826-119">プレビューでは、プレリリースパッケージには次のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dd826-119">In preview, the pre-release package contains the following components.</span></span>  

*   <span data-ttu-id="dd826-120">.NET Api: [WPF][ReferenceWpf09515]、 [WinForms][ReferenceWinforms09515]、および[Core][ReferenceDotnet09538]</span><span class="sxs-lookup"><span data-stu-id="dd826-120">.NET APIs: [WPF][ReferenceWpf09515], [WinForms][ReferenceWinforms09515], and [Core][ReferenceDotnet09538]</span></span>  
*   <span data-ttu-id="dd826-121">実験的な Api。</span><span class="sxs-lookup"><span data-stu-id="dd826-121">Experimental APIs.</span></span>  <span data-ttu-id="dd826-122">詳細については、「[実験的 api](#experimental-apis) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd826-122">For more information, see the [Experimental APIs](#experimental-apis) section.</span></span>  

## <span data-ttu-id="dd826-123">試験的な API</span><span class="sxs-lookup"><span data-stu-id="dd826-123">Experimental APIs</span></span>  

<span data-ttu-id="dd826-124">今後の機能を表す実験的な Api をテストしています。</span><span class="sxs-lookup"><span data-stu-id="dd826-124">We are testing experimental APIs that may represent future functionality.</span></span>  <span data-ttu-id="dd826-125">実験的な Api は、SDK で示されてい `experimental` ます。</span><span class="sxs-lookup"><span data-stu-id="dd826-125">The experimental APIs are marked as `experimental` in the SDK.</span></span>  <span data-ttu-id="dd826-126">実験的な Api は、リリースパッケージで完全に安定した Api として出荷される場合があります。</span><span class="sxs-lookup"><span data-stu-id="dd826-126">Experimental APIs may ship as fully stable APIs in the release package.</span></span>  <span data-ttu-id="dd826-127">すべての実験的な Api は、リリース前に変更することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="dd826-127">You should expect all experimental APIs to change before release.</span></span>  <span data-ttu-id="dd826-128">[WebView フィードバックリポジトリ][GithubMicrosoftedgeWebviewfeedback]を使って、実験的な api を評価し、フィードバックを共有してください。</span><span class="sxs-lookup"><span data-stu-id="dd826-128">Please evaluate the Experimental APIs and share feedback using the [WebView feedback repo][GithubMicrosoftedgeWebviewfeedback].</span></span>   

> [!CAUTION]
> <span data-ttu-id="dd826-129">プロダクションアプリケーションで実験的な Api を使うことは避けてください。</span><span class="sxs-lookup"><span data-stu-id="dd826-129">Avoid using the experimental APIs in production applications.</span></span>  

## <span data-ttu-id="dd826-130">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="dd826-130">Roadmap</span></span>  

<span data-ttu-id="dd826-131">WebView2 が安定した一般的な状態に達すると、リリースパッケージには、サポートされているすべての安定した Win32 C/c + + + .NET Api が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dd826-131">After WebView2 reaches a stable general available state, the release package contains all of the stable, supported Win32 C/C++ and .NET APIs.</span></span>  <span data-ttu-id="dd826-132">プレリリースパッケージには、開発者のフィードバックおよび共有の分析に基づいて変更される実験的な Api が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dd826-132">The pre-release package contains experimental APIs that are subject to change based upon developer feedback and shared insights.</span></span>  

<!--## Versioning  

After you have used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.  Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that prevent your SDK from working with different versions of installed browser binaries.  After version 1.0.0.0, different versions of the SDK may work with different versions of the installed browser by using the following best practices.  

1.  To account for breaking changes to the API be sure to check for failure when requesting the DLL export `CreateCoreWebView2Environment` and when running `QueryInterface` on any `CoreWebView2` object.  A return value of `E_NOINTERFACE` indicates that the SDK is not compatible with the Microsoft Edge browser binaries.  
1.  Checking for failure from `QueryInterface` also accounts for cases where the SDK is newer than the version of the Microsoft Edge browser and your app attempts to use an interface of which the Microsoft Edge browser is unaware.  

1.  When an interface is unavailable, you may consider disabling the associated feature if possible, or otherwise informing your users to update their browsers.  -->  

<!--links -->

[DistributionEvergreenMode]: ./distribution.md#evergreen-distribution-mode "Evergreen 配布モード-WebView2 を使用したアプリケーションの配布 |Microsoft ドキュメント"  
[ReferenceDotnet09538]: ../reference/dotnet/0-9-538-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[ReferenceWinforms09515]: ../reference/winforms/0-9-515-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[ReferenceWin3209538]: ../reference/win32/0-9-538-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[ReferenceWpf09515]: ../reference/wpf/0-9-515-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[Releasenotes]: ../releasenotes.md "WebView2 SDK のリリースノート |Microsoft ドキュメント"  

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge チャネルの概要 |Microsoft ドキュメント"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  
