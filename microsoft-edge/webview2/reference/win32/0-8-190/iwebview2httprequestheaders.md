---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: aea00f37f28034e1b7a33d4fd11c5ed78f779d00
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654454"
---
# <span data-ttu-id="61993-104">インターフェイス IWebView2HttpRequestHeaders</span><span class="sxs-lookup"><span data-stu-id="61993-104">interface IWebView2HttpRequestHeaders</span></span> 

> [!NOTE]
> <span data-ttu-id="61993-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="61993-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="61993-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61993-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2HttpRequestHeaders
  : public IUnknown
```

<span data-ttu-id="61993-107">HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="61993-107">HTTP request headers.</span></span>

## <span data-ttu-id="61993-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="61993-108">Summary</span></span>

 <span data-ttu-id="61993-109">Members</span><span class="sxs-lookup"><span data-stu-id="61993-109">Members</span></span>                        | <span data-ttu-id="61993-110">説明</span><span class="sxs-lookup"><span data-stu-id="61993-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="61993-111">GetHeader</span><span class="sxs-lookup"><span data-stu-id="61993-111">GetHeader</span></span>](#getheader) | <span data-ttu-id="61993-112">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="61993-112">Gets the header value matching the name.</span></span>
[<span data-ttu-id="61993-113">Contains</span><span class="sxs-lookup"><span data-stu-id="61993-113">Contains</span></span>](#contains) | <span data-ttu-id="61993-114">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="61993-114">Checks whether the headers contain an entry matching the header name.</span></span>
[<span data-ttu-id="61993-115">SetHeader</span><span class="sxs-lookup"><span data-stu-id="61993-115">SetHeader</span></span>](#setheader) | <span data-ttu-id="61993-116">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="61993-116">Adds or updates header that matches the name.</span></span>
[<span data-ttu-id="61993-117">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="61993-117">RemoveHeader</span></span>](#removeheader) | <span data-ttu-id="61993-118">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="61993-118">Removes header that matches the name.</span></span>
[<span data-ttu-id="61993-119">GetIterator</span><span class="sxs-lookup"><span data-stu-id="61993-119">GetIterator</span></span>](#getiterator) | <span data-ttu-id="61993-120">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="61993-120">Gets an iterator over the collection of request headers.</span></span>

<span data-ttu-id="61993-121">WebResourceRequested イベントと NavigationStarting イベントの HTTP 要求を検査するために使われます。</span><span class="sxs-lookup"><span data-stu-id="61993-121">Used to inspect the HTTP request on WebResourceRequested event and NavigationStarting event.</span></span> <span data-ttu-id="61993-122">ただし、WebResourceRequested イベントから HTTP 要求ヘッダーを変更することはできますが、NavigationStarting イベントからは変更できません。</span><span class="sxs-lookup"><span data-stu-id="61993-122">Note, you can modify the HTTP request headers from a WebResourceRequested event, but not from a NavigationStarting event.</span></span>

## <span data-ttu-id="61993-123">Members</span><span class="sxs-lookup"><span data-stu-id="61993-123">Members</span></span>

#### <span data-ttu-id="61993-124">GetHeader</span><span class="sxs-lookup"><span data-stu-id="61993-124">GetHeader</span></span> 

<span data-ttu-id="61993-125">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="61993-125">Gets the header value matching the name.</span></span>

> <span data-ttu-id="61993-126">パブリック HRESULT [GetHeader](#getheader)(LPCWSTR NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="61993-126">public HRESULT [GetHeader](#getheader)(LPCWSTR name,LPWSTR \* value)</span></span>

#### <span data-ttu-id="61993-127">Contains</span><span class="sxs-lookup"><span data-stu-id="61993-127">Contains</span></span> 

<span data-ttu-id="61993-128">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="61993-128">Checks whether the headers contain an entry matching the header name.</span></span>

> <span data-ttu-id="61993-129">パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL \* contains)</span><span class="sxs-lookup"><span data-stu-id="61993-129">public HRESULT [Contains](#contains)(LPCWSTR name,BOOL \* contains)</span></span>

#### <span data-ttu-id="61993-130">SetHeader</span><span class="sxs-lookup"><span data-stu-id="61993-130">SetHeader</span></span> 

<span data-ttu-id="61993-131">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="61993-131">Adds or updates header that matches the name.</span></span>

> <span data-ttu-id="61993-132">パブリック HRESULT [SetHeader](#setheader)(LPCWSTR NAME, LPCWSTR value)</span><span class="sxs-lookup"><span data-stu-id="61993-132">public HRESULT [SetHeader](#setheader)(LPCWSTR name,LPCWSTR value)</span></span>

#### <span data-ttu-id="61993-133">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="61993-133">RemoveHeader</span></span> 

<span data-ttu-id="61993-134">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="61993-134">Removes header that matches the name.</span></span>

> <span data-ttu-id="61993-135">パブリック HRESULT [Removeheader](#removeheader)(LPCWSTR name)</span><span class="sxs-lookup"><span data-stu-id="61993-135">public HRESULT [RemoveHeader](#removeheader)(LPCWSTR name)</span></span>

#### <span data-ttu-id="61993-136">GetIterator</span><span class="sxs-lookup"><span data-stu-id="61993-136">GetIterator</span></span> 

<span data-ttu-id="61993-137">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="61993-137">Gets an iterator over the collection of request headers.</span></span>

> <span data-ttu-id="61993-138">パブリック HRESULT [Getiterator](#getiterator)([IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="61993-138">public HRESULT [GetIterator](#getiterator)([IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

