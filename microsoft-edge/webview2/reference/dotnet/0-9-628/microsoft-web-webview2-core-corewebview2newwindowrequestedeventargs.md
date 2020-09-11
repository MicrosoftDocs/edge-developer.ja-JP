---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2NewWindowRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2NewWindowRequestedEventArgs。
ms.openlocfilehash: 5e5d16c025dccf788b355280eaa3ac3e910f240d
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012254"
---
# <span data-ttu-id="4b645-104">WebView2 クラス (CoreWebView2NewWindowRequestedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="4b645-104">Microsoft.Web.WebView2.Core.CoreWebView2NewWindowRequestedEventArgs class</span></span> 

<span data-ttu-id="4b645-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="4b645-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="4b645-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="4b645-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="4b645-107">NewWindowRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="4b645-107">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="4b645-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="4b645-108">Summary</span></span>

 <span data-ttu-id="4b645-109">Members</span><span class="sxs-lookup"><span data-stu-id="4b645-109">Members</span></span>                        | <span data-ttu-id="4b645-110">説明</span><span class="sxs-lookup"><span data-stu-id="4b645-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4b645-111">Handled</span><span class="sxs-lookup"><span data-stu-id="4b645-111">Handled</span></span>](#handled) | <span data-ttu-id="4b645-112">NewWindowRequestedEvent がホストによって処理されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="4b645-112">Whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="4b645-113">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="4b645-113">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="4b645-114">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="4b645-114">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>
[<span data-ttu-id="4b645-115">NewWindow</span><span class="sxs-lookup"><span data-stu-id="4b645-115">NewWindow</span></span>](#newwindow) | <span data-ttu-id="4b645-116">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="4b645-116">Gets the new window.</span></span>
[<span data-ttu-id="4b645-117">URI</span><span class="sxs-lookup"><span data-stu-id="4b645-117">Uri</span></span>](#uri) | <span data-ttu-id="4b645-118">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="4b645-118">The target uri of the NewWindowRequest.</span></span>
[<span data-ttu-id="4b645-119">WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="4b645-119">WindowFeatures</span></span>](#windowfeatures) | <span data-ttu-id="4b645-120">ウィンドウで指定されたウィンドウ機能。 [通話] を開きます。</span><span class="sxs-lookup"><span data-stu-id="4b645-120">Window features specified by the window.open call.</span></span>
[<span data-ttu-id="4b645-121">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="4b645-121">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="4b645-122">CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="4b645-122">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

<span data-ttu-id="4b645-123">このイベントは、WebView 内のコンテンツが新しいウィンドウを開くように要求したときに発生します (ウィンドウを開く () など)。</span><span class="sxs-lookup"><span data-stu-id="4b645-123">The event is fired when content inside WebView requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="4b645-124">Members</span><span class="sxs-lookup"><span data-stu-id="4b645-124">Members</span></span>

#### <span data-ttu-id="4b645-125">Handled</span><span class="sxs-lookup"><span data-stu-id="4b645-125">Handled</span></span> 

<span data-ttu-id="4b645-126">NewWindowRequestedEvent がホストによって処理されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="4b645-126">Whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="4b645-127">パブリックブール [処理](#handled)</span><span class="sxs-lookup"><span data-stu-id="4b645-127">public bool [Handled](#handled)</span></span>

<span data-ttu-id="4b645-128">この値が false で、NewWindow が設定されていない場合は、WebView にポップアップウィンドウが表示され、開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="4b645-128">If this is false and no NewWindow is set, the WebView will open a popup window and it will be returned as opened WindowProxy.</span></span> <span data-ttu-id="4b645-129">Window に対して NewWindow が設定されていない場合は true に設定します。 [呼び出し] を開くと、開いている WindowProxy は dummy ウィンドウオブジェクトになり、ウィンドウは読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="4b645-129">If set to true and no NewWindow is set for a window.open call, the opened WindowProxy will be for an dummy window object and no window will load.</span></span> <span data-ttu-id="4b645-130">Default は false です。</span><span class="sxs-lookup"><span data-stu-id="4b645-130">Default is false.</span></span>

#### <span data-ttu-id="4b645-131">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="4b645-131">IsUserInitiated</span></span> 

<span data-ttu-id="4b645-132">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="4b645-132">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>

> <span data-ttu-id="4b645-133">public bool [Isuserinitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="4b645-133">public bool [IsUserInitiated](#isuserinitiated)</span></span>

#### <span data-ttu-id="4b645-134">NewWindow</span><span class="sxs-lookup"><span data-stu-id="4b645-134">NewWindow</span></span> 

<span data-ttu-id="4b645-135">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="4b645-135">Gets the new window.</span></span>

> <span data-ttu-id="4b645-136">パブリック CoreWebView2 [NewWindow](#newwindow)</span><span class="sxs-lookup"><span data-stu-id="4b645-136">public CoreWebView2 [NewWindow](#newwindow)</span></span>

#### <span data-ttu-id="4b645-137">URI</span><span class="sxs-lookup"><span data-stu-id="4b645-137">Uri</span></span> 

<span data-ttu-id="4b645-138">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="4b645-138">The target uri of the NewWindowRequest.</span></span>

> <span data-ttu-id="4b645-139">パブリック文字列の [Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="4b645-139">public string [Uri](#uri)</span></span>

<span data-ttu-id="4b645-140">ターゲット WebView に移動しないようにします。</span><span class="sxs-lookup"><span data-stu-id="4b645-140">The target WebView should not be navigated.</span></span> <span data-ttu-id="4b645-141">NewWindow が設定されている場合は、トップレベルのウィンドウが開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="4b645-141">If the NewWindow is set, its top level window will return as the opened WindowProxy.</span></span>

#### <span data-ttu-id="4b645-142">WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="4b645-142">WindowFeatures</span></span> 

<span data-ttu-id="4b645-143">ウィンドウで指定されたウィンドウ機能。 [通話] を開きます。</span><span class="sxs-lookup"><span data-stu-id="4b645-143">Window features specified by the window.open call.</span></span>

> <span data-ttu-id="4b645-144">パブリック CoreWebView2WindowFeatures [Windowfeatures](#windowfeatures)</span><span class="sxs-lookup"><span data-stu-id="4b645-144">public CoreWebView2WindowFeatures [WindowFeatures](#windowfeatures)</span></span>

<span data-ttu-id="4b645-145">これらの機能は、新しい WebView ウィンドウの配置とサイズ変更のために考慮することができます。</span><span class="sxs-lookup"><span data-stu-id="4b645-145">These features can be considered for positioning and sizing of new WebView windows.</span></span>

#### <span data-ttu-id="4b645-146">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="4b645-146">GetDeferral</span></span> 

<span data-ttu-id="4b645-147">CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="4b645-147">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

> <span data-ttu-id="4b645-148">パブリック CoreWebView2Deferral [Getdeferral](#getdeferral)()</span><span class="sxs-lookup"><span data-stu-id="4b645-148">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="4b645-149">CoreWebView2Deferral オブジェクトを使って、後でウィンドウを開く要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="4b645-149">You can use the CoreWebView2Deferral object to complete the window open request at a later time.</span></span> <span data-ttu-id="4b645-150">このイベントが延期されている間、opener window は、ウィンドウから切り離されたウィンドウに WindowProxy を返します。これは、延期が完了すると移動します。</span><span class="sxs-lookup"><span data-stu-id="4b645-150">While this event is deferred the opener window will be returned a WindowProxy to an unnavigated window, which will navigate when the deferral is complete.</span></span>

