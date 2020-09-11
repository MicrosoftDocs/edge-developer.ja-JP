---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2WebResourceResponseReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2WebResourceResponseReceivedEventArgs。
ms.openlocfilehash: 2d0660616de0c234b1535b2af127843fea3a3a53
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012233"
---
# <span data-ttu-id="8a328-104">WebView2 クラス (CoreWebView2WebResourceResponseReceivedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="8a328-104">Microsoft.Web.WebView2.Core.CoreWebView2WebResourceResponseReceivedEventArgs class</span></span> 

<span data-ttu-id="8a328-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="8a328-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="8a328-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="8a328-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="8a328-107">WebResourceResponseReceived イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="8a328-107">Event args for the WebResourceResponseReceived event.</span></span>

## <span data-ttu-id="8a328-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="8a328-108">Summary</span></span>

 <span data-ttu-id="8a328-109">Members</span><span class="sxs-lookup"><span data-stu-id="8a328-109">Members</span></span>                        | <span data-ttu-id="8a328-110">説明</span><span class="sxs-lookup"><span data-stu-id="8a328-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="8a328-111">要求</span><span class="sxs-lookup"><span data-stu-id="8a328-111">Request</span></span>](#request) | <span data-ttu-id="8a328-112">Web リソース要求オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="8a328-112">Web resource request object.</span></span>
[<span data-ttu-id="8a328-113">応答</span><span class="sxs-lookup"><span data-stu-id="8a328-113">Response</span></span>](#response) | <span data-ttu-id="8a328-114">Web リソース応答オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="8a328-114">Web resource response object.</span></span>
[<span data-ttu-id="8a328-115">PopulateResponseContentAsync</span><span class="sxs-lookup"><span data-stu-id="8a328-115">PopulateResponseContentAsync</span></span>](#populateresponsecontentasync) | <span data-ttu-id="8a328-116">応答のコンテンツストリームを要求する Async メソッド。</span><span class="sxs-lookup"><span data-stu-id="8a328-116">Async method to request the Content stream of the response.</span></span>

## <span data-ttu-id="8a328-117">Members</span><span class="sxs-lookup"><span data-stu-id="8a328-117">Members</span></span>

#### <span data-ttu-id="8a328-118">要求</span><span class="sxs-lookup"><span data-stu-id="8a328-118">Request</span></span> 

<span data-ttu-id="8a328-119">Web リソース要求オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="8a328-119">Web resource request object.</span></span>

> <span data-ttu-id="8a328-120">パブリック [CoreWebView2WebResourceRequest](microsoft-web-webview2-core-corewebview2webresourcerequest.md) [要求](#request)</span><span class="sxs-lookup"><span data-stu-id="8a328-120">public [CoreWebView2WebResourceRequest](microsoft-web-webview2-core-corewebview2webresourcerequest.md) [Request](#request)</span></span>

<span data-ttu-id="8a328-121">このオブジェクトに加えた変更はすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="8a328-121">Any modifications to this object will be ignored.</span></span>

#### <span data-ttu-id="8a328-122">応答</span><span class="sxs-lookup"><span data-stu-id="8a328-122">Response</span></span> 

<span data-ttu-id="8a328-123">Web リソース応答オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="8a328-123">Web resource response object.</span></span>

> <span data-ttu-id="8a328-124">パブリック [CoreWebView2WebResourceResponse](microsoft-web-webview2-core-corewebview2webresourceresponse.md) [応答](#response)</span><span class="sxs-lookup"><span data-stu-id="8a328-124">public [CoreWebView2WebResourceResponse](microsoft-web-webview2-core-corewebview2webresourceresponse.md) [Response](#response)</span></span>

<span data-ttu-id="8a328-125">このオブジェクトに加えた変更はすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="8a328-125">Any modifications to this object will be ignored.</span></span>

#### <span data-ttu-id="8a328-126">PopulateResponseContentAsync</span><span class="sxs-lookup"><span data-stu-id="8a328-126">PopulateResponseContentAsync</span></span> 

<span data-ttu-id="8a328-127">応答のコンテンツストリームを要求する Async メソッド。</span><span class="sxs-lookup"><span data-stu-id="8a328-127">Async method to request the Content stream of the response.</span></span>

> <span data-ttu-id="8a328-128">パブリック async Task [PopulateResponseContentAsync](#populateresponsecontentasync)()</span><span class="sxs-lookup"><span data-stu-id="8a328-128">public async Task [PopulateResponseContentAsync](#populateresponsecontentasync)()</span></span>

