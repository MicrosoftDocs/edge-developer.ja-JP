---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/28/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 83f55e19c8c8c0f2fb075ff47e95e34be27c6602
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697337"
---
# <span data-ttu-id="b9c1b-104">インターフェイス ICoreWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="b9c1b-104">interface ICoreWebView2NavigationCompletedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="b9c1b-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="b9c1b-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2NavigationCompletedEventArgs
  : public IUnknown
```

<span data-ttu-id="b9c1b-107">NavigationCompleted イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-107">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="b9c1b-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="b9c1b-108">Summary</span></span>

 <span data-ttu-id="b9c1b-109">Members</span><span class="sxs-lookup"><span data-stu-id="b9c1b-109">Members</span></span>                        | <span data-ttu-id="b9c1b-110">説明</span><span class="sxs-lookup"><span data-stu-id="b9c1b-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b9c1b-111">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="b9c1b-111">get_IsSuccess</span></span>](#get_issuccess) | <span data-ttu-id="b9c1b-112">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-112">True when the navigation is successful.</span></span>
[<span data-ttu-id="b9c1b-113">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="b9c1b-113">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="b9c1b-114">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-114">The ID of the navigation.</span></span>
[<span data-ttu-id="b9c1b-115">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="b9c1b-115">get_WebErrorStatus</span></span>](#get_weberrorstatus) | <span data-ttu-id="b9c1b-116">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-116">The error code if the navigation failed.</span></span>

## <span data-ttu-id="b9c1b-117">Members</span><span class="sxs-lookup"><span data-stu-id="b9c1b-117">Members</span></span>

#### <span data-ttu-id="b9c1b-118">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="b9c1b-118">get_IsSuccess</span></span> 

<span data-ttu-id="b9c1b-119">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-119">True when the navigation is successful.</span></span>

> <span data-ttu-id="b9c1b-120">パブリック HRESULT [get_IsSuccess](#get_issuccess)(ブール \* の場合)</span><span class="sxs-lookup"><span data-stu-id="b9c1b-120">public HRESULT [get_IsSuccess](#get_issuccess)(BOOL \* isSuccess)</span></span>

<span data-ttu-id="b9c1b-121">これは、エラーページ内で終了するナビゲーション (ネットワークがない、DNS 参照エラー、HTTP server が4xx で応答する) でも、また、移動ページで呼び出された window. stop () などの追加機能については、false になります。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-121">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="b9c1b-122">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="b9c1b-122">get_NavigationId</span></span> 

<span data-ttu-id="b9c1b-123">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-123">The ID of the navigation.</span></span>

> <span data-ttu-id="b9c1b-124">パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span><span class="sxs-lookup"><span data-stu-id="b9c1b-124">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

#### <span data-ttu-id="b9c1b-125">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="b9c1b-125">get_WebErrorStatus</span></span> 

<span data-ttu-id="b9c1b-126">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-126">The error code if the navigation failed.</span></span>

> <span data-ttu-id="b9c1b-127">パブリック HRESULT [get_WebErrorStatus](#get_weberrorstatus)(COREWEBVIEW2_WEB_ERROR_STATUS \* COREWEBVIEW2_WEB_ERROR_STATUS)</span><span class="sxs-lookup"><span data-stu-id="b9c1b-127">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)(COREWEBVIEW2_WEB_ERROR_STATUS \* COREWEBVIEW2_WEB_ERROR_STATUS)</span></span>

