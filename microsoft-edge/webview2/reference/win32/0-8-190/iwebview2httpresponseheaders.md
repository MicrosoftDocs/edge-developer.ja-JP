---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 0f3564fa96bc1c13527cbf3b26ce92114d44eae4
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654368"
---
# <span data-ttu-id="75ee6-104">インターフェイス IWebView2HttpResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="75ee6-104">interface IWebView2HttpResponseHeaders</span></span> 

> [!NOTE]
> <span data-ttu-id="75ee6-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="75ee6-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="75ee6-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75ee6-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2HttpResponseHeaders
  : public IUnknown
```

<span data-ttu-id="75ee6-107">HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="75ee6-107">HTTP response headers.</span></span>

## <span data-ttu-id="75ee6-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="75ee6-108">Summary</span></span>

 <span data-ttu-id="75ee6-109">Members</span><span class="sxs-lookup"><span data-stu-id="75ee6-109">Members</span></span>                        | <span data-ttu-id="75ee6-110">説明</span><span class="sxs-lookup"><span data-stu-id="75ee6-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="75ee6-111">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="75ee6-111">AppendHeader</span></span>](#appendheader) | <span data-ttu-id="75ee6-112">名前と値が含まれるヘッダー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="75ee6-112">Appends header line with name and value.</span></span>
[<span data-ttu-id="75ee6-113">Contains</span><span class="sxs-lookup"><span data-stu-id="75ee6-113">Contains</span></span>](#contains) | <span data-ttu-id="75ee6-114">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="75ee6-114">Checks whether the headers contain entries matching the header name.</span></span>
[<span data-ttu-id="75ee6-115">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="75ee6-115">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="75ee6-116">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="75ee6-116">Gets the header values matching the name.</span></span>
[<span data-ttu-id="75ee6-117">GetIterator</span><span class="sxs-lookup"><span data-stu-id="75ee6-117">GetIterator</span></span>](#getiterator) | <span data-ttu-id="75ee6-118">応答ヘッダー全体のコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="75ee6-118">Gets an iterator over the collection of entire response headers.</span></span>

<span data-ttu-id="75ee6-119">WebResourceRequested イベントの WebResourceResponse を作成するために使われます。</span><span class="sxs-lookup"><span data-stu-id="75ee6-119">Used to construct a WebResourceResponse for the WebResourceRequested event.</span></span>

## <span data-ttu-id="75ee6-120">Members</span><span class="sxs-lookup"><span data-stu-id="75ee6-120">Members</span></span>

#### <span data-ttu-id="75ee6-121">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="75ee6-121">AppendHeader</span></span> 

<span data-ttu-id="75ee6-122">名前と値が含まれるヘッダー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="75ee6-122">Appends header line with name and value.</span></span>

> <span data-ttu-id="75ee6-123">パブリック HRESULT [Appendheader](#appendheader)(LPCWSTR NAME, LPCWSTR value)</span><span class="sxs-lookup"><span data-stu-id="75ee6-123">public HRESULT [AppendHeader](#appendheader)(LPCWSTR name,LPCWSTR value)</span></span>

#### <span data-ttu-id="75ee6-124">Contains</span><span class="sxs-lookup"><span data-stu-id="75ee6-124">Contains</span></span> 

<span data-ttu-id="75ee6-125">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="75ee6-125">Checks whether the headers contain entries matching the header name.</span></span>

> <span data-ttu-id="75ee6-126">パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL \* contains)</span><span class="sxs-lookup"><span data-stu-id="75ee6-126">public HRESULT [Contains](#contains)(LPCWSTR name,BOOL \* contains)</span></span>

#### <span data-ttu-id="75ee6-127">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="75ee6-127">GetHeaders</span></span> 

<span data-ttu-id="75ee6-128">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="75ee6-128">Gets the header values matching the name.</span></span>

> <span data-ttu-id="75ee6-129">パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name,[IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="75ee6-129">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name,[IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="75ee6-130">GetIterator</span><span class="sxs-lookup"><span data-stu-id="75ee6-130">GetIterator</span></span> 

<span data-ttu-id="75ee6-131">応答ヘッダー全体のコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="75ee6-131">Gets an iterator over the collection of entire response headers.</span></span>

> <span data-ttu-id="75ee6-132">パブリック HRESULT [Getiterator](#getiterator)([IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="75ee6-132">public HRESULT [GetIterator](#getiterator)([IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

