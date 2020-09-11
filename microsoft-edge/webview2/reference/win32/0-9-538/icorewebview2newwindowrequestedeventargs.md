---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: 0.9.579-WebView2 Win32 C++ ICoreWebView2NewWindowRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2NewWindowRequestedEventArgs
ms.openlocfilehash: 5486aa66e39e220e819bb00211a79bd449a25bfe
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010062"
---
# <span data-ttu-id="da6e4-104">0.9.579-インターフェイス ICoreWebView2NewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="da6e4-104">0.9.579 - interface ICoreWebView2NewWindowRequestedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2NewWindowRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="da6e4-105">NewWindowRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="da6e4-105">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="da6e4-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="da6e4-106">Summary</span></span>

 <span data-ttu-id="da6e4-107">Members</span><span class="sxs-lookup"><span data-stu-id="da6e4-107">Members</span></span>                        | <span data-ttu-id="da6e4-108">説明</span><span class="sxs-lookup"><span data-stu-id="da6e4-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="da6e4-109">get_Handled</span><span class="sxs-lookup"><span data-stu-id="da6e4-109">get_Handled</span></span>](#get_handled) | <span data-ttu-id="da6e4-110">NewWindowRequestedEvent がホストによって処理されるかどうかを取得します。</span><span class="sxs-lookup"><span data-stu-id="da6e4-110">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="da6e4-111">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="da6e4-111">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="da6e4-112">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="da6e4-112">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>
