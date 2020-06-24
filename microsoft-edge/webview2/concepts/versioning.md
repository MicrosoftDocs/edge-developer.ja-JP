---
description: Microsoft Edge WebView2 で使用されるバージョン管理モデル
title: Microsoft Edge WebView2 のバージョン管理
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/22/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf アプリ、wpf、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 3862576134d1179fb24b2ce865f705b2bf1db8a6
ms.sourcegitcommit: de171a8e7ccd9f23846f3cd06519e4a0104f1c52
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "10757607"
---
# <span data-ttu-id="ec127-104">WebView2 SDK のバージョンについて</span><span class="sxs-lookup"><span data-stu-id="ec127-104">Understand WebView2 SDK versions</span></span>  

<span data-ttu-id="ec127-105">WebView2 は Microsoft Edge によって異なります。</span><span class="sxs-lookup"><span data-stu-id="ec127-105">WebView2 depends on Microsoft Edge to function.</span></span> <span data-ttu-id="ec127-106">各 WebView2 SDK では、最小ブラウザーバージョンがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec127-106">Each WebView2 SDK requires that a minimum browser version is installed.</span></span>  <span data-ttu-id="ec127-107">最小バージョンは、SDK のパッケージバージョンに反映されています。</span><span class="sxs-lookup"><span data-stu-id="ec127-107">The minimum version is reflected in the package version of the SDK.</span></span>  <span data-ttu-id="ec127-108">たとえば、を使用する場合は、 `SDK package version 0.9.488` 488 以降のビルド番号で Microsoft Edge をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec127-108">For example, if you use the `SDK package version 0.9.488`, then you must install Microsoft Edge with a build number of 488 or later.</span></span> <span data-ttu-id="ec127-109">ブラウザーのバージョンも、WebView2 の[リリースノート][Webview2Releasenotes]で指定されています。</span><span class="sxs-lookup"><span data-stu-id="ec127-109">The browser version is also specified in the WebView2 [Release Notes][Webview2Releasenotes].</span></span>  <span data-ttu-id="ec127-110">ブラウザーの最新リリースの詳細については、「[ブラウザーチャネル][DeployedgeChannels]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec127-110">For more information on the latest releases of the browser, see [Browser Channels][DeployedgeChannels].</span></span>  

> [!NOTE]
> <span data-ttu-id="ec127-111">WebView2 は現在、プレビューに表示されています。</span><span class="sxs-lookup"><span data-stu-id="ec127-111">WebView2 is currently in preview.</span></span>  <span data-ttu-id="ec127-112">Microsoft Edge WebView チームは、ブラウザーバージョンと Sdk 間の下位互換性を確保するために努力していますが、ブラウザーの新しいバージョンによっては、古いバージョンの SDK がサポートされていない可能性があることを保証していません。</span><span class="sxs-lookup"><span data-stu-id="ec127-112">While, the Microsoft Edge WebView team strives to ensure backward compatibility between browser versions and SDKs, it is not guaranteed as some newer versions of the browser may not support older SDK versions.</span></span>  <span data-ttu-id="ec127-113">ブラウザーのバージョンと Sdk の間に互換性のある変更がある場合は、Microsoft Edge WebView チームで[リリースノート][Webview2Releasenotes]の変更が指定されます。</span><span class="sxs-lookup"><span data-stu-id="ec127-113">If there are breaking changes between browser versions and SDKs, the Microsoft Edge WebView team specifies the changes in the [release notes][Webview2Releasenotes].</span></span>  

<span data-ttu-id="ec127-114">今後、WebView2 アプリケーションの配布モデルが変更されます。</span><span class="sxs-lookup"><span data-stu-id="ec127-114">In the future, the distribution model for WebView2 applications will change.</span></span> <span data-ttu-id="ec127-115">詳細については、「 [WebView2 Runtime][Webview2IndexEdgeRuntime]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec127-115">For more information, see [WebView2 Runtime][Webview2IndexEdgeRuntime].</span></span>  
 
## <span data-ttu-id="ec127-116">リリースとプレリリース版のパッケージ</span><span class="sxs-lookup"><span data-stu-id="ec127-116">Release and pre-release package</span></span>  

<span data-ttu-id="ec127-117">[プレビュー] のリリースパッケージには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ec127-117">In preview, the release package contains the following.</span></span>  

*   <span data-ttu-id="ec127-118">[Win32 C/c + + api][Webview2ReferenceWin3209538]: SDK の api であり、GA 時には同じままであると想定されています。</span><span class="sxs-lookup"><span data-stu-id="ec127-118">[Win32 C/C++ APIs][Webview2ReferenceWin3209538]: APIs in the SDK that are expected to remain the same at GA.</span></span> 

