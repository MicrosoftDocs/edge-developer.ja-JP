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
ms.openlocfilehash: 19018ff63b62b0d76bed6dcce9cf1dbce2a37b11
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698992"
---
# <span data-ttu-id="c871b-104">インターフェイス ICoreWebView2HttpRequestHeaders</span><span class="sxs-lookup"><span data-stu-id="c871b-104">interface ICoreWebView2HttpRequestHeaders</span></span> 

```
interface ICoreWebView2HttpRequestHeaders
  : public IUnknown
```

<span data-ttu-id="c871b-105">HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="c871b-105">HTTP request headers.</span></span>

## <span data-ttu-id="c871b-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="c871b-106">Summary</span></span>

 <span data-ttu-id="c871b-107">Members</span><span class="sxs-lookup"><span data-stu-id="c871b-107">Members</span></span>                        | <span data-ttu-id="c871b-108">説明</span><span class="sxs-lookup"><span data-stu-id="c871b-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c871b-109">Contains</span><span class="sxs-lookup"><span data-stu-id="c871b-109">Contains</span></span>](#contains) | <span data-ttu-id="c871b-110">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c871b-110">Checks whether the headers contain an entry matching the header name.</span></span>
[<span data-ttu-id="c871b-111">GetHeader</span><span class="sxs-lookup"><span data-stu-id="c871b-111">GetHeader</span></span>](#getheader) | <span data-ttu-id="c871b-112">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="c871b-112">Gets the header value matching the name.</span></span>
[<span data-ttu-id="c871b-113">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="c871b-113">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="c871b-114">名前に一致するヘッダー値をイテレータを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="c871b-114">Gets the header value matching the name via an iterator.</span></span>
[<span data-ttu-id="c871b-115">GetIterator</span><span class="sxs-lookup"><span data-stu-id="c871b-115">GetIterator</span></span>](#getiterator) | <span data-ttu-id="c871b-116">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="c871b-116">Gets an iterator over the collection of request headers.</span></span>
[<span data-ttu-id="c871b-117">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="c871b-117">RemoveHeader</span></span>](#removeheader) | <span data-ttu-id="c871b-118">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c871b-118">Removes header that matches the name.</span></span>
[<span data-ttu-id="c871b-119">SetHeader</span><span class="sxs-lookup"><span data-stu-id="c871b-119">SetHeader</span></span>](#setheader) | <span data-ttu-id="c871b-120">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="c871b-120">Adds or updates header that matches the name.</span></span>

<span data-ttu-id="c871b-121">WebResourceRequested イベントと NavigationStarting イベントの HTTP 要求を検査するために使われます。</span><span class="sxs-lookup"><span data-stu-id="c871b-121">Used to inspect the HTTP request on WebResourceRequested event and NavigationStarting event.</span></span> <span data-ttu-id="c871b-122">ただし、WebResourceRequested イベントから HTTP 要求ヘッダーを変更することはできますが、NavigationStarting イベントからは変更できません。</span><span class="sxs-lookup"><span data-stu-id="c871b-122">Note, you can modify the HTTP request headers from a WebResourceRequested event, but not from a NavigationStarting event.</span></span>

## <span data-ttu-id="c871b-123">Members</span><span class="sxs-lookup"><span data-stu-id="c871b-123">Members</span></span>

#### <span data-ttu-id="c871b-124">Contains</span><span class="sxs-lookup"><span data-stu-id="c871b-124">Contains</span></span> 

<span data-ttu-id="c871b-125">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c871b-125">Checks whether the headers contain an entry matching the header name.</span></span>

> <span data-ttu-id="c871b-126">パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL \* contains)</span><span class="sxs-lookup"><span data-stu-id="c871b-126">public HRESULT [Contains](#contains)(LPCWSTR name, BOOL \* contains)</span></span>

#### <span data-ttu-id="c871b-127">GetHeader</span><span class="sxs-lookup"><span data-stu-id="c871b-127">GetHeader</span></span> 

<span data-ttu-id="c871b-128">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="c871b-128">Gets the header value matching the name.</span></span>

> <span data-ttu-id="c871b-129">パブリック HRESULT [GetHeader](#getheader)(LPCWSTR NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="c871b-129">public HRESULT [GetHeader](#getheader)(LPCWSTR name, LPWSTR \* value)</span></span>

#### <span data-ttu-id="c871b-130">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="c871b-130">GetHeaders</span></span> 

<span data-ttu-id="c871b-131">名前に一致するヘッダー値をイテレータを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="c871b-131">Gets the header value matching the name via an iterator.</span></span>

> <span data-ttu-id="c871b-132">パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="c871b-132">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="c871b-133">GetIterator</span><span class="sxs-lookup"><span data-stu-id="c871b-133">GetIterator</span></span> 

<span data-ttu-id="c871b-134">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="c871b-134">Gets an iterator over the collection of request headers.</span></span>

> <span data-ttu-id="c871b-135">パブリック HRESULT [Getiterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="c871b-135">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="c871b-136">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="c871b-136">RemoveHeader</span></span> 

<span data-ttu-id="c871b-137">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c871b-137">Removes header that matches the name.</span></span>

> <span data-ttu-id="c871b-138">パブリック HRESULT [Removeheader](#removeheader)(LPCWSTR name)</span><span class="sxs-lookup"><span data-stu-id="c871b-138">public HRESULT [RemoveHeader](#removeheader)(LPCWSTR name)</span></span>

#### <span data-ttu-id="c871b-139">SetHeader</span><span class="sxs-lookup"><span data-stu-id="c871b-139">SetHeader</span></span> 

<span data-ttu-id="c871b-140">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="c871b-140">Adds or updates header that matches the name.</span></span>

> <span data-ttu-id="c871b-141">パブリック HRESULT [SetHeader](#setheader)(LPCWSTR NAME, LPCWSTR value)</span><span class="sxs-lookup"><span data-stu-id="c871b-141">public HRESULT [SetHeader](#setheader)(LPCWSTR name, LPCWSTR value)</span></span>

