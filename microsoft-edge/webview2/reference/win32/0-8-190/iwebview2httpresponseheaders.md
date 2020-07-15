---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2HttpResponseHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 48a04ea60dff4cf9b6b52377927ee9085fb8bea2
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878436"
---
# <span data-ttu-id="a9ee0-104">0.8.355-インターフェイス IWebView2HttpResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="a9ee0-104">0.8.355 - interface IWebView2HttpResponseHeaders</span></span> 

> [!NOTE]
> <span data-ttu-id="a9ee0-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a9ee0-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="a9ee0-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9ee0-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2HttpResponseHeaders
  : public IUnknown
```

<span data-ttu-id="a9ee0-107">HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="a9ee0-107">HTTP response headers.</span></span>

## <span data-ttu-id="a9ee0-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="a9ee0-108">Summary</span></span>

 <span data-ttu-id="a9ee0-109">Members</span><span class="sxs-lookup"><span data-stu-id="a9ee0-109">Members</span></span>                        | <span data-ttu-id="a9ee0-110">説明</span><span class="sxs-lookup"><span data-stu-id="a9ee0-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a9ee0-111">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="a9ee0-111">AppendHeader</span></span>](#appendheader) | <span data-ttu-id="a9ee0-112">名前と値が含まれるヘッダー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="a9ee0-112">Appends header line with name and value.</span></span>
[<span data-ttu-id="a9ee0-113">Contains</span><span class="sxs-lookup"><span data-stu-id="a9ee0-113">Contains</span></span>](#contains) | <span data-ttu-id="a9ee0-114">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a9ee0-114">Checks whether the headers contain entries matching the header name.</span></span>
[<span data-ttu-id="a9ee0-115">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="a9ee0-115">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="a9ee0-116">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="a9ee0-116">Gets the header values matching the name.</span></span>
[<span data-ttu-id="a9ee0-117">GetIterator</span><span class="sxs-lookup"><span data-stu-id="a9ee0-117">GetIterator</span></span>](#getiterator) | <span data-ttu-id="a9ee0-118">応答ヘッダー全体のコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="a9ee0-118">Gets an iterator over the collection of entire response headers.</span></span>

<span data-ttu-id="a9ee0-119">WebResourceRequested イベントの WebResourceResponse を作成するために使われます。</span><span class="sxs-lookup"><span data-stu-id="a9ee0-119">Used to construct a WebResourceResponse for the WebResourceRequested event.</span></span>

## <span data-ttu-id="a9ee0-120">Members</span><span class="sxs-lookup"><span data-stu-id="a9ee0-120">Members</span></span>

#### <span data-ttu-id="a9ee0-121">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="a9ee0-121">AppendHeader</span></span> 

<span data-ttu-id="a9ee0-122">名前と値が含まれるヘッダー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="a9ee0-122">Appends header line with name and value.</span></span>

> <span data-ttu-id="a9ee0-123">パブリック HRESULT [Appendheader](#appendheader)(LPCWSTR NAME, LPCWSTR value)</span><span class="sxs-lookup"><span data-stu-id="a9ee0-123">public HRESULT [AppendHeader](#appendheader)(LPCWSTR name,LPCWSTR value)</span></span>

#### <span data-ttu-id="a9ee0-124">Contains</span><span class="sxs-lookup"><span data-stu-id="a9ee0-124">Contains</span></span> 

<span data-ttu-id="a9ee0-125">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a9ee0-125">Checks whether the headers contain entries matching the header name.</span></span>

> <span data-ttu-id="a9ee0-126">パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL \* contains)</span><span class="sxs-lookup"><span data-stu-id="a9ee0-126">public HRESULT [Contains](#contains)(LPCWSTR name,BOOL \* contains)</span></span>

#### <span data-ttu-id="a9ee0-127">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="a9ee0-127">GetHeaders</span></span> 

<span data-ttu-id="a9ee0-128">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="a9ee0-128">Gets the header values matching the name.</span></span>

> <span data-ttu-id="a9ee0-129">パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name,[IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="a9ee0-129">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name,[IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="a9ee0-130">GetIterator</span><span class="sxs-lookup"><span data-stu-id="a9ee0-130">GetIterator</span></span> 

<span data-ttu-id="a9ee0-131">応答ヘッダー全体のコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="a9ee0-131">Gets an iterator over the collection of entire response headers.</span></span>

> <span data-ttu-id="a9ee0-132">パブリック HRESULT [Getiterator](#getiterator)([IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="a9ee0-132">public HRESULT [GetIterator](#getiterator)([IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

