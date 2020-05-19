---
description: WebView2 の次の項目について
title: Microsoft Edge WebView のロードマップ2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: bc55c5a731ab6cba8f9be15208029aad0ad5357a
ms.sourcegitcommit: a75e062b71831ea850c85287a8d7d7ce3b55ec84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "10659745"
---
# <span data-ttu-id="d84be-104">Microsoft Edge WebView2 のロードマップ</span><span class="sxs-lookup"><span data-stu-id="d84be-104">Microsoft Edge WebView2 Roadmap</span></span>

##### <span data-ttu-id="d84be-105">最終更新日: 2020 年5月</span><span class="sxs-lookup"><span data-stu-id="d84be-105">Last Updated: May 2020</span></span>

<span data-ttu-id="d84be-106">WebView2 コントロールを使うと、開発者はネイティブアプリケーションに web テクノロジを埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="d84be-106">The WebView2 control allows developers to embed web technologies in their native applications.</span></span> <span data-ttu-id="d84be-107">このドキュメントでは、WebView2 の予想されるロードマップについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d84be-107">This document outlines the prospective roadmap for WebView2.</span></span> 

> [!NOTE]
> <span data-ttu-id="d84be-108">WebView2 は [アクティブな開発] の下にあり、ロードマップは市場の変更や顧客のフィードバックに基づいて進化し続けますので、ここに記載されているプランは網羅的ではなく、変更される可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d84be-108">WebView2 is under active development and the roadmap will continue to evolve based on market changes and customer feedback, so please note that the plans outlined here aren't exhaustive and are subject to change.</span></span> 

