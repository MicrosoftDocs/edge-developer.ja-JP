---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 3d85b1116a3f75058bda59f1c374700555b42a5e
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699084"
---
# <span data-ttu-id="23383-104">WebView2 クラス (CoreWebView2WebResourceRequestedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="23383-104">Microsoft.Web.WebView2.Core.CoreWebView2WebResourceRequestedEventArgs class</span></span> 

<span data-ttu-id="23383-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="23383-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="23383-106">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="23383-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="23383-107">WebResourceRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="23383-107">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="23383-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="23383-108">Summary</span></span>

 <span data-ttu-id="23383-109">Members</span><span class="sxs-lookup"><span data-stu-id="23383-109">Members</span></span>                        | <span data-ttu-id="23383-110">説明</span><span class="sxs-lookup"><span data-stu-id="23383-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="23383-111">要求</span><span class="sxs-lookup"><span data-stu-id="23383-111">Request</span></span>](#request) | <span data-ttu-id="23383-112">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="23383-112">The HTTP request.</span></span>
[<span data-ttu-id="23383-113">ResourceContext</span><span class="sxs-lookup"><span data-stu-id="23383-113">ResourceContext</span></span>](#resourcecontext) | <span data-ttu-id="23383-114">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="23383-114">The web resource request contexts.</span></span>
[<span data-ttu-id="23383-115">応答</span><span class="sxs-lookup"><span data-stu-id="23383-115">Response</span></span>](#response) | <span data-ttu-id="23383-116">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="23383-116">The HTTP response.</span></span>
[<span data-ttu-id="23383-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="23383-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="23383-118">CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="23383-118">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

## <span data-ttu-id="23383-119">Members</span><span class="sxs-lookup"><span data-stu-id="23383-119">Members</span></span>

#### <span data-ttu-id="23383-120">要求</span><span class="sxs-lookup"><span data-stu-id="23383-120">Request</span></span> 

<span data-ttu-id="23383-121">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="23383-121">The HTTP request.</span></span>

> <span data-ttu-id="23383-122">パブリック HttpRequestMessage[要求](#request)</span><span class="sxs-lookup"><span data-stu-id="23383-122">public HttpRequestMessage [Request](#request)</span></span>

#### <span data-ttu-id="23383-123">ResourceContext</span><span class="sxs-lookup"><span data-stu-id="23383-123">ResourceContext</span></span> 

<span data-ttu-id="23383-124">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="23383-124">The web resource request contexts.</span></span>

> <span data-ttu-id="23383-125">パブリック[CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [resourcecontext](#resourcecontext)</span><span class="sxs-lookup"><span data-stu-id="23383-125">public [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [ResourceContext](#resourcecontext)</span></span>

#### <span data-ttu-id="23383-126">応答</span><span class="sxs-lookup"><span data-stu-id="23383-126">Response</span></span> 

<span data-ttu-id="23383-127">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="23383-127">The HTTP response.</span></span>

> <span data-ttu-id="23383-128">パブリック HttpResponseMessage[応答](#response)</span><span class="sxs-lookup"><span data-stu-id="23383-128">public HttpResponseMessage [Response](#response)</span></span>

#### <span data-ttu-id="23383-129">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="23383-129">GetDeferral</span></span> 

<span data-ttu-id="23383-130">CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="23383-130">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

> <span data-ttu-id="23383-131">パブリック[CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [getdeferral](#getdeferral)()</span><span class="sxs-lookup"><span data-stu-id="23383-131">public [CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="23383-132">CoreWebView2Deferral オブジェクトを使って、後でネットワーク要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="23383-132">You can use the CoreWebView2Deferral object to complete the network request at a later time.</span></span>

