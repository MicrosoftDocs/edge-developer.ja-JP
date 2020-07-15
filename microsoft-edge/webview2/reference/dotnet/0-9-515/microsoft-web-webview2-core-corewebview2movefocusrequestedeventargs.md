---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (CoreWebView2MoveFocusRequestedEventArgs の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 37d64a18589df936383efe05317c1a625b841a6e
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877659"
---
# <span data-ttu-id="48e26-104">0.9.515 クラスの WebView2 クラス (CoreWebView2MoveFocusRequestedEventArgs)</span><span class="sxs-lookup"><span data-stu-id="48e26-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2MoveFocusRequestedEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="48e26-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="48e26-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="48e26-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48e26-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="48e26-107">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="48e26-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="48e26-108">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="48e26-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="48e26-109">MoveFocusRequested されたイベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="48e26-109">Event args for the MoveFocusRequested event.</span></span>

## <span data-ttu-id="48e26-110">まとめ</span><span class="sxs-lookup"><span data-stu-id="48e26-110">Summary</span></span>

 <span data-ttu-id="48e26-111">Members</span><span class="sxs-lookup"><span data-stu-id="48e26-111">Members</span></span>                        | <span data-ttu-id="48e26-112">説明</span><span class="sxs-lookup"><span data-stu-id="48e26-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="48e26-113">Handled</span><span class="sxs-lookup"><span data-stu-id="48e26-113">Handled</span></span>](#handled) | <span data-ttu-id="48e26-114">イベントがアプリによって処理されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="48e26-114">Indicate whether the event has been handled by the app.</span></span>
[<span data-ttu-id="48e26-115">理由</span><span class="sxs-lookup"><span data-stu-id="48e26-115">Reason</span></span>](#reason) | <span data-ttu-id="48e26-116">MoveFocus 要求されたイベントを WebView が発生させる理由。</span><span class="sxs-lookup"><span data-stu-id="48e26-116">The reason for WebView to fire the MoveFocus Requested event.</span></span>

## <span data-ttu-id="48e26-117">Members</span><span class="sxs-lookup"><span data-stu-id="48e26-117">Members</span></span>

#### <span data-ttu-id="48e26-118">Handled</span><span class="sxs-lookup"><span data-stu-id="48e26-118">Handled</span></span> 

<span data-ttu-id="48e26-119">イベントがアプリによって処理されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="48e26-119">Indicate whether the event has been handled by the app.</span></span>

> <span data-ttu-id="48e26-120">パブリックブール[処理](#handled)</span><span class="sxs-lookup"><span data-stu-id="48e26-120">public bool [Handled](#handled)</span></span>

<span data-ttu-id="48e26-121">アプリがフォーカスを目的の場所に移動した場合は、Handled プロパティを TRUE に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48e26-121">If the app has moved the focus to its desired location, it should set Handled property to TRUE.</span></span> <span data-ttu-id="48e26-122">イベントハンドラーから制御が返された後、Handled プロパティが false の場合は、既定のアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="48e26-122">When Handled property is false after the event handler returns, default action will be taken.</span></span> <span data-ttu-id="48e26-123">既定のアクションでは、アプリで次のタブ位置の子ウィンドウを検索し、フォーカスをそのウィンドウに移動しようとします。</span><span class="sxs-lookup"><span data-stu-id="48e26-123">The default action is to try to find the next tab stop child window in the app and try to move focus to that window.</span></span> <span data-ttu-id="48e26-124">フォーカスを移動できるその他のウィンドウがない場合は、WebView の web コンテンツ内でフォーカスが変更されます。</span><span class="sxs-lookup"><span data-stu-id="48e26-124">If there is no other such window to move focus to, focus will be cycled within the WebView's web content.</span></span>

#### <span data-ttu-id="48e26-125">理由</span><span class="sxs-lookup"><span data-stu-id="48e26-125">Reason</span></span> 

<span data-ttu-id="48e26-126">MoveFocus 要求されたイベントを WebView が発生させる理由。</span><span class="sxs-lookup"><span data-stu-id="48e26-126">The reason for WebView to fire the MoveFocus Requested event.</span></span>

> <span data-ttu-id="48e26-127">パブリック CoreWebView2MoveFocusReason の[理由](#reason)</span><span class="sxs-lookup"><span data-stu-id="48e26-127">public CoreWebView2MoveFocusReason [Reason](#reason)</span></span>

