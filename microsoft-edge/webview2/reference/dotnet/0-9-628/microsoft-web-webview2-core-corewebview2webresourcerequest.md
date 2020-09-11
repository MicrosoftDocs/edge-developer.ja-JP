---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2WebResourceRequest
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2WebResourceRequest。
ms.openlocfilehash: 5c8d164b24995cc31070232dd9b1a2d88fc16cec
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012239"
---
# <span data-ttu-id="3d950-104">WebView2 クラス (CoreWebView2WebResourceRequest クラス)</span><span class="sxs-lookup"><span data-stu-id="3d950-104">Microsoft.Web.WebView2.Core.CoreWebView2WebResourceRequest class</span></span> 

<span data-ttu-id="3d950-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="3d950-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="3d950-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="3d950-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="3d950-107">WebResourceRequested イベントと共に使用される HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="3d950-107">An HTTP request used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="3d950-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="3d950-108">Summary</span></span>

 <span data-ttu-id="3d950-109">Members</span><span class="sxs-lookup"><span data-stu-id="3d950-109">Members</span></span>                        | <span data-ttu-id="3d950-110">説明</span><span class="sxs-lookup"><span data-stu-id="3d950-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3d950-111">コンテンツ</span><span class="sxs-lookup"><span data-stu-id="3d950-111">Content</span></span>](#content) | <span data-ttu-id="3d950-112">HTTP 要求メッセージ本文をストリームとして送信します。</span><span class="sxs-lookup"><span data-stu-id="3d950-112">The HTTP request message body as stream.</span></span>
[<span data-ttu-id="3d950-113">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="3d950-113">Headers</span></span>](#headers) | <span data-ttu-id="3d950-114">変更可能な HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="3d950-114">The mutable HTTP request headers.</span></span>
[<span data-ttu-id="3d950-115">メソッド</span><span class="sxs-lookup"><span data-stu-id="3d950-115">Method</span></span>](#method) | <span data-ttu-id="3d950-116">HTTP 要求メソッド。</span><span class="sxs-lookup"><span data-stu-id="3d950-116">The HTTP request method.</span></span>
[<span data-ttu-id="3d950-117">URI</span><span class="sxs-lookup"><span data-stu-id="3d950-117">Uri</span></span>](#uri) | <span data-ttu-id="3d950-118">要求 URI。</span><span class="sxs-lookup"><span data-stu-id="3d950-118">The request URI.</span></span>

## <span data-ttu-id="3d950-119">Members</span><span class="sxs-lookup"><span data-stu-id="3d950-119">Members</span></span>

#### <span data-ttu-id="3d950-120">コンテンツ</span><span class="sxs-lookup"><span data-stu-id="3d950-120">Content</span></span> 

<span data-ttu-id="3d950-121">HTTP 要求メッセージ本文をストリームとして送信します。</span><span class="sxs-lookup"><span data-stu-id="3d950-121">The HTTP request message body as stream.</span></span>

> <span data-ttu-id="3d950-122">パブリックストリーム [コンテンツ](#content)</span><span class="sxs-lookup"><span data-stu-id="3d950-122">public Stream [Content](#content)</span></span>

<span data-ttu-id="3d950-123">データの投稿はここにあります。</span><span class="sxs-lookup"><span data-stu-id="3d950-123">POST data would be here.</span></span> <span data-ttu-id="3d950-124">ストリームが設定されている場合は、メッセージ本文を上書きします。この応答の WebResourceRequested イベントの遅延が完了するまで、ストリームにはすべてのコンテンツデータが利用可能になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d950-124">If a stream is set, which will override the message body, the stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="3d950-125">UI スレッドへのパフォーマンスへの影響を防ぐために、Stream はバックグラウンド STA から作成したり、バックグラウンドで作成したりする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d950-125">Stream should be agile or be created from a background STA to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="3d950-126">Null はコンテンツデータがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="3d950-126">Null means no content data.</span></span> <span data-ttu-id="3d950-127">IStream セマンティクスが適用されます (すべてのデータが使い果たされるまで、S_OK は読み取り呼び出しに戻ります)。</span><span class="sxs-lookup"><span data-stu-id="3d950-127">IStream semantics apply (return S_OK to Read calls until all data is exhausted).</span></span>

#### <span data-ttu-id="3d950-128">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="3d950-128">Headers</span></span> 

<span data-ttu-id="3d950-129">変更可能な HTTP 要求ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="3d950-129">The mutable HTTP request headers.</span></span>

> <span data-ttu-id="3d950-130">パブリック [CoreWebView2HttpRequestHeaders](microsoft-web-webview2-core-corewebview2httprequestheaders.md) [ヘッダー](#headers)</span><span class="sxs-lookup"><span data-stu-id="3d950-130">public [CoreWebView2HttpRequestHeaders](microsoft-web-webview2-core-corewebview2httprequestheaders.md) [Headers](#headers)</span></span>

#### <span data-ttu-id="3d950-131">メソッド</span><span class="sxs-lookup"><span data-stu-id="3d950-131">Method</span></span> 

<span data-ttu-id="3d950-132">HTTP 要求メソッド。</span><span class="sxs-lookup"><span data-stu-id="3d950-132">The HTTP request method.</span></span>

> <span data-ttu-id="3d950-133">パブリック文字列 [メソッド](#method)</span><span class="sxs-lookup"><span data-stu-id="3d950-133">public string [Method](#method)</span></span>

#### <span data-ttu-id="3d950-134">URI</span><span class="sxs-lookup"><span data-stu-id="3d950-134">Uri</span></span> 

<span data-ttu-id="3d950-135">要求 URI。</span><span class="sxs-lookup"><span data-stu-id="3d950-135">The request URI.</span></span>

> <span data-ttu-id="3d950-136">パブリック文字列の [Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="3d950-136">public string [Uri](#uri)</span></span>

