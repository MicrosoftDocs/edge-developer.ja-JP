---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (CoreWebView2NavigationCompletedEventArgs の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 3a15232a7fe2ddf230d0463069052c55f7abc843
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879136"
---
# <span data-ttu-id="d639f-104">0.9.515 クラスの WebView2 クラス (CoreWebView2NavigationCompletedEventArgs)</span><span class="sxs-lookup"><span data-stu-id="d639f-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2NavigationCompletedEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="d639f-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d639f-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="d639f-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d639f-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="d639f-107">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="d639f-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="d639f-108">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="d639f-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="d639f-109">NavigationCompleted イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="d639f-109">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="d639f-110">まとめ</span><span class="sxs-lookup"><span data-stu-id="d639f-110">Summary</span></span>

 <span data-ttu-id="d639f-111">Members</span><span class="sxs-lookup"><span data-stu-id="d639f-111">Members</span></span>                        | <span data-ttu-id="d639f-112">説明</span><span class="sxs-lookup"><span data-stu-id="d639f-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d639f-113">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="d639f-113">IsSuccess</span></span>](#issuccess) | <span data-ttu-id="d639f-114">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="d639f-114">True when the navigation is successful.</span></span>
[<span data-ttu-id="d639f-115">NavigationId</span><span class="sxs-lookup"><span data-stu-id="d639f-115">NavigationId</span></span>](#navigationid) | <span data-ttu-id="d639f-116">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="d639f-116">The ID of the navigation.</span></span>
[<span data-ttu-id="d639f-117">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="d639f-117">WebErrorStatus</span></span>](#weberrorstatus) | <span data-ttu-id="d639f-118">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="d639f-118">The error code if the navigation failed.</span></span>

## <span data-ttu-id="d639f-119">Members</span><span class="sxs-lookup"><span data-stu-id="d639f-119">Members</span></span>

#### <span data-ttu-id="d639f-120">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="d639f-120">IsSuccess</span></span> 

<span data-ttu-id="d639f-121">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="d639f-121">True when the navigation is successful.</span></span>

> <span data-ttu-id="d639f-122">公開ブール[値](#issuccess)</span><span class="sxs-lookup"><span data-stu-id="d639f-122">public bool [IsSuccess](#issuccess)</span></span>

<span data-ttu-id="d639f-123">これは、エラーページ内で終了するナビゲーション (ネットワークがない、DNS 参照エラー、HTTP server が4xx で応答する) でも、また、移動ページで呼び出された window. stop () などの追加機能については、false になります。</span><span class="sxs-lookup"><span data-stu-id="d639f-123">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="d639f-124">NavigationId</span><span class="sxs-lookup"><span data-stu-id="d639f-124">NavigationId</span></span> 

<span data-ttu-id="d639f-125">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="d639f-125">The ID of the navigation.</span></span>

> <span data-ttu-id="d639f-126">パブリック ulong [Navigationid](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="d639f-126">public ulong [NavigationId](#navigationid)</span></span>

#### <span data-ttu-id="d639f-127">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="d639f-127">WebErrorStatus</span></span> 

<span data-ttu-id="d639f-128">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="d639f-128">The error code if the navigation failed.</span></span>

> <span data-ttu-id="d639f-129">パブリック CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span><span class="sxs-lookup"><span data-stu-id="d639f-129">public CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span></span>

