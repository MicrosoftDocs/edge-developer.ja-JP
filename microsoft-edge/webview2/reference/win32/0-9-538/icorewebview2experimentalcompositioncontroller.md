---
description: Microsoft Edge WebView2 コントロールを使用して Win32 アプリの web コンテンツをホストする
title: Win32 アプリ用 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 アプリ、win32、edge、ICoreWebView2、ICoreWebView2Controller、browser control、edge html
ms.openlocfilehash: 7ae58e35ccaa66e4a711f8e32e06459eb2208b67
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698991"
---
# <span data-ttu-id="639d6-104">インターフェイス ICoreWebView2ExperimentalCompositionController</span><span class="sxs-lookup"><span data-stu-id="639d6-104">interface ICoreWebView2ExperimentalCompositionController</span></span> 

> [!NOTE]
> <span data-ttu-id="639d6-105">これは、プレリリース SDK バージョン0.9.538 に同梱されている実験的な API です。</span><span class="sxs-lookup"><span data-stu-id="639d6-105">This an experimental API that is shipped with our prerelease SDK version 0.9.538.</span></span>

```
interface ICoreWebView2ExperimentalCompositionController
  : public IUnknown
```

<span data-ttu-id="639d6-106">このインターフェイスは、ICoreWebView2Controller インターフェイスの拡張機能であり、ビジュアルホストをサポートします。</span><span class="sxs-lookup"><span data-stu-id="639d6-106">This interface is an extension of the ICoreWebView2Controller interface to support visual hosting.</span></span>

