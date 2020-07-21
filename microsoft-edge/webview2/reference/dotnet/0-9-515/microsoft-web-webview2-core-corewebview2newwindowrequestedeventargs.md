---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (CoreWebView2NewWindowRequestedEventArgs の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 98cfec908a0e1ad73046f7740f6e9a2efad8a853
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886288"
---
# <span data-ttu-id="ab556-104">0.9.515 クラスの WebView2 クラス (CoreWebView2NewWindowRequestedEventArgs)</span><span class="sxs-lookup"><span data-stu-id="ab556-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2NewWindowRequestedEventArgs class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="ab556-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="ab556-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="ab556-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="ab556-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="ab556-107">NewWindowRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="ab556-107">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="ab556-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="ab556-108">Summary</span></span>

 <span data-ttu-id="ab556-109">Members</span><span class="sxs-lookup"><span data-stu-id="ab556-109">Members</span></span>                        | <span data-ttu-id="ab556-110">説明</span><span class="sxs-lookup"><span data-stu-id="ab556-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ab556-111">Handled</span><span class="sxs-lookup"><span data-stu-id="ab556-111">Handled</span></span>](#handled) | <span data-ttu-id="ab556-112">NewWindowRequestedEvent がホストによって処理されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="ab556-112">Whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="ab556-113">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="ab556-113">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="ab556-114">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="ab556-114">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>
[<span data-ttu-id="ab556-115">NewWindow</span><span class="sxs-lookup"><span data-stu-id="ab556-115">NewWindow</span></span>](#newwindow) | <span data-ttu-id="ab556-116">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="ab556-116">Gets the new window.</span></span>
[<span data-ttu-id="ab556-117">URI</span><span class="sxs-lookup"><span data-stu-id="ab556-117">Uri</span></span>](#uri) | <span data-ttu-id="ab556-118">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="ab556-118">The target uri of the NewWindowRequest.</span></span>
[<span data-ttu-id="ab556-119">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="ab556-119">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="ab556-120">CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="ab556-120">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

<span data-ttu-id="ab556-121">このイベントは、webview 内のコンテンツが新しいウィンドウを開くように要求したときに発生します (ウィンドウを開く () など)。</span><span class="sxs-lookup"><span data-stu-id="ab556-121">The event is fired when content inside webview requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="ab556-122">Members</span><span class="sxs-lookup"><span data-stu-id="ab556-122">Members</span></span>

#### <span data-ttu-id="ab556-123">Handled</span><span class="sxs-lookup"><span data-stu-id="ab556-123">Handled</span></span> 

<span data-ttu-id="ab556-124">NewWindowRequestedEvent がホストによって処理されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="ab556-124">Whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="ab556-125">パブリックブール[処理](#handled)</span><span class="sxs-lookup"><span data-stu-id="ab556-125">public bool [Handled](#handled)</span></span>

<span data-ttu-id="ab556-126">この値が false で、NewWindow が設定されていない場合は、WebView にポップアップウィンドウが表示され、開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="ab556-126">If this is false and no NewWindow is set, the WebView will open a popup window and it will be returned as opened WindowProxy.</span></span> <span data-ttu-id="ab556-127">Window に対して NewWindow が設定されていない場合は true に設定します。 [呼び出し] を開くと、開いている WindowProxy は dummy ウィンドウオブジェクトになり、ウィンドウは読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="ab556-127">If set to true and no NewWindow is set for a window.open call, the opened WindowProxy will be for an dummy window object and no window will load.</span></span> <span data-ttu-id="ab556-128">Default は false です。</span><span class="sxs-lookup"><span data-stu-id="ab556-128">Default is false.</span></span>

#### <span data-ttu-id="ab556-129">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="ab556-129">IsUserInitiated</span></span> 

<span data-ttu-id="ab556-130">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="ab556-130">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>

> <span data-ttu-id="ab556-131">public bool [Isuserinitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="ab556-131">public bool [IsUserInitiated](#isuserinitiated)</span></span>

#### <span data-ttu-id="ab556-132">NewWindow</span><span class="sxs-lookup"><span data-stu-id="ab556-132">NewWindow</span></span> 

<span data-ttu-id="ab556-133">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="ab556-133">Gets the new window.</span></span>

> <span data-ttu-id="ab556-134">パブリック CoreWebView2 [NewWindow](#newwindow)</span><span class="sxs-lookup"><span data-stu-id="ab556-134">public CoreWebView2 [NewWindow](#newwindow)</span></span>

#### <span data-ttu-id="ab556-135">URI</span><span class="sxs-lookup"><span data-stu-id="ab556-135">Uri</span></span> 

<span data-ttu-id="ab556-136">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="ab556-136">The target uri of the NewWindowRequest.</span></span>

> <span data-ttu-id="ab556-137">パブリック文字列の[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="ab556-137">public string [Uri](#uri)</span></span>

<span data-ttu-id="ab556-138">ターゲット webview に移動しないようにします。</span><span class="sxs-lookup"><span data-stu-id="ab556-138">The target webview should not be navigated.</span></span> <span data-ttu-id="ab556-139">NewWindow が設定されている場合は、トップレベルのウィンドウが開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="ab556-139">If the NewWindow is set, its top level window will return as the opened WindowProxy.</span></span>

#### <span data-ttu-id="ab556-140">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="ab556-140">GetDeferral</span></span> 

<span data-ttu-id="ab556-141">CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="ab556-141">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

> <span data-ttu-id="ab556-142">パブリック CoreWebView2Deferral [Getdeferral](#getdeferral)()</span><span class="sxs-lookup"><span data-stu-id="ab556-142">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="ab556-143">CoreWebView2Deferral オブジェクトを使って、後でウィンドウを開く要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="ab556-143">You can use the CoreWebView2Deferral object to complete the window open request at a later time.</span></span> <span data-ttu-id="ab556-144">このイベントが延期されている間、opener window は、ウィンドウから切り離されたウィンドウに WindowProxy を返します。これは、延期が完了すると移動します。</span><span class="sxs-lookup"><span data-stu-id="ab556-144">While this event is deferred the opener window will be returned a WindowProxy to an unnavigated window, which will navigate when the deferral is complete.</span></span>

