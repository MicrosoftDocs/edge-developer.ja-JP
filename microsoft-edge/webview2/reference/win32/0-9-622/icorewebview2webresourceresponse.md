---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2WebResourceResponse
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2WebResourceResponse
ms.openlocfilehash: f259a9e6630470ed0557c4ab9593fdb1b8bbced2
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012227"
---
# <span data-ttu-id="6c946-104">インターフェイス ICoreWebView2WebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="6c946-104">interface ICoreWebView2WebResourceResponse</span></span> 

```
interface ICoreWebView2WebResourceResponse
  : public IUnknown
```

<span data-ttu-id="6c946-105">WebResourceRequested イベントと共に使用される HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="6c946-105">An HTTP response used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="6c946-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="6c946-106">Summary</span></span>

 <span data-ttu-id="6c946-107">Members</span><span class="sxs-lookup"><span data-stu-id="6c946-107">Members</span></span>                        | <span data-ttu-id="6c946-108">説明</span><span class="sxs-lookup"><span data-stu-id="6c946-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6c946-109">get_Content</span><span class="sxs-lookup"><span data-stu-id="6c946-109">get_Content</span></span>](#get_content) | <span data-ttu-id="6c946-110">ストリームとしての HTTP 応答のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="6c946-110">HTTP response content as stream.</span></span>
[<span data-ttu-id="6c946-111">get_Headers</span><span class="sxs-lookup"><span data-stu-id="6c946-111">get_Headers</span></span>](#get_headers) | <span data-ttu-id="6c946-112">上書きされた HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="6c946-112">Overridden HTTP response headers.</span></span>
[<span data-ttu-id="6c946-113">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="6c946-113">get_ReasonPhrase</span></span>](#get_reasonphrase) | <span data-ttu-id="6c946-114">HTTP 応答の理由の語句。</span><span class="sxs-lookup"><span data-stu-id="6c946-114">The HTTP response reason phrase.</span></span>
[<span data-ttu-id="6c946-115">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="6c946-115">get_StatusCode</span></span>](#get_statuscode) | <span data-ttu-id="6c946-116">HTTP 応答状態コード。</span><span class="sxs-lookup"><span data-stu-id="6c946-116">The HTTP response status code.</span></span>
[<span data-ttu-id="6c946-117">put_Content</span><span class="sxs-lookup"><span data-stu-id="6c946-117">put_Content</span></span>](#put_content) | <span data-ttu-id="6c946-118">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6c946-118">Set the Content property.</span></span>
[<span data-ttu-id="6c946-119">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="6c946-119">put_ReasonPhrase</span></span>](#put_reasonphrase) | <span data-ttu-id="6c946-120">"理由" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6c946-120">Set the ReasonPhrase property.</span></span>
[<span data-ttu-id="6c946-121">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="6c946-121">put_StatusCode</span></span>](#put_statuscode) | <span data-ttu-id="6c946-122">StatusCode プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6c946-122">Set the StatusCode property.</span></span>

## <span data-ttu-id="6c946-123">Members</span><span class="sxs-lookup"><span data-stu-id="6c946-123">Members</span></span>

#### <span data-ttu-id="6c946-124">get_Content</span><span class="sxs-lookup"><span data-stu-id="6c946-124">get_Content</span></span> 

<span data-ttu-id="6c946-125">ストリームとしての HTTP 応答のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="6c946-125">HTTP response content as stream.</span></span>

> <span data-ttu-id="6c946-126">パブリック HRESULT [get_Content](#get_content)(IStream \* \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="6c946-126">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="6c946-127">この応答の WebResourceRequested イベントの遅延が完了するまで、ストリームにはすべてのコンテンツデータが利用可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c946-127">Stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="6c946-128">UI スレッドに対するパフォーマンスへの影響を防ぐには、ストリームをアジャイルにするか、バックグラウンドスレッドから作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c946-128">Stream should be agile or be created from a background thread to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="6c946-129">Null はコンテンツデータがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="6c946-129">Null means no content data.</span></span> <span data-ttu-id="6c946-130">IStream セマンティクスが適用されます (すべてのデータが使い果たされるまで、S_OK は読み取り呼び出しに戻ります)。</span><span class="sxs-lookup"><span data-stu-id="6c946-130">IStream semantics apply (return S_OK to Read calls until all data is exhausted).</span></span>

#### <span data-ttu-id="6c946-131">get_Headers</span><span class="sxs-lookup"><span data-stu-id="6c946-131">get_Headers</span></span> 

<span data-ttu-id="6c946-132">上書きされた HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="6c946-132">Overridden HTTP response headers.</span></span>

> <span data-ttu-id="6c946-133">パブリック HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) \* \* ヘッダー)</span><span class="sxs-lookup"><span data-stu-id="6c946-133">public HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) \*\* headers)</span></span>

#### <span data-ttu-id="6c946-134">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="6c946-134">get_ReasonPhrase</span></span> 

<span data-ttu-id="6c946-135">HTTP 応答の理由の語句。</span><span class="sxs-lookup"><span data-stu-id="6c946-135">The HTTP response reason phrase.</span></span>

> <span data-ttu-id="6c946-136">パブリック HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* 理由語句)</span><span class="sxs-lookup"><span data-stu-id="6c946-136">public HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* reasonPhrase)</span></span>

#### <span data-ttu-id="6c946-137">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="6c946-137">get_StatusCode</span></span> 

<span data-ttu-id="6c946-138">HTTP 応答状態コード。</span><span class="sxs-lookup"><span data-stu-id="6c946-138">The HTTP response status code.</span></span>

> <span data-ttu-id="6c946-139">パブリック HRESULT [get_StatusCode](#get_statuscode)(Int \* StatusCode)</span><span class="sxs-lookup"><span data-stu-id="6c946-139">public HRESULT [get_StatusCode](#get_statuscode)(int \* statusCode)</span></span>

#### <span data-ttu-id="6c946-140">put_Content</span><span class="sxs-lookup"><span data-stu-id="6c946-140">put_Content</span></span> 

<span data-ttu-id="6c946-141">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6c946-141">Set the Content property.</span></span>

> <span data-ttu-id="6c946-142">パブリック HRESULT [put_Content](#put_content)(IStream \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="6c946-142">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="6c946-143">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="6c946-143">put_ReasonPhrase</span></span> 

<span data-ttu-id="6c946-144">"理由" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6c946-144">Set the ReasonPhrase property.</span></span>

> <span data-ttu-id="6c946-145">パブリック HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR 理由語句)</span><span class="sxs-lookup"><span data-stu-id="6c946-145">public HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR reasonPhrase)</span></span>

#### <span data-ttu-id="6c946-146">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="6c946-146">put_StatusCode</span></span> 

<span data-ttu-id="6c946-147">StatusCode プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6c946-147">Set the StatusCode property.</span></span>

> <span data-ttu-id="6c946-148">パブリック HRESULT [put_StatusCode](#put_statuscode)(int StatusCode)</span><span class="sxs-lookup"><span data-stu-id="6c946-148">public HRESULT [put_StatusCode](#put_statuscode)(int statusCode)</span></span>

