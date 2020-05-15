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
ms.openlocfilehash: 69bf9eeae4b6736ac6df6ddaa9594b7438cbf58c
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654232"
---
# <span data-ttu-id="e4045-104">インターフェイス IWebView2WebResourceRequest</span><span class="sxs-lookup"><span data-stu-id="e4045-104">interface IWebView2WebResourceRequest</span></span> 

> [!NOTE]
> <span data-ttu-id="e4045-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e4045-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="e4045-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4045-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebResourceRequest
  : public IUnknown
```

<span data-ttu-id="e4045-107">WebResourceRequested イベントと共に使用される HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="e4045-107">An HTTP request used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="e4045-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="e4045-108">Summary</span></span>

 <span data-ttu-id="e4045-109">Members</span><span class="sxs-lookup"><span data-stu-id="e4045-109">Members</span></span>                        | <span data-ttu-id="e4045-110">説明</span><span class="sxs-lookup"><span data-stu-id="e4045-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e4045-111">get_Uri</span><span class="sxs-lookup"><span data-stu-id="e4045-111">get_Uri</span></span>](#get_uri) | <span data-ttu-id="e4045-112">要求 URI。</span><span class="sxs-lookup"><span data-stu-id="e4045-112">The request URI.</span></span>
[<span data-ttu-id="e4045-113">put_Uri</span><span class="sxs-lookup"><span data-stu-id="e4045-113">put_Uri</span></span>](#put_uri) | <span data-ttu-id="e4045-114">Uri プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e4045-114">Set the Uri property.</span></span>
[<span data-ttu-id="e4045-115">get_Method</span><span class="sxs-lookup"><span data-stu-id="e4045-115">get_Method</span></span>](#get_method) | <span data-ttu-id="e4045-116">HTTP 要求メソッド。</span><span class="sxs-lookup"><span data-stu-id="e4045-116">The HTTP request method.</span></span>
[<span data-ttu-id="e4045-117">put_Method</span><span class="sxs-lookup"><span data-stu-id="e4045-117">put_Method</span></span>](#put_method) | <span data-ttu-id="e4045-118">Method プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e4045-118">Set the Method property.</span></span>
[<span data-ttu-id="e4045-119">get_Content</span><span class="sxs-lookup"><span data-stu-id="e4045-119">get_Content</span></span>](#get_content) | <span data-ttu-id="e4045-120">HTTP 要求メッセージ本文をストリームとして送信します。</span><span class="sxs-lookup"><span data-stu-id="e4045-120">The HTTP request message body as stream.</span></span>
[<span data-ttu-id="e4045-121">put_Content</span><span class="sxs-lookup"><span data-stu-id="e4045-121">put_Content</span></span>](#put_content) | <span data-ttu-id="e4045-122">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e4045-122">Set the Content property.</span></span>
[<span data-ttu-id="e4045-123">get_Headers</span><span class="sxs-lookup"><span data-stu-id="e4045-123">get_Headers</span></span>](#get_headers) | <span data-ttu-id="e4045-124">変更可能な HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="e4045-124">The mutable HTTP request headers.</span></span>

## <span data-ttu-id="e4045-125">Members</span><span class="sxs-lookup"><span data-stu-id="e4045-125">Members</span></span>

#### <span data-ttu-id="e4045-126">get_Uri</span><span class="sxs-lookup"><span data-stu-id="e4045-126">get_Uri</span></span> 

<span data-ttu-id="e4045-127">要求 URI。</span><span class="sxs-lookup"><span data-stu-id="e4045-127">The request URI.</span></span>

> <span data-ttu-id="e4045-128">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="e4045-128">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="e4045-129">put_Uri</span><span class="sxs-lookup"><span data-stu-id="e4045-129">put_Uri</span></span> 

<span data-ttu-id="e4045-130">Uri プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e4045-130">Set the Uri property.</span></span>

> <span data-ttu-id="e4045-131">パブリック HRESULT [put_Uri](#put_uri)(LPCWSTR Uri)</span><span class="sxs-lookup"><span data-stu-id="e4045-131">public HRESULT [put_Uri](#put_uri)(LPCWSTR uri)</span></span>

#### <span data-ttu-id="e4045-132">get_Method</span><span class="sxs-lookup"><span data-stu-id="e4045-132">get_Method</span></span> 

<span data-ttu-id="e4045-133">HTTP 要求メソッド。</span><span class="sxs-lookup"><span data-stu-id="e4045-133">The HTTP request method.</span></span>

> <span data-ttu-id="e4045-134">パブリック HRESULT [get_Method](#get_method)(LPWSTR \* メソッド)</span><span class="sxs-lookup"><span data-stu-id="e4045-134">public HRESULT [get_Method](#get_method)(LPWSTR \* method)</span></span>

#### <span data-ttu-id="e4045-135">put_Method</span><span class="sxs-lookup"><span data-stu-id="e4045-135">put_Method</span></span> 

<span data-ttu-id="e4045-136">Method プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e4045-136">Set the Method property.</span></span>

> <span data-ttu-id="e4045-137">パブリック HRESULT [put_Method](#put_method)(LPCWSTR メソッド)</span><span class="sxs-lookup"><span data-stu-id="e4045-137">public HRESULT [put_Method](#put_method)(LPCWSTR method)</span></span>

#### <span data-ttu-id="e4045-138">get_Content</span><span class="sxs-lookup"><span data-stu-id="e4045-138">get_Content</span></span> 

<span data-ttu-id="e4045-139">HTTP 要求メッセージ本文をストリームとして送信します。</span><span class="sxs-lookup"><span data-stu-id="e4045-139">The HTTP request message body as stream.</span></span>

> <span data-ttu-id="e4045-140">パブリック HRESULT [get_Content](#get_content)(IStream \* \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="e4045-140">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="e4045-141">データの投稿はここにあります。</span><span class="sxs-lookup"><span data-stu-id="e4045-141">POST data would be here.</span></span> <span data-ttu-id="e4045-142">ストリームが設定されている場合は、メッセージ本文を上書きします。この応答の WebResourceRequested イベントの遅延が完了するまで、ストリームにはすべてのコンテンツデータが利用可能になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4045-142">If a stream is set, which will override the message body, the stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="e4045-143">UI スレッドへのパフォーマンスへの影響を防ぐために、Stream はバックグラウンド STA から作成したり、バックグラウンドで作成したりする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4045-143">Stream should be agile or be created from a background STA to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="e4045-144">Null はコンテンツデータがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e4045-144">Null means no content data.</span></span> <span data-ttu-id="e4045-145">IStream セマンティクスが適用されます (すべてのデータが使い果たされるまで、S_OK は読み取り呼び出しに戻ります)</span><span class="sxs-lookup"><span data-stu-id="e4045-145">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="e4045-146">put_Content</span><span class="sxs-lookup"><span data-stu-id="e4045-146">put_Content</span></span> 

<span data-ttu-id="e4045-147">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e4045-147">Set the Content property.</span></span>

> <span data-ttu-id="e4045-148">パブリック HRESULT [put_Content](#put_content)(IStream \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="e4045-148">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="e4045-149">get_Headers</span><span class="sxs-lookup"><span data-stu-id="e4045-149">get_Headers</span></span> 

<span data-ttu-id="e4045-150">変更可能な HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="e4045-150">The mutable HTTP request headers.</span></span>

> <span data-ttu-id="e4045-151">パブリック HRESULT [get_Headers](#get_headers)([IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md) \* \* ヘッダー)</span><span class="sxs-lookup"><span data-stu-id="e4045-151">public HRESULT [get_Headers](#get_headers)([IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md) \*\* headers)</span></span>

