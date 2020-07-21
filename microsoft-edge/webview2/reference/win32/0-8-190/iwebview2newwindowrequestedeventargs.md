---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.8.355-WebView2 Win32 C++ IWebView2NewWindowRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge
ms.openlocfilehash: cbcac385546c44e776ed48b8ae4d3ab754b614e0
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885894"
---
# <span data-ttu-id="33cc5-104">0.8.355-インターフェイス IWebView2NewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="33cc5-104">0.8.355 - interface IWebView2NewWindowRequestedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2NewWindowRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="33cc5-105">NewWindowRequested イベントのイベント引数。</span><span class="sxs-lookup"><span data-stu-id="33cc5-105">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="33cc5-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="33cc5-106">Summary</span></span>

 <span data-ttu-id="33cc5-107">Members</span><span class="sxs-lookup"><span data-stu-id="33cc5-107">Members</span></span>                        | <span data-ttu-id="33cc5-108">説明</span><span class="sxs-lookup"><span data-stu-id="33cc5-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="33cc5-109">get_Uri</span><span class="sxs-lookup"><span data-stu-id="33cc5-109">get_Uri</span></span>](#get_uri) | <span data-ttu-id="33cc5-110">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="33cc5-110">The target uri of the NewWindowRequest.</span></span>
[<span data-ttu-id="33cc5-111">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="33cc5-111">put_NewWindow</span></span>](#put_newwindow) | <span data-ttu-id="33cc5-112">NewWindowRequest の結果として WebView を設定します。</span><span class="sxs-lookup"><span data-stu-id="33cc5-112">Sets a WebView as a result of the NewWindowRequest.</span></span>
[<span data-ttu-id="33cc5-113">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="33cc5-113">get_NewWindow</span></span>](#get_newwindow) | <span data-ttu-id="33cc5-114">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="33cc5-114">Gets the new window.</span></span>
[<span data-ttu-id="33cc5-115">put_Handled</span><span class="sxs-lookup"><span data-stu-id="33cc5-115">put_Handled</span></span>](#put_handled) | <span data-ttu-id="33cc5-116">NewWindowRequestedEvent がホストによって処理されるかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="33cc5-116">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="33cc5-117">get_Handled</span><span class="sxs-lookup"><span data-stu-id="33cc5-117">get_Handled</span></span>](#get_handled) | <span data-ttu-id="33cc5-118">NewWindowRequestedEvent がホストによって処理されるかどうかを取得します。</span><span class="sxs-lookup"><span data-stu-id="33cc5-118">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="33cc5-119">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="33cc5-119">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="33cc5-120">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="33cc5-120">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>
[<span data-ttu-id="33cc5-121">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="33cc5-121">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="33cc5-122">[IWebView2Deferral](IWebView2Deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="33cc5-122">Obtain an [IWebView2Deferral](IWebView2Deferral.md) object and put the event into a deferred state.</span></span>

<span data-ttu-id="33cc5-123">このイベントは、webview 内のコンテンツが新しいウィンドウ (open () など) に要求されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="33cc5-123">The event is fired when content inside webview requested to a open a new window (through window.open() etc.)</span></span>

## <span data-ttu-id="33cc5-124">Members</span><span class="sxs-lookup"><span data-stu-id="33cc5-124">Members</span></span>

#### <span data-ttu-id="33cc5-125">get_Uri</span><span class="sxs-lookup"><span data-stu-id="33cc5-125">get_Uri</span></span> 

<span data-ttu-id="33cc5-126">NewWindowRequest のターゲット uri。</span><span class="sxs-lookup"><span data-stu-id="33cc5-126">The target uri of the NewWindowRequest.</span></span>

> <span data-ttu-id="33cc5-127">パブリック HRESULT [get_Uri](#get_uri)(LPWSTR \* Uri)</span><span class="sxs-lookup"><span data-stu-id="33cc5-127">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="33cc5-128">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="33cc5-128">put_NewWindow</span></span> 

<span data-ttu-id="33cc5-129">NewWindowRequest の結果として WebView を設定します。</span><span class="sxs-lookup"><span data-stu-id="33cc5-129">Sets a WebView as a result of the NewWindowRequest.</span></span>

> <span data-ttu-id="33cc5-130">パブリック HRESULT [put_NewWindow](#put_newwindow)([IWebView2WebView](IWebView2WebView.md) \* NewWindow)</span><span class="sxs-lookup"><span data-stu-id="33cc5-130">public HRESULT [put_NewWindow](#put_newwindow)([IWebView2WebView](IWebView2WebView.md) \* newWindow)</span></span>

<span data-ttu-id="33cc5-131">ターゲット webview に移動しないようにします。</span><span class="sxs-lookup"><span data-stu-id="33cc5-131">The target webview should not be navigated.</span></span> <span data-ttu-id="33cc5-132">NewWindow が設定されている場合は、トップレベルのウィンドウが開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="33cc5-132">If the NewWindow is set, its top level window will return as the opened WindowProxy.</span></span>

#### <span data-ttu-id="33cc5-133">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="33cc5-133">get_NewWindow</span></span> 

<span data-ttu-id="33cc5-134">新しいウィンドウを取得します。</span><span class="sxs-lookup"><span data-stu-id="33cc5-134">Gets the new window.</span></span>

> <span data-ttu-id="33cc5-135">パブリック HRESULT [get_NewWindow](#get_newwindow)([IWebView2WebView](IWebView2WebView.md) \* \* NewWindow)</span><span class="sxs-lookup"><span data-stu-id="33cc5-135">public HRESULT [get_NewWindow](#get_newwindow)([IWebView2WebView](IWebView2WebView.md) \*\* newWindow)</span></span>

#### <span data-ttu-id="33cc5-136">put_Handled</span><span class="sxs-lookup"><span data-stu-id="33cc5-136">put_Handled</span></span> 

<span data-ttu-id="33cc5-137">NewWindowRequestedEvent がホストによって処理されるかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="33cc5-137">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="33cc5-138">パブリック HRESULT [put_Handled](#put_handled)(ブール値で処理される)</span><span class="sxs-lookup"><span data-stu-id="33cc5-138">public HRESULT [put_Handled](#put_handled)(BOOL handled)</span></span>

<span data-ttu-id="33cc5-139">この値が false で、NewWindow が設定されていない場合は、WebView にポップアップウィンドウが表示され、開いている WindowProxy として返されます。</span><span class="sxs-lookup"><span data-stu-id="33cc5-139">If this is false and no NewWindow is set, the WebView will open a popup window and it will be returned as opened WindowProxy.</span></span> <span data-ttu-id="33cc5-140">Window に対して NewWindow が設定されていない場合は true に設定します。 [呼び出し] を開くと、開いている WindowProxy は dummy ウィンドウオブジェクトになり、ウィンドウは読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="33cc5-140">If set to true and no NewWindow is set for a window.open call, the opened WindowProxy will be for an dummy window object and no window will load.</span></span> <span data-ttu-id="33cc5-141">Default は false です。</span><span class="sxs-lookup"><span data-stu-id="33cc5-141">Default is false.</span></span>

#### <span data-ttu-id="33cc5-142">get_Handled</span><span class="sxs-lookup"><span data-stu-id="33cc5-142">get_Handled</span></span> 

<span data-ttu-id="33cc5-143">NewWindowRequestedEvent がホストによって処理されるかどうかを取得します。</span><span class="sxs-lookup"><span data-stu-id="33cc5-143">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="33cc5-144">パブリック HRESULT [get_Handled](#get_handled)(ブール \* Handled)</span><span class="sxs-lookup"><span data-stu-id="33cc5-144">public HRESULT [get_Handled](#get_handled)(BOOL \* handled)</span></span>

#### <span data-ttu-id="33cc5-145">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="33cc5-145">get_IsUserInitiated</span></span> 

<span data-ttu-id="33cc5-146">IsUserInitiated は、新しいウィンドウ要求が、ターゲットを含むアンカータグをクリックするなど、ユーザーのジェスチャを通じて開始された場合に true になります。</span><span class="sxs-lookup"><span data-stu-id="33cc5-146">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>

> <span data-ttu-id="33cc5-147">パブリック HRESULT [get_IsUserInitiated](#get_isuserinitiated)(ブール \* isUserInitiated)</span><span class="sxs-lookup"><span data-stu-id="33cc5-147">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="33cc5-148">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="33cc5-148">GetDeferral</span></span> 

<span data-ttu-id="33cc5-149">[IWebView2Deferral](IWebView2Deferral.md)オブジェクトを取得し、イベントを遅延状態にします。</span><span class="sxs-lookup"><span data-stu-id="33cc5-149">Obtain an [IWebView2Deferral](IWebView2Deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="33cc5-150">パブリック HRESULT [Getdeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) \* \* 延期)</span><span class="sxs-lookup"><span data-stu-id="33cc5-150">public HRESULT [GetDeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="33cc5-151">[IWebView2Deferral](IWebView2Deferral.md)オブジェクトを使って、後でウィンドウを開く要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="33cc5-151">You can use the [IWebView2Deferral](IWebView2Deferral.md) object to complete the window open request at a later time.</span></span> <span data-ttu-id="33cc5-152">このイベントが延期されている間、opener window は、ウィンドウから切り離されたウィンドウに WindowProxy を返します。これは、延期が完了すると移動します。</span><span class="sxs-lookup"><span data-stu-id="33cc5-152">While this event is deferred the opener window will be returned a WindowProxy to an unnavigated window, which will navigate when the deferral is complete.</span></span>

