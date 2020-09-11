---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ContentLoadingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ContentLoadingEventArgs
ms.openlocfilehash: 229389c6859363ef9a7c3fbf7719dbe30a061875
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012385"
---
# <span data-ttu-id="35bb4-104">インターフェイス ICoreWebView2ContentLoadingEventArgs</span><span class="sxs-lookup"><span data-stu-id="35bb4-104">interface ICoreWebView2ContentLoadingEventArgs</span></span> 

```
interface ICoreWebView2ContentLoadingEventArgs
  : public IUnknown
```

<span data-ttu-id="35bb4-105">ContentLoading イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="35bb4-105">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="35bb4-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="35bb4-106">Summary</span></span>

 <span data-ttu-id="35bb4-107">Members</span><span class="sxs-lookup"><span data-stu-id="35bb4-107">Members</span></span>                        | <span data-ttu-id="35bb4-108">説明</span><span class="sxs-lookup"><span data-stu-id="35bb4-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="35bb4-109">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="35bb4-109">get_IsErrorPage</span></span>](#get_iserrorpage) | <span data-ttu-id="35bb4-110">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="35bb4-110">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="35bb4-111">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="35bb4-111">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="35bb4-112">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="35bb4-112">The ID of the navigation.</span></span>

## <span data-ttu-id="35bb4-113">Members</span><span class="sxs-lookup"><span data-stu-id="35bb4-113">Members</span></span>

#### <span data-ttu-id="35bb4-114">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="35bb4-114">get_IsErrorPage</span></span> 

<span data-ttu-id="35bb4-115">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="35bb4-115">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="35bb4-116">パブリック HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* IsErrorPage)</span><span class="sxs-lookup"><span data-stu-id="35bb4-116">public HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* isErrorPage)</span></span>

#### <span data-ttu-id="35bb4-117">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="35bb4-117">get_NavigationId</span></span> 

<span data-ttu-id="35bb4-118">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="35bb4-118">The ID of the navigation.</span></span>

> <span data-ttu-id="35bb4-119">パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigationid)</span><span class="sxs-lookup"><span data-stu-id="35bb4-119">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigationId)</span></span>