<span data-ttu-id="d84be-109">ロードマップについて懸念事項や質問がある場合は、フィードバックの[リポジトリ](https://github.com/MicrosoftEdge/WebViewFeedback)にフィードバックをお寄せください。</span><span class="sxs-lookup"><span data-stu-id="d84be-109">If you have concerns or questions about the Roadmap, please leave feedback in the [feedback repo](https://github.com/MicrosoftEdge/WebViewFeedback).</span></span>

<span data-ttu-id="d84be-110">WebView2 チームは、いくつかの主な取り組みを行っています。</span><span class="sxs-lookup"><span data-stu-id="d84be-110">The WebView2 team has a few major efforts underway:</span></span>

1.  <span data-ttu-id="d84be-111">WebView2 Runtime Installer (2020 年4四半期)</span><span class="sxs-lookup"><span data-stu-id="d84be-111">WebView2 Runtime Installer (Q4 2020)</span></span>
2.  <span data-ttu-id="d84be-112">修正済みバージョン (2020 年4四半期)</span><span class="sxs-lookup"><span data-stu-id="d84be-112">Fixed Version (Q4 2020)</span></span>
3.  <span data-ttu-id="d84be-113">Ga</span><span class="sxs-lookup"><span data-stu-id="d84be-113">General Availability</span></span> 
    *   <span data-ttu-id="d84be-114">Win32 C/c + + (2020 年4四半期)</span><span class="sxs-lookup"><span data-stu-id="d84be-114">Win32 C/C++ (Q4 2020)</span></span>
    *   <span data-ttu-id="d84be-115">.NET (Q4 年4四半期 2020)</span><span class="sxs-lookup"><span data-stu-id="d84be-115">.NET (Q4 2020)</span></span>
    *   [<span data-ttu-id="d84be-116">WinUI 3.0</span><span class="sxs-lookup"><span data-stu-id="d84be-116">WinUI 3.0</span></span>](https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md)

## <span data-ttu-id="d84be-117">WebView2 Runtime & Installer</span><span class="sxs-lookup"><span data-stu-id="d84be-117">WebView2 Runtime & Installer</span></span>

<span data-ttu-id="d84be-118">WebView2 [Evergreen](./concepts/distribution.md#microsoft-edge-webview2-runtime)配布モデルでは、ユーザーのコンピューターに WebView2 ランタイムをターゲット設定またはチェーンすることができます。</span><span class="sxs-lookup"><span data-stu-id="d84be-118">WebView2 [Evergreen](./concepts/distribution.md#microsoft-edge-webview2-runtime) distribution model will allow you to target or chain install the WebView2 Runtime onto your user's machine.</span></span> <span data-ttu-id="d84be-119">WebView2 のランタイムとインストーラーのプレビューは、2020年第4四半期2020および GA として提供される予定です。</span><span class="sxs-lookup"><span data-stu-id="d84be-119">A preview of the WebView2 Runtime and installer is expected to be available Q3 2020 and GA in Q4 2020.</span></span>

## <span data-ttu-id="d84be-120">修正されたバージョン</span><span class="sxs-lookup"><span data-stu-id="d84be-120">Fixed Version</span></span>

<span data-ttu-id="d84be-121">WebView2[固定](./concepts/distribution.md#roadmap)配布モデルでは、ネイティブアプリケーション内に Microsoft Edge バイナリをパッケージ化することができます。</span><span class="sxs-lookup"><span data-stu-id="d84be-121">WebView2 [Fixed](./concepts/distribution.md#roadmap) distribution model allows you to package the Microsoft Edge binaries inside your native application.</span></span> <span data-ttu-id="d84be-122">現時点では、エンジニアリング作業は、第3四半期2020および GA 四半期の2020年の終わりまでに、プレビューを表示する方法となっています。</span><span class="sxs-lookup"><span data-stu-id="d84be-122">Engineering work is currently under way with a preview anticipated to be ready towards the end of  Q3 2020 and GA Q4 2020.</span></span>

## <span data-ttu-id="d84be-123">Ga</span><span class="sxs-lookup"><span data-stu-id="d84be-123">General Availability</span></span> 

### <span data-ttu-id="d84be-124">Win32 C/c + +</span><span class="sxs-lookup"><span data-stu-id="d84be-124">Win32 C/C++</span></span>

<span data-ttu-id="d84be-125">Win32 C/c + + SDK の GA は、WebView2 Runtime および installer の GA の直後である、2020年4四半期に GA となります。</span><span class="sxs-lookup"><span data-stu-id="d84be-125">The Win32 C/C++ SDK is expected to GA in Q4 2020, shortly after the WebView2 Runtime and installer GA.</span></span>

### <span data-ttu-id="d84be-126">.NET</span><span class="sxs-lookup"><span data-stu-id="d84be-126">.NET</span></span>

<span data-ttu-id="d84be-127">.NET SDK は、Win32 C/C + + SDK をラップします。</span><span class="sxs-lookup"><span data-stu-id="d84be-127">The .NET SDK wraps the Win32 C/C++ SDK.</span></span> <span data-ttu-id="d84be-128">.NET SDK は、2020年4四半期に Win32 C/c + + GA の後、まもなく GA となります。</span><span class="sxs-lookup"><span data-stu-id="d84be-128">The .NET SDK is expected to GA shortly after the Win32 C/C++ GA in Q4 2020.</span></span>

### <span data-ttu-id="d84be-129">WinUI 3.0</span><span class="sxs-lookup"><span data-stu-id="d84be-129">WinUI 3.0</span></span>

<span data-ttu-id="d84be-130">WebView2 は、現在 alpha の[WIN UI 3.0](/uwp/toolkits/winui3/)経由で UWP アプリケーションに移動できます。</span><span class="sxs-lookup"><span data-stu-id="d84be-130">You can bring WebView2 to UWP applications through [Win UI 3.0](/uwp/toolkits/winui3/), currently in alpha.</span></span> <span data-ttu-id="d84be-131">[WINDOWS UI ライブラリのロードマップ](https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md)をチェックアウトして、最新の状態に維持します。</span><span class="sxs-lookup"><span data-stu-id="d84be-131">Checkout the [Windows UI Library Roadmap](https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md) to keep up to date.</span></span>  
