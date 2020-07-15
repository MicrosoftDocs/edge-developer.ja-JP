---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2NewWindowRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2NewWindowRequestedEventArgs
ms.openlocfilehash: bb18b6662fd5921406e19b3c333c97f8a1cd0dbc
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879437"
---
# <span data-ttu-id="d17b7-104">インターフェイス ICoreWebView2NewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="d17b7-104">interface ICoreWebView2NewWindowRequestedEventArgs</span></span> 

```
interface ICoreWebView2NewWindowRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="d17b7-105">NewWindowRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="d17b7-105">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="d17b7-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="d17b7-106">Summary</span></span>

 <span data-ttu-id="d17b7-107">Members</span><span class="sxs-lookup"><span data-stu-id="d17b7-107">Members</span></span>                        | <span data-ttu-id="d17b7-108">説明</span><span class="sxs-lookup"><span data-stu-id="d17b7-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d17b7-109">get_Handled</span><span class="sxs-lookup"><span data-stu-id="d17b7-109">get_Handled</span></span>](#get_handled) | <span data-ttu-id="d17b7-110">NewWindowRequestedEvent がホストによって処理されるかどうかを取得します。</span><span class="sxs-lookup"><span data-stu-id="d17b7-110">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="d17b7-111">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="d17b7-111">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="d17b7-112">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="d17b7-112">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>
[<span data-ttu-id="d17b7-113">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="d17b7-113">get_NewWindow</span></span>](#get_newwindow) | <span data-ttu-id="d17b7-114">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="d17b7-114">Gets the new window.</span></span>
[<span data-ttu-id="d17b7-115">get_Uri</span><span class="sxs-lookup"><span data-stu-id="d17b7-115">get_Uri</span></span>](#get_uri) | <span data-ttu-id="d17b7-116">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="d17b7-116">The target uri of the NewWindowRequest.</span></span>
[<span data-ttu-id="d17b7-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="d17b7-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="d17b7-118">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="d17b7-118">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>
[<span data-ttu-id="d17b7-119">put_Handled</span><span class="sxs-lookup"><span data-stu-id="d17b7-119">put_Handled</span></span>](#put_handled) | <span data-ttu-id="d17b7-120">NewWindowRequestedEvent がホストによって処理されるかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="d17b7-120">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="d17b7-121">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="d17b7-121">put_NewWindow</span></span>](#put_newwindow) | <span data-ttu-id="d17b7-122">NewWindowRequest の結果として WebView を設定します。</span><span class="sxs-lookup"><span data-stu-id="d17b7-122">Sets a WebView as a result of the NewWindowRequest.</span></span>

<span data-ttu-id="d17b7-123">このイベントは、webview 内のコンテンツが新しいウィンドウを開くように要求したときに発生します (ウィンドウを開く () など)。</span><span class="sxs-lookup"><span data-stu-id="d17b7-123">The event is fired when content inside webview requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="d17b7-124">Members</span><span class="sxs-lookup"><span data-stu-id="d17b7-124">Members</span></span>

#### <span data-ttu-id="d17b7-125">get_Handled</span><span class="sxs-lookup"><span data-stu-id="d17b7-125">get_Handled</span></span> 

<span data-ttu-id="d17b7-126">NewWindowRequestedEvent がホストによって処理されるかどうかを取得します。</span><span class="sxs-lookup"><span data-stu-id="d17b7-126">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="d17b7-127">パブリック HRESULT [get_Handled](#get_handled)(ブール \* Handled)</span><span class="sxs-lookup"><span data-stu-id="d17b7-127">public HRESULT [get_Handled](#get_handled)(BOOL \* handled)</span></span>

#### <span data-ttu-id="d17b7-128">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="d17b7-128">get_IsUserInitiated</span></span> 

<span data-ttu-id="d17b7-129">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="d17b7-129">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>

> <span data-ttu-id="d17b7-130">パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール \* isUserInitiated)</span><span class="sxs-lookup"><span data-stu-id="d17b7-130">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

<span data-ttu-id="d17b7-131">エッジポップアップブロックは、WebView に対して無効になっているため、アプリはこのフラグを使って、ユーザーによって開始されていないポップアップをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="d17b7-131">The Edge popup blocker is disabled for WebView so the app can use this flag to block non-user initiated popups.</span></span>

#### <span data-ttu-id="d17b7-132">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="d17b7-132">get_NewWindow</span></span> 

<span data-ttu-id="d17b7-133">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="d17b7-133">Gets the new window.</span></span>

> <span data-ttu-id="d17b7-134">パブリック HRESULT [get_NewWindow](#get_newwindow)([ICoreWebView2](icorewebview2.md) \* \* NewWindow)</span><span class="sxs-lookup"><span data-stu-id="d17b7-134">public HRESULT [get_NewWindow](#get_newwindow)([ICoreWebView2](icorewebview2.md) \*\* newWindow)</span></span>

#### <span data-ttu-id="d17b7-135">get_Uri</span><span class="sxs-lookup"><span data-stu-id="d17b7-135">get_Uri</span></span> 

<span data-ttu-id="d17b7-136">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="d17b7-136">The target uri of the NewWindowRequest.</span></span>

> <span data-ttu-id="d17b7-137">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="d17b7-137">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="d17b7-138">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="d17b7-138">GetDeferral</span></span> 

<span data-ttu-id="d17b7-139">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="d17b7-139">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="d17b7-140">パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="d17b7-140">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="d17b7-141">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを使って、後でウィンドウを開く要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="d17b7-141">You can use the [ICoreWebView2Deferral](icorewebview2deferral.md) object to complete the window open request at a later time.</span></span> <span data-ttu-id="d17b7-142">このイベントが延期されている間、opener window は、ウィンドウから切り離されたウィンドウに WindowProxy を返します。これは、延期が完了すると移動します。</span><span class="sxs-lookup"><span data-stu-id="d17b7-142">While this event is deferred the opener window will be returned a WindowProxy to an unnavigated window, which will navigate when the deferral is complete.</span></span>

#### <span data-ttu-id="d17b7-143">put_Handled</span><span class="sxs-lookup"><span data-stu-id="d17b7-143">put_Handled</span></span> 

<span data-ttu-id="d17b7-144">NewWindowRequestedEvent がホストによって処理されるかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="d17b7-144">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="d17b7-145">パブリック HRESULT [put_Handled](#put_handled)(ブール値で処理される)</span><span class="sxs-lookup"><span data-stu-id="d17b7-145">public HRESULT [put_Handled](#put_handled)(BOOL handled)</span></span>

<span data-ttu-id="d17b7-146">この値が false で、NewWindow が設定されていない場合は、WebView にポップアップウィンドウが表示され、開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="d17b7-146">If this is false and no NewWindow is set, the WebView will open a popup window and it will be returned as opened WindowProxy.</span></span> <span data-ttu-id="d17b7-147">Window に対して NewWindow が設定されていない場合は true に設定します。 [呼び出し] を開くと、開いている WindowProxy は dummy ウィンドウオブジェクトになり、ウィンドウは読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="d17b7-147">If set to true and no NewWindow is set for a window.open call, the opened WindowProxy will be for an dummy window object and no window will load.</span></span> <span data-ttu-id="d17b7-148">Default は false です。</span><span class="sxs-lookup"><span data-stu-id="d17b7-148">Default is false.</span></span>

#### <span data-ttu-id="d17b7-149">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="d17b7-149">put_NewWindow</span></span> 

<span data-ttu-id="d17b7-150">NewWindowRequest の結果として WebView を設定します。</span><span class="sxs-lookup"><span data-stu-id="d17b7-150">Sets a WebView as a result of the NewWindowRequest.</span></span>

> <span data-ttu-id="d17b7-151">パブリック HRESULT [put_NewWindow](#put_newwindow)([ICoreWebView2](icorewebview2.md) \* NewWindow)</span><span class="sxs-lookup"><span data-stu-id="d17b7-151">public HRESULT [put_NewWindow](#put_newwindow)([ICoreWebView2](icorewebview2.md) \* newWindow)</span></span>

<span data-ttu-id="d17b7-152">ターゲット webview に移動しないようにします。</span><span class="sxs-lookup"><span data-stu-id="d17b7-152">The target webview should not be navigated.</span></span> <span data-ttu-id="d17b7-153">NewWindow が設定されている場合は、トップレベルのウィンドウが開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="d17b7-153">If the NewWindow is set, its top level window will return as the opened WindowProxy.</span></span>

