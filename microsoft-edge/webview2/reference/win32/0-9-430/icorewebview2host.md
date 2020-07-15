---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2Host
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 9202c17d83ad7d0750dbf76724b550d73ecca434
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881034"
---
# <span data-ttu-id="078e0-104">0.9.430-インターフェイス ICoreWebView2Host</span><span class="sxs-lookup"><span data-stu-id="078e0-104">0.9.430 - interface ICoreWebView2Host</span></span> 

> [!NOTE]
> <span data-ttu-id="078e0-105">このインターフェイスは、SDK バージョン0.9.430 後のリリースで変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="078e0-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="078e0-106">最新 API リファレンスについては、[リファレンス](../../../webview2-api-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="078e0-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2Host
  : public IUnknown
```

<span data-ttu-id="078e0-107">このインターフェイスは、CoreWebView2 オブジェクトの所有者であり、ウィンドウ化とコンポジションに関連する、サイズ変更、表示/非表示、フォーカス、およびその他の機能のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="078e0-107">This interface is the owner of the CoreWebView2 object, and provides support for resizing, showing and hiding, focusing, and other functionality related to windowing and composition.</span></span>

## <span data-ttu-id="078e0-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="078e0-108">Summary</span></span>

 <span data-ttu-id="078e0-109">Members</span><span class="sxs-lookup"><span data-stu-id="078e0-109">Members</span></span>                        | <span data-ttu-id="078e0-110">説明</span><span class="sxs-lookup"><span data-stu-id="078e0-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="078e0-111">get_IsVisible</span><span class="sxs-lookup"><span data-stu-id="078e0-111">get_IsVisible</span></span>](#get_isvisible) | <span data-ttu-id="078e0-112">IsVisible プロパティは、webview の表示と非表示を切り替えるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="078e0-112">The IsVisible property determines whether to show or hide the webview.</span></span>
[<span data-ttu-id="078e0-113">put_IsVisible</span><span class="sxs-lookup"><span data-stu-id="078e0-113">put_IsVisible</span></span>](#put_isvisible) | <span data-ttu-id="078e0-114">IsVisible プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="078e0-114">Set the IsVisible property.</span></span>
[<span data-ttu-id="078e0-115">get_Bounds</span><span class="sxs-lookup"><span data-stu-id="078e0-115">get_Bounds</span></span>](#get_bounds) | <span data-ttu-id="078e0-116">Webview の境界。</span><span class="sxs-lookup"><span data-stu-id="078e0-116">The webview bounds.</span></span>
[<span data-ttu-id="078e0-117">put_Bounds</span><span class="sxs-lookup"><span data-stu-id="078e0-117">put_Bounds</span></span>](#put_bounds) | <span data-ttu-id="078e0-118">境界プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="078e0-118">Set the Bounds property.</span></span>
[<span data-ttu-id="078e0-119">get_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="078e0-119">get_ZoomFactor</span></span>](#get_zoomfactor) | <span data-ttu-id="078e0-120">WebView のズームファクター。</span><span class="sxs-lookup"><span data-stu-id="078e0-120">The zoom factor for the WebView.</span></span>
[<span data-ttu-id="078e0-121">put_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="078e0-121">put_ZoomFactor</span></span>](#put_zoomfactor) | <span data-ttu-id="078e0-122">ZoomFactor プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="078e0-122">Set the ZoomFactor property.</span></span>
[<span data-ttu-id="078e0-123">add_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="078e0-123">add_ZoomFactorChanged</span></span>](#add_zoomfactorchanged) | <span data-ttu-id="078e0-124">ZoomFactorChanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="078e0-124">Add an event handler for the ZoomFactorChanged event.</span></span>
[<span data-ttu-id="078e0-125">remove_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="078e0-125">remove_ZoomFactorChanged</span></span>](#remove_zoomfactorchanged) | <span data-ttu-id="078e0-126">Add_ZoomFactorChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="078e0-126">Remove an event handler previously added with add_ZoomFactorChanged.</span></span>
[<span data-ttu-id="078e0-127">SetBoundsAndZoomFactor</span><span class="sxs-lookup"><span data-stu-id="078e0-127">SetBoundsAndZoomFactor</span></span>](#setboundsandzoomfactor) | <span data-ttu-id="078e0-128">同時に境界と ZoomFactor のプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="078e0-128">Update Bounds and ZoomFactor properties at the same time.</span></span>
[<span data-ttu-id="078e0-129">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="078e0-129">MoveFocus</span></span>](#movefocus) | <span data-ttu-id="078e0-130">WebView にフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="078e0-130">Move focus into WebView.</span></span>
[<span data-ttu-id="078e0-131">add_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="078e0-131">add_MoveFocusRequested</span></span>](#add_movefocusrequested) | <span data-ttu-id="078e0-132">MoveFocusRequested されたイベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="078e0-132">Add an event handler for the MoveFocusRequested event.</span></span>
[<span data-ttu-id="078e0-133">remove_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="078e0-133">remove_MoveFocusRequested</span></span>](#remove_movefocusrequested) | <span data-ttu-id="078e0-134">Add_MoveFocusRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="078e0-134">Remove an event handler previously added with add_MoveFocusRequested.</span></span>
[<span data-ttu-id="078e0-135">add_GotFocus</span><span class="sxs-lookup"><span data-stu-id="078e0-135">add_GotFocus</span></span>](#add_gotfocus) | <span data-ttu-id="078e0-136">GotFocus イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="078e0-136">Add an event handler for the GotFocus event.</span></span>
[<span data-ttu-id="078e0-137">remove_GotFocus</span><span class="sxs-lookup"><span data-stu-id="078e0-137">remove_GotFocus</span></span>](#remove_gotfocus) | <span data-ttu-id="078e0-138">Add_GotFocus で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="078e0-138">Remove an event handler previously added with add_GotFocus.</span></span>
[<span data-ttu-id="078e0-139">add_LostFocus</span><span class="sxs-lookup"><span data-stu-id="078e0-139">add_LostFocus</span></span>](#add_lostfocus) | <span data-ttu-id="078e0-140">LostFocus イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="078e0-140">Add an event handler for the LostFocus event.</span></span>
[<span data-ttu-id="078e0-141">remove_LostFocus</span><span class="sxs-lookup"><span data-stu-id="078e0-141">remove_LostFocus</span></span>](#remove_lostfocus) | <span data-ttu-id="078e0-142">Add_LostFocus で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="078e0-142">Remove an event handler previously added with add_LostFocus.</span></span>
[<span data-ttu-id="078e0-143">add_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="078e0-143">add_AcceleratorKeyPressed</span></span>](#add_acceleratorkeypressed) | <span data-ttu-id="078e0-144">AcceleratorKeyPressed イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="078e0-144">Add an event handler for the AcceleratorKeyPressed event.</span></span>
[<span data-ttu-id="078e0-145">remove_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="078e0-145">remove_AcceleratorKeyPressed</span></span>](#remove_acceleratorkeypressed) | <span data-ttu-id="078e0-146">Add_AcceleratorKeyPressed で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="078e0-146">Remove an event handler previously added with add_AcceleratorKeyPressed.</span></span>
[<span data-ttu-id="078e0-147">get_ParentWindow</span><span class="sxs-lookup"><span data-stu-id="078e0-147">get_ParentWindow</span></span>](#get_parentwindow) | <span data-ttu-id="078e0-148">この WebView がコンテンツのレンダリングに使用しているアプリによって提供される親ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="078e0-148">The parent window provided by the app that this WebView is using to render content.</span></span>
[<span data-ttu-id="078e0-149">put_ParentWindow</span><span class="sxs-lookup"><span data-stu-id="078e0-149">put_ParentWindow</span></span>](#put_parentwindow) | <span data-ttu-id="078e0-150">WebView の親ウィンドウを設定します。</span><span class="sxs-lookup"><span data-stu-id="078e0-150">Set the parent window for the WebView.</span></span>
[<span data-ttu-id="078e0-151">NotifyParentWindowPositionChanged</span><span class="sxs-lookup"><span data-stu-id="078e0-151">NotifyParentWindowPositionChanged</span></span>](#notifyparentwindowpositionchanged) | <span data-ttu-id="078e0-152">これは、親 (または任意の先祖) HWND を移動したことを示す put_Bounds とは別の通知です。</span><span class="sxs-lookup"><span data-stu-id="078e0-152">This is a notification separate from put_Bounds that tells WebView its parent (or any ancestor) HWND moved.</span></span>
[<span data-ttu-id="078e0-153">Close</span><span class="sxs-lookup"><span data-stu-id="078e0-153">Close</span></span>](#close) | <span data-ttu-id="078e0-154">WebView を閉じ、基になるブラウザーインスタンスをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="078e0-154">Closes the WebView and cleans up the underlying browser instance.</span></span>
[<span data-ttu-id="078e0-155">get_CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="078e0-155">get_CoreWebView2</span></span>](#get_corewebview2) | <span data-ttu-id="078e0-156">この CoreWebView2Host に関連付けられている CoreWebView2 を取得します。</span><span class="sxs-lookup"><span data-stu-id="078e0-156">Gets the CoreWebView2 associated with this CoreWebView2Host.</span></span>
[<span data-ttu-id="078e0-157">CORE_WEBVIEW2_MOVE_FOCUS_REASON</span><span class="sxs-lookup"><span data-stu-id="078e0-157">CORE_WEBVIEW2_MOVE_FOCUS_REASON</span></span>](#core_webview2_move_focus_reason) | <span data-ttu-id="078e0-158">フォーカスを移動する理由。</span><span class="sxs-lookup"><span data-stu-id="078e0-158">Reason for moving focus.</span></span>
[<span data-ttu-id="078e0-159">CORE_WEBVIEW2_KEY_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="078e0-159">CORE_WEBVIEW2_KEY_EVENT_KIND</span></span>](#core_webview2_key_event_kind) | <span data-ttu-id="078e0-160">AcceleratorKeyPressed イベントをトリガーしたキーイベントの種類です。</span><span class="sxs-lookup"><span data-stu-id="078e0-160">The type of key event that triggered an AcceleratorKeyPressed event.</span></span>
[<span data-ttu-id="078e0-161">CORE_WEBVIEW2_PHYSICAL_KEY_STATUS</span><span class="sxs-lookup"><span data-stu-id="078e0-161">CORE_WEBVIEW2_PHYSICAL_KEY_STATUS</span></span>](#core_webview2_physical_key_status) | <span data-ttu-id="078e0-162">Win32 キーイベントに指定された LPARAM にパックされた情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="078e0-162">A structure representing the information packed into the LPARAM given to a Win32 key event.</span></span>

<span data-ttu-id="078e0-163">CoreWebView2Host は CoreWebView2 を所有しており、CoreWebView2Host へのすべての参照が終了した場合、WebView は閉じられます。</span><span class="sxs-lookup"><span data-stu-id="078e0-163">The CoreWebView2Host owns the CoreWebView2, and if all references to the CoreWebView2Host go away, the WebView will be closed.</span></span>

## <span data-ttu-id="078e0-164">Members</span><span class="sxs-lookup"><span data-stu-id="078e0-164">Members</span></span>

#### <span data-ttu-id="078e0-165">get_IsVisible</span><span class="sxs-lookup"><span data-stu-id="078e0-165">get_IsVisible</span></span> 

<span data-ttu-id="078e0-166">IsVisible プロパティは、webview の表示と非表示を切り替えるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="078e0-166">The IsVisible property determines whether to show or hide the webview.</span></span>

> <span data-ttu-id="078e0-167">パブリック HRESULT [get_IsVisible](#get_isvisible)(BOOL \* IsVisible)</span><span class="sxs-lookup"><span data-stu-id="078e0-167">public HRESULT [get_IsVisible](#get_isvisible)(BOOL \* isVisible)</span></span>

<span data-ttu-id="078e0-168">IsVisible が false に設定されている場合、webview は透過的であり、表示されません。</span><span class="sxs-lookup"><span data-stu-id="078e0-168">If IsVisible is set to false, the webview will be transparent and will not be rendered.</span></span> <span data-ttu-id="078e0-169">ただし、この操作を行っても、webview (CreateCoreWebView2Host に渡された HWND パラメーター) が含まれているウィンドウは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="078e0-169">However, this will not affect the window containing the webview (the HWND parameter that was passed to CreateCoreWebView2Host).</span></span> <span data-ttu-id="078e0-170">ウィンドウを非表示にする場合は、IsVisible プロパティを変更するだけでなく、直接 ShowWindow を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="078e0-170">If you want that window to disappear too, call ShowWindow on it directly in addition to modifying the IsVisible property.</span></span> <span data-ttu-id="078e0-171">子ウィンドウとして WebView を実行しても、上のウィンドウを最小化または復元したときにウィンドウメッセージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="078e0-171">WebView as a child window won't get window messages when the top window is minimized or restored.</span></span> <span data-ttu-id="078e0-172">パフォーマンスを向上させるために、アプリのウィンドウを最小化して、アプリウィンドウが復元されたときに true に戻す場合は、WebView の IsVisible プロパティを false に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="078e0-172">For performance reason, developer should set IsVisible property of the WebView to false when the app window is minimized and back to true when app window is restored.</span></span> <span data-ttu-id="078e0-173">アプリウィンドウでは、WM_SYSCOMMAND メッセージを受信したときに SC_MINIMIZE と SC_RESTORE コマンドを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="078e0-173">App window can do this by handling SC_MINIMIZE and SC_RESTORE command upon receiving WM_SYSCOMMAND message.</span></span>

```cpp
void ViewComponent::ToggleVisibility()
{
    BOOL visible;
    m_host->get_IsVisible(&visible);
    m_isVisible = !visible;
    m_host->put_IsVisible(m_isVisible);
}
```

#### <span data-ttu-id="078e0-174">put_IsVisible</span><span class="sxs-lookup"><span data-stu-id="078e0-174">put_IsVisible</span></span> 

<span data-ttu-id="078e0-175">IsVisible プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="078e0-175">Set the IsVisible property.</span></span>

> <span data-ttu-id="078e0-176">パブリック HRESULT [put_IsVisible](#put_isvisible)(BOOL IsVisible)</span><span class="sxs-lookup"><span data-stu-id="078e0-176">public HRESULT [put_IsVisible](#put_isvisible)(BOOL isVisible)</span></span>

```cpp
    if (message == WM_SYSCOMMAND)
    {
        if (wParam == SC_MINIMIZE)
        {
            // Hide the webview when the app window is minimized.
            m_host->put_IsVisible(FALSE);
        }
        else if (wParam == SC_RESTORE)
        {
            // When the app window is restored, show the webview
            // (unless the user has toggle visibility off).
            if (m_isVisible)
            {
                m_host->put_IsVisible(TRUE);
            }
        }
    }
