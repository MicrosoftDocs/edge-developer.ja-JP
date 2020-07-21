---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (CoreWebView2WebResourceRequestedEventArgs の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 656510998879e77c2e7797c700dacc5966299210
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884653"
---
# <span data-ttu-id="ecea8-104">0.9.515 クラスの WebView2 クラス (CoreWebView2WebResourceRequestedEventArgs)</span><span class="sxs-lookup"><span data-stu-id="ecea8-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2WebResourceRequestedEventArgs class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="ecea8-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="ecea8-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="ecea8-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="ecea8-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="ecea8-107">WebResourceRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="ecea8-107">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="ecea8-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="ecea8-108">Summary</span></span>

 <span data-ttu-id="ecea8-109">Members</span><span class="sxs-lookup"><span data-stu-id="ecea8-109">Members</span></span>                        | <span data-ttu-id="ecea8-110">説明</span><span class="sxs-lookup"><span data-stu-id="ecea8-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ecea8-111">要求</span><span class="sxs-lookup"><span data-stu-id="ecea8-111">Request</span></span>](#request) | <span data-ttu-id="ecea8-112">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="ecea8-112">The HTTP request.</span></span>
[<span data-ttu-id="ecea8-113">ResourceContext</span><span class="sxs-lookup"><span data-stu-id="ecea8-113">ResourceContext</span></span>](#resourcecontext) | <span data-ttu-id="ecea8-114">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="ecea8-114">The web resource request contexts.</span></span>
[<span data-ttu-id="ecea8-115">応答</span><span class="sxs-lookup"><span data-stu-id="ecea8-115">Response</span></span>](#response) | <span data-ttu-id="ecea8-116">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="ecea8-116">The HTTP response.</span></span>
[<span data-ttu-id="ecea8-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="ecea8-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="ecea8-118">CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="ecea8-118">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

## <span data-ttu-id="ecea8-119">Members</span><span class="sxs-lookup"><span data-stu-id="ecea8-119">Members</span></span>

#### <span data-ttu-id="ecea8-120">要求</span><span class="sxs-lookup"><span data-stu-id="ecea8-120">Request</span></span> 

<span data-ttu-id="ecea8-121">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="ecea8-121">The HTTP request.</span></span>

> <span data-ttu-id="ecea8-122">パブリック HttpRequestMessage[要求](#request)</span><span class="sxs-lookup"><span data-stu-id="ecea8-122">public HttpRequestMessage [Request](#request)</span></span>

#### <span data-ttu-id="ecea8-123">ResourceContext</span><span class="sxs-lookup"><span data-stu-id="ecea8-123">ResourceContext</span></span> 

<span data-ttu-id="ecea8-124">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="ecea8-124">The web resource request contexts.</span></span>

> <span data-ttu-id="ecea8-125">パブリック[CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [resourcecontext](#resourcecontext)</span><span class="sxs-lookup"><span data-stu-id="ecea8-125">public [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [ResourceContext](#resourcecontext)</span></span>

#### <span data-ttu-id="ecea8-126">応答</span><span class="sxs-lookup"><span data-stu-id="ecea8-126">Response</span></span> 

<span data-ttu-id="ecea8-127">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="ecea8-127">The HTTP response.</span></span>

> <span data-ttu-id="ecea8-128">パブリック HttpResponseMessage[応答](#response)</span><span class="sxs-lookup"><span data-stu-id="ecea8-128">public HttpResponseMessage [Response](#response)</span></span>

#### <span data-ttu-id="ecea8-129">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="ecea8-129">GetDeferral</span></span> 

<span data-ttu-id="ecea8-130">CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="ecea8-130">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

> <span data-ttu-id="ecea8-131">パブリック[CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [getdeferral](#getdeferral)()</span><span class="sxs-lookup"><span data-stu-id="ecea8-131">public [CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="ecea8-132">CoreWebView2Deferral オブジェクトを使って、後でネットワーク要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="ecea8-132">You can use the CoreWebView2Deferral object to complete the network request at a later time.</span></span>

