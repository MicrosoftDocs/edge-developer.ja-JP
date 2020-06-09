---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: c82c37d7127d69700f35fbf9e2a69f85159a7109
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698979"
---
# <span data-ttu-id="9ad09-104">WebView2 クラス (CoreWebView2NavigationCompletedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="9ad09-104">Microsoft.Web.WebView2.Core.CoreWebView2NavigationCompletedEventArgs class</span></span> 

<span data-ttu-id="9ad09-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="9ad09-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="9ad09-106">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="9ad09-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="9ad09-107">NavigationCompleted イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="9ad09-107">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="9ad09-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="9ad09-108">Summary</span></span>

 <span data-ttu-id="9ad09-109">Members</span><span class="sxs-lookup"><span data-stu-id="9ad09-109">Members</span></span>                        | <span data-ttu-id="9ad09-110">説明</span><span class="sxs-lookup"><span data-stu-id="9ad09-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9ad09-111">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="9ad09-111">IsSuccess</span></span>](#issuccess) | <span data-ttu-id="9ad09-112">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="9ad09-112">True when the navigation is successful.</span></span>
[<span data-ttu-id="9ad09-113">NavigationId</span><span class="sxs-lookup"><span data-stu-id="9ad09-113">NavigationId</span></span>](#navigationid) | <span data-ttu-id="9ad09-114">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="9ad09-114">The ID of the navigation.</span></span>
[<span data-ttu-id="9ad09-115">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="9ad09-115">WebErrorStatus</span></span>](#weberrorstatus) | <span data-ttu-id="9ad09-116">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="9ad09-116">The error code if the navigation failed.</span></span>

## <span data-ttu-id="9ad09-117">Members</span><span class="sxs-lookup"><span data-stu-id="9ad09-117">Members</span></span>

#### <span data-ttu-id="9ad09-118">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="9ad09-118">IsSuccess</span></span> 

<span data-ttu-id="9ad09-119">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="9ad09-119">True when the navigation is successful.</span></span>

> <span data-ttu-id="9ad09-120">公開ブール[値](#issuccess)</span><span class="sxs-lookup"><span data-stu-id="9ad09-120">public bool [IsSuccess](#issuccess)</span></span>

<span data-ttu-id="9ad09-121">これは、エラーページ内で終了するナビゲーション (ネットワークがない、DNS 参照エラー、HTTP server が4xx で応答する) でも、また、移動ページで呼び出された window. stop () などの追加機能については、false になります。</span><span class="sxs-lookup"><span data-stu-id="9ad09-121">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="9ad09-122">NavigationId</span><span class="sxs-lookup"><span data-stu-id="9ad09-122">NavigationId</span></span> 

<span data-ttu-id="9ad09-123">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="9ad09-123">The ID of the navigation.</span></span>

> <span data-ttu-id="9ad09-124">パブリック ulong [Navigationid](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="9ad09-124">public ulong [NavigationId](#navigationid)</span></span>

#### <span data-ttu-id="9ad09-125">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="9ad09-125">WebErrorStatus</span></span> 

<span data-ttu-id="9ad09-126">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="9ad09-126">The error code if the navigation failed.</span></span>

> <span data-ttu-id="9ad09-127">パブリック CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span><span class="sxs-lookup"><span data-stu-id="9ad09-127">public CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span></span>

