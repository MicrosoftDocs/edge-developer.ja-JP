---
description: Microsoft Edge WebView2 コントロールを使用してネイティブアプリケーションに web 技術 (HTML、CSS、JavaScript) を埋め込む
title: WebView2 について CoreWebView2CompositionController
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、webview、.net、wpf、winforms、アプリ、edge、CoreWebView2、CoreWebView2Controller、browser control、edge html、Microsoft の WebView2。 CoreWebView2CompositionController。
ms.openlocfilehash: 1eb2498e05e2ec9fafa317f6108d022f7354c249
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885283"
---
# <span data-ttu-id="8df11-104">WebView2 クラス (CoreWebView2CompositionController クラス)</span><span class="sxs-lookup"><span data-stu-id="8df11-104">Microsoft.Web.WebView2.Core.CoreWebView2CompositionController class</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="8df11-105">名前空間: WebView2 () </span><span class="sxs-lookup"><span data-stu-id="8df11-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="8df11-106">アセンブリ: Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="8df11-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="8df11-107">このクラスは、CoreWebView2Controller クラスの拡張機能であり、ビジュアルホストをサポートします。</span><span class="sxs-lookup"><span data-stu-id="8df11-107">This class is an extension of the CoreWebView2Controller class to support visual hosting.</span></span>

## <span data-ttu-id="8df11-108">まとめ</span><span class="sxs-lookup"><span data-stu-id="8df11-108">Summary</span></span>

 <span data-ttu-id="8df11-109">Members</span><span class="sxs-lookup"><span data-stu-id="8df11-109">Members</span></span>                        | <span data-ttu-id="8df11-110">説明</span><span class="sxs-lookup"><span data-stu-id="8df11-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="8df11-111">Cursor</span><span class="sxs-lookup"><span data-stu-id="8df11-111">Cursor</span></span>](#cursor) | <span data-ttu-id="8df11-112">WebView で現在のカーソルの位置を判断します。</span><span class="sxs-lookup"><span data-stu-id="8df11-112">The current cursor that WebView thinks it should be.</span></span>
