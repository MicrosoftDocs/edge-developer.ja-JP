---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2HttpRequestHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 2587a3e07869076be659e29d484a647b74c2bd7f
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880550"
---
# <span data-ttu-id="dba64-104">0.9.515-インターフェイス ICoreWebView2HttpRequestHeaders</span><span class="sxs-lookup"><span data-stu-id="dba64-104">0.9.515 - interface ICoreWebView2HttpRequestHeaders</span></span> 

> [!NOTE]
> <span data-ttu-id="dba64-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dba64-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="dba64-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dba64-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2HttpRequestHeaders
  : public IUnknown
```

<span data-ttu-id="dba64-107">HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="dba64-107">HTTP request headers.</span></span>

## <span data-ttu-id="dba64-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="dba64-108">Summary</span></span>

 <span data-ttu-id="dba64-109">Members</span><span class="sxs-lookup"><span data-stu-id="dba64-109">Members</span></span>                        | <span data-ttu-id="dba64-110">説明</span><span class="sxs-lookup"><span data-stu-id="dba64-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="dba64-111">Contains</span><span class="sxs-lookup"><span data-stu-id="dba64-111">Contains</span></span>](#contains) | <span data-ttu-id="dba64-112">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="dba64-112">Checks whether the headers contain an entry matching the header name.</span></span>
[<span data-ttu-id="dba64-113">GetHeader</span><span class="sxs-lookup"><span data-stu-id="dba64-113">GetHeader</span></span>](#getheader) | <span data-ttu-id="dba64-114">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="dba64-114">Gets the header value matching the name.</span></span>
[<span data-ttu-id="dba64-115">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="dba64-115">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="dba64-116">名前に一致するヘッダー値をイテレータを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="dba64-116">Gets the header value matching the name via an iterator.</span></span>
[<span data-ttu-id="dba64-117">GetIterator</span><span class="sxs-lookup"><span data-stu-id="dba64-117">GetIterator</span></span>](#getiterator) | <span data-ttu-id="dba64-118">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="dba64-118">Gets an iterator over the collection of request headers.</span></span>
[<span data-ttu-id="dba64-119">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="dba64-119">RemoveHeader</span></span>](#removeheader) | <span data-ttu-id="dba64-120">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="dba64-120">Removes header that matches the name.</span></span>
[<span data-ttu-id="dba64-121">SetHeader</span><span class="sxs-lookup"><span data-stu-id="dba64-121">SetHeader</span></span>](#setheader) | <span data-ttu-id="dba64-122">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="dba64-122">Adds or updates header that matches the name.</span></span>

<span data-ttu-id="dba64-123">WebResourceRequested イベントと NavigationStarting イベントの HTTP 要求を検査するために使われます。</span><span class="sxs-lookup"><span data-stu-id="dba64-123">Used to inspect the HTTP request on WebResourceRequested event and NavigationStarting event.</span></span> <span data-ttu-id="dba64-124">ただし、WebResourceRequested イベントから HTTP 要求ヘッダーを変更することはできますが、NavigationStarting イベントからは変更できません。</span><span class="sxs-lookup"><span data-stu-id="dba64-124">Note, you can modify the HTTP request headers from a WebResourceRequested event, but not from a NavigationStarting event.</span></span>

## <span data-ttu-id="dba64-125">Members</span><span class="sxs-lookup"><span data-stu-id="dba64-125">Members</span></span>

#### <span data-ttu-id="dba64-126">Contains</span><span class="sxs-lookup"><span data-stu-id="dba64-126">Contains</span></span> 

<span data-ttu-id="dba64-127">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="dba64-127">Checks whether the headers contain an entry matching the header name.</span></span>

> <span data-ttu-id="dba64-128">パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL \* contains)</span><span class="sxs-lookup"><span data-stu-id="dba64-128">public HRESULT [Contains](#contains)(LPCWSTR name, BOOL \* contains)</span></span>

#### <span data-ttu-id="dba64-129">GetHeader</span><span class="sxs-lookup"><span data-stu-id="dba64-129">GetHeader</span></span> 

<span data-ttu-id="dba64-130">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="dba64-130">Gets the header value matching the name.</span></span>

> <span data-ttu-id="dba64-131">パブリック HRESULT [GetHeader](#getheader)(LPCWSTR NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="dba64-131">public HRESULT [GetHeader](#getheader)(LPCWSTR name, LPWSTR \* value)</span></span>

#### <span data-ttu-id="dba64-132">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="dba64-132">GetHeaders</span></span> 

<span data-ttu-id="dba64-133">名前に一致するヘッダー値をイテレータを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="dba64-133">Gets the header value matching the name via an iterator.</span></span>

> <span data-ttu-id="dba64-134">パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="dba64-134">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="dba64-135">GetIterator</span><span class="sxs-lookup"><span data-stu-id="dba64-135">GetIterator</span></span> 

<span data-ttu-id="dba64-136">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="dba64-136">Gets an iterator over the collection of request headers.</span></span>

> <span data-ttu-id="dba64-137">パブリック HRESULT [Getiterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="dba64-137">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="dba64-138">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="dba64-138">RemoveHeader</span></span> 

<span data-ttu-id="dba64-139">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="dba64-139">Removes header that matches the name.</span></span>

> <span data-ttu-id="dba64-140">パブリック HRESULT [Removeheader](#removeheader)(LPCWSTR name)</span><span class="sxs-lookup"><span data-stu-id="dba64-140">public HRESULT [RemoveHeader](#removeheader)(LPCWSTR name)</span></span>

#### <span data-ttu-id="dba64-141">SetHeader</span><span class="sxs-lookup"><span data-stu-id="dba64-141">SetHeader</span></span> 

<span data-ttu-id="dba64-142">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="dba64-142">Adds or updates header that matches the name.</span></span>

> <span data-ttu-id="dba64-143">パブリック HRESULT [SetHeader](#setheader)(LPCWSTR NAME, LPCWSTR value)</span><span class="sxs-lookup"><span data-stu-id="dba64-143">public HRESULT [SetHeader](#setheader)(LPCWSTR name, LPCWSTR value)</span></span>

