---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: 0.9.515-WebView2 Win32 C++ ICoreWebView2ExperimentalCompositionController
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: ddb3fce4f3f9799bcfaf8a9aa297c3207392f916
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884541"
---
# <span data-ttu-id="78e79-104">0.9.515-インターフェイス ICoreWebView2ExperimentalCompositionController</span><span class="sxs-lookup"><span data-stu-id="78e79-104">0.9.515 - interface ICoreWebView2ExperimentalCompositionController</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalCompositionController
  : public IUnknown
```

<span data-ttu-id="78e79-105">このインターフェイスは、ICoreWebView2Controller インターフェイスの拡張機能であり、ビジュアルホストをサポートします。</span><span class="sxs-lookup"><span data-stu-id="78e79-105">This interface is an extension of the ICoreWebView2Controller interface to support visual hosting.</span></span>

## <span data-ttu-id="78e79-106">まとめ</span><span class="sxs-lookup"><span data-stu-id="78e79-106">Summary</span></span>

 <span data-ttu-id="78e79-107">Members</span><span class="sxs-lookup"><span data-stu-id="78e79-107">Members</span></span>                        | <span data-ttu-id="78e79-108">説明</span><span class="sxs-lookup"><span data-stu-id="78e79-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="78e79-109">add_CursorChanged</span><span class="sxs-lookup"><span data-stu-id="78e79-109">add_CursorChanged</span></span>](#add_cursorchanged) | <span data-ttu-id="78e79-110">カーソル変更イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="78e79-110">Add an event handler for the CursorChanged event.</span></span>
[<span data-ttu-id="78e79-111">CreateCoreWebView2PointerInfoFromPointerId</span><span class="sxs-lookup"><span data-stu-id="78e79-111">CreateCoreWebView2PointerInfoFromPointerId</span></span>](#createcorewebview2pointerinfofrompointerid) | <span data-ttu-id="78e79-112">システムから受け取ったポインター Id を[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)に変換するヘルパー関数。</span><span class="sxs-lookup"><span data-stu-id="78e79-112">A helper function to convert a pointerId received from the system into an [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md).</span></span>
[<span data-ttu-id="78e79-113">get_Cursor</span><span class="sxs-lookup"><span data-stu-id="78e79-113">get_Cursor</span></span>](#get_cursor) | <span data-ttu-id="78e79-114">WebView で現在のカーソルの位置を判断します。</span><span class="sxs-lookup"><span data-stu-id="78e79-114">The current cursor that WebView thinks it should be.</span></span>
[<span data-ttu-id="78e79-115">get_RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="78e79-115">get_RootVisualTarget</span></span>](#get_rootvisualtarget) | <span data-ttu-id="78e79-116">RootVisualTarget は、ホストアプリのビジュアルツリー内のビジュアルです。</span><span class="sxs-lookup"><span data-stu-id="78e79-116">The RootVisualTarget is a visual in the hosting app's visual tree.</span></span>
[<span data-ttu-id="78e79-117">get_UIAProvider</span><span class="sxs-lookup"><span data-stu-id="78e79-117">get_UIAProvider</span></span>](#get_uiaprovider) | <span data-ttu-id="78e79-118">WebView の UI オートメーションプロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="78e79-118">Returns the UI Automation Provider for the WebView.</span></span>
[<span data-ttu-id="78e79-119">put_RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="78e79-119">put_RootVisualTarget</span></span>](#put_rootvisualtarget) | <span data-ttu-id="78e79-120">RootVisualTarget プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="78e79-120">Set the RootVisualTarget property.</span></span>
[<span data-ttu-id="78e79-121">remove_CursorChanged</span><span class="sxs-lookup"><span data-stu-id="78e79-121">remove_CursorChanged</span></span>](#remove_cursorchanged) | <span data-ttu-id="78e79-122">Add_CursorChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="78e79-122">Remove an event handler previously added with add_CursorChanged.</span></span>
[<span data-ttu-id="78e79-123">SendMouseInput</span><span class="sxs-lookup"><span data-stu-id="78e79-123">SendMouseInput</span></span>](#sendmouseinput) | <span data-ttu-id="78e79-124">EventKind が COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL または COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL の場合、mouseData は、WHEEL の動きの量を指定します。</span><span class="sxs-lookup"><span data-stu-id="78e79-124">If eventKind is COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL or COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL, then mouseData specifies the amount of wheel movement.</span></span>
[<span data-ttu-id="78e79-125">Sendポインタ入力</span><span class="sxs-lookup"><span data-stu-id="78e79-125">SendPointerInput</span></span>](#sendpointerinput) | <span data-ttu-id="78e79-126">Sendpointer 入力は、COREWEBVIEW2_POINTER_EVENT_KIND で定義された型のタッチポインターまたはペンポインターの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="78e79-126">SendPointerInput accepts touch or pen pointer input of types defined in COREWEBVIEW2_POINTER_EVENT_KIND.</span></span>
[<span data-ttu-id="78e79-127">COREWEBVIEW2_MATRIX_4X4</span><span class="sxs-lookup"><span data-stu-id="78e79-127">COREWEBVIEW2_MATRIX_4X4</span></span>](#corewebview2_matrix_4x4) | <span data-ttu-id="78e79-128">3D 変換を表すマトリックス。</span><span class="sxs-lookup"><span data-stu-id="78e79-128">Matrix that represents a 3D transform.</span></span>
[<span data-ttu-id="78e79-129">COREWEBVIEW2_MOUSE_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="78e79-129">COREWEBVIEW2_MOUSE_EVENT_KIND</span></span>](#corewebview2_mouse_event_kind) | <span data-ttu-id="78e79-130">WebView に送信されるマウスイベントの種類を伝えるために、SendMouseInput で使われるマウスイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="78e79-130">Mouse event type used by SendMouseInput to convey the type of mouse event being sent to WebView.</span></span>
[<span data-ttu-id="78e79-131">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS</span><span class="sxs-lookup"><span data-stu-id="78e79-131">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS</span></span>](#corewebview2_mouse_event_virtual_keys) | <span data-ttu-id="78e79-132">SendMouseInput の COREWEBVIEW2_MOUSE_EVENT_KIND に関連付けられたマウスイベントの仮想キー。</span><span class="sxs-lookup"><span data-stu-id="78e79-132">Mouse event virtual keys associated with a COREWEBVIEW2_MOUSE_EVENT_KIND for SendMouseInput.</span></span>
[<span data-ttu-id="78e79-133">COREWEBVIEW2_POINTER_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="78e79-133">COREWEBVIEW2_POINTER_EVENT_KIND</span></span>](#corewebview2_pointer_event_kind) | <span data-ttu-id="78e79-134">WebView に送信されるポインターイベントの種類を伝えるために Sendpointer 入力で使われるポインターイベントの種類です。</span><span class="sxs-lookup"><span data-stu-id="78e79-134">Pointer event type used by SendPointerInput to convey the type of pointer event being sent to WebView.</span></span>

<span data-ttu-id="78e79-135">ICoreWebView2ExperimentalCompositionController インターフェイスを実装するオブジェクトも ICoreWebView2Controller を実装します。</span><span class="sxs-lookup"><span data-stu-id="78e79-135">An object implementing the ICoreWebView2ExperimentalCompositionController interface will also implement ICoreWebView2Controller.</span></span> <span data-ttu-id="78e79-136">呼び出し元は、サイズ変更、visibility、フォーカスなどのために ICoreWebView2Controller を使うことを前提としており、ICoreWebView2ExperimentalCompositionController を使ってコンポジションツリーに接続し、WebView 用の入力を提供します。</span><span class="sxs-lookup"><span data-stu-id="78e79-136">Callers are expected to use ICoreWebView2Controller for resizing, visibility, focus, and so on, and then use ICoreWebView2ExperimentalCompositionController to connect to a composition tree and provide input meant for the WebView.</span></span>

## <span data-ttu-id="78e79-137">Members</span><span class="sxs-lookup"><span data-stu-id="78e79-137">Members</span></span>

#### <span data-ttu-id="78e79-138">add_CursorChanged</span><span class="sxs-lookup"><span data-stu-id="78e79-138">add_CursorChanged</span></span> 

<span data-ttu-id="78e79-139">カーソル変更イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="78e79-139">Add an event handler for the CursorChanged event.</span></span>

> <span data-ttu-id="78e79-140">パブリック HRESULT [add_CursorChanged](#add_cursorchanged)([ICoreWebView2ExperimentalCursorChangedEventHandler](icorewebview2experimentalcursorchangedeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="78e79-140">public HRESULT [add_CursorChanged](#add_cursorchanged)([ICoreWebView2ExperimentalCursorChangedEventHandler](icorewebview2experimentalcursorchangedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="78e79-141">WebView がカーソルの変更であると判断されたときに、イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="78e79-141">The event fires when WebView thinks the cursor should be changed.</span></span> <span data-ttu-id="78e79-142">たとえば、マウスカーソルが現在既定のカーソルであり、テキストの上に移動した場合は、IBeam カーソルに変更しようとすることがあります。</span><span class="sxs-lookup"><span data-stu-id="78e79-142">For example, when the mouse cursor is currently the default cursor but is then moved over text, it may try to change to the IBeam cursor.</span></span>

```cpp
        // Register a handler for the CursorChanged event.
        CHECK_FAILURE(m_compositionController->add_CursorChanged(
            Callback<ICoreWebView2ExperimentalCursorChangedEventHandler>(
                [this](ICoreWebView2ExperimentalCompositionController* sender,
                       IUnknown* args) -> HRESULT {
                    HCURSOR cursor;
                    CHECK_FAILURE(sender->get_Cursor(&cursor));
                    SetClassLongPtr(m_appWindow->GetMainWindow(), GCLP_HCURSOR, (LONG_PTR)cursor);
                    return S_OK;
                })
                .Get(),
            &m_cursorChangedToken));
