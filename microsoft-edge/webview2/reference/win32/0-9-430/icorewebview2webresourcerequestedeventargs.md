---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2WebResourceRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 00aaddcc732076e4f7aa808b04132641fe7fe969
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886445"
---
# <span data-ttu-id="ec012-104">0.9.430-インターフェイス ICoreWebView2WebResourceRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="ec012-104">0.9.430 - interface ICoreWebView2WebResourceRequestedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="ec012-105">WebResourceRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="ec012-105">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="ec012-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="ec012-106">Summary</span></span>

 <span data-ttu-id="ec012-107">Members</span><span class="sxs-lookup"><span data-stu-id="ec012-107">Members</span></span>                        | <span data-ttu-id="ec012-108">説明</span><span class="sxs-lookup"><span data-stu-id="ec012-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ec012-109">get_Request</span><span class="sxs-lookup"><span data-stu-id="ec012-109">get_Request</span></span>](#get_request) | <span data-ttu-id="ec012-110">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="ec012-110">The HTTP request.</span></span>
[<span data-ttu-id="ec012-111">get_Response</span><span class="sxs-lookup"><span data-stu-id="ec012-111">get_Response</span></span>](#get_response) | <span data-ttu-id="ec012-112">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="ec012-112">The HTTP response.</span></span>
[<span data-ttu-id="ec012-113">put_Response</span><span class="sxs-lookup"><span data-stu-id="ec012-113">put_Response</span></span>](#put_response) | <span data-ttu-id="ec012-114">Response プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ec012-114">Set the Response property.</span></span>
[<span data-ttu-id="ec012-115">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="ec012-115">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="ec012-116">[ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="ec012-116">Obtain an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object and put the event into a deferred state.</span></span>
[<span data-ttu-id="ec012-117">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="ec012-117">get_ResourceContext</span></span>](#get_resourcecontext) | <span data-ttu-id="ec012-118">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="ec012-118">The web resource request contexts.</span></span>

## <span data-ttu-id="ec012-119">Members</span><span class="sxs-lookup"><span data-stu-id="ec012-119">Members</span></span>

#### <span data-ttu-id="ec012-120">get_Request</span><span class="sxs-lookup"><span data-stu-id="ec012-120">get_Request</span></span> 

<span data-ttu-id="ec012-121">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="ec012-121">The HTTP request.</span></span>

> <span data-ttu-id="ec012-122">パブリック HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](ICoreWebView2WebResourceRequest.md) \* \* Request)</span><span class="sxs-lookup"><span data-stu-id="ec012-122">public HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](ICoreWebView2WebResourceRequest.md) \*\* request)</span></span>

#### <span data-ttu-id="ec012-123">get_Response</span><span class="sxs-lookup"><span data-stu-id="ec012-123">get_Response</span></span> 

<span data-ttu-id="ec012-124">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="ec012-124">The HTTP response.</span></span>

> <span data-ttu-id="ec012-125">パブリック HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \* \* 応答)</span><span class="sxs-lookup"><span data-stu-id="ec012-125">public HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \*\* response)</span></span>

#### <span data-ttu-id="ec012-126">put_Response</span><span class="sxs-lookup"><span data-stu-id="ec012-126">put_Response</span></span> 

<span data-ttu-id="ec012-127">Response プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ec012-127">Set the Response property.</span></span>

> <span data-ttu-id="ec012-128">パブリック HRESULT [put_Response](#put_response)([ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \* Response)</span><span class="sxs-lookup"><span data-stu-id="ec012-128">public HRESULT [put_Response](#put_response)([ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \* response)</span></span>

#### <span data-ttu-id="ec012-129">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="ec012-129">GetDeferral</span></span> 

<span data-ttu-id="ec012-130">[ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="ec012-130">Obtain an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="ec012-131">パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="ec012-131">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="ec012-132">[ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを使って、後でネットワーク要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="ec012-132">You can use the [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object to complete the network request at a later time.</span></span>

#### <span data-ttu-id="ec012-133">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="ec012-133">get_ResourceContext</span></span> 

<span data-ttu-id="ec012-134">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="ec012-134">The web resource request contexts.</span></span>

> <span data-ttu-id="ec012-135">パブリック HRESULT [get_ResourceContext](#get_resourcecontext)(CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT \* コンテキスト)</span><span class="sxs-lookup"><span data-stu-id="ec012-135">public HRESULT [get_ResourceContext](#get_resourcecontext)(CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT \* context)</span></span>

