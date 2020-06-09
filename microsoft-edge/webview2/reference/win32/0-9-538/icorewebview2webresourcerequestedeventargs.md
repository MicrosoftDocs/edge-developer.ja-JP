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
ms.openlocfilehash: e83078b6ac45fbc0b479c5d6b0fde3263a8f34fd
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699037"
---
# <span data-ttu-id="4f116-104">インターフェイス ICoreWebView2WebResourceRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="4f116-104">interface ICoreWebView2WebResourceRequestedEventArgs</span></span> 

```
interface ICoreWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="4f116-105">WebResourceRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="4f116-105">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="4f116-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="4f116-106">Summary</span></span>

 <span data-ttu-id="4f116-107">Members</span><span class="sxs-lookup"><span data-stu-id="4f116-107">Members</span></span>                        | <span data-ttu-id="4f116-108">説明</span><span class="sxs-lookup"><span data-stu-id="4f116-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4f116-109">get_Request</span><span class="sxs-lookup"><span data-stu-id="4f116-109">get_Request</span></span>](#get_request) | <span data-ttu-id="4f116-110">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="4f116-110">The HTTP request.</span></span>
[<span data-ttu-id="4f116-111">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="4f116-111">get_ResourceContext</span></span>](#get_resourcecontext) | <span data-ttu-id="4f116-112">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="4f116-112">The web resource request contexts.</span></span>
[<span data-ttu-id="4f116-113">get_Response</span><span class="sxs-lookup"><span data-stu-id="4f116-113">get_Response</span></span>](#get_response) | <span data-ttu-id="4f116-114">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="4f116-114">The HTTP response.</span></span>
[<span data-ttu-id="4f116-115">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="4f116-115">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="4f116-116">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="4f116-116">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>
[<span data-ttu-id="4f116-117">put_Response</span><span class="sxs-lookup"><span data-stu-id="4f116-117">put_Response</span></span>](#put_response) | <span data-ttu-id="4f116-118">Response プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="4f116-118">Set the Response property.</span></span>

## <span data-ttu-id="4f116-119">Members</span><span class="sxs-lookup"><span data-stu-id="4f116-119">Members</span></span>

#### <span data-ttu-id="4f116-120">get_Request</span><span class="sxs-lookup"><span data-stu-id="4f116-120">get_Request</span></span> 

<span data-ttu-id="4f116-121">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="4f116-121">The HTTP request.</span></span>

> <span data-ttu-id="4f116-122">パブリック HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](icorewebview2webresourcerequest.md) \* \* Request)</span><span class="sxs-lookup"><span data-stu-id="4f116-122">public HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](icorewebview2webresourcerequest.md) \*\* request)</span></span>

#### <span data-ttu-id="4f116-123">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="4f116-123">get_ResourceContext</span></span> 

<span data-ttu-id="4f116-124">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="4f116-124">The web resource request contexts.</span></span>

> <span data-ttu-id="4f116-125">パブリック HRESULT [get_ResourceContext](#get_resourcecontext)(COREWEBVIEW2_WEB_RESOURCE_CONTEXT \* コンテキスト)</span><span class="sxs-lookup"><span data-stu-id="4f116-125">public HRESULT [get_ResourceContext](#get_resourcecontext)(COREWEBVIEW2_WEB_RESOURCE_CONTEXT \* context)</span></span>

#### <span data-ttu-id="4f116-126">get_Response</span><span class="sxs-lookup"><span data-stu-id="4f116-126">get_Response</span></span> 

<span data-ttu-id="4f116-127">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="4f116-127">The HTTP response.</span></span>

> <span data-ttu-id="4f116-128">パブリック HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* \* 応答)</span><span class="sxs-lookup"><span data-stu-id="4f116-128">public HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \*\* response)</span></span>

#### <span data-ttu-id="4f116-129">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="4f116-129">GetDeferral</span></span> 

<span data-ttu-id="4f116-130">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="4f116-130">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="4f116-131">パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="4f116-131">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="4f116-132">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを使って、後でネットワーク要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="4f116-132">You can use the [ICoreWebView2Deferral](icorewebview2deferral.md) object to complete the network request at a later time.</span></span>

#### <span data-ttu-id="4f116-133">put_Response</span><span class="sxs-lookup"><span data-stu-id="4f116-133">put_Response</span></span> 

<span data-ttu-id="4f116-134">Response プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="4f116-134">Set the Response property.</span></span>

> <span data-ttu-id="4f116-135">パブリック HRESULT [put_Response](#put_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* Response)</span><span class="sxs-lookup"><span data-stu-id="4f116-135">public HRESULT [put_Response](#put_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* response)</span></span>

