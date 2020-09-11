---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2WebResourceRequest
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2WebResourceRequest
ms.openlocfilehash: 9d14162c8c451bc62de86a671c586f544fb4191b
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012327"
---
# <span data-ttu-id="517b4-104">インターフェイス ICoreWebView2WebResourceRequest</span><span class="sxs-lookup"><span data-stu-id="517b4-104">interface ICoreWebView2WebResourceRequest</span></span> 

```
interface ICoreWebView2WebResourceRequest
  : public IUnknown
```

<span data-ttu-id="517b4-105">WebResourceRequested イベントと共に使用される HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="517b4-105">An HTTP request used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="517b4-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="517b4-106">Summary</span></span>

 <span data-ttu-id="517b4-107">Members</span><span class="sxs-lookup"><span data-stu-id="517b4-107">Members</span></span>                        | <span data-ttu-id="517b4-108">説明</span><span class="sxs-lookup"><span data-stu-id="517b4-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="517b4-109">get_Content</span><span class="sxs-lookup"><span data-stu-id="517b4-109">get_Content</span></span>](#get_content) | <span data-ttu-id="517b4-110">HTTP 要求メッセージ本文をストリームとして送信します。</span><span class="sxs-lookup"><span data-stu-id="517b4-110">The HTTP request message body as stream.</span></span>
