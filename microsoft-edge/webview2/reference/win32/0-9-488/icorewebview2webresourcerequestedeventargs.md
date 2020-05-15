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
ms.openlocfilehash: 8cdedd8051f52b7f6ad187ec948eabef96c6670b
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654215"
---
# <span data-ttu-id="8d5f0-104">インターフェイス ICoreWebView2WebResourceRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="8d5f0-104">interface ICoreWebView2WebResourceRequestedEventArgs</span></span> 

```
interface ICoreWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="8d5f0-105">WebResourceRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="8d5f0-105">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="8d5f0-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="8d5f0-106">Summary</span></span>

 <span data-ttu-id="8d5f0-107">Members</span><span class="sxs-lookup"><span data-stu-id="8d5f0-107">Members</span></span>                        | <span data-ttu-id="8d5f0-108">説明</span><span class="sxs-lookup"><span data-stu-id="8d5f0-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="8d5f0-109">get_Request</span><span class="sxs-lookup"><span data-stu-id="8d5f0-109">get_Request</span></span>](#get_request) | <span data-ttu-id="8d5f0-110">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="8d5f0-110">The HTTP request.</span></span>
[<span data-ttu-id="8d5f0-111">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="8d5f0-111">get_ResourceContext</span></span>](#get_resourcecontext) | <span data-ttu-id="8d5f0-112">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="8d5f0-112">The web resource request contexts.</span></span>
[<span data-ttu-id="8d5f0-113">get_Response</span><span class="sxs-lookup"><span data-stu-id="8d5f0-113">get_Response</span></span>](#get_response) | <span data-ttu-id="8d5f0-114">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="8d5f0-114">The HTTP response.</span></span>
[<span data-ttu-id="8d5f0-115">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="8d5f0-115">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="8d5f0-116">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="8d5f0-116">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>
[<span data-ttu-id="8d5f0-117">put_Response</span><span class="sxs-lookup"><span data-stu-id="8d5f0-117">put_Response</span></span>](#put_response) | <span data-ttu-id="8d5f0-118">Response プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="8d5f0-118">Set the Response property.</span></span>

## <span data-ttu-id="8d5f0-119">Members</span><span class="sxs-lookup"><span data-stu-id="8d5f0-119">Members</span></span>

#### <span data-ttu-id="8d5f0-120">get_Request</span><span class="sxs-lookup"><span data-stu-id="8d5f0-120">get_Request</span></span> 

<span data-ttu-id="8d5f0-121">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="8d5f0-121">The HTTP request.</span></span>

> <span data-ttu-id="8d5f0-122">パブリック HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](icorewebview2webresourcerequest.md) \* \* Request)</span><span class="sxs-lookup"><span data-stu-id="8d5f0-122">public HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](icorewebview2webresourcerequest.md) \*\* request)</span></span>

#### <span data-ttu-id="8d5f0-123">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="8d5f0-123">get_ResourceContext</span></span> 

<span data-ttu-id="8d5f0-124">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="8d5f0-124">The web resource request contexts.</span></span>

> <span data-ttu-id="8d5f0-125">パブリック HRESULT [get_ResourceContext](#get_resourcecontext)(COREWEBVIEW2_WEB_RESOURCE_CONTEXT \* コンテキスト)</span><span class="sxs-lookup"><span data-stu-id="8d5f0-125">public HRESULT [get_ResourceContext](#get_resourcecontext)(COREWEBVIEW2_WEB_RESOURCE_CONTEXT \* context)</span></span>

#### <span data-ttu-id="8d5f0-126">get_Response</span><span class="sxs-lookup"><span data-stu-id="8d5f0-126">get_Response</span></span> 

<span data-ttu-id="8d5f0-127">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="8d5f0-127">The HTTP response.</span></span>

> <span data-ttu-id="8d5f0-128">パブリック HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* \* 応答)</span><span class="sxs-lookup"><span data-stu-id="8d5f0-128">public HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \*\* response)</span></span>

#### <span data-ttu-id="8d5f0-129">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="8d5f0-129">GetDeferral</span></span> 

<span data-ttu-id="8d5f0-130">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="8d5f0-130">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="8d5f0-131">パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="8d5f0-131">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="8d5f0-132">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを使って、後でネットワーク要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="8d5f0-132">You can use the [ICoreWebView2Deferral](icorewebview2deferral.md) object to complete the network request at a later time.</span></span>

#### <span data-ttu-id="8d5f0-133">put_Response</span><span class="sxs-lookup"><span data-stu-id="8d5f0-133">put_Response</span></span> 

<span data-ttu-id="8d5f0-134">Response プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="8d5f0-134">Set the Response property.</span></span>

> <span data-ttu-id="8d5f0-135">パブリック HRESULT [put_Response](#put_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* Response)</span><span class="sxs-lookup"><span data-stu-id="8d5f0-135">public HRESULT [put_Response](#put_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* response)</span></span>

