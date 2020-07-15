---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 215297bf56234452aad33e135cfb03ec079a049b
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877974"
---
# <span data-ttu-id="4dd8f-104">0.9.430-インターフェイス ICoreWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="4dd8f-104">0.9.430 - interface ICoreWebView2NavigationCompletedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="4dd8f-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4dd8f-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="4dd8f-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dd8f-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2NavigationCompletedEventArgs
  : public IUnknown
```

<span data-ttu-id="4dd8f-107">NavigationCompleted イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="4dd8f-107">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="4dd8f-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="4dd8f-108">Summary</span></span>

 <span data-ttu-id="4dd8f-109">Members</span><span class="sxs-lookup"><span data-stu-id="4dd8f-109">Members</span></span>                        | <span data-ttu-id="4dd8f-110">説明</span><span class="sxs-lookup"><span data-stu-id="4dd8f-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4dd8f-111">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="4dd8f-111">get_IsSuccess</span></span>](#get_issuccess) | <span data-ttu-id="4dd8f-112">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="4dd8f-112">True when the navigation is successful.</span></span>
[<span data-ttu-id="4dd8f-113">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="4dd8f-113">get_WebErrorStatus</span></span>](#get_weberrorstatus) | <span data-ttu-id="4dd8f-114">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="4dd8f-114">The error code if the navigation failed.</span></span>
[<span data-ttu-id="4dd8f-115">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="4dd8f-115">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="4dd8f-116">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="4dd8f-116">The ID of the navigation.</span></span>

## <span data-ttu-id="4dd8f-117">Members</span><span class="sxs-lookup"><span data-stu-id="4dd8f-117">Members</span></span>

#### <span data-ttu-id="4dd8f-118">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="4dd8f-118">get_IsSuccess</span></span> 

<span data-ttu-id="4dd8f-119">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="4dd8f-119">True when the navigation is successful.</span></span>

> <span data-ttu-id="4dd8f-120">パブリック HRESULT [get_IsSuccess](#get_issuccess)(ブール \* の場合)</span><span class="sxs-lookup"><span data-stu-id="4dd8f-120">public HRESULT [get_IsSuccess](#get_issuccess)(BOOL \* isSuccess)</span></span>

<span data-ttu-id="4dd8f-121">これは、エラーページ内で終了するナビゲーション (ネットワークがない、DNS 参照エラー、HTTP server が4xx で応答する) でも、また、移動ページで呼び出された window. stop () などの追加機能については、false になります。</span><span class="sxs-lookup"><span data-stu-id="4dd8f-121">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="4dd8f-122">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="4dd8f-122">get_WebErrorStatus</span></span> 

<span data-ttu-id="4dd8f-123">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="4dd8f-123">The error code if the navigation failed.</span></span>

> <span data-ttu-id="4dd8f-124">パブリック HRESULT [get_WebErrorStatus](#get_weberrorstatus)(CORE_WEBVIEW2_WEB_ERROR_STATUS \* CORE_WEBVIEW2_WEB_ERROR_STATUS)</span><span class="sxs-lookup"><span data-stu-id="4dd8f-124">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)(CORE_WEBVIEW2_WEB_ERROR_STATUS \* CORE_WEBVIEW2_WEB_ERROR_STATUS)</span></span>

#### <span data-ttu-id="4dd8f-125">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="4dd8f-125">get_NavigationId</span></span> 

<span data-ttu-id="4dd8f-126">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="4dd8f-126">The ID of the navigation.</span></span>

> <span data-ttu-id="4dd8f-127">パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span><span class="sxs-lookup"><span data-stu-id="4dd8f-127">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

