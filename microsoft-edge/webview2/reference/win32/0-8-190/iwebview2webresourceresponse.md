---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2WebResourceResponse
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 82c94869a84165de4c3b8d09937d6ea5d1f79256
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885689"
---
# <span data-ttu-id="bd80b-104">0.8.355-インターフェイス IWebView2WebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="bd80b-104">0.8.355 - interface IWebView2WebResourceResponse</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2WebResourceResponse
  : public IUnknown
```

<span data-ttu-id="bd80b-105">WebResourceRequested イベントと共に使用される HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="bd80b-105">An HTTP response used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="bd80b-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="bd80b-106">Summary</span></span>

 <span data-ttu-id="bd80b-107">Members</span><span class="sxs-lookup"><span data-stu-id="bd80b-107">Members</span></span>                        | <span data-ttu-id="bd80b-108">説明</span><span class="sxs-lookup"><span data-stu-id="bd80b-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="bd80b-109">get_Content</span><span class="sxs-lookup"><span data-stu-id="bd80b-109">get_Content</span></span>](#get_content) | <span data-ttu-id="bd80b-110">ストリームとしての HTTP 応答のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="bd80b-110">HTTP response content as stream.</span></span>
[<span data-ttu-id="bd80b-111">put_Content</span><span class="sxs-lookup"><span data-stu-id="bd80b-111">put_Content</span></span>](#put_content) | <span data-ttu-id="bd80b-112">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="bd80b-112">Set the Content property.</span></span>
[<span data-ttu-id="bd80b-113">get_Headers</span><span class="sxs-lookup"><span data-stu-id="bd80b-113">get_Headers</span></span>](#get_headers) | <span data-ttu-id="bd80b-114">上書きされた HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="bd80b-114">Overridden HTTP response headers.</span></span>
[<span data-ttu-id="bd80b-115">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="bd80b-115">get_StatusCode</span></span>](#get_statuscode) | <span data-ttu-id="bd80b-116">HTTP 応答状態コード。</span><span class="sxs-lookup"><span data-stu-id="bd80b-116">The HTTP response status code.</span></span>
[<span data-ttu-id="bd80b-117">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="bd80b-117">put_StatusCode</span></span>](#put_statuscode) | <span data-ttu-id="bd80b-118">StatusCode プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="bd80b-118">Set the StatusCode property.</span></span>
[<span data-ttu-id="bd80b-119">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="bd80b-119">get_ReasonPhrase</span></span>](#get_reasonphrase) | <span data-ttu-id="bd80b-120">HTTP 応答の理由の語句。</span><span class="sxs-lookup"><span data-stu-id="bd80b-120">The HTTP response reason phrase.</span></span>
[<span data-ttu-id="bd80b-121">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="bd80b-121">put_ReasonPhrase</span></span>](#put_reasonphrase) | <span data-ttu-id="bd80b-122">"理由" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="bd80b-122">Set the ReasonPhrase property.</span></span>

## <span data-ttu-id="bd80b-123">Members</span><span class="sxs-lookup"><span data-stu-id="bd80b-123">Members</span></span>

#### <span data-ttu-id="bd80b-124">get_Content</span><span class="sxs-lookup"><span data-stu-id="bd80b-124">get_Content</span></span> 

<span data-ttu-id="bd80b-125">ストリームとしての HTTP 応答のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="bd80b-125">HTTP response content as stream.</span></span>

> <span data-ttu-id="bd80b-126">パブリック HRESULT [get_Content](#get_content)(IStream \* \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="bd80b-126">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="bd80b-127">この応答の WebResourceRequested イベントの遅延が完了するまで、ストリームにはすべてのコンテンツデータが利用可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd80b-127">Stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="bd80b-128">UI スレッドに対するパフォーマンスへの影響を防ぐには、ストリームをアジャイルにするか、バックグラウンドスレッドから作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd80b-128">Stream should be agile or be created from a background thread to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="bd80b-129">Null はコンテンツデータがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="bd80b-129">Null means no content data.</span></span> <span data-ttu-id="bd80b-130">IStream セマンティクスが適用されます (すべてのデータが使い果たされるまで、S_OK は読み取り呼び出しに戻ります)</span><span class="sxs-lookup"><span data-stu-id="bd80b-130">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="bd80b-131">put_Content</span><span class="sxs-lookup"><span data-stu-id="bd80b-131">put_Content</span></span> 

<span data-ttu-id="bd80b-132">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="bd80b-132">Set the Content property.</span></span>

> <span data-ttu-id="bd80b-133">パブリック HRESULT [put_Content](#put_content)(IStream \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="bd80b-133">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="bd80b-134">get_Headers</span><span class="sxs-lookup"><span data-stu-id="bd80b-134">get_Headers</span></span> 

<span data-ttu-id="bd80b-135">上書きされた HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="bd80b-135">Overridden HTTP response headers.</span></span>

> <span data-ttu-id="bd80b-136">パブリック HRESULT [get_Headers](#get_headers)([IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md) \* \* ヘッダー)</span><span class="sxs-lookup"><span data-stu-id="bd80b-136">public HRESULT [get_Headers](#get_headers)([IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md) \*\* headers)</span></span>

#### <span data-ttu-id="bd80b-137">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="bd80b-137">get_StatusCode</span></span> 

<span data-ttu-id="bd80b-138">HTTP 応答状態コード。</span><span class="sxs-lookup"><span data-stu-id="bd80b-138">The HTTP response status code.</span></span>

> <span data-ttu-id="bd80b-139">パブリック HRESULT [get_StatusCode](#get_statuscode)(Int \* StatusCode)</span><span class="sxs-lookup"><span data-stu-id="bd80b-139">public HRESULT [get_StatusCode](#get_statuscode)(int \* statusCode)</span></span>

#### <span data-ttu-id="bd80b-140">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="bd80b-140">put_StatusCode</span></span> 

<span data-ttu-id="bd80b-141">StatusCode プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="bd80b-141">Set the StatusCode property.</span></span>

> <span data-ttu-id="bd80b-142">パブリック HRESULT [put_StatusCode](#put_statuscode)(int StatusCode)</span><span class="sxs-lookup"><span data-stu-id="bd80b-142">public HRESULT [put_StatusCode](#put_statuscode)(int statusCode)</span></span>

#### <span data-ttu-id="bd80b-143">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="bd80b-143">get_ReasonPhrase</span></span> 

<span data-ttu-id="bd80b-144">HTTP 応答の理由の語句。</span><span class="sxs-lookup"><span data-stu-id="bd80b-144">The HTTP response reason phrase.</span></span>

> <span data-ttu-id="bd80b-145">パブリック HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* 理由語句)</span><span class="sxs-lookup"><span data-stu-id="bd80b-145">public HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* reasonPhrase)</span></span>

#### <span data-ttu-id="bd80b-146">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="bd80b-146">put_ReasonPhrase</span></span> 

<span data-ttu-id="bd80b-147">"理由" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="bd80b-147">Set the ReasonPhrase property.</span></span>

> <span data-ttu-id="bd80b-148">パブリック HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR 理由語句)</span><span class="sxs-lookup"><span data-stu-id="bd80b-148">public HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR reasonPhrase)</span></span>

