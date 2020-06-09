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
ms.openlocfilehash: c3f9b8bb9451d8364424db01ea19aecedb362d59
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697169"
---
# <span data-ttu-id="6f180-104">WebView2 クラス (CoreWebView2NewWindowRequestedEventArgs クラス)</span><span class="sxs-lookup"><span data-stu-id="6f180-104">Microsoft.Web.WebView2.Core.CoreWebView2NewWindowRequestedEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="6f180-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6f180-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="6f180-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f180-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="6f180-107">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="6f180-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="6f180-108">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="6f180-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="6f180-109">NewWindowRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="6f180-109">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="6f180-110">まとめ</span><span class="sxs-lookup"><span data-stu-id="6f180-110">Summary</span></span>

 <span data-ttu-id="6f180-111">Members</span><span class="sxs-lookup"><span data-stu-id="6f180-111">Members</span></span>                        | <span data-ttu-id="6f180-112">説明</span><span class="sxs-lookup"><span data-stu-id="6f180-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6f180-113">Handled</span><span class="sxs-lookup"><span data-stu-id="6f180-113">Handled</span></span>](#handled) | <span data-ttu-id="6f180-114">NewWindowRequestedEvent がホストによって処理されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="6f180-114">Whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="6f180-115">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="6f180-115">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="6f180-116">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="6f180-116">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>
[<span data-ttu-id="6f180-117">NewWindow</span><span class="sxs-lookup"><span data-stu-id="6f180-117">NewWindow</span></span>](#newwindow) | <span data-ttu-id="6f180-118">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="6f180-118">Gets the new window.</span></span>
[<span data-ttu-id="6f180-119">URI</span><span class="sxs-lookup"><span data-stu-id="6f180-119">Uri</span></span>](#uri) | <span data-ttu-id="6f180-120">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="6f180-120">The target uri of the NewWindowRequest.</span></span>
[<span data-ttu-id="6f180-121">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="6f180-121">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="6f180-122">CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="6f180-122">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

<span data-ttu-id="6f180-123">このイベントは、webview 内のコンテンツが新しいウィンドウを開くように要求したときに発生します (ウィンドウを開く () など)。</span><span class="sxs-lookup"><span data-stu-id="6f180-123">The event is fired when content inside webview requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="6f180-124">Members</span><span class="sxs-lookup"><span data-stu-id="6f180-124">Members</span></span>

#### <span data-ttu-id="6f180-125">Handled</span><span class="sxs-lookup"><span data-stu-id="6f180-125">Handled</span></span> 

<span data-ttu-id="6f180-126">NewWindowRequestedEvent がホストによって処理されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="6f180-126">Whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="6f180-127">パブリックブール[処理](#handled)</span><span class="sxs-lookup"><span data-stu-id="6f180-127">public bool [Handled](#handled)</span></span>

<span data-ttu-id="6f180-128">この値が false で、NewWindow が設定されていない場合は、WebView にポップアップウィンドウが表示され、開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="6f180-128">If this is false and no NewWindow is set, the WebView will open a popup window and it will be returned as opened WindowProxy.</span></span> <span data-ttu-id="6f180-129">Window に対して NewWindow が設定されていない場合は true に設定します。 [呼び出し] を開くと、開いている WindowProxy は dummy ウィンドウオブジェクトになり、ウィンドウは読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="6f180-129">If set to true and no NewWindow is set for a window.open call, the opened WindowProxy will be for an dummy window object and no window will load.</span></span> <span data-ttu-id="6f180-130">Default は false です。</span><span class="sxs-lookup"><span data-stu-id="6f180-130">Default is false.</span></span>

#### <span data-ttu-id="6f180-131">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="6f180-131">IsUserInitiated</span></span> 

<span data-ttu-id="6f180-132">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="6f180-132">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>

> <span data-ttu-id="6f180-133">public bool [Isuserinitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="6f180-133">public bool [IsUserInitiated](#isuserinitiated)</span></span>

#### <span data-ttu-id="6f180-134">NewWindow</span><span class="sxs-lookup"><span data-stu-id="6f180-134">NewWindow</span></span> 

<span data-ttu-id="6f180-135">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="6f180-135">Gets the new window.</span></span>

> <span data-ttu-id="6f180-136">パブリック CoreWebView2 [NewWindow](#newwindow)</span><span class="sxs-lookup"><span data-stu-id="6f180-136">public CoreWebView2 [NewWindow](#newwindow)</span></span>

#### <span data-ttu-id="6f180-137">URI</span><span class="sxs-lookup"><span data-stu-id="6f180-137">Uri</span></span> 

<span data-ttu-id="6f180-138">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="6f180-138">The target uri of the NewWindowRequest.</span></span>

> <span data-ttu-id="6f180-139">パブリック文字列の[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="6f180-139">public string [Uri](#uri)</span></span>

<span data-ttu-id="6f180-140">ターゲット webview に移動しないようにします。</span><span class="sxs-lookup"><span data-stu-id="6f180-140">The target webview should not be navigated.</span></span> <span data-ttu-id="6f180-141">NewWindow が設定されている場合は、トップレベルのウィンドウが開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="6f180-141">If the NewWindow is set, its top level window will return as the opened WindowProxy.</span></span>

#### <span data-ttu-id="6f180-142">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="6f180-142">GetDeferral</span></span> 

<span data-ttu-id="6f180-143">CoreWebView2Deferral オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="6f180-143">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

> <span data-ttu-id="6f180-144">パブリック CoreWebView2Deferral [Getdeferral](#getdeferral)()</span><span class="sxs-lookup"><span data-stu-id="6f180-144">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="6f180-145">CoreWebView2Deferral オブジェクトを使って、後でウィンドウを開く要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="6f180-145">You can use the CoreWebView2Deferral object to complete the window open request at a later time.</span></span> <span data-ttu-id="6f180-146">このイベントが延期されている間、opener window は、ウィンドウから切り離されたウィンドウに WindowProxy を返します。これは、延期が完了すると移動します。</span><span class="sxs-lookup"><span data-stu-id="6f180-146">While this event is deferred the opener window will be returned a WindowProxy to an unnavigated window, which will navigate when the deferral is complete.</span></span>

