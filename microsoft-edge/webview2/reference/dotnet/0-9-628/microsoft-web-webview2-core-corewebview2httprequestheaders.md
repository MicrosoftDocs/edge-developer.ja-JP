---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2HttpRequestHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2HttpRequestHeaders。
ms.openlocfilehash: 1441d5a45caf4e8f561de2487438b66e067760f6
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012218"
---
# <span data-ttu-id="21fbe-104">WebView2 クラス (CoreWebView2HttpRequestHeaders クラス)</span><span class="sxs-lookup"><span data-stu-id="21fbe-104">Microsoft.Web.WebView2.Core.CoreWebView2HttpRequestHeaders class</span></span> 

<span data-ttu-id="21fbe-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="21fbe-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="21fbe-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="21fbe-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="21fbe-107">HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="21fbe-107">HTTP request headers.</span></span>

## <span data-ttu-id="21fbe-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="21fbe-108">Summary</span></span>

 <span data-ttu-id="21fbe-109">Members</span><span class="sxs-lookup"><span data-stu-id="21fbe-109">Members</span></span>                        | <span data-ttu-id="21fbe-110">説明</span><span class="sxs-lookup"><span data-stu-id="21fbe-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="21fbe-111">Contains</span><span class="sxs-lookup"><span data-stu-id="21fbe-111">Contains</span></span>](#contains) | <span data-ttu-id="21fbe-112">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="21fbe-112">Checks whether the headers contain an entry matching the header name.</span></span>
[<span data-ttu-id="21fbe-113">GetHeader</span><span class="sxs-lookup"><span data-stu-id="21fbe-113">GetHeader</span></span>](#getheader) | <span data-ttu-id="21fbe-114">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="21fbe-114">Gets the header value matching the name.</span></span>
[<span data-ttu-id="21fbe-115">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="21fbe-115">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="21fbe-116">名前に一致するヘッダー値をイテレータを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="21fbe-116">Gets the header value matching the name via an iterator.</span></span>
[<span data-ttu-id="21fbe-117">GetIterator</span><span class="sxs-lookup"><span data-stu-id="21fbe-117">GetIterator</span></span>](#getiterator) | <span data-ttu-id="21fbe-118">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="21fbe-118">Gets an iterator over the collection of request headers.</span></span>
[<span data-ttu-id="21fbe-119">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="21fbe-119">RemoveHeader</span></span>](#removeheader) | <span data-ttu-id="21fbe-120">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="21fbe-120">Removes header that matches the name.</span></span>
[<span data-ttu-id="21fbe-121">SetHeader</span><span class="sxs-lookup"><span data-stu-id="21fbe-121">SetHeader</span></span>](#setheader) | <span data-ttu-id="21fbe-122">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="21fbe-122">Adds or updates header that matches the name.</span></span>

<span data-ttu-id="21fbe-123">WebResourceRequested イベントと NavigationStarting イベントの HTTP 要求を検査するために使われます。</span><span class="sxs-lookup"><span data-stu-id="21fbe-123">Used to inspect the HTTP request on WebResourceRequested event and NavigationStarting event.</span></span> <span data-ttu-id="21fbe-124">ただし、WebResourceRequested イベントから HTTP 要求ヘッダーを変更することはできますが、NavigationStarting イベントからは変更できません。</span><span class="sxs-lookup"><span data-stu-id="21fbe-124">Note, you can modify the HTTP request headers from a WebResourceRequested event, but not from a NavigationStarting event.</span></span>

## <span data-ttu-id="21fbe-125">Members</span><span class="sxs-lookup"><span data-stu-id="21fbe-125">Members</span></span>

#### <span data-ttu-id="21fbe-126">Contains</span><span class="sxs-lookup"><span data-stu-id="21fbe-126">Contains</span></span> 

<span data-ttu-id="21fbe-127">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="21fbe-127">Checks whether the headers contain an entry matching the header name.</span></span>

> <span data-ttu-id="21fbe-128">public bool [Contains](#contains)(文字列 name)</span><span class="sxs-lookup"><span data-stu-id="21fbe-128">public bool [Contains](#contains)(string name)</span></span>

#### <span data-ttu-id="21fbe-129">GetHeader</span><span class="sxs-lookup"><span data-stu-id="21fbe-129">GetHeader</span></span> 

<span data-ttu-id="21fbe-130">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="21fbe-130">Gets the header value matching the name.</span></span>

> <span data-ttu-id="21fbe-131">パブリック文字列 [GetHeader](#getheader)(文字列名)</span><span class="sxs-lookup"><span data-stu-id="21fbe-131">public string [GetHeader](#getheader)(string name)</span></span>

#### <span data-ttu-id="21fbe-132">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="21fbe-132">GetHeaders</span></span> 

<span data-ttu-id="21fbe-133">名前に一致するヘッダー値をイテレータを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="21fbe-133">Gets the header value matching the name via an iterator.</span></span>

> <span data-ttu-id="21fbe-134">パブリック CoreWebView2HttpHeadersCollectionIterator [GetHeaders](#getheaders)(文字列名)</span><span class="sxs-lookup"><span data-stu-id="21fbe-134">public CoreWebView2HttpHeadersCollectionIterator [GetHeaders](#getheaders)(string name)</span></span>

#### <span data-ttu-id="21fbe-135">GetIterator</span><span class="sxs-lookup"><span data-stu-id="21fbe-135">GetIterator</span></span> 

<span data-ttu-id="21fbe-136">要求ヘッダーのコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="21fbe-136">Gets an iterator over the collection of request headers.</span></span>

> <span data-ttu-id="21fbe-137">パブリック CoreWebView2HttpHeadersCollectionIterator [Getiterator](#getiterator)()</span><span class="sxs-lookup"><span data-stu-id="21fbe-137">public CoreWebView2HttpHeadersCollectionIterator [GetIterator](#getiterator)()</span></span>

#### <span data-ttu-id="21fbe-138">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="21fbe-138">RemoveHeader</span></span> 

<span data-ttu-id="21fbe-139">名前に一致するヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="21fbe-139">Removes header that matches the name.</span></span>

> <span data-ttu-id="21fbe-140">パブリック void [Removeheader](#removeheader)(文字列名)</span><span class="sxs-lookup"><span data-stu-id="21fbe-140">public void [RemoveHeader](#removeheader)(string name)</span></span>

#### <span data-ttu-id="21fbe-141">SetHeader</span><span class="sxs-lookup"><span data-stu-id="21fbe-141">SetHeader</span></span> 

<span data-ttu-id="21fbe-142">名前に一致するヘッダーを追加または更新します。</span><span class="sxs-lookup"><span data-stu-id="21fbe-142">Adds or updates header that matches the name.</span></span>

> <span data-ttu-id="21fbe-143">パブリック void [SetHeader](#setheader)(文字列名、文字列値)</span><span class="sxs-lookup"><span data-stu-id="21fbe-143">public void [SetHeader](#setheader)(string name, string value)</span></span>

