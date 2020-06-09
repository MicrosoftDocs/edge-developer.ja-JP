---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 54e2c06ef65f64560fbd5687148eace253352203
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698956"
---
# <span data-ttu-id="2e28c-104">WebView2 クラス (CoreWebView2NewWindowRequestedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="2e28c-104">Microsoft.Web.WebView2.Core.CoreWebView2NewWindowRequestedEventArgs class</span></span> 

<span data-ttu-id="2e28c-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="2e28c-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="2e28c-106">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="2e28c-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="2e28c-107">NewWindowRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="2e28c-107">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="2e28c-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="2e28c-108">Summary</span></span>

 <span data-ttu-id="2e28c-109">Members</span><span class="sxs-lookup"><span data-stu-id="2e28c-109">Members</span></span>                        | <span data-ttu-id="2e28c-110">説明</span><span class="sxs-lookup"><span data-stu-id="2e28c-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2e28c-111">Handled</span><span class="sxs-lookup"><span data-stu-id="2e28c-111">Handled</span></span>](#handled) | <span data-ttu-id="2e28c-112">NewWindowRequestedEvent がホストによって処理されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="2e28c-112">Whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="2e28c-113">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="2e28c-113">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="2e28c-114">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="2e28c-114">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>
[<span data-ttu-id="2e28c-115">NewWindow</span><span class="sxs-lookup"><span data-stu-id="2e28c-115">NewWindow</span></span>](#newwindow) | <span data-ttu-id="2e28c-116">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="2e28c-116">Gets the new window.</span></span>
[<span data-ttu-id="2e28c-117">URI</span><span class="sxs-lookup"><span data-stu-id="2e28c-117">Uri</span></span>](#uri) | <span data-ttu-id="2e28c-118">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="2e28c-118">The target uri of the NewWindowRequest.</span></span>
[<span data-ttu-id="2e28c-119">WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="2e28c-119">WindowFeatures</span></span>](#windowfeatures) | <span data-ttu-id="2e28c-120">ウィンドウで指定されたウィンドウ機能。 [通話] を開きます。</span><span class="sxs-lookup"><span data-stu-id="2e28c-120">Window features specified by the window.open call.</span></span>
[<span data-ttu-id="2e28c-121">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="2e28c-121">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="2e28c-122">CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="2e28c-122">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

<span data-ttu-id="2e28c-123">このイベントは、webview 内のコンテンツが新しいウィンドウを開くように要求したときに発生します (ウィンドウを開く () など)。</span><span class="sxs-lookup"><span data-stu-id="2e28c-123">The event is fired when content inside webview requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="2e28c-124">Members</span><span class="sxs-lookup"><span data-stu-id="2e28c-124">Members</span></span>

#### <span data-ttu-id="2e28c-125">Handled</span><span class="sxs-lookup"><span data-stu-id="2e28c-125">Handled</span></span> 

<span data-ttu-id="2e28c-126">NewWindowRequestedEvent がホストによって処理されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="2e28c-126">Whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="2e28c-127">パブリックブール[処理](#handled)</span><span class="sxs-lookup"><span data-stu-id="2e28c-127">public bool [Handled](#handled)</span></span>

<span data-ttu-id="2e28c-128">この値が false で、NewWindow が設定されていない場合は、WebView にポップアップウィンドウが表示され、開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="2e28c-128">If this is false and no NewWindow is set, the WebView will open a popup window and it will be returned as opened WindowProxy.</span></span> <span data-ttu-id="2e28c-129">Window に対して NewWindow が設定されていない場合は true に設定します。 [呼び出し] を開くと、開いている WindowProxy は dummy ウィンドウオブジェクトになり、ウィンドウは読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="2e28c-129">If set to true and no NewWindow is set for a window.open call, the opened WindowProxy will be for an dummy window object and no window will load.</span></span> <span data-ttu-id="2e28c-130">Default は false です。</span><span class="sxs-lookup"><span data-stu-id="2e28c-130">Default is false.</span></span>

#### <span data-ttu-id="2e28c-131">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="2e28c-131">IsUserInitiated</span></span> 

<span data-ttu-id="2e28c-132">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="2e28c-132">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>

> <span data-ttu-id="2e28c-133">public bool [Isuserinitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="2e28c-133">public bool [IsUserInitiated](#isuserinitiated)</span></span>

#### <span data-ttu-id="2e28c-134">NewWindow</span><span class="sxs-lookup"><span data-stu-id="2e28c-134">NewWindow</span></span> 

<span data-ttu-id="2e28c-135">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="2e28c-135">Gets the new window.</span></span>

> <span data-ttu-id="2e28c-136">パブリック CoreWebView2 [NewWindow](#newwindow)</span><span class="sxs-lookup"><span data-stu-id="2e28c-136">public CoreWebView2 [NewWindow](#newwindow)</span></span>

#### <span data-ttu-id="2e28c-137">URI</span><span class="sxs-lookup"><span data-stu-id="2e28c-137">Uri</span></span> 

<span data-ttu-id="2e28c-138">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="2e28c-138">The target uri of the NewWindowRequest.</span></span>

> <span data-ttu-id="2e28c-139">パブリック文字列の[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="2e28c-139">public string [Uri](#uri)</span></span>

<span data-ttu-id="2e28c-140">ターゲット webview に移動しないようにします。</span><span class="sxs-lookup"><span data-stu-id="2e28c-140">The target webview should not be navigated.</span></span> <span data-ttu-id="2e28c-141">NewWindow が設定されている場合は、トップレベルのウィンドウが開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="2e28c-141">If the NewWindow is set, its top level window will return as the opened WindowProxy.</span></span>

#### <span data-ttu-id="2e28c-142">WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="2e28c-142">WindowFeatures</span></span> 

> [!NOTE]
> <span data-ttu-id="2e28c-143">これは、SDK バージョン[0.9.538-プレリリース](../../../releasenotes.md#09538)で出荷される[実験的な API](../../../concepts/versioning.md#experimental-apis)です。</span><span class="sxs-lookup"><span data-stu-id="2e28c-143">This is an [experimental API](../../../concepts/versioning.md#experimental-apis) that shipped with our SDK version [0.9.538-prerelease](../../../releasenotes.md#09538).</span></span>

<span data-ttu-id="2e28c-144">ウィンドウで指定されたウィンドウ機能。 [通話] を開きます。</span><span class="sxs-lookup"><span data-stu-id="2e28c-144">Window features specified by the window.open call.</span></span>

> <span data-ttu-id="2e28c-145">パブリック CoreWebView2WindowFeatures [Windowfeatures](#windowfeatures)</span><span class="sxs-lookup"><span data-stu-id="2e28c-145">public CoreWebView2WindowFeatures [WindowFeatures](#windowfeatures)</span></span>

<span data-ttu-id="2e28c-146">これらの機能は、新しい webview ウィンドウの配置とサイズ変更のために考慮することができます。</span><span class="sxs-lookup"><span data-stu-id="2e28c-146">These features can be considered for positioning and sizing of new webview windows.</span></span>

#### <span data-ttu-id="2e28c-147">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="2e28c-147">GetDeferral</span></span> 

<span data-ttu-id="2e28c-148">CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="2e28c-148">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

> <span data-ttu-id="2e28c-149">パブリック CoreWebView2Deferral [Getdeferral](#getdeferral)()</span><span class="sxs-lookup"><span data-stu-id="2e28c-149">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="2e28c-150">CoreWebView2Deferral オブジェクトを使って、後でウィンドウを開く要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="2e28c-150">You can use the CoreWebView2Deferral object to complete the window open request at a later time.</span></span> <span data-ttu-id="2e28c-151">このイベントが延期されている間、opener window は、ウィンドウから切り離されたウィンドウに WindowProxy を返します。これは、延期が完了すると移動します。</span><span class="sxs-lookup"><span data-stu-id="2e28c-151">While this event is deferred the opener window will be returned a WindowProxy to an unnavigated window, which will navigate when the deferral is complete.</span></span>

