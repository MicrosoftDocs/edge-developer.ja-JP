---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/28/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: de0319060b6e618c30fc685815bcbcc41e8c3005
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697848"
---
# <span data-ttu-id="60816-104">インターフェイス ICoreWebView2MoveFocusRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="60816-104">interface ICoreWebView2MoveFocusRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="60816-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="60816-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="60816-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60816-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2MoveFocusRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="60816-107">MoveFocusRequested されたイベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="60816-107">Event args for the MoveFocusRequested event.</span></span>

## <span data-ttu-id="60816-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="60816-108">Summary</span></span>

 <span data-ttu-id="60816-109">Members</span><span class="sxs-lookup"><span data-stu-id="60816-109">Members</span></span>                        | <span data-ttu-id="60816-110">説明</span><span class="sxs-lookup"><span data-stu-id="60816-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="60816-111">get_Handled</span><span class="sxs-lookup"><span data-stu-id="60816-111">get_Handled</span></span>](#get_handled) | <span data-ttu-id="60816-112">イベントがアプリによって処理されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="60816-112">Indicate whether the event has been handled by the app.</span></span>
[<span data-ttu-id="60816-113">get_Reason</span><span class="sxs-lookup"><span data-stu-id="60816-113">get_Reason</span></span>](#get_reason) | <span data-ttu-id="60816-114">MoveFocus 要求されたイベントを WebView が発生させる理由。</span><span class="sxs-lookup"><span data-stu-id="60816-114">The reason for WebView to fire the MoveFocus Requested event.</span></span>
[<span data-ttu-id="60816-115">put_Handled</span><span class="sxs-lookup"><span data-stu-id="60816-115">put_Handled</span></span>](#put_handled) | <span data-ttu-id="60816-116">Handled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="60816-116">Set the Handled property.</span></span>

## <span data-ttu-id="60816-117">Members</span><span class="sxs-lookup"><span data-stu-id="60816-117">Members</span></span>

#### <span data-ttu-id="60816-118">get_Handled</span><span class="sxs-lookup"><span data-stu-id="60816-118">get_Handled</span></span> 

<span data-ttu-id="60816-119">イベントがアプリによって処理されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="60816-119">Indicate whether the event has been handled by the app.</span></span>

> <span data-ttu-id="60816-120">パブリック HRESULT [get_Handled](#get_handled)(ブール \* 値)</span><span class="sxs-lookup"><span data-stu-id="60816-120">public HRESULT [get_Handled](#get_handled)(BOOL \* value)</span></span>

<span data-ttu-id="60816-121">アプリがフォーカスを目的の場所に移動した場合は、Handled プロパティを TRUE に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60816-121">If the app has moved the focus to its desired location, it should set Handled property to TRUE.</span></span> <span data-ttu-id="60816-122">イベントハンドラーから制御が返された後、Handled プロパティが false の場合は、既定のアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="60816-122">When Handled property is false after the event handler returns, default action will be taken.</span></span> <span data-ttu-id="60816-123">既定のアクションでは、アプリで次のタブ位置の子ウィンドウを検索し、フォーカスをそのウィンドウに移動しようとします。</span><span class="sxs-lookup"><span data-stu-id="60816-123">The default action is to try to find the next tab stop child window in the app and try to move focus to that window.</span></span> <span data-ttu-id="60816-124">フォーカスを移動できるその他のウィンドウがない場合は、WebView の web コンテンツ内でフォーカスが変更されます。</span><span class="sxs-lookup"><span data-stu-id="60816-124">If there is no other such window to move focus to, focus will be cycled within the WebView's web content.</span></span>

#### <span data-ttu-id="60816-125">get_Reason</span><span class="sxs-lookup"><span data-stu-id="60816-125">get_Reason</span></span> 

<span data-ttu-id="60816-126">MoveFocus 要求されたイベントを WebView が発生させる理由。</span><span class="sxs-lookup"><span data-stu-id="60816-126">The reason for WebView to fire the MoveFocus Requested event.</span></span>

> <span data-ttu-id="60816-127">パブリック HRESULT [get_Reason](#get_reason)(COREWEBVIEW2_MOVE_FOCUS_REASON \* 値)</span><span class="sxs-lookup"><span data-stu-id="60816-127">public HRESULT [get_Reason](#get_reason)(COREWEBVIEW2_MOVE_FOCUS_REASON \* value)</span></span>

#### <span data-ttu-id="60816-128">put_Handled</span><span class="sxs-lookup"><span data-stu-id="60816-128">put_Handled</span></span> 

<span data-ttu-id="60816-129">Handled プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="60816-129">Set the Handled property.</span></span>

> <span data-ttu-id="60816-130">パブリック HRESULT [put_Handled](#put_handled)(BOOL 値)</span><span class="sxs-lookup"><span data-stu-id="60816-130">public HRESULT [put_Handled](#put_handled)(BOOL value)</span></span>

