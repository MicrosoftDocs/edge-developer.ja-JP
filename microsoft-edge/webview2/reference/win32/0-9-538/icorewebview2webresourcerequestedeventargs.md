---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2WebResourceRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2WebResourceRequestedEventArgs
ms.openlocfilehash: 2e55a43282a7548acefdb0b1ed1b8cac2254ef21
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010391"
---
# <span data-ttu-id="87862-104">0.9.579-インターフェイス ICoreWebView2WebResourceRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="87862-104">0.9.579 - interface ICoreWebView2WebResourceRequestedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="87862-105">WebResourceRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="87862-105">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="87862-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="87862-106">Summary</span></span>

 <span data-ttu-id="87862-107">Members</span><span class="sxs-lookup"><span data-stu-id="87862-107">Members</span></span>                        | <span data-ttu-id="87862-108">説明</span><span class="sxs-lookup"><span data-stu-id="87862-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="87862-109">get_Request</span><span class="sxs-lookup"><span data-stu-id="87862-109">get_Request</span></span>](#get_request) | <span data-ttu-id="87862-110">Web リソース要求。</span><span class="sxs-lookup"><span data-stu-id="87862-110">The Web resource request.</span></span>
[<span data-ttu-id="87862-111">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="87862-111">get_ResourceContext</span></span>](#get_resourcecontext) | <span data-ttu-id="87862-112">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="87862-112">The web resource request context.</span></span>
[<span data-ttu-id="87862-113">get_Response</span><span class="sxs-lookup"><span data-stu-id="87862-113">get_Response</span></span>](#get_response) | <span data-ttu-id="87862-114">Web リソース応答オブジェクトのプレースホルダー。</span><span class="sxs-lookup"><span data-stu-id="87862-114">A placeholder for the web resource response object.</span></span>
[<span data-ttu-id="87862-115">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="87862-115">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="87862-116">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="87862-116">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>
[<span data-ttu-id="87862-117">put_Response</span><span class="sxs-lookup"><span data-stu-id="87862-117">put_Response</span></span>](#put_response) | <span data-ttu-id="87862-118">Response プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="87862-118">Set the Response property.</span></span>

## <span data-ttu-id="87862-119">Members</span><span class="sxs-lookup"><span data-stu-id="87862-119">Members</span></span>

#### <span data-ttu-id="87862-120">get_Request</span><span class="sxs-lookup"><span data-stu-id="87862-120">get_Request</span></span> 

<span data-ttu-id="87862-121">Web リソース要求。</span><span class="sxs-lookup"><span data-stu-id="87862-121">The Web resource request.</span></span>

> <span data-ttu-id="87862-122">パブリック HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](icorewebview2webresourcerequest.md) \* \* Request)</span><span class="sxs-lookup"><span data-stu-id="87862-122">public HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](icorewebview2webresourcerequest.md) \*\* request)</span></span>

<span data-ttu-id="87862-123">要求オブジェクトに、後でネットワークスタックによって追加された一部のヘッダーが欠落している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="87862-123">The request object may be missing some headers that are added by network stack later on.</span></span>

#### <span data-ttu-id="87862-124">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="87862-124">get_ResourceContext</span></span> 

<span data-ttu-id="87862-125">Web リソース要求のコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="87862-125">The web resource request context.</span></span>

> <span data-ttu-id="87862-126">パブリック HRESULT [get_ResourceContext](#get_resourcecontext)(COREWEBVIEW2_WEB_RESOURCE_CONTEXT \* コンテキスト)</span><span class="sxs-lookup"><span data-stu-id="87862-126">public HRESULT [get_ResourceContext](#get_resourcecontext)(COREWEBVIEW2_WEB_RESOURCE_CONTEXT \* context)</span></span>

#### <span data-ttu-id="87862-127">get_Response</span><span class="sxs-lookup"><span data-stu-id="87862-127">get_Response</span></span> 

<span data-ttu-id="87862-128">Web リソース応答オブジェクトのプレースホルダー。</span><span class="sxs-lookup"><span data-stu-id="87862-128">A placeholder for the web resource response object.</span></span>

> <span data-ttu-id="87862-129">パブリック HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* \* 応答)</span><span class="sxs-lookup"><span data-stu-id="87862-129">public HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \*\* response)</span></span>

<span data-ttu-id="87862-130">このオブジェクトが設定されている場合、web リソース要求はこの応答で完了します。</span><span class="sxs-lookup"><span data-stu-id="87862-130">If this object is set, the web resource request will be completed with this response.</span></span>

#### <span data-ttu-id="87862-131">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="87862-131">GetDeferral</span></span> 

<span data-ttu-id="87862-132">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="87862-132">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="87862-133">パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="87862-133">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="87862-134">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを使って、後で要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="87862-134">You can use the [ICoreWebView2Deferral](icorewebview2deferral.md) object to complete the request at a later time.</span></span>

#### <span data-ttu-id="87862-135">put_Response</span><span class="sxs-lookup"><span data-stu-id="87862-135">put_Response</span></span> 

<span data-ttu-id="87862-136">Response プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="87862-136">Set the Response property.</span></span>

> <span data-ttu-id="87862-137">パブリック HRESULT [put_Response](#put_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* Response)</span><span class="sxs-lookup"><span data-stu-id="87862-137">public HRESULT [put_Response](#put_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* response)</span></span>

<span data-ttu-id="87862-138">空の Web リソース応答オブジェクトは、CreateWebResourceResponse を使って作成してから、その応答を構築するために変更することができます。</span><span class="sxs-lookup"><span data-stu-id="87862-138">An empty Web resource response object can be created with CreateWebResourceResponse and then modified to construct the response.</span></span>

