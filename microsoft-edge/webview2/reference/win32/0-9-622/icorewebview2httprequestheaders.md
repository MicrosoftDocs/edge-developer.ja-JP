---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2HttpRequestHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2HttpRequestHeaders
ms.openlocfilehash: 8455db6adccf2d3d10e9934fee940d00bba7377c
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012273"
---
# <span data-ttu-id="0bf9e-104">インターフェイス ICoreWebView2HttpRequestHeaders</span><span class="sxs-lookup"><span data-stu-id="0bf9e-104">interface ICoreWebView2HttpRequestHeaders</span></span> 

```
interface ICoreWebView2HttpRequestHeaders
  : public IUnknown
```

<span data-ttu-id="0bf9e-105">HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-105">HTTP request headers.</span></span>

## <span data-ttu-id="0bf9e-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="0bf9e-106">Summary</span></span>

 <span data-ttu-id="0bf9e-107">Members</span><span class="sxs-lookup"><span data-stu-id="0bf9e-107">Members</span></span>                        | <span data-ttu-id="0bf9e-108">説明</span><span class="sxs-lookup"><span data-stu-id="0bf9e-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0bf9e-109">Contains</span><span class="sxs-lookup"><span data-stu-id="0bf9e-109">Contains</span></span>](#contains) | <span data-ttu-id="0bf9e-110">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-110">Checks whether the headers contain an entry matching the header name.</span></span>
[<span data-ttu-id="0bf9e-111">GetHeader</span><span class="sxs-lookup"><span data-stu-id="0bf9e-111">GetHeader</span></span>](#getheader) | <span data-ttu-id="0bf9e-112">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-112">Gets the header value matching the name.</span></span>
[<span data-ttu-id="0bf9e-113">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="0bf9e-113">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="0bf9e-114">名前に一致するヘッダー値をイテレータを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-114">Gets the header value matching the name via an iterator.</span></span>
[<span data-ttu-id="0bf9e-115">GetIterator</span><span class="sxs-lookup"><span data-stu-id="0bf9e-115">GetIterator</span></span>](#getiterator) | <span data-ttu-id="0bf9e-116">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-116">Gets an iterator over the collection of request headers.</span></span>
[<span data-ttu-id="0bf9e-117">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="0bf9e-117">RemoveHeader</span></span>](#removeheader) | <span data-ttu-id="0bf9e-118">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-118">Removes header that matches the name.</span></span>
[<span data-ttu-id="0bf9e-119">SetHeader</span><span class="sxs-lookup"><span data-stu-id="0bf9e-119">SetHeader</span></span>](#setheader) | <span data-ttu-id="0bf9e-120">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-120">Adds or updates header that matches the name.</span></span>

<span data-ttu-id="0bf9e-121">WebResourceRequested イベントと NavigationStarting イベントの HTTP 要求を検査するために使われます。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-121">Used to inspect the HTTP request on WebResourceRequested event and NavigationStarting event.</span></span> <span data-ttu-id="0bf9e-122">ただし、WebResourceRequested イベントから HTTP 要求ヘッダーを変更することはできますが、NavigationStarting イベントからは変更できません。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-122">Note, you can modify the HTTP request headers from a WebResourceRequested event, but not from a NavigationStarting event.</span></span>

## <span data-ttu-id="0bf9e-123">Members</span><span class="sxs-lookup"><span data-stu-id="0bf9e-123">Members</span></span>

#### <span data-ttu-id="0bf9e-124">Contains</span><span class="sxs-lookup"><span data-stu-id="0bf9e-124">Contains</span></span> 

<span data-ttu-id="0bf9e-125">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-125">Checks whether the headers contain an entry matching the header name.</span></span>

> <span data-ttu-id="0bf9e-126">パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL \* contains)</span><span class="sxs-lookup"><span data-stu-id="0bf9e-126">public HRESULT [Contains](#contains)(LPCWSTR name, BOOL \* contains)</span></span>

#### <span data-ttu-id="0bf9e-127">GetHeader</span><span class="sxs-lookup"><span data-stu-id="0bf9e-127">GetHeader</span></span> 

<span data-ttu-id="0bf9e-128">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-128">Gets the header value matching the name.</span></span>

> <span data-ttu-id="0bf9e-129">パブリック HRESULT [GetHeader](#getheader)(LPCWSTR NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="0bf9e-129">public HRESULT [GetHeader](#getheader)(LPCWSTR name, LPWSTR \* value)</span></span>

#### <span data-ttu-id="0bf9e-130">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="0bf9e-130">GetHeaders</span></span> 

<span data-ttu-id="0bf9e-131">名前に一致するヘッダー値をイテレータを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-131">Gets the header value matching the name via an iterator.</span></span>

> <span data-ttu-id="0bf9e-132">パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="0bf9e-132">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="0bf9e-133">GetIterator</span><span class="sxs-lookup"><span data-stu-id="0bf9e-133">GetIterator</span></span> 

<span data-ttu-id="0bf9e-134">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-134">Gets an iterator over the collection of request headers.</span></span>

> <span data-ttu-id="0bf9e-135">パブリック HRESULT [Getiterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="0bf9e-135">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="0bf9e-136">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="0bf9e-136">RemoveHeader</span></span> 

<span data-ttu-id="0bf9e-137">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-137">Removes header that matches the name.</span></span>

> <span data-ttu-id="0bf9e-138">パブリック HRESULT [Removeheader](#removeheader)(LPCWSTR name)</span><span class="sxs-lookup"><span data-stu-id="0bf9e-138">public HRESULT [RemoveHeader](#removeheader)(LPCWSTR name)</span></span>

#### <span data-ttu-id="0bf9e-139">SetHeader</span><span class="sxs-lookup"><span data-stu-id="0bf9e-139">SetHeader</span></span> 

<span data-ttu-id="0bf9e-140">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-140">Adds or updates header that matches the name.</span></span>

> <span data-ttu-id="0bf9e-141">パブリック HRESULT [SetHeader](#setheader)(LPCWSTR NAME, LPCWSTR value)</span><span class="sxs-lookup"><span data-stu-id="0bf9e-141">public HRESULT [SetHeader](#setheader)(LPCWSTR name, LPCWSTR value)</span></span>

