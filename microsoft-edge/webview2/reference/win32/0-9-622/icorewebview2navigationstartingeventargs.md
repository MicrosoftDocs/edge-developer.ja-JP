---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2NavigationStartingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2NavigationStartingEventArgs
ms.openlocfilehash: ebfb4aaf3f0c2b5531aaab3783572cf550bebf83
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012343"
---
# <span data-ttu-id="4ee2c-104">インターフェイス ICoreWebView2NavigationStartingEventArgs</span><span class="sxs-lookup"><span data-stu-id="4ee2c-104">interface ICoreWebView2NavigationStartingEventArgs</span></span> 

```
interface ICoreWebView2NavigationStartingEventArgs
  : public IUnknown
```

<span data-ttu-id="4ee2c-105">NavigationStarting イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="4ee2c-105">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="4ee2c-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="4ee2c-106">Summary</span></span>

 <span data-ttu-id="4ee2c-107">Members</span><span class="sxs-lookup"><span data-stu-id="4ee2c-107">Members</span></span>                        | <span data-ttu-id="4ee2c-108">説明</span><span class="sxs-lookup"><span data-stu-id="4ee2c-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4ee2c-109">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="4ee2c-109">get_Cancel</span></span>](#get_cancel) | <span data-ttu-id="4ee2c-110">ホストでは、このフラグを設定して移動を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="4ee2c-110">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="4ee2c-111">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="4ee2c-111">get_IsRedirected</span></span>](#get_isredirected) | <span data-ttu-id="4ee2c-112">ナビゲーションがリダイレクトされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="4ee2c-112">True when the navigation is redirected.</span></span>
[<span data-ttu-id="4ee2c-113">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="4ee2c-113">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="4ee2c-114">プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="4ee2c-114">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="4ee2c-115">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="4ee2c-115">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="4ee2c-116">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="4ee2c-116">The ID of the navigation.</span></span>
[<span data-ttu-id="4ee2c-117">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="4ee2c-117">get_RequestHeaders</span></span>](#get_requestheaders) | <span data-ttu-id="4ee2c-118">ナビゲーションの HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="4ee2c-118">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="4ee2c-119">get_Uri</span><span class="sxs-lookup"><span data-stu-id="4ee2c-119">get_Uri</span></span>](#get_uri) | <span data-ttu-id="4ee2c-120">要求されたナビゲーションの uri。</span><span class="sxs-lookup"><span data-stu-id="4ee2c-120">The uri of the requested navigation.</span></span>
[<span data-ttu-id="4ee2c-121">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="4ee2c-121">put_Cancel</span></span>](#put_cancel) | <span data-ttu-id="4ee2c-122">"キャンセル" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="4ee2c-122">Set the Cancel property.</span></span>

## <span data-ttu-id="4ee2c-123">Members</span><span class="sxs-lookup"><span data-stu-id="4ee2c-123">Members</span></span>

#### <span data-ttu-id="4ee2c-124">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="4ee2c-124">get_Cancel</span></span> 

<span data-ttu-id="4ee2c-125">ホストでは、このフラグを設定して移動を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="4ee2c-125">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="4ee2c-126">パブリック HRESULT [get_Cancel](#get_cancel)(ブール \* キャンセル)</span><span class="sxs-lookup"><span data-stu-id="4ee2c-126">public HRESULT [get_Cancel](#get_cancel)(BOOL \* cancel)</span></span>

<span data-ttu-id="4ee2c-127">設定されている場合は、ナビゲーションが行われないか、現在のページのコンテンツがそのまま保持されます。</span><span class="sxs-lookup"><span data-stu-id="4ee2c-127">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="4ee2c-128">パフォーマンス上の理由から、GET HTTP 要求は、ホストの応答中に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4ee2c-128">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="4ee2c-129">つまり、ナビゲーションの要求の一部を cookie に設定して使うことができます。</span><span class="sxs-lookup"><span data-stu-id="4ee2c-129">This means cookies can be set and used part of a request for the navigation.</span></span> <span data-ttu-id="4ee2c-130">"About" に移動するための取り消し: srcdoc への空白またはフレームのナビゲーションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4ee2c-130">Cancellation for navigation to about:blank or frame navigation to srcdoc is not supported.</span></span> <span data-ttu-id="4ee2c-131">このような試みは無視されます。</span><span class="sxs-lookup"><span data-stu-id="4ee2c-131">Such attempts will be ignored.</span></span>

#### <span data-ttu-id="4ee2c-132">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="4ee2c-132">get_IsRedirected</span></span> 

<span data-ttu-id="4ee2c-133">ナビゲーションがリダイレクトされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="4ee2c-133">True when the navigation is redirected.</span></span>

> <span data-ttu-id="4ee2c-134">パブリック HRESULT [get_IsRedirected](#get_isredirected)(ブール \* isredirected)</span><span class="sxs-lookup"><span data-stu-id="4ee2c-134">public HRESULT [get_IsRedirected](#get_isredirected)(BOOL \* isRedirected)</span></span>

#### <span data-ttu-id="4ee2c-135">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="4ee2c-135">get_IsUserInitiated</span></span> 

<span data-ttu-id="4ee2c-136">プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="4ee2c-136">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="4ee2c-137">パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール \* isUserInitiated)</span><span class="sxs-lookup"><span data-stu-id="4ee2c-137">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="4ee2c-138">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="4ee2c-138">get_NavigationId</span></span> 

<span data-ttu-id="4ee2c-139">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="4ee2c-139">The ID of the navigation.</span></span>

> <span data-ttu-id="4ee2c-140">パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigationid)</span><span class="sxs-lookup"><span data-stu-id="4ee2c-140">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigationId)</span></span>

#### <span data-ttu-id="4ee2c-141">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="4ee2c-141">get_RequestHeaders</span></span> 

<span data-ttu-id="4ee2c-142">ナビゲーションの HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="4ee2c-142">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="4ee2c-143">パブリック HRESULT [get_RequestHeaders](#get_requestheaders)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \* \* RequestHeaders)</span><span class="sxs-lookup"><span data-stu-id="4ee2c-143">public HRESULT [get_RequestHeaders](#get_requestheaders)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \*\* requestHeaders)</span></span>

<span data-ttu-id="4ee2c-144">ただし、NavigationStarting イベントの HTTP 要求ヘッダーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="4ee2c-144">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="4ee2c-145">get_Uri</span><span class="sxs-lookup"><span data-stu-id="4ee2c-145">get_Uri</span></span> 

<span data-ttu-id="4ee2c-146">要求されたナビゲーションの uri。</span><span class="sxs-lookup"><span data-stu-id="4ee2c-146">The uri of the requested navigation.</span></span>

> <span data-ttu-id="4ee2c-147">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="4ee2c-147">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="4ee2c-148">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="4ee2c-148">put_Cancel</span></span> 

<span data-ttu-id="4ee2c-149">"キャンセル" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="4ee2c-149">Set the Cancel property.</span></span>

> <span data-ttu-id="4ee2c-150">パブリック HRESULT [put_Cancel](#put_cancel)(ブール値のキャンセル)</span><span class="sxs-lookup"><span data-stu-id="4ee2c-150">public HRESULT [put_Cancel](#put_cancel)(BOOL cancel)</span></span>

