---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: b0b868b99d3f77679b3684a20e7744d7a22fd715
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654354"
---
# <span data-ttu-id="8dbae-104">インターフェイス ICoreWebView2NavigationStartingEventArgs</span><span class="sxs-lookup"><span data-stu-id="8dbae-104">interface ICoreWebView2NavigationStartingEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="8dbae-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8dbae-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="8dbae-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8dbae-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2NavigationStartingEventArgs
  : public IUnknown
```

<span data-ttu-id="8dbae-107">NavigationStarting イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="8dbae-107">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="8dbae-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="8dbae-108">Summary</span></span>

 <span data-ttu-id="8dbae-109">Members</span><span class="sxs-lookup"><span data-stu-id="8dbae-109">Members</span></span>                        | <span data-ttu-id="8dbae-110">説明</span><span class="sxs-lookup"><span data-stu-id="8dbae-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="8dbae-111">get_Uri</span><span class="sxs-lookup"><span data-stu-id="8dbae-111">get_Uri</span></span>](#get_uri) | <span data-ttu-id="8dbae-112">要求されたナビゲーションの uri。</span><span class="sxs-lookup"><span data-stu-id="8dbae-112">The uri of the requested navigation.</span></span>
[<span data-ttu-id="8dbae-113">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="8dbae-113">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="8dbae-114">プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="8dbae-114">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="8dbae-115">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="8dbae-115">get_IsRedirected</span></span>](#get_isredirected) | <span data-ttu-id="8dbae-116">ナビゲーションがリダイレクトされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="8dbae-116">True when the navigation is redirected.</span></span>
[<span data-ttu-id="8dbae-117">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="8dbae-117">get_RequestHeaders</span></span>](#get_requestheaders) | <span data-ttu-id="8dbae-118">ナビゲーションの HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="8dbae-118">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="8dbae-119">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="8dbae-119">get_Cancel</span></span>](#get_cancel) | <span data-ttu-id="8dbae-120">ホストでは、このフラグを設定して移動を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="8dbae-120">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="8dbae-121">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="8dbae-121">put_Cancel</span></span>](#put_cancel) | <span data-ttu-id="8dbae-122">"キャンセル" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="8dbae-122">Set the Cancel property.</span></span>
[<span data-ttu-id="8dbae-123">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="8dbae-123">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="8dbae-124">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="8dbae-124">The ID of the navigation.</span></span>

## <span data-ttu-id="8dbae-125">Members</span><span class="sxs-lookup"><span data-stu-id="8dbae-125">Members</span></span>

#### <span data-ttu-id="8dbae-126">get_Uri</span><span class="sxs-lookup"><span data-stu-id="8dbae-126">get_Uri</span></span> 

<span data-ttu-id="8dbae-127">要求されたナビゲーションの uri。</span><span class="sxs-lookup"><span data-stu-id="8dbae-127">The uri of the requested navigation.</span></span>

> <span data-ttu-id="8dbae-128">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="8dbae-128">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="8dbae-129">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="8dbae-129">get_IsUserInitiated</span></span> 

<span data-ttu-id="8dbae-130">プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="8dbae-130">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="8dbae-131">パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール \* isUserInitiated)</span><span class="sxs-lookup"><span data-stu-id="8dbae-131">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="8dbae-132">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="8dbae-132">get_IsRedirected</span></span> 

<span data-ttu-id="8dbae-133">ナビゲーションがリダイレクトされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="8dbae-133">True when the navigation is redirected.</span></span>

> <span data-ttu-id="8dbae-134">パブリック HRESULT [get_IsRedirected](#get_isredirected)(ブール \* isredirected)</span><span class="sxs-lookup"><span data-stu-id="8dbae-134">public HRESULT [get_IsRedirected](#get_isredirected)(BOOL \* isRedirected)</span></span>

#### <span data-ttu-id="8dbae-135">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="8dbae-135">get_RequestHeaders</span></span> 

<span data-ttu-id="8dbae-136">ナビゲーションの HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="8dbae-136">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="8dbae-137">パブリック HRESULT [get_RequestHeaders](#get_requestheaders)([ICoreWebView2HttpRequestHeaders](ICoreWebView2HttpRequestHeaders.md) \* \* RequestHeaders)</span><span class="sxs-lookup"><span data-stu-id="8dbae-137">public HRESULT [get_RequestHeaders](#get_requestheaders)([ICoreWebView2HttpRequestHeaders](ICoreWebView2HttpRequestHeaders.md) \*\* requestHeaders)</span></span>

<span data-ttu-id="8dbae-138">ただし、NavigationStarting イベントの HTTP 要求ヘッダーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="8dbae-138">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="8dbae-139">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="8dbae-139">get_Cancel</span></span> 

<span data-ttu-id="8dbae-140">ホストでは、このフラグを設定して移動を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="8dbae-140">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="8dbae-141">パブリック HRESULT [get_Cancel](#get_cancel)(ブール \* キャンセル)</span><span class="sxs-lookup"><span data-stu-id="8dbae-141">public HRESULT [get_Cancel](#get_cancel)(BOOL \* cancel)</span></span>

<span data-ttu-id="8dbae-142">設定されている場合は、ナビゲーションが行われないか、現在のページのコンテンツがそのまま保持されます。</span><span class="sxs-lookup"><span data-stu-id="8dbae-142">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="8dbae-143">パフォーマンス上の理由から、GET HTTP 要求は、ホストの応答中に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8dbae-143">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="8dbae-144">つまり、ナビゲーションの要求の一部を cookie に設定して使うことができます。</span><span class="sxs-lookup"><span data-stu-id="8dbae-144">This means cookies can be set and used part of a request for the navigation.</span></span>

#### <span data-ttu-id="8dbae-145">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="8dbae-145">put_Cancel</span></span> 

<span data-ttu-id="8dbae-146">"キャンセル" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="8dbae-146">Set the Cancel property.</span></span>

> <span data-ttu-id="8dbae-147">パブリック HRESULT [put_Cancel](#put_cancel)(ブール値のキャンセル)</span><span class="sxs-lookup"><span data-stu-id="8dbae-147">public HRESULT [put_Cancel](#put_cancel)(BOOL cancel)</span></span>

#### <span data-ttu-id="8dbae-148">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="8dbae-148">get_NavigationId</span></span> 

<span data-ttu-id="8dbae-149">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="8dbae-149">The ID of the navigation.</span></span>

> <span data-ttu-id="8dbae-150">パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span><span class="sxs-lookup"><span data-stu-id="8dbae-150">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

