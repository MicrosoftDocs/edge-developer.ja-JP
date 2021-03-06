---
description: WebView2 の次の予定について説明します。
title: Microsoft Edge WebView 2 のロードマップ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、Webview2、Webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、エッジ html
ms.openlocfilehash: 0f51b5cab32bdb9b9aa9b6baceef5fe5a17eea54
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398414"
---
# <a name="microsoft-edge-webview2-roadmap"></a><span data-ttu-id="01334-104">Microsoft Edge WebView2 ロードマップ</span><span class="sxs-lookup"><span data-stu-id="01334-104">Microsoft Edge WebView2 roadmap</span></span>  

> [!NOTE]
> <span data-ttu-id="01334-105">最終更新日: 2020 年 11 月</span><span class="sxs-lookup"><span data-stu-id="01334-105">Last Updated:  November 2020</span></span>  

<span data-ttu-id="01334-106">WebView2 コントロールを使用すると、開発者は Web テクノロジをネイティブ アプリケーションに埋め込むできます。</span><span class="sxs-lookup"><span data-stu-id="01334-106">The WebView2 control allows developers to embed web technologies in their native applications.</span></span>  <span data-ttu-id="01334-107">次のページでは、WebView2 のロードマップの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="01334-107">The following page outlines the prospective roadmap for WebView2.</span></span>  

> [!NOTE]
> <span data-ttu-id="01334-108">WebView2 は積極的な開発中であり、市場の変化や顧客からのフィードバックに基づいてロードマップが進化し続けているので、ここで説明する計画は網羅的ではなく、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="01334-108">WebView2 is under active development and the roadmap continues to evolve based on market changes and customer feedback, so please note that the plans outlined here are not exhaustive and are subject to change.</span></span>  

<span data-ttu-id="01334-109">ロードマップに関する懸念や質問がある場合は、フィードバック repo でフィードバック [を提供してください][GithubMicrosoftedgeWebviewfeedbackMain]。</span><span class="sxs-lookup"><span data-stu-id="01334-109">If you have concerns or questions about the Roadmap, provide your feedback in the [feedback repo][GithubMicrosoftedgeWebviewfeedbackMain].</span></span>  

<span data-ttu-id="01334-110">WebView2 チームは、今後の更新に向けた以下の主要な取り組みを計画しています。</span><span class="sxs-lookup"><span data-stu-id="01334-110">The WebView2 team is planning the following major efforts for future updates.</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="01334-111">WebView2 ランタイム インストーラー</span><span class="sxs-lookup"><span data-stu-id="01334-111">WebView2 Runtime Installer</span></span>  
   :::column-end:::
   :::column span="2":::
      *   <span data-ttu-id="01334-112">Q4 2020</span><span class="sxs-lookup"><span data-stu-id="01334-112">Q4 2020</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="01334-113">修正済みバージョン</span><span class="sxs-lookup"><span data-stu-id="01334-113">Fixed Version</span></span>  
   :::column-end:::
   :::column span="2":::
      *   <span data-ttu-id="01334-114">Q4 2020</span><span class="sxs-lookup"><span data-stu-id="01334-114">Q4 2020</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="01334-115">一般提供</span><span class="sxs-lookup"><span data-stu-id="01334-115">General Availability</span></span>  
   :::column-end:::
   :::column span="2":::
      *   <span data-ttu-id="01334-116">Win32 C/C++ \(Q4 2020\)</span><span class="sxs-lookup"><span data-stu-id="01334-116">Win32 C/C++ \(Q4 2020\)</span></span>  
      *   <span data-ttu-id="01334-117">.NET \(Q4 2020\)</span><span class="sxs-lookup"><span data-stu-id="01334-117">.NET \(Q4 2020\)</span></span>  
      *   [<span data-ttu-id="01334-118">WinUI 3.0</span><span class="sxs-lookup"><span data-stu-id="01334-118">WinUI 3.0</span></span>][GithubMicrosoftUiXamlRoadmap]  
   :::column-end:::
:::row-end:::  

## <a name="webview2-runtime-and-installer"></a><span data-ttu-id="01334-119">WebView2 ランタイムとインストーラー</span><span class="sxs-lookup"><span data-stu-id="01334-119">WebView2 Runtime and Installer</span></span>  

