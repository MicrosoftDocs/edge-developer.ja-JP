---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2ContentLoadingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ContentLoadingEventArgs
ms.openlocfilehash: d70673714e3641e19f5c3d6367278c0c7bd2729b
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010300"
---
# <span data-ttu-id="5679b-104">0.9.579-インターフェイス ICoreWebView2ContentLoadingEventArgs</span><span class="sxs-lookup"><span data-stu-id="5679b-104">0.9.579 - interface ICoreWebView2ContentLoadingEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ContentLoadingEventArgs
  : public IUnknown
```

<span data-ttu-id="5679b-105">ContentLoading イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="5679b-105">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="5679b-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="5679b-106">Summary</span></span>

 <span data-ttu-id="5679b-107">Members</span><span class="sxs-lookup"><span data-stu-id="5679b-107">Members</span></span>                        | <span data-ttu-id="5679b-108">説明</span><span class="sxs-lookup"><span data-stu-id="5679b-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5679b-109">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="5679b-109">get_IsErrorPage</span></span>](#get_iserrorpage) | <span data-ttu-id="5679b-110">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="5679b-110">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="5679b-111">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="5679b-111">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="5679b-112">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="5679b-112">The ID of the navigation.</span></span>

## <span data-ttu-id="5679b-113">Members</span><span class="sxs-lookup"><span data-stu-id="5679b-113">Members</span></span>

#### <span data-ttu-id="5679b-114">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="5679b-114">get_IsErrorPage</span></span> 

<span data-ttu-id="5679b-115">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="5679b-115">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="5679b-116">パブリック HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* IsErrorPage)</span><span class="sxs-lookup"><span data-stu-id="5679b-116">public HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* isErrorPage)</span></span>

#### <span data-ttu-id="5679b-117">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="5679b-117">get_NavigationId</span></span> 

<span data-ttu-id="5679b-118">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="5679b-118">The ID of the navigation.</span></span>

> <span data-ttu-id="5679b-119">パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span><span class="sxs-lookup"><span data-stu-id="5679b-119">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

