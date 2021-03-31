---
description: WebView2 アプリケーションを管理する方法を理解する
title: WebView2 アプリケーションを管理する
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/21/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html、enterprise、グループポリシー、管理性
ms.openlocfilehash: 1eb8b9dc1637daa8d10004ab8c340fe9ae33e38b
ms.sourcegitcommit: 24151cc65bad92d751a8e7a868c102e1121456e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "11057864"
---
# <span data-ttu-id="95b61-104">WebView2 アプリケーションを管理する</span><span class="sxs-lookup"><span data-stu-id="95b61-104">Managing WebView2 applications</span></span>  

<span data-ttu-id="95b61-105">[WebView2][WebView2Landing] は、開発者がアプリケーションを構築するために使用するコンポーネントであり、開発者は、ユーザーデバイスで [自己更新 Evergreen WebView2 ランタイム][Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview] を展開して、アプリの電源を入れている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="95b61-105">[WebView2][WebView2Landing] is a component that developers use to build their applications, and the developers may deploy a [self-updating Evergreen WebView2 Runtime][Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview] on user device to power their applications.</span></span>  <span data-ttu-id="95b61-106">このドキュメントでは、IT 管理者が WebView2 アプリケーションとランタイムを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="95b61-106">This document discusses how IT admins may manage WebView2 applications and Runtime.</span></span>  <span data-ttu-id="95b61-107">IT の管理者と開発者の両方からのフィードバックは、 [WebView2 フィードバックリポジトリ][GithubMicrosoftedgeWebviewfeddback]で歓迎されます。</span><span class="sxs-lookup"><span data-stu-id="95b61-107">Feedback from both IT admins and developers is welcome on [WebView2 Feedback repo][GithubMicrosoftedgeWebviewfeddback].</span></span>  

## <span data-ttu-id="95b61-108">WebView2 のグループポリシー</span><span class="sxs-lookup"><span data-stu-id="95b61-108">Group policies for WebView2</span></span>  

<span data-ttu-id="95b61-109">IT 管理者は、グループポリシーオブジェクト \(GPO \) を使って、WebView2 のポリシー設定を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="95b61-109">IT admins may use group policy objects \(GPO\) to configure policy settings for WebView2.</span></span>  <span data-ttu-id="95b61-110">次のポリシーセットは、WebView2 には適用されません。</span><span class="sxs-lookup"><span data-stu-id="95b61-110">The following set of policies are/are not applicable to WebView2,</span></span>  

