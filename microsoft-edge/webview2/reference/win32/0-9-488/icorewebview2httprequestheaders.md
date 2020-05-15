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
ms.openlocfilehash: 9f04e05ef77801a571771257f4a5e48077c373fd
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654305"
---
# <span data-ttu-id="f167c-104">インターフェイス ICoreWebView2HttpRequestHeaders</span><span class="sxs-lookup"><span data-stu-id="f167c-104">interface ICoreWebView2HttpRequestHeaders</span></span> 

```
interface ICoreWebView2HttpRequestHeaders
  : public IUnknown
```

<span data-ttu-id="f167c-105">HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="f167c-105">HTTP request headers.</span></span>

## <span data-ttu-id="f167c-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="f167c-106">Summary</span></span>

 <span data-ttu-id="f167c-107">Members</span><span class="sxs-lookup"><span data-stu-id="f167c-107">Members</span></span>                        | <span data-ttu-id="f167c-108">説明</span><span class="sxs-lookup"><span data-stu-id="f167c-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f167c-109">Contains</span><span class="sxs-lookup"><span data-stu-id="f167c-109">Contains</span></span>](#contains) | <span data-ttu-id="f167c-110">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f167c-110">Checks whether the headers contain an entry matching the header name.</span></span>
[<span data-ttu-id="f167c-111">GetHeader</span><span class="sxs-lookup"><span data-stu-id="f167c-111">GetHeader</span></span>](#getheader) | <span data-ttu-id="f167c-112">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="f167c-112">Gets the header value matching the name.</span></span>
[<span data-ttu-id="f167c-113">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="f167c-113">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="f167c-114">名前に一致するヘッダー値をイテレータを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="f167c-114">Gets the header value matching the name via an iterator.</span></span>
[<span data-ttu-id="f167c-115">GetIterator</span><span class="sxs-lookup"><span data-stu-id="f167c-115">GetIterator</span></span>](#getiterator) | <span data-ttu-id="f167c-116">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="f167c-116">Gets an iterator over the collection of request headers.</span></span>
[<span data-ttu-id="f167c-117">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="f167c-117">RemoveHeader</span></span>](#removeheader) | <span data-ttu-id="f167c-118">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="f167c-118">Removes header that matches the name.</span></span>
[<span data-ttu-id="f167c-119">SetHeader</span><span class="sxs-lookup"><span data-stu-id="f167c-119">SetHeader</span></span>](#setheader) | <span data-ttu-id="f167c-120">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="f167c-120">Adds or updates header that matches the name.</span></span>

<span data-ttu-id="f167c-121">WebResourceRequested イベントと NavigationStarting イベントの HTTP 要求を検査するために使われます。</span><span class="sxs-lookup"><span data-stu-id="f167c-121">Used to inspect the HTTP request on WebResourceRequested event and NavigationStarting event.</span></span> <span data-ttu-id="f167c-122">ただし、WebResourceRequested イベントから HTTP 要求ヘッダーを変更することはできますが、NavigationStarting イベントからは変更できません。</span><span class="sxs-lookup"><span data-stu-id="f167c-122">Note, you can modify the HTTP request headers from a WebResourceRequested event, but not from a NavigationStarting event.</span></span>

## <span data-ttu-id="f167c-123">Members</span><span class="sxs-lookup"><span data-stu-id="f167c-123">Members</span></span>

#### <span data-ttu-id="f167c-124">Contains</span><span class="sxs-lookup"><span data-stu-id="f167c-124">Contains</span></span> 

<span data-ttu-id="f167c-125">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f167c-125">Checks whether the headers contain an entry matching the header name.</span></span>

> <span data-ttu-id="f167c-126">パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL \* contains)</span><span class="sxs-lookup"><span data-stu-id="f167c-126">public HRESULT [Contains](#contains)(LPCWSTR name, BOOL \* contains)</span></span>

#### <span data-ttu-id="f167c-127">GetHeader</span><span class="sxs-lookup"><span data-stu-id="f167c-127">GetHeader</span></span> 

<span data-ttu-id="f167c-128">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="f167c-128">Gets the header value matching the name.</span></span>

> <span data-ttu-id="f167c-129">パブリック HRESULT [GetHeader](#getheader)(LPCWSTR NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="f167c-129">public HRESULT [GetHeader](#getheader)(LPCWSTR name, LPWSTR \* value)</span></span>

#### <span data-ttu-id="f167c-130">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="f167c-130">GetHeaders</span></span> 

<span data-ttu-id="f167c-131">名前に一致するヘッダー値をイテレータを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="f167c-131">Gets the header value matching the name via an iterator.</span></span>

> <span data-ttu-id="f167c-132">パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="f167c-132">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="f167c-133">GetIterator</span><span class="sxs-lookup"><span data-stu-id="f167c-133">GetIterator</span></span> 

<span data-ttu-id="f167c-134">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="f167c-134">Gets an iterator over the collection of request headers.</span></span>

> <span data-ttu-id="f167c-135">パブリック HRESULT [Getiterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="f167c-135">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="f167c-136">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="f167c-136">RemoveHeader</span></span> 

<span data-ttu-id="f167c-137">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="f167c-137">Removes header that matches the name.</span></span>

> <span data-ttu-id="f167c-138">パブリック HRESULT [Removeheader](#removeheader)(LPCWSTR name)</span><span class="sxs-lookup"><span data-stu-id="f167c-138">public HRESULT [RemoveHeader](#removeheader)(LPCWSTR name)</span></span>

#### <span data-ttu-id="f167c-139">SetHeader</span><span class="sxs-lookup"><span data-stu-id="f167c-139">SetHeader</span></span> 

<span data-ttu-id="f167c-140">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="f167c-140">Adds or updates header that matches the name.</span></span>

> <span data-ttu-id="f167c-141">パブリック HRESULT [SetHeader](#setheader)(LPCWSTR NAME, LPCWSTR value)</span><span class="sxs-lookup"><span data-stu-id="f167c-141">public HRESULT [SetHeader](#setheader)(LPCWSTR name, LPCWSTR value)</span></span>

