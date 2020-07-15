---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2WebResourceRequest
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: cdea3b4d4643e6f14e546eb9edd27bf1534beadd
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877351"
---
# <span data-ttu-id="89326-104">0.9.515-インターフェイス ICoreWebView2WebResourceRequest</span><span class="sxs-lookup"><span data-stu-id="89326-104">0.9.515 - interface ICoreWebView2WebResourceRequest</span></span> 

> [!NOTE]
> <span data-ttu-id="89326-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89326-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="89326-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89326-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2WebResourceRequest
  : public IUnknown
```

<span data-ttu-id="89326-107">WebResourceRequested イベントと共に使用される HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="89326-107">An HTTP request used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="89326-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="89326-108">Summary</span></span>

 <span data-ttu-id="89326-109">Members</span><span class="sxs-lookup"><span data-stu-id="89326-109">Members</span></span>                        | <span data-ttu-id="89326-110">説明</span><span class="sxs-lookup"><span data-stu-id="89326-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="89326-111">get_Content</span><span class="sxs-lookup"><span data-stu-id="89326-111">get_Content</span></span>](#get_content) | <span data-ttu-id="89326-112">HTTP 要求メッセージ本文をストリームとして送信します。</span><span class="sxs-lookup"><span data-stu-id="89326-112">The HTTP request message body as stream.</span></span>
[<span data-ttu-id="89326-113">get_Headers</span><span class="sxs-lookup"><span data-stu-id="89326-113">get_Headers</span></span>](#get_headers) | <span data-ttu-id="89326-114">変更可能な HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="89326-114">The mutable HTTP request headers.</span></span>
[<span data-ttu-id="89326-115">get_Method</span><span class="sxs-lookup"><span data-stu-id="89326-115">get_Method</span></span>](#get_method) | <span data-ttu-id="89326-116">HTTP 要求メソッド。</span><span class="sxs-lookup"><span data-stu-id="89326-116">The HTTP request method.</span></span>
[<span data-ttu-id="89326-117">get_Uri</span><span class="sxs-lookup"><span data-stu-id="89326-117">get_Uri</span></span>](#get_uri) | <span data-ttu-id="89326-118">要求 URI。</span><span class="sxs-lookup"><span data-stu-id="89326-118">The request URI.</span></span>
[<span data-ttu-id="89326-119">put_Content</span><span class="sxs-lookup"><span data-stu-id="89326-119">put_Content</span></span>](#put_content) | <span data-ttu-id="89326-120">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="89326-120">Set the Content property.</span></span>
[<span data-ttu-id="89326-121">put_Method</span><span class="sxs-lookup"><span data-stu-id="89326-121">put_Method</span></span>](#put_method) | <span data-ttu-id="89326-122">Method プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="89326-122">Set the Method property.</span></span>
[<span data-ttu-id="89326-123">put_Uri</span><span class="sxs-lookup"><span data-stu-id="89326-123">put_Uri</span></span>](#put_uri) | <span data-ttu-id="89326-124">Uri プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="89326-124">Set the Uri property.</span></span>

## <span data-ttu-id="89326-125">Members</span><span class="sxs-lookup"><span data-stu-id="89326-125">Members</span></span>

#### <span data-ttu-id="89326-126">get_Content</span><span class="sxs-lookup"><span data-stu-id="89326-126">get_Content</span></span> 

<span data-ttu-id="89326-127">HTTP 要求メッセージ本文をストリームとして送信します。</span><span class="sxs-lookup"><span data-stu-id="89326-127">The HTTP request message body as stream.</span></span>

> <span data-ttu-id="89326-128">パブリック HRESULT [get_Content](#get_content)(IStream \* \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="89326-128">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="89326-129">データの投稿はここにあります。</span><span class="sxs-lookup"><span data-stu-id="89326-129">POST data would be here.</span></span> <span data-ttu-id="89326-130">ストリームが設定されている場合は、メッセージ本文を上書きします。この応答の WebResourceRequested イベントの遅延が完了するまで、ストリームにはすべてのコンテンツデータが利用可能になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="89326-130">If a stream is set, which will override the message body, the stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="89326-131">UI スレッドへのパフォーマンスへの影響を防ぐために、Stream はバックグラウンド STA から作成したり、バックグラウンドで作成したりする必要があります。</span><span class="sxs-lookup"><span data-stu-id="89326-131">Stream should be agile or be created from a background STA to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="89326-132">Null はコンテンツデータがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="89326-132">Null means no content data.</span></span> <span data-ttu-id="89326-133">IStream セマンティクスが適用されます (すべてのデータが使い果たされるまで、S_OK は読み取り呼び出しに戻ります)</span><span class="sxs-lookup"><span data-stu-id="89326-133">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="89326-134">get_Headers</span><span class="sxs-lookup"><span data-stu-id="89326-134">get_Headers</span></span> 

<span data-ttu-id="89326-135">変更可能な HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="89326-135">The mutable HTTP request headers.</span></span>

> <span data-ttu-id="89326-136">パブリック HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \* \* ヘッダー)</span><span class="sxs-lookup"><span data-stu-id="89326-136">public HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \*\* headers)</span></span>

#### <span data-ttu-id="89326-137">get_Method</span><span class="sxs-lookup"><span data-stu-id="89326-137">get_Method</span></span> 

<span data-ttu-id="89326-138">HTTP 要求メソッド。</span><span class="sxs-lookup"><span data-stu-id="89326-138">The HTTP request method.</span></span>

> <span data-ttu-id="89326-139">パブリック HRESULT [get_Method](#get_method)(LPWSTR \* メソッド)</span><span class="sxs-lookup"><span data-stu-id="89326-139">public HRESULT [get_Method](#get_method)(LPWSTR \* method)</span></span>

#### <span data-ttu-id="89326-140">get_Uri</span><span class="sxs-lookup"><span data-stu-id="89326-140">get_Uri</span></span> 

<span data-ttu-id="89326-141">要求 URI。</span><span class="sxs-lookup"><span data-stu-id="89326-141">The request URI.</span></span>

> <span data-ttu-id="89326-142">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="89326-142">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="89326-143">put_Content</span><span class="sxs-lookup"><span data-stu-id="89326-143">put_Content</span></span> 

<span data-ttu-id="89326-144">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="89326-144">Set the Content property.</span></span>

> <span data-ttu-id="89326-145">パブリック HRESULT [put_Content](#put_content)(IStream \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="89326-145">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="89326-146">put_Method</span><span class="sxs-lookup"><span data-stu-id="89326-146">put_Method</span></span> 

<span data-ttu-id="89326-147">Method プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="89326-147">Set the Method property.</span></span>

> <span data-ttu-id="89326-148">パブリック HRESULT [put_Method](#put_method)(LPCWSTR メソッド)</span><span class="sxs-lookup"><span data-stu-id="89326-148">public HRESULT [put_Method](#put_method)(LPCWSTR method)</span></span>

#### <span data-ttu-id="89326-149">put_Uri</span><span class="sxs-lookup"><span data-stu-id="89326-149">put_Uri</span></span> 

<span data-ttu-id="89326-150">Uri プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="89326-150">Set the Uri property.</span></span>

> <span data-ttu-id="89326-151">パブリック HRESULT [put_Uri](#put_uri)(LPCWSTR Uri)</span><span class="sxs-lookup"><span data-stu-id="89326-151">public HRESULT [put_Uri](#put_uri)(LPCWSTR uri)</span></span>