[<span data-ttu-id="517b4-111">get_Headers</span><span class="sxs-lookup"><span data-stu-id="517b4-111">get_Headers</span></span>](#get_headers) | <span data-ttu-id="517b4-112">変更可能な HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="517b4-112">The mutable HTTP request headers.</span></span>
[<span data-ttu-id="517b4-113">get_Method</span><span class="sxs-lookup"><span data-stu-id="517b4-113">get_Method</span></span>](#get_method) | <span data-ttu-id="517b4-114">HTTP 要求メソッド。</span><span class="sxs-lookup"><span data-stu-id="517b4-114">The HTTP request method.</span></span>
[<span data-ttu-id="517b4-115">get_Uri</span><span class="sxs-lookup"><span data-stu-id="517b4-115">get_Uri</span></span>](#get_uri) | <span data-ttu-id="517b4-116">要求 URI。</span><span class="sxs-lookup"><span data-stu-id="517b4-116">The request URI.</span></span>
[<span data-ttu-id="517b4-117">put_Content</span><span class="sxs-lookup"><span data-stu-id="517b4-117">put_Content</span></span>](#put_content) | <span data-ttu-id="517b4-118">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="517b4-118">Set the Content property.</span></span>
[<span data-ttu-id="517b4-119">put_Method</span><span class="sxs-lookup"><span data-stu-id="517b4-119">put_Method</span></span>](#put_method) | <span data-ttu-id="517b4-120">Method プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="517b4-120">Set the Method property.</span></span>
[<span data-ttu-id="517b4-121">put_Uri</span><span class="sxs-lookup"><span data-stu-id="517b4-121">put_Uri</span></span>](#put_uri) | <span data-ttu-id="517b4-122">Uri プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="517b4-122">Set the Uri property.</span></span>

## <span data-ttu-id="517b4-123">Members</span><span class="sxs-lookup"><span data-stu-id="517b4-123">Members</span></span>

#### <span data-ttu-id="517b4-124">get_Content</span><span class="sxs-lookup"><span data-stu-id="517b4-124">get_Content</span></span> 

<span data-ttu-id="517b4-125">HTTP 要求メッセージ本文をストリームとして送信します。</span><span class="sxs-lookup"><span data-stu-id="517b4-125">The HTTP request message body as stream.</span></span>

> <span data-ttu-id="517b4-126">パブリック HRESULT [get_Content](#get_content)(IStream \* \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="517b4-126">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="517b4-127">データの投稿はここにあります。</span><span class="sxs-lookup"><span data-stu-id="517b4-127">POST data would be here.</span></span> <span data-ttu-id="517b4-128">ストリームが設定されている場合は、メッセージ本文を上書きします。この応答の WebResourceRequested イベントの遅延が完了するまで、ストリームにはすべてのコンテンツデータが利用可能になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="517b4-128">If a stream is set, which will override the message body, the stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="517b4-129">UI スレッドへのパフォーマンスへの影響を防ぐために、Stream はバックグラウンド STA から作成したり、バックグラウンドで作成したりする必要があります。</span><span class="sxs-lookup"><span data-stu-id="517b4-129">Stream should be agile or be created from a background STA to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="517b4-130">Null はコンテンツデータがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="517b4-130">Null means no content data.</span></span> <span data-ttu-id="517b4-131">IStream セマンティクスが適用されます (すべてのデータが使い果たされるまで、S_OK は読み取り呼び出しに戻ります)。</span><span class="sxs-lookup"><span data-stu-id="517b4-131">IStream semantics apply (return S_OK to Read calls until all data is exhausted).</span></span>

#### <span data-ttu-id="517b4-132">get_Headers</span><span class="sxs-lookup"><span data-stu-id="517b4-132">get_Headers</span></span> 

<span data-ttu-id="517b4-133">変更可能な HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="517b4-133">The mutable HTTP request headers.</span></span>

> <span data-ttu-id="517b4-134">パブリック HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \* \* ヘッダー)</span><span class="sxs-lookup"><span data-stu-id="517b4-134">public HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \*\* headers)</span></span>

#### <span data-ttu-id="517b4-135">get_Method</span><span class="sxs-lookup"><span data-stu-id="517b4-135">get_Method</span></span> 

<span data-ttu-id="517b4-136">HTTP 要求メソッド。</span><span class="sxs-lookup"><span data-stu-id="517b4-136">The HTTP request method.</span></span>

> <span data-ttu-id="517b4-137">パブリック HRESULT [get_Method](#get_method)(LPWSTR \* メソッド)</span><span class="sxs-lookup"><span data-stu-id="517b4-137">public HRESULT [get_Method](#get_method)(LPWSTR \* method)</span></span>

#### <span data-ttu-id="517b4-138">get_Uri</span><span class="sxs-lookup"><span data-stu-id="517b4-138">get_Uri</span></span> 

<span data-ttu-id="517b4-139">要求 URI。</span><span class="sxs-lookup"><span data-stu-id="517b4-139">The request URI.</span></span>

> <span data-ttu-id="517b4-140">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="517b4-140">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="517b4-141">put_Content</span><span class="sxs-lookup"><span data-stu-id="517b4-141">put_Content</span></span> 

<span data-ttu-id="517b4-142">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="517b4-142">Set the Content property.</span></span>

> <span data-ttu-id="517b4-143">パブリック HRESULT [put_Content](#put_content)(IStream \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="517b4-143">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="517b4-144">put_Method</span><span class="sxs-lookup"><span data-stu-id="517b4-144">put_Method</span></span> 

<span data-ttu-id="517b4-145">Method プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="517b4-145">Set the Method property.</span></span>

> <span data-ttu-id="517b4-146">パブリック HRESULT [put_Method](#put_method)(LPCWSTR メソッド)</span><span class="sxs-lookup"><span data-stu-id="517b4-146">public HRESULT [put_Method](#put_method)(LPCWSTR method)</span></span>

#### <span data-ttu-id="517b4-147">put_Uri</span><span class="sxs-lookup"><span data-stu-id="517b4-147">put_Uri</span></span> 

<span data-ttu-id="517b4-148">Uri プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="517b4-148">Set the Uri property.</span></span>

> <span data-ttu-id="517b4-149">パブリック HRESULT [put_Uri](#put_uri)(LPCWSTR Uri)</span><span class="sxs-lookup"><span data-stu-id="517b4-149">public HRESULT [put_Uri](#put_uri)(LPCWSTR uri)</span></span>

