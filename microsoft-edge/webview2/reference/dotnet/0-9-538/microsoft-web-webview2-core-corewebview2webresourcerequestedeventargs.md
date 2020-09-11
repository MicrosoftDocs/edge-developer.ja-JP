---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 (CoreWebView2WebResourceRequestedEventArgs の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2WebResourceRequestedEventArgs。
ms.openlocfilehash: 2282b36d3b7dfcca83f84ed50a976d4e6622ce07
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010125"
---
# <span data-ttu-id="f7008-104">0.9.579 クラスの WebView2 クラス (CoreWebView2WebResourceRequestedEventArgs)</span><span class="sxs-lookup"><span data-stu-id="f7008-104">0.9.579 - Microsoft.Web.WebView2.Core.CoreWebView2WebResourceRequestedEventArgs class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="f7008-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="f7008-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="f7008-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="f7008-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="f7008-107">WebResourceRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="f7008-107">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="f7008-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="f7008-108">Summary</span></span>

 <span data-ttu-id="f7008-109">Members</span><span class="sxs-lookup"><span data-stu-id="f7008-109">Members</span></span>                        | <span data-ttu-id="f7008-110">説明</span><span class="sxs-lookup"><span data-stu-id="f7008-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f7008-111">要求</span><span class="sxs-lookup"><span data-stu-id="f7008-111">Request</span></span>](#request) | <span data-ttu-id="f7008-112">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="f7008-112">The HTTP request.</span></span>
[<span data-ttu-id="f7008-113">ResourceContext</span><span class="sxs-lookup"><span data-stu-id="f7008-113">ResourceContext</span></span>](#resourcecontext) | <span data-ttu-id="f7008-114">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="f7008-114">The web resource request contexts.</span></span>
[<span data-ttu-id="f7008-115">応答</span><span class="sxs-lookup"><span data-stu-id="f7008-115">Response</span></span>](#response) | <span data-ttu-id="f7008-116">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="f7008-116">The HTTP response.</span></span>
[<span data-ttu-id="f7008-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="f7008-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="f7008-118">CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="f7008-118">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

## <span data-ttu-id="f7008-119">Members</span><span class="sxs-lookup"><span data-stu-id="f7008-119">Members</span></span>

#### <span data-ttu-id="f7008-120">要求</span><span class="sxs-lookup"><span data-stu-id="f7008-120">Request</span></span> 

<span data-ttu-id="f7008-121">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="f7008-121">The HTTP request.</span></span>

> <span data-ttu-id="f7008-122">パブリック HttpRequestMessage [要求](#request)</span><span class="sxs-lookup"><span data-stu-id="f7008-122">public HttpRequestMessage [Request](#request)</span></span>

#### <span data-ttu-id="f7008-123">ResourceContext</span><span class="sxs-lookup"><span data-stu-id="f7008-123">ResourceContext</span></span> 

<span data-ttu-id="f7008-124">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="f7008-124">The web resource request contexts.</span></span>

> <span data-ttu-id="f7008-125">パブリック [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [resourcecontext](#resourcecontext)</span><span class="sxs-lookup"><span data-stu-id="f7008-125">public [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [ResourceContext](#resourcecontext)</span></span>

#### <span data-ttu-id="f7008-126">応答</span><span class="sxs-lookup"><span data-stu-id="f7008-126">Response</span></span> 

<span data-ttu-id="f7008-127">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="f7008-127">The HTTP response.</span></span>

> <span data-ttu-id="f7008-128">パブリック HttpResponseMessage [応答](#response)</span><span class="sxs-lookup"><span data-stu-id="f7008-128">public HttpResponseMessage [Response](#response)</span></span>

#### <span data-ttu-id="f7008-129">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="f7008-129">GetDeferral</span></span> 

<span data-ttu-id="f7008-130">CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="f7008-130">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

> <span data-ttu-id="f7008-131">パブリック [CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [getdeferral](#getdeferral)()</span><span class="sxs-lookup"><span data-stu-id="f7008-131">public [CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="f7008-132">CoreWebView2Deferral オブジェクトを使って、後でネットワーク要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="f7008-132">You can use the CoreWebView2Deferral object to complete the network request at a later time.</span></span>

