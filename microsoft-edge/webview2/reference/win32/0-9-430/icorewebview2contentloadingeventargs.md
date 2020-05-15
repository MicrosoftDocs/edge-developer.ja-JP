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
ms.openlocfilehash: c3ba6ac3a2478861abb7b26e726a9cbd606b0eb9
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654337"
---
# <span data-ttu-id="48c9b-104">インターフェイス ICoreWebView2ContentLoadingEventArgs</span><span class="sxs-lookup"><span data-stu-id="48c9b-104">interface ICoreWebView2ContentLoadingEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="48c9b-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="48c9b-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="48c9b-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48c9b-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ContentLoadingEventArgs
  : public IUnknown
```

<span data-ttu-id="48c9b-107">ContentLoading イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="48c9b-107">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="48c9b-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="48c9b-108">Summary</span></span>

 <span data-ttu-id="48c9b-109">Members</span><span class="sxs-lookup"><span data-stu-id="48c9b-109">Members</span></span>                        | <span data-ttu-id="48c9b-110">説明</span><span class="sxs-lookup"><span data-stu-id="48c9b-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="48c9b-111">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="48c9b-111">get_IsErrorPage</span></span>](#get_iserrorpage) | <span data-ttu-id="48c9b-112">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="48c9b-112">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="48c9b-113">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="48c9b-113">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="48c9b-114">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="48c9b-114">The ID of the navigation.</span></span>

## <span data-ttu-id="48c9b-115">Members</span><span class="sxs-lookup"><span data-stu-id="48c9b-115">Members</span></span>

#### <span data-ttu-id="48c9b-116">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="48c9b-116">get_IsErrorPage</span></span> 

<span data-ttu-id="48c9b-117">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="48c9b-117">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="48c9b-118">パブリック HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* IsErrorPage)</span><span class="sxs-lookup"><span data-stu-id="48c9b-118">public HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* isErrorPage)</span></span>

#### <span data-ttu-id="48c9b-119">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="48c9b-119">get_NavigationId</span></span> 

<span data-ttu-id="48c9b-120">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="48c9b-120">The ID of the navigation.</span></span>

> <span data-ttu-id="48c9b-121">パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span><span class="sxs-lookup"><span data-stu-id="48c9b-121">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

