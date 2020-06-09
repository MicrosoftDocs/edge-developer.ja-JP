---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 508ecacc867330c73132ae7e446b7483ea002f83
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699077"
---
# <span data-ttu-id="3c9a6-104">インターフェイス ICoreWebView2HttpResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="3c9a6-104">interface ICoreWebView2HttpResponseHeaders</span></span> 

```
interface ICoreWebView2HttpResponseHeaders
  : public IUnknown
```

<span data-ttu-id="3c9a6-105">HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="3c9a6-105">HTTP response headers.</span></span>

## <span data-ttu-id="3c9a6-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="3c9a6-106">Summary</span></span>

 <span data-ttu-id="3c9a6-107">Members</span><span class="sxs-lookup"><span data-stu-id="3c9a6-107">Members</span></span>                        | <span data-ttu-id="3c9a6-108">説明</span><span class="sxs-lookup"><span data-stu-id="3c9a6-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3c9a6-109">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="3c9a6-109">AppendHeader</span></span>](#appendheader) | <span data-ttu-id="3c9a6-110">名前と値が含まれるヘッダー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="3c9a6-110">Appends header line with name and value.</span></span>
[<span data-ttu-id="3c9a6-111">Contains</span><span class="sxs-lookup"><span data-stu-id="3c9a6-111">Contains</span></span>](#contains) | <span data-ttu-id="3c9a6-112">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3c9a6-112">Checks whether the headers contain entries matching the header name.</span></span>
[<span data-ttu-id="3c9a6-113">GetHeader</span><span class="sxs-lookup"><span data-stu-id="3c9a6-113">GetHeader</span></span>](#getheader) | <span data-ttu-id="3c9a6-114">名前に一致するコレクションの最初のヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="3c9a6-114">Gets the first header value in the collection matching the name.</span></span>
[<span data-ttu-id="3c9a6-115">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="3c9a6-115">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="3c9a6-116">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="3c9a6-116">Gets the header values matching the name.</span></span>
[<span data-ttu-id="3c9a6-117">GetIterator</span><span class="sxs-lookup"><span data-stu-id="3c9a6-117">GetIterator</span></span>](#getiterator) | <span data-ttu-id="3c9a6-118">応答ヘッダー全体のコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="3c9a6-118">Gets an iterator over the collection of entire response headers.</span></span>

<span data-ttu-id="3c9a6-119">WebResourceRequested イベントの WebResourceResponse を作成するために使われます。</span><span class="sxs-lookup"><span data-stu-id="3c9a6-119">Used to construct a WebResourceResponse for the WebResourceRequested event.</span></span>

## <span data-ttu-id="3c9a6-120">Members</span><span class="sxs-lookup"><span data-stu-id="3c9a6-120">Members</span></span>

#### <span data-ttu-id="3c9a6-121">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="3c9a6-121">AppendHeader</span></span> 

<span data-ttu-id="3c9a6-122">名前と値が含まれるヘッダー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="3c9a6-122">Appends header line with name and value.</span></span>

> <span data-ttu-id="3c9a6-123">パブリック HRESULT [Appendheader](#appendheader)(LPCWSTR NAME, LPCWSTR value)</span><span class="sxs-lookup"><span data-stu-id="3c9a6-123">public HRESULT [AppendHeader](#appendheader)(LPCWSTR name, LPCWSTR value)</span></span>

#### <span data-ttu-id="3c9a6-124">Contains</span><span class="sxs-lookup"><span data-stu-id="3c9a6-124">Contains</span></span> 

<span data-ttu-id="3c9a6-125">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3c9a6-125">Checks whether the headers contain entries matching the header name.</span></span>

> <span data-ttu-id="3c9a6-126">パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL \* contains)</span><span class="sxs-lookup"><span data-stu-id="3c9a6-126">public HRESULT [Contains](#contains)(LPCWSTR name, BOOL \* contains)</span></span>

#### <span data-ttu-id="3c9a6-127">GetHeader</span><span class="sxs-lookup"><span data-stu-id="3c9a6-127">GetHeader</span></span> 

<span data-ttu-id="3c9a6-128">名前に一致するコレクションの最初のヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="3c9a6-128">Gets the first header value in the collection matching the name.</span></span>

> <span data-ttu-id="3c9a6-129">パブリック HRESULT [GetHeader](#getheader)(LPCWSTR NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="3c9a6-129">public HRESULT [GetHeader](#getheader)(LPCWSTR name, LPWSTR \* value)</span></span>

#### <span data-ttu-id="3c9a6-130">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="3c9a6-130">GetHeaders</span></span> 

<span data-ttu-id="3c9a6-131">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="3c9a6-131">Gets the header values matching the name.</span></span>

> <span data-ttu-id="3c9a6-132">パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="3c9a6-132">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="3c9a6-133">GetIterator</span><span class="sxs-lookup"><span data-stu-id="3c9a6-133">GetIterator</span></span> 

<span data-ttu-id="3c9a6-134">応答ヘッダー全体のコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="3c9a6-134">Gets an iterator over the collection of entire response headers.</span></span>

> <span data-ttu-id="3c9a6-135">パブリック HRESULT [Getiterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="3c9a6-135">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

