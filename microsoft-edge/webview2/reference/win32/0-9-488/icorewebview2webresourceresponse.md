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
ms.openlocfilehash: d6b51600479f47eebb09d5cff8fb096455fb1766
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654212"
---
# <span data-ttu-id="08e9a-104">インターフェイス ICoreWebView2WebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="08e9a-104">interface ICoreWebView2WebResourceResponse</span></span> 

```
interface ICoreWebView2WebResourceResponse
  : public IUnknown
```

<span data-ttu-id="08e9a-105">WebResourceRequested イベントと共に使用される HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="08e9a-105">An HTTP response used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="08e9a-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="08e9a-106">Summary</span></span>

 <span data-ttu-id="08e9a-107">Members</span><span class="sxs-lookup"><span data-stu-id="08e9a-107">Members</span></span>                        | <span data-ttu-id="08e9a-108">説明</span><span class="sxs-lookup"><span data-stu-id="08e9a-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="08e9a-109">get_Content</span><span class="sxs-lookup"><span data-stu-id="08e9a-109">get_Content</span></span>](#get_content) | <span data-ttu-id="08e9a-110">ストリームとしての HTTP 応答のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="08e9a-110">HTTP response content as stream.</span></span>
[<span data-ttu-id="08e9a-111">get_Headers</span><span class="sxs-lookup"><span data-stu-id="08e9a-111">get_Headers</span></span>](#get_headers) | <span data-ttu-id="08e9a-112">上書きされた HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="08e9a-112">Overridden HTTP response headers.</span></span>
[<span data-ttu-id="08e9a-113">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="08e9a-113">get_ReasonPhrase</span></span>](#get_reasonphrase) | <span data-ttu-id="08e9a-114">HTTP 応答の理由の語句。</span><span class="sxs-lookup"><span data-stu-id="08e9a-114">The HTTP response reason phrase.</span></span>
[<span data-ttu-id="08e9a-115">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="08e9a-115">get_StatusCode</span></span>](#get_statuscode) | <span data-ttu-id="08e9a-116">HTTP 応答状態コード。</span><span class="sxs-lookup"><span data-stu-id="08e9a-116">The HTTP response status code.</span></span>
[<span data-ttu-id="08e9a-117">put_Content</span><span class="sxs-lookup"><span data-stu-id="08e9a-117">put_Content</span></span>](#put_content) | <span data-ttu-id="08e9a-118">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="08e9a-118">Set the Content property.</span></span>
[<span data-ttu-id="08e9a-119">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="08e9a-119">put_ReasonPhrase</span></span>](#put_reasonphrase) | <span data-ttu-id="08e9a-120">"理由" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="08e9a-120">Set the ReasonPhrase property.</span></span>
[<span data-ttu-id="08e9a-121">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="08e9a-121">put_StatusCode</span></span>](#put_statuscode) | <span data-ttu-id="08e9a-122">StatusCode プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="08e9a-122">Set the StatusCode property.</span></span>

## <span data-ttu-id="08e9a-123">Members</span><span class="sxs-lookup"><span data-stu-id="08e9a-123">Members</span></span>

#### <span data-ttu-id="08e9a-124">get_Content</span><span class="sxs-lookup"><span data-stu-id="08e9a-124">get_Content</span></span> 

<span data-ttu-id="08e9a-125">ストリームとしての HTTP 応答のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="08e9a-125">HTTP response content as stream.</span></span>

> <span data-ttu-id="08e9a-126">パブリック HRESULT [get_Content](#get_content)(IStream \* \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="08e9a-126">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="08e9a-127">この応答の WebResourceRequested イベントの遅延が完了するまで、ストリームにはすべてのコンテンツデータが利用可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="08e9a-127">Stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="08e9a-128">UI スレッドに対するパフォーマンスへの影響を防ぐには、ストリームをアジャイルにするか、バックグラウンドスレッドから作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08e9a-128">Stream should be agile or be created from a background thread to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="08e9a-129">Null はコンテンツデータがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="08e9a-129">Null means no content data.</span></span> <span data-ttu-id="08e9a-130">IStream セマンティクスが適用されます (すべてのデータが使い果たされるまで、S_OK は読み取り呼び出しに戻ります)</span><span class="sxs-lookup"><span data-stu-id="08e9a-130">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="08e9a-131">get_Headers</span><span class="sxs-lookup"><span data-stu-id="08e9a-131">get_Headers</span></span> 

<span data-ttu-id="08e9a-132">上書きされた HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="08e9a-132">Overridden HTTP response headers.</span></span>

> <span data-ttu-id="08e9a-133">パブリック HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) \* \* ヘッダー)</span><span class="sxs-lookup"><span data-stu-id="08e9a-133">public HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) \*\* headers)</span></span>

#### <span data-ttu-id="08e9a-134">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="08e9a-134">get_ReasonPhrase</span></span> 

<span data-ttu-id="08e9a-135">HTTP 応答の理由の語句。</span><span class="sxs-lookup"><span data-stu-id="08e9a-135">The HTTP response reason phrase.</span></span>

> <span data-ttu-id="08e9a-136">パブリック HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* 理由語句)</span><span class="sxs-lookup"><span data-stu-id="08e9a-136">public HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* reasonPhrase)</span></span>

#### <span data-ttu-id="08e9a-137">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="08e9a-137">get_StatusCode</span></span> 

<span data-ttu-id="08e9a-138">HTTP 応答状態コード。</span><span class="sxs-lookup"><span data-stu-id="08e9a-138">The HTTP response status code.</span></span>

> <span data-ttu-id="08e9a-139">パブリック HRESULT [get_StatusCode](#get_statuscode)(Int \* StatusCode)</span><span class="sxs-lookup"><span data-stu-id="08e9a-139">public HRESULT [get_StatusCode](#get_statuscode)(int \* statusCode)</span></span>

#### <span data-ttu-id="08e9a-140">put_Content</span><span class="sxs-lookup"><span data-stu-id="08e9a-140">put_Content</span></span> 

<span data-ttu-id="08e9a-141">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="08e9a-141">Set the Content property.</span></span>

> <span data-ttu-id="08e9a-142">パブリック HRESULT [put_Content](#put_content)(IStream \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="08e9a-142">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="08e9a-143">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="08e9a-143">put_ReasonPhrase</span></span> 

<span data-ttu-id="08e9a-144">"理由" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="08e9a-144">Set the ReasonPhrase property.</span></span>

> <span data-ttu-id="08e9a-145">パブリック HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR 理由語句)</span><span class="sxs-lookup"><span data-stu-id="08e9a-145">public HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR reasonPhrase)</span></span>

#### <span data-ttu-id="08e9a-146">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="08e9a-146">put_StatusCode</span></span> 

<span data-ttu-id="08e9a-147">StatusCode プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="08e9a-147">Set the StatusCode property.</span></span>

> <span data-ttu-id="08e9a-148">パブリック HRESULT [put_StatusCode](#put_statuscode)(int StatusCode)</span><span class="sxs-lookup"><span data-stu-id="08e9a-148">public HRESULT [put_StatusCode](#put_statuscode)(int statusCode)</span></span>

