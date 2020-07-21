---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (CoreWebView2NavigationCompletedEventArgs の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: e2e973e2ee1817decd24bbc1d0dc3daa9709795c
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885080"
---
# <span data-ttu-id="9d295-104">0.9.515 クラスの WebView2 クラス (CoreWebView2NavigationCompletedEventArgs)</span><span class="sxs-lookup"><span data-stu-id="9d295-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2NavigationCompletedEventArgs class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="9d295-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="9d295-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="9d295-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="9d295-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="9d295-107">NavigationCompleted イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="9d295-107">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="9d295-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="9d295-108">Summary</span></span>

 <span data-ttu-id="9d295-109">Members</span><span class="sxs-lookup"><span data-stu-id="9d295-109">Members</span></span>                        | <span data-ttu-id="9d295-110">説明</span><span class="sxs-lookup"><span data-stu-id="9d295-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9d295-111">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="9d295-111">IsSuccess</span></span>](#issuccess) | <span data-ttu-id="9d295-112">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="9d295-112">True when the navigation is successful.</span></span>
[<span data-ttu-id="9d295-113">NavigationId</span><span class="sxs-lookup"><span data-stu-id="9d295-113">NavigationId</span></span>](#navigationid) | <span data-ttu-id="9d295-114">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="9d295-114">The ID of the navigation.</span></span>
[<span data-ttu-id="9d295-115">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="9d295-115">WebErrorStatus</span></span>](#weberrorstatus) | <span data-ttu-id="9d295-116">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="9d295-116">The error code if the navigation failed.</span></span>

## <span data-ttu-id="9d295-117">Members</span><span class="sxs-lookup"><span data-stu-id="9d295-117">Members</span></span>

#### <span data-ttu-id="9d295-118">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="9d295-118">IsSuccess</span></span> 

<span data-ttu-id="9d295-119">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="9d295-119">True when the navigation is successful.</span></span>

> <span data-ttu-id="9d295-120">公開ブール[値](#issuccess)</span><span class="sxs-lookup"><span data-stu-id="9d295-120">public bool [IsSuccess](#issuccess)</span></span>

<span data-ttu-id="9d295-121">これは、エラーページ内で終了するナビゲーション (ネットワークがない、DNS 参照エラー、HTTP server が4xx で応答する) でも、また、移動ページで呼び出された window. stop () などの追加機能については、false になります。</span><span class="sxs-lookup"><span data-stu-id="9d295-121">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="9d295-122">NavigationId</span><span class="sxs-lookup"><span data-stu-id="9d295-122">NavigationId</span></span> 

<span data-ttu-id="9d295-123">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="9d295-123">The ID of the navigation.</span></span>

> <span data-ttu-id="9d295-124">パブリック ulong [Navigationid](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="9d295-124">public ulong [NavigationId](#navigationid)</span></span>

#### <span data-ttu-id="9d295-125">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="9d295-125">WebErrorStatus</span></span> 

<span data-ttu-id="9d295-126">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="9d295-126">The error code if the navigation failed.</span></span>

> <span data-ttu-id="9d295-127">パブリック CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span><span class="sxs-lookup"><span data-stu-id="9d295-127">public CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span></span>

