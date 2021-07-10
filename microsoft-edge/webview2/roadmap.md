---
description: WebView2 の次の予定について説明します。
title: WebView 2 Microsoft Edgeロードマップ
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、Webview2、Webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、ブラウザー コントロール、エッジ html
ms.openlocfilehash: 7b67e4a6844ead0f845667a70df8657745ece938
ms.sourcegitcommit: 8f37c931ecde4d58223113f7e3b42d37cc3df97f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2021
ms.locfileid: "11643421"
---
# <a name="microsoft-edge-webview2-roadmap"></a><span data-ttu-id="6b7d6-104">Microsoft EdgeWebView2 ロードマップ</span><span class="sxs-lookup"><span data-stu-id="6b7d6-104">Microsoft Edge WebView2 roadmap</span></span>  

> [!NOTE]
> <span data-ttu-id="6b7d6-105">最終更新日: 2021 年 7 月</span><span class="sxs-lookup"><span data-stu-id="6b7d6-105">Last Updated:  July 2021</span></span>  

<span data-ttu-id="6b7d6-106">WebView2 コントロールを使用すると、開発者は Web テクノロジをネイティブ アプリケーションに埋め込むできます。</span><span class="sxs-lookup"><span data-stu-id="6b7d6-106">The WebView2 control allows developers to embed web technologies in their native applications.</span></span>  <span data-ttu-id="6b7d6-107">次のページでは、WebView2 のロードマップの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="6b7d6-107">The following page outlines the prospective roadmap for WebView2.</span></span>  

> [!NOTE]
> <span data-ttu-id="6b7d6-108">WebView2 は積極的な開発中であり、市場の変化や顧客からのフィードバックに基づいてロードマップが進化し続けているので、ここで説明する計画は網羅的ではなく、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6b7d6-108">WebView2 is under active development and the roadmap continues to evolve based on market changes and customer feedback, so please note that the plans outlined here are not exhaustive and are subject to change.</span></span>  

<span data-ttu-id="6b7d6-109">ロードマップに関する懸念や質問がある場合は、フィードバック repo でフィードバック [を提供してください][GithubMicrosoftedgeWebviewfeedbackMain]。</span><span class="sxs-lookup"><span data-stu-id="6b7d6-109">If you have concerns or questions about the Roadmap, provide your feedback in the [feedback repo][GithubMicrosoftedgeWebviewfeedbackMain].</span></span>  

<span data-ttu-id="6b7d6-110">WebView2 チームは、今後の更新に向けた以下の主要な取り組みを計画しています。</span><span class="sxs-lookup"><span data-stu-id="6b7d6-110">The WebView2 team is planning the following major efforts for future updates.</span></span>  

* <span data-ttu-id="6b7d6-111">UWP プレビュー</span><span class="sxs-lookup"><span data-stu-id="6b7d6-111">UWP Preview</span></span>
* <span data-ttu-id="6b7d6-112">MacOS プレビュー</span><span class="sxs-lookup"><span data-stu-id="6b7d6-112">MacOS Preview</span></span>
* <span data-ttu-id="6b7d6-113">Xbox Preview</span><span class="sxs-lookup"><span data-stu-id="6b7d6-113">Xbox Preview</span></span>
* <span data-ttu-id="6b7d6-114">HoloLensプレビュー</span><span class="sxs-lookup"><span data-stu-id="6b7d6-114">HoloLens Preview</span></span>

## <a name="webview2-runtime-and-installer"></a><span data-ttu-id="6b7d6-115">WebView2 ランタイムとインストーラー</span><span class="sxs-lookup"><span data-stu-id="6b7d6-115">WebView2 Runtime and Installer</span></span>  

<span data-ttu-id="6b7d6-116">[Evergreen 配布モデルを使用][ConceptDistributionEvergreenModel] すると、WebView2 ランタイムをユーザーのコンピューターにターゲットまたはチェーンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="6b7d6-116">[Evergreen distribution model][ConceptDistributionEvergreenModel] allows you to target or chain install the WebView2 Runtime onto your user's machine.</span></span>  <span data-ttu-id="6b7d6-117">Evergreen WebView2 ランタイムとインストーラーが一般提供 \(GA\) に達しました。</span><span class="sxs-lookup"><span data-stu-id="6b7d6-117">The Evergreen WebView2 Runtime and installer has reached General Availability \(GA\).</span></span>  

