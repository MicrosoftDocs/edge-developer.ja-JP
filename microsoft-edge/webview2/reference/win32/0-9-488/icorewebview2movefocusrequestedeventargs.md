---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2MoveFocusRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 38cd243a5af924da008c3735e43489684deabd0e
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883701"
---
# <span data-ttu-id="b124d-104">0.9.515-インターフェイス ICoreWebView2MoveFocusRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="b124d-104">0.9.515 - interface ICoreWebView2MoveFocusRequestedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2MoveFocusRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="b124d-105">MoveFocusRequested されたイベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="b124d-105">Event args for the MoveFocusRequested event.</span></span>

## <span data-ttu-id="b124d-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="b124d-106">Summary</span></span>

 <span data-ttu-id="b124d-107">Members</span><span class="sxs-lookup"><span data-stu-id="b124d-107">Members</span></span>                        | <span data-ttu-id="b124d-108">説明</span><span class="sxs-lookup"><span data-stu-id="b124d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b124d-109">get_Handled</span><span class="sxs-lookup"><span data-stu-id="b124d-109">get_Handled</span></span>](#get_handled) | <span data-ttu-id="b124d-110">イベントがアプリによって処理されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b124d-110">Indicate whether the event has been handled by the app.</span></span>
[<span data-ttu-id="b124d-111">get_Reason</span><span class="sxs-lookup"><span data-stu-id="b124d-111">get_Reason</span></span>](#get_reason) | <span data-ttu-id="b124d-112">MoveFocus 要求されたイベントを WebView が発生させる理由。</span><span class="sxs-lookup"><span data-stu-id="b124d-112">The reason for WebView to fire the MoveFocus Requested event.</span></span>
[<span data-ttu-id="b124d-113">put_Handled</span><span class="sxs-lookup"><span data-stu-id="b124d-113">put_Handled</span></span>](#put_handled) | <span data-ttu-id="b124d-114">Handled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="b124d-114">Set the Handled property.</span></span>

## <span data-ttu-id="b124d-115">Members</span><span class="sxs-lookup"><span data-stu-id="b124d-115">Members</span></span>

#### <span data-ttu-id="b124d-116">get_Handled</span><span class="sxs-lookup"><span data-stu-id="b124d-116">get_Handled</span></span> 

<span data-ttu-id="b124d-117">イベントがアプリによって処理されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b124d-117">Indicate whether the event has been handled by the app.</span></span>

> <span data-ttu-id="b124d-118">パブリック HRESULT [get_Handled](#get_handled)(ブール \* 値)</span><span class="sxs-lookup"><span data-stu-id="b124d-118">public HRESULT [get_Handled](#get_handled)(BOOL \* value)</span></span>

<span data-ttu-id="b124d-119">アプリがフォーカスを目的の場所に移動した場合は、Handled プロパティを TRUE に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b124d-119">If the app has moved the focus to its desired location, it should set Handled property to TRUE.</span></span> <span data-ttu-id="b124d-120">イベントハンドラーから制御が返された後、Handled プロパティが false の場合は、既定のアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="b124d-120">When Handled property is false after the event handler returns, default action will be taken.</span></span> <span data-ttu-id="b124d-121">既定のアクションでは、アプリで次のタブ位置の子ウィンドウを検索し、フォーカスをそのウィンドウに移動しようとします。</span><span class="sxs-lookup"><span data-stu-id="b124d-121">The default action is to try to find the next tab stop child window in the app and try to move focus to that window.</span></span> <span data-ttu-id="b124d-122">フォーカスを移動できるその他のウィンドウがない場合は、WebView の web コンテンツ内でフォーカスが変更されます。</span><span class="sxs-lookup"><span data-stu-id="b124d-122">If there is no other such window to move focus to, focus will be cycled within the WebView's web content.</span></span>

#### <span data-ttu-id="b124d-123">get_Reason</span><span class="sxs-lookup"><span data-stu-id="b124d-123">get_Reason</span></span> 

<span data-ttu-id="b124d-124">MoveFocus 要求されたイベントを WebView が発生させる理由。</span><span class="sxs-lookup"><span data-stu-id="b124d-124">The reason for WebView to fire the MoveFocus Requested event.</span></span>

> <span data-ttu-id="b124d-125">パブリック HRESULT [get_Reason](#get_reason)(COREWEBVIEW2_MOVE_FOCUS_REASON \* 値)</span><span class="sxs-lookup"><span data-stu-id="b124d-125">public HRESULT [get_Reason](#get_reason)(COREWEBVIEW2_MOVE_FOCUS_REASON \* value)</span></span>

#### <span data-ttu-id="b124d-126">put_Handled</span><span class="sxs-lookup"><span data-stu-id="b124d-126">put_Handled</span></span> 

<span data-ttu-id="b124d-127">Handled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="b124d-127">Set the Handled property.</span></span>

> <span data-ttu-id="b124d-128">パブリック HRESULT [put_Handled](#put_handled)(BOOL 値)</span><span class="sxs-lookup"><span data-stu-id="b124d-128">public HRESULT [put_Handled](#put_handled)(BOOL value)</span></span>