```

#### <span data-ttu-id="78e79-143">CreateCoreWebView2PointerInfoFromPointerId</span><span class="sxs-lookup"><span data-stu-id="78e79-143">CreateCoreWebView2PointerInfoFromPointerId</span></span> 

<span data-ttu-id="78e79-144">システムから受け取ったポインター Id を[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)に変換するヘルパー関数。</span><span class="sxs-lookup"><span data-stu-id="78e79-144">A helper function to convert a pointerId received from the system into an [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md).</span></span>

> <span data-ttu-id="78e79-145">パブリック HRESULT [CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid)(UINT ポインター ID、HWND parentwindow、struct COREWEBVIEW2_MATRIX_4X4 Transform、 [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \* \* ポインター情報)</span><span class="sxs-lookup"><span data-stu-id="78e79-145">public HRESULT [CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid)(UINT pointerId, HWND parentWindow, struct COREWEBVIEW2_MATRIX_4X4 transform, [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \*\* pointerInfo)</span></span>

<span data-ttu-id="78e79-146">parentWindow は、webview を含む HWND です。</span><span class="sxs-lookup"><span data-stu-id="78e79-146">parentWindow is the HWND that contains the webview.</span></span> <span data-ttu-id="78e79-147">これは、webview を含む hwnd ツリー内の任意の HWND にすることができます。</span><span class="sxs-lookup"><span data-stu-id="78e79-147">This can be any HWND in the hwnd tree that contains the webview.</span></span> <span data-ttu-id="78e79-148">COREWEBVIEW2_MATRIX_4X4 は、その HWND から webview への変換です。</span><span class="sxs-lookup"><span data-stu-id="78e79-148">The COREWEBVIEW2_MATRIX_4X4 is the transform from that HWND to the webview.</span></span> <span data-ttu-id="78e79-149">返された[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)は、Sendポインタ info で使われます。</span><span class="sxs-lookup"><span data-stu-id="78e79-149">The returned [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) is used in SendPointerInfo.</span></span> <span data-ttu-id="78e79-150">ポインターの型は、ペンまたはタッチである必要があります。または、関数は失敗します。</span><span class="sxs-lookup"><span data-stu-id="78e79-150">The pointer type must be either pen or touch or the function will fail.</span></span>



#### <span data-ttu-id="78e79-151">get_Cursor</span><span class="sxs-lookup"><span data-stu-id="78e79-151">get_Cursor</span></span> 

<span data-ttu-id="78e79-152">WebView で現在のカーソルの位置を判断します。</span><span class="sxs-lookup"><span data-stu-id="78e79-152">The current cursor that WebView thinks it should be.</span></span>

> <span data-ttu-id="78e79-153">パブリック HRESULT [get_Cursor](#get_cursor)(hcursor \* cursor)</span><span class="sxs-lookup"><span data-stu-id="78e79-153">public HRESULT [get_Cursor](#get_cursor)(HCURSOR \* cursor)</span></span>

<span data-ttu-id="78e79-154">カーソルは WM_SETCURSOR スルー:: SetCursor で設定するか、WebView ~:: SetClassLongPtr の対応する親または先祖の HWND で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78e79-154">The cursor should be set in WM_SETCURSOR through ::SetCursor or set on the corresponding parent/ancestor HWND of the WebView through ::SetClassLongPtr.</span></span> <span data-ttu-id="78e79-155">HCURSOR を解放すると、カーソルをすぐに設定するよりも、コピーを保持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="78e79-155">The HCURSOR can be freed so CopyCursor/DestroyCursor is recommended to keep your own copy if you are doing more than immediately setting the cursor.</span></span>

#### <span data-ttu-id="78e79-156">get_RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="78e79-156">get_RootVisualTarget</span></span> 

<span data-ttu-id="78e79-157">RootVisualTarget は、ホストアプリのビジュアルツリー内のビジュアルです。</span><span class="sxs-lookup"><span data-stu-id="78e79-157">The RootVisualTarget is a visual in the hosting app's visual tree.</span></span>

> <span data-ttu-id="78e79-158">パブリック HRESULT [get_RootVisualTarget](#get_rootvisualtarget)(IUnknown \* \* target)</span><span class="sxs-lookup"><span data-stu-id="78e79-158">public HRESULT [get_RootVisualTarget](#get_rootvisualtarget)(IUnknown \*\* target)</span></span>

<span data-ttu-id="78e79-159">このビジュアルは、WebView がそのビジュアルツリーを接続する場所です。</span><span class="sxs-lookup"><span data-stu-id="78e79-159">This visual is where the WebView will connect its visual tree.</span></span> <span data-ttu-id="78e79-160">アプリでは、このビジュアルを使って、アプリ内で WebView を配置します。</span><span class="sxs-lookup"><span data-stu-id="78e79-160">The app uses this visual to position the WebView within the app.</span></span> <span data-ttu-id="78e79-161">この場合も、アプリでは、境界プロパティを使って WebView のサイズを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78e79-161">The app still needs to use the Bounds property to size the WebView.</span></span> <span data-ttu-id="78e79-162">RootVisualTarget プロパティは、IDCompositionVisual または Windows:: UI:: コンポジション:: ContainerVisual とすることができます。</span><span class="sxs-lookup"><span data-stu-id="78e79-162">The RootVisualTarget property can be an IDCompositionVisual or a Windows::UI::Composition::ContainerVisual.</span></span> <span data-ttu-id="78e79-163">WebView は、プロパティ setter から戻る前に、ビジュアルツリーを提供された visual に接続します。</span><span class="sxs-lookup"><span data-stu-id="78e79-163">WebView will connect its visual tree to the provided visual before returning from the property setter.</span></span> <span data-ttu-id="78e79-164">アプリは、Root Visualtarget プロパティのデバイス設定でコミットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="78e79-164">The app needs to commit on its device setting the RootVisualTarget property.</span></span> <span data-ttu-id="78e79-165">RootVisualTarget プロパティは、アプリのビジュアルツリーから WebView を切断するために nullptr に設定されています。</span><span class="sxs-lookup"><span data-stu-id="78e79-165">The RootVisualTarget property supports being set to nullptr to disconnect the WebView from the app's visual tree.</span></span> 
```cpp
            // Set the host app visual that the WebView will connect its visual
            // tree to.
            BuildDCompTreeUsingVisual();
            CHECK_FAILURE(m_compositionController->put_RootVisualTarget(m_dcompWebViewVisual.get()));
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

