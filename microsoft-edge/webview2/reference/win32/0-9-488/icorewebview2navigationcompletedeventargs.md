---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: c13d0625669d6303c115c3d415d12278cfbe8320
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880501"
---
# <span data-ttu-id="cb7ca-104">0.9.515-インターフェイス ICoreWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="cb7ca-104">0.9.515 - interface ICoreWebView2NavigationCompletedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="cb7ca-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="cb7ca-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2NavigationCompletedEventArgs
  : public IUnknown
```

<span data-ttu-id="cb7ca-107">NavigationCompleted イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-107">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="cb7ca-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="cb7ca-108">Summary</span></span>

 <span data-ttu-id="cb7ca-109">Members</span><span class="sxs-lookup"><span data-stu-id="cb7ca-109">Members</span></span>                        | <span data-ttu-id="cb7ca-110">説明</span><span class="sxs-lookup"><span data-stu-id="cb7ca-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="cb7ca-111">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="cb7ca-111">get_IsSuccess</span></span>](#get_issuccess) | <span data-ttu-id="cb7ca-112">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-112">True when the navigation is successful.</span></span>
[<span data-ttu-id="cb7ca-113">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="cb7ca-113">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="cb7ca-114">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-114">The ID of the navigation.</span></span>
[<span data-ttu-id="cb7ca-115">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="cb7ca-115">get_WebErrorStatus</span></span>](#get_weberrorstatus) | <span data-ttu-id="cb7ca-116">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-116">The error code if the navigation failed.</span></span>

## <span data-ttu-id="cb7ca-117">Members</span><span class="sxs-lookup"><span data-stu-id="cb7ca-117">Members</span></span>

#### <span data-ttu-id="cb7ca-118">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="cb7ca-118">get_IsSuccess</span></span> 

<span data-ttu-id="cb7ca-119">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-119">True when the navigation is successful.</span></span>

> <span data-ttu-id="cb7ca-120">パブリック HRESULT [get_IsSuccess](#get_issuccess)(ブール \* の場合)</span><span class="sxs-lookup"><span data-stu-id="cb7ca-120">public HRESULT [get_IsSuccess](#get_issuccess)(BOOL \* isSuccess)</span></span>

<span data-ttu-id="cb7ca-121">これは、エラーページ内で終了するナビゲーション (ネットワークがない、DNS 参照エラー、HTTP server が4xx で応答する) でも、また、移動ページで呼び出された window. stop () などの追加機能については、false になります。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-121">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="cb7ca-122">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="cb7ca-122">get_NavigationId</span></span> 

<span data-ttu-id="cb7ca-123">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-123">The ID of the navigation.</span></span>

> <span data-ttu-id="cb7ca-124">パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span><span class="sxs-lookup"><span data-stu-id="cb7ca-124">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

#### <span data-ttu-id="cb7ca-125">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="cb7ca-125">get_WebErrorStatus</span></span> 

<span data-ttu-id="cb7ca-126">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="cb7ca-126">The error code if the navigation failed.</span></span>

> <span data-ttu-id="cb7ca-127">パブリック HRESULT [get_WebErrorStatus](#get_weberrorstatus)(COREWEBVIEW2_WEB_ERROR_STATUS \* COREWEBVIEW2_WEB_ERROR_STATUS)</span><span class="sxs-lookup"><span data-stu-id="cb7ca-127">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)(COREWEBVIEW2_WEB_ERROR_STATUS \* COREWEBVIEW2_WEB_ERROR_STATUS)</span></span>

