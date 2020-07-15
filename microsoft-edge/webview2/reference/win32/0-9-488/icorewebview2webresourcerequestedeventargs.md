---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2WebResourceRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 70a7d997dfd89b6d9bb8eb8af9a87ff0a130b69f
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880305"
---
# <span data-ttu-id="93c7a-104">0.9.515-インターフェイス ICoreWebView2WebResourceRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="93c7a-104">0.9.515 - interface ICoreWebView2WebResourceRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="93c7a-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="93c7a-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="93c7a-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93c7a-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="93c7a-107">WebResourceRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="93c7a-107">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="93c7a-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="93c7a-108">Summary</span></span>

 <span data-ttu-id="93c7a-109">Members</span><span class="sxs-lookup"><span data-stu-id="93c7a-109">Members</span></span>                        | <span data-ttu-id="93c7a-110">説明</span><span class="sxs-lookup"><span data-stu-id="93c7a-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="93c7a-111">get_Request</span><span class="sxs-lookup"><span data-stu-id="93c7a-111">get_Request</span></span>](#get_request) | <span data-ttu-id="93c7a-112">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="93c7a-112">The HTTP request.</span></span>
[<span data-ttu-id="93c7a-113">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="93c7a-113">get_ResourceContext</span></span>](#get_resourcecontext) | <span data-ttu-id="93c7a-114">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="93c7a-114">The web resource request contexts.</span></span>
[<span data-ttu-id="93c7a-115">get_Response</span><span class="sxs-lookup"><span data-stu-id="93c7a-115">get_Response</span></span>](#get_response) | <span data-ttu-id="93c7a-116">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="93c7a-116">The HTTP response.</span></span>
[<span data-ttu-id="93c7a-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="93c7a-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="93c7a-118">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="93c7a-118">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>
[<span data-ttu-id="93c7a-119">put_Response</span><span class="sxs-lookup"><span data-stu-id="93c7a-119">put_Response</span></span>](#put_response) | <span data-ttu-id="93c7a-120">Response プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="93c7a-120">Set the Response property.</span></span>

## <span data-ttu-id="93c7a-121">Members</span><span class="sxs-lookup"><span data-stu-id="93c7a-121">Members</span></span>

#### <span data-ttu-id="93c7a-122">get_Request</span><span class="sxs-lookup"><span data-stu-id="93c7a-122">get_Request</span></span> 

<span data-ttu-id="93c7a-123">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="93c7a-123">The HTTP request.</span></span>

> <span data-ttu-id="93c7a-124">パブリック HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](icorewebview2webresourcerequest.md) \* \* Request)</span><span class="sxs-lookup"><span data-stu-id="93c7a-124">public HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](icorewebview2webresourcerequest.md) \*\* request)</span></span>

#### <span data-ttu-id="93c7a-125">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="93c7a-125">get_ResourceContext</span></span> 

<span data-ttu-id="93c7a-126">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="93c7a-126">The web resource request contexts.</span></span>

> <span data-ttu-id="93c7a-127">パブリック HRESULT [get_ResourceContext](#get_resourcecontext)(COREWEBVIEW2_WEB_RESOURCE_CONTEXT \* コンテキスト)</span><span class="sxs-lookup"><span data-stu-id="93c7a-127">public HRESULT [get_ResourceContext](#get_resourcecontext)(COREWEBVIEW2_WEB_RESOURCE_CONTEXT \* context)</span></span>

#### <span data-ttu-id="93c7a-128">get_Response</span><span class="sxs-lookup"><span data-stu-id="93c7a-128">get_Response</span></span> 

<span data-ttu-id="93c7a-129">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="93c7a-129">The HTTP response.</span></span>

> <span data-ttu-id="93c7a-130">パブリック HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* \* 応答)</span><span class="sxs-lookup"><span data-stu-id="93c7a-130">public HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \*\* response)</span></span>

#### <span data-ttu-id="93c7a-131">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="93c7a-131">GetDeferral</span></span> 

<span data-ttu-id="93c7a-132">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="93c7a-132">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="93c7a-133">パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="93c7a-133">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="93c7a-134">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを使って、後でネットワーク要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="93c7a-134">You can use the [ICoreWebView2Deferral](icorewebview2deferral.md) object to complete the network request at a later time.</span></span>

#### <span data-ttu-id="93c7a-135">put_Response</span><span class="sxs-lookup"><span data-stu-id="93c7a-135">put_Response</span></span> 

<span data-ttu-id="93c7a-136">Response プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="93c7a-136">Set the Response property.</span></span>

> <span data-ttu-id="93c7a-137">パブリック HRESULT [put_Response](#put_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* Response)</span><span class="sxs-lookup"><span data-stu-id="93c7a-137">public HRESULT [put_Response](#put_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* response)</span></span>

