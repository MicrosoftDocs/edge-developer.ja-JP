---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2NavigationStartingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 8bc625d12cc3b3ebe06970fd282dd8f60bcabd22
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878401"
---
# <span data-ttu-id="767b4-104">0.8.355-インターフェイス IWebView2NavigationStartingEventArgs</span><span class="sxs-lookup"><span data-stu-id="767b4-104">0.8.355 - interface IWebView2NavigationStartingEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="767b4-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="767b4-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="767b4-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="767b4-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2NavigationStartingEventArgs
  : public IUnknown
```

<span data-ttu-id="767b4-107">NavigationStarting イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="767b4-107">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="767b4-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="767b4-108">Summary</span></span>

 <span data-ttu-id="767b4-109">Members</span><span class="sxs-lookup"><span data-stu-id="767b4-109">Members</span></span>                        | <span data-ttu-id="767b4-110">説明</span><span class="sxs-lookup"><span data-stu-id="767b4-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="767b4-111">get_Uri</span><span class="sxs-lookup"><span data-stu-id="767b4-111">get_Uri</span></span>](#get_uri) | <span data-ttu-id="767b4-112">要求されたナビゲーションの uri。</span><span class="sxs-lookup"><span data-stu-id="767b4-112">The uri of the requested navigation.</span></span>
[<span data-ttu-id="767b4-113">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="767b4-113">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="767b4-114">プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="767b4-114">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="767b4-115">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="767b4-115">get_IsRedirected</span></span>](#get_isredirected) | <span data-ttu-id="767b4-116">ナビゲーションがリダイレクトされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="767b4-116">True when the navigation is redirected.</span></span>
[<span data-ttu-id="767b4-117">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="767b4-117">get_RequestHeaders</span></span>](#get_requestheaders) | <span data-ttu-id="767b4-118">ナビゲーションの HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="767b4-118">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="767b4-119">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="767b4-119">get_Cancel</span></span>](#get_cancel) | <span data-ttu-id="767b4-120">ホストでは、このフラグを設定して移動を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="767b4-120">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="767b4-121">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="767b4-121">put_Cancel</span></span>](#put_cancel) | <span data-ttu-id="767b4-122">"キャンセル" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="767b4-122">Set the Cancel property.</span></span>

## <span data-ttu-id="767b4-123">Members</span><span class="sxs-lookup"><span data-stu-id="767b4-123">Members</span></span>

#### <span data-ttu-id="767b4-124">get_Uri</span><span class="sxs-lookup"><span data-stu-id="767b4-124">get_Uri</span></span> 

<span data-ttu-id="767b4-125">要求されたナビゲーションの uri。</span><span class="sxs-lookup"><span data-stu-id="767b4-125">The uri of the requested navigation.</span></span>

> <span data-ttu-id="767b4-126">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="767b4-126">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="767b4-127">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="767b4-127">get_IsUserInitiated</span></span> 

<span data-ttu-id="767b4-128">プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="767b4-128">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="767b4-129">パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール \* isUserInitiated)</span><span class="sxs-lookup"><span data-stu-id="767b4-129">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="767b4-130">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="767b4-130">get_IsRedirected</span></span> 

<span data-ttu-id="767b4-131">ナビゲーションがリダイレクトされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="767b4-131">True when the navigation is redirected.</span></span>

> <span data-ttu-id="767b4-132">パブリック HRESULT [get_IsRedirected](#get_isredirected)(ブール \* isredirected)</span><span class="sxs-lookup"><span data-stu-id="767b4-132">public HRESULT [get_IsRedirected](#get_isredirected)(BOOL \* isRedirected)</span></span>

#### <span data-ttu-id="767b4-133">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="767b4-133">get_RequestHeaders</span></span> 

<span data-ttu-id="767b4-134">ナビゲーションの HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="767b4-134">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="767b4-135">パブリック HRESULT [get_RequestHeaders](#get_requestheaders)([IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md) \* \* RequestHeaders)</span><span class="sxs-lookup"><span data-stu-id="767b4-135">public HRESULT [get_RequestHeaders](#get_requestheaders)([IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md) \*\* requestHeaders)</span></span>

<span data-ttu-id="767b4-136">ただし、NavigationStarting イベントの HTTP 要求ヘッダーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="767b4-136">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="767b4-137">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="767b4-137">get_Cancel</span></span> 

<span data-ttu-id="767b4-138">ホストでは、このフラグを設定して移動を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="767b4-138">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="767b4-139">パブリック HRESULT [get_Cancel](#get_cancel)(ブール \* キャンセル)</span><span class="sxs-lookup"><span data-stu-id="767b4-139">public HRESULT [get_Cancel](#get_cancel)(BOOL \* cancel)</span></span>

<span data-ttu-id="767b4-140">設定されている場合は、ナビゲーションが行われないか、現在のページのコンテンツがそのまま保持されます。</span><span class="sxs-lookup"><span data-stu-id="767b4-140">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="767b4-141">パフォーマンス上の理由から、GET HTTP 要求は、ホストの応答中に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="767b4-141">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="767b4-142">つまり、ナビゲーションの要求の一部を cookie に設定して使うことができます。</span><span class="sxs-lookup"><span data-stu-id="767b4-142">This means cookies can be set and used part of a request for the navigation.</span></span>

#### <span data-ttu-id="767b4-143">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="767b4-143">put_Cancel</span></span> 

<span data-ttu-id="767b4-144">"キャンセル" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="767b4-144">Set the Cancel property.</span></span>

> <span data-ttu-id="767b4-145">パブリック HRESULT [put_Cancel](#put_cancel)(ブール値のキャンセル)</span><span class="sxs-lookup"><span data-stu-id="767b4-145">public HRESULT [put_Cancel](#put_cancel)(BOOL cancel)</span></span>

