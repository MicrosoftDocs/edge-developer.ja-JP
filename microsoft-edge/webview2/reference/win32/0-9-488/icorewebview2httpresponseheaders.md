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
ms.openlocfilehash: fe03c3ab6d951ecd54bd76cd7abc89de637496ea
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654390"
---
# <span data-ttu-id="54eac-104">インターフェイス ICoreWebView2HttpResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="54eac-104">interface ICoreWebView2HttpResponseHeaders</span></span> 

```
interface ICoreWebView2HttpResponseHeaders
  : public IUnknown
```

<span data-ttu-id="54eac-105">HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="54eac-105">HTTP response headers.</span></span>

## <span data-ttu-id="54eac-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="54eac-106">Summary</span></span>

 <span data-ttu-id="54eac-107">Members</span><span class="sxs-lookup"><span data-stu-id="54eac-107">Members</span></span>                        | <span data-ttu-id="54eac-108">説明</span><span class="sxs-lookup"><span data-stu-id="54eac-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="54eac-109">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="54eac-109">AppendHeader</span></span>](#appendheader) | <span data-ttu-id="54eac-110">名前と値が含まれるヘッダー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="54eac-110">Appends header line with name and value.</span></span>
[<span data-ttu-id="54eac-111">Contains</span><span class="sxs-lookup"><span data-stu-id="54eac-111">Contains</span></span>](#contains) | <span data-ttu-id="54eac-112">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="54eac-112">Checks whether the headers contain entries matching the header name.</span></span>
[<span data-ttu-id="54eac-113">GetHeader</span><span class="sxs-lookup"><span data-stu-id="54eac-113">GetHeader</span></span>](#getheader) | <span data-ttu-id="54eac-114">名前に一致するコレクションの最初のヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="54eac-114">Gets the first header value in the collection matching the name.</span></span>
[<span data-ttu-id="54eac-115">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="54eac-115">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="54eac-116">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="54eac-116">Gets the header values matching the name.</span></span>
[<span data-ttu-id="54eac-117">GetIterator</span><span class="sxs-lookup"><span data-stu-id="54eac-117">GetIterator</span></span>](#getiterator) | <span data-ttu-id="54eac-118">応答ヘッダー全体のコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="54eac-118">Gets an iterator over the collection of entire response headers.</span></span>

<span data-ttu-id="54eac-119">WebResourceRequested イベントの WebResourceResponse を作成するために使われます。</span><span class="sxs-lookup"><span data-stu-id="54eac-119">Used to construct a WebResourceResponse for the WebResourceRequested event.</span></span>

## <span data-ttu-id="54eac-120">Members</span><span class="sxs-lookup"><span data-stu-id="54eac-120">Members</span></span>

#### <span data-ttu-id="54eac-121">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="54eac-121">AppendHeader</span></span> 

<span data-ttu-id="54eac-122">名前と値が含まれるヘッダー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="54eac-122">Appends header line with name and value.</span></span>

> <span data-ttu-id="54eac-123">パブリック HRESULT [Appendheader](#appendheader)(LPCWSTR NAME, LPCWSTR value)</span><span class="sxs-lookup"><span data-stu-id="54eac-123">public HRESULT [AppendHeader](#appendheader)(LPCWSTR name, LPCWSTR value)</span></span>

#### <span data-ttu-id="54eac-124">Contains</span><span class="sxs-lookup"><span data-stu-id="54eac-124">Contains</span></span> 

<span data-ttu-id="54eac-125">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="54eac-125">Checks whether the headers contain entries matching the header name.</span></span>

> <span data-ttu-id="54eac-126">パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL \* contains)</span><span class="sxs-lookup"><span data-stu-id="54eac-126">public HRESULT [Contains](#contains)(LPCWSTR name, BOOL \* contains)</span></span>

#### <span data-ttu-id="54eac-127">GetHeader</span><span class="sxs-lookup"><span data-stu-id="54eac-127">GetHeader</span></span> 

<span data-ttu-id="54eac-128">名前に一致するコレクションの最初のヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="54eac-128">Gets the first header value in the collection matching the name.</span></span>

> <span data-ttu-id="54eac-129">パブリック HRESULT [GetHeader](#getheader)(LPCWSTR NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="54eac-129">public HRESULT [GetHeader](#getheader)(LPCWSTR name, LPWSTR \* value)</span></span>

#### <span data-ttu-id="54eac-130">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="54eac-130">GetHeaders</span></span> 

<span data-ttu-id="54eac-131">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="54eac-131">Gets the header values matching the name.</span></span>

> <span data-ttu-id="54eac-132">パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="54eac-132">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="54eac-133">GetIterator</span><span class="sxs-lookup"><span data-stu-id="54eac-133">GetIterator</span></span> 

<span data-ttu-id="54eac-134">応答ヘッダー全体のコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="54eac-134">Gets an iterator over the collection of entire response headers.</span></span>

> <span data-ttu-id="54eac-135">パブリック HRESULT [Getiterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="54eac-135">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

