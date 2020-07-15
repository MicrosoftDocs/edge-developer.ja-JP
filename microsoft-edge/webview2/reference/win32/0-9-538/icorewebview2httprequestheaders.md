---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2HttpRequestHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2HttpRequestHeaders
ms.openlocfilehash: 903355ff04463ad86f1e25771f5f321f7d0df479
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879164"
---
# <span data-ttu-id="30278-104">インターフェイス ICoreWebView2HttpRequestHeaders</span><span class="sxs-lookup"><span data-stu-id="30278-104">interface ICoreWebView2HttpRequestHeaders</span></span> 

```
interface ICoreWebView2HttpRequestHeaders
  : public IUnknown
```

<span data-ttu-id="30278-105">HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="30278-105">HTTP request headers.</span></span>

## <span data-ttu-id="30278-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="30278-106">Summary</span></span>

 <span data-ttu-id="30278-107">Members</span><span class="sxs-lookup"><span data-stu-id="30278-107">Members</span></span>                        | <span data-ttu-id="30278-108">説明</span><span class="sxs-lookup"><span data-stu-id="30278-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="30278-109">Contains</span><span class="sxs-lookup"><span data-stu-id="30278-109">Contains</span></span>](#contains) | <span data-ttu-id="30278-110">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="30278-110">Checks whether the headers contain an entry matching the header name.</span></span>
[<span data-ttu-id="30278-111">GetHeader</span><span class="sxs-lookup"><span data-stu-id="30278-111">GetHeader</span></span>](#getheader) | <span data-ttu-id="30278-112">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="30278-112">Gets the header value matching the name.</span></span>
[<span data-ttu-id="30278-113">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="30278-113">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="30278-114">名前に一致するヘッダー値をイテレータを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="30278-114">Gets the header value matching the name via an iterator.</span></span>
[<span data-ttu-id="30278-115">GetIterator</span><span class="sxs-lookup"><span data-stu-id="30278-115">GetIterator</span></span>](#getiterator) | <span data-ttu-id="30278-116">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="30278-116">Gets an iterator over the collection of request headers.</span></span>
[<span data-ttu-id="30278-117">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="30278-117">RemoveHeader</span></span>](#removeheader) | <span data-ttu-id="30278-118">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="30278-118">Removes header that matches the name.</span></span>
[<span data-ttu-id="30278-119">SetHeader</span><span class="sxs-lookup"><span data-stu-id="30278-119">SetHeader</span></span>](#setheader) | <span data-ttu-id="30278-120">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="30278-120">Adds or updates header that matches the name.</span></span>

<span data-ttu-id="30278-121">WebResourceRequested イベントと NavigationStarting イベントの HTTP 要求を検査するために使われます。</span><span class="sxs-lookup"><span data-stu-id="30278-121">Used to inspect the HTTP request on WebResourceRequested event and NavigationStarting event.</span></span> <span data-ttu-id="30278-122">ただし、WebResourceRequested イベントから HTTP 要求ヘッダーを変更することはできますが、NavigationStarting イベントからは変更できません。</span><span class="sxs-lookup"><span data-stu-id="30278-122">Note, you can modify the HTTP request headers from a WebResourceRequested event, but not from a NavigationStarting event.</span></span>

## <span data-ttu-id="30278-123">Members</span><span class="sxs-lookup"><span data-stu-id="30278-123">Members</span></span>

#### <span data-ttu-id="30278-124">Contains</span><span class="sxs-lookup"><span data-stu-id="30278-124">Contains</span></span> 

<span data-ttu-id="30278-125">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="30278-125">Checks whether the headers contain an entry matching the header name.</span></span>

> <span data-ttu-id="30278-126">パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL \* contains)</span><span class="sxs-lookup"><span data-stu-id="30278-126">public HRESULT [Contains](#contains)(LPCWSTR name, BOOL \* contains)</span></span>

#### <span data-ttu-id="30278-127">GetHeader</span><span class="sxs-lookup"><span data-stu-id="30278-127">GetHeader</span></span> 

<span data-ttu-id="30278-128">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="30278-128">Gets the header value matching the name.</span></span>

> <span data-ttu-id="30278-129">パブリック HRESULT [GetHeader](#getheader)(LPCWSTR NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="30278-129">public HRESULT [GetHeader](#getheader)(LPCWSTR name, LPWSTR \* value)</span></span>

#### <span data-ttu-id="30278-130">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="30278-130">GetHeaders</span></span> 

<span data-ttu-id="30278-131">名前に一致するヘッダー値をイテレータを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="30278-131">Gets the header value matching the name via an iterator.</span></span>

> <span data-ttu-id="30278-132">パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="30278-132">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="30278-133">GetIterator</span><span class="sxs-lookup"><span data-stu-id="30278-133">GetIterator</span></span> 

<span data-ttu-id="30278-134">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="30278-134">Gets an iterator over the collection of request headers.</span></span>

> <span data-ttu-id="30278-135">パブリック HRESULT [Getiterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="30278-135">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="30278-136">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="30278-136">RemoveHeader</span></span> 

<span data-ttu-id="30278-137">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="30278-137">Removes header that matches the name.</span></span>

> <span data-ttu-id="30278-138">パブリック HRESULT [Removeheader](#removeheader)(LPCWSTR name)</span><span class="sxs-lookup"><span data-stu-id="30278-138">public HRESULT [RemoveHeader](#removeheader)(LPCWSTR name)</span></span>

#### <span data-ttu-id="30278-139">SetHeader</span><span class="sxs-lookup"><span data-stu-id="30278-139">SetHeader</span></span> 

<span data-ttu-id="30278-140">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="30278-140">Adds or updates header that matches the name.</span></span>

> <span data-ttu-id="30278-141">パブリック HRESULT [SetHeader](#setheader)(LPCWSTR NAME, LPCWSTR value)</span><span class="sxs-lookup"><span data-stu-id="30278-141">public HRESULT [SetHeader](#setheader)(LPCWSTR name, LPCWSTR value)</span></span>

