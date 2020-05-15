---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 899a6f50db1d77f3f24524c5ccec139dcbdbcaf9
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654231"
---
# <span data-ttu-id="3284c-104">インターフェイス IWebView2WebResourceRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="3284c-104">interface IWebView2WebResourceRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="3284c-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3284c-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="3284c-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3284c-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="3284c-107">WebResourceRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="3284c-107">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="3284c-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="3284c-108">Summary</span></span>

 <span data-ttu-id="3284c-109">Members</span><span class="sxs-lookup"><span data-stu-id="3284c-109">Members</span></span>                        | <span data-ttu-id="3284c-110">説明</span><span class="sxs-lookup"><span data-stu-id="3284c-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3284c-111">get_Request</span><span class="sxs-lookup"><span data-stu-id="3284c-111">get_Request</span></span>](#get_request) | <span data-ttu-id="3284c-112">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="3284c-112">The HTTP request.</span></span>
[<span data-ttu-id="3284c-113">get_Response</span><span class="sxs-lookup"><span data-stu-id="3284c-113">get_Response</span></span>](#get_response) | <span data-ttu-id="3284c-114">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="3284c-114">The HTTP response.</span></span>
[<span data-ttu-id="3284c-115">put_Response</span><span class="sxs-lookup"><span data-stu-id="3284c-115">put_Response</span></span>](#put_response) | <span data-ttu-id="3284c-116">Response プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="3284c-116">Set the Response property.</span></span>
[<span data-ttu-id="3284c-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="3284c-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="3284c-118">[IWebView2Deferral](IWebView2Deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="3284c-118">Obtain an [IWebView2Deferral](IWebView2Deferral.md) object and put the event into a deferred state.</span></span>

## <span data-ttu-id="3284c-119">Members</span><span class="sxs-lookup"><span data-stu-id="3284c-119">Members</span></span>

#### <span data-ttu-id="3284c-120">get_Request</span><span class="sxs-lookup"><span data-stu-id="3284c-120">get_Request</span></span> 

<span data-ttu-id="3284c-121">HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="3284c-121">The HTTP request.</span></span>

> <span data-ttu-id="3284c-122">パブリック HRESULT [get_Request](#get_request)([IWebView2WebResourceRequest](IWebView2WebResourceRequest.md) \* \* Request)</span><span class="sxs-lookup"><span data-stu-id="3284c-122">public HRESULT [get_Request](#get_request)([IWebView2WebResourceRequest](IWebView2WebResourceRequest.md) \*\* request)</span></span>

#### <span data-ttu-id="3284c-123">get_Response</span><span class="sxs-lookup"><span data-stu-id="3284c-123">get_Response</span></span> 

<span data-ttu-id="3284c-124">HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="3284c-124">The HTTP response.</span></span>

> <span data-ttu-id="3284c-125">パブリック HRESULT [get_Response](#get_response)([IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) \* \* 応答)</span><span class="sxs-lookup"><span data-stu-id="3284c-125">public HRESULT [get_Response](#get_response)([IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) \*\* response)</span></span>

#### <span data-ttu-id="3284c-126">put_Response</span><span class="sxs-lookup"><span data-stu-id="3284c-126">put_Response</span></span> 

<span data-ttu-id="3284c-127">Response プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="3284c-127">Set the Response property.</span></span>

> <span data-ttu-id="3284c-128">パブリック HRESULT [put_Response](#put_response)([IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) \* Response)</span><span class="sxs-lookup"><span data-stu-id="3284c-128">public HRESULT [put_Response](#put_response)([IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) \* response)</span></span>

#### <span data-ttu-id="3284c-129">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="3284c-129">GetDeferral</span></span> 

<span data-ttu-id="3284c-130">[IWebView2Deferral](IWebView2Deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="3284c-130">Obtain an [IWebView2Deferral](IWebView2Deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="3284c-131">パブリック HRESULT [Getdeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="3284c-131">public HRESULT [GetDeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="3284c-132">[IWebView2Deferral](IWebView2Deferral.md)オブジェクトを使って、後でネットワーク要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="3284c-132">You can use the [IWebView2Deferral](IWebView2Deferral.md) object to complete the network request at a later time.</span></span>

