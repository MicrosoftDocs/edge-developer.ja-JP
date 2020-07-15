---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2HttpResponseHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 356f8bfc235e522ef5e976baf61f8c9017766a3d
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880536"
---
# <span data-ttu-id="aadd3-104">0.9.515-インターフェイス ICoreWebView2HttpResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="aadd3-104">0.9.515 - interface ICoreWebView2HttpResponseHeaders</span></span> 

> [!NOTE]
> <span data-ttu-id="aadd3-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aadd3-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="aadd3-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aadd3-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2HttpResponseHeaders
  : public IUnknown
```

<span data-ttu-id="aadd3-107">HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="aadd3-107">HTTP response headers.</span></span>

## <span data-ttu-id="aadd3-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="aadd3-108">Summary</span></span>

 <span data-ttu-id="aadd3-109">Members</span><span class="sxs-lookup"><span data-stu-id="aadd3-109">Members</span></span>                        | <span data-ttu-id="aadd3-110">説明</span><span class="sxs-lookup"><span data-stu-id="aadd3-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="aadd3-111">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="aadd3-111">AppendHeader</span></span>](#appendheader) | <span data-ttu-id="aadd3-112">名前と値が含まれるヘッダー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="aadd3-112">Appends header line with name and value.</span></span>
[<span data-ttu-id="aadd3-113">Contains</span><span class="sxs-lookup"><span data-stu-id="aadd3-113">Contains</span></span>](#contains) | <span data-ttu-id="aadd3-114">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="aadd3-114">Checks whether the headers contain entries matching the header name.</span></span>
[<span data-ttu-id="aadd3-115">GetHeader</span><span class="sxs-lookup"><span data-stu-id="aadd3-115">GetHeader</span></span>](#getheader) | <span data-ttu-id="aadd3-116">名前に一致するコレクションの最初のヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="aadd3-116">Gets the first header value in the collection matching the name.</span></span>
[<span data-ttu-id="aadd3-117">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="aadd3-117">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="aadd3-118">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="aadd3-118">Gets the header values matching the name.</span></span>
[<span data-ttu-id="aadd3-119">GetIterator</span><span class="sxs-lookup"><span data-stu-id="aadd3-119">GetIterator</span></span>](#getiterator) | <span data-ttu-id="aadd3-120">応答ヘッダー全体のコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="aadd3-120">Gets an iterator over the collection of entire response headers.</span></span>

<span data-ttu-id="aadd3-121">WebResourceRequested イベントの WebResourceResponse を作成するために使われます。</span><span class="sxs-lookup"><span data-stu-id="aadd3-121">Used to construct a WebResourceResponse for the WebResourceRequested event.</span></span>

## <span data-ttu-id="aadd3-122">Members</span><span class="sxs-lookup"><span data-stu-id="aadd3-122">Members</span></span>

#### <span data-ttu-id="aadd3-123">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="aadd3-123">AppendHeader</span></span> 

<span data-ttu-id="aadd3-124">名前と値が含まれるヘッダー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="aadd3-124">Appends header line with name and value.</span></span>

> <span data-ttu-id="aadd3-125">パブリック HRESULT [Appendheader](#appendheader)(LPCWSTR NAME, LPCWSTR value)</span><span class="sxs-lookup"><span data-stu-id="aadd3-125">public HRESULT [AppendHeader](#appendheader)(LPCWSTR name, LPCWSTR value)</span></span>

#### <span data-ttu-id="aadd3-126">Contains</span><span class="sxs-lookup"><span data-stu-id="aadd3-126">Contains</span></span> 

<span data-ttu-id="aadd3-127">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="aadd3-127">Checks whether the headers contain entries matching the header name.</span></span>

> <span data-ttu-id="aadd3-128">パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL \* contains)</span><span class="sxs-lookup"><span data-stu-id="aadd3-128">public HRESULT [Contains](#contains)(LPCWSTR name, BOOL \* contains)</span></span>

#### <span data-ttu-id="aadd3-129">GetHeader</span><span class="sxs-lookup"><span data-stu-id="aadd3-129">GetHeader</span></span> 

<span data-ttu-id="aadd3-130">名前に一致するコレクションの最初のヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="aadd3-130">Gets the first header value in the collection matching the name.</span></span>

> <span data-ttu-id="aadd3-131">パブリック HRESULT [GetHeader](#getheader)(LPCWSTR NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="aadd3-131">public HRESULT [GetHeader](#getheader)(LPCWSTR name, LPWSTR \* value)</span></span>

#### <span data-ttu-id="aadd3-132">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="aadd3-132">GetHeaders</span></span> 

<span data-ttu-id="aadd3-133">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="aadd3-133">Gets the header values matching the name.</span></span>

> <span data-ttu-id="aadd3-134">パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="aadd3-134">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="aadd3-135">GetIterator</span><span class="sxs-lookup"><span data-stu-id="aadd3-135">GetIterator</span></span> 

<span data-ttu-id="aadd3-136">応答ヘッダー全体のコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="aadd3-136">Gets an iterator over the collection of entire response headers.</span></span>

> <span data-ttu-id="aadd3-137">パブリック HRESULT [Getiterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="aadd3-137">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

