---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 2ea3500c5e230b543f75241c47c58163276942da
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "10654401"
---
# <span data-ttu-id="900b4-104">インターフェイス ICoreWebView2NewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="900b4-104">interface ICoreWebView2NewWindowRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="900b4-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="900b4-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="900b4-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="900b4-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2NewWindowRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="900b4-107">NewWindowRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="900b4-107">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="900b4-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="900b4-108">Summary</span></span>

 <span data-ttu-id="900b4-109">Members</span><span class="sxs-lookup"><span data-stu-id="900b4-109">Members</span></span>                        | <span data-ttu-id="900b4-110">説明</span><span class="sxs-lookup"><span data-stu-id="900b4-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="900b4-111">get_Uri</span><span class="sxs-lookup"><span data-stu-id="900b4-111">get_Uri</span></span>](#get_uri) | <span data-ttu-id="900b4-112">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="900b4-112">The target uri of the NewWindowRequest.</span></span>
[<span data-ttu-id="900b4-113">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="900b4-113">put_NewWindow</span></span>](#put_newwindow) | <span data-ttu-id="900b4-114">NewWindowRequest の結果として WebView を設定します。</span><span class="sxs-lookup"><span data-stu-id="900b4-114">Sets a WebView as a result of the NewWindowRequest.</span></span>
[<span data-ttu-id="900b4-115">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="900b4-115">get_NewWindow</span></span>](#get_newwindow) | <span data-ttu-id="900b4-116">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="900b4-116">Gets the new window.</span></span>
[<span data-ttu-id="900b4-117">put_Handled</span><span class="sxs-lookup"><span data-stu-id="900b4-117">put_Handled</span></span>](#put_handled) | <span data-ttu-id="900b4-118">NewWindowRequestedEvent がホストによって処理されるかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="900b4-118">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="900b4-119">get_Handled</span><span class="sxs-lookup"><span data-stu-id="900b4-119">get_Handled</span></span>](#get_handled) | <span data-ttu-id="900b4-120">NewWindowRequestedEvent がホストによって処理されるかどうかを取得します。</span><span class="sxs-lookup"><span data-stu-id="900b4-120">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="900b4-121">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="900b4-121">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="900b4-122">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="900b4-122">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>
[<span data-ttu-id="900b4-123">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="900b4-123">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="900b4-124">[ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="900b4-124">Obtain an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object and put the event into a deferred state.</span></span>

<span data-ttu-id="900b4-125">このイベントは、webview 内のコンテンツが新しいウィンドウ (open () など) に要求されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="900b4-125">The event is fired when content inside webview requested to a open a new window (through window.open() etc.)</span></span>

## <span data-ttu-id="900b4-126">Members</span><span class="sxs-lookup"><span data-stu-id="900b4-126">Members</span></span>

#### <span data-ttu-id="900b4-127">get_Uri</span><span class="sxs-lookup"><span data-stu-id="900b4-127">get_Uri</span></span> 

<span data-ttu-id="900b4-128">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="900b4-128">The target uri of the NewWindowRequest.</span></span>

> <span data-ttu-id="900b4-129">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="900b4-129">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="900b4-130">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="900b4-130">put_NewWindow</span></span> 

<span data-ttu-id="900b4-131">NewWindowRequest の結果として WebView を設定します。</span><span class="sxs-lookup"><span data-stu-id="900b4-131">Sets a WebView as a result of the NewWindowRequest.</span></span>

> <span data-ttu-id="900b4-132">パブリック HRESULT [put_NewWindow](#put_newwindow)([ICoreWebView2](ICoreWebView2.md) \* NewWindow)</span><span class="sxs-lookup"><span data-stu-id="900b4-132">public HRESULT [put_NewWindow](#put_newwindow)([ICoreWebView2](ICoreWebView2.md) \* newWindow)</span></span>

<span data-ttu-id="900b4-133">ターゲット webview に移動しないようにします。</span><span class="sxs-lookup"><span data-stu-id="900b4-133">The target webview should not be navigated.</span></span> <span data-ttu-id="900b4-134">NewWindow が設定されている場合は、トップレベルのウィンドウが開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="900b4-134">If the NewWindow is set, its top level window will return as the opened WindowProxy.</span></span>

#### <span data-ttu-id="900b4-135">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="900b4-135">get_NewWindow</span></span> 

<span data-ttu-id="900b4-136">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="900b4-136">Gets the new window.</span></span>

> <span data-ttu-id="900b4-137">パブリック HRESULT [get_NewWindow](#get_newwindow)([ICoreWebView2](ICoreWebView2.md) \* \* NewWindow)</span><span class="sxs-lookup"><span data-stu-id="900b4-137">public HRESULT [get_NewWindow](#get_newwindow)([ICoreWebView2](ICoreWebView2.md) \*\* newWindow)</span></span>

#### <span data-ttu-id="900b4-138">put_Handled</span><span class="sxs-lookup"><span data-stu-id="900b4-138">put_Handled</span></span> 

<span data-ttu-id="900b4-139">NewWindowRequestedEvent がホストによって処理されるかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="900b4-139">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="900b4-140">パブリック HRESULT [put_Handled](#put_handled)(ブール値で処理される)</span><span class="sxs-lookup"><span data-stu-id="900b4-140">public HRESULT [put_Handled](#put_handled)(BOOL handled)</span></span>

<span data-ttu-id="900b4-141">この値が false で、NewWindow が設定されていない場合は、WebView にポップアップウィンドウが表示され、開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="900b4-141">If this is false and no NewWindow is set, the WebView will open a popup window and it will be returned as opened WindowProxy.</span></span> <span data-ttu-id="900b4-142">Window に対して NewWindow が設定されていない場合は true に設定します。 [呼び出し] を開くと、開いている WindowProxy は dummy ウィンドウオブジェクトになり、ウィンドウは読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="900b4-142">If set to true and no NewWindow is set for a window.open call, the opened WindowProxy will be for an dummy window object and no window will load.</span></span> <span data-ttu-id="900b4-143">Default は false です。</span><span class="sxs-lookup"><span data-stu-id="900b4-143">Default is false.</span></span>

#### <span data-ttu-id="900b4-144">get_Handled</span><span class="sxs-lookup"><span data-stu-id="900b4-144">get_Handled</span></span> 

<span data-ttu-id="900b4-145">NewWindowRequestedEvent がホストによって処理されるかどうかを取得します。</span><span class="sxs-lookup"><span data-stu-id="900b4-145">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="900b4-146">パブリック HRESULT [get_Handled](#get_handled)(ブール \* Handled)</span><span class="sxs-lookup"><span data-stu-id="900b4-146">public HRESULT [get_Handled](#get_handled)(BOOL \* handled)</span></span>

#### <span data-ttu-id="900b4-147">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="900b4-147">get_IsUserInitiated</span></span> 

<span data-ttu-id="900b4-148">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="900b4-148">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>

> <span data-ttu-id="900b4-149">パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール \* isUserInitiated)</span><span class="sxs-lookup"><span data-stu-id="900b4-149">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="900b4-150">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="900b4-150">GetDeferral</span></span> 

<span data-ttu-id="900b4-151">[ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="900b4-151">Obtain an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="900b4-152">パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="900b4-152">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="900b4-153">[ICoreWebView2Deferral](ICoreWebView2Deferral.md)オブジェクトを使って、後でウィンドウを開く要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="900b4-153">You can use the [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object to complete the window open request at a later time.</span></span> <span data-ttu-id="900b4-154">このイベントが延期されている間、opener window は、ウィンドウから切り離されたウィンドウに WindowProxy を返します。これは、延期が完了すると移動します。</span><span class="sxs-lookup"><span data-stu-id="900b4-154">While this event is deferred the opener window will be returned a WindowProxy to an unnavigated window, which will navigate when the deferral is complete.</span></span>

