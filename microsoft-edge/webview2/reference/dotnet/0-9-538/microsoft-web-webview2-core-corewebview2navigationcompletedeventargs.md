---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 (CoreWebView2NavigationCompletedEventArgs の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2NavigationCompletedEventArgs。
ms.openlocfilehash: 01102cc9aa9d6fbec7f4d223e1115892dabe2899
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010972"
---
# <span data-ttu-id="452ad-104">0.9.579 クラスの WebView2 クラス (CoreWebView2NavigationCompletedEventArgs)</span><span class="sxs-lookup"><span data-stu-id="452ad-104">0.9.579 - Microsoft.Web.WebView2.Core.CoreWebView2NavigationCompletedEventArgs class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="452ad-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="452ad-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="452ad-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="452ad-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="452ad-107">NavigationCompleted イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="452ad-107">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="452ad-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="452ad-108">Summary</span></span>

 <span data-ttu-id="452ad-109">Members</span><span class="sxs-lookup"><span data-stu-id="452ad-109">Members</span></span>                        | <span data-ttu-id="452ad-110">説明</span><span class="sxs-lookup"><span data-stu-id="452ad-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="452ad-111">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="452ad-111">IsSuccess</span></span>](#issuccess) | <span data-ttu-id="452ad-112">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="452ad-112">True when the navigation is successful.</span></span>
[<span data-ttu-id="452ad-113">NavigationId</span><span class="sxs-lookup"><span data-stu-id="452ad-113">NavigationId</span></span>](#navigationid) | <span data-ttu-id="452ad-114">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="452ad-114">The ID of the navigation.</span></span>
[<span data-ttu-id="452ad-115">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="452ad-115">WebErrorStatus</span></span>](#weberrorstatus) | <span data-ttu-id="452ad-116">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="452ad-116">The error code if the navigation failed.</span></span>

## <span data-ttu-id="452ad-117">Members</span><span class="sxs-lookup"><span data-stu-id="452ad-117">Members</span></span>

#### <span data-ttu-id="452ad-118">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="452ad-118">IsSuccess</span></span> 

<span data-ttu-id="452ad-119">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="452ad-119">True when the navigation is successful.</span></span>

> <span data-ttu-id="452ad-120">公開ブール [値](#issuccess)</span><span class="sxs-lookup"><span data-stu-id="452ad-120">public bool [IsSuccess](#issuccess)</span></span>

<span data-ttu-id="452ad-121">これは、エラーページ内で終了するナビゲーション (ネットワークがない、DNS 参照エラー、HTTP server が4xx で応答する) でも、また、移動ページで呼び出された window. stop () などの追加機能については、false になります。</span><span class="sxs-lookup"><span data-stu-id="452ad-121">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="452ad-122">NavigationId</span><span class="sxs-lookup"><span data-stu-id="452ad-122">NavigationId</span></span> 

<span data-ttu-id="452ad-123">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="452ad-123">The ID of the navigation.</span></span>

> <span data-ttu-id="452ad-124">パブリック ulong [Navigationid](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="452ad-124">public ulong [NavigationId](#navigationid)</span></span>

#### <span data-ttu-id="452ad-125">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="452ad-125">WebErrorStatus</span></span> 

<span data-ttu-id="452ad-126">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="452ad-126">The error code if the navigation failed.</span></span>

> <span data-ttu-id="452ad-127">パブリック CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span><span class="sxs-lookup"><span data-stu-id="452ad-127">public CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span></span>

