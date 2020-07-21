---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 (CoreWebView2Controller の場合)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 50c84a725e9f399fa31b4f78a019556bd3147bcb
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885101"
---
# <span data-ttu-id="dc1a8-104">0.9.515 クラスの WebView2 クラス (CoreWebView2Controller)</span><span class="sxs-lookup"><span data-stu-id="dc1a8-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2Controller class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="dc1a8-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="dc1a8-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="dc1a8-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="dc1a8-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="dc1a8-107">このクラスは、CoreWebView2 オブジェクトの所有者であり、ウィンドウ化やコンポジションに関連する、サイズ変更、表示/非表示、フォーカス、およびその他の機能のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-107">This class is the owner of the CoreWebView2 object, and provides support for resizing, showing and hiding, focusing, and other functionality related to windowing and composition.</span></span>

## <span data-ttu-id="dc1a8-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="dc1a8-108">Summary</span></span>

 <span data-ttu-id="dc1a8-109">Members</span><span class="sxs-lookup"><span data-stu-id="dc1a8-109">Members</span></span>                        | <span data-ttu-id="dc1a8-110">説明</span><span class="sxs-lookup"><span data-stu-id="dc1a8-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="dc1a8-111">AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="dc1a8-111">AcceleratorKeyPressed</span></span>](#acceleratorkeypressed) | <span data-ttu-id="dc1a8-112">AcceleratorKeyPressed は、WebView がフォーカスされているときに、アクセスキーまたはキーコンボが押されたとき、または離されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-112">AcceleratorKeyPressed fires when an accelerator key or key combo is pressed or released while the WebView is focused.</span></span>
