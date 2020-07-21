---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 099a022fef47beca0e0163e6e0e070aa37520a06
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883729"
---
# <span data-ttu-id="c58d8-104">0.9.430-インターフェイス ICoreWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="c58d8-104">0.9.430 - interface ICoreWebView2NavigationCompletedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2NavigationCompletedEventArgs
  : public IUnknown
```

<span data-ttu-id="c58d8-105">NavigationCompleted イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="c58d8-105">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="c58d8-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="c58d8-106">Summary</span></span>

 <span data-ttu-id="c58d8-107">Members</span><span class="sxs-lookup"><span data-stu-id="c58d8-107">Members</span></span>                        | <span data-ttu-id="c58d8-108">説明</span><span class="sxs-lookup"><span data-stu-id="c58d8-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c58d8-109">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="c58d8-109">get_IsSuccess</span></span>](#get_issuccess) | <span data-ttu-id="c58d8-110">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="c58d8-110">True when the navigation is successful.</span></span>
[<span data-ttu-id="c58d8-111">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="c58d8-111">get_WebErrorStatus</span></span>](#get_weberrorstatus) | <span data-ttu-id="c58d8-112">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="c58d8-112">The error code if the navigation failed.</span></span>
[<span data-ttu-id="c58d8-113">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="c58d8-113">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="c58d8-114">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="c58d8-114">The ID of the navigation.</span></span>

## <span data-ttu-id="c58d8-115">Members</span><span class="sxs-lookup"><span data-stu-id="c58d8-115">Members</span></span>

#### <span data-ttu-id="c58d8-116">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="c58d8-116">get_IsSuccess</span></span> 

<span data-ttu-id="c58d8-117">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="c58d8-117">True when the navigation is successful.</span></span>

> <span data-ttu-id="c58d8-118">パブリック HRESULT [get_IsSuccess](#get_issuccess)(ブール \* の場合)</span><span class="sxs-lookup"><span data-stu-id="c58d8-118">public HRESULT [get_IsSuccess](#get_issuccess)(BOOL \* isSuccess)</span></span>

<span data-ttu-id="c58d8-119">これは、エラーページ内で終了するナビゲーション (ネットワークがない、DNS 参照エラー、HTTP server が4xx で応答する) でも、また、移動ページで呼び出された window. stop () などの追加機能については、false になります。</span><span class="sxs-lookup"><span data-stu-id="c58d8-119">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="c58d8-120">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="c58d8-120">get_WebErrorStatus</span></span> 

<span data-ttu-id="c58d8-121">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="c58d8-121">The error code if the navigation failed.</span></span>

> <span data-ttu-id="c58d8-122">パブリック HRESULT [get_WebErrorStatus](#get_weberrorstatus)(CORE_WEBVIEW2_WEB_ERROR_STATUS \* CORE_WEBVIEW2_WEB_ERROR_STATUS)</span><span class="sxs-lookup"><span data-stu-id="c58d8-122">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)(CORE_WEBVIEW2_WEB_ERROR_STATUS \* CORE_WEBVIEW2_WEB_ERROR_STATUS)</span></span>

#### <span data-ttu-id="c58d8-123">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="c58d8-123">get_NavigationId</span></span> 

<span data-ttu-id="c58d8-124">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="c58d8-124">The ID of the navigation.</span></span>

> <span data-ttu-id="c58d8-125">パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span><span class="sxs-lookup"><span data-stu-id="c58d8-125">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

