---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.430-WebView2 Win32 C++ ICoreWebView2Host
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Host、browser control、edge html
ms.openlocfilehash: 39566c867c28739d21dd99c369d161d29a308946
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885619"
---
# <span data-ttu-id="0dd72-104">0.9.430-インターフェイス ICoreWebView2Host</span><span class="sxs-lookup"><span data-stu-id="0dd72-104">0.9.430 - interface ICoreWebView2Host</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2Host
  : public IUnknown
```

<span data-ttu-id="0dd72-105">このインターフェイスは、CoreWebView2 オブジェクトの所有者であり、ウィンドウ化とコンポジションに関連する、サイズ変更、表示/非表示、フォーカス、およびその他の機能のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-105">This interface is the owner of the CoreWebView2 object, and provides support for resizing, showing and hiding, focusing, and other functionality related to windowing and composition.</span></span>

## <span data-ttu-id="0dd72-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="0dd72-106">Summary</span></span>

 <span data-ttu-id="0dd72-107">Members</span><span class="sxs-lookup"><span data-stu-id="0dd72-107">Members</span></span>                        | <span data-ttu-id="0dd72-108">説明</span><span class="sxs-lookup"><span data-stu-id="0dd72-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0dd72-109">get_IsVisible</span><span class="sxs-lookup"><span data-stu-id="0dd72-109">get_IsVisible</span></span>](#get_isvisible) | <span data-ttu-id="0dd72-110">IsVisible プロパティは、webview の表示と非表示を切り替えるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-110">The IsVisible property determines whether to show or hide the webview.</span></span>
[<span data-ttu-id="0dd72-111">put_IsVisible</span><span class="sxs-lookup"><span data-stu-id="0dd72-111">put_IsVisible</span></span>](#put_isvisible) | <span data-ttu-id="0dd72-112">IsVisible プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-112">Set the IsVisible property.</span></span>
[<span data-ttu-id="0dd72-113">get_Bounds</span><span class="sxs-lookup"><span data-stu-id="0dd72-113">get_Bounds</span></span>](#get_bounds) | <span data-ttu-id="0dd72-114">Webview の境界。</span><span class="sxs-lookup"><span data-stu-id="0dd72-114">The webview bounds.</span></span>
[<span data-ttu-id="0dd72-115">put_Bounds</span><span class="sxs-lookup"><span data-stu-id="0dd72-115">put_Bounds</span></span>](#put_bounds) | <span data-ttu-id="0dd72-116">境界プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-116">Set the Bounds property.</span></span>
[<span data-ttu-id="0dd72-117">get_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="0dd72-117">get_ZoomFactor</span></span>](#get_zoomfactor) | <span data-ttu-id="0dd72-118">WebView のズームファクター。</span><span class="sxs-lookup"><span data-stu-id="0dd72-118">The zoom factor for the WebView.</span></span>
[<span data-ttu-id="0dd72-119">put_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="0dd72-119">put_ZoomFactor</span></span>](#put_zoomfactor) | <span data-ttu-id="0dd72-120">ZoomFactor プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-120">Set the ZoomFactor property.</span></span>
[<span data-ttu-id="0dd72-121">add_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="0dd72-121">add_ZoomFactorChanged</span></span>](#add_zoomfactorchanged) | <span data-ttu-id="0dd72-122">ZoomFactorChanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-122">Add an event handler for the ZoomFactorChanged event.</span></span>
[<span data-ttu-id="0dd72-123">remove_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="0dd72-123">remove_ZoomFactorChanged</span></span>](#remove_zoomfactorchanged) | <span data-ttu-id="0dd72-124">Add_ZoomFactorChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-124">Remove an event handler previously added with add_ZoomFactorChanged.</span></span>
[<span data-ttu-id="0dd72-125">SetBoundsAndZoomFactor</span><span class="sxs-lookup"><span data-stu-id="0dd72-125">SetBoundsAndZoomFactor</span></span>](#setboundsandzoomfactor) | <span data-ttu-id="0dd72-126">同時に境界と ZoomFactor のプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-126">Update Bounds and ZoomFactor properties at the same time.</span></span>
[<span data-ttu-id="0dd72-127">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="0dd72-127">MoveFocus</span></span>](#movefocus) | <span data-ttu-id="0dd72-128">WebView にフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-128">Move focus into WebView.</span></span>
[<span data-ttu-id="0dd72-129">add_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="0dd72-129">add_MoveFocusRequested</span></span>](#add_movefocusrequested) | <span data-ttu-id="0dd72-130">MoveFocusRequested されたイベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-130">Add an event handler for the MoveFocusRequested event.</span></span>
[<span data-ttu-id="0dd72-131">remove_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="0dd72-131">remove_MoveFocusRequested</span></span>](#remove_movefocusrequested) | <span data-ttu-id="0dd72-132">Add_MoveFocusRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-132">Remove an event handler previously added with add_MoveFocusRequested.</span></span>
[<span data-ttu-id="0dd72-133">add_GotFocus</span><span class="sxs-lookup"><span data-stu-id="0dd72-133">add_GotFocus</span></span>](#add_gotfocus) | <span data-ttu-id="0dd72-134">GotFocus イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-134">Add an event handler for the GotFocus event.</span></span>
[<span data-ttu-id="0dd72-135">remove_GotFocus</span><span class="sxs-lookup"><span data-stu-id="0dd72-135">remove_GotFocus</span></span>](#remove_gotfocus) | <span data-ttu-id="0dd72-136">Add_GotFocus で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-136">Remove an event handler previously added with add_GotFocus.</span></span>
[<span data-ttu-id="0dd72-137">add_LostFocus</span><span class="sxs-lookup"><span data-stu-id="0dd72-137">add_LostFocus</span></span>](#add_lostfocus) | <span data-ttu-id="0dd72-138">LostFocus イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-138">Add an event handler for the LostFocus event.</span></span>
[<span data-ttu-id="0dd72-139">remove_LostFocus</span><span class="sxs-lookup"><span data-stu-id="0dd72-139">remove_LostFocus</span></span>](#remove_lostfocus) | <span data-ttu-id="0dd72-140">Add_LostFocus で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-140">Remove an event handler previously added with add_LostFocus.</span></span>
[<span data-ttu-id="0dd72-141">add_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="0dd72-141">add_AcceleratorKeyPressed</span></span>](#add_acceleratorkeypressed) | <span data-ttu-id="0dd72-142">AcceleratorKeyPressed イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-142">Add an event handler for the AcceleratorKeyPressed event.</span></span>
[<span data-ttu-id="0dd72-143">remove_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="0dd72-143">remove_AcceleratorKeyPressed</span></span>](#remove_acceleratorkeypressed) | <span data-ttu-id="0dd72-144">Add_AcceleratorKeyPressed で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-144">Remove an event handler previously added with add_AcceleratorKeyPressed.</span></span>
[<span data-ttu-id="0dd72-145">get_ParentWindow</span><span class="sxs-lookup"><span data-stu-id="0dd72-145">get_ParentWindow</span></span>](#get_parentwindow) | <span data-ttu-id="0dd72-146">この WebView がコンテンツのレンダリングに使用しているアプリによって提供される親ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="0dd72-146">The parent window provided by the app that this WebView is using to render content.</span></span>
[<span data-ttu-id="0dd72-147">put_ParentWindow</span><span class="sxs-lookup"><span data-stu-id="0dd72-147">put_ParentWindow</span></span>](#put_parentwindow) | <span data-ttu-id="0dd72-148">WebView の親ウィンドウを設定します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-148">Set the parent window for the WebView.</span></span>
[<span data-ttu-id="0dd72-149">NotifyParentWindowPositionChanged</span><span class="sxs-lookup"><span data-stu-id="0dd72-149">NotifyParentWindowPositionChanged</span></span>](#notifyparentwindowpositionchanged) | <span data-ttu-id="0dd72-150">これは、親 (または任意の先祖) HWND を移動したことを示す put_Bounds とは別の通知です。</span><span class="sxs-lookup"><span data-stu-id="0dd72-150">This is a notification separate from put_Bounds that tells WebView its parent (or any ancestor) HWND moved.</span></span>
[<span data-ttu-id="0dd72-151">Close</span><span class="sxs-lookup"><span data-stu-id="0dd72-151">Close</span></span>](#close) | <span data-ttu-id="0dd72-152">WebView を閉じ、基になるブラウザーインスタンスをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="0dd72-152">Closes the WebView and cleans up the underlying browser instance.</span></span>
[<span data-ttu-id="0dd72-153">get_CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="0dd72-153">get_CoreWebView2</span></span>](#get_corewebview2) | <span data-ttu-id="0dd72-154">この CoreWebView2Host に関連付けられている CoreWebView2 を取得します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-154">Gets the CoreWebView2 associated with this CoreWebView2Host.</span></span>
[<span data-ttu-id="0dd72-155">CORE_WEBVIEW2_MOVE_FOCUS_REASON</span><span class="sxs-lookup"><span data-stu-id="0dd72-155">CORE_WEBVIEW2_MOVE_FOCUS_REASON</span></span>](#core_webview2_move_focus_reason) | <span data-ttu-id="0dd72-156">フォーカスを移動する理由。</span><span class="sxs-lookup"><span data-stu-id="0dd72-156">Reason for moving focus.</span></span>
[<span data-ttu-id="0dd72-157">CORE_WEBVIEW2_KEY_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="0dd72-157">CORE_WEBVIEW2_KEY_EVENT_KIND</span></span>](#core_webview2_key_event_kind) | <span data-ttu-id="0dd72-158">AcceleratorKeyPressed イベントをトリガーしたキーイベントの種類です。</span><span class="sxs-lookup"><span data-stu-id="0dd72-158">The type of key event that triggered an AcceleratorKeyPressed event.</span></span>
[<span data-ttu-id="0dd72-159">CORE_WEBVIEW2_PHYSICAL_KEY_STATUS</span><span class="sxs-lookup"><span data-stu-id="0dd72-159">CORE_WEBVIEW2_PHYSICAL_KEY_STATUS</span></span>](#core_webview2_physical_key_status) | <span data-ttu-id="0dd72-160">Win32 キーイベントに指定された LPARAM にパックされた情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="0dd72-160">A structure representing the information packed into the LPARAM given to a Win32 key event.</span></span>

<span data-ttu-id="0dd72-161">CoreWebView2Host は CoreWebView2 を所有しており、CoreWebView2Host へのすべての参照が終了した場合、WebView は閉じられます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-161">The CoreWebView2Host owns the CoreWebView2, and if all references to the CoreWebView2Host go away, the WebView will be closed.</span></span>

## <span data-ttu-id="0dd72-162">Members</span><span class="sxs-lookup"><span data-stu-id="0dd72-162">Members</span></span>

#### <span data-ttu-id="0dd72-163">get_IsVisible</span><span class="sxs-lookup"><span data-stu-id="0dd72-163">get_IsVisible</span></span> 

<span data-ttu-id="0dd72-164">IsVisible プロパティは、webview の表示と非表示を切り替えるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-164">The IsVisible property determines whether to show or hide the webview.</span></span>

> <span data-ttu-id="0dd72-165">パブリック HRESULT [get_IsVisible](#get_isvisible)(BOOL \* IsVisible)</span><span class="sxs-lookup"><span data-stu-id="0dd72-165">public HRESULT [get_IsVisible](#get_isvisible)(BOOL \* isVisible)</span></span>

<span data-ttu-id="0dd72-166">IsVisible が false に設定されている場合、webview は透過的であり、表示されません。</span><span class="sxs-lookup"><span data-stu-id="0dd72-166">If IsVisible is set to false, the webview will be transparent and will not be rendered.</span></span> <span data-ttu-id="0dd72-167">ただし、この操作を行っても、webview (CreateCoreWebView2Host に渡された HWND パラメーター) が含まれているウィンドウは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="0dd72-167">However, this will not affect the window containing the webview (the HWND parameter that was passed to CreateCoreWebView2Host).</span></span> <span data-ttu-id="0dd72-168">ウィンドウを非表示にする場合は、IsVisible プロパティを変更するだけでなく、直接 ShowWindow を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-168">If you want that window to disappear too, call ShowWindow on it directly in addition to modifying the IsVisible property.</span></span> <span data-ttu-id="0dd72-169">子ウィンドウとして WebView を実行しても、上のウィンドウを最小化または復元したときにウィンドウメッセージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="0dd72-169">WebView as a child window won't get window messages when the top window is minimized or restored.</span></span> <span data-ttu-id="0dd72-170">パフォーマンスを向上させるために、アプリのウィンドウを最小化して、アプリウィンドウが復元されたときに true に戻す場合は、WebView の IsVisible プロパティを false に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0dd72-170">For performance reason, developer should set IsVisible property of the WebView to false when the app window is minimized and back to true when app window is restored.</span></span> <span data-ttu-id="0dd72-171">アプリウィンドウでは、WM_SYSCOMMAND メッセージを受信したときに SC_MINIMIZE と SC_RESTORE コマンドを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-171">App window can do this by handling SC_MINIMIZE and SC_RESTORE command upon receiving WM_SYSCOMMAND message.</span></span>

```cpp
void ViewComponent::ToggleVisibility()
{
    BOOL visible;
    m_host->get_IsVisible(&visible);
    m_isVisible = !visible;
    m_host->put_IsVisible(m_isVisible);
}
```

#### <span data-ttu-id="0dd72-172">put_IsVisible</span><span class="sxs-lookup"><span data-stu-id="0dd72-172">put_IsVisible</span></span> 

<span data-ttu-id="0dd72-173">IsVisible プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-173">Set the IsVisible property.</span></span>

> <span data-ttu-id="0dd72-174">パブリック HRESULT [put_IsVisible](#put_isvisible)(BOOL IsVisible)</span><span class="sxs-lookup"><span data-stu-id="0dd72-174">public HRESULT [put_IsVisible](#put_isvisible)(BOOL isVisible)</span></span>

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

#### <span data-ttu-id="0dd72-175">get_Bounds</span><span class="sxs-lookup"><span data-stu-id="0dd72-175">get_Bounds</span></span> 

<span data-ttu-id="0dd72-176">Webview の境界。</span><span class="sxs-lookup"><span data-stu-id="0dd72-176">The webview bounds.</span></span>

> <span data-ttu-id="0dd72-177">パブリック HRESULT [get_Bounds](#get_bounds)(RECT \* 境界)</span><span class="sxs-lookup"><span data-stu-id="0dd72-177">public HRESULT [get_Bounds](#get_bounds)(RECT \* bounds)</span></span>

<span data-ttu-id="0dd72-178">境界は親 HWND を基準としています。</span><span class="sxs-lookup"><span data-stu-id="0dd72-178">Bounds are relative to the parent HWND.</span></span> <span data-ttu-id="0dd72-179">アプリには、WebView を配置する2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="0dd72-179">The app has two ways it can position a WebView:</span></span>

1. <span data-ttu-id="0dd72-180">WebView 親 HWND である子 HWND を作成します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-180">Create a child HWND that is the WebView parent HWND.</span></span> <span data-ttu-id="0dd72-181">WebView が必要な場所にこのウィンドウを配置します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-181">Position this window where the WebView should be.</span></span> <span data-ttu-id="0dd72-182">この場合、(0, 0) を使用して、WebView の Bound の左上隅 (offset) にします。</span><span class="sxs-lookup"><span data-stu-id="0dd72-182">In this case, use (0, 0) for the WebView's Bound's top left corner (the offset).</span></span>

1. <span data-ttu-id="0dd72-183">アプリの一番上のウィンドウは、WebView 親 HWND として使います。</span><span class="sxs-lookup"><span data-stu-id="0dd72-183">Use the app's top most window as the WebView parent HWND.</span></span> <span data-ttu-id="0dd72-184">Webview の左上隅を、アプリ内で適切に配置されるように設定します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-184">Set the WebView's Bound's top left corner so that the WebView is positioned correctly in the app.</span></span> <span data-ttu-id="0dd72-185">バインドされた値は、ホストの座標空間にあります。</span><span class="sxs-lookup"><span data-stu-id="0dd72-185">The Bound's values are in the host's coordinate space.</span></span>

#### <span data-ttu-id="0dd72-186">put_Bounds</span><span class="sxs-lookup"><span data-stu-id="0dd72-186">put_Bounds</span></span> 

<span data-ttu-id="0dd72-187">境界プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-187">Set the Bounds property.</span></span>

> <span data-ttu-id="0dd72-188">パブリック HRESULT [put_Bounds](#put_bounds)(四角形の境界)</span><span class="sxs-lookup"><span data-stu-id="0dd72-188">public HRESULT [put_Bounds](#put_bounds)(RECT bounds)</span></span>

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

#### <span data-ttu-id="0dd72-189">get_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="0dd72-189">get_ZoomFactor</span></span> 

<span data-ttu-id="0dd72-190">WebView のズームファクター。</span><span class="sxs-lookup"><span data-stu-id="0dd72-190">The zoom factor for the WebView.</span></span>

> <span data-ttu-id="0dd72-191">パブリック HRESULT [get_ZoomFactor](#get_zoomfactor)(Double \* ZoomFactor)</span><span class="sxs-lookup"><span data-stu-id="0dd72-191">public HRESULT [get_ZoomFactor](#get_zoomfactor)(double \* zoomFactor)</span></span>

<span data-ttu-id="0dd72-192">ズーム倍率を変更すると、ページレイアウトが変更される場合があることに注意して `window.innerWidth/innerHeight` ください。</span><span class="sxs-lookup"><span data-stu-id="0dd72-192">Note that changing zoom factor could cause `window.innerWidth/innerHeight` and page layout to change.</span></span> <span data-ttu-id="0dd72-193">Put_ZoomFactor を呼び出すことによってホストによって適用されるズームファクターは、WebView の新しい既定のズームになります。</span><span class="sxs-lookup"><span data-stu-id="0dd72-193">A zoom factor that is applied by the host by calling put_ZoomFactor becomes the new default zoom for the WebView.</span></span> <span data-ttu-id="0dd72-194">このズーム倍率は、ナビゲーション間で適用され、ユーザーが ctrl + 0 キーを押したときに表示されるズームファクター WebView に戻ります。</span><span class="sxs-lookup"><span data-stu-id="0dd72-194">This zoom factor applies across navigations and is the zoom factor WebView is returned to when the user presses ctrl+0.</span></span> <span data-ttu-id="0dd72-195">拡大率がユーザーによって変更された場合 (アプリの ZoomFactorChanged を受け取る場合)、現在のページに対してのみズームが適用されます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-195">When the zoom factor is changed by the user (resulting in the app receiving ZoomFactorChanged), that zoom applies only for the current page.</span></span> <span data-ttu-id="0dd72-196">すべてのユーザーのズームは、現在のページに対してのみ適用され、ナビゲーションではリセットされます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-196">Any user applied zoom is only for the current page and is reset on a navigation.</span></span> <span data-ttu-id="0dd72-197">0以下の zoomFactor を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="0dd72-197">Specifying a zoomFactor less than or equal to 0 is not allowed.</span></span> <span data-ttu-id="0dd72-198">WebView には、内部でサポートされているズームファクター範囲もあります。</span><span class="sxs-lookup"><span data-stu-id="0dd72-198">WebView also has an internal supported zoom factor range.</span></span> <span data-ttu-id="0dd72-199">指定したズームファクターがその範囲外の場合は、範囲内に収まるように正規化され、実際に適用されたズームファクターに対して ZoomFactorChanged イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-199">When a specified zoom factor is out of that range, it will be normalized to be within the range, and a ZoomFactorChanged event will be fired for the real applied zoom factor.</span></span> <span data-ttu-id="0dd72-200">この範囲の正規化が行われると、ZoomFactor プロパティは、ZoomFactor プロパティの前の変更時に指定されたズーム率を報告します。これは、webview が正規化されたズームファクターを適用した後に ZoomFactorChanged イベントが受信されるまでです。</span><span class="sxs-lookup"><span data-stu-id="0dd72-200">When this range normalization happens, the ZoomFactor property will report the zoom factor specified during the previous modification of the ZoomFactor property until the ZoomFactorChanged event is received after webview applies the normalized zoom factor.</span></span>

#### <span data-ttu-id="0dd72-201">put_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="0dd72-201">put_ZoomFactor</span></span> 

<span data-ttu-id="0dd72-202">ZoomFactor プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-202">Set the ZoomFactor property.</span></span>

> <span data-ttu-id="0dd72-203">パブリック HRESULT [put_ZoomFactor](#put_zoomfactor)(double ZoomFactor)</span><span class="sxs-lookup"><span data-stu-id="0dd72-203">public HRESULT [put_ZoomFactor](#put_zoomfactor)(double zoomFactor)</span></span>

#### <span data-ttu-id="0dd72-204">add_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="0dd72-204">add_ZoomFactorChanged</span></span> 

<span data-ttu-id="0dd72-205">ZoomFactorChanged イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-205">Add an event handler for the ZoomFactorChanged event.</span></span>

> <span data-ttu-id="0dd72-206">パブリック HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)([ICoreWebView2ZoomFactorChangedEventHandler](ICoreWebView2ZoomFactorChangedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="0dd72-206">public HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)([ICoreWebView2ZoomFactorChangedEventHandler](ICoreWebView2ZoomFactorChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="0dd72-207">WebView の ZoomFactor プロパティが変更されると、イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-207">The event fires when the ZoomFactor property of the WebView changes.</span></span> <span data-ttu-id="0dd72-208">呼び出し元が ZoomFactor プロパティを変更したか、ユーザーが手動でズームを変更したために、イベントが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0dd72-208">The event could fire because the caller modified the ZoomFactor property, or due to the user manually modifying the zoom.</span></span> <span data-ttu-id="0dd72-209">ZoomFactor プロパティを使用して呼び出し元によって変更された場合、内部のズームファクターはすぐに更新され、ZoomFactorChanged イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="0dd72-209">When it is modified by the caller via the ZoomFactor property, the internal zoom factor is updated immediately and there will be no ZoomFactorChanged event.</span></span> <span data-ttu-id="0dd72-210">WebView は、各サイトで使用されている直前の拡大率を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-210">WebView associates the last used zoom factor for each site.</span></span> <span data-ttu-id="0dd72-211">そのため、別のページに移動するときにズーム倍率が変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0dd72-211">Therefore, it is possible for the zoom factor to change when navigating to a different page.</span></span> <span data-ttu-id="0dd72-212">このため、ズームファクターが変更された場合、ZoomFactorChanged イベントは ContentLoading イベントの直後に発生します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-212">When the zoom factor changes due to this, the ZoomFactorChanged event fires right after the ContentLoading event.</span></span>

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

#### <span data-ttu-id="0dd72-213">remove_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="0dd72-213">remove_ZoomFactorChanged</span></span> 

<span data-ttu-id="0dd72-214">Add_ZoomFactorChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-214">Remove an event handler previously added with add_ZoomFactorChanged.</span></span>

> <span data-ttu-id="0dd72-215">パブリック HRESULT [remove_ZoomFactorChanged](#remove_zoomfactorchanged)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="0dd72-215">public HRESULT [remove_ZoomFactorChanged](#remove_zoomfactorchanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="0dd72-216">SetBoundsAndZoomFactor</span><span class="sxs-lookup"><span data-stu-id="0dd72-216">SetBoundsAndZoomFactor</span></span> 

<span data-ttu-id="0dd72-217">同時に境界と ZoomFactor のプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-217">Update Bounds and ZoomFactor properties at the same time.</span></span>

> <span data-ttu-id="0dd72-218">パブリック HRESULT [SetBoundsAndZoomFactor](#setboundsandzoomfactor)(RECT 境界、double zoomFactor)</span><span class="sxs-lookup"><span data-stu-id="0dd72-218">public HRESULT [SetBoundsAndZoomFactor](#setboundsandzoomfactor)(RECT bounds,double zoomFactor)</span></span>

<span data-ttu-id="0dd72-219">この操作は、ホストの perspecive によってアトミック処理されます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-219">This operation is atomic from the host's perspecive.</span></span> <span data-ttu-id="0dd72-220">この関数から戻ると、関数が正常に終了した場合は、境界プロパティと ZoomFactor プロパティの両方が更新されます。または、関数が失敗した場合にも更新されません。</span><span class="sxs-lookup"><span data-stu-id="0dd72-220">After returning from this function, the Bounds and ZoomFactor properties will have both been updated if the function is successful, or neither will be updated if the function fails.</span></span> <span data-ttu-id="0dd72-221">境界と ZoomFactor の両方が同じ目盛で更新されている場合 (つまり、境界と ZoomFactor の両方が2倍)、ページには、ウィンドウ内の変更が表示されません。その場合は、中間レンダリングを使わずに、コンテンツが新しいサイズとズームでレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-221">If Bounds and ZoomFactor are both updated by the same scale (i.e. Bounds and ZoomFactor are both doubled), then the page will not see a change in window.innerWidth/innerHeight and the WebView will render the content at the new size and zoom without intermediate renderings.</span></span> <span data-ttu-id="0dd72-222">この関数は、ZoomFactor または境界の1つだけを更新するためにも使うことができ、一方の値と他方の値の新しい値を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-222">This function can also be used to update just one of ZoomFactor or Bounds by passing in the new value for one and the current value for the other.</span></span>

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

#### <span data-ttu-id="0dd72-223">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="0dd72-223">MoveFocus</span></span> 

<span data-ttu-id="0dd72-224">WebView にフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-224">Move focus into WebView.</span></span>

> <span data-ttu-id="0dd72-225">パブリック HRESULT [MoveFocus](#movefocus)([CORE_WEBVIEW2_MOVE_FOCUS_REASON](#core_webview2_move_focus_reason)の理由)</span><span class="sxs-lookup"><span data-stu-id="0dd72-225">public HRESULT [MoveFocus](#movefocus)([CORE_WEBVIEW2_MOVE_FOCUS_REASON](#core_webview2_move_focus_reason) reason)</span></span>

<span data-ttu-id="0dd72-226">WebView はフォーカスを取得し、WebView でホストされているページ内の対応する要素にフォーカスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-226">WebView will get focus and focus will be set to correspondent element in the page hosted in the WebView.</span></span> <span data-ttu-id="0dd72-227">プログラム的な理由により、フォーカスは前にフォーカスされた要素、または、前にフォーカスされている要素がない場合は既定の要素に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-227">For Programmatic reason, focus is set to previously focused element or the default element if there is no previously focused element.</span></span> <span data-ttu-id="0dd72-228">次の理由から、フォーカスは最初の要素に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-228">For Next reason, focus is set to the first element.</span></span> <span data-ttu-id="0dd72-229">前の理由から、フォーカスは最後の要素に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-229">For Previous reason, focus is set to the last element.</span></span> <span data-ttu-id="0dd72-230">また、WebView または Tab キーをクリックするなど、ユーザーの操作によってフォーカスを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-230">WebView can also got focus through user interaction like clicking into WebView or Tab into it.</span></span> <span data-ttu-id="0dd72-231">Tab キーを押した場合は、次のタブと shift キーを押しながら tab キーを押すと、[次へ] または [前のページ] を使用して MoveFocus を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-231">For tabbing, the app can call MoveFocus with Next or Previous to align with tab and shift+tab respectively when it decides the WebView is the next tabbable element.</span></span> <span data-ttu-id="0dd72-232">または、アプリがメッセージループの一部として IsDialogMessage を呼び出して、プラットフォームがタブを自動処理できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-232">Or, the app can call IsDialogMessage as part of its message loop to allow the platform to auto handle tabbing.</span></span> <span data-ttu-id="0dd72-233">プラットフォームは、すべてのウィンドウを通じて WS_TABSTOP で回転します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-233">The platform will rotate through all windows with WS_TABSTOP.</span></span> <span data-ttu-id="0dd72-234">WebView が IsDialogMessage からフォーカスを取得すると、tab と shift + tab の最初または最後の要素にフォーカスが内部的に配置されます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-234">When the WebView gets focus from IsDialogMessage, it will internally put the focus on the first or last element for tab and shift+tab respectively.</span></span>

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

#### <span data-ttu-id="0dd72-235">add_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="0dd72-235">add_MoveFocusRequested</span></span> 

<span data-ttu-id="0dd72-236">MoveFocusRequested されたイベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-236">Add an event handler for the MoveFocusRequested event.</span></span>

> <span data-ttu-id="0dd72-237">パブリック HRESULT [add_MoveFocusRequested](#add_movefocusrequested)([ICoreWebView2MoveFocusRequestedEventHandler](ICoreWebView2MoveFocusRequestedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="0dd72-237">public HRESULT [add_MoveFocusRequested](#add_movefocusrequested)([ICoreWebView2MoveFocusRequestedEventHandler](ICoreWebView2MoveFocusRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="0dd72-238">MoveFocusRequested は、ユーザーが WebView から tab キーを移動しようとしたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-238">MoveFocusRequested fires when user tries to tab out of the WebView.</span></span> <span data-ttu-id="0dd72-239">このイベントが発生すると、WebView のフォーカスが変更されません。</span><span class="sxs-lookup"><span data-stu-id="0dd72-239">The WebView's focus has not changed when this event is fired.</span></span>

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

#### <span data-ttu-id="0dd72-240">remove_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="0dd72-240">remove_MoveFocusRequested</span></span> 

<span data-ttu-id="0dd72-241">Add_MoveFocusRequested で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-241">Remove an event handler previously added with add_MoveFocusRequested.</span></span>

> <span data-ttu-id="0dd72-242">パブリック HRESULT [remove_MoveFocusRequested](#remove_movefocusrequested)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="0dd72-242">public HRESULT [remove_MoveFocusRequested](#remove_movefocusrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="0dd72-243">add_GotFocus</span><span class="sxs-lookup"><span data-stu-id="0dd72-243">add_GotFocus</span></span> 

<span data-ttu-id="0dd72-244">GotFocus イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-244">Add an event handler for the GotFocus event.</span></span>

> <span data-ttu-id="0dd72-245">パブリック HRESULT [add_GotFocus](#add_gotfocus)([ICoreWebView2FocusChangedEventHandler](ICoreWebView2FocusChangedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="0dd72-245">public HRESULT [add_GotFocus](#add_gotfocus)([ICoreWebView2FocusChangedEventHandler](ICoreWebView2FocusChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="0dd72-246">GotFocus は、WebView がフォーカスを取得したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-246">GotFocus fires when WebView got focus.</span></span>

#### <span data-ttu-id="0dd72-247">remove_GotFocus</span><span class="sxs-lookup"><span data-stu-id="0dd72-247">remove_GotFocus</span></span> 

<span data-ttu-id="0dd72-248">Add_GotFocus で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-248">Remove an event handler previously added with add_GotFocus.</span></span>

> <span data-ttu-id="0dd72-249">パブリック HRESULT [remove_GotFocus](#remove_gotfocus)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="0dd72-249">public HRESULT [remove_GotFocus](#remove_gotfocus)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="0dd72-250">add_LostFocus</span><span class="sxs-lookup"><span data-stu-id="0dd72-250">add_LostFocus</span></span> 

<span data-ttu-id="0dd72-251">LostFocus イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-251">Add an event handler for the LostFocus event.</span></span>

> <span data-ttu-id="0dd72-252">パブリック HRESULT [add_LostFocus](#add_lostfocus)([ICoreWebView2FocusChangedEventHandler](ICoreWebView2FocusChangedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="0dd72-252">public HRESULT [add_LostFocus](#add_lostfocus)([ICoreWebView2FocusChangedEventHandler](ICoreWebView2FocusChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="0dd72-253">このとき、WebView はフォーカスを失ったときに発生します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-253">LostFocus fires when WebView lost focus.</span></span> <span data-ttu-id="0dd72-254">MoveFocusRequested イベントが発生した場合は、MoveFocusRequested イベントが発生したときに、フォーカスはまだ WebView に残っています。</span><span class="sxs-lookup"><span data-stu-id="0dd72-254">In the case where MoveFocusRequested event is fired, the focus is still on WebView when MoveFocusRequested event fires.</span></span> <span data-ttu-id="0dd72-255">フォーカスが失われたのは、アプリのコードが、または MoveFocusRequested イベントを WebView から離した場合にのみ、後で発生します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-255">Lost focus only fires afterwards when app's code or default action of MoveFocusRequested event set focus away from WebView.</span></span>

#### <span data-ttu-id="0dd72-256">remove_LostFocus</span><span class="sxs-lookup"><span data-stu-id="0dd72-256">remove_LostFocus</span></span> 

<span data-ttu-id="0dd72-257">Add_LostFocus で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-257">Remove an event handler previously added with add_LostFocus.</span></span>

> <span data-ttu-id="0dd72-258">パブリック HRESULT [remove_LostFocus](#remove_lostfocus)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="0dd72-258">public HRESULT [remove_LostFocus](#remove_lostfocus)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="0dd72-259">add_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="0dd72-259">add_AcceleratorKeyPressed</span></span> 

<span data-ttu-id="0dd72-260">AcceleratorKeyPressed イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-260">Add an event handler for the AcceleratorKeyPressed event.</span></span>

> <span data-ttu-id="0dd72-261">パブリック HRESULT [add_AcceleratorKeyPressed](#add_acceleratorkeypressed)([ICoreWebView2AcceleratorKeyPressedEventHandler](ICoreWebView2AcceleratorKeyPressedEventHandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="0dd72-261">public HRESULT [add_AcceleratorKeyPressed](#add_acceleratorkeypressed)([ICoreWebView2AcceleratorKeyPressedEventHandler](ICoreWebView2AcceleratorKeyPressedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="0dd72-262">AcceleratorKeyPressed は、WebView がフォーカスされているときに、アクセスキーまたはキーコンボが押されたとき、または離されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-262">AcceleratorKeyPressed fires when an accelerator key or key combo is pressed or released while the WebView is focused.</span></span> <span data-ttu-id="0dd72-263">次のいずれかの場合、キーはアクセラレータと見なされます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-263">A key is considered an accelerator if either:</span></span>

1. <span data-ttu-id="0dd72-264">Ctrl または Alt は現在保留中か</span><span class="sxs-lookup"><span data-stu-id="0dd72-264">Ctrl or Alt is currently being held, or</span></span>

1. <span data-ttu-id="0dd72-265">押されたキーは文字にマップされません。</span><span class="sxs-lookup"><span data-stu-id="0dd72-265">the pressed key does not map to a character.</span></span> <span data-ttu-id="0dd72-266">一部の特定のキーは、Shift などのアクセラレータとは見なされません。</span><span class="sxs-lookup"><span data-stu-id="0dd72-266">A few specific keys are never considered accelerators, such as Shift.</span></span> <span data-ttu-id="0dd72-267">Escape キーは、常にアクセラレータと見なされます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-267">The Escape key is always considered an accelerator.</span></span>

<span data-ttu-id="0dd72-268">キーを押したままにした場合に発生する自動実行のキーイベントも、このイベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-268">Autorepeated key events caused by holding the key down will also fire this event.</span></span> <span data-ttu-id="0dd72-269">これらをフィルター処理するには、イベント引数 ' KeyEventLParam または PhysicalKeyStatus を確認します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-269">You can filter these out by checking the event args' KeyEventLParam or PhysicalKeyStatus.</span></span>

<span data-ttu-id="0dd72-270">ウィンドウモードでは、このイベントハンドラーが同期的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-270">In windowed mode, this event handler is called synchronously.</span></span> <span data-ttu-id="0dd72-271">イベント引数に対して Handle () を呼び出すか、イベントハンドラーから制御が返されるまで、ブラウザープロセスはブロックされ、プロセス間の COM 通話の送信は RPC_E_CANTCALLOUT_ININPUTSYNCCALL で失敗します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-271">Until you call Handle() on the event args or the event handler returns, the browser process will be blocked and outgoing cross-process COM calls will fail with RPC_E_CANTCALLOUT_ININPUTSYNCCALL.</span></span> <span data-ttu-id="0dd72-272">ただし、すべての CoreWebView2 API メソッドが動作します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-272">All CoreWebView2 API methods will work, however.</span></span>

<span data-ttu-id="0dd72-273">ウィンドウレスモードでは、イベントハンドラーは非同期的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-273">In windowless mode, the event handler is called asynchronously.</span></span> <span data-ttu-id="0dd72-274">さらに入力は、イベントハンドラーから制御が返されるかハンドル () が呼び出されるまで、ブラウザーには届きませんが、ブラウザープロセス自体はブロックされず、送信 COM 呼び出しは正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-274">Further input will not reach the browser until the event handler returns or Handle() is called, but the browser process itself will not be blocked, and outgoing COM calls will work normally.</span></span>

<span data-ttu-id="0dd72-275">ショートカットキーを処理する必要があることがわかっている場合は、最初にハンドル (TRUE) を呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0dd72-275">It is recommended to call Handle(TRUE) as early as you can know that you want to handle the accelerator key.</span></span>

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

#### <span data-ttu-id="0dd72-276">remove_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="0dd72-276">remove_AcceleratorKeyPressed</span></span> 

<span data-ttu-id="0dd72-277">Add_AcceleratorKeyPressed で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-277">Remove an event handler previously added with add_AcceleratorKeyPressed.</span></span>

> <span data-ttu-id="0dd72-278">パブリック HRESULT [remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="0dd72-278">public HRESULT [remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="0dd72-279">get_ParentWindow</span><span class="sxs-lookup"><span data-stu-id="0dd72-279">get_ParentWindow</span></span> 

<span data-ttu-id="0dd72-280">この WebView がコンテンツのレンダリングに使用しているアプリによって提供される親ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="0dd72-280">The parent window provided by the app that this WebView is using to render content.</span></span>

> <span data-ttu-id="0dd72-281">パブリック HRESULT [get_ParentWindow](#get_parentwindow)(HWND \* topLevelWindow)</span><span class="sxs-lookup"><span data-stu-id="0dd72-281">public HRESULT [get_ParentWindow](#get_parentwindow)(HWND \* topLevelWindow)</span></span>

<span data-ttu-id="0dd72-282">この API では、最初に CreateCoreWebView2Host に渡されたウィンドウが返されます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-282">This API initially returns the window passed into CreateCoreWebView2Host.</span></span>

#### <span data-ttu-id="0dd72-283">put_ParentWindow</span><span class="sxs-lookup"><span data-stu-id="0dd72-283">put_ParentWindow</span></span> 

<span data-ttu-id="0dd72-284">WebView の親ウィンドウを設定します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-284">Set the parent window for the WebView.</span></span>

> <span data-ttu-id="0dd72-285">パブリック HRESULT [put_ParentWindow](#put_parentwindow)(HWND topLevelWindow)</span><span class="sxs-lookup"><span data-stu-id="0dd72-285">public HRESULT [put_ParentWindow](#put_parentwindow)(HWND topLevelWindow)</span></span>

<span data-ttu-id="0dd72-286">これにより、WebView が、新しく指定したウィンドウにウィンドウを再表示します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-286">This will cause the WebView to reparent its window to the newly provided window.</span></span>

#### <span data-ttu-id="0dd72-287">NotifyParentWindowPositionChanged</span><span class="sxs-lookup"><span data-stu-id="0dd72-287">NotifyParentWindowPositionChanged</span></span> 

<span data-ttu-id="0dd72-288">これは、親 (または任意の先祖) HWND を移動したことを示す put_Bounds とは別の通知です。</span><span class="sxs-lookup"><span data-stu-id="0dd72-288">This is a notification separate from put_Bounds that tells WebView its parent (or any ancestor) HWND moved.</span></span>

> <span data-ttu-id="0dd72-289">パブリック HRESULT [NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged)()</span><span class="sxs-lookup"><span data-stu-id="0dd72-289">public HRESULT [NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged)()</span></span>

<span data-ttu-id="0dd72-290">これは、アクセシビリティと、WebView の特定のダイアログで正常に動作するために必要です。</span><span class="sxs-lookup"><span data-stu-id="0dd72-290">This is needed for accessibility and certain dialogs in WebView to work correctly.</span></span> 

```cpp
    if (message == WM_MOVE || message == WM_MOVING)
    {
        m_host->NotifyParentWindowPositionChanged();
        return true;
    }