[<span data-ttu-id="8df11-113">カーソルが変更されました</span><span class="sxs-lookup"><span data-stu-id="8df11-113">CursorChanged</span></span>](#cursorchanged) | <span data-ttu-id="8df11-114">WebView がカーソルの変更であると判断されたときに、イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="8df11-114">The event fires when WebView thinks the cursor should be changed.</span></span>
[<span data-ttu-id="8df11-115">RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="8df11-115">RootVisualTarget</span></span>](#rootvisualtarget) | <span data-ttu-id="8df11-116">RootVisualTarget は、ホストアプリのビジュアルツリー内のビジュアルです。</span><span class="sxs-lookup"><span data-stu-id="8df11-116">The RootVisualTarget is a visual in the hosting app's visual tree.</span></span>
[<span data-ttu-id="8df11-117">UIAProvider</span><span class="sxs-lookup"><span data-stu-id="8df11-117">UIAProvider</span></span>](#uiaprovider) | <span data-ttu-id="8df11-118">WebView の UI オートメーションプロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="8df11-118">Returns the UI Automation Provider for the WebView.</span></span>
[<span data-ttu-id="8df11-119">CreateCoreWebView2PointerInfoFromPointerId</span><span class="sxs-lookup"><span data-stu-id="8df11-119">CreateCoreWebView2PointerInfoFromPointerId</span></span>](#createcorewebview2pointerinfofrompointerid) | <span data-ttu-id="8df11-120">システムから受け取ったポインター Id を CoreWebView2PointerInfo に変換するヘルパー関数。</span><span class="sxs-lookup"><span data-stu-id="8df11-120">A helper function to convert a pointerId received from the system into a CoreWebView2PointerInfo.</span></span>
[<span data-ttu-id="8df11-121">SendMouseInput</span><span class="sxs-lookup"><span data-stu-id="8df11-121">SendMouseInput</span></span>](#sendmouseinput) | <span data-ttu-id="8df11-122">EventKind が CoreWebView2MouseEventKind Wheel または CoreWebView2MouseEventKind の場合は、mouseData はホイールの動きの量を指定します。</span><span class="sxs-lookup"><span data-stu-id="8df11-122">If eventKind is CoreWebView2MouseEventKind.HorizontalWheel or CoreWebView2MouseEventKind.Wheel, then mouseData specifies the amount of wheel movement.</span></span>
[<span data-ttu-id="8df11-123">Sendポインタ入力</span><span class="sxs-lookup"><span data-stu-id="8df11-123">SendPointerInput</span></span>](#sendpointerinput) | <span data-ttu-id="8df11-124">Sendpointer Input は、CoreWebView2PointerEventKind で定義された型のタッチポインターまたはペンポインターの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="8df11-124">SendPointerInput accepts touch or pen pointer input of types defined in CoreWebView2PointerEventKind.</span></span>

## <span data-ttu-id="8df11-125">Members</span><span class="sxs-lookup"><span data-stu-id="8df11-125">Members</span></span>

#### <span data-ttu-id="8df11-126">Cursor</span><span class="sxs-lookup"><span data-stu-id="8df11-126">Cursor</span></span> 

<span data-ttu-id="8df11-127">WebView で現在のカーソルの位置を判断します。</span><span class="sxs-lookup"><span data-stu-id="8df11-127">The current cursor that WebView thinks it should be.</span></span>

> <span data-ttu-id="8df11-128">パブリック IntPtr[カーソル](#cursor)</span><span class="sxs-lookup"><span data-stu-id="8df11-128">public IntPtr [Cursor](#cursor)</span></span>

<span data-ttu-id="8df11-129">WM_SETCURSOR でカーソルを設定するか、WebView ~ SetClassLongPtr の対応する親または先祖の HWND を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8df11-129">The cursor should be set in WM_SETCURSOR through Mouse.SetCursor or set on the corresponding parent/ancestor HWND of the WebView through SetClassLongPtr.</span></span> <span data-ttu-id="8df11-130">HCURSOR を解放すると、カーソルをすぐに設定するよりも、コピーを保持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8df11-130">The HCURSOR can be freed so CopyCursor/DestroyCursor is recommended to keep your own copy if you are doing more than immediately setting the cursor.</span></span>

#### <span data-ttu-id="8df11-131">カーソルが変更されました</span><span class="sxs-lookup"><span data-stu-id="8df11-131">CursorChanged</span></span> 

<span data-ttu-id="8df11-132">WebView がカーソルの変更であると判断されたときに、イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="8df11-132">The event fires when WebView thinks the cursor should be changed.</span></span>

> <span data-ttu-id="8df11-133">< オブジェクト >[カーソルが変更された](#cursorchanged)パブリックイベント EventHandler</span><span class="sxs-lookup"><span data-stu-id="8df11-133">public event EventHandler< object > [CursorChanged](#cursorchanged)</span></span>

<span data-ttu-id="8df11-134">たとえば、マウスカーソルが現在既定のカーソルであり、テキストの上に移動した場合は、IBeam カーソルに変更しようとすることがあります。</span><span class="sxs-lookup"><span data-stu-id="8df11-134">For example, when the mouse cursor is currently the default cursor but is then moved over text, it may try to change to the IBeam cursor.</span></span>

#### <span data-ttu-id="8df11-135">RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="8df11-135">RootVisualTarget</span></span> 

<span data-ttu-id="8df11-136">RootVisualTarget は、ホストアプリのビジュアルツリー内のビジュアルです。</span><span class="sxs-lookup"><span data-stu-id="8df11-136">The RootVisualTarget is a visual in the hosting app's visual tree.</span></span>

> <span data-ttu-id="8df11-137">パブリックオブジェクト[Rootvisualtarget](#rootvisualtarget)</span><span class="sxs-lookup"><span data-stu-id="8df11-137">public object [RootVisualTarget](#rootvisualtarget)</span></span>

<span data-ttu-id="8df11-138">このビジュアルは、WebView がそのビジュアルツリーを接続する場所です。</span><span class="sxs-lookup"><span data-stu-id="8df11-138">This visual is where the WebView will connect its visual tree.</span></span> <span data-ttu-id="8df11-139">アプリでは、このビジュアルを使って、アプリ内で WebView を配置します。</span><span class="sxs-lookup"><span data-stu-id="8df11-139">The app uses this visual to position the WebView within the app.</span></span> <span data-ttu-id="8df11-140">この場合も、アプリでは、境界プロパティを使って WebView のサイズを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8df11-140">The app still needs to use the Bounds property to size the WebView.</span></span> <span data-ttu-id="8df11-141">RootVisualTarget プロパティは、IDCompositionVisual または Windows:: UI:: コンポジション:: ContainerVisual とすることができます。</span><span class="sxs-lookup"><span data-stu-id="8df11-141">The RootVisualTarget property can be an IDCompositionVisual or a Windows::UI::Composition::ContainerVisual.</span></span> <span data-ttu-id="8df11-142">WebView は、プロパティ setter から戻る前に、ビジュアルツリーを提供された visual に接続します。</span><span class="sxs-lookup"><span data-stu-id="8df11-142">WebView will connect its visual tree to the provided visual before returning from the property setter.</span></span> <span data-ttu-id="8df11-143">アプリは、Root Visualtarget プロパティのデバイス設定でコミットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8df11-143">The app needs to commit on its device setting the RootVisualTarget property.</span></span> <span data-ttu-id="8df11-144">RootVisualTarget プロパティは、アプリのビジュアルツリーから WebView を切断するために nullptr に設定されています。</span><span class="sxs-lookup"><span data-stu-id="8df11-144">The RootVisualTarget property supports being set to nullptr to disconnect the WebView from the app's visual tree.</span></span>

#### <span data-ttu-id="8df11-145">UIAProvider</span><span class="sxs-lookup"><span data-stu-id="8df11-145">UIAProvider</span></span> 

<span data-ttu-id="8df11-146">WebView の UI オートメーションプロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="8df11-146">Returns the UI Automation Provider for the WebView.</span></span>

> <span data-ttu-id="8df11-147">パブリックオブジェクト[Uiaprovider](#uiaprovider)</span><span class="sxs-lookup"><span data-stu-id="8df11-147">public object [UIAProvider](#uiaprovider)</span></span>

#### <span data-ttu-id="8df11-148">CreateCoreWebView2PointerInfoFromPointerId</span><span class="sxs-lookup"><span data-stu-id="8df11-148">CreateCoreWebView2PointerInfoFromPointerId</span></span> 

<span data-ttu-id="8df11-149">システムから受け取ったポインター Id を CoreWebView2PointerInfo に変換するヘルパー関数。</span><span class="sxs-lookup"><span data-stu-id="8df11-149">A helper function to convert a pointerId received from the system into a CoreWebView2PointerInfo.</span></span>

> <span data-ttu-id="8df11-150">パブリック[CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) [CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid)(Uint ポインター Id、IntPtr parentwindow、Matrix4x4 transform)</span><span class="sxs-lookup"><span data-stu-id="8df11-150">public [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) [CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid)(uint PointerId, IntPtr ParentWindow, Matrix4x4 transform)</span></span>

<span data-ttu-id="8df11-151">parentWindow は、webview を含む HWND です。</span><span class="sxs-lookup"><span data-stu-id="8df11-151">parentWindow is the HWND that contains the webview.</span></span> <span data-ttu-id="8df11-152">これは、webview を含む hwnd ツリー内の任意の HWND にすることができます。</span><span class="sxs-lookup"><span data-stu-id="8df11-152">This can be any HWND in the hwnd tree that contains the webview.</span></span> <span data-ttu-id="8df11-153">CoreWebView2Matrix4x4 は、その HWND から webview への変換です。</span><span class="sxs-lookup"><span data-stu-id="8df11-153">The CoreWebView2Matrix4x4 is the transform from that HWND to the webview.</span></span> <span data-ttu-id="8df11-154">返された CoreWebView2PointerInfo は、Sendポインタ Info で使われます。</span><span class="sxs-lookup"><span data-stu-id="8df11-154">The returned CoreWebView2PointerInfo is used in SendPointerInfo.</span></span> <span data-ttu-id="8df11-155">ポインターの型は、ペンまたはタッチである必要があります。または、関数は失敗します。</span><span class="sxs-lookup"><span data-stu-id="8df11-155">The pointer type must be either pen or touch or the function will fail.</span></span>

#### <span data-ttu-id="8df11-156">SendMouseInput</span><span class="sxs-lookup"><span data-stu-id="8df11-156">SendMouseInput</span></span> 

<span data-ttu-id="8df11-157">EventKind が CoreWebView2MouseEventKind Wheel または CoreWebView2MouseEventKind の場合は、mouseData はホイールの動きの量を指定します。</span><span class="sxs-lookup"><span data-stu-id="8df11-157">If eventKind is CoreWebView2MouseEventKind.HorizontalWheel or CoreWebView2MouseEventKind.Wheel, then mouseData specifies the amount of wheel movement.</span></span>

> <span data-ttu-id="8df11-158">パブリックの void [Sendmouseinput](#sendmouseinput)([CoreWebView2MouseEventKind](./namespace-microsoft-web-webview2-core.md) eventkind、 [CoreWebView2MouseEventVirtualKeys](./namespace-microsoft-web-webview2-core.md) Virtualkeys、uint mousedata、ポイントポイント)</span><span class="sxs-lookup"><span data-stu-id="8df11-158">public void [SendMouseInput](#sendmouseinput)([CoreWebView2MouseEventKind](./namespace-microsoft-web-webview2-core.md) eventKind, [CoreWebView2MouseEventVirtualKeys](./namespace-microsoft-web-webview2-core.md) virtualKeys, uint mouseData, Point point)</span></span>

<span data-ttu-id="8df11-159">正の値は、ホイールがユーザーによって前方に回転されたことを示します。負の値は、ホイールが背面に回転していることを示します。</span><span class="sxs-lookup"><span data-stu-id="8df11-159">A positive value indicates that the wheel was rotated forward, away from the user; a negative value indicates that the wheel was rotated backward, toward the user.</span></span> <span data-ttu-id="8df11-160">ホイールクリックの1つは、120として定義されている WHEEL_DELTA として定義されています。</span><span class="sxs-lookup"><span data-stu-id="8df11-160">One wheel click is defined as WHEEL_DELTA, which is 120.</span></span> <span data-ttu-id="8df11-161">EventKind が CoreWebView2MouseEventKind XButtonDoubleClick CoreWebView2MouseEventKind Down または CoreWebView2MouseEventKind Up の場合、mouseData は、どの X ボタンが押されたか、離されたかを指定します。</span><span class="sxs-lookup"><span data-stu-id="8df11-161">If eventKind is CoreWebView2MouseEventKind.XButtonDoubleClick CoreWebView2MouseEventKind.XButtonDown, or CoreWebView2MouseEventKind.XButtonUp, then mouseData specifies which X buttons were pressed or released.</span></span> <span data-ttu-id="8df11-162">この値は、最初の X ボタンが押されている場合は1、2番目の X ボタンが押されたとき、または離された場合は1になります。</span><span class="sxs-lookup"><span data-stu-id="8df11-162">This value should be 1 if the first X button is pressed/released and 2 if the second X button is pressed/released.</span></span> <span data-ttu-id="8df11-163">EventKind が CoreWebView2MouseEventKind の場合は、virtualKeys、mouseData、point がすべてゼロである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8df11-163">If eventKind is CoreWebView2MouseEventKind.Leave, then virtualKeys, mouseData, and point should all be zero.</span></span> <span data-ttu-id="8df11-164">EventKind がその他の値である場合は、mouseData は0である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8df11-164">If eventKind is any other value, then mouseData should be zero.</span></span> <span data-ttu-id="8df11-165">Point は、WebView のクライアント座標空間に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8df11-165">Point is expected to be in the client coordinate space of the WebView.</span></span> <span data-ttu-id="8df11-166">WebView から始まり、WebView とホストアプリケーションの外側に移動する可能性のあるマウスイベントを追跡するには、SetCapture と ReleaseCapture の呼び出しをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8df11-166">To track mouse events that start in the WebView and can potentially move outside of the WebView and host application, calling SetCapture and ReleaseCapture is recommended.</span></span> <span data-ttu-id="8df11-167">ホバーポップアップを消すには、WM_MOUSELEAVE メッセージを送信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8df11-167">To dismiss hover popups, it is also recommended to send WM_MOUSELEAVE messages.</span></span>

#### <span data-ttu-id="8df11-168">Sendポインタ入力</span><span class="sxs-lookup"><span data-stu-id="8df11-168">SendPointerInput</span></span> 

<span data-ttu-id="8df11-169">Sendpointer Input は、CoreWebView2PointerEventKind で定義された型のタッチポインターまたはペンポインターの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="8df11-169">SendPointerInput accepts touch or pen pointer input of types defined in CoreWebView2PointerEventKind.</span></span>

> <span data-ttu-id="8df11-170">パブリック void [Sendポインタ入力](#sendpointerinput)([CoreWebView2PointerEventKind](./namespace-microsoft-web-webview2-core.md) eventType、 [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md)ポインター info)</span><span class="sxs-lookup"><span data-stu-id="8df11-170">public void [SendPointerInput](#sendpointerinput)([CoreWebView2PointerEventKind](./namespace-microsoft-web-webview2-core.md) eventType, [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) pointerInfo)</span></span>

<span data-ttu-id="8df11-171">システムからのポインター入力は、最初に CoreWebView2PointerInfo に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8df11-171">Any pointer input from the system must be converted into a CoreWebView2PointerInfo first.</span></span>

