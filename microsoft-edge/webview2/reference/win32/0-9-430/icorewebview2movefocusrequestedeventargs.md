---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2MoveFocusRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 643e2e998cc8ca70bfd90fbcb9bbf1f6c690322b
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884548"
---
# <span data-ttu-id="00065-104">0.9.430-インターフェイス ICoreWebView2MoveFocusRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="00065-104">0.9.430 - interface ICoreWebView2MoveFocusRequestedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2MoveFocusRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="00065-105">MoveFocusRequested されたイベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="00065-105">Event args for the MoveFocusRequested event.</span></span>

## <span data-ttu-id="00065-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="00065-106">Summary</span></span>

 <span data-ttu-id="00065-107">Members</span><span class="sxs-lookup"><span data-stu-id="00065-107">Members</span></span>                        | <span data-ttu-id="00065-108">説明</span><span class="sxs-lookup"><span data-stu-id="00065-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="00065-109">get_Reason</span><span class="sxs-lookup"><span data-stu-id="00065-109">get_Reason</span></span>](#get_reason) | <span data-ttu-id="00065-110">MoveFocus 要求されたイベントを WebView が発生させる理由。</span><span class="sxs-lookup"><span data-stu-id="00065-110">The reason for WebView to fire the MoveFocus Requested event.</span></span>
[<span data-ttu-id="00065-111">get_Handled</span><span class="sxs-lookup"><span data-stu-id="00065-111">get_Handled</span></span>](#get_handled) | <span data-ttu-id="00065-112">イベントがアプリによって処理されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="00065-112">Indicate whether the event has been handled by the app.</span></span>
[<span data-ttu-id="00065-113">put_Handled</span><span class="sxs-lookup"><span data-stu-id="00065-113">put_Handled</span></span>](#put_handled) | <span data-ttu-id="00065-114">Handled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="00065-114">Set the Handled property.</span></span>

## <span data-ttu-id="00065-115">Members</span><span class="sxs-lookup"><span data-stu-id="00065-115">Members</span></span>

#### <span data-ttu-id="00065-116">get_Reason</span><span class="sxs-lookup"><span data-stu-id="00065-116">get_Reason</span></span> 

<span data-ttu-id="00065-117">MoveFocus 要求されたイベントを WebView が発生させる理由。</span><span class="sxs-lookup"><span data-stu-id="00065-117">The reason for WebView to fire the MoveFocus Requested event.</span></span>

> <span data-ttu-id="00065-118">パブリック HRESULT [get_Reason](#get_reason)(CORE_WEBVIEW2_MOVE_FOCUS_REASON \* 値)</span><span class="sxs-lookup"><span data-stu-id="00065-118">public HRESULT [get_Reason](#get_reason)(CORE_WEBVIEW2_MOVE_FOCUS_REASON \* value)</span></span>

#### <span data-ttu-id="00065-119">get_Handled</span><span class="sxs-lookup"><span data-stu-id="00065-119">get_Handled</span></span> 

<span data-ttu-id="00065-120">イベントがアプリによって処理されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="00065-120">Indicate whether the event has been handled by the app.</span></span>

> <span data-ttu-id="00065-121">パブリック HRESULT [get_Handled](#get_handled)(ブール \* 値)</span><span class="sxs-lookup"><span data-stu-id="00065-121">public HRESULT [get_Handled](#get_handled)(BOOL \* value)</span></span>

<span data-ttu-id="00065-122">アプリがフォーカスを目的の場所に移動した場合は、Handled プロパティを TRUE に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00065-122">If the app has moved the focus to its desired location, it should set Handled property to TRUE.</span></span> <span data-ttu-id="00065-123">イベントハンドラーから制御が返された後、Handled プロパティが false の場合は、既定のアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="00065-123">When Handled property is false after the event handler returns, default action will be taken.</span></span> <span data-ttu-id="00065-124">既定のアクションでは、アプリで次のタブ位置の子ウィンドウを検索し、フォーカスをそのウィンドウに移動しようとします。</span><span class="sxs-lookup"><span data-stu-id="00065-124">The default action is to try to find the next tab stop child window in the app and try to move focus to that window.</span></span> <span data-ttu-id="00065-125">フォーカスを移動できるその他のウィンドウがない場合は、WebView の web コンテンツ内でフォーカスが変更されます。</span><span class="sxs-lookup"><span data-stu-id="00065-125">If there is no other such window to move focus to, focus will be cycled within the WebView's web content.</span></span>

#### <span data-ttu-id="00065-126">put_Handled</span><span class="sxs-lookup"><span data-stu-id="00065-126">put_Handled</span></span> 

<span data-ttu-id="00065-127">Handled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="00065-127">Set the Handled property.</span></span>

> <span data-ttu-id="00065-128">パブリック HRESULT [put_Handled](#put_handled)(BOOL 値)</span><span class="sxs-lookup"><span data-stu-id="00065-128">public HRESULT [put_Handled](#put_handled)(BOOL value)</span></span>

