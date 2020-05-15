---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: 2e3afec26b0e09a80182118f74b6f50733b0c71a
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654355"
---
# <span data-ttu-id="97dce-104">インターフェイス IWebView2MoveFocusRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="97dce-104">interface IWebView2MoveFocusRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="97dce-105">このインターフェイスは、SDK バージョン0.8.355 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="97dce-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="97dce-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97dce-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2MoveFocusRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="97dce-107">MoveFocusRequested されたイベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="97dce-107">Event args for the MoveFocusRequested event.</span></span>

## <span data-ttu-id="97dce-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="97dce-108">Summary</span></span>

 <span data-ttu-id="97dce-109">Members</span><span class="sxs-lookup"><span data-stu-id="97dce-109">Members</span></span>                        | <span data-ttu-id="97dce-110">説明</span><span class="sxs-lookup"><span data-stu-id="97dce-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="97dce-111">get_Reason</span><span class="sxs-lookup"><span data-stu-id="97dce-111">get_Reason</span></span>](#get_reason) | <span data-ttu-id="97dce-112">MoveFocus 要求されたイベントを WebView が発生させる理由。</span><span class="sxs-lookup"><span data-stu-id="97dce-112">The reason for WebView to fire the MoveFocus Requested event.</span></span>
[<span data-ttu-id="97dce-113">get_Handled</span><span class="sxs-lookup"><span data-stu-id="97dce-113">get_Handled</span></span>](#get_handled) | <span data-ttu-id="97dce-114">イベントがアプリによって処理されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="97dce-114">Indicate whether the event has been handled by the app.</span></span>
[<span data-ttu-id="97dce-115">put_Handled</span><span class="sxs-lookup"><span data-stu-id="97dce-115">put_Handled</span></span>](#put_handled) | <span data-ttu-id="97dce-116">Handled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="97dce-116">Set the Handled property.</span></span>

## <span data-ttu-id="97dce-117">Members</span><span class="sxs-lookup"><span data-stu-id="97dce-117">Members</span></span>

#### <span data-ttu-id="97dce-118">get_Reason</span><span class="sxs-lookup"><span data-stu-id="97dce-118">get_Reason</span></span> 

<span data-ttu-id="97dce-119">MoveFocus 要求されたイベントを WebView が発生させる理由。</span><span class="sxs-lookup"><span data-stu-id="97dce-119">The reason for WebView to fire the MoveFocus Requested event.</span></span>

> <span data-ttu-id="97dce-120">パブリック HRESULT [get_Reason](#get_reason)(WEBVIEW2_MOVE_FOCUS_REASON \* 値)</span><span class="sxs-lookup"><span data-stu-id="97dce-120">public HRESULT [get_Reason](#get_reason)(WEBVIEW2_MOVE_FOCUS_REASON \* value)</span></span>

#### <span data-ttu-id="97dce-121">get_Handled</span><span class="sxs-lookup"><span data-stu-id="97dce-121">get_Handled</span></span> 

<span data-ttu-id="97dce-122">イベントがアプリによって処理されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="97dce-122">Indicate whether the event has been handled by the app.</span></span>

> <span data-ttu-id="97dce-123">パブリック HRESULT [get_Handled](#get_handled)(ブール \* 値)</span><span class="sxs-lookup"><span data-stu-id="97dce-123">public HRESULT [get_Handled](#get_handled)(BOOL \* value)</span></span>

<span data-ttu-id="97dce-124">アプリがフォーカスを目的の場所に移動した場合は、Handled プロパティを TRUE に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97dce-124">If the app has moved the focus to its desired location, it should set Handled property to TRUE.</span></span> <span data-ttu-id="97dce-125">イベントハンドラーから制御が返された後、Handled プロパティが false の場合は、既定のアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="97dce-125">When Handled property is false after the event handler returns, default action will be taken.</span></span> <span data-ttu-id="97dce-126">既定のアクションでは、アプリで次のタブ位置の子ウィンドウを検索し、フォーカスをそのウィンドウに移動しようとします。</span><span class="sxs-lookup"><span data-stu-id="97dce-126">The default action is to try to find the next tab stop child window in the app and try to move focus to that window.</span></span> <span data-ttu-id="97dce-127">フォーカスを移動できるその他のウィンドウがない場合は、WebView の web コンテンツ内でフォーカスが変更されます。</span><span class="sxs-lookup"><span data-stu-id="97dce-127">If there is no other such window to move focus to, focus will be cycled within the WebView's web content.</span></span>

#### <span data-ttu-id="97dce-128">put_Handled</span><span class="sxs-lookup"><span data-stu-id="97dce-128">put_Handled</span></span> 

<span data-ttu-id="97dce-129">Handled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="97dce-129">Set the Handled property.</span></span>

> <span data-ttu-id="97dce-130">パブリック HRESULT [put_Handled](#put_handled)(BOOL 値)</span><span class="sxs-lookup"><span data-stu-id="97dce-130">public HRESULT [put_Handled](#put_handled)(BOOL value)</span></span>

