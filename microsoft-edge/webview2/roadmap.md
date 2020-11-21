---
description: WebView2 の次の項目について
title: Microsoft Edge WebView のロードマップ2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 99e743db0c1fb17ea46405b08e1ed074a3386068
ms.sourcegitcommit: fab44f7e183a3c4f12bf925512fc62d84a4d6edc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "11182361"
---
# <span data-ttu-id="c37b6-104">Microsoft Edge WebView2 のロードマップ</span><span class="sxs-lookup"><span data-stu-id="c37b6-104">Microsoft Edge WebView2 roadmap</span></span>  

##### <span data-ttu-id="c37b6-105">最終更新日: 2020 年11月</span><span class="sxs-lookup"><span data-stu-id="c37b6-105">Last Updated: November 2020</span></span>  

<span data-ttu-id="c37b6-106">WebView2 コントロールを使うと、開発者はネイティブアプリケーションに web テクノロジを埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="c37b6-106">The WebView2 control allows developers to embed web technologies in their native applications.</span></span>  <span data-ttu-id="c37b6-107">次のページは、WebView2 の予想されるロードマップの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="c37b6-107">The following page outlines the prospective roadmap for WebView2.</span></span>  

> [!NOTE]
> <span data-ttu-id="c37b6-108">WebView2 は [アクティブな開発] の下にあります。また、ロードマップは市場の変化や顧客のフィードバックに基づいて進化し続けているため、ここで説明されているプランは完全ではなく、変更される可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c37b6-108">WebView2 is under active development and the roadmap continues to evolve based on market changes and customer feedback, so please note that the plans outlined here are not exhaustive and are subject to change.</span></span>  

<span data-ttu-id="c37b6-109">ロードマップに関する懸念事項または質問がある場合は、フィードバックの [リポジトリ][GithubMicrosoftedgeWebviewfeedbackMain]にフィードバックを提供してください。</span><span class="sxs-lookup"><span data-stu-id="c37b6-109">If you have concerns or questions about the Roadmap, provide your feedback in the [feedback repo][GithubMicrosoftedgeWebviewfeedbackMain].</span></span>  

<span data-ttu-id="c37b6-110">WebView2 チームは今後の更新プログラムに対して、次の主な取り組みを計画しています。</span><span class="sxs-lookup"><span data-stu-id="c37b6-110">The WebView2 team is planning the following major efforts for future updates.</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="c37b6-111">WebView2 Runtime Installer</span><span class="sxs-lookup"><span data-stu-id="c37b6-111">WebView2 Runtime Installer</span></span>  
   :::column-end:::
   :::column span="2":::
      *   <span data-ttu-id="c37b6-112">2020年第4四半期</span><span class="sxs-lookup"><span data-stu-id="c37b6-112">Q4 2020</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="c37b6-113">修正済みバージョン</span><span class="sxs-lookup"><span data-stu-id="c37b6-113">Fixed Version</span></span>  
   :::column-end:::
   :::column span="2":::
      *   <span data-ttu-id="c37b6-114">2020年第4四半期</span><span class="sxs-lookup"><span data-stu-id="c37b6-114">Q4 2020</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="c37b6-115">Ga</span><span class="sxs-lookup"><span data-stu-id="c37b6-115">General Availability</span></span>  
   :::column-end:::
   :::column span="2":::
      *   <span data-ttu-id="c37b6-116">Win32 C/c + + (2020 年4四半期 \)</span><span class="sxs-lookup"><span data-stu-id="c37b6-116">Win32 C/C++ \(Q4 2020\)</span></span>  
      *   <span data-ttu-id="c37b6-117">.NET \ (Q4 年4四半期 2020 \)</span><span class="sxs-lookup"><span data-stu-id="c37b6-117">.NET \(Q4 2020\)</span></span>  
      *   [<span data-ttu-id="c37b6-118">WinUI 3.0</span><span class="sxs-lookup"><span data-stu-id="c37b6-118">WinUI 3.0</span></span>][GithubMicrosoftUiXamlRoadmap]  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="c37b6-119">WebView2 のランタイムとインストーラー</span><span class="sxs-lookup"><span data-stu-id="c37b6-119">WebView2 Runtime and Installer</span></span>  

