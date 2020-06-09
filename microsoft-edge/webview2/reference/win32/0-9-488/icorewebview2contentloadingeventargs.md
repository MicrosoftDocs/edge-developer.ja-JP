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
ms.openlocfilehash: c720b700257554891f13477f5f3508e331ac6b25
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698205"
---
# <span data-ttu-id="f5748-104">インターフェイス ICoreWebView2ContentLoadingEventArgs</span><span class="sxs-lookup"><span data-stu-id="f5748-104">interface ICoreWebView2ContentLoadingEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="f5748-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f5748-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="f5748-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5748-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ContentLoadingEventArgs
  : public IUnknown
```

<span data-ttu-id="f5748-107">ContentLoading イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="f5748-107">Event args for the ContentLoading event.</span></span>

## <span data-ttu-id="f5748-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="f5748-108">Summary</span></span>

 <span data-ttu-id="f5748-109">Members</span><span class="sxs-lookup"><span data-stu-id="f5748-109">Members</span></span>                        | <span data-ttu-id="f5748-110">説明</span><span class="sxs-lookup"><span data-stu-id="f5748-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f5748-111">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="f5748-111">get_IsErrorPage</span></span>](#get_iserrorpage) | <span data-ttu-id="f5748-112">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="f5748-112">True if the loaded content is an error page.</span></span>
[<span data-ttu-id="f5748-113">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="f5748-113">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="f5748-114">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="f5748-114">The ID of the navigation.</span></span>

## <span data-ttu-id="f5748-115">Members</span><span class="sxs-lookup"><span data-stu-id="f5748-115">Members</span></span>

#### <span data-ttu-id="f5748-116">get_IsErrorPage</span><span class="sxs-lookup"><span data-stu-id="f5748-116">get_IsErrorPage</span></span> 

<span data-ttu-id="f5748-117">読み込まれたコンテンツがエラーページの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="f5748-117">True if the loaded content is an error page.</span></span>

> <span data-ttu-id="f5748-118">パブリック HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* IsErrorPage)</span><span class="sxs-lookup"><span data-stu-id="f5748-118">public HRESULT [get_IsErrorPage](#get_iserrorpage)(BOOL \* isErrorPage)</span></span>

#### <span data-ttu-id="f5748-119">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="f5748-119">get_NavigationId</span></span> 

<span data-ttu-id="f5748-120">ナビゲーションの ID です。</span><span class="sxs-lookup"><span data-stu-id="f5748-120">The ID of the navigation.</span></span>

> <span data-ttu-id="f5748-121">パブリック HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span><span class="sxs-lookup"><span data-stu-id="f5748-121">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