```

#### <span data-ttu-id="078e0-177">get_Bounds</span><span class="sxs-lookup"><span data-stu-id="078e0-177">get_Bounds</span></span> 

<span data-ttu-id="078e0-178">Webview の境界。</span><span class="sxs-lookup"><span data-stu-id="078e0-178">The webview bounds.</span></span>

> <span data-ttu-id="078e0-179">パブリック HRESULT [get_Bounds](#get_bounds)(RECT \* 境界)</span><span class="sxs-lookup"><span data-stu-id="078e0-179">public HRESULT [get_Bounds](#get_bounds)(RECT \* bounds)</span></span>

<span data-ttu-id="078e0-180">境界は親 HWND を基準としています。</span><span class="sxs-lookup"><span data-stu-id="078e0-180">Bounds are relative to the parent HWND.</span></span> <span data-ttu-id="078e0-181">アプリには、WebView を配置する2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="078e0-181">The app has two ways it can position a WebView:</span></span>

1. <span data-ttu-id="078e0-182">WebView 親 HWND である子 HWND を作成します。</span><span class="sxs-lookup"><span data-stu-id="078e0-182">Create a child HWND that is the WebView parent HWND.</span></span> <span data-ttu-id="078e0-183">WebView が必要な場所にこのウィンドウを配置します。</span><span class="sxs-lookup"><span data-stu-id="078e0-183">Position this window where the WebView should be.</span></span> <span data-ttu-id="078e0-184">この場合、(0, 0) を使用して、WebView の Bound の左上隅 (offset) にします。</span><span class="sxs-lookup"><span data-stu-id="078e0-184">In this case, use (0, 0) for the WebView's Bound's top left corner (the offset).</span></span>

1. <span data-ttu-id="078e0-185">アプリの一番上のウィンドウは、WebView 親 HWND として使います。</span><span class="sxs-lookup"><span data-stu-id="078e0-185">Use the app's top most window as the WebView parent HWND.</span></span> <span data-ttu-id="078e0-186">Webview の左上隅を、アプリ内で適切に配置されるように設定します。</span><span class="sxs-lookup"><span data-stu-id="078e0-186">Set the WebView's Bound's top left corner so that the WebView is positioned correctly in the app.</span></span> <span data-ttu-id="078e0-187">バインドされた値は、ホストの座標空間にあります。</span><span class="sxs-lookup"><span data-stu-id="078e0-187">The Bound's values are in the host's coordinate space.</span></span>

#### <span data-ttu-id="078e0-188">put_Bounds</span><span class="sxs-lookup"><span data-stu-id="078e0-188">put_Bounds</span></span> 

<span data-ttu-id="078e0-189">境界プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="078e0-189">Set the Bounds property.</span></span>

> <span data-ttu-id="078e0-190">パブリック HRESULT [put_Bounds](#put_bounds)(四角形の境界)</span><span class="sxs-lookup"><span data-stu-id="078e0-190">public HRESULT [put_Bounds](#put_bounds)(RECT bounds)</span></span>

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

    m_host->put_Bounds(desiredBounds);
}
```

