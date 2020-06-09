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
ms.openlocfilehash: d3b3f4e78ef37ad2101a3a8f817279e999cea3e3
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697617"
---
# <span data-ttu-id="59fd4-104">WebView2 クラス (CoreWebView2NavigationCompletedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="59fd4-104">Microsoft.Web.WebView2.Core.CoreWebView2NavigationCompletedEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="59fd4-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="59fd4-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="59fd4-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59fd4-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="59fd4-107">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="59fd4-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="59fd4-108">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="59fd4-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="59fd4-109">NavigationCompleted イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="59fd4-109">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="59fd4-110">まとめ</span><span class="sxs-lookup"><span data-stu-id="59fd4-110">Summary</span></span>

 <span data-ttu-id="59fd4-111">Members</span><span class="sxs-lookup"><span data-stu-id="59fd4-111">Members</span></span>                        | <span data-ttu-id="59fd4-112">説明</span><span class="sxs-lookup"><span data-stu-id="59fd4-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="59fd4-113">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="59fd4-113">IsSuccess</span></span>](#issuccess) | <span data-ttu-id="59fd4-114">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="59fd4-114">True when the navigation is successful.</span></span>
[<span data-ttu-id="59fd4-115">NavigationId</span><span class="sxs-lookup"><span data-stu-id="59fd4-115">NavigationId</span></span>](#navigationid) | <span data-ttu-id="59fd4-116">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="59fd4-116">The ID of the navigation.</span></span>
[<span data-ttu-id="59fd4-117">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="59fd4-117">WebErrorStatus</span></span>](#weberrorstatus) | <span data-ttu-id="59fd4-118">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="59fd4-118">The error code if the navigation failed.</span></span>

## <span data-ttu-id="59fd4-119">Members</span><span class="sxs-lookup"><span data-stu-id="59fd4-119">Members</span></span>

#### <span data-ttu-id="59fd4-120">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="59fd4-120">IsSuccess</span></span> 

<span data-ttu-id="59fd4-121">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="59fd4-121">True when the navigation is successful.</span></span>

> <span data-ttu-id="59fd4-122">公開ブール[値](#issuccess)</span><span class="sxs-lookup"><span data-stu-id="59fd4-122">public bool [IsSuccess](#issuccess)</span></span>

<span data-ttu-id="59fd4-123">これは、エラーページ内で終了するナビゲーション (ネットワークがない、DNS 参照エラー、HTTP server が4xx で応答する) でも、また、移動ページで呼び出された window. stop () などの追加機能については、false になります。</span><span class="sxs-lookup"><span data-stu-id="59fd4-123">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="59fd4-124">NavigationId</span><span class="sxs-lookup"><span data-stu-id="59fd4-124">NavigationId</span></span> 

<span data-ttu-id="59fd4-125">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="59fd4-125">The ID of the navigation.</span></span>

> <span data-ttu-id="59fd4-126">パブリック ulong [Navigationid](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="59fd4-126">public ulong [NavigationId](#navigationid)</span></span>

#### <span data-ttu-id="59fd4-127">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="59fd4-127">WebErrorStatus</span></span> 

<span data-ttu-id="59fd4-128">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="59fd4-128">The error code if the navigation failed.</span></span>

> <span data-ttu-id="59fd4-129">パブリック CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span><span class="sxs-lookup"><span data-stu-id="59fd4-129">public CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span></span>

