---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: b496c37949e934fadf0af736059566edcab9f5c3
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885934"
---
# <span data-ttu-id="d0a41-104">0.8.355-インターフェイス IWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="d0a41-104">0.8.355 - interface IWebView2NavigationCompletedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2NavigationCompletedEventArgs
  : public IUnknown
```

<span data-ttu-id="d0a41-105">NavigationCompleted イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="d0a41-105">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="d0a41-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="d0a41-106">Summary</span></span>

 <span data-ttu-id="d0a41-107">Members</span><span class="sxs-lookup"><span data-stu-id="d0a41-107">Members</span></span>                        | <span data-ttu-id="d0a41-108">説明</span><span class="sxs-lookup"><span data-stu-id="d0a41-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d0a41-109">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="d0a41-109">get_IsSuccess</span></span>](#get_issuccess) | <span data-ttu-id="d0a41-110">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="d0a41-110">True when the navigation is successful.</span></span>
[<span data-ttu-id="d0a41-111">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="d0a41-111">get_WebErrorStatus</span></span>](#get_weberrorstatus) | <span data-ttu-id="d0a41-112">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="d0a41-112">The error code if the navigation failed.</span></span>

## <span data-ttu-id="d0a41-113">Members</span><span class="sxs-lookup"><span data-stu-id="d0a41-113">Members</span></span>

#### <span data-ttu-id="d0a41-114">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="d0a41-114">get_IsSuccess</span></span> 

<span data-ttu-id="d0a41-115">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="d0a41-115">True when the navigation is successful.</span></span>

> <span data-ttu-id="d0a41-116">パブリック HRESULT [get_IsSuccess](#get_issuccess)(ブール \* の場合)</span><span class="sxs-lookup"><span data-stu-id="d0a41-116">public HRESULT [get_IsSuccess](#get_issuccess)(BOOL \* isSuccess)</span></span>

<span data-ttu-id="d0a41-117">これは、エラーページ内で終了するナビゲーション (ネットワークがない、DNS 参照エラー、HTTP server が4xx で応答する) でも、また、移動ページで呼び出された window. stop () などの追加機能については、false になります。</span><span class="sxs-lookup"><span data-stu-id="d0a41-117">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="d0a41-118">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="d0a41-118">get_WebErrorStatus</span></span> 

<span data-ttu-id="d0a41-119">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="d0a41-119">The error code if the navigation failed.</span></span>

> <span data-ttu-id="d0a41-120">パブリック HRESULT [get_WebErrorStatus](#get_weberrorstatus)(WEBVIEW2_WEB_ERROR_STATUS \* WEBVIEW2_WEB_ERROR_STATUS)</span><span class="sxs-lookup"><span data-stu-id="d0a41-120">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)(WEBVIEW2_WEB_ERROR_STATUS \* WEBVIEW2_WEB_ERROR_STATUS)</span></span>

