---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2NavigationCompletedEventArgs
ms.openlocfilehash: d40ee75eb77e8de6eab1188e6c17edacce00f635
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879808"
---
# <span data-ttu-id="e13cf-104">インターフェイス ICoreWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="e13cf-104">interface ICoreWebView2NavigationCompletedEventArgs</span></span> 

```
interface ICoreWebView2NavigationCompletedEventArgs
  : public IUnknown
```

<span data-ttu-id="e13cf-105">NavigationCompleted イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="e13cf-105">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="e13cf-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="e13cf-106">Summary</span></span>

 <span data-ttu-id="e13cf-107">Members</span><span class="sxs-lookup"><span data-stu-id="e13cf-107">Members</span></span>                        | <span data-ttu-id="e13cf-108">説明</span><span class="sxs-lookup"><span data-stu-id="e13cf-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e13cf-109">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="e13cf-109">get_IsSuccess</span></span>](#get_issuccess) | <span data-ttu-id="e13cf-110">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="e13cf-110">True when the navigation is successful.</span></span>
[<span data-ttu-id="e13cf-111">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="e13cf-111">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="e13cf-112">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="e13cf-112">The ID of the navigation.</span></span>
[<span data-ttu-id="e13cf-113">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="e13cf-113">get_WebErrorStatus</span></span>](#get_weberrorstatus) | <span data-ttu-id="e13cf-114">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="e13cf-114">The error code if the navigation failed.</span></span>

## <span data-ttu-id="e13cf-115">Members</span><span class="sxs-lookup"><span data-stu-id="e13cf-115">Members</span></span>

#### <span data-ttu-id="e13cf-116">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="e13cf-116">get_IsSuccess</span></span> 

<span data-ttu-id="e13cf-117">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="e13cf-117">True when the navigation is successful.</span></span>

> <span data-ttu-id="e13cf-118">パブリック HRESULT [get_IsSuccess](#get_issuccess)(ブール \* の場合)</span><span class="sxs-lookup"><span data-stu-id="e13cf-118">public HRESULT [get_IsSuccess](#get_issuccess)(BOOL \* isSuccess)</span></span>

<span data-ttu-id="e13cf-119">これは、エラーページ内で終了するナビゲーション (ネットワークがない、DNS 参照エラー、HTTP server が4xx で応答する) でも、また、移動ページで呼び出された window. stop () などの追加機能については、false になります。</span><span class="sxs-lookup"><span data-stu-id="e13cf-119">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="e13cf-120">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="e13cf-120">get_NavigationId</span></span> 

<span data-ttu-id="e13cf-121">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="e13cf-121">The ID of the navigation.</span></span>

> <span data-ttu-id="e13cf-122">パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span><span class="sxs-lookup"><span data-stu-id="e13cf-122">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

#### <span data-ttu-id="e13cf-123">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="e13cf-123">get_WebErrorStatus</span></span> 

<span data-ttu-id="e13cf-124">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="e13cf-124">The error code if the navigation failed.</span></span>

> <span data-ttu-id="e13cf-125">パブリック HRESULT [get_WebErrorStatus](#get_weberrorstatus)(COREWEBVIEW2_WEB_ERROR_STATUS \* COREWEBVIEW2_WEB_ERROR_STATUS)</span><span class="sxs-lookup"><span data-stu-id="e13cf-125">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)(COREWEBVIEW2_WEB_ERROR_STATUS \* COREWEBVIEW2_WEB_ERROR_STATUS)</span></span>

