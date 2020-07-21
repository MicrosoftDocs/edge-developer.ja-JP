---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2ContentLoadingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 32b0f46b00195a265238541f8715ec21ca3757a1
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883876"
---
# <span data-ttu-id="d1f0c-104">0.9.515-インターフェイス ICoreWebView2ContentLoadingEventArgs</span><span class="sxs-lookup"><span data-stu-id="d1f0c-104">0.9.515 - interface ICoreWebView2ContentLoadingEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ContentLoadingEventArgs
  : public IUnknown
```

<span data-ttu-id="d1f0c-105">ContentLoading イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="d1f0c-105">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="d1f0c-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="d1f0c-106">Summary</span></span>

 <span data-ttu-id="d1f0c-107">Members</span><span class="sxs-lookup"><span data-stu-id="d1f0c-107">Members</span></span>                        | <span data-ttu-id="d1f0c-108">説明</span><span class="sxs-lookup"><span data-stu-id="d1f0c-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d1f0c-109">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="d1f0c-109">get_IsErrorPage</span></span>](#get_iserrorpage) | <span data-ttu-id="d1f0c-110">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="d1f0c-110">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="d1f0c-111">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="d1f0c-111">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="d1f0c-112">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="d1f0c-112">The ID of the navigation.</span></span>

## <span data-ttu-id="d1f0c-113">Members</span><span class="sxs-lookup"><span data-stu-id="d1f0c-113">Members</span></span>

#### <span data-ttu-id="d1f0c-114">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="d1f0c-114">get_IsErrorPage</span></span> 

<span data-ttu-id="d1f0c-115">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="d1f0c-115">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="d1f0c-116">パブリック HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* IsErrorPage)</span><span class="sxs-lookup"><span data-stu-id="d1f0c-116">public HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* isErrorPage)</span></span>

#### <span data-ttu-id="d1f0c-117">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="d1f0c-117">get_NavigationId</span></span> 

<span data-ttu-id="d1f0c-118">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="d1f0c-118">The ID of the navigation.</span></span>

> <span data-ttu-id="d1f0c-119">パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span><span class="sxs-lookup"><span data-stu-id="d1f0c-119">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

