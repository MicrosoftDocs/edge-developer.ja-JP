---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2NewWindowRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2NewWindowRequestedEventArgs
ms.openlocfilehash: d1cf39fe71c4b00f10a14da8a65428eb24daa71f
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012322"
---
# <span data-ttu-id="d9c12-104">インターフェイス ICoreWebView2NewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="d9c12-104">interface ICoreWebView2NewWindowRequestedEventArgs</span></span> 

```
interface ICoreWebView2NewWindowRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="d9c12-105">NewWindowRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="d9c12-105">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="d9c12-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="d9c12-106">Summary</span></span>

 <span data-ttu-id="d9c12-107">Members</span><span class="sxs-lookup"><span data-stu-id="d9c12-107">Members</span></span>                        | <span data-ttu-id="d9c12-108">説明</span><span class="sxs-lookup"><span data-stu-id="d9c12-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d9c12-109">get_Handled</span><span class="sxs-lookup"><span data-stu-id="d9c12-109">get_Handled</span></span>](#get_handled) | <span data-ttu-id="d9c12-110">NewWindowRequestedEvent がホストによって処理されるかどうかを取得します。</span><span class="sxs-lookup"><span data-stu-id="d9c12-110">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="d9c12-111">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="d9c12-111">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="d9c12-112">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="d9c12-112">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>
[<span data-ttu-id="d9c12-113">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="d9c12-113">get_NewWindow</span></span>](#get_newwindow) | <span data-ttu-id="d9c12-114">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="d9c12-114">Gets the new window.</span></span>
[<span data-ttu-id="d9c12-115">get_Uri</span><span class="sxs-lookup"><span data-stu-id="d9c12-115">get_Uri</span></span>](#get_uri) | <span data-ttu-id="d9c12-116">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="d9c12-116">The target uri of the NewWindowRequest.</span></span>
[<span data-ttu-id="d9c12-117">get_WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="d9c12-117">get_WindowFeatures</span></span>](#get_windowfeatures) | <span data-ttu-id="d9c12-118">ウィンドウで指定されたウィンドウ機能。 [通話] を開きます。</span><span class="sxs-lookup"><span data-stu-id="d9c12-118">Window features specified by the window.open call.</span></span>
[<span data-ttu-id="d9c12-119">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="d9c12-119">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="d9c12-120">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="d9c12-120">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>
[<span data-ttu-id="d9c12-121">put_Handled</span><span class="sxs-lookup"><span data-stu-id="d9c12-121">put_Handled</span></span>](#put_handled) | <span data-ttu-id="d9c12-122">NewWindowRequestedEvent がホストによって処理されるかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="d9c12-122">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="d9c12-123">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="d9c12-123">put_NewWindow</span></span>](#put_newwindow) | <span data-ttu-id="d9c12-124">NewWindowRequest の結果として WebView を設定します。</span><span class="sxs-lookup"><span data-stu-id="d9c12-124">Sets a WebView as a result of the NewWindowRequest.</span></span>

<span data-ttu-id="d9c12-125">このイベントは、webview 内のコンテンツが新しいウィンドウを開くように要求したときに発生します (ウィンドウを開く () など)。</span><span class="sxs-lookup"><span data-stu-id="d9c12-125">The event is fired when content inside webview requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="d9c12-126">Members</span><span class="sxs-lookup"><span data-stu-id="d9c12-126">Members</span></span>

#### <span data-ttu-id="d9c12-127">get_Handled</span><span class="sxs-lookup"><span data-stu-id="d9c12-127">get_Handled</span></span> 

<span data-ttu-id="d9c12-128">NewWindowRequestedEvent がホストによって処理されるかどうかを取得します。</span><span class="sxs-lookup"><span data-stu-id="d9c12-128">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="d9c12-129">パブリック HRESULT [get_Handled](#get_handled)(ブール \* Handled)</span><span class="sxs-lookup"><span data-stu-id="d9c12-129">public HRESULT [get_Handled](#get_handled)(BOOL \* handled)</span></span>

#### <span data-ttu-id="d9c12-130">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="d9c12-130">get_IsUserInitiated</span></span> 

<span data-ttu-id="d9c12-131">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="d9c12-131">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>

> <span data-ttu-id="d9c12-132">パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール \* isUserInitiated)</span><span class="sxs-lookup"><span data-stu-id="d9c12-132">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

<span data-ttu-id="d9c12-133">エッジポップアップブロックは、WebView に対して無効になっているため、アプリはこのフラグを使って、ユーザーによって開始されていないポップアップをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="d9c12-133">The Edge popup blocker is disabled for WebView so the app can use this flag to block non-user initiated popups.</span></span>

#### <span data-ttu-id="d9c12-134">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="d9c12-134">get_NewWindow</span></span> 

<span data-ttu-id="d9c12-135">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="d9c12-135">Gets the new window.</span></span>

> <span data-ttu-id="d9c12-136">パブリック HRESULT [get_NewWindow](#get_newwindow)([ICoreWebView2](icorewebview2.md) \* \* NewWindow)</span><span class="sxs-lookup"><span data-stu-id="d9c12-136">public HRESULT [get_NewWindow](#get_newwindow)([ICoreWebView2](icorewebview2.md) \*\* newWindow)</span></span>

#### <span data-ttu-id="d9c12-137">get_Uri</span><span class="sxs-lookup"><span data-stu-id="d9c12-137">get_Uri</span></span> 

<span data-ttu-id="d9c12-138">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="d9c12-138">The target uri of the NewWindowRequest.</span></span>

> <span data-ttu-id="d9c12-139">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="d9c12-139">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="d9c12-140">get_WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="d9c12-140">get_WindowFeatures</span></span> 

<span data-ttu-id="d9c12-141">ウィンドウで指定されたウィンドウ機能。 [通話] を開きます。</span><span class="sxs-lookup"><span data-stu-id="d9c12-141">Window features specified by the window.open call.</span></span>

> <span data-ttu-id="d9c12-142">パブリック HRESULT [get_WindowFeatures](#get_windowfeatures)([ICoreWebView2WindowFeatures](icorewebview2windowfeatures.md) \* \* windowfeatures)</span><span class="sxs-lookup"><span data-stu-id="d9c12-142">public HRESULT [get_WindowFeatures](#get_windowfeatures)([ICoreWebView2WindowFeatures](icorewebview2windowfeatures.md) \*\* windowFeatures)</span></span>

<span data-ttu-id="d9c12-143">これらの機能は、新しい webview ウィンドウの配置とサイズ変更のために考慮することができます。</span><span class="sxs-lookup"><span data-stu-id="d9c12-143">These features can be considered for positioning and sizing of new webview windows.</span></span>

#### <span data-ttu-id="d9c12-144">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="d9c12-144">GetDeferral</span></span> 

<span data-ttu-id="d9c12-145">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="d9c12-145">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="d9c12-146">パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="d9c12-146">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="d9c12-147">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを使って、後でウィンドウを開く要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="d9c12-147">You can use the [ICoreWebView2Deferral](icorewebview2deferral.md) object to complete the window open request at a later time.</span></span> <span data-ttu-id="d9c12-148">このイベントが延期されている間、opener window は、ウィンドウから切り離されたウィンドウに WindowProxy を返します。これは、延期が完了すると移動します。</span><span class="sxs-lookup"><span data-stu-id="d9c12-148">While this event is deferred the opener window will be returned a WindowProxy to an unnavigated window, which will navigate when the deferral is complete.</span></span>

#### <span data-ttu-id="d9c12-149">put_Handled</span><span class="sxs-lookup"><span data-stu-id="d9c12-149">put_Handled</span></span> 

<span data-ttu-id="d9c12-150">NewWindowRequestedEvent がホストによって処理されるかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="d9c12-150">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="d9c12-151">パブリック HRESULT [put_Handled](#put_handled)(ブール値で処理される)</span><span class="sxs-lookup"><span data-stu-id="d9c12-151">public HRESULT [put_Handled](#put_handled)(BOOL handled)</span></span>

<span data-ttu-id="d9c12-152">この値が false で、NewWindow が設定されていない場合は、WebView にポップアップウィンドウが表示され、開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="d9c12-152">If this is false and no NewWindow is set, the WebView will open a popup window and it will be returned as opened WindowProxy.</span></span> <span data-ttu-id="d9c12-153">Window に対して NewWindow が設定されていない場合は true に設定します。 [呼び出し] を開くと、開いている WindowProxy は dummy ウィンドウオブジェクトになり、ウィンドウは読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="d9c12-153">If set to true and no NewWindow is set for a window.open call, the opened WindowProxy will be for an dummy window object and no window will load.</span></span> <span data-ttu-id="d9c12-154">Default は false です。</span><span class="sxs-lookup"><span data-stu-id="d9c12-154">Default is false.</span></span>

#### <span data-ttu-id="d9c12-155">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="d9c12-155">put_NewWindow</span></span> 

<span data-ttu-id="d9c12-156">NewWindowRequest の結果として WebView を設定します。</span><span class="sxs-lookup"><span data-stu-id="d9c12-156">Sets a WebView as a result of the NewWindowRequest.</span></span>

> <span data-ttu-id="d9c12-157">パブリック HRESULT [put_NewWindow](#put_newwindow)([ICoreWebView2](icorewebview2.md) \* NewWindow)</span><span class="sxs-lookup"><span data-stu-id="d9c12-157">public HRESULT [put_NewWindow](#put_newwindow)([ICoreWebView2](icorewebview2.md) \* newWindow)</span></span>

<span data-ttu-id="d9c12-158">ターゲット WebView に移動しないようにします。</span><span class="sxs-lookup"><span data-stu-id="d9c12-158">The target WebView should not be navigated.</span></span> <span data-ttu-id="d9c12-159">NewWindow が設定されている場合は、トップレベルのウィンドウが開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="d9c12-159">If the NewWindow is set, its top level window will return as the opened WindowProxy.</span></span>

