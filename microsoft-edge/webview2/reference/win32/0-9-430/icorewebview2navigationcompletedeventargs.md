---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/24/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: f9d24d10d9487198988b4c6d3ad4a941a32dc396
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654567"
---
# <span data-ttu-id="48244-104">インターフェイス ICoreWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="48244-104">interface ICoreWebView2NavigationCompletedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="48244-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="48244-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="48244-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48244-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2NavigationCompletedEventArgs
  : public IUnknown
```

<span data-ttu-id="48244-107">NavigationCompleted イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="48244-107">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="48244-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="48244-108">Summary</span></span>

 <span data-ttu-id="48244-109">Members</span><span class="sxs-lookup"><span data-stu-id="48244-109">Members</span></span>                        | <span data-ttu-id="48244-110">説明</span><span class="sxs-lookup"><span data-stu-id="48244-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="48244-111">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="48244-111">get_IsSuccess</span></span>](#get_issuccess) | <span data-ttu-id="48244-112">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="48244-112">True when the navigation is successful.</span></span>
[<span data-ttu-id="48244-113">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="48244-113">get_WebErrorStatus</span></span>](#get_weberrorstatus) | <span data-ttu-id="48244-114">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="48244-114">The error code if the navigation failed.</span></span>
[<span data-ttu-id="48244-115">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="48244-115">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="48244-116">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="48244-116">The ID of the navigation.</span></span>

## <span data-ttu-id="48244-117">Members</span><span class="sxs-lookup"><span data-stu-id="48244-117">Members</span></span>

#### <span data-ttu-id="48244-118">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="48244-118">get_IsSuccess</span></span> 

<span data-ttu-id="48244-119">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="48244-119">True when the navigation is successful.</span></span>

> <span data-ttu-id="48244-120">パブリック HRESULT [get_IsSuccess](#get_issuccess)(ブール \* の場合)</span><span class="sxs-lookup"><span data-stu-id="48244-120">public HRESULT [get_IsSuccess](#get_issuccess)(BOOL \* isSuccess)</span></span>

<span data-ttu-id="48244-121">これは、エラーページ内で終了するナビゲーション (ネットワークがない、DNS 参照エラー、HTTP server が4xx で応答する) でも、また、移動ページで呼び出された window. stop () などの追加機能については、false になります。</span><span class="sxs-lookup"><span data-stu-id="48244-121">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="48244-122">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="48244-122">get_WebErrorStatus</span></span> 

<span data-ttu-id="48244-123">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="48244-123">The error code if the navigation failed.</span></span>

> <span data-ttu-id="48244-124">パブリック HRESULT [get_WebErrorStatus](#get_weberrorstatus)(CORE_WEBVIEW2_WEB_ERROR_STATUS \* CORE_WEBVIEW2_WEB_ERROR_STATUS)</span><span class="sxs-lookup"><span data-stu-id="48244-124">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)(CORE_WEBVIEW2_WEB_ERROR_STATUS \* CORE_WEBVIEW2_WEB_ERROR_STATUS)</span></span>

#### <span data-ttu-id="48244-125">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="48244-125">get_NavigationId</span></span> 

<span data-ttu-id="48244-126">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="48244-126">The ID of the navigation.</span></span>

> <span data-ttu-id="48244-127">パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span><span class="sxs-lookup"><span data-stu-id="48244-127">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

