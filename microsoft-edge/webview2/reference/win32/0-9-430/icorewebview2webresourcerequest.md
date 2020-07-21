---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2WebResourceRequest
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: ca7063ff1cd527032e9548d22a0346f8d1590480
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885703"
---
# <span data-ttu-id="2ffae-104">0.9.430-インターフェイス ICoreWebView2WebResourceRequest</span><span class="sxs-lookup"><span data-stu-id="2ffae-104">0.9.430 - interface ICoreWebView2WebResourceRequest</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebResourceRequest
  : public IUnknown
```

<span data-ttu-id="2ffae-105">WebResourceRequested イベントと共に使用される HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="2ffae-105">An HTTP request used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="2ffae-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="2ffae-106">Summary</span></span>

 <span data-ttu-id="2ffae-107">Members</span><span class="sxs-lookup"><span data-stu-id="2ffae-107">Members</span></span>                        | <span data-ttu-id="2ffae-108">説明</span><span class="sxs-lookup"><span data-stu-id="2ffae-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2ffae-109">get_Uri</span><span class="sxs-lookup"><span data-stu-id="2ffae-109">get_Uri</span></span>](#get_uri) | <span data-ttu-id="2ffae-110">要求 URI。</span><span class="sxs-lookup"><span data-stu-id="2ffae-110">The request URI.</span></span>
[<span data-ttu-id="2ffae-111">put_Uri</span><span class="sxs-lookup"><span data-stu-id="2ffae-111">put_Uri</span></span>](#put_uri) | <span data-ttu-id="2ffae-112">Uri プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2ffae-112">Set the Uri property.</span></span>
[<span data-ttu-id="2ffae-113">get_Method</span><span class="sxs-lookup"><span data-stu-id="2ffae-113">get_Method</span></span>](#get_method) | <span data-ttu-id="2ffae-114">HTTP 要求メソッド。</span><span class="sxs-lookup"><span data-stu-id="2ffae-114">The HTTP request method.</span></span>
[<span data-ttu-id="2ffae-115">put_Method</span><span class="sxs-lookup"><span data-stu-id="2ffae-115">put_Method</span></span>](#put_method) | <span data-ttu-id="2ffae-116">Method プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2ffae-116">Set the Method property.</span></span>
[<span data-ttu-id="2ffae-117">get_Content</span><span class="sxs-lookup"><span data-stu-id="2ffae-117">get_Content</span></span>](#get_content) | <span data-ttu-id="2ffae-118">HTTP 要求メッセージ本文をストリームとして送信します。</span><span class="sxs-lookup"><span data-stu-id="2ffae-118">The HTTP request message body as stream.</span></span>
[<span data-ttu-id="2ffae-119">put_Content</span><span class="sxs-lookup"><span data-stu-id="2ffae-119">put_Content</span></span>](#put_content) | <span data-ttu-id="2ffae-120">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2ffae-120">Set the Content property.</span></span>
[<span data-ttu-id="2ffae-121">get_Headers</span><span class="sxs-lookup"><span data-stu-id="2ffae-121">get_Headers</span></span>](#get_headers) | <span data-ttu-id="2ffae-122">変更可能な HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="2ffae-122">The mutable HTTP request headers.</span></span>

## <span data-ttu-id="2ffae-123">Members</span><span class="sxs-lookup"><span data-stu-id="2ffae-123">Members</span></span>

#### <span data-ttu-id="2ffae-124">get_Uri</span><span class="sxs-lookup"><span data-stu-id="2ffae-124">get_Uri</span></span> 

<span data-ttu-id="2ffae-125">要求 URI。</span><span class="sxs-lookup"><span data-stu-id="2ffae-125">The request URI.</span></span>

> <span data-ttu-id="2ffae-126">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="2ffae-126">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="2ffae-127">put_Uri</span><span class="sxs-lookup"><span data-stu-id="2ffae-127">put_Uri</span></span> 

<span data-ttu-id="2ffae-128">Uri プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2ffae-128">Set the Uri property.</span></span>

> <span data-ttu-id="2ffae-129">パブリック HRESULT [put_Uri](#put_uri)(LPCWSTR Uri)</span><span class="sxs-lookup"><span data-stu-id="2ffae-129">public HRESULT [put_Uri](#put_uri)(LPCWSTR uri)</span></span>

#### <span data-ttu-id="2ffae-130">get_Method</span><span class="sxs-lookup"><span data-stu-id="2ffae-130">get_Method</span></span> 

<span data-ttu-id="2ffae-131">HTTP 要求メソッド。</span><span class="sxs-lookup"><span data-stu-id="2ffae-131">The HTTP request method.</span></span>

> <span data-ttu-id="2ffae-132">パブリック HRESULT [get_Method](#get_method)(LPWSTR \* メソッド)</span><span class="sxs-lookup"><span data-stu-id="2ffae-132">public HRESULT [get_Method](#get_method)(LPWSTR \* method)</span></span>

#### <span data-ttu-id="2ffae-133">put_Method</span><span class="sxs-lookup"><span data-stu-id="2ffae-133">put_Method</span></span> 

<span data-ttu-id="2ffae-134">Method プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2ffae-134">Set the Method property.</span></span>

> <span data-ttu-id="2ffae-135">パブリック HRESULT [put_Method](#put_method)(LPCWSTR メソッド)</span><span class="sxs-lookup"><span data-stu-id="2ffae-135">public HRESULT [put_Method](#put_method)(LPCWSTR method)</span></span>

#### <span data-ttu-id="2ffae-136">get_Content</span><span class="sxs-lookup"><span data-stu-id="2ffae-136">get_Content</span></span> 

<span data-ttu-id="2ffae-137">HTTP 要求メッセージ本文をストリームとして送信します。</span><span class="sxs-lookup"><span data-stu-id="2ffae-137">The HTTP request message body as stream.</span></span>

> <span data-ttu-id="2ffae-138">パブリック HRESULT [get_Content](#get_content)(IStream \* \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="2ffae-138">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="2ffae-139">データの投稿はここにあります。</span><span class="sxs-lookup"><span data-stu-id="2ffae-139">POST data would be here.</span></span> <span data-ttu-id="2ffae-140">ストリームが設定されている場合は、メッセージ本文を上書きします。この応答の WebResourceRequested イベントの遅延が完了するまで、ストリームにはすべてのコンテンツデータが利用可能になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ffae-140">If a stream is set, which will override the message body, the stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="2ffae-141">UI スレッドへのパフォーマンスへの影響を防ぐために、Stream はバックグラウンド STA から作成したり、バックグラウンドで作成したりする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ffae-141">Stream should be agile or be created from a background STA to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="2ffae-142">Null はコンテンツデータがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="2ffae-142">Null means no content data.</span></span> <span data-ttu-id="2ffae-143">IStream セマンティクスが適用されます (すべてのデータが使い果たされるまで、S_OK は読み取り呼び出しに戻ります)</span><span class="sxs-lookup"><span data-stu-id="2ffae-143">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="2ffae-144">put_Content</span><span class="sxs-lookup"><span data-stu-id="2ffae-144">put_Content</span></span> 

<span data-ttu-id="2ffae-145">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2ffae-145">Set the Content property.</span></span>

> <span data-ttu-id="2ffae-146">パブリック HRESULT [put_Content](#put_content)(IStream \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="2ffae-146">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="2ffae-147">get_Headers</span><span class="sxs-lookup"><span data-stu-id="2ffae-147">get_Headers</span></span> 

<span data-ttu-id="2ffae-148">変更可能な HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="2ffae-148">The mutable HTTP request headers.</span></span>

> <span data-ttu-id="2ffae-149">パブリック HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpRequestHeaders](ICoreWebView2HttpRequestHeaders.md) \* \* ヘッダー)</span><span class="sxs-lookup"><span data-stu-id="2ffae-149">public HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpRequestHeaders](ICoreWebView2HttpRequestHeaders.md) \*\* headers)</span></span>

