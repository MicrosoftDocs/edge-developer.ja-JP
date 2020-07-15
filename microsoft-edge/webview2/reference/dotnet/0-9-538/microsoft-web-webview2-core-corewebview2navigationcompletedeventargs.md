---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2NavigationCompletedEventArgs。
ms.openlocfilehash: aaaad1f622887ed1c941a9cf12ee4c753b352286
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878884"
---
# <span data-ttu-id="a8e30-104">WebView2 クラス (CoreWebView2NavigationCompletedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="a8e30-104">Microsoft.Web.WebView2.Core.CoreWebView2NavigationCompletedEventArgs class</span></span> 

<span data-ttu-id="a8e30-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="a8e30-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="a8e30-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="a8e30-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="a8e30-107">NavigationCompleted イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="a8e30-107">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="a8e30-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="a8e30-108">Summary</span></span>

 <span data-ttu-id="a8e30-109">Members</span><span class="sxs-lookup"><span data-stu-id="a8e30-109">Members</span></span>                        | <span data-ttu-id="a8e30-110">説明</span><span class="sxs-lookup"><span data-stu-id="a8e30-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a8e30-111">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="a8e30-111">IsSuccess</span></span>](#issuccess) | <span data-ttu-id="a8e30-112">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="a8e30-112">True when the navigation is successful.</span></span>
[<span data-ttu-id="a8e30-113">NavigationId</span><span class="sxs-lookup"><span data-stu-id="a8e30-113">NavigationId</span></span>](#navigationid) | <span data-ttu-id="a8e30-114">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="a8e30-114">The ID of the navigation.</span></span>
[<span data-ttu-id="a8e30-115">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="a8e30-115">WebErrorStatus</span></span>](#weberrorstatus) | <span data-ttu-id="a8e30-116">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="a8e30-116">The error code if the navigation failed.</span></span>

## <span data-ttu-id="a8e30-117">Members</span><span class="sxs-lookup"><span data-stu-id="a8e30-117">Members</span></span>

#### <span data-ttu-id="a8e30-118">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="a8e30-118">IsSuccess</span></span> 

<span data-ttu-id="a8e30-119">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="a8e30-119">True when the navigation is successful.</span></span>

> <span data-ttu-id="a8e30-120">公開ブール[値](#issuccess)</span><span class="sxs-lookup"><span data-stu-id="a8e30-120">public bool [IsSuccess](#issuccess)</span></span>

<span data-ttu-id="a8e30-121">これは、エラーページ内で終了するナビゲーション (ネットワークがない、DNS 参照エラー、HTTP server が4xx で応答する) でも、また、移動ページで呼び出された window. stop () などの追加機能については、false になります。</span><span class="sxs-lookup"><span data-stu-id="a8e30-121">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="a8e30-122">NavigationId</span><span class="sxs-lookup"><span data-stu-id="a8e30-122">NavigationId</span></span> 

<span data-ttu-id="a8e30-123">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="a8e30-123">The ID of the navigation.</span></span>

> <span data-ttu-id="a8e30-124">パブリック ulong [Navigationid](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="a8e30-124">public ulong [NavigationId](#navigationid)</span></span>

#### <span data-ttu-id="a8e30-125">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="a8e30-125">WebErrorStatus</span></span> 

<span data-ttu-id="a8e30-126">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="a8e30-126">The error code if the navigation failed.</span></span>

> <span data-ttu-id="a8e30-127">パブリック CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span><span class="sxs-lookup"><span data-stu-id="a8e30-127">public CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span></span>

