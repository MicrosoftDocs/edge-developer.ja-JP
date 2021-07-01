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
ms.openlocfilehash: f32488a26f3e3c926517b0e40e6aac6a309e42b8
ms.sourcegitcommit: 5ae09b1ad6cd576c9fec12538b23cd849861f2b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2021
ms.locfileid: "11627965"
---
# <a name="managing-webview2-applications"></a><span data-ttu-id="b2171-104">WebView2 アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="b2171-104">Managing WebView2 applications</span></span>  

<span data-ttu-id="b2171-105">[WebView2][WebView2Landing] は、開発者がアプリケーションのビルドに使用するコンポーネントであり、開発者はアプリケーションに電力を供給するために、ユーザー デバイスに自己更新 [の Evergreen WebView2 ランタイム][Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview] を展開できます。</span><span class="sxs-lookup"><span data-stu-id="b2171-105">[WebView2][WebView2Landing] is a component that developers use to build their applications, and the developers may deploy a [self-updating Evergreen WebView2 Runtime][Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview] on user device to power their applications.</span></span>  <span data-ttu-id="b2171-106">このドキュメントでは、IT 管理者が WebView2 アプリケーションとランタイムを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b2171-106">This document discusses how IT admins may manage WebView2 applications and Runtime.</span></span>  <span data-ttu-id="b2171-107">WEBView2 Feedback repo では、IT 管理者と開発者 [の両方からのフィードバックを歓迎します][GithubMicrosoftedgeWebviewfeddback]。</span><span class="sxs-lookup"><span data-stu-id="b2171-107">Feedback from both IT admins and developers is welcome on [WebView2 Feedback repo][GithubMicrosoftedgeWebviewfeddback].</span></span>  

## <a name="group-policies-for-webview2"></a><span data-ttu-id="b2171-108">WebView2 のグループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="b2171-108">Group policies for WebView2</span></span>  

<span data-ttu-id="b2171-109">IT 管理者は、グループ ポリシー オブジェクト \(GPO\) を使用して WebView2 のポリシー設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="b2171-109">IT admins may use group policy objects \(GPO\) to configure policy settings for WebView2.</span></span>  <span data-ttu-id="b2171-110">次の一連のポリシーは、WebView2 には適用できません。</span><span class="sxs-lookup"><span data-stu-id="b2171-110">The following set of policies are/are not applicable to WebView2,</span></span>  

*   <span data-ttu-id="b2171-111">[Microsoft Edge -][EdgeUpdatePolicies]更新ポリシーは、IT 管理者が WebView2 ランタイムのインストールおよび更新の側面を管理するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="b2171-111">[Microsoft Edge - Update policies][EdgeUpdatePolicies] are available for IT admins to manage the install and update aspects of the WebView2 Runtime.</span></span>  <span data-ttu-id="b2171-112">ブラウザー Microsoft Edge WebView2 ランタイムは、同じ更新メカニズムを使用して更新されます。</span><span class="sxs-lookup"><span data-stu-id="b2171-112">The Microsoft Edge browser and WebView2 Runtime are updated using the same update mechanism.</span></span>  <span data-ttu-id="b2171-113">チャネル固有のポリシーがない限り、ブラウザーと `Update` WebView2 ランタイムの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b2171-113">Unless a policy, such as `Update`, is channel-specific, it applies to both the browser and WebView2 Runtime.</span></span>  <span data-ttu-id="b2171-114">たとえば、IT 管理者は、ブラウザーと WebView2 ランタイムの両方の自動更新を抑制するために、毎日の時間を `UpdateSuppressed` 設定できます。</span><span class="sxs-lookup"><span data-stu-id="b2171-114">For example, `UpdateSuppressed` allows IT admins to set time during each day to suppress auto-update for both the browser and WebView2 Runtime.</span></span>  <span data-ttu-id="b2171-115">これにより、IT 管理者は、ブラウザーと WebView2 ランタイムの両方の設定とプロキシを 1 回構成して、ネットワーク帯域幅/トラフィックを制御したり、その他の目的で構成することができます。</span><span class="sxs-lookup"><span data-stu-id="b2171-115">This enables IT admins to configure preferences and proxies once for both the browser and WebView2 Runtime to control their network bandwidth/traffic or for other purposes.</span></span>  <span data-ttu-id="b2171-116">IT 管理者は、Microsoft Edge[の][ConfigureMicrosoftEdge]ガイドに従って、Microsoft Edgeポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="b2171-116">IT admins may follow [Microsoft Edge's guide][ConfigureMicrosoftEdge] to configure Microsoft Edge - Update policies.</span></span>  
*   <span data-ttu-id="b2171-117">[Microsoft Edge - ブラウザー ポリシー][EdgeBrowserPolicies]は WebView2 アプリケーションには適用されません。</span><span class="sxs-lookup"><span data-stu-id="b2171-117">[Microsoft Edge - Browser policies][EdgeBrowserPolicies] doesn't apply to WebView2 applications.</span></span>  <span data-ttu-id="b2171-118">これは、アプリとブラウザーの使用例が異なって、IT 管理者が WebView2 を使用するアプリケーションを認識していない可能性があるからです。</span><span class="sxs-lookup"><span data-stu-id="b2171-118">This is by design because apps and browsers have different use cases, and IT admins may not be aware of what applications use WebView2.</span></span>  <span data-ttu-id="b2171-119">WebView2 にブラウザー ポリシーを適用すると、意図しない結果が生じ得る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b2171-119">Applying browser policies on WebView2 may have unintended consequences.</span></span>  <span data-ttu-id="b2171-120">たとえば、IT 管理者はブラウザーで JavaScript をブロックし、JavaScript を使用しているすべての WebView2 アプリが壊れている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b2171-120">For example, IT admins may block JavaScript in the browser and all WebView2 apps using JavaScript are broken.</span></span>  
*   <span data-ttu-id="b2171-121">[WebView2 固有のポリシーを][WebView2Policies] 使用すると、WebView2 を直接管理できます。</span><span class="sxs-lookup"><span data-stu-id="b2171-121">[WebView2-specific policies][WebView2Policies] are available to for you to manage WebView2 directly.</span></span>  <span data-ttu-id="b2171-122">ただし、WebView2 を直接管理する代わりに管理者がアプリを管理しやすいため、開発者は WebView2 の使用を管理するために独自のグループ ポリシーを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b2171-122">However, we recommend that developers implement their own group policies to manage the use of WebView2 because it is easier for administrators to manage the app instead of managing WebView2 directly.</span></span>  

<!-- Links -->  

[Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview]: ./distribution.md#understanding-the-webview2-runtime "WebView2 ランタイムとインストーラー (プレビュー) - WebView2 を使用したアプリケーションの配布について|Microsoft Docs"  

[WebView2Landing]: ../index.md "WebView2 Microsoft Edge (プレビュー) の概要|Microsoft Docs"  

[EdgeUpdatePolicies]: /deployedge/microsoft-edge-update-policies "Microsoft Edge - ポリシーの更新|Microsoft Docs"  
[EdgeBrowserPolicies]: /deployedge/microsoft-edge-policies "Microsoft Edge - ブラウザー ポリシー|Microsoft Docs"  
[ConfigureMicrosoftEdge]: /deployedge/configure-microsoft-edge "サーバー Microsoft Edgeポリシー設定を構成Windows |Microsoft Docs"  
[WebView2Policies]: /deployedge/microsoft-edge-webview-policies "Microsoft EdgeWebView2 ポリシー ドキュメント |Microsoft Docs" 

[GithubMicrosoftedgeWebviewfeddback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック - MicrosoftEdge/WebViewFeedback | GitHub"  
