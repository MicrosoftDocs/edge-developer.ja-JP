---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: cc64e805b0d929d71340d5a012e7848860c35f5c
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654419"
---
# <span data-ttu-id="4869a-104">インターフェイス ICoreWebView2NewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="4869a-104">interface ICoreWebView2NewWindowRequestedEventArgs</span></span> 

```
interface ICoreWebView2NewWindowRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="4869a-105">NewWindowRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="4869a-105">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="4869a-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="4869a-106">Summary</span></span>

 <span data-ttu-id="4869a-107">Members</span><span class="sxs-lookup"><span data-stu-id="4869a-107">Members</span></span>                        | <span data-ttu-id="4869a-108">説明</span><span class="sxs-lookup"><span data-stu-id="4869a-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4869a-109">get_Handled</span><span class="sxs-lookup"><span data-stu-id="4869a-109">get_Handled</span></span>](#get_handled) | <span data-ttu-id="4869a-110">NewWindowRequestedEvent がホストによって処理されるかどうかを取得します。</span><span class="sxs-lookup"><span data-stu-id="4869a-110">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="4869a-111">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="4869a-111">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="4869a-112">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="4869a-112">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>
[<span data-ttu-id="4869a-113">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="4869a-113">get_NewWindow</span></span>](#get_newwindow) | <span data-ttu-id="4869a-114">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="4869a-114">Gets the new window.</span></span>
[<span data-ttu-id="4869a-115">get_Uri</span><span class="sxs-lookup"><span data-stu-id="4869a-115">get_Uri</span></span>](#get_uri) | <span data-ttu-id="4869a-116">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="4869a-116">The target uri of the NewWindowRequest.</span></span>
[<span data-ttu-id="4869a-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="4869a-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="4869a-118">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="4869a-118">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>
[<span data-ttu-id="4869a-119">put_Handled</span><span class="sxs-lookup"><span data-stu-id="4869a-119">put_Handled</span></span>](#put_handled) | <span data-ttu-id="4869a-120">NewWindowRequestedEvent がホストによって処理されるかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="4869a-120">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="4869a-121">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="4869a-121">put_NewWindow</span></span>](#put_newwindow) | <span data-ttu-id="4869a-122">NewWindowRequest の結果として WebView を設定します。</span><span class="sxs-lookup"><span data-stu-id="4869a-122">Sets a WebView as a result of the NewWindowRequest.</span></span>

<span data-ttu-id="4869a-123">このイベントは、webview 内のコンテンツが新しいウィンドウを開くように要求したときに発生します (ウィンドウを開く () など)。</span><span class="sxs-lookup"><span data-stu-id="4869a-123">The event is fired when content inside webview requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="4869a-124">Members</span><span class="sxs-lookup"><span data-stu-id="4869a-124">Members</span></span>

#### <span data-ttu-id="4869a-125">get_Handled</span><span class="sxs-lookup"><span data-stu-id="4869a-125">get_Handled</span></span> 

<span data-ttu-id="4869a-126">NewWindowRequestedEvent がホストによって処理されるかどうかを取得します。</span><span class="sxs-lookup"><span data-stu-id="4869a-126">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="4869a-127">パブリック HRESULT [get_Handled](#get_handled)(ブール \* Handled)</span><span class="sxs-lookup"><span data-stu-id="4869a-127">public HRESULT [get_Handled](#get_handled)(BOOL \* handled)</span></span>

#### <span data-ttu-id="4869a-128">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="4869a-128">get_IsUserInitiated</span></span> 

<span data-ttu-id="4869a-129">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="4869a-129">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>

> <span data-ttu-id="4869a-130">パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール \* isUserInitiated)</span><span class="sxs-lookup"><span data-stu-id="4869a-130">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="4869a-131">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="4869a-131">get_NewWindow</span></span> 

<span data-ttu-id="4869a-132">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="4869a-132">Gets the new window.</span></span>

> <span data-ttu-id="4869a-133">パブリック HRESULT [get_NewWindow](#get_newwindow)([ICoreWebView2](icorewebview2.md) \* \* NewWindow)</span><span class="sxs-lookup"><span data-stu-id="4869a-133">public HRESULT [get_NewWindow](#get_newwindow)([ICoreWebView2](icorewebview2.md) \*\* newWindow)</span></span>

#### <span data-ttu-id="4869a-134">get_Uri</span><span class="sxs-lookup"><span data-stu-id="4869a-134">get_Uri</span></span> 

<span data-ttu-id="4869a-135">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="4869a-135">The target uri of the NewWindowRequest.</span></span>

> <span data-ttu-id="4869a-136">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="4869a-136">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="4869a-137">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="4869a-137">GetDeferral</span></span> 

<span data-ttu-id="4869a-138">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="4869a-138">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="4869a-139">パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="4869a-139">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="4869a-140">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを使って、後でウィンドウを開く要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="4869a-140">You can use the [ICoreWebView2Deferral](icorewebview2deferral.md) object to complete the window open request at a later time.</span></span> <span data-ttu-id="4869a-141">このイベントが延期されている間、opener window は、ウィンドウから切り離されたウィンドウに WindowProxy を返します。これは、延期が完了すると移動します。</span><span class="sxs-lookup"><span data-stu-id="4869a-141">While this event is deferred the opener window will be returned a WindowProxy to an unnavigated window, which will navigate when the deferral is complete.</span></span>

#### <span data-ttu-id="4869a-142">put_Handled</span><span class="sxs-lookup"><span data-stu-id="4869a-142">put_Handled</span></span> 

<span data-ttu-id="4869a-143">NewWindowRequestedEvent がホストによって処理されるかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="4869a-143">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="4869a-144">パブリック HRESULT [put_Handled](#put_handled)(ブール値で処理される)</span><span class="sxs-lookup"><span data-stu-id="4869a-144">public HRESULT [put_Handled](#put_handled)(BOOL handled)</span></span>

<span data-ttu-id="4869a-145">この値が false で、NewWindow が設定されていない場合は、WebView にポップアップウィンドウが表示され、開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="4869a-145">If this is false and no NewWindow is set, the WebView will open a popup window and it will be returned as opened WindowProxy.</span></span> <span data-ttu-id="4869a-146">Window に対して NewWindow が設定されていない場合は true に設定します。 [呼び出し] を開くと、開いている WindowProxy は dummy ウィンドウオブジェクトになり、ウィンドウは読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="4869a-146">If set to true and no NewWindow is set for a window.open call, the opened WindowProxy will be for an dummy window object and no window will load.</span></span> <span data-ttu-id="4869a-147">Default は false です。</span><span class="sxs-lookup"><span data-stu-id="4869a-147">Default is false.</span></span>

#### <span data-ttu-id="4869a-148">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="4869a-148">put_NewWindow</span></span> 

<span data-ttu-id="4869a-149">NewWindowRequest の結果として WebView を設定します。</span><span class="sxs-lookup"><span data-stu-id="4869a-149">Sets a WebView as a result of the NewWindowRequest.</span></span>

> <span data-ttu-id="4869a-150">パブリック HRESULT [put_NewWindow](#put_newwindow)([ICoreWebView2](icorewebview2.md) \* NewWindow)</span><span class="sxs-lookup"><span data-stu-id="4869a-150">public HRESULT [put_NewWindow](#put_newwindow)([ICoreWebView2](icorewebview2.md) \* newWindow)</span></span>

<span data-ttu-id="4869a-151">ターゲット webview に移動しないようにします。</span><span class="sxs-lookup"><span data-stu-id="4869a-151">The target webview should not be navigated.</span></span> <span data-ttu-id="4869a-152">NewWindow が設定されている場合は、トップレベルのウィンドウが開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="4869a-152">If the NewWindow is set, its top level window will return as the opened WindowProxy.</span></span>
