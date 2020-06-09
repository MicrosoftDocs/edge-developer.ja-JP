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
ms.openlocfilehash: 58ca180e73c3e4644e466e13c4059f32102f1896
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698957"
---
# <span data-ttu-id="6e292-104">WebView2 クラス (CoreWebView2NavigationStartingEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="6e292-104">Microsoft.Web.WebView2.Core.CoreWebView2NavigationStartingEventArgs class</span></span> 

<span data-ttu-id="6e292-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="6e292-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="6e292-106">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="6e292-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="6e292-107">NavigationStarting イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="6e292-107">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="6e292-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="6e292-108">Summary</span></span>

 <span data-ttu-id="6e292-109">Members</span><span class="sxs-lookup"><span data-stu-id="6e292-109">Members</span></span>                        | <span data-ttu-id="6e292-110">説明</span><span class="sxs-lookup"><span data-stu-id="6e292-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6e292-111">Cancel</span><span class="sxs-lookup"><span data-stu-id="6e292-111">Cancel</span></span>](#cancel) | <span data-ttu-id="6e292-112">ホストでは、このフラグを設定して移動を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="6e292-112">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="6e292-113">IsRedirected</span><span class="sxs-lookup"><span data-stu-id="6e292-113">IsRedirected</span></span>](#isredirected) | <span data-ttu-id="6e292-114">ナビゲーションがリダイレクトされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="6e292-114">True when the navigation is redirected.</span></span>
[<span data-ttu-id="6e292-115">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="6e292-115">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="6e292-116">プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="6e292-116">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="6e292-117">NavigationId</span><span class="sxs-lookup"><span data-stu-id="6e292-117">NavigationId</span></span>](#navigationid) | <span data-ttu-id="6e292-118">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="6e292-118">The ID of the navigation.</span></span>
[<span data-ttu-id="6e292-119">RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="6e292-119">RequestHeaders</span></span>](#requestheaders) | <span data-ttu-id="6e292-120">ナビゲーションの HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="6e292-120">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="6e292-121">URI</span><span class="sxs-lookup"><span data-stu-id="6e292-121">Uri</span></span>](#uri) | <span data-ttu-id="6e292-122">要求されたナビゲーションの uri。</span><span class="sxs-lookup"><span data-stu-id="6e292-122">The uri of the requested navigation.</span></span>

## <span data-ttu-id="6e292-123">Members</span><span class="sxs-lookup"><span data-stu-id="6e292-123">Members</span></span>

#### <span data-ttu-id="6e292-124">Cancel</span><span class="sxs-lookup"><span data-stu-id="6e292-124">Cancel</span></span> 

<span data-ttu-id="6e292-125">ホストでは、このフラグを設定して移動を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="6e292-125">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="6e292-126">パブリックブール値の[キャンセル](#cancel)</span><span class="sxs-lookup"><span data-stu-id="6e292-126">public bool [Cancel](#cancel)</span></span>

<span data-ttu-id="6e292-127">設定されている場合は、ナビゲーションが行われないか、現在のページのコンテンツがそのまま保持されます。</span><span class="sxs-lookup"><span data-stu-id="6e292-127">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="6e292-128">パフォーマンス上の理由から、GET HTTP 要求は、ホストの応答中に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e292-128">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="6e292-129">つまり、ナビゲーションの要求の一部を cookie に設定して使うことができます。</span><span class="sxs-lookup"><span data-stu-id="6e292-129">This means cookies can be set and used part of a request for the navigation.</span></span>

#### <span data-ttu-id="6e292-130">IsRedirected</span><span class="sxs-lookup"><span data-stu-id="6e292-130">IsRedirected</span></span> 

<span data-ttu-id="6e292-131">ナビゲーションがリダイレクトされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="6e292-131">True when the navigation is redirected.</span></span>

> <span data-ttu-id="6e292-132">パブリックブール値[リダイレクト](#isredirected)</span><span class="sxs-lookup"><span data-stu-id="6e292-132">public bool [IsRedirected](#isredirected)</span></span>

#### <span data-ttu-id="6e292-133">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="6e292-133">IsUserInitiated</span></span> 

<span data-ttu-id="6e292-134">プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="6e292-134">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="6e292-135">public bool [Isuserinitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="6e292-135">public bool [IsUserInitiated](#isuserinitiated)</span></span>

#### <span data-ttu-id="6e292-136">NavigationId</span><span class="sxs-lookup"><span data-stu-id="6e292-136">NavigationId</span></span> 

<span data-ttu-id="6e292-137">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="6e292-137">The ID of the navigation.</span></span>

> <span data-ttu-id="6e292-138">パブリック ulong [Navigationid](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="6e292-138">public ulong [NavigationId](#navigationid)</span></span>

#### <span data-ttu-id="6e292-139">RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="6e292-139">RequestHeaders</span></span> 

<span data-ttu-id="6e292-140">ナビゲーションの HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="6e292-140">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="6e292-141">パブリック HttpRequestHeaders [RequestHeaders](#requestheaders)</span><span class="sxs-lookup"><span data-stu-id="6e292-141">public HttpRequestHeaders [RequestHeaders](#requestheaders)</span></span>

<span data-ttu-id="6e292-142">ただし、NavigationStarting イベントの HTTP 要求ヘッダーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="6e292-142">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="6e292-143">URI</span><span class="sxs-lookup"><span data-stu-id="6e292-143">Uri</span></span> 

<span data-ttu-id="6e292-144">要求されたナビゲーションの uri。</span><span class="sxs-lookup"><span data-stu-id="6e292-144">The uri of the requested navigation.</span></span>

> <span data-ttu-id="6e292-145">パブリック文字列の[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="6e292-145">public string [Uri](#uri)</span></span>

