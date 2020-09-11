---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2NavigationCompletedEventArgs。
ms.openlocfilehash: dfa6aedb10e60a2af15c7b098c479f8537d6c747
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012212"
---
# <span data-ttu-id="2dc1e-104">WebView2 クラス (CoreWebView2NavigationCompletedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="2dc1e-104">Microsoft.Web.WebView2.Core.CoreWebView2NavigationCompletedEventArgs class</span></span> 

<span data-ttu-id="2dc1e-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="2dc1e-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="2dc1e-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="2dc1e-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="2dc1e-107">NavigationCompleted イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="2dc1e-107">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="2dc1e-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="2dc1e-108">Summary</span></span>

 <span data-ttu-id="2dc1e-109">Members</span><span class="sxs-lookup"><span data-stu-id="2dc1e-109">Members</span></span>                        | <span data-ttu-id="2dc1e-110">説明</span><span class="sxs-lookup"><span data-stu-id="2dc1e-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2dc1e-111">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="2dc1e-111">IsSuccess</span></span>](#issuccess) | <span data-ttu-id="2dc1e-112">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="2dc1e-112">True when the navigation is successful.</span></span>
[<span data-ttu-id="2dc1e-113">NavigationId</span><span class="sxs-lookup"><span data-stu-id="2dc1e-113">NavigationId</span></span>](#navigationid) | <span data-ttu-id="2dc1e-114">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="2dc1e-114">The ID of the navigation.</span></span>
[<span data-ttu-id="2dc1e-115">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="2dc1e-115">WebErrorStatus</span></span>](#weberrorstatus) | <span data-ttu-id="2dc1e-116">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="2dc1e-116">The error code if the navigation failed.</span></span>

## <span data-ttu-id="2dc1e-117">Members</span><span class="sxs-lookup"><span data-stu-id="2dc1e-117">Members</span></span>

#### <span data-ttu-id="2dc1e-118">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="2dc1e-118">IsSuccess</span></span> 

<span data-ttu-id="2dc1e-119">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="2dc1e-119">True when the navigation is successful.</span></span>

> <span data-ttu-id="2dc1e-120">公開ブール [値](#issuccess)</span><span class="sxs-lookup"><span data-stu-id="2dc1e-120">public bool [IsSuccess](#issuccess)</span></span>

<span data-ttu-id="2dc1e-121">これは、エラーページ内で終了するナビゲーション (ネットワークがない、DNS 参照エラー、HTTP server が4xx で応答する) でも、その他のシナリオ (たとえば、移動中のページで呼び出された window. stop () など) では、false になります。</span><span class="sxs-lookup"><span data-stu-id="2dc1e-121">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional scenarios such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="2dc1e-122">NavigationId</span><span class="sxs-lookup"><span data-stu-id="2dc1e-122">NavigationId</span></span> 

<span data-ttu-id="2dc1e-123">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="2dc1e-123">The ID of the navigation.</span></span>

> <span data-ttu-id="2dc1e-124">パブリック ulong [Navigationid](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="2dc1e-124">public ulong [NavigationId](#navigationid)</span></span>

#### <span data-ttu-id="2dc1e-125">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="2dc1e-125">WebErrorStatus</span></span> 

<span data-ttu-id="2dc1e-126">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="2dc1e-126">The error code if the navigation failed.</span></span>

> <span data-ttu-id="2dc1e-127">パブリック CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span><span class="sxs-lookup"><span data-stu-id="2dc1e-127">public CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span></span>

