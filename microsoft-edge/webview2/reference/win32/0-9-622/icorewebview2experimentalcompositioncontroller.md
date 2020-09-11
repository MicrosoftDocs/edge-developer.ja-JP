---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 Win32 C++ ICoreWebView2ExperimentalCompositionController
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html、ICoreWebView2ExperimentalCompositionController
ms.openlocfilehash: bf73ce6a5e3a1171bf731e953c3016f9baea2ff1
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012278"
---
# <span data-ttu-id="c8303-104">インターフェイス ICoreWebView2ExperimentalCompositionController</span><span class="sxs-lookup"><span data-stu-id="c8303-104">interface ICoreWebView2ExperimentalCompositionController</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalCompositionController
  : public IUnknown
```

<span data-ttu-id="c8303-105">このインターフェイスは、 [ICoreWebView2Controller](icorewebview2controller.md) インターフェイスの拡張機能であり、ビジュアルホストをサポートします。</span><span class="sxs-lookup"><span data-stu-id="c8303-105">This interface is an extension of the [ICoreWebView2Controller](icorewebview2controller.md) interface to support visual hosting.</span></span>

## <span data-ttu-id="c8303-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="c8303-106">Summary</span></span>

 <span data-ttu-id="c8303-107">Members</span><span class="sxs-lookup"><span data-stu-id="c8303-107">Members</span></span>                        | <span data-ttu-id="c8303-108">説明</span><span class="sxs-lookup"><span data-stu-id="c8303-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c8303-109">add_CursorChanged</span><span class="sxs-lookup"><span data-stu-id="c8303-109">add_CursorChanged</span></span>](#add_cursorchanged) | <span data-ttu-id="c8303-110">カーソル変更イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="c8303-110">Add an event handler for the CursorChanged event.</span></span>
[<span data-ttu-id="c8303-111">CreateCoreWebView2PointerInfoFromPointerId</span><span class="sxs-lookup"><span data-stu-id="c8303-111">CreateCoreWebView2PointerInfoFromPointerId</span></span>](#createcorewebview2pointerinfofrompointerid) | <span data-ttu-id="c8303-112">システムから受け取ったポインター Id を [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)に変換するヘルパー関数。</span><span class="sxs-lookup"><span data-stu-id="c8303-112">A helper function to convert a pointerId received from the system into an [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md).</span></span>
[<span data-ttu-id="c8303-113">get_Cursor</span><span class="sxs-lookup"><span data-stu-id="c8303-113">get_Cursor</span></span>](#get_cursor) | <span data-ttu-id="c8303-114">WebView で現在のカーソルの位置を判断します。</span><span class="sxs-lookup"><span data-stu-id="c8303-114">The current cursor that WebView thinks it should be.</span></span>
[<span data-ttu-id="c8303-115">get_RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="c8303-115">get_RootVisualTarget</span></span>](#get_rootvisualtarget) | <span data-ttu-id="c8303-116">RootVisualTarget は、ホストアプリのビジュアルツリー内のビジュアルです。</span><span class="sxs-lookup"><span data-stu-id="c8303-116">The RootVisualTarget is a visual in the hosting app's visual tree.</span></span>
[<span data-ttu-id="c8303-117">get_UIAProvider</span><span class="sxs-lookup"><span data-stu-id="c8303-117">get_UIAProvider</span></span>](#get_uiaprovider) | <span data-ttu-id="c8303-118">WebView の UI オートメーションプロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="c8303-118">Returns the UI Automation Provider for the WebView.</span></span>
[<span data-ttu-id="c8303-119">put_RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="c8303-119">put_RootVisualTarget</span></span>](#put_rootvisualtarget) | <span data-ttu-id="c8303-120">RootVisualTarget プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="c8303-120">Set the RootVisualTarget property.</span></span>
[<span data-ttu-id="c8303-121">remove_CursorChanged</span><span class="sxs-lookup"><span data-stu-id="c8303-121">remove_CursorChanged</span></span>](#remove_cursorchanged) | <span data-ttu-id="c8303-122">Add_CursorChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c8303-122">Remove an event handler previously added with add_CursorChanged.</span></span>
[<span data-ttu-id="c8303-123">SendMouseInput</span><span class="sxs-lookup"><span data-stu-id="c8303-123">SendMouseInput</span></span>](#sendmouseinput) | <span data-ttu-id="c8303-124">EventKind が COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL または COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL の場合、mouseData は、WHEEL の動きの量を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8303-124">If eventKind is COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL or COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL, then mouseData specifies the amount of wheel movement.</span></span>
[<span data-ttu-id="c8303-125">Sendポインタ入力</span><span class="sxs-lookup"><span data-stu-id="c8303-125">SendPointerInput</span></span>](#sendpointerinput) | <span data-ttu-id="c8303-126">Sendpointer 入力は、COREWEBVIEW2_POINTER_EVENT_KIND で定義された型のタッチポインターまたはペンポインターの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="c8303-126">SendPointerInput accepts touch or pen pointer input of types defined in COREWEBVIEW2_POINTER_EVENT_KIND.</span></span>
[<span data-ttu-id="c8303-127">COREWEBVIEW2_MATRIX_4X4</span><span class="sxs-lookup"><span data-stu-id="c8303-127">COREWEBVIEW2_MATRIX_4X4</span></span>](#corewebview2_matrix_4x4) | <span data-ttu-id="c8303-128">3D 変換を表すマトリックス。</span><span class="sxs-lookup"><span data-stu-id="c8303-128">Matrix that represents a 3D transform.</span></span>
[<span data-ttu-id="c8303-129">COREWEBVIEW2_MOUSE_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="c8303-129">COREWEBVIEW2_MOUSE_EVENT_KIND</span></span>](#corewebview2_mouse_event_kind) | <span data-ttu-id="c8303-130">WebView に送信されるマウスイベントの種類を伝えるために、SendMouseInput で使われるマウスイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="c8303-130">Mouse event type used by SendMouseInput to convey the type of mouse event being sent to WebView.</span></span>
[<span data-ttu-id="c8303-131">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS</span><span class="sxs-lookup"><span data-stu-id="c8303-131">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS</span></span>](#corewebview2_mouse_event_virtual_keys) | <span data-ttu-id="c8303-132">SendMouseInput の COREWEBVIEW2_MOUSE_EVENT_KIND に関連付けられたマウスイベントの仮想キー。</span><span class="sxs-lookup"><span data-stu-id="c8303-132">Mouse event virtual keys associated with a COREWEBVIEW2_MOUSE_EVENT_KIND for SendMouseInput.</span></span>
[<span data-ttu-id="c8303-133">COREWEBVIEW2_POINTER_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="c8303-133">COREWEBVIEW2_POINTER_EVENT_KIND</span></span>](#corewebview2_pointer_event_kind) | <span data-ttu-id="c8303-134">WebView に送信されるポインターイベントの種類を伝えるために Sendpointer 入力で使われるポインターイベントの種類です。</span><span class="sxs-lookup"><span data-stu-id="c8303-134">Pointer event type used by SendPointerInput to convey the type of pointer event being sent to WebView.</span></span>

<span data-ttu-id="c8303-135">ICoreWebView2ExperimentalCompositionController インターフェイスを実装するオブジェクトも [ICoreWebView2Controller](icorewebview2controller.md)を実装します。</span><span class="sxs-lookup"><span data-stu-id="c8303-135">An object implementing the ICoreWebView2ExperimentalCompositionController interface will also implement [ICoreWebView2Controller](icorewebview2controller.md).</span></span> <span data-ttu-id="c8303-136">呼び出し元は、サイズ変更、visibility、フォーカスなどのために [ICoreWebView2Controller](icorewebview2controller.md) を使うことを前提としており、ICoreWebView2ExperimentalCompositionController を使ってコンポジションツリーに接続し、WebView 用の入力を提供します。</span><span class="sxs-lookup"><span data-stu-id="c8303-136">Callers are expected to use [ICoreWebView2Controller](icorewebview2controller.md) for resizing, visibility, focus, and so on, and then use ICoreWebView2ExperimentalCompositionController to connect to a composition tree and provide input meant for the WebView.</span></span>

## <span data-ttu-id="c8303-137">Members</span><span class="sxs-lookup"><span data-stu-id="c8303-137">Members</span></span>

#### <span data-ttu-id="c8303-138">add_CursorChanged</span><span class="sxs-lookup"><span data-stu-id="c8303-138">add_CursorChanged</span></span> 

<span data-ttu-id="c8303-139">カーソル変更イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="c8303-139">Add an event handler for the CursorChanged event.</span></span>

> <span data-ttu-id="c8303-140">パブリック HRESULT [add_CursorChanged](#add_cursorchanged)([ICoreWebView2ExperimentalCursorChangedEventHandler](icorewebview2experimentalcursorchangedeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="c8303-140">public HRESULT [add_CursorChanged](#add_cursorchanged)([ICoreWebView2ExperimentalCursorChangedEventHandler](icorewebview2experimentalcursorchangedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="c8303-141">WebView がカーソルの変更であると判断されたときに、イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="c8303-141">The event fires when WebView thinks the cursor should be changed.</span></span> <span data-ttu-id="c8303-142">たとえば、マウスカーソルが現在既定のカーソルであり、テキストの上に移動した場合は、IBeam カーソルに変更しようとすることがあります。</span><span class="sxs-lookup"><span data-stu-id="c8303-142">For example, when the mouse cursor is currently the default cursor but is then moved over text, it may try to change to the IBeam cursor.</span></span>

<span data-ttu-id="c8303-143">送信者は、SendMouseInput API を介して COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE メッセージ (COREWEBVIEW2_MOUSE_EVENT_KIND_MOVE メッセージに加えて) を送信することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c8303-143">It is expected for the developer to send COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE messages (in addition to COREWEBVIEW2_MOUSE_EVENT_KIND_MOVE messages) through the SendMouseInput API.</span></span> <span data-ttu-id="c8303-144">これは、カーソルの変更されたイベントを送信する WebView 内に実際にマウスがあることを確認するためです。</span><span class="sxs-lookup"><span data-stu-id="c8303-144">This is to ensure that the mouse is actually within the WebView that sends out CursorChanged events.</span></span>

```cpp
        // Register a handler for the CursorChanged event.
        CHECK_FAILURE(m_compositionController->add_CursorChanged(
            Callback<ICoreWebView2ExperimentalCursorChangedEventHandler>(
                [this](ICoreWebView2ExperimentalCompositionController* sender, IUnknown* args)
                    -> HRESULT {
                    HRESULT hr = S_OK;
                    HCURSOR cursor;
                        CHECK_FAILURE(sender->get_Cursor(&cursor));
                    if (SUCCEEDED(hr))
                    {
                        SetClassLongPtr(
                            m_appWindow->GetMainWindow(), GCLP_HCURSOR, (LONG_PTR)cursor);
                    }
                    return hr;
                })
                .Get(),
            &m_cursorChangedToken));
