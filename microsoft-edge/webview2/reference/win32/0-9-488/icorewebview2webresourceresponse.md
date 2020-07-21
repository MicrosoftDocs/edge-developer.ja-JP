---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2WebResourceResponse
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: e17e12759bef051a33e99999f0e938da5bd16939
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883785"
---
# <span data-ttu-id="6f7c2-104">0.9.515-インターフェイス ICoreWebView2WebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="6f7c2-104">0.9.515 - interface ICoreWebView2WebResourceResponse</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebResourceResponse
  : public IUnknown
```

<span data-ttu-id="6f7c2-105">WebResourceRequested イベントと共に使用される HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="6f7c2-105">An HTTP response used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="6f7c2-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="6f7c2-106">Summary</span></span>

 <span data-ttu-id="6f7c2-107">Members</span><span class="sxs-lookup"><span data-stu-id="6f7c2-107">Members</span></span>                        | <span data-ttu-id="6f7c2-108">説明</span><span class="sxs-lookup"><span data-stu-id="6f7c2-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6f7c2-109">get_Content</span><span class="sxs-lookup"><span data-stu-id="6f7c2-109">get_Content</span></span>](#get_content) | <span data-ttu-id="6f7c2-110">ストリームとしての HTTP 応答のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="6f7c2-110">HTTP response content as stream.</span></span>
[<span data-ttu-id="6f7c2-111">get_Headers</span><span class="sxs-lookup"><span data-stu-id="6f7c2-111">get_Headers</span></span>](#get_headers) | <span data-ttu-id="6f7c2-112">上書きされた HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="6f7c2-112">Overridden HTTP response headers.</span></span>
[<span data-ttu-id="6f7c2-113">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="6f7c2-113">get_ReasonPhrase</span></span>](#get_reasonphrase) | <span data-ttu-id="6f7c2-114">HTTP 応答の理由の語句。</span><span class="sxs-lookup"><span data-stu-id="6f7c2-114">The HTTP response reason phrase.</span></span>
[<span data-ttu-id="6f7c2-115">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="6f7c2-115">get_StatusCode</span></span>](#get_statuscode) | <span data-ttu-id="6f7c2-116">HTTP 応答状態コード。</span><span class="sxs-lookup"><span data-stu-id="6f7c2-116">The HTTP response status code.</span></span>
[<span data-ttu-id="6f7c2-117">put_Content</span><span class="sxs-lookup"><span data-stu-id="6f7c2-117">put_Content</span></span>](#put_content) | <span data-ttu-id="6f7c2-118">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6f7c2-118">Set the Content property.</span></span>
[<span data-ttu-id="6f7c2-119">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="6f7c2-119">put_ReasonPhrase</span></span>](#put_reasonphrase) | <span data-ttu-id="6f7c2-120">"理由" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6f7c2-120">Set the ReasonPhrase property.</span></span>
[<span data-ttu-id="6f7c2-121">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="6f7c2-121">put_StatusCode</span></span>](#put_statuscode) | <span data-ttu-id="6f7c2-122">StatusCode プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6f7c2-122">Set the StatusCode property.</span></span>

## <span data-ttu-id="6f7c2-123">Members</span><span class="sxs-lookup"><span data-stu-id="6f7c2-123">Members</span></span>

#### <span data-ttu-id="6f7c2-124">get_Content</span><span class="sxs-lookup"><span data-stu-id="6f7c2-124">get_Content</span></span> 

<span data-ttu-id="6f7c2-125">ストリームとしての HTTP 応答のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="6f7c2-125">HTTP response content as stream.</span></span>

> <span data-ttu-id="6f7c2-126">パブリック HRESULT [get_Content](#get_content)(IStream \* \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="6f7c2-126">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="6f7c2-127">この応答の WebResourceRequested イベントの遅延が完了するまで、ストリームにはすべてのコンテンツデータが利用可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f7c2-127">Stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="6f7c2-128">UI スレッドに対するパフォーマンスへの影響を防ぐには、ストリームをアジャイルにするか、バックグラウンドスレッドから作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f7c2-128">Stream should be agile or be created from a background thread to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="6f7c2-129">Null はコンテンツデータがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="6f7c2-129">Null means no content data.</span></span> <span data-ttu-id="6f7c2-130">IStream セマンティクスが適用されます (すべてのデータが使い果たされるまで、S_OK は読み取り呼び出しに戻ります)</span><span class="sxs-lookup"><span data-stu-id="6f7c2-130">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="6f7c2-131">get_Headers</span><span class="sxs-lookup"><span data-stu-id="6f7c2-131">get_Headers</span></span> 

<span data-ttu-id="6f7c2-132">上書きされた HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="6f7c2-132">Overridden HTTP response headers.</span></span>

> <span data-ttu-id="6f7c2-133">パブリック HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) \* \* ヘッダー)</span><span class="sxs-lookup"><span data-stu-id="6f7c2-133">public HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) \*\* headers)</span></span>

#### <span data-ttu-id="6f7c2-134">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="6f7c2-134">get_ReasonPhrase</span></span> 

<span data-ttu-id="6f7c2-135">HTTP 応答の理由の語句。</span><span class="sxs-lookup"><span data-stu-id="6f7c2-135">The HTTP response reason phrase.</span></span>

> <span data-ttu-id="6f7c2-136">パブリック HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* 理由語句)</span><span class="sxs-lookup"><span data-stu-id="6f7c2-136">public HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* reasonPhrase)</span></span>

#### <span data-ttu-id="6f7c2-137">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="6f7c2-137">get_StatusCode</span></span> 

<span data-ttu-id="6f7c2-138">HTTP 応答状態コード。</span><span class="sxs-lookup"><span data-stu-id="6f7c2-138">The HTTP response status code.</span></span>

> <span data-ttu-id="6f7c2-139">パブリック HRESULT [get_StatusCode](#get_statuscode)(Int \* StatusCode)</span><span class="sxs-lookup"><span data-stu-id="6f7c2-139">public HRESULT [get_StatusCode](#get_statuscode)(int \* statusCode)</span></span>

#### <span data-ttu-id="6f7c2-140">put_Content</span><span class="sxs-lookup"><span data-stu-id="6f7c2-140">put_Content</span></span> 

<span data-ttu-id="6f7c2-141">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6f7c2-141">Set the Content property.</span></span>

> <span data-ttu-id="6f7c2-142">パブリック HRESULT [put_Content](#put_content)(IStream \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="6f7c2-142">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="6f7c2-143">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="6f7c2-143">put_ReasonPhrase</span></span> 

<span data-ttu-id="6f7c2-144">"理由" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6f7c2-144">Set the ReasonPhrase property.</span></span>

> <span data-ttu-id="6f7c2-145">パブリック HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR 理由語句)</span><span class="sxs-lookup"><span data-stu-id="6f7c2-145">public HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR reasonPhrase)</span></span>

#### <span data-ttu-id="6f7c2-146">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="6f7c2-146">put_StatusCode</span></span> 

<span data-ttu-id="6f7c2-147">StatusCode プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6f7c2-147">Set the StatusCode property.</span></span>

> <span data-ttu-id="6f7c2-148">パブリック HRESULT [put_StatusCode](#put_statuscode)(int StatusCode)</span><span class="sxs-lookup"><span data-stu-id="6f7c2-148">public HRESULT [put_StatusCode](#put_statuscode)(int statusCode)</span></span>