## <a name="fixed-version"></a><span data-ttu-id="6b7d6-118">固定バージョン</span><span class="sxs-lookup"><span data-stu-id="6b7d6-118">Fixed version</span></span>  

<span data-ttu-id="6b7d6-119">[固定バージョン配布モデルを使用][ConceptsDistributionFixedVersionModel]すると、ネイティブ アプリケーションMicrosoft Edgeバイナリをパッケージ化できます。</span><span class="sxs-lookup"><span data-stu-id="6b7d6-119">[Fixed version distribution model][ConceptsDistributionFixedVersionModel] allows you to package the Microsoft Edge binaries inside your native application.</span></span>  <span data-ttu-id="6b7d6-120">固定バージョンが一般提供 \(GA\) に達しました。</span><span class="sxs-lookup"><span data-stu-id="6b7d6-120">The Fixed Version has reached General Availability \(GA\).</span></span>  

## <a name="general-availability"></a><span data-ttu-id="6b7d6-121">一般提供</span><span class="sxs-lookup"><span data-stu-id="6b7d6-121">General availability</span></span>  

### <a name="win32-cc"></a><span data-ttu-id="6b7d6-122">Win32 C/C++</span><span class="sxs-lookup"><span data-stu-id="6b7d6-122">Win32 C/C++</span></span>  

<span data-ttu-id="6b7d6-123">Win32 C/C++ SDK が GA に達しました。</span><span class="sxs-lookup"><span data-stu-id="6b7d6-123">The Win32 C/C++ SDK has reached GA.</span></span>  

### <a name="net"></a><span data-ttu-id="6b7d6-124">.NET</span><span class="sxs-lookup"><span data-stu-id="6b7d6-124">.NET</span></span>  

<span data-ttu-id="6b7d6-125">.NET SDK が GA に達しました。</span><span class="sxs-lookup"><span data-stu-id="6b7d6-125">The .NET SDK has reached GA.</span></span> 

### <a name="windows-ui-library-3"></a><span data-ttu-id="6b7d6-126">WindowsUI ライブラリ 3</span><span class="sxs-lookup"><span data-stu-id="6b7d6-126">Windows UI Library 3</span></span>

<span data-ttu-id="6b7d6-127">アプリケーションの WebView2 コントロールには、Windowsアプリ SDK を使用して UI ライブラリ[3 (WinUI3)][UwpToolkitsWinui3Index]をWindowsできます。</span><span class="sxs-lookup"><span data-stu-id="6b7d6-127">You can access WebView2 controls in your applications using [Windows UI Library 3 (WinUI3)][UwpToolkitsWinui3Index] with the Windows App SDK.</span></span> <span data-ttu-id="6b7d6-128">これは現在プレビュー中です。</span><span class="sxs-lookup"><span data-stu-id="6b7d6-128">This is currently in preview.</span></span> <span data-ttu-id="6b7d6-129">詳細については、「App SDK ロードマップ[」Windowsを参照してください][WindowsAppSDK|::ref1::|]。</span><span class="sxs-lookup"><span data-stu-id="6b7d6-129">For more information, navigate to the [Windows App SDK roadmap][WindowsAppSDK|::ref1::|].</span></span>

 
<!-- links -->  

[WindowsAppSDKRoadmap]: https://github.com/microsoft/WindowsAppSDK/blob/main/docs/roadmap.md "ロードマップ"
[ConceptDistributionEvergreenModel]: ./concepts/distribution.md#evergreen-distribution-mode "Evergreen 配布モデル - WebView2 を使用したアプリケーションの|Microsoft Docs"  
[ConceptsDistributionFixedVersionModel]: ./concepts/distribution.md#fixed-version-distribution-mode "固定バージョン配布モデル - WebView2 を使用したアプリケーションの|Microsoft Docs"  

[UwpToolkitsWinui3Index]: /uwp/toolkits/winui3/index "WindowsUI ライブラリ 3.0 プレビュー 1 (2020 年 5 月) |Microsoft Docs"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView フィードバック-MicrosoftEdge/WebViewFeedback | GitHub"  

[GithubMicrosoftUiXamlRoadmap]: https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md "WindowsUI ライブラリのロードマップ - microsoft/microsoft-ui-xaml |GitHub"  
