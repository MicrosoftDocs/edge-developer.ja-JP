---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2HttpRequestHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 1e0148c0d1e27cb4f1c52fb6ad55cc2e7613a94b
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885969"
---
# <span data-ttu-id="6cefd-104">0.8.355-インターフェイス IWebView2HttpRequestHeaders</span><span class="sxs-lookup"><span data-stu-id="6cefd-104">0.8.355 - interface IWebView2HttpRequestHeaders</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2HttpRequestHeaders
  : public IUnknown
```

<span data-ttu-id="6cefd-105">HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="6cefd-105">HTTP request headers.</span></span>

## <span data-ttu-id="6cefd-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="6cefd-106">Summary</span></span>

 <span data-ttu-id="6cefd-107">Members</span><span class="sxs-lookup"><span data-stu-id="6cefd-107">Members</span></span>                        | <span data-ttu-id="6cefd-108">説明</span><span class="sxs-lookup"><span data-stu-id="6cefd-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6cefd-109">GetHeader</span><span class="sxs-lookup"><span data-stu-id="6cefd-109">GetHeader</span></span>](#getheader) | <span data-ttu-id="6cefd-110">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="6cefd-110">Gets the header value matching the name.</span></span>
[<span data-ttu-id="6cefd-111">Contains</span><span class="sxs-lookup"><span data-stu-id="6cefd-111">Contains</span></span>](#contains) | <span data-ttu-id="6cefd-112">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="6cefd-112">Checks whether the headers contain an entry matching the header name.</span></span>
[<span data-ttu-id="6cefd-113">SetHeader</span><span class="sxs-lookup"><span data-stu-id="6cefd-113">SetHeader</span></span>](#setheader) | <span data-ttu-id="6cefd-114">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="6cefd-114">Adds or updates header that matches the name.</span></span>
[<span data-ttu-id="6cefd-115">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="6cefd-115">RemoveHeader</span></span>](#removeheader) | <span data-ttu-id="6cefd-116">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="6cefd-116">Removes header that matches the name.</span></span>
[<span data-ttu-id="6cefd-117">GetIterator</span><span class="sxs-lookup"><span data-stu-id="6cefd-117">GetIterator</span></span>](#getiterator) | <span data-ttu-id="6cefd-118">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="6cefd-118">Gets an iterator over the collection of request headers.</span></span>

<span data-ttu-id="6cefd-119">WebResourceRequested イベントと NavigationStarting イベントの HTTP 要求を検査するために使われます。</span><span class="sxs-lookup"><span data-stu-id="6cefd-119">Used to inspect the HTTP request on WebResourceRequested event and NavigationStarting event.</span></span> <span data-ttu-id="6cefd-120">ただし、WebResourceRequested イベントから HTTP 要求ヘッダーを変更することはできますが、NavigationStarting イベントからは変更できません。</span><span class="sxs-lookup"><span data-stu-id="6cefd-120">Note, you can modify the HTTP request headers from a WebResourceRequested event, but not from a NavigationStarting event.</span></span>

## <span data-ttu-id="6cefd-121">Members</span><span class="sxs-lookup"><span data-stu-id="6cefd-121">Members</span></span>

#### <span data-ttu-id="6cefd-122">GetHeader</span><span class="sxs-lookup"><span data-stu-id="6cefd-122">GetHeader</span></span> 

<span data-ttu-id="6cefd-123">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="6cefd-123">Gets the header value matching the name.</span></span>

> <span data-ttu-id="6cefd-124">パブリック HRESULT [GetHeader](#getheader)(LPCWSTR NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="6cefd-124">public HRESULT [GetHeader](#getheader)(LPCWSTR name,LPWSTR \* value)</span></span>

#### <span data-ttu-id="6cefd-125">Contains</span><span class="sxs-lookup"><span data-stu-id="6cefd-125">Contains</span></span> 

<span data-ttu-id="6cefd-126">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="6cefd-126">Checks whether the headers contain an entry matching the header name.</span></span>

> <span data-ttu-id="6cefd-127">パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL \* contains)</span><span class="sxs-lookup"><span data-stu-id="6cefd-127">public HRESULT [Contains](#contains)(LPCWSTR name,BOOL \* contains)</span></span>

#### <span data-ttu-id="6cefd-128">SetHeader</span><span class="sxs-lookup"><span data-stu-id="6cefd-128">SetHeader</span></span> 

<span data-ttu-id="6cefd-129">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="6cefd-129">Adds or updates header that matches the name.</span></span>

> <span data-ttu-id="6cefd-130">パブリック HRESULT [SetHeader](#setheader)(LPCWSTR NAME, LPCWSTR value)</span><span class="sxs-lookup"><span data-stu-id="6cefd-130">public HRESULT [SetHeader](#setheader)(LPCWSTR name,LPCWSTR value)</span></span>

#### <span data-ttu-id="6cefd-131">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="6cefd-131">RemoveHeader</span></span> 

<span data-ttu-id="6cefd-132">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="6cefd-132">Removes header that matches the name.</span></span>

> <span data-ttu-id="6cefd-133">パブリック HRESULT [Removeheader](#removeheader)(LPCWSTR name)</span><span class="sxs-lookup"><span data-stu-id="6cefd-133">public HRESULT [RemoveHeader](#removeheader)(LPCWSTR name)</span></span>

#### <span data-ttu-id="6cefd-134">GetIterator</span><span class="sxs-lookup"><span data-stu-id="6cefd-134">GetIterator</span></span> 

<span data-ttu-id="6cefd-135">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="6cefd-135">Gets an iterator over the collection of request headers.</span></span>

> <span data-ttu-id="6cefd-136">パブリック HRESULT [Getiterator](#getiterator)([IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="6cefd-136">public HRESULT [GetIterator](#getiterator)([IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

