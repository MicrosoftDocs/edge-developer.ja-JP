---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2WebResourceRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2WebResourceRequestedEventArgs
ms.openlocfilehash: 3613ed9b2ef562e8760de1a88322ef028ddf4ca9
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879220"
---
# <span data-ttu-id="ace05-104">インターフェイス ICoreWebView2WebResourceRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="ace05-104">interface ICoreWebView2WebResourceRequestedEventArgs</span></span> 

```
interface ICoreWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="ace05-105">WebResourceRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="ace05-105">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="ace05-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="ace05-106">Summary</span></span>

 <span data-ttu-id="ace05-107">Members</span><span class="sxs-lookup"><span data-stu-id="ace05-107">Members</span></span>                        | <span data-ttu-id="ace05-108">説明</span><span class="sxs-lookup"><span data-stu-id="ace05-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ace05-109">get_Request</span><span class="sxs-lookup"><span data-stu-id="ace05-109">get_Request</span></span>](#get_request) | <span data-ttu-id="ace05-110">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="ace05-110">The HTTP request.</span></span>
[<span data-ttu-id="ace05-111">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="ace05-111">get_ResourceContext</span></span>](#get_resourcecontext) | <span data-ttu-id="ace05-112">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="ace05-112">The web resource request contexts.</span></span>
[<span data-ttu-id="ace05-113">get_Response</span><span class="sxs-lookup"><span data-stu-id="ace05-113">get_Response</span></span>](#get_response) | <span data-ttu-id="ace05-114">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="ace05-114">The HTTP response.</span></span>
[<span data-ttu-id="ace05-115">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="ace05-115">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="ace05-116">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="ace05-116">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>
[<span data-ttu-id="ace05-117">put_Response</span><span class="sxs-lookup"><span data-stu-id="ace05-117">put_Response</span></span>](#put_response) | <span data-ttu-id="ace05-118">Response プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ace05-118">Set the Response property.</span></span>

## <span data-ttu-id="ace05-119">Members</span><span class="sxs-lookup"><span data-stu-id="ace05-119">Members</span></span>

#### <span data-ttu-id="ace05-120">get_Request</span><span class="sxs-lookup"><span data-stu-id="ace05-120">get_Request</span></span> 

<span data-ttu-id="ace05-121">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="ace05-121">The HTTP request.</span></span>

> <span data-ttu-id="ace05-122">パブリック HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](icorewebview2webresourcerequest.md) \* \* Request)</span><span class="sxs-lookup"><span data-stu-id="ace05-122">public HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](icorewebview2webresourcerequest.md) \*\* request)</span></span>

#### <span data-ttu-id="ace05-123">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="ace05-123">get_ResourceContext</span></span> 

<span data-ttu-id="ace05-124">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="ace05-124">The web resource request contexts.</span></span>

> <span data-ttu-id="ace05-125">パブリック HRESULT [get_ResourceContext](#get_resourcecontext)(COREWEBVIEW2_WEB_RESOURCE_CONTEXT \* コンテキスト)</span><span class="sxs-lookup"><span data-stu-id="ace05-125">public HRESULT [get_ResourceContext](#get_resourcecontext)(COREWEBVIEW2_WEB_RESOURCE_CONTEXT \* context)</span></span>

#### <span data-ttu-id="ace05-126">get_Response</span><span class="sxs-lookup"><span data-stu-id="ace05-126">get_Response</span></span> 

<span data-ttu-id="ace05-127">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="ace05-127">The HTTP response.</span></span>

> <span data-ttu-id="ace05-128">パブリック HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* \* 応答)</span><span class="sxs-lookup"><span data-stu-id="ace05-128">public HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \*\* response)</span></span>

#### <span data-ttu-id="ace05-129">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="ace05-129">GetDeferral</span></span> 

<span data-ttu-id="ace05-130">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="ace05-130">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="ace05-131">パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="ace05-131">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="ace05-132">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを使って、後でネットワーク要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="ace05-132">You can use the [ICoreWebView2Deferral](icorewebview2deferral.md) object to complete the network request at a later time.</span></span>

#### <span data-ttu-id="ace05-133">put_Response</span><span class="sxs-lookup"><span data-stu-id="ace05-133">put_Response</span></span> 

<span data-ttu-id="ace05-134">Response プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ace05-134">Set the Response property.</span></span>

> <span data-ttu-id="ace05-135">パブリック HRESULT [put_Response](#put_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* Response)</span><span class="sxs-lookup"><span data-stu-id="ace05-135">public HRESULT [put_Response](#put_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* response)</span></span>

