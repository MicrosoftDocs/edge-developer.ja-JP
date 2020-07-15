---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2WebResourceRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 826cdf960a20e32b8e0fa6b5a8ddad720ac137a6
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877582"
---
# <span data-ttu-id="7e216-104">0.9.430-インターフェイス ICoreWebView2WebResourceRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="7e216-104">0.9.430 - interface ICoreWebView2WebResourceRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="7e216-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7e216-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="7e216-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e216-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="7e216-107">WebResourceRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="7e216-107">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="7e216-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="7e216-108">Summary</span></span>

 <span data-ttu-id="7e216-109">Members</span><span class="sxs-lookup"><span data-stu-id="7e216-109">Members</span></span>                        | <span data-ttu-id="7e216-110">説明</span><span class="sxs-lookup"><span data-stu-id="7e216-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="7e216-111">get_Request</span><span class="sxs-lookup"><span data-stu-id="7e216-111">get_Request</span></span>](#get_request) | <span data-ttu-id="7e216-112">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="7e216-112">The HTTP request.</span></span>
[<span data-ttu-id="7e216-113">get_Response</span><span class="sxs-lookup"><span data-stu-id="7e216-113">get_Response</span></span>](#get_response) | <span data-ttu-id="7e216-114">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="7e216-114">The HTTP response.</span></span>
[<span data-ttu-id="7e216-115">put_Response</span><span class="sxs-lookup"><span data-stu-id="7e216-115">put_Response</span></span>](#put_response) | <span data-ttu-id="7e216-116">Response プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="7e216-116">Set the Response property.</span></span>
[<span data-ttu-id="7e216-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="7e216-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="7e216-118">[ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="7e216-118">Obtain an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object and put the event into a deferred state.</span></span>
[<span data-ttu-id="7e216-119">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="7e216-119">get_ResourceContext</span></span>](#get_resourcecontext) | <span data-ttu-id="7e216-120">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="7e216-120">The web resource request contexts.</span></span>

## <span data-ttu-id="7e216-121">Members</span><span class="sxs-lookup"><span data-stu-id="7e216-121">Members</span></span>

#### <span data-ttu-id="7e216-122">get_Request</span><span class="sxs-lookup"><span data-stu-id="7e216-122">get_Request</span></span> 

<span data-ttu-id="7e216-123">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="7e216-123">The HTTP request.</span></span>

> <span data-ttu-id="7e216-124">パブリック HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](ICoreWebView2WebResourceRequest.md) \* \* Request)</span><span class="sxs-lookup"><span data-stu-id="7e216-124">public HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](ICoreWebView2WebResourceRequest.md) \*\* request)</span></span>

#### <span data-ttu-id="7e216-125">get_Response</span><span class="sxs-lookup"><span data-stu-id="7e216-125">get_Response</span></span> 

<span data-ttu-id="7e216-126">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="7e216-126">The HTTP response.</span></span>

> <span data-ttu-id="7e216-127">パブリック HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \* \* 応答)</span><span class="sxs-lookup"><span data-stu-id="7e216-127">public HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \*\* response)</span></span>

#### <span data-ttu-id="7e216-128">put_Response</span><span class="sxs-lookup"><span data-stu-id="7e216-128">put_Response</span></span> 

<span data-ttu-id="7e216-129">Response プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="7e216-129">Set the Response property.</span></span>

> <span data-ttu-id="7e216-130">パブリック HRESULT [put_Response](#put_response)([ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \* Response)</span><span class="sxs-lookup"><span data-stu-id="7e216-130">public HRESULT [put_Response](#put_response)([ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \* response)</span></span>

#### <span data-ttu-id="7e216-131">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="7e216-131">GetDeferral</span></span> 

<span data-ttu-id="7e216-132">[ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="7e216-132">Obtain an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="7e216-133">パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="7e216-133">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="7e216-134">[ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを使って、後でネットワーク要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="7e216-134">You can use the [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object to complete the network request at a later time.</span></span>

#### <span data-ttu-id="7e216-135">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="7e216-135">get_ResourceContext</span></span> 

<span data-ttu-id="7e216-136">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="7e216-136">The web resource request contexts.</span></span>

> <span data-ttu-id="7e216-137">パブリック HRESULT [get_ResourceContext](#get_resourcecontext)(CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT \* コンテキスト)</span><span class="sxs-lookup"><span data-stu-id="7e216-137">public HRESULT [get_ResourceContext](#get_resourcecontext)(CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT \* context)</span></span>