[<span data-ttu-id="dc1a8-113">範囲</span><span class="sxs-lookup"><span data-stu-id="dc1a8-113">Bounds</span></span>](#bounds) | <span data-ttu-id="dc1a8-114">Webview の境界。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-114">The webview bounds.</span></span>
[<span data-ttu-id="dc1a8-115">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="dc1a8-115">CoreWebView2</span></span>](#corewebview2) | <span data-ttu-id="dc1a8-116">この CoreWebView2Controller に関連付けられている CoreWebView2 を取得します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-116">Gets the CoreWebView2 associated with this CoreWebView2Controller.</span></span>
[<span data-ttu-id="dc1a8-117">GotFocus</span><span class="sxs-lookup"><span data-stu-id="dc1a8-117">GotFocus</span></span>](#gotfocus) | <span data-ttu-id="dc1a8-118">GotFocus は、WebView がフォーカスを取得したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-118">GotFocus fires when WebView got focus.</span></span>
[<span data-ttu-id="dc1a8-119">IsVisible</span><span class="sxs-lookup"><span data-stu-id="dc1a8-119">IsVisible</span></span>](#isvisible) | <span data-ttu-id="dc1a8-120">IsVisible プロパティは、webview の表示と非表示を切り替えるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-120">The IsVisible property determines whether to show or hide the webview.</span></span>
[<span data-ttu-id="dc1a8-121">LostFocus</span><span class="sxs-lookup"><span data-stu-id="dc1a8-121">LostFocus</span></span>](#lostfocus) | <span data-ttu-id="dc1a8-122">このとき、WebView はフォーカスを失ったときに発生します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-122">LostFocus fires when WebView lost focus.</span></span>
[<span data-ttu-id="dc1a8-123">MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="dc1a8-123">MoveFocusRequested</span></span>](#movefocusrequested) | <span data-ttu-id="dc1a8-124">MoveFocusRequested は、ユーザーが WebView から tab キーを移動しようとしたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-124">MoveFocusRequested fires when user tries to tab out of the WebView.</span></span>
[<span data-ttu-id="dc1a8-125">ParentWindow</span><span class="sxs-lookup"><span data-stu-id="dc1a8-125">ParentWindow</span></span>](#parentwindow) | <span data-ttu-id="dc1a8-126">この WebView がコンテンツのレンダリングに使用しているアプリによって提供される親ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-126">The parent window provided by the app that this WebView is using to render content.</span></span>
[<span data-ttu-id="dc1a8-127">ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="dc1a8-127">ZoomFactor</span></span>](#zoomfactor) | <span data-ttu-id="dc1a8-128">WebView のズームファクター。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-128">The zoom factor for the WebView.</span></span>
[<span data-ttu-id="dc1a8-129">ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="dc1a8-129">ZoomFactorChanged</span></span>](#zoomfactorchanged) | <span data-ttu-id="dc1a8-130">WebView の ZoomFactor プロパティが変更されると、イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-130">The event fires when the ZoomFactor property of the WebView changes.</span></span>
[<span data-ttu-id="dc1a8-131">Close</span><span class="sxs-lookup"><span data-stu-id="dc1a8-131">Close</span></span>](#close) | <span data-ttu-id="dc1a8-132">WebView を閉じ、基になるブラウザーインスタンスをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-132">Closes the WebView and cleans up the underlying browser instance.</span></span>
[<span data-ttu-id="dc1a8-133">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="dc1a8-133">MoveFocus</span></span>](#movefocus) | <span data-ttu-id="dc1a8-134">WebView にフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-134">Move focus into WebView.</span></span>
[<span data-ttu-id="dc1a8-135">NotifyParentWindowPositionChanged</span><span class="sxs-lookup"><span data-stu-id="dc1a8-135">NotifyParentWindowPositionChanged</span></span>](#notifyparentwindowpositionchanged) | <span data-ttu-id="dc1a8-136">これは、その親 (または任意の先祖) の HWND が移動されたことを WebView に示す境界とは別の通知です。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-136">This is a notification separate from Bounds that tells WebView its parent (or any ancestor) HWND moved.</span></span>
[<span data-ttu-id="dc1a8-137">SetBoundsAndZoomFactor</span><span class="sxs-lookup"><span data-stu-id="dc1a8-137">SetBoundsAndZoomFactor</span></span>](#setboundsandzoomfactor) | <span data-ttu-id="dc1a8-138">同時に境界と ZoomFactor のプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-138">Update Bounds and ZoomFactor properties at the same time.</span></span>

<span data-ttu-id="dc1a8-139">CoreWebView2Controller は CoreWebView2 を所有しており、CoreWebView2Controller へのすべての参照が終了した場合、WebView は閉じられます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-139">The CoreWebView2Controller owns the CoreWebView2, and if all references to the CoreWebView2Controller go away, the WebView will be closed.</span></span>

## <span data-ttu-id="dc1a8-140">Members</span><span class="sxs-lookup"><span data-stu-id="dc1a8-140">Members</span></span>

#### <span data-ttu-id="dc1a8-141">AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="dc1a8-141">AcceleratorKeyPressed</span></span> 

<span data-ttu-id="dc1a8-142">AcceleratorKeyPressed は、WebView がフォーカスされているときに、アクセスキーまたはキーコンボが押されたとき、または離されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-142">AcceleratorKeyPressed fires when an accelerator key or key combo is pressed or released while the WebView is focused.</span></span>

> <span data-ttu-id="dc1a8-143">パブリックイベント EventHandler< [CoreWebView2AcceleratorKeyPressedEventArgs](microsoft-web-webview2-core-corewebview2acceleratorkeypressedeventargs.md)  >  [AcceleratorKeyPressed](#acceleratorkeypressed)</span><span class="sxs-lookup"><span data-stu-id="dc1a8-143">public event EventHandler< [CoreWebView2AcceleratorKeyPressedEventArgs](microsoft-web-webview2-core-corewebview2acceleratorkeypressedeventargs.md) > [AcceleratorKeyPressed](#acceleratorkeypressed)</span></span>

<span data-ttu-id="dc1a8-144">AcceleratorKeyPressed は、WebView がフォーカスされているときに、アクセスキーまたはキーコンボが押されたとき、または離されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-144">AcceleratorKeyPressed fires when an accelerator key or key combo is pressed or released while the WebView is focused.</span></span> <span data-ttu-id="dc1a8-145">次のいずれかの場合、キーはアクセラレータと見なされます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-145">A key is considered an accelerator if either:</span></span>

1. <span data-ttu-id="dc1a8-146">Ctrl または Alt は現在保留中か</span><span class="sxs-lookup"><span data-stu-id="dc1a8-146">Ctrl or Alt is currently being held, or</span></span>

1. <span data-ttu-id="dc1a8-147">押されたキーは文字にマップされません。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-147">the pressed key does not map to a character.</span></span> <span data-ttu-id="dc1a8-148">一部の特定のキーは、Shift などのアクセラレータとは見なされません。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-148">A few specific keys are never considered accelerators, such as Shift.</span></span> <span data-ttu-id="dc1a8-149">Escape キーは、常にアクセラレータと見なされます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-149">The Escape key is always considered an accelerator.</span></span>

<span data-ttu-id="dc1a8-150">キーを押したままにした場合に発生する自動実行のキーイベントも、このイベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-150">Autorepeated key events caused by holding the key down will also fire this event.</span></span> <span data-ttu-id="dc1a8-151">これらをフィルター処理するには、イベント引数 ' KeyEventLParam または PhysicalKeyStatus を確認します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-151">You can filter these out by checking the event args' KeyEventLParam or PhysicalKeyStatus.</span></span>

<span data-ttu-id="dc1a8-152">ウィンドウモードでは、このイベントハンドラーが同期的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-152">In windowed mode, this event handler is called synchronously.</span></span> <span data-ttu-id="dc1a8-153">イベント引数に対して Handle () を呼び出すか、イベントハンドラーから制御が返されるまで、ブラウザープロセスはブロックされ、プロセス間の COM 通話の送信は RPC_E_CANTCALLOUT_ININPUTSYNCCALL で失敗します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-153">Until you call Handle() on the event args or the event handler returns, the browser process will be blocked and outgoing cross-process COM calls will fail with RPC_E_CANTCALLOUT_ININPUTSYNCCALL.</span></span> <span data-ttu-id="dc1a8-154">ただし、すべての CoreWebView2 API メソッドが動作します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-154">All CoreWebView2 API methods will work, however.</span></span>

<span data-ttu-id="dc1a8-155">ウィンドウレスモードでは、イベントハンドラーは非同期的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-155">In windowless mode, the event handler is called asynchronously.</span></span> <span data-ttu-id="dc1a8-156">さらに入力は、イベントハンドラーから制御が返されるかハンドル () が呼び出されるまで、ブラウザーには届きませんが、ブラウザープロセス自体はブロックされず、送信 COM 呼び出しは正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-156">Further input will not reach the browser until the event handler returns or Handle() is called, but the browser process itself will not be blocked, and outgoing COM calls will work normally.</span></span>

<span data-ttu-id="dc1a8-157">ショートカットキーを処理する必要があることがわかっている場合は、最初にハンドル (TRUE) を呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-157">It is recommended to call Handle(TRUE) as early as you can know that you want to handle the accelerator key.</span></span>

#### <span data-ttu-id="dc1a8-158">範囲</span><span class="sxs-lookup"><span data-stu-id="dc1a8-158">Bounds</span></span> 

<span data-ttu-id="dc1a8-159">Webview の境界。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-159">The webview bounds.</span></span>

> <span data-ttu-id="dc1a8-160">パブリック四角形の[境界](#bounds)</span><span class="sxs-lookup"><span data-stu-id="dc1a8-160">public Rect [Bounds](#bounds)</span></span>

<span data-ttu-id="dc1a8-161">境界は親 HWND を基準としています。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-161">Bounds are relative to the parent HWND.</span></span> <span data-ttu-id="dc1a8-162">アプリには、WebView を配置する2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-162">The app has two ways it can position a WebView:</span></span>

1. <span data-ttu-id="dc1a8-163">WebView 親 HWND である子 HWND を作成します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-163">Create a child HWND that is the WebView parent HWND.</span></span> <span data-ttu-id="dc1a8-164">WebView が必要な場所にこのウィンドウを配置します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-164">Position this window where the WebView should be.</span></span> <span data-ttu-id="dc1a8-165">この場合、(0, 0) を使用して、WebView の Bound の左上隅 (offset) にします。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-165">In this case, use (0, 0) for the WebView's Bound's top left corner (the offset).</span></span>

1. <span data-ttu-id="dc1a8-166">アプリの一番上のウィンドウは、WebView 親 HWND として使います。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-166">Use the app's top most window as the WebView parent HWND.</span></span> <span data-ttu-id="dc1a8-167">Webview の左上隅を、アプリ内で適切に配置されるように設定します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-167">Set the WebView's Bound's top left corner so that the WebView is positioned correctly in the app.</span></span> <span data-ttu-id="dc1a8-168">バインドされた値は、ホストの座標空間にあります。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-168">The Bound's values are in the host's coordinate space.</span></span>

#### <span data-ttu-id="dc1a8-169">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="dc1a8-169">CoreWebView2</span></span> 

<span data-ttu-id="dc1a8-170">この CoreWebView2Controller に関連付けられている CoreWebView2 を取得します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-170">Gets the CoreWebView2 associated with this CoreWebView2Controller.</span></span>

> <span data-ttu-id="dc1a8-171">パブリック[CoreWebView2](microsoft-web-webview2-core-corewebview2.md) [CoreWebView2](#corewebview2)</span><span class="sxs-lookup"><span data-stu-id="dc1a8-171">public [CoreWebView2](microsoft-web-webview2-core-corewebview2.md) [CoreWebView2](#corewebview2)</span></span>

#### <span data-ttu-id="dc1a8-172">GotFocus</span><span class="sxs-lookup"><span data-stu-id="dc1a8-172">GotFocus</span></span> 

<span data-ttu-id="dc1a8-173">GotFocus は、WebView がフォーカスを取得したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-173">GotFocus fires when WebView got focus.</span></span>

> <span data-ttu-id="dc1a8-174">パブリックイベントハンドラー< オブジェクト > [GotFocus](#gotfocus)</span><span class="sxs-lookup"><span data-stu-id="dc1a8-174">public event EventHandler< object > [GotFocus](#gotfocus)</span></span>

#### <span data-ttu-id="dc1a8-175">IsVisible</span><span class="sxs-lookup"><span data-stu-id="dc1a8-175">IsVisible</span></span> 

<span data-ttu-id="dc1a8-176">IsVisible プロパティは、webview の表示と非表示を切り替えるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-176">The IsVisible property determines whether to show or hide the webview.</span></span>

> <span data-ttu-id="dc1a8-177">public bool [IsVisible](#isvisible)</span><span class="sxs-lookup"><span data-stu-id="dc1a8-177">public bool [IsVisible](#isvisible)</span></span>

<span data-ttu-id="dc1a8-178">IsVisible が false に設定されている場合、webview は透過的であり、表示されません。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-178">If IsVisible is set to false, the webview will be transparent and will not be rendered.</span></span> <span data-ttu-id="dc1a8-179">ただし、この操作を行っても、webview (CreateCoreWebView2Controller に渡された HWND パラメーター) が含まれているウィンドウは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-179">However, this will not affect the window containing the webview (the HWND parameter that was passed to CreateCoreWebView2Controller).</span></span> <span data-ttu-id="dc1a8-180">ウィンドウを非表示にする場合は、IsVisible プロパティを変更するだけでなく、直接 ShowWindow を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-180">If you want that window to disappear too, call ShowWindow on it directly in addition to modifying the IsVisible property.</span></span> <span data-ttu-id="dc1a8-181">子ウィンドウとして WebView を実行しても、上のウィンドウを最小化または復元したときにウィンドウメッセージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-181">WebView as a child window won't get window messages when the top window is minimized or restored.</span></span> <span data-ttu-id="dc1a8-182">パフォーマンスを向上させるために、アプリのウィンドウを最小化して、アプリウィンドウが復元されたときに true に戻す場合は、WebView の IsVisible プロパティを false に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-182">For performance reason, developer should set IsVisible property of the WebView to false when the app window is minimized and back to true when app window is restored.</span></span> <span data-ttu-id="dc1a8-183">アプリウィンドウでは、WM_SYSCOMMAND メッセージを受信したときに SC_MINIMIZE と SC_RESTORE コマンドを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-183">App window can do this by handling SC_MINIMIZE and SC_RESTORE command upon receiving WM_SYSCOMMAND message.</span></span>

#### <span data-ttu-id="dc1a8-184">LostFocus</span><span class="sxs-lookup"><span data-stu-id="dc1a8-184">LostFocus</span></span> 

<span data-ttu-id="dc1a8-185">このとき、WebView はフォーカスを失ったときに発生します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-185">LostFocus fires when WebView lost focus.</span></span>

> <span data-ttu-id="dc1a8-186">パブリックイベント EventHandler< オブジェクト > [LostFocus](#lostfocus)</span><span class="sxs-lookup"><span data-stu-id="dc1a8-186">public event EventHandler< object > [LostFocus](#lostfocus)</span></span>

<span data-ttu-id="dc1a8-187">MoveFocusRequested イベントが発生した場合は、MoveFocusRequested イベントが発生したときに、フォーカスはまだ WebView に残っています。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-187">In the case where MoveFocusRequested event is fired, the focus is still on WebView when MoveFocusRequested event fires.</span></span> <span data-ttu-id="dc1a8-188">フォーカスが失われたのは、アプリのコードが、または MoveFocusRequested イベントを WebView から離した場合にのみ、後で発生します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-188">Lost focus only fires afterwards when app's code or default action of MoveFocusRequested event set focus away from WebView.</span></span>

#### <span data-ttu-id="dc1a8-189">MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="dc1a8-189">MoveFocusRequested</span></span> 

<span data-ttu-id="dc1a8-190">MoveFocusRequested は、ユーザーが WebView から tab キーを移動しようとしたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-190">MoveFocusRequested fires when user tries to tab out of the WebView.</span></span>

> <span data-ttu-id="dc1a8-191">パブリックイベント EventHandler< [CoreWebView2MoveFocusRequestedEventArgs](microsoft-web-webview2-core-corewebview2movefocusrequestedeventargs.md)  >  [movefocusrequested](#movefocusrequested)</span><span class="sxs-lookup"><span data-stu-id="dc1a8-191">public event EventHandler< [CoreWebView2MoveFocusRequestedEventArgs](microsoft-web-webview2-core-corewebview2movefocusrequestedeventargs.md) > [MoveFocusRequested](#movefocusrequested)</span></span>

<span data-ttu-id="dc1a8-192">このイベントが発生すると、WebView のフォーカスが変更されません。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-192">The WebView's focus has not changed when this event is fired.</span></span>

#### <span data-ttu-id="dc1a8-193">ParentWindow</span><span class="sxs-lookup"><span data-stu-id="dc1a8-193">ParentWindow</span></span> 

<span data-ttu-id="dc1a8-194">この WebView がコンテンツのレンダリングに使用しているアプリによって提供される親ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-194">The parent window provided by the app that this WebView is using to render content.</span></span>

> <span data-ttu-id="dc1a8-195">パブリック IntPtr の[親ウィンドウ](#parentwindow)</span><span class="sxs-lookup"><span data-stu-id="dc1a8-195">public IntPtr [ParentWindow](#parentwindow)</span></span>

<span data-ttu-id="dc1a8-196">プロパティを設定すると、WebView が、新しく提供されたウィンドウにウィンドウを再表示します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-196">Setting the property will cause the WebView to reparent its window to the newly provided window.</span></span>

#### <span data-ttu-id="dc1a8-197">ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="dc1a8-197">ZoomFactor</span></span> 

<span data-ttu-id="dc1a8-198">WebView のズームファクター。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-198">The zoom factor for the WebView.</span></span>

> <span data-ttu-id="dc1a8-199">パブリックダブル[ZoomFactor](#zoomfactor)</span><span class="sxs-lookup"><span data-stu-id="dc1a8-199">public double [ZoomFactor](#zoomfactor)</span></span>

<span data-ttu-id="dc1a8-200">ズーム倍率を変更すると、ページレイアウトが変更される場合があることに注意して `window.innerWidth/innerHeight` ください。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-200">Note that changing zoom factor could cause `window.innerWidth/innerHeight` and page layout to change.</span></span> <span data-ttu-id="dc1a8-201">ZoomFactor を呼び出して、ホストによって適用される拡大率は、WebView の新しい既定のズームになります。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-201">A zoom factor that is applied by the host by calling ZoomFactor becomes the new default zoom for the WebView.</span></span> <span data-ttu-id="dc1a8-202">このズーム倍率は、ナビゲーション間で適用され、ユーザーが ctrl + 0 キーを押したときに表示されるズームファクター WebView に戻ります。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-202">This zoom factor applies across navigations and is the zoom factor WebView is returned to when the user presses ctrl+0.</span></span> <span data-ttu-id="dc1a8-203">拡大率がユーザーによって変更された場合 (アプリの ZoomFactorChanged を受け取る場合)、現在のページに対してのみズームが適用されます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-203">When the zoom factor is changed by the user (resulting in the app receiving ZoomFactorChanged), that zoom applies only for the current page.</span></span> <span data-ttu-id="dc1a8-204">すべてのユーザーのズームは、現在のページに対してのみ適用され、ナビゲーションではリセットされます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-204">Any user applied zoom is only for the current page and is reset on a navigation.</span></span> <span data-ttu-id="dc1a8-205">0以下の zoomFactor を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-205">Specifying a zoomFactor less than or equal to 0 is not allowed.</span></span> <span data-ttu-id="dc1a8-206">WebView には、内部でサポートされているズームファクター範囲もあります。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-206">WebView also has an internal supported zoom factor range.</span></span> <span data-ttu-id="dc1a8-207">指定したズームファクターがその範囲外の場合は、範囲内に収まるように正規化され、実際に適用されたズームファクターに対して ZoomFactorChanged イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-207">When a specified zoom factor is out of that range, it will be normalized to be within the range, and a ZoomFactorChanged event will be fired for the real applied zoom factor.</span></span> <span data-ttu-id="dc1a8-208">この範囲の正規化が行われると、ZoomFactor プロパティは、ZoomFactor プロパティの前の変更時に指定されたズーム率を報告します。これは、webview が正規化されたズームファクターを適用した後に ZoomFactorChanged イベントが受信されるまでです。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-208">When this range normalization happens, the ZoomFactor property will report the zoom factor specified during the previous modification of the ZoomFactor property until the ZoomFactorChanged event is received after webview applies the normalized zoom factor.</span></span>

#### <span data-ttu-id="dc1a8-209">ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="dc1a8-209">ZoomFactorChanged</span></span> 

<span data-ttu-id="dc1a8-210">WebView の ZoomFactor プロパティが変更されると、イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-210">The event fires when the ZoomFactor property of the WebView changes.</span></span>

> <span data-ttu-id="dc1a8-211">public イベント EventHandler< object > [ZoomFactorChanged](#zoomfactorchanged)</span><span class="sxs-lookup"><span data-stu-id="dc1a8-211">public event EventHandler< object > [ZoomFactorChanged](#zoomfactorchanged)</span></span>

<span data-ttu-id="dc1a8-212">呼び出し元が ZoomFactor プロパティを変更したか、ユーザーが手動でズームを変更したために、イベントが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-212">The event could fire because the caller modified the ZoomFactor property, or due to the user manually modifying the zoom.</span></span> <span data-ttu-id="dc1a8-213">ZoomFactor プロパティを使用して呼び出し元によって変更された場合、内部のズームファクターはすぐに更新され、ZoomFactorChanged イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-213">When it is modified by the caller via the ZoomFactor property, the internal zoom factor is updated immediately and there will be no ZoomFactorChanged event.</span></span> <span data-ttu-id="dc1a8-214">WebView は、各サイトで使用されている直前の拡大率を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-214">WebView associates the last used zoom factor for each site.</span></span> <span data-ttu-id="dc1a8-215">そのため、別のページに移動するときにズーム倍率が変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-215">Therefore, it is possible for the zoom factor to change when navigating to a different page.</span></span> <span data-ttu-id="dc1a8-216">このため、ズームファクターが変更された場合、ZoomFactorChanged イベントは ContentLoading イベントの直後に発生します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-216">When the zoom factor changes due to this, the ZoomFactorChanged event fires right after the ContentLoading event.</span></span>

#### <span data-ttu-id="dc1a8-217">Close</span><span class="sxs-lookup"><span data-stu-id="dc1a8-217">Close</span></span> 

<span data-ttu-id="dc1a8-218">WebView を閉じ、基になるブラウザーインスタンスをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-218">Closes the WebView and cleans up the underlying browser instance.</span></span>

> <span data-ttu-id="dc1a8-219">パブリックの void [Close](#close)()</span><span class="sxs-lookup"><span data-stu-id="dc1a8-219">public void [Close](#close)()</span></span>

<span data-ttu-id="dc1a8-220">ブラウザインスタンスをクリーンアップすると、WebView を電源にしているリソースが解放されます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-220">Cleaning up the browser instance will release the resources powering the WebView.</span></span> <span data-ttu-id="dc1a8-221">他の WebViews が使用していない場合は、ブラウザーインスタンスがシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-221">The browser instance will be shut down if there are no other WebViews using it.</span></span>

<span data-ttu-id="dc1a8-222">Close を呼び出した後、すべてのメソッド呼び出しは失敗し、イベントハンドラーは発生しなくなります。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-222">After calling Close, all method calls will fail and event handlers will stop firing.</span></span> <span data-ttu-id="dc1a8-223">具体的には、WebView が呼び出されたときに、WebView はそのイベントハンドラーへの参照を解放します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-223">Specifically, the WebView will release its references to its event handlers when Close is called.</span></span>

<span data-ttu-id="dc1a8-224">Close は、CoreWebView2Controller が最終的な参照を失い、destructed である場合に、暗黙的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-224">Close is implicitly called when the CoreWebView2Controller loses its final reference and is destructed.</span></span> <span data-ttu-id="dc1a8-225">ただし、WebView とアプリコードの間の参照が誤って循環しないように、明示的に Close を呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-225">But it is best practice to explicitly call Close to avoid any accidental cycle of references between the WebView and the app code.</span></span> <span data-ttu-id="dc1a8-226">具体的には、イベントハンドラーで WebView への参照をキャプチャすると、WebView とイベントハンドラーの間に参照サイクルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-226">Specifically, if you capture a reference to the WebView in an event handler you will create a reference cycle between the WebView and the event handler.</span></span> <span data-ttu-id="dc1a8-227">Close を呼び出すと、すべてのイベントハンドラーが解放され、このサイクルが停止します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-227">Calling Close will break this cycle by releasing all event handlers.</span></span> <span data-ttu-id="dc1a8-228">ただし、このような状況を回避するには、WebView を明示的に呼び出すと共に、webview への参照をキャプチャせずに、webview を正しくクリーンアップできるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-228">But to avoid this situation it is best practice both to explicitly call Close on the WebView and to not capture a reference to the WebView to ensure the WebView can be cleaned up correctly.</span></span>

#### <span data-ttu-id="dc1a8-229">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="dc1a8-229">MoveFocus</span></span> 

<span data-ttu-id="dc1a8-230">WebView にフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-230">Move focus into WebView.</span></span>

> <span data-ttu-id="dc1a8-231">パブリック void [MoveFocus](#movefocus)([CoreWebView2MoveFocusReason](./namespace-microsoft-web-webview2-core.md)の理由)</span><span class="sxs-lookup"><span data-stu-id="dc1a8-231">public void [MoveFocus](#movefocus)([CoreWebView2MoveFocusReason](./namespace-microsoft-web-webview2-core.md) reason)</span></span>

<span data-ttu-id="dc1a8-232">WebView はフォーカスを取得し、WebView でホストされているページ内の対応する要素にフォーカスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-232">WebView will get focus and focus will be set to correspondent element in the page hosted in the WebView.</span></span> <span data-ttu-id="dc1a8-233">プログラム的な理由により、フォーカスは前にフォーカスされた要素、または、前にフォーカスされている要素がない場合は既定の要素に設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-233">For Programmatic reason, focus is set to previously focused element or the default element if there is no previously focused element.</span></span> <span data-ttu-id="dc1a8-234">次の理由から、フォーカスは最初の要素に設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-234">For Next reason, focus is set to the first element.</span></span> <span data-ttu-id="dc1a8-235">前の理由から、フォーカスは最後の要素に設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-235">For Previous reason, focus is set to the last element.</span></span> <span data-ttu-id="dc1a8-236">また、WebView または Tab キーをクリックするなど、ユーザーの操作によってフォーカスを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-236">WebView can also got focus through user interaction like clicking into WebView or Tab into it.</span></span> <span data-ttu-id="dc1a8-237">Tab キーを押した場合は、次のタブと shift キーを押しながら tab キーを押すと、[次へ] または [前のページ] を使用して MoveFocus を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-237">For tabbing, the app can call MoveFocus with Next or Previous to align with tab and shift+tab respectively when it decides the WebView is the next tabbable element.</span></span> <span data-ttu-id="dc1a8-238">または、アプリがメッセージループの一部として IsDialogMessage を呼び出して、プラットフォームがタブを自動処理できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-238">Or, the app can call IsDialogMessage as part of its message loop to allow the platform to auto handle tabbing.</span></span> <span data-ttu-id="dc1a8-239">プラットフォームは、すべてのウィンドウを通じて WS_TABSTOP で回転します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-239">The platform will rotate through all windows with WS_TABSTOP.</span></span> <span data-ttu-id="dc1a8-240">WebView が IsDialogMessage からフォーカスを取得すると、tab と shift + tab の最初または最後の要素にフォーカスが内部的に配置されます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-240">When the WebView gets focus from IsDialogMessage, it will internally put the focus on the first or last element for tab and shift+tab respectively.</span></span>

#### <span data-ttu-id="dc1a8-241">NotifyParentWindowPositionChanged</span><span class="sxs-lookup"><span data-stu-id="dc1a8-241">NotifyParentWindowPositionChanged</span></span> 

<span data-ttu-id="dc1a8-242">これは、その親 (または任意の先祖) の HWND が移動されたことを WebView に示す境界とは別の通知です。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-242">This is a notification separate from Bounds that tells WebView its parent (or any ancestor) HWND moved.</span></span>

> <span data-ttu-id="dc1a8-243">パブリック void [NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged)()</span><span class="sxs-lookup"><span data-stu-id="dc1a8-243">public void [NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged)()</span></span>

<span data-ttu-id="dc1a8-244">これは、アクセシビリティと、WebView の特定のダイアログで正常に動作するために必要です。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-244">This is needed for accessibility and certain dialogs in WebView to work correctly.</span></span>

#### <span data-ttu-id="dc1a8-245">SetBoundsAndZoomFactor</span><span class="sxs-lookup"><span data-stu-id="dc1a8-245">SetBoundsAndZoomFactor</span></span> 

<span data-ttu-id="dc1a8-246">同時に境界と ZoomFactor のプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-246">Update Bounds and ZoomFactor properties at the same time.</span></span>

> <span data-ttu-id="dc1a8-247">パブリック void [SetBoundsAndZoomFactor](#setboundsandzoomfactor)(Rect 境界、double ZoomFactor)</span><span class="sxs-lookup"><span data-stu-id="dc1a8-247">public void [SetBoundsAndZoomFactor](#setboundsandzoomfactor)(Rect Bounds, double ZoomFactor)</span></span>

<span data-ttu-id="dc1a8-248">この操作は、ホストの観点からはアトミックです。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-248">This operation is atomic from the host's perspective.</span></span> <span data-ttu-id="dc1a8-249">この関数から戻ると、関数が正常に終了した場合は、境界プロパティと ZoomFactor プロパティの両方が更新されます。または、関数が失敗した場合にも更新されません。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-249">After returning from this function, the Bounds and ZoomFactor properties will have both been updated if the function is successful, or neither will be updated if the function fails.</span></span> <span data-ttu-id="dc1a8-250">境界と ZoomFactor の両方が同じ目盛で更新されている場合 (つまり、境界と ZoomFactor の両方が2倍)、ページには、ウィンドウ内の変更が表示されません。その場合は、中間レンダリングを使わずに、コンテンツが新しいサイズとズームでレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-250">If Bounds and ZoomFactor are both updated by the same scale (i.e. Bounds and ZoomFactor are both doubled), then the page will not see a change in window.innerWidth/innerHeight and the WebView will render the content at the new size and zoom without intermediate renderings.</span></span> <span data-ttu-id="dc1a8-251">この関数は、ZoomFactor または境界の1つだけを更新するためにも使うことができ、一方の値と他方の値の新しい値を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="dc1a8-251">This function can also be used to update just one of ZoomFactor or Bounds by passing in the new value for one and the current value for the other.</span></span>

