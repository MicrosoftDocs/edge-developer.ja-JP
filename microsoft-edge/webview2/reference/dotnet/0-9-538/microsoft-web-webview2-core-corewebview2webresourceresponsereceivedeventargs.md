---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2WebResourceResponseReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2WebResourceResponseReceivedEventArgs。
ms.openlocfilehash: 44fc4f47aa10a7e409ac584cb75b750048056e47
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886528"
---
# <span data-ttu-id="1c9a4-104">WebView2 クラス (CoreWebView2WebResourceResponseReceivedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="1c9a4-104">Microsoft.Web.WebView2.Core.CoreWebView2WebResourceResponseReceivedEventArgs class</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="1c9a4-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="1c9a4-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="1c9a4-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="1c9a4-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="1c9a4-107">WebResourceResponseReceived イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="1c9a4-107">Event args for the WebResourceResponseReceived event.</span></span>

## <span data-ttu-id="1c9a4-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="1c9a4-108">Summary</span></span>

 <span data-ttu-id="1c9a4-109">Members</span><span class="sxs-lookup"><span data-stu-id="1c9a4-109">Members</span></span>                        | <span data-ttu-id="1c9a4-110">説明</span><span class="sxs-lookup"><span data-stu-id="1c9a4-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="1c9a4-111">要求</span><span class="sxs-lookup"><span data-stu-id="1c9a4-111">Request</span></span>](#request) | <span data-ttu-id="1c9a4-112">Web リソース要求オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1c9a4-112">Web resource request object.</span></span>
[<span data-ttu-id="1c9a4-113">応答</span><span class="sxs-lookup"><span data-stu-id="1c9a4-113">Response</span></span>](#response) | <span data-ttu-id="1c9a4-114">Web リソース応答オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1c9a4-114">Web resource response object.</span></span>
[<span data-ttu-id="1c9a4-115">PopulateResponseContentAsync</span><span class="sxs-lookup"><span data-stu-id="1c9a4-115">PopulateResponseContentAsync</span></span>](#populateresponsecontentasync) | <span data-ttu-id="1c9a4-116">応答のコンテンツストリームを要求する Async メソッド。</span><span class="sxs-lookup"><span data-stu-id="1c9a4-116">Async method to request the Content stream of the response.</span></span>

## <span data-ttu-id="1c9a4-117">Members</span><span class="sxs-lookup"><span data-stu-id="1c9a4-117">Members</span></span>

#### <span data-ttu-id="1c9a4-118">要求</span><span class="sxs-lookup"><span data-stu-id="1c9a4-118">Request</span></span> 

<span data-ttu-id="1c9a4-119">Web リソース要求オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1c9a4-119">Web resource request object.</span></span>

> <span data-ttu-id="1c9a4-120">パブリック HttpRequestMessage[要求](#request)</span><span class="sxs-lookup"><span data-stu-id="1c9a4-120">public HttpRequestMessage [Request](#request)</span></span>

<span data-ttu-id="1c9a4-121">このオブジェクトに加えた変更はすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="1c9a4-121">Any modifications to this object will be ignored.</span></span>

#### <span data-ttu-id="1c9a4-122">応答</span><span class="sxs-lookup"><span data-stu-id="1c9a4-122">Response</span></span> 

<span data-ttu-id="1c9a4-123">Web リソース応答オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1c9a4-123">Web resource response object.</span></span>

> <span data-ttu-id="1c9a4-124">パブリック HttpResponseMessage[応答](#response)</span><span class="sxs-lookup"><span data-stu-id="1c9a4-124">public HttpResponseMessage [Response](#response)</span></span>

<span data-ttu-id="1c9a4-125">このオブジェクトに加えた変更はすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="1c9a4-125">Any modifications to this object will be ignored.</span></span>

#### <span data-ttu-id="1c9a4-126">PopulateResponseContentAsync</span><span class="sxs-lookup"><span data-stu-id="1c9a4-126">PopulateResponseContentAsync</span></span> 

<span data-ttu-id="1c9a4-127">応答のコンテンツストリームを要求する Async メソッド。</span><span class="sxs-lookup"><span data-stu-id="1c9a4-127">Async method to request the Content stream of the response.</span></span>

> <span data-ttu-id="1c9a4-128">パブリック async Task [PopulateResponseContentAsync](#populateresponsecontentasync)()</span><span class="sxs-lookup"><span data-stu-id="1c9a4-128">public async Task [PopulateResponseContentAsync](#populateresponsecontentasync)()</span></span>

