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
ms.openlocfilehash: d99c05026257116dd5c6c7119325e00227d9a6d0
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697813"
---
# <span data-ttu-id="459fa-104">インターフェイス ICoreWebView2NewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="459fa-104">interface ICoreWebView2NewWindowRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="459fa-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="459fa-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="459fa-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="459fa-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2NewWindowRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="459fa-107">NewWindowRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="459fa-107">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="459fa-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="459fa-108">Summary</span></span>

 <span data-ttu-id="459fa-109">Members</span><span class="sxs-lookup"><span data-stu-id="459fa-109">Members</span></span>                        | <span data-ttu-id="459fa-110">説明</span><span class="sxs-lookup"><span data-stu-id="459fa-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="459fa-111">get_Handled</span><span class="sxs-lookup"><span data-stu-id="459fa-111">get_Handled</span></span>](#get_handled) | <span data-ttu-id="459fa-112">NewWindowRequestedEvent がホストによって処理されるかどうかを取得します。</span><span class="sxs-lookup"><span data-stu-id="459fa-112">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="459fa-113">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="459fa-113">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="459fa-114">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="459fa-114">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>
[<span data-ttu-id="459fa-115">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="459fa-115">get_NewWindow</span></span>](#get_newwindow) | <span data-ttu-id="459fa-116">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="459fa-116">Gets the new window.</span></span>
[<span data-ttu-id="459fa-117">get_Uri</span><span class="sxs-lookup"><span data-stu-id="459fa-117">get_Uri</span></span>](#get_uri) | <span data-ttu-id="459fa-118">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="459fa-118">The target uri of the NewWindowRequest.</span></span>
[<span data-ttu-id="459fa-119">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="459fa-119">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="459fa-120">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="459fa-120">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>
[<span data-ttu-id="459fa-121">put_Handled</span><span class="sxs-lookup"><span data-stu-id="459fa-121">put_Handled</span></span>](#put_handled) | <span data-ttu-id="459fa-122">NewWindowRequestedEvent がホストによって処理されるかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="459fa-122">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="459fa-123">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="459fa-123">put_NewWindow</span></span>](#put_newwindow) | <span data-ttu-id="459fa-124">NewWindowRequest の結果として WebView を設定します。</span><span class="sxs-lookup"><span data-stu-id="459fa-124">Sets a WebView as a result of the NewWindowRequest.</span></span>

<span data-ttu-id="459fa-125">このイベントは、webview 内のコンテンツが新しいウィンドウを開くように要求したときに発生します (ウィンドウを開く () など)。</span><span class="sxs-lookup"><span data-stu-id="459fa-125">The event is fired when content inside webview requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="459fa-126">Members</span><span class="sxs-lookup"><span data-stu-id="459fa-126">Members</span></span>

#### <span data-ttu-id="459fa-127">get_Handled</span><span class="sxs-lookup"><span data-stu-id="459fa-127">get_Handled</span></span> 

<span data-ttu-id="459fa-128">NewWindowRequestedEvent がホストによって処理されるかどうかを取得します。</span><span class="sxs-lookup"><span data-stu-id="459fa-128">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="459fa-129">パブリック HRESULT [get_Handled](#get_handled)(ブール \* Handled)</span><span class="sxs-lookup"><span data-stu-id="459fa-129">public HRESULT [get_Handled](#get_handled)(BOOL \* handled)</span></span>

#### <span data-ttu-id="459fa-130">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="459fa-130">get_IsUserInitiated</span></span> 

<span data-ttu-id="459fa-131">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="459fa-131">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>

> <span data-ttu-id="459fa-132">パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール \* isUserInitiated)</span><span class="sxs-lookup"><span data-stu-id="459fa-132">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="459fa-133">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="459fa-133">get_NewWindow</span></span> 

<span data-ttu-id="459fa-134">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="459fa-134">Gets the new window.</span></span>

> <span data-ttu-id="459fa-135">パブリック HRESULT [get_NewWindow](#get_newwindow)([ICoreWebView2](icorewebview2.md) \* \* NewWindow)</span><span class="sxs-lookup"><span data-stu-id="459fa-135">public HRESULT [get_NewWindow](#get_newwindow)([ICoreWebView2](icorewebview2.md) \*\* newWindow)</span></span>

#### <span data-ttu-id="459fa-136">get_Uri</span><span class="sxs-lookup"><span data-stu-id="459fa-136">get_Uri</span></span> 

<span data-ttu-id="459fa-137">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="459fa-137">The target uri of the NewWindowRequest.</span></span>

> <span data-ttu-id="459fa-138">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="459fa-138">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="459fa-139">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="459fa-139">GetDeferral</span></span> 

<span data-ttu-id="459fa-140">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="459fa-140">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="459fa-141">パブリック HRESULT [Getdeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="459fa-141">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="459fa-142">[ICoreWebView2Deferral](icorewebview2deferral.md)オブジェクトを使って、後でウィンドウを開く要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="459fa-142">You can use the [ICoreWebView2Deferral](icorewebview2deferral.md) object to complete the window open request at a later time.</span></span> <span data-ttu-id="459fa-143">このイベントが延期されている間、opener window は、ウィンドウから切り離されたウィンドウに WindowProxy を返します。これは、延期が完了すると移動します。</span><span class="sxs-lookup"><span data-stu-id="459fa-143">While this event is deferred the opener window will be returned a WindowProxy to an unnavigated window, which will navigate when the deferral is complete.</span></span>

#### <span data-ttu-id="459fa-144">put_Handled</span><span class="sxs-lookup"><span data-stu-id="459fa-144">put_Handled</span></span> 

<span data-ttu-id="459fa-145">NewWindowRequestedEvent がホストによって処理されるかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="459fa-145">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="459fa-146">パブリック HRESULT [put_Handled](#put_handled)(ブール値で処理される)</span><span class="sxs-lookup"><span data-stu-id="459fa-146">public HRESULT [put_Handled](#put_handled)(BOOL handled)</span></span>

<span data-ttu-id="459fa-147">この値が false で、NewWindow が設定されていない場合は、WebView にポップアップウィンドウが表示され、開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="459fa-147">If this is false and no NewWindow is set, the WebView will open a popup window and it will be returned as opened WindowProxy.</span></span> <span data-ttu-id="459fa-148">Window に対して NewWindow が設定されていない場合は true に設定します。 [呼び出し] を開くと、開いている WindowProxy は dummy ウィンドウオブジェクトになり、ウィンドウは読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="459fa-148">If set to true and no NewWindow is set for a window.open call, the opened WindowProxy will be for an dummy window object and no window will load.</span></span> <span data-ttu-id="459fa-149">Default は false です。</span><span class="sxs-lookup"><span data-stu-id="459fa-149">Default is false.</span></span>

#### <span data-ttu-id="459fa-150">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="459fa-150">put_NewWindow</span></span> 

<span data-ttu-id="459fa-151">NewWindowRequest の結果として WebView を設定します。</span><span class="sxs-lookup"><span data-stu-id="459fa-151">Sets a WebView as a result of the NewWindowRequest.</span></span>

> <span data-ttu-id="459fa-152">パブリック HRESULT [put_NewWindow](#put_newwindow)([ICoreWebView2](icorewebview2.md) \* NewWindow)</span><span class="sxs-lookup"><span data-stu-id="459fa-152">public HRESULT [put_NewWindow](#put_newwindow)([ICoreWebView2](icorewebview2.md) \* newWindow)</span></span>

<span data-ttu-id="459fa-153">ターゲット webview に移動しないようにします。</span><span class="sxs-lookup"><span data-stu-id="459fa-153">The target webview should not be navigated.</span></span> <span data-ttu-id="459fa-154">NewWindow が設定されている場合は、トップレベルのウィンドウが開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="459fa-154">If the NewWindow is set, its top level window will return as the opened WindowProxy.</span></span>