<span data-ttu-id="c37b6-120">[Evergreen 配布モデル][ConceptDistributionEvergreenModel] では、ユーザーのコンピューターに WebView2 ランタイムをターゲットまたは連鎖してインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="c37b6-120">[Evergreen distribution model][ConceptDistributionEvergreenModel] allows you to target or chain install the WebView2 Runtime onto your user's machine.</span></span>  <span data-ttu-id="c37b6-121">Evergreen WebView2 Runtime と installer は、一般的な可用性 \ (GA) に到達しました。</span><span class="sxs-lookup"><span data-stu-id="c37b6-121">The Evergreen WebView2 Runtime and installer has reached General Availability \(GA\).</span></span>  

## <span data-ttu-id="c37b6-122">修正されたバージョン</span><span class="sxs-lookup"><span data-stu-id="c37b6-122">Fixed version</span></span>  

<span data-ttu-id="c37b6-123">[固定バージョンの配布モデル][ConceptsDistributionFixedVersionModel] では、ネイティブアプリケーション内に Microsoft Edge バイナリをパッケージ化することができます。</span><span class="sxs-lookup"><span data-stu-id="c37b6-123">[Fixed version distribution model][ConceptsDistributionFixedVersionModel] allows you to package the Microsoft Edge binaries inside your native application.</span></span>  <span data-ttu-id="c37b6-124">修正されたバージョンは、一般的な可用性 \ (GA) に到達しました。</span><span class="sxs-lookup"><span data-stu-id="c37b6-124">The Fixed Version has reached General Availability \(GA\).</span></span>  

## <span data-ttu-id="c37b6-125">Ga</span><span class="sxs-lookup"><span data-stu-id="c37b6-125">General availability</span></span>  

### <span data-ttu-id="c37b6-126">Win32 C/c + +</span><span class="sxs-lookup"><span data-stu-id="c37b6-126">Win32 C/C++</span></span>  

<span data-ttu-id="c37b6-127">Win32 C/c + + SDK の GA に到達しました。</span><span class="sxs-lookup"><span data-stu-id="c37b6-127">The Win32 C/C++ SDK has reached GA.</span></span>  

### <span data-ttu-id="c37b6-128">.NET</span><span class="sxs-lookup"><span data-stu-id="c37b6-128">.NET</span></span>  

<span data-ttu-id="c37b6-129">.NET SDK の GA に到達しました。</span><span class="sxs-lookup"><span data-stu-id="c37b6-129">The .NET SDK has reached GA.</span></span> 

### <span data-ttu-id="c37b6-130">WinUI 3.0</span><span class="sxs-lookup"><span data-stu-id="c37b6-130">WinUI 3.0</span></span>  

<span data-ttu-id="c37b6-131">UWP アプリケーションの WebView2 にアクセスするには、現在、 [WIN UI 3.0][UwpToolkitsWinui3Index]を使用します。</span><span class="sxs-lookup"><span data-stu-id="c37b6-131">You can access WebView2 in your UWP applications using [Win UI 3.0][UwpToolkitsWinui3Index], currently in alpha.</span></span>  <span data-ttu-id="c37b6-132">最新の状態に保つ方法について詳しくは、「 [WINDOWS UI ライブラリのロードマップ][GithubMicrosoftUiXamlRoadmap]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c37b6-132">For more information about keeping up to date, see [Windows UI Library Roadmap][GithubMicrosoftUiXamlRoadmap].</span></span>  

<!-- links -->  

[ConceptDistributionEvergreenModel]: ./concepts/distribution.md#evergreen-distribution-mode "Evergreen 配布モデル-WebView2 を使用したアプリケーションの配布 |Microsoft ドキュメント"  
[ConceptsDistributionFixedVersionModel]: ./concepts/distribution.md#fixed-version-distribution-mode "WebView2 を使用したアプリケーションの配布モデルの固定バージョン |Microsoft ドキュメント"  

[UwpToolkitsWinui3Index]: /uwp/toolkits/winui3/index "Windows UI ライブラリ3.0 プレビュー 1 (2020 年5月) |Microsoft ドキュメント"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback |GitHub"  

[GithubMicrosoftUiXamlRoadmap]: https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md "Windows UI ライブラリのロードマップ-microsoft/microsoft-UI-xaml |GitHub"  
