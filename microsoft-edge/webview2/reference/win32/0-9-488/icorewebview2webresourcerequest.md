---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2WebResourceRequest
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: b60df5b7493ab095c6e71f7d28dbb6ec78d39052
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883771"
---
# <span data-ttu-id="0aafb-104">0.9.515-インターフェイス ICoreWebView2WebResourceRequest</span><span class="sxs-lookup"><span data-stu-id="0aafb-104">0.9.515 - interface ICoreWebView2WebResourceRequest</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebResourceRequest
  : public IUnknown
```

<span data-ttu-id="0aafb-105">WebResourceRequested イベントと共に使用される HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="0aafb-105">An HTTP request used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="0aafb-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="0aafb-106">Summary</span></span>

 <span data-ttu-id="0aafb-107">Members</span><span class="sxs-lookup"><span data-stu-id="0aafb-107">Members</span></span>                        | <span data-ttu-id="0aafb-108">説明</span><span class="sxs-lookup"><span data-stu-id="0aafb-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0aafb-109">get_Content</span><span class="sxs-lookup"><span data-stu-id="0aafb-109">get_Content</span></span>](#get_content) | <span data-ttu-id="0aafb-110">HTTP 要求メッセージ本文をストリームとして送信します。</span><span class="sxs-lookup"><span data-stu-id="0aafb-110">The HTTP request message body as stream.</span></span>
[<span data-ttu-id="0aafb-111">get_Headers</span><span class="sxs-lookup"><span data-stu-id="0aafb-111">get_Headers</span></span>](#get_headers) | <span data-ttu-id="0aafb-112">変更可能な HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="0aafb-112">The mutable HTTP request headers.</span></span>
[<span data-ttu-id="0aafb-113">get_Method</span><span class="sxs-lookup"><span data-stu-id="0aafb-113">get_Method</span></span>](#get_method) | <span data-ttu-id="0aafb-114">HTTP 要求メソッド。</span><span class="sxs-lookup"><span data-stu-id="0aafb-114">The HTTP request method.</span></span>
[<span data-ttu-id="0aafb-115">get_Uri</span><span class="sxs-lookup"><span data-stu-id="0aafb-115">get_Uri</span></span>](#get_uri) | <span data-ttu-id="0aafb-116">要求 URI。</span><span class="sxs-lookup"><span data-stu-id="0aafb-116">The request URI.</span></span>
[<span data-ttu-id="0aafb-117">put_Content</span><span class="sxs-lookup"><span data-stu-id="0aafb-117">put_Content</span></span>](#put_content) | <span data-ttu-id="0aafb-118">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0aafb-118">Set the Content property.</span></span>
[<span data-ttu-id="0aafb-119">put_Method</span><span class="sxs-lookup"><span data-stu-id="0aafb-119">put_Method</span></span>](#put_method) | <span data-ttu-id="0aafb-120">Method プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0aafb-120">Set the Method property.</span></span>
[<span data-ttu-id="0aafb-121">put_Uri</span><span class="sxs-lookup"><span data-stu-id="0aafb-121">put_Uri</span></span>](#put_uri) | <span data-ttu-id="0aafb-122">Uri プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0aafb-122">Set the Uri property.</span></span>

## <span data-ttu-id="0aafb-123">Members</span><span class="sxs-lookup"><span data-stu-id="0aafb-123">Members</span></span>

#### <span data-ttu-id="0aafb-124">get_Content</span><span class="sxs-lookup"><span data-stu-id="0aafb-124">get_Content</span></span> 

<span data-ttu-id="0aafb-125">HTTP 要求メッセージ本文をストリームとして送信します。</span><span class="sxs-lookup"><span data-stu-id="0aafb-125">The HTTP request message body as stream.</span></span>

> <span data-ttu-id="0aafb-126">パブリック HRESULT [get_Content](#get_content)(IStream \* \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="0aafb-126">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="0aafb-127">データの投稿はここにあります。</span><span class="sxs-lookup"><span data-stu-id="0aafb-127">POST data would be here.</span></span> <span data-ttu-id="0aafb-128">ストリームが設定されている場合は、メッセージ本文を上書きします。この応答の WebResourceRequested イベントの遅延が完了するまで、ストリームにはすべてのコンテンツデータが利用可能になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0aafb-128">If a stream is set, which will override the message body, the stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="0aafb-129">UI スレッドへのパフォーマンスへの影響を防ぐために、Stream はバックグラウンド STA から作成したり、バックグラウンドで作成したりする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0aafb-129">Stream should be agile or be created from a background STA to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="0aafb-130">Null はコンテンツデータがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="0aafb-130">Null means no content data.</span></span> <span data-ttu-id="0aafb-131">IStream セマンティクスが適用されます (すべてのデータが使い果たされるまで、S_OK は読み取り呼び出しに戻ります)</span><span class="sxs-lookup"><span data-stu-id="0aafb-131">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="0aafb-132">get_Headers</span><span class="sxs-lookup"><span data-stu-id="0aafb-132">get_Headers</span></span> 

<span data-ttu-id="0aafb-133">変更可能な HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="0aafb-133">The mutable HTTP request headers.</span></span>

> <span data-ttu-id="0aafb-134">パブリック HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \* \* ヘッダー)</span><span class="sxs-lookup"><span data-stu-id="0aafb-134">public HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \*\* headers)</span></span>

#### <span data-ttu-id="0aafb-135">get_Method</span><span class="sxs-lookup"><span data-stu-id="0aafb-135">get_Method</span></span> 

<span data-ttu-id="0aafb-136">HTTP 要求メソッド。</span><span class="sxs-lookup"><span data-stu-id="0aafb-136">The HTTP request method.</span></span>

> <span data-ttu-id="0aafb-137">パブリック HRESULT [get_Method](#get_method)(LPWSTR \* メソッド)</span><span class="sxs-lookup"><span data-stu-id="0aafb-137">public HRESULT [get_Method](#get_method)(LPWSTR \* method)</span></span>

#### <span data-ttu-id="0aafb-138">get_Uri</span><span class="sxs-lookup"><span data-stu-id="0aafb-138">get_Uri</span></span> 

<span data-ttu-id="0aafb-139">要求 URI。</span><span class="sxs-lookup"><span data-stu-id="0aafb-139">The request URI.</span></span>

> <span data-ttu-id="0aafb-140">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="0aafb-140">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="0aafb-141">put_Content</span><span class="sxs-lookup"><span data-stu-id="0aafb-141">put_Content</span></span> 

<span data-ttu-id="0aafb-142">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0aafb-142">Set the Content property.</span></span>

> <span data-ttu-id="0aafb-143">パブリック HRESULT [put_Content](#put_content)(IStream \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="0aafb-143">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="0aafb-144">put_Method</span><span class="sxs-lookup"><span data-stu-id="0aafb-144">put_Method</span></span> 

<span data-ttu-id="0aafb-145">Method プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0aafb-145">Set the Method property.</span></span>

> <span data-ttu-id="0aafb-146">パブリック HRESULT [put_Method](#put_method)(LPCWSTR メソッド)</span><span class="sxs-lookup"><span data-stu-id="0aafb-146">public HRESULT [put_Method](#put_method)(LPCWSTR method)</span></span>

#### <span data-ttu-id="0aafb-147">put_Uri</span><span class="sxs-lookup"><span data-stu-id="0aafb-147">put_Uri</span></span> 

<span data-ttu-id="0aafb-148">Uri プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0aafb-148">Set the Uri property.</span></span>

> <span data-ttu-id="0aafb-149">パブリック HRESULT [put_Uri](#put_uri)(LPCWSTR Uri)</span><span class="sxs-lookup"><span data-stu-id="0aafb-149">public HRESULT [put_Uri](#put_uri)(LPCWSTR uri)</span></span>

