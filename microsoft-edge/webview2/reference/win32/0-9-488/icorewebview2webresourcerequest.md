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
ms.openlocfilehash: 4b76cf998f8e2fd8982f7e51f1d9167e3862ec02
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654217"
---
# <span data-ttu-id="965b1-104">インターフェイス ICoreWebView2WebResourceRequest</span><span class="sxs-lookup"><span data-stu-id="965b1-104">interface ICoreWebView2WebResourceRequest</span></span> 

```
interface ICoreWebView2WebResourceRequest
  : public IUnknown
```

<span data-ttu-id="965b1-105">WebResourceRequested イベントと共に使用される HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="965b1-105">An HTTP request used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="965b1-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="965b1-106">Summary</span></span>

 <span data-ttu-id="965b1-107">Members</span><span class="sxs-lookup"><span data-stu-id="965b1-107">Members</span></span>                        | <span data-ttu-id="965b1-108">説明</span><span class="sxs-lookup"><span data-stu-id="965b1-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="965b1-109">get_Content</span><span class="sxs-lookup"><span data-stu-id="965b1-109">get_Content</span></span>](#get_content) | <span data-ttu-id="965b1-110">HTTP 要求メッセージ本文をストリームとして送信します。</span><span class="sxs-lookup"><span data-stu-id="965b1-110">The HTTP request message body as stream.</span></span>
[<span data-ttu-id="965b1-111">get_Headers</span><span class="sxs-lookup"><span data-stu-id="965b1-111">get_Headers</span></span>](#get_headers) | <span data-ttu-id="965b1-112">変更可能な HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="965b1-112">The mutable HTTP request headers.</span></span>
[<span data-ttu-id="965b1-113">get_Method</span><span class="sxs-lookup"><span data-stu-id="965b1-113">get_Method</span></span>](#get_method) | <span data-ttu-id="965b1-114">HTTP 要求メソッド。</span><span class="sxs-lookup"><span data-stu-id="965b1-114">The HTTP request method.</span></span>
[<span data-ttu-id="965b1-115">get_Uri</span><span class="sxs-lookup"><span data-stu-id="965b1-115">get_Uri</span></span>](#get_uri) | <span data-ttu-id="965b1-116">要求 URI。</span><span class="sxs-lookup"><span data-stu-id="965b1-116">The request URI.</span></span>
[<span data-ttu-id="965b1-117">put_Content</span><span class="sxs-lookup"><span data-stu-id="965b1-117">put_Content</span></span>](#put_content) | <span data-ttu-id="965b1-118">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="965b1-118">Set the Content property.</span></span>
[<span data-ttu-id="965b1-119">put_Method</span><span class="sxs-lookup"><span data-stu-id="965b1-119">put_Method</span></span>](#put_method) | <span data-ttu-id="965b1-120">Method プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="965b1-120">Set the Method property.</span></span>
[<span data-ttu-id="965b1-121">put_Uri</span><span class="sxs-lookup"><span data-stu-id="965b1-121">put_Uri</span></span>](#put_uri) | <span data-ttu-id="965b1-122">Uri プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="965b1-122">Set the Uri property.</span></span>

## <span data-ttu-id="965b1-123">Members</span><span class="sxs-lookup"><span data-stu-id="965b1-123">Members</span></span>

#### <span data-ttu-id="965b1-124">get_Content</span><span class="sxs-lookup"><span data-stu-id="965b1-124">get_Content</span></span> 

<span data-ttu-id="965b1-125">HTTP 要求メッセージ本文をストリームとして送信します。</span><span class="sxs-lookup"><span data-stu-id="965b1-125">The HTTP request message body as stream.</span></span>

> <span data-ttu-id="965b1-126">パブリック HRESULT [get_Content](#get_content)(IStream \* \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="965b1-126">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="965b1-127">データの投稿はここにあります。</span><span class="sxs-lookup"><span data-stu-id="965b1-127">POST data would be here.</span></span> <span data-ttu-id="965b1-128">ストリームが設定されている場合は、メッセージ本文を上書きします。この応答の WebResourceRequested イベントの遅延が完了するまで、ストリームにはすべてのコンテンツデータが利用可能になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="965b1-128">If a stream is set, which will override the message body, the stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="965b1-129">UI スレッドへのパフォーマンスへの影響を防ぐために、Stream はバックグラウンド STA から作成したり、バックグラウンドで作成したりする必要があります。</span><span class="sxs-lookup"><span data-stu-id="965b1-129">Stream should be agile or be created from a background STA to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="965b1-130">Null はコンテンツデータがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="965b1-130">Null means no content data.</span></span> <span data-ttu-id="965b1-131">IStream セマンティクスが適用されます (すべてのデータが使い果たされるまで、S_OK は読み取り呼び出しに戻ります)</span><span class="sxs-lookup"><span data-stu-id="965b1-131">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="965b1-132">get_Headers</span><span class="sxs-lookup"><span data-stu-id="965b1-132">get_Headers</span></span> 

<span data-ttu-id="965b1-133">変更可能な HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="965b1-133">The mutable HTTP request headers.</span></span>

> <span data-ttu-id="965b1-134">パブリック HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \* \* ヘッダー)</span><span class="sxs-lookup"><span data-stu-id="965b1-134">public HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \*\* headers)</span></span>

#### <span data-ttu-id="965b1-135">get_Method</span><span class="sxs-lookup"><span data-stu-id="965b1-135">get_Method</span></span> 

<span data-ttu-id="965b1-136">HTTP 要求メソッド。</span><span class="sxs-lookup"><span data-stu-id="965b1-136">The HTTP request method.</span></span>

> <span data-ttu-id="965b1-137">パブリック HRESULT [get_Method](#get_method)(LPWSTR \* メソッド)</span><span class="sxs-lookup"><span data-stu-id="965b1-137">public HRESULT [get_Method](#get_method)(LPWSTR \* method)</span></span>

#### <span data-ttu-id="965b1-138">get_Uri</span><span class="sxs-lookup"><span data-stu-id="965b1-138">get_Uri</span></span> 

<span data-ttu-id="965b1-139">要求 URI。</span><span class="sxs-lookup"><span data-stu-id="965b1-139">The request URI.</span></span>

> <span data-ttu-id="965b1-140">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="965b1-140">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="965b1-141">put_Content</span><span class="sxs-lookup"><span data-stu-id="965b1-141">put_Content</span></span> 

<span data-ttu-id="965b1-142">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="965b1-142">Set the Content property.</span></span>

> <span data-ttu-id="965b1-143">パブリック HRESULT [put_Content](#put_content)(IStream \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="965b1-143">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="965b1-144">put_Method</span><span class="sxs-lookup"><span data-stu-id="965b1-144">put_Method</span></span> 

<span data-ttu-id="965b1-145">Method プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="965b1-145">Set the Method property.</span></span>

> <span data-ttu-id="965b1-146">パブリック HRESULT [put_Method](#put_method)(LPCWSTR メソッド)</span><span class="sxs-lookup"><span data-stu-id="965b1-146">public HRESULT [put_Method](#put_method)(LPCWSTR method)</span></span>

#### <span data-ttu-id="965b1-147">put_Uri</span><span class="sxs-lookup"><span data-stu-id="965b1-147">put_Uri</span></span> 

<span data-ttu-id="965b1-148">Uri プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="965b1-148">Set the Uri property.</span></span>

> <span data-ttu-id="965b1-149">パブリック HRESULT [put_Uri](#put_uri)(LPCWSTR Uri)</span><span class="sxs-lookup"><span data-stu-id="965b1-149">public HRESULT [put_Uri](#put_uri)(LPCWSTR uri)</span></span>

