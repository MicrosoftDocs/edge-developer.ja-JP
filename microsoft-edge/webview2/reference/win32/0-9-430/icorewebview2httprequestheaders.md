---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: e12809d1db7e8c7764ad75e9a10f44ac3f445fa4
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654319"
---
# <span data-ttu-id="71a4e-104">インターフェイス ICoreWebView2HttpRequestHeaders</span><span class="sxs-lookup"><span data-stu-id="71a4e-104">interface ICoreWebView2HttpRequestHeaders</span></span> 

> [!NOTE]
> <span data-ttu-id="71a4e-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="71a4e-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="71a4e-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71a4e-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2HttpRequestHeaders
  : public IUnknown
```

<span data-ttu-id="71a4e-107">HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="71a4e-107">HTTP request headers.</span></span>

## <span data-ttu-id="71a4e-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="71a4e-108">Summary</span></span>

 <span data-ttu-id="71a4e-109">Members</span><span class="sxs-lookup"><span data-stu-id="71a4e-109">Members</span></span>                        | <span data-ttu-id="71a4e-110">説明</span><span class="sxs-lookup"><span data-stu-id="71a4e-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="71a4e-111">GetHeader</span><span class="sxs-lookup"><span data-stu-id="71a4e-111">GetHeader</span></span>](#getheader) | <span data-ttu-id="71a4e-112">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="71a4e-112">Gets the header value matching the name.</span></span>
[<span data-ttu-id="71a4e-113">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="71a4e-113">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="71a4e-114">名前に一致するヘッダー値をイテレータを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="71a4e-114">Gets the header value matching the name via an iterator.</span></span>
[<span data-ttu-id="71a4e-115">Contains</span><span class="sxs-lookup"><span data-stu-id="71a4e-115">Contains</span></span>](#contains) | <span data-ttu-id="71a4e-116">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="71a4e-116">Checks whether the headers contain an entry matching the header name.</span></span>
[<span data-ttu-id="71a4e-117">SetHeader</span><span class="sxs-lookup"><span data-stu-id="71a4e-117">SetHeader</span></span>](#setheader) | <span data-ttu-id="71a4e-118">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="71a4e-118">Adds or updates header that matches the name.</span></span>
[<span data-ttu-id="71a4e-119">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="71a4e-119">RemoveHeader</span></span>](#removeheader) | <span data-ttu-id="71a4e-120">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="71a4e-120">Removes header that matches the name.</span></span>
[<span data-ttu-id="71a4e-121">GetIterator</span><span class="sxs-lookup"><span data-stu-id="71a4e-121">GetIterator</span></span>](#getiterator) | <span data-ttu-id="71a4e-122">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="71a4e-122">Gets an iterator over the collection of request headers.</span></span>

<span data-ttu-id="71a4e-123">WebResourceRequested イベントと NavigationStarting イベントの HTTP 要求を検査するために使われます。</span><span class="sxs-lookup"><span data-stu-id="71a4e-123">Used to inspect the HTTP request on WebResourceRequested event and NavigationStarting event.</span></span> <span data-ttu-id="71a4e-124">ただし、WebResourceRequested イベントから HTTP 要求ヘッダーを変更することはできますが、NavigationStarting イベントからは変更できません。</span><span class="sxs-lookup"><span data-stu-id="71a4e-124">Note, you can modify the HTTP request headers from a WebResourceRequested event, but not from a NavigationStarting event.</span></span>

## <span data-ttu-id="71a4e-125">Members</span><span class="sxs-lookup"><span data-stu-id="71a4e-125">Members</span></span>

#### <span data-ttu-id="71a4e-126">GetHeader</span><span class="sxs-lookup"><span data-stu-id="71a4e-126">GetHeader</span></span> 

<span data-ttu-id="71a4e-127">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="71a4e-127">Gets the header value matching the name.</span></span>

> <span data-ttu-id="71a4e-128">パブリック HRESULT [GetHeader](#getheader)(LPCWSTR NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="71a4e-128">public HRESULT [GetHeader](#getheader)(LPCWSTR name,LPWSTR \* value)</span></span>

#### <span data-ttu-id="71a4e-129">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="71a4e-129">GetHeaders</span></span> 

<span data-ttu-id="71a4e-130">名前に一致するヘッダー値をイテレータを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="71a4e-130">Gets the header value matching the name via an iterator.</span></span>

> <span data-ttu-id="71a4e-131">パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name,[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="71a4e-131">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name,[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="71a4e-132">Contains</span><span class="sxs-lookup"><span data-stu-id="71a4e-132">Contains</span></span> 

<span data-ttu-id="71a4e-133">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="71a4e-133">Checks whether the headers contain an entry matching the header name.</span></span>

> <span data-ttu-id="71a4e-134">パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL \* contains)</span><span class="sxs-lookup"><span data-stu-id="71a4e-134">public HRESULT [Contains](#contains)(LPCWSTR name,BOOL \* contains)</span></span>

#### <span data-ttu-id="71a4e-135">SetHeader</span><span class="sxs-lookup"><span data-stu-id="71a4e-135">SetHeader</span></span> 

<span data-ttu-id="71a4e-136">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="71a4e-136">Adds or updates header that matches the name.</span></span>

> <span data-ttu-id="71a4e-137">パブリック HRESULT [SetHeader](#setheader)(LPCWSTR NAME, LPCWSTR value)</span><span class="sxs-lookup"><span data-stu-id="71a4e-137">public HRESULT [SetHeader](#setheader)(LPCWSTR name,LPCWSTR value)</span></span>

#### <span data-ttu-id="71a4e-138">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="71a4e-138">RemoveHeader</span></span> 

<span data-ttu-id="71a4e-139">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="71a4e-139">Removes header that matches the name.</span></span>

> <span data-ttu-id="71a4e-140">パブリック HRESULT [Removeheader](#removeheader)(LPCWSTR name)</span><span class="sxs-lookup"><span data-stu-id="71a4e-140">public HRESULT [RemoveHeader](#removeheader)(LPCWSTR name)</span></span>

#### <span data-ttu-id="71a4e-141">GetIterator</span><span class="sxs-lookup"><span data-stu-id="71a4e-141">GetIterator</span></span> 

<span data-ttu-id="71a4e-142">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="71a4e-142">Gets an iterator over the collection of request headers.</span></span>

> <span data-ttu-id="71a4e-143">パブリック HRESULT [Getiterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="71a4e-143">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>
