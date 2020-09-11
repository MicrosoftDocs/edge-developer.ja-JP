---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2WebResourceResponse
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2WebResourceResponse。
ms.openlocfilehash: 5359634d83717ce844d2c1604a2645ceffc477cc
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012235"
---
# <span data-ttu-id="8bce1-104">WebView2 クラス (CoreWebView2WebResourceResponse クラス)</span><span class="sxs-lookup"><span data-stu-id="8bce1-104">Microsoft.Web.WebView2.Core.CoreWebView2WebResourceResponse class</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="8bce1-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="8bce1-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="8bce1-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="8bce1-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="8bce1-107">WebResourceRequested イベントと共に使用される HTTP 応答。</span><span class="sxs-lookup"><span data-stu-id="8bce1-107">An HTTP response used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="8bce1-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="8bce1-108">Summary</span></span>

 <span data-ttu-id="8bce1-109">Members</span><span class="sxs-lookup"><span data-stu-id="8bce1-109">Members</span></span>                        | <span data-ttu-id="8bce1-110">説明</span><span class="sxs-lookup"><span data-stu-id="8bce1-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="8bce1-111">コンテンツ</span><span class="sxs-lookup"><span data-stu-id="8bce1-111">Content</span></span>](#content) | <span data-ttu-id="8bce1-112">ストリームとしての HTTP 応答のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="8bce1-112">HTTP response content as stream.</span></span>
[<span data-ttu-id="8bce1-113">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="8bce1-113">Headers</span></span>](#headers) | <span data-ttu-id="8bce1-114">上書きされた HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="8bce1-114">Overridden HTTP response headers.</span></span>
[<span data-ttu-id="8bce1-115">理由語句</span><span class="sxs-lookup"><span data-stu-id="8bce1-115">ReasonPhrase</span></span>](#reasonphrase) | <span data-ttu-id="8bce1-116">HTTP 応答の理由の語句。</span><span class="sxs-lookup"><span data-stu-id="8bce1-116">The HTTP response reason phrase.</span></span>
[<span data-ttu-id="8bce1-117">StatusCode</span><span class="sxs-lookup"><span data-stu-id="8bce1-117">StatusCode</span></span>](#statuscode) | <span data-ttu-id="8bce1-118">HTTP 応答状態コード。</span><span class="sxs-lookup"><span data-stu-id="8bce1-118">The HTTP response status code.</span></span>

## <span data-ttu-id="8bce1-119">Members</span><span class="sxs-lookup"><span data-stu-id="8bce1-119">Members</span></span>

#### <span data-ttu-id="8bce1-120">コンテンツ</span><span class="sxs-lookup"><span data-stu-id="8bce1-120">Content</span></span> 

<span data-ttu-id="8bce1-121">ストリームとしての HTTP 応答のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="8bce1-121">HTTP response content as stream.</span></span>

> <span data-ttu-id="8bce1-122">パブリックストリーム [コンテンツ](#content)</span><span class="sxs-lookup"><span data-stu-id="8bce1-122">public Stream [Content](#content)</span></span>

<span data-ttu-id="8bce1-123">この応答の WebResourceRequested イベントの遅延が完了するまで、ストリームにはすべてのコンテンツデータが利用可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bce1-123">Stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="8bce1-124">UI スレッドに対するパフォーマンスへの影響を防ぐには、ストリームをアジャイルにするか、バックグラウンドスレッドから作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bce1-124">Stream should be agile or be created from a background thread to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="8bce1-125">Null はコンテンツデータがないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="8bce1-125">Null means no content data.</span></span> <span data-ttu-id="8bce1-126">IStream セマンティクスが適用されます (すべてのデータが使い果たされるまで、S_OK は読み取り呼び出しに戻ります)。</span><span class="sxs-lookup"><span data-stu-id="8bce1-126">IStream semantics apply (return S_OK to Read calls until all data is exhausted).</span></span>

#### <span data-ttu-id="8bce1-127">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="8bce1-127">Headers</span></span> 

<span data-ttu-id="8bce1-128">上書きされた HTTP 応答ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="8bce1-128">Overridden HTTP response headers.</span></span>

> <span data-ttu-id="8bce1-129">パブリック [CoreWebView2HttpResponseHeaders](microsoft-web-webview2-core-corewebview2httpresponseheaders.md) [ヘッダー](#headers)</span><span class="sxs-lookup"><span data-stu-id="8bce1-129">public [CoreWebView2HttpResponseHeaders](microsoft-web-webview2-core-corewebview2httpresponseheaders.md) [Headers](#headers)</span></span>

#### <span data-ttu-id="8bce1-130">理由語句</span><span class="sxs-lookup"><span data-stu-id="8bce1-130">ReasonPhrase</span></span> 

<span data-ttu-id="8bce1-131">HTTP 応答の理由の語句。</span><span class="sxs-lookup"><span data-stu-id="8bce1-131">The HTTP response reason phrase.</span></span>

> <span data-ttu-id="8bce1-132">パブリック文字列の [理由語句](#reasonphrase)</span><span class="sxs-lookup"><span data-stu-id="8bce1-132">public string [ReasonPhrase](#reasonphrase)</span></span>

#### <span data-ttu-id="8bce1-133">StatusCode</span><span class="sxs-lookup"><span data-stu-id="8bce1-133">StatusCode</span></span> 

<span data-ttu-id="8bce1-134">HTTP 応答状態コード。</span><span class="sxs-lookup"><span data-stu-id="8bce1-134">The HTTP response status code.</span></span>

> <span data-ttu-id="8bce1-135">パブリック int の [StatusCode](#statuscode)</span><span class="sxs-lookup"><span data-stu-id="8bce1-135">public int [StatusCode](#statuscode)</span></span>

