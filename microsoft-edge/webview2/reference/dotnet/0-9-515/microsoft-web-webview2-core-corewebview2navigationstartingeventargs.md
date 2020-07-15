---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (CoreWebView2NavigationStartingEventArgs の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: ea3936ac1267fa085f62db843f5cac3fad2635b5
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879787"
---
# <span data-ttu-id="cd15d-104">0.9.515 クラスの WebView2 クラス (CoreWebView2NavigationStartingEventArgs)</span><span class="sxs-lookup"><span data-stu-id="cd15d-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2NavigationStartingEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="cd15d-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cd15d-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="cd15d-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd15d-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="cd15d-107">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="cd15d-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="cd15d-108">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="cd15d-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="cd15d-109">NavigationStarting イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="cd15d-109">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="cd15d-110">まとめ</span><span class="sxs-lookup"><span data-stu-id="cd15d-110">Summary</span></span>

 <span data-ttu-id="cd15d-111">Members</span><span class="sxs-lookup"><span data-stu-id="cd15d-111">Members</span></span>                        | <span data-ttu-id="cd15d-112">説明</span><span class="sxs-lookup"><span data-stu-id="cd15d-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="cd15d-113">Cancel</span><span class="sxs-lookup"><span data-stu-id="cd15d-113">Cancel</span></span>](#cancel) | <span data-ttu-id="cd15d-114">ホストでは、このフラグを設定して移動を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="cd15d-114">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="cd15d-115">IsRedirected</span><span class="sxs-lookup"><span data-stu-id="cd15d-115">IsRedirected</span></span>](#isredirected) | <span data-ttu-id="cd15d-116">ナビゲーションがリダイレクトされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="cd15d-116">True when the navigation is redirected.</span></span>
[<span data-ttu-id="cd15d-117">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="cd15d-117">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="cd15d-118">プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="cd15d-118">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="cd15d-119">NavigationId</span><span class="sxs-lookup"><span data-stu-id="cd15d-119">NavigationId</span></span>](#navigationid) | <span data-ttu-id="cd15d-120">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="cd15d-120">The ID of the navigation.</span></span>
[<span data-ttu-id="cd15d-121">RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="cd15d-121">RequestHeaders</span></span>](#requestheaders) | <span data-ttu-id="cd15d-122">ナビゲーションの HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="cd15d-122">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="cd15d-123">URI</span><span class="sxs-lookup"><span data-stu-id="cd15d-123">Uri</span></span>](#uri) | <span data-ttu-id="cd15d-124">要求されたナビゲーションの uri。</span><span class="sxs-lookup"><span data-stu-id="cd15d-124">The uri of the requested navigation.</span></span>

## <span data-ttu-id="cd15d-125">Members</span><span class="sxs-lookup"><span data-stu-id="cd15d-125">Members</span></span>

#### <span data-ttu-id="cd15d-126">Cancel</span><span class="sxs-lookup"><span data-stu-id="cd15d-126">Cancel</span></span> 

<span data-ttu-id="cd15d-127">ホストでは、このフラグを設定して移動を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="cd15d-127">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="cd15d-128">パブリックブール値の[キャンセル](#cancel)</span><span class="sxs-lookup"><span data-stu-id="cd15d-128">public bool [Cancel](#cancel)</span></span>

<span data-ttu-id="cd15d-129">設定されている場合は、ナビゲーションが行われないか、現在のページのコンテンツがそのまま保持されます。</span><span class="sxs-lookup"><span data-stu-id="cd15d-129">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="cd15d-130">パフォーマンス上の理由から、GET HTTP 要求は、ホストの応答中に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cd15d-130">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="cd15d-131">つまり、ナビゲーションの要求の一部を cookie に設定して使うことができます。</span><span class="sxs-lookup"><span data-stu-id="cd15d-131">This means cookies can be set and used part of a request for the navigation.</span></span>

#### <span data-ttu-id="cd15d-132">IsRedirected</span><span class="sxs-lookup"><span data-stu-id="cd15d-132">IsRedirected</span></span> 

<span data-ttu-id="cd15d-133">ナビゲーションがリダイレクトされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="cd15d-133">True when the navigation is redirected.</span></span>

> <span data-ttu-id="cd15d-134">パブリックブール値[リダイレクト](#isredirected)</span><span class="sxs-lookup"><span data-stu-id="cd15d-134">public bool [IsRedirected](#isredirected)</span></span>

#### <span data-ttu-id="cd15d-135">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="cd15d-135">IsUserInitiated</span></span> 

<span data-ttu-id="cd15d-136">プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="cd15d-136">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="cd15d-137">public bool [Isuserinitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="cd15d-137">public bool [IsUserInitiated](#isuserinitiated)</span></span>

#### <span data-ttu-id="cd15d-138">NavigationId</span><span class="sxs-lookup"><span data-stu-id="cd15d-138">NavigationId</span></span> 

<span data-ttu-id="cd15d-139">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="cd15d-139">The ID of the navigation.</span></span>

> <span data-ttu-id="cd15d-140">パブリック ulong [Navigationid](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="cd15d-140">public ulong [NavigationId](#navigationid)</span></span>

#### <span data-ttu-id="cd15d-141">RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="cd15d-141">RequestHeaders</span></span> 

<span data-ttu-id="cd15d-142">ナビゲーションの HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="cd15d-142">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="cd15d-143">パブリック HttpRequestHeaders [RequestHeaders](#requestheaders)</span><span class="sxs-lookup"><span data-stu-id="cd15d-143">public HttpRequestHeaders [RequestHeaders](#requestheaders)</span></span>

<span data-ttu-id="cd15d-144">ただし、NavigationStarting イベントの HTTP 要求ヘッダーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="cd15d-144">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="cd15d-145">URI</span><span class="sxs-lookup"><span data-stu-id="cd15d-145">Uri</span></span> 

<span data-ttu-id="cd15d-146">要求されたナビゲーションの uri。</span><span class="sxs-lookup"><span data-stu-id="cd15d-146">The uri of the requested navigation.</span></span>

> <span data-ttu-id="cd15d-147">パブリック文字列の[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="cd15d-147">public string [Uri](#uri)</span></span>

