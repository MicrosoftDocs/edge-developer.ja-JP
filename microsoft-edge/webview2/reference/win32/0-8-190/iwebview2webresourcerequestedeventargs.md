---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2WebResourceRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: aa5206be13790fd7a783f2afb4471de90fc8f2ae
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885719"
---
# <span data-ttu-id="90d9f-104">0.8.355-インターフェイス IWebView2WebResourceRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="90d9f-104">0.8.355 - interface IWebView2WebResourceRequestedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="90d9f-105">WebResourceRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="90d9f-105">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="90d9f-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="90d9f-106">Summary</span></span>

 <span data-ttu-id="90d9f-107">Members</span><span class="sxs-lookup"><span data-stu-id="90d9f-107">Members</span></span>                        | <span data-ttu-id="90d9f-108">説明</span><span class="sxs-lookup"><span data-stu-id="90d9f-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="90d9f-109">get_Request</span><span class="sxs-lookup"><span data-stu-id="90d9f-109">get_Request</span></span>](#get_request) | <span data-ttu-id="90d9f-110">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="90d9f-110">The HTTP request.</span></span>
[<span data-ttu-id="90d9f-111">get_Response</span><span class="sxs-lookup"><span data-stu-id="90d9f-111">get_Response</span></span>](#get_response) | <span data-ttu-id="90d9f-112">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="90d9f-112">The HTTP response.</span></span>
[<span data-ttu-id="90d9f-113">put_Response</span><span class="sxs-lookup"><span data-stu-id="90d9f-113">put_Response</span></span>](#put_response) | <span data-ttu-id="90d9f-114">Response プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="90d9f-114">Set the Response property.</span></span>
[<span data-ttu-id="90d9f-115">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="90d9f-115">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="90d9f-116">[IWebView2Deferral](IWebView2Deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="90d9f-116">Obtain an [IWebView2Deferral](IWebView2Deferral.md) object and put the event into a deferred state.</span></span>

## <span data-ttu-id="90d9f-117">Members</span><span class="sxs-lookup"><span data-stu-id="90d9f-117">Members</span></span>

#### <span data-ttu-id="90d9f-118">get_Request</span><span class="sxs-lookup"><span data-stu-id="90d9f-118">get_Request</span></span> 

<span data-ttu-id="90d9f-119">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="90d9f-119">The HTTP request.</span></span>

> <span data-ttu-id="90d9f-120">パブリック HRESULT [get_Request](#get_request)([IWebView2WebResourceRequest](IWebView2WebResourceRequest.md) \* \* Request)</span><span class="sxs-lookup"><span data-stu-id="90d9f-120">public HRESULT [get_Request](#get_request)([IWebView2WebResourceRequest](IWebView2WebResourceRequest.md) \*\* request)</span></span>

#### <span data-ttu-id="90d9f-121">get_Response</span><span class="sxs-lookup"><span data-stu-id="90d9f-121">get_Response</span></span> 

<span data-ttu-id="90d9f-122">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="90d9f-122">The HTTP response.</span></span>

> <span data-ttu-id="90d9f-123">パブリック HRESULT [get_Response](#get_response)([IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) \* \* 応答)</span><span class="sxs-lookup"><span data-stu-id="90d9f-123">public HRESULT [get_Response](#get_response)([IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) \*\* response)</span></span>

#### <span data-ttu-id="90d9f-124">put_Response</span><span class="sxs-lookup"><span data-stu-id="90d9f-124">put_Response</span></span> 

<span data-ttu-id="90d9f-125">Response プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="90d9f-125">Set the Response property.</span></span>

> <span data-ttu-id="90d9f-126">パブリック HRESULT [put_Response](#put_response)([IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) \* Response)</span><span class="sxs-lookup"><span data-stu-id="90d9f-126">public HRESULT [put_Response](#put_response)([IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) \* response)</span></span>

#### <span data-ttu-id="90d9f-127">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="90d9f-127">GetDeferral</span></span> 

<span data-ttu-id="90d9f-128">[IWebView2Deferral](IWebView2Deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="90d9f-128">Obtain an [IWebView2Deferral](IWebView2Deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="90d9f-129">パブリック HRESULT [Getdeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="90d9f-129">public HRESULT [GetDeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="90d9f-130">[IWebView2Deferral](IWebView2Deferral.md)オブジェクトを使って、後でネットワーク要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="90d9f-130">You can use the [IWebView2Deferral](IWebView2Deferral.md) object to complete the network request at a later time.</span></span>