#### <span data-ttu-id="78e79-166">get_UIAProvider</span><span class="sxs-lookup"><span data-stu-id="78e79-166">get_UIAProvider</span></span> 

<span data-ttu-id="78e79-167">WebView の UI オートメーションプロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="78e79-167">Returns the UI Automation Provider for the WebView.</span></span>

> <span data-ttu-id="78e79-168">パブリック HRESULT [get_UIAProvider](#get_uiaprovider)(IUnknown \* \* provider)</span><span class="sxs-lookup"><span data-stu-id="78e79-168">public HRESULT [get_UIAProvider](#get_uiaprovider)(IUnknown \*\* provider)</span></span>

#### <span data-ttu-id="78e79-169">put_RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="78e79-169">put_RootVisualTarget</span></span> 

<span data-ttu-id="78e79-170">RootVisualTarget プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="78e79-170">Set the RootVisualTarget property.</span></span>

> <span data-ttu-id="78e79-171">パブリック HRESULT [put_RootVisualTarget](#put_rootvisualtarget)(IUnknown \* ターゲット)</span><span class="sxs-lookup"><span data-stu-id="78e79-171">public HRESULT [put_RootVisualTarget](#put_rootvisualtarget)(IUnknown \* target)</span></span>

#### <span data-ttu-id="78e79-172">remove_CursorChanged</span><span class="sxs-lookup"><span data-stu-id="78e79-172">remove_CursorChanged</span></span> 

<span data-ttu-id="78e79-173">Add_CursorChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="78e79-173">Remove an event handler previously added with add_CursorChanged.</span></span>

> <span data-ttu-id="78e79-174">パブリック HRESULT [remove_CursorChanged](#remove_cursorchanged)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="78e79-174">public HRESULT [remove_CursorChanged](#remove_cursorchanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="78e79-175">SendMouseInput</span><span class="sxs-lookup"><span data-stu-id="78e79-175">SendMouseInput</span></span> 

<span data-ttu-id="78e79-176">EventKind が COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL または COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL の場合、mouseData は、WHEEL の動きの量を指定します。</span><span class="sxs-lookup"><span data-stu-id="78e79-176">If eventKind is COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL or COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL, then mouseData specifies the amount of wheel movement.</span></span>

> <span data-ttu-id="78e79-177">パブリック HRESULT 送信[マウス入力](#sendmouseinput)([COREWEBVIEW2_MOUSE_EVENT_KIND](#corewebview2_mouse_event_kind) eventkind、 [COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS](#corewebview2_mouse_event_virtual_keys) VIRTUALKEYS、UINT32 mousedata、ポイントポイント)</span><span class="sxs-lookup"><span data-stu-id="78e79-177">public HRESULT [SendMouseInput](#sendmouseinput)([COREWEBVIEW2_MOUSE_EVENT_KIND](#corewebview2_mouse_event_kind) eventKind, [COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS](#corewebview2_mouse_event_virtual_keys) virtualKeys, UINT32 mouseData, POINT point)</span></span>

<span data-ttu-id="78e79-178">正の値は、ホイールがユーザーによって前方に回転されたことを示します。負の値は、ホイールが背面に回転していることを示します。</span><span class="sxs-lookup"><span data-stu-id="78e79-178">A positive value indicates that the wheel was rotated forward, away from the user; a negative value indicates that the wheel was rotated backward, toward the user.</span></span> <span data-ttu-id="78e79-179">ホイールクリックの1つは、120として定義されている WHEEL_DELTA として定義されています。</span><span class="sxs-lookup"><span data-stu-id="78e79-179">One wheel click is defined as WHEEL_DELTA, which is 120.</span></span> <span data-ttu-id="78e79-180">EventKind が COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOUBLE_CLICK COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOWN、または COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_UP の場合、mouseData は、どの X ボタンが押されたか、離されたかを指定します。</span><span class="sxs-lookup"><span data-stu-id="78e79-180">If eventKind is COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOUBLE_CLICK COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOWN, or COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_UP, then mouseData specifies which X buttons were pressed or released.</span></span> <span data-ttu-id="78e79-181">この値は、最初の X ボタンが押されている場合は1、2番目の X ボタンが押されたとき、または離された場合は1になります。</span><span class="sxs-lookup"><span data-stu-id="78e79-181">This value should be 1 if the first X button is pressed/released and 2 if the second X button is pressed/released.</span></span> <span data-ttu-id="78e79-182">EventKind が COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE の場合、virtualKeys、mouseData、point はすべてゼロである必要があります。</span><span class="sxs-lookup"><span data-stu-id="78e79-182">If eventKind is COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE, then virtualKeys, mouseData, and point should all be zero.</span></span> <span data-ttu-id="78e79-183">EventKind がその他の値である場合は、mouseData は0である必要があります。</span><span class="sxs-lookup"><span data-stu-id="78e79-183">If eventKind is any other value, then mouseData should be zero.</span></span> <span data-ttu-id="78e79-184">Point は、WebView のクライアント座標空間に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78e79-184">Point is expected to be in the client coordinate space of the WebView.</span></span> <span data-ttu-id="78e79-185">WebView から始まり、WebView とホストアプリケーションの外側に移動する可能性のあるマウスイベントを追跡するには、SetCapture と ReleaseCapture の呼び出しをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="78e79-185">To track mouse events that start in the WebView and can potentially move outside of the WebView and host application, calling SetCapture and ReleaseCapture is recommended.</span></span> <span data-ttu-id="78e79-186">ホバーポップアップを消すには、WM_MOUSELEAVE メッセージを送信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="78e79-186">To dismiss hover popups, it is also recommended to send WM_MOUSELEAVE messages.</span></span> 
```cpp
bool ViewComponent::OnMouseMessage(UINT message, WPARAM wParam, LPARAM lParam)
{
    // Manually relay mouse messages to the WebView
    if (m_dcompDevice || m_wincompHelper)
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

#### <span data-ttu-id="78e79-187">Sendポインタ入力</span><span class="sxs-lookup"><span data-stu-id="78e79-187">SendPointerInput</span></span> 

<span data-ttu-id="78e79-188">Sendpointer 入力は、COREWEBVIEW2_POINTER_EVENT_KIND で定義された型のタッチポインターまたはペンポインターの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="78e79-188">SendPointerInput accepts touch or pen pointer input of types defined in COREWEBVIEW2_POINTER_EVENT_KIND.</span></span>

> <span data-ttu-id="78e79-189">パブリック HRESULT 送信[ポインター入力](#sendpointerinput)([COREWEBVIEW2_POINTER_EVENT_KIND](#corewebview2_pointer_event_kind) eventType、 [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \* のポインター情報)</span><span class="sxs-lookup"><span data-stu-id="78e79-189">public HRESULT [SendPointerInput](#sendpointerinput)([COREWEBVIEW2_POINTER_EVENT_KIND](#corewebview2_pointer_event_kind) eventType, [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \* pointerInfo)</span></span>

<span data-ttu-id="78e79-190">システムからのポインター入力は、最初に[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78e79-190">Any pointer input from the system must be converted into an [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) first.</span></span>

#### <span data-ttu-id="78e79-191">COREWEBVIEW2_MATRIX_4X4</span><span class="sxs-lookup"><span data-stu-id="78e79-191">COREWEBVIEW2_MATRIX_4X4</span></span> 

<span data-ttu-id="78e79-192">3D 変換を表すマトリックス。</span><span class="sxs-lookup"><span data-stu-id="78e79-192">Matrix that represents a 3D transform.</span></span>

> <span data-ttu-id="78e79-193">typedef [COREWEBVIEW2_MATRIX_4X4](#corewebview2_matrix_4x4)</span><span class="sxs-lookup"><span data-stu-id="78e79-193">typedef [COREWEBVIEW2_MATRIX_4X4](#corewebview2_matrix_4x4)</span></span>

<span data-ttu-id="78e79-194">この変換は、CreateCoreWebView2PointerInfoFromPointerId を呼び出したときに適切な座標を計算するために使われます。</span><span class="sxs-lookup"><span data-stu-id="78e79-194">This transform is used to calculate correct coordinates when calling CreateCoreWebView2PointerInfoFromPointerId.</span></span> <span data-ttu-id="78e79-195">これは D2D1_MATRIX_4X4_F と同じです。</span><span class="sxs-lookup"><span data-stu-id="78e79-195">This is equivalent to a D2D1_MATRIX_4X4_F</span></span>

#### <span data-ttu-id="78e79-196">COREWEBVIEW2_MOUSE_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="78e79-196">COREWEBVIEW2_MOUSE_EVENT_KIND</span></span> 

<span data-ttu-id="78e79-197">WebView に送信されるマウスイベントの種類を伝えるために、SendMouseInput で使われるマウスイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="78e79-197">Mouse event type used by SendMouseInput to convey the type of mouse event being sent to WebView.</span></span>

> <span data-ttu-id="78e79-198">列挙型[COREWEBVIEW2_MOUSE_EVENT_KIND](#corewebview2_mouse_event_kind)</span><span class="sxs-lookup"><span data-stu-id="78e79-198">enum [COREWEBVIEW2_MOUSE_EVENT_KIND](#corewebview2_mouse_event_kind)</span></span>

 <span data-ttu-id="78e79-199">値</span><span class="sxs-lookup"><span data-stu-id="78e79-199">Values</span></span>                         | <span data-ttu-id="78e79-200">説明</span><span class="sxs-lookup"><span data-stu-id="78e79-200">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="78e79-201">COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL</span><span class="sxs-lookup"><span data-stu-id="78e79-201">COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL</span></span>            | <span data-ttu-id="78e79-202">マウスの水平ホイールスクロールイベント、WM_MOUSEHWHEEL。</span><span class="sxs-lookup"><span data-stu-id="78e79-202">Mouse horizontal wheel scroll event, WM_MOUSEHWHEEL.</span></span>
<span data-ttu-id="78e79-203">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_DOUBLE_CLICK</span><span class="sxs-lookup"><span data-stu-id="78e79-203">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_DOUBLE_CLICK</span></span>            | <span data-ttu-id="78e79-204">[左] ボタンをダブルクリックすると、[マウスイベント] が WM_LBUTTONDBLCLK ます。</span><span class="sxs-lookup"><span data-stu-id="78e79-204">Left button double click mouse event, WM_LBUTTONDBLCLK.</span></span>
<span data-ttu-id="78e79-205">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_DOWN</span><span class="sxs-lookup"><span data-stu-id="78e79-205">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_DOWN</span></span>            | <span data-ttu-id="78e79-206">[左] ボタンのマウスイベント、WM_LBUTTONDOWN。</span><span class="sxs-lookup"><span data-stu-id="78e79-206">Left button down mouse event, WM_LBUTTONDOWN.</span></span>
<span data-ttu-id="78e79-207">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_UP</span><span class="sxs-lookup"><span data-stu-id="78e79-207">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_UP</span></span>            | <span data-ttu-id="78e79-208">[左] ボタンのマウスイベント、WM_LBUTTONUP。</span><span class="sxs-lookup"><span data-stu-id="78e79-208">Left button up mouse event, WM_LBUTTONUP.</span></span>
<span data-ttu-id="78e79-209">COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE</span><span class="sxs-lookup"><span data-stu-id="78e79-209">COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE</span></span>            | <span data-ttu-id="78e79-210">マウスの終了イベント、WM_MOUSELEAVE。</span><span class="sxs-lookup"><span data-stu-id="78e79-210">Mouse leave event, WM_MOUSELEAVE.</span></span>
<span data-ttu-id="78e79-211">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_DOUBLE_CLICK</span><span class="sxs-lookup"><span data-stu-id="78e79-211">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_DOUBLE_CLICK</span></span>            | <span data-ttu-id="78e79-212">中央ボタン [マウスイベント]、[WM_MBUTTONDBLCLK] の順にダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="78e79-212">Middle button double click mouse event, WM_MBUTTONDBLCLK.</span></span>
<span data-ttu-id="78e79-213">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_DOWN</span><span class="sxs-lookup"><span data-stu-id="78e79-213">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_DOWN</span></span>            | <span data-ttu-id="78e79-214">中央ボタンのマウスイベント、WM_MBUTTONDOWN。</span><span class="sxs-lookup"><span data-stu-id="78e79-214">Middle button down mouse event, WM_MBUTTONDOWN.</span></span>
<span data-ttu-id="78e79-215">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_UP</span><span class="sxs-lookup"><span data-stu-id="78e79-215">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_UP</span></span>            | <span data-ttu-id="78e79-216">中央ボタン上のマウスイベント、WM_MBUTTONUP。</span><span class="sxs-lookup"><span data-stu-id="78e79-216">Middle button up mouse event, WM_MBUTTONUP.</span></span>
<span data-ttu-id="78e79-217">COREWEBVIEW2_MOUSE_EVENT_KIND_MOVE</span><span class="sxs-lookup"><span data-stu-id="78e79-217">COREWEBVIEW2_MOUSE_EVENT_KIND_MOVE</span></span>            | <span data-ttu-id="78e79-218">マウス移動イベント、WM_MOUSEMOVE。</span><span class="sxs-lookup"><span data-stu-id="78e79-218">Mouse move event, WM_MOUSEMOVE.</span></span>
<span data-ttu-id="78e79-219">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_DOUBLE_CLICK</span><span class="sxs-lookup"><span data-stu-id="78e79-219">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_DOUBLE_CLICK</span></span>            | <span data-ttu-id="78e79-220">右ボタン [マウスイベント]、[WM_RBUTTONDBLCLK] の順にダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="78e79-220">Right button double click mouse event, WM_RBUTTONDBLCLK.</span></span>
<span data-ttu-id="78e79-221">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_DOWN</span><span class="sxs-lookup"><span data-stu-id="78e79-221">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_DOWN</span></span>            | <span data-ttu-id="78e79-222">右ボタンのマウスイベント、WM_RBUTTONDOWN。</span><span class="sxs-lookup"><span data-stu-id="78e79-222">Right button down mouse event, WM_RBUTTONDOWN.</span></span>
<span data-ttu-id="78e79-223">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_UP</span><span class="sxs-lookup"><span data-stu-id="78e79-223">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_UP</span></span>            | <span data-ttu-id="78e79-224">マウスの右上にあるイベントの [WM_RBUTTONUP] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78e79-224">Right button up mouse event, WM_RBUTTONUP.</span></span>
<span data-ttu-id="78e79-225">COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL</span><span class="sxs-lookup"><span data-stu-id="78e79-225">COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL</span></span>            | <span data-ttu-id="78e79-226">マウスホイールスクロールイベント、WM_MOUSEWHEEL。</span><span class="sxs-lookup"><span data-stu-id="78e79-226">Mouse wheel scroll event, WM_MOUSEWHEEL.</span></span>
<span data-ttu-id="78e79-227">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOUBLE_CLICK</span><span class="sxs-lookup"><span data-stu-id="78e79-227">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOUBLE_CLICK</span></span>            | <span data-ttu-id="78e79-228">第1または第2の X ボタンをダブルクリックすると、[マウスイベント] が WM_XBUTTONDBLCLK ます。</span><span class="sxs-lookup"><span data-stu-id="78e79-228">First or second X button double click mouse event, WM_XBUTTONDBLCLK.</span></span>
<span data-ttu-id="78e79-229">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOWN</span><span class="sxs-lookup"><span data-stu-id="78e79-229">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOWN</span></span>            | <span data-ttu-id="78e79-230">最初または2番目の X ボタンのマウスイベントを WM_XBUTTONDOWN します。</span><span class="sxs-lookup"><span data-stu-id="78e79-230">First or second X button down mouse event, WM_XBUTTONDOWN.</span></span>
<span data-ttu-id="78e79-231">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_UP</span><span class="sxs-lookup"><span data-stu-id="78e79-231">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_UP</span></span>            | <span data-ttu-id="78e79-232">最初または2番目の X ボタンのマウスイベントを WM_XBUTTONUP します。</span><span class="sxs-lookup"><span data-stu-id="78e79-232">First or second X button up mouse event, WM_XBUTTONUP.</span></span>

<span data-ttu-id="78e79-233">この列挙型の値は、対応する WM_ \* ウィンドウメッセージと整列します。</span><span class="sxs-lookup"><span data-stu-id="78e79-233">The values of this enum align with the matching WM_\* window messages.</span></span>

#### <span data-ttu-id="78e79-234">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS</span><span class="sxs-lookup"><span data-stu-id="78e79-234">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS</span></span> 

<span data-ttu-id="78e79-235">SendMouseInput の COREWEBVIEW2_MOUSE_EVENT_KIND に関連付けられたマウスイベントの仮想キー。</span><span class="sxs-lookup"><span data-stu-id="78e79-235">Mouse event virtual keys associated with a COREWEBVIEW2_MOUSE_EVENT_KIND for SendMouseInput.</span></span>

> <span data-ttu-id="78e79-236">列挙型[COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS](#corewebview2_mouse_event_virtual_keys)</span><span class="sxs-lookup"><span data-stu-id="78e79-236">enum [COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS](#corewebview2_mouse_event_virtual_keys)</span></span>

 <span data-ttu-id="78e79-237">値</span><span class="sxs-lookup"><span data-stu-id="78e79-237">Values</span></span>                         | <span data-ttu-id="78e79-238">説明</span><span class="sxs-lookup"><span data-stu-id="78e79-238">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="78e79-239">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_NONE</span><span class="sxs-lookup"><span data-stu-id="78e79-239">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_NONE</span></span>            | <span data-ttu-id="78e79-240">追加のキーが押されていません。</span><span class="sxs-lookup"><span data-stu-id="78e79-240">No additional keys pressed.</span></span>
<span data-ttu-id="78e79-241">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_LEFT_BUTTON</span><span class="sxs-lookup"><span data-stu-id="78e79-241">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_LEFT_BUTTON</span></span>            | <span data-ttu-id="78e79-242">マウスの左ボタンが押されています。 MK_LBUTTON。</span><span class="sxs-lookup"><span data-stu-id="78e79-242">Left mouse button is down, MK_LBUTTON.</span></span>
<span data-ttu-id="78e79-243">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_RIGHT_BUTTON</span><span class="sxs-lookup"><span data-stu-id="78e79-243">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_RIGHT_BUTTON</span></span>            | <span data-ttu-id="78e79-244">マウスの右ボタンが押されて MK_RBUTTON ます。</span><span class="sxs-lookup"><span data-stu-id="78e79-244">Right mouse button is down, MK_RBUTTON.</span></span>
<span data-ttu-id="78e79-245">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_SHIFT</span><span class="sxs-lookup"><span data-stu-id="78e79-245">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_SHIFT</span></span>            | <span data-ttu-id="78e79-246">SHIFT キーを押しながら MK_SHIFT ます。</span><span class="sxs-lookup"><span data-stu-id="78e79-246">SHIFT key is down, MK_SHIFT.</span></span>
<span data-ttu-id="78e79-247">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_CONTROL</span><span class="sxs-lookup"><span data-stu-id="78e79-247">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_CONTROL</span></span>            | <span data-ttu-id="78e79-248">CTRL キーを押しながら MK_CONTROL ます。</span><span class="sxs-lookup"><span data-stu-id="78e79-248">CTRL key is down, MK_CONTROL.</span></span>
<span data-ttu-id="78e79-249">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_MIDDLE_BUTTON</span><span class="sxs-lookup"><span data-stu-id="78e79-249">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_MIDDLE_BUTTON</span></span>            | <span data-ttu-id="78e79-250">マウスの中央ボタンが押されて MK_MBUTTON。</span><span class="sxs-lookup"><span data-stu-id="78e79-250">Middle mouse button is down, MK_MBUTTON.</span></span>
<span data-ttu-id="78e79-251">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_X_BUTTON1</span><span class="sxs-lookup"><span data-stu-id="78e79-251">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_X_BUTTON1</span></span>            | <span data-ttu-id="78e79-252">最初の X ボタンが押されて MK_XBUTTON1。</span><span class="sxs-lookup"><span data-stu-id="78e79-252">First X button is down, MK_XBUTTON1.</span></span>
<span data-ttu-id="78e79-253">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_X_BUTTON2</span><span class="sxs-lookup"><span data-stu-id="78e79-253">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_X_BUTTON2</span></span>            | <span data-ttu-id="78e79-254">第2の X ボタンが押され、MK_XBUTTON2 ます。</span><span class="sxs-lookup"><span data-stu-id="78e79-254">Second X button is down, MK_XBUTTON2.</span></span>

<span data-ttu-id="78e79-255">これらの値は、複数の仮想キーがイベントとして押されている場合に、ビットフラグに組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="78e79-255">These values can be combined into a bit flag if more than one virtual key is pressed for the event.</span></span> <span data-ttu-id="78e79-256">この列挙型の値は、一致する MK_ \* マウスキーと整列します。</span><span class="sxs-lookup"><span data-stu-id="78e79-256">The values of this enum align with the matching MK_\* mouse keys.</span></span>

#### <span data-ttu-id="78e79-257">COREWEBVIEW2_POINTER_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="78e79-257">COREWEBVIEW2_POINTER_EVENT_KIND</span></span> 

<span data-ttu-id="78e79-258">WebView に送信されるポインターイベントの種類を伝えるために Sendpointer 入力で使われるポインターイベントの種類です。</span><span class="sxs-lookup"><span data-stu-id="78e79-258">Pointer event type used by SendPointerInput to convey the type of pointer event being sent to WebView.</span></span>

> <span data-ttu-id="78e79-259">列挙型[COREWEBVIEW2_POINTER_EVENT_KIND](#corewebview2_pointer_event_kind)</span><span class="sxs-lookup"><span data-stu-id="78e79-259">enum [COREWEBVIEW2_POINTER_EVENT_KIND](#corewebview2_pointer_event_kind)</span></span>

 <span data-ttu-id="78e79-260">値</span><span class="sxs-lookup"><span data-stu-id="78e79-260">Values</span></span>                         | <span data-ttu-id="78e79-261">説明</span><span class="sxs-lookup"><span data-stu-id="78e79-261">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="78e79-262">COREWEBVIEW2_POINTER_EVENT_KIND_ACTIVATE</span><span class="sxs-lookup"><span data-stu-id="78e79-262">COREWEBVIEW2_POINTER_EVENT_KIND_ACTIVATE</span></span>            | <span data-ttu-id="78e79-263">WM_POINTERACTIVATE に対応します。</span><span class="sxs-lookup"><span data-stu-id="78e79-263">Corresponds to WM_POINTERACTIVATE.</span></span>
<span data-ttu-id="78e79-264">COREWEBVIEW2_POINTER_EVENT_KIND_DOWN</span><span class="sxs-lookup"><span data-stu-id="78e79-264">COREWEBVIEW2_POINTER_EVENT_KIND_DOWN</span></span>            | <span data-ttu-id="78e79-265">WM_POINTERDOWN に対応します。</span><span class="sxs-lookup"><span data-stu-id="78e79-265">Corresponds to WM_POINTERDOWN.</span></span>
<span data-ttu-id="78e79-266">COREWEBVIEW2_POINTER_EVENT_KIND_ENTER</span><span class="sxs-lookup"><span data-stu-id="78e79-266">COREWEBVIEW2_POINTER_EVENT_KIND_ENTER</span></span>            | <span data-ttu-id="78e79-267">WM_POINTERENTER に対応します。</span><span class="sxs-lookup"><span data-stu-id="78e79-267">Corresponds to WM_POINTERENTER.</span></span>
<span data-ttu-id="78e79-268">COREWEBVIEW2_POINTER_EVENT_KIND_LEAVE</span><span class="sxs-lookup"><span data-stu-id="78e79-268">COREWEBVIEW2_POINTER_EVENT_KIND_LEAVE</span></span>            | <span data-ttu-id="78e79-269">WM_POINTERLEAVE に対応します。</span><span class="sxs-lookup"><span data-stu-id="78e79-269">Corresponds to WM_POINTERLEAVE.</span></span>
<span data-ttu-id="78e79-270">COREWEBVIEW2_POINTER_EVENT_KIND_UP</span><span class="sxs-lookup"><span data-stu-id="78e79-270">COREWEBVIEW2_POINTER_EVENT_KIND_UP</span></span>            | <span data-ttu-id="78e79-271">WM_POINTERUP に対応します。</span><span class="sxs-lookup"><span data-stu-id="78e79-271">Corresponds to WM_POINTERUP.</span></span>
<span data-ttu-id="78e79-272">COREWEBVIEW2_POINTER_EVENT_KIND_UPDATE</span><span class="sxs-lookup"><span data-stu-id="78e79-272">COREWEBVIEW2_POINTER_EVENT_KIND_UPDATE</span></span>            | <span data-ttu-id="78e79-273">WM_POINTERUPDATE に対応します。</span><span class="sxs-lookup"><span data-stu-id="78e79-273">Corresponds to WM_POINTERUPDATE.</span></span>

<span data-ttu-id="78e79-274">この列挙型の値は、対応する WM_POINTER \* ウィンドウメッセージと整列します。</span><span class="sxs-lookup"><span data-stu-id="78e79-274">The values of this enum align with the matching WM_POINTER\* window messages.</span></span>

