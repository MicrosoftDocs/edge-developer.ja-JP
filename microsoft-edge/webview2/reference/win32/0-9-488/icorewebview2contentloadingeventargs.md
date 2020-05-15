---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: c6bb99078b5574ba89c0d66b49e2c63cd6888d28
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654446"
---
# <span data-ttu-id="6e5e1-104">インターフェイス ICoreWebView2ContentLoadingEventArgs</span><span class="sxs-lookup"><span data-stu-id="6e5e1-104">interface ICoreWebView2ContentLoadingEventArgs</span></span> 

```
interface ICoreWebView2ContentLoadingEventArgs
  : public IUnknown
```

<span data-ttu-id="6e5e1-105">ContentLoading イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-105">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="6e5e1-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="6e5e1-106">Summary</span></span>

 <span data-ttu-id="6e5e1-107">Members</span><span class="sxs-lookup"><span data-stu-id="6e5e1-107">Members</span></span>                        | <span data-ttu-id="6e5e1-108">説明</span><span class="sxs-lookup"><span data-stu-id="6e5e1-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6e5e1-109">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="6e5e1-109">get_IsErrorPage</span></span>](#get_iserrorpage) | <span data-ttu-id="6e5e1-110">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-110">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="6e5e1-111">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="6e5e1-111">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="6e5e1-112">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-112">The ID of the navigation.</span></span>

## <span data-ttu-id="6e5e1-113">Members</span><span class="sxs-lookup"><span data-stu-id="6e5e1-113">Members</span></span>

#### <span data-ttu-id="6e5e1-114">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="6e5e1-114">get_IsErrorPage</span></span> 

<span data-ttu-id="6e5e1-115">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-115">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="6e5e1-116">パブリック HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* IsErrorPage)</span><span class="sxs-lookup"><span data-stu-id="6e5e1-116">public HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* isErrorPage)</span></span>

#### <span data-ttu-id="6e5e1-117">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="6e5e1-117">get_NavigationId</span></span> 

<span data-ttu-id="6e5e1-118">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="6e5e1-118">The ID of the navigation.</span></span>

> <span data-ttu-id="6e5e1-119">パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span><span class="sxs-lookup"><span data-stu-id="6e5e1-119">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

