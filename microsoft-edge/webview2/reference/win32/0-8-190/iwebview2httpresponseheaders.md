---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2HttpResponseHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 077c85b2458c2cf843c4d2f0548d17ec01ba4751
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885962"
---
# <span data-ttu-id="0eacc-104">0.8.355-インターフェイス IWebView2HttpResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="0eacc-104">0.8.355 - interface IWebView2HttpResponseHeaders</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2HttpResponseHeaders
  : public IUnknown
```

<span data-ttu-id="0eacc-105">HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="0eacc-105">HTTP response headers.</span></span>

## <span data-ttu-id="0eacc-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="0eacc-106">Summary</span></span>

 <span data-ttu-id="0eacc-107">Members</span><span class="sxs-lookup"><span data-stu-id="0eacc-107">Members</span></span>                        | <span data-ttu-id="0eacc-108">説明</span><span class="sxs-lookup"><span data-stu-id="0eacc-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0eacc-109">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="0eacc-109">AppendHeader</span></span>](#appendheader) | <span data-ttu-id="0eacc-110">名前と値が含まれるヘッダー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="0eacc-110">Appends header line with name and value.</span></span>
[<span data-ttu-id="0eacc-111">Contains</span><span class="sxs-lookup"><span data-stu-id="0eacc-111">Contains</span></span>](#contains) | <span data-ttu-id="0eacc-112">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0eacc-112">Checks whether the headers contain entries matching the header name.</span></span>
[<span data-ttu-id="0eacc-113">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="0eacc-113">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="0eacc-114">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="0eacc-114">Gets the header values matching the name.</span></span>
[<span data-ttu-id="0eacc-115">GetIterator</span><span class="sxs-lookup"><span data-stu-id="0eacc-115">GetIterator</span></span>](#getiterator) | <span data-ttu-id="0eacc-116">応答ヘッダー全体のコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="0eacc-116">Gets an iterator over the collection of entire response headers.</span></span>

<span data-ttu-id="0eacc-117">WebResourceRequested イベントの WebResourceResponse を作成するために使われます。</span><span class="sxs-lookup"><span data-stu-id="0eacc-117">Used to construct a WebResourceResponse for the WebResourceRequested event.</span></span>

## <span data-ttu-id="0eacc-118">Members</span><span class="sxs-lookup"><span data-stu-id="0eacc-118">Members</span></span>

#### <span data-ttu-id="0eacc-119">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="0eacc-119">AppendHeader</span></span> 

<span data-ttu-id="0eacc-120">名前と値が含まれるヘッダー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="0eacc-120">Appends header line with name and value.</span></span>

> <span data-ttu-id="0eacc-121">パブリック HRESULT [Appendheader](#appendheader)(LPCWSTR NAME, LPCWSTR value)</span><span class="sxs-lookup"><span data-stu-id="0eacc-121">public HRESULT [AppendHeader](#appendheader)(LPCWSTR name,LPCWSTR value)</span></span>

#### <span data-ttu-id="0eacc-122">Contains</span><span class="sxs-lookup"><span data-stu-id="0eacc-122">Contains</span></span> 

<span data-ttu-id="0eacc-123">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0eacc-123">Checks whether the headers contain entries matching the header name.</span></span>

> <span data-ttu-id="0eacc-124">パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL \* contains)</span><span class="sxs-lookup"><span data-stu-id="0eacc-124">public HRESULT [Contains](#contains)(LPCWSTR name,BOOL \* contains)</span></span>

#### <span data-ttu-id="0eacc-125">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="0eacc-125">GetHeaders</span></span> 

<span data-ttu-id="0eacc-126">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="0eacc-126">Gets the header values matching the name.</span></span>

> <span data-ttu-id="0eacc-127">パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name,[IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="0eacc-127">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name,[IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="0eacc-128">GetIterator</span><span class="sxs-lookup"><span data-stu-id="0eacc-128">GetIterator</span></span> 

<span data-ttu-id="0eacc-129">応答ヘッダー全体のコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="0eacc-129">Gets an iterator over the collection of entire response headers.</span></span>

> <span data-ttu-id="0eacc-130">パブリック HRESULT [Getiterator](#getiterator)([IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="0eacc-130">public HRESULT [GetIterator](#getiterator)([IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

