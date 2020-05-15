---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 9210a4b70d0e2edf30cbaad906f57b360688dfe8
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654249"
---
# <span data-ttu-id="7c306-104">WebView2 クラス (CoreWebView2WebResourceRequestedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="7c306-104">Microsoft.Web.WebView2.Core.CoreWebView2WebResourceRequestedEventArgs class</span></span> 

<span data-ttu-id="7c306-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="7c306-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="7c306-106">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="7c306-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="7c306-107">WebResourceRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="7c306-107">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="7c306-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="7c306-108">Summary</span></span>

 <span data-ttu-id="7c306-109">Members</span><span class="sxs-lookup"><span data-stu-id="7c306-109">Members</span></span>                        | <span data-ttu-id="7c306-110">説明</span><span class="sxs-lookup"><span data-stu-id="7c306-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="7c306-111">要求</span><span class="sxs-lookup"><span data-stu-id="7c306-111">Request</span></span>](#request) | <span data-ttu-id="7c306-112">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="7c306-112">The HTTP request.</span></span>
[<span data-ttu-id="7c306-113">ResourceContext</span><span class="sxs-lookup"><span data-stu-id="7c306-113">ResourceContext</span></span>](#resourcecontext) | <span data-ttu-id="7c306-114">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="7c306-114">The web resource request contexts.</span></span>
[<span data-ttu-id="7c306-115">応答</span><span class="sxs-lookup"><span data-stu-id="7c306-115">Response</span></span>](#response) | <span data-ttu-id="7c306-116">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="7c306-116">The HTTP response.</span></span>
[<span data-ttu-id="7c306-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="7c306-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="7c306-118">CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="7c306-118">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

## <span data-ttu-id="7c306-119">Members</span><span class="sxs-lookup"><span data-stu-id="7c306-119">Members</span></span>

#### <span data-ttu-id="7c306-120">要求</span><span class="sxs-lookup"><span data-stu-id="7c306-120">Request</span></span> 

<span data-ttu-id="7c306-121">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="7c306-121">The HTTP request.</span></span>

> <span data-ttu-id="7c306-122">パブリック HttpRequestMessage[要求](#request)</span><span class="sxs-lookup"><span data-stu-id="7c306-122">public HttpRequestMessage [Request](#request)</span></span>

#### <span data-ttu-id="7c306-123">ResourceContext</span><span class="sxs-lookup"><span data-stu-id="7c306-123">ResourceContext</span></span> 

<span data-ttu-id="7c306-124">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="7c306-124">The web resource request contexts.</span></span>

> <span data-ttu-id="7c306-125">パブリック[CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [resourcecontext](#resourcecontext)</span><span class="sxs-lookup"><span data-stu-id="7c306-125">public [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [ResourceContext](#resourcecontext)</span></span>

#### <span data-ttu-id="7c306-126">応答</span><span class="sxs-lookup"><span data-stu-id="7c306-126">Response</span></span> 

<span data-ttu-id="7c306-127">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="7c306-127">The HTTP response.</span></span>

> <span data-ttu-id="7c306-128">パブリック HttpResponseMessage[応答](#response)</span><span class="sxs-lookup"><span data-stu-id="7c306-128">public HttpResponseMessage [Response](#response)</span></span>

#### <span data-ttu-id="7c306-129">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="7c306-129">GetDeferral</span></span> 

<span data-ttu-id="7c306-130">CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="7c306-130">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

> <span data-ttu-id="7c306-131">パブリック[CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [getdeferral](#getdeferral)()</span><span class="sxs-lookup"><span data-stu-id="7c306-131">public [CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="7c306-132">CoreWebView2Deferral オブジェクトを使って、後でネットワーク要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="7c306-132">You can use the CoreWebView2Deferral object to complete the network request at a later time.</span></span>

