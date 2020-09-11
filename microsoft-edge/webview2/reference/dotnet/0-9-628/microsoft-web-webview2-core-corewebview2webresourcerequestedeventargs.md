---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2WebResourceRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2WebResourceRequestedEventArgs。
ms.openlocfilehash: 501483894a2abca58c5a1856ab587b93be904c8b
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012238"
---
# <span data-ttu-id="12ce9-104">WebView2 クラス (CoreWebView2WebResourceRequestedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="12ce9-104">Microsoft.Web.WebView2.Core.CoreWebView2WebResourceRequestedEventArgs class</span></span> 

<span data-ttu-id="12ce9-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="12ce9-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="12ce9-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="12ce9-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="12ce9-107">WebResourceRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="12ce9-107">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="12ce9-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="12ce9-108">Summary</span></span>

 <span data-ttu-id="12ce9-109">Members</span><span class="sxs-lookup"><span data-stu-id="12ce9-109">Members</span></span>                        | <span data-ttu-id="12ce9-110">説明</span><span class="sxs-lookup"><span data-stu-id="12ce9-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="12ce9-111">要求</span><span class="sxs-lookup"><span data-stu-id="12ce9-111">Request</span></span>](#request) | <span data-ttu-id="12ce9-112">Web リソース要求。</span><span class="sxs-lookup"><span data-stu-id="12ce9-112">The Web resource request.</span></span>
[<span data-ttu-id="12ce9-113">ResourceContext</span><span class="sxs-lookup"><span data-stu-id="12ce9-113">ResourceContext</span></span>](#resourcecontext) | <span data-ttu-id="12ce9-114">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="12ce9-114">The web resource request context.</span></span>
[<span data-ttu-id="12ce9-115">応答</span><span class="sxs-lookup"><span data-stu-id="12ce9-115">Response</span></span>](#response) | <span data-ttu-id="12ce9-116">Web リソース応答オブジェクトのプレースホルダー。</span><span class="sxs-lookup"><span data-stu-id="12ce9-116">A placeholder for the web resource response object.</span></span>
[<span data-ttu-id="12ce9-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="12ce9-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="12ce9-118">CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="12ce9-118">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

## <span data-ttu-id="12ce9-119">Members</span><span class="sxs-lookup"><span data-stu-id="12ce9-119">Members</span></span>

#### <span data-ttu-id="12ce9-120">要求</span><span class="sxs-lookup"><span data-stu-id="12ce9-120">Request</span></span> 

<span data-ttu-id="12ce9-121">Web リソース要求。</span><span class="sxs-lookup"><span data-stu-id="12ce9-121">The Web resource request.</span></span>

> <span data-ttu-id="12ce9-122">パブリック [CoreWebView2WebResourceRequest](microsoft-web-webview2-core-corewebview2webresourcerequest.md) [要求](#request)</span><span class="sxs-lookup"><span data-stu-id="12ce9-122">public [CoreWebView2WebResourceRequest](microsoft-web-webview2-core-corewebview2webresourcerequest.md) [Request](#request)</span></span>

<span data-ttu-id="12ce9-123">要求オブジェクトに、後でネットワークスタックによって追加された一部のヘッダーが欠落している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="12ce9-123">The request object may be missing some headers that are added by network stack later on.</span></span>

#### <span data-ttu-id="12ce9-124">ResourceContext</span><span class="sxs-lookup"><span data-stu-id="12ce9-124">ResourceContext</span></span> 

<span data-ttu-id="12ce9-125">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="12ce9-125">The web resource request context.</span></span>

> <span data-ttu-id="12ce9-126">パブリック [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [resourcecontext](#resourcecontext)</span><span class="sxs-lookup"><span data-stu-id="12ce9-126">public [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [ResourceContext](#resourcecontext)</span></span>

#### <span data-ttu-id="12ce9-127">応答</span><span class="sxs-lookup"><span data-stu-id="12ce9-127">Response</span></span> 

<span data-ttu-id="12ce9-128">Web リソース応答オブジェクトのプレースホルダー。</span><span class="sxs-lookup"><span data-stu-id="12ce9-128">A placeholder for the web resource response object.</span></span>

> <span data-ttu-id="12ce9-129">パブリック [CoreWebView2WebResourceResponse](microsoft-web-webview2-core-corewebview2webresourceresponse.md) [応答](#response)</span><span class="sxs-lookup"><span data-stu-id="12ce9-129">public [CoreWebView2WebResourceResponse](microsoft-web-webview2-core-corewebview2webresourceresponse.md) [Response](#response)</span></span>

<span data-ttu-id="12ce9-130">このオブジェクトが設定されている場合、web リソース要求はこの応答で完了します。</span><span class="sxs-lookup"><span data-stu-id="12ce9-130">If this object is set, the web resource request will be completed with this response.</span></span> <span data-ttu-id="12ce9-131">空の Web リソース応答オブジェクトは、CreateWebResourceResponse を使って作成してから、その応答を構築するために変更することができます。</span><span class="sxs-lookup"><span data-stu-id="12ce9-131">An empty Web resource response object can be created with CreateWebResourceResponse and then modified to construct the response.</span></span>

#### <span data-ttu-id="12ce9-132">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="12ce9-132">GetDeferral</span></span> 

<span data-ttu-id="12ce9-133">CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="12ce9-133">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

> <span data-ttu-id="12ce9-134">パブリック [CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [getdeferral](#getdeferral)()</span><span class="sxs-lookup"><span data-stu-id="12ce9-134">public [CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="12ce9-135">CoreWebView2Deferral オブジェクトを使って、後で要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="12ce9-135">You can use the CoreWebView2Deferral object to complete the request at a later time.</span></span>

