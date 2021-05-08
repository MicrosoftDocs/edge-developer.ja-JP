---
description: WebView2 アプリケーションを管理する方法を理解する
title: WebView2 アプリケーションの管理
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/21/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、Webview2、Webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、エッジ HTML、エンタープライズ、グループ ポリシー、管理性
ms.openlocfilehash: 1eb8b9dc1637daa8d10004ab8c340fe9ae33e38b
ms.sourcegitcommit: 24151cc65bad92d751a8e7a868c102e1121456e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "11057864"
---
# <span data-ttu-id="84851-104">WebView2 アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="84851-104">Managing WebView2 applications</span></span>  

<span data-ttu-id="84851-105">[WebView2][WebView2Landing] は、開発者がアプリケーションのビルドに使用するコンポーネントであり、開発者はアプリケーションに電力を供給するために、ユーザー デバイスに自己更新 [の Evergreen WebView2 ランタイム][Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview] を展開できます。</span><span class="sxs-lookup"><span data-stu-id="84851-105">[WebView2][WebView2Landing] is a component that developers use to build their applications, and the developers may deploy a [self-updating Evergreen WebView2 Runtime][Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview] on user device to power their applications.</span></span>  <span data-ttu-id="84851-106">このドキュメントでは、IT 管理者が WebView2 アプリケーションとランタイムを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="84851-106">This document discusses how IT admins may manage WebView2 applications and Runtime.</span></span>  <span data-ttu-id="84851-107">WEBView2 Feedback repo では、IT 管理者と開発者 [の両方からのフィードバックを歓迎します][GithubMicrosoftedgeWebviewfeddback]。</span><span class="sxs-lookup"><span data-stu-id="84851-107">Feedback from both IT admins and developers is welcome on [WebView2 Feedback repo][GithubMicrosoftedgeWebviewfeddback].</span></span>  

## <span data-ttu-id="84851-108">WebView2 のグループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="84851-108">Group policies for WebView2</span></span>  

<span data-ttu-id="84851-109">IT 管理者は、グループ ポリシー オブジェクト \(GPO\) を使用して WebView2 のポリシー設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="84851-109">IT admins may use group policy objects \(GPO\) to configure policy settings for WebView2.</span></span>  <span data-ttu-id="84851-110">次の一連のポリシーは、WebView2 には適用できません。</span><span class="sxs-lookup"><span data-stu-id="84851-110">The following set of policies are/are not applicable to WebView2,</span></span>  

*   <span data-ttu-id="84851-111">[Microsoft Edge -][EdgeUpdatePolicies]更新ポリシーは、IT 管理者が WebView2 ランタイムのインストールおよび更新の側面を管理するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="84851-111">[Microsoft Edge - Update policies][EdgeUpdatePolicies] are available for IT admins to manage the install and update aspects of the WebView2 Runtime.</span></span>  <span data-ttu-id="84851-112">ブラウザー Microsoft Edge WebView2 ランタイムは、同じ更新メカニズムを使用して更新されます。</span><span class="sxs-lookup"><span data-stu-id="84851-112">The Microsoft Edge browser and WebView2 Runtime are updated using the same update mechanism.</span></span>  <span data-ttu-id="84851-113">チャネル固有のポリシーがない限り、ブラウザーと `Update` WebView2 ランタイムの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="84851-113">Unless a policy, such as `Update`, is channel-specific, it applies to both the browser and WebView2 Runtime.</span></span>  <span data-ttu-id="84851-114">たとえば、IT 管理者は、ブラウザーと WebView2 ランタイムの両方の自動更新を抑制するために、毎日の時間を `UpdateSuppressed` 設定できます。</span><span class="sxs-lookup"><span data-stu-id="84851-114">For example, `UpdateSuppressed` allows IT admins to set time during each day to suppress auto-update for both the browser and WebView2 Runtime.</span></span>  <span data-ttu-id="84851-115">これにより、IT 管理者は、ブラウザーと WebView2 ランタイムの両方の設定とプロキシを 1 回構成して、ネットワーク帯域幅/トラフィックを制御したり、その他の目的で構成することができます。</span><span class="sxs-lookup"><span data-stu-id="84851-115">This enables IT admins to configure preferences and proxies once for both the browser and WebView2 Runtime to control their network bandwidth/traffic or for other purposes.</span></span>  <span data-ttu-id="84851-116">IT 管理者は、Microsoft Edge[の][ConfigureMicrosoftEdge]ガイドに従って、Microsoft Edgeポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="84851-116">IT admins may follow [Microsoft Edge's guide][ConfigureMicrosoftEdge] to configure Microsoft Edge - Update policies.</span></span>  
*   <span data-ttu-id="84851-117">[Microsoft Edge - ブラウザー ポリシー][EdgeBrowserPolicies]は WebView2 アプリケーションには適用されません。</span><span class="sxs-lookup"><span data-stu-id="84851-117">[Microsoft Edge - Browser policies][EdgeBrowserPolicies] doesn't apply to WebView2 applications.</span></span>  <span data-ttu-id="84851-118">これは、アプリとブラウザーの使用例が異なって、IT 管理者が WebView2 を使用するアプリケーションを認識していない可能性があるからです。</span><span class="sxs-lookup"><span data-stu-id="84851-118">This is by design because apps and browsers have different use cases, and IT admins may not be aware of what applications use WebView2.</span></span>  <span data-ttu-id="84851-119">WebView2 にブラウザー ポリシーを適用すると、意図しない結果が生じ得る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="84851-119">Applying browser policies on WebView2 may have unintended consequences.</span></span>  <span data-ttu-id="84851-120">たとえば、IT 管理者はブラウザーで JavaScript をブロックし、JavaScript を使用しているすべての WebView2 アプリが壊れている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="84851-120">For example, IT admins may block JavaScript in the browser and all WebView2 apps using JavaScript are broken.</span></span>  
*   <span data-ttu-id="84851-121">\(Soon\) WebView2 固有のポリシー – WebView2 は、WebView2 の管理が直接理にかなっている場合に、グループ ポリシーの小さな追加セットを公開します。</span><span class="sxs-lookup"><span data-stu-id="84851-121">\(Coming soon\) WebView2-specific policies – WebView2 will expose a small additional set of group policies in cases where managing WebView2 directly makes sense.</span></span>  <span data-ttu-id="84851-122">It 管理者が WebView2 ではなくアプリを直接管理する方が簡単なので、WebView2 の使用を管理するために、アプリ開発者は独自のグループ ポリシーを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="84851-122">We recommend app developers to implement their own group policies to manage their use of WebView2, as it is more straightforward for IT admins to manage the app rather than WebView2 directly.</span></span>  

<!-- Links -->  

[Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview]: ./distribution.md#understanding-the-webview2-runtime "WebView2 ランタイムとインストーラー (プレビュー) - WebView2 を使用したアプリケーションの配布について|Microsoft Docs"  

[WebView2Landing]: ../index.md "WebView2 Microsoft Edge (プレビュー) の概要|Microsoft Docs"  

[EdgeUpdatePolicies]: /deployedge/microsoft-edge-update-policies "Microsoft Edge - ポリシーの更新|Microsoft Docs"  
[EdgeBrowserPolicies]: /deployedge/microsoft-edge-policies "Microsoft Edge - ブラウザー ポリシー|Microsoft Docs"  
[ConfigureMicrosoftEdge]: /deployedge/configure-microsoft-edge "サーバー Microsoft Edgeポリシー設定を構成Windows |Microsoft Docs"  


[GithubMicrosoftedgeWebviewfeddback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック - MicrosoftEdge/WebViewFeedback | GitHub"  
