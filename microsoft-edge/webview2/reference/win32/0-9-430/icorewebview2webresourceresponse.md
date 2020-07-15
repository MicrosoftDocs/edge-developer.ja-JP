---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2WebResourceResponse
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: c0c33bab95f8d2c7908864b1869bc9a186216ef9
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877547"
---
# <span data-ttu-id="6d856-104">0.9.430-インターフェイス ICoreWebView2WebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="6d856-104">0.9.430 - interface ICoreWebView2WebResourceResponse</span></span> 

> [!NOTE]
> <span data-ttu-id="6d856-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6d856-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="6d856-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d856-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2WebResourceResponse
  : public IUnknown
```

<span data-ttu-id="6d856-107">WebResourceRequested イベントと共に使用される HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="6d856-107">An HTTP response used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="6d856-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="6d856-108">Summary</span></span>

 <span data-ttu-id="6d856-109">Members</span><span class="sxs-lookup"><span data-stu-id="6d856-109">Members</span></span>                        | <span data-ttu-id="6d856-110">説明</span><span class="sxs-lookup"><span data-stu-id="6d856-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6d856-111">get_Content</span><span class="sxs-lookup"><span data-stu-id="6d856-111">get_Content</span></span>](#get_content) | <span data-ttu-id="6d856-112">ストリームとしての HTTP 応答のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="6d856-112">HTTP response content as stream.</span></span>
[<span data-ttu-id="6d856-113">put_Content</span><span class="sxs-lookup"><span data-stu-id="6d856-113">put_Content</span></span>](#put_content) | <span data-ttu-id="6d856-114">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6d856-114">Set the Content property.</span></span>
[<span data-ttu-id="6d856-115">get_Headers</span><span class="sxs-lookup"><span data-stu-id="6d856-115">get_Headers</span></span>](#get_headers) | <span data-ttu-id="6d856-116">上書きされた HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="6d856-116">Overridden HTTP response headers.</span></span>
[<span data-ttu-id="6d856-117">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="6d856-117">get_StatusCode</span></span>](#get_statuscode) | <span data-ttu-id="6d856-118">HTTP 応答状態コード。</span><span class="sxs-lookup"><span data-stu-id="6d856-118">The HTTP response status code.</span></span>
[<span data-ttu-id="6d856-119">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="6d856-119">put_StatusCode</span></span>](#put_statuscode) | <span data-ttu-id="6d856-120">StatusCode プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6d856-120">Set the StatusCode property.</span></span>
[<span data-ttu-id="6d856-121">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="6d856-121">get_ReasonPhrase</span></span>](#get_reasonphrase) | <span data-ttu-id="6d856-122">HTTP 応答の理由の語句。</span><span class="sxs-lookup"><span data-stu-id="6d856-122">The HTTP response reason phrase.</span></span>
[<span data-ttu-id="6d856-123">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="6d856-123">put_ReasonPhrase</span></span>](#put_reasonphrase) | <span data-ttu-id="6d856-124">"理由" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6d856-124">Set the ReasonPhrase property.</span></span>

## <span data-ttu-id="6d856-125">Members</span><span class="sxs-lookup"><span data-stu-id="6d856-125">Members</span></span>

#### <span data-ttu-id="6d856-126">get_Content</span><span class="sxs-lookup"><span data-stu-id="6d856-126">get_Content</span></span> 

<span data-ttu-id="6d856-127">ストリームとしての HTTP 応答のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="6d856-127">HTTP response content as stream.</span></span>

> <span data-ttu-id="6d856-128">パブリック HRESULT [get_Content](#get_content)(IStream \* \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="6d856-128">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="6d856-129">この応答の WebResourceRequested イベントの遅延が完了するまで、ストリームにはすべてのコンテンツデータが利用可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d856-129">Stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="6d856-130">UI スレッドに対するパフォーマンスへの影響を防ぐには、ストリームをアジャイルにするか、バックグラウンドスレッドから作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d856-130">Stream should be agile or be created from a background thread to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="6d856-131">Null はコンテンツデータがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="6d856-131">Null means no content data.</span></span> <span data-ttu-id="6d856-132">IStream セマンティクスが適用されます (すべてのデータが使い果たされるまで、S_OK は読み取り呼び出しに戻ります)</span><span class="sxs-lookup"><span data-stu-id="6d856-132">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="6d856-133">put_Content</span><span class="sxs-lookup"><span data-stu-id="6d856-133">put_Content</span></span> 

<span data-ttu-id="6d856-134">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6d856-134">Set the Content property.</span></span>

> <span data-ttu-id="6d856-135">パブリック HRESULT [put_Content](#put_content)(IStream \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="6d856-135">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="6d856-136">get_Headers</span><span class="sxs-lookup"><span data-stu-id="6d856-136">get_Headers</span></span> 

<span data-ttu-id="6d856-137">上書きされた HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="6d856-137">Overridden HTTP response headers.</span></span>

> <span data-ttu-id="6d856-138">パブリック HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpResponseHeaders](ICoreWebView2HttpResponseHeaders.md) \* \* ヘッダー)</span><span class="sxs-lookup"><span data-stu-id="6d856-138">public HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpResponseHeaders](ICoreWebView2HttpResponseHeaders.md) \*\* headers)</span></span>

#### <span data-ttu-id="6d856-139">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="6d856-139">get_StatusCode</span></span> 

<span data-ttu-id="6d856-140">HTTP 応答状態コード。</span><span class="sxs-lookup"><span data-stu-id="6d856-140">The HTTP response status code.</span></span>

> <span data-ttu-id="6d856-141">パブリック HRESULT [get_StatusCode](#get_statuscode)(Int \* StatusCode)</span><span class="sxs-lookup"><span data-stu-id="6d856-141">public HRESULT [get_StatusCode](#get_statuscode)(int \* statusCode)</span></span>

#### <span data-ttu-id="6d856-142">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="6d856-142">put_StatusCode</span></span> 

<span data-ttu-id="6d856-143">StatusCode プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6d856-143">Set the StatusCode property.</span></span>

> <span data-ttu-id="6d856-144">パブリック HRESULT [put_StatusCode](#put_statuscode)(int StatusCode)</span><span class="sxs-lookup"><span data-stu-id="6d856-144">public HRESULT [put_StatusCode](#put_statuscode)(int statusCode)</span></span>

#### <span data-ttu-id="6d856-145">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="6d856-145">get_ReasonPhrase</span></span> 

<span data-ttu-id="6d856-146">HTTP 応答の理由の語句。</span><span class="sxs-lookup"><span data-stu-id="6d856-146">The HTTP response reason phrase.</span></span>

> <span data-ttu-id="6d856-147">パブリック HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* 理由語句)</span><span class="sxs-lookup"><span data-stu-id="6d856-147">public HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* reasonPhrase)</span></span>

#### <span data-ttu-id="6d856-148">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="6d856-148">put_ReasonPhrase</span></span> 

<span data-ttu-id="6d856-149">"理由" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6d856-149">Set the ReasonPhrase property.</span></span>

> <span data-ttu-id="6d856-150">パブリック HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR 理由語句)</span><span class="sxs-lookup"><span data-stu-id="6d856-150">public HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR reasonPhrase)</span></span>

