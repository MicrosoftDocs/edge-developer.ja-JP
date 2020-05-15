---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 3c88108f0e1df89c62c8713ff37f35d0c759cf6c
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654540"
---
# <span data-ttu-id="9800f-104">WebView2 クラス (CoreWebView2MoveFocusRequestedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="9800f-104">Microsoft.Web.WebView2.Core.CoreWebView2MoveFocusRequestedEventArgs class</span></span> 

<span data-ttu-id="9800f-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="9800f-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="9800f-106">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="9800f-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="9800f-107">MoveFocusRequested されたイベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="9800f-107">Event args for the MoveFocusRequested event.</span></span>

## <span data-ttu-id="9800f-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="9800f-108">Summary</span></span>

 <span data-ttu-id="9800f-109">Members</span><span class="sxs-lookup"><span data-stu-id="9800f-109">Members</span></span>                        | <span data-ttu-id="9800f-110">説明</span><span class="sxs-lookup"><span data-stu-id="9800f-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9800f-111">Handled</span><span class="sxs-lookup"><span data-stu-id="9800f-111">Handled</span></span>](#handled) | <span data-ttu-id="9800f-112">イベントがアプリによって処理されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="9800f-112">Indicate whether the event has been handled by the app.</span></span>
[<span data-ttu-id="9800f-113">理由</span><span class="sxs-lookup"><span data-stu-id="9800f-113">Reason</span></span>](#reason) | <span data-ttu-id="9800f-114">MoveFocus 要求されたイベントを WebView が発生させる理由。</span><span class="sxs-lookup"><span data-stu-id="9800f-114">The reason for WebView to fire the MoveFocus Requested event.</span></span>

## <span data-ttu-id="9800f-115">Members</span><span class="sxs-lookup"><span data-stu-id="9800f-115">Members</span></span>

#### <span data-ttu-id="9800f-116">Handled</span><span class="sxs-lookup"><span data-stu-id="9800f-116">Handled</span></span> 

<span data-ttu-id="9800f-117">イベントがアプリによって処理されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="9800f-117">Indicate whether the event has been handled by the app.</span></span>

> <span data-ttu-id="9800f-118">パブリックブール[処理](#handled)</span><span class="sxs-lookup"><span data-stu-id="9800f-118">public bool [Handled](#handled)</span></span>

<span data-ttu-id="9800f-119">アプリがフォーカスを目的の場所に移動した場合は、Handled プロパティを TRUE に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9800f-119">If the app has moved the focus to its desired location, it should set Handled property to TRUE.</span></span> <span data-ttu-id="9800f-120">イベントハンドラーから制御が返された後、Handled プロパティが false の場合は、既定のアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="9800f-120">When Handled property is false after the event handler returns, default action will be taken.</span></span> <span data-ttu-id="9800f-121">既定のアクションでは、アプリで次のタブ位置の子ウィンドウを検索し、フォーカスをそのウィンドウに移動しようとします。</span><span class="sxs-lookup"><span data-stu-id="9800f-121">The default action is to try to find the next tab stop child window in the app and try to move focus to that window.</span></span> <span data-ttu-id="9800f-122">フォーカスを移動できるその他のウィンドウがない場合は、WebView の web コンテンツ内でフォーカスが変更されます。</span><span class="sxs-lookup"><span data-stu-id="9800f-122">If there is no other such window to move focus to, focus will be cycled within the WebView's web content.</span></span>

#### <span data-ttu-id="9800f-123">理由</span><span class="sxs-lookup"><span data-stu-id="9800f-123">Reason</span></span> 

<span data-ttu-id="9800f-124">MoveFocus 要求されたイベントを WebView が発生させる理由。</span><span class="sxs-lookup"><span data-stu-id="9800f-124">The reason for WebView to fire the MoveFocus Requested event.</span></span>

> <span data-ttu-id="9800f-125">パブリック CoreWebView2MoveFocusReason の[理由](#reason)</span><span class="sxs-lookup"><span data-stu-id="9800f-125">public CoreWebView2MoveFocusReason [Reason](#reason)</span></span>

