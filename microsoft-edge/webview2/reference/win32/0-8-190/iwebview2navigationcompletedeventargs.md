---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: fa1debd3b212492eea03e4ecf6e5daff5751f89b
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654370"
---
# <span data-ttu-id="9f56f-104">インターフェイス IWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="9f56f-104">interface IWebView2NavigationCompletedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="9f56f-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9f56f-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="9f56f-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f56f-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2NavigationCompletedEventArgs
  : public IUnknown
```

<span data-ttu-id="9f56f-107">NavigationCompleted イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="9f56f-107">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="9f56f-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="9f56f-108">Summary</span></span>

 <span data-ttu-id="9f56f-109">Members</span><span class="sxs-lookup"><span data-stu-id="9f56f-109">Members</span></span>                        | <span data-ttu-id="9f56f-110">説明</span><span class="sxs-lookup"><span data-stu-id="9f56f-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9f56f-111">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="9f56f-111">get_IsSuccess</span></span>](#get_issuccess) | <span data-ttu-id="9f56f-112">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="9f56f-112">True when the navigation is successful.</span></span>
[<span data-ttu-id="9f56f-113">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="9f56f-113">get_WebErrorStatus</span></span>](#get_weberrorstatus) | <span data-ttu-id="9f56f-114">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="9f56f-114">The error code if the navigation failed.</span></span>

## <span data-ttu-id="9f56f-115">Members</span><span class="sxs-lookup"><span data-stu-id="9f56f-115">Members</span></span>

#### <span data-ttu-id="9f56f-116">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="9f56f-116">get_IsSuccess</span></span> 

<span data-ttu-id="9f56f-117">ナビゲーションが成功した場合は True です。</span><span class="sxs-lookup"><span data-stu-id="9f56f-117">True when the navigation is successful.</span></span>

> <span data-ttu-id="9f56f-118">パブリック HRESULT [get_IsSuccess](#get_issuccess)(ブール \* の場合)</span><span class="sxs-lookup"><span data-stu-id="9f56f-118">public HRESULT [get_IsSuccess](#get_issuccess)(BOOL \* isSuccess)</span></span>

<span data-ttu-id="9f56f-119">これは、エラーページ内で終了するナビゲーション (ネットワークがない、DNS 参照エラー、HTTP server が4xx で応答する) でも、また、移動ページで呼び出された window. stop () などの追加機能については、false になります。</span><span class="sxs-lookup"><span data-stu-id="9f56f-119">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="9f56f-120">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="9f56f-120">get_WebErrorStatus</span></span> 

<span data-ttu-id="9f56f-121">ナビゲーションに失敗した場合のエラーコード。</span><span class="sxs-lookup"><span data-stu-id="9f56f-121">The error code if the navigation failed.</span></span>

> <span data-ttu-id="9f56f-122">パブリック HRESULT [get_WebErrorStatus](#get_weberrorstatus)(WEBVIEW2_WEB_ERROR_STATUS \* WEBVIEW2_WEB_ERROR_STATUS)</span><span class="sxs-lookup"><span data-stu-id="9f56f-122">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)(WEBVIEW2_WEB_ERROR_STATUS \* WEBVIEW2_WEB_ERROR_STATUS)</span></span>

