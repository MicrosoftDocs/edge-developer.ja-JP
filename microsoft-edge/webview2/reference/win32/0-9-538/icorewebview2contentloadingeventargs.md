---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ContentLoadingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ContentLoadingEventArgs
ms.openlocfilehash: 571aae9e1e00938c9bf0f3fb872fccf340269105
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877456"
---
# <span data-ttu-id="a8215-104">インターフェイス ICoreWebView2ContentLoadingEventArgs</span><span class="sxs-lookup"><span data-stu-id="a8215-104">interface ICoreWebView2ContentLoadingEventArgs</span></span> 

```
interface ICoreWebView2ContentLoadingEventArgs
  : public IUnknown
```

<span data-ttu-id="a8215-105">ContentLoading イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="a8215-105">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="a8215-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="a8215-106">Summary</span></span>

 <span data-ttu-id="a8215-107">Members</span><span class="sxs-lookup"><span data-stu-id="a8215-107">Members</span></span>                        | <span data-ttu-id="a8215-108">説明</span><span class="sxs-lookup"><span data-stu-id="a8215-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a8215-109">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="a8215-109">get_IsErrorPage</span></span>](#get_iserrorpage) | <span data-ttu-id="a8215-110">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="a8215-110">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="a8215-111">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="a8215-111">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="a8215-112">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="a8215-112">The ID of the navigation.</span></span>

## <span data-ttu-id="a8215-113">Members</span><span class="sxs-lookup"><span data-stu-id="a8215-113">Members</span></span>

#### <span data-ttu-id="a8215-114">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="a8215-114">get_IsErrorPage</span></span> 

<span data-ttu-id="a8215-115">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="a8215-115">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="a8215-116">パブリック HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* IsErrorPage)</span><span class="sxs-lookup"><span data-stu-id="a8215-116">public HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* isErrorPage)</span></span>

#### <span data-ttu-id="a8215-117">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="a8215-117">get_NavigationId</span></span> 

<span data-ttu-id="a8215-118">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="a8215-118">The ID of the navigation.</span></span>

> <span data-ttu-id="a8215-119">パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span><span class="sxs-lookup"><span data-stu-id="a8215-119">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

