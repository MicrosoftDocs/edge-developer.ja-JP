---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2Controller
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 8e0f95f8346f4c4b60b6de2676503b79c743afcb
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880823"
---
# <span data-ttu-id="2b6fa-104">0.9.515-インターフェイス ICoreWebView2Controller</span><span class="sxs-lookup"><span data-stu-id="2b6fa-104">0.9.515 - interface ICoreWebView2Controller</span></span> 

> [!NOTE]
> <span data-ttu-id="2b6fa-105">この参照は、SDK バージョン0.9.515 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="2b6fa-106">最新 API リファレンスについては、 [WEBVIEW2 api リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2Controller
  : public IUnknown
```

<span data-ttu-id="2b6fa-107">このインターフェイスは、CoreWebView2 オブジェクトの所有者であり、ウィンドウ化とコンポジションに関連する、サイズ変更、表示/非表示、フォーカス、およびその他の機能のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-107">This interface is the owner of the CoreWebView2 object, and provides support for resizing, showing and hiding, focusing, and other functionality related to windowing and composition.</span></span>

## <span data-ttu-id="2b6fa-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="2b6fa-108">Summary</span></span>

 <span data-ttu-id="2b6fa-109">Members</span><span class="sxs-lookup"><span data-stu-id="2b6fa-109">Members</span></span>                        | <span data-ttu-id="2b6fa-110">説明</span><span class="sxs-lookup"><span data-stu-id="2b6fa-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2b6fa-111">add_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="2b6fa-111">add_AcceleratorKeyPressed</span></span>](#add_acceleratorkeypressed) | <span data-ttu-id="2b6fa-112">AcceleratorKeyPressed イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-112">Add an event handler for the AcceleratorKeyPressed event.</span></span>
[<span data-ttu-id="2b6fa-113">add_GotFocus</span><span class="sxs-lookup"><span data-stu-id="2b6fa-113">add_GotFocus</span></span>](#add_gotfocus) | <span data-ttu-id="2b6fa-114">GotFocus イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-114">Add an event handler for the GotFocus event.</span></span>
[<span data-ttu-id="2b6fa-115">add_LostFocus</span><span class="sxs-lookup"><span data-stu-id="2b6fa-115">add_LostFocus</span></span>](#add_lostfocus) | <span data-ttu-id="2b6fa-116">LostFocus イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-116">Add an event handler for the LostFocus event.</span></span>
[<span data-ttu-id="2b6fa-117">add_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="2b6fa-117">add_MoveFocusRequested</span></span>](#add_movefocusrequested) | <span data-ttu-id="2b6fa-118">MoveFocusRequested されたイベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-118">Add an event handler for the MoveFocusRequested event.</span></span>
[<span data-ttu-id="2b6fa-119">add_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="2b6fa-119">add_ZoomFactorChanged</span></span>](#add_zoomfactorchanged) | <span data-ttu-id="2b6fa-120">ZoomFactorChanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-120">Add an event handler for the ZoomFactorChanged event.</span></span>
[<span data-ttu-id="2b6fa-121">Close</span><span class="sxs-lookup"><span data-stu-id="2b6fa-121">Close</span></span>](#close) | <span data-ttu-id="2b6fa-122">WebView を閉じ、基になるブラウザーインスタンスをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-122">Closes the WebView and cleans up the underlying browser instance.</span></span>
[<span data-ttu-id="2b6fa-123">get_Bounds</span><span class="sxs-lookup"><span data-stu-id="2b6fa-123">get_Bounds</span></span>](#get_bounds) | <span data-ttu-id="2b6fa-124">Webview の境界。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-124">The webview bounds.</span></span>
[<span data-ttu-id="2b6fa-125">get_CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="2b6fa-125">get_CoreWebView2</span></span>](#get_corewebview2) | <span data-ttu-id="2b6fa-126">この CoreWebView2Controller に関連付けられている CoreWebView2 を取得します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-126">Gets the CoreWebView2 associated with this CoreWebView2Controller.</span></span>
[<span data-ttu-id="2b6fa-127">get_IsVisible</span><span class="sxs-lookup"><span data-stu-id="2b6fa-127">get_IsVisible</span></span>](#get_isvisible) | <span data-ttu-id="2b6fa-128">IsVisible プロパティは、webview の表示と非表示を切り替えるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-128">The IsVisible property determines whether to show or hide the webview.</span></span>
[<span data-ttu-id="2b6fa-129">get_ParentWindow</span><span class="sxs-lookup"><span data-stu-id="2b6fa-129">get_ParentWindow</span></span>](#get_parentwindow) | <span data-ttu-id="2b6fa-130">この WebView がコンテンツのレンダリングに使用しているアプリによって提供される親ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-130">The parent window provided by the app that this WebView is using to render content.</span></span>
[<span data-ttu-id="2b6fa-131">get_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="2b6fa-131">get_ZoomFactor</span></span>](#get_zoomfactor) | <span data-ttu-id="2b6fa-132">WebView のズームファクター。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-132">The zoom factor for the WebView.</span></span>
[<span data-ttu-id="2b6fa-133">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="2b6fa-133">MoveFocus</span></span>](#movefocus) | <span data-ttu-id="2b6fa-134">WebView にフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-134">Move focus into WebView.</span></span>
[<span data-ttu-id="2b6fa-135">NotifyParentWindowPositionChanged</span><span class="sxs-lookup"><span data-stu-id="2b6fa-135">NotifyParentWindowPositionChanged</span></span>](#notifyparentwindowpositionchanged) | <span data-ttu-id="2b6fa-136">これは、その親 (または任意の先祖) の HWND が移動されたことを WebView に示す境界とは別の通知です。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-136">This is a notification separate from Bounds that tells WebView its parent (or any ancestor) HWND moved.</span></span>
[<span data-ttu-id="2b6fa-137">put_Bounds</span><span class="sxs-lookup"><span data-stu-id="2b6fa-137">put_Bounds</span></span>](#put_bounds) | <span data-ttu-id="2b6fa-138">境界プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-138">Set the Bounds property.</span></span>
[<span data-ttu-id="2b6fa-139">put_IsVisible</span><span class="sxs-lookup"><span data-stu-id="2b6fa-139">put_IsVisible</span></span>](#put_isvisible) | <span data-ttu-id="2b6fa-140">IsVisible プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-140">Set the IsVisible property.</span></span>
[<span data-ttu-id="2b6fa-141">put_ParentWindow</span><span class="sxs-lookup"><span data-stu-id="2b6fa-141">put_ParentWindow</span></span>](#put_parentwindow) | <span data-ttu-id="2b6fa-142">WebView の親ウィンドウを設定します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-142">Set the parent window for the WebView.</span></span>
[<span data-ttu-id="2b6fa-143">put_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="2b6fa-143">put_ZoomFactor</span></span>](#put_zoomfactor) | <span data-ttu-id="2b6fa-144">ZoomFactor プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-144">Set the ZoomFactor property.</span></span>
[<span data-ttu-id="2b6fa-145">remove_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="2b6fa-145">remove_AcceleratorKeyPressed</span></span>](#remove_acceleratorkeypressed) | <span data-ttu-id="2b6fa-146">Add_AcceleratorKeyPressed で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-146">Remove an event handler previously added with add_AcceleratorKeyPressed.</span></span>
[<span data-ttu-id="2b6fa-147">remove_GotFocus</span><span class="sxs-lookup"><span data-stu-id="2b6fa-147">remove_GotFocus</span></span>](#remove_gotfocus) | <span data-ttu-id="2b6fa-148">Add_GotFocus で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-148">Remove an event handler previously added with add_GotFocus.</span></span>
[<span data-ttu-id="2b6fa-149">remove_LostFocus</span><span class="sxs-lookup"><span data-stu-id="2b6fa-149">remove_LostFocus</span></span>](#remove_lostfocus) | <span data-ttu-id="2b6fa-150">Add_LostFocus で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-150">Remove an event handler previously added with add_LostFocus.</span></span>
[<span data-ttu-id="2b6fa-151">remove_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="2b6fa-151">remove_MoveFocusRequested</span></span>](#remove_movefocusrequested) | <span data-ttu-id="2b6fa-152">Add_MoveFocusRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-152">Remove an event handler previously added with add_MoveFocusRequested.</span></span>
[<span data-ttu-id="2b6fa-153">remove_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="2b6fa-153">remove_ZoomFactorChanged</span></span>](#remove_zoomfactorchanged) | <span data-ttu-id="2b6fa-154">Add_ZoomFactorChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-154">Remove an event handler previously added with add_ZoomFactorChanged.</span></span>
[<span data-ttu-id="2b6fa-155">SetBoundsAndZoomFactor</span><span class="sxs-lookup"><span data-stu-id="2b6fa-155">SetBoundsAndZoomFactor</span></span>](#setboundsandzoomfactor) | <span data-ttu-id="2b6fa-156">同時に境界と ZoomFactor のプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-156">Update Bounds and ZoomFactor properties at the same time.</span></span>

<span data-ttu-id="2b6fa-157">CoreWebView2Controller は CoreWebView2 を所有しており、CoreWebView2Controller へのすべての参照が終了した場合、WebView は閉じられます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-157">The CoreWebView2Controller owns the CoreWebView2, and if all references to the CoreWebView2Controller go away, the WebView will be closed.</span></span>

## <span data-ttu-id="2b6fa-158">Members</span><span class="sxs-lookup"><span data-stu-id="2b6fa-158">Members</span></span>

#### <span data-ttu-id="2b6fa-159">add_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="2b6fa-159">add_AcceleratorKeyPressed</span></span> 

<span data-ttu-id="2b6fa-160">AcceleratorKeyPressed イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-160">Add an event handler for the AcceleratorKeyPressed event.</span></span>

> <span data-ttu-id="2b6fa-161">パブリック HRESULT [add_AcceleratorKeyPressed](#add_acceleratorkeypressed)([ICoreWebView2AcceleratorKeyPressedEventHandler](icorewebview2acceleratorkeypressedeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="2b6fa-161">public HRESULT [add_AcceleratorKeyPressed](#add_acceleratorkeypressed)([ICoreWebView2AcceleratorKeyPressedEventHandler](icorewebview2acceleratorkeypressedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="2b6fa-162">AcceleratorKeyPressed は、WebView がフォーカスされているときに、アクセスキーまたはキーコンボが押されたとき、または離されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-162">AcceleratorKeyPressed fires when an accelerator key or key combo is pressed or released while the WebView is focused.</span></span> <span data-ttu-id="2b6fa-163">次のいずれかの場合、キーはアクセラレータと見なされます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-163">A key is considered an accelerator if either:</span></span>

1. <span data-ttu-id="2b6fa-164">Ctrl または Alt は現在保留中か</span><span class="sxs-lookup"><span data-stu-id="2b6fa-164">Ctrl or Alt is currently being held, or</span></span>

1. <span data-ttu-id="2b6fa-165">押されたキーは文字にマップされません。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-165">the pressed key does not map to a character.</span></span> <span data-ttu-id="2b6fa-166">一部の特定のキーは、Shift などのアクセラレータとは見なされません。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-166">A few specific keys are never considered accelerators, such as Shift.</span></span> <span data-ttu-id="2b6fa-167">Escape キーは、常にアクセラレータと見なされます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-167">The Escape key is always considered an accelerator.</span></span>

<span data-ttu-id="2b6fa-168">キーを押したままにした場合に発生する自動実行のキーイベントも、このイベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-168">Autorepeated key events caused by holding the key down will also fire this event.</span></span> <span data-ttu-id="2b6fa-169">これらをフィルター処理するには、イベント引数 ' KeyEventLParam または PhysicalKeyStatus を確認します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-169">You can filter these out by checking the event args' KeyEventLParam or PhysicalKeyStatus.</span></span>

<span data-ttu-id="2b6fa-170">ウィンドウモードでは、このイベントハンドラーが同期的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-170">In windowed mode, this event handler is called synchronously.</span></span> <span data-ttu-id="2b6fa-171">イベント引数に対して Handle () を呼び出すか、イベントハンドラーから制御が返されるまで、ブラウザープロセスはブロックされ、プロセス間の COM 通話の送信は RPC_E_CANTCALLOUT_ININPUTSYNCCALL で失敗します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-171">Until you call Handle() on the event args or the event handler returns, the browser process will be blocked and outgoing cross-process COM calls will fail with RPC_E_CANTCALLOUT_ININPUTSYNCCALL.</span></span> <span data-ttu-id="2b6fa-172">ただし、すべての CoreWebView2 API メソッドが動作します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-172">All CoreWebView2 API methods will work, however.</span></span>

<span data-ttu-id="2b6fa-173">ウィンドウレスモードでは、イベントハンドラーは非同期的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-173">In windowless mode, the event handler is called asynchronously.</span></span> <span data-ttu-id="2b6fa-174">さらに入力は、イベントハンドラーから制御が返されるかハンドル () が呼び出されるまで、ブラウザーには届きませんが、ブラウザープロセス自体はブロックされず、送信 COM 呼び出しは正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-174">Further input will not reach the browser until the event handler returns or Handle() is called, but the browser process itself will not be blocked, and outgoing COM calls will work normally.</span></span>

<span data-ttu-id="2b6fa-175">ショートカットキーを処理する必要があることがわかっている場合は、最初にハンドル (TRUE) を呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-175">It is recommended to call Handle(TRUE) as early as you can know that you want to handle the accelerator key.</span></span>

```cpp
    // Register a handler for the AcceleratorKeyPressed event.
    CHECK_FAILURE(m_controller->add_AcceleratorKeyPressed(
        Callback<ICoreWebView2AcceleratorKeyPressedEventHandler>(
            [this](
                ICoreWebView2Controller* sender,
                ICoreWebView2AcceleratorKeyPressedEventArgs* args) -> HRESULT {
                COREWEBVIEW2_KEY_EVENT_KIND kind;
                CHECK_FAILURE(args->get_KeyEventKind(&kind));
                // We only care about key down events.
                if (kind == COREWEBVIEW2_KEY_EVENT_KIND_KEY_DOWN ||
                    kind == COREWEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_DOWN)
                {
                    UINT key;
                    CHECK_FAILURE(args->get_VirtualKey(&key));
                    // Check if the key is one we want to handle.
                    if (std::function<void()> action =
                            m_appWindow->GetAcceleratorKeyFunction(key))
                    {
                        // Keep the browser from handling this key, whether it's autorepeated or
                        // not.
                        CHECK_FAILURE(args->put_Handled(TRUE));

                        // Filter out autorepeated keys.
                        COREWEBVIEW2_PHYSICAL_KEY_STATUS status;
                        CHECK_FAILURE(args->get_PhysicalKeyStatus(&status));
                        if (!status.WasKeyDown)
                        {
                            // Perform the action asynchronously to avoid blocking the
                            // browser process's event queue.
                            m_appWindow->RunAsync(action);
                        }
                    }
                }
                return S_OK;
            })
            .Get(),
        &m_acceleratorKeyPressedToken));
```

#### <span data-ttu-id="2b6fa-176">add_GotFocus</span><span class="sxs-lookup"><span data-stu-id="2b6fa-176">add_GotFocus</span></span> 

<span data-ttu-id="2b6fa-177">GotFocus イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-177">Add an event handler for the GotFocus event.</span></span>

> <span data-ttu-id="2b6fa-178">パブリック HRESULT [add_GotFocus](#add_gotfocus)([ICoreWebView2FocusChangedEventHandler](icorewebview2focuschangedeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="2b6fa-178">public HRESULT [add_GotFocus](#add_gotfocus)([ICoreWebView2FocusChangedEventHandler](icorewebview2focuschangedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="2b6fa-179">GotFocus は、WebView がフォーカスを取得したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-179">GotFocus fires when WebView got focus.</span></span>

#### <span data-ttu-id="2b6fa-180">add_LostFocus</span><span class="sxs-lookup"><span data-stu-id="2b6fa-180">add_LostFocus</span></span> 

<span data-ttu-id="2b6fa-181">LostFocus イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-181">Add an event handler for the LostFocus event.</span></span>

> <span data-ttu-id="2b6fa-182">パブリック HRESULT [add_LostFocus](#add_lostfocus)([ICoreWebView2FocusChangedEventHandler](icorewebview2focuschangedeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="2b6fa-182">public HRESULT [add_LostFocus](#add_lostfocus)([ICoreWebView2FocusChangedEventHandler](icorewebview2focuschangedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="2b6fa-183">このとき、WebView はフォーカスを失ったときに発生します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-183">LostFocus fires when WebView lost focus.</span></span> <span data-ttu-id="2b6fa-184">MoveFocusRequested イベントが発生した場合は、MoveFocusRequested イベントが発生したときに、フォーカスはまだ WebView に残っています。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-184">In the case where MoveFocusRequested event is fired, the focus is still on WebView when MoveFocusRequested event fires.</span></span> <span data-ttu-id="2b6fa-185">フォーカスが失われたのは、アプリのコードが、または MoveFocusRequested イベントを WebView から離した場合にのみ、後で発生します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-185">Lost focus only fires afterwards when app's code or default action of MoveFocusRequested event set focus away from WebView.</span></span>

#### <span data-ttu-id="2b6fa-186">add_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="2b6fa-186">add_MoveFocusRequested</span></span> 

<span data-ttu-id="2b6fa-187">MoveFocusRequested されたイベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-187">Add an event handler for the MoveFocusRequested event.</span></span>

> <span data-ttu-id="2b6fa-188">パブリック HRESULT [add_MoveFocusRequested](#add_movefocusrequested)([ICoreWebView2MoveFocusRequestedEventHandler](icorewebview2movefocusrequestedeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="2b6fa-188">public HRESULT [add_MoveFocusRequested](#add_movefocusrequested)([ICoreWebView2MoveFocusRequestedEventHandler](icorewebview2movefocusrequestedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="2b6fa-189">MoveFocusRequested は、ユーザーが WebView から tab キーを移動しようとしたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-189">MoveFocusRequested fires when user tries to tab out of the WebView.</span></span> <span data-ttu-id="2b6fa-190">このイベントが発生すると、WebView のフォーカスが変更されません。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-190">The WebView's focus has not changed when this event is fired.</span></span>

```cpp
    // Register a handler for the MoveFocusRequested event.
    // This event will be fired when the user tabs out of the webview.
    // The handler will focus another window in the app, depending on which
    // direction the focus is being shifted.
    CHECK_FAILURE(m_controller->add_MoveFocusRequested(
        Callback<ICoreWebView2MoveFocusRequestedEventHandler>(
            [this](
                ICoreWebView2Controller* sender,
                ICoreWebView2MoveFocusRequestedEventArgs* args) -> HRESULT {
                if (!g_autoTabHandle)
                {
                    COREWEBVIEW2_MOVE_FOCUS_REASON reason;
                    CHECK_FAILURE(args->get_Reason(&reason));

                    if (reason == COREWEBVIEW2_MOVE_FOCUS_REASON_NEXT)
                    {
                        TabForwards(-1);
                    }
                    else if (reason == COREWEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS)
                    {
                        TabBackwards(int(m_tabbableWindows.size()));
                    }
                    CHECK_FAILURE(args->put_Handled(TRUE));
                }
                return S_OK;
            })
            .Get(),
        &m_moveFocusRequestedToken));
```

#### <span data-ttu-id="2b6fa-191">add_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="2b6fa-191">add_ZoomFactorChanged</span></span> 

<span data-ttu-id="2b6fa-192">ZoomFactorChanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-192">Add an event handler for the ZoomFactorChanged event.</span></span>

> <span data-ttu-id="2b6fa-193">パブリック HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)([ICoreWebView2ZoomFactorChangedEventHandler](icorewebview2zoomfactorchangedeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="2b6fa-193">public HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)([ICoreWebView2ZoomFactorChangedEventHandler](icorewebview2zoomfactorchangedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="2b6fa-194">WebView の ZoomFactor プロパティが変更されると、イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-194">The event fires when the ZoomFactor property of the WebView changes.</span></span> <span data-ttu-id="2b6fa-195">呼び出し元が ZoomFactor プロパティを変更したか、ユーザーが手動でズームを変更したために、イベントが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-195">The event could fire because the caller modified the ZoomFactor property, or due to the user manually modifying the zoom.</span></span> <span data-ttu-id="2b6fa-196">ZoomFactor プロパティを使用して呼び出し元によって変更された場合、内部のズームファクターはすぐに更新され、ZoomFactorChanged イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-196">When it is modified by the caller via the ZoomFactor property, the internal zoom factor is updated immediately and there will be no ZoomFactorChanged event.</span></span> <span data-ttu-id="2b6fa-197">WebView は、各サイトで使用されている直前の拡大率を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-197">WebView associates the last used zoom factor for each site.</span></span> <span data-ttu-id="2b6fa-198">そのため、別のページに移動するときにズーム倍率が変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-198">Therefore, it is possible for the zoom factor to change when navigating to a different page.</span></span> <span data-ttu-id="2b6fa-199">このため、ズームファクターが変更された場合、ZoomFactorChanged イベントは ContentLoading イベントの直後に発生します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-199">When the zoom factor changes due to this, the ZoomFactorChanged event fires right after the ContentLoading event.</span></span>

```cpp
    // Register a handler for the ZoomFactorChanged event.
    // This handler just announces the new level of zoom on the window's title bar.
    CHECK_FAILURE(m_controller->add_ZoomFactorChanged(
        Callback<ICoreWebView2ZoomFactorChangedEventHandler>(
            [this](ICoreWebView2Controller* sender, IUnknown* args) -> HRESULT {
                double zoomFactor;
                CHECK_FAILURE(sender->get_ZoomFactor(&zoomFactor));

                std::wstring message = L"WebView2APISample (Zoom: " +
                                       std::to_wstring(int(zoomFactor * 100)) + L"%)";
                SetWindowText(m_appWindow->GetMainWindow(), message.c_str());
                return S_OK;
            })
            .Get(),
        &m_zoomFactorChangedToken));
```

#### <span data-ttu-id="2b6fa-200">Close</span><span class="sxs-lookup"><span data-stu-id="2b6fa-200">Close</span></span> 

<span data-ttu-id="2b6fa-201">WebView を閉じ、基になるブラウザーインスタンスをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-201">Closes the WebView and cleans up the underlying browser instance.</span></span>

> <span data-ttu-id="2b6fa-202">パブリック HRESULT [Close](#close)()</span><span class="sxs-lookup"><span data-stu-id="2b6fa-202">public HRESULT [Close](#close)()</span></span>

<span data-ttu-id="2b6fa-203">ブラウザインスタンスをクリーンアップすると、WebView を電源にしているリソースが解放されます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-203">Cleaning up the browser instance will release the resources powering the WebView.</span></span> <span data-ttu-id="2b6fa-204">他の WebViews が使用していない場合は、ブラウザーインスタンスがシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-204">The browser instance will be shut down if there are no other WebViews using it.</span></span>

<span data-ttu-id="2b6fa-205">Close を呼び出した後、すべてのメソッド呼び出しは失敗し、イベントハンドラーは発生しなくなります。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-205">After calling Close, all method calls will fail and event handlers will stop firing.</span></span> <span data-ttu-id="2b6fa-206">具体的には、WebView が呼び出されたときに、WebView はそのイベントハンドラーへの参照を解放します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-206">Specifically, the WebView will release its references to its event handlers when Close is called.</span></span>

<span data-ttu-id="2b6fa-207">Close は、CoreWebView2Controller が最終的な参照を失い、destructed である場合に、暗黙的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-207">Close is implicitly called when the CoreWebView2Controller loses its final reference and is destructed.</span></span> <span data-ttu-id="2b6fa-208">ただし、WebView とアプリコードの間の参照が誤って循環しないように、明示的に Close を呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-208">But it is best practice to explicitly call Close to avoid any accidental cycle of references between the WebView and the app code.</span></span> <span data-ttu-id="2b6fa-209">具体的には、イベントハンドラーで WebView への参照をキャプチャすると、WebView とイベントハンドラーの間に参照サイクルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-209">Specifically, if you capture a reference to the WebView in an event handler you will create a reference cycle between the WebView and the event handler.</span></span> <span data-ttu-id="2b6fa-210">Close を呼び出すと、すべてのイベントハンドラーが解放され、このサイクルが停止します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-210">Calling Close will break this cycle by releasing all event handlers.</span></span> <span data-ttu-id="2b6fa-211">ただし、このような状況を回避するには、WebView を明示的に呼び出すと共に、webview への参照をキャプチャせずに、webview を正しくクリーンアップできるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-211">But to avoid this situation it is best practice both to explicitly call Close on the WebView and to not capture a reference to the WebView to ensure the WebView can be cleaned up correctly.</span></span>

```cpp
// Close the WebView and deinitialize related state. This doesn't close the app window.
void AppWindow::CloseWebView(bool cleanupUserDataFolder)
{
    DeleteAllComponents();
    if (m_controller)
    {
        m_controller->Close();
        m_controller = nullptr;
        m_webView = nullptr;
    }
    m_webViewEnvironment = nullptr;
    if (cleanupUserDataFolder)
    {
        // For non-UWP apps, the default user data folder {Executable File Name}.WebView2
        // is in the same directory next to the app executable. If end
        // developers specify userDataFolder during WebView environment
        // creation, they would need to pass in that explicit value here.
        // For more information about userDataFolder:
        // https://docs.microsoft.com/microsoft-edge/hosting/webview2/reference/win32/0-9-488/webview2-idl#createwebview2environmentwithoptions
        WCHAR userDataFolder[MAX_PATH] = L"";
        // Obtain the absolute path for relative paths that include "./" or "../"
        _wfullpath(
            userDataFolder, GetLocalPath(L"WebView2APISample.exe.WebView2").c_str(), MAX_PATH);
        std::wstring userDataFolderPath(userDataFolder);

        std::wstring message = L"Are you sure you want to clean up the user data folder at\n";
        message += userDataFolderPath;
        message += L"\n?\nWarning: This action is not reversible.\n\n";
        message += L"Click No if there are other open WebView instances.\n";

        if (MessageBox(m_mainWindow, message.c_str(), L"Cleanup User Data Folder", MB_YESNO) ==
            IDYES)
        {
            CHECK_FAILURE(DeleteFileRecursive(userDataFolderPath));
        }
    }
}
```

#### <span data-ttu-id="2b6fa-212">get_Bounds</span><span class="sxs-lookup"><span data-stu-id="2b6fa-212">get_Bounds</span></span> 

<span data-ttu-id="2b6fa-213">Webview の境界。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-213">The webview bounds.</span></span>

> <span data-ttu-id="2b6fa-214">パブリック HRESULT [get_Bounds](#get_bounds)(RECT \* 境界)</span><span class="sxs-lookup"><span data-stu-id="2b6fa-214">public HRESULT [get_Bounds](#get_bounds)(RECT \* bounds)</span></span>

<span data-ttu-id="2b6fa-215">境界は親 HWND を基準としています。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-215">Bounds are relative to the parent HWND.</span></span> <span data-ttu-id="2b6fa-216">アプリには、WebView を配置する2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-216">The app has two ways it can position a WebView:</span></span>

1. <span data-ttu-id="2b6fa-217">WebView 親 HWND である子 HWND を作成します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-217">Create a child HWND that is the WebView parent HWND.</span></span> <span data-ttu-id="2b6fa-218">WebView が必要な場所にこのウィンドウを配置します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-218">Position this window where the WebView should be.</span></span> <span data-ttu-id="2b6fa-219">この場合、(0, 0) を使用して、WebView の Bound の左上隅 (offset) にします。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-219">In this case, use (0, 0) for the WebView's Bound's top left corner (the offset).</span></span>

1. <span data-ttu-id="2b6fa-220">アプリの一番上のウィンドウは、WebView 親 HWND として使います。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-220">Use the app's top most window as the WebView parent HWND.</span></span> <span data-ttu-id="2b6fa-221">Webview の左上隅を、アプリ内で適切に配置されるように設定します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-221">Set the WebView's Bound's top left corner so that the WebView is positioned correctly in the app.</span></span> <span data-ttu-id="2b6fa-222">バインドされた値は、ホストの座標空間にあります。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-222">The Bound's values are in the host's coordinate space.</span></span>

#### <span data-ttu-id="2b6fa-223">get_CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="2b6fa-223">get_CoreWebView2</span></span> 

<span data-ttu-id="2b6fa-224">この CoreWebView2Controller に関連付けられている CoreWebView2 を取得します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-224">Gets the CoreWebView2 associated with this CoreWebView2Controller.</span></span>

> <span data-ttu-id="2b6fa-225">パブリック HRESULT [get_CoreWebView2](#get_corewebview2)([ICoreWebView2](icorewebview2.md) \* \* CoreWebView2)</span><span class="sxs-lookup"><span data-stu-id="2b6fa-225">public HRESULT [get_CoreWebView2](#get_corewebview2)([ICoreWebView2](icorewebview2.md) \*\* coreWebView2)</span></span>

#### <span data-ttu-id="2b6fa-226">get_IsVisible</span><span class="sxs-lookup"><span data-stu-id="2b6fa-226">get_IsVisible</span></span> 

<span data-ttu-id="2b6fa-227">IsVisible プロパティは、webview の表示と非表示を切り替えるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-227">The IsVisible property determines whether to show or hide the webview.</span></span>

> <span data-ttu-id="2b6fa-228">パブリック HRESULT [get_IsVisible](#get_isvisible)(BOOL \* IsVisible)</span><span class="sxs-lookup"><span data-stu-id="2b6fa-228">public HRESULT [get_IsVisible](#get_isvisible)(BOOL \* isVisible)</span></span>

<span data-ttu-id="2b6fa-229">IsVisible が false に設定されている場合、webview は透過的であり、表示されません。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-229">If IsVisible is set to false, the webview will be transparent and will not be rendered.</span></span> <span data-ttu-id="2b6fa-230">ただし、この操作を行っても、webview (CreateCoreWebView2Controller に渡された HWND パラメーター) が含まれているウィンドウは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-230">However, this will not affect the window containing the webview (the HWND parameter that was passed to CreateCoreWebView2Controller).</span></span> <span data-ttu-id="2b6fa-231">ウィンドウを非表示にする場合は、IsVisible プロパティを変更するだけでなく、直接 ShowWindow を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-231">If you want that window to disappear too, call ShowWindow on it directly in addition to modifying the IsVisible property.</span></span> <span data-ttu-id="2b6fa-232">子ウィンドウとして WebView を実行しても、上のウィンドウを最小化または復元したときにウィンドウメッセージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-232">WebView as a child window won't get window messages when the top window is minimized or restored.</span></span> <span data-ttu-id="2b6fa-233">パフォーマンスを向上させるために、アプリのウィンドウを最小化して、アプリウィンドウが復元されたときに true に戻す場合は、WebView の IsVisible プロパティを false に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-233">For performance reason, developer should set IsVisible property of the WebView to false when the app window is minimized and back to true when app window is restored.</span></span> <span data-ttu-id="2b6fa-234">アプリウィンドウでは、WM_SYSCOMMAND メッセージを受信したときに SC_MINIMIZE と SC_RESTORE コマンドを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-234">App window can do this by handling SC_MINIMIZE and SC_RESTORE command upon receiving WM_SYSCOMMAND message.</span></span>

```cpp
void ViewComponent::ToggleVisibility()
{
    BOOL visible;
    m_controller->get_IsVisible(&visible);
    m_isVisible = !visible;
    m_controller->put_IsVisible(m_isVisible);
}
```

#### <span data-ttu-id="2b6fa-235">get_ParentWindow</span><span class="sxs-lookup"><span data-stu-id="2b6fa-235">get_ParentWindow</span></span> 

<span data-ttu-id="2b6fa-236">この WebView がコンテンツのレンダリングに使用しているアプリによって提供される親ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-236">The parent window provided by the app that this WebView is using to render content.</span></span>

> <span data-ttu-id="2b6fa-237">パブリック HRESULT [get_ParentWindow](#get_parentwindow)(HWND \* topLevelWindow)</span><span class="sxs-lookup"><span data-stu-id="2b6fa-237">public HRESULT [get_ParentWindow](#get_parentwindow)(HWND \* topLevelWindow)</span></span>

<span data-ttu-id="2b6fa-238">この API では、最初に CreateCoreWebView2Controller に渡されたウィンドウが返されます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-238">This API initially returns the window passed into CreateCoreWebView2Controller.</span></span>

#### <span data-ttu-id="2b6fa-239">get_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="2b6fa-239">get_ZoomFactor</span></span> 

<span data-ttu-id="2b6fa-240">WebView のズームファクター。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-240">The zoom factor for the WebView.</span></span>

> <span data-ttu-id="2b6fa-241">パブリック HRESULT [get_ZoomFactor](#get_zoomfactor)(Double \* ZoomFactor)</span><span class="sxs-lookup"><span data-stu-id="2b6fa-241">public HRESULT [get_ZoomFactor](#get_zoomfactor)(double \* zoomFactor)</span></span>

<span data-ttu-id="2b6fa-242">ズーム倍率を変更すると、ページレイアウトが変更される場合があることに注意して `window.innerWidth/innerHeight` ください。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-242">Note that changing zoom factor could cause `window.innerWidth/innerHeight` and page layout to change.</span></span> <span data-ttu-id="2b6fa-243">ZoomFactor を呼び出して、ホストによって適用される拡大率は、WebView の新しい既定のズームになります。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-243">A zoom factor that is applied by the host by calling ZoomFactor becomes the new default zoom for the WebView.</span></span> <span data-ttu-id="2b6fa-244">このズーム倍率は、ナビゲーション間で適用され、ユーザーが ctrl + 0 キーを押したときに表示されるズームファクター WebView に戻ります。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-244">This zoom factor applies across navigations and is the zoom factor WebView is returned to when the user presses ctrl+0.</span></span> <span data-ttu-id="2b6fa-245">拡大率がユーザーによって変更された場合 (アプリの ZoomFactorChanged を受け取る場合)、現在のページに対してのみズームが適用されます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-245">When the zoom factor is changed by the user (resulting in the app receiving ZoomFactorChanged), that zoom applies only for the current page.</span></span> <span data-ttu-id="2b6fa-246">すべてのユーザーのズームは、現在のページに対してのみ適用され、ナビゲーションではリセットされます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-246">Any user applied zoom is only for the current page and is reset on a navigation.</span></span> <span data-ttu-id="2b6fa-247">0以下の zoomFactor を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-247">Specifying a zoomFactor less than or equal to 0 is not allowed.</span></span> <span data-ttu-id="2b6fa-248">WebView には、内部でサポートされているズームファクター範囲もあります。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-248">WebView also has an internal supported zoom factor range.</span></span> <span data-ttu-id="2b6fa-249">指定したズームファクターがその範囲外の場合は、範囲内に収まるように正規化され、実際に適用されたズームファクターに対して ZoomFactorChanged イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-249">When a specified zoom factor is out of that range, it will be normalized to be within the range, and a ZoomFactorChanged event will be fired for the real applied zoom factor.</span></span> <span data-ttu-id="2b6fa-250">この範囲の正規化が行われると、ZoomFactor プロパティは、ZoomFactor プロパティの前の変更時に指定されたズーム率を報告します。これは、webview が正規化されたズームファクターを適用した後に ZoomFactorChanged イベントが受信されるまでです。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-250">When this range normalization happens, the ZoomFactor property will report the zoom factor specified during the previous modification of the ZoomFactor property until the ZoomFactorChanged event is received after webview applies the normalized zoom factor.</span></span>

#### <span data-ttu-id="2b6fa-251">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="2b6fa-251">MoveFocus</span></span> 

<span data-ttu-id="2b6fa-252">WebView にフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-252">Move focus into WebView.</span></span>

> <span data-ttu-id="2b6fa-253">パブリック HRESULT [MoveFocus](#movefocus)(COREWEBVIEW2_MOVE_FOCUS_REASON の理由)</span><span class="sxs-lookup"><span data-stu-id="2b6fa-253">public HRESULT [MoveFocus](#movefocus)(COREWEBVIEW2_MOVE_FOCUS_REASON reason)</span></span>

<span data-ttu-id="2b6fa-254">WebView はフォーカスを取得し、WebView でホストされているページ内の対応する要素にフォーカスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-254">WebView will get focus and focus will be set to correspondent element in the page hosted in the WebView.</span></span> <span data-ttu-id="2b6fa-255">プログラム的な理由により、フォーカスは前にフォーカスされた要素、または、前にフォーカスされている要素がない場合は既定の要素に設定されます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-255">For Programmatic reason, focus is set to previously focused element or the default element if there is no previously focused element.</span></span> <span data-ttu-id="2b6fa-256">次の理由から、フォーカスは最初の要素に設定されます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-256">For Next reason, focus is set to the first element.</span></span> <span data-ttu-id="2b6fa-257">前の理由から、フォーカスは最後の要素に設定されます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-257">For Previous reason, focus is set to the last element.</span></span> <span data-ttu-id="2b6fa-258">また、WebView または Tab キーをクリックするなど、ユーザーの操作によってフォーカスを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-258">WebView can also got focus through user interaction like clicking into WebView or Tab into it.</span></span> <span data-ttu-id="2b6fa-259">Tab キーを押した場合は、次のタブと shift キーを押しながら tab キーを押すと、[次へ] または [前のページ] を使用して MoveFocus を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-259">For tabbing, the app can call MoveFocus with Next or Previous to align with tab and shift+tab respectively when it decides the WebView is the next tabbable element.</span></span> <span data-ttu-id="2b6fa-260">または、アプリがメッセージループの一部として IsDialogMessage を呼び出して、プラットフォームがタブを自動処理できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-260">Or, the app can call IsDialogMessage as part of its message loop to allow the platform to auto handle tabbing.</span></span> <span data-ttu-id="2b6fa-261">プラットフォームは、すべてのウィンドウを通じて WS_TABSTOP で回転します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-261">The platform will rotate through all windows with WS_TABSTOP.</span></span> <span data-ttu-id="2b6fa-262">WebView が IsDialogMessage からフォーカスを取得すると、tab と shift + tab の最初または最後の要素にフォーカスが内部的に配置されます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-262">When the WebView gets focus from IsDialogMessage, it will internally put the focus on the first or last element for tab and shift+tab respectively.</span></span>

```cpp
    while (GetMessage(&msg, nullptr, 0, 0))
    {
        if (!TranslateAccelerator(msg.hwnd, hAccelTable, &msg))
        {
            // Calling IsDialogMessage handles Tab traversal automatically. If the
            // app wants the platform to auto handle tab, then call IsDialogMessage
            // before calling TranslateMessage/DispatchMessage. If the app wants to
            // handle tabbing itself, then skip calling IsDialogMessage and call
            // TranslateMessage/DispatchMessage directly.
            if (!g_autoTabHandle || !IsDialogMessage(GetAncestor(msg.hwnd, GA_ROOT), &msg))
            {
                TranslateMessage(&msg);
                DispatchMessage(&msg);
            }
        }
    }
```

```cpp
        if (wParam == VK_TAB)
        {
            // Find out if the window is one we've customized for tab handling
            for (size_t i = 0; i < m_tabbableWindows.size(); i++)
            {
                if (m_tabbableWindows[i].first == hWnd)
                {
                    if (GetKeyState(VK_SHIFT) < 0)
                    {
                        TabBackwards(i);
                    }
                    else
                    {
                        TabForwards(i);
                    }
                    return true;
                }
            }
        }
```

```cpp
void ControlComponent::TabForwards(int currentIndex)
{
    // Find first enabled window after the active one
    for (size_t i = currentIndex + 1; i < m_tabbableWindows.size(); i++)
    {
        HWND hwnd = m_tabbableWindows.at(i).first;
        if (IsWindowEnabled(hwnd))
        {
            SetFocus(hwnd);
            return;
        }
    }
    // If this is the last enabled window, tab forwards into the WebView.
    m_controller->MoveFocus(COREWEBVIEW2_MOVE_FOCUS_REASON_NEXT);
}

void ControlComponent::TabBackwards(int currentIndex)
{
    // Find first enabled window before the active one
    for (int i = currentIndex - 1; i >= 0; i--)
    {
        HWND hwnd = m_tabbableWindows.at(i).first;
        if (IsWindowEnabled(hwnd))
        {
            SetFocus(hwnd);
            return;
        }
    }
    // If this is the last enabled window, tab forwards into the WebView.
    CHECK_FAILURE(m_controller->MoveFocus(COREWEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS));
}
```

#### <span data-ttu-id="2b6fa-263">NotifyParentWindowPositionChanged</span><span class="sxs-lookup"><span data-stu-id="2b6fa-263">NotifyParentWindowPositionChanged</span></span> 

<span data-ttu-id="2b6fa-264">これは、その親 (または任意の先祖) の HWND が移動されたことを WebView に示す境界とは別の通知です。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-264">This is a notification separate from Bounds that tells WebView its parent (or any ancestor) HWND moved.</span></span>

> <span data-ttu-id="2b6fa-265">パブリック HRESULT [NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged)()</span><span class="sxs-lookup"><span data-stu-id="2b6fa-265">public HRESULT [NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged)()</span></span>

<span data-ttu-id="2b6fa-266">これは、アクセシビリティと、WebView の特定のダイアログで正常に動作するために必要です。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-266">This is needed for accessibility and certain dialogs in WebView to work correctly.</span></span> 
```cpp
    if (message == WM_MOVE || message == WM_MOVING)
    {
        m_controller->NotifyParentWindowPositionChanged();
        return true;
    }
```

#### <span data-ttu-id="2b6fa-267">put_Bounds</span><span class="sxs-lookup"><span data-stu-id="2b6fa-267">put_Bounds</span></span> 

<span data-ttu-id="2b6fa-268">境界プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-268">Set the Bounds property.</span></span>

> <span data-ttu-id="2b6fa-269">パブリック HRESULT [put_Bounds](#put_bounds)(四角形の境界)</span><span class="sxs-lookup"><span data-stu-id="2b6fa-269">public HRESULT [put_Bounds](#put_bounds)(RECT bounds)</span></span>

```cpp
// Update the bounds of the WebView window to fit available space.
void ViewComponent::ResizeWebView()
{
    SIZE webViewSize = {
            LONG((m_webViewBounds.right - m_webViewBounds.left) * m_webViewRatio * m_webViewScale),
            LONG((m_webViewBounds.bottom - m_webViewBounds.top) * m_webViewRatio * m_webViewScale) };

    RECT desiredBounds = m_webViewBounds;
    desiredBounds.bottom = LONG(
        webViewSize.cy + m_webViewBounds.top);
    desiredBounds.right = LONG(
        webViewSize.cx + m_webViewBounds.left);

    m_controller->put_Bounds(desiredBounds);
    if (m_compositionController)
    {
        POINT webViewOffset = {m_webViewBounds.left, m_webViewBounds.top};

        if (m_dcompDevice)
        {
            CHECK_FAILURE(m_dcompRootVisual->SetOffsetX(float(webViewOffset.x)));
            CHECK_FAILURE(m_dcompRootVisual->SetOffsetY(float(webViewOffset.y)));
            CHECK_FAILURE(m_dcompRootVisual->SetClip(
                {0, 0, float(webViewSize.cx), float(webViewSize.cy)}));
            CHECK_FAILURE(m_dcompDevice->Commit());
        }
        else if (m_wincompHelper)
        {
            m_wincompHelper->UpdateSizeAndPosition(webViewOffset, webViewSize);
        }
    }
}
```

#### <span data-ttu-id="2b6fa-270">put_IsVisible</span><span class="sxs-lookup"><span data-stu-id="2b6fa-270">put_IsVisible</span></span> 

<span data-ttu-id="2b6fa-271">IsVisible プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-271">Set the IsVisible property.</span></span>

> <span data-ttu-id="2b6fa-272">パブリック HRESULT [put_IsVisible](#put_isvisible)(BOOL IsVisible)</span><span class="sxs-lookup"><span data-stu-id="2b6fa-272">public HRESULT [put_IsVisible](#put_isvisible)(BOOL isVisible)</span></span>

```cpp
    if (message == WM_SYSCOMMAND)
    {
        if (wParam == SC_MINIMIZE)
        {
            // Hide the webview when the app window is minimized.
            m_controller->put_IsVisible(FALSE);
        }
        else if (wParam == SC_RESTORE)
        {
            // When the app window is restored, show the webview
            // (unless the user has toggle visibility off).
            if (m_isVisible)
            {
                m_controller->put_IsVisible(TRUE);
            }
        }
    }
```

#### <span data-ttu-id="2b6fa-273">put_ParentWindow</span><span class="sxs-lookup"><span data-stu-id="2b6fa-273">put_ParentWindow</span></span> 

<span data-ttu-id="2b6fa-274">WebView の親ウィンドウを設定します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-274">Set the parent window for the WebView.</span></span>

> <span data-ttu-id="2b6fa-275">パブリック HRESULT [put_ParentWindow](#put_parentwindow)(HWND topLevelWindow)</span><span class="sxs-lookup"><span data-stu-id="2b6fa-275">public HRESULT [put_ParentWindow](#put_parentwindow)(HWND topLevelWindow)</span></span>

<span data-ttu-id="2b6fa-276">これにより、WebView が、新しく指定したウィンドウにウィンドウを再表示します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-276">This will cause the WebView to reparent its window to the newly provided window.</span></span>

#### <span data-ttu-id="2b6fa-277">put_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="2b6fa-277">put_ZoomFactor</span></span> 

<span data-ttu-id="2b6fa-278">ZoomFactor プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-278">Set the ZoomFactor property.</span></span>

> <span data-ttu-id="2b6fa-279">パブリック HRESULT [put_ZoomFactor](#put_zoomfactor)(double ZoomFactor)</span><span class="sxs-lookup"><span data-stu-id="2b6fa-279">public HRESULT [put_ZoomFactor](#put_zoomfactor)(double zoomFactor)</span></span>

#### <span data-ttu-id="2b6fa-280">remove_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="2b6fa-280">remove_AcceleratorKeyPressed</span></span> 

<span data-ttu-id="2b6fa-281">Add_AcceleratorKeyPressed で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-281">Remove an event handler previously added with add_AcceleratorKeyPressed.</span></span>

> <span data-ttu-id="2b6fa-282">パブリック HRESULT [remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="2b6fa-282">public HRESULT [remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="2b6fa-283">remove_GotFocus</span><span class="sxs-lookup"><span data-stu-id="2b6fa-283">remove_GotFocus</span></span> 

<span data-ttu-id="2b6fa-284">Add_GotFocus で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-284">Remove an event handler previously added with add_GotFocus.</span></span>

> <span data-ttu-id="2b6fa-285">パブリック HRESULT [remove_GotFocus](#remove_gotfocus)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="2b6fa-285">public HRESULT [remove_GotFocus](#remove_gotfocus)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="2b6fa-286">remove_LostFocus</span><span class="sxs-lookup"><span data-stu-id="2b6fa-286">remove_LostFocus</span></span> 

<span data-ttu-id="2b6fa-287">Add_LostFocus で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-287">Remove an event handler previously added with add_LostFocus.</span></span>

> <span data-ttu-id="2b6fa-288">パブリック HRESULT [remove_LostFocus](#remove_lostfocus)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="2b6fa-288">public HRESULT [remove_LostFocus](#remove_lostfocus)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="2b6fa-289">remove_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="2b6fa-289">remove_MoveFocusRequested</span></span> 

<span data-ttu-id="2b6fa-290">Add_MoveFocusRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-290">Remove an event handler previously added with add_MoveFocusRequested.</span></span>

> <span data-ttu-id="2b6fa-291">パブリック HRESULT [remove_MoveFocusRequested](#remove_movefocusrequested)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="2b6fa-291">public HRESULT [remove_MoveFocusRequested](#remove_movefocusrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="2b6fa-292">remove_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="2b6fa-292">remove_ZoomFactorChanged</span></span> 

<span data-ttu-id="2b6fa-293">Add_ZoomFactorChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-293">Remove an event handler previously added with add_ZoomFactorChanged.</span></span>

> <span data-ttu-id="2b6fa-294">パブリック HRESULT [remove_ZoomFactorChanged](#remove_zoomfactorchanged)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="2b6fa-294">public HRESULT [remove_ZoomFactorChanged](#remove_zoomfactorchanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="2b6fa-295">SetBoundsAndZoomFactor</span><span class="sxs-lookup"><span data-stu-id="2b6fa-295">SetBoundsAndZoomFactor</span></span> 

<span data-ttu-id="2b6fa-296">同時に境界と ZoomFactor のプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-296">Update Bounds and ZoomFactor properties at the same time.</span></span>

> <span data-ttu-id="2b6fa-297">パブリック HRESULT [SetBoundsAndZoomFactor](#setboundsandzoomfactor)(RECT 境界、double zoomFactor)</span><span class="sxs-lookup"><span data-stu-id="2b6fa-297">public HRESULT [SetBoundsAndZoomFactor](#setboundsandzoomfactor)(RECT bounds, double zoomFactor)</span></span>

<span data-ttu-id="2b6fa-298">この操作は、ホストの観点からはアトミックです。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-298">This operation is atomic from the host's perspective.</span></span> <span data-ttu-id="2b6fa-299">この関数から戻ると、関数が正常に終了した場合は、境界プロパティと ZoomFactor プロパティの両方が更新されます。または、関数が失敗した場合にも更新されません。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-299">After returning from this function, the Bounds and ZoomFactor properties will have both been updated if the function is successful, or neither will be updated if the function fails.</span></span> <span data-ttu-id="2b6fa-300">境界と ZoomFactor の両方が同じ目盛で更新されている場合 (つまり、境界と ZoomFactor の両方が2倍)、ページには、ウィンドウ内の変更が表示されません。その場合は、中間レンダリングを使わずに、コンテンツが新しいサイズとズームでレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-300">If Bounds and ZoomFactor are both updated by the same scale (i.e. Bounds and ZoomFactor are both doubled), then the page will not see a change in window.innerWidth/innerHeight and the WebView will render the content at the new size and zoom without intermediate renderings.</span></span> <span data-ttu-id="2b6fa-301">この関数は、ZoomFactor または境界の1つだけを更新するためにも使うことができ、一方の値と他方の値の新しい値を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="2b6fa-301">This function can also be used to update just one of ZoomFactor or Bounds by passing in the new value for one and the current value for the other.</span></span>

```cpp
void ViewComponent::SetScale(float scale)
{
    RECT bounds;
    CHECK_FAILURE(m_controller->get_Bounds(&bounds));
    double scaleChange = scale / m_webViewScale;

    bounds.bottom = LONG(
        (bounds.bottom - bounds.top) * scaleChange + bounds.top);
    bounds.right = LONG(
        (bounds.right - bounds.left) * scaleChange + bounds.left);

    m_webViewScale = scale;
    m_controller->SetBoundsAndZoomFactor(bounds, scale);
}
```