*   <span data-ttu-id="95b61-111">[Microsoft Edge-更新ポリシー][EdgeUpdatePolicies] は、IT 管理者が WebView2 ランタイムのインストールと更新の側面を管理するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="95b61-111">[Microsoft Edge - Update policies][EdgeUpdatePolicies] are available for IT admins to manage the install and update aspects of the WebView2 Runtime.</span></span>  <span data-ttu-id="95b61-112">Microsoft Edge ブラウザーと WebView2 ランタイムは、同じ更新メカニズムを使用して更新されます。</span><span class="sxs-lookup"><span data-stu-id="95b61-112">The Microsoft Edge browser and WebView2 Runtime are updated using the same update mechanism.</span></span>  <span data-ttu-id="95b61-113">などのポリシーがチャネル固有のものである場合 `Update` を除き、ブラウザーと WebView2 の両方のランタイムに適用されます。</span><span class="sxs-lookup"><span data-stu-id="95b61-113">Unless a policy, such as `Update`, is channel-specific, it applies to both the browser and WebView2 Runtime.</span></span>  <span data-ttu-id="95b61-114">たとえば、 `UpdateSuppressed` IT 管理者は、ブラウザーと WebView2 の両方のランタイムの自動更新を非表示にするように、その日の間に時間を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="95b61-114">For example, `UpdateSuppressed` allows IT admins to set time during each day to suppress auto-update for both the browser and WebView2 Runtime.</span></span>  <span data-ttu-id="95b61-115">これにより、IT 管理者は、ブラウザーと WebView2 ランタイムの両方に対して1回設定とプロキシを構成し、ネットワーク帯域幅やトラフィックを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="95b61-115">This enables IT admins to configure preferences and proxies once for both the browser and WebView2 Runtime to control their network bandwidth/traffic or for other purposes.</span></span>  <span data-ttu-id="95b61-116">IT 管理者は [microsoft edge のガイド][ConfigureMicrosoftEdge] に従って Microsoft edge 更新ポリシーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="95b61-116">IT admins may follow [Microsoft Edge's guide][ConfigureMicrosoftEdge] to configure Microsoft Edge - Update policies.</span></span>  
*   <span data-ttu-id="95b61-117">[Microsoft Edge-ブラウザーのポリシーは、][EdgeBrowserPolicies] WebView2 アプリケーションには適用されません。</span><span class="sxs-lookup"><span data-stu-id="95b61-117">[Microsoft Edge - Browser policies][EdgeBrowserPolicies] doesn't apply to WebView2 applications.</span></span>  <span data-ttu-id="95b61-118">これは、アプリとブラウザーがさまざまなユースケースを持つため、IT 管理者が WebView2 を使用するアプリケーションを認識しない場合があるためです。</span><span class="sxs-lookup"><span data-stu-id="95b61-118">This is by design because apps and browsers have different use cases, and IT admins may not be aware of what applications use WebView2.</span></span>  <span data-ttu-id="95b61-119">WebView2 にブラウザーポリシーを適用すると、意図しない結果が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="95b61-119">Applying browser policies on WebView2 may have unintended consequences.</span></span>  <span data-ttu-id="95b61-120">たとえば、IT 管理者がブラウザーで JavaScript をブロックし、JavaScript を使っているすべての WebView2 アプリが壊れていることがあります。</span><span class="sxs-lookup"><span data-stu-id="95b61-120">For example, IT admins may block JavaScript in the browser and all WebView2 apps using JavaScript are broken.</span></span>  
*   <span data-ttu-id="95b61-121">\(近日中に) WebView2 固有のポリシー– WebView2 では、WebView2 の直接管理が適切である場合に、グループポリシーの小さな追加セットが公開されます。</span><span class="sxs-lookup"><span data-stu-id="95b61-121">\(Coming soon\) WebView2-specific policies – WebView2 will expose a small additional set of group policies in cases where managing WebView2 directly makes sense.</span></span>  <span data-ttu-id="95b61-122">アプリの開発者は、WebView2 の使用を管理するために、独自のグループポリシーを実装することをお勧めします。 IT 管理者は、WebView2 ではなく、アプリを直接管理できます。</span><span class="sxs-lookup"><span data-stu-id="95b61-122">We recommend app developers to implement their own group policies to manage their use of WebView2, as it is more straightforward for IT admins to manage the app rather than WebView2 directly.</span></span>  

<!-- Links -->  

[Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview]: ./distribution.md#understanding-the-webview2-runtime "WebView2 Runtime と installer (Preview) を使ったアプリケーションの配布について WebView2 |Microsoft ドキュメント"  

[WebView2Landing]: ../index.md "Microsoft Edge WebView2 の概要 (プレビュー) |Microsoft ドキュメント"  

[EdgeUpdatePolicies]: /deployedge/microsoft-edge-update-policies "Microsoft Edge-更新プログラムのポリシー |Microsoft ドキュメント"  
[EdgeBrowserPolicies]: /deployedge/microsoft-edge-policies "Microsoft Edge-ブラウザーのポリシー |Microsoft ドキュメント"  
[ConfigureMicrosoftEdge]: /deployedge/configure-microsoft-edge "Windows で Microsoft Edge のポリシー設定を構成するMicrosoft ドキュメント"  


[GithubMicrosoftedgeWebviewfeddback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  
