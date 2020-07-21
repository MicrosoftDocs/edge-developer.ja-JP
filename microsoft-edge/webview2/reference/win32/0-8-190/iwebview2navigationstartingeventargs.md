---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2NavigationStartingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 5996f0eff4db17530750eb39c7693ea0f8496a4d
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885899"
---
# <span data-ttu-id="2ebd5-104">0.8.355-インターフェイス IWebView2NavigationStartingEventArgs</span><span class="sxs-lookup"><span data-stu-id="2ebd5-104">0.8.355 - interface IWebView2NavigationStartingEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2NavigationStartingEventArgs
  : public IUnknown
```

<span data-ttu-id="2ebd5-105">NavigationStarting イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="2ebd5-105">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="2ebd5-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="2ebd5-106">Summary</span></span>

 <span data-ttu-id="2ebd5-107">Members</span><span class="sxs-lookup"><span data-stu-id="2ebd5-107">Members</span></span>                        | <span data-ttu-id="2ebd5-108">説明</span><span class="sxs-lookup"><span data-stu-id="2ebd5-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2ebd5-109">get_Uri</span><span class="sxs-lookup"><span data-stu-id="2ebd5-109">get_Uri</span></span>](#get_uri) | <span data-ttu-id="2ebd5-110">要求されたナビゲーションの uri。</span><span class="sxs-lookup"><span data-stu-id="2ebd5-110">The uri of the requested navigation.</span></span>
[<span data-ttu-id="2ebd5-111">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="2ebd5-111">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="2ebd5-112">プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="2ebd5-112">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="2ebd5-113">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="2ebd5-113">get_IsRedirected</span></span>](#get_isredirected) | <span data-ttu-id="2ebd5-114">ナビゲーションがリダイレクトされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="2ebd5-114">True when the navigation is redirected.</span></span>
[<span data-ttu-id="2ebd5-115">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="2ebd5-115">get_RequestHeaders</span></span>](#get_requestheaders) | <span data-ttu-id="2ebd5-116">ナビゲーションの HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="2ebd5-116">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="2ebd5-117">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="2ebd5-117">get_Cancel</span></span>](#get_cancel) | <span data-ttu-id="2ebd5-118">ホストでは、このフラグを設定して移動を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="2ebd5-118">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="2ebd5-119">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="2ebd5-119">put_Cancel</span></span>](#put_cancel) | <span data-ttu-id="2ebd5-120">"キャンセル" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2ebd5-120">Set the Cancel property.</span></span>

## <span data-ttu-id="2ebd5-121">Members</span><span class="sxs-lookup"><span data-stu-id="2ebd5-121">Members</span></span>

#### <span data-ttu-id="2ebd5-122">get_Uri</span><span class="sxs-lookup"><span data-stu-id="2ebd5-122">get_Uri</span></span> 

<span data-ttu-id="2ebd5-123">要求されたナビゲーションの uri。</span><span class="sxs-lookup"><span data-stu-id="2ebd5-123">The uri of the requested navigation.</span></span>

> <span data-ttu-id="2ebd5-124">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="2ebd5-124">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="2ebd5-125">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="2ebd5-125">get_IsUserInitiated</span></span> 

<span data-ttu-id="2ebd5-126">プログラムによるナビゲーションとは異なり、ナビゲーションがユーザーのジェスチャを通じて開始された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="2ebd5-126">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="2ebd5-127">パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール \* isUserInitiated)</span><span class="sxs-lookup"><span data-stu-id="2ebd5-127">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="2ebd5-128">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="2ebd5-128">get_IsRedirected</span></span> 

<span data-ttu-id="2ebd5-129">ナビゲーションがリダイレクトされた場合は True です。</span><span class="sxs-lookup"><span data-stu-id="2ebd5-129">True when the navigation is redirected.</span></span>

> <span data-ttu-id="2ebd5-130">パブリック HRESULT [get_IsRedirected](#get_isredirected)(ブール \* isredirected)</span><span class="sxs-lookup"><span data-stu-id="2ebd5-130">public HRESULT [get_IsRedirected](#get_isredirected)(BOOL \* isRedirected)</span></span>

#### <span data-ttu-id="2ebd5-131">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="2ebd5-131">get_RequestHeaders</span></span> 

<span data-ttu-id="2ebd5-132">ナビゲーションの HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="2ebd5-132">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="2ebd5-133">パブリック HRESULT [get_RequestHeaders](#get_requestheaders)([IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md) \* \* RequestHeaders)</span><span class="sxs-lookup"><span data-stu-id="2ebd5-133">public HRESULT [get_RequestHeaders](#get_requestheaders)([IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md) \*\* requestHeaders)</span></span>

<span data-ttu-id="2ebd5-134">ただし、NavigationStarting イベントの HTTP 要求ヘッダーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="2ebd5-134">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="2ebd5-135">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="2ebd5-135">get_Cancel</span></span> 

<span data-ttu-id="2ebd5-136">ホストでは、このフラグを設定して移動を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="2ebd5-136">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="2ebd5-137">パブリック HRESULT [get_Cancel](#get_cancel)(ブール \* キャンセル)</span><span class="sxs-lookup"><span data-stu-id="2ebd5-137">public HRESULT [get_Cancel](#get_cancel)(BOOL \* cancel)</span></span>

<span data-ttu-id="2ebd5-138">設定されている場合は、ナビゲーションが行われないか、現在のページのコンテンツがそのまま保持されます。</span><span class="sxs-lookup"><span data-stu-id="2ebd5-138">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="2ebd5-139">パフォーマンス上の理由から、GET HTTP 要求は、ホストの応答中に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2ebd5-139">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="2ebd5-140">つまり、ナビゲーションの要求の一部を cookie に設定して使うことができます。</span><span class="sxs-lookup"><span data-stu-id="2ebd5-140">This means cookies can be set and used part of a request for the navigation.</span></span>

#### <span data-ttu-id="2ebd5-141">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="2ebd5-141">put_Cancel</span></span> 

<span data-ttu-id="2ebd5-142">"キャンセル" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2ebd5-142">Set the Cancel property.</span></span>

> <span data-ttu-id="2ebd5-143">パブリック HRESULT [put_Cancel](#put_cancel)(ブール値のキャンセル)</span><span class="sxs-lookup"><span data-stu-id="2ebd5-143">public HRESULT [put_Cancel](#put_cancel)(BOOL cancel)</span></span>

