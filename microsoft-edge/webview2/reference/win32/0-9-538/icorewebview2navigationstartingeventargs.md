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
ms.openlocfilehash: 705289c386a174bf6ac3929fabf9ede92e0987ae
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698946"
---
# <span data-ttu-id="e9efe-104">インターフェイス ICoreWebView2NavigationStartingEventArgs</span><span class="sxs-lookup"><span data-stu-id="e9efe-104">interface ICoreWebView2NavigationStartingEventArgs</span></span> 

```
interface ICoreWebView2NavigationStartingEventArgs
  : public IUnknown
```

<span data-ttu-id="e9efe-105">NavigationStarting イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="e9efe-105">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="e9efe-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="e9efe-106">Summary</span></span>

 <span data-ttu-id="e9efe-107">Members</span><span class="sxs-lookup"><span data-stu-id="e9efe-107">Members</span></span>                        | <span data-ttu-id="e9efe-108">説明</span><span class="sxs-lookup"><span data-stu-id="e9efe-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e9efe-109">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="e9efe-109">get_Cancel</span></span>](#get_cancel) | <span data-ttu-id="e9efe-110">ホストでは、このフラグを設定して移動を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="e9efe-110">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="e9efe-111">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="e9efe-111">get_IsRedirected</span></span>](#get_isredirected) | <span data-ttu-id="e9efe-112">ナビゲーションがリダイレクトされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="e9efe-112">True when the navigation is redirected.</span></span>
[<span data-ttu-id="e9efe-113">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="e9efe-113">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="e9efe-114">プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="e9efe-114">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="e9efe-115">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="e9efe-115">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="e9efe-116">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="e9efe-116">The ID of the navigation.</span></span>
[<span data-ttu-id="e9efe-117">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="e9efe-117">get_RequestHeaders</span></span>](#get_requestheaders) | <span data-ttu-id="e9efe-118">ナビゲーションの HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="e9efe-118">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="e9efe-119">get_Uri</span><span class="sxs-lookup"><span data-stu-id="e9efe-119">get_Uri</span></span>](#get_uri) | <span data-ttu-id="e9efe-120">要求されたナビゲーションの uri。</span><span class="sxs-lookup"><span data-stu-id="e9efe-120">The uri of the requested navigation.</span></span>
[<span data-ttu-id="e9efe-121">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="e9efe-121">put_Cancel</span></span>](#put_cancel) | <span data-ttu-id="e9efe-122">"キャンセル" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e9efe-122">Set the Cancel property.</span></span>

## <span data-ttu-id="e9efe-123">Members</span><span class="sxs-lookup"><span data-stu-id="e9efe-123">Members</span></span>

#### <span data-ttu-id="e9efe-124">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="e9efe-124">get_Cancel</span></span> 

<span data-ttu-id="e9efe-125">ホストでは、このフラグを設定して移動を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="e9efe-125">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="e9efe-126">パブリック HRESULT [get_Cancel](#get_cancel)(ブール \* キャンセル)</span><span class="sxs-lookup"><span data-stu-id="e9efe-126">public HRESULT [get_Cancel](#get_cancel)(BOOL \* cancel)</span></span>

<span data-ttu-id="e9efe-127">設定されている場合は、ナビゲーションが行われないか、現在のページのコンテンツがそのまま保持されます。</span><span class="sxs-lookup"><span data-stu-id="e9efe-127">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="e9efe-128">パフォーマンス上の理由から、GET HTTP 要求は、ホストの応答中に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e9efe-128">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="e9efe-129">つまり、ナビゲーションの要求の一部を cookie に設定して使うことができます。</span><span class="sxs-lookup"><span data-stu-id="e9efe-129">This means cookies can be set and used part of a request for the navigation.</span></span>

#### <span data-ttu-id="e9efe-130">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="e9efe-130">get_IsRedirected</span></span> 

<span data-ttu-id="e9efe-131">ナビゲーションがリダイレクトされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="e9efe-131">True when the navigation is redirected.</span></span>

> <span data-ttu-id="e9efe-132">パブリック HRESULT [get_IsRedirected](#get_isredirected)(ブール \* isredirected)</span><span class="sxs-lookup"><span data-stu-id="e9efe-132">public HRESULT [get_IsRedirected](#get_isredirected)(BOOL \* isRedirected)</span></span>

#### <span data-ttu-id="e9efe-133">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="e9efe-133">get_IsUserInitiated</span></span> 

<span data-ttu-id="e9efe-134">プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="e9efe-134">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="e9efe-135">パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール \* isUserInitiated)</span><span class="sxs-lookup"><span data-stu-id="e9efe-135">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="e9efe-136">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="e9efe-136">get_NavigationId</span></span> 

<span data-ttu-id="e9efe-137">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="e9efe-137">The ID of the navigation.</span></span>

> <span data-ttu-id="e9efe-138">パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span><span class="sxs-lookup"><span data-stu-id="e9efe-138">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

#### <span data-ttu-id="e9efe-139">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="e9efe-139">get_RequestHeaders</span></span> 

<span data-ttu-id="e9efe-140">ナビゲーションの HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="e9efe-140">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="e9efe-141">パブリック HRESULT [get_RequestHeaders](#get_requestheaders)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \* \* RequestHeaders)</span><span class="sxs-lookup"><span data-stu-id="e9efe-141">public HRESULT [get_RequestHeaders](#get_requestheaders)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \*\* requestHeaders)</span></span>

<span data-ttu-id="e9efe-142">ただし、NavigationStarting イベントの HTTP 要求ヘッダーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e9efe-142">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="e9efe-143">get_Uri</span><span class="sxs-lookup"><span data-stu-id="e9efe-143">get_Uri</span></span> 

<span data-ttu-id="e9efe-144">要求されたナビゲーションの uri。</span><span class="sxs-lookup"><span data-stu-id="e9efe-144">The uri of the requested navigation.</span></span>

> <span data-ttu-id="e9efe-145">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="e9efe-145">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="e9efe-146">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="e9efe-146">put_Cancel</span></span> 

<span data-ttu-id="e9efe-147">"キャンセル" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e9efe-147">Set the Cancel property.</span></span>

> <span data-ttu-id="e9efe-148">パブリック HRESULT [put_Cancel](#put_cancel)(ブール値のキャンセル)</span><span class="sxs-lookup"><span data-stu-id="e9efe-148">public HRESULT [put_Cancel](#put_cancel)(BOOL cancel)</span></span>

