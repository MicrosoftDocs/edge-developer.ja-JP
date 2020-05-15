---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: b23b724977b9d164c48dc99d0da2e64d61539549
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654521"
---
# <span data-ttu-id="61f5a-104">インターフェイス ICoreWebView2HttpResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="61f5a-104">interface ICoreWebView2HttpResponseHeaders</span></span> 

> [!NOTE]
> <span data-ttu-id="61f5a-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="61f5a-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="61f5a-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61f5a-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2HttpResponseHeaders
  : public IUnknown
```

<span data-ttu-id="61f5a-107">HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="61f5a-107">HTTP response headers.</span></span>

## <span data-ttu-id="61f5a-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="61f5a-108">Summary</span></span>

 <span data-ttu-id="61f5a-109">Members</span><span class="sxs-lookup"><span data-stu-id="61f5a-109">Members</span></span>                        | <span data-ttu-id="61f5a-110">説明</span><span class="sxs-lookup"><span data-stu-id="61f5a-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="61f5a-111">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="61f5a-111">AppendHeader</span></span>](#appendheader) | <span data-ttu-id="61f5a-112">名前と値が含まれるヘッダー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="61f5a-112">Appends header line with name and value.</span></span>
[<span data-ttu-id="61f5a-113">Contains</span><span class="sxs-lookup"><span data-stu-id="61f5a-113">Contains</span></span>](#contains) | <span data-ttu-id="61f5a-114">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="61f5a-114">Checks whether the headers contain entries matching the header name.</span></span>
[<span data-ttu-id="61f5a-115">GetHeader</span><span class="sxs-lookup"><span data-stu-id="61f5a-115">GetHeader</span></span>](#getheader) | <span data-ttu-id="61f5a-116">名前に一致するコレクションの最初のヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="61f5a-116">Gets the first header value in the collection matching the name.</span></span>
[<span data-ttu-id="61f5a-117">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="61f5a-117">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="61f5a-118">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="61f5a-118">Gets the header values matching the name.</span></span>
[<span data-ttu-id="61f5a-119">GetIterator</span><span class="sxs-lookup"><span data-stu-id="61f5a-119">GetIterator</span></span>](#getiterator) | <span data-ttu-id="61f5a-120">応答ヘッダー全体のコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="61f5a-120">Gets an iterator over the collection of entire response headers.</span></span>

<span data-ttu-id="61f5a-121">WebResourceRequested イベントの WebResourceResponse を作成するために使われます。</span><span class="sxs-lookup"><span data-stu-id="61f5a-121">Used to construct a WebResourceResponse for the WebResourceRequested event.</span></span>

## <span data-ttu-id="61f5a-122">Members</span><span class="sxs-lookup"><span data-stu-id="61f5a-122">Members</span></span>

#### <span data-ttu-id="61f5a-123">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="61f5a-123">AppendHeader</span></span> 

<span data-ttu-id="61f5a-124">名前と値が含まれるヘッダー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="61f5a-124">Appends header line with name and value.</span></span>

> <span data-ttu-id="61f5a-125">パブリック HRESULT [Appendheader](#appendheader)(LPCWSTR NAME, LPCWSTR value)</span><span class="sxs-lookup"><span data-stu-id="61f5a-125">public HRESULT [AppendHeader](#appendheader)(LPCWSTR name,LPCWSTR value)</span></span>

#### <span data-ttu-id="61f5a-126">Contains</span><span class="sxs-lookup"><span data-stu-id="61f5a-126">Contains</span></span> 

<span data-ttu-id="61f5a-127">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="61f5a-127">Checks whether the headers contain entries matching the header name.</span></span>

> <span data-ttu-id="61f5a-128">パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL \* contains)</span><span class="sxs-lookup"><span data-stu-id="61f5a-128">public HRESULT [Contains](#contains)(LPCWSTR name,BOOL \* contains)</span></span>

#### <span data-ttu-id="61f5a-129">GetHeader</span><span class="sxs-lookup"><span data-stu-id="61f5a-129">GetHeader</span></span> 

<span data-ttu-id="61f5a-130">名前に一致するコレクションの最初のヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="61f5a-130">Gets the first header value in the collection matching the name.</span></span>

> <span data-ttu-id="61f5a-131">パブリック HRESULT [GetHeader](#getheader)(LPCWSTR NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="61f5a-131">public HRESULT [GetHeader](#getheader)(LPCWSTR name,LPWSTR \* value)</span></span>

#### <span data-ttu-id="61f5a-132">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="61f5a-132">GetHeaders</span></span> 

<span data-ttu-id="61f5a-133">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="61f5a-133">Gets the header values matching the name.</span></span>

> <span data-ttu-id="61f5a-134">パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name,[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="61f5a-134">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name,[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="61f5a-135">GetIterator</span><span class="sxs-lookup"><span data-stu-id="61f5a-135">GetIterator</span></span> 

<span data-ttu-id="61f5a-136">応答ヘッダー全体のコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="61f5a-136">Gets an iterator over the collection of entire response headers.</span></span>

> <span data-ttu-id="61f5a-137">パブリック HRESULT [Getiterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="61f5a-137">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

