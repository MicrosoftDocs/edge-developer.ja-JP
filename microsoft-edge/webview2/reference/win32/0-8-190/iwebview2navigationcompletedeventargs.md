---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 7c10e669b4caf13f43f858e343c9bad3da155518
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878415"
---
# <span data-ttu-id="eb371-104">0.8.355-インターフェイス IWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="eb371-104">0.8.355 - interface IWebView2NavigationCompletedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="eb371-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eb371-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="eb371-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb371-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2NavigationCompletedEventArgs
  : public IUnknown
```

<span data-ttu-id="eb371-107">NavigationCompleted イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="eb371-107">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="eb371-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="eb371-108">Summary</span></span>

 <span data-ttu-id="eb371-109">Members</span><span class="sxs-lookup"><span data-stu-id="eb371-109">Members</span></span>                        | <span data-ttu-id="eb371-110">説明</span><span class="sxs-lookup"><span data-stu-id="eb371-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="eb371-111">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="eb371-111">get_IsSuccess</span></span>](#get_issuccess) | <span data-ttu-id="eb371-112">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="eb371-112">True when the navigation is successful.</span></span>
[<span data-ttu-id="eb371-113">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="eb371-113">get_WebErrorStatus</span></span>](#get_weberrorstatus) | <span data-ttu-id="eb371-114">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="eb371-114">The error code if the navigation failed.</span></span>

## <span data-ttu-id="eb371-115">Members</span><span class="sxs-lookup"><span data-stu-id="eb371-115">Members</span></span>

#### <span data-ttu-id="eb371-116">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="eb371-116">get_IsSuccess</span></span> 

<span data-ttu-id="eb371-117">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="eb371-117">True when the navigation is successful.</span></span>

> <span data-ttu-id="eb371-118">パブリック HRESULT [get_IsSuccess](#get_issuccess)(ブール \* の場合)</span><span class="sxs-lookup"><span data-stu-id="eb371-118">public HRESULT [get_IsSuccess](#get_issuccess)(BOOL \* isSuccess)</span></span>

<span data-ttu-id="eb371-119">これは、エラーページ内で終了するナビゲーション (ネットワークがない、DNS 参照エラー、HTTP server が4xx で応答する) でも、また、移動ページで呼び出された window. stop () などの追加機能については、false になります。</span><span class="sxs-lookup"><span data-stu-id="eb371-119">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="eb371-120">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="eb371-120">get_WebErrorStatus</span></span> 

<span data-ttu-id="eb371-121">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="eb371-121">The error code if the navigation failed.</span></span>

> <span data-ttu-id="eb371-122">パブリック HRESULT [get_WebErrorStatus](#get_weberrorstatus)(WEBVIEW2_WEB_ERROR_STATUS \* WEBVIEW2_WEB_ERROR_STATUS)</span><span class="sxs-lookup"><span data-stu-id="eb371-122">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)(WEBVIEW2_WEB_ERROR_STATUS \* WEBVIEW2_WEB_ERROR_STATUS)</span></span>

