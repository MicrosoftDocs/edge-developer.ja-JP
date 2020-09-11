---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2HttpResponseHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2HttpResponseHeaders。
ms.openlocfilehash: 51218283460975421859c65da8a43553767ad216
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012282"
---
# <span data-ttu-id="7180d-104">WebView2 クラス (CoreWebView2HttpResponseHeaders クラス)</span><span class="sxs-lookup"><span data-stu-id="7180d-104">Microsoft.Web.WebView2.Core.CoreWebView2HttpResponseHeaders class</span></span> 

<span data-ttu-id="7180d-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="7180d-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="7180d-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="7180d-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="7180d-107">HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="7180d-107">HTTP response headers.</span></span>

## <span data-ttu-id="7180d-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="7180d-108">Summary</span></span>

 <span data-ttu-id="7180d-109">Members</span><span class="sxs-lookup"><span data-stu-id="7180d-109">Members</span></span>                        | <span data-ttu-id="7180d-110">説明</span><span class="sxs-lookup"><span data-stu-id="7180d-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="7180d-111">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="7180d-111">AppendHeader</span></span>](#appendheader) | <span data-ttu-id="7180d-112">名前と値が含まれるヘッダー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="7180d-112">Appends header line with name and value.</span></span>
[<span data-ttu-id="7180d-113">Contains</span><span class="sxs-lookup"><span data-stu-id="7180d-113">Contains</span></span>](#contains) | <span data-ttu-id="7180d-114">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7180d-114">Checks whether the headers contain entries matching the header name.</span></span>
[<span data-ttu-id="7180d-115">GetHeader</span><span class="sxs-lookup"><span data-stu-id="7180d-115">GetHeader</span></span>](#getheader) | <span data-ttu-id="7180d-116">名前に一致するコレクションの最初のヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="7180d-116">Gets the first header value in the collection matching the name.</span></span>
[<span data-ttu-id="7180d-117">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="7180d-117">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="7180d-118">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="7180d-118">Gets the header values matching the name.</span></span>
[<span data-ttu-id="7180d-119">GetIterator</span><span class="sxs-lookup"><span data-stu-id="7180d-119">GetIterator</span></span>](#getiterator) | <span data-ttu-id="7180d-120">応答ヘッダー全体のコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="7180d-120">Gets an iterator over the collection of entire response headers.</span></span>

<span data-ttu-id="7180d-121">WebResourceRequested イベントの WebResourceResponse を作成するために使われます。</span><span class="sxs-lookup"><span data-stu-id="7180d-121">Used to construct a WebResourceResponse for the WebResourceRequested event.</span></span>

## <span data-ttu-id="7180d-122">Members</span><span class="sxs-lookup"><span data-stu-id="7180d-122">Members</span></span>

#### <span data-ttu-id="7180d-123">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="7180d-123">AppendHeader</span></span> 

<span data-ttu-id="7180d-124">名前と値が含まれるヘッダー行を追加します。</span><span class="sxs-lookup"><span data-stu-id="7180d-124">Appends header line with name and value.</span></span>

> <span data-ttu-id="7180d-125">パブリック void [Appendheader](#appendheader)(文字列名、文字列値)</span><span class="sxs-lookup"><span data-stu-id="7180d-125">public void [AppendHeader](#appendheader)(string name, string value)</span></span>

#### <span data-ttu-id="7180d-126">Contains</span><span class="sxs-lookup"><span data-stu-id="7180d-126">Contains</span></span> 

<span data-ttu-id="7180d-127">ヘッダー名に一致するエントリがヘッダーに含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7180d-127">Checks whether the headers contain entries matching the header name.</span></span>

> <span data-ttu-id="7180d-128">public bool [Contains](#contains)(文字列 name)</span><span class="sxs-lookup"><span data-stu-id="7180d-128">public bool [Contains](#contains)(string name)</span></span>

#### <span data-ttu-id="7180d-129">GetHeader</span><span class="sxs-lookup"><span data-stu-id="7180d-129">GetHeader</span></span> 

<span data-ttu-id="7180d-130">名前に一致するコレクションの最初のヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="7180d-130">Gets the first header value in the collection matching the name.</span></span>

> <span data-ttu-id="7180d-131">パブリック文字列 [GetHeader](#getheader)(文字列名)</span><span class="sxs-lookup"><span data-stu-id="7180d-131">public string [GetHeader](#getheader)(string name)</span></span>

#### <span data-ttu-id="7180d-132">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="7180d-132">GetHeaders</span></span> 

<span data-ttu-id="7180d-133">名前に一致するヘッダー値を取得します。</span><span class="sxs-lookup"><span data-stu-id="7180d-133">Gets the header values matching the name.</span></span>

> <span data-ttu-id="7180d-134">パブリック CoreWebView2HttpHeadersCollectionIterator [GetHeaders](#getheaders)(文字列名)</span><span class="sxs-lookup"><span data-stu-id="7180d-134">public CoreWebView2HttpHeadersCollectionIterator [GetHeaders](#getheaders)(string name)</span></span>

#### <span data-ttu-id="7180d-135">GetIterator</span><span class="sxs-lookup"><span data-stu-id="7180d-135">GetIterator</span></span> 

<span data-ttu-id="7180d-136">応答ヘッダー全体のコレクションに対する反復子を取得します。</span><span class="sxs-lookup"><span data-stu-id="7180d-136">Gets an iterator over the collection of entire response headers.</span></span>

> <span data-ttu-id="7180d-137">パブリック CoreWebView2HttpHeadersCollectionIterator [Getiterator](#getiterator)()</span><span class="sxs-lookup"><span data-stu-id="7180d-137">public CoreWebView2HttpHeadersCollectionIterator [GetIterator](#getiterator)()</span></span>

