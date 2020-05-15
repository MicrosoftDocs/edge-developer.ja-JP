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
ms.openlocfilehash: cca15ccc5292f5eaf6f317ffb657f46fcd84b4a9
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654538"
---
# <span data-ttu-id="76f2a-104">WebView2 クラス (CoreWebView2NewWindowRequestedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="76f2a-104">Microsoft.Web.WebView2.Core.CoreWebView2NewWindowRequestedEventArgs class</span></span> 

<span data-ttu-id="76f2a-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="76f2a-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="76f2a-106">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="76f2a-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="76f2a-107">NewWindowRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="76f2a-107">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="76f2a-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="76f2a-108">Summary</span></span>

 <span data-ttu-id="76f2a-109">Members</span><span class="sxs-lookup"><span data-stu-id="76f2a-109">Members</span></span>                        | <span data-ttu-id="76f2a-110">説明</span><span class="sxs-lookup"><span data-stu-id="76f2a-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="76f2a-111">Handled</span><span class="sxs-lookup"><span data-stu-id="76f2a-111">Handled</span></span>](#handled) | <span data-ttu-id="76f2a-112">NewWindowRequestedEvent がホストによって処理されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="76f2a-112">Whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="76f2a-113">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="76f2a-113">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="76f2a-114">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="76f2a-114">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>
[<span data-ttu-id="76f2a-115">NewWindow</span><span class="sxs-lookup"><span data-stu-id="76f2a-115">NewWindow</span></span>](#newwindow) | <span data-ttu-id="76f2a-116">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="76f2a-116">Gets the new window.</span></span>
[<span data-ttu-id="76f2a-117">URI</span><span class="sxs-lookup"><span data-stu-id="76f2a-117">Uri</span></span>](#uri) | <span data-ttu-id="76f2a-118">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="76f2a-118">The target uri of the NewWindowRequest.</span></span>
[<span data-ttu-id="76f2a-119">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="76f2a-119">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="76f2a-120">CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="76f2a-120">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

<span data-ttu-id="76f2a-121">このイベントは、webview 内のコンテンツが新しいウィンドウを開くように要求したときに発生します (ウィンドウを開く () など)。</span><span class="sxs-lookup"><span data-stu-id="76f2a-121">The event is fired when content inside webview requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="76f2a-122">Members</span><span class="sxs-lookup"><span data-stu-id="76f2a-122">Members</span></span>

#### <span data-ttu-id="76f2a-123">Handled</span><span class="sxs-lookup"><span data-stu-id="76f2a-123">Handled</span></span> 

<span data-ttu-id="76f2a-124">NewWindowRequestedEvent がホストによって処理されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="76f2a-124">Whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="76f2a-125">パブリックブール[処理](#handled)</span><span class="sxs-lookup"><span data-stu-id="76f2a-125">public bool [Handled](#handled)</span></span>

<span data-ttu-id="76f2a-126">この値が false で、NewWindow が設定されていない場合は、WebView にポップアップウィンドウが表示され、開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="76f2a-126">If this is false and no NewWindow is set, the WebView will open a popup window and it will be returned as opened WindowProxy.</span></span> <span data-ttu-id="76f2a-127">Window に対して NewWindow が設定されていない場合は true に設定します。 [呼び出し] を開くと、開いている WindowProxy は dummy ウィンドウオブジェクトになり、ウィンドウは読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="76f2a-127">If set to true and no NewWindow is set for a window.open call, the opened WindowProxy will be for an dummy window object and no window will load.</span></span> <span data-ttu-id="76f2a-128">Default は false です。</span><span class="sxs-lookup"><span data-stu-id="76f2a-128">Default is false.</span></span>

#### <span data-ttu-id="76f2a-129">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="76f2a-129">IsUserInitiated</span></span> 

<span data-ttu-id="76f2a-130">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="76f2a-130">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>

> <span data-ttu-id="76f2a-131">public bool [Isuserinitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="76f2a-131">public bool [IsUserInitiated](#isuserinitiated)</span></span>

#### <span data-ttu-id="76f2a-132">NewWindow</span><span class="sxs-lookup"><span data-stu-id="76f2a-132">NewWindow</span></span> 

<span data-ttu-id="76f2a-133">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="76f2a-133">Gets the new window.</span></span>

> <span data-ttu-id="76f2a-134">パブリック CoreWebView2 [NewWindow](#newwindow)</span><span class="sxs-lookup"><span data-stu-id="76f2a-134">public CoreWebView2 [NewWindow](#newwindow)</span></span>

#### <span data-ttu-id="76f2a-135">URI</span><span class="sxs-lookup"><span data-stu-id="76f2a-135">Uri</span></span> 

<span data-ttu-id="76f2a-136">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="76f2a-136">The target uri of the NewWindowRequest.</span></span>

> <span data-ttu-id="76f2a-137">パブリック文字列の[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="76f2a-137">public string [Uri](#uri)</span></span>

<span data-ttu-id="76f2a-138">ターゲット webview に移動しないようにします。</span><span class="sxs-lookup"><span data-stu-id="76f2a-138">The target webview should not be navigated.</span></span> <span data-ttu-id="76f2a-139">NewWindow が設定されている場合は、トップレベルのウィンドウが開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="76f2a-139">If the NewWindow is set, its top level window will return as the opened WindowProxy.</span></span>

#### <span data-ttu-id="76f2a-140">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="76f2a-140">GetDeferral</span></span> 

<span data-ttu-id="76f2a-141">CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="76f2a-141">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

> <span data-ttu-id="76f2a-142">パブリック CoreWebView2Deferral [Getdeferral](#getdeferral)()</span><span class="sxs-lookup"><span data-stu-id="76f2a-142">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="76f2a-143">CoreWebView2Deferral オブジェクトを使って、後でウィンドウを開く要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="76f2a-143">You can use the CoreWebView2Deferral object to complete the window open request at a later time.</span></span> <span data-ttu-id="76f2a-144">このイベントが延期されている間、opener window は、ウィンドウから切り離されたウィンドウに WindowProxy を返します。これは、延期が完了すると移動します。</span><span class="sxs-lookup"><span data-stu-id="76f2a-144">While this event is deferred the opener window will be returned a WindowProxy to an unnavigated window, which will navigate when the deferral is complete.</span></span>