```

#### <span data-ttu-id="c8303-145">CreateCoreWebView2PointerInfoFromPointerId</span><span class="sxs-lookup"><span data-stu-id="c8303-145">CreateCoreWebView2PointerInfoFromPointerId</span></span> 

<span data-ttu-id="c8303-146">システムから受け取ったポインター Id を [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)に変換するヘルパー関数。</span><span class="sxs-lookup"><span data-stu-id="c8303-146">A helper function to convert a pointerId received from the system into an [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md).</span></span>

> <span data-ttu-id="c8303-147">パブリック HRESULT [CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid)(UINT ポインター ID、HWND parentwindow、struct COREWEBVIEW2_MATRIX_4X4 Transform、 [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \* \* ポインター情報)</span><span class="sxs-lookup"><span data-stu-id="c8303-147">public HRESULT [CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid)(UINT pointerId, HWND parentWindow, struct COREWEBVIEW2_MATRIX_4X4 transform, [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \*\* pointerInfo)</span></span>

<span data-ttu-id="c8303-148">parentWindow は、webview を含む HWND です。</span><span class="sxs-lookup"><span data-stu-id="c8303-148">parentWindow is the HWND that contains the webview.</span></span> <span data-ttu-id="c8303-149">これは、webview を含む hwnd ツリー内の任意の HWND にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c8303-149">This can be any HWND in the hwnd tree that contains the webview.</span></span> <span data-ttu-id="c8303-150">COREWEBVIEW2_MATRIX_4X4 は、その HWND から webview への変換です。</span><span class="sxs-lookup"><span data-stu-id="c8303-150">The COREWEBVIEW2_MATRIX_4X4 is the transform from that HWND to the webview.</span></span> <span data-ttu-id="c8303-151">返された [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) は、Sendポインタ info で使われます。</span><span class="sxs-lookup"><span data-stu-id="c8303-151">The returned [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) is used in SendPointerInfo.</span></span> <span data-ttu-id="c8303-152">ポインターの型は、ペンまたはタッチである必要があります。または、関数は失敗します。</span><span class="sxs-lookup"><span data-stu-id="c8303-152">The pointer type must be either pen or touch or the function will fail.</span></span>

#### <span data-ttu-id="c8303-153">get_Cursor</span><span class="sxs-lookup"><span data-stu-id="c8303-153">get_Cursor</span></span> 

<span data-ttu-id="c8303-154">WebView で現在のカーソルの位置を判断します。</span><span class="sxs-lookup"><span data-stu-id="c8303-154">The current cursor that WebView thinks it should be.</span></span>

> <span data-ttu-id="c8303-155">パブリック HRESULT [get_Cursor](#get_cursor)(hcursor \* cursor)</span><span class="sxs-lookup"><span data-stu-id="c8303-155">public HRESULT [get_Cursor](#get_cursor)(HCURSOR \* cursor)</span></span>

<span data-ttu-id="c8303-156">カーソルは WM_SETCURSOR スルー:: SetCursor で設定するか、WebView ~:: SetClassLongPtr の対応する親または先祖の HWND で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8303-156">The cursor should be set in WM_SETCURSOR through ::SetCursor or set on the corresponding parent/ancestor HWND of the WebView through ::SetClassLongPtr.</span></span> <span data-ttu-id="c8303-157">HCURSOR を解放すると、カーソルをすぐに設定するよりも、コピーを保持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c8303-157">The HCURSOR can be freed so CopyCursor/DestroyCursor is recommended to keep your own copy if you are doing more than immediately setting the cursor.</span></span>

#### <span data-ttu-id="c8303-158">get_RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="c8303-158">get_RootVisualTarget</span></span> 

<span data-ttu-id="c8303-159">RootVisualTarget は、ホストアプリのビジュアルツリー内のビジュアルです。</span><span class="sxs-lookup"><span data-stu-id="c8303-159">The RootVisualTarget is a visual in the hosting app's visual tree.</span></span>

> <span data-ttu-id="c8303-160">パブリック HRESULT [get_RootVisualTarget](#get_rootvisualtarget)(IUnknown \* \* target)</span><span class="sxs-lookup"><span data-stu-id="c8303-160">public HRESULT [get_RootVisualTarget](#get_rootvisualtarget)(IUnknown \*\* target)</span></span>

<span data-ttu-id="c8303-161">このビジュアルは、WebView がそのビジュアルツリーを接続する場所です。</span><span class="sxs-lookup"><span data-stu-id="c8303-161">This visual is where the WebView will connect its visual tree.</span></span> <span data-ttu-id="c8303-162">アプリでは、このビジュアルを使って、アプリ内で WebView を配置します。</span><span class="sxs-lookup"><span data-stu-id="c8303-162">The app uses this visual to position the WebView within the app.</span></span> <span data-ttu-id="c8303-163">この場合も、アプリでは、境界プロパティを使って WebView のサイズを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8303-163">The app still needs to use the Bounds property to size the WebView.</span></span> <span data-ttu-id="c8303-164">RootVisualTarget プロパティは、IDCompositionVisual または Windows:: UI:: コンポジション:: ContainerVisual とすることができます。</span><span class="sxs-lookup"><span data-stu-id="c8303-164">The RootVisualTarget property can be an IDCompositionVisual or a Windows::UI::Composition::ContainerVisual.</span></span> <span data-ttu-id="c8303-165">WebView は、プロパティ setter から戻る前に、ビジュアルツリーを提供された visual に接続します。</span><span class="sxs-lookup"><span data-stu-id="c8303-165">WebView will connect its visual tree to the provided visual before returning from the property setter.</span></span> <span data-ttu-id="c8303-166">アプリは、Root Visualtarget プロパティのデバイス設定でコミットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8303-166">The app needs to commit on its device setting the RootVisualTarget property.</span></span> <span data-ttu-id="c8303-167">RootVisualTarget プロパティは、アプリのビジュアルツリーから WebView を切断するために nullptr に設定されています。</span><span class="sxs-lookup"><span data-stu-id="c8303-167">The RootVisualTarget property supports being set to nullptr to disconnect the WebView from the app's visual tree.</span></span> 
```cpp
            // Set the host app visual that the WebView will connect its visual
            // tree to.
            BuildDCompTreeUsingVisual();
            if (m_isDcompTargetMode)
            {
                if (!m_dcompTarget)
                {
                    m_dcompTarget = Make<DCompTargetImpl>(this);
                }
                CHECK_FAILURE(
                    m_compositionController->put_RootVisualTarget(m_dcompTarget.get()));
            }
            else
            {
                CHECK_FAILURE(
                    m_compositionController->put_RootVisualTarget(m_dcompWebViewVisual.get()));
            }
            CHECK_FAILURE(m_dcompDevice->Commit());
