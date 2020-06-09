---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 2b9ad09fd347a6719523213e5ebc13d9000d536b
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697708"
---
# <span data-ttu-id="e0927-104">WebView2 クラス (CoreWebView2Controller クラス)</span><span class="sxs-lookup"><span data-stu-id="e0927-104">Microsoft.Web.WebView2.Core.CoreWebView2Controller class</span></span> 

> [!NOTE]
> <span data-ttu-id="e0927-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e0927-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="e0927-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0927-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="e0927-107">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="e0927-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="e0927-108">"WebView2" アセンブリを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0927-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="e0927-109">このクラスは、CoreWebView2 オブジェクトの所有者であり、ウィンドウ化やコンポジションに関連する、サイズ変更、表示/非表示、フォーカス、およびその他の機能のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="e0927-109">This class is the owner of the CoreWebView2 object, and provides support for resizing, showing and hiding, focusing, and other functionality related to windowing and composition.</span></span>

## <span data-ttu-id="e0927-110">まとめ</span><span class="sxs-lookup"><span data-stu-id="e0927-110">Summary</span></span>

 <span data-ttu-id="e0927-111">Members</span><span class="sxs-lookup"><span data-stu-id="e0927-111">Members</span></span>                        | <span data-ttu-id="e0927-112">説明</span><span class="sxs-lookup"><span data-stu-id="e0927-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e0927-113">AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="e0927-113">AcceleratorKeyPressed</span></span>](#acceleratorkeypressed) | <span data-ttu-id="e0927-114">AcceleratorKeyPressed は、WebView がフォーカスされているときに、アクセスキーまたはキーコンボが押されたとき、または離されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="e0927-114">AcceleratorKeyPressed fires when an accelerator key or key combo is pressed or released while the WebView is focused.</span></span>
[<span data-ttu-id="e0927-115">範囲</span><span class="sxs-lookup"><span data-stu-id="e0927-115">Bounds</span></span>](#bounds) | <span data-ttu-id="e0927-116">Webview の境界。</span><span class="sxs-lookup"><span data-stu-id="e0927-116">The webview bounds.</span></span>
[<span data-ttu-id="e0927-117">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="e0927-117">CoreWebView2</span></span>](#corewebview2) | <span data-ttu-id="e0927-118">この CoreWebView2Controller に関連付けられている CoreWebView2 を取得します。</span><span class="sxs-lookup"><span data-stu-id="e0927-118">Gets the CoreWebView2 associated with this CoreWebView2Controller.</span></span>
[<span data-ttu-id="e0927-119">GotFocus</span><span class="sxs-lookup"><span data-stu-id="e0927-119">GotFocus</span></span>](#gotfocus) | <span data-ttu-id="e0927-120">GotFocus は、WebView がフォーカスを取得したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="e0927-120">GotFocus fires when WebView got focus.</span></span>
[<span data-ttu-id="e0927-121">IsVisible</span><span class="sxs-lookup"><span data-stu-id="e0927-121">IsVisible</span></span>](#isvisible) | <span data-ttu-id="e0927-122">IsVisible プロパティは、webview の表示と非表示を切り替えるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e0927-122">The IsVisible property determines whether to show or hide the webview.</span></span>
[<span data-ttu-id="e0927-123">LostFocus</span><span class="sxs-lookup"><span data-stu-id="e0927-123">LostFocus</span></span>](#lostfocus) | <span data-ttu-id="e0927-124">このとき、WebView はフォーカスを失ったときに発生します。</span><span class="sxs-lookup"><span data-stu-id="e0927-124">LostFocus fires when WebView lost focus.</span></span>
[<span data-ttu-id="e0927-125">MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="e0927-125">MoveFocusRequested</span></span>](#movefocusrequested) | <span data-ttu-id="e0927-126">MoveFocusRequested は、ユーザーが WebView から tab キーを移動しようとしたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="e0927-126">MoveFocusRequested fires when user tries to tab out of the WebView.</span></span>
[<span data-ttu-id="e0927-127">ParentWindow</span><span class="sxs-lookup"><span data-stu-id="e0927-127">ParentWindow</span></span>](#parentwindow) | <span data-ttu-id="e0927-128">この WebView がコンテンツのレンダリングに使用しているアプリによって提供される親ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="e0927-128">The parent window provided by the app that this WebView is using to render content.</span></span>
[<span data-ttu-id="e0927-129">ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="e0927-129">ZoomFactor</span></span>](#zoomfactor) | <span data-ttu-id="e0927-130">WebView のズームファクター。</span><span class="sxs-lookup"><span data-stu-id="e0927-130">The zoom factor for the WebView.</span></span>
[<span data-ttu-id="e0927-131">ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="e0927-131">ZoomFactorChanged</span></span>](#zoomfactorchanged) | <span data-ttu-id="e0927-132">WebView の ZoomFactor プロパティが変更されると、イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="e0927-132">The event fires when the ZoomFactor property of the WebView changes.</span></span>
[<span data-ttu-id="e0927-133">Close</span><span class="sxs-lookup"><span data-stu-id="e0927-133">Close</span></span>](#close) | <span data-ttu-id="e0927-134">WebView を閉じ、基になるブラウザーインスタンスをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="e0927-134">Closes the WebView and cleans up the underlying browser instance.</span></span>
[<span data-ttu-id="e0927-135">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="e0927-135">MoveFocus</span></span>](#movefocus) | <span data-ttu-id="e0927-136">WebView にフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="e0927-136">Move focus into WebView.</span></span>
[<span data-ttu-id="e0927-137">NotifyParentWindowPositionChanged</span><span class="sxs-lookup"><span data-stu-id="e0927-137">NotifyParentWindowPositionChanged</span></span>](#notifyparentwindowpositionchanged) | <span data-ttu-id="e0927-138">これは、その親 (または任意の先祖) の HWND が移動されたことを WebView に示す境界とは別の通知です。</span><span class="sxs-lookup"><span data-stu-id="e0927-138">This is a notification separate from Bounds that tells WebView its parent (or any ancestor) HWND moved.</span></span>
[<span data-ttu-id="e0927-139">SetBoundsAndZoomFactor</span><span class="sxs-lookup"><span data-stu-id="e0927-139">SetBoundsAndZoomFactor</span></span>](#setboundsandzoomfactor) | <span data-ttu-id="e0927-140">同時に境界と ZoomFactor のプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="e0927-140">Update Bounds and ZoomFactor properties at the same time.</span></span>

<span data-ttu-id="e0927-141">CoreWebView2Controller は CoreWebView2 を所有しており、CoreWebView2Controller へのすべての参照が終了した場合、WebView は閉じられます。</span><span class="sxs-lookup"><span data-stu-id="e0927-141">The CoreWebView2Controller owns the CoreWebView2, and if all references to the CoreWebView2Controller go away, the WebView will be closed.</span></span>

## <span data-ttu-id="e0927-142">Members</span><span class="sxs-lookup"><span data-stu-id="e0927-142">Members</span></span>

#### <span data-ttu-id="e0927-143">AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="e0927-143">AcceleratorKeyPressed</span></span> 

<span data-ttu-id="e0927-144">AcceleratorKeyPressed は、WebView がフォーカスされているときに、アクセスキーまたはキーコンボが押されたとき、または離されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="e0927-144">AcceleratorKeyPressed fires when an accelerator key or key combo is pressed or released while the WebView is focused.</span></span>

> <span data-ttu-id="e0927-145">パブリックイベント EventHandler< [CoreWebView2AcceleratorKeyPressedEventArgs](microsoft-web-webview2-core-corewebview2acceleratorkeypressedeventargs.md)  >  [AcceleratorKeyPressed](#acceleratorkeypressed)</span><span class="sxs-lookup"><span data-stu-id="e0927-145">public event EventHandler< [CoreWebView2AcceleratorKeyPressedEventArgs](microsoft-web-webview2-core-corewebview2acceleratorkeypressedeventargs.md) > [AcceleratorKeyPressed](#acceleratorkeypressed)</span></span>

<span data-ttu-id="e0927-146">AcceleratorKeyPressed は、WebView がフォーカスされているときに、アクセスキーまたはキーコンボが押されたとき、または離されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="e0927-146">AcceleratorKeyPressed fires when an accelerator key or key combo is pressed or released while the WebView is focused.</span></span> <span data-ttu-id="e0927-147">次のいずれかの場合、キーはアクセラレータと見なされます。</span><span class="sxs-lookup"><span data-stu-id="e0927-147">A key is considered an accelerator if either:</span></span>

1. <span data-ttu-id="e0927-148">Ctrl または Alt は現在保留中か</span><span class="sxs-lookup"><span data-stu-id="e0927-148">Ctrl or Alt is currently being held, or</span></span>

1. <span data-ttu-id="e0927-149">押されたキーは文字にマップされません。</span><span class="sxs-lookup"><span data-stu-id="e0927-149">the pressed key does not map to a character.</span></span> <span data-ttu-id="e0927-150">一部の特定のキーは、Shift などのアクセラレータとは見なされません。</span><span class="sxs-lookup"><span data-stu-id="e0927-150">A few specific keys are never considered accelerators, such as Shift.</span></span> <span data-ttu-id="e0927-151">Escape キーは、常にアクセラレータと見なされます。</span><span class="sxs-lookup"><span data-stu-id="e0927-151">The Escape key is always considered an accelerator.</span></span>

<span data-ttu-id="e0927-152">キーを押したままにした場合に発生する自動実行のキーイベントも、このイベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="e0927-152">Autorepeated key events caused by holding the key down will also fire this event.</span></span> <span data-ttu-id="e0927-153">これらをフィルター処理するには、イベント引数 ' KeyEventLParam または PhysicalKeyStatus を確認します。</span><span class="sxs-lookup"><span data-stu-id="e0927-153">You can filter these out by checking the event args' KeyEventLParam or PhysicalKeyStatus.</span></span>

<span data-ttu-id="e0927-154">ウィンドウモードでは、このイベントハンドラーが同期的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e0927-154">In windowed mode, this event handler is called synchronously.</span></span> <span data-ttu-id="e0927-155">イベント引数に対して Handle () を呼び出すか、イベントハンドラーから制御が返されるまで、ブラウザープロセスはブロックされ、プロセス間の COM 通話の送信は RPC_E_CANTCALLOUT_ININPUTSYNCCALL で失敗します。</span><span class="sxs-lookup"><span data-stu-id="e0927-155">Until you call Handle() on the event args or the event handler returns, the browser process will be blocked and outgoing cross-process COM calls will fail with RPC_E_CANTCALLOUT_ININPUTSYNCCALL.</span></span> <span data-ttu-id="e0927-156">ただし、すべての CoreWebView2 API メソッドが動作します。</span><span class="sxs-lookup"><span data-stu-id="e0927-156">All CoreWebView2 API methods will work, however.</span></span>

<span data-ttu-id="e0927-157">ウィンドウレスモードでは、イベントハンドラーは非同期的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e0927-157">In windowless mode, the event handler is called asynchronously.</span></span> <span data-ttu-id="e0927-158">さらに入力は、イベントハンドラーから制御が返されるかハンドル () が呼び出されるまで、ブラウザーには届きませんが、ブラウザープロセス自体はブロックされず、送信 COM 呼び出しは正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="e0927-158">Further input will not reach the browser until the event handler returns or Handle() is called, but the browser process itself will not be blocked, and outgoing COM calls will work normally.</span></span>

<span data-ttu-id="e0927-159">ショートカットキーを処理する必要があることがわかっている場合は、最初にハンドル (TRUE) を呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e0927-159">It is recommended to call Handle(TRUE) as early as you can know that you want to handle the accelerator key.</span></span>

#### <span data-ttu-id="e0927-160">範囲</span><span class="sxs-lookup"><span data-stu-id="e0927-160">Bounds</span></span> 

<span data-ttu-id="e0927-161">Webview の境界。</span><span class="sxs-lookup"><span data-stu-id="e0927-161">The webview bounds.</span></span>

> <span data-ttu-id="e0927-162">パブリック四角形の[境界](#bounds)</span><span class="sxs-lookup"><span data-stu-id="e0927-162">public Rect [Bounds](#bounds)</span></span>

<span data-ttu-id="e0927-163">境界は親 HWND を基準としています。</span><span class="sxs-lookup"><span data-stu-id="e0927-163">Bounds are relative to the parent HWND.</span></span> <span data-ttu-id="e0927-164">アプリには、WebView を配置する2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="e0927-164">The app has two ways it can position a WebView:</span></span>

1. <span data-ttu-id="e0927-165">WebView 親 HWND である子 HWND を作成します。</span><span class="sxs-lookup"><span data-stu-id="e0927-165">Create a child HWND that is the WebView parent HWND.</span></span> <span data-ttu-id="e0927-166">WebView が必要な場所にこのウィンドウを配置します。</span><span class="sxs-lookup"><span data-stu-id="e0927-166">Position this window where the WebView should be.</span></span> <span data-ttu-id="e0927-167">この場合、(0, 0) を使用して、WebView の Bound の左上隅 (offset) にします。</span><span class="sxs-lookup"><span data-stu-id="e0927-167">In this case, use (0, 0) for the WebView's Bound's top left corner (the offset).</span></span>

1. <span data-ttu-id="e0927-168">アプリの一番上のウィンドウは、WebView 親 HWND として使います。</span><span class="sxs-lookup"><span data-stu-id="e0927-168">Use the app's top most window as the WebView parent HWND.</span></span> <span data-ttu-id="e0927-169">Webview の左上隅を、アプリ内で適切に配置されるように設定します。</span><span class="sxs-lookup"><span data-stu-id="e0927-169">Set the WebView's Bound's top left corner so that the WebView is positioned correctly in the app.</span></span> <span data-ttu-id="e0927-170">バインドされた値は、ホストの座標空間にあります。</span><span class="sxs-lookup"><span data-stu-id="e0927-170">The Bound's values are in the host's coordinate space.</span></span>

#### <span data-ttu-id="e0927-171">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="e0927-171">CoreWebView2</span></span> 

<span data-ttu-id="e0927-172">この CoreWebView2Controller に関連付けられている CoreWebView2 を取得します。</span><span class="sxs-lookup"><span data-stu-id="e0927-172">Gets the CoreWebView2 associated with this CoreWebView2Controller.</span></span>

> <span data-ttu-id="e0927-173">パブリック[CoreWebView2](microsoft-web-webview2-core-corewebview2.md) [CoreWebView2](#corewebview2)</span><span class="sxs-lookup"><span data-stu-id="e0927-173">public [CoreWebView2](microsoft-web-webview2-core-corewebview2.md) [CoreWebView2](#corewebview2)</span></span>

#### <span data-ttu-id="e0927-174">GotFocus</span><span class="sxs-lookup"><span data-stu-id="e0927-174">GotFocus</span></span> 

<span data-ttu-id="e0927-175">GotFocus は、WebView がフォーカスを取得したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="e0927-175">GotFocus fires when WebView got focus.</span></span>

> <span data-ttu-id="e0927-176">パブリックイベントハンドラー< オブジェクト > [GotFocus](#gotfocus)</span><span class="sxs-lookup"><span data-stu-id="e0927-176">public event EventHandler< object > [GotFocus](#gotfocus)</span></span>

#### <span data-ttu-id="e0927-177">IsVisible</span><span class="sxs-lookup"><span data-stu-id="e0927-177">IsVisible</span></span> 

<span data-ttu-id="e0927-178">IsVisible プロパティは、webview の表示と非表示を切り替えるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e0927-178">The IsVisible property determines whether to show or hide the webview.</span></span>

> <span data-ttu-id="e0927-179">public bool [IsVisible](#isvisible)</span><span class="sxs-lookup"><span data-stu-id="e0927-179">public bool [IsVisible](#isvisible)</span></span>

<span data-ttu-id="e0927-180">IsVisible が false に設定されている場合、webview は透過的であり、表示されません。</span><span class="sxs-lookup"><span data-stu-id="e0927-180">If IsVisible is set to false, the webview will be transparent and will not be rendered.</span></span> <span data-ttu-id="e0927-181">ただし、この操作を行っても、webview (CreateCoreWebView2Controller に渡された HWND パラメーター) が含まれているウィンドウは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="e0927-181">However, this will not affect the window containing the webview (the HWND parameter that was passed to CreateCoreWebView2Controller).</span></span> <span data-ttu-id="e0927-182">ウィンドウを非表示にする場合は、IsVisible プロパティを変更するだけでなく、直接 ShowWindow を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e0927-182">If you want that window to disappear too, call ShowWindow on it directly in addition to modifying the IsVisible property.</span></span> <span data-ttu-id="e0927-183">子ウィンドウとして WebView を実行しても、上のウィンドウを最小化または復元したときにウィンドウメッセージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="e0927-183">WebView as a child window won't get window messages when the top window is minimized or restored.</span></span> <span data-ttu-id="e0927-184">パフォーマンスを向上させるために、アプリのウィンドウを最小化して、アプリウィンドウが復元されたときに true に戻す場合は、WebView の IsVisible プロパティを false に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0927-184">For performance reason, developer should set IsVisible property of the WebView to false when the app window is minimized and back to true when app window is restored.</span></span> <span data-ttu-id="e0927-185">アプリウィンドウでは、WM_SYSCOMMAND メッセージを受信したときに SC_MINIMIZE と SC_RESTORE コマンドを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="e0927-185">App window can do this by handling SC_MINIMIZE and SC_RESTORE command upon receiving WM_SYSCOMMAND message.</span></span>

#### <span data-ttu-id="e0927-186">LostFocus</span><span class="sxs-lookup"><span data-stu-id="e0927-186">LostFocus</span></span> 

<span data-ttu-id="e0927-187">このとき、WebView はフォーカスを失ったときに発生します。</span><span class="sxs-lookup"><span data-stu-id="e0927-187">LostFocus fires when WebView lost focus.</span></span>

> <span data-ttu-id="e0927-188">パブリックイベント EventHandler< オブジェクト > [LostFocus](#lostfocus)</span><span class="sxs-lookup"><span data-stu-id="e0927-188">public event EventHandler< object > [LostFocus](#lostfocus)</span></span>

<span data-ttu-id="e0927-189">MoveFocusRequested イベントが発生した場合は、MoveFocusRequested イベントが発生したときに、フォーカスはまだ WebView に残っています。</span><span class="sxs-lookup"><span data-stu-id="e0927-189">In the case where MoveFocusRequested event is fired, the focus is still on WebView when MoveFocusRequested event fires.</span></span> <span data-ttu-id="e0927-190">フォーカスが失われたのは、アプリのコードが、または MoveFocusRequested イベントを WebView から離した場合にのみ、後で発生します。</span><span class="sxs-lookup"><span data-stu-id="e0927-190">Lost focus only fires afterwards when app's code or default action of MoveFocusRequested event set focus away from WebView.</span></span>

#### <span data-ttu-id="e0927-191">MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="e0927-191">MoveFocusRequested</span></span> 

<span data-ttu-id="e0927-192">MoveFocusRequested は、ユーザーが WebView から tab キーを移動しようとしたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="e0927-192">MoveFocusRequested fires when user tries to tab out of the WebView.</span></span>

> <span data-ttu-id="e0927-193">パブリックイベント EventHandler< [CoreWebView2MoveFocusRequestedEventArgs](microsoft-web-webview2-core-corewebview2movefocusrequestedeventargs.md)  >  [movefocusrequested](#movefocusrequested)</span><span class="sxs-lookup"><span data-stu-id="e0927-193">public event EventHandler< [CoreWebView2MoveFocusRequestedEventArgs](microsoft-web-webview2-core-corewebview2movefocusrequestedeventargs.md) > [MoveFocusRequested](#movefocusrequested)</span></span>

<span data-ttu-id="e0927-194">このイベントが発生すると、WebView のフォーカスが変更されません。</span><span class="sxs-lookup"><span data-stu-id="e0927-194">The WebView's focus has not changed when this event is fired.</span></span>

#### <span data-ttu-id="e0927-195">ParentWindow</span><span class="sxs-lookup"><span data-stu-id="e0927-195">ParentWindow</span></span> 

<span data-ttu-id="e0927-196">この WebView がコンテンツのレンダリングに使用しているアプリによって提供される親ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="e0927-196">The parent window provided by the app that this WebView is using to render content.</span></span>

> <span data-ttu-id="e0927-197">パブリック IntPtr の[親ウィンドウ](#parentwindow)</span><span class="sxs-lookup"><span data-stu-id="e0927-197">public IntPtr [ParentWindow](#parentwindow)</span></span>

<span data-ttu-id="e0927-198">プロパティを設定すると、WebView が、新しく提供されたウィンドウにウィンドウを再表示します。</span><span class="sxs-lookup"><span data-stu-id="e0927-198">Setting the property will cause the WebView to reparent its window to the newly provided window.</span></span>

#### <span data-ttu-id="e0927-199">ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="e0927-199">ZoomFactor</span></span> 

<span data-ttu-id="e0927-200">WebView のズームファクター。</span><span class="sxs-lookup"><span data-stu-id="e0927-200">The zoom factor for the WebView.</span></span>

> <span data-ttu-id="e0927-201">パブリックダブル[ZoomFactor](#zoomfactor)</span><span class="sxs-lookup"><span data-stu-id="e0927-201">public double [ZoomFactor](#zoomfactor)</span></span>

<span data-ttu-id="e0927-202">ズーム倍率を変更すると、ページレイアウトが変更される場合があることに注意して `window.innerWidth/innerHeight` ください。</span><span class="sxs-lookup"><span data-stu-id="e0927-202">Note that changing zoom factor could cause `window.innerWidth/innerHeight` and page layout to change.</span></span> <span data-ttu-id="e0927-203">ZoomFactor を呼び出して、ホストによって適用される拡大率は、WebView の新しい既定のズームになります。</span><span class="sxs-lookup"><span data-stu-id="e0927-203">A zoom factor that is applied by the host by calling ZoomFactor becomes the new default zoom for the WebView.</span></span> <span data-ttu-id="e0927-204">このズーム倍率は、ナビゲーション間で適用され、ユーザーが ctrl + 0 キーを押したときに表示されるズームファクター WebView に戻ります。</span><span class="sxs-lookup"><span data-stu-id="e0927-204">This zoom factor applies across navigations and is the zoom factor WebView is returned to when the user presses ctrl+0.</span></span> <span data-ttu-id="e0927-205">拡大率がユーザーによって変更された場合 (アプリの ZoomFactorChanged を受け取る場合)、現在のページに対してのみズームが適用されます。</span><span class="sxs-lookup"><span data-stu-id="e0927-205">When the zoom factor is changed by the user (resulting in the app receiving ZoomFactorChanged), that zoom applies only for the current page.</span></span> <span data-ttu-id="e0927-206">すべてのユーザーのズームは、現在のページに対してのみ適用され、ナビゲーションではリセットされます。</span><span class="sxs-lookup"><span data-stu-id="e0927-206">Any user applied zoom is only for the current page and is reset on a navigation.</span></span> <span data-ttu-id="e0927-207">0以下の zoomFactor を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e0927-207">Specifying a zoomFactor less than or equal to 0 is not allowed.</span></span> <span data-ttu-id="e0927-208">WebView には、内部でサポートされているズームファクター範囲もあります。</span><span class="sxs-lookup"><span data-stu-id="e0927-208">WebView also has an internal supported zoom factor range.</span></span> <span data-ttu-id="e0927-209">指定したズームファクターがその範囲外の場合は、範囲内に収まるように正規化され、実際に適用されたズームファクターに対して ZoomFactorChanged イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="e0927-209">When a specified zoom factor is out of that range, it will be normalized to be within the range, and a ZoomFactorChanged event will be fired for the real applied zoom factor.</span></span> <span data-ttu-id="e0927-210">この範囲の正規化が行われると、ZoomFactor プロパティは、ZoomFactor プロパティの前の変更時に指定されたズーム率を報告します。これは、webview が正規化されたズームファクターを適用した後に ZoomFactorChanged イベントが受信されるまでです。</span><span class="sxs-lookup"><span data-stu-id="e0927-210">When this range normalization happens, the ZoomFactor property will report the zoom factor specified during the previous modification of the ZoomFactor property until the ZoomFactorChanged event is received after webview applies the normalized zoom factor.</span></span>

#### <span data-ttu-id="e0927-211">ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="e0927-211">ZoomFactorChanged</span></span> 

<span data-ttu-id="e0927-212">WebView の ZoomFactor プロパティが変更されると、イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="e0927-212">The event fires when the ZoomFactor property of the WebView changes.</span></span>

> <span data-ttu-id="e0927-213">public イベント EventHandler< object > [ZoomFactorChanged](#zoomfactorchanged)</span><span class="sxs-lookup"><span data-stu-id="e0927-213">public event EventHandler< object > [ZoomFactorChanged](#zoomfactorchanged)</span></span>

<span data-ttu-id="e0927-214">呼び出し元が ZoomFactor プロパティを変更したか、ユーザーが手動でズームを変更したために、イベントが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e0927-214">The event could fire because the caller modified the ZoomFactor property, or due to the user manually modifying the zoom.</span></span> <span data-ttu-id="e0927-215">ZoomFactor プロパティを使用して呼び出し元によって変更された場合、内部のズームファクターはすぐに更新され、ZoomFactorChanged イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="e0927-215">When it is modified by the caller via the ZoomFactor property, the internal zoom factor is updated immediately and there will be no ZoomFactorChanged event.</span></span> <span data-ttu-id="e0927-216">WebView は、各サイトで使用されている直前の拡大率を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="e0927-216">WebView associates the last used zoom factor for each site.</span></span> <span data-ttu-id="e0927-217">そのため、別のページに移動するときにズーム倍率が変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e0927-217">Therefore, it is possible for the zoom factor to change when navigating to a different page.</span></span> <span data-ttu-id="e0927-218">このため、ズームファクターが変更された場合、ZoomFactorChanged イベントは ContentLoading イベントの直後に発生します。</span><span class="sxs-lookup"><span data-stu-id="e0927-218">When the zoom factor changes due to this, the ZoomFactorChanged event fires right after the ContentLoading event.</span></span>

#### <span data-ttu-id="e0927-219">Close</span><span class="sxs-lookup"><span data-stu-id="e0927-219">Close</span></span> 

<span data-ttu-id="e0927-220">WebView を閉じ、基になるブラウザーインスタンスをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="e0927-220">Closes the WebView and cleans up the underlying browser instance.</span></span>

> <span data-ttu-id="e0927-221">パブリックの void [Close](#close)()</span><span class="sxs-lookup"><span data-stu-id="e0927-221">public void [Close](#close)()</span></span>

<span data-ttu-id="e0927-222">ブラウザインスタンスをクリーンアップすると、WebView を電源にしているリソースが解放されます。</span><span class="sxs-lookup"><span data-stu-id="e0927-222">Cleaning up the browser instance will release the resources powering the WebView.</span></span> <span data-ttu-id="e0927-223">他の WebViews が使用していない場合は、ブラウザーインスタンスがシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="e0927-223">The browser instance will be shut down if there are no other WebViews using it.</span></span>

<span data-ttu-id="e0927-224">Close を呼び出した後、すべてのメソッド呼び出しは失敗し、イベントハンドラーは発生しなくなります。</span><span class="sxs-lookup"><span data-stu-id="e0927-224">After calling Close, all method calls will fail and event handlers will stop firing.</span></span> <span data-ttu-id="e0927-225">具体的には、WebView が呼び出されたときに、WebView はそのイベントハンドラーへの参照を解放します。</span><span class="sxs-lookup"><span data-stu-id="e0927-225">Specifically, the WebView will release its references to its event handlers when Close is called.</span></span>

<span data-ttu-id="e0927-226">Close は、CoreWebView2Controller が最終的な参照を失い、destructed である場合に、暗黙的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e0927-226">Close is implicitly called when the CoreWebView2Controller loses its final reference and is destructed.</span></span> <span data-ttu-id="e0927-227">ただし、WebView とアプリコードの間の参照が誤って循環しないように、明示的に Close を呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e0927-227">But it is best practice to explicitly call Close to avoid any accidental cycle of references between the WebView and the app code.</span></span> <span data-ttu-id="e0927-228">具体的には、イベントハンドラーで WebView への参照をキャプチャすると、WebView とイベントハンドラーの間に参照サイクルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e0927-228">Specifically, if you capture a reference to the WebView in an event handler you will create a reference cycle between the WebView and the event handler.</span></span> <span data-ttu-id="e0927-229">Close を呼び出すと、すべてのイベントハンドラーが解放され、このサイクルが停止します。</span><span class="sxs-lookup"><span data-stu-id="e0927-229">Calling Close will break this cycle by releasing all event handlers.</span></span> <span data-ttu-id="e0927-230">ただし、このような状況を回避するには、WebView を明示的に呼び出すと共に、webview への参照をキャプチャせずに、webview を正しくクリーンアップできるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e0927-230">But to avoid this situation it is best practice both to explicitly call Close on the WebView and to not capture a reference to the WebView to ensure the WebView can be cleaned up correctly.</span></span>

#### <span data-ttu-id="e0927-231">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="e0927-231">MoveFocus</span></span> 

<span data-ttu-id="e0927-232">WebView にフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="e0927-232">Move focus into WebView.</span></span>

> <span data-ttu-id="e0927-233">パブリック void [MoveFocus](#movefocus)([CoreWebView2MoveFocusReason](./namespace-microsoft-web-webview2-core.md)の理由)</span><span class="sxs-lookup"><span data-stu-id="e0927-233">public void [MoveFocus](#movefocus)([CoreWebView2MoveFocusReason](./namespace-microsoft-web-webview2-core.md) reason)</span></span>

<span data-ttu-id="e0927-234">WebView はフォーカスを取得し、WebView でホストされているページ内の対応する要素にフォーカスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="e0927-234">WebView will get focus and focus will be set to correspondent element in the page hosted in the WebView.</span></span> <span data-ttu-id="e0927-235">プログラム的な理由により、フォーカスは前にフォーカスされた要素、または、前にフォーカスされている要素がない場合は既定の要素に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e0927-235">For Programmatic reason, focus is set to previously focused element or the default element if there is no previously focused element.</span></span> <span data-ttu-id="e0927-236">次の理由から、フォーカスは最初の要素に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e0927-236">For Next reason, focus is set to the first element.</span></span> <span data-ttu-id="e0927-237">前の理由から、フォーカスは最後の要素に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e0927-237">For Previous reason, focus is set to the last element.</span></span> <span data-ttu-id="e0927-238">また、WebView または Tab キーをクリックするなど、ユーザーの操作によってフォーカスを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="e0927-238">WebView can also got focus through user interaction like clicking into WebView or Tab into it.</span></span> <span data-ttu-id="e0927-239">Tab キーを押した場合は、次のタブと shift キーを押しながら tab キーを押すと、[次へ] または [前のページ] を使用して MoveFocus を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="e0927-239">For tabbing, the app can call MoveFocus with Next or Previous to align with tab and shift+tab respectively when it decides the WebView is the next tabbable element.</span></span> <span data-ttu-id="e0927-240">または、アプリがメッセージループの一部として IsDialogMessage を呼び出して、プラットフォームがタブを自動処理できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e0927-240">Or, the app can call IsDialogMessage as part of its message loop to allow the platform to auto handle tabbing.</span></span> <span data-ttu-id="e0927-241">プラットフォームは、すべてのウィンドウを通じて WS_TABSTOP で回転します。</span><span class="sxs-lookup"><span data-stu-id="e0927-241">The platform will rotate through all windows with WS_TABSTOP.</span></span> <span data-ttu-id="e0927-242">WebView が IsDialogMessage からフォーカスを取得すると、tab と shift + tab の最初または最後の要素にフォーカスが内部的に配置されます。</span><span class="sxs-lookup"><span data-stu-id="e0927-242">When the WebView gets focus from IsDialogMessage, it will internally put the focus on the first or last element for tab and shift+tab respectively.</span></span>

#### <span data-ttu-id="e0927-243">NotifyParentWindowPositionChanged</span><span class="sxs-lookup"><span data-stu-id="e0927-243">NotifyParentWindowPositionChanged</span></span> 

<span data-ttu-id="e0927-244">これは、その親 (または任意の先祖) の HWND が移動されたことを WebView に示す境界とは別の通知です。</span><span class="sxs-lookup"><span data-stu-id="e0927-244">This is a notification separate from Bounds that tells WebView its parent (or any ancestor) HWND moved.</span></span>

> <span data-ttu-id="e0927-245">パブリック void [NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged)()</span><span class="sxs-lookup"><span data-stu-id="e0927-245">public void [NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged)()</span></span>

<span data-ttu-id="e0927-246">これは、アクセシビリティと、WebView の特定のダイアログで正常に動作するために必要です。</span><span class="sxs-lookup"><span data-stu-id="e0927-246">This is needed for accessibility and certain dialogs in WebView to work correctly.</span></span>

#### <span data-ttu-id="e0927-247">SetBoundsAndZoomFactor</span><span class="sxs-lookup"><span data-stu-id="e0927-247">SetBoundsAndZoomFactor</span></span> 

<span data-ttu-id="e0927-248">同時に境界と ZoomFactor のプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="e0927-248">Update Bounds and ZoomFactor properties at the same time.</span></span>

> <span data-ttu-id="e0927-249">パブリック void [SetBoundsAndZoomFactor](#setboundsandzoomfactor)(Rect 境界、double ZoomFactor)</span><span class="sxs-lookup"><span data-stu-id="e0927-249">public void [SetBoundsAndZoomFactor](#setboundsandzoomfactor)(Rect Bounds, double ZoomFactor)</span></span>

<span data-ttu-id="e0927-250">この操作は、ホストの観点からはアトミックです。</span><span class="sxs-lookup"><span data-stu-id="e0927-250">This operation is atomic from the host's perspective.</span></span> <span data-ttu-id="e0927-251">この関数から戻ると、関数が正常に終了した場合は、境界プロパティと ZoomFactor プロパティの両方が更新されます。または、関数が失敗した場合にも更新されません。</span><span class="sxs-lookup"><span data-stu-id="e0927-251">After returning from this function, the Bounds and ZoomFactor properties will have both been updated if the function is successful, or neither will be updated if the function fails.</span></span> <span data-ttu-id="e0927-252">境界と ZoomFactor の両方が同じ目盛で更新されている場合 (つまり、境界と ZoomFactor の両方が2倍)、ページには、ウィンドウ内の変更が表示されません。その場合は、中間レンダリングを使わずに、コンテンツが新しいサイズとズームでレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="e0927-252">If Bounds and ZoomFactor are both updated by the same scale (i.e. Bounds and ZoomFactor are both doubled), then the page will not see a change in window.innerWidth/innerHeight and the WebView will render the content at the new size and zoom without intermediate renderings.</span></span> <span data-ttu-id="e0927-253">この関数は、ZoomFactor または境界の1つだけを更新するためにも使うことができ、一方の値と他方の値の新しい値を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="e0927-253">This function can also be used to update just one of ZoomFactor or Bounds by passing in the new value for one and the current value for the other.</span></span>

