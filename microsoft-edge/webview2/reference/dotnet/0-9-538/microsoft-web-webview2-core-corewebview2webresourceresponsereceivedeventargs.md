---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 (CoreWebView2WebResourceResponseReceivedEventArgs の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2WebResourceResponseReceivedEventArgs。
ms.openlocfilehash: a8c988fdfee72ed22e74886b440819d7a9d6fe24
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010512"
---
# <span data-ttu-id="47f7e-104">0.9.579 クラスの WebView2 クラス (CoreWebView2WebResourceResponseReceivedEventArgs)</span><span class="sxs-lookup"><span data-stu-id="47f7e-104">0.9.579 - Microsoft.Web.WebView2.Core.CoreWebView2WebResourceResponseReceivedEventArgs class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="47f7e-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="47f7e-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="47f7e-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="47f7e-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="47f7e-107">WebResourceResponseReceived イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="47f7e-107">Event args for the WebResourceResponseReceived event.</span></span>

## <span data-ttu-id="47f7e-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="47f7e-108">Summary</span></span>

 <span data-ttu-id="47f7e-109">Members</span><span class="sxs-lookup"><span data-stu-id="47f7e-109">Members</span></span>                        | <span data-ttu-id="47f7e-110">説明</span><span class="sxs-lookup"><span data-stu-id="47f7e-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="47f7e-111">要求</span><span class="sxs-lookup"><span data-stu-id="47f7e-111">Request</span></span>](#request) | <span data-ttu-id="47f7e-112">Web リソース要求オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="47f7e-112">Web resource request object.</span></span>
[<span data-ttu-id="47f7e-113">応答</span><span class="sxs-lookup"><span data-stu-id="47f7e-113">Response</span></span>](#response) | <span data-ttu-id="47f7e-114">Web リソース応答オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="47f7e-114">Web resource response object.</span></span>
[<span data-ttu-id="47f7e-115">PopulateResponseContentAsync</span><span class="sxs-lookup"><span data-stu-id="47f7e-115">PopulateResponseContentAsync</span></span>](#populateresponsecontentasync) | <span data-ttu-id="47f7e-116">応答のコンテンツストリームを要求する Async メソッド。</span><span class="sxs-lookup"><span data-stu-id="47f7e-116">Async method to request the Content stream of the response.</span></span>

## <span data-ttu-id="47f7e-117">Members</span><span class="sxs-lookup"><span data-stu-id="47f7e-117">Members</span></span>

#### <span data-ttu-id="47f7e-118">要求</span><span class="sxs-lookup"><span data-stu-id="47f7e-118">Request</span></span> 

<span data-ttu-id="47f7e-119">Web リソース要求オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="47f7e-119">Web resource request object.</span></span>

> <span data-ttu-id="47f7e-120">パブリック HttpRequestMessage [要求](#request)</span><span class="sxs-lookup"><span data-stu-id="47f7e-120">public HttpRequestMessage [Request](#request)</span></span>

<span data-ttu-id="47f7e-121">このオブジェクトに加えた変更はすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="47f7e-121">Any modifications to this object will be ignored.</span></span>

#### <span data-ttu-id="47f7e-122">応答</span><span class="sxs-lookup"><span data-stu-id="47f7e-122">Response</span></span> 

<span data-ttu-id="47f7e-123">Web リソース応答オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="47f7e-123">Web resource response object.</span></span>

> <span data-ttu-id="47f7e-124">パブリック HttpResponseMessage [応答](#response)</span><span class="sxs-lookup"><span data-stu-id="47f7e-124">public HttpResponseMessage [Response](#response)</span></span>

<span data-ttu-id="47f7e-125">このオブジェクトに加えた変更はすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="47f7e-125">Any modifications to this object will be ignored.</span></span>

#### <span data-ttu-id="47f7e-126">PopulateResponseContentAsync</span><span class="sxs-lookup"><span data-stu-id="47f7e-126">PopulateResponseContentAsync</span></span> 

<span data-ttu-id="47f7e-127">応答のコンテンツストリームを要求する Async メソッド。</span><span class="sxs-lookup"><span data-stu-id="47f7e-127">Async method to request the Content stream of the response.</span></span>

> <span data-ttu-id="47f7e-128">パブリック async Task [PopulateResponseContentAsync](#populateresponsecontentasync)()</span><span class="sxs-lookup"><span data-stu-id="47f7e-128">public async Task [PopulateResponseContentAsync](#populateresponsecontentasync)()</span></span>

