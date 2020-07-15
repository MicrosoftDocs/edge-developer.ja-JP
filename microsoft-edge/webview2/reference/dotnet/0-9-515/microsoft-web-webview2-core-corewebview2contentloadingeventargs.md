---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (CoreWebView2ContentLoadingEventArgs の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 899adcb7cfa171e8c1f6cb9693092e36f2e41a5f
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877764"
---
# <span data-ttu-id="d1e65-104">0.9.515 クラスの WebView2 クラス (CoreWebView2ContentLoadingEventArgs)</span><span class="sxs-lookup"><span data-stu-id="d1e65-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2ContentLoadingEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="d1e65-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d1e65-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="d1e65-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1e65-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="d1e65-107">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="d1e65-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="d1e65-108">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="d1e65-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="d1e65-109">ContentLoading イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="d1e65-109">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="d1e65-110">まとめ</span><span class="sxs-lookup"><span data-stu-id="d1e65-110">Summary</span></span>

 <span data-ttu-id="d1e65-111">Members</span><span class="sxs-lookup"><span data-stu-id="d1e65-111">Members</span></span>                        | <span data-ttu-id="d1e65-112">説明</span><span class="sxs-lookup"><span data-stu-id="d1e65-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d1e65-113">IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="d1e65-113">IsErrorPage</span></span>](#iserrorpage) | <span data-ttu-id="d1e65-114">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="d1e65-114">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="d1e65-115">NavigationId</span><span class="sxs-lookup"><span data-stu-id="d1e65-115">NavigationId</span></span>](#navigationid) | <span data-ttu-id="d1e65-116">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="d1e65-116">The ID of the navigation.</span></span>

## <span data-ttu-id="d1e65-117">Members</span><span class="sxs-lookup"><span data-stu-id="d1e65-117">Members</span></span>

#### <span data-ttu-id="d1e65-118">IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="d1e65-118">IsErrorPage</span></span> 

<span data-ttu-id="d1e65-119">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="d1e65-119">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="d1e65-120">public bool [IsErrorPage](#iserrorpage)</span><span class="sxs-lookup"><span data-stu-id="d1e65-120">public bool [IsErrorPage](#iserrorpage)</span></span>

#### <span data-ttu-id="d1e65-121">NavigationId</span><span class="sxs-lookup"><span data-stu-id="d1e65-121">NavigationId</span></span> 

<span data-ttu-id="d1e65-122">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="d1e65-122">The ID of the navigation.</span></span>

> <span data-ttu-id="d1e65-123">パブリック ulong [Navigationid](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="d1e65-123">public ulong [NavigationId](#navigationid)</span></span>

