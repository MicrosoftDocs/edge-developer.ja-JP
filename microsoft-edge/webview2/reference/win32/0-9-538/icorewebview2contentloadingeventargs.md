---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 8acec97ec6060cd53adc3821f6a51db2048935fb
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699024"
---
# <span data-ttu-id="28e4a-104">インターフェイス ICoreWebView2ContentLoadingEventArgs</span><span class="sxs-lookup"><span data-stu-id="28e4a-104">interface ICoreWebView2ContentLoadingEventArgs</span></span> 

```
interface ICoreWebView2ContentLoadingEventArgs
  : public IUnknown
```

<span data-ttu-id="28e4a-105">ContentLoading イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="28e4a-105">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="28e4a-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="28e4a-106">Summary</span></span>

 <span data-ttu-id="28e4a-107">Members</span><span class="sxs-lookup"><span data-stu-id="28e4a-107">Members</span></span>                        | <span data-ttu-id="28e4a-108">説明</span><span class="sxs-lookup"><span data-stu-id="28e4a-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="28e4a-109">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="28e4a-109">get_IsErrorPage</span></span>](#get_iserrorpage) | <span data-ttu-id="28e4a-110">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="28e4a-110">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="28e4a-111">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="28e4a-111">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="28e4a-112">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="28e4a-112">The ID of the navigation.</span></span>

## <span data-ttu-id="28e4a-113">Members</span><span class="sxs-lookup"><span data-stu-id="28e4a-113">Members</span></span>

#### <span data-ttu-id="28e4a-114">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="28e4a-114">get_IsErrorPage</span></span> 

<span data-ttu-id="28e4a-115">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="28e4a-115">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="28e4a-116">パブリック HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* IsErrorPage)</span><span class="sxs-lookup"><span data-stu-id="28e4a-116">public HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* isErrorPage)</span></span>

#### <span data-ttu-id="28e4a-117">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="28e4a-117">get_NavigationId</span></span> 

<span data-ttu-id="28e4a-118">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="28e4a-118">The ID of the navigation.</span></span>

> <span data-ttu-id="28e4a-119">パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span><span class="sxs-lookup"><span data-stu-id="28e4a-119">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

