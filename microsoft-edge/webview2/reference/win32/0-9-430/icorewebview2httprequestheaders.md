---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2HttpRequestHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: a67c5c267178ea873cd12d8a22dea7409b260d52
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880998"
---
# <span data-ttu-id="86df8-104">0.9.430-インターフェイス ICoreWebView2HttpRequestHeaders</span><span class="sxs-lookup"><span data-stu-id="86df8-104">0.9.430 - interface ICoreWebView2HttpRequestHeaders</span></span> 

> [!NOTE]
> <span data-ttu-id="86df8-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="86df8-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="86df8-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86df8-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2HttpRequestHeaders
  : public IUnknown
```

<span data-ttu-id="86df8-107">HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="86df8-107">HTTP request headers.</span></span>

## <span data-ttu-id="86df8-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="86df8-108">Summary</span></span>

 <span data-ttu-id="86df8-109">Members</span><span class="sxs-lookup"><span data-stu-id="86df8-109">Members</span></span>                        | <span data-ttu-id="86df8-110">説明</span><span class="sxs-lookup"><span data-stu-id="86df8-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="86df8-111">GetHeader</span><span class="sxs-lookup"><span data-stu-id="86df8-111">GetHeader</span></span>](#getheader) | <span data-ttu-id="86df8-112">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="86df8-112">Gets the header value matching the name.</span></span>
[<span data-ttu-id="86df8-113">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="86df8-113">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="86df8-114">名前に一致するヘッダー値をイテレータを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="86df8-114">Gets the header value matching the name via an iterator.</span></span>
[<span data-ttu-id="86df8-115">Contains</span><span class="sxs-lookup"><span data-stu-id="86df8-115">Contains</span></span>](#contains) | <span data-ttu-id="86df8-116">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="86df8-116">Checks whether the headers contain an entry matching the header name.</span></span>
[<span data-ttu-id="86df8-117">SetHeader</span><span class="sxs-lookup"><span data-stu-id="86df8-117">SetHeader</span></span>](#setheader) | <span data-ttu-id="86df8-118">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="86df8-118">Adds or updates header that matches the name.</span></span>
[<span data-ttu-id="86df8-119">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="86df8-119">RemoveHeader</span></span>](#removeheader) | <span data-ttu-id="86df8-120">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="86df8-120">Removes header that matches the name.</span></span>
[<span data-ttu-id="86df8-121">GetIterator</span><span class="sxs-lookup"><span data-stu-id="86df8-121">GetIterator</span></span>](#getiterator) | <span data-ttu-id="86df8-122">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="86df8-122">Gets an iterator over the collection of request headers.</span></span>

<span data-ttu-id="86df8-123">WebResourceRequested イベントと NavigationStarting イベントの HTTP 要求を検査するために使われます。</span><span class="sxs-lookup"><span data-stu-id="86df8-123">Used to inspect the HTTP request on WebResourceRequested event and NavigationStarting event.</span></span> <span data-ttu-id="86df8-124">ただし、WebResourceRequested イベントから HTTP 要求ヘッダーを変更することはできますが、NavigationStarting イベントからは変更できません。</span><span class="sxs-lookup"><span data-stu-id="86df8-124">Note, you can modify the HTTP request headers from a WebResourceRequested event, but not from a NavigationStarting event.</span></span>

## <span data-ttu-id="86df8-125">Members</span><span class="sxs-lookup"><span data-stu-id="86df8-125">Members</span></span>

#### <span data-ttu-id="86df8-126">GetHeader</span><span class="sxs-lookup"><span data-stu-id="86df8-126">GetHeader</span></span> 

<span data-ttu-id="86df8-127">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="86df8-127">Gets the header value matching the name.</span></span>

> <span data-ttu-id="86df8-128">パブリック HRESULT [GetHeader](#getheader)(LPCWSTR NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="86df8-128">public HRESULT [GetHeader](#getheader)(LPCWSTR name,LPWSTR \* value)</span></span>

#### <span data-ttu-id="86df8-129">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="86df8-129">GetHeaders</span></span> 

<span data-ttu-id="86df8-130">名前に一致するヘッダー値をイテレータを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="86df8-130">Gets the header value matching the name via an iterator.</span></span>

> <span data-ttu-id="86df8-131">パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name,[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="86df8-131">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name,[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="86df8-132">Contains</span><span class="sxs-lookup"><span data-stu-id="86df8-132">Contains</span></span> 

<span data-ttu-id="86df8-133">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="86df8-133">Checks whether the headers contain an entry matching the header name.</span></span>

> <span data-ttu-id="86df8-134">パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL \* contains)</span><span class="sxs-lookup"><span data-stu-id="86df8-134">public HRESULT [Contains](#contains)(LPCWSTR name,BOOL \* contains)</span></span>

#### <span data-ttu-id="86df8-135">SetHeader</span><span class="sxs-lookup"><span data-stu-id="86df8-135">SetHeader</span></span> 

<span data-ttu-id="86df8-136">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="86df8-136">Adds or updates header that matches the name.</span></span>

> <span data-ttu-id="86df8-137">パブリック HRESULT [SetHeader](#setheader)(LPCWSTR NAME, LPCWSTR value)</span><span class="sxs-lookup"><span data-stu-id="86df8-137">public HRESULT [SetHeader](#setheader)(LPCWSTR name,LPCWSTR value)</span></span>

#### <span data-ttu-id="86df8-138">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="86df8-138">RemoveHeader</span></span> 

<span data-ttu-id="86df8-139">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="86df8-139">Removes header that matches the name.</span></span>

> <span data-ttu-id="86df8-140">パブリック HRESULT [Removeheader](#removeheader)(LPCWSTR name)</span><span class="sxs-lookup"><span data-stu-id="86df8-140">public HRESULT [RemoveHeader](#removeheader)(LPCWSTR name)</span></span>

#### <span data-ttu-id="86df8-141">GetIterator</span><span class="sxs-lookup"><span data-stu-id="86df8-141">GetIterator</span></span> 

<span data-ttu-id="86df8-142">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="86df8-142">Gets an iterator over the collection of request headers.</span></span>

> <span data-ttu-id="86df8-143">パブリック HRESULT [Getiterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="86df8-143">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

