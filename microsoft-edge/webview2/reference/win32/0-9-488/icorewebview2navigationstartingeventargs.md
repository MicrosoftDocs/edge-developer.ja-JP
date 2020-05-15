---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 3b348d64bb09fcdc693ffbdfa5481fe6d7520cae
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654235"
---
# <span data-ttu-id="8e726-104">インターフェイス ICoreWebView2NavigationStartingEventArgs</span><span class="sxs-lookup"><span data-stu-id="8e726-104">interface ICoreWebView2NavigationStartingEventArgs</span></span> 

```
interface ICoreWebView2NavigationStartingEventArgs
  : public IUnknown
```

<span data-ttu-id="8e726-105">NavigationStarting イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="8e726-105">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="8e726-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="8e726-106">Summary</span></span>

 <span data-ttu-id="8e726-107">Members</span><span class="sxs-lookup"><span data-stu-id="8e726-107">Members</span></span>                        | <span data-ttu-id="8e726-108">説明</span><span class="sxs-lookup"><span data-stu-id="8e726-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="8e726-109">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="8e726-109">get_Cancel</span></span>](#get_cancel) | <span data-ttu-id="8e726-110">ホストでは、このフラグを設定して移動を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="8e726-110">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="8e726-111">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="8e726-111">get_IsRedirected</span></span>](#get_isredirected) | <span data-ttu-id="8e726-112">ナビゲーションがリダイレクトされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="8e726-112">True when the navigation is redirected.</span></span>
[<span data-ttu-id="8e726-113">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="8e726-113">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="8e726-114">プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="8e726-114">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="8e726-115">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="8e726-115">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="8e726-116">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="8e726-116">The ID of the navigation.</span></span>
[<span data-ttu-id="8e726-117">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="8e726-117">get_RequestHeaders</span></span>](#get_requestheaders) | <span data-ttu-id="8e726-118">ナビゲーションの HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="8e726-118">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="8e726-119">get_Uri</span><span class="sxs-lookup"><span data-stu-id="8e726-119">get_Uri</span></span>](#get_uri) | <span data-ttu-id="8e726-120">要求されたナビゲーションの uri。</span><span class="sxs-lookup"><span data-stu-id="8e726-120">The uri of the requested navigation.</span></span>
[<span data-ttu-id="8e726-121">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="8e726-121">put_Cancel</span></span>](#put_cancel) | <span data-ttu-id="8e726-122">"キャンセル" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="8e726-122">Set the Cancel property.</span></span>

## <span data-ttu-id="8e726-123">Members</span><span class="sxs-lookup"><span data-stu-id="8e726-123">Members</span></span>

#### <span data-ttu-id="8e726-124">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="8e726-124">get_Cancel</span></span> 

<span data-ttu-id="8e726-125">ホストでは、このフラグを設定して移動を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="8e726-125">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="8e726-126">パブリック HRESULT [get_Cancel](#get_cancel)(ブール \* キャンセル)</span><span class="sxs-lookup"><span data-stu-id="8e726-126">public HRESULT [get_Cancel](#get_cancel)(BOOL \* cancel)</span></span>

<span data-ttu-id="8e726-127">設定されている場合は、ナビゲーションが行われないか、現在のページのコンテンツがそのまま保持されます。</span><span class="sxs-lookup"><span data-stu-id="8e726-127">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="8e726-128">パフォーマンス上の理由から、GET HTTP 要求は、ホストの応答中に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8e726-128">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="8e726-129">つまり、ナビゲーションの要求の一部を cookie に設定して使うことができます。</span><span class="sxs-lookup"><span data-stu-id="8e726-129">This means cookies can be set and used part of a request for the navigation.</span></span>

#### <span data-ttu-id="8e726-130">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="8e726-130">get_IsRedirected</span></span> 

<span data-ttu-id="8e726-131">ナビゲーションがリダイレクトされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="8e726-131">True when the navigation is redirected.</span></span>

> <span data-ttu-id="8e726-132">パブリック HRESULT [get_IsRedirected](#get_isredirected)(ブール \* isredirected)</span><span class="sxs-lookup"><span data-stu-id="8e726-132">public HRESULT [get_IsRedirected](#get_isredirected)(BOOL \* isRedirected)</span></span>

#### <span data-ttu-id="8e726-133">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="8e726-133">get_IsUserInitiated</span></span> 

<span data-ttu-id="8e726-134">プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="8e726-134">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="8e726-135">パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール \* isUserInitiated)</span><span class="sxs-lookup"><span data-stu-id="8e726-135">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="8e726-136">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="8e726-136">get_NavigationId</span></span> 

<span data-ttu-id="8e726-137">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="8e726-137">The ID of the navigation.</span></span>

> <span data-ttu-id="8e726-138">パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span><span class="sxs-lookup"><span data-stu-id="8e726-138">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

#### <span data-ttu-id="8e726-139">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="8e726-139">get_RequestHeaders</span></span> 

<span data-ttu-id="8e726-140">ナビゲーションの HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="8e726-140">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="8e726-141">パブリック HRESULT [get_RequestHeaders](#get_requestheaders)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \* \* RequestHeaders)</span><span class="sxs-lookup"><span data-stu-id="8e726-141">public HRESULT [get_RequestHeaders](#get_requestheaders)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \*\* requestHeaders)</span></span>

<span data-ttu-id="8e726-142">ただし、NavigationStarting イベントの HTTP 要求ヘッダーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="8e726-142">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="8e726-143">get_Uri</span><span class="sxs-lookup"><span data-stu-id="8e726-143">get_Uri</span></span> 

<span data-ttu-id="8e726-144">要求されたナビゲーションの uri。</span><span class="sxs-lookup"><span data-stu-id="8e726-144">The uri of the requested navigation.</span></span>

> <span data-ttu-id="8e726-145">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="8e726-145">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="8e726-146">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="8e726-146">put_Cancel</span></span> 

<span data-ttu-id="8e726-147">"キャンセル" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="8e726-147">Set the Cancel property.</span></span>

> <span data-ttu-id="8e726-148">パブリック HRESULT [put_Cancel](#put_cancel)(ブール値のキャンセル)</span><span class="sxs-lookup"><span data-stu-id="8e726-148">public HRESULT [put_Cancel](#put_cancel)(BOOL cancel)</span></span>