```

#### <span data-ttu-id="0dd72-291">Close</span><span class="sxs-lookup"><span data-stu-id="0dd72-291">Close</span></span> 

<span data-ttu-id="0dd72-292">WebView を閉じ、基になるブラウザーインスタンスをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="0dd72-292">Closes the WebView and cleans up the underlying browser instance.</span></span>

> <span data-ttu-id="0dd72-293">パブリック HRESULT [Close](#close)()</span><span class="sxs-lookup"><span data-stu-id="0dd72-293">public HRESULT [Close](#close)()</span></span>

<span data-ttu-id="0dd72-294">ブラウザーの instace をクリーンアップすると、WebView に電源が入っているリソースが解放されます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-294">Cleaning up the browser instace will release the resources powering the WebView.</span></span> <span data-ttu-id="0dd72-295">他の WebViews が使用していない場合は、ブラウザーインスタンスがシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-295">The browser instance will be shut down if there are no other WebViews using it.</span></span>

<span data-ttu-id="0dd72-296">Close を呼び出した後、すべてのメソッド呼び出しは失敗し、イベントハンドラーは発生しなくなります。</span><span class="sxs-lookup"><span data-stu-id="0dd72-296">After calling Close, all method calls will fail and event handlers will stop firing.</span></span> <span data-ttu-id="0dd72-297">具体的には、WebView が呼び出されたときに、WebView はそのイベントハンドラーへの参照を解放します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-297">Specifically, the WebView will release its references to its event handlers when Close is called.</span></span>

<span data-ttu-id="0dd72-298">Close は、CoreWebView2Host が最終的な参照を失い、destructed である場合に、暗黙的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-298">Close is implicitly called when the CoreWebView2Host loses its final reference and is destructed.</span></span> <span data-ttu-id="0dd72-299">ただし、WebView とアプリコードの間の参照が誤って循環しないように、明示的に Close を呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0dd72-299">But it is best practice to explicitly call Close to avoid any accidental cycle of references between the WebView and the app code.</span></span> <span data-ttu-id="0dd72-300">具体的には、イベントハンドラーで WebView への参照をキャプチャすると、WebView とイベントハンドラーの間に参照サイクルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="0dd72-300">Specifically, if you capture a reference to the WebView in an event handler you will create a reference cycle between the WebView and the event handler.</span></span> <span data-ttu-id="0dd72-301">Close を呼び出すと、すべてのイベントハンドラーが解放され、このサイクルが停止します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-301">Calling Close will break this cycle by releasing all event handlers.</span></span> <span data-ttu-id="0dd72-302">ただし、このような状況を回避するには、WebView を明示的に呼び出すと共に、webview への参照をキャプチャせずに、webview を正しくクリーンアップできるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0dd72-302">But to avoid this situation it is best practice both to explicitly call Close on the WebView and to not capture a reference to the WebView to ensure the WebView can be cleaned up correctly.</span></span>

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

#### <span data-ttu-id="0dd72-303">get_CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="0dd72-303">get_CoreWebView2</span></span> 

<span data-ttu-id="0dd72-304">この CoreWebView2Host に関連付けられている CoreWebView2 を取得します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-304">Gets the CoreWebView2 associated with this CoreWebView2Host.</span></span>

> <span data-ttu-id="0dd72-305">パブリック HRESULT [get_CoreWebView2](#get_corewebview2)([ICoreWebView2](ICoreWebView2.md) \* \* CoreWebView2)</span><span class="sxs-lookup"><span data-stu-id="0dd72-305">public HRESULT [get_CoreWebView2](#get_corewebview2)([ICoreWebView2](ICoreWebView2.md) \*\* coreWebView2)</span></span>

#### <span data-ttu-id="0dd72-306">CORE_WEBVIEW2_MOVE_FOCUS_REASON</span><span class="sxs-lookup"><span data-stu-id="0dd72-306">CORE_WEBVIEW2_MOVE_FOCUS_REASON</span></span> 

<span data-ttu-id="0dd72-307">フォーカスを移動する理由。</span><span class="sxs-lookup"><span data-stu-id="0dd72-307">Reason for moving focus.</span></span>

> <span data-ttu-id="0dd72-308">列挙型[CORE_WEBVIEW2_MOVE_FOCUS_REASON](#core_webview2_move_focus_reason)</span><span class="sxs-lookup"><span data-stu-id="0dd72-308">enum [CORE_WEBVIEW2_MOVE_FOCUS_REASON](#core_webview2_move_focus_reason)</span></span>

 <span data-ttu-id="0dd72-309">値</span><span class="sxs-lookup"><span data-stu-id="0dd72-309">Values</span></span>                         | <span data-ttu-id="0dd72-310">説明</span><span class="sxs-lookup"><span data-stu-id="0dd72-310">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="0dd72-311">CORE_WEBVIEW2_MOVE_FOCUS_REASON_PROGRAMMATIC</span><span class="sxs-lookup"><span data-stu-id="0dd72-311">CORE_WEBVIEW2_MOVE_FOCUS_REASON_PROGRAMMATIC</span></span>            | <span data-ttu-id="0dd72-312">コード設定による WebView へのフォーカス。</span><span class="sxs-lookup"><span data-stu-id="0dd72-312">Code setting focus into WebView.</span></span>
<span data-ttu-id="0dd72-313">CORE_WEBVIEW2_MOVE_FOCUS_REASON_NEXT</span><span class="sxs-lookup"><span data-stu-id="0dd72-313">CORE_WEBVIEW2_MOVE_FOCUS_REASON_NEXT</span></span>            | <span data-ttu-id="0dd72-314">タブトラバーサルを前方に移動するためにフォーカスを移動する。</span><span class="sxs-lookup"><span data-stu-id="0dd72-314">Moving focus due to Tab traversal forward.</span></span>
<span data-ttu-id="0dd72-315">CORE_WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS</span><span class="sxs-lookup"><span data-stu-id="0dd72-315">CORE_WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS</span></span>            | <span data-ttu-id="0dd72-316">タブトラバーサルに戻るためにフォーカスを移動する。</span><span class="sxs-lookup"><span data-stu-id="0dd72-316">Moving focus due to Tab traversal backward.</span></span>

#### <span data-ttu-id="0dd72-317">CORE_WEBVIEW2_KEY_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="0dd72-317">CORE_WEBVIEW2_KEY_EVENT_KIND</span></span> 

<span data-ttu-id="0dd72-318">AcceleratorKeyPressed イベントをトリガーしたキーイベントの種類です。</span><span class="sxs-lookup"><span data-stu-id="0dd72-318">The type of key event that triggered an AcceleratorKeyPressed event.</span></span>

> <span data-ttu-id="0dd72-319">列挙型[CORE_WEBVIEW2_KEY_EVENT_KIND](#core_webview2_key_event_kind)</span><span class="sxs-lookup"><span data-stu-id="0dd72-319">enum [CORE_WEBVIEW2_KEY_EVENT_KIND](#core_webview2_key_event_kind)</span></span>

 <span data-ttu-id="0dd72-320">値</span><span class="sxs-lookup"><span data-stu-id="0dd72-320">Values</span></span>                         | <span data-ttu-id="0dd72-321">説明</span><span class="sxs-lookup"><span data-stu-id="0dd72-321">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="0dd72-322">CORE_WEBVIEW2_KEY_EVENT_KIND_KEY_DOWN</span><span class="sxs-lookup"><span data-stu-id="0dd72-322">CORE_WEBVIEW2_KEY_EVENT_KIND_KEY_DOWN</span></span>            | <span data-ttu-id="0dd72-323">ウィンドウメッセージ WM_KEYDOWN に対応します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-323">Correspond to window message WM_KEYDOWN.</span></span>
<span data-ttu-id="0dd72-324">CORE_WEBVIEW2_KEY_EVENT_KIND_KEY_UP</span><span class="sxs-lookup"><span data-stu-id="0dd72-324">CORE_WEBVIEW2_KEY_EVENT_KIND_KEY_UP</span></span>            | <span data-ttu-id="0dd72-325">ウィンドウメッセージ WM_KEYUP に対応します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-325">Correspond to window message WM_KEYUP.</span></span>
<span data-ttu-id="0dd72-326">CORE_WEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_DOWN</span><span class="sxs-lookup"><span data-stu-id="0dd72-326">CORE_WEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_DOWN</span></span>            | <span data-ttu-id="0dd72-327">ウィンドウメッセージ WM_SYSKEYDOWN に対応します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-327">Correspond to window message WM_SYSKEYDOWN.</span></span>
<span data-ttu-id="0dd72-328">CORE_WEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_UP</span><span class="sxs-lookup"><span data-stu-id="0dd72-328">CORE_WEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_UP</span></span>            | <span data-ttu-id="0dd72-329">ウィンドウメッセージ WM_SYSKEYUP に対応します。</span><span class="sxs-lookup"><span data-stu-id="0dd72-329">Correspond to window message WM_SYSKEYUP.</span></span>

#### <span data-ttu-id="0dd72-330">CORE_WEBVIEW2_PHYSICAL_KEY_STATUS</span><span class="sxs-lookup"><span data-stu-id="0dd72-330">CORE_WEBVIEW2_PHYSICAL_KEY_STATUS</span></span> 

<span data-ttu-id="0dd72-331">Win32 キーイベントに指定された LPARAM にパックされた情報を表す構造体。</span><span class="sxs-lookup"><span data-stu-id="0dd72-331">A structure representing the information packed into the LPARAM given to a Win32 key event.</span></span>

> <span data-ttu-id="0dd72-332">typedef [CORE_WEBVIEW2_PHYSICAL_KEY_STATUS](#core_webview2_physical_key_status)</span><span class="sxs-lookup"><span data-stu-id="0dd72-332">typedef [CORE_WEBVIEW2_PHYSICAL_KEY_STATUS](#core_webview2_physical_key_status)</span></span>

<span data-ttu-id="0dd72-333">詳細については、WM_KEYDOWN のドキュメントを参照してください。[https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown)</span><span class="sxs-lookup"><span data-stu-id="0dd72-333">See the documentation for WM_KEYDOWN for details at [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown)</span></span>