```

```cpp
// Create host app visual that the WebView will connect to.
//   - Create a IDCompositionTarget for the host window
//   - Create a visual and set that as the IDCompositionTarget's root
//   - Create another visual and add that to the IDCompositionTarget's root.
//     This visual will be the visual root for the WebView.
void ViewComponent::BuildDCompTreeUsingVisual()
{
    CHECK_FAILURE_BOOL(m_dcompDevice != nullptr);

    if (m_dcompWebViewVisual == nullptr)
    {
        CHECK_FAILURE(m_dcompDevice->CreateTargetForHwnd(
            m_appWindow->GetMainWindow(), TRUE, &m_dcompHwndTarget));
        CHECK_FAILURE(m_dcompDevice->CreateVisual(&m_dcompRootVisual));
        CHECK_FAILURE(m_dcompHwndTarget->SetRoot(m_dcompRootVisual.get()));
        CHECK_FAILURE(m_dcompDevice->CreateVisual(&m_dcompWebViewVisual));
        CHECK_FAILURE(m_dcompRootVisual->AddVisual(m_dcompWebViewVisual.get(), TRUE, nullptr));
    }
}
```

#### <span data-ttu-id="c8303-168">get_UIAProvider</span><span class="sxs-lookup"><span data-stu-id="c8303-168">get_UIAProvider</span></span> 

<span data-ttu-id="c8303-169">WebView の UI オートメーションプロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="c8303-169">Returns the UI Automation Provider for the WebView.</span></span>

> <span data-ttu-id="c8303-170">パブリック HRESULT [get_UIAProvider](#get_uiaprovider)(IUnknown \* \* provider)</span><span class="sxs-lookup"><span data-stu-id="c8303-170">public HRESULT [get_UIAProvider](#get_uiaprovider)(IUnknown \*\* provider)</span></span>

#### <span data-ttu-id="c8303-171">put_RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="c8303-171">put_RootVisualTarget</span></span> 

<span data-ttu-id="c8303-172">RootVisualTarget プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="c8303-172">Set the RootVisualTarget property.</span></span>

> <span data-ttu-id="c8303-173">パブリック HRESULT [put_RootVisualTarget](#put_rootvisualtarget)(IUnknown \* ターゲット)</span><span class="sxs-lookup"><span data-stu-id="c8303-173">public HRESULT [put_RootVisualTarget](#put_rootvisualtarget)(IUnknown \* target)</span></span>

#### <span data-ttu-id="c8303-174">remove_CursorChanged</span><span class="sxs-lookup"><span data-stu-id="c8303-174">remove_CursorChanged</span></span> 

<span data-ttu-id="c8303-175">Add_CursorChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c8303-175">Remove an event handler previously added with add_CursorChanged.</span></span>

> <span data-ttu-id="c8303-176">パブリック HRESULT [remove_CursorChanged](#remove_cursorchanged)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="c8303-176">public HRESULT [remove_CursorChanged](#remove_cursorchanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="c8303-177">SendMouseInput</span><span class="sxs-lookup"><span data-stu-id="c8303-177">SendMouseInput</span></span> 

<span data-ttu-id="c8303-178">EventKind が COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL または COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL の場合、mouseData は、WHEEL の動きの量を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8303-178">If eventKind is COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL or COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL, then mouseData specifies the amount of wheel movement.</span></span>

> <span data-ttu-id="c8303-179">パブリック HRESULT 送信 [マウス入力](#sendmouseinput)([COREWEBVIEW2_MOUSE_EVENT_KIND](#corewebview2_mouse_event_kind) eventkind、 [COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS](#corewebview2_mouse_event_virtual_keys) VIRTUALKEYS、UINT32 mousedata、ポイントポイント)</span><span class="sxs-lookup"><span data-stu-id="c8303-179">public HRESULT [SendMouseInput](#sendmouseinput)([COREWEBVIEW2_MOUSE_EVENT_KIND](#corewebview2_mouse_event_kind) eventKind, [COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS](#corewebview2_mouse_event_virtual_keys) virtualKeys, UINT32 mouseData, POINT point)</span></span>

<span data-ttu-id="c8303-180">正の値は、ホイールがユーザーによって前方に回転されたことを示します。負の値は、ホイールが背面に回転していることを示します。</span><span class="sxs-lookup"><span data-stu-id="c8303-180">A positive value indicates that the wheel was rotated forward, away from the user; a negative value indicates that the wheel was rotated backward, toward the user.</span></span> <span data-ttu-id="c8303-181">ホイールクリックの1つは、120として定義されている WHEEL_DELTA として定義されています。</span><span class="sxs-lookup"><span data-stu-id="c8303-181">One wheel click is defined as WHEEL_DELTA, which is 120.</span></span> <span data-ttu-id="c8303-182">EventKind が COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOUBLE_CLICK COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOWN、または COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_UP の場合、mouseData は、どの X ボタンが押されたか、離されたかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8303-182">If eventKind is COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOUBLE_CLICK COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOWN, or COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_UP, then mouseData specifies which X buttons were pressed or released.</span></span> <span data-ttu-id="c8303-183">この値は、最初の X ボタンが押されている場合は1、2番目の X ボタンが押されたとき、または離された場合は1になります。</span><span class="sxs-lookup"><span data-stu-id="c8303-183">This value should be 1 if the first X button is pressed/released and 2 if the second X button is pressed/released.</span></span> <span data-ttu-id="c8303-184">EventKind が COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE の場合、virtualKeys、mouseData、point はすべてゼロである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8303-184">If eventKind is COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE, then virtualKeys, mouseData, and point should all be zero.</span></span> <span data-ttu-id="c8303-185">EventKind がその他の値である場合は、mouseData は0である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8303-185">If eventKind is any other value, then mouseData should be zero.</span></span> <span data-ttu-id="c8303-186">Point は、WebView のクライアント座標空間に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8303-186">Point is expected to be in the client coordinate space of the WebView.</span></span> <span data-ttu-id="c8303-187">WebView から始まり、WebView とホストアプリケーションの外側に移動する可能性のあるマウスイベントを追跡するには、SetCapture と ReleaseCapture の呼び出しをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c8303-187">To track mouse events that start in the WebView and can potentially move outside of the WebView and host application, calling SetCapture and ReleaseCapture is recommended.</span></span> <span data-ttu-id="c8303-188">ホバーポップアップを消すには、COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE メッセージを送信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c8303-188">To dismiss hover popups, it is also recommended to send COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE messages.</span></span> 
```cpp
bool ViewComponent::OnMouseMessage(UINT message, WPARAM wParam, LPARAM lParam)
{
    // Manually relay mouse messages to the WebView
#ifdef USE_WEBVIEW2_WIN10
    if (m_dcompDevice || m_wincompCompositor)
#else
    if (m_dcompDevice)
#endif
    {
        POINT point;
        POINTSTOPOINT(point, lParam);
        if (message == WM_MOUSEWHEEL || message == WM_MOUSEHWHEEL)
        {
            // Mouse wheel messages are delivered in screen coordinates.
            // SendMouseInput expects client coordinates for the WebView, so convert
            // the point from screen to client.
            ::ScreenToClient(m_appWindow->GetMainWindow(), &point);
        }
        // Send the message to the WebView if the mouse location is inside the
        // bounds of the WebView, if the message is telling the WebView the
        // mouse has left the client area, or if we are currently capturing
        // mouse events.
        bool isMouseInWebView = PtInRect(&m_webViewBounds, point);
        if (isMouseInWebView || message == WM_MOUSELEAVE || m_isCapturingMouse)
        {
            DWORD mouseData = 0;

            switch (message)
            {
            case WM_MOUSEWHEEL:
            case WM_MOUSEHWHEEL:
                mouseData = GET_WHEEL_DELTA_WPARAM(wParam);
                break;
            case WM_XBUTTONDBLCLK:
            case WM_XBUTTONDOWN:
            case WM_XBUTTONUP:
                mouseData = GET_XBUTTON_WPARAM(wParam);
                break;
            case WM_MOUSEMOVE:
                if (!m_isTrackingMouse)
                {
                    // WebView needs to know when the mouse leaves the client area
                    // so that it can dismiss hover popups. TrackMouseEvent will
                    // provide a notification when the mouse leaves the client area.
                    TrackMouseEvents(TME_LEAVE);
                    m_isTrackingMouse = true;
                }
                break;
            case WM_MOUSELEAVE:
                m_isTrackingMouse = false;
                break;
            }

            // We need to capture the mouse in case the user drags the
            // mouse outside of the window bounds and we still need to send
            // mouse messages to the WebView process. This is useful for
            // scenarios like dragging the scroll bar or panning a map.
            // This is very similar to the Pointer Message case where a
            // press started inside of the WebView.
            if (message == WM_LBUTTONDOWN || message == WM_MBUTTONDOWN ||
                message == WM_RBUTTONDOWN || message == WM_XBUTTONDOWN)
            {
                if (isMouseInWebView && ::GetCapture() != m_appWindow->GetMainWindow())
                {
                    m_isCapturingMouse = true;
                    ::SetCapture(m_appWindow->GetMainWindow());
                }
            }
            else if (message == WM_LBUTTONUP || message == WM_MBUTTONUP ||
                message == WM_RBUTTONUP || message == WM_XBUTTONUP)
            {
                if (::GetCapture() == m_appWindow->GetMainWindow())
                {
                    m_isCapturingMouse = false;
                    ::ReleaseCapture();
                }
            }

            // Adjust the point from app client coordinates to webview client coordinates.
            // WM_MOUSELEAVE messages don't have a point, so don't adjust the point.
            if (message != WM_MOUSELEAVE)
            {
                point.x -= m_webViewBounds.left;
                point.y -= m_webViewBounds.top;
            }

            CHECK_FAILURE(m_compositionController->SendMouseInput(
                static_cast<COREWEBVIEW2_MOUSE_EVENT_KIND>(message),
                static_cast<COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS>(GET_KEYSTATE_WPARAM(wParam)),
                mouseData, point));
            return true;
        }
        else if (message == WM_MOUSEMOVE && m_isTrackingMouse)
        {
            // When the mouse moves outside of the WebView, but still inside the app
            // turn off mouse tracking and send the WebView a leave event.
            m_isTrackingMouse = false;
            TrackMouseEvents(TME_LEAVE | TME_CANCEL);
            OnMouseMessage(WM_MOUSELEAVE, 0, 0);
        }
    }
    return false;
}
```

#### <span data-ttu-id="c8303-189">Sendポインタ入力</span><span class="sxs-lookup"><span data-stu-id="c8303-189">SendPointerInput</span></span> 

<span data-ttu-id="c8303-190">Sendpointer 入力は、COREWEBVIEW2_POINTER_EVENT_KIND で定義された型のタッチポインターまたはペンポインターの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="c8303-190">SendPointerInput accepts touch or pen pointer input of types defined in COREWEBVIEW2_POINTER_EVENT_KIND.</span></span>

> <span data-ttu-id="c8303-191">パブリック HRESULT 送信 [ポインター入力](#sendpointerinput)([COREWEBVIEW2_POINTER_EVENT_KIND](#corewebview2_pointer_event_kind) eventkind, [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \* のポインター情報)</span><span class="sxs-lookup"><span data-stu-id="c8303-191">public HRESULT [SendPointerInput](#sendpointerinput)([COREWEBVIEW2_POINTER_EVENT_KIND](#corewebview2_pointer_event_kind) eventKind, [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \* pointerInfo)</span></span>

<span data-ttu-id="c8303-192">システムからのポインター入力は、最初に [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8303-192">Any pointer input from the system must be converted into an [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) first.</span></span>

#### <span data-ttu-id="c8303-193">COREWEBVIEW2_MATRIX_4X4</span><span class="sxs-lookup"><span data-stu-id="c8303-193">COREWEBVIEW2_MATRIX_4X4</span></span> 

<span data-ttu-id="c8303-194">3D 変換を表すマトリックス。</span><span class="sxs-lookup"><span data-stu-id="c8303-194">Matrix that represents a 3D transform.</span></span>

> <span data-ttu-id="c8303-195">typedef [COREWEBVIEW2_MATRIX_4X4](#corewebview2_matrix_4x4)</span><span class="sxs-lookup"><span data-stu-id="c8303-195">typedef [COREWEBVIEW2_MATRIX_4X4](#corewebview2_matrix_4x4)</span></span>

<span data-ttu-id="c8303-196">この変換は、CreateCoreWebView2PointerInfoFromPointerId を呼び出したときに適切な座標を計算するために使われます。</span><span class="sxs-lookup"><span data-stu-id="c8303-196">This transform is used to calculate correct coordinates when calling CreateCoreWebView2PointerInfoFromPointerId.</span></span> <span data-ttu-id="c8303-197">これは D2D1_MATRIX_4X4_F と同じです。</span><span class="sxs-lookup"><span data-stu-id="c8303-197">This is equivalent to a D2D1_MATRIX_4X4_F</span></span>

#### <span data-ttu-id="c8303-198">COREWEBVIEW2_MOUSE_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="c8303-198">COREWEBVIEW2_MOUSE_EVENT_KIND</span></span> 

<span data-ttu-id="c8303-199">WebView に送信されるマウスイベントの種類を伝えるために、SendMouseInput で使われるマウスイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="c8303-199">Mouse event type used by SendMouseInput to convey the type of mouse event being sent to WebView.</span></span>

> <span data-ttu-id="c8303-200">列挙型 [COREWEBVIEW2_MOUSE_EVENT_KIND](#corewebview2_mouse_event_kind)</span><span class="sxs-lookup"><span data-stu-id="c8303-200">enum [COREWEBVIEW2_MOUSE_EVENT_KIND](#corewebview2_mouse_event_kind)</span></span>

 <span data-ttu-id="c8303-201">値</span><span class="sxs-lookup"><span data-stu-id="c8303-201">Values</span></span>                         | <span data-ttu-id="c8303-202">説明</span><span class="sxs-lookup"><span data-stu-id="c8303-202">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="c8303-203">COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL</span><span class="sxs-lookup"><span data-stu-id="c8303-203">COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL</span></span>            | <span data-ttu-id="c8303-204">マウスの水平ホイールスクロールイベント、WM_MOUSEHWHEEL。</span><span class="sxs-lookup"><span data-stu-id="c8303-204">Mouse horizontal wheel scroll event, WM_MOUSEHWHEEL.</span></span>
<span data-ttu-id="c8303-205">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_DOUBLE_CLICK</span><span class="sxs-lookup"><span data-stu-id="c8303-205">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_DOUBLE_CLICK</span></span>            | <span data-ttu-id="c8303-206">[左] ボタンをダブルクリックすると、[マウスイベント] が WM_LBUTTONDBLCLK ます。</span><span class="sxs-lookup"><span data-stu-id="c8303-206">Left button double click mouse event, WM_LBUTTONDBLCLK.</span></span>
<span data-ttu-id="c8303-207">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_DOWN</span><span class="sxs-lookup"><span data-stu-id="c8303-207">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_DOWN</span></span>            | <span data-ttu-id="c8303-208">[左] ボタンのマウスイベント、WM_LBUTTONDOWN。</span><span class="sxs-lookup"><span data-stu-id="c8303-208">Left button down mouse event, WM_LBUTTONDOWN.</span></span>
<span data-ttu-id="c8303-209">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_UP</span><span class="sxs-lookup"><span data-stu-id="c8303-209">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_UP</span></span>            | <span data-ttu-id="c8303-210">[左] ボタンのマウスイベント、WM_LBUTTONUP。</span><span class="sxs-lookup"><span data-stu-id="c8303-210">Left button up mouse event, WM_LBUTTONUP.</span></span>
<span data-ttu-id="c8303-211">COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE</span><span class="sxs-lookup"><span data-stu-id="c8303-211">COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE</span></span>            | <span data-ttu-id="c8303-212">マウスの終了イベント、WM_MOUSELEAVE。</span><span class="sxs-lookup"><span data-stu-id="c8303-212">Mouse leave event, WM_MOUSELEAVE.</span></span>
<span data-ttu-id="c8303-213">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_DOUBLE_CLICK</span><span class="sxs-lookup"><span data-stu-id="c8303-213">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_DOUBLE_CLICK</span></span>            | <span data-ttu-id="c8303-214">中央ボタン [マウスイベント]、[WM_MBUTTONDBLCLK] の順にダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8303-214">Middle button double click mouse event, WM_MBUTTONDBLCLK.</span></span>
<span data-ttu-id="c8303-215">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_DOWN</span><span class="sxs-lookup"><span data-stu-id="c8303-215">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_DOWN</span></span>            | <span data-ttu-id="c8303-216">中央ボタンのマウスイベント、WM_MBUTTONDOWN。</span><span class="sxs-lookup"><span data-stu-id="c8303-216">Middle button down mouse event, WM_MBUTTONDOWN.</span></span>
<span data-ttu-id="c8303-217">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_UP</span><span class="sxs-lookup"><span data-stu-id="c8303-217">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_UP</span></span>            | <span data-ttu-id="c8303-218">中央ボタン上のマウスイベント、WM_MBUTTONUP。</span><span class="sxs-lookup"><span data-stu-id="c8303-218">Middle button up mouse event, WM_MBUTTONUP.</span></span>
<span data-ttu-id="c8303-219">COREWEBVIEW2_MOUSE_EVENT_KIND_MOVE</span><span class="sxs-lookup"><span data-stu-id="c8303-219">COREWEBVIEW2_MOUSE_EVENT_KIND_MOVE</span></span>            | <span data-ttu-id="c8303-220">マウス移動イベント、WM_MOUSEMOVE。</span><span class="sxs-lookup"><span data-stu-id="c8303-220">Mouse move event, WM_MOUSEMOVE.</span></span>
<span data-ttu-id="c8303-221">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_DOUBLE_CLICK</span><span class="sxs-lookup"><span data-stu-id="c8303-221">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_DOUBLE_CLICK</span></span>            | <span data-ttu-id="c8303-222">右ボタン [マウスイベント]、[WM_RBUTTONDBLCLK] の順にダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8303-222">Right button double click mouse event, WM_RBUTTONDBLCLK.</span></span>
<span data-ttu-id="c8303-223">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_DOWN</span><span class="sxs-lookup"><span data-stu-id="c8303-223">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_DOWN</span></span>            | <span data-ttu-id="c8303-224">右ボタンのマウスイベント、WM_RBUTTONDOWN。</span><span class="sxs-lookup"><span data-stu-id="c8303-224">Right button down mouse event, WM_RBUTTONDOWN.</span></span>
<span data-ttu-id="c8303-225">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_UP</span><span class="sxs-lookup"><span data-stu-id="c8303-225">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_UP</span></span>            | <span data-ttu-id="c8303-226">マウスの右上にあるイベントの [WM_RBUTTONUP] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8303-226">Right button up mouse event, WM_RBUTTONUP.</span></span>
<span data-ttu-id="c8303-227">COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL</span><span class="sxs-lookup"><span data-stu-id="c8303-227">COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL</span></span>            | <span data-ttu-id="c8303-228">マウスホイールスクロールイベント、WM_MOUSEWHEEL。</span><span class="sxs-lookup"><span data-stu-id="c8303-228">Mouse wheel scroll event, WM_MOUSEWHEEL.</span></span>
<span data-ttu-id="c8303-229">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOUBLE_CLICK</span><span class="sxs-lookup"><span data-stu-id="c8303-229">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOUBLE_CLICK</span></span>            | <span data-ttu-id="c8303-230">第1または第2の X ボタンをダブルクリックすると、[マウスイベント] が WM_XBUTTONDBLCLK ます。</span><span class="sxs-lookup"><span data-stu-id="c8303-230">First or second X button double click mouse event, WM_XBUTTONDBLCLK.</span></span>
<span data-ttu-id="c8303-231">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOWN</span><span class="sxs-lookup"><span data-stu-id="c8303-231">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOWN</span></span>            | <span data-ttu-id="c8303-232">最初または2番目の X ボタンのマウスイベントを WM_XBUTTONDOWN します。</span><span class="sxs-lookup"><span data-stu-id="c8303-232">First or second X button down mouse event, WM_XBUTTONDOWN.</span></span>
<span data-ttu-id="c8303-233">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_UP</span><span class="sxs-lookup"><span data-stu-id="c8303-233">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_UP</span></span>            | <span data-ttu-id="c8303-234">最初または2番目の X ボタンのマウスイベントを WM_XBUTTONUP します。</span><span class="sxs-lookup"><span data-stu-id="c8303-234">First or second X button up mouse event, WM_XBUTTONUP.</span></span>

<span data-ttu-id="c8303-235">この列挙型の値は、対応する WM_ \* ウィンドウメッセージと整列します。</span><span class="sxs-lookup"><span data-stu-id="c8303-235">The values of this enum align with the matching WM_\* window messages.</span></span>

#### <span data-ttu-id="c8303-236">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS</span><span class="sxs-lookup"><span data-stu-id="c8303-236">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS</span></span> 

<span data-ttu-id="c8303-237">SendMouseInput の COREWEBVIEW2_MOUSE_EVENT_KIND に関連付けられたマウスイベントの仮想キー。</span><span class="sxs-lookup"><span data-stu-id="c8303-237">Mouse event virtual keys associated with a COREWEBVIEW2_MOUSE_EVENT_KIND for SendMouseInput.</span></span>

> <span data-ttu-id="c8303-238">列挙型 [COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS](#corewebview2_mouse_event_virtual_keys)</span><span class="sxs-lookup"><span data-stu-id="c8303-238">enum [COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS](#corewebview2_mouse_event_virtual_keys)</span></span>

 <span data-ttu-id="c8303-239">値</span><span class="sxs-lookup"><span data-stu-id="c8303-239">Values</span></span>                         | <span data-ttu-id="c8303-240">説明</span><span class="sxs-lookup"><span data-stu-id="c8303-240">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="c8303-241">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_NONE</span><span class="sxs-lookup"><span data-stu-id="c8303-241">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_NONE</span></span>            | <span data-ttu-id="c8303-242">追加のキーが押されていません。</span><span class="sxs-lookup"><span data-stu-id="c8303-242">No additional keys pressed.</span></span>
<span data-ttu-id="c8303-243">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_LEFT_BUTTON</span><span class="sxs-lookup"><span data-stu-id="c8303-243">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_LEFT_BUTTON</span></span>            | <span data-ttu-id="c8303-244">マウスの左ボタンが押されています。 MK_LBUTTON。</span><span class="sxs-lookup"><span data-stu-id="c8303-244">Left mouse button is down, MK_LBUTTON.</span></span>
<span data-ttu-id="c8303-245">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_RIGHT_BUTTON</span><span class="sxs-lookup"><span data-stu-id="c8303-245">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_RIGHT_BUTTON</span></span>            | <span data-ttu-id="c8303-246">マウスの右ボタンが押されて MK_RBUTTON ます。</span><span class="sxs-lookup"><span data-stu-id="c8303-246">Right mouse button is down, MK_RBUTTON.</span></span>
<span data-ttu-id="c8303-247">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_SHIFT</span><span class="sxs-lookup"><span data-stu-id="c8303-247">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_SHIFT</span></span>            | <span data-ttu-id="c8303-248">SHIFT キーを押しながら MK_SHIFT ます。</span><span class="sxs-lookup"><span data-stu-id="c8303-248">SHIFT key is down, MK_SHIFT.</span></span>
<span data-ttu-id="c8303-249">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_CONTROL</span><span class="sxs-lookup"><span data-stu-id="c8303-249">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_CONTROL</span></span>            | <span data-ttu-id="c8303-250">CTRL キーを押しながら MK_CONTROL ます。</span><span class="sxs-lookup"><span data-stu-id="c8303-250">CTRL key is down, MK_CONTROL.</span></span>
<span data-ttu-id="c8303-251">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_MIDDLE_BUTTON</span><span class="sxs-lookup"><span data-stu-id="c8303-251">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_MIDDLE_BUTTON</span></span>            | <span data-ttu-id="c8303-252">マウスの中央ボタンが押されて MK_MBUTTON。</span><span class="sxs-lookup"><span data-stu-id="c8303-252">Middle mouse button is down, MK_MBUTTON.</span></span>
<span data-ttu-id="c8303-253">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_X_BUTTON1</span><span class="sxs-lookup"><span data-stu-id="c8303-253">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_X_BUTTON1</span></span>            | <span data-ttu-id="c8303-254">最初の X ボタンが押されて MK_XBUTTON1。</span><span class="sxs-lookup"><span data-stu-id="c8303-254">First X button is down, MK_XBUTTON1.</span></span>
<span data-ttu-id="c8303-255">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_X_BUTTON2</span><span class="sxs-lookup"><span data-stu-id="c8303-255">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_X_BUTTON2</span></span>            | <span data-ttu-id="c8303-256">第2の X ボタンが押され、MK_XBUTTON2 ます。</span><span class="sxs-lookup"><span data-stu-id="c8303-256">Second X button is down, MK_XBUTTON2.</span></span>

<span data-ttu-id="c8303-257">これらの値は、複数の仮想キーがイベントとして押されている場合に、ビットフラグに組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="c8303-257">These values can be combined into a bit flag if more than one virtual key is pressed for the event.</span></span> <span data-ttu-id="c8303-258">この列挙型の値は、一致する MK_ \* マウスキーと整列します。</span><span class="sxs-lookup"><span data-stu-id="c8303-258">The values of this enum align with the matching MK_\* mouse keys.</span></span>

#### <span data-ttu-id="c8303-259">COREWEBVIEW2_POINTER_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="c8303-259">COREWEBVIEW2_POINTER_EVENT_KIND</span></span> 

<span data-ttu-id="c8303-260">WebView に送信されるポインターイベントの種類を伝えるために Sendpointer 入力で使われるポインターイベントの種類です。</span><span class="sxs-lookup"><span data-stu-id="c8303-260">Pointer event type used by SendPointerInput to convey the type of pointer event being sent to WebView.</span></span>

> <span data-ttu-id="c8303-261">列挙型 [COREWEBVIEW2_POINTER_EVENT_KIND](#corewebview2_pointer_event_kind)</span><span class="sxs-lookup"><span data-stu-id="c8303-261">enum [COREWEBVIEW2_POINTER_EVENT_KIND](#corewebview2_pointer_event_kind)</span></span>

 <span data-ttu-id="c8303-262">値</span><span class="sxs-lookup"><span data-stu-id="c8303-262">Values</span></span>                         | <span data-ttu-id="c8303-263">説明</span><span class="sxs-lookup"><span data-stu-id="c8303-263">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="c8303-264">COREWEBVIEW2_POINTER_EVENT_KIND_ACTIVATE</span><span class="sxs-lookup"><span data-stu-id="c8303-264">COREWEBVIEW2_POINTER_EVENT_KIND_ACTIVATE</span></span>            | <span data-ttu-id="c8303-265">WM_POINTERACTIVATE に対応します。</span><span class="sxs-lookup"><span data-stu-id="c8303-265">Corresponds to WM_POINTERACTIVATE.</span></span>
<span data-ttu-id="c8303-266">COREWEBVIEW2_POINTER_EVENT_KIND_DOWN</span><span class="sxs-lookup"><span data-stu-id="c8303-266">COREWEBVIEW2_POINTER_EVENT_KIND_DOWN</span></span>            | <span data-ttu-id="c8303-267">WM_POINTERDOWN に対応します。</span><span class="sxs-lookup"><span data-stu-id="c8303-267">Corresponds to WM_POINTERDOWN.</span></span>
<span data-ttu-id="c8303-268">COREWEBVIEW2_POINTER_EVENT_KIND_ENTER</span><span class="sxs-lookup"><span data-stu-id="c8303-268">COREWEBVIEW2_POINTER_EVENT_KIND_ENTER</span></span>            | <span data-ttu-id="c8303-269">WM_POINTERENTER に対応します。</span><span class="sxs-lookup"><span data-stu-id="c8303-269">Corresponds to WM_POINTERENTER.</span></span>
<span data-ttu-id="c8303-270">COREWEBVIEW2_POINTER_EVENT_KIND_LEAVE</span><span class="sxs-lookup"><span data-stu-id="c8303-270">COREWEBVIEW2_POINTER_EVENT_KIND_LEAVE</span></span>            | <span data-ttu-id="c8303-271">WM_POINTERLEAVE に対応します。</span><span class="sxs-lookup"><span data-stu-id="c8303-271">Corresponds to WM_POINTERLEAVE.</span></span>
<span data-ttu-id="c8303-272">COREWEBVIEW2_POINTER_EVENT_KIND_UP</span><span class="sxs-lookup"><span data-stu-id="c8303-272">COREWEBVIEW2_POINTER_EVENT_KIND_UP</span></span>            | <span data-ttu-id="c8303-273">WM_POINTERUP に対応します。</span><span class="sxs-lookup"><span data-stu-id="c8303-273">Corresponds to WM_POINTERUP.</span></span>
<span data-ttu-id="c8303-274">COREWEBVIEW2_POINTER_EVENT_KIND_UPDATE</span><span class="sxs-lookup"><span data-stu-id="c8303-274">COREWEBVIEW2_POINTER_EVENT_KIND_UPDATE</span></span>            | <span data-ttu-id="c8303-275">WM_POINTERUPDATE に対応します。</span><span class="sxs-lookup"><span data-stu-id="c8303-275">Corresponds to WM_POINTERUPDATE.</span></span>

<span data-ttu-id="c8303-276">この列挙型の値は、対応する WM_POINTER \* ウィンドウメッセージと整列します。</span><span class="sxs-lookup"><span data-stu-id="c8303-276">The values of this enum align with the matching WM_POINTER\* window messages.</span></span>