<span data-ttu-id="01334-120">[Evergreen 配布モデルを使用][ConceptDistributionEvergreenModel] すると、WebView2 ランタイムをユーザーのコンピューターにターゲットまたはチェーンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="01334-120">[Evergreen distribution model][ConceptDistributionEvergreenModel] allows you to target or chain install the WebView2 Runtime onto your user's machine.</span></span>  <span data-ttu-id="01334-121">Evergreen WebView2 ランタイムとインストーラーが一般提供 \(GA\) に達しました。</span><span class="sxs-lookup"><span data-stu-id="01334-121">The Evergreen WebView2 Runtime and installer has reached General Availability \(GA\).</span></span>  

## <a name="fixed-version"></a><span data-ttu-id="01334-122">固定バージョン</span><span class="sxs-lookup"><span data-stu-id="01334-122">Fixed version</span></span>  

<span data-ttu-id="01334-123">[固定バージョン配布モデルを使用][ConceptsDistributionFixedVersionModel] すると、ネイティブ アプリケーション内で Microsoft Edge バイナリをパッケージ化できます。</span><span class="sxs-lookup"><span data-stu-id="01334-123">[Fixed version distribution model][ConceptsDistributionFixedVersionModel] allows you to package the Microsoft Edge binaries inside your native application.</span></span>  <span data-ttu-id="01334-124">固定バージョンが一般提供 \(GA\) に達しました。</span><span class="sxs-lookup"><span data-stu-id="01334-124">The Fixed Version has reached General Availability \(GA\).</span></span>  

## <a name="general-availability"></a><span data-ttu-id="01334-125">一般提供</span><span class="sxs-lookup"><span data-stu-id="01334-125">General availability</span></span>  

### <a name="win32-cc"></a><span data-ttu-id="01334-126">Win32 C/C++</span><span class="sxs-lookup"><span data-stu-id="01334-126">Win32 C/C++</span></span>  

<span data-ttu-id="01334-127">Win32 C/C++ SDK が GA に達しました。</span><span class="sxs-lookup"><span data-stu-id="01334-127">The Win32 C/C++ SDK has reached GA.</span></span>  

### <a name="net"></a><span data-ttu-id="01334-128">.NET</span><span class="sxs-lookup"><span data-stu-id="01334-128">.NET</span></span>  

<span data-ttu-id="01334-129">.NET SDK が GA に達しました。</span><span class="sxs-lookup"><span data-stu-id="01334-129">The .NET SDK has reached GA.</span></span> 

### <a name="winui-30"></a><span data-ttu-id="01334-130">WinUI 3.0</span><span class="sxs-lookup"><span data-stu-id="01334-130">WinUI 3.0</span></span>  

<span data-ttu-id="01334-131">現在アルファ版の Win [UI 3.0][UwpToolkitsWinui3Index]を使用して、UWP アプリケーションの WebView2 にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="01334-131">You can access WebView2 in your UWP applications using [Win UI 3.0][UwpToolkitsWinui3Index], currently in alpha.</span></span>  <span data-ttu-id="01334-132">最新の状態を維持する方法の詳細については [、「Windows UI ライブラリのロードマップ」に移動します][GithubMicrosoftUiXamlRoadmap]。</span><span class="sxs-lookup"><span data-stu-id="01334-132">For more information about keeping up to date, navigate to [Windows UI Library Roadmap][GithubMicrosoftUiXamlRoadmap].</span></span>  

<!-- links -->  

[ConceptDistributionEvergreenModel]: ./concepts/distribution.md#evergreen-distribution-mode "Evergreen 配布モデル - WebView2 を使用したアプリケーションの|Microsoft Docs"  
[ConceptsDistributionFixedVersionModel]: ./concepts/distribution.md#fixed-version-distribution-mode "固定バージョン配布モデル - WebView2 を使用したアプリケーションの|Microsoft Docs"  

[UwpToolkitsWinui3Index]: /uwp/toolkits/winui3/index "Windows UI ライブラリ 3.0 プレビュー 1 (2020 年 5 月) |Microsoft Docs"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback | GitHub"  

[GithubMicrosoftUiXamlRoadmap]: https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md "Windows UI ライブラリのロードマップ - microsoft/microsoft-ui-xaml |GitHub"  
