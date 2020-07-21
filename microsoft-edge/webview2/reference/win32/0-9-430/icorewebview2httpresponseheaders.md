---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2HttpResponseHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 321d18a726ac19db92018cb27d31867029991cf0
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886221"
---
# <span data-ttu-id="5c9ed-104">0.9.430-インターフェイス ICoreWebView2HttpResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="5c9ed-104">0.9.430 - interface ICoreWebView2HttpResponseHeaders</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2HttpResponseHeaders
  : public IUnknown
```

<span data-ttu-id="5c9ed-105">HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="5c9ed-105">HTTP response headers.</span></span>

## <span data-ttu-id="5c9ed-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="5c9ed-106">Summary</span></span>

 <span data-ttu-id="5c9ed-107">Members</span><span class="sxs-lookup"><span data-stu-id="5c9ed-107">Members</span></span>                        | <span data-ttu-id="5c9ed-108">説明</span><span class="sxs-lookup"><span data-stu-id="5c9ed-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5c9ed-109">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="5c9ed-109">AppendHeader</span></span>](#appendheader) | <span data-ttu-id="5c9ed-110">名前と値が含まれるヘッダー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="5c9ed-110">Appends header line with name and value.</span></span>
[<span data-ttu-id="5c9ed-111">Contains</span><span class="sxs-lookup"><span data-stu-id="5c9ed-111">Contains</span></span>](#contains) | <span data-ttu-id="5c9ed-112">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5c9ed-112">Checks whether the headers contain entries matching the header name.</span></span>
[<span data-ttu-id="5c9ed-113">GetHeader</span><span class="sxs-lookup"><span data-stu-id="5c9ed-113">GetHeader</span></span>](#getheader) | <span data-ttu-id="5c9ed-114">名前に一致するコレクションの最初のヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="5c9ed-114">Gets the first header value in the collection matching the name.</span></span>
[<span data-ttu-id="5c9ed-115">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="5c9ed-115">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="5c9ed-116">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="5c9ed-116">Gets the header values matching the name.</span></span>
[<span data-ttu-id="5c9ed-117">GetIterator</span><span class="sxs-lookup"><span data-stu-id="5c9ed-117">GetIterator</span></span>](#getiterator) | <span data-ttu-id="5c9ed-118">応答ヘッダー全体のコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="5c9ed-118">Gets an iterator over the collection of entire response headers.</span></span>

<span data-ttu-id="5c9ed-119">WebResourceRequested イベントの WebResourceResponse を作成するために使われます。</span><span class="sxs-lookup"><span data-stu-id="5c9ed-119">Used to construct a WebResourceResponse for the WebResourceRequested event.</span></span>

## <span data-ttu-id="5c9ed-120">Members</span><span class="sxs-lookup"><span data-stu-id="5c9ed-120">Members</span></span>

#### <span data-ttu-id="5c9ed-121">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="5c9ed-121">AppendHeader</span></span> 

<span data-ttu-id="5c9ed-122">名前と値が含まれるヘッダー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="5c9ed-122">Appends header line with name and value.</span></span>

> <span data-ttu-id="5c9ed-123">パブリック HRESULT [Appendheader](#appendheader)(LPCWSTR NAME, LPCWSTR value)</span><span class="sxs-lookup"><span data-stu-id="5c9ed-123">public HRESULT [AppendHeader](#appendheader)(LPCWSTR name,LPCWSTR value)</span></span>

#### <span data-ttu-id="5c9ed-124">Contains</span><span class="sxs-lookup"><span data-stu-id="5c9ed-124">Contains</span></span> 

<span data-ttu-id="5c9ed-125">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5c9ed-125">Checks whether the headers contain entries matching the header name.</span></span>

> <span data-ttu-id="5c9ed-126">パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL \* contains)</span><span class="sxs-lookup"><span data-stu-id="5c9ed-126">public HRESULT [Contains](#contains)(LPCWSTR name,BOOL \* contains)</span></span>

#### <span data-ttu-id="5c9ed-127">GetHeader</span><span class="sxs-lookup"><span data-stu-id="5c9ed-127">GetHeader</span></span> 

<span data-ttu-id="5c9ed-128">名前に一致するコレクションの最初のヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="5c9ed-128">Gets the first header value in the collection matching the name.</span></span>

> <span data-ttu-id="5c9ed-129">パブリック HRESULT [GetHeader](#getheader)(LPCWSTR NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="5c9ed-129">public HRESULT [GetHeader](#getheader)(LPCWSTR name,LPWSTR \* value)</span></span>

#### <span data-ttu-id="5c9ed-130">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="5c9ed-130">GetHeaders</span></span> 

<span data-ttu-id="5c9ed-131">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="5c9ed-131">Gets the header values matching the name.</span></span>

> <span data-ttu-id="5c9ed-132">パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name,[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="5c9ed-132">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name,[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="5c9ed-133">GetIterator</span><span class="sxs-lookup"><span data-stu-id="5c9ed-133">GetIterator</span></span> 

<span data-ttu-id="5c9ed-134">応答ヘッダー全体のコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="5c9ed-134">Gets an iterator over the collection of entire response headers.</span></span>

> <span data-ttu-id="5c9ed-135">パブリック HRESULT [Getiterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="5c9ed-135">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

