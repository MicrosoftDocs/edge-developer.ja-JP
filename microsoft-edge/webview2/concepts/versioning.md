---
description: Microsoft Edge WebView2 で使用されるバージョン管理モデル
title: Microsoft Edge WebView2 のバージョン管理
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 059bbeb34f372af0cef944e484599c0b50543cc9
ms.sourcegitcommit: 288bd2a1bec418a84d1f0bda013c1913886bd269
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "10844426"
---
# <span data-ttu-id="f153f-104">WebView2 SDK のバージョンについて</span><span class="sxs-lookup"><span data-stu-id="f153f-104">Understand WebView2 SDK versions</span></span>  

<span data-ttu-id="f153f-105">WebView2 は Microsoft Edge によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f153f-105">WebView2 depends on Microsoft Edge to function.</span></span>  <span data-ttu-id="f153f-106">各 WebView2 SDK では、最小ブラウザーバージョンがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f153f-106">Each WebView2 SDK requires that a minimum browser version is installed.</span></span>  <span data-ttu-id="f153f-107">最小バージョンは、SDK のパッケージバージョンに反映されています。</span><span class="sxs-lookup"><span data-stu-id="f153f-107">The minimum version is reflected in the package version of the SDK.</span></span>  <span data-ttu-id="f153f-108">たとえば、を使用する場合は、 `SDK package version 0.9.488` 488 以降のビルド番号で Microsoft Edge をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f153f-108">For example, if you use the `SDK package version 0.9.488`, then you must install Microsoft Edge with a build number of 488 or later.</span></span>  <span data-ttu-id="f153f-109">ブラウザーのバージョンも、WebView2 の[リリースノート][Releasenotes]で指定されています。</span><span class="sxs-lookup"><span data-stu-id="f153f-109">The browser version is also specified in the WebView2 [Release Notes][Releasenotes].</span></span>  <span data-ttu-id="f153f-110">ブラウザーの最新リリースの詳細については、「[ブラウザーチャネル][DeployedgeChannels]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f153f-110">For more information on the latest releases of the browser, see [Browser Channels][DeployedgeChannels].</span></span>  

> [!NOTE]
> <span data-ttu-id="f153f-111">WebView2 は現在、プレビューに表示されています。</span><span class="sxs-lookup"><span data-stu-id="f153f-111">WebView2 is currently in preview.</span></span>  <span data-ttu-id="f153f-112">WebView チームは、ブラウザーのバージョンと Sdk の下位互換性を確保するために努力していますが、新しいバージョンのブラウザーでは旧バージョンの SDK がサポートされていない可能性があるため、これは保証されていません。</span><span class="sxs-lookup"><span data-stu-id="f153f-112">While the WebView team strives to ensure backward compatibility between browser versions and SDKs, it is not guaranteed since newer versions of the browser may not support older SDK versions.</span></span>  <span data-ttu-id="f153f-113">ブラウザーのバージョンと Sdk の間に互換性のある変更がある場合、WebView チームで[リリースノート][Releasenotes]の変更を指定します。</span><span class="sxs-lookup"><span data-stu-id="f153f-113">If there are breaking changes between browser versions and SDKs, the WebView team specifies the changes in the [release notes][Releasenotes].</span></span>  

<span data-ttu-id="f153f-114">今後、WebView チームは WebView2 アプリケーションの配布モデルを変更することを計画しています。</span><span class="sxs-lookup"><span data-stu-id="f153f-114">In the future, the  WebView team plans to change the distribution model for WebView2 applications.</span></span>  <span data-ttu-id="f153f-115">詳細については、「 [Evergreen 配布モード][DistributionEvergreenMode]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f153f-115">For more information, see see [Evergreen distribution mode][DistributionEvergreenMode].</span></span>  
 
## <span data-ttu-id="f153f-116">リリースとプレリリース版のパッケージ</span><span class="sxs-lookup"><span data-stu-id="f153f-116">Release and pre-release package</span></span>  

<span data-ttu-id="f153f-117">[プレビュー] のリリースパッケージには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f153f-117">In preview, the release package contains the following.</span></span>  

*   <span data-ttu-id="f153f-118">[Win32 C/c + + api][ReferenceWin3209538]: SDK の api であり、GA 時には同じままであると想定されています。</span><span class="sxs-lookup"><span data-stu-id="f153f-118">[Win32 C/C++ APIs][ReferenceWin3209538]: APIs in the SDK that are expected to remain the same at GA.</span></span> 

