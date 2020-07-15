---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2NavigationStartingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 9aa44483fc824f8a26af6293f031c58d681de624
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880473"
---
# <span data-ttu-id="4da11-104">0.9.515-インターフェイス ICoreWebView2NavigationStartingEventArgs</span><span class="sxs-lookup"><span data-stu-id="4da11-104">0.9.515 - interface ICoreWebView2NavigationStartingEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="4da11-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4da11-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="4da11-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4da11-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2NavigationStartingEventArgs
  : public IUnknown
```

<span data-ttu-id="4da11-107">NavigationStarting イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="4da11-107">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="4da11-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="4da11-108">Summary</span></span>

 <span data-ttu-id="4da11-109">Members</span><span class="sxs-lookup"><span data-stu-id="4da11-109">Members</span></span>                        | <span data-ttu-id="4da11-110">説明</span><span class="sxs-lookup"><span data-stu-id="4da11-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4da11-111">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="4da11-111">get_Cancel</span></span>](#get_cancel) | <span data-ttu-id="4da11-112">ホストでは、このフラグを設定して移動を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="4da11-112">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="4da11-113">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="4da11-113">get_IsRedirected</span></span>](#get_isredirected) | <span data-ttu-id="4da11-114">ナビゲーションがリダイレクトされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="4da11-114">True when the navigation is redirected.</span></span>
[<span data-ttu-id="4da11-115">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="4da11-115">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="4da11-116">プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="4da11-116">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="4da11-117">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="4da11-117">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="4da11-118">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="4da11-118">The ID of the navigation.</span></span>
[<span data-ttu-id="4da11-119">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="4da11-119">get_RequestHeaders</span></span>](#get_requestheaders) | <span data-ttu-id="4da11-120">ナビゲーションの HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="4da11-120">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="4da11-121">get_Uri</span><span class="sxs-lookup"><span data-stu-id="4da11-121">get_Uri</span></span>](#get_uri) | <span data-ttu-id="4da11-122">要求されたナビゲーションの uri。</span><span class="sxs-lookup"><span data-stu-id="4da11-122">The uri of the requested navigation.</span></span>
[<span data-ttu-id="4da11-123">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="4da11-123">put_Cancel</span></span>](#put_cancel) | <span data-ttu-id="4da11-124">"キャンセル" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="4da11-124">Set the Cancel property.</span></span>

## <span data-ttu-id="4da11-125">Members</span><span class="sxs-lookup"><span data-stu-id="4da11-125">Members</span></span>

#### <span data-ttu-id="4da11-126">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="4da11-126">get_Cancel</span></span> 

<span data-ttu-id="4da11-127">ホストでは、このフラグを設定して移動を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="4da11-127">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="4da11-128">パブリック HRESULT [get_Cancel](#get_cancel)(ブール \* キャンセル)</span><span class="sxs-lookup"><span data-stu-id="4da11-128">public HRESULT [get_Cancel](#get_cancel)(BOOL \* cancel)</span></span>

<span data-ttu-id="4da11-129">設定されている場合は、ナビゲーションが行われないか、現在のページのコンテンツがそのまま保持されます。</span><span class="sxs-lookup"><span data-stu-id="4da11-129">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="4da11-130">パフォーマンス上の理由から、GET HTTP 要求は、ホストの応答中に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4da11-130">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="4da11-131">つまり、ナビゲーションの要求の一部を cookie に設定して使うことができます。</span><span class="sxs-lookup"><span data-stu-id="4da11-131">This means cookies can be set and used part of a request for the navigation.</span></span>

#### <span data-ttu-id="4da11-132">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="4da11-132">get_IsRedirected</span></span> 

<span data-ttu-id="4da11-133">ナビゲーションがリダイレクトされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="4da11-133">True when the navigation is redirected.</span></span>

> <span data-ttu-id="4da11-134">パブリック HRESULT [get_IsRedirected](#get_isredirected)(ブール \* isredirected)</span><span class="sxs-lookup"><span data-stu-id="4da11-134">public HRESULT [get_IsRedirected](#get_isredirected)(BOOL \* isRedirected)</span></span>

#### <span data-ttu-id="4da11-135">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="4da11-135">get_IsUserInitiated</span></span> 

<span data-ttu-id="4da11-136">プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="4da11-136">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="4da11-137">パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール \* isUserInitiated)</span><span class="sxs-lookup"><span data-stu-id="4da11-137">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="4da11-138">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="4da11-138">get_NavigationId</span></span> 

<span data-ttu-id="4da11-139">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="4da11-139">The ID of the navigation.</span></span>

> <span data-ttu-id="4da11-140">パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span><span class="sxs-lookup"><span data-stu-id="4da11-140">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

#### <span data-ttu-id="4da11-141">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="4da11-141">get_RequestHeaders</span></span> 

<span data-ttu-id="4da11-142">ナビゲーションの HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="4da11-142">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="4da11-143">パブリック HRESULT [get_RequestHeaders](#get_requestheaders)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \* \* RequestHeaders)</span><span class="sxs-lookup"><span data-stu-id="4da11-143">public HRESULT [get_RequestHeaders](#get_requestheaders)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \*\* requestHeaders)</span></span>

<span data-ttu-id="4da11-144">ただし、NavigationStarting イベントの HTTP 要求ヘッダーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="4da11-144">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="4da11-145">get_Uri</span><span class="sxs-lookup"><span data-stu-id="4da11-145">get_Uri</span></span> 

<span data-ttu-id="4da11-146">要求されたナビゲーションの uri。</span><span class="sxs-lookup"><span data-stu-id="4da11-146">The uri of the requested navigation.</span></span>

> <span data-ttu-id="4da11-147">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="4da11-147">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="4da11-148">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="4da11-148">put_Cancel</span></span> 

<span data-ttu-id="4da11-149">"キャンセル" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="4da11-149">Set the Cancel property.</span></span>

> <span data-ttu-id="4da11-150">パブリック HRESULT [put_Cancel](#put_cancel)(ブール値のキャンセル)</span><span class="sxs-lookup"><span data-stu-id="4da11-150">public HRESULT [put_Cancel](#put_cancel)(BOOL cancel)</span></span>