<span data-ttu-id="ec127-119">プレビューでは、プレリリースパッケージには以下が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ec127-119">In preview, the pre-release package contains the following.</span></span>  

*   <span data-ttu-id="ec127-120">.NET Api: [WPF][Webview2ReferenceWpf09515]、 [WinForms][Webview2ReferenceWinforms09515]、および[Core][Webview2ReferenceDotnet09538]</span><span class="sxs-lookup"><span data-stu-id="ec127-120">.NET APIs: [WPF][Webview2ReferenceWpf09515], [WinForms][Webview2ReferenceWinforms09515], and [Core][Webview2ReferenceDotnet09538]</span></span>
*   <span data-ttu-id="ec127-121">実験的な Api。</span><span class="sxs-lookup"><span data-stu-id="ec127-121">Experimental APIs.</span></span>  <span data-ttu-id="ec127-122">詳細については、「 [Experimantal api](#experimental-apis) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec127-122">For more information, see the [Experimantal APIs](#experimental-apis) section.</span></span>  

### <span data-ttu-id="ec127-123">試験的な API</span><span class="sxs-lookup"><span data-stu-id="ec127-123">Experimental APIs</span></span>  

<span data-ttu-id="ec127-124">WebView チームは、実験的な Api という名前の将来の機能を表す Api をテストしています。</span><span class="sxs-lookup"><span data-stu-id="ec127-124">The WebView Team is testing APIs that represent future functionality named Experimental APIs.</span></span>  <span data-ttu-id="ec127-125">実験的な Api は、SDK で示されてい `experimental` ます。</span><span class="sxs-lookup"><span data-stu-id="ec127-125">The Experimental APIs are marked as `experimental` in the SDK.</span></span>  <span data-ttu-id="ec127-126">一部の実験的な Api は、リリースパッケージで完全に安定した Api として配布される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ec127-126">Some Experimental APIs may ship as fully stable APIs in the release package.</span></span>  <span data-ttu-id="ec127-127">すべての実験的な Api は、リリース前に変更することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="ec127-127">You should expect all experimental APIs to change before release.</span></span>  <span data-ttu-id="ec127-128">[WebView フィードバックリポジトリ][GithubMicrosoftedgeWebviewfeedback]を使って、実験的な api を評価し、フィードバックを共有してください。</span><span class="sxs-lookup"><span data-stu-id="ec127-128">Please evaluate the Experimental APIs and share feedback using the [WebView feedback repo][GithubMicrosoftedgeWebviewfeedback].</span></span>   

> [!CAUTION]
> <span data-ttu-id="ec127-129">プロダクションアプリケーションで実験的な Api を使うことは避けてください。</span><span class="sxs-lookup"><span data-stu-id="ec127-129">Avoid using the experimental APIs in production applications.</span></span>  

### <span data-ttu-id="ec127-130">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="ec127-130">Roadmap</span></span>  

<span data-ttu-id="ec127-131">WebView2 が安定した一般的な状態に達すると、リリースパッケージには、サポートされているすべての安定した Win32 C/c + + + .NET Api が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ec127-131">After WebView2 reaches a stable general available state, the release package contains all of the stable, supported Win32 C/C++ and .NET APIs.</span></span>  <span data-ttu-id="ec127-132">プレリリースパッケージには、開発者のフィードバックおよび共有の分析に基づいて変更される実験的な Api が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ec127-132">The pre-release package contains experimental APIs that are subject to change based upon developer feedback and shared insights.</span></span>  

<!--links -->

[Webview2IndexEdgeRuntime]: ./distribution.md#microsoft-edge-webview2-runtime "Microsoft Edge WebView2 Runtime-WebView2 を使用したアプリケーションの配布 |Microsoft ドキュメント"  
[Webview2ReferenceDotnet09538]: ../reference/dotnet/0-9-538-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[Webview2ReferenceWinforms09515]: ../reference/winforms/0-9-515-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[Webview2ReferenceWin3209538]: ../reference/win32/0-9-538-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[Webview2ReferenceWpf09515]: ../reference/wpf/0-9-515-reference-webview2.md "Reference (WebView2) |Microsoft ドキュメント"  
[Webview2Releasenotes]: ../releasenotes.md "WebView2 SDK のリリースノート |Microsoft ドキュメント"  

[DeployedgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge チャネルの概要 |Microsoft ドキュメント"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  
