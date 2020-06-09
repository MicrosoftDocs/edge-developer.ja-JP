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
ms.openlocfilehash: 5b80691f0e42be4cdea7c99b165bfe9cebf632dd
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697932"
---
# <span data-ttu-id="09232-104">インターフェイス ICoreWebView2WebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="09232-104">interface ICoreWebView2WebResourceResponse</span></span> 

> [!NOTE]
> <span data-ttu-id="09232-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="09232-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="09232-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09232-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2WebResourceResponse
  : public IUnknown
```

<span data-ttu-id="09232-107">WebResourceRequested イベントと共に使用される HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="09232-107">An HTTP response used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="09232-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="09232-108">Summary</span></span>

 <span data-ttu-id="09232-109">Members</span><span class="sxs-lookup"><span data-stu-id="09232-109">Members</span></span>                        | <span data-ttu-id="09232-110">説明</span><span class="sxs-lookup"><span data-stu-id="09232-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="09232-111">get_Content</span><span class="sxs-lookup"><span data-stu-id="09232-111">get_Content</span></span>](#get_content) | <span data-ttu-id="09232-112">ストリームとしての HTTP 応答のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="09232-112">HTTP response content as stream.</span></span>
[<span data-ttu-id="09232-113">get_Headers</span><span class="sxs-lookup"><span data-stu-id="09232-113">get_Headers</span></span>](#get_headers) | <span data-ttu-id="09232-114">上書きされた HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="09232-114">Overridden HTTP response headers.</span></span>
[<span data-ttu-id="09232-115">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="09232-115">get_ReasonPhrase</span></span>](#get_reasonphrase) | <span data-ttu-id="09232-116">HTTP 応答の理由の語句。</span><span class="sxs-lookup"><span data-stu-id="09232-116">The HTTP response reason phrase.</span></span>
[<span data-ttu-id="09232-117">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="09232-117">get_StatusCode</span></span>](#get_statuscode) | <span data-ttu-id="09232-118">HTTP 応答状態コード。</span><span class="sxs-lookup"><span data-stu-id="09232-118">The HTTP response status code.</span></span>
[<span data-ttu-id="09232-119">put_Content</span><span class="sxs-lookup"><span data-stu-id="09232-119">put_Content</span></span>](#put_content) | <span data-ttu-id="09232-120">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="09232-120">Set the Content property.</span></span>
[<span data-ttu-id="09232-121">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="09232-121">put_ReasonPhrase</span></span>](#put_reasonphrase) | <span data-ttu-id="09232-122">"理由" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="09232-122">Set the ReasonPhrase property.</span></span>
[<span data-ttu-id="09232-123">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="09232-123">put_StatusCode</span></span>](#put_statuscode) | <span data-ttu-id="09232-124">StatusCode プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="09232-124">Set the StatusCode property.</span></span>

## <span data-ttu-id="09232-125">Members</span><span class="sxs-lookup"><span data-stu-id="09232-125">Members</span></span>

#### <span data-ttu-id="09232-126">get_Content</span><span class="sxs-lookup"><span data-stu-id="09232-126">get_Content</span></span> 

<span data-ttu-id="09232-127">ストリームとしての HTTP 応答のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="09232-127">HTTP response content as stream.</span></span>

> <span data-ttu-id="09232-128">パブリック HRESULT [get_Content](#get_content)(IStream \* \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="09232-128">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="09232-129">この応答の WebResourceRequested イベントの遅延が完了するまで、ストリームにはすべてのコンテンツデータが利用可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="09232-129">Stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="09232-130">UI スレッドに対するパフォーマンスへの影響を防ぐには、ストリームをアジャイルにするか、バックグラウンドスレッドから作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09232-130">Stream should be agile or be created from a background thread to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="09232-131">Null はコンテンツデータがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="09232-131">Null means no content data.</span></span> <span data-ttu-id="09232-132">IStream セマンティクスが適用されます (すべてのデータが使い果たされるまで、S_OK は読み取り呼び出しに戻ります)</span><span class="sxs-lookup"><span data-stu-id="09232-132">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="09232-133">get_Headers</span><span class="sxs-lookup"><span data-stu-id="09232-133">get_Headers</span></span> 

<span data-ttu-id="09232-134">上書きされた HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="09232-134">Overridden HTTP response headers.</span></span>

> <span data-ttu-id="09232-135">パブリック HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) \* \* ヘッダー)</span><span class="sxs-lookup"><span data-stu-id="09232-135">public HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) \*\* headers)</span></span>

#### <span data-ttu-id="09232-136">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="09232-136">get_ReasonPhrase</span></span> 

<span data-ttu-id="09232-137">HTTP 応答の理由の語句。</span><span class="sxs-lookup"><span data-stu-id="09232-137">The HTTP response reason phrase.</span></span>

> <span data-ttu-id="09232-138">パブリック HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* 理由語句)</span><span class="sxs-lookup"><span data-stu-id="09232-138">public HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* reasonPhrase)</span></span>

#### <span data-ttu-id="09232-139">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="09232-139">get_StatusCode</span></span> 

<span data-ttu-id="09232-140">HTTP 応答状態コード。</span><span class="sxs-lookup"><span data-stu-id="09232-140">The HTTP response status code.</span></span>

> <span data-ttu-id="09232-141">パブリック HRESULT [get_StatusCode](#get_statuscode)(Int \* StatusCode)</span><span class="sxs-lookup"><span data-stu-id="09232-141">public HRESULT [get_StatusCode](#get_statuscode)(int \* statusCode)</span></span>

#### <span data-ttu-id="09232-142">put_Content</span><span class="sxs-lookup"><span data-stu-id="09232-142">put_Content</span></span> 

<span data-ttu-id="09232-143">Content プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="09232-143">Set the Content property.</span></span>

> <span data-ttu-id="09232-144">パブリック HRESULT [put_Content](#put_content)(IStream \* コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="09232-144">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="09232-145">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="09232-145">put_ReasonPhrase</span></span> 

<span data-ttu-id="09232-146">"理由" プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="09232-146">Set the ReasonPhrase property.</span></span>

> <span data-ttu-id="09232-147">パブリック HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR 理由語句)</span><span class="sxs-lookup"><span data-stu-id="09232-147">public HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR reasonPhrase)</span></span>

#### <span data-ttu-id="09232-148">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="09232-148">put_StatusCode</span></span> 

<span data-ttu-id="09232-149">StatusCode プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="09232-149">Set the StatusCode property.</span></span>

> <span data-ttu-id="09232-150">パブリック HRESULT [put_StatusCode](#put_statuscode)(int StatusCode)</span><span class="sxs-lookup"><span data-stu-id="09232-150">public HRESULT [put_StatusCode](#put_statuscode)(int statusCode)</span></span>