[<span data-ttu-id="da6e4-113">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="da6e4-113">get_NewWindow</span></span>](#get_newwindow) | <span data-ttu-id="da6e4-114">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="da6e4-114">Gets the new window.</span></span>
[<span data-ttu-id="da6e4-115">get_Uri</span><span class="sxs-lookup"><span data-stu-id="da6e4-115">get_Uri</span></span>](#get_uri) | <span data-ttu-id="da6e4-116">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="da6e4-116">The target uri of the NewWindowRequest.</span></span>
[<span data-ttu-id="da6e4-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="da6e4-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="da6e4-118">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="da6e4-118">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>
[<span data-ttu-id="da6e4-119">put_Handled</span><span class="sxs-lookup"><span data-stu-id="da6e4-119">put_Handled</span></span>](#put_handled) | <span data-ttu-id="da6e4-120">NewWindowRequestedEvent がホストによって処理されるかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="da6e4-120">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="da6e4-121">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="da6e4-121">put_NewWindow</span></span>](#put_newwindow) | <span data-ttu-id="da6e4-122">NewWindowRequest の結果として WebView を設定します。</span><span class="sxs-lookup"><span data-stu-id="da6e4-122">Sets a WebView as a result of the NewWindowRequest.</span></span>

<span data-ttu-id="da6e4-123">このイベントは、webview 内のコンテンツが新しいウィンドウを開くように要求したときに発生します (ウィンドウを開く () など)。</span><span class="sxs-lookup"><span data-stu-id="da6e4-123">The event is fired when content inside webview requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="da6e4-124">Members</span><span class="sxs-lookup"><span data-stu-id="da6e4-124">Members</span></span>

#### <span data-ttu-id="da6e4-125">get_Handled</span><span class="sxs-lookup"><span data-stu-id="da6e4-125">get_Handled</span></span> 

<span data-ttu-id="da6e4-126">NewWindowRequestedEvent がホストによって処理されるかどうかを取得します。</span><span class="sxs-lookup"><span data-stu-id="da6e4-126">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="da6e4-127">パブリック HRESULT [get_Handled](#get_handled)(ブール \* Handled)</span><span class="sxs-lookup"><span data-stu-id="da6e4-127">public HRESULT [get_Handled](#get_handled)(BOOL \* handled)</span></span>

#### <span data-ttu-id="da6e4-128">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="da6e4-128">get_IsUserInitiated</span></span> 

<span data-ttu-id="da6e4-129">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="da6e4-129">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>

> <span data-ttu-id="da6e4-130">パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール \* isUserInitiated)</span><span class="sxs-lookup"><span data-stu-id="da6e4-130">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

<span data-ttu-id="da6e4-131">エッジポップアップブロックは、WebView に対して無効になっているため、アプリはこのフラグを使って、ユーザーによって開始されていないポップアップをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="da6e4-131">The Edge popup blocker is disabled for WebView so the app can use this flag to block non-user initiated popups.</span></span>

#### <span data-ttu-id="da6e4-132">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="da6e4-132">get_NewWindow</span></span> 

<span data-ttu-id="da6e4-133">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="da6e4-133">Gets the new window.</span></span>

> <span data-ttu-id="da6e4-134">パブリック HRESULT [get_NewWindow](#get_newwindow)([ICoreWebView2](icorewebview2.md) \* \* NewWindow)</span><span class="sxs-lookup"><span data-stu-id="da6e4-134">public HRESULT [get_NewWindow](#get_newwindow)([ICoreWebView2](icorewebview2.md) \*\* newWindow)</span></span>

#### <span data-ttu-id="da6e4-135">get_Uri</span><span class="sxs-lookup"><span data-stu-id="da6e4-135">get_Uri</span></span> 

<span data-ttu-id="da6e4-136">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="da6e4-136">The target uri of the NewWindowRequest.</span></span>

> <span data-ttu-id="da6e4-137">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="da6e4-137">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="da6e4-138">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="da6e4-138">GetDeferral</span></span> 

<span data-ttu-id="da6e4-139">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="da6e4-139">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="da6e4-140">パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="da6e4-140">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="da6e4-141">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを使って、後でウィンドウを開く要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="da6e4-141">You can use the [ICoreWebView2Deferral](icorewebview2deferral.md) object to complete the window open request at a later time.</span></span> <span data-ttu-id="da6e4-142">このイベントが延期されている間、opener window は、ウィンドウから切り離されたウィンドウに WindowProxy を返します。これは、延期が完了すると移動します。</span><span class="sxs-lookup"><span data-stu-id="da6e4-142">While this event is deferred the opener window will be returned a WindowProxy to an unnavigated window, which will navigate when the deferral is complete.</span></span>

#### <span data-ttu-id="da6e4-143">put_Handled</span><span class="sxs-lookup"><span data-stu-id="da6e4-143">put_Handled</span></span> 

<span data-ttu-id="da6e4-144">NewWindowRequestedEvent がホストによって処理されるかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="da6e4-144">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="da6e4-145">パブリック HRESULT [put_Handled](#put_handled)(ブール値で処理される)</span><span class="sxs-lookup"><span data-stu-id="da6e4-145">public HRESULT [put_Handled](#put_handled)(BOOL handled)</span></span>

<span data-ttu-id="da6e4-146">この値が false で、NewWindow が設定されていない場合は、WebView にポップアップウィンドウが表示され、開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="da6e4-146">If this is false and no NewWindow is set, the WebView will open a popup window and it will be returned as opened WindowProxy.</span></span> <span data-ttu-id="da6e4-147">Window に対して NewWindow が設定されていない場合は true に設定します。 [呼び出し] を開くと、開いている WindowProxy は dummy ウィンドウオブジェクトになり、ウィンドウは読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="da6e4-147">If set to true and no NewWindow is set for a window.open call, the opened WindowProxy will be for an dummy window object and no window will load.</span></span> <span data-ttu-id="da6e4-148">Default は false です。</span><span class="sxs-lookup"><span data-stu-id="da6e4-148">Default is false.</span></span>

#### <span data-ttu-id="da6e4-149">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="da6e4-149">put_NewWindow</span></span> 

<span data-ttu-id="da6e4-150">NewWindowRequest の結果として WebView を設定します。</span><span class="sxs-lookup"><span data-stu-id="da6e4-150">Sets a WebView as a result of the NewWindowRequest.</span></span>

> <span data-ttu-id="da6e4-151">パブリック HRESULT [put_NewWindow](#put_newwindow)([ICoreWebView2](icorewebview2.md) \* NewWindow)</span><span class="sxs-lookup"><span data-stu-id="da6e4-151">public HRESULT [put_NewWindow](#put_newwindow)([ICoreWebView2](icorewebview2.md) \* newWindow)</span></span>

<span data-ttu-id="da6e4-152">ターゲット webview に移動しないようにします。</span><span class="sxs-lookup"><span data-stu-id="da6e4-152">The target webview should not be navigated.</span></span> <span data-ttu-id="da6e4-153">NewWindow が設定されている場合は、トップレベルのウィンドウが開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="da6e4-153">If the NewWindow is set, its top level window will return as the opened WindowProxy.</span></span>