#### <span data-ttu-id="078e0-191">get_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="078e0-191">get_ZoomFactor</span></span> 

<span data-ttu-id="078e0-192">WebView のズームファクター。</span><span class="sxs-lookup"><span data-stu-id="078e0-192">The zoom factor for the WebView.</span></span>

> <span data-ttu-id="078e0-193">パブリック HRESULT [get_ZoomFactor](#get_zoomfactor)(Double \* ZoomFactor)</span><span class="sxs-lookup"><span data-stu-id="078e0-193">public HRESULT [get_ZoomFactor](#get_zoomfactor)(double \* zoomFactor)</span></span>

<span data-ttu-id="078e0-194">ズーム倍率を変更すると、ページレイアウトが変更される場合があることに注意して `window.innerWidth/innerHeight` ください。</span><span class="sxs-lookup"><span data-stu-id="078e0-194">Note that changing zoom factor could cause `window.innerWidth/innerHeight` and page layout to change.</span></span> <span data-ttu-id="078e0-195">Put_ZoomFactor を呼び出すことによってホストによって適用されるズームファクターは、WebView の新しい既定のズームになります。</span><span class="sxs-lookup"><span data-stu-id="078e0-195">A zoom factor that is applied by the host by calling put_ZoomFactor becomes the new default zoom for the WebView.</span></span> <span data-ttu-id="078e0-196">このズーム倍率は、ナビゲーション間で適用され、ユーザーが ctrl + 0 キーを押したときに表示されるズームファクター WebView に戻ります。</span><span class="sxs-lookup"><span data-stu-id="078e0-196">This zoom factor applies across navigations and is the zoom factor WebView is returned to when the user presses ctrl+0.</span></span> <span data-ttu-id="078e0-197">拡大率がユーザーによって変更された場合 (アプリの ZoomFactorChanged を受け取る場合)、現在のページに対してのみズームが適用されます。</span><span class="sxs-lookup"><span data-stu-id="078e0-197">When the zoom factor is changed by the user (resulting in the app receiving ZoomFactorChanged), that zoom applies only for the current page.</span></span> <span data-ttu-id="078e0-198">すべてのユーザーのズームは、現在のページに対してのみ適用され、ナビゲーションではリセットされます。</span><span class="sxs-lookup"><span data-stu-id="078e0-198">Any user applied zoom is only for the current page and is reset on a navigation.</span></span> <span data-ttu-id="078e0-199">0以下の zoomFactor を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="078e0-199">Specifying a zoomFactor less than or equal to 0 is not allowed.</span></span> <span data-ttu-id="078e0-200">WebView には、内部でサポートされているズームファクター範囲もあります。</span><span class="sxs-lookup"><span data-stu-id="078e0-200">WebView also has an internal supported zoom factor range.</span></span> <span data-ttu-id="078e0-201">指定したズームファクターがその範囲外の場合は、範囲内に収まるように正規化され、実際に適用されたズームファクターに対して ZoomFactorChanged イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="078e0-201">When a specified zoom factor is out of that range, it will be normalized to be within the range, and a ZoomFactorChanged event will be fired for the real applied zoom factor.</span></span> <span data-ttu-id="078e0-202">この範囲の正規化が行われると、ZoomFactor プロパティは、ZoomFactor プロパティの前の変更時に指定されたズーム率を報告します。これは、webview が正規化されたズームファクターを適用した後に ZoomFactorChanged イベントが受信されるまでです。</span><span class="sxs-lookup"><span data-stu-id="078e0-202">When this range normalization happens, the ZoomFactor property will report the zoom factor specified during the previous modification of the ZoomFactor property until the ZoomFactorChanged event is received after webview applies the normalized zoom factor.</span></span>

#### <span data-ttu-id="078e0-203">put_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="078e0-203">put_ZoomFactor</span></span> 

<span data-ttu-id="078e0-204">ZoomFactor プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="078e0-204">Set the ZoomFactor property.</span></span>

> <span data-ttu-id="078e0-205">パブリック HRESULT [put_ZoomFactor](#put_zoomfactor)(double ZoomFactor)</span><span class="sxs-lookup"><span data-stu-id="078e0-205">public HRESULT [put_ZoomFactor](#put_zoomfactor)(double zoomFactor)</span></span>

#### <span data-ttu-id="078e0-206">add_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="078e0-206">add_ZoomFactorChanged</span></span> 

<span data-ttu-id="078e0-207">ZoomFactorChanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="078e0-207">Add an event handler for the ZoomFactorChanged event.</span></span>

> <span data-ttu-id="078e0-208">パブリック HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)([ICoreWebView2ZoomFactorChangedEventHandler](ICoreWebView2ZoomFactorChangedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="078e0-208">public HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)([ICoreWebView2ZoomFactorChangedEventHandler](ICoreWebView2ZoomFactorChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="078e0-209">WebView の ZoomFactor プロパティが変更されると、イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="078e0-209">The event fires when the ZoomFactor property of the WebView changes.</span></span> <span data-ttu-id="078e0-210">呼び出し元が ZoomFactor プロパティを変更したか、ユーザーが手動でズームを変更したために、イベントが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="078e0-210">The event could fire because the caller modified the ZoomFactor property, or due to the user manually modifying the zoom.</span></span> <span data-ttu-id="078e0-211">ZoomFactor プロパティを使用して呼び出し元によって変更された場合、内部のズームファクターはすぐに更新され、ZoomFactorChanged イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="078e0-211">When it is modified by the caller via the ZoomFactor property, the internal zoom factor is updated immediately and there will be no ZoomFactorChanged event.</span></span> <span data-ttu-id="078e0-212">WebView は、各サイトで使用されている直前の拡大率を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="078e0-212">WebView associates the last used zoom factor for each site.</span></span> <span data-ttu-id="078e0-213">そのため、別のページに移動するときにズーム倍率が変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="078e0-213">Therefore, it is possible for the zoom factor to change when navigating to a different page.</span></span> <span data-ttu-id="078e0-214">このため、ズームファクターが変更された場合、ZoomFactorChanged イベントは ContentLoading イベントの直後に発生します。</span><span class="sxs-lookup"><span data-stu-id="078e0-214">When the zoom factor changes due to this, the ZoomFactorChanged event fires right after the ContentLoading event.</span></span>

```cpp
    // Register a handler for the ZoomFactorChanged event.
    // This handler just announces the new level of zoom on the window's title bar.
    CHECK_FAILURE(m_host->add_ZoomFactorChanged(
        Callback<ICoreWebView2ZoomFactorChangedEventHandler>(
            [this](ICoreWebView2Host* sender, IUnknown* args) -> HRESULT {
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

#### <span data-ttu-id="078e0-215">remove_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="078e0-215">remove_ZoomFactorChanged</span></span> 

<span data-ttu-id="078e0-216">Add_ZoomFactorChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="078e0-216">Remove an event handler previously added with add_ZoomFactorChanged.</span></span>

> <span data-ttu-id="078e0-217">パブリック HRESULT [remove_ZoomFactorChanged](#remove_zoomfactorchanged)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="078e0-217">public HRESULT [remove_ZoomFactorChanged](#remove_zoomfactorchanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="078e0-218">SetBoundsAndZoomFactor</span><span class="sxs-lookup"><span data-stu-id="078e0-218">SetBoundsAndZoomFactor</span></span> 

<span data-ttu-id="078e0-219">同時に境界と ZoomFactor のプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="078e0-219">Update Bounds and ZoomFactor properties at the same time.</span></span>

> <span data-ttu-id="078e0-220">パブリック HRESULT [SetBoundsAndZoomFactor](#setboundsandzoomfactor)(RECT 境界、double zoomFactor)</span><span class="sxs-lookup"><span data-stu-id="078e0-220">public HRESULT [SetBoundsAndZoomFactor](#setboundsandzoomfactor)(RECT bounds,double zoomFactor)</span></span>

<span data-ttu-id="078e0-221">この操作は、ホストの perspecive によってアトミック処理されます。</span><span class="sxs-lookup"><span data-stu-id="078e0-221">This operation is atomic from the host's perspecive.</span></span> <span data-ttu-id="078e0-222">この関数から戻ると、関数が正常に終了した場合は、境界プロパティと ZoomFactor プロパティの両方が更新されます。または、関数が失敗した場合にも更新されません。</span><span class="sxs-lookup"><span data-stu-id="078e0-222">After returning from this function, the Bounds and ZoomFactor properties will have both been updated if the function is successful, or neither will be updated if the function fails.</span></span> <span data-ttu-id="078e0-223">境界と ZoomFactor の両方が同じ目盛で更新されている場合 (つまり、境界と ZoomFactor の両方が2倍)、ページには、ウィンドウ内の変更が表示されません。その場合は、中間レンダリングを使わずに、コンテンツが新しいサイズとズームでレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="078e0-223">If Bounds and ZoomFactor are both updated by the same scale (i.e. Bounds and ZoomFactor are both doubled), then the page will not see a change in window.innerWidth/innerHeight and the WebView will render the content at the new size and zoom without intermediate renderings.</span></span> <span data-ttu-id="078e0-224">この関数は、ZoomFactor または境界の1つだけを更新するためにも使うことができ、一方の値と他方の値の新しい値を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="078e0-224">This function can also be used to update just one of ZoomFactor or Bounds by passing in the new value for one and the current value for the other.</span></span>

```cpp
void ViewComponent::SetScale(float scale)
{
    RECT bounds;
    CHECK_FAILURE(m_host->get_Bounds(&bounds));
    double scaleChange = scale / m_webViewScale;

    bounds.bottom = LONG(
        (bounds.bottom - bounds.top) * scaleChange + bounds.top);
    bounds.right = LONG(
        (bounds.right - bounds.left) * scaleChange + bounds.left);

    m_webViewScale = scale;
    m_host->SetBoundsAndZoomFactor(bounds, scale);
}
```

#### <span data-ttu-id="078e0-225">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="078e0-225">MoveFocus</span></span> 

<span data-ttu-id="078e0-226">WebView にフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="078e0-226">Move focus into WebView.</span></span>

> <span data-ttu-id="078e0-227">パブリック HRESULT [MoveFocus](#movefocus)([CORE_WEBVIEW2_MOVE_FOCUS_REASON](#core_webview2_move_focus_reason)の理由)</span><span class="sxs-lookup"><span data-stu-id="078e0-227">public HRESULT [MoveFocus](#movefocus)([CORE_WEBVIEW2_MOVE_FOCUS_REASON](#core_webview2_move_focus_reason) reason)</span></span>

<span data-ttu-id="078e0-228">WebView はフォーカスを取得し、WebView でホストされているページ内の対応する要素にフォーカスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="078e0-228">WebView will get focus and focus will be set to correspondent element in the page hosted in the WebView.</span></span> <span data-ttu-id="078e0-229">プログラム的な理由により、フォーカスは前にフォーカスされた要素、または、前にフォーカスされている要素がない場合は既定の要素に設定されます。</span><span class="sxs-lookup"><span data-stu-id="078e0-229">For Programmatic reason, focus is set to previously focused element or the default element if there is no previously focused element.</span></span> <span data-ttu-id="078e0-230">次の理由から、フォーカスは最初の要素に設定されます。</span><span class="sxs-lookup"><span data-stu-id="078e0-230">For Next reason, focus is set to the first element.</span></span> <span data-ttu-id="078e0-231">前の理由から、フォーカスは最後の要素に設定されます。</span><span class="sxs-lookup"><span data-stu-id="078e0-231">For Previous reason, focus is set to the last element.</span></span> <span data-ttu-id="078e0-232">また、WebView または Tab キーをクリックするなど、ユーザーの操作によってフォーカスを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="078e0-232">WebView can also got focus through user interaction like clicking into WebView or Tab into it.</span></span> <span data-ttu-id="078e0-233">Tab キーを押した場合は、次のタブと shift キーを押しながら tab キーを押すと、[次へ] または [前のページ] を使用して MoveFocus を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="078e0-233">For tabbing, the app can call MoveFocus with Next or Previous to align with tab and shift+tab respectively when it decides the WebView is the next tabbable element.</span></span> <span data-ttu-id="078e0-234">または、アプリがメッセージループの一部として IsDialogMessage を呼び出して、プラットフォームがタブを自動処理できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="078e0-234">Or, the app can call IsDialogMessage as part of its message loop to allow the platform to auto handle tabbing.</span></span> <span data-ttu-id="078e0-235">プラットフォームは、すべてのウィンドウを通じて WS_TABSTOP で回転します。</span><span class="sxs-lookup"><span data-stu-id="078e0-235">The platform will rotate through all windows with WS_TABSTOP.</span></span> <span data-ttu-id="078e0-236">WebView が IsDialogMessage からフォーカスを取得すると、tab と shift + tab の最初または最後の要素にフォーカスが内部的に配置されます。</span><span class="sxs-lookup"><span data-stu-id="078e0-236">When the WebView gets focus from IsDialogMessage, it will internally put the focus on the first or last element for tab and shift+tab respectively.</span></span>

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
            for (int i = 0; i < m_tabbableWindows.size(); i++)
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
    for (int i = currentIndex + 1; i < m_tabbableWindows.size(); i++)
    {
        HWND hwnd = m_tabbableWindows.at(i).first;
        if (IsWindowEnabled(hwnd))
        {
            SetFocus(hwnd);
            return;
        }
    }
    // If this is the last enabled window, tab forwards into the WebView.
    m_host->MoveFocus(CORE_WEBVIEW2_MOVE_FOCUS_REASON_NEXT);
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
    CHECK_FAILURE(m_host->MoveFocus(CORE_WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS));
}
```

#### <span data-ttu-id="078e0-237">add_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="078e0-237">add_MoveFocusRequested</span></span> 

<span data-ttu-id="078e0-238">MoveFocusRequested されたイベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="078e0-238">Add an event handler for the MoveFocusRequested event.</span></span>

> <span data-ttu-id="078e0-239">パブリック HRESULT [add_MoveFocusRequested](#add_movefocusrequested)([ICoreWebView2MoveFocusRequestedEventHandler](ICoreWebView2MoveFocusRequestedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="078e0-239">public HRESULT [add_MoveFocusRequested](#add_movefocusrequested)([ICoreWebView2MoveFocusRequestedEventHandler](ICoreWebView2MoveFocusRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="078e0-240">MoveFocusRequested は、ユーザーが WebView から tab キーを移動しようとしたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="078e0-240">MoveFocusRequested fires when user tries to tab out of the WebView.</span></span> <span data-ttu-id="078e0-241">このイベントが発生すると、WebView のフォーカスが変更されません。</span><span class="sxs-lookup"><span data-stu-id="078e0-241">The WebView's focus has not changed when this event is fired.</span></span>

```cpp
    // Register a handler for the MoveFocusRequested event.
    // This event will be fired when the user tabs out of the webview.
    // The handler will focus another window in the app, depending on which
    // direction the focus is being shifted.
    CHECK_FAILURE(m_host->add_MoveFocusRequested(
        Callback<ICoreWebView2MoveFocusRequestedEventHandler>(
            [this](
                ICoreWebView2Host* sender,
                ICoreWebView2MoveFocusRequestedEventArgs* args) -> HRESULT {
                if (!g_autoTabHandle)
                {
                    CORE_WEBVIEW2_MOVE_FOCUS_REASON reason;
                    CHECK_FAILURE(args->get_Reason(&reason));

                    if (reason == CORE_WEBVIEW2_MOVE_FOCUS_REASON_NEXT)
                    {
                        TabForwards(-1);
                    }
                    else if (reason == CORE_WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS)
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

#### <span data-ttu-id="078e0-242">remove_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="078e0-242">remove_MoveFocusRequested</span></span> 

<span data-ttu-id="078e0-243">Add_MoveFocusRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="078e0-243">Remove an event handler previously added with add_MoveFocusRequested.</span></span>

> <span data-ttu-id="078e0-244">パブリック HRESULT [remove_MoveFocusRequested](#remove_movefocusrequested)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="078e0-244">public HRESULT [remove_MoveFocusRequested](#remove_movefocusrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="078e0-245">add_GotFocus</span><span class="sxs-lookup"><span data-stu-id="078e0-245">add_GotFocus</span></span> 

<span data-ttu-id="078e0-246">GotFocus イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="078e0-246">Add an event handler for the GotFocus event.</span></span>

> <span data-ttu-id="078e0-247">パブリック HRESULT [add_GotFocus](#add_gotfocus)([ICoreWebView2FocusChangedEventHandler](ICoreWebView2FocusChangedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="078e0-247">public HRESULT [add_GotFocus](#add_gotfocus)([ICoreWebView2FocusChangedEventHandler](ICoreWebView2FocusChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="078e0-248">GotFocus は、WebView がフォーカスを取得したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="078e0-248">GotFocus fires when WebView got focus.</span></span>

#### <span data-ttu-id="078e0-249">remove_GotFocus</span><span class="sxs-lookup"><span data-stu-id="078e0-249">remove_GotFocus</span></span> 

<span data-ttu-id="078e0-250">Add_GotFocus で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="078e0-250">Remove an event handler previously added with add_GotFocus.</span></span>

> <span data-ttu-id="078e0-251">パブリック HRESULT [remove_GotFocus](#remove_gotfocus)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="078e0-251">public HRESULT [remove_GotFocus](#remove_gotfocus)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="078e0-252">add_LostFocus</span><span class="sxs-lookup"><span data-stu-id="078e0-252">add_LostFocus</span></span> 

<span data-ttu-id="078e0-253">LostFocus イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="078e0-253">Add an event handler for the LostFocus event.</span></span>

> <span data-ttu-id="078e0-254">パブリック HRESULT [add_LostFocus](#add_lostfocus)([ICoreWebView2FocusChangedEventHandler](ICoreWebView2FocusChangedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="078e0-254">public HRESULT [add_LostFocus](#add_lostfocus)([ICoreWebView2FocusChangedEventHandler](ICoreWebView2FocusChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="078e0-255">このとき、WebView はフォーカスを失ったときに発生します。</span><span class="sxs-lookup"><span data-stu-id="078e0-255">LostFocus fires when WebView lost focus.</span></span> <span data-ttu-id="078e0-256">MoveFocusRequested イベントが発生した場合は、MoveFocusRequested イベントが発生したときに、フォーカスはまだ WebView に残っています。</span><span class="sxs-lookup"><span data-stu-id="078e0-256">In the case where MoveFocusRequested event is fired, the focus is still on WebView when MoveFocusRequested event fires.</span></span> <span data-ttu-id="078e0-257">フォーカスが失われたのは、アプリのコードが、または MoveFocusRequested イベントを WebView から離した場合にのみ、後で発生します。</span><span class="sxs-lookup"><span data-stu-id="078e0-257">Lost focus only fires afterwards when app's code or default action of MoveFocusRequested event set focus away from WebView.</span></span>

#### <span data-ttu-id="078e0-258">remove_LostFocus</span><span class="sxs-lookup"><span data-stu-id="078e0-258">remove_LostFocus</span></span> 

<span data-ttu-id="078e0-259">Add_LostFocus で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="078e0-259">Remove an event handler previously added with add_LostFocus.</span></span>

> <span data-ttu-id="078e0-260">パブリック HRESULT [remove_LostFocus](#remove_lostfocus)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="078e0-260">public HRESULT [remove_LostFocus](#remove_lostfocus)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="078e0-261">add_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="078e0-261">add_AcceleratorKeyPressed</span></span> 

<span data-ttu-id="078e0-262">AcceleratorKeyPressed イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="078e0-262">Add an event handler for the AcceleratorKeyPressed event.</span></span>

> <span data-ttu-id="078e0-263">パブリック HRESULT [add_AcceleratorKeyPressed](#add_acceleratorkeypressed)([ICoreWebView2AcceleratorKeyPressedEventHandler](ICoreWebView2AcceleratorKeyPressedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="078e0-263">public HRESULT [add_AcceleratorKeyPressed](#add_acceleratorkeypressed)([ICoreWebView2AcceleratorKeyPressedEventHandler](ICoreWebView2AcceleratorKeyPressedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="078e0-264">AcceleratorKeyPressed は、WebView がフォーカスされているときに、アクセスキーまたはキーコンボが押されたとき、または離されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="078e0-264">AcceleratorKeyPressed fires when an accelerator key or key combo is pressed or released while the WebView is focused.</span></span> <span data-ttu-id="078e0-265">次のいずれかの場合、キーはアクセラレータと見なされます。</span><span class="sxs-lookup"><span data-stu-id="078e0-265">A key is considered an accelerator if either:</span></span>

1. <span data-ttu-id="078e0-266">Ctrl または Alt は現在保留中か</span><span class="sxs-lookup"><span data-stu-id="078e0-266">Ctrl or Alt is currently being held, or</span></span>

1. <span data-ttu-id="078e0-267">押されたキーは文字にマップされません。</span><span class="sxs-lookup"><span data-stu-id="078e0-267">the pressed key does not map to a character.</span></span> <span data-ttu-id="078e0-268">一部の特定のキーは、Shift などのアクセラレータとは見なされません。</span><span class="sxs-lookup"><span data-stu-id="078e0-268">A few specific keys are never considered accelerators, such as Shift.</span></span> <span data-ttu-id="078e0-269">Escape キーは、常にアクセラレータと見なされます。</span><span class="sxs-lookup"><span data-stu-id="078e0-269">The Escape key is always considered an accelerator.</span></span>

<span data-ttu-id="078e0-270">キーを押したままにした場合に発生する自動実行のキーイベントも、このイベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="078e0-270">Autorepeated key events caused by holding the key down will also fire this event.</span></span> <span data-ttu-id="078e0-271">これらをフィルター処理するには、イベント引数 ' KeyEventLParam または PhysicalKeyStatus を確認します。</span><span class="sxs-lookup"><span data-stu-id="078e0-271">You can filter these out by checking the event args' KeyEventLParam or PhysicalKeyStatus.</span></span>

<span data-ttu-id="078e0-272">ウィンドウモードでは、このイベントハンドラーが同期的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="078e0-272">In windowed mode, this event handler is called synchronously.</span></span> <span data-ttu-id="078e0-273">イベント引数に対して Handle () を呼び出すか、イベントハンドラーから制御が返されるまで、ブラウザープロセスはブロックされ、プロセス間の COM 通話の送信は RPC_E_CANTCALLOUT_ININPUTSYNCCALL で失敗します。</span><span class="sxs-lookup"><span data-stu-id="078e0-273">Until you call Handle() on the event args or the event handler returns, the browser process will be blocked and outgoing cross-process COM calls will fail with RPC_E_CANTCALLOUT_ININPUTSYNCCALL.</span></span> <span data-ttu-id="078e0-274">ただし、すべての CoreWebView2 API メソッドが動作します。</span><span class="sxs-lookup"><span data-stu-id="078e0-274">All CoreWebView2 API methods will work, however.</span></span>

<span data-ttu-id="078e0-275">ウィンドウレスモードでは、イベントハンドラーは非同期的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="078e0-275">In windowless mode, the event handler is called asynchronously.</span></span> <span data-ttu-id="078e0-276">さらに入力は、イベントハンドラーから制御が返されるかハンドル () が呼び出されるまで、ブラウザーには届きませんが、ブラウザープロセス自体はブロックされず、送信 COM 呼び出しは正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="078e0-276">Further input will not reach the browser until the event handler returns or Handle() is called, but the browser process itself will not be blocked, and outgoing COM calls will work normally.</span></span>

<span data-ttu-id="078e0-277">ショートカットキーを処理する必要があることがわかっている場合は、最初にハンドル (TRUE) を呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="078e0-277">It is recommended to call Handle(TRUE) as early as you can know that you want to handle the accelerator key.</span></span>

```cpp
    // Register a handler for the AcceleratorKeyPressed event.
    CHECK_FAILURE(m_host->add_AcceleratorKeyPressed(
        Callback<ICoreWebView2AcceleratorKeyPressedEventHandler>(
            [this](
                ICoreWebView2Host* sender,
                ICoreWebView2AcceleratorKeyPressedEventArgs* args) -> HRESULT {
                CORE_WEBVIEW2_KEY_EVENT_KIND kind;
                CHECK_FAILURE(args->get_KeyEventKind(&kind));
                // We only care about key down events.
                if (kind == CORE_WEBVIEW2_KEY_EVENT_KIND_KEY_DOWN ||
                    kind == CORE_WEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_DOWN)
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
                        CORE_WEBVIEW2_PHYSICAL_KEY_STATUS status;
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

#### <span data-ttu-id="078e0-278">remove_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="078e0-278">remove_AcceleratorKeyPressed</span></span> 

<span data-ttu-id="078e0-279">Add_AcceleratorKeyPressed で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="078e0-279">Remove an event handler previously added with add_AcceleratorKeyPressed.</span></span>

> <span data-ttu-id="078e0-280">パブリック HRESULT [remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="078e0-280">public HRESULT [remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="078e0-281">get_ParentWindow</span><span class="sxs-lookup"><span data-stu-id="078e0-281">get_ParentWindow</span></span> 

<span data-ttu-id="078e0-282">この WebView がコンテンツのレンダリングに使用しているアプリによって提供される親ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="078e0-282">The parent window provided by the app that this WebView is using to render content.</span></span>

> <span data-ttu-id="078e0-283">パブリック HRESULT [get_ParentWindow](#get_parentwindow)(HWND \* topLevelWindow)</span><span class="sxs-lookup"><span data-stu-id="078e0-283">public HRESULT [get_ParentWindow](#get_parentwindow)(HWND \* topLevelWindow)</span></span>

<span data-ttu-id="078e0-284">この API では、最初に CreateCoreWebView2Host に渡されたウィンドウが返されます。</span><span class="sxs-lookup"><span data-stu-id="078e0-284">This API initially returns the window passed into CreateCoreWebView2Host.</span></span>

#### <span data-ttu-id="078e0-285">put_ParentWindow</span><span class="sxs-lookup"><span data-stu-id="078e0-285">put_ParentWindow</span></span> 

<span data-ttu-id="078e0-286">WebView の親ウィンドウを設定します。</span><span class="sxs-lookup"><span data-stu-id="078e0-286">Set the parent window for the WebView.</span></span>

> <span data-ttu-id="078e0-287">パブリック HRESULT [put_ParentWindow](#put_parentwindow)(HWND topLevelWindow)</span><span class="sxs-lookup"><span data-stu-id="078e0-287">public HRESULT [put_ParentWindow](#put_parentwindow)(HWND topLevelWindow)</span></span>

<span data-ttu-id="078e0-288">これにより、WebView が、新しく指定したウィンドウにウィンドウを再表示します。</span><span class="sxs-lookup"><span data-stu-id="078e0-288">This will cause the WebView to reparent its window to the newly provided window.</span></span>

#### <span data-ttu-id="078e0-289">NotifyParentWindowPositionChanged</span><span class="sxs-lookup"><span data-stu-id="078e0-289">NotifyParentWindowPositionChanged</span></span> 

<span data-ttu-id="078e0-290">これは、親 (または任意の先祖) HWND を移動したことを示す put_Bounds とは別の通知です。</span><span class="sxs-lookup"><span data-stu-id="078e0-290">This is a notification separate from put_Bounds that tells WebView its parent (or any ancestor) HWND moved.</span></span>

> <span data-ttu-id="078e0-291">パブリック HRESULT [NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged)()</span><span class="sxs-lookup"><span data-stu-id="078e0-291">public HRESULT [NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged)()</span></span>

<span data-ttu-id="078e0-292">これは、アクセシビリティと、WebView の特定のダイアログで正常に動作するために必要です。</span><span class="sxs-lookup"><span data-stu-id="078e0-292">This is needed for accessibility and certain dialogs in WebView to work correctly.</span></span> 

```cpp
    if (message == WM_MOVE || message == WM_MOVING)
    {
        m_host->NotifyParentWindowPositionChanged();
        return true;
    }
```

#### <span data-ttu-id="078e0-293">Close</span><span class="sxs-lookup"><span data-stu-id="078e0-293">Close</span></span> 

<span data-ttu-id="078e0-294">WebView を閉じ、基になるブラウザーインスタンスをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="078e0-294">Closes the WebView and cleans up the underlying browser instance.</span></span>

> <span data-ttu-id="078e0-295">パブリック HRESULT [Close](#close)()</span><span class="sxs-lookup"><span data-stu-id="078e0-295">public HRESULT [Close](#close)()</span></span>

<span data-ttu-id="078e0-296">ブラウザーの instace をクリーンアップすると、WebView に電源が入っているリソースが解放されます。</span><span class="sxs-lookup"><span data-stu-id="078e0-296">Cleaning up the browser instace will release the resources powering the WebView.</span></span> <span data-ttu-id="078e0-297">他の WebViews が使用していない場合は、ブラウザーインスタンスがシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="078e0-297">The browser instance will be shut down if there are no other WebViews using it.</span></span>

<span data-ttu-id="078e0-298">Close を呼び出した後、すべてのメソッド呼び出しは失敗し、イベントハンドラーは発生しなくなります。</span><span class="sxs-lookup"><span data-stu-id="078e0-298">After calling Close, all method calls will fail and event handlers will stop firing.</span></span> <span data-ttu-id="078e0-299">具体的には、WebView が呼び出されたときに、WebView はそのイベントハンドラーへの参照を解放します。</span><span class="sxs-lookup"><span data-stu-id="078e0-299">Specifically, the WebView will release its references to its event handlers when Close is called.</span></span>

<span data-ttu-id="078e0-300">Close は、CoreWebView2Host が最終的な参照を失い、destructed である場合に、暗黙的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="078e0-300">Close is implicitly called when the CoreWebView2Host loses its final reference and is destructed.</span></span> <span data-ttu-id="078e0-301">ただし、WebView とアプリコードの間の参照が誤って循環しないように、明示的に Close を呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="078e0-301">But it is best practice to explicitly call Close to avoid any accidental cycle of references between the WebView and the app code.</span></span> <span data-ttu-id="078e0-302">具体的には、イベントハンドラーで WebView への参照をキャプチャすると、WebView とイベントハンドラーの間に参照サイクルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="078e0-302">Specifically, if you capture a reference to the WebView in an event handler you will create a reference cycle between the WebView and the event handler.</span></span> <span data-ttu-id="078e0-303">Close を呼び出すと、すべてのイベントハンドラーが解放され、このサイクルが停止します。</span><span class="sxs-lookup"><span data-stu-id="078e0-303">Calling Close will break this cycle by releasing all event handlers.</span></span> <span data-ttu-id="078e0-304">ただし、このような状況を回避するには、WebView を明示的に呼び出すと共に、webview への参照をキャプチャせずに、webview を正しくクリーンアップできるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="078e0-304">But to avoid this situation it is best practice both to explicitly call Close on the WebView and to not capture a reference to the WebView to ensure the WebView can be cleaned up correctly.</span></span>

```cpp
// Close the WebView and deinitialize related state. This doesn't close the app window.
void AppWindow::CloseWebView(bool cleanupUserDataFolder)
{
    DeleteAllComponents();
    if (m_host)
    {
        m_host->Close();
        m_host = nullptr;
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
        // https://docs.microsoft.com/microsoft-edge/hosting/webview2/reference/win32/0-9-488/webview2.idl#createwebview2environmentwithdetails
        WCHAR userDataFolder[MAX_PATH] = L"";
        // Obtain the absolute path for relative paths that include "./" or "../"
        _wfullpath(
            userDataFolder, GetLocalPath(L"WebView2APISample.exe.WebView2").c_str(), MAX_PATH);
        std::wstring userDataFolderPath(userDataFolder);

        std::wstring message = L"Are you sure you want to clean up the user data folder at\n";
        message += userDataFolderPath;
        message += L"\n?\nWarning: This action is not reversible.\n\n";
        message += L"Click No if there are other open WebView instnaces.\n";

        if (MessageBox(m_mainWindow, message.c_str(), L"Cleanup User Data Folder", MB_YESNO) ==
            IDYES)
        {
            CHECK_FAILURE(DeleteFileRecursive(userDataFolderPath));
        }
    }
}
```

#### <span data-ttu-id="078e0-305">get_CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="078e0-305">get_CoreWebView2</span></span> 

<span data-ttu-id="078e0-306">この CoreWebView2Host に関連付けられている CoreWebView2 を取得します。</span><span class="sxs-lookup"><span data-stu-id="078e0-306">Gets the CoreWebView2 associated with this CoreWebView2Host.</span></span>

> <span data-ttu-id="078e0-307">パブリック HRESULT [get_CoreWebView2](#get_corewebview2)([ICoreWebView2](ICoreWebView2.md) \* \* CoreWebView2)</span><span class="sxs-lookup"><span data-stu-id="078e0-307">public HRESULT [get_CoreWebView2](#get_corewebview2)([ICoreWebView2](ICoreWebView2.md) \*\* coreWebView2)</span></span>

#### <span data-ttu-id="078e0-308">CORE_WEBVIEW2_MOVE_FOCUS_REASON</span><span class="sxs-lookup"><span data-stu-id="078e0-308">CORE_WEBVIEW2_MOVE_FOCUS_REASON</span></span> 

<span data-ttu-id="078e0-309">フォーカスを移動する理由。</span><span class="sxs-lookup"><span data-stu-id="078e0-309">Reason for moving focus.</span></span>

> <span data-ttu-id="078e0-310">列挙型[CORE_WEBVIEW2_MOVE_FOCUS_REASON](#core_webview2_move_focus_reason)</span><span class="sxs-lookup"><span data-stu-id="078e0-310">enum [CORE_WEBVIEW2_MOVE_FOCUS_REASON](#core_webview2_move_focus_reason)</span></span>

 <span data-ttu-id="078e0-311">値</span><span class="sxs-lookup"><span data-stu-id="078e0-311">Values</span></span>                         | <span data-ttu-id="078e0-312">説明</span><span class="sxs-lookup"><span data-stu-id="078e0-312">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="078e0-313">CORE_WEBVIEW2_MOVE_FOCUS_REASON_PROGRAMMATIC</span><span class="sxs-lookup"><span data-stu-id="078e0-313">CORE_WEBVIEW2_MOVE_FOCUS_REASON_PROGRAMMATIC</span></span>            | <span data-ttu-id="078e0-314">コード設定による WebView へのフォーカス。</span><span class="sxs-lookup"><span data-stu-id="078e0-314">Code setting focus into WebView.</span></span>
<span data-ttu-id="078e0-315">CORE_WEBVIEW2_MOVE_FOCUS_REASON_NEXT</span><span class="sxs-lookup"><span data-stu-id="078e0-315">CORE_WEBVIEW2_MOVE_FOCUS_REASON_NEXT</span></span>            | <span data-ttu-id="078e0-316">タブトラバーサルを前方に移動するためにフォーカスを移動する。</span><span class="sxs-lookup"><span data-stu-id="078e0-316">Moving focus due to Tab traversal forward.</span></span>
<span data-ttu-id="078e0-317">CORE_WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS</span><span class="sxs-lookup"><span data-stu-id="078e0-317">CORE_WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS</span></span>            | <span data-ttu-id="078e0-318">タブトラバーサルに戻るためにフォーカスを移動する。</span><span class="sxs-lookup"><span data-stu-id="078e0-318">Moving focus due to Tab traversal backward.</span></span>

#### <span data-ttu-id="078e0-319">CORE_WEBVIEW2_KEY_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="078e0-319">CORE_WEBVIEW2_KEY_EVENT_KIND</span></span> 

<span data-ttu-id="078e0-320">AcceleratorKeyPressed イベントをトリガーしたキーイベントの種類です。</span><span class="sxs-lookup"><span data-stu-id="078e0-320">The type of key event that triggered an AcceleratorKeyPressed event.</span></span>

> <span data-ttu-id="078e0-321">列挙型[CORE_WEBVIEW2_KEY_EVENT_KIND](#core_webview2_key_event_kind)</span><span class="sxs-lookup"><span data-stu-id="078e0-321">enum [CORE_WEBVIEW2_KEY_EVENT_KIND](#core_webview2_key_event_kind)</span></span>

 <span data-ttu-id="078e0-322">値</span><span class="sxs-lookup"><span data-stu-id="078e0-322">Values</span></span>                         | <span data-ttu-id="078e0-323">説明</span><span class="sxs-lookup"><span data-stu-id="078e0-323">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="078e0-324">CORE_WEBVIEW2_KEY_EVENT_KIND_KEY_DOWN</span><span class="sxs-lookup"><span data-stu-id="078e0-324">CORE_WEBVIEW2_KEY_EVENT_KIND_KEY_DOWN</span></span>            | <span data-ttu-id="078e0-325">ウィンドウメッセージ WM_KEYDOWN に対応します。</span><span class="sxs-lookup"><span data-stu-id="078e0-325">Correspond to window message WM_KEYDOWN.</span></span>
<span data-ttu-id="078e0-326">CORE_WEBVIEW2_KEY_EVENT_KIND_KEY_UP</span><span class="sxs-lookup"><span data-stu-id="078e0-326">CORE_WEBVIEW2_KEY_EVENT_KIND_KEY_UP</span></span>            | <span data-ttu-id="078e0-327">ウィンドウメッセージ WM_KEYUP に対応します。</span><span class="sxs-lookup"><span data-stu-id="078e0-327">Correspond to window message WM_KEYUP.</span></span>
<span data-ttu-id="078e0-328">CORE_WEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_DOWN</span><span class="sxs-lookup"><span data-stu-id="078e0-328">CORE_WEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_DOWN</span></span>            | <span data-ttu-id="078e0-329">ウィンドウメッセージ WM_SYSKEYDOWN に対応します。</span><span class="sxs-lookup"><span data-stu-id="078e0-329">Correspond to window message WM_SYSKEYDOWN.</span></span>
<span data-ttu-id="078e0-330">CORE_WEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_UP</span><span class="sxs-lookup"><span data-stu-id="078e0-330">CORE_WEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_UP</span></span>            | <span data-ttu-id="078e0-331">ウィンドウメッセージ WM_SYSKEYUP に対応します。</span><span class="sxs-lookup"><span data-stu-id="078e0-331">Correspond to window message WM_SYSKEYUP.</span></span>

#### <span data-ttu-id="078e0-332">CORE_WEBVIEW2_PHYSICAL_KEY_STATUS</span><span class="sxs-lookup"><span data-stu-id="078e0-332">CORE_WEBVIEW2_PHYSICAL_KEY_STATUS</span></span> 

<span data-ttu-id="078e0-333">Win32 キーイベントに指定された LPARAM にパックされた情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="078e0-333">A structure representing the information packed into the LPARAM given to a Win32 key event.</span></span>

> <span data-ttu-id="078e0-334">typedef [CORE_WEBVIEW2_PHYSICAL_KEY_STATUS](#core_webview2_physical_key_status)</span><span class="sxs-lookup"><span data-stu-id="078e0-334">typedef [CORE_WEBVIEW2_PHYSICAL_KEY_STATUS](#core_webview2_physical_key_status)</span></span>

<span data-ttu-id="078e0-335">詳細については、WM_KEYDOWN のドキュメントを参照してください。[https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown)</span><span class="sxs-lookup"><span data-stu-id="078e0-335">See the documentation for WM_KEYDOWN for details at [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown)</span></span>