<span data-ttu-id="f153f-119">プレビューでは、プレリリースパッケージには次のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f153f-119">In preview, the pre-release package contains the following components.</span></span>  

*   <span data-ttu-id="f153f-120">.NET Api: [WPF][ReferenceWpf09515]、 [WinForms][ReferenceWinforms09515]、および[Core][ReferenceDotnet09538]</span><span class="sxs-lookup"><span data-stu-id="f153f-120">.NET APIs: [WPF][ReferenceWpf09515], [WinForms][ReferenceWinforms09515], and [Core][ReferenceDotnet09538]</span></span>
*   <span data-ttu-id="f153f-121">実験的な Api。</span><span class="sxs-lookup"><span data-stu-id="f153f-121">Experimental APIs.</span></span>  <span data-ttu-id="f153f-122">詳細については、「[実験的 api](#experimental-apis) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f153f-122">For more information, see the [Experimental APIs](#experimental-apis) section.</span></span>  

### <span data-ttu-id="f153f-123">試験的な API</span><span class="sxs-lookup"><span data-stu-id="f153f-123">Experimental APIs</span></span>  

<span data-ttu-id="f153f-124">WebView チームは、実験的な Api という名前の将来の機能を表す Api をテストしています。</span><span class="sxs-lookup"><span data-stu-id="f153f-124">The WebView Team is testing APIs that represent future functionality named Experimental APIs.</span></span>  <span data-ttu-id="f153f-125">実験的な Api は、SDK で示されてい `experimental` ます。</span><span class="sxs-lookup"><span data-stu-id="f153f-125">The Experimental APIs are marked as `experimental` in the SDK.</span></span>  <span data-ttu-id="f153f-126">一部の実験的な Api は、リリースパッケージで完全に安定した Api として配布される場合があります。</span><span class="sxs-lookup"><span data-stu-id="f153f-126">Some Experimental APIs may ship as fully stable APIs in the release package.</span></span>  <span data-ttu-id="f153f-127">すべての実験的な Api は、リリース前に変更することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="f153f-127">You should expect all experimental APIs to change before release.</span></span>  <span data-ttu-id="f153f-128">[WebView フィードバックリポジトリ][GithubMicrosoftedgeWebviewfeedback]を使って、実験的な api を評価し、フィードバックを共有してください。</span><span class="sxs-lookup"><span data-stu-id="f153f-128">Please evaluate the Experimental APIs and share feedback using the [WebView feedback repo][GithubMicrosoftedgeWebviewfeedback].</span></span>   

> [!CAUTION]
> <span data-ttu-id="f153f-129">プロダクションアプリケーションで実験的な Api を使うことは避けてください。</span><span class="sxs-lookup"><span data-stu-id="f153f-129">Avoid using the experimental APIs in production applications.</span></span>  

### <span data-ttu-id="f153f-130">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="f153f-130">Roadmap</span></span>  

<span data-ttu-id="f153f-131">WebView2 が安定した一般的な状態に達すると、リリースパッケージには、サポートされているすべての安定した Win32 C/c + + + .NET Api が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f153f-131">After WebView2 reaches a stable general available state, the release package contains all of the stable, supported Win32 C/C++ and .NET APIs.</span></span>  <span data-ttu-id="f153f-132">プレリリースパッケージには、開発者のフィードバックおよび共有の分析に基づいて変更される実験的な Api が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f153f-132">The pre-release package contains experimental APIs that are subject to change based upon developer feedback and shared insights.</span></span>  

<!--links -->

[DistributionEvergreenMode]: ./distribution.md#evergreen-distribution-mode "Evergreen 配布モード-WebView2 を使用したアプリケーションの配布 |Microsoft ドキュメント"  
[ReferenceDotnet09538]: ../reference/dotnet/0-9-538-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[ReferenceWinforms09515]: ../reference/winforms/0-9-515-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[ReferenceWin3209538]: ../reference/win32/0-9-538-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[ReferenceWpf09515]: ../reference/wpf/0-9-515-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[Releasenotes]: ../releasenotes.md "WebView2 SDK のリリースノート |Microsoft ドキュメント"  

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge チャネルの概要 |Microsoft ドキュメント"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  
