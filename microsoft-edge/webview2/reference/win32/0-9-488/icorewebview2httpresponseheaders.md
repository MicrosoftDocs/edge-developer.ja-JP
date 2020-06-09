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
ms.openlocfilehash: 63044cae80aebfb1e759070ec797673b0c9378d2
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697253"
---
# <span data-ttu-id="d0947-104">インターフェイス ICoreWebView2HttpResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="d0947-104">interface ICoreWebView2HttpResponseHeaders</span></span> 

> [!NOTE]
> <span data-ttu-id="d0947-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d0947-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="d0947-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0947-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2HttpResponseHeaders
  : public IUnknown
```

<span data-ttu-id="d0947-107">HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="d0947-107">HTTP response headers.</span></span>

## <span data-ttu-id="d0947-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="d0947-108">Summary</span></span>

 <span data-ttu-id="d0947-109">Members</span><span class="sxs-lookup"><span data-stu-id="d0947-109">Members</span></span>                        | <span data-ttu-id="d0947-110">説明</span><span class="sxs-lookup"><span data-stu-id="d0947-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d0947-111">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="d0947-111">AppendHeader</span></span>](#appendheader) | <span data-ttu-id="d0947-112">名前と値が含まれるヘッダー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="d0947-112">Appends header line with name and value.</span></span>
[<span data-ttu-id="d0947-113">Contains</span><span class="sxs-lookup"><span data-stu-id="d0947-113">Contains</span></span>](#contains) | <span data-ttu-id="d0947-114">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0947-114">Checks whether the headers contain entries matching the header name.</span></span>
[<span data-ttu-id="d0947-115">GetHeader</span><span class="sxs-lookup"><span data-stu-id="d0947-115">GetHeader</span></span>](#getheader) | <span data-ttu-id="d0947-116">名前に一致するコレクションの最初のヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="d0947-116">Gets the first header value in the collection matching the name.</span></span>
[<span data-ttu-id="d0947-117">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="d0947-117">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="d0947-118">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="d0947-118">Gets the header values matching the name.</span></span>
[<span data-ttu-id="d0947-119">GetIterator</span><span class="sxs-lookup"><span data-stu-id="d0947-119">GetIterator</span></span>](#getiterator) | <span data-ttu-id="d0947-120">応答ヘッダー全体のコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="d0947-120">Gets an iterator over the collection of entire response headers.</span></span>

<span data-ttu-id="d0947-121">WebResourceRequested イベントの WebResourceResponse を作成するために使われます。</span><span class="sxs-lookup"><span data-stu-id="d0947-121">Used to construct a WebResourceResponse for the WebResourceRequested event.</span></span>

## <span data-ttu-id="d0947-122">Members</span><span class="sxs-lookup"><span data-stu-id="d0947-122">Members</span></span>

#### <span data-ttu-id="d0947-123">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="d0947-123">AppendHeader</span></span> 

<span data-ttu-id="d0947-124">名前と値が含まれるヘッダー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="d0947-124">Appends header line with name and value.</span></span>

> <span data-ttu-id="d0947-125">パブリック HRESULT [Appendheader](#appendheader)(LPCWSTR NAME, LPCWSTR value)</span><span class="sxs-lookup"><span data-stu-id="d0947-125">public HRESULT [AppendHeader](#appendheader)(LPCWSTR name, LPCWSTR value)</span></span>

#### <span data-ttu-id="d0947-126">Contains</span><span class="sxs-lookup"><span data-stu-id="d0947-126">Contains</span></span> 

<span data-ttu-id="d0947-127">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0947-127">Checks whether the headers contain entries matching the header name.</span></span>

> <span data-ttu-id="d0947-128">パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL \* contains)</span><span class="sxs-lookup"><span data-stu-id="d0947-128">public HRESULT [Contains](#contains)(LPCWSTR name, BOOL \* contains)</span></span>

#### <span data-ttu-id="d0947-129">GetHeader</span><span class="sxs-lookup"><span data-stu-id="d0947-129">GetHeader</span></span> 

<span data-ttu-id="d0947-130">名前に一致するコレクションの最初のヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="d0947-130">Gets the first header value in the collection matching the name.</span></span>

> <span data-ttu-id="d0947-131">パブリック HRESULT [GetHeader](#getheader)(LPCWSTR NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="d0947-131">public HRESULT [GetHeader](#getheader)(LPCWSTR name, LPWSTR \* value)</span></span>

#### <span data-ttu-id="d0947-132">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="d0947-132">GetHeaders</span></span> 

<span data-ttu-id="d0947-133">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="d0947-133">Gets the header values matching the name.</span></span>

> <span data-ttu-id="d0947-134">パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="d0947-134">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="d0947-135">GetIterator</span><span class="sxs-lookup"><span data-stu-id="d0947-135">GetIterator</span></span> 

<span data-ttu-id="d0947-136">応答ヘッダー全体のコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="d0947-136">Gets an iterator over the collection of entire response headers.</span></span>

> <span data-ttu-id="d0947-137">パブリック HRESULT [Getiterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="d0947-137">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

