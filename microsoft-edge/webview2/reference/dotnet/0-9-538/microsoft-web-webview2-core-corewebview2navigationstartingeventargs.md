---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2NavigationStartingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2NavigationStartingEventArgs。
ms.openlocfilehash: cd692de6aaa3dc694fb2fe149411e5fd64de1ee2
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878870"
---
# <span data-ttu-id="6a858-104">WebView2 クラス (CoreWebView2NavigationStartingEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="6a858-104">Microsoft.Web.WebView2.Core.CoreWebView2NavigationStartingEventArgs class</span></span> 

<span data-ttu-id="6a858-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="6a858-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="6a858-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="6a858-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="6a858-107">NavigationStarting イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="6a858-107">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="6a858-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="6a858-108">Summary</span></span>

 <span data-ttu-id="6a858-109">Members</span><span class="sxs-lookup"><span data-stu-id="6a858-109">Members</span></span>                        | <span data-ttu-id="6a858-110">説明</span><span class="sxs-lookup"><span data-stu-id="6a858-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6a858-111">Cancel</span><span class="sxs-lookup"><span data-stu-id="6a858-111">Cancel</span></span>](#cancel) | <span data-ttu-id="6a858-112">ホストでは、このフラグを設定して移動を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="6a858-112">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="6a858-113">IsRedirected</span><span class="sxs-lookup"><span data-stu-id="6a858-113">IsRedirected</span></span>](#isredirected) | <span data-ttu-id="6a858-114">ナビゲーションがリダイレクトされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="6a858-114">True when the navigation is redirected.</span></span>
[<span data-ttu-id="6a858-115">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="6a858-115">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="6a858-116">プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="6a858-116">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="6a858-117">NavigationId</span><span class="sxs-lookup"><span data-stu-id="6a858-117">NavigationId</span></span>](#navigationid) | <span data-ttu-id="6a858-118">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="6a858-118">The ID of the navigation.</span></span>
[<span data-ttu-id="6a858-119">RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="6a858-119">RequestHeaders</span></span>](#requestheaders) | <span data-ttu-id="6a858-120">ナビゲーションの HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="6a858-120">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="6a858-121">URI</span><span class="sxs-lookup"><span data-stu-id="6a858-121">Uri</span></span>](#uri) | <span data-ttu-id="6a858-122">要求されたナビゲーションの uri。</span><span class="sxs-lookup"><span data-stu-id="6a858-122">The uri of the requested navigation.</span></span>

## <span data-ttu-id="6a858-123">Members</span><span class="sxs-lookup"><span data-stu-id="6a858-123">Members</span></span>

#### <span data-ttu-id="6a858-124">Cancel</span><span class="sxs-lookup"><span data-stu-id="6a858-124">Cancel</span></span> 

<span data-ttu-id="6a858-125">ホストでは、このフラグを設定して移動を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="6a858-125">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="6a858-126">パブリックブール値の[キャンセル](#cancel)</span><span class="sxs-lookup"><span data-stu-id="6a858-126">public bool [Cancel](#cancel)</span></span>

<span data-ttu-id="6a858-127">設定されている場合は、ナビゲーションが行われないか、現在のページのコンテンツがそのまま保持されます。</span><span class="sxs-lookup"><span data-stu-id="6a858-127">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="6a858-128">パフォーマンス上の理由から、GET HTTP 要求は、ホストの応答中に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a858-128">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="6a858-129">つまり、ナビゲーションの要求の一部を cookie に設定して使うことができます。</span><span class="sxs-lookup"><span data-stu-id="6a858-129">This means cookies can be set and used part of a request for the navigation.</span></span>

#### <span data-ttu-id="6a858-130">IsRedirected</span><span class="sxs-lookup"><span data-stu-id="6a858-130">IsRedirected</span></span> 

<span data-ttu-id="6a858-131">ナビゲーションがリダイレクトされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="6a858-131">True when the navigation is redirected.</span></span>

> <span data-ttu-id="6a858-132">パブリックブール値[リダイレクト](#isredirected)</span><span class="sxs-lookup"><span data-stu-id="6a858-132">public bool [IsRedirected](#isredirected)</span></span>

#### <span data-ttu-id="6a858-133">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="6a858-133">IsUserInitiated</span></span> 

<span data-ttu-id="6a858-134">プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="6a858-134">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="6a858-135">public bool [Isuserinitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="6a858-135">public bool [IsUserInitiated](#isuserinitiated)</span></span>

#### <span data-ttu-id="6a858-136">NavigationId</span><span class="sxs-lookup"><span data-stu-id="6a858-136">NavigationId</span></span> 

<span data-ttu-id="6a858-137">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="6a858-137">The ID of the navigation.</span></span>

> <span data-ttu-id="6a858-138">パブリック ulong [Navigationid](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="6a858-138">public ulong [NavigationId](#navigationid)</span></span>

#### <span data-ttu-id="6a858-139">RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="6a858-139">RequestHeaders</span></span> 

<span data-ttu-id="6a858-140">ナビゲーションの HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="6a858-140">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="6a858-141">パブリック HttpRequestHeaders [RequestHeaders](#requestheaders)</span><span class="sxs-lookup"><span data-stu-id="6a858-141">public HttpRequestHeaders [RequestHeaders](#requestheaders)</span></span>

<span data-ttu-id="6a858-142">ただし、NavigationStarting イベントの HTTP 要求ヘッダーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="6a858-142">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="6a858-143">URI</span><span class="sxs-lookup"><span data-stu-id="6a858-143">Uri</span></span> 

<span data-ttu-id="6a858-144">要求されたナビゲーションの uri。</span><span class="sxs-lookup"><span data-stu-id="6a858-144">The uri of the requested navigation.</span></span>

> <span data-ttu-id="6a858-145">パブリック文字列の[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="6a858-145">public string [Uri](#uri)</span></span>

