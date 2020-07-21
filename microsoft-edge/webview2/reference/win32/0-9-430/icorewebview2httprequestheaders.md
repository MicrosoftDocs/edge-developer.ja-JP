---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2HttpRequestHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 04a8bf376ad7649021c4ab1555c3090cce5b52fb
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885612"
---
# <span data-ttu-id="50449-104">0.9.430-インターフェイス ICoreWebView2HttpRequestHeaders</span><span class="sxs-lookup"><span data-stu-id="50449-104">0.9.430 - interface ICoreWebView2HttpRequestHeaders</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2HttpRequestHeaders
  : public IUnknown
```

<span data-ttu-id="50449-105">HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="50449-105">HTTP request headers.</span></span>

## <span data-ttu-id="50449-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="50449-106">Summary</span></span>

 <span data-ttu-id="50449-107">Members</span><span class="sxs-lookup"><span data-stu-id="50449-107">Members</span></span>                        | <span data-ttu-id="50449-108">説明</span><span class="sxs-lookup"><span data-stu-id="50449-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="50449-109">GetHeader</span><span class="sxs-lookup"><span data-stu-id="50449-109">GetHeader</span></span>](#getheader) | <span data-ttu-id="50449-110">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="50449-110">Gets the header value matching the name.</span></span>
[<span data-ttu-id="50449-111">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="50449-111">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="50449-112">名前に一致するヘッダー値をイテレータを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="50449-112">Gets the header value matching the name via an iterator.</span></span>
[<span data-ttu-id="50449-113">Contains</span><span class="sxs-lookup"><span data-stu-id="50449-113">Contains</span></span>](#contains) | <span data-ttu-id="50449-114">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="50449-114">Checks whether the headers contain an entry matching the header name.</span></span>
[<span data-ttu-id="50449-115">SetHeader</span><span class="sxs-lookup"><span data-stu-id="50449-115">SetHeader</span></span>](#setheader) | <span data-ttu-id="50449-116">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="50449-116">Adds or updates header that matches the name.</span></span>
[<span data-ttu-id="50449-117">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="50449-117">RemoveHeader</span></span>](#removeheader) | <span data-ttu-id="50449-118">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="50449-118">Removes header that matches the name.</span></span>
[<span data-ttu-id="50449-119">GetIterator</span><span class="sxs-lookup"><span data-stu-id="50449-119">GetIterator</span></span>](#getiterator) | <span data-ttu-id="50449-120">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="50449-120">Gets an iterator over the collection of request headers.</span></span>

<span data-ttu-id="50449-121">WebResourceRequested イベントと NavigationStarting イベントの HTTP 要求を検査するために使われます。</span><span class="sxs-lookup"><span data-stu-id="50449-121">Used to inspect the HTTP request on WebResourceRequested event and NavigationStarting event.</span></span> <span data-ttu-id="50449-122">ただし、WebResourceRequested イベントから HTTP 要求ヘッダーを変更することはできますが、NavigationStarting イベントからは変更できません。</span><span class="sxs-lookup"><span data-stu-id="50449-122">Note, you can modify the HTTP request headers from a WebResourceRequested event, but not from a NavigationStarting event.</span></span>

## <span data-ttu-id="50449-123">Members</span><span class="sxs-lookup"><span data-stu-id="50449-123">Members</span></span>

#### <span data-ttu-id="50449-124">GetHeader</span><span class="sxs-lookup"><span data-stu-id="50449-124">GetHeader</span></span> 

<span data-ttu-id="50449-125">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="50449-125">Gets the header value matching the name.</span></span>

> <span data-ttu-id="50449-126">パブリック HRESULT [GetHeader](#getheader)(LPCWSTR NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="50449-126">public HRESULT [GetHeader](#getheader)(LPCWSTR name,LPWSTR \* value)</span></span>

#### <span data-ttu-id="50449-127">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="50449-127">GetHeaders</span></span> 

<span data-ttu-id="50449-128">名前に一致するヘッダー値をイテレータを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="50449-128">Gets the header value matching the name via an iterator.</span></span>

> <span data-ttu-id="50449-129">パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name,[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="50449-129">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name,[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="50449-130">Contains</span><span class="sxs-lookup"><span data-stu-id="50449-130">Contains</span></span> 

<span data-ttu-id="50449-131">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="50449-131">Checks whether the headers contain an entry matching the header name.</span></span>

> <span data-ttu-id="50449-132">パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL \* contains)</span><span class="sxs-lookup"><span data-stu-id="50449-132">public HRESULT [Contains](#contains)(LPCWSTR name,BOOL \* contains)</span></span>

#### <span data-ttu-id="50449-133">SetHeader</span><span class="sxs-lookup"><span data-stu-id="50449-133">SetHeader</span></span> 

<span data-ttu-id="50449-134">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="50449-134">Adds or updates header that matches the name.</span></span>

> <span data-ttu-id="50449-135">パブリック HRESULT [SetHeader](#setheader)(LPCWSTR NAME, LPCWSTR value)</span><span class="sxs-lookup"><span data-stu-id="50449-135">public HRESULT [SetHeader](#setheader)(LPCWSTR name,LPCWSTR value)</span></span>

#### <span data-ttu-id="50449-136">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="50449-136">RemoveHeader</span></span> 

<span data-ttu-id="50449-137">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="50449-137">Removes header that matches the name.</span></span>

> <span data-ttu-id="50449-138">パブリック HRESULT [Removeheader](#removeheader)(LPCWSTR name)</span><span class="sxs-lookup"><span data-stu-id="50449-138">public HRESULT [RemoveHeader](#removeheader)(LPCWSTR name)</span></span>

#### <span data-ttu-id="50449-139">GetIterator</span><span class="sxs-lookup"><span data-stu-id="50449-139">GetIterator</span></span> 

<span data-ttu-id="50449-140">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="50449-140">Gets an iterator over the collection of request headers.</span></span>

> <span data-ttu-id="50449-141">パブリック HRESULT [Getiterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="50449-141">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

