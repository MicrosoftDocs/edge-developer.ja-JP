---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2MoveFocusRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2MoveFocusRequestedEventArgs
ms.openlocfilehash: 7d86b0129c126b39ae8200550a024819e2004b49
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010027"
---
# <span data-ttu-id="22078-104">0.9.579-インターフェイス ICoreWebView2MoveFocusRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="22078-104">0.9.579 - interface ICoreWebView2MoveFocusRequestedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2MoveFocusRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="22078-105">MoveFocusRequested されたイベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="22078-105">Event args for the MoveFocusRequested event.</span></span>

## <span data-ttu-id="22078-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="22078-106">Summary</span></span>

 <span data-ttu-id="22078-107">Members</span><span class="sxs-lookup"><span data-stu-id="22078-107">Members</span></span>                        | <span data-ttu-id="22078-108">説明</span><span class="sxs-lookup"><span data-stu-id="22078-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="22078-109">get_Handled</span><span class="sxs-lookup"><span data-stu-id="22078-109">get_Handled</span></span>](#get_handled) | <span data-ttu-id="22078-110">イベントがアプリによって処理されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="22078-110">Indicate whether the event has been handled by the app.</span></span>
[<span data-ttu-id="22078-111">get_Reason</span><span class="sxs-lookup"><span data-stu-id="22078-111">get_Reason</span></span>](#get_reason) | <span data-ttu-id="22078-112">MoveFocus 要求されたイベントを WebView が発生させる理由。</span><span class="sxs-lookup"><span data-stu-id="22078-112">The reason for WebView to fire the MoveFocus Requested event.</span></span>
[<span data-ttu-id="22078-113">put_Handled</span><span class="sxs-lookup"><span data-stu-id="22078-113">put_Handled</span></span>](#put_handled) | <span data-ttu-id="22078-114">Handled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="22078-114">Set the Handled property.</span></span>

## <span data-ttu-id="22078-115">Members</span><span class="sxs-lookup"><span data-stu-id="22078-115">Members</span></span>

#### <span data-ttu-id="22078-116">get_Handled</span><span class="sxs-lookup"><span data-stu-id="22078-116">get_Handled</span></span> 

<span data-ttu-id="22078-117">イベントがアプリによって処理されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="22078-117">Indicate whether the event has been handled by the app.</span></span>

> <span data-ttu-id="22078-118">パブリック HRESULT [get_Handled](#get_handled)(ブール \* 値)</span><span class="sxs-lookup"><span data-stu-id="22078-118">public HRESULT [get_Handled](#get_handled)(BOOL \* value)</span></span>

<span data-ttu-id="22078-119">アプリがフォーカスを目的の場所に移動した場合は、Handled プロパティを TRUE に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22078-119">If the app has moved the focus to its desired location, it should set Handled property to TRUE.</span></span> <span data-ttu-id="22078-120">イベントハンドラーから制御が返された後、Handled プロパティが false の場合は、既定のアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="22078-120">When Handled property is false after the event handler returns, default action will be taken.</span></span> <span data-ttu-id="22078-121">既定のアクションでは、アプリで次のタブ位置の子ウィンドウを検索し、フォーカスをそのウィンドウに移動しようとします。</span><span class="sxs-lookup"><span data-stu-id="22078-121">The default action is to try to find the next tab stop child window in the app and try to move focus to that window.</span></span> <span data-ttu-id="22078-122">フォーカスを移動できるその他のウィンドウがない場合は、WebView の web コンテンツ内でフォーカスが変更されます。</span><span class="sxs-lookup"><span data-stu-id="22078-122">If there is no other such window to move focus to, focus will be cycled within the WebView's web content.</span></span>

#### <span data-ttu-id="22078-123">get_Reason</span><span class="sxs-lookup"><span data-stu-id="22078-123">get_Reason</span></span> 

<span data-ttu-id="22078-124">MoveFocus 要求されたイベントを WebView が発生させる理由。</span><span class="sxs-lookup"><span data-stu-id="22078-124">The reason for WebView to fire the MoveFocus Requested event.</span></span>

> <span data-ttu-id="22078-125">パブリック HRESULT [get_Reason](#get_reason)(COREWEBVIEW2_MOVE_FOCUS_REASON \* 値)</span><span class="sxs-lookup"><span data-stu-id="22078-125">public HRESULT [get_Reason](#get_reason)(COREWEBVIEW2_MOVE_FOCUS_REASON \* value)</span></span>

#### <span data-ttu-id="22078-126">put_Handled</span><span class="sxs-lookup"><span data-stu-id="22078-126">put_Handled</span></span> 

<span data-ttu-id="22078-127">Handled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="22078-127">Set the Handled property.</span></span>

> <span data-ttu-id="22078-128">パブリック HRESULT [put_Handled](#put_handled)(BOOL 値)</span><span class="sxs-lookup"><span data-stu-id="22078-128">public HRESULT [put_Handled](#put_handled)(BOOL value)</span></span>

