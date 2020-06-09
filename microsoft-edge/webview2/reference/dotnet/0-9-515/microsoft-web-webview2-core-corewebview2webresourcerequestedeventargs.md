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
ms.openlocfilehash: 072ce10e7ac1f34238278366c3e8799a3268cb0b
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697533"
---
# <span data-ttu-id="aa862-104">WebView2 クラス (CoreWebView2WebResourceRequestedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="aa862-104">Microsoft.Web.WebView2.Core.CoreWebView2WebResourceRequestedEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="aa862-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aa862-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="aa862-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa862-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="aa862-107">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="aa862-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="aa862-108">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="aa862-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="aa862-109">WebResourceRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="aa862-109">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="aa862-110">まとめ</span><span class="sxs-lookup"><span data-stu-id="aa862-110">Summary</span></span>

 <span data-ttu-id="aa862-111">Members</span><span class="sxs-lookup"><span data-stu-id="aa862-111">Members</span></span>                        | <span data-ttu-id="aa862-112">説明</span><span class="sxs-lookup"><span data-stu-id="aa862-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="aa862-113">要求</span><span class="sxs-lookup"><span data-stu-id="aa862-113">Request</span></span>](#request) | <span data-ttu-id="aa862-114">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="aa862-114">The HTTP request.</span></span>
[<span data-ttu-id="aa862-115">ResourceContext</span><span class="sxs-lookup"><span data-stu-id="aa862-115">ResourceContext</span></span>](#resourcecontext) | <span data-ttu-id="aa862-116">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="aa862-116">The web resource request contexts.</span></span>
[<span data-ttu-id="aa862-117">応答</span><span class="sxs-lookup"><span data-stu-id="aa862-117">Response</span></span>](#response) | <span data-ttu-id="aa862-118">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="aa862-118">The HTTP response.</span></span>
[<span data-ttu-id="aa862-119">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="aa862-119">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="aa862-120">CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="aa862-120">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

## <span data-ttu-id="aa862-121">Members</span><span class="sxs-lookup"><span data-stu-id="aa862-121">Members</span></span>

#### <span data-ttu-id="aa862-122">要求</span><span class="sxs-lookup"><span data-stu-id="aa862-122">Request</span></span> 

<span data-ttu-id="aa862-123">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="aa862-123">The HTTP request.</span></span>

> <span data-ttu-id="aa862-124">パブリック HttpRequestMessage[要求](#request)</span><span class="sxs-lookup"><span data-stu-id="aa862-124">public HttpRequestMessage [Request](#request)</span></span>

#### <span data-ttu-id="aa862-125">ResourceContext</span><span class="sxs-lookup"><span data-stu-id="aa862-125">ResourceContext</span></span> 

<span data-ttu-id="aa862-126">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="aa862-126">The web resource request contexts.</span></span>

> <span data-ttu-id="aa862-127">パブリック[CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [resourcecontext](#resourcecontext)</span><span class="sxs-lookup"><span data-stu-id="aa862-127">public [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [ResourceContext](#resourcecontext)</span></span>

#### <span data-ttu-id="aa862-128">応答</span><span class="sxs-lookup"><span data-stu-id="aa862-128">Response</span></span> 

<span data-ttu-id="aa862-129">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="aa862-129">The HTTP response.</span></span>

> <span data-ttu-id="aa862-130">パブリック HttpResponseMessage[応答](#response)</span><span class="sxs-lookup"><span data-stu-id="aa862-130">public HttpResponseMessage [Response](#response)</span></span>

#### <span data-ttu-id="aa862-131">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="aa862-131">GetDeferral</span></span> 

<span data-ttu-id="aa862-132">CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="aa862-132">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

> <span data-ttu-id="aa862-133">パブリック[CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [getdeferral](#getdeferral)()</span><span class="sxs-lookup"><span data-stu-id="aa862-133">public [CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="aa862-134">CoreWebView2Deferral オブジェクトを使って、後でネットワーク要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="aa862-134">You can use the CoreWebView2Deferral object to complete the network request at a later time.</span></span>

