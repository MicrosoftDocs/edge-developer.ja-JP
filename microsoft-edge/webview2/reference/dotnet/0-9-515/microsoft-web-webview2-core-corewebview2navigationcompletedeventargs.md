---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 2a18fe9f8f79a109047d029affab8d84a6ef845c
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654180"
---
# <span data-ttu-id="45208-104">WebView2 クラス (CoreWebView2NavigationCompletedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="45208-104">Microsoft.Web.WebView2.Core.CoreWebView2NavigationCompletedEventArgs class</span></span> 

<span data-ttu-id="45208-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="45208-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="45208-106">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="45208-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="45208-107">NavigationCompleted イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="45208-107">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="45208-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="45208-108">Summary</span></span>

 <span data-ttu-id="45208-109">Members</span><span class="sxs-lookup"><span data-stu-id="45208-109">Members</span></span>                        | <span data-ttu-id="45208-110">説明</span><span class="sxs-lookup"><span data-stu-id="45208-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="45208-111">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="45208-111">IsSuccess</span></span>](#issuccess) | <span data-ttu-id="45208-112">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="45208-112">True when the navigation is successful.</span></span>
[<span data-ttu-id="45208-113">NavigationId</span><span class="sxs-lookup"><span data-stu-id="45208-113">NavigationId</span></span>](#navigationid) | <span data-ttu-id="45208-114">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="45208-114">The ID of the navigation.</span></span>
[<span data-ttu-id="45208-115">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="45208-115">WebErrorStatus</span></span>](#weberrorstatus) | <span data-ttu-id="45208-116">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="45208-116">The error code if the navigation failed.</span></span>

## <span data-ttu-id="45208-117">Members</span><span class="sxs-lookup"><span data-stu-id="45208-117">Members</span></span>

#### <span data-ttu-id="45208-118">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="45208-118">IsSuccess</span></span> 

<span data-ttu-id="45208-119">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="45208-119">True when the navigation is successful.</span></span>

> <span data-ttu-id="45208-120">公開ブール[値](#issuccess)</span><span class="sxs-lookup"><span data-stu-id="45208-120">public bool [IsSuccess](#issuccess)</span></span>

<span data-ttu-id="45208-121">これは、エラーページ内で終了するナビゲーション (ネットワークがない、DNS 参照エラー、HTTP server が4xx で応答する) でも、また、移動ページで呼び出された window. stop () などの追加機能については、false になります。</span><span class="sxs-lookup"><span data-stu-id="45208-121">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="45208-122">NavigationId</span><span class="sxs-lookup"><span data-stu-id="45208-122">NavigationId</span></span> 

<span data-ttu-id="45208-123">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="45208-123">The ID of the navigation.</span></span>

> <span data-ttu-id="45208-124">パブリック ulong [Navigationid](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="45208-124">public ulong [NavigationId](#navigationid)</span></span>

#### <span data-ttu-id="45208-125">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="45208-125">WebErrorStatus</span></span> 

<span data-ttu-id="45208-126">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="45208-126">The error code if the navigation failed.</span></span>

> <span data-ttu-id="45208-127">パブリック CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span><span class="sxs-lookup"><span data-stu-id="45208-127">public CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span></span>

