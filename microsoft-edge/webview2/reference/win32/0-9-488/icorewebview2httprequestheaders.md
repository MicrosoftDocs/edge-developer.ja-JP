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
ms.openlocfilehash: effceb6fafb062b1747f39876b8d2a5e02721aa8
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697274"
---
# <span data-ttu-id="42051-104">インターフェイス ICoreWebView2HttpRequestHeaders</span><span class="sxs-lookup"><span data-stu-id="42051-104">interface ICoreWebView2HttpRequestHeaders</span></span> 

> [!NOTE]
> <span data-ttu-id="42051-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="42051-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="42051-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42051-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2HttpRequestHeaders
  : public IUnknown
```

<span data-ttu-id="42051-107">HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="42051-107">HTTP request headers.</span></span>

## <span data-ttu-id="42051-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="42051-108">Summary</span></span>

 <span data-ttu-id="42051-109">Members</span><span class="sxs-lookup"><span data-stu-id="42051-109">Members</span></span>                        | <span data-ttu-id="42051-110">説明</span><span class="sxs-lookup"><span data-stu-id="42051-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="42051-111">Contains</span><span class="sxs-lookup"><span data-stu-id="42051-111">Contains</span></span>](#contains) | <span data-ttu-id="42051-112">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="42051-112">Checks whether the headers contain an entry matching the header name.</span></span>
[<span data-ttu-id="42051-113">GetHeader</span><span class="sxs-lookup"><span data-stu-id="42051-113">GetHeader</span></span>](#getheader) | <span data-ttu-id="42051-114">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="42051-114">Gets the header value matching the name.</span></span>
[<span data-ttu-id="42051-115">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="42051-115">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="42051-116">名前に一致するヘッダー値をイテレータを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="42051-116">Gets the header value matching the name via an iterator.</span></span>
[<span data-ttu-id="42051-117">GetIterator</span><span class="sxs-lookup"><span data-stu-id="42051-117">GetIterator</span></span>](#getiterator) | <span data-ttu-id="42051-118">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="42051-118">Gets an iterator over the collection of request headers.</span></span>
[<span data-ttu-id="42051-119">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="42051-119">RemoveHeader</span></span>](#removeheader) | <span data-ttu-id="42051-120">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="42051-120">Removes header that matches the name.</span></span>
[<span data-ttu-id="42051-121">SetHeader</span><span class="sxs-lookup"><span data-stu-id="42051-121">SetHeader</span></span>](#setheader) | <span data-ttu-id="42051-122">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="42051-122">Adds or updates header that matches the name.</span></span>

<span data-ttu-id="42051-123">WebResourceRequested イベントと NavigationStarting イベントの HTTP 要求を検査するために使われます。</span><span class="sxs-lookup"><span data-stu-id="42051-123">Used to inspect the HTTP request on WebResourceRequested event and NavigationStarting event.</span></span> <span data-ttu-id="42051-124">ただし、WebResourceRequested イベントから HTTP 要求ヘッダーを変更することはできますが、NavigationStarting イベントからは変更できません。</span><span class="sxs-lookup"><span data-stu-id="42051-124">Note, you can modify the HTTP request headers from a WebResourceRequested event, but not from a NavigationStarting event.</span></span>

## <span data-ttu-id="42051-125">Members</span><span class="sxs-lookup"><span data-stu-id="42051-125">Members</span></span>

#### <span data-ttu-id="42051-126">Contains</span><span class="sxs-lookup"><span data-stu-id="42051-126">Contains</span></span> 

<span data-ttu-id="42051-127">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="42051-127">Checks whether the headers contain an entry matching the header name.</span></span>

> <span data-ttu-id="42051-128">パブリック HRESULT [Contains](#contains)(LPCWSTR NAME, BOOL \* contains)</span><span class="sxs-lookup"><span data-stu-id="42051-128">public HRESULT [Contains](#contains)(LPCWSTR name, BOOL \* contains)</span></span>

#### <span data-ttu-id="42051-129">GetHeader</span><span class="sxs-lookup"><span data-stu-id="42051-129">GetHeader</span></span> 

<span data-ttu-id="42051-130">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="42051-130">Gets the header value matching the name.</span></span>

> <span data-ttu-id="42051-131">パブリック HRESULT [GetHeader](#getheader)(LPCWSTR NAME, LPWSTR \* value)</span><span class="sxs-lookup"><span data-stu-id="42051-131">public HRESULT [GetHeader](#getheader)(LPCWSTR name, LPWSTR \* value)</span></span>

#### <span data-ttu-id="42051-132">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="42051-132">GetHeaders</span></span> 

<span data-ttu-id="42051-133">名前に一致するヘッダー値をイテレータを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="42051-133">Gets the header value matching the name via an iterator.</span></span>

> <span data-ttu-id="42051-134">パブリック HRESULT [GetHeaders](#getheaders)(LPCWSTR Name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="42051-134">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="42051-135">GetIterator</span><span class="sxs-lookup"><span data-stu-id="42051-135">GetIterator</span></span> 

<span data-ttu-id="42051-136">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="42051-136">Gets an iterator over the collection of request headers.</span></span>

> <span data-ttu-id="42051-137">パブリック HRESULT [Getiterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* iterator)</span><span class="sxs-lookup"><span data-stu-id="42051-137">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="42051-138">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="42051-138">RemoveHeader</span></span> 

<span data-ttu-id="42051-139">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="42051-139">Removes header that matches the name.</span></span>

> <span data-ttu-id="42051-140">パブリック HRESULT [Removeheader](#removeheader)(LPCWSTR name)</span><span class="sxs-lookup"><span data-stu-id="42051-140">public HRESULT [RemoveHeader](#removeheader)(LPCWSTR name)</span></span>

#### <span data-ttu-id="42051-141">SetHeader</span><span class="sxs-lookup"><span data-stu-id="42051-141">SetHeader</span></span> 

<span data-ttu-id="42051-142">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="42051-142">Adds or updates header that matches the name.</span></span>

> <span data-ttu-id="42051-143">パブリック HRESULT [SetHeader](#setheader)(LPCWSTR NAME, LPCWSTR value)</span><span class="sxs-lookup"><span data-stu-id="42051-143">public HRESULT [SetHeader](#setheader)(LPCWSTR name, LPCWSTR value)</span></span>

