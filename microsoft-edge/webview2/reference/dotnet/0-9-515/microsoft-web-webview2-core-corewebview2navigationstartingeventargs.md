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
ms.openlocfilehash: 8b7ac3ab27cf5a2d9e80a77eabc488599820a02f
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654592"
---
# <span data-ttu-id="5739a-104">WebView2 クラス (CoreWebView2NavigationStartingEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="5739a-104">Microsoft.Web.WebView2.Core.CoreWebView2NavigationStartingEventArgs class</span></span> 

<span data-ttu-id="5739a-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="5739a-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="5739a-106">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="5739a-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="5739a-107">NavigationStarting イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="5739a-107">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="5739a-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="5739a-108">Summary</span></span>

 <span data-ttu-id="5739a-109">Members</span><span class="sxs-lookup"><span data-stu-id="5739a-109">Members</span></span>                        | <span data-ttu-id="5739a-110">説明</span><span class="sxs-lookup"><span data-stu-id="5739a-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5739a-111">Cancel</span><span class="sxs-lookup"><span data-stu-id="5739a-111">Cancel</span></span>](#cancel) | <span data-ttu-id="5739a-112">ホストでは、このフラグを設定して移動を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="5739a-112">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="5739a-113">IsRedirected</span><span class="sxs-lookup"><span data-stu-id="5739a-113">IsRedirected</span></span>](#isredirected) | <span data-ttu-id="5739a-114">ナビゲーションがリダイレクトされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="5739a-114">True when the navigation is redirected.</span></span>
[<span data-ttu-id="5739a-115">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="5739a-115">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="5739a-116">プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="5739a-116">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="5739a-117">NavigationId</span><span class="sxs-lookup"><span data-stu-id="5739a-117">NavigationId</span></span>](#navigationid) | <span data-ttu-id="5739a-118">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="5739a-118">The ID of the navigation.</span></span>
[<span data-ttu-id="5739a-119">RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="5739a-119">RequestHeaders</span></span>](#requestheaders) | <span data-ttu-id="5739a-120">ナビゲーションの HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="5739a-120">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="5739a-121">URI</span><span class="sxs-lookup"><span data-stu-id="5739a-121">Uri</span></span>](#uri) | <span data-ttu-id="5739a-122">要求されたナビゲーションの uri。</span><span class="sxs-lookup"><span data-stu-id="5739a-122">The uri of the requested navigation.</span></span>

## <span data-ttu-id="5739a-123">Members</span><span class="sxs-lookup"><span data-stu-id="5739a-123">Members</span></span>

#### <span data-ttu-id="5739a-124">Cancel</span><span class="sxs-lookup"><span data-stu-id="5739a-124">Cancel</span></span> 

<span data-ttu-id="5739a-125">ホストでは、このフラグを設定して移動を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="5739a-125">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="5739a-126">パブリックブール値の[キャンセル](#cancel)</span><span class="sxs-lookup"><span data-stu-id="5739a-126">public bool [Cancel](#cancel)</span></span>

<span data-ttu-id="5739a-127">設定されている場合は、ナビゲーションが行われないか、現在のページのコンテンツがそのまま保持されます。</span><span class="sxs-lookup"><span data-stu-id="5739a-127">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="5739a-128">パフォーマンス上の理由から、GET HTTP 要求は、ホストの応答中に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5739a-128">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="5739a-129">つまり、ナビゲーションの要求の一部を cookie に設定して使うことができます。</span><span class="sxs-lookup"><span data-stu-id="5739a-129">This means cookies can be set and used part of a request for the navigation.</span></span>

#### <span data-ttu-id="5739a-130">IsRedirected</span><span class="sxs-lookup"><span data-stu-id="5739a-130">IsRedirected</span></span> 

<span data-ttu-id="5739a-131">ナビゲーションがリダイレクトされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="5739a-131">True when the navigation is redirected.</span></span>

> <span data-ttu-id="5739a-132">パブリックブール値[リダイレクト](#isredirected)</span><span class="sxs-lookup"><span data-stu-id="5739a-132">public bool [IsRedirected](#isredirected)</span></span>

#### <span data-ttu-id="5739a-133">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="5739a-133">IsUserInitiated</span></span> 

<span data-ttu-id="5739a-134">プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="5739a-134">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="5739a-135">public bool [Isuserinitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="5739a-135">public bool [IsUserInitiated](#isuserinitiated)</span></span>

#### <span data-ttu-id="5739a-136">NavigationId</span><span class="sxs-lookup"><span data-stu-id="5739a-136">NavigationId</span></span> 

<span data-ttu-id="5739a-137">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="5739a-137">The ID of the navigation.</span></span>

> <span data-ttu-id="5739a-138">パブリック ulong [Navigationid](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="5739a-138">public ulong [NavigationId](#navigationid)</span></span>

#### <span data-ttu-id="5739a-139">RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="5739a-139">RequestHeaders</span></span> 

<span data-ttu-id="5739a-140">ナビゲーションの HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="5739a-140">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="5739a-141">パブリック HttpRequestHeaders [RequestHeaders](#requestheaders)</span><span class="sxs-lookup"><span data-stu-id="5739a-141">public HttpRequestHeaders [RequestHeaders](#requestheaders)</span></span>

<span data-ttu-id="5739a-142">ただし、NavigationStarting イベントの HTTP 要求ヘッダーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="5739a-142">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="5739a-143">URI</span><span class="sxs-lookup"><span data-stu-id="5739a-143">Uri</span></span> 

<span data-ttu-id="5739a-144">要求されたナビゲーションの uri。</span><span class="sxs-lookup"><span data-stu-id="5739a-144">The uri of the requested navigation.</span></span>

> <span data-ttu-id="5739a-145">パブリック文字列の[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="5739a-145">public string [Uri](#uri)</span></span>

