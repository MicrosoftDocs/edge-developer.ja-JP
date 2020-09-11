---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2HttpResponseHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2HttpResponseHeaders
ms.openlocfilehash: 6278f29f983503916e0015ab4bbac44f79ffe3d9
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011308"
---
# <span data-ttu-id="abf87-104">0.9.579-インターフェイス ICoreWebView2HttpResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="abf87-104">0.9.579 - interface ICoreWebView2HttpResponseHeaders</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2HttpResponseHeaders
  : public IUnknown
```

<span data-ttu-id="abf87-105">HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="abf87-105">HTTP response headers.</span></span>

## <span data-ttu-id="abf87-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="abf87-106">Summary</span></span>

 <span data-ttu-id="abf87-107">Members</span><span class="sxs-lookup"><span data-stu-id="abf87-107">Members</span></span>                        | <span data-ttu-id="abf87-108">説明</span><span class="sxs-lookup"><span data-stu-id="abf87-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="abf87-109">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="abf87-109">AppendHeader</span></span>](#appendheader) | <span data-ttu-id="abf87-110">名前と値が含まれるヘッダー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="abf87-110">Appends header line with name and value.</span></span>
[<span data-ttu-id="abf87-111">Contains</span><span class="sxs-lookup"><span data-stu-id="abf87-111">Contains</span></span>](#contains) | <span data-ttu-id="abf87-112">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="abf87-112">Checks whether the headers contain entries matching the header name.</span></span>
[<span data-ttu-id="abf87-113">GetHeader</span><span class="sxs-lookup"><span data-stu-id="abf87-113">GetHeader</span></span>](#getheader) | <span data-ttu-id="abf87-114">名前に一致するコレクションの最初のヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="abf87-114">Gets the first header value in the collection matching the name.</span></span>
[<span data-ttu-id="abf87-115">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="abf87-115">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="abf87-116">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="abf87-116">Gets the header values matching the name.</span></span>
[<span data-ttu-id="abf87-117">GetIterator</span><span class="sxs-lookup"><span data-stu-id="abf87-117">GetIterator</span></span>](#getiterator) | <span data-ttu-id="abf87-118">応答ヘッダー全体のコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="abf87-118">Gets an iterator over the collection of entire response headers.</span></span>

<span data-ttu-id="abf87-119">WebResourceRequested イベントの WebResourceResponse を作成するために使われます。</span><span class="sxs-lookup"><span data-stu-id="abf87-119">Used to construct a WebResourceResponse for the WebResourceRequested event.</span></span>

## <span data-ttu-id="abf87-120">Members</span><span class="sxs-lookup"><span data-stu-id="abf87-120">Members</span></span>

#### <span data-ttu-id="abf87-121">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="abf87-121">AppendHeader</span></span> 

<span data-ttu-id="abf87-122">名前と値が含まれるヘッダー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="abf87-122">Appends header line with name and value.</span></span>

> <span data-ttu-id="abf87-123">パブリック HRESULT [Appendheader](#appendheader)(LPCWSTR NAME, LPCWSTR value)</span><span class="sxs-lookup"><span data-stu-id="abf87-123">public HRESULT [AppendHeader](#appendheader)(LPCWSTR name, LPCWSTR value)</span></span>

#### <span data-ttu-id="abf87-124">Contains</span><span class="sxs-lookup"><span data-stu-id="abf87-124">Contains</span></span> 

<span data-ttu-id="abf87-125">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="abf87-125">Checks whether the headers contain entries matching the header name.</span></span>

> <span data-ttu-id="abf87-126">パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL \* contains)</span><span class="sxs-lookup"><span data-stu-id="abf87-126">public HRESULT [Contains](#contains)(LPCWSTR name, BOOL \* contains)</span></span>

#### <span data-ttu-id="abf87-127">GetHeader</span><span class="sxs-lookup"><span data-stu-id="abf87-127">GetHeader</span></span> 

<span data-ttu-id="abf87-128">名前に一致するコレクションの最初のヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="abf87-128">Gets the first header value in the collection matching the name.</span></span>

> <span data-ttu-id="abf87-129">パブリック HRESULT [GetHeader](#getheader)(LPCWSTR NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="abf87-129">public HRESULT [GetHeader](#getheader)(LPCWSTR name, LPWSTR \* value)</span></span>

#### <span data-ttu-id="abf87-130">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="abf87-130">GetHeaders</span></span> 

<span data-ttu-id="abf87-131">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="abf87-131">Gets the header values matching the name.</span></span>

> <span data-ttu-id="abf87-132">パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="abf87-132">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="abf87-133">GetIterator</span><span class="sxs-lookup"><span data-stu-id="abf87-133">GetIterator</span></span> 

<span data-ttu-id="abf87-134">応答ヘッダー全体のコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="abf87-134">Gets an iterator over the collection of entire response headers.</span></span>

> <span data-ttu-id="abf87-135">パブリック HRESULT [Getiterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="abf87-135">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

