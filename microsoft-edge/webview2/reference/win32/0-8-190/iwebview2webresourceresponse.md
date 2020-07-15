---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2WebResourceResponse
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 95c0a881a8a201d21ca9cb2662c282b36efa2ed3
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878107"
---
# <span data-ttu-id="a45b9-104">0.8.355-インターフェイス IWebView2WebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="a45b9-104">0.8.355 - interface IWebView2WebResourceResponse</span></span> 

> [!NOTE]
> <span data-ttu-id="a45b9-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a45b9-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="a45b9-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a45b9-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebResourceResponse
  : public IUnknown
```

<span data-ttu-id="a45b9-107">WebResourceRequested イベントと共に使用される HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="a45b9-107">An HTTP response used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="a45b9-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="a45b9-108">Summary</span></span>

 <span data-ttu-id="a45b9-109">Members</span><span class="sxs-lookup"><span data-stu-id="a45b9-109">Members</span></span>                        | <span data-ttu-id="a45b9-110">説明</span><span class="sxs-lookup"><span data-stu-id="a45b9-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a45b9-111">get_Content</span><span class="sxs-lookup"><span data-stu-id="a45b9-111">get_Content</span></span>](#get_content) | <span data-ttu-id="a45b9-112">ストリームとしての HTTP 応答のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="a45b9-112">HTTP response content as stream.</span></span>
[<span data-ttu-id="a45b9-113">put_Content</span><span class="sxs-lookup"><span data-stu-id="a45b9-113">put_Content</span></span>](#put_content) | <span data-ttu-id="a45b9-114">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a45b9-114">Set the Content property.</span></span>
[<span data-ttu-id="a45b9-115">get_Headers</span><span class="sxs-lookup"><span data-stu-id="a45b9-115">get_Headers</span></span>](#get_headers) | <span data-ttu-id="a45b9-116">上書きされた HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="a45b9-116">Overridden HTTP response headers.</span></span>
[<span data-ttu-id="a45b9-117">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="a45b9-117">get_StatusCode</span></span>](#get_statuscode) | <span data-ttu-id="a45b9-118">HTTP 応答状態コード。</span><span class="sxs-lookup"><span data-stu-id="a45b9-118">The HTTP response status code.</span></span>
[<span data-ttu-id="a45b9-119">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="a45b9-119">put_StatusCode</span></span>](#put_statuscode) | <span data-ttu-id="a45b9-120">StatusCode プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a45b9-120">Set the StatusCode property.</span></span>
[<span data-ttu-id="a45b9-121">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="a45b9-121">get_ReasonPhrase</span></span>](#get_reasonphrase) | <span data-ttu-id="a45b9-122">HTTP 応答の理由の語句。</span><span class="sxs-lookup"><span data-stu-id="a45b9-122">The HTTP response reason phrase.</span></span>
[<span data-ttu-id="a45b9-123">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="a45b9-123">put_ReasonPhrase</span></span>](#put_reasonphrase) | <span data-ttu-id="a45b9-124">"理由" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a45b9-124">Set the ReasonPhrase property.</span></span>

## <span data-ttu-id="a45b9-125">Members</span><span class="sxs-lookup"><span data-stu-id="a45b9-125">Members</span></span>

#### <span data-ttu-id="a45b9-126">get_Content</span><span class="sxs-lookup"><span data-stu-id="a45b9-126">get_Content</span></span> 

<span data-ttu-id="a45b9-127">ストリームとしての HTTP 応答のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="a45b9-127">HTTP response content as stream.</span></span>

> <span data-ttu-id="a45b9-128">パブリック HRESULT [get_Content](#get_content)(IStream \* \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="a45b9-128">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="a45b9-129">この応答の WebResourceRequested イベントの遅延が完了するまで、ストリームにはすべてのコンテンツデータが利用可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a45b9-129">Stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="a45b9-130">UI スレッドに対するパフォーマンスへの影響を防ぐには、ストリームをアジャイルにするか、バックグラウンドスレッドから作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a45b9-130">Stream should be agile or be created from a background thread to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="a45b9-131">Null はコンテンツデータがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="a45b9-131">Null means no content data.</span></span> <span data-ttu-id="a45b9-132">IStream セマンティクスが適用されます (すべてのデータが使い果たされるまで、S_OK は読み取り呼び出しに戻ります)</span><span class="sxs-lookup"><span data-stu-id="a45b9-132">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="a45b9-133">put_Content</span><span class="sxs-lookup"><span data-stu-id="a45b9-133">put_Content</span></span> 

<span data-ttu-id="a45b9-134">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a45b9-134">Set the Content property.</span></span>

> <span data-ttu-id="a45b9-135">パブリック HRESULT [put_Content](#put_content)(IStream \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="a45b9-135">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="a45b9-136">get_Headers</span><span class="sxs-lookup"><span data-stu-id="a45b9-136">get_Headers</span></span> 

<span data-ttu-id="a45b9-137">上書きされた HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="a45b9-137">Overridden HTTP response headers.</span></span>

> <span data-ttu-id="a45b9-138">パブリック HRESULT [get_Headers](#get_headers)([IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md) \* \* ヘッダー)</span><span class="sxs-lookup"><span data-stu-id="a45b9-138">public HRESULT [get_Headers](#get_headers)([IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md) \*\* headers)</span></span>

#### <span data-ttu-id="a45b9-139">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="a45b9-139">get_StatusCode</span></span> 

<span data-ttu-id="a45b9-140">HTTP 応答状態コード。</span><span class="sxs-lookup"><span data-stu-id="a45b9-140">The HTTP response status code.</span></span>

> <span data-ttu-id="a45b9-141">パブリック HRESULT [get_StatusCode](#get_statuscode)(Int \* StatusCode)</span><span class="sxs-lookup"><span data-stu-id="a45b9-141">public HRESULT [get_StatusCode](#get_statuscode)(int \* statusCode)</span></span>

#### <span data-ttu-id="a45b9-142">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="a45b9-142">put_StatusCode</span></span> 

<span data-ttu-id="a45b9-143">StatusCode プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a45b9-143">Set the StatusCode property.</span></span>

> <span data-ttu-id="a45b9-144">パブリック HRESULT [put_StatusCode](#put_statuscode)(int StatusCode)</span><span class="sxs-lookup"><span data-stu-id="a45b9-144">public HRESULT [put_StatusCode](#put_statuscode)(int statusCode)</span></span>

#### <span data-ttu-id="a45b9-145">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="a45b9-145">get_ReasonPhrase</span></span> 

<span data-ttu-id="a45b9-146">HTTP 応答の理由の語句。</span><span class="sxs-lookup"><span data-stu-id="a45b9-146">The HTTP response reason phrase.</span></span>

> <span data-ttu-id="a45b9-147">パブリック HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* 理由語句)</span><span class="sxs-lookup"><span data-stu-id="a45b9-147">public HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* reasonPhrase)</span></span>

#### <span data-ttu-id="a45b9-148">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="a45b9-148">put_ReasonPhrase</span></span> 

<span data-ttu-id="a45b9-149">"理由" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a45b9-149">Set the ReasonPhrase property.</span></span>

> <span data-ttu-id="a45b9-150">パブリック HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR 理由語句)</span><span class="sxs-lookup"><span data-stu-id="a45b9-150">public HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR reasonPhrase)</span></span>