## <span data-ttu-id="639d6-107">まとめ</span><span class="sxs-lookup"><span data-stu-id="639d6-107">Summary</span></span>

 <span data-ttu-id="639d6-108">Members</span><span class="sxs-lookup"><span data-stu-id="639d6-108">Members</span></span>                        | <span data-ttu-id="639d6-109">説明</span><span class="sxs-lookup"><span data-stu-id="639d6-109">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="639d6-110">add_CursorChanged</span><span class="sxs-lookup"><span data-stu-id="639d6-110">add_CursorChanged</span></span>](#add_cursorchanged) | <span data-ttu-id="639d6-111">カーソル変更イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="639d6-111">Add an event handler for the CursorChanged event.</span></span>
[<span data-ttu-id="639d6-112">CreateCoreWebView2PointerInfoFromPointerId</span><span class="sxs-lookup"><span data-stu-id="639d6-112">CreateCoreWebView2PointerInfoFromPointerId</span></span>](#createcorewebview2pointerinfofrompointerid) | <span data-ttu-id="639d6-113">システムから受け取ったポインター Id を[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)に変換するヘルパー関数。</span><span class="sxs-lookup"><span data-stu-id="639d6-113">A helper function to convert a pointerId received from the system into an [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md).</span></span>
[<span data-ttu-id="639d6-114">get_Cursor</span><span class="sxs-lookup"><span data-stu-id="639d6-114">get_Cursor</span></span>](#get_cursor) | <span data-ttu-id="639d6-115">WebView で現在のカーソルの位置を判断します。</span><span class="sxs-lookup"><span data-stu-id="639d6-115">The current cursor that WebView thinks it should be.</span></span>
[<span data-ttu-id="639d6-116">get_RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="639d6-116">get_RootVisualTarget</span></span>](#get_rootvisualtarget) | <span data-ttu-id="639d6-117">RootVisualTarget は、ホストアプリのビジュアルツリー内のビジュアルです。</span><span class="sxs-lookup"><span data-stu-id="639d6-117">The RootVisualTarget is a visual in the hosting app's visual tree.</span></span>
[<span data-ttu-id="639d6-118">get_UIAProvider</span><span class="sxs-lookup"><span data-stu-id="639d6-118">get_UIAProvider</span></span>](#get_uiaprovider) | <span data-ttu-id="639d6-119">WebView の UI オートメーションプロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="639d6-119">Returns the UI Automation Provider for the WebView.</span></span>
[<span data-ttu-id="639d6-120">put_RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="639d6-120">put_RootVisualTarget</span></span>](#put_rootvisualtarget) | <span data-ttu-id="639d6-121">RootVisualTarget プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="639d6-121">Set the RootVisualTarget property.</span></span>
[<span data-ttu-id="639d6-122">remove_CursorChanged</span><span class="sxs-lookup"><span data-stu-id="639d6-122">remove_CursorChanged</span></span>](#remove_cursorchanged) | <span data-ttu-id="639d6-123">Add_CursorChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="639d6-123">Remove an event handler previously added with add_CursorChanged.</span></span>
[<span data-ttu-id="639d6-124">SendMouseInput</span><span class="sxs-lookup"><span data-stu-id="639d6-124">SendMouseInput</span></span>](#sendmouseinput) | <span data-ttu-id="639d6-125">EventKind が COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL または COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL の場合、mouseData は、WHEEL の動きの量を指定します。</span><span class="sxs-lookup"><span data-stu-id="639d6-125">If eventKind is COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL or COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL, then mouseData specifies the amount of wheel movement.</span></span>
[<span data-ttu-id="639d6-126">Sendポインタ入力</span><span class="sxs-lookup"><span data-stu-id="639d6-126">SendPointerInput</span></span>](#sendpointerinput) | <span data-ttu-id="639d6-127">Sendpointer 入力は、COREWEBVIEW2_POINTER_EVENT_KIND で定義された型のタッチポインターまたはペンポインターの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="639d6-127">SendPointerInput accepts touch or pen pointer input of types defined in COREWEBVIEW2_POINTER_EVENT_KIND.</span></span>
[<span data-ttu-id="639d6-128">COREWEBVIEW2_MATRIX_4X4</span><span class="sxs-lookup"><span data-stu-id="639d6-128">COREWEBVIEW2_MATRIX_4X4</span></span>](#corewebview2_matrix_4x4) | <span data-ttu-id="639d6-129">3D 変換を表すマトリックス。</span><span class="sxs-lookup"><span data-stu-id="639d6-129">Matrix that represents a 3D transform.</span></span>
[<span data-ttu-id="639d6-130">COREWEBVIEW2_MOUSE_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="639d6-130">COREWEBVIEW2_MOUSE_EVENT_KIND</span></span>](#corewebview2_mouse_event_kind) | <span data-ttu-id="639d6-131">WebView に送信されるマウスイベントの種類を伝えるために、SendMouseInput で使われるマウスイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="639d6-131">Mouse event type used by SendMouseInput to convey the type of mouse event being sent to WebView.</span></span>
[<span data-ttu-id="639d6-132">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS</span><span class="sxs-lookup"><span data-stu-id="639d6-132">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS</span></span>](#corewebview2_mouse_event_virtual_keys) | <span data-ttu-id="639d6-133">SendMouseInput の COREWEBVIEW2_MOUSE_EVENT_KIND に関連付けられたマウスイベントの仮想キー。</span><span class="sxs-lookup"><span data-stu-id="639d6-133">Mouse event virtual keys associated with a COREWEBVIEW2_MOUSE_EVENT_KIND for SendMouseInput.</span></span>
[<span data-ttu-id="639d6-134">COREWEBVIEW2_POINTER_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="639d6-134">COREWEBVIEW2_POINTER_EVENT_KIND</span></span>](#corewebview2_pointer_event_kind) | <span data-ttu-id="639d6-135">WebView に送信されるポインターイベントの種類を伝えるために Sendpointer 入力で使われるポインターイベントの種類です。</span><span class="sxs-lookup"><span data-stu-id="639d6-135">Pointer event type used by SendPointerInput to convey the type of pointer event being sent to WebView.</span></span>

<span data-ttu-id="639d6-136">ICoreWebView2ExperimentalCompositionController インターフェイスを実装するオブジェクトも ICoreWebView2Controller を実装します。</span><span class="sxs-lookup"><span data-stu-id="639d6-136">An object implementing the ICoreWebView2ExperimentalCompositionController interface will also implement ICoreWebView2Controller.</span></span> <span data-ttu-id="639d6-137">呼び出し元は、サイズ変更、visibility、フォーカスなどのために ICoreWebView2Controller を使うことを前提としており、ICoreWebView2ExperimentalCompositionController を使ってコンポジションツリーに接続し、WebView 用の入力を提供します。</span><span class="sxs-lookup"><span data-stu-id="639d6-137">Callers are expected to use ICoreWebView2Controller for resizing, visibility, focus, and so on, and then use ICoreWebView2ExperimentalCompositionController to connect to a composition tree and provide input meant for the WebView.</span></span>

## <span data-ttu-id="639d6-138">Members</span><span class="sxs-lookup"><span data-stu-id="639d6-138">Members</span></span>

#### <span data-ttu-id="639d6-139">add_CursorChanged</span><span class="sxs-lookup"><span data-stu-id="639d6-139">add_CursorChanged</span></span> 

<span data-ttu-id="639d6-140">カーソル変更イベントのイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="639d6-140">Add an event handler for the CursorChanged event.</span></span>

> <span data-ttu-id="639d6-141">パブリック HRESULT [add_CursorChanged](#add_cursorchanged)([ICoreWebView2ExperimentalCursorChangedEventHandler](icorewebview2experimentalcursorchangedeventhandler.md) \* eventHandler、EventRegistrationToken \* token)</span><span class="sxs-lookup"><span data-stu-id="639d6-141">public HRESULT [add_CursorChanged](#add_cursorchanged)([ICoreWebView2ExperimentalCursorChangedEventHandler](icorewebview2experimentalcursorchangedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="639d6-142">WebView がカーソルの変更であると判断されたときに、イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="639d6-142">The event fires when WebView thinks the cursor should be changed.</span></span> <span data-ttu-id="639d6-143">たとえば、マウスカーソルが現在既定のカーソルであり、テキストの上に移動した場合は、IBeam カーソルに変更しようとすることがあります。</span><span class="sxs-lookup"><span data-stu-id="639d6-143">For example, when the mouse cursor is currently the default cursor but is then moved over text, it may try to change to the IBeam cursor.</span></span>

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

#### <span data-ttu-id="639d6-144">CreateCoreWebView2PointerInfoFromPointerId</span><span class="sxs-lookup"><span data-stu-id="639d6-144">CreateCoreWebView2PointerInfoFromPointerId</span></span> 

<span data-ttu-id="639d6-145">システムから受け取ったポインター Id を[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)に変換するヘルパー関数。</span><span class="sxs-lookup"><span data-stu-id="639d6-145">A helper function to convert a pointerId received from the system into an [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md).</span></span>

> <span data-ttu-id="639d6-146">パブリック HRESULT [CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid)(UINT ポインター ID、HWND parentwindow、struct COREWEBVIEW2_MATRIX_4X4 Transform、 [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \* \* ポインター情報)</span><span class="sxs-lookup"><span data-stu-id="639d6-146">public HRESULT [CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid)(UINT pointerId, HWND parentWindow, struct COREWEBVIEW2_MATRIX_4X4 transform, [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \*\* pointerInfo)</span></span>

<span data-ttu-id="639d6-147">parentWindow は、webview を含む HWND です。</span><span class="sxs-lookup"><span data-stu-id="639d6-147">parentWindow is the HWND that contains the webview.</span></span> <span data-ttu-id="639d6-148">これは、webview を含む hwnd ツリー内の任意の HWND にすることができます。</span><span class="sxs-lookup"><span data-stu-id="639d6-148">This can be any HWND in the hwnd tree that contains the webview.</span></span> <span data-ttu-id="639d6-149">COREWEBVIEW2_MATRIX_4X4 は、その HWND から webview への変換です。</span><span class="sxs-lookup"><span data-stu-id="639d6-149">The COREWEBVIEW2_MATRIX_4X4 is the transform from that HWND to the webview.</span></span> <span data-ttu-id="639d6-150">返された[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)は、Sendポインタ info で使われます。</span><span class="sxs-lookup"><span data-stu-id="639d6-150">The returned [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) is used in SendPointerInfo.</span></span> <span data-ttu-id="639d6-151">ポインターの型は、ペンまたはタッチである必要があります。または、関数は失敗します。</span><span class="sxs-lookup"><span data-stu-id="639d6-151">The pointer type must be either pen or touch or the function will fail.</span></span>



#### <span data-ttu-id="639d6-152">get_Cursor</span><span class="sxs-lookup"><span data-stu-id="639d6-152">get_Cursor</span></span> 

<span data-ttu-id="639d6-153">WebView で現在のカーソルの位置を判断します。</span><span class="sxs-lookup"><span data-stu-id="639d6-153">The current cursor that WebView thinks it should be.</span></span>

> <span data-ttu-id="639d6-154">パブリック HRESULT [get_Cursor](#get_cursor)(hcursor \* cursor)</span><span class="sxs-lookup"><span data-stu-id="639d6-154">public HRESULT [get_Cursor](#get_cursor)(HCURSOR \* cursor)</span></span>

<span data-ttu-id="639d6-155">カーソルは WM_SETCURSOR スルー:: SetCursor で設定するか、WebView ~:: SetClassLongPtr の対応する親または先祖の HWND で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="639d6-155">The cursor should be set in WM_SETCURSOR through ::SetCursor or set on the corresponding parent/ancestor HWND of the WebView through ::SetClassLongPtr.</span></span> <span data-ttu-id="639d6-156">HCURSOR を解放すると、カーソルをすぐに設定するよりも、コピーを保持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="639d6-156">The HCURSOR can be freed so CopyCursor/DestroyCursor is recommended to keep your own copy if you are doing more than immediately setting the cursor.</span></span>

#### <span data-ttu-id="639d6-157">get_RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="639d6-157">get_RootVisualTarget</span></span> 

<span data-ttu-id="639d6-158">RootVisualTarget は、ホストアプリのビジュアルツリー内のビジュアルです。</span><span class="sxs-lookup"><span data-stu-id="639d6-158">The RootVisualTarget is a visual in the hosting app's visual tree.</span></span>

> <span data-ttu-id="639d6-159">パブリック HRESULT [get_RootVisualTarget](#get_rootvisualtarget)(IUnknown \* \* target)</span><span class="sxs-lookup"><span data-stu-id="639d6-159">public HRESULT [get_RootVisualTarget](#get_rootvisualtarget)(IUnknown \*\* target)</span></span>

<span data-ttu-id="639d6-160">このビジュアルは、WebView がそのビジュアルツリーを接続する場所です。</span><span class="sxs-lookup"><span data-stu-id="639d6-160">This visual is where the WebView will connect its visual tree.</span></span> <span data-ttu-id="639d6-161">アプリでは、このビジュアルを使って、アプリ内で WebView を配置します。</span><span class="sxs-lookup"><span data-stu-id="639d6-161">The app uses this visual to position the WebView within the app.</span></span> <span data-ttu-id="639d6-162">この場合も、アプリでは、境界プロパティを使って WebView のサイズを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="639d6-162">The app still needs to use the Bounds property to size the WebView.</span></span> <span data-ttu-id="639d6-163">RootVisualTarget プロパティは、IDCompositionVisual または Windows:: UI:: コンポジション:: ContainerVisual とすることができます。</span><span class="sxs-lookup"><span data-stu-id="639d6-163">The RootVisualTarget property can be an IDCompositionVisual or a Windows::UI::Composition::ContainerVisual.</span></span> <span data-ttu-id="639d6-164">WebView は、プロパティ setter から戻る前に、ビジュアルツリーを提供された visual に接続します。</span><span class="sxs-lookup"><span data-stu-id="639d6-164">WebView will connect its visual tree to the provided visual before returning from the property setter.</span></span> <span data-ttu-id="639d6-165">アプリは、Root Visualtarget プロパティのデバイス設定でコミットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="639d6-165">The app needs to commit on its device setting the RootVisualTarget property.</span></span> <span data-ttu-id="639d6-166">RootVisualTarget プロパティは、アプリのビジュアルツリーから WebView を切断するために nullptr に設定されています。</span><span class="sxs-lookup"><span data-stu-id="639d6-166">The RootVisualTarget property supports being set to nullptr to disconnect the WebView from the app's visual tree.</span></span> 
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

#### <span data-ttu-id="639d6-167">get_UIAProvider</span><span class="sxs-lookup"><span data-stu-id="639d6-167">get_UIAProvider</span></span> 

<span data-ttu-id="639d6-168">WebView の UI オートメーションプロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="639d6-168">Returns the UI Automation Provider for the WebView.</span></span>

> <span data-ttu-id="639d6-169">パブリック HRESULT [get_UIAProvider](#get_uiaprovider)(IUnknown \* \* provider)</span><span class="sxs-lookup"><span data-stu-id="639d6-169">public HRESULT [get_UIAProvider](#get_uiaprovider)(IUnknown \*\* provider)</span></span>

#### <span data-ttu-id="639d6-170">put_RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="639d6-170">put_RootVisualTarget</span></span> 

<span data-ttu-id="639d6-171">RootVisualTarget プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="639d6-171">Set the RootVisualTarget property.</span></span>

> <span data-ttu-id="639d6-172">パブリック HRESULT [put_RootVisualTarget](#put_rootvisualtarget)(IUnknown \* ターゲット)</span><span class="sxs-lookup"><span data-stu-id="639d6-172">public HRESULT [put_RootVisualTarget](#put_rootvisualtarget)(IUnknown \* target)</span></span>

#### <span data-ttu-id="639d6-173">remove_CursorChanged</span><span class="sxs-lookup"><span data-stu-id="639d6-173">remove_CursorChanged</span></span> 

<span data-ttu-id="639d6-174">Add_CursorChanged で以前に追加されたイベントハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="639d6-174">Remove an event handler previously added with add_CursorChanged.</span></span>

> <span data-ttu-id="639d6-175">パブリック HRESULT [remove_CursorChanged](#remove_cursorchanged)(EventRegistrationToken token)</span><span class="sxs-lookup"><span data-stu-id="639d6-175">public HRESULT [remove_CursorChanged](#remove_cursorchanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="639d6-176">SendMouseInput</span><span class="sxs-lookup"><span data-stu-id="639d6-176">SendMouseInput</span></span> 

<span data-ttu-id="639d6-177">EventKind が COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL または COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL の場合、mouseData は、WHEEL の動きの量を指定します。</span><span class="sxs-lookup"><span data-stu-id="639d6-177">If eventKind is COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL or COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL, then mouseData specifies the amount of wheel movement.</span></span>

> <span data-ttu-id="639d6-178">パブリック HRESULT 送信[マウス入力](#sendmouseinput)([COREWEBVIEW2_MOUSE_EVENT_KIND](#corewebview2_mouse_event_kind) eventkind、 [COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS](#corewebview2_mouse_event_virtual_keys) VIRTUALKEYS、UINT32 mousedata、ポイントポイント)</span><span class="sxs-lookup"><span data-stu-id="639d6-178">public HRESULT [SendMouseInput](#sendmouseinput)([COREWEBVIEW2_MOUSE_EVENT_KIND](#corewebview2_mouse_event_kind) eventKind, [COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS](#corewebview2_mouse_event_virtual_keys) virtualKeys, UINT32 mouseData, POINT point)</span></span>

<span data-ttu-id="639d6-179">正の値は、ホイールがユーザーによって前方に回転されたことを示します。負の値は、ホイールが背面に回転していることを示します。</span><span class="sxs-lookup"><span data-stu-id="639d6-179">A positive value indicates that the wheel was rotated forward, away from the user; a negative value indicates that the wheel was rotated backward, toward the user.</span></span> <span data-ttu-id="639d6-180">ホイールクリックの1つは、120として定義されている WHEEL_DELTA として定義されています。</span><span class="sxs-lookup"><span data-stu-id="639d6-180">One wheel click is defined as WHEEL_DELTA, which is 120.</span></span> <span data-ttu-id="639d6-181">EventKind が COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOUBLE_CLICK COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOWN、または COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_UP の場合、mouseData は、どの X ボタンが押されたか、離されたかを指定します。</span><span class="sxs-lookup"><span data-stu-id="639d6-181">If eventKind is COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOUBLE_CLICK COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOWN, or COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_UP, then mouseData specifies which X buttons were pressed or released.</span></span> <span data-ttu-id="639d6-182">この値は、最初の X ボタンが押されている場合は1、2番目の X ボタンが押されたとき、または離された場合は1になります。</span><span class="sxs-lookup"><span data-stu-id="639d6-182">This value should be 1 if the first X button is pressed/released and 2 if the second X button is pressed/released.</span></span> <span data-ttu-id="639d6-183">EventKind が COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE の場合、virtualKeys、mouseData、point はすべてゼロである必要があります。</span><span class="sxs-lookup"><span data-stu-id="639d6-183">If eventKind is COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE, then virtualKeys, mouseData, and point should all be zero.</span></span> <span data-ttu-id="639d6-184">EventKind がその他の値である場合は、mouseData は0である必要があります。</span><span class="sxs-lookup"><span data-stu-id="639d6-184">If eventKind is any other value, then mouseData should be zero.</span></span> <span data-ttu-id="639d6-185">Point は、WebView のクライアント座標空間に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="639d6-185">Point is expected to be in the client coordinate space of the WebView.</span></span> <span data-ttu-id="639d6-186">WebView から始まり、WebView とホストアプリケーションの外側に移動する可能性のあるマウスイベントを追跡するには、SetCapture と ReleaseCapture の呼び出しをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="639d6-186">To track mouse events that start in the WebView and can potentially move outside of the WebView and host application, calling SetCapture and ReleaseCapture is recommended.</span></span> <span data-ttu-id="639d6-187">ホバーポップアップを消すには、WM_MOUSELEAVE メッセージを送信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="639d6-187">To dismiss hover popups, it is also recommended to send WM_MOUSELEAVE messages.</span></span> 
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

#### <span data-ttu-id="639d6-188">Sendポインタ入力</span><span class="sxs-lookup"><span data-stu-id="639d6-188">SendPointerInput</span></span> 

<span data-ttu-id="639d6-189">Sendpointer 入力は、COREWEBVIEW2_POINTER_EVENT_KIND で定義された型のタッチポインターまたはペンポインターの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="639d6-189">SendPointerInput accepts touch or pen pointer input of types defined in COREWEBVIEW2_POINTER_EVENT_KIND.</span></span>

> <span data-ttu-id="639d6-190">パブリック HRESULT 送信[ポインター入力](#sendpointerinput)([COREWEBVIEW2_POINTER_EVENT_KIND](#corewebview2_pointer_event_kind) eventType、 [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \* のポインター情報)</span><span class="sxs-lookup"><span data-stu-id="639d6-190">public HRESULT [SendPointerInput](#sendpointerinput)([COREWEBVIEW2_POINTER_EVENT_KIND](#corewebview2_pointer_event_kind) eventType, [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \* pointerInfo)</span></span>

<span data-ttu-id="639d6-191">システムからのポインター入力は、最初に[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="639d6-191">Any pointer input from the system must be converted into an [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) first.</span></span>

#### <span data-ttu-id="639d6-192">COREWEBVIEW2_MATRIX_4X4</span><span class="sxs-lookup"><span data-stu-id="639d6-192">COREWEBVIEW2_MATRIX_4X4</span></span> 

<span data-ttu-id="639d6-193">3D 変換を表すマトリックス。</span><span class="sxs-lookup"><span data-stu-id="639d6-193">Matrix that represents a 3D transform.</span></span>

> <span data-ttu-id="639d6-194">typedef [COREWEBVIEW2_MATRIX_4X4](#corewebview2_matrix_4x4)</span><span class="sxs-lookup"><span data-stu-id="639d6-194">typedef [COREWEBVIEW2_MATRIX_4X4](#corewebview2_matrix_4x4)</span></span>

<span data-ttu-id="639d6-195">この変換は、CreateCoreWebView2PointerInfoFromPointerId を呼び出したときに適切な座標を計算するために使われます。</span><span class="sxs-lookup"><span data-stu-id="639d6-195">This transform is used to calculate correct coordinates when calling CreateCoreWebView2PointerInfoFromPointerId.</span></span> <span data-ttu-id="639d6-196">これは D2D1_MATRIX_4X4_F と同じです。</span><span class="sxs-lookup"><span data-stu-id="639d6-196">This is equivalent to a D2D1_MATRIX_4X4_F</span></span>

#### <span data-ttu-id="639d6-197">COREWEBVIEW2_MOUSE_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="639d6-197">COREWEBVIEW2_MOUSE_EVENT_KIND</span></span> 

<span data-ttu-id="639d6-198">WebView に送信されるマウスイベントの種類を伝えるために、SendMouseInput で使われるマウスイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="639d6-198">Mouse event type used by SendMouseInput to convey the type of mouse event being sent to WebView.</span></span>

> <span data-ttu-id="639d6-199">列挙型[COREWEBVIEW2_MOUSE_EVENT_KIND](#corewebview2_mouse_event_kind)</span><span class="sxs-lookup"><span data-stu-id="639d6-199">enum [COREWEBVIEW2_MOUSE_EVENT_KIND](#corewebview2_mouse_event_kind)</span></span>

 <span data-ttu-id="639d6-200">値</span><span class="sxs-lookup"><span data-stu-id="639d6-200">Values</span></span>                         | <span data-ttu-id="639d6-201">説明</span><span class="sxs-lookup"><span data-stu-id="639d6-201">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="639d6-202">COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL</span><span class="sxs-lookup"><span data-stu-id="639d6-202">COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL</span></span>            | <span data-ttu-id="639d6-203">マウスの水平ホイールスクロールイベント、WM_MOUSEHWHEEL。</span><span class="sxs-lookup"><span data-stu-id="639d6-203">Mouse horizontal wheel scroll event, WM_MOUSEHWHEEL.</span></span>
<span data-ttu-id="639d6-204">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_DOUBLE_CLICK</span><span class="sxs-lookup"><span data-stu-id="639d6-204">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_DOUBLE_CLICK</span></span>            | <span data-ttu-id="639d6-205">[左] ボタンをダブルクリックすると、[マウスイベント] が WM_LBUTTONDBLCLK ます。</span><span class="sxs-lookup"><span data-stu-id="639d6-205">Left button double click mouse event, WM_LBUTTONDBLCLK.</span></span>
<span data-ttu-id="639d6-206">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_DOWN</span><span class="sxs-lookup"><span data-stu-id="639d6-206">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_DOWN</span></span>            | <span data-ttu-id="639d6-207">[左] ボタンのマウスイベント、WM_LBUTTONDOWN。</span><span class="sxs-lookup"><span data-stu-id="639d6-207">Left button down mouse event, WM_LBUTTONDOWN.</span></span>
<span data-ttu-id="639d6-208">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_UP</span><span class="sxs-lookup"><span data-stu-id="639d6-208">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_UP</span></span>            | <span data-ttu-id="639d6-209">[左] ボタンのマウスイベント、WM_LBUTTONUP。</span><span class="sxs-lookup"><span data-stu-id="639d6-209">Left button up mouse event, WM_LBUTTONUP.</span></span>
<span data-ttu-id="639d6-210">COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE</span><span class="sxs-lookup"><span data-stu-id="639d6-210">COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE</span></span>            | <span data-ttu-id="639d6-211">マウスの終了イベント、WM_MOUSELEAVE。</span><span class="sxs-lookup"><span data-stu-id="639d6-211">Mouse leave event, WM_MOUSELEAVE.</span></span>
<span data-ttu-id="639d6-212">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_DOUBLE_CLICK</span><span class="sxs-lookup"><span data-stu-id="639d6-212">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_DOUBLE_CLICK</span></span>            | <span data-ttu-id="639d6-213">中央ボタン [マウスイベント]、[WM_MBUTTONDBLCLK] の順にダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="639d6-213">Middle button double click mouse event, WM_MBUTTONDBLCLK.</span></span>
<span data-ttu-id="639d6-214">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_DOWN</span><span class="sxs-lookup"><span data-stu-id="639d6-214">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_DOWN</span></span>            | <span data-ttu-id="639d6-215">中央ボタンのマウスイベント、WM_MBUTTONDOWN。</span><span class="sxs-lookup"><span data-stu-id="639d6-215">Middle button down mouse event, WM_MBUTTONDOWN.</span></span>
<span data-ttu-id="639d6-216">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_UP</span><span class="sxs-lookup"><span data-stu-id="639d6-216">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_UP</span></span>            | <span data-ttu-id="639d6-217">中央ボタン上のマウスイベント、WM_MBUTTONUP。</span><span class="sxs-lookup"><span data-stu-id="639d6-217">Middle button up mouse event, WM_MBUTTONUP.</span></span>
<span data-ttu-id="639d6-218">COREWEBVIEW2_MOUSE_EVENT_KIND_MOVE</span><span class="sxs-lookup"><span data-stu-id="639d6-218">COREWEBVIEW2_MOUSE_EVENT_KIND_MOVE</span></span>            | <span data-ttu-id="639d6-219">マウス移動イベント、WM_MOUSEMOVE。</span><span class="sxs-lookup"><span data-stu-id="639d6-219">Mouse move event, WM_MOUSEMOVE.</span></span>
<span data-ttu-id="639d6-220">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_DOUBLE_CLICK</span><span class="sxs-lookup"><span data-stu-id="639d6-220">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_DOUBLE_CLICK</span></span>            | <span data-ttu-id="639d6-221">右ボタン [マウスイベント]、[WM_RBUTTONDBLCLK] の順にダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="639d6-221">Right button double click mouse event, WM_RBUTTONDBLCLK.</span></span>
<span data-ttu-id="639d6-222">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_DOWN</span><span class="sxs-lookup"><span data-stu-id="639d6-222">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_DOWN</span></span>            | <span data-ttu-id="639d6-223">右ボタンのマウスイベント、WM_RBUTTONDOWN。</span><span class="sxs-lookup"><span data-stu-id="639d6-223">Right button down mouse event, WM_RBUTTONDOWN.</span></span>
<span data-ttu-id="639d6-224">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_UP</span><span class="sxs-lookup"><span data-stu-id="639d6-224">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_UP</span></span>            | <span data-ttu-id="639d6-225">マウスの右上にあるイベントの [WM_RBUTTONUP] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="639d6-225">Right button up mouse event, WM_RBUTTONUP.</span></span>
<span data-ttu-id="639d6-226">COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL</span><span class="sxs-lookup"><span data-stu-id="639d6-226">COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL</span></span>            | <span data-ttu-id="639d6-227">マウスホイールスクロールイベント、WM_MOUSEWHEEL。</span><span class="sxs-lookup"><span data-stu-id="639d6-227">Mouse wheel scroll event, WM_MOUSEWHEEL.</span></span>
<span data-ttu-id="639d6-228">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOUBLE_CLICK</span><span class="sxs-lookup"><span data-stu-id="639d6-228">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOUBLE_CLICK</span></span>            | <span data-ttu-id="639d6-229">第1または第2の X ボタンをダブルクリックすると、[マウスイベント] が WM_XBUTTONDBLCLK ます。</span><span class="sxs-lookup"><span data-stu-id="639d6-229">First or second X button double click mouse event, WM_XBUTTONDBLCLK.</span></span>
<span data-ttu-id="639d6-230">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOWN</span><span class="sxs-lookup"><span data-stu-id="639d6-230">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOWN</span></span>            | <span data-ttu-id="639d6-231">最初または2番目の X ボタンのマウスイベントを WM_XBUTTONDOWN します。</span><span class="sxs-lookup"><span data-stu-id="639d6-231">First or second X button down mouse event, WM_XBUTTONDOWN.</span></span>
<span data-ttu-id="639d6-232">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_UP</span><span class="sxs-lookup"><span data-stu-id="639d6-232">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_UP</span></span>            | <span data-ttu-id="639d6-233">最初または2番目の X ボタンのマウスイベントを WM_XBUTTONUP します。</span><span class="sxs-lookup"><span data-stu-id="639d6-233">First or second X button up mouse event, WM_XBUTTONUP.</span></span>

<span data-ttu-id="639d6-234">この列挙型の値は、対応する WM_ \* ウィンドウメッセージと整列します。</span><span class="sxs-lookup"><span data-stu-id="639d6-234">The values of this enum align with the matching WM_\* window messages.</span></span>

#### <span data-ttu-id="639d6-235">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS</span><span class="sxs-lookup"><span data-stu-id="639d6-235">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS</span></span> 

<span data-ttu-id="639d6-236">SendMouseInput の COREWEBVIEW2_MOUSE_EVENT_KIND に関連付けられたマウスイベントの仮想キー。</span><span class="sxs-lookup"><span data-stu-id="639d6-236">Mouse event virtual keys associated with a COREWEBVIEW2_MOUSE_EVENT_KIND for SendMouseInput.</span></span>

> <span data-ttu-id="639d6-237">列挙型[COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS](#corewebview2_mouse_event_virtual_keys)</span><span class="sxs-lookup"><span data-stu-id="639d6-237">enum [COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS](#corewebview2_mouse_event_virtual_keys)</span></span>

 <span data-ttu-id="639d6-238">値</span><span class="sxs-lookup"><span data-stu-id="639d6-238">Values</span></span>                         | <span data-ttu-id="639d6-239">説明</span><span class="sxs-lookup"><span data-stu-id="639d6-239">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="639d6-240">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_NONE</span><span class="sxs-lookup"><span data-stu-id="639d6-240">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_NONE</span></span>            | <span data-ttu-id="639d6-241">追加のキーが押されていません。</span><span class="sxs-lookup"><span data-stu-id="639d6-241">No additional keys pressed.</span></span>
<span data-ttu-id="639d6-242">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_LEFT_BUTTON</span><span class="sxs-lookup"><span data-stu-id="639d6-242">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_LEFT_BUTTON</span></span>            | <span data-ttu-id="639d6-243">マウスの左ボタンが押されています。 MK_LBUTTON。</span><span class="sxs-lookup"><span data-stu-id="639d6-243">Left mouse button is down, MK_LBUTTON.</span></span>
<span data-ttu-id="639d6-244">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_RIGHT_BUTTON</span><span class="sxs-lookup"><span data-stu-id="639d6-244">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_RIGHT_BUTTON</span></span>            | <span data-ttu-id="639d6-245">マウスの右ボタンが押されて MK_RBUTTON ます。</span><span class="sxs-lookup"><span data-stu-id="639d6-245">Right mouse button is down, MK_RBUTTON.</span></span>
<span data-ttu-id="639d6-246">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_SHIFT</span><span class="sxs-lookup"><span data-stu-id="639d6-246">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_SHIFT</span></span>            | <span data-ttu-id="639d6-247">SHIFT キーを押しながら MK_SHIFT ます。</span><span class="sxs-lookup"><span data-stu-id="639d6-247">SHIFT key is down, MK_SHIFT.</span></span>
<span data-ttu-id="639d6-248">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_CONTROL</span><span class="sxs-lookup"><span data-stu-id="639d6-248">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_CONTROL</span></span>            | <span data-ttu-id="639d6-249">CTRL キーを押しながら MK_CONTROL ます。</span><span class="sxs-lookup"><span data-stu-id="639d6-249">CTRL key is down, MK_CONTROL.</span></span>
<span data-ttu-id="639d6-250">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_MIDDLE_BUTTON</span><span class="sxs-lookup"><span data-stu-id="639d6-250">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_MIDDLE_BUTTON</span></span>            | <span data-ttu-id="639d6-251">マウスの中央ボタンが押されて MK_MBUTTON。</span><span class="sxs-lookup"><span data-stu-id="639d6-251">Middle mouse button is down, MK_MBUTTON.</span></span>
<span data-ttu-id="639d6-252">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_X_BUTTON1</span><span class="sxs-lookup"><span data-stu-id="639d6-252">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_X_BUTTON1</span></span>            | <span data-ttu-id="639d6-253">最初の X ボタンが押されて MK_XBUTTON1。</span><span class="sxs-lookup"><span data-stu-id="639d6-253">First X button is down, MK_XBUTTON1.</span></span>
<span data-ttu-id="639d6-254">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_X_BUTTON2</span><span class="sxs-lookup"><span data-stu-id="639d6-254">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_X_BUTTON2</span></span>            | <span data-ttu-id="639d6-255">第2の X ボタンが押され、MK_XBUTTON2 ます。</span><span class="sxs-lookup"><span data-stu-id="639d6-255">Second X button is down, MK_XBUTTON2.</span></span>

<span data-ttu-id="639d6-256">これらの値は、複数の仮想キーがイベントとして押されている場合に、ビットフラグに組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="639d6-256">These values can be combined into a bit flag if more than one virtual key is pressed for the event.</span></span> <span data-ttu-id="639d6-257">この列挙型の値は、一致する MK_ \* マウスキーと整列します。</span><span class="sxs-lookup"><span data-stu-id="639d6-257">The values of this enum align with the matching MK_\* mouse keys.</span></span>

#### <span data-ttu-id="639d6-258">COREWEBVIEW2_POINTER_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="639d6-258">COREWEBVIEW2_POINTER_EVENT_KIND</span></span> 

<span data-ttu-id="639d6-259">WebView に送信されるポインターイベントの種類を伝えるために Sendpointer 入力で使われるポインターイベントの種類です。</span><span class="sxs-lookup"><span data-stu-id="639d6-259">Pointer event type used by SendPointerInput to convey the type of pointer event being sent to WebView.</span></span>

> <span data-ttu-id="639d6-260">列挙型[COREWEBVIEW2_POINTER_EVENT_KIND](#corewebview2_pointer_event_kind)</span><span class="sxs-lookup"><span data-stu-id="639d6-260">enum [COREWEBVIEW2_POINTER_EVENT_KIND](#corewebview2_pointer_event_kind)</span></span>

 <span data-ttu-id="639d6-261">値</span><span class="sxs-lookup"><span data-stu-id="639d6-261">Values</span></span>                         | <span data-ttu-id="639d6-262">説明</span><span class="sxs-lookup"><span data-stu-id="639d6-262">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="639d6-263">COREWEBVIEW2_POINTER_EVENT_KIND_ACTIVATE</span><span class="sxs-lookup"><span data-stu-id="639d6-263">COREWEBVIEW2_POINTER_EVENT_KIND_ACTIVATE</span></span>            | <span data-ttu-id="639d6-264">WM_POINTERACTIVATE に対応します。</span><span class="sxs-lookup"><span data-stu-id="639d6-264">Corresponds to WM_POINTERACTIVATE.</span></span>
<span data-ttu-id="639d6-265">COREWEBVIEW2_POINTER_EVENT_KIND_DOWN</span><span class="sxs-lookup"><span data-stu-id="639d6-265">COREWEBVIEW2_POINTER_EVENT_KIND_DOWN</span></span>            | <span data-ttu-id="639d6-266">WM_POINTERDOWN に対応します。</span><span class="sxs-lookup"><span data-stu-id="639d6-266">Corresponds to WM_POINTERDOWN.</span></span>
<span data-ttu-id="639d6-267">COREWEBVIEW2_POINTER_EVENT_KIND_ENTER</span><span class="sxs-lookup"><span data-stu-id="639d6-267">COREWEBVIEW2_POINTER_EVENT_KIND_ENTER</span></span>            | <span data-ttu-id="639d6-268">WM_POINTERENTER に対応します。</span><span class="sxs-lookup"><span data-stu-id="639d6-268">Corresponds to WM_POINTERENTER.</span></span>
<span data-ttu-id="639d6-269">COREWEBVIEW2_POINTER_EVENT_KIND_LEAVE</span><span class="sxs-lookup"><span data-stu-id="639d6-269">COREWEBVIEW2_POINTER_EVENT_KIND_LEAVE</span></span>            | <span data-ttu-id="639d6-270">WM_POINTERLEAVE に対応します。</span><span class="sxs-lookup"><span data-stu-id="639d6-270">Corresponds to WM_POINTERLEAVE.</span></span>
<span data-ttu-id="639d6-271">COREWEBVIEW2_POINTER_EVENT_KIND_UP</span><span class="sxs-lookup"><span data-stu-id="639d6-271">COREWEBVIEW2_POINTER_EVENT_KIND_UP</span></span>            | <span data-ttu-id="639d6-272">WM_POINTERUP に対応します。</span><span class="sxs-lookup"><span data-stu-id="639d6-272">Corresponds to WM_POINTERUP.</span></span>
<span data-ttu-id="639d6-273">COREWEBVIEW2_POINTER_EVENT_KIND_UPDATE</span><span class="sxs-lookup"><span data-stu-id="639d6-273">COREWEBVIEW2_POINTER_EVENT_KIND_UPDATE</span></span>            | <span data-ttu-id="639d6-274">WM_POINTERUPDATE に対応します。</span><span class="sxs-lookup"><span data-stu-id="639d6-274">Corresponds to WM_POINTERUPDATE.</span></span>

<span data-ttu-id="639d6-275">この列挙型の値は、対応する WM_POINTER \* ウィンドウメッセージと整列します。</span><span class="sxs-lookup"><span data-stu-id="639d6-275">The values of this enum align with the matching WM_POINTER\* window messages.</span></span>

