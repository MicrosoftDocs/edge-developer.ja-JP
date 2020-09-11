---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2NavigationCompletedEventArgs
ms.openlocfilehash: 482137fd0ffa10c60381d5b0f3dc3d7db6f9fdf7
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011294"
---
# <span data-ttu-id="5b2a0-104">0.9.579-インターフェイス ICoreWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="5b2a0-104">0.9.579 - interface ICoreWebView2NavigationCompletedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2NavigationCompletedEventArgs
  : public IUnknown
```

<span data-ttu-id="5b2a0-105">NavigationCompleted イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="5b2a0-105">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="5b2a0-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="5b2a0-106">Summary</span></span>

 <span data-ttu-id="5b2a0-107">Members</span><span class="sxs-lookup"><span data-stu-id="5b2a0-107">Members</span></span>                        | <span data-ttu-id="5b2a0-108">説明</span><span class="sxs-lookup"><span data-stu-id="5b2a0-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5b2a0-109">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="5b2a0-109">get_IsSuccess</span></span>](#get_issuccess) | <span data-ttu-id="5b2a0-110">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="5b2a0-110">True when the navigation is successful.</span></span>
[<span data-ttu-id="5b2a0-111">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="5b2a0-111">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="5b2a0-112">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="5b2a0-112">The ID of the navigation.</span></span>
[<span data-ttu-id="5b2a0-113">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="5b2a0-113">get_WebErrorStatus</span></span>](#get_weberrorstatus) | <span data-ttu-id="5b2a0-114">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="5b2a0-114">The error code if the navigation failed.</span></span>

## <span data-ttu-id="5b2a0-115">Members</span><span class="sxs-lookup"><span data-stu-id="5b2a0-115">Members</span></span>

#### <span data-ttu-id="5b2a0-116">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="5b2a0-116">get_IsSuccess</span></span> 

<span data-ttu-id="5b2a0-117">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="5b2a0-117">True when the navigation is successful.</span></span>

> <span data-ttu-id="5b2a0-118">パブリック HRESULT [get_IsSuccess](#get_issuccess)(ブール \* の場合)</span><span class="sxs-lookup"><span data-stu-id="5b2a0-118">public HRESULT [get_IsSuccess](#get_issuccess)(BOOL \* isSuccess)</span></span>

<span data-ttu-id="5b2a0-119">これは、エラーページ内で終了するナビゲーション (ネットワークがない、DNS 参照エラー、HTTP server が4xx で応答する) でも、また、移動ページで呼び出された window. stop () などの追加機能については、false になります。</span><span class="sxs-lookup"><span data-stu-id="5b2a0-119">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="5b2a0-120">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="5b2a0-120">get_NavigationId</span></span> 

<span data-ttu-id="5b2a0-121">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="5b2a0-121">The ID of the navigation.</span></span>

> <span data-ttu-id="5b2a0-122">パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span><span class="sxs-lookup"><span data-stu-id="5b2a0-122">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

#### <span data-ttu-id="5b2a0-123">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="5b2a0-123">get_WebErrorStatus</span></span> 

<span data-ttu-id="5b2a0-124">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="5b2a0-124">The error code if the navigation failed.</span></span>

> <span data-ttu-id="5b2a0-125">パブリック HRESULT [get_WebErrorStatus](#get_weberrorstatus)(COREWEBVIEW2_WEB_ERROR_STATUS \* COREWEBVIEW2_WEB_ERROR_STATUS)</span><span class="sxs-lookup"><span data-stu-id="5b2a0-125">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)(COREWEBVIEW2_WEB_ERROR_STATUS \* COREWEBVIEW2_WEB_ERROR_STATUS)</span></span>

